# 03 · Kiểm kê LiDAR và biên bản nhà thuê (`RoomLedger`, mã `KKL`)

App quét phòng bằng LiDAR (RoomPlan) để có mặt bằng và diện tích m², ghi lại đồ đạc (ảnh, serial/model bằng OCR, giá trị, tình trạng), rồi xuất **biên bản nhận/trả nhà có dấu thời gian** và **báo cáo kiểm kê đồ đạc** cho bảo hiểm, chuyển nhà và tiền cọc. Mọi xử lý chạy trên máy. Xuất PDF và USDZ luôn miễn phí.

Tên mã `RoomLedger` chỉ dùng nội bộ. Quy ước ID, ưu tiên và ước tính theo [README chung](../README.md). Phần dùng chung lấy từ [lõi `SensorCore`](../shared-core.md) và không định nghĩa lại ở đây.

| File | Nội dung |
|---|---|
| [epics-features.md](epics-features.md) | 11 epic, 100 feature, ước tính, tiêu chí nghiệm thu, lộ trình sprint |
| [technical-design.md](technical-design.md) | Kiến trúc, mô hình dữ liệu, pipeline RoomPlan/ARKit, thuật toán, StoreKit, kiểm thử, spike |
| [backlog.csv](backlog.csv) | Danh sách feature để nhập Jira, Linear hoặc GitHub Projects |

## 1. Tóm tắt

