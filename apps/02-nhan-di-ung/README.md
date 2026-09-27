# App 02 · Máy quét nhãn thành phần và dị ứng (`AllergenLens`, mã `NDU`)

Tên mã chỉ dùng nội bộ. Quy ước ID, ưu tiên và dấu ⚠/🧪 theo [README chung](../README.md). Phần dùng chung nằm ở [shared-core.md](../shared-core.md).

| File | Nội dung |
|---|---|
| [epics-features.md](epics-features.md) | 10 epic, 69 feature, ước tính, lộ trình sprint, ước tính nội dung |
| [technical-design.md](technical-design.md) | Kiến trúc, dữ liệu, pipeline, thuật toán, an toàn, kiểm thử, spike |
| [backlog.csv](backlog.csv) | Danh sách feature để nhập vào Jira, Linear hoặc GitHub Projects |

## Tóm tắt

- App đọc **chính danh sách thành phần in trên bao bì** bằng OCR, đối chiếu với từ điển chất gây dị ứng đa ngôn ngữ nằm trên máy, rồi tô sáng những gì liên quan tới hồ sơ của người dùng. Không cần mã vạch, không cần mạng, không cần tài khoản.
- Đọc nhãn ở **9 ngôn ngữ** ngay từ bản đầu: EN, DE, FR, IT, ES, NL, SV, DA, NB. UI lúc ra mắt có 7 locale: `en`, `en-GB`, `de`, `fr`, `it`, `es`, `nl`.
- Danh sách chất gây dị ứng dựa trên **14 chất ở Annex II, Quy định (EU) số 1169/2011**. Cách viết chính xác của từng mục phải trích từ văn bản quy định trước khi phát hành ⚠.
- **An toàn là ràng buộc thiết kế số một.** Bỏ sót có thể làm người dùng bị hại, nên app thiên về không bỏ sót (recall), chấp nhận báo nhầm nhiều hơn, và không bao giờ nói "an toàn".
- Ra mắt khoảng **đầu tháng 5/2027** ở FR, DE, IT, ES, NL, UK, trước mùa du lịch hè.
- MVP cần **45 ngày công dev** (lõi `SensorCore` đã có) và khoảng **148 người-ngày nội dung** (từ điển, duyệt bản ngữ, thẻ dị ứng, bộ kiểm thử). Phần nội dung lớn gấp khoảng 3 lần phần code.
- Giá **$/€9.99–19.99/năm**, ngang Yuka. Với mức giá này, Apple Ads không hoàn vốn năm đầu ở tỷ lệ chuyển đổi freemium, nên tăng trưởng dựa vào ASO, cộng đồng người dị ứng và coeliac, báo chí và cơ hội được Apple giới thiệu.

## Người dùng mục tiêu và việc cần làm

| Nhóm | Việc cần làm (job-to-be-done) | Khó khăn hôm nay | App giúp gì |
|---|---|---|---|
| Người dị ứng thực phẩm | "Trong siêu thị, tôi cần biết nhanh sản phẩm này có chứa thứ tôi dị ứng không" | Chữ nhỏ, tên kỹ thuật (casein, whey, E322), từ ghép tiếng Đức, câu "may contain" | Tô sáng từng chỗ khớp, nói rõ lý do, báo khi chưa đọc hết danh sách |
| Người bị coeliac | "Tôi cần bắt được mọi nguồn gluten, kể cả spelt, malt, semolina" | Nhiều tên ngũ cốc và dẫn xuất theo từng ngôn ngữ | Nhóm "coeliac" gồm ngũ cốc chứa gluten và dẫn xuất; claim "gluten-free" chỉ hiện như thông tin |
| Người ăn chay, thuần chay | "Tôi muốn biết có thành phần động vật không" | Gelatine, carmine, rennet, số E nguồn không rõ | Nhóm chế độ ăn; số E nguồn mơ hồ hiện "Có thể có" |
| Cha mẹ có con dị ứng | "Tôi quét cho cả nhà, mỗi người tránh một thứ khác nhau" | Nhớ hồ sơ của từng người | Hồ sơ gia đình, chế độ "Cả nhà" (Plus) |
| Người đi du lịch trong EU | "Tôi đọc nhãn tiếng Ý, tiếng Hà Lan mà không biết tiếng" và "Tôi cần nói với nhà hàng" | Dịch máy không hiểu ngữ cảnh dị ứng; mất mạng ở nước ngoài | Đọc 9 ngôn ngữ offline; thẻ dị ứng câu mẫu do người dịch và duyệt (Plus) |

