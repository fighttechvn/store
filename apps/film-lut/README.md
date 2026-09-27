# Kế hoạch sản phẩm cho ba app Filmode (camera film và LUT)

Thư mục này chứa kế hoạch tính năng cho ba app film/LUT đề xuất trong [báo cáo "Lõi LUT của Filmode đủ nuôi ba app"](../../reports/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u.md), mục "Ba app nên xây trên một lõi look chung" (Bảng 8–13). Nhà phát triển: Trung-Hieu Tran / FightTech (Việt Nam).

Ba app dùng chung một lõi là **Filmode Core** (mã `FLC`), mô tả ở [filmode-core.md](filmode-core.md). Điểm nối ba app là một định dạng look chung (`.flook`: LUT .cube kèm công thức JSON), chia sẻ được bằng QR và link ([filmode-core.md, mục 5](filmode-core.md#5-định-dạng-look-flook-v1)).

| Thư mục | App | Mã | Package / bundle | Nền tảng (thứ tự) | Ra mắt dự kiến (Bảng 13) | Thị trường đợt 1 |
|---|---|---|---|---|---|---|
| [01-filmode](01-filmode/) | **Filmode**: máy ảnh digicam, film và sự kiện. Hiện là "Filmode Vibe" trên Play và "Filmode - Film & LUT Editor" trên iOS | `FMD` | Android `app.filmode`; iOS id 6791145420, bundle `app.filmode` | Android và iOS song song (iOS đã có) | Sửa nền T10/2026; bản dựng trên lõi T10/2026–T1/2027, kịp Tết Nguyên đán 2027 | VN, ID, TH, PH, KR, BR |
| [02-filmode-studio](02-filmode-studio/) | **Filmode Studio**: công thức màu và LUT cho ảnh (app mới, tách từ trình sửa của Filmode iOS) | `FMS` | Android `app.filmode.studio` (đề xuất ⚠); iOS bundle mới (đề xuất ⚠) | Android trước, iOS sau khoảng một quý | Android Q1/2027; iOS Q2/2027 | VN, ID; EN (US, SG, AU) cho "film recipes"; JP |
| [03-filcam](03-filcam/) | **FilCam**: máy quay LUT và RAW | `FCM` | Android `app.filmode.filcam`; iOS chưa có | Android trước; iOS khi bản Android đã ổn định | Android Q2–Q3/2027 | VN, US, ID, BR; sau đó JP, KR, DE |

Thứ tự làm theo báo cáo: 01 → 02 → 03. Filmode đi trước vì đã có sẵn và vì lượng tìm "digicam" đang ở đỉnh. Tên store gợi ý và giá đề xuất nằm ở Bảng 8 của báo cáo.

## Mỗi thư mục app gồm

| File | Nội dung |
|---|---|
| `README.md` | Tổng quan: người dùng, định vị, phạm vi MVP và bản sau, gói và giá, số liệu thị trường, KPI theo Bảng 13, rủi ro |
| `epics-features.md` | Chia tính năng theo **Epic → Module → Feature**, có gói, ưu tiên, ước tính, phụ thuộc và tiêu chí nghiệm thu |
| `backlog.csv` | Danh sách feature dạng CSV để nhập Jira, Linear hoặc GitHub Projects |

Lõi dùng hai file ở thư mục này: [filmode-core.md](filmode-core.md) và [filmode-core-backlog.csv](filmode-core-backlog.csv).

## Quy ước

**Cấp bậc**
- **Epic:** một năng lực người dùng nhận thấy, ví dụ "Ảnh động" hay "Quay video có LUT".
- **Module:** một đơn vị code sở hữu phần việc. Trên Android là Gradle module: lõi là `:core:<tên>` (danh sách ở [filmode-core.md mục 3](filmode-core.md#3-bản-đồ-module)); app là `:app:filmode`, `:app:studio`, `:app:filcam` và module tính năng riêng đề xuất đặt tên `:filmode:<tên>`, `:studio:<tên>`, `:filcam:<tên>`. Trên iOS là target Swift package, ghi dạng `FilmodeCoreKit/<Target>` cho lõi và `<App>Kit/<Target>` cho app. Module giả: `build-logic`, `(ci)`, `(tools)`, `(qa)`, `(backend)`, `(web)`, `(app)`.
- **Feature:** một đơn vị giao được, có tiêu chí nghiệm thu, ước tính 0,5–5 ngày công. Lớn hơn thì tách.

**Mã ID:** epic là `<APP>-E<NN>`, feature là `<APP>-E<NN>-<NN>`. Ví dụ `FMD-E03-02` là feature thứ 2 của epic 3 trong Filmode. Mã app: `FLC` (lõi), `FMD`, `FMS`, `FCM`. ID đã phát hành không bao giờ đổi hay dùng lại; feature bỏ đi thì giữ dòng và ghi "(bỏ)".

**Ánh xạ với báo cáo:** mỗi epic có cột "↔ Báo cáo" trỏ về số epic trong báo cáo. Lõi: C1–C6 → `FLC-E01`…`FLC-E06`; epic thêm đánh số tiếp (`FLC-E07`, `FLC-E08`). Khuyến nghị cho app giữ đúng thứ tự của báo cáo: A1–A11 (Bảng 10) → `FMD-E01`…`FMD-E11`, B1–B11 (Bảng 11) → `FMS-E01`…`FMS-E11`, F1–F9 (Bảng 12) → `FCM-E01`…`FCM-E09`. Epic thêm (ví dụ chất lượng, iOS) đánh số tiếp và ghi lý do. Trong cột Feature có thể ghi số module của báo cáo, ví dụ "(A3.2)".

**Phụ thuộc:** app chỉ tham chiếu feature lõi (`FLC-…`) trong cột "Phụ thuộc", không làm lại. App cần lõi thay đổi thì ghi vào mục "Điều chỉnh lõi" trong `epics-features.md` của app để người điều phối đưa vào lõi. Nhiều phụ thuộc ngăn bằng `;`.

**Ưu tiên**
- `Có sẵn`: đã phát hành trong Filmode Vibe 1.5.9, Filmode iOS 1.4.4 hoặc FilCam 1.0.21. Ghi số ngày cần để kiểm lại, gom vào module hoặc refactor (thường 0–1,5 ngày; 0 nếu chỉ cần kiểm tra).
- `MVP`: bắt buộc cho bản ra mắt đầu tiên của app theo Bảng 13. Với Filmode, MVP là bản dựng lại trên lõi ở giai đoạn 1. Với lõi, `MVP` là thứ phải xong trước bản Filmode đó.
- `V1`: bản tiếp theo, trong 1–2 quý sau ra mắt (cột "V1" của Bảng 10–12). Với lõi, `V1` là thứ phải xong trước MVP của Studio hoặc FilCam, trước bản iOS dùng lõi, hoặc trước một mục V1 của app; cột Feature ghi "cần cho …".
- `V2`: sau khi app đạt mốc đo của Bảng 13.
- `V3`: tầm xa, ví dụ gói look mang thương hiệu creator (B9.3).

**Gói** (cột "Gói", một giá trị mỗi dòng)
- `Free`: miễn phí mãi. Được ghi vào `free-tier.json` và không bao giờ chuyển sang trả phí (FLC-E03-04).
- `Pro`: mở bằng thuê bao tháng/năm hoặc gói trọn đời của app đó.
- `IAP`: mua lẻ một lần: một máy, một gói look, gói theo mùa, gói creator.
- `Pass`: pass sự kiện (Group, Party, Wedding), dùng cho một sự kiện.
- `—`: hạ tầng hoặc việc không bán.

Một tính năng có phần miễn phí và phần trả phí (ví dụ "cuộn 12 kiểu Free, 24/36 Pro") thì tách thành hai dòng.

**Ước tính:** ngày công của 1 dev Android có kinh nghiệm (dev iOS cho mục iOS), đã gồm unit test. Không gồm thiết kế UI, dịch thuật, nội dung (dựng look, LUT, khung) và rà soát pháp lý.

**Tiêu chí nghiệm thu:** viết ngắn dạng "Khi … thì …", kiểm chứng được bằng test tự động hoặc thao tác thủ công có quy trình. Dùng số đo khi có thể (fps, giây, ΔE).

**Đánh dấu**
- ⚠ **cần xác minh**: chi tiết API, chính sách store, quy định pháp lý hoặc số liệu chưa được xác nhận từ nguồn chính thức. Phải xác minh trước khi code hoặc trước khi đưa vào metadata store.
- 🧪 **spike**: việc làm thử có giới hạn thời gian (1–3 ngày) trước khi cam kết thiết kế. Spike là một dòng riêng trong backlog.

**CSV:** header đúng như sau, mỗi feature một dòng, UTF-8, dấu thập phân là `.`:

```
id,app,epic_id,epic,module,feature,tier,priority,estimate_days,depends_on,acceptance_criteria
```

`tier` là giá trị của cột Gói; `depends_on` ngăn bằng `;`.

## Ràng buộc chung cho cả ba app

**Android**
- `minSdk` 26 (Android 8.0). FilCam đang ghi Android 8.0+ trên trang web; minSdk của Filmode Vibe chưa rõ ⚠. CameraX 1.6 cần tối thiểu API 23 nên không vướng.
- `targetSdk` và `compileSdk` 36 ⚠ theo lịch target API của Play lúc phát hành.
- OpenGL ES 3.0 là bắt buộc (khai `uses-feature` glEsVersion 0x00030000). AGSL (API 33+) chỉ dùng cho hiệu ứng UI và luôn có dự phòng.
- Stack: Kotlin, Jetpack Compose, CameraX 1.6.x (Camera2Interop cho điều khiển tay), OpenGL ES 3.x, Media3 Transformer và effect ⚠ bản, Play Billing Library 8.x ⚠, Room, DataStore, WorkManager, kotlinx.serialization.
- Quyền: `CAMERA`; `RECORD_AUDIO` chỉ khi quay có tiếng; không `READ_MEDIA_*`, chỉ dùng Photo Picker; `WRITE_EXTERNAL_STORAGE` chỉ tới API 28; không `AD_ID`; `ACCESS_MEDIA_LOCATION` chỉ khi người dùng bật giữ vị trí cho ảnh nhập.

**iOS**
- Filmode iOS hiện khai iOS 13.0+. Package lõi `FilmodeCoreKit` đề xuất iOS 17+ ⚠ (StoreKit 2, SwiftUI Observation); cần xem tỉ lệ người dùng trước khi nâng.
- Swift 6 strict concurrency, SwiftUI, AVFoundation, Core Image và Metal, StoreKit 2.
- Phần iOS của lõi là `V1`: Filmode iOS giữ code đang chạy tới khi chuyển sang lõi cùng lúc với Studio iOS (Q2/2027).

**Sản phẩm**
- Không bắt tài khoản, chạy offline. Tài khoản chỉ để đồng bộ, board, sự kiện. Không đăng nhập bằng OTP số điện thoại.
- Không quảng cáo, không watermark. Quyền mua khôi phục được qua store mà không cần tài khoản.
- Không bao giờ chuyển tính năng miễn phí sang Pro; giữ nguyên quyền của người đã mua kể cả khi đổi SKU.
- Paywall theo [checklist của lõi](filmode-core.md#43-checklist-paywall): số tiền thực là chữ lớn nhất, điều khoản dùng thử có ngày, cách hủy bằng tiếng Việt và tiếng Anh, nút đóng thấy ngay.
- Giá theo vùng cho VN, ID, PH, BR, IN; giá VN khoảng 40–50% giá Mỹ (Bảng 8).
- Tên look, công thức, khung, máy đều tự đặt. `NameGuard` và lint chặn Kodak, Portra, Fujifilm, Classic Chrome, Velvia, Polaroid, Instax, Leica, CineStill… Không đóng gói LUT CC BY-SA (RawTherapee, G'MIC).
- Ngôn ngữ đợt 1: vi, en, ko, ja, id, th, pt-BR. Luôn gọi "Tết Nguyên đán / Lunar New Year".
- Hiệu năng: preview 30 fps trên máy tầm trung, xử lý ảnh dưới 1,5 giây ([ngân sách](filmode-core.md#42-ngân-sách-hiệu-năng)).
- Thiết bị: test trên [ma trận của lõi](filmode-core.md#44-ma-trận-thiết-bị) (Galaxy A/S, Redmi Note, OPPO A/Reno, Vivo, Pixel); ẩn tính năng máy không hỗ trợ.
- Quyền riêng tư: theo [lập trường của lõi](filmode-core.md#41-lập-trường-quyền-riêng-tư). Ảnh xử lý trên máy; chỉ thu dữ liệu ẩn danh để sửa lỗi và đo phễu, tắt được; không hứa "Không thu thập dữ liệu".

## Tổng hợp khối lượng

Đơn vị là ngày công của 1 dev. Số của lõi lấy từ [filmode-core-backlog.csv](filmode-core-backlog.csv); số của app sẽ điền khi ba thư mục app xong.

| Phần | Epic | Feature | Có sẵn | MVP | V1 | V2 | V3 | Tổng |
|---|---|---|---|---|---|---|---|---|
| [Lõi Filmode Core (`FLC`)](filmode-core.md) | 8 | 75 | 6,5 | 96 | 64,5 | 0 | 0 | 167 |
| [01 · Filmode (`FMD`)](01-filmode/) | xem thư mục app | | | | | | | |
| [02 · Filmode Studio (`FMS`)](02-filmode-studio/) | xem thư mục app | | | | | | | |
| [03 · FilCam (`FCM`)](03-filcam/) | xem thư mục app | | | | | | | |
| **Tổng** | | | | | | | | |

MVP của lõi (96 ngày) phải xong trong giai đoạn 1 cùng App 1, nên cần ít nhất 2 dev Android (xem [lộ trình lõi](filmode-core.md#8-lộ-trình)).

## Bản đồ module

Chiều mũi tên là chiều phụ thuộc: tầng trên dùng tầng dưới, không bao giờ ngược lại. Module lõi không import code app.

```
Tầng app        :app:filmode        :app:studio        :app:filcam      (+ module tính năng riêng của app)
                      │                   │                  │
Tầng giao diện  :core:ui ─── :core:paywall
                      │                   │
Tầng tính năng  :core:camera   :core:library   :core:sync   :core:account   :core:segment
                      │                   │
Tầng xử lý      :core:gpu   :core:lut-io   :core:media   :core:billing
                      │                   │
Tầng nền        :core:look   :core:device   :core:config   :core:analytics   :core:l10n
```

| Module lõi | Filmode (FMD) | Studio (FMS) | FilCam (FCM) | Target iOS tương ứng |
|---|---|---|---|---|
| `:core:look` | ✓ | ✓ | ✓ | `LookFormat` |
| `:core:lut-io` | ✓ | ✓ | ✓ | `LUTIO` |
| `:core:gpu` | ✓ | ✓ | ✓ | `LookRender` |
| `:core:camera` | ✓ | — | ✓ | (app, AVFoundation) |
| `:core:device` | ✓ | ✓ | ✓ | — |
| `:core:segment` | ✓ (photobooth) | ✓ (tông da) | — | (app, Vision) |
| `:core:media` | ✓ | ✓ | ✓ | `MediaKit` |
| `:core:library` | ✓ | ✓ | ✓ | `LookLibrary` |
| `:core:billing` | ✓ | ✓ | ✓ | `StoreCore` |
| `:core:paywall` | ✓ | ✓ | ✓ | `StoreCore` |
| `:core:account` | ✓ (board, sự kiện) | ✓ (đồng bộ, cộng đồng) | ✓ (đồng bộ) | `AccountSync` |
| `:core:sync` | ✓ | ✓ | ✓ | `AccountSync` |
| `:core:l10n` | ✓ | ✓ | ✓ | (String Catalog của app) |
| `:core:analytics` | ✓ | ✓ | ✓ | `Telemetry` |
| `:core:config` | ✓ | ✓ | ✓ | `Telemetry` |
| `:core:ui` | ✓ | ✓ | ✓ | — |
| `:core:testing` | test | test | test | — |

Ngoài app: `(web)` có trang `filmode.app/r` và `/l` cùng renderer WebGL2 (dùng cho web camera sự kiện của FMD); `(backend)` có rules, functions, hosting (Firebase đề xuất ⚠); `(tools)` có `look-cli` và script đẩy giá.

## Việc cần xác minh sớm nhất

Danh sách đầy đủ ở [filmode-core.md mục 10](filmode-core.md#10-rủi-ro-spike-và-việc-cần-xác-minh). Các mục ảnh hưởng tới code MVP:

- Code đang chạy của Filmode Vibe và FilCam: ngôn ngữ, UI, camera stack, minSdk thật, backend của Cloud Boards.
- targetSdk bắt buộc của Play và bản Play Billing Library bắt buộc lúc phát hành.
- Phân loại analytics và crash trong Data safety, App Privacy.
- Yêu cầu xóa tài khoản của Play, vì Filmode Vibe đã có đăng nhập Google.
- Dùng chung khóa ký cho ba app (cần cho thư viện look dùng chung) và hành vi App Links khi nhiều app cùng nhận một link.
- Package và bundle ID của Filmode Studio.