- **Vấn đề:** người thuê và chủ nhà cần bằng chứng tình trạng nhà khi nhận và trả nhà; người có bảo hiểm nhà cần danh sách đồ đạc có ảnh, serial và giá trị. Công cụ hiện có hoặc là app vẽ mặt bằng cho thợ (magicplan, Polycam) với giá B2B, hoặc là app kiểm kê không có mặt bằng và chạy trên cloud.
- **Cơ hội:** Encircle đã bỏ app kiểm kê miễn phí cho người dùng phổ thông ngày 17/12/2025. Nghiên cứu không tìm thấy app phổ thông nào dùng LiDAR quét phòng cho mục đích kiểm kê. Từ khóa LiDAR/floor plan tăng nhanh nhất trong nhóm cảm biến.
- **Lời hứa:** "Quét phòng, ghi tình trạng, ký, xuất PDF. Không tài khoản, không cloud, không khóa file cũ."
- **Thiết bị:** RoomPlan cần LiDAR (iPhone 12 Pro – 18 Pro). Khoảng 65–75% iPhone đang dùng không có LiDAR (ước tính của báo cáo), gồm cả iPhone 17, 17e và Air. Các máy này dùng chế độ ảnh + đo AR + nhập kích thước tay, vẫn ra đủ biên bản.
- **Lịch:** xây trong 1–2/2027 (4 sprint 2 tuần), ra mắt đầu 3/2027 ở UK, DE, FR, NL. Đề xuất #6 của báo cáo (tiền khảo sát cải tạo và heat pump) thành module Pro ở V2.
- **Nguồn lực:** MVP riêng của app khoảng **45 ngày công** (lõi đã có). Vừa với **2 dev** trong 8 tuần; 1 dev thì phải lùi ra mắt 2–3 tuần hoặc cắt phạm vi (xem [lộ trình sprint](epics-features.md#lộ-trình-sprint)).

## 2. Người dùng mục tiêu và job-to-be-done

| Nhóm | Tình huống | Việc cần làm xong ("khi … tôi muốn … để …") | Đầu ra | Trả tiền? |
|---|---|---|---|---|
| Người thuê nhà (UK, DE, FR, NL) | Ngày nhận nhà, ngày trả nhà | Khi nhận nhà, tôi muốn ghi tình trạng từng phòng có ảnh, thời điểm và chữ ký hai bên, để khi trả nhà không bị trừ tiền cọc vô lý | Biên bản move-in / move-out PDF, gói ZIP có hash | Thường không (1 nhà miễn phí) |
| Chủ nhà nhỏ, đại lý cho thuê nhỏ | Nhiều nhà, nhiều lượt thuê | Khi đổi người thuê, tôi muốn lặp lại cùng một quy trình và mẫu PDF có thương hiệu, để tiết kiệm thời gian và có hồ sơ nhất quán | Biên bản theo mẫu nước, lịch sử thuê, so sánh move-in/move-out | Có: nhiều nhà, gói chủ nhà, mẫu thương hiệu |
| Chủ nhà hoặc người thuê có bảo hiểm nhà | Trước khi có sự cố | Khi mua đồ giá trị, tôi muốn lưu ảnh, serial, hóa đơn và giá, để khi mất trộm hay cháy có danh sách nộp bảo hiểm | Báo cáo kiểm kê PDF + CSV, mặt bằng | Có thể: thường 1 nhà |
| Người chuyển nhà | Trước và sau khi chuyển | Khi chuyển nhà, tôi muốn biết kích thước phòng và danh sách đồ, để sắp xếp đồ đạc và đối chiếu hư hỏng khi vận chuyển | Mặt bằng có kích thước, USDZ, danh sách đồ theo phòng | Thường không |
| Chủ nhà chuẩn bị cải tạo, lắp heat pump (V2) | Trước khi mời thợ báo giá | Khi mời thợ, tôi muốn gửi sẵn mặt bằng, kích thước cửa sổ và ảnh tem radiator, để thợ báo giá nhanh hơn | Gói tiền khảo sát PDF/CSV, IFC nếu spike đạt | Có (module Pro) – **cầu chưa được kiểm chứng** |

Ngoài ra ghi chú nghiên cứu nêu chủ nhà cho thuê ngắn hạn là nhóm phụ. Chưa có số liệu về tranh chấp tiền cọc ở UK hay EU; đây là khoảng trống dữ liệu.

## 3. Định vị và khác biệt

**Câu định vị:** biên bản nhà thuê và kiểm kê đồ đạc có mặt bằng LiDAR, xử lý 100% trên iPhone, **xuất PDF và USDZ miễn phí**, dữ liệu cũ không bao giờ bị khóa.

Chiêu "xuất miễn phí, thu tiền cho quy trình" đánh vào hai lời phàn nàn cảm xúc nhất của mảng này:
- Polycam bị chê "tăng giá hơn gấp đôi cho cùng tính năng"; bản miễn phí chỉ xuất GLTF.
- Người dùng magicplan than bị khóa khỏi bản vẽ làm trong 3–4 năm và gặp sai số 6–8 inch.

Số liệu dưới lấy từ báo cáo và ghi chú nghiên cứu (iTunes Lookup API, Apple RSS, ngày 27/9/2026). EU-7 gồm GB, DE, FR, IT, ES, NL, PL.

| App | Trọng tâm | Lượt đánh giá US / EU-7 | Top grossing | Giá | Điểm yếu mình khai thác | Khác biệt của `RoomLedger` |
|---|---|---|---|---|---|---|
| Polycam | Quét 3D, splat, floor plan; chuyển sang tài liệu cho xây dựng, bảo hiểm | 43.579 / 32.664 | Photo & Video: US #89, GB #58, DE #53, FR #42 | Basic $149.99/năm (DE 179,99 €); Business $400/người/năm (web) | Bản miễn phí chỉ xuất GLTF; tăng giá | Xuất PDF + USDZ miễn phí; đầu ra là biên bản, không phải mô hình 3D |
| magicplan | Floor plan chuyên nghiệp, ước tính cho thợ, bảo hiểm | 41.136 / 46.430 (DE 14.719) | Productivity: DE #49, FR #64 | $129.99–$899.99/năm, cùng chữ số ở £/€; miễn phí tối đa 2 dự án | Bị khóa bản vẽ cũ; giá B2B | Không bao giờ khóa dữ liệu cũ (nhà vượt hạn mức vẫn xem và xuất được) |
| CamToPlan (+ PRO, + LiDAR) | Đo AR và vẽ mặt bằng | 16.608 / 16.005 (FR 6.026) | Utilities FR #86 | $4.99–$49.99 một lần; bản LiDAR $49.99 | Công cụ đo, không có quy trình biên bản | Checklist tình trạng, chữ ký, mẫu theo nước |
| RoomScan Pro LiDAR | Floor plan (RoomPlan, Touch Mode) cho thợ | 2.115 / 1.227 | Không lọt top 100 | $119.99/năm (€119,99) | Nhắm thợ; xuất ESX, IFC, DXF | Nhắm người thuê và chủ nhà nhỏ, giá thấp hơn nhiều |
| Encircle (app phổ thông) | Kiểm kê nhà | – | – | – | **Đã ngừng 17/12/2025** để tập trung vào nhà thầu phục hồi | Lấp khoảng trống; không cần tài khoản |
| HomeProof, Vorby, Scanlily, Kept; Sortly | Kiểm kê nhà (mới 2026); Sortly thiên doanh nghiệp | – | – | – | Dựa trên tài khoản cloud; không có quét phòng LiDAR | Mặt bằng LiDAR + on-device |

Ở Đức, mảng vẽ mặt bằng bằng LiDAR đã có ít nhất 5 app phổ thông (WohnScanner, Grundriss 3D, Room Scanner Pro, Grundrissplan, magicplan). Vì vậy `RoomLedger` không định vị là "app vẽ mặt bằng" hay "3D scanner" chung chung (tránh cả Guideline 4.3), mà là **quy trình biên bản và kiểm kê** có mặt bằng đi kèm.

**Không làm:** tuyên bố đo đạc chính thức; tuyên bố biên bản có giá trị pháp lý thay cho luật địa phương; tính diện tích ở theo quy tắc từng nước (như WoFlV ở Đức ⚠); tính tải nhiệt theo DIN EN 12831 hay MCS; lưu dữ liệu trên server.

## 4. Phạm vi theo bản

Chi tiết từng feature ở [epics-features.md](epics-features.md). Số ngày là ngày công dev, chưa gồm thiết kế UI, dịch thuật và rà soát nội dung pháp lý của mẫu biên bản.

| Bản | Ngày công | Nội dung chính |
|---|---|---|
| **MVP** (ra mắt đầu 3/2027) | 45 | Nhà → phòng → đợt kiểm tra; quét RoomPlan từng phòng, diện tích m² từ đa giác sàn; màn xem lại; chế độ không LiDAR (ảnh + đo AR 2 điểm + nhập tay); item có ảnh, OCR serial/model, giá trị, hóa đơn; checklist tình trạng theo phòng, ảnh lỗi chú thích PencilKit, chỉ số đồng hồ, chìa khóa, chữ ký hai bên; manifest SHA-256 in trong PDF; mẫu biên bản UK/DE/FR/NL; báo cáo kiểm kê; xuất PDF, USDZ, CSV, ZIP miễn phí; paywall theo số nhà (gói năm + slot mua một lần); dự án mẫu cho App Review; benchmark độ chính xác |
| **V1.1** (8 tuần sau ra mắt, theo dữ liệu) | 37 | So sánh move-in/move-out và PDF trước/sau; tạo move-out từ move-in; mẫu PDF có thương hiệu; sửa kích thước đã quét; quét nhiều phòng + mặt bằng toàn căn (sau spike); gợi ý item từ đồ vật RoomPlan; OCR đồng hồ; lưu trữ `.roomledger`; làm mờ mặt người; gói chủ nhà, gói tháng/trọn đời |
| **V2** (sau khi đạt tiêu chí "đẩy mạnh") | 33 | Module Pro tiền khảo sát cải tạo (bảng cửa sổ/cửa, OCR tem radiator, diện tích sàn, PDF/CSV, IFC nếu spike đạt); nhận hóa đơn từ app 01 qua App Group ⚠; ký trên thiết bị thứ hai; ghi chú giọng nói; SVG/DXF; đồng bộ iCloud ⚠; IT, ES |

## 5. Số liệu thị trường

Mọi số dưới đây lấy từ [báo cáo](../../reports/App%20iPhone%20offline%20d%C3%B9ng%20c%E1%BA%A3m%20bi%E1%BA%BFn.md), [kế hoạch 12 tháng](../../reports/K%E1%BA%BF%20ho%E1%BA%A1ch%20top%205%20app%20iOS.md) và ghi chú nghiên cứu. Mảng LiDAR/3D **không có ước tính tải hay doanh thu công khai**; chỉ dùng được lượt đánh giá và thứ hạng.

**Cầu tìm kiếm Google US (thay đổi 2 năm; mức nền đối chứng +62%):**

| Từ khóa | Volume US/tháng (quy đổi) | Δ 2 năm | Nhận định |
|---|---|---|---|
| lidar app | 1–3K | +475% | Tăng rất nhanh |
| floor plan app | 1–3K | +238% | Tăng rất nhanh |
| room scanner | 1–3K | +129%\* | Tăng (spike-inflated) |
| lidar scanner | 3–8K | +140% | Tăng, một phần do game Arc Raiders |
| measure app | 8–20K | +100% | Ngang nền, khớp rộng |

\* spike-inflated: đỉnh tháng 4–6/2026 cao gấp 3 lần trở lên so với trung vị trước đó.

**EU (Google Trends, Δ 2 năm):** nhóm 3D tăng ở cả sáu thị trường ưu tiên: UK "3d scanner app" +55%, DE "3D Scanner App" +46%, FR "scanner 3d" +43%, IT "scanner 3d" +44%, NL "3d scanner" +82%, ES "escáner 3d" +222% (nền rất thấp). Nhóm "đo" cũng tăng: UK "measure app" +62%, NL "meet app" +102%.

**Autocomplete App Store:** US "lidar room scanner", "room scan lidar", "floor plan scanner"; DE "lidar scanner 3d", "3d scan lidar", "entfernung messen"; FR "lidar plan", "lidar scanner 3d gratuit", "mesurer distance"; NL "meten met camera", "afstand meten". Từ "free/kostenlos/gratuit/gratis" xuất hiện ở mọi thị trường.

**Mùa vụ:** từ khóa 3D/LiDAR đạt đỉnh tháng 11–12 (mùa iPhone mới). Ra mắt tháng 3 nằm ngoài đỉnh này; nhu cầu biên bản nhà thuê gắn với lịch chuyển nhà, chưa có dữ liệu mùa vụ riêng.

**Thiết bị và nền tảng:**
- LiDAR chỉ có trên iPhone 12 Pro – 18 Pro; khoảng 25–35% iPhone đang dùng (ước tính, dựa trên tỷ lệ dòng Pro 38% doanh số Mỹ quý 1/2025).
- Tỷ lệ iOS trên web di động (StatCounter, 8/2026): UK khoảng 51%; DE, ES, NL, PL khoảng 27–31%.
- iOS 26 chạy trên 79% iPhone (Apple, 6/2026); app đặt mức tối thiểu iOS 26.

**Kinh tế quảng cáo (kế hoạch 12 tháng, mục 5):** ở NL (CPA Apple Ads $1.07, VAT 21%) với giá $39.99/năm, chi phí có 1 người trả tiền là $53,50 ở freemium 2,0% và $10,00 ở hard paywall 10,7%; tiền thực nhận năm đầu $28,09. Vậy chỉ hoàn vốn quảng cáo khi chuyển đổi gần mức hard paywall. Ngân sách thử Apple Ads khoảng 300 lượt chạm mỗi thị trường: UK ≈ $393, DE ≈ $258, FR ≈ $225, NL ≈ $195, tổng ≈ $1.070. Apple Ads không nhắm được theo model máy, nên một phần ngân sách sẽ rơi vào người dùng không có LiDAR; chế độ dự phòng phải đủ tốt để họ không gỡ app.

## 6. Mô hình giá (tóm tắt)

Giá là **suy luận của báo cáo**, cần kiểm chứng sau ra mắt.

| | Miễn phí | Trả phí |
|---|---|---|
| Số bất động sản | 1 (dự án mẫu không tính) | Nhiều |
| Quét, đo, item, biên bản, chữ ký | Đầy đủ | Đầy đủ |
| Xuất PDF, USDZ, CSV, ZIP | **Miễn phí, không watermark** | Miễn phí |
| Mẫu PDF có thương hiệu, công cụ chủ nhà (lịch sử thuê, xuất hàng loạt) | – | Có |
| Giá | – | Khoảng **€14,99 / nhà, mua một lần** (slot không tiêu hao) hoặc khoảng **€39,99 / năm** (không giới hạn nhà, trial 7 ngày) |

Mua "theo nhà một lần" có rủi ro App Review về loại IAP (consumable hay non-consumable) ⚠. Đề xuất: bán **slot bất động sản dạng non-consumable đánh số** (`kkl.property.slot.01` … `.10`), khôi phục được, gán cho nhà ngay trên máy. Phân tích đầy đủ ở [technical-design.md mục 10](technical-design.md#10-storekit). Dù hết hạn gói hay hoàn tiền, nhà vượt hạn mức chỉ chuyển sang chỉ đọc: vẫn xem và xuất được.

## 7. KPI 8 tuần sau ra mắt

| KPI | Ngưỡng | Nguồn ngưỡng | Cách đo |
|---|---|---|---|
| Phiên quét hoàn tất ít nhất một phòng | ≥ 60% | Mục tiêu nội bộ (kế hoạch) | Bộ đếm cục bộ (KKL-E02-03). App không gửi dữ liệu, nên đo trên nhóm TestFlight trước ra mắt và qua thống kê người dùng tự nguyện gửi (KKL-E11-05, V1.1) ⚠ |
| Tải → trả tiền (D35) | ≥ 2,0% | RevenueCat 2026, trung vị freemium Tây Âu | App Store Connect (Sales and Trends, Analytics) |
| Doanh thu mỗi lượt cài ngày 14 (RPI D14) | ≥ $0,25 | RevenueCat 2026, Tây Âu | Ước lượng từ proceeds / lượt cài theo tuần trong App Store Connect; không có cohort chính xác vì không dùng SDK ⚠ |
| Trial → trả tiền | ≥ 29,7% | RevenueCat 2026, Tây Âu | App Store Connect (subscription reports) |
| Hoàn tiền | < 3% | Kế hoạch | App Store Connect |
| Sai số đo LiDAR so với máy đo laser | Công bố theo benchmark; mục tiêu P95 chiều dài tường ≤ 3 cm ⚠ | Mục tiêu nội bộ | `room-bench` trên N ≥ 12 phòng (KKL-E11-02) |

Quyết định sau 8 tuần theo bảng ở kế hoạch 12 tháng, mục 6: **đẩy mạnh** khi RPI D14 ≥ $0,25 và chi phí có 1 người trả tiền thấp hơn tiền thực nhận năm đầu (mở V2 và bản địa hóa đợt 2); **sửa** khi RPI D14 từ $0,10 đến $0,25 (A/B bản dịch paywall trước, rồi thử paywall cứng hơn cho nhà thứ 2); **dừng đầu tư** khi RPI D14 dưới $0,10 sau hai vòng ASO.

## 8. Rủi ro chính

| Rủi ro | Ảnh hưởng | Cách xử lý |
|---|---|---|
| Chỉ khoảng 25–35% máy có LiDAR; Apple Ads không nhắm theo model máy | Nhiều người tải về không có tính năng chính | Chế độ ảnh + đo AR + nhập tay vẫn ra đủ biên bản; ảnh chụp màn hình nói rõ "LiDAR trên iPhone Pro, máy khác đo bằng AR" |
| Mẫu biên bản không đúng yêu cầu pháp lý từng nước (đặc biệt FR état des lieux) ⚠ | Mất niềm tin, đánh giá xấu | Rà soát nội dung mẫu với người có chuyên môn ở từng nước trước ra mắt; disclaimer "không thay tư vấn pháp lý" |
| App Review từ chối slot "theo nhà" | Trễ ra mắt | Hỏi App Review trong sprint 1; phương án B là chỉ bán gói năm lúc ra mắt |
| Sai số đo bị hiểu là đo chính thức | Khiếu nại, đánh giá 1 sao | Benchmark công khai dung sai; nhãn nguồn số đo; không tuyên bố "chính xác đến mm" (Guideline 2.3.1) |
| Đồng hồ máy có thể bị chỉnh; không có dấu thời gian tin cậy khi offline | Giá trị chứng cứ của "dấu thời gian" bị giới hạn | Nói rõ trong app; manifest SHA-256 chứng minh tính toàn vẹn sau khi xuất; gợi ý gửi mã xác minh cho bên kia ngay khi ký |
| Mảng vẽ mặt bằng ở Đức đã đông | Khó xếp hạng từ khóa "floor plan" | ASO theo việc cần làm ("Wohnungsübergabeprotokoll", "état des lieux", "inventory report") thay vì "scanner" |
| Dữ liệu chỉ nằm trên máy | Mất máy là mất biên bản | Dữ liệu có trong backup iCloud/Finder của máy (lõi); xuất ZIP mỗi lần ký; lưu trữ `.roomledger` ở V1.1 |
| V1.1 trùng lúc xây app 02 (3–4/2027) | V1.1 chậm | Ưu tiên V1.1 theo thứ tự ở lộ trình sprint; chỉ làm phần dữ liệu ủng hộ |
| KPI hoàn tất phiên quét khó đo khi không có analytics | Quyết định dựa trên mẫu nhỏ | TestFlight ≥ 30 người có máy LiDAR; thống kê tự nguyện ở V1.1 ⚠ |

## 9. Liên kết

- [README chung](../README.md), [lõi `SensorCore`](../shared-core.md), [backlog lõi](../shared-core-backlog.csv)
- [Báo cáo: App iPhone offline dùng cảm biến](../../reports/App%20iPhone%20offline%20d%C3%B9ng%20c%E1%BA%A3m%20bi%E1%BA%BFn.md) – mục "LiDAR và 3D sống nhờ khách hàng chuyên nghiệp", "Sáu sản phẩm nên xây"
- [Kế hoạch top 5 app iOS](../../reports/K%E1%BA%BF%20ho%E1%BA%A1ch%20top%205%20app%20iOS.md) – mục "App 3 · Kiểm kê LiDAR và biên bản nhà thuê"
- Ghi chú nghiên cứu: `research_notes/App iPhone offline dùng cảm biến/` – `lidar_3d_ar_apps.md`, `apple_ondevice_tech_and_review.md`, `niche_opportunities.md`, `europe_market_optimization.md`, `keyword_search_demand.md`
