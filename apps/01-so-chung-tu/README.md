# Sổ chứng từ riêng tư (`ReceiptBook`, mã `SCT`)

App iPhone chụp và nhận hóa đơn, biên lai, hóa đơn điện tử; trích xuất trường; phân loại; xuất theo kỳ cho kế toán. Mọi xử lý chạy trên máy, không có server, không có tài khoản.

Đọc trước: [quy ước chung](../README.md) và [lõi dùng chung `SensorCore`](../shared-core.md). Tài liệu này chỉ mô tả phần riêng của app. Phần lõi (chụp, OCR, khung trích xuất, lưu trữ, xuất file, paywall, khóa Face ID) được tham chiếu bằng mã `CORE-…`, không định nghĩa lại.

## Tóm tắt

- **Lời hứa:** "Chứng từ của bạn không rời iPhone." Ở Đức, WISO lưu chứng từ trên server, còn SteuerGO gửi dữ liệu sang OpenAI ở Mỹ.
- **Người dùng:** người làm tự do, chủ nhà cho thuê và doanh nghiệp siêu nhỏ ở Anh (Making Tax Digital), Đức (Belege, Kleinunternehmer, nhận E-Rechnung), Pháp (notes de frais) và người dùng tiếng Anh ở Mỹ. Chế độ Việt Nam cho hộ kinh doanh là `V1.1`.
- **Không nhắm** người làm công ăn lương ở Đức, vì họ đã có MeinElster+ miễn phí và chính thức.
- **App xuất file, không nộp thuế.** App không nộp dữ liệu cho HMRC và không bao giờ tuyên bố được HMRC công nhận. Người dùng đưa file xuất vào phần mềm tương thích MTD hoặc gửi cho kế toán.
- **Thu tiền cho đầu ra.** Chụp, lưu, xem, tìm và xuất PDF từng chứng từ luôn miễn phí. Gói Pro mở xuất theo kỳ cho kế toán (CSV, PDF kỳ, ZIP) và tự phân loại. Nhiều hồ sơ doanh nghiệp vào Pro ở `V1.1`.
- **Khối lượng:** 87 feature. MVP 50 ngày công, `V1.1` 52,5 ngày, `V2` 22,5 ngày. Lõi MVP khoảng 42 ngày tính riêng.
- **Lịch:** xây từ 28/9 đến 27/11/2026, nộp App Store ngày 1/12, phát hành dự kiến 8/12/2026. Cần **2 dev iOS toàn thời gian**; 1 dev không kịp mùa thuế (xem [Lộ trình sprint](epics-features.md#lộ-trình-sprint)).

## Tài liệu trong thư mục

| File | Nội dung |
|---|---|
| [epics-features.md](epics-features.md) | 12 epic, 87 feature, ưu tiên, ước tính, tiêu chí nghiệm thu, tổng theo ưu tiên, lộ trình sprint |
| [technical-design.md](technical-design.md) | Kiến trúc, module, mô hình dữ liệu, pipeline, thuật toán, màn hình, thiết bị, bản địa hóa, tuân thủ, StoreKit, hiệu năng, kiểm thử, spike |
| [backlog.csv](backlog.csv) | Toàn bộ feature dạng CSV, cùng cột với [shared-core-backlog.csv](../shared-core-backlog.csv) |
| [../shared-core.md](../shared-core.md) | Lõi `SensorCore` mà app này dùng lại |

## Người dùng mục tiêu và việc cần làm

| Thị trường | Người dùng | Việc cần làm (job-to-be-done) | Bối cảnh quy định (nguồn) |
|---|---|---|---|
| Anh (UK) | Sole trader và landlord có thu nhập trên ngưỡng MTD | "Khi nhận biên lai, tôi muốn ghi lại ngay trên điện thoại, để cuối quý đưa số liệu đúng danh mục vào phần mềm MTD hoặc gửi kế toán mà không phải gõ lại." | MTD áp dụng từ 6/4/2026 cho thu nhập trên £50K; ngưỡng hạ xuống £30K năm 2027 và £20K năm 2028. Phải giữ sổ số, nộp cập nhật theo quý qua phần mềm tương thích HMRC (ví dụ FreeAgent, QuickBooks, Xero). Không bắt buộc giữ bản số của biên lai nếu dữ liệu đã ghi số ([niche_opportunities.md](../../research_notes/App%20iPhone%20offline%20d%C3%B9ng%20c%E1%BA%A3m%20bi%E1%BA%BFn/niche_opportunities.md), mục Key Question 4) |
| Đức (DE) | Freiberufler, Kleinunternehmer, chủ nhà cho thuê | "Khi hóa đơn điện tử đến qua email hoặc khi cầm Beleg giấy, tôi muốn lưu đúng bản gốc và có danh sách theo quý cho Steuerberater, mà không đưa dữ liệu lên cloud." | Từ 1/1/2025 mọi doanh nghiệp, kể cả Kleinunternehmer (§19 UStG), phải nhận được e-invoice (XRechnung, ZUGFeRD, EN 16931). PDF và giấy không còn được tính là e-invoice. Phải lưu trữ theo cách không sửa được, thực tế cần công cụ. Có quy tắc GoBD cho "ersetzendes Scannen" ([niche_opportunities.md](../../research_notes/App%20iPhone%20offline%20d%C3%B9ng%20c%E1%BA%A3m%20bi%E1%BA%BFn/niche_opportunities.md)) |
| Pháp (FR) | Indépendant, micro-entrepreneur ⚠ cần xác minh phạm vi | "Tôi muốn gom notes de frais và hóa đơn trong tháng hoặc quý, rồi gửi một gói gọn cho expert-comptable." | Báo cáo chỉ nêu nhu cầu "notes de frais". Mốc cải cách hóa đơn điện tử ở Pháp chưa có trong ghi chú nghiên cứu ⚠ cần xác minh. Factur-X cùng họ kỹ thuật với ZUGFeRD nên dùng chung parser |
| Mỹ (EN-US) | Người tự làm chủ dùng tiếng Anh | "Tôi muốn có file biên lai theo quý và cả năm để kế toán khai thuế." | Chi tiết danh mục thuế Mỹ không có trong ghi chú ⚠ cần xác minh. EN-US chủ yếu để phủ locale và storefront Mỹ |
| Việt Nam (`V1.1`) | Hộ kinh doanh | "Từ khi bỏ thuế khoán, tôi cần sổ thu chi và lưu hóa đơn để tự kê khai." | Thuế khoán kết thúc 1/1/2026; hộ kinh doanh kê khai dựa trên hóa đơn điện tử, eTax Mobile và dòng tiền ngân hàng. Ghi chú nêu phải có sổ khi doanh thu từ 500 triệu đồng, nên dùng hóa đơn điện tử khi trên 1 tỷ đồng (nguồn báo chí, ⚠ cần xác minh văn bản gốc) |

**Không nhắm:** người làm công ăn lương ở Đức (MeinElster+ miễn phí, chính thức, cho gom biên lai cả năm). Không làm phần mềm kế toán đầy đủ và không nộp tờ khai.

## Định vị và khác biệt

Câu định vị: **"Chứng từ của bạn không rời iPhone."** Ảnh chụp màn hình đầu tiên nêu lời hứa bằng ngôn ngữ địa phương, ví dụ "100% offline – keine Daten verlassen dein iPhone" ([kế hoạch 12 tháng](../../reports/K%E1%BA%BF%20ho%E1%BA%A1ch%20top%205%20app%20iOS.md), mục 8).

| Đối thủ | Dữ liệu nằm ở đâu | Số liệu | Khác biệt của SCT | Nguồn |
|---|---|---|---|---|
| WISO Steuer (Buhl) | "TÜV-certified servers in Germany" | n/a | Chứng từ ở lại trên máy | [niche_opportunities.md](../../research_notes/App%20iPhone%20offline%20d%C3%B9ng%20c%E1%BA%A3m%20bi%E1%BA%BFn/niche_opportunities.md) |
| SteuerGO IntelliScan | Gửi dữ liệu "once and encrypted to OpenAI (USA)" | n/a | Trích xuất bằng Vision và Foundation Models trên máy | như trên |
| MeinElster+ | App chính thức, miễn phí | n/a | Không cạnh tranh: SCT nhắm người tự kinh doanh, có xuất theo kỳ và e-invoice | như trên |
| Genius Scan | Xử lý on-device | $300k/tháng (Sensor Tower, iOS toàn cầu, T8/2026); Ultra $39.99/năm, 44,99 € ở DE | Genius Scan là máy quét chung. SCT có trường thuế, VAT nhiều bậc, danh mục theo nước, kỳ báo cáo, đọc XRechnung/ZUGFeRD | [báo cáo](../../reports/App%20iPhone%20offline%20d%C3%B9ng%20c%E1%BA%A3m%20bi%E1%BA%BFn.md), mục "Offline tạo niềm tin" và "Giá theo storefront" |
| Dext | Cloud | 10k lượt tải, $80k/tháng; Business $12.99/tháng; #25 Business grossing ở UK | Không cần cloud, giá năm thấp hơn | [camera_ocr_vision_apps.md](../../research_notes/App%20iPhone%20offline%20d%C3%B9ng%20c%E1%BA%A3m%20bi%E1%BA%BFn/camera_ocr_vision_apps.md) |
| Expensify | Cloud | 10k lượt tải, $40k/tháng; $4.99/tháng | Hướng tới người tự kinh doanh, không phải báo cáo chi phí nhân viên | như trên |
| CamScanner, iScanner | CamScanner n/a; iScanner offline, sync cần mạng | CamScanner $8M, iScanner $4M/tháng | Hai app này bán tính năng quét chung và gói tuần. SCT bán quy trình thuế, không có gói tuần ở EU | [báo cáo](../../reports/App%20iPhone%20offline%20d%C3%B9ng%20c%E1%BA%A3m%20bi%E1%BA%BFn.md) |
| Xero, QuickBooks, FreeAgent | Cloud | n/a | Đây là phần mềm kế toán đầy đủ (suy luận của ghi chú). SCT là cầu nối "chụp → phân loại → xuất" vào các phần mềm này | [niche_opportunities.md](../../research_notes/App%20iPhone%20offline%20d%C3%B9ng%20c%E1%BA%A3m%20bi%E1%BA%BFn/niche_opportunities.md) |

Ba điểm khác biệt phải thể hiện được trong Review Notes (Guideline 4.3):
1. Quy trình dọc có đầu ra riêng: gói xuất theo kỳ cho kế toán, không phải "thêm một app quét PDF".
2. Đọc hóa đơn điện tử Đức (XRechnung UBL/CII, ZUGFeRD) và Pháp (Factur-X) mà không cần server.
3. Chạy trên mọi iPhone iOS 26. Foundation Models chỉ là lớp nâng cấp.

## Phạm vi

Chi tiết từng feature ở [epics-features.md](epics-features.md).

**MVP (50 ngày công, ra mắt đầu 12/2026)**
- Onboarding không tài khoản: quốc gia, loại hình, cài đặt VAT, năm thuế.
- Chụp bằng VisionKit; nhập ảnh, PDF, XML từ Photos và Files; Share Extension nhận file từ Mail.
- Trích xuất: người bán, ngày, tổng, net, VAT nhiều bậc, tiền tệ, số hóa đơn, phương thức thanh toán; độ tin cậy từng trường; màn xem lại và sửa.
- Hóa đơn điện tử: XRechnung UBL và CII, XML nhúng trong ZUGFeRD/Factur-X (sau spike), bản xem đọc được, kiểm tra cơ bản.
- Phân loại theo danh mục của từng nước: luật, học từ sửa đổi, Foundation Models trên máy hỗ trợ.
- Kỳ báo cáo theo nước; xuất PDF một chứng từ (miễn phí); CSV, PDF kỳ, ZIP kèm manifest SHA-256 (Pro).
- Bản gốc bất biến, audit log, xóa mềm, khóa Face ID; xuất toàn bộ bản gốc miễn phí và xóa toàn bộ dữ liệu.
- Paywall tuân thủ, 3 sản phẩm, 4 locale (EN-US, EN-GB, DE, FR).

**`V1.1` (52,5 ngày, là danh sách chọn theo dữ liệu, không phải cam kết)**
- Nhiều hồ sơ doanh nghiệp, thẻ bất động sản cho landlord.
- Mẫu xuất cho Xero, QuickBooks, FreeAgent, DATEV, lexoffice, sevDesk (định dạng ⚠ cần xác minh).
- Học theo người bán, dòng hàng, ngoại tệ, tách danh mục, khoản thu.
- Sao lưu mã hóa, kiểm tra toàn vẹn, nhắc thời hạn lưu trữ ⚠, đồng bộ CloudKit tùy chọn ⚠.
- Spotlight, App Intents, widget, Camera Control/Visual Intelligence ⚠.
- Offer code, win-back, A/B paywall bằng product ID.
- **Chế độ Việt Nam:** OCR `vi-VT`, hóa đơn điện tử VN ⚠, sổ thu chi hộ kinh doanh ⚠, giá VND.

Sau ra mắt, hai dev chuyển sang app 03 trong tháng 1–2/2027 theo kế hoạch 12 tháng. Vì vậy thực tế chỉ làm được khoảng 15–20 ngày `V1.1` trước đó. Thứ tự đề xuất ở [epics-features.md](epics-features.md#tổng-theo-ưu-tiên).

**`V2` (22,5 ngày):** gói AT/CH, chụp từ màn hình khóa, IT/ES/NL, kiểm tra quy tắc EN 16931, cải cách e-invoice Pháp ⚠, xuất `.xlsx`, so sánh Foundation Models iOS 27.

## Gói và giá

| Sản phẩm | Loại | Giá khởi điểm đề xuất | Ghi chú |
|---|---|---|---|
| `sct.pro.yearly` | Thuê bao năm, trial 7 ngày | $39.99 / £39.99 / 39,99 € | Nằm trong dải $/£/€29.99–49.99 của kế hoạch; trung vị năm ở Tây Âu $39.44 |
| `sct.pro.monthly` | Thuê bao tháng | $9.99 / £9.99 / 9,99 € | Trung vị tháng ở Tây Âu $9.99 |
| `sct.pro.lifetime` | Mua một lần | 49,99 € (DE, AT); CH ⚠ | Chỉ hiện ở storefront nói tiếng Đức; dải €39–59 của kế hoạch |
| VN (`V1.1`) | Năm và tháng | 299.000₫/năm, 49.000₫/tháng | Trong dải 49.000–499.000₫ |

Không có gói tuần ở EU. Không dùng toggle trên paywall. Chi tiết và lý do ở [technical-design.md §10](technical-design.md#10-storekit).

## Số liệu thị trường

Mọi số dưới đây lấy từ [báo cáo](../../reports/App%20iPhone%20offline%20d%C3%B9ng%20c%E1%BA%A3m%20bi%E1%BA%BFn.md) (dữ liệu ngày 27/9/2026), [kế hoạch 12 tháng](../../reports/K%E1%BA%BF%20ho%E1%BA%A1ch%20top%205%20app%20iOS.md) hoặc ghi chú nghiên cứu. Doanh thu Sensor Tower là ước tính toàn cầu, chỉ iOS, tháng 8/2026.

| Chỉ số | Giá trị | Nguồn |
|---|---|---|
| Bể doanh thu quét tài liệu/OCR | Khoảng $22,1M/tháng, 19 app | Báo cáo, mục "Hai mươi lăm app camera" |
| Phân khúc "receipt scan" | 3 app, $170k/tháng | camera_ocr_vision_apps.md |
| Người chịu MTD từ 4/2026 | Khoảng 864.000 sole trader và landlord | niche_opportunities.md (ByteStart) |
| Ngưỡng MTD | £50K (2026), £30K (2027), £20K (2028) | như trên |
| Nghĩa vụ nhận e-invoice ở Đức | Từ 1/1/2025, gồm cả Kleinunternehmer | như trên (BMF) |
| Người châu Âu muốn ưu tiên quyền riêng tư | 92% | Báo cáo (Eurobarometer 2025) |
| Tìm kiếm Google (Mỹ, 2 năm) | "scan to pdf" 8–20K/tháng, +186% (bị thổi phồng bởi đỉnh 2026); "ocr app" +643%; "pdf scanner app" +153%; "receipt scanner" +20%, dưới mức nền | Báo cáo; keyword_search_demand.md |
| Mùa vụ | "receipt scanner" (1–3K lượt/tháng ở Mỹ) và nhóm quét chứng từ đạt đỉnh tháng 1–2, mùa thuế | keyword_search_demand.md |
| Tìm kiếm ở Đức | "Dokumente scannen" +23% (ngang); "Belege scannen" không có dữ liệu | Báo cáo |
| Độ khó head term | KD 82 | Báo cáo |
| Thị phần iOS (StatCounter, 8/2026) | UK 51,47%; FR 36,26%; DE 27,54% | Báo cáo |
| Apple Ads CPT / CPA | UK $1.31 / $2.02; DE $0.86 / $1.34; FR $0.75 / $1.11 | Báo cáo (Adapty) |
| Hoàn vốn Apple Ads năm đầu, gói $39.99 | DE: 43% (freemium 2,0%) / 228% (hard 10,7%); UK: 28% / 150% | Kế hoạch, mục 5 |
| Chuẩn Tây Âu | Tải → trả tiền D35 2,0%; trial → trả tiền 29,7%; RPI D14 $0.25; hoàn tiền dưới 3% | Báo cáo (RevenueCat 2026) |
| Danh mục Business | Tải → trial 9,1%; tải → trả tiền 2,6%; RPI D14 $0.31 | như trên |
| Độ dài trial | 5–9 ngày: 37,4% trial → trả tiền; ≤4 ngày: 25,5% | như trên |
| Việt Nam | RPI D14 khối IN/SEA $0.08; hoàn tiền 7,7%; Apple 18% máy xuất xưởng Q1/2025 | Báo cáo |
| Thiết bị có Apple Intelligence | Khoảng 35–50% iPhone đang dùng (ước tính của báo cáo) | Báo cáo |

Hệ quả: cầu tìm kiếm cho "receipt scanner" yếu, nên nhu cầu dựa vào quy định và điểm yếu đối thủ. Apple Ads chỉ nên chạy khi tỷ lệ chuyển đổi tiến gần mức hard paywall. Ngân sách thử của kế hoạch cho UK, DE, FR là khoảng $393 + $258 + $225 ≈ $876 (tính từ bảng ở mục 6 của kế hoạch).

## KPI 8 tuần sau ra mắt

App không có SDK analytics và không tự thu sự kiện. Mọi KPI đo bằng App Store Connect (Sales, Subscriptions, App Analytics của người dùng đồng ý chia sẻ ⚠ cần xác minh phạm vi) và báo cáo Apple Ads.

| KPI | Ngưỡng | Loại | Đo bằng |
|---|---|---|---|
| Tải → trả tiền trong 35 ngày | ≥ 2,0% | Chuẩn Tây Âu (RevenueCat 2026) | App Store Connect |
| RPI ngày 14 | ≥ $0.25 | Chuẩn Tây Âu | App Store Connect |
| Trial → trả tiền | ≥ 29,7% | Chuẩn Tây Âu | App Store Connect Subscriptions |
| Hoàn tiền | < 3% | Chuẩn Tây Âu | App Store Connect |
| Độ chính xác tổng tiền trên bộ dữ liệu vàng | ≥ 92% chỉ dùng luật | Mục tiêu nội bộ | `ocr-bench` trong CI |
| Tỷ lệ phiên không crash | ≥ 99,5% | Mục tiêu nội bộ | Xcode Organizer |

Quyết định theo mục 6 của kế hoạch:
- **Đẩy mạnh:** RPI D14 ≥ $0.25 và chi phí có 1 người trả tiền thấp hơn tiền thực nhận năm đầu → tăng Apple Ads ở storefront đạt, mở bản địa hóa đợt 2.
- **Sửa:** RPI D14 từ $0.10 đến $0.25 → A/B bản dịch paywall trước, rồi giá, rồi thử hard paywall ở bước xuất.
- **Dừng đầu tư:** RPI D14 dưới $0.10 sau hai vòng ASO → bảo trì, chuyển nguồn lực sang app 03.

## Rủi ro chính

| Rủi ro | Ảnh hưởng | Cách xử lý |
|---|---|---|
| Lõi và app cần khoảng 92 ngày công trong 10 tuần | Lỡ mùa thuế tháng 1–2 | 2 dev từ 28/9; cut-line khoảng 4,5 ngày; phương án B ra UK/EN-US trước, DE/FR ở 1.0.1 (xem [lộ trình](epics-features.md#lộ-trình-sprint)) |
| Cầu "receipt scanner" yếu, "Belege scannen" không có dữ liệu | Ít lượt tải tự nhiên | Chạy Keyword Planner trước khi chốt metadata; Apple Ads exact match theo storefront |
| Tuyên bố pháp lý sai (HMRC, GoBD, tư vấn thuế) | Bị từ chối review, rủi ro pháp lý | Disclaimer cố định, kiểm tra chuỗi trong CI, rà soát pháp lý mọi mục ⚠ trước khi đưa vào metadata |
| Trích xuất sai mà không báo | Mất niềm tin, hoàn tiền | Luật chạy trước; LLM chỉ lấp chỗ trống; kiểm tra toán VAT; màn xem lại; ngưỡng tự chấp nhận thận trọng |
| Chỉ 35–50% máy có Apple Intelligence | Trải nghiệm không đều | Mọi tính năng trả phí chạy được bằng luật; paywall ghi rõ "AI trên máy hỗ trợ" |
| Freemium 2,0% không hoàn vốn Apple Ads (UK 28%, DE 43%) | Tăng trưởng chậm | ASO trước; chỉ chạy Ads khi chuyển đổi gần hard paywall; thử hard paywall ở bước xuất |
| Mất dữ liệu vì chỉ lưu trên máy | Mất chứng từ cần lưu nhiều năm | Dữ liệu nằm trong backup iCloud/Finder của thiết bị; nhắc xuất ZIP định kỳ; sao lưu mã hóa ở `V1.1` |
| CloudKit hoặc MetricKit làm đổi nhãn "Data Not Collected" | Mất lợi thế định vị | MVP không sync; xác minh hướng dẫn App Privacy trước `V1.1` ⚠ |
| Định dạng và quy định chưa xác minh (DATEV, danh mục thuế, thời hạn lưu trữ, mẫu sổ VN) | Làm lại | Mọi mục ⚠ có owner và hạn xác minh trong S0 (xem [technical-design.md §14](technical-design.md#14-câu-hỏi-mở)) |

## Liên kết

- [Quy ước chung cho 3 app](../README.md)
- [Lõi dùng chung `SensorCore`](../shared-core.md) và [backlog lõi](../shared-core-backlog.csv)
- [Báo cáo nghiên cứu](../../reports/App%20iPhone%20offline%20d%C3%B9ng%20c%E1%BA%A3m%20bi%E1%BA%BFn.md)
- [Kế hoạch 12 tháng](../../reports/K%E1%BA%BF%20ho%E1%BA%A1ch%20top%205%20app%20iOS.md)
