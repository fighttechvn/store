# Thiết kế sản phẩm và kỹ thuật cho 3 app iOS đầu tiên

Thư mục này chứa kế hoạch tính năng và thiết kế kỹ thuật cho 3 app đứng đầu trong [báo cáo nghiên cứu](../reports/App%20iPhone%20offline%20d%C3%B9ng%20c%E1%BA%A3m%20bi%E1%BA%BFn.md) và [kế hoạch 12 tháng](../reports/K%E1%BA%BF%20ho%E1%BA%A1ch%20top%205%20app%20iOS.md).

| Thư mục | App | Tên mã (target Xcode) | Mã ID | Ra mắt dự kiến | Thị trường đợt 1 |
|---|---|---|---|---|---|
| [01-so-chung-tu](01-so-chung-tu/) | Sổ chứng từ riêng tư | `ReceiptBook` | `SCT` | Đầu 12/2026 | UK, DE, FR, EN-US; chế độ VN |
| [02-nhan-di-ung](02-nhan-di-ung/) | Máy quét nhãn thành phần và dị ứng | `AllergenLens` | `NDU` | 5/2027 | FR, DE, IT, ES, NL, UK |
| [03-kiem-ke-lidar](03-kiem-ke-lidar/) | Kiểm kê LiDAR và biên bản nhà thuê | `RoomLedger` | `KKL` | 3/2027 | UK, DE, FR, NL |

Tên mã chỉ dùng nội bộ, chưa phải tên thương mại. Thứ tự build theo kế hoạch 12 tháng là 01 → 03 → 02. Số thứ tự thư mục theo thứ hạng trong báo cáo.

Phần dùng chung cho cả 3 app nằm ở [shared-core.md](shared-core.md) (mã `CORE`).

## Mỗi thư mục app gồm

| File | Nội dung |
|---|---|
| `README.md` | Tổng quan: người dùng, định vị, phạm vi MVP và bản sau, số liệu thị trường, KPI, rủi ro |
| `epics-features.md` | Chia tính năng theo **Epic → Module → Feature**, có ưu tiên, ước tính và tiêu chí nghiệm thu |
| `technical-design.md` | Kiến trúc, mô hình dữ liệu, pipeline xử lý, API Apple, ma trận thiết bị, bảo mật, hiệu năng, kiểm thử, spike kỹ thuật |
| `backlog.csv` | Danh sách feature dạng CSV để nhập vào Jira, Linear hoặc GitHub Projects |

## Quy ước

**Cấp bậc**
- **Epic:** một năng lực nghiệp vụ người dùng nhận thấy được, ví dụ "Chụp chứng từ".
- **Module:** một Swift module (target trong package) sở hữu phần code của epic. Một epic có thể dùng nhiều module; module dùng chung nằm trong `SensorCore`.
- **Feature:** một đơn vị giao được, có tiêu chí nghiệm thu, ước tính 0,5–5 ngày công.

**Mã ID:** `<APP>-E<NN>-<NN>`. Ví dụ `SCT-E03-04` là feature thứ 4 của epic 3 trong app Sổ chứng từ. Epic dùng `<APP>-E<NN>`. Phần lõi dùng `CORE-E<NN>-<NN>`.

**Ưu tiên**
- `MVP`: bắt buộc cho bản ra mắt đầu tiên.
- `V1.1`: trong vòng 8 tuần sau ra mắt, tùy dữ liệu đo lường.
- `V2`: sau khi app đạt tiêu chí "đẩy mạnh".

**Ước tính:** ngày công của 1 dev iOS có kinh nghiệm, đã gồm unit test. Không gồm thiết kế UI, dịch thuật và nội dung.

**Tiêu chí nghiệm thu:** viết ngắn dạng "Khi … thì …", kiểm chứng được bằng test hoặc thao tác thủ công.

**Đánh dấu**
- ⚠ **cần xác minh**: chi tiết API, quy định pháp lý hoặc số liệu chưa được xác nhận từ nguồn chính thức. Phải xác minh trước khi code hoặc trước khi đưa vào metadata App Store.
- 🧪 **spike**: việc cần làm thử (time-box 1–3 ngày) trước khi cam kết thiết kế.

## Ràng buộc chung cho cả 3 app

- iOS 26 trở lên, Xcode 26 trở lên, Swift 6 với strict concurrency, SwiftUI và Observation.
- **Xử lý on-device.** MVP không có server riêng, không có SDK analytics hay quảng cáo, nhắm nhãn "Data Not Collected".
- Lõi chạy trên mọi iPhone hỗ trợ iOS 26. Foundation Models (iPhone 15 Pro trở lên) và LiDAR (dòng Pro) chỉ là lớp nâng cấp, luôn có đường dự phòng.
- Thanh toán qua Apple IAP (StoreKit 2), đăng ký Small Business Program. Ở EU không bật thanh toán thay thế hay link-out.
- Bản địa hóa đợt 1: EN-US, EN-UK, DE, FR. Tiếng Việt có trong app 1 (chế độ VN) và đợt 3 cho các app còn lại.

## Tổng hợp khối lượng

Số liệu lấy từ các file `backlog.csv`; đơn vị là ngày công của 1 dev.

| Phần | Epic | Feature | MVP | V1.1 | V2 | Tổng |
|---|---|---|---|---|---|---|
| [Lõi `SensorCore`](shared-core.md) | 14 | 33 | 44,5 | 4 | 0 | 48,5 |
| [01 · Sổ chứng từ](01-so-chung-tu/) | 12 | 87 | 50 | 52,5 | 22,5 | 125 |
| [02 · Nhãn dị ứng](02-nhan-di-ung/) | 10 | 69 | 45 | 20 | 11 | 76 |
| [03 · Kiểm kê LiDAR](03-kiem-ke-lidar/) | 11 | 100 | 45 | 37 | 33 | 115 |
| **Tổng** | **47** | **289** | **184,5** | **113,5** | **66,5** | **364,5** |