## Định vị và khác biệt

**Định vị:** "Đọc chính danh sách thành phần trên bao bì, bằng 9 ngôn ngữ châu Âu, ngay trên iPhone. Nói rõ đã thấy gì, vì sao, và đã đọc hết danh sách hay chưa."

| Đối thủ | Cách làm | Khoảng trống cho NDU | Nguồn |
|---|---|---|---|
| Yuka (FR) | Quét mã vạch, tra cơ sở dữ liệu online; chế độ offline (100.000 sản phẩm quét nhiều nhất) và cảnh báo dị ứng chỉ có ở Premium | Khoảng 90% sản phẩm do người dùng thêm vào, nên có chỗ thiếu; cách chấm điểm bị chê thiếu minh bạch. NDU không cần mã vạch có trong cơ sở dữ liệu | Báo cáo, [Glossy](https://www.glossy.co/beauty/yuka-beauty-wellness-product-scanning-app/), [Yuka Help](https://help.yuka.io/l/en/article/ur4x5k32qg-database-in-offline-mode) |
| Alergio | Text Scanner và Travel Cards "work 100% offline" | Offline **không** còn là khác biệt riêng. NDU khác ở độ phủ, từ điển 9 ngôn ngữ có người duyệt, và lý do minh bạch cho từng hit | Ghi chú nghiên cứu, [Alergio](https://www.alergioapp.com/) |
| AllergIQ | Gắn cờ chất gây dị ứng ẩn dưới tên kỹ thuật và số E; dịch thẻ dị ứng | Báo cáo đánh giá các app dị ứng "còn non trẻ" và chủ yếu tiếng Anh (suy luận của nghiên cứu) | Ghi chú nghiên cứu, [AllergIQ](https://allergiq.org/) |
| Food Check AI, Spokin | Đọc nhãn tiếng nước ngoài; đánh giá cộng đồng cho du lịch có dị ứng | Chưa có dữ liệu về cách xử lý an toàn | Ghi chú nghiên cứu |
| CodeCheck (DE/AT/CH), Open Food Facts (FR) | Quét mã vạch dựa trên cơ sở dữ liệu | Cùng điểm yếu mã vạch như Yuka | Ghi chú nghiên cứu |
| Live Text và Translate có sẵn trong iOS | Đọc và dịch chữ miễn phí | Không đối chiếu hồ sơ, không biết dẫn xuất, số E, câu "may contain", không báo độ phủ | Suy luận |

Năm điểm khác biệt cần giữ:
1. **Không cần mã vạch.** Sản phẩm mới, hàng địa phương, hàng chợ đều đọc được, miễn là có danh sách thành phần.
2. **Minh bạch, không chấm điểm.** Mỗi hit hiện chữ đọc được, mục từ điển khớp, và vì sao nó thuộc chất đó.
3. **Chỉ báo độ phủ.** App nói đã thấy đầu và cuối danh sách chưa, chữ có rõ không. Trong ghi chú nghiên cứu chưa thấy đối thủ nào làm điều này.
4. **9 ngôn ngữ đọc nhãn lúc ra mắt**, từ điển do người bản ngữ có chuyên môn soạn và hai người duyệt.
5. **Không tài khoản, không server, nhắm nhãn "Data Not Collected".** Hồ sơ dị ứng là dữ liệu sức khỏe và không rời máy.

## Phạm vi

**MVP (ra mắt 5/2027, 45 ngày dev):**
- Onboarding có màn disclaimer bắt buộc; hồ sơ với 14 chất Annex II, 4 chế độ ăn (thuần chay, chay, coeliac, lactose), thành phần tùy chỉnh, mức độ, ngôn ngữ đọc.
- Hồ sơ gia đình cơ bản (Plus).
- Quét live bằng `DataScannerViewController` có vùng quan tâm; chốt kết quả bằng ảnh tĩnh; dự phòng chụp tĩnh và nhập ảnh; đèn pin; nhắc lau camera; thêm ảnh cho cùng nhãn.
- Phân tích: tìm khối thành phần theo tiêu đề đa ngôn ngữ, nối từ ngắt dòng, ngoặc lồng nhau, chuẩn hóa, khớp chính xác và từ ghép, khớp mờ chịu lỗi OCR, dẫn xuất, số E nguồn mơ hồ, câu "may contain", free-from, độ phủ.
- Kết quả: 4 trạng thái mỗi chất, chỉ báo độ phủ, overlay trên ảnh, lý do từng hit, VoiceOver và haptic.
- Thẻ dị ứng du lịch 9 ngôn ngữ (Plus): câu mẫu đã duyệt, toàn màn hình offline, xuất ảnh/PDF, ghi chú tùy chỉnh dịch bằng Translation framework có nhãn "bản dịch máy".
- Lịch sử và sản phẩm đã lưu (Plus).
- Bộ kiểm thử an toàn, cổng phát hành chặn khi độ nhạy giảm, nút báo bỏ sót.

**V1.1 (trong 8 tuần sau ra mắt, 20 ngày dev):** giải thích dễ hiểu bằng Foundation Models có nhãn AI; ghép văn bản nhiều ảnh cho bao bì cong; overlay live "xem trước"; cập nhật từ điển qua Background Assets ⚠; mã vạch làm khóa cục bộ; phân tích lại lịch sử khi từ điển đổi; widget mở thẻ; thêm ngôn ngữ thẻ; UI SV, DA, NB; offer code.

**V2 (sau khi đạt tiêu chí "đẩy mạnh", 11 ngày dev):** đọc nhãn PT và PL; thử tiếng Phần Lan; tín hiệu chữ in đậm; Visual Intelligence; Wallet pass (cần server ký); Spotlight; thử gói tháng hoặc trọn đời; UI đợt 3.

Danh sách đầy đủ: [epics-features.md](epics-features.md).

## Số liệu thị trường

Mọi số dưới đây lấy từ [báo cáo nghiên cứu](../../reports/App%20iPhone%20offline%20d%C3%B9ng%20c%E1%BA%A3m%20bi%E1%BA%BFn.md) và [kế hoạch 12 tháng](../../reports/K%E1%BA%BF%20ho%E1%BA%A1ch%20top%205%20app%20iOS.md), dữ liệu thu ngày 27/9/2026. Số tải và doanh thu là ước tính làm tròn của Sensor Tower, toàn cầu, chỉ iOS, không có số theo nước.

| Chỉ số | Giá trị | Ghi chú |
|---|---|---|
| "food scanner" (Google, Mỹ) | 3–8K lượt/tháng, **+331%\*** trong 2 năm | Dải volume quy đổi từ Google Trends, có thể lệch 2–3 lần |
| "nutrition scanner" (Google, Mỹ) | 300–1K lượt/tháng, **+917%\***; toàn cầu +2300% | Như trên |
| Yuka, doanh thu Premium năm 2025 | **$11.884.771** | Công ty tự công bố; đội 20 người; không nhận tiền nhãn hàng |
| Yuka, iOS toàn cầu tháng 8/2026 | Khoảng **$1M/tháng**, 800k lượt tải | Ước tính Sensor Tower |
| Yuka, người dùng | Khoảng 73 triệu | Doanh thu mỗi người dùng rất thấp |
| Yuka, thứ hạng 27/9/2026 | Top 10 Free H&F ở IT, GB, ES, FR. Top Grossing H&F: FR #16, IT #16, US #25, ES #28, UK #30, DE #79, NL ngoài top 100 | Apple RSS, một ngày |
| Yuka, giá Premium | Khoảng $10–20/năm | Offline, tìm không cần mã vạch, cảnh báo dị ứng nằm trong Premium |
| Foodvisor | Khoảng **$2M/tháng**, 400k lượt tải | Ước tính Sensor Tower; app calorie qua ảnh, không phải đối thủ trực tiếp |
| Phân khúc AI calorie qua ảnh | $6M/tháng, 11 app, khoảng 70 đối thủ | Kế hoạch khuyên chuyển hướng sang dị ứng và thành phần thay vì clone Cal AI |
| Phân khúc quét mã vạch sản phẩm | $1M/tháng, Yuka thống trị | |
| Chuẩn Tây Âu (RevenueCat 2026) | Tải → trả tiền D35 **2,0%**; trial → trả tiền 29,7%; RPI D14 **$0,25**; hoàn tiền dưới 3% | Dùng làm ngưỡng KPI |
| Chuẩn Health & Fitness toàn cầu | Tải → trả tiền D35 2,9%; trial → trả tiền 37,7%; RPI D14 $0,48 | Tham khảo nếu app nằm trong danh mục H&F |
| Apple Ads ở Pháp | CPA $1,11. Với giá $14.99/năm và freemium 2,0%: $55,50 để có 1 người trả tiền, thu thực năm đầu $10,62, tức chỉ **19%** | Mục 5 của kế hoạch |
| iOS 26 | Chạy trên 79% iPhone (Apple, 6/2026) | Mức tối thiểu của app |
| Live Text | 24 ngôn ngữ, gồm DE, FR, IT, ES, NL, DA, NO, SV, PL; **không có tiếng Phần Lan** | |
| Foundation Models | 16 ngôn ngữ; **không có PL, FI**; cần iPhone 15 Pro trở lên, khoảng 35–50% máy đang dùng (ước tính) | Chỉ là lớp nâng cấp |

\* spike-inflated: đỉnh tháng 4–6/2026 cao gấp 3 lần trở lên so với trung vị trước đó, nên mức tăng thật có thể nhỏ hơn.

Chưa có dữ liệu: volume từ khóa App Store theo từng ngôn ngữ EU (ví dụ "Allergene Scanner"), doanh thu của các app dị ứng nhỏ như Alergio hay AllergIQ. Từ khóa địa phương phải đo bằng Apple Ads sau khi ra mắt.

## Nguyên tắc an toàn

1. **Thiên về không bỏ sót.** Khi phải chọn giữa báo nhầm và bỏ sót, luôn chọn báo nhầm. Khớp mờ và ứng viên OCR chỉ được thêm hit, không bao giờ bớt hit.
2. **Không bao giờ nói "an toàn".** Không dùng chữ "safe", "an toàn", "sicher", "sûr", "sicuro", "seguro", "veilig", "säker", "sikker", "trygg" trong kết quả. Không dùng dấu tích xanh. Test tự động chặn các từ này.
3. **Bốn trạng thái cho mỗi chất:** "Phát hiện"; "Có thể có (vết/may contain)"; "Không chắc chắn, hãy đọc lại nhãn"; "Không thấy trong phần đã đọc". Câu cuối luôn đi kèm chỉ báo độ phủ.
4. **Chỉ báo độ phủ luôn hiện:** đã thấy đầu danh sách chưa, đã thấy cuối chưa, chữ có đủ rõ không. Thiếu bằng chứng thì mặc định là "Một phần".
5. **Chữ mờ thì nói là mờ.** Độ tin cậy OCR thấp hoặc chữ bị cắt ở mép → "Không chắc chắn, hãy đọc lại nhãn".
6. **Luôn nhắc "Công cụ hỗ trợ — luôn đọc lại nhãn"** ở onboarding, màn kết quả, thẻ dị ứng, ảnh chia sẻ và mô tả App Store.
7. **Không chẩn đoán, không tư vấn y tế** (Guideline 1.4.1). Mức độ nghiêm trọng người dùng khai chỉ đổi cách hiển thị, không đổi độ nhạy.
8. **Không khóa thông tin an toàn sau paywall.** Quét, 9 ngôn ngữ, 14 chất, chế độ ăn, thành phần tùy chỉnh và "Có thể có" luôn miễn phí.
9. **Foundation Models chỉ diễn đạt lại** một mục từ điển đã khớp (V1.1), luôn có nhãn "Do AI tạo" (AI Act Điều 50, áp dụng từ 2/8/2026), không bao giờ quyết định trạng thái.
10. **Từ điển là tài sản an toàn:** hai người duyệt cho mỗi ngôn ngữ, test tự động cho mỗi term, cổng phát hành chặn khi recall giảm, quy trình xử lý báo bỏ sót có thời hạn.

Chi tiết: [technical-design.md mục 9](technical-design.md#9-an-toàn-quyền-riêng-tư-và-tuân-thủ).

## Kiếm tiền

| Miễn phí | Plus (`ndu.plus.yearly`, trial 7 ngày) |
|---|---|
| Một hồ sơ, quét không giới hạn, đủ tính năng an toàn | Hồ sơ gia đình (tối đa 6) và chế độ "Cả nhà" |
| Xem lại lần quét gần nhất | Lịch sử và sản phẩm đã lưu |
| Xem trước thẻ dị ứng | Thẻ dị ứng du lịch 9 ngôn ngữ, toàn màn hình, xuất ảnh/PDF |

- Giá đề xuất €14,99/năm (giữa khung $/€9.99–19.99 của kế hoạch). Thử €9,99 và €19,99 sau khi có dữ liệu ⚠.
- Dùng Apple IAP ở EU, Small Business Program (15%). Paywall theo checklist chung: các gói đặt cạnh nhau, giá thực là chữ lớn nhất, mốc "Ngày 7: bị tính tiền", nút đóng rõ, một lối từ chối.
- **Tăng trưởng không dựa vào Apple Ads.** Chỉ dùng ngân sách thử khoảng 300 lượt chạm mỗi thị trường để đo từ khóa địa phương.
- Kênh chính:
  - **ASO:** "food scanner", "nutrition scanner", "food scanner good or bad free"; metadata EN-UK là ô từ khóa thứ hai miễn phí trên hầu hết storefront EU.
  - **Cộng đồng:** hội coeliac và hội dị ứng từng nước, nhóm cha mẹ có con dị ứng (suy luận, chưa có dữ liệu).
  - **Báo chí công nghệ địa phương** với góc riêng tư và offline: heise, t3n, Caschys Blog, iphone-ticker.de, Macwelt (DE); Frandroid, iPhon.fr, Numerama (FR); Macitynet (IT); Applesfera (ES); iCulture (NL); iMore (UK).
  - **Được Apple giới thiệu:** nhóm biên tập ưu tiên app bản địa hóa tốt, dễ tiếp cận, tôn trọng quyền riêng tư, dùng Vision và ML trên máy.

## KPI sau 8 tuần

Ngưỡng theo trung vị Tây Âu (RevenueCat 2026), giống kế hoạch 12 tháng:

| Chỉ số | Ngưỡng | Đo bằng |
|---|---|---|
| Tải → trả tiền trong 35 ngày | ≥ 2,0% | App Store Connect |
| Trial → trả tiền | ≥ 29,7% | App Store Connect |
| RPI D14 | ≥ $0,25 | App Store Connect (tính tay) |
| Hoàn tiền | < 3% | App Store Connect |

Chỉ số an toàn (mục tiêu nội bộ). App không có analytics, nên các chỉ số này chỉ đo trên bộ ảnh vàng, nhóm beta và báo cáo người dùng tự gửi:

| Chỉ số | Mục tiêu |
|---|---|
| Critical miss trên bộ ảnh vàng ở mỗi bản phát hành | 0 |
| Báo bỏ sót mức S1 còn mở quá 72 giờ | 0 |
| Đánh giá App Store nêu vấn đề an toàn chưa được xử lý | 0 |

Quyết định sau 8 tuần theo bảng "đẩy mạnh / sửa / dừng đầu tư" ở mục 6 của kế hoạch 12 tháng.

## Rủi ro chính

| Rủi ro | Ảnh hưởng | Cách xử lý |
|---|---|---|
| Bỏ sót chất gây dị ứng | Người dùng bị hại; mất niềm tin; rủi ro pháp lý | Thiết kế thiên về recall, độ phủ, cổng phát hành, 2 người duyệt từ điển, quy trình sự cố |
| Người dùng hiểu "Không thấy" là "an toàn" | Như trên | Không dùng từ và biểu tượng "an toàn"; câu "trong phần đã đọc"; test người dùng ở beta |
| Bị từ chối theo Guideline 1.4.1 | Trễ ra mắt | Không chẩn đoán; disclaimer rõ; Review Notes giải thích cách hoạt động |
| Phạm vi pháp lý: app có bị coi là thiết bị y tế (MDR) không; Chỉ thị trách nhiệm sản phẩm mới của EU có áp dụng cho phần mềm không ⚠ | Nghĩa vụ pháp lý lớn | Tư vấn luật trước khi ra mắt (C15); giữ mục đích sử dụng là "hỗ trợ đọc nhãn" |
| Từ điển thiếu hoặc sai ở một ngôn ngữ | Bỏ sót có hệ thống | 148 người-ngày nội dung; bộ văn bản và ảnh cho từng ngôn ngữ |
| OCR kém trên bao bì cong, bóng, chữ nhỏ | "Không chắc chắn" nhiều, người dùng bỏ app | Spike S1; đèn; nhiều ảnh; ghép văn bản (V1.1) |
| Công thức sản phẩm thay đổi | Kết quả cũ sai | Không hiện kết quả cũ như hiện tại; luôn nhắc quét lại |
| Alergio, AllergIQ đã có offline và thẻ dịch | Khác biệt yếu | Nhấn vào độ phủ, 9 ngôn ngữ có người duyệt, minh bạch |
| Giá thấp, Apple Ads không hoàn vốn | Tăng trưởng chậm | ASO, cộng đồng, báo chí, featuring |
| 1 dev, lịch trùng ra mắt app 3 (3/2027) và xây app 4 (5–6/2027) | Trễ hoặc V1.1 chậm | Danh sách cắt; thuê dev bán thời gian khoảng 2 tuần |
| Nguồn dữ liệu số E có ràng buộc giấy phép (ví dụ ODbL) ⚠ | Phải công bố dữ liệu phái sinh | Tự dựng từ văn bản quy định; luật sư rà |

## Liên kết

- [Kế hoạch 12 tháng, mục App 2](../../reports/K%E1%BA%BF%20ho%E1%BA%A1ch%20top%205%20app%20iOS.md#app-2--m%C3%A1y-qu%C3%A9t-nh%C3%A3n-th%C3%A0nh-ph%E1%BA%A7n-v%C3%A0-d%E1%BB%8B-%E1%BB%A9ng)
- [Báo cáo nghiên cứu](../../reports/App%20iPhone%20offline%20d%C3%B9ng%20c%E1%BA%A3m%20bi%E1%BA%BFn.md)
- Ghi chú nghiên cứu: [cơ hội ngách](../../research_notes/App%20iPhone%20offline%20d%C3%B9ng%20c%E1%BA%A3m%20bi%E1%BA%BFn/niche_opportunities.md), [công nghệ Apple và App Review](../../research_notes/App%20iPhone%20offline%20d%C3%B9ng%20c%E1%BA%A3m%20bi%E1%BA%BFn/apple_ondevice_tech_and_review.md), [tối ưu cho châu Âu](../../research_notes/App%20iPhone%20offline%20d%C3%B9ng%20c%E1%BA%A3m%20bi%E1%BA%BFn/europe_market_optimization.md), [kiếm tiền](../../research_notes/App%20iPhone%20offline%20d%C3%B9ng%20c%E1%BA%A3m%20bi%E1%BA%BFn/monetization_paid_features.md)
- [Lõi dùng chung `SensorCore`](../shared-core.md)
