# AllergenLens (NDU) · Epic, module và feature

Tài liệu này chia việc của app 02 theo **Epic → Module → Feature**. Quy ước ID, ưu tiên, cách ước tính và dấu ⚠/🧪 theo [README chung](../README.md). Phần lõi `SensorCore` đã có sẵn khi app này bắt đầu (3/2027), nên bảng dưới chỉ gồm việc riêng của app. Cột "Phụ thuộc" ghi ID của `CORE` hoặc của chính app.

Ngày công là ngày của 1 dev iOS, đã gồm unit test, **không gồm** thiết kế UI, soạn từ điển, dịch thuật và duyệt nội dung. Phần nội dung được ước tính riêng ở [mục Nội dung](#nội-dung-không-phải-dev) vì chất lượng từ điển quyết định độ an toàn nhiều hơn code.

Thiết kế kỹ thuật chi tiết: [technical-design.md](technical-design.md). Bản CSV: [backlog.csv](backlog.csv).

## Danh sách epic

| ID | Epic | Mục tiêu | Module | Ngày MVP | Tổng ngày |
|---|---|---|---|---|---|
| NDU-E01 | Onboarding & hồ sơ dị ứng | Người dùng khai báo đúng thứ cần tránh trong dưới 2 phút và hiểu app chỉ là công cụ hỗ trợ | `ProfileFeature`, `LensModels` | 5 | 5 |
| NDU-E02 | Quét nhãn | Lấy được ảnh đủ nét của toàn bộ danh sách thành phần, kể cả khi thiếu sáng hoặc bao bì cong | `LabelCapture`, `ScanFeature`, `IngredientEngine`, `AllergenLens` | 4 | 10 |
| NDU-E03 | Phân tích thành phần | Từ chữ OCR ra trạng thái cho từng chất trong hồ sơ, thiên về không bỏ sót, có ước tính đã đọc đủ danh sách hay chưa | `IngredientEngine` | 12 | 16 |
| NDU-E04 | Từ điển & dữ liệu | Từ điển đa ngôn ngữ có người duyệt, có phiên bản, kiểm tra tự động trước khi vào app | `Lexicon`, `lexicon-build` | 4,5 | 9,5 |
| NDU-E05 | Kết quả & giải thích | Kết quả dễ hiểu, minh bạch lý do, dùng được bằng VoiceOver, không bao giờ nói "an toàn" | `ScanFeature`, `ExplainFeature` | 3,5 | 8,5 |
| NDU-E06 | Thẻ dị ứng du lịch | Thẻ offline bằng ngôn ngữ nơi đến, câu mẫu do người dịch và duyệt | `AllergyCards`, `AllergenLensWidget` | 3,5 | 8,5 |
| NDU-E07 | Lịch sử & sản phẩm đã lưu | Xem lại lần quét và sản phẩm quen, luôn nhắc quét lại vì công thức có thể đổi | `HistoryFeature` | 2,5 | 6 |
| NDU-E08 | Paywall & gói | Thu tiền cho hồ sơ gia đình, thẻ du lịch và lịch sử; không khóa thông tin an toàn | `AllergenLens` (+ `CorePaywall`) | 2 | 3 |
| NDU-E09 | Bản địa hóa & tuân thủ | UI 7 locale lúc ra mắt, disclaimer đúng chỗ, qua App Review 1.4.1, accessibility tốt | `AllergenLens`, `(ci)` | 3 | 4 |
| NDU-E10 | An toàn & chất lượng | Đo được và chặn phát hành khi độ nhạy giảm; có quy trình xử lý báo bỏ sót | `SafetyBench`, `Lexicon`, `ScanFeature`, `(ci)` | 5 | 5,5 |
| | **Tổng** | | | **45** | **76** |

## NDU-E01 · Onboarding & hồ sơ dị ứng

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| NDU-E01-01 | ProfileFeature | Luồng onboarding: giới thiệu, màn disclaimer phải bấm "Tôi hiểu", xin quyền camera với purpose string cụ thể | MVP | 1 | CORE-E13-01, CORE-E09-01 | Khi chưa bấm "Tôi hiểu" thì không vào được màn quét; khi từ chối quyền camera thì vẫn quét được bằng ảnh nhập |
| NDU-E01-02 | ProfileFeature | Chọn trong 14 chất gây dị ứng Annex II; tên và mô tả ngắn lấy từ từ điển theo ngôn ngữ UI | MVP | 0,5 | NDU-E04-01 | Khi đổi ngôn ngữ UI thì vẫn đủ 14 mục với tên mới; khi mở lần đầu thì không mục nào được chọn sẵn |
| NDU-E01-03 | ProfileFeature | Chế độ ăn: thuần chay, chay, coeliac/không gluten, không dung nạp lactose; mỗi chế độ ánh xạ sang nhóm mục từ điển | MVP | 0,5 | NDU-E04-01 | Khi chọn "coeliac" thì kết quả kiểm tra nhóm ngũ cốc chứa gluten gồm cả dẫn xuất (ví dụ malt, spelt) |
| NDU-E01-04 | ProfileFeature | Thành phần tùy chỉnh: tên, biến thể, ngôn ngữ; khớp như mục từ điển (có khớp mờ, bắt tiền tố) | MVP | 1 | NDU-E03-06, NDU-E03-07 | Khi thêm "kiwi" thì "Kiwi", "KIWI" và "Kiwis" trên nhãn đều cho trạng thái "Phát hiện" |
| NDU-E01-05 | ProfileFeature | Mức độ nghiêm trọng và ngôn ngữ đọc nhãn (mặc định bật cả 9) | MVP | 0,5 | NDU-E01-06 | Khi đổi mức độ thì trạng thái phát hiện không đổi; khi tắt một ngôn ngữ đọc thì app cảnh báo giảm độ nhạy |
| NDU-E01-06 | LensModels | Mô hình SwiftData `Profile`, `AllergenSelection`, `CustomTerm`; sửa, xóa hồ sơ; xóa toàn bộ dữ liệu | MVP | 0,5 | CORE-E05-01, CORE-E05-02 | Khi chọn "Xóa toàn bộ dữ liệu" thì store và file ảnh trống và app quay về onboarding |
| NDU-E01-07 | ProfileFeature | Hồ sơ gia đình (tối đa 6), chọn hồ sơ đang quét hoặc "Cả nhà" | MVP | 1 | NDU-E01-06, NDU-E08-01 | Khi quét ở chế độ "Cả nhà" thì kết quả tách theo từng người; khi chưa có Plus thì tạo hồ sơ thứ 2 sẽ mở paywall |

Ghi chú:
- Mức độ nghiêm trọng chỉ đổi cách nhấn mạnh và câu trên thẻ dị ứng. Nó **không** làm giảm độ nhạy, không ẩn "Có thể có".
- Kế hoạch 12 tháng xếp hồ sơ gia đình vào "để sau", nhưng lại tính nó là quyền lợi trả phí. Tài liệu này đưa bản cơ bản vào MVP (1 ngày) để paywall có đủ ba quyền lợi lúc ra mắt. Nếu trễ lịch, đây là mục cắt đầu tiên.

## NDU-E02 · Quét nhãn

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| NDU-E02-01 | LabelCapture | Màn quét live: dùng wrapper `DataScannerViewController` của CORE, `.text(languages:)` theo ngôn ngữ đọc, vùng quan tâm nằm ngang, chữ hướng dẫn | MVP | 1 | CORE-E02-02, NDU-E01-05 | Khi `isSupported` hoặc `isAvailable` là false thì màn tự chuyển sang chụp tĩnh, không crash |
| NDU-E02-02 | LabelCapture | Chụp tĩnh dự phòng bằng AVFoundation (chạm để lấy nét, khóa phơi sáng) và nhập ảnh | MVP | 1 | CORE-E02-03 | Khi chụp hoặc chọn ảnh HEIC/JPEG thì ảnh đi vào đúng pipeline phân tích như ảnh chốt từ live |
| NDU-E02-03 | LabelCapture | Đèn pin, cảnh báo ảnh tối, nhắc lau camera | MVP | 0,5 | CORE-E02-04 | Khi ảnh chốt có độ sáng trung bình dưới ngưỡng thì app gợi ý bật đèn và chụp lại; khi điểm smudge vượt ngưỡng thì hiện "Lau camera" |
| NDU-E02-04 | LabelCapture | Nút "Chốt kết quả": `capturePhoto()` → OCR ảnh tĩnh bằng Vision (confidence, ứng viên) → phân tích | MVP | 1 | CORE-E03-01, CORE-E03-02, NDU-E03-01 | Khi bấm "Chốt kết quả" thì kết quả luôn lấy từ ảnh tĩnh, không lấy từ frame live, và ảnh được giữ để vẽ overlay |
| NDU-E02-05 | ScanFeature | Thêm ảnh cho cùng một nhãn (mặt sau, phần bị cong); hợp nhất hit, độ phủ tính thận trọng | MVP | 0,5 | NDU-E03-09 | Khi thêm ảnh thứ 2 thì hit của cả hai ảnh đều hiện; khi không chứng minh được phần giữa đã đọc thì độ phủ là "Một phần" |
| NDU-E02-06 | IngredientEngine | Ghép văn bản nhiều ảnh chồng lấn cho danh sách dài hoặc bao bì cong (căn dòng trùng, khử lặp) 🧪 | V1.1 | 3 | NDU-E02-05 | Khi quét chai cong bằng 3 ảnh chồng lấn thì văn bản ghép khớp bản chép tay ở ≥ 95% token và độ phủ là "Đủ" khi có cả đầu và cuối |
| NDU-E02-07 | AllergenLens | App Shortcut "Quét nhãn" và mở từ nút Camera Control ⚠ | V1.1 | 1 | CORE-E11-01 | Khi gọi "Quét nhãn" từ Shortcuts hoặc Siri thì app mở thẳng màn quét |
| NDU-E02-08 | AllergenLens | Tích hợp Visual Intelligence: ảnh nhãn → mở kết quả trong app ⚠ | V2 | 2 | CORE-E11-01 | Khi dùng Visual Intelligence trên nhãn thì app trả về mục mở màn kết quả của ảnh đó |

Ghi chú:
- Frame live chỉ dùng để ngắm và (từ V1.1) xem trước. Mọi kết luận hiển thị cho người dùng đến từ ảnh tĩnh có confidence theo dòng. Lý do nằm ở [technical-design.md mục 4](technical-design.md#4-pipeline-chi-tiết).
- "Ghép" ở NDU-E02-06 là ghép **văn bản** theo dòng trùng nhau, không phải ghép ảnh panorama.

## NDU-E03 · Phân tích thành phần

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| NDU-E03-01 | IngredientEngine | Adapter OCR → `LabelText`: dòng, khung chuẩn hóa, confidence, top-3 ứng viên, cờ chạm mép, nguồn (live hay ảnh tĩnh) | MVP | 1 | CORE-E03-01, CORE-E03-02, CORE-E03-03 | Khi OCR ảnh mẫu thì mỗi dòng có khung 0–1, confidence và tối đa 3 ứng viên; dòng chạm mép ảnh có cờ `touchesEdge` |
| NDU-E03-02 | IngredientEngine | Tìm khối thành phần theo tiêu đề đa ngôn ngữ ("Ingredients", "Zutaten", "Ingrédients"…); nhiều khối, nhiều ngôn ngữ trên một nhãn; nhận ra ngôn ngữ chưa hỗ trợ | MVP | 1,5 | NDU-E04-01 | Khi nhãn có "Zutaten:" và "Ingrédients :" thì trả về 2 khối gắn đúng ngôn ngữ; khi nhãn chỉ có tiếng Phần Lan thì mọi chất là "Không chắc chắn" kèm lý do "ngôn ngữ chưa hỗ trợ" |
| NDU-E03-03 | IngredientEngine | Ghép dòng và nối từ bị ngắt dòng; giữ cả hai biến thể khi không chắc | MVP | 0,5 | NDU-E03-01 | Khi "Wei-" cuối dòng và "zenmehl" đầu dòng sau thì có token "Weizenmehl"; khi "Milch-" đứng trước "und Sahne" thì không nối và "Milch" vẫn được khớp |
| NDU-E03-04 | IngredientEngine | Tách token: `,` `;` `·`, liên từ, ngoặc tròn/vuông lồng nhau, phần trăm, dạng "Nhóm: danh sách" | MVP | 1 | NDU-E03-03 | Khi gặp "Schokolade 20 % (Zucker, Kakaobutter, Vollmilchpulver (Milch))" thì cây token có 3 cấp; ngoặc lệch không làm mất token nào |
| NDU-E03-05 | IngredientEngine | Chuẩn hóa: NFKC, casefold, gập dấu theo bảng từng ngôn ngữ, `ß`→`ss`, thống nhất dấu nháy và gạch, số E | MVP | 0,5 | NDU-E03-04 | Khi đầu vào là "E 322", "E-322" hoặc "e322" thì đều thành "E322"; chạy chuẩn hóa hai lần cho cùng kết quả |
| NDU-E03-06 | IngredientEngine | Khớp chính xác nhiều từ bằng Aho-Corasick; luật ranh giới từ và từ ghép cho DE, NL, SV, DA, NB | MVP | 2 | NDU-E03-05, NDU-E04-01 | Khi nhãn có "Magermilchpulver" thì khớp sữa; khi có "Buchweizen" thì không khớp lúa mì nhờ mục loại trừ; 100% term trong bộ test đều khớp |
| NDU-E03-07 | IngredientEngine | Khớp mờ chịu lỗi OCR: Damerau-Levenshtein có trọng số nhầm lẫn OCR, ngưỡng theo độ dài, xét cả top-3 ứng viên 🧪 | MVP | 2 | NDU-E03-06 | Khi có "rnilk" hoặc "Weizcn" thì tạo hit loại "đọc gần đúng"; term ≤ 4 ký tự không bao giờ khớp mờ |
| NDU-E03-08 | IngredientEngine | Ngữ cảnh: câu phòng ngừa ("may contain", "kann Spuren von … enthalten", "peut contenir"), câu "Contains/Enthält", free-from và loại trừ có phạm vi | MVP | 1,5 | NDU-E03-06 | Khi gặp "Kann Spuren von Haselnüssen enthalten" thì hạt cây là "Có thể có"; "glutenfrei" không tạo hit gluten nhưng không che hit "Hafer" ở chỗ khác |
| NDU-E03-09 | IngredientEngine | Ước tính độ phủ: tiêu đề đầu, dấu kết thúc, dòng chạm mép, ngoặc cân bằng, confidence | MVP | 1 | NDU-E03-02 | Khi ảnh cắt mất phần cuối danh sách thì độ phủ là "Một phần" với lý do "Thiếu phần cuối" |
| NDU-E03-10 | IngredientEngine | Phân loại cuối theo hồ sơ: 4 trạng thái mỗi chất; dẫn xuất và số E nguồn mơ hồ; ưu tiên recall | MVP | 1 | NDU-E03-08, NDU-E03-09 | Khi có "E322" không ghi nguồn thì đậu nành và trứng là "Có thể có"; khi độ phủ chưa đủ thì màn tổng kết không có câu nào dạng "không có" |
| NDU-E03-11 | IngredientEngine | Phân tích tăng dần cho chế độ live: debounce, ổn định hit giữa các frame | V1.1 | 1 | NDU-E03-10 | Khi rê camera qua nhãn thì một hit không bật/tắt quá 1 lần mỗi giây và độ trễ hiển thị ≤ 300 ms |
| NDU-E03-12 | IngredientEngine | Tín hiệu nhấn mạnh: từ IN HOA trong danh sách chữ thường mà không có trong từ điển → "Không chắc chắn" ⚠ | V1.1 | 1 | NDU-E03-10 | Khi nhãn có một từ IN HOA lạ trong danh sách chữ thường thì kết quả hiện "Từ được nhấn mạnh chưa nhận ra" |
| NDU-E03-13 | IngredientEngine | Tín hiệu chữ in đậm từ ảnh (cách nhấn mạnh chất gây dị ứng theo Quy định 1169/2011 ⚠) 🧪 | V2 | 2 | NDU-E03-12 | Khi một từ in đậm không có trong từ điển thì kết quả hiện ở mức "Không chắc chắn" kèm vùng ảnh |

Ghi chú:
- Khớp mờ và ứng viên OCR chỉ được **thêm** hit, không bao giờ được **bớt** hit. Mục loại trừ chỉ có hiệu lực khi khớp chính xác.
- Bốn trạng thái mỗi chất: "Phát hiện", "Có thể có", "Không chắc chắn, hãy đọc lại nhãn", "Không thấy trong phần đã đọc". Luật đầy đủ ở [technical-design.md mục 5.9](technical-design.md#59-luật-phân-loại-cuối).

## NDU-E04 · Từ điển & dữ liệu

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| NDU-E04-01 | Lexicon | Schema JSON (mục chất × ngôn ngữ, số E, mẫu phủ định, ngữ pháp nhãn), mô hình Codable, loader dựng automaton, hiện phiên bản | MVP | 1,5 | – | Khi nạp từ điển đóng gói thì dựng xong ≤ 150 ms trên iPhone 12 và phiên bản hiện trong Cài đặt; file sai schema bị từ chối |
| NDU-E04-02 | lexicon-build | CLI `Tools/lexicon-build`: nguồn YAML/CSV có người duyệt → JSON; kiểm tra schema, trùng, xung đột, đủ 14 chất × 9 ngôn ngữ, đủ người duyệt | MVP | 2 | NDU-E04-01 | Khi thiếu một chất ở một ngôn ngữ hoặc một mục thiếu người duyệt thì CLI thoát với mã lỗi và in danh sách |
| NDU-E04-03 | lexicon-build | Sinh test từ nguồn (term có câu dương, loại trừ có câu âm), báo cáo rủi ro (term ngắn, va chạm chéo ngôn ngữ, láng giềng mờ), diff phiên bản | MVP | 1 | NDU-E04-02 | Khi một term bị xóa so với bản trước thì diff ghi rõ và build fail nếu thay đổi chưa có 2 người duyệt |
| NDU-E04-04 | Lexicon | Cập nhật từ điển qua Apple-hosted Background Assets: kiểm schema, tự kiểm, không hạ phiên bản, lùi về bản đóng gói khi lỗi ⚠ 🧪 | V1.1 | 3 | NDU-E04-01, NDU-E10-04 | Khi gói tải về sai schema hoặc trượt tự kiểm thì app dùng bản đóng gói và phiên bản hiển thị không đổi |
| NDU-E04-05 | Lexicon | Đọc nhãn tiếng Bồ Đào Nha và Ba Lan (ngữ pháp, cờ từ ghép, bộ vàng; từ điển là việc nội dung) | V2 | 1 | NDU-E04-02 | Khi chạy bộ vàng PT và PL thì đạt cùng ngưỡng cổng phát hành như 9 ngôn ngữ đầu |
| NDU-E04-06 | Lexicon | Tiếng Phần Lan: thử `VNRecognizeTextRequest` với FI, hoặc dựa vào khối tiếng Thụy Điển trên nhãn bán ở Phần Lan ⚠ 🧪 | V2 | 1 | NDU-E04-02 | Khi nhãn có khối tiếng Thụy Điển thì khối đó được phân tích; khi chỉ có tiếng Phần Lan thì app báo "chưa hỗ trợ ngôn ngữ này" |

Ghi chú:
- MVP đóng gói từ điển trong app. Muốn sửa một term bị thiếu thì phải phát hành bản app mới và xin xét duyệt nhanh (expedited review). NDU-E04-04 bỏ được bước này ở V1.1.
- Quyền dùng dữ liệu số E và nguồn tham khảo (ví dụ Open Food Facts, giấy phép ODbL) phải được rà trước khi soạn ⚠. Đề xuất tự dựng từ văn bản quy định EU và chuyên gia duyệt.

## NDU-E05 · Kết quả & giải thích

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| NDU-E05-01 | ScanFeature | Màn kết quả: tổng kết theo hồ sơ, chỉ báo độ phủ, 4 trạng thái, footer "Công cụ hỗ trợ — luôn đọc lại nhãn" | MVP | 1,5 | NDU-E03-10, CORE-E13-01 | Khi mọi chất là "Không thấy" và độ phủ "Đủ" thì màn dùng màu trung tính, không có dấu tích xanh và không có chữ "an toàn" |
| NDU-E05-02 | ScanFeature | Overlay tô sáng trên ảnh và danh sách hit có lý do (chữ đọc được → mục từ điển → chất, loại hit, độ tin cậy) | MVP | 1,5 | NDU-E05-01 | Khi chạm một hit thì ảnh phóng tới vùng chữ và hiện lý do; mọi hit đều có ít nhất một khung trên ảnh |
| NDU-E05-03 | ScanFeature | VoiceOver đọc kết quả theo thứ tự mức độ; haptic riêng cho "Phát hiện", "Có thể có", "Không chắc chắn" | MVP | 0,5 | CORE-E09-02 | Khi kết quả xuất hiện thì VoiceOver đọc câu tổng kết trước; mọi thông tin của haptic đều có ở dạng chữ |
| NDU-E05-04 | ScanFeature | Chia sẻ ảnh kết quả (ảnh, tô sáng, disclaimer, phiên bản từ điển, thời điểm) | V1.1 | 0,5 | NDU-E05-02 | Khi chia sẻ thì ảnh xuất có dòng "Công cụ hỗ trợ — luôn đọc lại nhãn" và phiên bản từ điển |
| NDU-E05-05 | ScanFeature | Overlay live "Xem trước" trên màn quét | V1.1 | 1,5 | NDU-E03-11 | Khi đang ngắm thì hit hiện với nhãn "Xem trước"; không có trạng thái "Không thấy" nào trước khi chốt |
| NDU-E05-06 | ExplainFeature | Giải thích dễ hiểu bằng Foundation Models, neo vào mục từ điển, nhãn "Do AI tạo", lọc đầu ra ⚠ | V1.1 | 3 | CORE-E04-02, CORE-E13-01, NDU-E05-02 | Khi FM không khả dụng thì nút ẩn và lý do từ từ điển vẫn hiện; khi đầu ra chứa từ cấm ("safe", "sicher", "sûr"…) thì bị loại |

Ghi chú:
- MVP đã có lý do do người viết cho từng mục từ điển (ví dụ "casein: protein của sữa → Sữa"). Foundation Models ở V1.1 chỉ diễn đạt lại cho dễ hiểu, không thêm dữ kiện mới. Quy định sử dụng Foundation Models cấm dịch vụ y tế có quản lý; cách dùng này cần rà lại trước khi bật ⚠.

## NDU-E06 · Thẻ dị ứng du lịch

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| NDU-E06-01 | AllergyCards | Mô hình template và gói câu mẫu đã dịch, đã duyệt (14 chất, 4 chế độ ăn, 3 mức độ, câu cấp cứu) cho 9 ngôn ngữ; trình tạo thẻ song ngữ | MVP | 1,5 | NDU-E01-02, NDU-E01-03 | Khi chọn ngôn ngữ đích IT thì thẻ dùng đúng câu mẫu IT đã duyệt kèm dòng dịch sang ngôn ngữ UI; không câu mẫu nào đi qua dịch máy |
| NDU-E06-02 | AllergyCards | Chế độ toàn màn hình offline (chữ lớn, tương phản cao, giữ màn hình sáng) và xuất PNG/PDF | MVP | 1 | CORE-E06-01, NDU-E06-01 | Khi bật chế độ máy bay thì thẻ vẫn mở và xuất được; màn hình không tự tắt khi đang hiện thẻ |
| NDU-E06-03 | AllergyCards | Ghi chú tùy chỉnh dịch bằng Translation framework (`.translationTask`), nhãn "Bản dịch máy, chưa kiểm tra" | MVP | 1 | NDU-E06-01 | Khi gói ngôn ngữ chưa tải và máy offline thì app báo rõ và vẫn hiện thẻ, không có ghi chú dịch |
| NDU-E06-04 | AllergenLensWidget | Widget và App Shortcut mở thẻ nhanh | V1.1 | 1,5 | CORE-E11-01, NDU-E06-02 | Khi chạm widget thì thẻ mở toàn màn hình trong ≤ 1 giây |
| NDU-E06-05 | AllergyCards | Thêm ngôn ngữ thẻ chỉ bằng dữ liệu (đề xuất PT, PL, FI, EL, HR ⚠) | V1.1 | 0,5 | NDU-E06-01 | Khi thêm file ngôn ngữ thẻ đã duyệt thì ngôn ngữ đó xuất hiện mà không phải sửa code |
| NDU-E06-06 | AllergyCards | Thẻ Apple Wallet (cần server ký pass) ⚠ | V2 | 3 | NDU-E06-02 | Khi thêm thẻ vào Wallet thì pass hiện đúng câu mẫu đã duyệt; khóa ký không nằm trong app |

Ghi chú:
- **Không có Wallet pass trong MVP.** Pass của Apple Wallet phải được ký bằng chứng chỉ Pass Type ID. Ký trên máy nghĩa là nhúng khóa riêng vào app, ai cũng trích ra được. Ký trên server thì phá nguyên tắc "MVP không có server" và có thể ảnh hưởng nhãn "Data Not Collected". Ảnh PNG trong Photos cộng widget (V1.1) đủ cho việc mở nhanh khi offline.
- Thẻ không cần OCR, nên ngôn ngữ thẻ không bị giới hạn bởi Live Text. Ví dụ thẻ tiếng Phần Lan vẫn làm được dù app chưa đọc được nhãn tiếng Phần Lan.

## NDU-E07 · Lịch sử & sản phẩm đã lưu

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| NDU-E07-01 | HistoryFeature | Lịch sử quét cục bộ: ảnh thu nhỏ, văn bản OCR, hit, độ phủ, phiên bản từ điển; danh sách, lọc, xóa | MVP | 1,5 | CORE-E05-01, CORE-E05-02, NDU-E08-01 | Khi chưa có Plus thì chỉ xem lại được lần quét gần nhất; khi có Plus thì thấy toàn bộ lịch sử và xóa được từng mục |
| NDU-E07-02 | HistoryFeature | Lưu sản phẩm (tên, ảnh, ghi chú); luôn hiện ngày quét và nút "Quét lại" | MVP | 1 | NDU-E07-01 | Khi mở sản phẩm đã lưu thì kết quả cũ hiện kèm ngày quét và lời nhắc "công thức có thể đã đổi" |
| NDU-E07-03 | HistoryFeature | Mã vạch chỉ làm khóa cục bộ (DataScanner `.barcode`), không tra cơ sở dữ liệu online | V1.1 | 1 | NDU-E07-02 | Khi quét mã vạch của sản phẩm đã lưu thì app mở sản phẩm đó và yêu cầu quét lại danh sách; không có request mạng |
| NDU-E07-04 | HistoryFeature | Phân tích lại lịch sử khi từ điển đổi phiên bản; đánh dấu mục có kết quả thay đổi | V1.1 | 1,5 | NDU-E07-01 | Khi từ điển mới thêm term khớp một sản phẩm đã lưu thì sản phẩm đó có nhãn "Kết quả đã thay đổi" |
| NDU-E07-05 | HistoryFeature | Đưa sản phẩm đã lưu vào Spotlight (chỉ index trên máy) | V2 | 1 | CORE-E11-01, NDU-E07-02 | Khi tìm tên sản phẩm trong Spotlight thì thấy sản phẩm và mở đúng màn |

## NDU-E08 · Paywall & gói

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| NDU-E08-01 | AllergenLens | Sản phẩm `ndu.plus.yearly` (trial 7 ngày), StoreKit Configuration, ánh xạ quyền lợi `familyProfiles`, `travelCards`, `history` | MVP | 1 | CORE-E07-01 | Khi mua hoặc khôi phục thì 3 quyền lợi mở ngay; khi gói hết hạn thì dữ liệu còn nguyên, chỉ bị khóa xem, và quét vẫn dùng đầy đủ |
| NDU-E08-02 | AllergenLens | Paywall theo ngữ cảnh (hồ sơ thứ 2, thẻ, lịch sử), ưu đãi cuối onboarding, xem trước thẻ | MVP | 1 | CORE-E07-02, NDU-E08-01 | Khi đóng paywall thì người dùng về đúng chỗ cũ và quét vẫn dùng được; checklist paywall của kế hoạch đạt 100% |
| NDU-E08-03 | AllergenLens | Offer code, win-back offer, "Quản lý gói" | V1.1 | 0,5 | CORE-E07-03 | Khi nhập offer code thì quyền lợi Plus kích hoạt |
| NDU-E08-04 | AllergenLens | Gói tháng hoặc gói trọn đời để thử nghiệm giá ⚠ | V2 | 0,5 | NDU-E08-01 | Khi thêm sản phẩm mới thì ánh xạ quyền lợi và các màn bị khóa không phải sửa |

Ghi chú: quét không giới hạn, cả 9 ngôn ngữ đọc, 14 chất, chế độ ăn, thành phần tùy chỉnh, cảnh báo "Có thể có" và chỉ báo độ phủ **luôn miễn phí**. Không đặt bất kỳ thông tin an toàn nào sau paywall.

## NDU-E09 · Bản địa hóa & tuân thủ

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| NDU-E09-01 | AllergenLens | String Catalog 7 locale UI (`en`, `en-GB`, `de`, `fr`, `it`, `es`, `nl`); tên chất lấy từ từ điển | MVP | 0,5 | CORE-E10-01 | Khi chạy 7 locale ở cỡ chữ lớn nhất thì không có chuỗi cứng và không bị cắt chữ |
| NDU-E09-02 | AllergenLens | Disclaimer theo ngữ cảnh, test chặn từ cấm ("safe", "an toàn", "sicher", "sûr"…), `PrivacyInfo.xcprivacy`, purpose string, Review Notes cho Guideline 1.4.1 | MVP | 1 | CORE-E13-01 | Khi String Catalog có từ cấm trong ngữ cảnh kết quả thì test fail |
| NDU-E09-03 | AllergenLens | Rà soát accessibility: VoiceOver, Dynamic Type, tương phản, không dùng màu làm kênh duy nhất, Reduce Motion; khai Accessibility Nutrition Labels | MVP | 1 | CORE-E09-01, CORE-E09-02 | Khi chỉ dùng VoiceOver thì hoàn tất được quét → kết quả → thẻ |
| NDU-E09-04 | (ci) | Metadata fastlane và ảnh màn hình 7 locale | MVP | 0,5 | CORE-E01-03 | Khi chạy lane thì metadata 7 locale lên App Store Connect và không có câu hứa "an toàn" |
| NDU-E09-05 | AllergenLens | UI đợt 2: `sv`, `da`, `nb` | V1.1 | 0,5 | NDU-E09-01 | Khi đổi ngôn ngữ máy sang SV, DA hoặc NB thì toàn bộ UI hiện đúng ngôn ngữ |
| NDU-E09-06 | AllergenLens | UI đợt 3: `pl`, `fi`, `pt-PT`, `vi` | V2 | 0,5 | NDU-E09-05 | Khi đổi ngôn ngữ máy sang một trong 4 locale thì UI hiện đúng; nếu chưa đọc được nhãn ngôn ngữ đó thì app nói rõ |

## NDU-E10 · An toàn & chất lượng

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| NDU-E10-01 | SafetyBench | Bộ văn bản an toàn và red-team chạy bằng Swift Testing (≥ 200 danh sách mỗi ngôn ngữ, có đáp án) | MVP | 1 | NDU-E03-10 | Khi chạy test thì recall "Phát hiện hoặc Có thể có" đạt 100% và có bảng theo chất × ngôn ngữ |
| NDU-E10-02 | SafetyBench | Bộ ảnh vàng nhãn thật chấm qua `ocr-bench`: recall/precision theo chất × ngôn ngữ, đếm critical miss và lỗi "Đủ" sai | MVP | 1 | CORE-E12-02, NDU-E10-01 | Khi chạy bench thì in bảng recall theo chất × ngôn ngữ và danh sách critical miss kèm ảnh |
| NDU-E10-03 | (ci) | Cổng phát hành: chặn khi có critical miss, recall giảm, lỗi "Đủ" sai vượt ngưỡng hoặc test từ điển fail | MVP | 0,5 | CORE-E01-02, NDU-E10-02 | Khi một PR làm xuất hiện critical miss thì workflow release fail |
| NDU-E10-04 | Lexicon | Tự kiểm lúc nạp từ điển (bộ câu kiểm tra cố định); trượt thì không cho trạng thái "Không thấy" | MVP | 0,5 | NDU-E04-01 | Khi từ điển nạp bị hỏng thì mọi chất hiện "Không chắc chắn" và app báo lỗi rõ |
| NDU-E10-05 | ScanFeature | "Báo bỏ sót / báo nhầm": soạn email để người dùng tự gửi; ảnh chỉ đính kèm khi người dùng bật | MVP | 0,5 | NDU-E05-02 | Khi người dùng báo bỏ sót thì email có văn bản OCR, phiên bản từ điển và engine; không có gì được gửi nếu người dùng không bấm gửi |
| NDU-E10-06 | ScanFeature | Lớp chẩn đoán nội bộ (dòng OCR, confidence, token, lý do) chỉ có trong build nội bộ | MVP | 0,5 | NDU-E05-02 | Khi build App Store thì cờ `NDU_INTERNAL` tắt và lớp chẩn đoán không có trong binary |
| NDU-E10-07 | SafetyBench | XCUITest luồng chính với ảnh tiêm vào pipeline và snapshot kết quả dạng JSON | MVP | 1 | CORE-E09-02, NDU-E05-01 | Khi thay đổi engine làm đổi kết quả của ảnh mẫu thì diff snapshot hiện trong PR |
| NDU-E10-08 | Lexicon | Trang "Có gì mới trong từ điển" trong app | V1.1 | 0,5 | NDU-E04-04 | Khi từ điển đổi phiên bản thì trang liệt kê số term thêm/bớt theo chất |

Định nghĩa **critical miss**: chất có trong phần danh sách nhìn thấy được trên ảnh, nhưng app báo "Không thấy trong phần đã đọc" trong khi độ phủ là "Đủ". Mục tiêu là 0 trên bộ ảnh vàng. Chỉ tiêu chi tiết ở [technical-design.md mục 12](technical-design.md#12-kiểm-thử).

## Tổng theo ưu tiên

| Ưu tiên | Số feature | Ngày công dev |
|---|---|---|
| MVP | 46 | 45 |
| V1.1 | 15 | 20 |
| V2 | 8 | 11 |
| **Tổng** | **69** | **76** |

Ngoài 45 ngày MVP còn **5 ngày spike** 🧪 (S1–S3 ở [technical-design.md mục 13](technical-design.md#13-spike-và-rủi-ro)), làm trước sprint 1.

MVP 45 ngày nằm ở cận trên của khung 35–45 ngày đã đặt. Lý do: phần phân tích (E03) và kiểm thử an toàn (E10) chiếm 17 ngày và không nên cắt. Nếu trễ lịch, cắt theo thứ tự:

| Thứ tự cắt | Feature | Tiết kiệm | Hệ quả |
|---|---|---|---|
| 1 | NDU-E01-07 Hồ sơ gia đình | 1 ngày | Paywall lúc ra mắt còn 2 quyền lợi (thẻ, lịch sử) |
| 2 | NDU-E06-03 Ghi chú dịch bằng Translation | 1 ngày | Thẻ chỉ có câu mẫu đã duyệt |
| 3 | NDU-E07-02 Lưu sản phẩm | 1 ngày | Chỉ còn lịch sử quét |

Không bao giờ cắt: NDU-E03-01 → NDU-E03-10, NDU-E10-01 → NDU-E10-04, NDU-E05-01 → NDU-E05-03, NDU-E09-02, NDU-E09-03.

## Lộ trình sprint

Kế hoạch 12 tháng đặt app 2 xây trong tháng 3–4/2027 và ra mắt tháng 5/2027, trước mùa du lịch hè. Bảng dưới giả định **1 dev toàn thời gian**, sprint 2 tuần, 10 ngày công mỗi sprint.

| Giai đoạn | Thời gian | Nội dung | Ngày |
|---|---|---|---|
| Tuần spike | 22–26/2/2027 | 🧪 S1 OCR bao bì cong/bóng, S2 độ chính xác OCR theo ngôn ngữ và chi tiết API DataScanner, S3 ngưỡng khớp mờ. S2 có thể chạy sớm hơn trên `ocr-bench` từ 1/2027 | 5 |
| Sprint 1 | 1–12/3 | Nền từ điển và engine: NDU-E01-06, NDU-E04-01, NDU-E04-02, NDU-E04-03, NDU-E03-01 → NDU-E03-05, NDU-E10-04 | 10 |
| Sprint 2 | 15–26/3 | Khớp và phân loại: NDU-E03-06 → NDU-E03-10, NDU-E10-01, NDU-E10-02, NDU-E10-03 | 10 |
| Sprint 3 | 29/3–9/4 | Chụp, onboarding, màn kết quả: NDU-E02-01 → NDU-E02-05, NDU-E01-01 → NDU-E01-03, NDU-E05-01 → NDU-E05-03, NDU-E10-06 | 10 |
| Sprint 4 | 12–23/4 | Hồ sơ, thẻ, lịch sử, gói: NDU-E01-04, NDU-E01-05, NDU-E01-07, NDU-E06-01 → NDU-E06-03, NDU-E07-01, NDU-E07-02, NDU-E08-01, NDU-E10-05 | 10 |
| Tuần phát hành | 26–30/4 | NDU-E08-02, NDU-E09-01 → NDU-E09-04, NDU-E10-07; chạy cổng phát hành; nộp App Review | 5 |
| Ra mắt | khoảng 5–7/5/2027 | FR, DE, IT, ES, NL, UK | – |

Mốc kiểm soát:
- **12/3:** engine chạy trên bộ văn bản của EN, DE, FR.
- **26/3:** engine đạt cổng trên bộ văn bản cả 9 ngôn ngữ; bench ảnh chạy được.
- **9/4:** TestFlight nội bộ có luồng quét → kết quả. Chốt chuỗi UI để gửi dịch.
- **13/4:** TestFlight external cho nhóm beta người dị ứng/coeliac (cần qua Beta App Review).
- **16/4:** đóng băng từ điển v1.0, đủ chữ ký 2 người duyệt cho mọi ngôn ngữ. Sau mốc này, mọi thay đổi từ điển phải qua lại toàn bộ cổng phát hành.
- **30/4:** nộp App Review kèm Review Notes cho Guideline 1.4.1.

Rủi ro lịch:
- Tổng cộng là 10 tuần (50 ngày công), không phải 8 tuần. Hai tuần chênh là tuần spike cuối tháng 2 và tuần nộp app cuối tháng 4.
- Theo kế hoạch 12 tháng, app 3 ra mắt trong tháng 3/2027, trùng sprint 1–2. Với 1 dev, việc sửa lỗi sau ra mắt của app 3 sẽ lấy ngày của app 2. Cách xử lý: dùng danh sách cắt ở trên, hoặc thuê thêm 1 dev bán thời gian khoảng 2 tuần cho `lexicon-build` và `SafetyBench`.
- V1.1 (20 ngày) rơi vào tháng 5–6/2027, trùng lúc xây app 4. Ưu tiên V1.1 theo phản hồi: ghép nhiều ảnh (NDU-E02-06) và cập nhật từ điển không cần bản app mới (NDU-E04-04) nên làm trước mùa du lịch hè.

## Nội dung (không phải dev)

Đây là phần việc lớn nhất của app, và quyết định độ an toàn. Ước tính theo người-ngày, do chuyên gia bản ngữ, chuyên gia thực phẩm/dinh dưỡng, dịch giả và luật sư làm. Mọi con số là ước tính của tài liệu này, cần chốt khi có báo giá.

| ID | Hạng mục | Người làm | Cách tính | Người-ngày |
|---|---|---|---|---|
| C01 | Trích nguồn quy định: danh sách 14 chất theo Annex II Quy định (EU) 1169/2011 bản chính thức từng ngôn ngữ; nguồn cho NB (Na Uy, EEA) và EN-UK (luật UK) ⚠ | Chuyên gia quy định thực phẩm | 0,5 × 9 ngôn ngữ | 4,5 |
| C02 | Soạn từ điển chất gây dị ứng: term, đồng nghĩa, dẫn xuất, luật từ ghép, loại trừ | Chuyên gia thực phẩm bản ngữ | EN làm bản trục 6 + 8 ngôn ngữ × 4 | 38 |
| C03 | Nhóm chế độ ăn (thuần chay, chay, lactose, coeliac) | Như trên | 1 × 9 | 9 |
| C04 | Bảng số E và nguồn có thể gây dị ứng hoặc nguồn động vật; chuyên gia duyệt ⚠ | Chuyên gia khoa học thực phẩm | 3 + 1,5 | 4,5 |
| C05 | Ngữ pháp nhãn: tiêu đề, dấu kết thúc, câu phòng ngừa, free-from, liên từ | Người bản ngữ | 0,5 × 9 | 4,5 |
| C06 | Duyệt độc lập lần 1 (người bản ngữ có chuyên môn dinh dưỡng hoặc dị ứng) | Chuyên gia dinh dưỡng bản ngữ | 2 × 9 | 18 |
| C07 | Duyệt ký lần 2, xử lý khác biệt | Người duyệt thứ hai | 1 × 9 | 9 |
| C08 | Mẫu thẻ dị ứng: soạn bản EN, duyệt y khoa các câu về mức độ và cấp cứu ⚠ | Chuyên gia dinh dưỡng/bác sĩ dị ứng | 2 + 1 | 3 |
| C09 | Dịch mẫu thẻ sang 8 ngôn ngữ và duyệt bản ngữ | Dịch giả + người duyệt | 8 × (0,75 + 0,5) | 10 |
| C10 | Thu thập bộ ảnh vàng: 450 nhãn thật (60 × EN, DE, FR, IT, ES, NL; 30 × SV, DA, NB) | Nhóm dự án + cộng tác viên ở EU | ước tính | 6 |
| C11 | Ghi đáp án cho ảnh vàng (chép danh sách, chất có mặt, độ khó) | Người ghi nhãn | 450 × khoảng 10 phút | 9,5 |
| C12 | Bộ văn bản an toàn và red-team (≥ 200 danh sách mỗi ngôn ngữ, phần lớn sinh từ C11 và biến thể) | Người bản ngữ | 1,5 × 9 | 13,5 |
| C13 | Dịch UI sang 6 locale ngoài tiếng Anh và duyệt | Dịch giả | 1,5 × 6 | 9 |
| C14 | Metadata App Store 7 locale với bộ từ khóa riêng | ASO + dịch giả | 0,5 × 7 | 3,5 |
| C15 | Rà soát pháp lý: disclaimer, mô tả App Store, privacy policy, câu trên thẻ, phạm vi MDR ⚠ | Luật sư EU | ước tính | 3 |
| C16 | Nhóm beta người dị ứng/coeliac: tuyển, hướng dẫn, tổng hợp phản hồi | Người phụ trách sản phẩm | ước tính | 3 |
| | **Tổng MVP** | | | **148** |

Tổng theo nhóm:

| Nhóm | Hạng mục | Người-ngày |
|---|---|---|
| Từ điển | C01–C07 | 87,5 |
| Thẻ dị ứng | C08–C09 | 13 |
| Bộ kiểm thử an toàn | C10–C12 | 29 |
| Bản địa hóa UI và metadata | C13–C14 | 12,5 |
| Pháp lý và beta | C15–C16 | 6 |
| **Tổng** | | **148** |

Phần nội dung gấp khoảng 3,3 lần phần dev của MVP. Lịch đề xuất:
- **12/2026:** C01, bản trục EN của C02, C04; tuyển người duyệt cho 9 ngôn ngữ.
- **1/2027:** C02 và C03 cho 8 ngôn ngữ còn lại, C05; bắt đầu C10.
- **2/2027:** C06, C08, C11.
- **3/2027:** C07, C09, C12, C13.
- **4/2027:** đóng băng từ điển 16/4; C14, C15, C16.

Nội dung sau MVP (ước tính):
- **V1.1, khoảng 22,5 người-ngày:** thêm 5 ngôn ngữ thẻ (6,5), dịch UI SV, DA, NB (4,5), đánh giá câu giải thích của Foundation Models theo ngôn ngữ UI (3,5), trực từ điển và xử lý báo bỏ sót trong 8 tuần đầu (khoảng 1 ngày mỗi tuần, 8).
- **V2:** từ điển và bộ vàng PT, PL (khoảng 11 mỗi ngôn ngữ); FI chỉ sau spike NDU-E04-06; dịch UI đợt 3 (6).
