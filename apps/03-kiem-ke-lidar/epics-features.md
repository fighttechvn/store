# Epic và feature · `RoomLedger` (KKL)

Quy ước ID, ưu tiên, ước tính và dấu ⚠ / 🧪 theo [README chung](../README.md). Ước tính là ngày công của 1 dev iOS có kinh nghiệm, đã gồm unit test; **không gồm** thiết kế UI, dịch thuật, rà soát pháp lý nội dung mẫu biên bản và metadata ASO.

Feature của lõi (`CORE-…`) chỉ được tham chiếu trong cột "Phụ thuộc", không làm lại ở đây. Tên module là Swift target trong `Apps/RoomLedger` (xem [technical-design.md mục 2](technical-design.md#2-module-map)). `(app)` là target app, `(tests)` là test target, `(qa)` là việc kiểm thử thủ công có quy trình.

Thiết bị: mọi feature có LiDAR phải kiểm `CoreDevice.Capabilities` trước và có đường dự phòng (KKL-E02-01, KKL-E03).

## Tổng quan epic

| ID | Epic | Mục tiêu | Module | MVP (ngày) | Tổng (ngày) |
|---|---|---|---|---|---|
| KKL-E01 | Bất động sản & dự án | Cấu trúc nhà → phòng → đợt kiểm tra (move-in, move-out, inventory), các bên, địa chỉ; dự án mẫu | LedgerModel, LedgerProperty, (app) | 5 | 9 |
| KKL-E02 | Quét phòng LiDAR | Quét từng phòng bằng RoomPlan, ra kích thước tường/cửa/cửa sổ, diện tích sàn, USDZ; về sau ghép nhiều phòng | LedgerScan, LedgerGeometry | 8 | 15,5 |
| KKL-E03 | Chế độ không LiDAR | Máy không LiDAR vẫn ra đủ biên bản: ảnh phòng, đo AR, nhập kích thước tay, nói rõ độ chính xác | LedgerMeasure | 5 | 10 |
| KKL-E04 | Kiểm kê đồ đạc | Item có ảnh, serial/model bằng OCR, giá trị, hóa đơn, tình trạng, vị trí | LedgerInventory | 2,5 | 11,5 |
| KKL-E05 | Tình trạng & biên bản | Checklist theo phòng, ảnh lỗi có chú thích, đồng hồ, chìa khóa, chữ ký, dấu thời gian, manifest SHA-256, so sánh move-in/move-out | LedgerCondition, LedgerReport | 5,5 | 15,5 |
| KKL-E06 | Báo cáo & xuất | Mẫu PDF theo nước, mặt bằng 2D vector, báo cáo kiểm kê, USDZ, CSV, ZIP | LedgerReport | 8 | 15 |
| KKL-E07 | Module Pro tiền khảo sát cải tạo | V2: bảng cửa sổ/cửa, OCR tem radiator, diện tích sàn, gói PDF/CSV, IFC nếu spike đạt | LedgerSurvey, LedgerPaywall | 0 | 14 |
| KKL-E08 | Lưu trữ & hiệu năng tài sản | Ảnh, USDZ, JSON lớn trên máy: bố cục file, thumbnail, dung lượng, lưu trữ xuất/nhập | LedgerAssets | 1,5 | 8,5 |
| KKL-E09 | Paywall & gói | Quyền lợi theo số nhà, mẫu thương hiệu; thiết kế StoreKit tuân thủ cho "mua theo nhà" | LedgerPaywall | 3,5 | 5 |
| KKL-E10 | Bản địa hóa & tuân thủ | EN-GB, DE, FR, NL; đơn vị mét; disclaimer; quyền riêng tư; Review Notes | (app), LedgerCondition, LedgerReport | 2 | 5,5 |
| KKL-E11 | Chất lượng đo đạc | Fixture, benchmark với máy đo laser, ma trận thiết bị và nhiệt, UI test | (tests), (qa), Tools/room-bench, (app) | 4 | 5,5 |
| | **Tổng** | | | **45** | **115** |

## KKL-E01 · Bất động sản & dự án

Mục tiêu: người dùng tổ chức dữ liệu theo nhà, phòng và từng lần kiểm tra. Một đợt kiểm tra đã ký thì bất biến.

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| KKL-E01-01 | LedgerModel | Schema SwiftData v1 (`Property`, `Room`, `Inspection`, `Party`, `RoomScan`, `SurfaceDimension`, `Item`, `ConditionEntry`, `Defect`, `MeterReading`, `KeySet`, `Signature`, `ReportExport`) theo `VersionedSchema`; độ dài bằng mét (`Double`), tiền bằng `Decimal` | MVP | 1,5 | CORE-E05-01 | Khi test tạo đủ 13 loại bản ghi rồi mở lại container thì không mất quan hệ; khi xóa một `Property` thì mọi bản ghi con bị xóa theo |
| KKL-E01-02 | LedgerProperty | Tạo và sửa bất động sản: tên, địa chỉ theo định dạng từng nước, loại nhà, ảnh bìa, nước của mẫu biên bản | MVP | 1 | KKL-E01-01; CORE-E09-01 | Khi tạo nhà với nước DE thì mẫu biên bản mặc định là DE và địa chỉ in theo thứ tự "Straße Nr., PLZ Ort" |
| KKL-E01-03 | LedgerProperty | Danh sách phòng: thêm, đổi tên, sắp xếp, loại phòng có sẵn (bếp, phòng tắm, phòng ngủ…), tầng | MVP | 0,5 | KKL-E01-01 | Khi kéo đổi thứ tự phòng thì PDF in các phòng theo thứ tự mới |
| KKL-E01-04 | LedgerProperty | Đợt kiểm tra: loại move-in / move-out / inventory / interim, ngày giờ, các bên (người thuê, chủ nhà, đại lý, nhân chứng), trạng thái nháp → đã ký → bản sửa đổi | MVP | 1 | KKL-E01-01; CORE-E05-03 | Khi đợt kiểm tra đã ký thì mọi trường chỉ đọc; khi sửa thì app tạo bản sửa đổi và ghi audit |
| KKL-E01-05 | (app) | Onboarding: vai trò (người thuê, chủ nhà, bảo hiểm, chuyển nhà), nước, thông báo năng lực máy (LiDAR hay chế độ ảnh + đo AR) | MVP | 0,5 | KKL-E02-01 | Khi mở lần đầu trên iPhone 17 thì onboarding giới thiệu chế độ ảnh + đo AR và không hiện nút quét LiDAR |
| KKL-E01-06 | LedgerProperty | Dự án mẫu dựng từ fixture (scan, ảnh, biên bản đã điền) để người mới và App Review xem ngay | MVP | 0,5 | KKL-E11-01; KKL-E06-02 | Khi mở dự án mẫu trên máy không LiDAR thì thấy mặt bằng, m² và xuất được PDF, USDZ; dự án mẫu không tính vào hạn mức 1 nhà miễn phí |
| KKL-E01-07 | LedgerProperty | Tạo move-out từ move-in: chép phòng, item, danh sách phần tử; không chép tình trạng, ảnh lỗi, chữ ký | V1.1 | 1 | KKL-E01-04 | Khi tạo move-out từ move-in thì mỗi phòng, phần tử và item có `sourceID` trỏ về bản move-in |
| KKL-E01-08 | LedgerProperty | Lịch sử thuê theo nhà: nhiều lượt thuê, người thuê theo thời gian (công cụ chủ nhà) | V1.1 | 1,5 | KKL-E01-04; KKL-E09-01 | Khi mở một nhà có 3 lượt thuê thì thấy dòng thời gian theo ngày bắt đầu, mỗi lượt có move-in và move-out |
| KKL-E01-09 | LedgerProperty | Spotlight và App Shortcuts: tìm nhà và item; lệnh "Bắt đầu kiểm tra" | V1.1 | 1 | CORE-E11-01 | Khi gõ tên một item trong Spotlight thì mở đúng item trong app |
| KKL-E01-10 | LedgerProperty | Chọn các bên từ Danh bạ bằng `CNContactPickerViewController` (không xin quyền Contacts) | V1.1 | 0,5 | KKL-E01-04 | Khi chọn một liên hệ thì chỉ tên và email được chép vào; app không hiện hộp xin quyền Contacts |

## KKL-E02 · Quét phòng LiDAR

Mục tiêu: một phòng quét xong trong vài phút, ra kích thước và m² dùng được cho biên bản. `RoomGeometrySnapshot` (định dạng riêng) là nguồn sự thật cho báo cáo; JSON của `CapturedRoom` chỉ là bản lưu gốc.

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| KKL-E02-01 | LedgerScan | Cổng năng lực: đọc `CoreDevice.Capabilities` (`RoomCaptureSession.isSupported`, `supportsSceneReconstruction(.mesh)`), chọn đường LiDAR hay dự phòng | MVP | 0,5 | CORE-E01-01 | Khi chạy trên máy không LiDAR hoặc Simulator thì app không khởi tạo `RoomCaptureSession`, không crash và mở chế độ dự phòng |
| KKL-E02-02 | LedgerScan | Bọc `RoomCaptureView` cho SwiftUI: bật coaching, nút Xong/Hủy, giữ màn hình sáng, khóa hướng dọc | MVP | 1,5 | KKL-E02-01 | Khi quét xong một phòng 4 tường và bấm Xong thì nhận được `CapturedRoomData` và phiên dừng |
| KKL-E02-03 | LedgerScan | Vòng đời phiên: app xuống nền, cuộc gọi, lỗi kết thúc phiên (vượt kích thước cảnh, mất tracking ⚠ tên lỗi), `thermalState`, cảnh báo bộ nhớ; bộ đếm phiên bắt đầu/hoàn tất lưu trên máy | MVP | 1 | KKL-E02-02 | Khi app xuống nền giữa phiên thì quay lại thấy màn "Phiên bị gián đoạn" có nút quét lại; khi `thermalState` là `.critical` thì phiên dừng và dữ liệu đã có được giữ |
| KKL-E02-04 | LedgerScan | Hậu xử lý `RoomBuilder` → `CapturedRoom`; lưu `CapturedRoomData` trước khi xử lý, JSON của `CapturedRoom` (Codable ⚠) và USDZ vào kho tài sản | MVP | 1 | KKL-E02-02; KKL-E08-01 | Khi builder xong thì có file JSON và USDZ; JSON đọc lại thành `CapturedRoom` có cùng số tường, cửa, cửa sổ |
| KKL-E02-05 | LedgerGeometry | Chuẩn hóa sang `RoomGeometrySnapshot` (Codable, không import RoomPlan): tường là đoạn thẳng trên mặt XZ, cửa/cửa sổ/lỗ mở gắn tường cha, kích thước bằng mét, đồ vật có danh mục | MVP | 1,5 | KKL-E02-04 | Khi chạy test trên 12 fixture thì mọi cửa và cửa sổ có tường cha và vị trí dọc tường nằm trong [0, chiều dài tường] |
| KKL-E02-06 | LedgerGeometry | Diện tích sàn từ đa giác `floors` (`polygonCorners`, iOS 17 ⚠) bằng công thức shoelace; dự phòng bằng vòng tường; chu vi, chiều cao trần; ghi nguồn tính | MVP | 1 | KKL-E02-05; KKL-E02-08 | Khi fixture phòng chữ nhật 4,00 × 3,00 m thì diện tích là 12,00 m² ± 0,01; khi không có `floors` thì dùng vòng tường và ghi nguồn `wallLoop` |
| KKL-E02-07 | LedgerScan | Màn xem lại sau quét: mặt bằng 2D, danh sách tường/cửa/cửa sổ và kích thước, xóa bề mặt nhận sai, xem 3D bằng AR Quick Look, xóa scan để quét lại | MVP | 1 | KKL-E02-05; KKL-E06-01 | Khi xóa một cửa sổ nhận nhầm thì mặt bằng và PDF không còn cửa sổ đó, diện tích sàn không đổi |
| KKL-E02-08 | LedgerScan | 🧪 Spike 0,5 ngày: kiểm tra `floors` và `polygonCorners` trên iOS 26 máy thật; so diện tích hai cách tính trên 5 phòng với máy đo laser; chọn cách lấy kết quả quét (đường A hay B, thiết kế kỹ thuật mục 4.1) | MVP | 0,5 | KKL-E02-04 | Khi xong spike thì có bảng 5 phòng (đa giác sàn, vòng tường, đo laser), quyết định cách tính diện tích mặc định và cách lấy kết quả quét |
| KKL-E02-09 | LedgerScan | Sửa kích thước của bề mặt đã quét, giữ giá trị gốc, ghi nguồn `.manual` | V1.1 | 1 | KKL-E02-07; CORE-E05-03 | Khi sửa chiều rộng một cửa thì audit log có giá trị cũ, giá trị mới và nguồn; PDF ghi "đã chỉnh tay" |
| KKL-E02-10 | LedgerScan | Quét lại một phòng và giữ bản cũ làm phiên bản | V1.1 | 0,5 | KKL-E02-04 | Khi quét lại phòng đã có biên bản ký thì biên bản đó vẫn trỏ tới bản quét cũ |
| KKL-E02-11 | LedgerScan | 🧪 Spike 2 ngày: quét nhiều phòng liên tiếp giữ chung `ARSession` rồi ghép bằng `StructureBuilder` (iOS 17 ⚠); đo độ lệch mối nối | V1.1 | 2 | KKL-E02-04 | Khi xong spike thì có số đo độ lệch mối nối trên 3 căn hộ và quyết định làm hay bỏ KKL-E02-12 |
| KKL-E02-12 | LedgerScan | Ghép nhiều phòng thành `CapturedStructure`, mặt bằng toàn căn, tổng diện tích | V1.1 | 3 | KKL-E02-11 | Khi quét liên tiếp 3 phòng thì mặt bằng toàn căn không có mối nối lệch quá ngưỡng chốt sau spike |
| KKL-E02-13 | LedgerScan | Mẹo trước khi quét (bật đèn, mở cửa, dọn lối đi) và mẹo theo lỗi của lần trước | V1.1 | 0,5 | KKL-E02-03 | Khi phiên trước kết thúc vì thiếu sáng thì lần sau màn chuẩn bị hiện mẹo bật đèn |
| KKL-E02-14 | LedgerScan | Gợi ý loại phòng từ `sections` của `CapturedRoom` (iOS 17 ⚠) | V1.1 | 0,5 | KKL-E02-05 | Khi quét phòng tắm có bồn cầu và bồn tắm thì loại phòng được gợi ý là phòng tắm; người dùng đổi được |

## KKL-E03 · Chế độ không LiDAR

Mục tiêu: 65–75% máy không có LiDAR (ước tính) vẫn làm được biên bản đầy đủ. App nói thật về độ chính xác, dung sai lấy từ benchmark (KKL-E11-02).

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| KKL-E03-01 | LedgerMeasure | Camera chụp ảnh (AVFoundation) dùng chung cho phòng, item, lỗi; triển khai `CaptureSource` của CoreCapture; ghi thời điểm chụp; bỏ GPS khỏi metadata | MVP | 1 | CORE-E05-02 | Khi chụp một ảnh thì file lưu có `capturedAt` và metadata không chứa vị trí GPS |
| KKL-E03-02 | LedgerMeasure | Hồ sơ phòng bằng ảnh: danh sách góc chụp gợi ý (4 góc, sàn, trần, cửa sổ, cửa), đánh dấu đủ | MVP | 0,5 | KKL-E03-01 | Khi chụp đủ các góc gợi ý thì phòng có trạng thái "Đã ghi hình" |
| KKL-E03-03 | LedgerMeasure | Đo khoảng cách bằng AR: `ARWorldTrackingConfiguration` phát hiện mặt phẳng ngang/dọc, raycast từ tâm màn hình, chốt 2 điểm, gán kết quả cho tường, cửa, cửa sổ hoặc chiều cao trần | MVP | 2 | KKL-E02-01 | Khi tracking ở trạng thái `limited` thì nút chốt điểm bị khóa và hiện lý do; khi đo mẫu chuẩn 1,000 m trên iPhone 17 thì sai số nằm trong ngưỡng công bố ở KKL-E11-02 |
| KKL-E03-04 | LedgerMeasure | Nhập kích thước tay: phòng chữ nhật (dài × rộng × cao) hoặc đa giác vuông góc (danh sách cạnh), tính diện tích và chu vi | MVP | 1 | KKL-E01-03; KKL-E02-06 | Khi nhập phòng chữ L gồm 6 cạnh vuông góc thì diện tích khớp tính tay; khi nhập giá trị ≤ 0 hoặc đa giác không khép thì bị từ chối kèm lý do |
| KKL-E03-05 | LedgerMeasure | Nhãn nguồn số đo (LiDAR, AR, tay) và câu giải thích độ chính xác trên UI và PDF | MVP | 0,5 | KKL-E03-03; KKL-E06-02 | Khi một phòng có số đo AR thì PDF ghi nguồn "Đo bằng AR" kèm dung sai lấy từ kết quả benchmark |
| KKL-E03-06 | LedgerMeasure | Phác mặt bằng từ kích thước tay (chữ nhật, chữ L) để dùng chung renderer 2D | V1.1 | 1,5 | KKL-E03-04; KKL-E06-01 | Khi nhập phòng chữ nhật thì PDF có mặt bằng với nhãn kích thước giống phòng quét LiDAR |
| KKL-E03-07 | LedgerMeasure | Đo đa giác sàn bằng AR: đặt lần lượt các góc sàn, khép đa giác, tính diện tích | V1.1 | 2 | KKL-E03-03 | Khi đo một phòng chữ nhật 12 m² thì diện tích lệch không quá ngưỡng AR đã công bố |
| KKL-E03-08 | LedgerMeasure | Trên máy LiDAR: raycast lên mesh `sceneReconstruction` khi không dùng được RoomPlan (phòng quá lớn, hành lang dài) | V2 | 1,5 | KKL-E03-03 | Khi phòng vượt giới hạn của RoomPlan thì vẫn đo được khoảng cách trên mesh với nhãn nguồn "LiDAR mesh" |

## KKL-E04 · Kiểm kê đồ đạc

Mục tiêu: danh sách đồ đạc đủ để nộp bảo hiểm hoặc đối chiếu khi chuyển nhà. OCR chỉ gợi ý; người dùng luôn xác nhận.

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| KKL-E04-01 | LedgerInventory | Tạo item: nhiều ảnh, tên, danh mục, phòng, số lượng, tình trạng 5 mức, ghi chú | MVP | 1 | KKL-E03-01; KKL-E01-03 | Khi thêm item có 3 ảnh thì item hiện trong phòng với ảnh đầu làm thumbnail và có trong báo cáo kiểm kê |
| KKL-E04-02 | LedgerInventory | OCR serial/model trên ảnh tem nhãn: `LineRecognizer` + luật nhãn đa ngôn ngữ (S/N, Serial, Seriennummer, N° de série, Model, Modell, Type…), xử lý nhầm O/0 và I/1, người dùng chọn ứng viên | MVP | 1 | CORE-E03-02; CORE-E04-01 | Khi chạy bộ 30 ảnh tem nhãn thì serial đúng nằm trong 3 ứng viên đầu ở ≥ 85% ảnh (mục tiêu nội bộ) |
| KKL-E04-03 | LedgerInventory | Giá trị, tiền tệ, ngày mua; đính kèm ảnh hoặc PDF hóa đơn (quét tài liệu, nhập file) | MVP | 0,5 | CORE-E02-01; CORE-E02-03; CORE-E10-01 | Khi nhập 1.299,00 € ở storefront DE thì PDF và CSV hiện đúng định dạng DE; hóa đơn đính kèm mở được từ item |
| KKL-E04-04 | LedgerInventory | Gợi ý item từ `CapturedRoom.objects` (giường, sofa, bàn, tủ lạnh, máy giặt…) thành item nháp có danh mục và vị trí | V1.1 | 1 | KKL-E02-05; KKL-E04-01 | Khi phòng quét có 1 giường và 1 tủ thì màn gợi ý có 2 item nháp; người dùng bỏ qua được từng item |
| KKL-E04-05 | LedgerInventory | Ghim item lên mặt bằng 2D (tọa độ trên mặt XZ) | V1.1 | 1,5 | KKL-E04-01; KKL-E06-01 | Khi ghim một item thì mặt bằng trong PDF có số thứ tự item ở đúng vị trí |
| KKL-E04-06 | LedgerInventory | Đọc hóa đơn đính kèm (ngày, tổng tiền, cửa hàng) bằng `DocumentRecognizer` + `MergedExtractor`, điền sẵn giá trị | V1.1 | 1 | CORE-E03-01; CORE-E04-03; KKL-E04-03 | Khi đính kèm hóa đơn mẫu thì ngày và tổng tiền được điền sẵn; trường độ tin cậy thấp bị đánh dấu "cần xem lại" |
| KKL-E04-07 | LedgerInventory | Quét mã vạch EAN/UPC hoặc Code 128 trên hộp hoặc tem, lưu làm mã sản phẩm hoặc serial (không tra cứu online) | V1.1 | 0,5 | CORE-E02-02 | Khi quét mã Code 128 trên tem serial thì giá trị được điền vào ô serial |
| KKL-E04-08 | LedgerInventory | Tổng giá trị theo phòng và danh mục; nhắc item thiếu ảnh, serial hoặc giá trị | V1.1 | 0,5 | KKL-E04-03 | Khi 2 item chưa có giá trị thì màn tổng hiện nhắc "2 item thiếu giá trị" |
| KKL-E04-09 | LedgerInventory | Nhận hóa đơn từ app `ReceiptBook` (SCT) qua App Group chung của cùng team ⚠ | V2 | 3 | KKL-E04-03 | Khi người dùng có cả hai app và chọn "Lấy từ Sổ chứng từ" thì thấy danh sách hóa đơn và gắn được vào item |
| KKL-E04-10 | LedgerInventory | Gợi ý tên và danh mục item bằng Foundation Models khi máy hỗ trợ; gắn nhãn AI | V2 | 1,5 | CORE-E04-02; CORE-E13-01 | Khi Foundation Models không khả dụng thì không hiện gợi ý và không có lỗi; khi có gợi ý thì hiện nhãn "AI-generated" |

## KKL-E05 · Tình trạng & biên bản

Mục tiêu: biên bản đủ các mục người thuê và chủ nhà thường cần, ký trên máy, có bằng chứng toàn vẹn. Không kết luận ai chịu trách nhiệm hư hỏng.

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| KKL-E05-01 | LedgerCondition | Checklist theo phòng: phần tử có sẵn theo loại phòng (tường, sàn, trần, cửa, cửa sổ, ổ điện, đèn, thiết bị); mỗi phần tử có tình trạng, độ sạch, ghi chú, "không áp dụng"; mục chìa khóa và đồ bàn giao (loại, số lượng, ảnh) | MVP | 1,5 | KKL-E01-04 | Khi tạo phòng loại "phòng tắm" thì checklist có sẵn phần tử vệ sinh; khi phần tử bị đánh dấu "không áp dụng" thì phần tử đó không được in |
| KKL-E05-02 | LedgerCondition | Ảnh lỗi gắn với phần tử; chú thích bằng PencilKit (`PKCanvasView` phủ trên ảnh); lớp vẽ lưu riêng, ảnh gốc giữ nguyên; ảnh nhập từ thư viện được đánh dấu | MVP | 1,5 | KKL-E03-01 | Khi khoanh vết nứt thì PDF in ảnh đã chú thích, còn ZIP có ảnh gốc với hash khớp manifest |
| KKL-E05-03 | LedgerCondition | Chỉ số đồng hồ điện, gas, nước, nhiệt: ảnh + nhập số, số đồng hồ, đơn vị | MVP | 0,5 | KKL-E03-01 | Khi một đồng hồ đã khai chưa có chỉ số thì màn ký hiện cảnh báo trước khi ký |
| KKL-E05-04 | LedgerCondition | Chữ ký các bên bằng PencilKit, tên in, vai trò, thời điểm và múi giờ; ký đủ thì khóa; sửa sau khi ký tạo bản sửa đổi | MVP | 1 | KKL-E01-04; CORE-E05-03 | Khi cả hai bên đã ký thì nút sửa đổi thành "Tạo bản sửa đổi" và bản cũ giữ nguyên hash |
| KKL-E05-05 | LedgerCondition | Dấu thời gian và manifest SHA-256: chốt dữ liệu thành `snapshot.json`, hash từng ảnh gốc, USDZ, JSON; hash gốc in ở trang cuối PDF và trong `manifest.json` | MVP | 1 | CORE-E06-03; KKL-E05-04 | Khi sửa 1 byte trong một ảnh của gói ZIP thì bước kiểm tra lại báo đúng file bị lệch |
| KKL-E05-06 | LedgerCondition | OCR chữ số đồng hồ (`LineRecognizer`, tắt sửa lỗi ngôn ngữ, lọc chữ số, vùng chọn) để điền sẵn chỉ số | V1.1 | 1 | CORE-E03-02; KKL-E05-03 | Khi chạy 20 ảnh đồng hồ số thì ≥ 80% ảnh đọc đúng toàn bộ chữ số (mục tiêu nội bộ); người dùng luôn xác nhận |
| KKL-E05-07 | LedgerCondition | Màn "Kiểm tra gói": mở ZIP, tính lại hash, so với manifest | V1.1 | 0,5 | KKL-E05-05 | Khi mở gói không bị sửa thì hiện "Khớp"; khi gói bị sửa thì liệt kê file lệch |
| KKL-E05-08 | LedgerCondition | So sánh move-in và move-out: ghép phòng, phần tử, item theo `sourceID`, dự phòng theo danh mục + tên; đánh dấu tình trạng xấu đi, lỗi mới, item thiếu | V1.1 | 2,5 | KKL-E01-07 | Khi move-out có một phần tử tụt 2 mức và một item bị xóa thì màn so sánh hiện đúng 2 thay đổi đó |
| KKL-E05-09 | LedgerReport | PDF so sánh trước/sau: ảnh move-in và move-out cạnh nhau theo phần tử | V1.1 | 1,5 | KKL-E05-08; KKL-E06-02 | Khi xuất PDF so sánh thì mỗi thay đổi có ảnh của hai thời điểm và ngày chụp |
| KKL-E05-10 | LedgerCondition | Ghi chú giọng nói on-device cho lỗi (`SpeechAnalyzer`/`SpeechTranscriber`, iOS 26 ⚠) | V2 | 1,5 | KKL-E05-02 | Khi đọc ghi chú bằng tiếng Đức ở chế độ máy bay thì văn bản vẫn xuất hiện |
| KKL-E05-11 | LedgerCondition | Ký trên thiết bị thứ hai: gửi gói `.roomledger` qua AirDrop, bên kia xem và ký, gửi lại; kiểm hash hai chiều | V2 | 3 | KKL-E08-04 | Khi bên thứ hai ký trên máy của họ thì gói trả về có chữ ký mới và hash dữ liệu trùng bản gốc |

## KKL-E06 · Báo cáo & xuất

Mục tiêu: đầu ra là thứ người dùng mang đi được. **Xuất luôn miễn phí.** Nội dung mẫu theo nước phải được người có chuyên môn ở nước đó duyệt trước ra mắt ⚠.

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| KKL-E06-01 | LedgerReport | Renderer mặt bằng 2D vector: tường, cửa (khe + cung mở), cửa sổ (nét đôi), lỗ mở, nhãn kích thước, m² ở giữa phòng, thước tỷ lệ; xoay theo tường dài nhất | MVP | 2,5 | KKL-E02-05 | Khi render 12 fixture thì không có nhãn kích thước nào đè lên nhau ở phòng ≤ 8 tường; mặt bằng trong PDF là vector (phóng to không vỡ) |
| KKL-E06-02 | LedgerReport | Khung mẫu biên bản: bìa, các bên, mặt bằng, từng phòng (checklist, ảnh lỗi, item), đồng hồ, chìa khóa, chữ ký, trang manifest; nén ảnh cho PDF | MVP | 2 | CORE-E06-01; KKL-E05-05 | Khi xuất biên bản 5 phòng, 60 ảnh thì PDF A4 có đủ các mục và dung lượng ≤ 25 MB (mục tiêu) |
| KKL-E06-03 | LedgerReport | Biến thể theo nước: UK check-in/inventory report, DE Wohnungsübergabeprotokoll, FR état des lieux (mục bắt buộc ⚠ cần xác minh), NL; thuật ngữ, thứ tự mục | MVP | 1 | KKL-E06-02 | Khi đổi nước của nhà từ UK sang FR thì PDF dùng tiêu đề, thuật ngữ và thứ tự mục của mẫu FR; test trích chữ PDF tìm thấy mọi mục bắt buộc trong danh sách đã duyệt |
| KKL-E06-04 | LedgerReport | Báo cáo kiểm kê (bảo hiểm, chuyển nhà): item theo phòng, ảnh, serial/model, giá trị, ngày mua, tổng | MVP | 1 | KKL-E06-02; KKL-E04-03 | Khi nhà có 40 item ở 5 phòng thì báo cáo có tổng giá trị theo phòng và tổng chung khớp dữ liệu |
| KKL-E06-05 | LedgerReport | Xuất và chia sẻ USDZ từng phòng; xem bằng AR Quick Look (`QLPreviewController`) | MVP | 0,5 | KKL-E02-04 | Khi người dùng miễn phí bấm xuất USDZ thì file được chia sẻ và không hiện paywall |
| KKL-E06-06 | LedgerReport | Gói ZIP: PDF, ảnh gốc, USDZ, JSON dữ liệu, `manifest.json` | MVP | 0,5 | CORE-E06-03; KKL-E05-05 | Khi giải nén trên macOS và chạy `shasum -a 256` thì mọi hash khớp manifest |
| KKL-E06-07 | LedgerReport | Xuất CSV kiểm kê theo locale | MVP | 0,5 | CORE-E06-02; KKL-E04-03 | Khi mở CSV bằng Excel FR thì cột giá trị là số và dấu thập phân đúng |
| KKL-E06-08 | LedgerReport | Bố cục nhãn kích thước nâng cao: đặt ngoài tường, đường dẫn cho tường ngắn, bảng kích thước khi quá chật | V1.1 | 1 | KKL-E06-01 | Khi phòng có 14 tường, có tường < 30 cm thì không nhãn nào đè nhau; tường quá ngắn có trong bảng kích thước |
| KKL-E06-09 | LedgerReport | Mẫu PDF có thương hiệu: logo, màu, thông tin đại lý, chân trang | V1.1 | 1,5 | KKL-E06-02; KKL-E09-01 | Khi chưa có gói trả phí mà chọn mẫu thương hiệu thì hiện paywall; khi có thì PDF có logo ở mọi trang |
| KKL-E06-10 | LedgerReport | Mặt bằng toàn căn từ `CapturedStructure` | V1.1 | 1 | KKL-E02-12; KKL-E06-01 | Khi nhà có structure 3 phòng thì PDF có một trang mặt bằng toàn căn với tên và m² từng phòng |
| KKL-E06-11 | LedgerReport | PDF có mật khẩu (tùy chọn khi xuất) | V1.1 | 0,5 | KKL-E06-02 | Khi đặt mật khẩu thì Preview trên macOS yêu cầu mật khẩu để mở |
| KKL-E06-12 | LedgerReport | Xuất mặt bằng SVG và DXF | V2 | 2 | KKL-E06-01 | Khi mở DXF trong một viewer CAD thì kích thước tường khớp số mét trong app |
| KKL-E06-13 | LedgerReport | Xuất OBJ và USDZ toàn căn qua ModelIO ⚠ | V2 | 1 | KKL-E02-12 | Khi xuất OBJ thì file mở được trong Blender với đơn vị mét |

## KKL-E07 · Module Pro tiền khảo sát cải tạo (V2)

Mục tiêu: gộp đề xuất #6 của báo cáo thành module Pro. **Cầu từ phía chủ nhà chưa được kiểm chứng**; chỉ bắt đầu sau khi app đạt tiêu chí "đẩy mạnh". Không tuyên bố tuân thủ DIN EN 12831 hay MCS; không tự áp quy tắc diện tích ở của từng nước.

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| KKL-E07-01 | LedgerSurvey | Bảng cửa sổ và cửa theo phòng: rộng, cao, cao bệ cửa từ RoomPlan; loại kính, khung nhập tay | V2 | 2 | KKL-E02-05 | Khi nhà có 9 cửa sổ quét được thì bảng có 9 dòng với kích thước và phòng |
| KKL-E07-02 | LedgerSurvey | OCR tem radiator, nồi hơi: hãng, model, công suất (W), kích thước; lưu ảnh tem | V2 | 1,5 | CORE-E03-02; CORE-E04-01 | Khi chạy 20 ảnh tem mẫu thì trường công suất đúng ở ≥ 80% ảnh (mục tiêu nội bộ); người dùng luôn xác nhận |
| KKL-E07-03 | LedgerSurvey | Diện tích sàn đo được theo phòng và tổng; không tự áp quy tắc diện tích ở của từng nước (như WoFlV ở Đức ⚠) | V2 | 1,5 | KKL-E02-06 | Khi xuất gói thì bảng diện tích ghi rõ "diện tích sàn đo được", không dùng thuật ngữ Wohnfläche theo WoFlV |
| KKL-E07-04 | LedgerSurvey | Gói tiền khảo sát PDF/CSV cho thợ và tư vấn năng lượng, kèm disclaimer không phải tính tải nhiệt theo DIN EN 12831 hay khảo sát MCS | V2 | 1,5 | KKL-E06-02; CORE-E06-02 | Khi xuất gói thì trang đầu có disclaimer; khi rà app và metadata thì không có câu "tuân thủ DIN EN 12831" hay "MCS" |
| KKL-E07-05 | LedgerSurvey | 🧪 Spike 3 ngày: xuất IFC tối thiểu (tường, cửa, cửa sổ, không gian; phiên bản schema ⚠) và mở thử trong 2 viewer IFC | V2 | 3 | KKL-E02-05 | Khi xong spike thì 3 fixture mở được trong 2 viewer và có quyết định làm tiếp hay bỏ |
| KKL-E07-06 | LedgerSurvey | Xuất IFC cơ bản | V2 | 4 | KKL-E07-05 | Khi mở file IFC trong viewer thì số tường, cửa, cửa sổ khớp app và kích thước lệch ≤ 1 mm so với dữ liệu app |
| KKL-E07-07 | LedgerPaywall | Sản phẩm IAP cho module (gộp vào gói năm hay mua riêng theo nhà ⚠) | V2 | 0,5 | KKL-E09-01 | Khi mua module thì quyền lợi `preSurvey` bật ngay và còn sau khi khôi phục mua |

## KKL-E08 · Lưu trữ & hiệu năng tài sản

Mục tiêu: một căn nhà có thể có vài trăm ảnh và vài USDZ. App vẫn nhanh, không để file mồ côi, người dùng thấy dung lượng.

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| KKL-E08-01 | LedgerAssets | Bố cục thư mục theo nhà và đợt kiểm tra trên `BlobStore` (ảnh gốc, bản xem trước, USDZ, JSON); xóa nhà xóa sạch file; bật khóa Face ID tùy chọn | MVP | 1 | CORE-E05-02; CORE-E08-01 | Khi xóa một nhà thì dung lượng app giảm tương ứng và test đếm file không thấy file mồ côi |
| KKL-E08-02 | LedgerAssets | Thumbnail bằng ImageIO downsampling, cache bộ nhớ có giới hạn | MVP | 0,5 | KKL-E08-01 | Khi cuộn danh sách 300 ảnh trên iPhone 12 Pro thì bộ nhớ không vượt ngân sách ở mục 11 của thiết kế kỹ thuật |
| KKL-E08-03 | LedgerAssets | Màn dung lượng: theo nhà, theo loại file; cảnh báo khi máy còn ít chỗ trống | V1.1 | 1 | KKL-E08-01 | Khi máy còn < 1 GB trống thì app cảnh báo trước khi quét |
| KKL-E08-04 | LedgerAssets | Xuất và nhập lưu trữ `.roomledger` (ZIP gồm dữ liệu, tài sản, manifest) để sao lưu hoặc chuyển máy | V1.1 | 2 | CORE-E06-03; KKL-E05-05 | Khi xuất một nhà rồi nhập vào máy khác thì mọi phòng, item, biên bản và hash giống bản gốc |
| KKL-E08-05 | LedgerAssets | Đồng bộ iCloud (CloudKit), chờ quyết định ở lõi và kiểm tra lại nhãn quyền riêng tư ⚠ | V2 | 4 | CORE-E05-01 | Khi bật đồng bộ trên hai máy thì một item sửa ở máy A xuất hiện ở máy B |

## KKL-E09 · Paywall & gói

Mục tiêu: thu tiền cho quy trình nhiều nhà và thương hiệu, không bao giờ cho việc xuất. Thiết kế StoreKit cho "mua theo nhà" ở [technical-design.md mục 10](technical-design.md#10-storekit).

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| KKL-E09-01 | LedgerPaywall | Danh mục sản phẩm và ánh xạ quyền lợi: `kkl.pro.yearly`, `kkl.property.slot.01`…`.10` → `propertyLimit`, `brandedTemplates`, `landlordTools` | MVP | 1 | CORE-E07-01 | Khi mua `kkl.pro.yearly` thì `propertyLimit` thành không giới hạn ngay, kể cả sau khi khởi động lại app |
| KKL-E09-02 | LedgerPaywall | Slot bất động sản: gán slot đã mua cho một nhà; khôi phục số slot sau cài lại; nhà vượt hạn mức chuyển chỉ đọc nhưng vẫn xem và xuất được | MVP | 1 | KKL-E09-01; KKL-E01-02 | Khi gói năm hết hạn và người dùng có 3 nhà, 1 slot thì 2 nhà giữ quyền sửa, nhà còn lại chỉ đọc nhưng vẫn xuất PDF được |
| KKL-E09-03 | LedgerPaywall | Điểm hiện paywall: tạo nhà thứ 2, chọn mẫu thương hiệu; nội dung paywall 4 ngôn ngữ; không bao giờ chặn xuất | MVP | 0,5 | CORE-E07-02; KKL-E09-01 | Khi người dùng miễn phí tạo nhà thứ 2 thì paywall hiện gói năm và "thêm 1 nhà" cạnh nhau; khi bấm xuất PDF/USDZ thì không bao giờ mở paywall |
| KKL-E09-04 | LedgerPaywall | 🧪 Kiểm chứng sớm rủi ro review: tạo sản phẩm slot trong App Store Connect, hỏi App Review, chuẩn bị phương án B (chỉ gói năm) | MVP | 0,5 | CORE-E07-01 | Khi hết sprint 1 thì có câu trả lời hoặc quyết định phương án, ghi vào mục 10 của thiết kế kỹ thuật |
| KKL-E09-05 | LedgerPaywall | Test StoreKit: file `.storekit`, `SKTestSession` cho mua, khôi phục, hoàn tiền, hết hạn, Ask to Buy | MVP | 0,5 | KKL-E09-02 | Khi giả lập hoàn tiền một slot thì nhà gắn slot đó chuyển chỉ đọc và dữ liệu không mất |
| KKL-E09-06 | LedgerPaywall | Gói chủ nhà: non-consumable 5 slot (`kkl.bundle.landlord5`) nếu dữ liệu cho thấy nhiều người mua 2–4 slot | V1.1 | 0,5 | KKL-E09-02 | Khi mua gói chủ nhà thì hạn mức tăng 5 và khôi phục được |
| KKL-E09-07 | LedgerPaywall | Gói tháng hoặc trọn đời (thử ở DE) theo kết quả 8 tuần | V1.1 | 0,5 | KKL-E09-01 | Khi mua trọn đời thì quyền lợi giống gói năm và không hết hạn |
| KKL-E09-08 | LedgerPaywall | Offer code, win-back, "Quản lý gói" | V1.1 | 0,5 | CORE-E07-03 | Khi nhập offer code gói năm thì quyền lợi kích hoạt |

## KKL-E10 · Bản địa hóa & tuân thủ

Mục tiêu: ra mắt đồng thời UK, DE, FR, NL; không hứa quá về đo đạc hay giá trị pháp lý; qua App Review trên máy không LiDAR.

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| KKL-E10-01 | (app) | String Catalog EN (US, GB), DE, FR, NL cho giao diện, tên phòng, phần tử checklist, danh mục item; đơn vị mét và m² | MVP | 0,5 | CORE-E10-01 | Khi đổi ngôn ngữ máy sang NL thì mọi màn chính và PDF không còn chuỗi tiếng Anh sót |
| KKL-E10-02 | (app) | Disclaimer: không phải khảo sát đo đạc chính thức hay tư vấn pháp lý; dung sai đo; hiện lần đầu, trong Cài đặt và chân trang PDF | MVP | 0,5 | CORE-E13-01 | Khi xuất bất kỳ PDF nào thì chân trang có disclaimer đúng ngôn ngữ mẫu |
| KKL-E10-03 | (app) | Quyền riêng tư: purpose string camera, nhắc hỏi ý kiến trước khi chụp người hoặc đồ của người khác, không ghi GPS, `PrivacyInfo.xcprivacy` | MVP | 0,5 | CORE-E13-01 | Khi từ chối quyền camera thì app không crash, hiện hướng dẫn mở Cài đặt và vẫn nhập được ảnh từ thư viện |
| KKL-E10-04 | (app) | Review Notes: cách test trên máy không LiDAR (chế độ dự phòng + dự án mẫu), link video quét LiDAR, cách test slot và gói năm | MVP | 0,5 | KKL-E01-06; CORE-E13-01 | Khi một người ngoài nhóm làm theo Review Notes trên iPhone 17 thì xem được mặt bằng mẫu, xuất được PDF và mua thử được trong sandbox |
| KKL-E10-05 | (app) | Hiển thị phụ ft/in và ft² (EN-US, tùy chọn ở UK) | V1.1 | 0,5 | KKL-E10-01 | Khi bật hiển thị phụ thì PDF ghi "12,0 m² (129 ft²)" theo định dạng locale |
| KKL-E10-06 | LedgerCondition | Làm mờ mặt người trong ảnh trước khi xuất (Vision phát hiện khuôn mặt) | V1.1 | 1 | KKL-E03-01 | Khi ảnh có người thì ảnh trong PDF bị làm mờ vùng mặt; ảnh gốc trên máy không đổi |
| KKL-E10-07 | LedgerReport | Mô tả văn bản cho mặt bằng: VoiceOver đọc tên phòng, m², số tường; PDF có bảng kích thước dạng chữ | V1.1 | 0,5 | KKL-E06-01; CORE-E09-02 | Khi dùng VoiceOver trên mặt bằng thì nghe được tên phòng, m² và số tường |
| KKL-E10-08 | (app) | Bản địa hóa đợt 2: IT, ES (giao diện + mẫu biên bản) | V2 | 1,5 | KKL-E10-01; KKL-E06-03 | Khi đổi ngôn ngữ sang IT thì mọi màn chính và mẫu PDF IT hiển thị đúng |

## KKL-E11 · Chất lượng đo đạc

Mục tiêu: có số liệu thật về sai số trước khi viết bất kỳ câu nào về độ chính xác trong app hay trên App Store. RoomPlan không chạy trong Simulator, nên logic phải test được bằng fixture.

| ID | Module | Feature | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| KKL-E11-01 | (tests) | Thư viện fixture: ≥ 12 phòng quét thật (JSON `CapturedRoom`, `RoomGeometrySnapshot`, USDZ, số đo laser); loader cho unit test, SwiftUI preview, UI test và dự án mẫu | MVP | 1 | KKL-E02-04 | Khi chạy test trên Simulator thì mọi test hình học chạy bằng fixture, không cần RoomPlan |
| KKL-E11-02 | Tools/room-bench | Giao thức benchmark với máy đo laser trên N ≥ 12 phòng khác hình dạng; CLI tính sai số theo tường, cửa, diện tích (LiDAR và AR) | MVP | 1,5 | KKL-E11-01; KKL-E03-03 | Khi chạy `room-bench` thì in bảng MAE và P95 theo loại số đo và thiết bị; kết quả được dùng làm dung sai công bố |
| KKL-E11-03 | (qa) | Ma trận thiết bị và nhiệt: phiên 10 phút trên 3 máy LiDAR, luồng dự phòng trên 3 máy không LiDAR; ghi `thermalState`, bộ nhớ đỉnh, thời gian `RoomBuilder` | MVP | 1 | KKL-E02-03 | Khi hoàn tất ma trận thì không máy nào crash và số liệu nằm trong ngân sách ở mục 11, hoặc có ticket sửa |
| KKL-E11-04 | (tests) | UI test khói: luồng chính với scanner giả nạp fixture và luồng máy không LiDAR | MVP | 0,5 | KKL-E11-01 | Khi CI chạy UI test thì luồng tạo nhà → quét giả → ký → xuất PDF pass trên Simulator |
| KKL-E11-05 | (app) | Chia sẻ thống kê phiên quét tự nguyện qua share sheet (người dùng tự gửi); kiểm tra ảnh hưởng tới nhãn quyền riêng tư ⚠ | V1.1 | 0,5 | KKL-E02-03 | Khi người dùng bấm "Gửi thống kê" thì chỉ file đếm phiên (không ảnh, không tên, không địa chỉ) được đưa vào share sheet |
| KKL-E11-06 | (qa) | Chạy lại benchmark trên bản iOS lớn mới và máy mới | V1.1 | 1 | KKL-E11-02 | Khi có bản iOS lớn mới thì trong 2 tuần có bảng benchmark mới; dung sai công bố được cập nhật nếu lệch |

## Tổng theo ưu tiên

| Epic | MVP | V1.1 | V2 | Tổng | Số feature |
|---|---|---|---|---|---|
| KKL-E01 Bất động sản & dự án | 5 | 4 | 0 | 9 | 10 |
| KKL-E02 Quét phòng LiDAR | 8 | 7,5 | 0 | 15,5 | 14 |
| KKL-E03 Chế độ không LiDAR | 5 | 3,5 | 1,5 | 10 | 8 |
| KKL-E04 Kiểm kê đồ đạc | 2,5 | 4,5 | 4,5 | 11,5 | 10 |
| KKL-E05 Tình trạng & biên bản | 5,5 | 5,5 | 4,5 | 15,5 | 11 |
| KKL-E06 Báo cáo & xuất | 8 | 4 | 3 | 15 | 13 |
| KKL-E07 Module Pro tiền khảo sát | 0 | 0 | 14 | 14 | 7 |
| KKL-E08 Lưu trữ & hiệu năng tài sản | 1,5 | 3 | 4 | 8,5 | 5 |
| KKL-E09 Paywall & gói | 3,5 | 1,5 | 0 | 5 | 8 |
| KKL-E10 Bản địa hóa & tuân thủ | 2 | 2 | 1,5 | 5,5 | 8 |
| KKL-E11 Chất lượng đo đạc | 4 | 1,5 | 0 | 5,5 | 6 |
| **Tổng** | **45** | **37** | **33** | **115** | **100** |

Số feature theo ưu tiên: MVP 49, V1.1 35, V2 16. Trong đó có 4 spike 🧪 (KKL-E02-08, KKL-E02-11, KKL-E07-05, KKL-E09-04).

Phần lõi dùng lại (không tính ở trên): CoreCapture (CORE-E02-01..03), CoreOCR (CORE-E03-01..03), CoreExtraction (CORE-E04-01, -03), CoreStore (CORE-E05-01..03), CoreExport (CORE-E06-01..03), CorePaywall (CORE-E07-01..03), CoreSecurity (CORE-E08-01), CoreDesign (CORE-E09-01..02), CoreLocalization (CORE-E10-01), CoreIntents (CORE-E11-01), CoreDiagnostics (CORE-E12-01), CoreCompliance (CORE-E13-01). `CoreDevice` có trong [shared-core.md mục 3.1](../shared-core.md) nhưng chưa có ID trong backlog lõi; tạm tham chiếu CORE-E01-01 (xem câu hỏi mở ở thiết kế kỹ thuật).

## Lộ trình sprint

Kế hoạch 12 tháng đặt app 03 xây trong tháng 1–2/2027 và ra mắt tháng 3/2027. Bốn sprint 2 tuần, mỗi sprint kết thúc bằng một build TestFlight nội bộ.

| Sprint | Ngày | Mục tiêu | Feature | Ngày công |
|---|---|---|---|---|
| S1 | 4/1 – 15/1/2027 | Nền dữ liệu, quét một phòng ra JSON + USDZ, camera, hỏi App Review sớm | KKL-E01-01, -02, -03, -04; KKL-E02-01, -02, -03, -04, -08 🧪; KKL-E03-01; KKL-E08-01; KKL-E09-04 🧪; KKL-E11-01 (ghi fixture) | 12 |
| S2 | 18/1 – 29/1/2027 | Hình học, m², mặt bằng 2D, chế độ không LiDAR, item | KKL-E02-05, -06, -07; KKL-E06-01; KKL-E03-02, -03, -04; KKL-E04-01, -02, -03; KKL-E08-02 | 12,5 |
| S3 | 1/2 – 12/2/2027 | Biên bản, chữ ký, manifest, mẫu theo nước, mọi định dạng xuất | KKL-E05-01, -02, -03, -04, -05; KKL-E06-02, -03, -04, -05, -06, -07; KKL-E03-05 | 11,5 |
| S4 | 15/2 – 26/2/2027 | Paywall, bản địa hóa, tuân thủ, benchmark, dự án mẫu, nộp review | KKL-E09-01, -02, -03, -05; KKL-E10-01, -02, -03, -04; KKL-E11-02, -03, -04; KKL-E01-05, -06 | 9 |
| Ra mắt | 1/3 – 9/3/2027 | Trả lời App Review, metadata 4 locale, bật Apple Ads thử (≈ $1.070) | – | – |
| **Tổng MVP** | | | | **45** |

Ghi chú lịch:
- Nộp App Review chậm nhất 26/2. Ra mắt dự kiến tuần 1–9/3/2027 tùy thời gian duyệt.
- Nếu dev rảnh sau khi app 01 ra mắt (đầu 12/2026), kéo sớm KKL-E02-08 (spike sàn) và KKL-E09-04 (hỏi App Review) sang tuần 14–18/12/2026 để giảm rủi ro S1.
- Việc không tính ngày công nhưng phải xong trước S4: dịch 4 ngôn ngữ, rà soát nội dung mẫu biên bản UK/DE/FR/NL ⚠, ảnh chụp màn hình, video quét LiDAR cho Review Notes, privacy policy.

**1 hay 2 dev.** MVP 45 ngày công. Một dev có tối đa 40 ngày danh nghĩa trong 8 tuần, thực tế khoảng 34–36 ngày vì còn sửa lỗi app 01 (đang trong 8 tuần đo lường), review code và làm việc với nội dung. Vậy:
- **2 dev (hoặc 1 dev + 1 dev bán thời gian khoảng 50%): vừa lịch 8 tuần.** Mỗi sprint dùng khoảng 60% công suất; phần dư dành cho tích hợp UI, sửa lỗi TestFlight và bản dịch. Gợi ý chia: dev A làm quét, hình học, mặt bằng, báo cáo (E02, E06, E11); dev B làm dữ liệu, không LiDAR, item, biên bản, paywall (E01, E03, E04, E05, E09, E10).
- **1 dev: không vừa 8 tuần.** Chọn một trong hai: (a) lùi ra mắt 2–3 tuần (cuối 3/2027), dời lịch đo lường sang tháng 4–5 và làm app 02 trễ tương ứng; hoặc (b) cắt khoảng 3 ngày sang V1.1 là KKL-E09-02/-04/-05 (ra mắt chỉ với gói năm), KKL-E06-07 (CSV), phần FR/NL của KKL-E06-03 (ra UK, DE trước, FR, NL sau 2–3 tuần). Phương án (b) vẫn còn khoảng 42 ngày, nên thực tế cần kết hợp với (a).

**Thứ tự V1.1** (8 tuần sau ra mắt, trùng lúc xây app 02; chỉ làm phần dữ liệu ủng hộ):
1. So sánh move-in/move-out: KKL-E01-07, KKL-E05-08, KKL-E05-09 (5 ngày).
2. Giá trị trả phí: KKL-E06-09 mẫu thương hiệu, KKL-E01-08 lịch sử thuê, KKL-E09-06..08 (4,5 ngày).
3. Độ tin cậy dữ liệu: KKL-E02-09, KKL-E02-10, KKL-E08-04 (3,5 ngày).
4. Kiểm kê: KKL-E04-04, KKL-E04-06, KKL-E04-08, KKL-E05-06 (3,5 ngày).
5. Nhiều phòng: KKL-E02-11 🧪 trước; chỉ làm KKL-E02-12 và KKL-E06-10 nếu spike đạt (6 ngày).
6. Phần còn lại theo phản hồi người dùng.