App 02 còn khoảng **148 ngày công nội dung** cho MVP, không phải code: từ điển dị ứng 9 ngôn ngữ, mẫu thẻ du lịch, bộ ảnh nhãn để kiểm thử an toàn, bản dịch, rà soát pháp lý.

### Epic của từng app

| App | Epic |
|---|---|
| 01 · Sổ chứng từ | E01 Onboarding & hồ sơ · E02 Chụp & nhập chứng từ · E03 Nhận dạng & trích xuất · E04 Hóa đơn điện tử · E05 Phân loại & sổ sách · E06 Kỳ báo cáo & xuất · E07 Lưu trữ, bảo mật & toàn vẹn · E08 Tìm kiếm & tích hợp hệ thống · E09 Paywall & gói · E10 Bản địa hóa & tuân thủ · E11 Chế độ Việt Nam (V1.1) · E12 Chất lượng |
| 02 · Nhãn dị ứng | E01 Onboarding & hồ sơ dị ứng · E02 Quét nhãn · E03 Phân tích thành phần · E04 Từ điển & dữ liệu · E05 Kết quả & giải thích · E06 Thẻ dị ứng du lịch · E07 Lịch sử & sản phẩm đã lưu · E08 Paywall & gói · E09 Bản địa hóa & tuân thủ · E10 An toàn & chất lượng |
| 03 · Kiểm kê LiDAR | E01 Bất động sản & dự án · E02 Quét phòng LiDAR · E03 Chế độ không LiDAR · E04 Kiểm kê đồ đạc · E05 Tình trạng & biên bản · E06 Báo cáo & xuất · E07 Module Pro tiền khảo sát cải tạo (V2) · E08 Lưu trữ & hiệu năng tài sản · E09 Paywall & gói · E10 Bản địa hóa & tuân thủ · E11 Chất lượng đo đạc |

## Nhân sự và lịch

Thiết kế chi tiết cho thấy kế hoạch 12 tháng ("1–2 dev") thực tế cần **2 dev iOS từ cuối 9/2026 đến hết 4/2027**, cộng một nhóm nội dung cho app 02.

| Giai đoạn | Việc | Khối lượng trước khi nộp | Nhân sự tối thiểu | Ghi chú |
|---|---|---|---|---|
| 28/9–4/12/2026 | Lõi + app 01 | khoảng 93,5 ngày công | 2 dev toàn thời gian | 1 dev thì nộp khoảng 2/2027, lỡ mùa thuế. Có cut-line 4,5 ngày và phương án B (UK, US trước) |
| 4/1–26/2/2027 | App 03 | 45 ngày công | 2 dev, hoặc 1 dev + 50% dev thứ hai | 1 dev thì lùi ra mắt 2–3 tuần |
| 22/2–30/4/2027 | App 02 | 45 ngày công + 5 ngày spike | 1 dev (10 tuần) | Chồng lên giai đoạn sửa lỗi sau ra mắt app 03. Nội dung 148 ngày công phải bắt đầu từ 12/2026–1/2027 |

## Việc cần xác minh sớm nhất

Mỗi thư mục có danh sách ⚠ riêng. Các mục ảnh hưởng tới code MVP phải xác minh trong sprint đầu của app đó:

- **Lõi:** danh sách ngôn ngữ của `RecognizeDocumentsRequest`; mã `vi-VT` trên máy thật; chữ ký API Foundation Models; `Decimal` trong SwiftData; ảnh hưởng của MetricKit/CloudKit tới nhãn "Data Not Collected".
- **01:** lịch quý của UK MTD; danh mục chi phí từng nước; định dạng DATEV và phần mềm kế toán; bảng ánh xạ EN 16931 sang UBL/CII; đọc file đính kèm PDF/A-3.
- **02:** câu chữ 14 chất gây dị ứng theo Phụ lục II Quy định 1169/2011 ở từng ngôn ngữ; nguồn dị ứng của E-number mơ hồ và giấy phép dữ liệu; phạm vi MDR, trách nhiệm sản phẩm và GDPR Điều 9; quy định sử dụng Foundation Models cho phần giải thích.
- **03:** API RoomPlan (`floors`, `Codable`, `StructureBuilder`, lỗi phiên quét); App Review với sản phẩm "slot" không tiêu hao; nội dung bắt buộc của mẫu biên bản FR/UK/DE/NL.

## Họ app thứ hai: film và LUT (Filmode)

Thư mục [film-lut/](film-lut/README.md) chứa kế hoạch cho một họ app khác, Android trước, dựng trên lõi chung Filmode Core (`FLC`), theo [báo cáo "Lõi LUT của Filmode đủ nuôi ba app"](../reports/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u.md). Quy ước ID, ưu tiên và gói của họ app này nằm trong README của thư mục đó, không dùng quy ước ở trên.

- [01 · Filmode](film-lut/01-filmode/) (`FMD`): máy ảnh digicam, film và chế độ sự kiện; bản dựng lại ra mắt 18/1/2027.
- [02 · Filmode Studio](film-lut/02-filmode-studio/) (`FMS`): công thức màu và LUT cho ảnh; Android Q1/2027, iOS Q2/2027.
- [03 · FilCam](film-lut/03-filcam/) (`FCM`): máy quay LUT và RAW; Android Q3/2027.
