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
