# Kế hoạch sản phẩm cho ba app Filmode (camera film và LUT)

Thư mục này chứa kế hoạch tính năng cho ba app film/LUT đề xuất trong [báo cáo "Lõi LUT của Filmode đủ nuôi ba app"](../../reports/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u.md), mục "Ba app nên xây trên một lõi look chung" (Bảng 8–13). Nhà phát triển: Trung-Hieu Tran / FightTech (Việt Nam).

Ba app dùng chung một lõi là **Filmode Core** (mã `FLC`), mô tả ở [filmode-core.md](filmode-core.md). Điểm nối ba app là một định dạng look chung (`.flook`: LUT .cube kèm công thức JSON), chia sẻ được bằng QR và link ([filmode-core.md, mục 5](filmode-core.md#5-định-dạng-look-flook-v1)).

| Thư mục | App | Mã | Package / bundle | Nền tảng (thứ tự) | Ra mắt dự kiến | Thị trường đợt 1 |
|---|---|---|---|---|---|---|
| [01-filmode](01-filmode/) | **Filmode**: máy ảnh digicam, film và sự kiện. Hiện là "Filmode Vibe" trên Play và "Filmode - Film & LUT Editor" trên iOS | `FMD` | Android `app.filmode`; iOS id 6791145420, bundle `app.filmode` | Android và iOS song song (iOS đã có) | Sửa nền 5–23/10/2026; bản dựng lại trên lõi ra mắt 18/1/2027, kịp Tết Nguyên đán; chế độ sự kiện ở V1, pilot T3–T4/2027 (lệch Bảng 13, xem [dưới](#chỗ-lệch-so-với-bảng-13)) | VN, ID, TH, PH, KR, BR |
| [02-filmode-studio](02-filmode-studio/) | **Filmode Studio**: công thức màu và LUT cho ảnh (app mới, tách từ trình sửa của Filmode iOS) | `FMS` | Android `app.filmode.studio` (đề xuất ⚠); iOS bundle mới (đề xuất ⚠) | Android trước, iOS sau khoảng một quý | Android 29/3/2027 (Q1); iOS nộp review 18/6/2027 (Q2) | VN, ID; EN (US, SG, AU) cho "film recipes"; JP |
| [03-filcam](03-filcam/) | **FilCam**: máy quay LUT và RAW | `FCM` | Android `app.filmode.filcam`; iOS chưa có | Android trước; iOS khi bản Android đã ổn định | Android 26/7–6/8/2027 (Q3); iOS khoảng Q1/2028 ⚠, chỉ khi đạt mốc đo | VN, US, ID, BR; sau đó JP, KR, DE |

Thứ tự làm theo báo cáo: 01 → 02 → 03. Filmode đi trước vì đã có sẵn và vì lượng tìm "digicam" đang ở đỉnh. Tên store gợi ý và giá đề xuất nằm ở Bảng 8 của báo cáo. Ai làm gì, vào quý nào ở mục [Lịch và nhân sự cả họ app](#lịch-và-nhân-sự-cả-họ-app).

## Ranh giới giữa các app

Apple siết guideline 4.3 từ 9/6/2026: app "biến thể" của cùng nhà phát triển có thể bị từ chối. Filmode iOS đã có trình sửa, Match Photo và bộ nhập .xmp, nên ranh giới Filmode ↔ Studio phải rõ. Quy tắc dưới đây giống hệt ở [README Filmode mục 3.3](01-filmode/README.md#33-ranh-giới-với-filmode-studio-apple-43) và [README Studio mục 2](02-filmode-studio/README.md#2-vì-sao-là-một-app-riêng):

- **Filmode là máy ảnh + chỉnh nhanh:** áp máy hoặc look cho ảnh có sẵn, chỉnh cơ bản, khung, áp hàng loạt, Match Photo để tạo look cho kính ngắm. Chỉnh sâu đi qua nút "Mở trong Filmode Studio" (A6.2, FMD-E06-06).
- **Filmode iOS giữ mọi tính năng trình sửa người dùng đang có hoặc đã trả tiền** (trình sửa, Match Photo, Match → LUT, nhập .cube và .xmp, video 4K, chỉnh hàng loạt): giữ mãi, không gỡ, theo luật của Apple về tính năng đã trả tiền và cam kết không thu hồi (FLC-E03-04, FMD-E11-06). Filmode iOS không nhận thêm tính năng chỉnh sâu mới. Trình sửa đang có của Filmode Vibe trên Android (LUT, preset, curves, nhập .cube; FMD-E06-01) cũng được giữ như vậy.
- **Mọi tính năng chỉnh sâu mới làm ở Studio**, trên cả Android và iOS: công thức theo thang máy ảnh, HSL, bánh xe màu, RAW, xuất LUT, parser công thức dạng chữ, cộng đồng. Filmode Android không thêm màn xuất .cube; look Match được gửi sang Studio để xuất (FMD-E11-05).
- **Quyền Pro mua riêng từng app** (`fmd.*`, `fms.*`, `fcm.*`). Không có tài khoản thì không cấp quyền chéo giữa các package được. Gói chung nhiều app chỉ là phương án V2 ⚠, làm qua tài khoản tùy chọn; chưa có trong backlog.

FilCam là máy quay: quay có LUT, Log, chỉnh màu clip và xuất LUT cho video. Look đi giữa ba app bằng `.flook`, QR và thư viện dùng chung của lõi, không bằng cách chép tính năng của app khác.

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
- **Module:** một đơn vị code sở hữu phần việc. Trên Android là Gradle module: lõi là `:core:<tên>` (danh sách ở [filmode-core.md mục 3](filmode-core.md#3-bản-đồ-module)); app là `:app:filmode`, `:app:studio`, `:app:filcam` và module tính năng riêng đề xuất đặt tên `:filmode:<tên>`, `:studio:<tên>`, `:filcam:<tên>`. Trên iOS là target Swift: lõi ghi `FilmodeCoreKit/<Target>`; app ghi `FilmodeiOS/<Area>`, `StudioiOS/<Area>`, `FilCamiOS/<Area>` (tên tạm ⚠, chốt khi dựng project). Module giả: `build-logic`, `(ci)`, `(tools)`, `(qa)`, `(backend)`, `(web)`, `(app)`.
- **Feature:** một đơn vị giao được, có tiêu chí nghiệm thu, ước tính 0,5–5 ngày công. Lớn hơn thì tách.

**Mã ID:** epic là `<APP>-E<NN>`, feature là `<APP>-E<NN>-<NN>`. Ví dụ `FMD-E03-02` là feature thứ 2 của epic 3 trong Filmode. Mã app: `FLC` (lõi), `FMD`, `FMS`, `FCM`. ID đã phát hành không bao giờ đổi hay dùng lại; feature mới thêm vào cuối epic; feature bỏ đi thì giữ dòng và ghi "(bỏ)".

**Ánh xạ với báo cáo:** mỗi epic có cột "↔ Báo cáo" trỏ về số epic trong báo cáo. Lõi: C1–C6 → `FLC-E01`…`FLC-E06`; epic thêm đánh số tiếp (`FLC-E07`, `FLC-E08`). Khuyến nghị cho app giữ đúng thứ tự của báo cáo: A1–A11 (Bảng 10) → `FMD-E01`…`FMD-E11`, B1–B11 (Bảng 11) → `FMS-E01`…`FMS-E11`, F1–F9 (Bảng 12) → `FCM-E01`…`FCM-E09`. Epic thêm (ví dụ chất lượng, iOS) đánh số tiếp và ghi lý do. Trong cột Feature có thể ghi số module của báo cáo, ví dụ "(A3.2)".

**Phụ thuộc:** app chỉ tham chiếu feature lõi (`FLC-…`) trong cột "Phụ thuộc", không làm lại. App cần lõi thay đổi thì ghi vào mục "Điều chỉnh lõi" trong `epics-features.md` của app; người điều phối đưa vào lõi và ghi FLC ID đang xử lý ở cột cuối của mục đó ([bảng đối chiếu ở lõi mục 11](filmode-core.md#11-yêu-cầu-của-app-đã-đưa-vào-lõi)). Nhiều phụ thuộc ngăn bằng `;`.

**Ưu tiên**
- `Có sẵn`: đã phát hành trong Filmode Vibe 1.5.9, Filmode iOS 1.4.4 hoặc FilCam 1.0.21. Ghi số ngày cần để kiểm lại, gom vào module hoặc refactor (thường 0–1,5 ngày; 0 nếu chỉ cần kiểm tra).
- `MVP`: bắt buộc cho bản ra mắt đầu tiên của app theo Bảng 13. Với Filmode, MVP là bản dựng lại trên lõi ở giai đoạn 1. Với lõi, `MVP` là thứ phải xong trước bản Filmode đó.
- `V1`: bản tiếp theo, trong 1–2 quý sau ra mắt (cột "V1" của Bảng 10–12). Với lõi, `V1` là thứ phải xong trước MVP của Studio hoặc FilCam, trước bản iOS dùng lõi, hoặc trước một mục V1 của app; cột Feature ghi "cần cho …" và [lõi mục 8](filmode-core.md#8-lộ-trình) ghi hạn cụ thể.
- `V2`: sau khi app đạt mốc đo của Bảng 13.
- `V3`: tầm xa, ví dụ gói look mang thương hiệu creator (B9.3).

**Gói** (cột "Gói", một giá trị mỗi dòng)
- `Free`: miễn phí mãi. Được ghi vào `free-tier.json` (mỗi app một mục) và không bao giờ chuyển sang trả phí (FLC-E03-04).
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
- Phần iOS của lõi là `V1`, xong trước 2/4/2027: Filmode iOS giữ code đang chạy tới khi chuyển sang lõi (T3–T4/2027), cùng quý với Studio iOS (Q2/2027).

**Sản phẩm**
- Không bắt tài khoản, chạy offline. Tài khoản chỉ để đồng bộ, board, sự kiện. Không đăng nhập bằng OTP số điện thoại.
- Không quảng cáo, không watermark. Quyền mua khôi phục được qua store mà không cần tài khoản.
- Không bao giờ chuyển tính năng miễn phí sang Pro; giữ nguyên quyền của người đã mua kể cả khi đổi SKU.
- Paywall theo [checklist của lõi](filmode-core.md#43-checklist-paywall): số tiền thực là chữ lớn nhất, điều khoản dùng thử có ngày, cách hủy bằng tiếng Việt và tiếng Anh, nút đóng thấy ngay.
- Giá theo vùng cho VN, ID, PH, BR, IN; giá VN khoảng 40–50% giá Mỹ (Bảng 8).
- Tên look, công thức, khung, máy đều tự đặt. `NameGuard` và lint (FLC-E04-02, FLC-E04-03) chặn tên phim và máy ảnh (Kodak, Portra, Ektar, Fujifilm, Fuji, Velvia, Provia, Classic Chrome, Polaroid, Instax, Leica, Contax, Canon, Lomo, Lomography, Holga, CineStill, Ilford…), kính lọc (Tiffen, Pro-Mist), hãng và phần mềm (Blackmagic, DaVinci, Apple, Samsung, CapCut, VSCO, Lightroom) và app đối thủ (Dazz, Sora, Snap). "Film simulation" là từ khóa ASO chưa rõ có phải nhãn hiệu ⚠: lint chỉ cảnh báo. Không đóng gói LUT CC BY-SA (RawTherapee, G'MIC).
- Ngôn ngữ đợt 1: vi, en, ko, ja, id, th, pt-BR. Luôn gọi "Tết Nguyên đán / Lunar New Year".
- Hiệu năng: preview 30 fps trên máy tầm trung, xử lý ảnh dưới 1,5 giây ([ngân sách](filmode-core.md#42-ngân-sách-hiệu-năng)).
- Thiết bị: test trên [ma trận của lõi](filmode-core.md#44-ma-trận-thiết-bị) (Galaxy A/S, Redmi Note, OPPO A/Reno, Vivo, Pixel; FilCam thêm máy tier A/B); ẩn tính năng máy không hỗ trợ.
- Quyền riêng tư: theo [lập trường của lõi](filmode-core.md#41-lập-trường-quyền-riêng-tư). Ảnh xử lý trên máy; chỉ thu dữ liệu ẩn danh để sửa lỗi và đo phễu, tắt được; không hứa "Không thu thập dữ liệu".

## Tổng hợp khối lượng

Đơn vị là ngày công của 1 dev. Số lấy từ bốn file CSV: [filmode-core-backlog.csv](filmode-core-backlog.csv), [01-filmode/backlog.csv](01-filmode/backlog.csv), [02-filmode-studio/backlog.csv](02-filmode-studio/backlog.csv), [03-filcam/backlog.csv](03-filcam/backlog.csv).

| Phần | Epic | Feature | Có sẵn | MVP | V1 | V2 | V3 | Tổng |
|---|---|---|---|---|---|---|---|---|
| [Lõi Filmode Core (`FLC`)](filmode-core.md) | 8 | 85 | 6,5 | 98,5 | 82,5 | 0 | 0 | 187,5 |
| [01 · Filmode (`FMD`)](01-filmode/) | 13 | 123 | 8,5 | 95 | 109 | 7 | 0 | 219,5 |
| [02 · Filmode Studio (`FMS`)](02-filmode-studio/) | 13 | 106 | 0 | 68 | 95,5 | 78,5 | 4 | 246 |
| [03 · FilCam (`FCM`)](03-filcam/) | 11 | 107 | 10 | 93 | 75 | 43 | 0 | 221 |
| **Tổng** | **45** | **421** | **25** | **354,5** | **362** | **128,5** | **4** | **874** |

Cột MVP của mỗi dòng là một mốc khác nhau: lõi và Filmode trước 15/1/2027, Studio trước 26/3/2027, FilCam trước 23/7/2027. `V1` của lõi là thứ phải xong trước MVP của Studio, FilCam hoặc trước bản iOS dùng lõi ([lõi mục 8](filmode-core.md#8-lộ-trình)).

**Chia theo nền tảng** (feature / ngày). Android là module `:core:*`, `:app:*`, `:filmode:*`, `:studio:*`, `:filcam:*` và `build-logic`. iOS là `FilmodeCoreKit…`, `FilmodeiOS/…`, `StudioiOS/…`, `FilCamiOS/…` cộng ba dòng QA iOS (FMD-E13-08, FMS-E12-14, FCM-E10-13). Nhóm còn lại là `(web)`, `(backend)`, `(tools)`, `(ci)`, `(qa)`.

| Phần | Android | iOS | Web, backend, công cụ, QA | Tổng |
|---|---|---|---|---|
| Lõi (`FLC`) | 62 / 125 | 10 / 28,5 | 13 / 34 | 85 / 187,5 |
| Filmode (`FMD`) | 83 / 137,5 | 15 / 37 | 25 / 45 | 123 / 219,5 |
| Filmode Studio (`FMS`) | 72 / 153 | 20 / 51 | 14 / 42 | 106 / 246 |
| FilCam (`FCM`) | 83 / 160 | 13 / 37 | 11 / 24 | 107 / 221 |
| **Tổng** | **300 / 575,5** | **58 / 153,5** | **63 / 145** | **421 / 874** |

Nội dung (dựng look, LUT, khung, ảnh mẫu, bài hướng dẫn) không tính ở trên: khoảng 59 ngày cho Filmode, 54 ngày cho Studio và 37,5 ngày cho FilCam, do người dựng look và nội dung làm.

## Lịch và nhân sự cả họ app

Lịch này gộp lộ trình của [lõi](filmode-core.md#8-lộ-trình), [Filmode](01-filmode/epics-features.md#lộ-trình-sprint), [Studio](02-filmode-studio/epics-features.md#lộ-trình-sprint) và [FilCam](03-filcam/epics-features.md#lộ-trình-sprint). Mỗi kế hoạch app tự tính người cho mình; cộng lại thì thấy chỗ chồng nhau. Tên dev dưới đây dùng chung cho mọi file.

### Người

| Người | Vai | Vào từ |
|---|---|---|
| Dev A (Android) | Pipeline GPU, camera, pass chữ ký, ảnh động; sau Filmode làm lõi V1 cho Studio và FilCam rồi sang FilCam (camera, video, Log) | 5/10/2026 |
| Dev B (Android) | Thư viện, billing, paywall, đo lường, CI của lõi; sau Filmode sang Studio (công thức, nhập, match, paywall) | 5/10/2026 |
| Dev C (Android) | Tính năng Filmode (máy, cuộn, nhập ảnh, board, ASO, đồng bộ iOS–Android); sau ra mắt làm Filmode V1 | 5/10/2026 |
| Dev hợp đồng (Android) | Pass chữ ký và kho máy của Filmode, S2–S5 | 9/11/2026 – 1/1/2027 |
| Dev D (Android, **tuyển mới**) | Studio MVP (trình sửa, preview, xuất), làm FLC-E01-27, -28; từ 5/4/2027 sang FilCam (công cụ đo, thư viện LUT, chỉnh màu, kiếm tiền) | 4/1/2027 |
| Dev iOS | 50% trong giai đoạn 0–1 (Filmode iOS trên code cũ, bắt đầu lõi iOS); 100% từ T1/2027 (lõi iOS, Filmode iOS chuyển lõi, Studio iOS) | 5/10/2026 |
| Dev web/backend (**tuyển mới**, fullstack) | Backend chung, WebGL2, xác minh pass, web camera sự kiện, trang web của Studio và FilCam; 100% tới 2/4/2027, 50% từ Q2/2027 | 11/1/2027 |
| Tester thiết bị | 50% từ S3 của Filmode; 100% khi FilCam chạy thử 2 tuần trên ma trận (28/6 – 23/7/2027) | 23/11/2026 |

Người dựng look và nội dung, người hỗ trợ khách trực Zalo trong ngày pilot sự kiện tính riêng, không phải dev.

### Theo quý

| Quý | Filmode (FMD) | Studio (FMS) | FilCam (FCM) | Lõi (FLC) | Android | iOS | Web/backend, QA |
|---|---|---|---|---|---|---|---|
| Q4/2026 | Giai đoạn 0 (5–23/10) trên code cũ; bản dựng lại S1–S5 (26/10 – 1/1); iOS trên code cũ nộp review trước 8/1 | — | — | Giai đoạn 0 (11 ngày); MVP và Có sẵn (94 ngày) | A, B, C, hợp đồng | iOS 50%: Filmode iOS code cũ, FLC-E07-05 | Tester 50% từ S3 |
| Q1/2027 | S6 và closed test (4–15/1); ra mắt 18/1; MVP.1 (22/2); V1-a sự kiện 15/2 – 26/3; iOS chuyển lõi 1/3 – 2/4 | MVP S1–S6 (4/1 – 26/3), rollout từ 29/3 | — | V1 cho Studio (20,5 ngày theo hạn từng sprint), sự kiện (7,5, trước 15/2), iOS (25), FilCam (15,5, trước 19/4) | A (S6, rồi lõi V1); B (S6, rồi Studio); C (Filmode); D (Studio) | iOS 100%: lõi iOS, Filmode iOS V1-iOS-a | Web/backend 100% từ 11/1: FLC-E08-02, -03-10, -01-23, web và backend sự kiện; tester 50% |
| Q2/2027 | V1-b (pilot 3–5 đám cưới T3–T4, tới 7/5); V1-c (video, 5 máy, extensions) tới 2/7 | V1 Android S7–S12 (5/4 – 25/6); iOS I1–I6, nộp 18/6 | MVP S1–S7 (5/4 – 9/7) | FLC-E08-03, FLC-E08-04, FLC-E01-22, FLC-E01-32 | A, D (FilCam); B (Studio V1); C (Filmode V1) | Studio iOS, FLC-E01-32 | Web/backend 50%: web Filmode V1-c, Studio V1, lõi; tester 50%, 100% từ 28/6 |
| Q3/2027 | Gói Trung thu, mùa cưới (trước 15/8); iOS V1-iOS-b (T7–T8); V2 nếu đạt mốc "đẩy mạnh" | V2 nếu đạt mốc (quyết định khoảng cuối T5); không thì bảo trì | S8 chạy thử 2 tuần; rollout 26/7 – 6/8; V1 S9–S12 | FLC-E01-31 (trước 23/8), FLC-E02-07, FLC-E02-06 | A, D (FilCam V1); B (Studio V2 hoặc bảo trì); C (Filmode, FLC-E02-06; còn dư thì hỗ trợ FilCam) | Filmode iOS V1-iOS-b, FLC-E02-07; Studio iOS V2 nếu đạt | Web/backend 50%: Studio V2 nếu đạt, trang web FilCam; tester 100% tới 23/7 rồi 50% |
| Q4/2027 | Bảo trì, gói Noel (V2) nếu đạt mốc | V2 (cộng đồng, chợ creator) nếu đạt mốc | V1 S13 (tới 15/10); mốc 12 tuần cuối T10 | — | A, D (FilCam V1, V2 nếu đạt); B (Studio V2); C (Filmode) | Spike FilCam iOS nếu đạt mốc | Web/backend 50% |
| Q1/2028 | — | V3 (gói creator mang thương hiệu) khi có creator bán được hàng | iOS (V2, 37 ngày) ⚠ | — | Theo mốc đo | FilCam iOS ⚠ | — |

### Tải so với sức

Sức danh nghĩa là 5 ngày mỗi tuần mỗi người, trừ ngày lễ và khoảng 5 ngày nghỉ Tết Nguyên đán (4–10/2/2027). Bảng 13 khuyên dành 20–25% công sức cho kiểm thử thiết bị, sửa lỗi và review, nên tải trên khoảng 75–80% là không còn chỗ trống.

| Đợt | Việc (ngày công, từ CSV và lộ trình sprint) | Người | Sức danh nghĩa | Tải |
|---|---|---|---|---|
| Giai đoạn 1, 26/10/2026 – 15/1/2027 | Lõi 94 + Filmode Android và công cụ 92,5 = **186,5** | A, B, C + hợp đồng 8 tuần | 177 + 40 = 217 | **86%**; không có dev hợp đồng thì 105% |
| Q1/2027 (D từ 4/1; A, B, C từ 18/1) | Studio MVP 68 + lõi dev Studio làm 7,5 (FLC-E01-27, -28, FLC-E02-08, -11); lõi V1 do A làm 23; Filmode MVP.1 và phần Android của V1-a khoảng 20,5 | A, B, C, D | 60 + 3 × 50 = 210 | 57%; riêng cặp Studio (B, D) 69% |
| Q1/2027, web/backend | Lõi 11,5 (FLC-E08-02, -03-10, -01-23) + sự kiện Filmode 22 | Dev web/backend từ 11/1 | 55 | 61% |
| Q1/2027, iOS | Lõi iOS 21 + Filmode iOS V1-iOS-a 16 | Dev iOS | 60 | 62% |
| Q2/2027 | FilCam S1–S7 khoảng 91 (phần Android của 100); Studio V1 50,5; Filmode V1-b, V1-c 34 + FLC-E01-22 2,5 | A, D; B; C | 4 × 62 = 248 | **72%**; FilCam 73%, Studio 81%, Filmode 59% |
| Q2/2027, iOS | Studio iOS 37 + FLC-E01-32 2 | Dev iOS | 62 | 63% |
| Q3/2027 | FilCam S8 và V1 S9–S12 62; Filmode gói mùa và lõi 6; nếu đạt mốc: Studio V2 Android 36,5, Filmode V2 7 | A, D; B; C | 4 × 63 = 252 | 27–44%: phần dư dùng cho sửa lỗi sau ra mắt FilCam và Studio, hoặc giảm người |

### Chỗ không vừa với số người các kế hoạch app nêu

Mỗi kế hoạch app đúng khi đọc riêng, nhưng cộng lại có năm chỗ không làm được nếu giữ đúng số người đã nêu:

1. **Giai đoạn 1 cần 186,5 ngày, 3 dev Android chỉ có 177.** Cần dev hợp đồng 8 tuần (khuyến nghị) hoặc áp cut-line của lõi (6,5 ngày) và của Filmode (10 ngày), còn 170 ngày và không còn chỗ sửa lỗi closed test.
2. **4–15/1/2027: Studio S1 cần 2 dev Android trong khi Filmode S6 giữ cả A, B, C.** Studio S1 chạy với một dev (D, phải tuyển xong trước 4/1); FMS-E13-01 và FMS-E02-02 dời sang S2 khi B vào.
3. **Phần V1 của lõi (khoảng 68,5 ngày phải xong trong T1–T4/2027) không nằm trong kế hoạch app nào.** Giao cho A (Android), dev web/backend, dev iOS; B và D làm phần lõi gắn với Studio. Hạn từng mục ở [lõi mục 8](filmode-core.md#8-lộ-trình).
4. **Q2/2027 cần 4 dev Android** (FilCam 2, Studio V1 1, Filmode V1 1), không phải 3. Vì vậy dev D được giữ lại sau Studio MVP và sang FilCam.
5. **Q2/2027 cần 66 ngày iOS** (Studio iOS 37 + Filmode iOS V1 29) cho một dev iOS có khoảng 62 ngày. Lịch ở đây tách Filmode iOS V1: phần chuyển lõi 16 ngày làm ngay sau lõi iOS (1/3 – 2/4/2027), phần còn lại 13 ngày (pass Metal, Live Photo, DV/VHS, chủ tiệc iOS) dời sang T7–T8/2027, để Studio iOS nộp đúng 18/6.

Ngoài ra, kế hoạch Filmode chỉ tính "1 dev web/backend khoảng 8 tuần" cho sự kiện (29 ngày web và backend ở V1). Cộng phần web và backend `V1` của lõi (16 ngày), của Studio (8 ngày ở V1, 23 ngày ở V2) và trang web của FilCam (3,5 ngày), cần một dev fullstack toàn thời gian trong Q1/2027 và nửa thời gian từ Q2/2027.

**Khuyến nghị:** 4 dev Android (A, B, C và dev D tuyển từ 4/1/2027) + dev Android hợp đồng 8 tuần (S2–S5) + 1 dev iOS (50% trong giai đoạn 0–1, 100% từ T1/2027) + 1 dev web/backend (từ 11/1/2027) + tester thiết bị 50% (100% khi FilCam chạy thử).

**Nếu không tuyển được dev D** (chỉ A, B, C trong 2027): Studio bắt đầu 18/1 với A và B, ra mắt khoảng giữa T4/2027 (hoặc giữ cuối T3 bằng cut-line (b) của Studio). C làm Filmode sau ra mắt, phần Android của sự kiện và phần lõi V1 cho Studio (FLC-E01-27, -28, FLC-E02-11, bộ nhập, deep link, Ultra HDR). A làm phần lõi cho FilCam sau khi Studio ra mắt; FilCam bắt đầu khoảng 10/5/2027 với A và C (C rời Filmode sau pilot) và ra mắt khoảng giữa T9/2027. Filmode V1-c (video, 5 máy V1, extensions, photobooth mới) dời sang Q4/2027; B ở lại Studio V1. Thứ tự vẫn là sự kiện và pilot của Filmode, rồi Studio, rồi FilCam.

**Nếu chỉ có 2 dev Android trong giai đoạn 1:** không kịp bản dựng lại trước Tết. Làm giai đoạn 0, gói Tết, đổi tên, giá VN và 2–3 máy chữ ký (Mochi 32, Flash Drift, Paper 27) trên code đang chạy; phát hành bản dựng lại trên lõi vào T3/2027; pilot sự kiện T4–T5/2027; Studio Android lùi sang Q2/2027 (ra mắt khoảng T6); FilCam lùi sang Q4/2027.

### Chỗ lệch so với Bảng 13

| Mục | Bảng 13 | Kế hoạch | Lý do |
|---|---|---|---|
| Chế độ sự kiện của Filmode (A7) | Giai đoạn 1 (T10/2026 – T1/2027): "chế độ sự kiện chạy trên web" | `V1`: lát cắt sự kiện 15/2 – 26/3/2027, pilot 3–5 đám cưới hoặc tiệc thật trong T3–T4/2027 (FMD-E07-17); phần còn lại chỉ làm khi pilot đạt ngưỡng | (1) Giai đoạn 1 đã vượt sức 3 dev Android chỉ với bản dựng lại và gói Tết; (2) phần lõi sự kiện cần (WebGL2 FLC-E01-23, xác minh pass và sự kiện thử FLC-E03-10, backend FLC-E08-02) là `V1`, hạn 15/2/2027; (3) báo cáo ghi chưa có dữ liệu nhu cầu app sự kiện ở Việt Nam, nên phải thử nhỏ trước khi đầu tư lớn; (4) mùa cưới sau Tết (T3–T4) là lúc chạy pilot. [README Filmode mục 4.7](01-filmode/README.md#47-chế-độ-sự-kiện-a7) ghi cùng lý do |
| Filmode iOS chuyển lõi | Không nêu | T3–T4/2027 (chuyển lõi), T7–T8/2027 (phần V1 còn lại) | Một dev iOS không làm kịp cả Studio iOS và Filmode iOS V1 trong Q2 |
| FilCam iOS | "Bản iOS 6–8 và 5–8 tuần-người" trong giai đoạn 3 | `V2`, khoảng Q1/2028 ⚠, chỉ khi FilCam Android đạt mốc "đẩy mạnh" | Báo cáo xếp Apple Log ở V2; iOS đã có Blackmagic miễn phí |

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

Target iOS của lõi nằm trong `FilmodeCoreKit` (ghi `FilmodeCoreKit/<Target>`); code iOS của app ghi `FilmodeiOS/<Area>`, `StudioiOS/<Area>`, `FilCamiOS/<Area>`.

Ngoài app: `(web)` có trang `filmode.app/r` và `/l` cùng renderer WebGL2 (dùng cho web camera sự kiện của FMD); `(backend)` có rules, functions, hosting (Firebase đề xuất ⚠); `(tools)` có `look-cli` và script đẩy giá.

## Việc cần xác minh sớm nhất

Danh sách đầy đủ ở [filmode-core.md mục 10](filmode-core.md#10-rủi-ro-spike-và-việc-cần-xác-minh). Các mục ảnh hưởng tới code MVP:

- Code đang chạy của Filmode Vibe và FilCam: ngôn ngữ, UI, camera stack, minSdk thật, backend của Cloud Boards.
- targetSdk bắt buộc của Play và bản Play Billing Library bắt buộc lúc phát hành.
- Phân loại analytics và crash trong Data safety, App Privacy.
- Yêu cầu xóa tài khoản của Play, vì Filmode Vibe đã có đăng nhập Google.
- Dùng chung khóa ký cho ba app (cần cho thư viện look dùng chung) và hành vi App Links khi nhiều app cùng nhận một link.
- Package và bundle ID của Filmode Studio.
- Flash màn hình của CameraX (FLC-E01-16) và hai `CameraEffect` theo target cho FilCam (FLC-E01-29).

## Quyết định cần chủ sản phẩm chốt

- Tuyển dev Android thứ tư (dev D) từ 4/1/2027 và một dev web/backend từ 11/1/2027; thuê dev Android hợp đồng 8 tuần cho S2–S5 của Filmode. Không có thì chọn một phương án ở [Chỗ không vừa](#chỗ-không-vừa-với-số-người-các-kế-hoạch-app-nêu).
- Chấp nhận dời chế độ sự kiện của Filmode sang V1 có pilot (lệch Bảng 13).
- Package `app.filmode.studio` và bundle iOS của Studio ⚠; dùng chung khóa ký cho ba app Android.
- Gói Pro chung nhiều app qua tài khoản tùy chọn: chỉ xét ở V2 ⚠.
- FilCam 1.0.21 cũng có báo lỗi "không lưu được ảnh" (8/9/2026) và Bảng 13 nói giai đoạn 0 sửa "cả hai app", nhưng backlog FilCam chưa có dòng sửa trên code cũ. Đề xuất áp cách lưu của FLC-E06-02 lên FilCam 1.0.21 trong giai đoạn 0 (khoảng 1 ngày, dev A) ⚠.
- Nhãn hiệu: "film simulation" trong từ khóa ASO của Studio; tên tiếng Anh "Classic Negative", "Nostalgic Negative" của hai tông nền Studio; tên 18 máy của Filmode ⚠.
- iOS tối thiểu của `FilmodeCoreKit` (đề xuất iOS 17+) so với iOS 13.0+ của Filmode iOS hiện tại.
