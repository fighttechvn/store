# Epic và feature: Sổ chứng từ riêng tư (`SCT`)

Quy ước ID, ưu tiên, ước tính và cách viết tiêu chí nghiệm thu theo [README chung](../README.md). Ước tính là ngày công của 1 dev iOS có kinh nghiệm, đã gồm unit test, chưa gồm thiết kế UI, dịch thuật và nội dung.

Feature của lõi (`CORE-…`) không lặp lại ở đây, chỉ xuất hiện trong cột "Phụ thuộc". Xem [shared-core.md](../shared-core.md). Module `RB…` là module riêng của app, mô tả ở [technical-design.md §2](technical-design.md#2-module-map). Bản CSV: [backlog.csv](backlog.csv).

## Danh sách epic

| ID | Epic | Mục tiêu | Module | Ngày MVP | Tổng ngày |
|---|---|---|---|---|---|
| SCT-E01 | Onboarding & hồ sơ | Có hồ sơ doanh nghiệp đúng quốc gia và cài đặt thuế trong dưới 1 phút, không cần tài khoản | RBCountry, RBOnboarding | 3 | 8,5 |
| SCT-E02 | Chụp & nhập chứng từ | Đưa mọi chứng từ vào app trong vài giây: camera, Photos, Files, Share Extension từ Mail | RBCapture, ReceiptBookShare | 5,5 | 9 |
| SCT-E03 | Nhận dạng & trích xuất | Trích người bán, ngày, tổng, VAT nhiều bậc, tiền tệ, số hóa đơn, có độ tin cậy từng trường và màn sửa nhanh | RBExtract | 10,5 | 18 |
| SCT-E04 | Hóa đơn điện tử | Đọc XRechnung (UBL, CII) và ZUGFeRD/Factur-X không cần OCR, hiển thị dạng đọc được | RBEInvoice | 7 | 15 |
| SCT-E05 | Phân loại & sổ sách | Xếp chứng từ vào danh mục của từng nước bằng luật, AI trên máy và sửa đổi của người dùng | RBLedger | 5,5 | 11 |
| SCT-E06 | Kỳ báo cáo & xuất | Gói xuất theo kỳ cho kế toán: CSV, PDF kỳ, ZIP có SHA-256 | RBReporting | 5,5 | 16,5 |
| SCT-E07 | Lưu trữ, bảo mật & toàn vẹn | Số tiền chính xác, bản gốc bất biến, khóa app, không giam dữ liệu, sao lưu | RBDomain, RBVault | 4 | 13,5 |
| SCT-E08 | Tìm kiếm & tích hợp hệ thống | Tìm chứng từ trong app; Spotlight, Shortcuts, widget | RBSystem, ReceiptBookWidget | 1 | 7 |
| SCT-E09 | Paywall & gói | Thu tiền cho đầu ra, không khóa dữ liệu, tuân thủ luật paywall | RBPaywall | 2,5 | 4,5 |
| SCT-E10 | Bản địa hóa & tuân thủ | EN-US, EN-GB, DE, FR; disclaimer; privacy; Review Notes | ReceiptBook, RBCountry | 2,5 | 4 |
| SCT-E11 | Chế độ Việt Nam | Sổ thu chi hộ kinh doanh, OCR tiếng Việt, hóa đơn điện tử VN | RBVietnam | 0 | 11,5 |
| SCT-E12 | Chất lượng | Bộ dữ liệu vàng, bench độ chính xác trong CI, test UI và StoreKit | (tools), Tests | 3 | 6,5 |
| | **Tổng** | | | **50** | **125** |

## SCT-E01 · Onboarding & hồ sơ

Người dùng mở app, chọn nước và loại hình, rồi chụp được ngay. Mọi quy tắc theo nước (tiền tệ, bậc VAT, kỳ, danh mục, định dạng CSV) nằm trong "gói quốc gia" dạng dữ liệu, không nằm trong code.

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| SCT-E01-01 | RBCountry | Định dạng "gói quốc gia" (JSON trong bundle) và loader: tiền tệ, bậc VAT có hiệu lực theo ngày, quy tắc kỳ, bộ danh mục, định dạng CSV, khóa disclaimer. Gói UK, DE, FR, US | MVP | 1 | CORE-E10-01 | Khi nạp 4 gói thì validator không báo lỗi; khi chọn DE thì tiền tệ mặc định là EUR và bậc 19% có sẵn |
| SCT-E01-02 | RBOnboarding | Onboarding 3 bước: lời hứa "chứng từ không rời iPhone", chọn quốc gia (gợi ý theo storefront), chọn loại hình (sole trader, landlord, Freiberufler, Kleinunternehmer, micro-entrepreneur ⚠, self-employed). Không tài khoản | MVP | 1,5 | SCT-E01-01; SCT-E07-01; CORE-E09-01; CORE-E13-01 | Khi hoàn tất thì có đúng 1 `BusinessProfile`; không màn nào hỏi email hay đăng nhập; disclaimer thuế hiện đúng 1 lần |
| SCT-E01-03 | RBOnboarding | Cài đặt thuế của hồ sơ: có đăng ký VAT không, cờ Kleinunternehmer (§19 UStG) ⚠, tiền tệ gốc, ngày bắt đầu năm thuế (UK 6/4 ⚠), loại kỳ; sửa được trong Cài đặt | MVP | 0,5 | SCT-E01-02 | Khi đổi ngày bắt đầu năm thuế thì mọi chứng từ được gán lại kỳ và tổng ở màn sổ cập nhật |
| SCT-E01-04 | RBOnboarding | Nhiều hồ sơ doanh nghiệp, chuyển nhanh ở thanh trên (Pro) | V1.1 | 2 | SCT-E01-03; SCT-E09-02 | Khi có 2 hồ sơ thì chứng từ, danh mục, luật, kỳ và file xuất tách biệt; người dùng free chỉ tạo được 1 hồ sơ |
| SCT-E01-05 | RBOnboarding | Thẻ bất động sản hoặc dự án (landlord ở UK), lọc và xuất theo thẻ | V1.1 | 1,5 | SCT-E01-03; SCT-E06-03 | Khi gắn 3 chứng từ vào thẻ "Flat 2" thì CSV có cột thẻ và tổng theo thẻ khớp màn sổ |
| SCT-E01-06 | RBCountry | Gói quốc gia AT và CH (CHF, bậc VAT, danh mục) ⚠ | V2 | 2 | SCT-E01-01 | Khi chọn CH thì tiền tệ là CHF và bậc VAT lấy từ gói đã được xác minh |

## SCT-E02 · Chụp & nhập chứng từ

Hóa đơn điện tử ở Đức thường đến dưới dạng file đính kèm email. Vì vậy Share Extension và "Mở bằng ReceiptBook" nằm trong MVP, không để sau. Extension chỉ chép file vào hộp nhận; mọi xử lý nặng chạy trong app.

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| SCT-E02-01 | RBCapture | Luồng chụp: nút chụp nổi → document camera của CORE → tạo `Document` và `Page`; sau khi quét nhiều trang hỏi "1 chứng từ" hay "mỗi trang 1 chứng từ" | MVP | 1 | CORE-E02-01; SCT-E07-02 | Khi quét 3 trang và chọn "mỗi trang 1 chứng từ" thì có 3 `Document`, mỗi cái 1 `Page`, ảnh gốc lưu nguyên và thẻ hiện trong Hộp nhận ≤ 0,5 giây |
| SCT-E02-02 | RBCapture | Nhập từ Photos và Files (ảnh, PDF nhiều trang, XML), nhận diện loại bằng `UTType`; đăng ký "Mở bằng ReceiptBook" cho PDF và XML | MVP | 0,5 | CORE-E02-03; SCT-E07-02 | Khi nhập PDF 3 trang thì có 1 `Document` với 3 `Page` và SHA-256 lưu trong app khớp file nguồn |
| SCT-E02-03 | ReceiptBookShare | Share Extension nhận PDF, XML, ảnh từ Mail, Files, Safari: chỉ chép file vào hộp nhận App Group kèm metadata, không OCR, không gọi mạng | MVP | 2 | SCT-E02-04 | Khi chia sẻ 1 file XRechnung `.xml` từ Mail thì lần mở app kế tiếp chứng từ nằm trong Hộp nhận với nguồn `shareExtension` |
| SCT-E02-04 | RBCapture | Hàng đợi xử lý bền (Hộp nhận): trạng thái chờ, đang xử lý, cần xem lại, xong, lỗi; xử lý tuần tự; tiếp tục sau khi app bị tắt | MVP | 1 | SCT-E07-01 | Khi tắt app giữa lúc OCR rồi mở lại thì chứng từ được xử lý tiếp, không mất và không nhân đôi |
| SCT-E02-05 | RBCapture | Phát hiện trùng: SHA-256 file (chặn) và so khớp mờ người bán, ngày, tổng, số hóa đơn (cảnh báo) | MVP | 1 | SCT-E03-05 | Khi nhập lại cùng 1 file thì app báo "đã có" và không tạo bản mới; khi chụp lại cùng biên lai thì hiện cảnh báo kèm link tới bản cũ |
| SCT-E02-06 | RBCapture | Nhắc lau camera khi ảnh có dấu hiệu ống kính bẩn | V1.1 | 0,5 | CORE-E02-04 | Khi điểm smudge vượt ngưỡng thì hiện nhắc trước khi lưu, người dùng vẫn lưu được |
| SCT-E02-07 | RBCapture | Nhập hàng loạt từ một thư mục trong Files, có báo cáo kết quả | V1.1 | 1 | SCT-E02-02; SCT-E02-05 | Khi chọn 50 file thì app báo số file đã nhập, trùng và lỗi, giao diện không bị treo |
| SCT-E02-08 | RBCapture | Chụp từ màn hình khóa bằng LockedCameraCapture ⚠ | V2 | 2 | SCT-E02-01 | Khi mở từ màn hình khóa thì chỉ chụp được, không xem được chứng từ cũ |

## SCT-E03 · Nhận dạng & trích xuất

App thêm extractor riêng cho chứng từ, conform `FieldExtractor` của `CoreExtraction`. Luật chạy trên mọi máy và chạy trước. Foundation Models chỉ lấp trường thiếu. Mọi trường có điểm tin cậy và nguồn.

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| SCT-E03-01 | RBExtract | Điều phối OCR: PDF có lớp chữ thì lấy chữ bằng PDFKit, còn lại OCR bằng CORE; gộp nhiều trang; lưu văn bản và bounding box | MVP | 1 | CORE-E03-01; CORE-E03-02; CORE-E03-03 | Khi nhập PDF hóa đơn có lớp chữ thì không chạy OCR và văn bản khớp `PDFPage.string`; khi OCR ảnh 2 trang thì mỗi dòng có số trang và tọa độ |
| SCT-E03-02 | RBExtract | `ReceiptRuleExtractor` (conform `FieldExtractor`): tổng, ngày, người bán, số hóa đơn, tiền tệ, phương thức thanh toán, loại chứng từ (biên lai, hóa đơn, credit note); từ khóa EN, DE, FR | MVP | 3 | CORE-E04-01; SCT-E03-01 | Khi chạy trên bộ vàng EN/DE/FR thì đạt ngưỡng "chỉ luật" ở mục 12 của thiết kế (tổng ≥ 92%, ngày ≥ 90%) |
| SCT-E03-03 | RBExtract | Tách nhiều dòng VAT (bậc, net, VAT, gross) từ bảng thuế; hỗ trợ mã A/B trên biên lai Đức và dòng "VAT @ 20%" | MVP | 1,5 | SCT-E03-02 | Khi biên lai DE có bậc 19% và 7% thì ra 2 `VATLine` và tổng gross khớp tổng chứng từ trong dung sai |
| SCT-E03-04 | RBExtract | `ReceiptLLMExtractor`: `@Generable ReceiptDraft` có `@Guide`; chỉ chạy khi Foundation Models khả dụng và hỗ trợ ngôn ngữ; cắt khối theo token | MVP | 1,5 | CORE-E04-02; SCT-E03-01 | Khi Foundation Models không khả dụng thì pipeline vẫn trả kết quả từ luật; khi khả dụng thì trường luật bỏ trống được lấp với nguồn `llm` |
| SCT-E03-05 | RBExtract | Hợp nhất và kiểm tra: `MergedExtractor`, kiểm tra toán VAT, ngày hợp lý, bậc VAT có trong gói; gắn cờ "cần xem lại" | MVP | 1,5 | CORE-E04-03; SCT-E03-03; SCT-E03-04 | Khi net + VAT lệch gross quá dung sai thì chứng từ ở trạng thái cần xem lại và trường lệch được tô |
| SCT-E03-06 | RBExtract | Màn xem lại và sửa: ảnh có khung vùng nguồn, nhập số theo locale, nút chấp nhận nhanh; mỗi lần sửa ghi audit | MVP | 2 | SCT-E03-05; CORE-E05-03 | Khi sửa tổng tiền thì có `AuditEntry` với giá trị cũ, mới và nguồn `user`; khi nhập "1.234,56" với hồ sơ DE thì lưu 1234.56 |
| SCT-E03-07 | RBExtract | Học theo người bán: chuẩn hóa tên (alias), nhớ tiền tệ, bậc VAT, phương thức thanh toán thường gặp | V1.1 | 1,5 | SCT-E03-06 | Khi đổi "SHELL DEUTSCHLAND OIL GMBH" thành "Shell" một lần thì các chứng từ sau của người bán này tự hiện "Shell" |
| SCT-E03-08 | RBExtract | Trích dòng hàng từ bảng của `RecognizeDocumentsRequest` | V1.1 | 3 | SCT-E03-02 | Khi hóa đơn có bảng 5 dòng thì ra 5 dòng hàng và tổng các dòng khớp net ± 1 đơn vị nhỏ nhất |
| SCT-E03-09 | RBExtract | Chứng từ ngoại tệ: nhập tỷ giá tay, lưu cả số gốc và số quy đổi | V1.1 | 1 | SCT-E03-06 | Khi có chứng từ USD trong hồ sơ GBP thì CSV có số gốc, tiền tệ gốc, tỷ giá và số quy đổi |
| SCT-E03-10 | RBExtract | Từ khóa và định dạng số cho IT, ES, NL (bản địa hóa đợt 2) | V2 | 2 | SCT-E03-02 | Khi chạy bộ vàng IT/ES/NL thì tổng tiền đúng ≥ 90% |

## SCT-E04 · Hóa đơn điện tử

MVP đọc XRechnung (UBL và CII) và XML nhúng trong ZUGFeRD/Factur-X (PDF/A-3). MVP không có kiểm tra KoSIT đầy đủ; app ghi rõ điều này trên màn hình. XML gốc là bản lưu trữ chính và không bao giờ bị sửa.

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| SCT-E04-01 | RBEInvoice | 🧪 Spike: trích file nhúng từ PDF/A-3 bằng `CGPDFDocument` (Names → EmbeddedFiles, `/AF`) trên 10 file ZUGFeRD/Factur-X mẫu | MVP | 1 | | Khi xong spike thì có báo cáo: tỷ lệ trích được, cách xử lý stream nén và PDF mã hóa, quyết định giữ hay đổi cách làm |
| SCT-E04-02 | RBEInvoice | Nhận diện định dạng theo namespace gốc; parser UBL 2.1 (XRechnung UBL: Invoice, CreditNote) → `EInvoice`; tắt entity ngoài, từ chối DOCTYPE | MVP | 2 | SCT-E07-01 | Khi parse bộ mẫu UBL thì số hóa đơn, ngày, người bán, tổng net, VAT, gross và từng nhóm thuế khớp giá trị trong XML 100% |
| SCT-E04-03 | RBEInvoice | Parser CII (XRechnung CII, ZUGFeRD, Factur-X) → cùng model `EInvoice` | MVP | 1,5 | SCT-E04-02 | Khi parse bộ mẫu CII thì đạt cùng tiêu chí như parser UBL |
| SCT-E04-04 | RBEInvoice | Trích XML nhúng từ PDF theo kết quả spike; PDF giữ làm bản hiển thị | MVP | 1 | SCT-E04-01; SCT-E04-03 | Khi nhập PDF ZUGFeRD thì chứng từ có cả PDF và XML gốc, các trường lấy từ XML với nguồn `eInvoice` và không chạy OCR |
| SCT-E04-05 | RBEInvoice | Ánh xạ `EInvoice` → `Document` và `VATLine`; màn xem dạng đọc được (người bán, người mua, dòng hàng, thuế, thanh toán) | MVP | 1 | SCT-E04-02 | Khi mở XRechnung chỉ có XML thì người dùng thấy bản đọc được, không thấy XML thô, và có nút xem XML gốc |
| SCT-E04-06 | RBEInvoice | Kiểm tra cơ bản: trường bắt buộc, tổng dòng = net, net + VAT = gross; ghi rõ đây không phải kiểm tra KoSIT đầy đủ | MVP | 0,5 | SCT-E04-05 | Khi XML có tổng lệch thì hiện cảnh báo và chứng từ ở trạng thái cần xem lại |
| SCT-E04-07 | RBEInvoice | Xử lý đủ các profile ZUGFeRD/Factur-X, gồm profile không có dòng hàng ⚠ | V1.1 | 1 | SCT-E04-03 | Khi profile không có dòng hàng thì vẫn nhập được tổng và thuế, không báo lỗi |
| SCT-E04-08 | RBEInvoice | Kiểm tra một phần quy tắc nghiệp vụ EN 16931 trên máy ⚠ | V2 | 5 | SCT-E04-06 | Khi chạy bộ test chính thức đã chọn thì mọi quy tắc đã cài cho kết quả giống bộ kiểm tra tham chiếu |
| SCT-E04-09 | RBEInvoice | Hóa đơn điện tử Pháp theo cải cách (mốc và định dạng ⚠) | V2 | 2 | SCT-E04-03 | Khi nhập hóa đơn mẫu theo định dạng đã xác minh thì các trường chính khớp 100% |

## SCT-E05 · Phân loại & sổ sách

Danh mục là dữ liệu trong gói quốc gia, mỗi danh mục có mã ổn định. Thứ tự phân loại: luật của người dùng → luật học được → luật từ khóa của gói → Foundation Models → "Chưa phân loại". App không tự tạo luật ngầm; chỉ đề xuất.

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| SCT-E05-01 | RBLedger | Bộ danh mục theo quốc gia trong gói (UK self-employment, UK property, DE kiểu EÜR, FR, US) ⚠ danh sách; danh mục tùy chỉnh ánh xạ về mã chuẩn | MVP | 1,5 | SCT-E01-01 | Khi hồ sơ là UK thì chỉ thấy danh mục UK; danh mục tùy chỉnh vẫn xuất mã chuẩn trong CSV |
| SCT-E05-02 | RBLedger | Rules engine (người bán, từ khóa, khoảng tiền, bậc VAT, phương thức) và học từ sửa đổi: đề xuất luật, không tự tạo ngầm | MVP | 1,5 | SCT-E05-01 | Khi người dùng xếp cùng người bán vào 1 danh mục 2 lần thì app đề xuất luật; luật đã lưu áp cho chứng từ mới |
| SCT-E05-03 | RBLedger | Tự phân loại (Pro): luật trước, sau đó Foundation Models chọn trong danh sách mã của gói (schema động); không có Foundation Models thì dùng luật từ khóa của gói; nhãn "gợi ý" | MVP | 1,5 | CORE-E04-02; SCT-E05-02; SCT-E09-02 | Khi Foundation Models không khả dụng thì vẫn có gợi ý từ luật; mã do Foundation Models trả về luôn nằm trong danh sách của gói |
| SCT-E05-04 | RBLedger | Màn sổ theo kỳ: danh sách, lọc danh mục và trạng thái, tổng theo danh mục, tổng VAT theo bậc | MVP | 1 | SCT-E06-01 | Khi xem Q3 thì tổng theo danh mục bằng tổng cột tương ứng trong CSV cùng kỳ |
| SCT-E05-05 | RBLedger | Tách 1 chứng từ vào nhiều danh mục | V1.1 | 2 | SCT-E05-04 | Khi tách 100 € thành 60 € và 40 € thì CSV có 2 dòng và tổng vẫn là 100 € |
| SCT-E05-06 | RBLedger | Tỷ lệ dùng cho kinh doanh (ví dụ điện thoại 50%) ⚠ quy tắc thuế từng nước | V1.1 | 1,5 | SCT-E05-04 | Khi đặt 50% thì CSV có cả số gốc và phần kinh doanh |
| SCT-E05-07 | RBLedger | Khoản thu: đánh dấu chứng từ là thu hoặc nhập tay; tổng thu và chi theo kỳ | V1.1 | 2 | SCT-E05-04 | Khi thêm 2 khoản thu thì màn sổ và CSV tách riêng thu và chi |

## SCT-E06 · Kỳ báo cáo & xuất

PDF một chứng từ luôn miễn phí. Xuất theo kỳ là tính năng Pro. Mẫu cho từng phần mềm kế toán để sau vì định dạng chưa được xác minh.

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| SCT-E06-01 | RBReporting | Quy tắc kỳ theo gói quốc gia (UK quý theo năm thuế ⚠, DE Monat/Quartal/Jahr, FR mois/trimestre, US quý) và khoảng tùy chọn; gán kỳ theo ngày chứng từ | MVP | 1 | SCT-E01-03 | Khi hồ sơ UK bắt đầu năm thuế 6/4 thì chứng từ ngày 5/7 thuộc quý 1 và ngày 6/7 thuộc quý 2, theo bảng kỳ đã xác minh ⚠ |
| SCT-E06-02 | RBReporting | PDF một chứng từ (miễn phí): bản gốc, trường đã trích, SHA-256 | MVP | 0,5 | CORE-E06-01; SCT-E03-06 | Khi xuất PDF đơn thì hash in trên PDF khớp hash tính lại từ file gốc |
| SCT-E06-03 | RBReporting | CSV theo kỳ (Pro): schema cột cố định, 1 dòng cho mỗi bậc VAT, định dạng theo quốc gia của hồ sơ | MVP | 1 | CORE-E06-02; SCT-E06-01 | Khi mở CSV bằng Excel bản DE thì cột và số đúng; tổng cột gross khớp màn sổ |
| SCT-E06-04 | RBReporting | Gói ZIP cho kế toán (Pro): CSV, PDF kỳ, bản gốc (ảnh, PDF, XML), audit, `manifest.csv` SHA-256 | MVP | 1 | CORE-E06-03; SCT-E06-03; SCT-E06-05 | Khi giải nén và tính lại SHA-256 thì 100% file khớp manifest |
| SCT-E06-05 | RBReporting | PDF tổng hợp kỳ (Pro): trang tóm tắt theo danh mục và bậc VAT, sau đó mỗi chứng từ 1 trang | MVP | 1 | CORE-E06-01; SCT-E06-01 | Khi kỳ có 50 chứng từ thì PDF có trang tóm tắt và 50 trang chứng từ, tổng khớp CSV |
| SCT-E06-06 | RBReporting | Màn xuất: chọn kỳ, kiểm tra trước khi xuất (cần xem lại, thiếu ngày, nghi trùng), xem trước tổng, chia sẻ; đánh dấu lần xuất lỗi thời khi chứng từ trong kỳ bị sửa | MVP | 1 | SCT-E06-04 | Khi kỳ còn chứng từ cần xem lại thì app liệt kê trước khi cho xuất; khi sửa chứng từ của kỳ đã xuất thì `ExportBatch.isStale` là true và có banner |
| SCT-E06-07 | RBReporting | CSV nhập cho Xero, QuickBooks, FreeAgent ⚠ định dạng | V1.1 | 2 | SCT-E06-03 | Khi nhập file mẫu vào tài khoản thử của từng phần mềm thì không có dòng lỗi |
| SCT-E06-08 | RBReporting | Xuất cho DATEV (Buchungsstapel) và CSV cho lexoffice, sevDesk ⚠ định dạng và điều kiện sử dụng | V1.1 | 3 | SCT-E06-03 | Khi một Steuerberater thử nhập file mẫu thì không có dòng lỗi |
| SCT-E06-09 | RBReporting | Nhắc hạn kỳ bằng thông báo cục bộ (hạn MTD theo quý ⚠) | V1.1 | 1 | SCT-E06-01 | Khi còn 7 ngày tới hạn của kỳ đã chọn thì có 1 thông báo cục bộ; không có thông báo nào đi qua server |
| SCT-E06-10 | RBReporting | Xuất Excel `.xlsx` bằng writer tự viết, không dùng SDK | V2 | 3 | SCT-E06-03 | Khi mở bằng Excel và Numbers thì số là kiểu số và ngày là kiểu ngày |
| SCT-E06-11 | RBReporting | Mẫu xuất cho phần mềm kế toán phổ biến ở Pháp ⚠ chọn phần mềm | V2 | 2 | SCT-E06-03 | Khi nhập file mẫu vào phần mềm đã chọn thì không có dòng lỗi |

## SCT-E07 · Lưu trữ, bảo mật & toàn vẹn

Tiền không bao giờ dùng `Double`. Bản gốc ghi một lần và không bị sửa. Cách làm theo tinh thần GoBD nhưng app **không** tuyên bố tuân thủ GoBD ⚠.

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| SCT-E07-01 | RBDomain | Schema SwiftData v1 (`VersionedSchema`), kiểu `Money` (Decimal + mã ISO 4217, lưu số nguyên đơn vị nhỏ nhất), `DayKey`; tương thích CloudKit từ đầu (thuộc tính có giá trị mặc định, quan hệ optional) | MVP | 1,5 | CORE-E05-01 | Khi lưu rồi đọc lại 1.000 số tiền ngẫu nhiên thì khớp tuyệt đối; lint báo lỗi nếu có `Double` trong trường tiền |
| SCT-E07-02 | RBVault | Bản gốc bất biến: ghi byte gốc 1 lần qua `BlobStore`, SHA-256 lúc nhập, không ghi đè; xóa mềm có lý do và thùng rác | MVP | 1 | CORE-E05-02; CORE-E05-03 | Khi sửa trường hoặc xoay ảnh xem trước thì file gốc và hash không đổi; khi xóa thì chứng từ vào thùng rác và có `AuditEntry` |
| SCT-E07-03 | RBVault | Mở rộng khóa app của CORE: yêu cầu Face ID khi xuất; không lộ ảnh chứng từ trong app switcher | MVP | 0,5 | CORE-E08-01 | Khi bật khóa thì xuất ZIP phải xác thực lại; ảnh chụp app switcher không có nội dung chứng từ |
| SCT-E07-04 | RBVault | Xuất toàn bộ bản gốc ra một thư mục trong Files (miễn phí, kèm danh sách SHA-256, không có CSV hay PDF kỳ) và xóa toàn bộ dữ liệu trên máy (2 bước xác nhận) | MVP | 1 | SCT-E07-02 | Khi xuất toàn bộ bản gốc thì thư mục có mọi file gốc và SHA-256 tính lại khớp danh sách; khi xác nhận xóa thì store SwiftData và BlobStore trống và app quay về onboarding |
| SCT-E07-05 | RBVault | Xem lịch sử sửa (audit) trong chi tiết chứng từ | V1.1 | 0,5 | CORE-E05-03 | Khi mở lịch sử thì thấy mọi thay đổi với thời điểm, nguồn, giá trị cũ và mới |
| SCT-E07-06 | RBVault | Kiểm tra toàn vẹn định kỳ và chuỗi hash cho audit log | V1.1 | 1 | SCT-E07-02 | Khi 1 file gốc bị thay đổi ngoài app thì lần kiểm tra kế tiếp báo đúng chứng từ đó |
| SCT-E07-07 | RBVault | Sao lưu mã hóa `.sctbackup` (AES-GCM, khóa dẫn từ mật khẩu ⚠ thuật toán) và khôi phục | V1.1 | 3 | SCT-E07-02 | Khi khôi phục bản sao lưu trên máy khác thì số chứng từ, hash và tổng mọi kỳ khớp máy gốc |
| SCT-E07-08 | RBVault | Nhắc thời hạn lưu trữ theo quốc gia ⚠ số năm; cảnh báo khi xóa chứng từ còn trong hạn | V1.1 | 1 | SCT-E07-02; SCT-E01-01 | Khi xóa chứng từ còn trong thời hạn của gói thì app cảnh báo trước khi cho xóa |
| SCT-E07-09 | RBVault | Đồng bộ CloudKit tùy chọn, mặc định tắt (Pro) ⚠ ảnh hưởng nhãn quyền riêng tư | V1.1 | 4 | SCT-E07-01; SCT-E09-02 | Khi bật trên 2 máy thì chứng từ mới xuất hiện ở máy kia; khi tắt thì không còn dữ liệu nào gửi đi |

## SCT-E08 · Tìm kiếm & tích hợp hệ thống

MVP chỉ có tìm kiếm trong app. Khung App Intents và `IndexedEntity` của lõi là `V1.1` (CORE-E11-01), nên các tích hợp hệ thống cũng là `V1.1`.

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| SCT-E08-01 | RBSystem | Tìm kiếm trong app: người bán, số tiền, số hóa đơn, văn bản OCR | MVP | 1 | SCT-E03-01 | Khi có 5.000 chứng từ thì kết quả hiện trong ≤ 300 ms trên iPhone 12 |
| SCT-E08-02 | RBSystem | Spotlight `IndexedEntity`: chỉ người bán, ngày, tổng; xóa chỉ mục khi bật khóa app | V1.1 | 1 | CORE-E11-01 | Khi tìm tên người bán trong Spotlight thì thấy chứng từ; khi bật khóa thì chỉ mục bị xóa |
| SCT-E08-03 | RBSystem | App Intents và App Shortcuts: "Thêm chứng từ", "Tổng chi quý này" | V1.1 | 1,5 | CORE-E11-01; SCT-E05-04 | Khi hỏi Siri "Tổng chi quý này" thì nhận đúng tổng của kỳ hiện tại; khi bật khóa thì phải mở app để xác thực |
| SCT-E08-04 | ReceiptBookWidget | Widget: nút chụp nhanh, tổng chi kỳ hiện tại (ẩn số khi bật khóa) | V1.1 | 1,5 | SCT-E08-03 | Khi thêm chứng từ thì widget cập nhật ở lần làm mới kế tiếp; khi bật khóa thì widget không hiện số tiền |
| SCT-E08-05 | RBSystem | 🧪 Camera Control và Visual Intelligence qua App Intents ⚠ API trên iOS 26 | V1.1 | 2 | SCT-E08-03 | Khi dùng Visual Intelligence trên một biên lai thì có hành động "Thêm vào ReceiptBook" mở đúng luồng nhập |

## SCT-E09 · Paywall & gói

Paywall chỉ liệt kê tính năng đã có trong bản đang phát hành (Guideline 3.1.2(c)). Ở MVP đó là xuất theo kỳ và tự phân loại. "Nhiều doanh nghiệp" chỉ vào danh sách quyền lợi khi SCT-E01-04 phát hành.

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| SCT-E09-01 | RBPaywall | Cấu hình sản phẩm `sct.pro.yearly` (trial 7 ngày), `sct.pro.monthly`, `sct.pro.lifetime` → quyền lợi `pro`; bảng tính năng bị khóa | MVP | 1 | CORE-E07-01 | Khi mua bất kỳ sản phẩm nào thì tính năng Pro mở ngay; khi hoàn tiền thì khóa lại ở lần kiểm tra kế tiếp |
| SCT-E09-02 | RBPaywall | Điểm chặn theo ngữ cảnh: xuất theo kỳ (CSV, ZIP, PDF kỳ), tự phân loại; không chặn chụp, lưu, xem, tìm, PDF đơn, xóa | MVP | 0,5 | SCT-E09-01 | Khi người dùng free bấm "Xuất quý" thì thấy paywall; khi đóng paywall thì mọi tính năng miễn phí vẫn dùng được |
| SCT-E09-03 | RBPaywall | Nội dung paywall theo storefront: gói đặt cạnh nhau, giá thực là chữ lớn nhất, mốc "Ngày 7", gói trọn đời chỉ ở DE/AT/CH, quyền lợi ghi cụ thể; hiện 1 lần ở cuối onboarding, có nút đóng | MVP | 1 | CORE-E07-02; SCT-E09-02 | Khi so với checklist paywall của kế hoạch thì đạt 100%; storefront FR không hiện gói trọn đời |
| SCT-E09-04 | RBPaywall | Offer code, win-back, "Quản lý gói" | V1.1 | 0,5 | CORE-E07-03 | Khi nhập offer code hợp lệ thì quyền lợi Pro kích hoạt |
| SCT-E09-05 | RBPaywall | A/B paywall không cần SDK: mỗi biến thể dùng product ID riêng, đọc kết quả từ báo cáo App Store Connect ⚠ | V1.1 | 1,5 | SCT-E09-03 | Khi chạy 2 biến thể thì báo cáo Sales tách được số trial và số trả tiền theo product ID |

## SCT-E10 · Bản địa hóa & tuân thủ

Dịch thuật không tính vào ngày công. Feature ở đây là phần kỹ thuật và văn bản bắt buộc.

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| SCT-E10-01 | ReceiptBook | String Catalog EN-US, EN-GB, DE, FR; bảng thuật ngữ thuế theo nước (VAT, MwSt/USt, TVA); pseudo-locale kiểm tra chuỗi dài | MVP | 1 | CORE-E10-01 | Khi chạy pseudo-locale chuỗi dài thì không chuỗi nào bị cắt ở các màn chính |
| SCT-E10-02 | ReceiptBook | Văn bản tuân thủ: disclaimer thuế (không được HMRC công nhận, không nộp cho HMRC, không tư vấn thuế, không cam kết GoBD ⚠), nhãn AI cho gợi ý, `PrivacyInfo.xcprivacy` cho app và extension, purpose string camera | MVP | 0,5 | CORE-E13-01 | Khi CI tìm trong bundle và metadata thì không có cụm "HMRC approved", "HMRC recognised", "GoBD-zertifiziert" hoặc tương đương |
| SCT-E10-03 | ReceiptBook | Review Notes và metadata theo locale: nêu quy trình dọc, đường dự phòng khi không có Foundation Models, file e-invoice mẫu cho reviewer | MVP | 0,5 | CORE-E01-03 | Khi reviewer làm theo Notes thì thử được chụp, e-invoice, paywall và xuất trên máy không có Apple Intelligence |
| SCT-E10-04 | ReceiptBook | Kiểm tra accessibility các màn riêng của app (xem lại, sổ, xuất, paywall) | MVP | 0,5 | CORE-E09-02 | Khi chỉ dùng VoiceOver thì sửa được tổng tiền và xuất được một kỳ |
| SCT-E10-05 | ReceiptBook | Bản địa hóa đợt 2: IT, ES, NL (UI và metadata) | V2 | 1,5 | SCT-E03-10 | Khi đổi ngôn ngữ máy sang IT, ES hoặc NL thì không còn chuỗi tiếng Anh ở màn chính |

## SCT-E11 · Chế độ Việt Nam

Đề xuất giữ ở `V1.1`, không đưa vào MVP, vì ba lý do:
- RPI D14 khối IN/SEA chỉ $0.08 so với $0.25 ở Tây Âu, hoàn tiền 7,7% (báo cáo). Việt Nam là chế độ bản địa hóa, không phải thị trường chính.
- Mẫu sổ và cấu trúc XML hóa đơn điện tử VN chưa có trong ghi chú nghiên cứu; phải xác minh văn bản gốc trước khi code.
- Lịch MVP đã kín.

Phần lớn engine dùng lại được: pipeline OCR (`vi-VT` qua CORE-E03-02), parser XML, kỳ báo cáo, CSV, PDF.

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| SCT-E11-01 | RBVietnam | Gói quốc gia VN: VND không có phần lẻ, loại hình hộ kinh doanh, ngưỡng doanh thu ⚠ | V1.1 | 1 | SCT-E01-01 | Khi chọn VN thì số tiền hiện dạng 1.234.000 ₫ và ô nhập không nhận phần lẻ |
| SCT-E11-02 | RBVietnam | OCR và luật tiếng Việt: định tuyến `vi-VT`; từ khóa "Tổng cộng", "Tổng tiền thanh toán", "Thuế GTGT", "Tiền thuế GTGT", "Cộng tiền hàng"; kiểm tra định dạng MST ⚠ | V1.1 | 2 | CORE-E03-02; SCT-E03-02 | Khi chạy bộ vàng VN thì tổng tiền đúng ≥ 90% và dấu tiếng Việt trong tên người bán đúng ≥ 95% ký tự |
| SCT-E11-03 | RBVietnam | 🧪 Đọc hóa đơn điện tử VN dạng XML theo Nghị định 123/2020/NĐ-CP và văn bản hướng dẫn ⚠ cấu trúc XML | V1.1 | 3 | SCT-E04-02 | Khi nhập XML mẫu thì số hóa đơn, ký hiệu, ngày, MST người bán, tổng tiền và thuế khớp 100% |
| SCT-E11-04 | RBVietnam | Sổ doanh thu, chi phí hộ kinh doanh theo mẫu sổ hiện hành ⚠ số hiệu văn bản và mẫu; xuất PDF và CSV | V1.1 | 3 | SCT-E11-01; SCT-E05-07; SCT-E06-03 | Khi xuất sổ quý thì cột và tổng đúng mẫu đã xác minh |
| SCT-E11-05 | RBVietnam | Danh mục chi phí cho hộ kinh doanh ⚠ | V1.1 | 0,5 | SCT-E05-01 | Khi hồ sơ là VN thì chỉ thấy danh mục VN |
| SCT-E11-06 | RBVietnam | Giao diện tiếng Việt, metadata VN, giá VN (49.000–499.000₫) | V1.1 | 1 | SCT-E10-01; SCT-E09-03 | Khi storefront là VN thì paywall hiện giá VND và không hiện gói trọn đời |
| SCT-E11-07 | RBVietnam | Đọc mã QR tra cứu trên hóa đơn VN ⚠ | V2 | 1 | SCT-E11-03 | Khi quét QR trên hóa đơn mẫu thì điền đúng số hóa đơn và MST |

## SCT-E12 · Chất lượng

Bộ dữ liệu vàng và `ocr-bench` là của lõi (CORE-E12-02). Epic này thêm nhãn trường chứng từ, bộ mẫu e-invoice và ngưỡng riêng của app. Thành phần bộ dữ liệu ở [technical-design.md §12](technical-design.md#12-kiểm-thử).

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| SCT-E12-01 | (tools) | Bộ dữ liệu vàng SCT: schema nhãn JSON, quy trình ẩn danh, đợt đầu 185 ảnh/PDF và 40 e-invoice | MVP | 1 | | Khi validator chạy trên bộ vàng thì mọi file có nhãn hợp lệ theo schema và đã qua bước ẩn danh |
| SCT-E12-02 | (tools) | Bench trích xuất trong CI: chạy `ReceiptRuleExtractor` (và Foundation Models trên Mac có Apple Intelligence) trên bộ vàng; fail khi tụt quá 2 điểm % | MVP | 1 | CORE-E12-02; SCT-E12-01; SCT-E03-05 | Khi một PR làm độ chính xác tổng tiền tụt hơn 2 điểm % thì CI fail và in bảng theo trường và ngôn ngữ |
| SCT-E12-03 | Tests | UI test luồng chính (onboarding → nhập ảnh mẫu → xem lại → xuất), StoreKit test (mua, trial, hết hạn, hoàn tiền, trọn đời), test 1.000 chứng từ | MVP | 1 | SCT-E06-06; SCT-E09-03 | Khi chạy trên CI thì mọi kịch bản pass, kể cả khi ép Foundation Models ở trạng thái không khả dụng |
| SCT-E12-04 | (tools) | Mở rộng bộ vàng lên khoảng 500 file, thêm VN, lấy mẫu từ beta có đồng ý | V1.1 | 1,5 | SCT-E12-01 | Khi chạy bench thì có bảng riêng cho VN và cho ảnh khó |
| SCT-E12-05 | (tools) | 🧪 So sánh Foundation Models iOS 27 (ảnh đầu vào, `OCRTool`) với pipeline hiện tại | V2 | 2 | SCT-E12-02 | Khi xong thì có bảng độ chính xác và thời gian trên cùng bộ vàng để quyết định có dùng nhánh iOS 27 |

## Tổng theo ưu tiên

| Ưu tiên | Số feature | Ngày công |
|---|---|---|
| MVP | 45 | 50 |
| V1.1 | 32 | 52,5 |
| V2 | 10 | 22,5 |
| **Tổng** | **87** | **125** |

Theo epic:

| Epic | MVP | V1.1 | V2 | Tổng |
|---|---|---|---|---|
| SCT-E01 | 3 | 3,5 | 2 | 8,5 |
| SCT-E02 | 5,5 | 1,5 | 2 | 9 |
| SCT-E03 | 10,5 | 5,5 | 2 | 18 |
| SCT-E04 | 7 | 1 | 7 | 15 |
| SCT-E05 | 5,5 | 5,5 | 0 | 11 |
| SCT-E06 | 5,5 | 6 | 5 | 16,5 |
| SCT-E07 | 4 | 9,5 | 0 | 13,5 |
| SCT-E08 | 1 | 6 | 0 | 7 |
| SCT-E09 | 2,5 | 2 | 0 | 4,5 |
| SCT-E10 | 2,5 | 0 | 1,5 | 4 |
| SCT-E11 | 0 | 10,5 | 1 | 11,5 |
| SCT-E12 | 3 | 1,5 | 2 | 6,5 |
| **Tổng** | **50** | **52,5** | **22,5** | **125** |

**Thứ tự `V1.1` đề xuất.** Sau ra mắt chỉ còn khoảng 15–20 ngày công trước khi cả hai dev chuyển sang app 03 (tháng 1–2/2027). Nên chọn theo dữ liệu, theo thứ tự:
1. Sửa lỗi và độ chính xác từ dữ liệu beta và đánh giá.
2. SCT-E06-07 (Xero, QuickBooks, FreeAgent) và SCT-E06-08 (DATEV, lexoffice, sevDesk), vì đây là đầu ra kế toán cần, sau khi xác minh định dạng.
3. SCT-E01-04 và SCT-E01-05 (nhiều hồ sơ, thẻ bất động sản), rồi thêm "nhiều doanh nghiệp" vào paywall.
4. SCT-E09-04 (offer code, win-back) trước mùa gia hạn.
5. SCT-E07-07 (sao lưu mã hóa).
6. Chế độ Việt Nam (SCT-E11) chỉ khi chỉ số EU đạt mức "đẩy mạnh" hoặc có người làm riêng.

## Lộ trình sprint

**Khối lượng cần làm trước khi nộp:** lõi MVP 42 ngày (trong đó CORE-E02-02 `DataScannerViewController` 2 ngày không cần cho SCT, dời sang khi build app 02/03) cộng 2 ngày 🧪 spike OCR của lõi, cộng SCT MVP 50 ngày. Tổng khoảng **92 ngày công**.

**1 dev hay 2 dev:**
- **1 dev: không khả thi.** 92 ngày công là khoảng 18–19 tuần. Bắt đầu 28/9 thì nộp sớm nhất khoảng tháng 2/2027, lỡ mùa thuế tháng 1–2.
- **2 dev toàn thời gian từ 28/9: vừa khít, không có biên.** Công suất gộp đến ngày đóng tính năng 27/11 khoảng 88 ngày công (S0 trừ việc thủ tục, S1–S3 đủ, S4 chỉ tuần đầu). Kế hoạch dưới đây chạy gần 100% công suất, nên phải chuẩn bị sẵn cut-line và phương án B.

| Sprint | Thời gian | Mục tiêu | CORE | SCT | Ngày (CORE + SCT) |
|---|---|---|---|---|---|
| S0 | 28/9–9/10 | Nền móng, spike, thủ tục | CORE-E01-01, E01-02, E05-01, E05-02, E05-03, E09-01, E10-01, E12-01; 🧪 spike OCR EN/DE/FR/VI (2 ngày) | SCT-E07-01, E01-01, E04-01 🧪, E12-01, E10-01 | 12 + 5,5 = 17,5 |
| S1 | 12/10–23/10 | Chụp, nhập, OCR, hồ sơ, parser UBL/CII | CORE-E02-01, E02-03, E03-01, E03-02, E03-03, E13-01 | SCT-E01-02, E01-03, E07-02, E02-01, E02-02, E02-04, E03-01, E04-02, E04-03 | 9 + 10 = 19 |
| S2 | 26/10–6/11 | Trích xuất bằng luật và LLM, ZUGFeRD, Share Extension | CORE-E04-01, E04-02, E04-03, E12-02 | SCT-E03-02, E03-03, E03-04, E04-04, E04-05, E02-03 | 10 + 10 = 20 |
| S3 | 9/11–20/11 | Xem lại, phân loại, kỳ, paywall; build TestFlight beta ngoài | CORE-E06-01, E06-02, E06-03, E07-01, E07-02 | SCT-E03-05, E03-06, E04-06, E05-01, E05-02, E05-03, E06-01, E09-01, E09-02, E02-05 | 8 + 12 = 20 |
| S4 | 23/11–4/12 | Xuất, tuân thủ, test; đóng tính năng 27/11; nộp 1/12 | CORE-E08-01, E09-02, E01-03 | SCT-E05-04, E06-02, E06-03, E06-04, E06-05, E06-06, E09-03, E08-01, E07-03, E07-04, E10-02, E10-03, E10-04, E12-02, E12-03 | 3 + 12,5 = 15,5 |
| | | **Tổng** | **42** | **50** | **92** |

Mốc:
- **S0:** song song với thủ tục của kế hoạch (Small Business Program, DSA trader status, bảng câu hỏi độ tuổi, Keyword Planner, landing page, privacy policy). Mọi mục ⚠ ảnh hưởng tới code MVP phải xác minh xong trong S0.
- **Cuối S3 (20/11):** bản beta đầu tiên lên TestFlight nhóm ngoài (người dùng UK và DE thật).
- **27/11:** đóng tính năng. Tuần 30/11–4/12 chỉ sửa lỗi, chụp ảnh màn hình, đẩy metadata.
- **1/12:** nộp App Store. **8/12:** phát hành thủ công. Còn đến 15/12 để xử lý một lần bị từ chối mà vẫn trước mùa tìm kiếm tháng 1–2.

S4 có 15,5 ngày công việc nhưng chỉ tuần đầu (khoảng 10 ngày công) dành cho tính năng. Phần dư khoảng 5,5 ngày: 4,5 ngày xử lý bằng cut-line, 1 ngày lấn vào đầu tuần ổn định.

**Cut-line** (kích hoạt nếu cuối S2 trễ hơn 3 ngày công; chuyển sang `V1.1` theo thứ tự):
1. SCT-E03-04 `ReceiptLLMExtractor` (1,5 ngày): ra mắt chỉ với luật; Foundation Models vẫn dùng cho phân loại.
2. SCT-E08-01 tìm kiếm (1 ngày): chỉ giữ bộ lọc ở màn sổ.
3. SCT-E06-05 PDF tổng hợp kỳ (1 ngày): ZIP chứa PDF từng chứng từ thay cho PDF kỳ.
4. Phần so khớp mờ của SCT-E02-05 (0,5 ngày): chỉ giữ chặn trùng theo SHA-256.
5. Phần "xóa toàn bộ dữ liệu" của SCT-E07-04 (0,5 ngày): gỡ app vẫn xóa hết dữ liệu. Giữ phần xuất toàn bộ bản gốc.

Tổng cut-line khoảng 4,5 ngày.

**Phương án B** (nếu cuối S3 vẫn trễ): nộp bản UK và EN-US ngày 1/12. Tách E-Rechnung (SCT-E04, 7 ngày) và chuỗi DE/FR sang bản 1.0.1 khoảng 15/12. Anh là thị trường nhạy lịch nhất vì hạn nộp tờ khai năm cuối tháng 1 (⚠ cần xác minh ngày chính xác). Đây cũng là phương án đã nêu trong rủi ro của lõi.
