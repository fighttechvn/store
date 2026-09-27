# Lõi dùng chung Filmode Core (mã `FLC`)

Filmode Core là bộ module Android (Gradle) và Swift package iOS (`FilmodeCoreKit`) dùng chung cho **Filmode** (`FMD`), **Filmode Studio** (`FMS`) và **FilCam** (`FCM`). Lõi được xây cùng Filmode ở giai đoạn 1 của lộ trình (T10/2026–T1/2027). Studio và FilCam dùng lại lõi và chỉ bổ sung khi cần.

Đọc [README](README.md) trước để nắm quy ước ID, ưu tiên, gói và ước tính. Nguồn: [báo cáo](../../reports/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u.md), mục "Ba app nên xây trên một lõi look chung" (Bảng 9 là 6 epic C1–C6 của lõi) và phần rủi ro sau đó. Chi tiết kỹ thuật lấy từ [ghi chú khả thi kỹ thuật](../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/tech_feasibility_opportunities.md), [hồ sơ Filmode/FilCam](../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/film_camera_apps.md), [ghi chú kiếm tiền](../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/monetization_paid_features.md) và [ghi chú cảm nhận người dùng](../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/user_sentiment_pain_points.md).

Bản CSV: [filmode-core-backlog.csv](filmode-core-backlog.csv).

## 1. Mục đích và phạm vi

Lõi giải bốn việc mà cả ba app đều cần:

1. **Một look đi được khắp nơi.** Cùng một file look dùng cho chụp ảnh (Filmode), sửa ảnh (Studio), quay video (FilCam), trên Android, iOS và web. Đây là điểm nối ba app trong báo cáo và là vòng lặp chia sẻ "công thức màu" qua QR.
2. **Ảnh xuất giống preview.** Preview, ảnh tĩnh và video dùng chung một mã shader và một seed grain. Lời chê "lúc chưa chụp nhìn đẹp lắm mà chụp thì xấu" của Kapi là lỗi phải tránh.
3. **Mua được, giữ được.** Không cần tài khoản, khôi phục qua store, không bao giờ chuyển thứ miễn phí sang Pro, giữ quyền của người đã mua. Paywall hồi tố là nguyên nhân số một của đánh giá 1★ trong ngách.
4. **Qua được store.** Photo Picker thay cho `READ_MEDIA_*`, paywall đúng luật thuê bao của Play, tên look không dùng nhãn hiệu, không đóng gói LUT CC BY-SA.

**Code đang có.** Filmode Vibe 1.5.9, FilCam 1.0.21 và Filmode iOS 1.4.4 đã có LUT 64³ trên GPU, nhập .cube và preset, billing, đăng nhập Google cho Cloud Boards, tách nền người và dò khả năng máy. Các phần đó mang ưu tiên `Có sẵn`: gom vào module rồi kiểm lại. Ghi chú nghiên cứu không nói code hiện tại viết bằng gì (Kotlin và Compose hay khác; preview dùng CameraX hay Camera2) ⚠. Ước tính `Có sẵn` giả định code là Kotlin và tách ra module được; phải kiểm lại ở tuần đầu.

### 1.1 Ranh giới lõi và app

| Thuộc lõi (`FLC`) | Thuộc app |
|---|---|
| Định dạng look, bộ nhập và xuất LUT, pipeline GPU, các pass chung (grain, halation, bloom, vignette, CA, khung, date stamp) | Hiệu ứng chữ ký VHS, CCD, kira/star, rain, frost, leak động (FMD), cắm vào lõi qua `EffectPass` |
| Wrapper CameraX, dò khả năng máy, xoay đúng hướng | UI kính ngắm, các dòng máy, ảnh động Motion Photo/Live Photo, cuộn phim (FMD); điều khiển tay, phơi sáng dài, bracketing, ghi RAW DNG, pseudo-Log, quay video (FCM) |
| Thuật toán Match v1 (ảnh mẫu → LUT) | UI match và gói bán (FMS, FMD), Match v2 bằng AI (FMS) |
| Thư viện look, deep link, đồng bộ, thư viện dùng chung ba app | Board, sự kiện, web camera (FMD); công thức dạng chữ, cộng đồng, chợ creator (FMS); bộ LUT kỹ thuật và scopes (FCM) |
| Billing, `Entitlements`, paywall, bảng giá theo vùng | Danh sách SKU, nội dung từng gói, chỗ gọi paywall |
| Hạ tầng ngôn ngữ, `NameGuard`, lint, fastlane | Chuỗi, metadata và ảnh chụp màn hình riêng của app |

Khi một app cần thứ đang nằm ở app khác (ví dụ FilCam cần Match của Studio), thứ đó chuyển vào lõi. Match v1, tách nền người và Ultra HDR đã được chuyển vào lõi vì lý do này (mục 9).

Ngược lại, thứ chỉ một app cần thì ở lại app, kể cả khi app đó ghi trong mục "Điều chỉnh lõi":
- Trình ghi Motion Photo và bộ đệm vòng mã hóa từ đầu ra GPU thuộc FMD (`:filmode:motion`, FMD-E03-01..03). Hiện chỉ Filmode có ảnh động; chuyển vào `:core:media` khi app thứ hai cần.
- Phần dò năng lực riêng cho video (chế độ `TONEMAP`, dải AE fps theo kích thước, encoder HEVC/Main10 và bitrate tối đa, cấu hình hai nhánh) thuộc FCM (FCM-E07-01), dựng trên FLC-E05-02. Chuyển vào lõi khi Filmode cần quay video dài.
- RAW của Studio (`:studio:raw`) ở lại app. Chuyển vào `:core:media` nếu FilCam cần mở DNG trong trình chỉnh clip.

Mục 11 liệt kê mọi yêu cầu của ba app và FLC ID đang xử lý từng yêu cầu.

## 2. Nguyên tắc

| Nguyên tắc | Cách làm |
|---|---|
| Một shader, một kết quả | Preview, ảnh tĩnh, video và web dùng cùng thứ tự pass, cùng hàm hash cho grain. Golden test (FLC-E07-03) canh lệch giữa preview và ảnh xuất. |
| Offline trước | Mọi tính năng miễn phí và mọi quyền đã mua chạy khi không có mạng. Mạng chỉ dùng cho board, sự kiện, đồng bộ và link look. |
| Không tài khoản | Đăng nhập là tùy chọn. Không dùng OTP số điện thoại vì người dùng Việt gắn nó với spam. |
| Không thu hồi | Tính năng miễn phí nằm trong `free-tier.json`; CI chặn mọi thay đổi làm hẹp gói miễn phí. Bảng map SKU cũ không bao giờ bị xóa dòng. |
| Hỏi năng lực máy trước | Mọi tính năng phụ thuộc phần cứng hỏi `CameraCapabilities` và `DeviceProfile` trước. Máy không làm được thì ẩn tính năng, không hiện rồi báo lỗi. |
| Quyền tối thiểu | Photo Picker, không `READ_MEDIA_*`, không `AD_ID`, micro chỉ khi quay có tiếng. |
| Lõi không biết app | Module `:core:*` không import code app. App cắm vào lõi qua interface: `EffectPass`, `DateStampFormatter`, cấu hình paywall, bảng SKU, danh sách look đóng gói. |
| GPU đúng chỗ | Đường camera và encoder dùng OpenGL ES 3.x (CameraX `SurfaceProcessor`, Media3 `GlEffect`). AGSL chỉ cho hiệu ứng UI, cần API 33+ và luôn có dự phòng. |
| Lỗi nói rõ | Lỗi hiện cho người dùng nói chuyện gì xảy ra và cách sửa. Log không chứa ảnh, tên file hay tên người dùng. |

## 3. Bản đồ module

### 3.1 Cấu trúc repo đề xuất

```
filmode/                          # một monorepo cho cả ba app
├── android/
│   ├── build-logic/              # convention plugin, version catalog
│   ├── core/
│   │   ├── look/                 # :core:look      định dạng look, .flook, codec QR, NameGuard
│   │   ├── lut-io/               # :core:lut-io    nhập/xuất LUT và preset, pipeline CPU, Match v1
│   │   ├── gpu/                  # :core:gpu       GLES 3, đồ thị pass, render ảnh tĩnh, LookGlEffect
│   │   ├── camera/               # :core:camera    CameraX 1.6, CameraEffect, dò khả năng, quyền
│   │   ├── device/               # :core:device    tier hiệu năng, quirk, nhiệt
│   │   ├── segment/              # :core:segment   tách nền người, mask tông da
│   │   ├── media/                # :core:media     Photo Picker, MediaStore, EXIF, Ultra HDR
│   │   ├── library/              # :core:library   thư viện look, thumbnail, deep link, provider
│   │   ├── billing/              # :core:billing   Play Billing, Entitlements, map SKU cũ
│   │   ├── paywall/              # :core:paywall   paywall Compose, thử giá A/B
│   │   ├── account/              # :core:account   đăng nhập tùy chọn, xóa tài khoản
│   │   ├── sync/                 # :core:sync      đồng bộ thư viện look
│   │   ├── l10n/                 # :core:l10n      chuỗi 7 ngôn ngữ, định dạng theo locale
│   │   ├── analytics/            # :core:analytics sự kiện, crash, hiệu năng, cài đặt quyền riêng tư
│   │   ├── config/               # :core:config    remote config, cờ tính năng, A/B
│   │   ├── ui/                   # :core:ui        design system, bộ chọn look
│   │   └── testing/              # :core:testing   golden image, fake billing (chỉ cho test)
│   ├── app-filmode/  app-studio/  app-filcam/     # :app:* và module tính năng riêng của từng app
│   └── tools/look-cli/  tools/price-sync/
├── ios/
│   ├── Packages/FilmodeCoreKit/  # LookFormat, LUTIO, LookRender, LookLibrary, StoreCore, AccountSync, MediaKit, Telemetry
│   └── Apps/Filmode/  Apps/Studio/  (Apps/FilCam/ sau)   # target app: FilmodeiOS/<Area>, StudioiOS/<Area>, FilCamiOS/<Area>
├── web/                          # trang /r và /l, renderer WebGL2, web camera sự kiện của FMD
├── backend/                      # rules, functions, hosting (Firebase ⚠)
└── spec/look/                    # đặc tả .flook, bảng khóa ngắn, fixture chung Kotlin/Swift/JS
```

Vì sao một monorepo: fixture của định dạng look phải dùng chung cho Kotlin, Swift và JavaScript; bảng map SKU và `free-tier.json` phải được CI của cả ba app đọc. Nếu đội muốn giữ repo riêng cho từng app thì `spec/` phải là một repo con có version ⚠.

### 3.2 Module Android

| Module | Chức năng | Phụ thuộc lõi | FMD | FMS | FCM |
|---|---|---|---|---|---|
| `:core:look` | Model `look.json`, container `.flook`, luật phiên bản, codec QR/link, `NameGuard` | — | ✓ | ✓ | ✓ |
| `:core:lut-io` | Nhập .cube/HALD/.3dl/.xmp/.dng, xuất .cube/HALD, pipeline CPU tham chiếu, Match v1 | `:core:look` | ✓ | ✓ | ✓ |
| `:core:gpu` | Renderer GLES 3, texture 3D, trilinear/tetrahedral, đồ thị pass, render ảnh tĩnh theo tile, `LookGlEffect` cho Media3 | `:core:look`, `:core:device` | ✓ | ✓ | ✓ |
| `:core:camera` | Wrapper CameraX 1.6 + `CameraEffect` (một effect, hoặc hai effect theo target cho FCM), Camera2Interop và `Camera2CameraControl`, flash màn hình, `CameraCapabilities`, luồng xin quyền | `:core:gpu`, `:core:device` | ✓ | — | ✓ |
| `:core:device` | Tier hiệu năng A/B/C, quirk theo model, theo dõi nhiệt, callback nhiệt `CRITICAL` khi quay | `:core:config` | ✓ | ✓ | ✓ |
| `:core:segment` | Tách nền người (đang chạy trong photobooth), mask tông da | `:core:gpu`, `:core:device` | ✓ | ✓ | — |
| `:core:media` | Photo Picker, lưu MediaStore (cả file sidecar không phải media), EXIF, xóa GPS, Ultra HDR | — | ✓ | ✓ | ✓ |
| `:core:library` | Thư viện look (Room), thumbnail, chuyển dữ liệu bản cũ, deep link, provider dùng chung, 16 tông nền dùng chung | `:core:look`, `:core:gpu` | ✓ | ✓ | ✓ |
| `:core:billing` | Play Billing, `Entitlements`, map SKU cũ, `free-tier.json` | `:core:config` | ✓ | ✓ | ✓ |
| `:core:paywall` | Paywall Compose, "thử trước, trả khi lưu", thử giá A/B | `:core:billing`, `:core:ui`, `:core:l10n`, `:core:analytics` | ✓ | ✓ | ✓ |
| `:core:account` | Đăng nhập Google tùy chọn, xóa tài khoản | — | ✓ | ✓ | ✓ |
| `:core:sync` | Đồng bộ thư viện look (V1) | `:core:account`, `:core:library` | ✓ | ✓ | ✓ |
| `:core:l10n` | Chuỗi 7 ngôn ngữ, per-app language, định dạng tiền/số/ngày | — | ✓ | ✓ | ✓ |
| `:core:analytics` | Facade sự kiện, crash, trace hiệu năng, cài đặt quyền riêng tư | `:core:config` | ✓ | ✓ | ✓ |
| `:core:config` | Remote config, cờ tính năng, phân nhóm A/B, kill switch | — | ✓ | ✓ | ✓ |
| `:core:ui` | Design system Compose, bộ chọn look, thanh cường độ, so sánh trước/sau | `:core:l10n` | ✓ | ✓ | ✓ |
| `:core:testing` | Golden image, fake billing, fixture (chỉ `testImplementation`) | tất cả | ✓ | ✓ | ✓ |

### 3.3 Target iOS trong `FilmodeCoreKit`

Cột Module của backlog ghi target iOS của lõi dạng `FilmodeCoreKit/<Target>`. Code iOS riêng của app ghi dạng `FilmodeiOS/<Area>`, `StudioiOS/<Area>` và `FilCamiOS/<Area>` (tên tạm ⚠, chốt khi dựng project). Toàn bộ phần iOS của lõi là `V1`: Filmode iOS giữ code đang chạy tới khi chuyển sang lõi (T3–T4/2027), cùng quý với bản iOS của Studio (Q2/2027).

| Target | Tương ứng Android | Chức năng | Feature |
|---|---|---|---|
| `LookFormat` | `:core:look` | Model look, `.flook`, codec QR | FLC-E01-24 |
| `LUTIO` | `:core:lut-io` | Nhập và xuất LUT, preset, Match v1 | FLC-E01-25, FLC-E01-32 |
| `LookRender` | `:core:gpu` | Renderer Metal, `CIColorCubeWithColorSpace` cho preview | FLC-E01-26 |
| `LookLibrary` | `:core:library` | Thư viện look, App Group, Universal Links | FLC-E02-10 |
| `AccountSync` | `:core:account`, `:core:sync` | Sign in with Apple/Google, đồng bộ | FLC-E02-07 |
| `StoreCore` | `:core:billing`, `:core:paywall` | StoreKit 2, `Entitlements`, paywall SwiftUI | FLC-E03-09 |
| `MediaKit` | `:core:media` | PhotosPicker, lưu add-only, EXIF | FLC-E06-07 |
| `Telemetry` | `:core:analytics`, `:core:config` | Analytics, crash, remote config | FLC-E05-08 |

### 3.4 Module giả

| Ký hiệu | Ý nghĩa |
|---|---|
| `build-logic` | Convention plugin Gradle, version catalog |
| `(ci)` | Workflow CI, fastlane |
| `(tools)` | CLI chạy trên máy dev hoặc CI: `look-cli`, script đẩy giá, lint |
| `(qa)` | Việc kiểm thử thủ công có quy trình, spike đo trên máy thật |
| `(backend)` | Rules, functions, hosting phía server |
| `(web)` | Trang web tĩnh và renderer WebGL2 |

### 3.5 Backend

Ghi chú nghiên cứu chỉ biết Filmode Vibe có "Cloud Boards" đăng nhập bằng Google, chia sẻ bằng mã và xem được trên web app; không biết backend là gì ⚠. FLC-E08-01 khảo sát trước. Đề xuất tối thiểu nếu chưa có gì ràng buộc: **Firebase** (Auth cho Google và Apple, Firestore cho metadata, Cloud Storage cho ảnh board/sự kiện và file `.flook`, Functions cho xác minh mua, `NameGuard` phía server và xóa tài khoản, Hosting cho `filmode.app/r`, `/l`, `assetlinks.json`, `apple-app-site-association`). Lý do: đăng nhập Google và web app hiện có gợi ý Firebase ⚠; một nhà cung cấp cho cả analytics, crash và remote config thì chỉ phải khai một lần trong Data safety. Nếu Cloud Boards đang chạy trên Supabase hay server riêng thì giữ nguyên nền đó và chỉ thay tên dịch vụ trong FLC-E08-02.

## 4. Quy tắc lõi phải giữ

### 4.1 Lập trường quyền riêng tư

**Quyết định:** không hứa "Không thu thập dữ liệu". Lõi hứa bốn điều kiểm chứng được:

1. Không quảng cáo, không SDK quảng cáo, không quyền `AD_ID`, không IDFA và không hộp ATT.
2. Ảnh và video được xử lý trên máy. Ảnh chỉ rời máy khi người dùng tự đưa lên board, sự kiện, đồng bộ hoặc link look công khai.
3. Không bắt tài khoản. Mọi tính năng miễn phí và mọi quyền đã mua dùng được khi không đăng nhập.
4. Chỉ thu dữ liệu ẩn danh để sửa lỗi và đo phễu: sự kiện sử dụng (FLC-E05-07), crash và chẩn đoán (FLC-E05-06). Người dùng tắt được trong Cài đặt (FLC-E06-06).

Vì sao không nhắm "Data not collected": phễu cài → chụp/sửa → lưu → paywall → mua là mốc đo của Bảng 13, và thử A/B giá (C3.3) cần số này. FilCam hiện đã khai trong Data safety là có thu (tùy chọn) Device or other IDs, App interactions, Crash logs, Diagnostics; Filmode Vibe khai thêm tên, email, ảnh cho board. Lõi giữ đúng phạm vi đó, không mở rộng.

| Dữ liệu | Khi nào | Khai báo |
|---|---|---|
| Sự kiện sử dụng, crash, chẩn đoán, ID cài đặt của SDK | Mặc định bật, tắt được; ở EEA/UK hỏi đồng ý trước ⚠ | Data safety: thu thập, không chia sẻ, mã hóa khi truyền ⚠ phân loại của Firebase. App Privacy: Usage Data, Diagnostics, không dùng để theo dõi ⚠ |
| Tên, email, ID tài khoản | Chỉ khi người dùng đăng nhập | Thu thập, tùy chọn, xóa được trong app và qua web |
| Ảnh, look | Chỉ ảnh và look người dùng tự đưa lên board, sự kiện, đồng bộ, link | Thu thập, tùy chọn, xóa được |
| Không bao giờ gửi | Ảnh trong máy, tên file, tên look người dùng đặt, vị trí, danh bạ | — |

### 4.2 Ngân sách hiệu năng

"Máy tầm trung chuẩn" tạm chọn là Galaxy A35 và Redmi Note 13 ⚠; chốt sau spike FLC-E05-03.

| Chỉ số | Mục tiêu | Máy | Đo bằng |
|---|---|---|---|
| Preview 1080p với LUT + grain + halation | ≥ 30 fps | Máy tầm trung chuẩn | Trace FLC-E05-06 |
| Xử lý ảnh 12 MP với look đủ pass | p90 < 1,5 giây | Máy tầm trung chuẩn | Trace FLC-E05-06 |
| Ảnh 50 MP | Không OOM | Máy có cảm biến 50 MP | Test FLC-E01-15 |
| Mở app lạnh tới khung preview đầu | ≤ 1,5 giây ⚠ | Máy tầm trung chuẩn | Macrobenchmark |
| Thumbnail 60 look | Ảnh đầu < 300 ms, cả lưới < 2 giây | Máy tầm trung chuẩn | Test FLC-E02-02 |
| Lệch preview và ảnh xuất | ΔE trung bình < 2 | Mọi máy ma trận | Golden FLC-E07-03 |
| Tỉ lệ crash và ANR | Dưới ngưỡng "bad behavior" của Play Vitals (crash 1,09%, ANR 0,47% ⚠) | Toàn bộ người dùng | Play Console |
| Kích thước lõi trong APK | ≤ 15 MB, không tính look đóng gói ⚠ | — | Bundle size report |

Các ngân sách trên là mục tiêu thiết kế. Hiệu chỉnh sau spike FLC-E05-03.

### 4.3 Checklist paywall

Dùng cho FLC-E03-06 (Android), FLC-E03-09 (iOS) và mọi paywall của app. Đạt 100% mới được phát hành.

1. Số tiền thực bị trừ và chu kỳ là chữ lớn nhất, ví dụ "149.000 ₫/năm". Không lấy giá quy ra tháng làm chữ chính cho gói năm.
2. Giá lấy từ store (`ProductDetails`, `Product`), đúng tiền tệ địa phương, không ghi cứng.
3. Dùng thử ghi ngày cụ thể: "Miễn phí 7 ngày, sau đó 149.000 ₫/năm, tự gia hạn. Bị trừ tiền ngày 04/10/2026 nếu không hủy trước."
4. Cách hủy ghi bằng ngôn ngữ của người dùng (tối thiểu VI và EN) kèm link tới trang quản lý thuê bao của store.
5. Nút đóng hiện ngay khi mở paywall, không trì hoãn, vùng chạm ≥ 48 dp.
6. Các gói đặt cạnh nhau, không dùng toggle để giấu gói. Trên Android, gói trọn đời hiện rõ.
7. Không đặt tên SKU hay nút là "Free Trial" cho thuê bao tự gia hạn. Nút ghi "Dùng thử 7 ngày" kèm giá sau dùng thử.
8. Chỉ một màn, không dẫn người dùng qua nhiều bước để đăng ký.
9. Có "Khôi phục mua", "Quản lý gói", "Điều khoản", "Quyền riêng tư".
10. Liệt kê gói mở ra gì và nói rõ những gì vẫn miễn phí.
11. Không chặn người dùng bằng paywall trước khi họ thấy giá trị. Paywall lúc onboarding (nếu có) đóng được ngay.
12. Người đã có quyền không bao giờ thấy paywall cho quyền đó.

### 4.4 Ma trận thiết bị

Báo cáo yêu cầu dành 20–25% công sức cho kiểm thử thiết bị và chạy thử 2 tuần trên ma trận trước khi cam kết.

| Hãng (thị phần VN 2025) | Máy đề xuất | Vì sao |
|---|---|---|
| Samsung (26%) | Galaxy A15 hoặc A16, A35, A55 | Tầm thấp và tầm trung phổ biến nhất; máy tầm trung chuẩn |
| Samsung | Galaxy S24 hoặc S25 | Extensions, 10-bit, đủ ống kính, Samsung Log cho FCM |
| Xiaomi (17%) | Redmi Note 13, Redmi Note 14 | Tầm trung; máy tầm trung chuẩn thứ hai |
| OPPO (18%) | Một máy dòng A, một máy dòng Reno | Tầm thấp và tầm trung |
| Vivo | Một máy dòng Y hoặc V | Có trong ma trận của báo cáo |
| Google | Pixel 7a hoặc 8 | Máy tham chiếu của CameraX |
| Apple (cho phần iOS, V1) | iPhone 12, iPhone 15 hoặc 16, một máy Pro | Máy thấp nhất cần 30 fps; máy Pro cho Apple Log (FCM) |

Tối thiểu 8 máy Android cho mỗi bản phát hành của FMD và FMS (FLC-E05-05). Model cụ thể của dòng OPPO A và Vivo chốt khi mua máy ⚠.

FilCam cần tối thiểu 10 máy (FLC-E05-05, FCM-E07-06), vì quay 4K và HLG cần thêm máy tier A và B. Tier cuối cùng theo benchmark (FLC-E05-04); cột tier dưới là dự kiến ⚠. Bảng tier đầy đủ ở [README FilCam mục 5.8](03-filcam/README.md#58-tương-thích-thiết-bị-fcm-e07).

| Máy thêm cho FilCam | Tier dự kiến | Vì sao |
|---|---|---|
| Pixel 9 (cùng Pixel 8 nếu đã có Pixel 7a) | A | Máy tham chiếu CameraX cho HLG 10-bit, hai nhánh 4K |
| Galaxy S25 (cạnh S24) | A | Clip Samsung Log mẫu; 4K60 |
| Redmi Note 14 Pro 5G | B | 4K30 tầm trung khá |
| OPPO Reno12 hoặc Reno13 | B | Tầm trung khá của OPPO |
| Vivo V30 hoặc V40 | B | Tầm trung khá của Vivo |
| iPhone 15 Pro, Galaxy S24 Ultra | — | Chỉ để quay clip mẫu Apple Log, Samsung Log cho trình chỉnh màu |

## 5. Định dạng look `.flook` v1

Mọi app đọc và ghi đúng một định dạng. Đặc tả này là hợp đồng giữa ba app; đổi nó phải qua lõi.

### 5.1 File

| Mục | Quy định |
|---|---|
| Đuôi file | `.flook` |
| Container | ZIP (deflate). Không thư mục con nào ngoài `overlays/`; tên entry ASCII |
| MIME | `application/vnd.filmode.look+zip` (dùng nội bộ, chưa đăng ký IANA ⚠) |
| UTType iOS | `app.filmode.look`, conform `public.zip-archive` ⚠ app nào export type |
| `look.json` | Bắt buộc, UTF-8, ≤ 64 KB |
| `lut.cube` | Tùy chọn. LUT 3D 33³ hoặc 64³ dạng .cube text (Resolve/Adobe), có `LUT_3D_SIZE`, `DOMAIN_MIN`, `DOMAIN_MAX`. Kích thước khác được resample khi nhập |
| `thumb.jpg` | Tùy chọn, cạnh dài ≤ 512 px, ≤ 150 KB |
| `overlays/*.png` | Tùy chọn, tối đa 4 file (khung, leak, bụi), mỗi file ≤ 2 MB |
| Giới hạn | File nén ≤ 10 MB; giải nén ≤ 40 MB. Vượt thì từ chối (FLC-E01-02) |

### 5.2 `look.json`

| Trường | Kiểu và khoảng | Bắt buộc | Ghi chú |
|---|---|---|---|
| `format` | `"filmode.look"` | có | Nhận diện file |
| `formatVersion` | số nguyên, hiện là `1` | có | Xem 5.3 |
| `id` | UUID v4; look dựng sẵn dùng `fm:<slug>` | có | Không đổi qua các lần sửa |
| `revision` | số nguyên ≥ 1 | có | Tăng mỗi lần sửa nội dung |
| `name` | chuỗi 1–40 ký tự | có | Qua `NameGuard` khi chia sẻ |
| `names` | map locale → chuỗi | không | Tên bản địa của look dựng sẵn |
| `author` | `{name, handle, url}`; `handle`, `url` tùy chọn | không | Ghi tên tác giả |
| `remixOf` | `{id, revision, author}` | không | Ghi nguồn khi remix |
| `createdAt`, `updatedAt` | ISO 8601 UTC | không | |
| `origin` | `{type, importedFrom}`; `type` là `builtin`, `user`, `import`, `match` hoặc `studio`; `importedFrom` là `cube`, `hald`, `3dl`, `xmp`, `dng` hoặc `text` | có | `text`: công thức dán từ bài viết dạng chữ (FMS-E02-11, FLC-E01-27) |
| `license` | `owned`, `cc0`, `personal` hoặc `unknown` | không | Look đóng gói trong app phải là `owned` (FLC-E04-03). Look `personal` hoặc `unknown` có `lut.cube` không được tải lên công khai (FLC-E08-03) |
| `base` | `{lut: "lut.cube", size: 33 hoặc 64, space: "srgb"}`, hoặc `{ref: "fm:<slug>@<rev>"}`, hoặc bỏ trống | không | Bỏ trống là recipe thuần tham số. `space` mặc định `srgb` (đầu vào gamma sRGB/Rec.709). 16 tông nền dùng chung ba app là `fm:base/<slug>` (FLC-E02-11) |
| `inputTransform` | `{lut, size, from}`; `from` là `samsung-log`, `apple-log`, `fm-log` hoặc `hlg` | không | LUT kỹ thuật Log → Rec.709, chạy trước `base` (FLC-E01-20, V1). `fm-log` là đường cong FM-Log v1 của FilCam, đặc tả ở `spec/look/` (FCM-E03-02); `hlg` thêm ở FLC-E01-27 |
| `intensity` | 0–1, mặc định 1 | không | Trộn kết quả LUT với ảnh sau `adjust` |
| `adjust` | `exposure` −3…3 EV; `temperature`, `tint`, `contrast`, `highlights`, `shadows`, `saturation`, `clarity`, `sharpness`, `fade` −100…100; `wbShift` `{r, b}` −9…9; `colorDepth`, `colorDepthBlue`, `toneRange` 0–1 | không | Tham số kiểu công thức máy ảnh. Ba trường cuối thêm ở FLC-E01-27 cho công thức của Studio (độ sâu màu, độ sâu xanh lam, dải động). Chỉnh HSL, đường cong, bánh xe màu thì app bake vào `lut.cube` khi lưu look |
| `grain` | `amount` 0–1; `size` 0,5–3; `roughness` 0–1; `chroma` 0–1; `response` là `midtone` hoặc `flat`; `seed` là `auto` hoặc số; `animated` true/false | không | `size` tính theo pixel ở ảnh chuẩn 12 MP |
| `halation` | `amount`, `radius`, `threshold` 0–1; `tint` [r, g, b] | không | `radius` là tỉ lệ cạnh ngắn |
| `bloom` | `amount`, `radius`, `threshold` 0–1 | không | |
| `vignette` | `amount` −1…1; `midpoint`, `roundness`, `feather` 0–1 | không | |
| `chromaticAberration` | `amount` 0–1 | không | |
| `frame` | `{ref: "fm:frame/<slug>"}` hoặc `{file: "overlays/frame.png"}`; `aspect` | không | Tên khung cũng qua `NameGuard` |
| `dateStamp` | `enabled`; `format` (`yy_m_d`, `yyyy.mm.dd`, `d_m_yy`… hoặc `x-<app>:<tên>` do app cung cấp); `color` hex; `position` `br`, `bl` hoặc `tr`; `style` `seg7` hoặc `dot`; `source` `exif` hoặc `capture` | không | `x-fmd:lunar-vi` (ngày âm lịch), `x-fmd:dv-osd` (OSD và timecode DV) qua `DateStampFormatter` (FLC-E01-14). App không có formatter thì in `yy_m_d` |
| `overlays` | tối đa 4 phần tử `{type, file hoặc ref, opacity, blend}`; `type` là `leak`, `dust` hoặc `texture` | không | |
| `requires` | mảng tên khối đang dùng, cộng tên đầy đủ của trường tùy chọn thêm sau v1 (ví dụ `adjust.colorDepth`) | tự sinh khi ghi | App không hỗ trợ một khối hay trường thì báo tên đó |
| `tags` | mảng chuỗi | không | |
| `x-fmd`, `x-fms`, `x-fcm` | object | không | Dữ liệu riêng của từng app. App khác không đọc nhưng phải giữ nguyên khi ghi lại. Lược đồ `x-fms` (`recipe`, `crop`, `mask`, `packId`, `publishedId`) nằm trong `spec/look/` để fixture kiểm được (FLC-E01-27); trang `/r` đọc `x-fms.recipe` (FLC-E02-08) |

### 5.3 Phiên bản và tương thích

- `formatVersion` chỉ tăng khi có thay đổi **không tương thích**: đổi nghĩa hoặc xóa trường. Thêm trường tùy chọn thì không tăng.
- Đọc: nếu `formatVersion` lớn hơn bản app hiểu thì báo "Cần cập nhật app để mở look này" và không mở. Trường lạ thì bỏ qua khi render nhưng giữ nguyên khi ghi lại.
- Khối có trong `requires` mà app không render được (ví dụ FilCam chưa có `frame`) thì app vẫn áp phần còn lại và hiện "App này chưa hỗ trợ: khung".
- Trường tùy chọn thêm sau v1 (ba trường `adjust` và giá trị enum mới của FLC-E01-27) không tăng `formatVersion`. Người ghi đưa tên trường vào `requires`, nên app bản cũ báo "App này chưa hỗ trợ: độ sâu màu" thay vì render lệch mà không nói.
- Ghi: luôn ghi `formatVersion` thấp nhất đủ diễn tả nội dung. Mỗi lần sửa nội dung thì tăng `revision`.
- Look dựng sẵn được tham chiếu bằng `fm:<slug>@<rev>`. `slug` không bao giờ bị dùng lại cho look khác. App chỉ cần giữ revision mới nhất; QR trỏ revision cũ thì mở revision mới nhất và báo "Look đã được cập nhật".
- Có bản migrate cho mọi `formatVersion` cũ. Bộ fixture chung trong `spec/look/fixtures` là đáp án cho Kotlin, Swift và JavaScript.

### 5.4 Chia sẻ bằng QR và link

| Kênh | Nội dung | Giới hạn | Ghi chú |
|---|---|---|---|
| QR hoặc link recipe `https://filmode.app/r/1#<payload>` | Recipe không kèm LUT riêng; `base` là look dựng sẵn hoặc bỏ trống | Payload ≤ 600 ký tự; cả URL ≤ 660 ký tự | Vừa QR phiên bản 20, mức sửa lỗi M (tối đa 666 byte) ⚠. Recipe thường 150–300 ký tự nên QR khoảng phiên bản 8–13 ⚠. Payload nằm sau `#` nên không bao giờ gửi lên server |
| Link look cloud `https://filmode.app/l/<id>` (V1) | Bất kỳ `.flook` nào, kể cả có LUT riêng | File ≤ 10 MB; `id` 8 ký tự base62 | Cần FLC-E08-03. `id` cũng là "mã chữ" của Studio (FMS B8.1) |
| File `.flook` | Đủ mọi thứ | ≤ 10 MB | Gửi qua share sheet, Zalo, Messenger, AirDrop; không cần mạng hay tài khoản |

Payload recipe: JSON của `look.json` bỏ các trường `id`, `createdAt`, `updatedAt`, `requires`, đổi tên khóa theo bảng khóa ngắn v1 (`spec/look/share-keys-v1.json`, đóng băng, chỉ được thêm khóa), nén deflate, mã hóa base64url, thêm CRC32 ở cuối. Số `1` trong đường dẫn là phiên bản codec.

Link mở như sau:
- Android: `assetlinks.json` trên `filmode.app` khai cả ba package. Khi nhiều app đã cài cùng nhận một đường dẫn thì hệ thống cho người dùng chọn ⚠ kiểm hành vi trên Android 12+. Tham số `?app=fmd`, `fms` hoặc `fcm` chỉ gợi ý app ưu tiên cho trang web.
- iOS: Universal Links qua `apple-app-site-association` (FLC-E02-10).
- Chưa cài app: trang web tĩnh giải mã payload ngay trên trình duyệt, hiện tên look, thông số, ảnh mẫu của look dựng sẵn và nút Google Play/App Store (FLC-E02-08). Recipe của Studio thì hiện tham số theo thang công thức đọc từ `x-fms.recipe`, giống thẻ công thức.

### 5.5 Ví dụ `look.json`

```json
{
  "format": "filmode.look",
  "formatVersion": 1,
  "id": "7f3c2a1e-4b8d-4c55-9a51-0d2f6e8b9c10",
  "revision": 3,
  "name": "Nắng Sài Gòn",
  "author": { "name": "Hiếu", "handle": "@filmode" },
  "origin": { "type": "studio" },
  "base": { "ref": "fm:golden@2" },
  "intensity": 0.85,
  "adjust": { "exposure": 0.3, "wbShift": { "r": 2, "b": -3 }, "highlights": -20, "shadows": 15, "saturation": -10 },
  "grain": { "amount": 0.35, "size": 1.2, "roughness": 0.6, "chroma": 0.1, "response": "midtone", "seed": "auto" },
  "halation": { "amount": 0.25, "radius": 0.02, "threshold": 0.8, "tint": [1.0, 0.35, 0.15] },
  "vignette": { "amount": -0.3, "midpoint": 0.5, "roundness": 0.2, "feather": 0.6 },
  "dateStamp": { "enabled": true, "format": "yy_m_d", "color": "#FF8A00", "position": "br", "style": "seg7", "source": "exif" },
  "requires": ["adjust", "grain", "halation", "vignette", "dateStamp"],
  "tags": ["film", "nắng"]
}
```

Look này không có LUT riêng (`base` trỏ look dựng sẵn), nên chia sẻ được bằng QR.

## 6. Tổng quan epic

| ID | Epic | Mục tiêu | Module | ↔ Báo cáo | Feature | Có sẵn (ngày) | MVP (ngày) | V1 (ngày) | Tổng (ngày) |
|---|---|---|---|---|---|---|---|---|---|
| FLC-E01 | Look Engine | Một định dạng look, một bộ nhập/xuất và một pipeline GPU cho ba app; ảnh xuất giống preview | `:core:look`, `:core:lut-io`, `:core:gpu`, `:core:camera`, `:core:segment`, `:core:ui`, `(web)`, `LookFormat`, `LUTIO`, `LookRender` | C1 | 32 | 2,5 | 31,5 | 38,5 | 72,5 |
| FLC-E02 | Không tài khoản, thư viện và liên kết ba app | Dùng đủ khi không tài khoản, không mạng; tài khoản chỉ để đồng bộ, board, sự kiện; một look đi được giữa ba app | `:core:library`, `:core:account`, `:core:sync`, `AccountSync`, `LookLibrary` | C2 | 11 | 1 | 7 | 17,5 | 25,5 |
| FLC-E03 | Thanh toán và paywall | Mua và khôi phục không cần tài khoản; không bao giờ mất quyền đã mua; paywall qua chính sách Play và App Store | `:core:billing`, `:core:paywall`, `StoreCore`, `(tools)`, `(backend)` | C3 | 10 | 1 | 15,5 | 8 | 24,5 |
| FLC-E04 | Bản địa hóa và tên an toàn | 7 ngôn ngữ đợt 1; không tên nhãn hiệu nào lọt vào app hay listing; không đóng gói LUT share-alike | `:core:l10n`, `:core:look`, `(tools)`, `(ci)` | C4 | 4 | 0 | 8,5 | 0 | 8,5 |
| FLC-E05 | Chất lượng, thiết bị và đo lường | Chạy ổn trên máy tầm trung phổ biến ở VN/ĐNA, ẩn thứ máy không làm được, đo phễu mà không phá lời hứa quyền riêng tư | `:core:camera`, `:core:device`, `:core:analytics`, `:core:config`, `Telemetry`, `(qa)` | C5 | 10 | 1 | 16 | 2,5 | 19,5 |
| FLC-E06 | Quyền riêng tư, media và lưu trữ | Không xin quyền thừa; lưu ảnh không bao giờ hỏng; EXIF đúng; khai báo minh bạch | `:core:media`, `:core:camera`, `:core:analytics`, `MediaKit` | C6 | 8 | 0 | 8,5 | 5,5 | 14 |
| FLC-E07 | Nền tảng build, CI và kiểm thử | Một repo, một build-logic, CI và golden test chung để giữ lời hứa "preview = ảnh xuất" và "không thu hồi" | `build-logic`, `(ci)`, `:core:testing`, `(tools)`, `:core:ui`, `FilmodeCoreKit` | mới | 6 | 0 | 11,5 | 2 | 13,5 |
| FLC-E08 | Hạ tầng cloud dùng chung | Một backend cho board, sự kiện, đồng bộ và link look thay vì ba backend | `(backend)` | mới | 4 | 1 | 0 | 8,5 | 9,5 |
| | **Tổng** | | | | **85** | **6,5** | **98,5** | **82,5** | **187,5** |

`FLC-E01`…`FLC-E06` khớp 1:1 với C1–C6 của Bảng 9. Hai epic thêm:
- **FLC-E07 Nền tảng build, CI và kiểm thử.** Ba app trên hai nền tảng dùng chung khoảng 17 module. Không có build-logic, CI và golden test chung thì không kiểm được hai lời hứa lớn nhất: "preview = ảnh xuất" và "không thu hồi".
- **FLC-E08 Hạ tầng cloud dùng chung.** Board (FMD, đang chạy), sự kiện (FMD V1), đồng bộ look (C2.2), link look (C2.3) và cộng đồng (FMS) đều cần đăng nhập, lưu trữ và quy tắc bảo mật. Một backend rẻ hơn ba backend và chỉ phải khai quyền riêng tư một lần.

Chia theo nền tảng:

| Nền tảng | Feature | Ngày |
|---|---|---|
| Android | 62 | 125 |
| iOS | 10 | 28,5 |
| Web, backend, công cụ, QA | 13 | 34 |

Mười feature `FLC-E01-27`…`FLC-E01-32`, `FLC-E02-11`, `FLC-E05-10`, `FLC-E06-08`, `FLC-E08-04` là yêu cầu của ba app (mục "Điều chỉnh lõi" của từng app), thêm vào cuối epic; bảng đối chiếu ở mục 11.

Lõi không có mục `V2` hay `V3`. Các phần V2–V3 trong báo cáo (Match v2 bằng AI, khám phá công thức, chợ creator, chia doanh thu) hiện chỉ một app dùng nên nằm ở app. Khi app thứ hai cần thì chuyển vào lõi.

## 7. Epic và feature

Cột Module dùng ký hiệu ở mục 3. Cột Gói ở lõi chỉ ghi `Free`, `Pro` hay `Pass` khi báo cáo đã chốt cùng một gói cho mọi app (ví dụ nhập .cube luôn miễn phí, xuất LUT luôn là Pro); `—` là hạ tầng hoặc app tự quyết gói. Mục `V1` ghi "cần cho …" để biết app nào cần trước.

### FLC-E01 · Look Engine

Mục tiêu: một định dạng look, một bộ nhập và xuất, một pipeline GPU cho cả ba app; ảnh xuất giống preview.

Ánh xạ Bảng 9: C1.1 → 01–03 · C1.2 → 04–08 · C1.3 → 09–16, 20–22 · C1.4 → 24–26 · C1.5 → 19. Thêm ngoài Bảng 9: 17 (bộ chọn look dùng chung), 18 (Match v1, chuyển từ B4.1 vì FMD A11.1 và FCM F6.2 cũng cần), 23 (renderer WebGL2 cho web camera sự kiện A7.2). Yêu cầu của app: 27 (mở rộng định dạng look cho FMS, FCM), 28 (ba trường `adjust` mới trên GPU và CPU), 29 (hai `CameraEffect` cho FCM), 30 (`previewOnly`, `beforeLook`), 31 (đường 10-bit), 32 (Match v1 bản Swift). FLC-E01-11, -14, -15, -16 được mở rộng theo yêu cầu của FMD (mục 11).

FilCam đang dùng Camera2 cho điều khiển tay và phơi sáng dài. Lõi cho CameraX 1.6 kèm Camera2Interop (FLC-E01-16). Các chế độ cần session Camera2 riêng (phơi sáng dài, bracketing) vẫn thuộc FCM, nhưng phải render qua `:core:gpu`.

Khối lượng: 32 feature · Có sẵn 2,5 ngày · MVP 31,5 ngày · V1 38,5 ngày · tổng **72,5 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FLC-E01-01 | `:core:look` | Mô hình look v1 (`look.json`, mục 5.2): `base`, `intensity`, `adjust`, `grain`, `halation`, `bloom`, `vignette`, `chromaticAberration`, `frame`, `dateStamp`, `overlays`, tác giả, `revision`; kotlinx.serialization; validator theo khoảng giá trị | — | MVP | 2 | FLC-E07-01 | Khi đọc 30 file mẫu trong bộ fixture rồi ghi lại thì JSON thu được giống bản gốc từng trường; khi `grain.amount` = 3 thì validator trả lỗi kèm đường dẫn `grain.amount` |
| FLC-E01-02 | `:core:look` | Container `.flook` (ZIP gồm `look.json`, `lut.cube`, `thumb.jpg`, `overlays/`) và luật phiên bản (mục 5.3): `formatVersion`, giữ nguyên khối `x-*`, `requires`, migrate; chặn zip-slip và zip-bomb; giới hạn kích thước | — | MVP | 2 | FLC-E01-01 | Khi mở file `formatVersion` 2 trên app chỉ hiểu v1 thì hiện "Cần cập nhật app để mở look này" và không crash; khi file có khối `x-fms` thì ghi lại vẫn còn nguyên; khi ZIP có entry `../a` hoặc giải nén vượt 40 MB thì bị từ chối và không có file nào ghi ra ngoài thư mục tạm |
| FLC-E01-03 | `:core:look` | Codec chia sẻ (mục 5.4): recipe không kèm LUT riêng → JSON khóa ngắn → deflate → base64url + CRC32; URL `https://filmode.app/r/1#…`; payload tối đa 600 ký tự; look dựng sẵn tham chiếu bằng `fm:<slug>@<rev>` | Free | MVP | 1,5 | FLC-E01-01 | Khi mã hóa 50 recipe mẫu thì mọi URL ≤ 660 ký tự và giải mã ra đúng recipe gốc; khi sửa 1 ký tự trong payload thì báo "Mã không hợp lệ"; khi look có LUT riêng thì codec trả `needsFileOrLink` để UI chuyển sang chia sẻ file hoặc link |
| FLC-E01-04 | `:core:lut-io` | Gom bộ nhập đang chạy vào module: .cube của Filmode Vibe và FilCam, preset kiểu Lightroom của Filmode Vibe; thêm test .cube 17/33/65 và `DOMAIN_MIN`/`DOMAIN_MAX` | Free | Có sẵn | 1 | FLC-E07-01 | Khi nhập lại toàn bộ .cube và preset trong bộ test cũ thì ảnh render giống bản đang phát hành (golden khớp); khi nhập .cube 17 và 65 thì cả hai đều thành look dùng được |
| FLC-E01-05 | `:core:lut-io` | Nhập HALD (level 8 và 12, PNG 8/16-bit), .3dl, .cube có kèm phần 1D; resample tetrahedral về 33³ hoặc 64³; nhập nhiều file từ .zip qua `ACTION_OPEN_DOCUMENT` hoặc share intent, có báo cáo từng file (cần cho FMS B3.1, FCM F4.1) | Free | V1 | 2,5 | FLC-E01-04; FLC-E01-06 | Khi nhập zip 30 file có 2 file hỏng thì 28 look được tạo và báo cáo nêu tên, lý do của 2 file lỗi; khi nhập HALD level 8 và .cube 64 của cùng một LUT thì hai look render lệch nhau ΔE trung bình < 0,5 |
| FLC-E01-06 | `:core:lut-io` | Pipeline tham chiếu CPU (Kotlin, float): `adjust` + LUT tetrahedral; dùng để bake LUT khi nhập, xuất, match và làm đáp án cho golden test | — | MVP | 2 | FLC-E01-01 | Khi chạy trên ramp xám và ColorChecker thì kết quả khớp bản tính float64 độc lập (sai số ≤ 1e-4); khi bake lưới 33³ trên máy tầm trung chuẩn thì xong < 300 ms |
| FLC-E01-07 | `:core:lut-io` | 🧪 Spike 1 ngày: so ảnh render từ .xmp bằng bộ chuyển của ta với ảnh xuất từ Lightroom trên 10 preset mẫu; chốt tham số nào chuyển được và ngưỡng ΔE | — | V1 | 1 | FLC-E01-06 | Khi xong spike thì có bảng 10 preset (ΔE trung bình, trường không chuyển được) và ngưỡng chấp nhận cho FLC-E01-08 |
| FLC-E01-08 | `:core:lut-io` | Chuyển .xmp và preset .dng (XMP nhúng trong DNG) thành look: WB, phơi sáng, tương phản, tone curve, HSL, color grading bake thành LUT 33³; grain và vignette sang khối tương ứng; báo cáo phần không chuyển được (làm nét, khử nhiễu, clarity, dehaze, mask, lens profile) (cần cho FMS B3.1) | Free | V1 | 3 | FLC-E01-04; FLC-E01-07 | Khi nhập 20 preset mẫu (10 .xmp, 10 .dng) thì mỗi preset ra một look kèm báo cáo và ΔE trung bình không vượt ngưỡng chốt ở spike; khi file .dng là ảnh RAW không có thiết lập thì báo "File này là ảnh RAW, không phải preset" |
| FLC-E01-09 | `:core:gpu` | Gom renderer GLES đang chạy (LUT 64³ `GL_TEXTURE_3D`, trilinear, EGL context) thành API `LookRenderer` dùng chung cho Filmode Vibe và FilCam | — | Có sẵn | 1,5 | FLC-E07-01 | Khi render 43 look hiện có trên bộ ảnh chuẩn thì kết quả khớp bản đang phát hành (PSNR ≥ 45 dB) |
| FLC-E01-10 | `:core:gpu` | Hai chế độ nội suy: trilinear phần cứng cho preview, tetrahedral trong fragment shader (`highp`) cho ảnh tĩnh và xuất; chọn bằng `RenderQuality` | — | MVP | 1,5 | FLC-E01-09; FLC-E01-06 | Khi render LUT kiểm thử có đường cong gắt thì đường tetrahedral lệch bản CPU ≤ 1/255 ở mọi pixel ramp; khi preview trilinear 1080p trên máy tầm trung chuẩn thì vẫn ≥ 30 fps |
| FLC-E01-11 | `:core:gpu` | Đồ thị pass theo thứ tự cố định (adjust → LUT → halation/bloom → grain → vignette/CA → overlay, khung, date stamp) dựng từ `look.json`; API `EffectPass` để app cắm hiệu ứng riêng (VHS, CCD, star…); pass được xin N khung đầu ra trước đó (lịch sử khung trên GPU, tối đa 12) và nhận thời điểm của khung trong clip; pass rẻ: adjust, vignette, CA | — | MVP | 4,5 | FLC-E01-01; FLC-E01-09 | Khi look chỉ có LUT thì chỉ 1 pass chạy; khi mọi tham số `adjust` bằng 0 thì ảnh ra trùng ảnh vào từng bit (ảnh 8-bit); khi app đăng ký pass "VHS" ở vị trí `afterGrain` thì pass chạy đúng thứ tự ở cả preview và ảnh xuất; khi pass "flashDrift" xin 12 khung trước thì nhận đúng 12 texture theo thứ tự thời gian và bộ nhớ GPU chỉ thêm 12 khung ở độ phân giải preview; khi quay video thì thời điểm pass nhận khớp timestamp của khung trong file |
| FLC-E01-12 | `:core:gpu` | Grain theo độ sáng (mạnh ở vùng trung tính, giảm ở bóng sâu và vùng cháy); `size`, `roughness`, `chroma`; seed = hash(photoId, look revision) để preview và ảnh xuất giống nhau; grain động theo khung cho video | — | MVP | 2 | FLC-E01-11 | Khi render cùng `photoId` hai lần thì ảnh giống hệt từng bit; khi so khung preview đóng băng với ảnh xuất thu về cùng kích thước thì SSIM ≥ 0,95; khi vùng trắng cháy hoặc đen tuyệt đối thì gần như không có grain |
| FLC-E01-13 | `:core:gpu` | Halation (lệch đỏ, bán kính kênh đỏ lớn hơn kênh xanh) và bloom: ngưỡng → thu ¼ → Gaussian tách được → cộng lại; tự hạ xuống ⅛ trên máy tier C | — | MVP | 2 | FLC-E01-11; FLC-E05-04 | Khi preview 1080p với LUT + halation + bloom + grain trên máy tầm trung chuẩn thì ≥ 30 fps; khi so ảnh xuất với preview cùng khung thì ΔE trung bình < 2 |
| FLC-E01-14 | `:core:gpu` | Khung và date stamp: khung PNG theo tỉ lệ (3:4, 1:1, 9:16); date stamp kiểu LED 7 đoạn, đổi được định dạng, màu, vị trí; giờ lấy từ EXIF `DateTimeOriginal` hoặc lúc chụp; interface `DateStampFormatter` để app tự cung cấp chữ (ngày âm lịch, OSD và timecode DV chạy theo khung); `dateStamp.format` nhận giá trị `x-<app>:<tên>`, app không có formatter đó thì in `yy_m_d` | — | MVP | 2 | FLC-E01-11; FLC-E04-01 | Khi áp date stamp cho ảnh nhập có EXIF chụp ngày 01/05/2019 thì stamp in ngày đó theo định dạng đã chọn, không phải ngày hôm nay; khi đổi tỉ lệ sang 1:1 thì khung không bị kéo méo; khi FMD đăng ký formatter `x-fmd:lunar-vi` thì stamp in chữ do app trả về ở cả preview và ảnh xuất; khi Studio mở look có `x-fmd:lunar-vi` thì in kiểu `yy_m_d` và hiện "App này chưa hỗ trợ: kiểu ngày x-fmd:lunar-vi" |
| FLC-E01-15 | `:core:gpu` | Render ảnh tĩnh ngoài màn hình theo tile (có vùng chồng cho pass blur), 8 hoặc 16-bit, ra `Bitmap`/`HardwareBuffer`; ảnh tới 50 MP; móc mã hóa lại JPEG: app đặt một điểm trong đồ thị để ảnh xuất được mã hóa JPEG thật ở chất lượng app chọn rồi giải mã lại trước các pass sau (khối JPEG của máy CCD, VGA); chất lượng JPEG khi lưu do app truyền cho FLC-E06-02 | — | MVP | 3 | FLC-E01-10; FLC-E01-13 | Khi xử lý ảnh 12 MP với look đủ pass trên máy tầm trung chuẩn thì p90 < 1,5 giây; khi xử lý ảnh 50 MP thì không OOM và không thấy đường nối tile ở vùng có halation; khi app đặt móc JPEG q = 65 sau pass "ccd" thì ảnh xuất có khối 8×8 thật (đo được bước nhảy ở biên khối) còn preview không chậm đi vì móc chỉ chạy ở ảnh xuất |
| FLC-E01-16 | `:core:camera` | Wrapper CameraX 1.6: `SessionConfig` + `CameraEffect` với `SurfaceProcessor` của `:core:gpu` cho Preview, ImageCapture, VideoCapture; đổi look không dựng lại session; xoay và lật gương đúng trên mọi hãng; mở Camera2Interop cho điều khiển tay; mở flash màn hình của CameraX (`ImageCapture.FLASH_MODE_SCREEN`, `ScreenFlashView` ⚠) và trả cho app khung trước flash và khung flash | — | MVP | 4 | FLC-E01-11; FLC-E05-02 | Khi đổi 10 look liên tục trên kính ngắm thì không có khung đen và session không bị dựng lại; khi chụp bằng camera trước và sau ở 4 hướng trên 8 máy ma trận thì ảnh lưu đúng chiều; khi so ảnh chụp với khung preview cùng look thì golden test đạt; khi chụp selfie với flash màn hình thì app nhận được cả khung trước flash và khung flash của cùng lần chụp |
| FLC-E01-17 | `:core:ui` | Component chọn look (carousel và lưới), thanh cường độ, giữ để so sánh trước/sau; dùng chung cho kính ngắm và trình sửa | — | MVP | 2 | FLC-E02-02; FLC-E07-06 | Khi kéo thanh cường độ trên kính ngắm thì preview đổi theo từng khung, không giật; khi giữ nút so sánh thì thấy ảnh gốc và thả ra thì thấy look; khi bật TalkBack thì nghe được tên look và giá trị cường độ |
| FLC-E01-18 | `:core:lut-io` | Match v1: từ ảnh mẫu tạo LUT 33³ bằng truyền màu thống kê (mean/std trong Lab kiểu Reinhard, khớp CDF từng kênh), có giới hạn để không vỡ vùng xám và màu da; dùng chung cho Match Photo (FMD A11.1), FMS B4.1, FCM F6.2 | — | MVP | 3 | FLC-E01-06 | Khi chạy 20 cặp ảnh mẫu thì LUT tạo xong < 500 ms trên máy tầm trung chuẩn; khi match thì ô xám trung tính của ColorChecker lệch màu không quá ngưỡng đặt trong test; khi bấm lưu thì kết quả thành look trong thư viện |
| FLC-E01-19 | `:core:lut-io` | Xuất look thành .cube 33/65 (ghi `TITLE`, tác giả) và HALD PNG 16-bit level 8; chỉ bake phần màu, báo phần không đi theo LUT (grain, halation, vignette, khung) (cần cho FCM MVP vì sidecar `.cube` của ghi sạch FCM-E02-11; FMS B7.2 và FCM F6.1 ở V1) | Pro | V1 | 2 | FLC-E01-02; FLC-E01-06 | Khi xuất .cube 33 rồi nhập lại thì phần màu khớp look gốc (ΔE trung bình < 1); khi mở file trong DaVinci Resolve và VN thì màu đúng (kiểm tay); khi bấm xuất thì người dùng thấy danh sách hiệu ứng không đi theo LUT |
| FLC-E01-20 | `:core:gpu` | Chuỗi LUT: khối `inputTransform` (LUT kỹ thuật Log → Rec.709) chạy trước LUT sáng tạo; khi đổi look thì gộp hai LUT thành một texture để giữ một lần lookup (cần cho FCM F2.2, F3.1, F5.2) | — | V1 | 1,5 | FLC-E01-11 | Khi áp "Log → 709 + look" cho clip Samsung Log mẫu thì kết quả khớp việc áp hai LUT tuần tự bằng CPU (ΔE trung bình < 1) và preview vẫn ≥ 30 fps |
| FLC-E01-21 | `:core:gpu` | `LookGlEffect` cho Media3 (Transformer và `ExoPlayer.setVideoEffects`): tự xử lý transfer function trước khi lookup thay vì dùng `SingleColorLut` nhận RGB tuyến tính ⚠; grain động (cần cho FMD A4, FCM F2.3, F5) | — | V1 | 2,5 | FLC-E01-11; FLC-E01-12 | Khi xuất clip 10 giây 1080p với look có LUT và grain thì khung giữa khớp ảnh tĩnh cùng khung (ΔE trung bình < 2) và âm thanh giữ nguyên; khi xem trước bằng ExoPlayer thì màu giống file xuất |
| FLC-E01-22 | `:core:segment` | Gom tách nền người đang chạy trong photobooth của Filmode Vibe thành API mask; pass "giữ tông da" trộn ảnh gốc và ảnh có look theo mask có feather; phát hiện GPU delegate trả mask rỗng thì chuyển CPU (cần cho FMS B5.1) | — | V1 | 2,5 | FLC-E01-11 | Khi áp look đỏ mạnh lên 20 ảnh chân dung với "giữ tông da" bật thì vùng da lệch ảnh gốc ΔE < 3 và không có viền sáng dễ thấy quanh tóc; khi GPU delegate trả mask rỗng thì tự chuyển sang CPU và ghi một sự kiện chẩn đoán |
| FLC-E01-23 | (web) | Renderer WebGL2 cho look (LUT 3D, `adjust` gồm ba trường mới của FLC-E01-27, grain cùng hàm hash, vignette, khung; halation khi GPU đủ mạnh) để web camera sự kiện (FMD A7.2) và trang xem look dùng chung định dạng (cần cho FMD V1: xong trước 15/2/2027 để kịp lát cắt sự kiện và pilot) | — | V1 | 3,5 | FLC-E01-02; FLC-E07-04; FLC-E01-27 | Khi mở trang trên Chrome Android tầm trung và Safari iOS thì preview camera ≥ 24 fps với LUT và grain; khi so ảnh chụp trên web với ảnh app Android cùng look thì ΔE trung bình < 2; khi recipe có `colorDepth` và `toneRange` thì ảnh chụp trên web lệch ảnh Android ΔE trung bình < 2 |
| FLC-E01-24 | `FilmodeCoreKit/LookFormat` | Model look, `.flook` và codec chia sẻ bằng Swift (Codable), chạy cùng bộ fixture với Kotlin; gồm các trường thêm ở FLC-E01-27 (ba trường `adjust`, `origin.importedFrom: text`, `inputTransform.from: hlg`) và lược đồ `x-fms` | — | V1 | 2,5 | FLC-E07-04; FLC-E07-05; FLC-E01-27 | Khi chạy bộ fixture chung thì Swift và Kotlin cho cùng JSON round-trip và cùng payload QR cho 50 recipe mẫu; khi đọc rồi ghi lại look có khối `x-fms` thì khối đó giữ nguyên |
| FLC-E01-25 | `FilmodeCoreKit/LUTIO` | Gom bộ nhập .cube/.xmp đang chạy của Filmode iOS; thêm HALD, .3dl, preset .dng, báo cáo chuyển đổi, xuất .cube/HALD; cho cùng kết quả với Android | Free | V1 | 3 | FLC-E01-24; FLC-E01-08 | Khi nhập 20 preset mẫu trên iOS và Android thì hai bên cho cùng báo cáo và LUT lệch nhau ΔE trung bình < 0,5 |
| FLC-E01-26 | `FilmodeCoreKit/LookRender` | Renderer Metal đủ pass: LUT 3D tetrahedral (preview có thể dùng `CIColorCubeWithColorSpace` ≤ 64³), `adjust` (gồm ba trường của FLC-E01-27), grain cùng hàm hash và seed, halation/bloom ¼ độ phân giải, vignette, CA, khung, date stamp, chuỗi LUT | — | V1 | 5 | FLC-E01-24; FLC-E07-03 | Khi render bộ ảnh chuẩn thì iOS khớp golden của Android (ΔE trung bình < 1; grain SSIM ≥ 0,9 sau khi thu nhỏ); khi preview 1080p trên iPhone 12 thì ≥ 30 fps |
| FLC-E01-27 | `:core:look` | Mở rộng look v1, chỉ thêm trường tùy chọn nên `formatVersion` giữ 1 (mục 5.2, 5.3): `adjust.colorDepth`, `adjust.colorDepthBlue`, `adjust.toneRange` 0–1 kèm khóa ngắn mới trong `share-keys-v1.json`; `origin.importedFrom` thêm `text`; `inputTransform.from` thêm `hlg`, `fm-log` trỏ tới đặc tả FM-Log v1 (FCM-E03-02); lược đồ `x-fms` (`recipe`, `crop`, `mask`, `packId`, `publishedId`) đăng ký trong `spec/look/`; trường mới được ghi vào `requires` để app cũ báo tên (cần cho FMS MVP: làm trong FMS S1 4–15/1/2027 để `x-fms` có từ S1 và ba trường `adjust` có trước FMS S2 18/1/2027; FCM V1: `hlg`) | — | V1 | 1 | FLC-E01-01; FLC-E01-03; FLC-E07-04 | Khi mã hóa 50 recipe mẫu có ba trường mới thì mọi URL vẫn ≤ 660 ký tự và giải mã ra đúng giá trị; khi app chỉ hiểu bản trước mở look có `adjust.colorDepth` thì trường được giữ khi ghi lại và app hiện "App này chưa hỗ trợ: độ sâu màu"; khi Kotlin, Swift và JavaScript đọc rồi ghi lại fixture có khối `x-fms` đầy đủ thì khối giữ nguyên |
| FLC-E01-28 | `:core:gpu` | Render ba trường `adjust` mới trong pass `adjust` của GPU và pipeline CPU tham chiếu (FLC-E01-06): `colorDepth` giảm độ sáng màu có độ bão hòa cao, `colorDepthBlue` như trên với mask sắc độ khoảng 200–260°, `toneRange` làm vai mềm ở vùng sáng; chạy trước LUT theo thứ tự ở README Studio mục 5.2 (cần cho FMS MVP, xong trước FMS S2 18/1/2027; WebGL ở FLC-E01-23, Metal ở FLC-E01-26) | — | V1 | 1 | FLC-E01-27; FLC-E01-11; FLC-E01-06 | Khi ba trường mới bằng 0 thì ảnh ra trùng ảnh vào từng bit; khi `colorDepth` = 1 thì vùng đỏ bão hòa tối đi còn ô xám của ColorChecker không đổi (ΔE < 0,5); khi so GPU với CPU trên bộ ảnh chuẩn thì lệch ≤ 1/255 |
| FLC-E01-29 | `:core:camera` | Hai `CameraEffect` theo target trong `SessionConfig`: PREVIEW chạy graph "xem", VIDEO_CAPTURE chạy graph "ghi" hoặc không effect; kiểm bằng `isSessionConfigSupported` trước khi bind; báo cho app khi CameraX ép stream sharing; mở `Camera2CameraControl` cho `TONEMAP_*`, `CONTROL_AE_TARGET_FPS_RANGE`, `SENSOR_*` ⚠ (cần cho FCM MVP: FCM-E02-02, FCM-E01-10; FCM V1: FCM-E03-03) | — | V1 | 2,5 | FLC-E01-16; FLC-E05-02 | Khi app gắn hai effect trên máy chạy được hai luồng thì khung trích từ file không có look còn preview có look; khi CameraX phải dùng stream sharing thì API báo trước khi bind để app vào chế độ một nhánh; khi app đặt `SENSOR_EXPOSURE_TIME` qua `Camera2CameraControl` thì `CaptureResult` trả đúng giá trị |
| FLC-E01-30 | `:core:gpu` | `EffectPass` cho công cụ đo và chỉnh màu: cờ `previewOnly` (pass chỉ chạy ở nhánh preview, không bao giờ vào ảnh hay file quay) và điểm cắm `beforeLook` sau `inputTransform`, trước LUT sáng tạo (cần cho FCM MVP: FCM-E01-06, FCM-E05-04; FCM V1: FCM-E05-08) | — | V1 | 1 | FLC-E01-11; FLC-E01-20 | Khi pass zebra mang cờ `previewOnly` thì khung trích từ file quay và ảnh chụp không có vạch zebra; khi pass đường cong cắm ở `beforeLook` thì chạy sau LUT kỹ thuật và trước look ở cả preview, file quay và ảnh xuất |
| FLC-E01-31 | `:core:gpu` | Đường 10-bit cho video ⚠: `SurfaceProcessor` nhận luồng `DynamicRange.HLG_10_BIT` (EGL BT.2020 HLG, `GL_EXT_YUV_target` ⚠); `LookGlEffect` nhận clip 10-bit gắn nhãn SDR (clip Log) mà không lượng tử về 8-bit và chạy sau bước tone map HDR → SDR của Transformer; phạm vi chốt theo spike FCM-E03-06 và FCM-E05-09 (cần cho FCM V1: FCM-E03-07, FCM-E05-11, FCM-E05-13) | — | V1 | 2 | FLC-E01-21; FLC-E01-29 | Khi quay HLG trên máy tier A thì preview có look và file là HEVC Main10 BT.2020 HLG; khi áp look lên clip Log 10-bit thì ramp trời không có nhiều bậc banding hơn bản xử lý bằng CPU 16-bit; khi xuất clip HLG thành SDR có look thì look chạy sau bước tone map |
| FLC-E01-32 | `FilmodeCoreKit/LUTIO` | Match v1 bản Swift: cùng thuật toán và bộ fixture với FLC-E01-18 (cần cho Studio iOS FMS-E12-09, xong trước 17/5/2027; Filmode iOS chuyển lõi FMD-E11-08) | — | V1 | 2 | FLC-E01-18; FLC-E01-25 | Khi match 20 cặp ảnh mẫu trên iOS và Android thì LUT lệch nhau ΔE trung bình < 1; khi match trên iPhone 12 thì LUT xong < 500 ms |

### FLC-E02 · Không tài khoản, thư viện và liên kết ba app

Mục tiêu: dùng được đủ khi không có tài khoản và không có mạng. Tài khoản chỉ để đồng bộ, board và sự kiện. Một look đi được giữa ba app.

Ánh xạ Bảng 9: C2.1 → 01–03 (khôi phục mua nằm ở FLC-E03-03; ảnh lưu vào album tên rõ nằm ở FLC-E06-02) · C2.2 → 04–07 · C2.3 → 08–10. Yêu cầu của FMS: 11 (tông nền dùng chung ba app).

Xóa tài khoản (FLC-E02-05) là `MVP` dù báo cáo xếp C2.2 là V1: Filmode Vibe đã cho đăng nhập Google để dùng Cloud Boards, nên phải có lối xóa tài khoản ngay ⚠.

Khối lượng: 11 feature · Có sẵn 1 ngày · MVP 7 ngày · V1 17,5 ngày · tổng **25,5 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FLC-E02-01 | `:core:library` | Thư viện look offline (Room): look dựng sẵn đóng gói trong app với ID ổn định `fm:<slug>` (không bao giờ dùng lại ID), look người dùng, yêu thích, thư mục, thẻ; không cần mạng, không cần tài khoản | Free | MVP | 2,5 | FLC-E01-02 | Khi cài app rồi bật chế độ máy bay thì mọi look dựng sẵn, look đã nhập và look Pro đã mua đều dùng được; khi đổi tên hiển thị một look dựng sẵn thì ID giữ nguyên và QR cũ vẫn mở đúng look |
| FLC-E02-02 | `:core:library` | Thumbnail look trên ảnh của người dùng hoặc khung hình hiện tại: render nền theo lô, cache LRU, làm mới theo `revision` | Free | MVP | 1,5 | FLC-E02-01; FLC-E01-15 | Khi mở bộ chọn 60 look thì thumbnail đầu hiện < 300 ms và cả lưới xong < 2 giây trên máy tầm trung chuẩn; khi sửa look thì thumbnail tự làm mới |
| FLC-E02-03 | `:core:library` | Chuyển dữ liệu từ bản đang phát hành (LUT và preset đã nhập, công thức đã lưu của FilCam, cài đặt) sang kho mới khi cập nhật | Free | MVP | 1,5 | FLC-E02-01 | Khi cập nhật từ Filmode Vibe 1.5.9 hoặc FilCam 1.0.21 có 10 LUT đã nhập và 3 công thức thì sau cập nhật vẫn thấy đủ và dùng được; khi chuyển lỗi thì file gốc không bị xóa và lần mở sau thử lại |
| FLC-E02-04 | `:core:account` | Gom đăng nhập Google đang chạy của Cloud Boards vào module; chuyển sang Credential Manager (Sign in with Google) nếu đang dùng API cũ ⚠ | — | Có sẵn | 1 | FLC-E07-01; FLC-E08-01 | Khi đăng nhập trên bản mới thì board cũ vẫn hiện đủ; khi không đăng nhập thì mọi tính năng ngoài board, sự kiện và đồng bộ vẫn dùng được |
| FLC-E02-05 | `:core:account` | Xóa tài khoản ngay trong app và qua trang web (yêu cầu của Play khi app cho tạo tài khoản ⚠): xóa board, look đã đồng bộ, hồ sơ; quyền đã mua giữ nguyên vì gắn với store | — | MVP | 1,5 | FLC-E02-04 | Khi xác nhận xóa tài khoản thì dữ liệu cloud của người đó bị xóa (kiểm bằng truy vấn backend) và app đăng xuất; khi mở lại app thì Pro trọn đời vẫn còn nhờ khôi phục qua store |
| FLC-E02-06 | `:core:sync` | Đồng bộ thư viện look và công thức giữa các máy của người đã đăng nhập: hàng đợi offline-first, tải `.flook` lên cloud, giải xung đột theo `revision`, bản thua lưu thành "(bản sao xung đột)" | Free | V1 | 3 | FLC-E02-01; FLC-E08-02 | Khi sửa cùng một look trên hai máy lúc offline rồi bật mạng thì không mất bản nào; khi mất mạng giữa lúc tải thì lần mở sau tự tải tiếp |
| FLC-E02-07 | `FilmodeCoreKit/AccountSync` | Sign in with Apple và Google trên iOS (quy định đăng nhập của Apple ⚠), cùng tài khoản backend; client đồng bộ thư viện look như Android; xóa tài khoản trong app | Free | V1 | 3,5 | FLC-E02-06; FLC-E02-10 | Khi tạo look trên Android rồi đăng nhập cùng tài khoản Google trên iPhone thì look xuất hiện trong ≤ 1 phút; khi xóa tài khoản trên iOS thì dữ liệu cloud bị xóa như trên Android |
| FLC-E02-08 | `:core:library` | Deep link và App Links: `https://filmode.app/r/1#…` (recipe trong link) và `/l/<id>` (look lưu trên cloud) mở trong app đã cài, nhiều app cùng nhận thì hệ thống cho chọn ⚠; nhận `.flook` qua Intent (`ACTION_VIEW`, `ACTION_SEND`) để "Mở trong Filmode, Studio hoặc FilCam"; trang web tĩnh giải mã recipe ngay trên trình duyệt khi chưa cài app; trang `/r` đọc `x-fms.recipe` để hiện tham số theo thang công thức như trên thẻ và nhận gợi ý `?app=fmd`, `fms`, `fcm` (cần cho FMS B2.4, FMD A8.2) | Free | V1 | 4 | FLC-E01-03; FLC-E02-01; FLC-E08-02 | Khi quét QR recipe trên máy có cả Filmode và Studio thì hệ thống hỏi mở bằng app nào; khi chưa cài app nào thì trang web hiện tên look, thông số và nút Google Play/App Store, còn recipe không bị gửi lên server; khi bấm "Mở trong FilCam" từ Studio thì FilCam mở màn nhập look mà không cần mạng; khi quét QR thẻ công thức của Studio trên máy chưa cài app thì trang hiện đúng các nấc như trên thẻ (ví dụ "Vùng tối +2", "Dải động 400") |
| FLC-E02-09 | `:core:library` | Thư viện look dùng chung giữa ba app Android trên cùng máy: `ContentProvider` bảo vệ bằng signature permission (ba app phải cùng chứng chỉ ký ⚠); look có `license` là `personal` hoặc `unknown` chỉ đi giữa các app trên cùng máy, không lên link công khai | Free | V1 | 2,5 | FLC-E02-01; FLC-E07-02 | Khi lưu look trong Studio thì FilCam trên cùng máy thấy look đó ở mục "Từ Filmode Studio" mà không cần đăng nhập; khi app lạ không cùng chứng chỉ gọi provider thì bị từ chối |
| FLC-E02-10 | `FilmodeCoreKit/LookLibrary` | Thư viện look trên iOS: look dựng sẵn và look người dùng, offline, thumbnail; App Group chung giữa các app iOS của đội; Universal Links cho `/r` và `/l`; đóng gói 16 tông nền `fm:base/<slug>` như Android (FLC-E02-11) | Free | V1 | 3 | FLC-E01-24; FLC-E07-05; FLC-E02-11 | Khi bật chế độ máy bay thì thư viện iOS vẫn dùng đủ; khi lưu look trong Studio iOS thì Filmode iOS thấy look đó; khi quét QR recipe trên iPhone đã cài app thì app mở đúng look |
| FLC-E02-11 | `:core:library` | Tông nền dùng chung `fm:base/<slug>`: 16 look (LUT 33³ do Studio dựng, manifest `owned`) đóng gói trong cả ba app Android (khoảng 1,5 MB nén ⚠), tải theo yêu cầu từ `filmode.app/b/<slug>@<rev>.flook` khi app thiếu, lưu cache để chạy offline (cần cho FMS MVP, xong trước FMS S2 18/1/2027; FMD và FCM mở recipe của Studio) | Free | V1 | 1,5 | FLC-E02-01; FLC-E08-02 | Khi quét QR recipe của Studio trong Filmode hoặc FilCam thì look render bằng đúng tông nền và lệch Studio ΔE trung bình < 1; khi app thiếu một tông nền và có mạng thì tải về và lần sau dùng được khi offline; khi thiếu mà không có mạng thì hiện "Cần mạng để tải tông nền" thay vì render sai |

### FLC-E03 · Thanh toán và paywall

Mục tiêu: mua và khôi phục không cần tài khoản; không bao giờ mất quyền đã mua; paywall qua được luật thuê bao của Play và App Store.

Ánh xạ Bảng 9: C3.1 → 01–03, 09, 10 · C3.2 → 05, 06 · C3.3 → 07, 08 · C3.4 → 04 (mã khuyến mãi ở 05 và 09).

Gói theo báo cáo: tháng, năm (dùng thử 3–7 ngày chỉ ở gói năm), trọn đời, gói lẻ, pass sự kiện. Giá VN khoảng 40–50% giá Mỹ. Gói trọn đời đặt nổi bật trên Android vì 32,2% lượt hủy thuê bao trên Play đến từ lỗi thanh toán.

Khối lượng: 10 feature · Có sẵn 1 ngày · MVP 15,5 ngày · V1 8 ngày · tổng **24,5 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FLC-E03-01 | `:core:billing` | Gom code Play Billing đang chạy của Filmode Vibe và FilCam vào module; lập danh sách mọi SKU đang bán | — | Có sẵn | 1 | FLC-E07-01 | Khi mua thử bằng license tester trên bản mới thì mọi SKU đang bán vẫn mua được và mở đúng quyền như bản cũ |
| FLC-E03-02 | `:core:billing` | Nâng lên Play Billing Library 8.x ⚠: tự kết nối lại; `ProductDetails` cho thuê bao (base plan tháng và năm, offer dùng thử 3–7 ngày chỉ ở gói năm) và sản phẩm một lần (trọn đời, máy lẻ, gói look, pass); acknowledge; giao dịch `PENDING` | — | MVP | 2 | FLC-E03-01 | Khi thanh toán bằng phương thức chậm (pending) thì app hiện "Đang chờ thanh toán" và cấp quyền khi giao dịch xong; khi kiểm trên Play Console thì không giao dịch nào quá 3 ngày chưa acknowledge |
| FLC-E03-03 | `:core:billing` | Mô hình `Entitlements` tách khỏi SKU (SKU → `pro`, `camera:<id>`, `pack:<id>`, `pass:<loại>`), đọc từ config đóng gói và remote config; khôi phục bằng `queryPurchasesAsync` khi mở app và nút "Khôi phục", không cần tài khoản; cache quyền để chạy offline | Free | MVP | 2,5 | FLC-E03-02; FLC-E05-09 | Khi cài lại app trên máy mới cùng tài khoản Google Play thì Pro trọn đời hiện lại ≤ 5 giây sau khi có mạng mà không cần đăng nhập Filmode; khi offline 30 ngày thì quyền đã mua vẫn còn; khi thêm SKU mới map vào quyền có sẵn thì không phải sửa code app |
| FLC-E03-04 | `:core:billing` | Cam kết không thu hồi: bảng map mọi SKU từng bán (Filmode Android; Filmode iOS gồm Pro tháng, 3 tháng, năm, trọn đời, gói Cinematic, Pro-Mist, Y2K Digicam, pass; FilCam Pro) sang quyền mới, không bao giờ xóa dòng; mỗi dòng ghi tên hiển thị và trạng thái (đang bán, ngừng bán cho người mới), nên SKU đổi tên (gói "Pro-Mist" hiện tên "Soft Mist", giữ product ID) và SKU ngừng bán (gói 3 tháng iOS vẫn gia hạn và cấp quyền) vẫn map đúng; `free-tier.json` liệt kê mọi thứ miễn phí theo phiên bản, mỗi app một mục (`fmd`, `fms`, `fcm`); CI chặn khi một mục miễn phí bị bỏ hoặc chuyển sang Pro | Free | MVP | 2 | FLC-E03-03; FLC-E07-02 | Khi test với giao dịch giả của từng SKU cũ thì quyền tương ứng được cấp; khi PR chuyển look "Golden" từ Free sang Pro hoặc xóa một SKU cũ khỏi bảng map thì CI fail và nêu tên mục; khi người đã mua gói "Pro-Mist" cập nhật thì gói hiện tên "Soft Mist" và quyền còn nguyên; khi PR bỏ một mục trong phần `fcm` của `free-tier.json` thì CI fail |
| FLC-E03-05 | `:core:billing` | Giữ khách khi thanh toán lỗi và quản lý gói: `showInAppMessages` (TRANSACTIONAL) cho grace period và account hold ⚠; link tới trang quản lý thuê bao của Play; lối nhập mã khuyến mãi Play | — | MVP | 1,5 | FLC-E03-03 | Khi thuê bao ở grace period thì mở app thấy thông báo sửa thanh toán của Play; khi bấm "Quản lý gói" thì mở đúng trang thuê bao của app trên Play; khi nhập mã khuyến mãi hợp lệ thì quyền kích hoạt lúc quay lại app mà không cần khởi động lại |
| FLC-E03-06 | `:core:paywall` | Paywall Compose dùng chung, cấu hình theo app, đạt checklist mục 4.3: số tiền thực bị trừ và chu kỳ là chữ lớn nhất, điều khoản dùng thử có ngày cụ thể, cách hủy theo ngôn ngữ người dùng, nút đóng hiện ngay, các gói đặt cạnh nhau, gói trọn đời nổi bật; helper "thử trước, trả khi lưu" | — | MVP | 4 | FLC-E03-03; FLC-E04-01; FLC-E07-06 | Khi chạy screenshot test 7 ngôn ngữ thì checklist mục 4.3 đạt 100%; khi gói năm là 149.000 ₫ thì chữ lớn nhất là "149.000 ₫/năm"; khi người dùng miễn phí chọn look Pro thì xem trước được ngay, paywall chỉ hiện lúc lưu, và đóng paywall thì ảnh chưa lưu vẫn còn |
| FLC-E03-07 | `:core:paywall` | Thử A/B giá bằng remote config: biến thể chọn base plan hoặc offer (Play) và product ID (iOS); gắn `variant` vào mọi sự kiện paywall; người đã có quyền không vào thử nghiệm | — | MVP | 1,5 | FLC-E03-06; FLC-E05-07; FLC-E05-09 | Khi remote config gán nhóm B thì paywall hiện base plan của nhóm B và mọi sự kiện paywall mang `variant=B`; khi người dùng đã có Pro thì không bao giờ thấy paywall thử giá |
| FLC-E03-08 | (tools) | Bảng giá theo vùng (VN, ID, PH, BR, IN, TH, KR, JP, US) trong một file cấu hình; script đẩy lên Play Console (Play Developer API ⚠) và App Store Connect API; báo lệch giữa bảng và store; người đang thuê bao giữ giá cũ | — | MVP | 2 | — | Khi chạy script thì Play Console có đúng giá VND đã đặt cho từng SKU và lần chạy lại báo 0 dòng lệch; khi đổi giá một base plan thì người đang thuê bao vẫn giữ giá cũ ⚠ |
| FLC-E03-09 | `FilmodeCoreKit/StoreCore` | StoreKit 2: sản phẩm, mua, `Transaction.updates`, `currentEntitlements`, `AppStore.sync()`; cùng mô hình `Entitlements` và bảng map SKU cũ; offer code, "Quản lý gói"; paywall SwiftUI đạt checklist mục 4.3 | — | V1 | 4 | FLC-E03-04; FLC-E07-05 | Khi người đã mua Pro trọn đời trên Filmode iOS 1.4.4 cập nhật lên bản dùng lõi thì vẫn có Pro; khi nhập offer code thì quyền kích hoạt; khi chụp màn hình paywall trên iPhone SE và iPhone Pro Max ở VI, EN thì checklist đạt 100% |
| FLC-E03-10 | (backend) | Xác minh mua phía server cho quyền dùng trên cloud: Play Developer API + RTDN, App Store Server API + Server Notifications V2 ⚠; pass sự kiện là sản phẩm tiêu hao, chỉ consume sau khi server gắn pass với một sự kiện; sự kiện thử miễn phí (5 khách × 10 ảnh, 7 ngày) do server cấp không cần giao dịch, mỗi tài khoản chủ tiệc một lần ⚠; hoàn tiền pass thì khóa sự kiện chưa bắt đầu (cần cho FMD A7.4, xong trước 15/2/2027) | Pass | V1 | 4 | FLC-E03-03; FLC-E08-02 | Khi mua Wedding Pass rồi tạo sự kiện thì server ghi pass cho sự kiện và app mới consume; khi pass bị hoàn tiền thì sự kiện chưa bắt đầu bị khóa; khi gửi giao dịch giả thì server từ chối; khi chủ tiệc tạo sự kiện thử thì server cấp hạn mức thử mà không có giao dịch nào, còn lần thử thứ hai của cùng tài khoản bị từ chối |

### FLC-E04 · Bản địa hóa và tên an toàn

Mục tiêu: 7 ngôn ngữ đợt 1 (vi, en, ko, ja, id, th, pt-BR); không tên nhãn hiệu nào lọt vào app hay listing; không đóng gói LUT có giấy phép share-alike.

Ánh xạ Bảng 9: C4.1 → 01 · C4.2 → 02, 03 · C4.3 → 04. Thử nghiệm listing trên Play làm bằng tay trong Play Console, không cần code.

Khối lượng: 4 feature · MVP 8,5 ngày · tổng **8,5 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FLC-E04-01 | `:core:l10n` | Hạ tầng chuỗi 7 ngôn ngữ (vi, en, ko, ja, id, th, pt-BR) cho phần lõi; chọn ngôn ngữ riêng trong app (per-app language, AppCompat cho API < 33); định dạng tiền, số, ngày theo locale; pseudo-locale test; thêm ngôn ngữ mới (ví dụ `de` khi FilCam mở thị trường Đức) chỉ cần thêm file chuỗi và chạy lại pseudo-locale test | — | MVP | 2 | FLC-E07-01 | Khi đổi ngôn ngữ trong app sang tiếng Thái thì paywall và thông báo lỗi đổi ngay mà không khởi động lại; khi chạy pseudo-locale thì không có chuỗi bị cắt ở màn lõi; khi giá là 149000 VND thì hiện "149.000 ₫" |
| FLC-E04-02 | `:core:look` | `NameGuard`: chặn nhãn hiệu trong tên look, recipe, khung, máy, board và sự kiện công khai. Danh sách gốc: phim và máy ảnh (Kodak, Portra, Ektar, Ektachrome, Kodachrome, Tri-X, T-Max, Fujifilm, Fuji, Velvia, Provia, Classic Chrome, Acros, Superia, Instax, Polaroid, Leica, Contax, Canon, Lomo, Lomography, Holga, CineStill, Ilford, Agfa), kính lọc (Tiffen, Pro-Mist), hãng và phần mềm (Blackmagic, DaVinci, Apple, iPhone, Samsung, CapCut, VSCO, Lightroom), app đối thủ (Dazz, Huji, Sora, Snap); "film simulation" chưa rõ có phải nhãn hiệu ⚠ nên chỉ cảnh báo khi dùng làm từ khóa ASO, chưa chặn; chuẩn hóa dấu, hoa thường, ký tự thay thế (0 → o), khớp theo từ nguyên vẹn; danh sách cập nhật qua remote config; gợi ý tên tự đặt; tên file nhập được giữ khi dùng riêng nhưng phải đổi khi chia sẻ | — | MVP | 1,5 | FLC-E01-01; FLC-E05-09 | Khi đặt tên "p0rtra 400" hoặc "Fuji Classic-Chrome" rồi chia sẻ thì bị chặn kèm gợi ý; khi đặt "Golden" hoặc "Classic Warm" thì được chấp nhận; khi nhập "Kodak Gold 200.cube" để dùng riêng thì tên được giữ, còn khi tạo QR thì app bắt đổi tên; khi đặt "Snapshot 1" thì được chấp nhận; khi đặt "Soft Pro-Mist" rồi chia sẻ thì bị chặn |
| FLC-E04-03 | (tools) | Lint trong CI: tên thương hiệu (danh sách của `NameGuard`) và thuật ngữ văn hóa ("Chinese New Year" → "Tết Nguyên đán / Lunar New Year") trên asset, chuỗi và metadata store; manifest nguồn gốc cho mọi LUT/look đóng gói (tác giả, ngày, giấy phép `owned`), chặn CC BY-SA, CeCILL và LUT trùng checksum các bộ HaldCLUT công khai (RawTherapee, G'MIC); danh sách ngoại lệ có lý do và người duyệt cho file chỉ nhận đầu vào hoặc chỉ gọi tên định dạng (chính danh sách của `NameGuard`; bảng map tên kiểu nền của parser công thức FMS; tên nguồn "Apple Log", "Samsung Log" trong bộ chọn nguồn của FCM ⚠ rà pháp lý); chuỗi trong file ngoại lệ không được hiện trên UI | — | MVP | 2 | FLC-E04-02 | Khi asset có khung tên "Polaroid" hoặc file chuỗi có "Chinese New Year" thì CI fail và chỉ ra file, dòng; khi thêm LUT không có manifest, có `license: CC-BY-SA-4.0` hoặc trùng checksum một HaldCLUT công khai thì CI fail; khi bảng map của parser FMS có "Velvia" thì lint cho qua vì file nằm trong danh sách ngoại lệ, còn khi chuỗi đó có trong file chuỗi UI thì CI fail |
| FLC-E04-04 | (ci) | Listing store theo thị trường: fastlane `supply` (Play) và `deliver` (App Store) cho 3 app, metadata theo locale trong repo; kiểm độ dài (tiêu đề 30, mô tả ngắn 80 ký tự) và chạy lint tên trước khi đẩy; chụp ảnh màn hình tự động theo locale | — | MVP | 3 | FLC-E04-03 | Khi chạy lane `metadata` thì listing 7 locale được đẩy lên Play; khi tiêu đề quá 30 ký tự hoặc có từ cấm thì lane dừng trước khi đẩy; khi chạy lane `screenshots` thì có đủ ảnh cho 7 locale |

### FLC-E05 · Chất lượng, thiết bị và đo lường

Mục tiêu: chạy ổn trên máy tầm trung phổ biến ở Việt Nam và Đông Nam Á; ẩn thứ máy không làm được; đo được phễu mà không phá lập trường quyền riêng tư (mục 4.1).

Ánh xạ Bảng 9: C5.1 → 01–05 · C5.2 → 06 · C5.3 → 07–09. Yêu cầu của FCM: 10 (nhiệt khi quay video).

Khối lượng: 10 feature · Có sẵn 1 ngày · MVP 16 ngày · V1 2,5 ngày · tổng **19,5 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FLC-E05-01 | `:core:camera` | Gom phần dò khả năng máy đang chạy của FilCam ("ẩn thứ máy không hỗ trợ") thành API `CameraCapabilities` | — | Có sẵn | 1 | FLC-E07-01 | Khi chạy trên các máy FilCam đang test thì kết quả dò giống bản đang phát hành |
| FLC-E05-02 | `:core:camera` | Mở rộng dò khả năng: ống kính (siêu rộng 0.5×, tele qua zoom ratio và camera vật lý), flash camera trước, fps theo độ phân giải, 10-bit/HLG và UHD (`isFeatureGroupSupported`, `isSessionConfigSupported`), RAW (`getSupportedOutputFormats`), Ultra HDR, Extensions (Night, HDR, Bokeh), low-light boost, quay tốc độ cao; cache theo build fingerprint | — | MVP | 2 | FLC-E05-01 | Khi chạy trên 8 máy ma trận thì bảng năng lực khớp kiểm tra tay; khi máy không hỗ trợ một tính năng thì tính năng đó bị ẩn khỏi UI thay vì hiện rồi báo lỗi; khi dò lần thứ hai thì kết quả lấy từ cache < 50 ms |
| FLC-E05-03 | (qa) | 🧪 Spike 2 ngày: đo fps preview 1080p (LUT + grain + halation) và thời gian xử lý ảnh 12 MP trên 8 máy ma trận bằng nguyên mẫu `:core:gpu`; chốt máy tầm trung chuẩn và ngưỡng tier A/B/C | — | MVP | 2 | FLC-E01-11 | Khi xong spike thì có bảng fps và thời gian xử lý của 8 máy, tên máy tầm trung chuẩn và ngưỡng tier được ghi vào mục 4.2 |
| FLC-E05-04 | `:core:device` | Hồ sơ hiệu năng máy (tier A/B/C) từ GPU renderer, RAM, SoC (`Build.SOC_MODEL`, API 31+) và benchmark 1 giây lần đầu; chọn độ phân giải preview và chất lượng pass theo tier; quirk theo model qua remote config; theo dõi nhiệt (`getThermalHeadroom`, API 30+) để giảm tải | — | MVP | 2,5 | FLC-E05-03; FLC-E05-09 | Khi chạy trên máy tier C thì halation tự hạ xuống ⅛ và preview vẫn ≥ 30 fps; khi remote config đặt quirk tắt Ultra HDR cho một model thì lần mở sau tính năng bị ẩn; khi nhiệt ở mức `SEVERE` thì app giảm fps preview và hiện cảnh báo |
| FLC-E05-05 | (qa) | Ma trận thiết bị và quy trình test cho mỗi bản phát hành (mục 4.4): checklist xoay, flash, ống kính, lưu ảnh, tốc độ, nhiệt, thanh toán; tối thiểu 8 máy cho FMD và FMS, 10 máy cho FCM (thêm máy tier A và B để quay 4K và HLG); chạy thêm trên device farm ⚠ | — | MVP | 3 | FLC-E07-02 | Khi phát hành một bản thì có bảng kết quả trên ≥ 8 máy (FCM ≥ 10 máy); khi bất kỳ máy nào có lỗi "không lưu được ảnh" thì bản đó không được phát hành |
| FLC-E05-06 | `:core:analytics` | Crash, ANR và hiệu năng: Crashlytics ⚠ với khóa model, tier, pass, cấu hình camera; không log đường dẫn ảnh hay tên người dùng; trace thời gian xử lý ảnh, fps preview, mở app lạnh; Macrobenchmark và Baseline Profile cho luồng mở camera | — | MVP | 3 | FLC-E07-02 | Khi app crash trong một pass render thì báo cáo có model, tier và tên pass, không có đường dẫn ảnh; khi p90 xử lý ảnh > 1,5 giây hoặc mở app lạnh vượt ngân sách mục 4.2 thì CI cảnh báo |
| FLC-E05-07 | `:core:analytics` | Facade sự kiện và phễu chung ba app: `first_open` → `capture`/`edit` → `save` → `paywall_view` → `purchase_start` → `purchase_success`/`restore`; tham số chuẩn (app, ID look dựng sẵn, tier máy, `variant`); không gửi ảnh, tên file, tên look người dùng đặt; không quyền `AD_ID` | — | MVP | 2 | FLC-E05-09 | Khi đi hết luồng chụp → lưu → paywall → mua bằng license tester thì 6 sự kiện hiện đúng thứ tự trong DebugView; khi kiểm merged manifest thì không có quyền `AD_ID` |
| FLC-E05-08 | `FilmodeCoreKit/Telemetry` | Facade analytics, crash và remote config trên iOS với cùng lược đồ sự kiện và khóa config như Android | — | V1 | 1,5 | FLC-E05-07; FLC-E07-05 | Khi đi hết luồng mua trên iOS thì có cùng 6 sự kiện với cùng tên tham số như Android; khi chạy app thì không có lời gọi API quảng cáo và không hiện hộp ATT |
| FLC-E05-09 | `:core:config` | Remote config, cờ tính năng, phân nhóm A/B: giá trị mặc định đóng gói, chạy offline, kill switch từng tính năng, danh sách từ cấm và quirk máy | — | MVP | 1,5 | FLC-E07-01 | Khi mở app lần đầu ở chế độ máy bay thì dùng giá trị mặc định và mọi tính năng miễn phí chạy; khi bật kill switch "halation" thì lần mở sau pass halation tắt; khi mạng chậm thì không màn nào phải chờ config mới hiện |
| FLC-E05-10 | `:core:device` | Nhiệt khi quay video: callback riêng khi trạng thái nhiệt lên `CRITICAL` hoặc `EMERGENCY` để app dừng ghi an toàn trước khi hệ thống cắt camera; dự báo `getThermalHeadroom(30)` cho app (cần cho FCM MVP: FCM-E07-05; FCM V1: FCM-E07-07) | — | V1 | 1 | FLC-E05-04 | Khi giả lập `CRITICAL` bằng lệnh adb của thermalservice ⚠ thì callback đến trong ≤ 1 giây và app kịp đóng file; khi headroom dự báo 30 giây ≥ 1,0 thì API báo "sắp nóng" trước khi trạng thái lên `SEVERE` |

### FLC-E06 · Quyền riêng tư, media và lưu trữ

Mục tiêu: không xin quyền thừa; lưu ảnh không bao giờ hỏng (đây là lỗi đầu tiên người dùng báo ở cả Filmode Vibe và FilCam); EXIF đúng; khai báo minh bạch.

Ánh xạ Bảng 9: C6.1 → 01, 02, 05, 07 · C6.2 → 03, 04 · C6.3 → 06. Yêu cầu của FCM: 08 (lưu file sidecar).

Khối lượng: 8 feature · MVP 8,5 ngày · V1 5,5 ngày · tổng **14 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FLC-E06-01 | `:core:media` | Mở ảnh và video bằng Photo Picker (`PickVisualMedia`, bản backport qua Google Play services, dự phòng `ACTION_OPEN_DOCUMENT`); CI chặn `READ_MEDIA_IMAGES`, `READ_MEDIA_VIDEO`, `READ_EXTERNAL_STORAGE` trong merged manifest | Free | MVP | 1 | FLC-E07-02 | Khi build release thì bước kiểm manifest không thấy quyền `READ_MEDIA_*`; khi chạy trên Android 8 thì vẫn chọn được ảnh; khi chọn 20 ảnh thì nhận đủ 20 URI |
| FLC-E06-02 | `:core:media` | Lưu ảnh và video vào MediaStore trong album tên rõ (`Pictures/Filmode`, `Pictures/FilCam`, `Pictures/Filmode Studio`) với `IS_PENDING`; JPEG, HEIF, PNG; hàng đợi lưu bền (WorkManager) để không mất ảnh; `WRITE_EXTERNAL_STORAGE` chỉ cho API ≤ 28; thông báo "Đã lưu vào album …" có nút mở | Free | MVP | 2,5 | — | Khi chụp 100 ảnh liên tiếp rồi kill app ngay sau ảnh cuối thì mở lại thấy đủ 100 ảnh trong album và không còn file rác `IS_PENDING`; khi chạy trên Android 8–9 thì lưu được sau khi cấp quyền; khi lưu lỗi thì app hiện lý do và nút thử lại |
| FLC-E06-03 | `:core:media` | EXIF: giữ EXIF gốc (máy, thời gian, phơi sáng, hướng) khi áp look, thêm thẻ `Software`; xử lý hướng nhất quán; tùy chọn xóa vị trí khi chia sẻ (mặc định bật); chỉ xin `ACCESS_MEDIA_LOCATION` khi người dùng bật giữ vị trí cho ảnh nhập | Free | MVP | 2 | FLC-E06-02 | Khi áp look cho JPEG có EXIF đầy đủ thì ảnh xuất giữ `DateTimeOriginal`, `Make`, `Model`, ISO, có `Software` và không bị xoay hai lần; khi chia sẻ với "xóa vị trí" bật thì exiftool không thấy thẻ GPS nào, còn ảnh trong album không bị sửa |
| FLC-E06-04 | `:core:media` | Xuất Ultra HDR: áp look lên ảnh nền SDR và chỉnh gain map tương ứng (`Gainmap`, API 34+ ⚠), dự phòng SDR (cần cho FMS B7.1, FMD A2.4) | Free | V1 | 2,5 | FLC-E01-15; FLC-E06-02 | Khi xuất ảnh Ultra HDR có look trên máy hỗ trợ thì Google Photos hiện ảnh HDR và vùng sáng không đổi màu so với bản SDR; khi máy không hỗ trợ thì xuất JPEG SDR bình thường |
| FLC-E06-05 | `:core:camera` | Luồng xin quyền camera và micro: giải thích trước khi hỏi, xử lý "không hỏi lại", mở Cài đặt; micro chỉ xin khi quay có tiếng; không crash khi bị từ chối | — | MVP | 1 | FLC-E07-06 | Khi từ chối quyền camera hai lần thì app hiện màn hướng dẫn mở Cài đặt, không crash và vẫn vào được phần không cần camera; khi chỉ chụp ảnh thì app không bao giờ hỏi quyền micro |
| FLC-E06-06 | `:core:analytics` | Minh bạch (mục 4.1): mẫu Data safety và nhãn App Privacy, trang quyền riêng tư VI/EN; màn Cài đặt để tắt analytics và crash report, xem và xóa dữ liệu cloud; hỏi đồng ý trước ở EEA/UK ⚠ | — | MVP | 2 | FLC-E05-06; FLC-E05-07 | Khi so khai báo Data safety với danh sách SDK và sự kiện thì khớp 100%; khi tắt "Chia sẻ dữ liệu sử dụng" thì proxy không thấy request analytics hay crash nào |
| FLC-E06-07 | `FilmodeCoreKit/MediaKit` | PhotosPicker (không xin toàn bộ thư viện), lưu add-only vào album tên rõ, EXIF giữ và xóa GPS khi chia sẻ bằng ImageIO | Free | V1 | 2 | FLC-E07-05 | Khi lưu ảnh lần đầu thì iOS chỉ hỏi quyền "Chỉ thêm ảnh"; khi chia sẻ với "xóa vị trí" bật thì ảnh không còn GPS |
| FLC-E06-08 | `:core:media` | Lưu file không phải media (`.cube`, `.flook`, `.json`) cạnh ảnh và video: qua `MediaStore.Files` vào `Documents/<tên app>/` ⚠, dùng cùng hàng đợi bền và `IS_PENDING` như FLC-E06-02; trả URI để app nối file với clip (cần cho FCM MVP: sidecar FCM-E02-11; FCM V1: FCM-E04-06) | Free | V1 | 1 | FLC-E06-02 | Khi quay xong một clip ghi sạch thì ba file sidecar nằm trong `Documents/FilCam/` và mở được bằng app quản lý file; khi kill app giữa lúc lưu thì không còn file rác `IS_PENDING`; app không cần quyền đọc bộ nhớ nào |

### FLC-E07 · Nền tảng build, CI và kiểm thử

Epic mới, không có trong Bảng 9 (lý do ở mục 6).

Khối lượng: 6 feature · MVP 11,5 ngày · V1 2 ngày · tổng **13,5 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FLC-E07-01 | `build-logic` | Repo Android chung: version catalog, convention plugin, module `:core:*`, 3 app shell `:app:filmode`, `:app:studio`, `:app:filcam`; minSdk 26, targetSdk 36 ⚠, GLES 3.0 bắt buộc; kiểm đồ thị module | — | MVP | 2 | — | Khi chạy `./gradlew bundleRelease` thì ra 3 AAB; khi một module `:core:*` phụ thuộc module app thì build fail |
| FLC-E07-02 | (ci) | CI mỗi PR: build, unit test, lint, kiểm manifest, lint tên, so free-tier; phát hành: ký qua Play App Signing, đẩy AAB lên internal track, staged rollout, tải mapping R8 | — | MVP | 3 | FLC-E07-01 | Khi PR làm hỏng unit test hoặc thêm `READ_MEDIA_IMAGES` thì CI fail; khi gắn tag `fmd-v2.0.0` thì AAB của Filmode lên internal track mà không cần thao tác tay |
| FLC-E07-03 | `:core:testing` | Golden image: bộ ảnh chuẩn (ColorChecker, ramp xám, da người, cảnh đêm, ảnh 12 MP); render qua đường preview và đường xuất trên máy thật mỗi đêm (device farm ⚠); so ΔE và PSNR; đính kèm ảnh diff | — | MVP | 2,5 | FLC-E01-09; FLC-E07-02 | Khi một PR làm output của một look lệch ΔE trung bình > 1 thì job golden fail và đính kèm ảnh diff; khi so đường preview với đường xuất của cùng khung thì lệch nằm trong ngưỡng |
| FLC-E07-04 | (tools) | `look-cli` (JVM, dùng lại `:core:look` và `:core:lut-io`): kiểm, chuyển đổi, đóng gói `.flook`, render bằng pipeline CPU; bộ fixture chung Kotlin và Swift trong `spec/look/` | — | MVP | 2 | FLC-E01-02; FLC-E01-06 | Khi chạy `look-cli pack look.json look.cube` thì ra `.flook` hợp lệ; khi chạy `look-cli check assets/` thì liệt kê mọi look thiếu manifest hoặc có tên vi phạm |
| FLC-E07-05 | `FilmodeCoreKit` | Swift package `FilmodeCoreKit` (Swift 6 strict concurrency, iOS 17+ ⚠) gắn vào project Filmode iOS đang chạy; CI macOS build và test | — | V1 | 2 | — | Khi build Filmode iOS với package thì không có cảnh báo concurrency; khi mở PR thì CI chạy test của mọi target |
| FLC-E07-06 | `:core:ui` | Design system Compose: theme sáng tối, token màu, chữ, khoảng cách, override theo app; component nút, sheet, toast, màn lỗi, màn báo cáo nhập; hỗ trợ TalkBack và cỡ chữ lớn | — | MVP | 2 | FLC-E07-01 | Khi bật cỡ chữ 200% hoặc TalkBack thì mọi màn lõi (paywall, nhập, báo cáo, quyền) vẫn dùng được |

### FLC-E08 · Hạ tầng cloud dùng chung

Epic mới, không có trong Bảng 9 (lý do ở mục 6). Board và sự kiện là tính năng của FMD; lõi chỉ lo nền chung. FLC-E08-04 (báo lỗi theo máy, trang danh sách máy) là yêu cầu của FCM.

Khối lượng: 4 feature · Có sẵn 1 ngày · V1 8,5 ngày · tổng **9,5 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FLC-E08-01 | (backend) | Khảo sát backend Cloud Boards đang chạy (dịch vụ, schema, rules, chi phí, web app) ⚠; quyết định dùng lại hay chuyển | — | Có sẵn | 1 | — | Khi xong khảo sát thì có tài liệu dịch vụ, schema, quy tắc bảo mật, chi phí tháng hiện tại và quyết định dùng lại hay chuyển |
| FLC-E08-02 | (backend) | Backend chung (đề xuất Firebase: Auth, Firestore, Cloud Storage, Functions, Hosting ⚠): môi trường dev và prod, security rules theo tài khoản, hạn mức upload mỗi người, cảnh báo ngân sách, dung lượng theo tính năng (board, sự kiện, đồng bộ); `assetlinks.json` và `apple-app-site-association` trên `filmode.app`; tài khoản ẩn danh cho khách web (Anonymous Auth ⚠) và App Check (reCAPTCHA Enterprise cho web, Play Integrity cho Android ⚠) (cần cho FMS MVP; FMD A7 xong trước 15/2/2027) | — | V1 | 4 | FLC-E08-01 | Khi người dùng A đọc dữ liệu của B bằng request tự dựng thì rules từ chối (test trên emulator); khi chi phí tháng vượt 80% ngân sách thì có email cảnh báo; khi khách mở trang sự kiện mà không đăng nhập thì nhận token ẩn danh không có email hay số điện thoại; khi script không qua App Check gọi function tải ảnh thì bị từ chối |
| FLC-E08-03 | (backend) | API look công khai: tải `.flook` (≤ 10 MB) → ID ngắn 8 ký tự → link `filmode.app/l/<id>`; chạy `NameGuard` phía server; giới hạn tần suất; gỡ theo báo cáo hoặc khiếu nại (endpoint quản trị); từ chối tải lên công khai look có `license` là `personal` hoặc `unknown` kèm `lut.cube` (cần cho FMS B8.1) | Free | V1 | 3 | FLC-E08-02; FLC-E04-02 | Khi tải lên look tên "Portra 400" thì server trả lỗi 422 kèm lý do; khi mở link trên máy khác chưa đăng nhập thì tải được look; khi quản trị gỡ look thì link hiện "Look đã bị gỡ"; khi tải lên look có `license: personal` kèm `lut.cube` (kể cả từ bản app cũ) thì server trả 422 và không lưu file |
| FLC-E08-04 | (backend) | Báo lỗi theo máy và trang danh sách máy: endpoint nhận báo cáo (model, SoC, bản Android, tier, bảng năng lực, log đã lọc; không ảnh, không đường dẫn), giới hạn tần suất theo bản cài, xóa sau 90 ngày ⚠; hosting trang tĩnh `filmode.app/filcam/devices` sinh bằng script từ kết quả ma trận (cần cho FCM MVP: FCM-E07-04; FCM V1: FCM-E07-08) | — | V1 | 1,5 | FLC-E08-02 | Khi một bản cài gửi báo cáo vượt hạn mức (mặc định 5 báo cáo mỗi giờ ⚠) thì server trả 429; khi báo cáo có chuỗi giống đường dẫn file thì server bỏ trường đó trước khi lưu; khi script đẩy danh sách mới thì trang `filmode.app/filcam/devices` cập nhật mà không sửa tay |

## 8. Lộ trình

Khớp Bảng 13 của báo cáo và [lịch cả họ app](README.md#lịch-và-nhân-sự-cả-họ-app). Số ngày là ngày công của lõi, chưa gồm việc của app. Mục `V1` được xếp theo ngày app cần, không theo quý.

| Giai đoạn (Bảng 13) | Xong trước | Việc của lõi | Ngày công lõi |
|---|---|---|---|
| 0. Sửa nền | 23/10/2026 | Làm ngay trên code đang chạy, rồi chuyển vào module ở giai đoạn 1: FLC-E06-02 (lưu ảnh không lỗi), FLC-E04-02 và FLC-E04-03 (danh sách từ cấm; đổi khung "Polaroid" thành "Instant"), FLC-E04-04 (listing, tiêu đề mới), FLC-E03-08 (bảng giá VN theo vùng). Đổi danh mục Play sang Photography là thao tác tay | 11 |
| 1. Lõi và App 1 | 15/1/2027 (FMD S6; ra mắt 18/1) | Mọi mục `Có sẵn` và `MVP` còn lại: định dạng look, pipeline GPU, `EffectPass` có lịch sử khung, camera có flash màn hình, thư viện, billing, paywall, ngôn ngữ, đo lường, CI | 94 (87,5 MVP + 6,5 Có sẵn) |
| 2. Studio Android (FMS S1–S6, 4/1–26/3/2027) | Theo sprint FMS cần: FLC-E01-27 trong S1 (4–15/1); FLC-E01-28, FLC-E02-11, FLC-E08-02 trước S2 (18/1); FLC-E01-05, -07, -08 trước S3 (1/2); FLC-E02-08 trước S4 (15/2); FLC-E06-04 trước S5 (1/3) | Mở rộng định dạng look, ba trường `adjust`, tông nền dùng chung, backend, bộ nhập HALD/.3dl/zip/XMP/DNG, deep link và trang `/r`, Ultra HDR | 20,5 |
| 2a. Sự kiện FMD (V1-a từ 15/2/2027) | 15/2/2027 | FLC-E01-23 (WebGL2), FLC-E03-10 (xác minh pass, sự kiện thử); FLC-E08-02 đã có ở dòng trên | 7,5 |
| 2b. Lõi iOS; Filmode iOS chuyển lõi; Studio iOS | 2/4/2027 (Studio I1 từ 5/4); FLC-E01-32 trước 17/5 (Studio I4) | FLC-E07-05, FLC-E01-24, FLC-E01-25, FLC-E01-26, FLC-E02-10, FLC-E03-09, FLC-E05-08, FLC-E06-07, FLC-E01-32. Dev iOS bắt đầu FLC-E07-05 từ T12/2026; FLC-E01-24 làm sau FLC-E01-27 | 25 |
| 3. FilCam (từ 5/4/2027) | 19/4/2027 (FCM S2) | FLC-E01-19 (xuất .cube cho sidecar), FLC-E01-20 (chuỗi LUT), FLC-E01-21 (Media3, cũng cần cho video FMD A4), FLC-E02-09 (thư viện dùng chung), FLC-E01-29 (hai `CameraEffect`), FLC-E01-30 (`previewOnly`), FLC-E05-10 (nhiệt), FLC-E06-08 (lưu sidecar), FLC-E08-04 (báo lỗi theo máy) | 15,5 |
| V1 của từng app | Theo lịch V1 của app | FLC-E08-03 (link look cloud, trước FMS S9 3/5/2027), FLC-E01-22 (tông da, trước FMD V1-c 10/5 và FMS S11 31/5), FLC-E01-31 (đường 10-bit, trước FCM S10 23/8), FLC-E02-07 (đồng bộ iOS, trước Filmode iOS V1-iOS-b T7/2027), FLC-E02-06 (đồng bộ, trước FCM S13 4/10) | 14 |
| 4. Chợ creator | Nửa cuối 2027 | Chưa có mục lõi mới; dùng lại FLC-E08-03 | 0 |
| **Tổng** | | | **187,5** |

**Nhân sự.** Giai đoạn 1 (26/10/2026–15/1/2027, 12 tuần) có 94 ngày lõi cộng 92,5 ngày Android và công cụ của Filmode (FMD S1–S6), tức 186,5 ngày công. Ba dev Android có khoảng 177 ngày danh nghĩa trong 12 tuần (trừ ngày 1/1). Vì vậy lõi cần **3 dev Android + 1 dev Android hợp đồng khoảng 8 tuần (S2–S5) + tester thiết bị 50% + dev iOS 50%**, như [Filmode mục Nhân sự](01-filmode/epics-features.md#nhân-sự) tính. Chỉ có 3 dev mà không có dev hợp đồng thì phải áp cut-line của lõi (6,5 ngày) và của app (10 ngày), còn 170 ngày, gần hết công suất. Chỉ có 2 dev Android thì bản dựng lại không kịp Tết; phương án dự phòng ở [README chung](README.md#lịch-và-nhân-sự-cả-họ-app).

Sau ngày ra mắt Filmode (18/1/2027), phần `V1` của lõi dồn vào T1–T4/2027: khoảng 20,5 ngày cho Studio, 7,5 ngày cho sự kiện, 15,5 ngày cho FilCam và 25 ngày iOS. Người làm: dev A (GPU, camera) làm bộ nhập, Ultra HDR và các mục cho FilCam; dev B (thư viện) làm FLC-E02-08, FLC-E02-11; dev Android mới của Studio (dev D, từ 4/1/2027) làm FLC-E01-27, FLC-E01-28 trong FMS S1–S2; dev web/backend (từ 11/1/2027) làm FLC-E08-02, FLC-E03-10, FLC-E01-23, FLC-E08-03, FLC-E08-04; dev iOS làm toàn bộ phần iOS. Chủ module lõi review mọi thay đổi `:core:*` do dev app làm.

Báo cáo ước "định dạng look 3–5 tuần-người". Phần tương ứng ở đây (FLC-E01-01 đến FLC-E01-04, FLC-E01-06, FLC-E02-01, FLC-E02-03, FLC-E07-04) là 14,5 ngày, cộng 7,5 ngày `V1` cho bộ nhập mở rộng và phần mở rộng định dạng (FLC-E01-05, -07, -08, -27), tức khoảng 4,5 tuần-người. Hai con số khớp nhau.

**Cut-line của lõi** (dùng khi giai đoạn 1 chỉ có 3 dev Android, không có dev hợp đồng; dời sang V1, tổng khoảng 6,5 ngày): FLC-E03-07 thử giá A/B (1,5); FLC-E01-18 Match v1 (3; vẫn phải xong trước FMS S5 1/3/2027 vì Match v1 là MVP của Studio, còn Match Photo trên Android của FMD lùi sang bản MVP.1); phần chụp màn hình tự động của FLC-E04-04 (khoảng 1); chạy golden hằng đêm của FLC-E07-03 đổi thành chạy tay trước khi phát hành (khoảng 1). **Không được cắt:** FLC-E06-02 (lưu ảnh), FLC-E03-03 và FLC-E03-04 (khôi phục, không thu hồi), FLC-E03-06 (paywall tuân thủ), FLC-E04-02 và FLC-E04-03 (tên an toàn), FLC-E06-01 (Photo Picker), phần lịch sử khung của FLC-E01-11 (Flash Drift là máy chữ ký của bản Tết).

## 9. Chỗ lệch so với Bảng 9

| Mục trong báo cáo | Báo cáo | Backlog lõi | Lý do |
|---|---|---|---|
| C1.2 Bộ nhập | MVP | .cube và preset đang chạy là `Có sẵn` (FLC-E01-04); HALD, .3dl, zip, XMP/DNG có báo cáo là `V1` (FLC-E01-05, -07, -08) | Filmode Vibe đã nhập .cube và preset; phần mở rộng cần cho Studio MVP (Q1/2027), ngay sau giai đoạn 1 |
| C1.4 Pipeline iOS | V1 | `V1`, kèm toàn bộ phần iOS khác của lõi (định dạng, thư viện, StoreKit 2, media, telemetry) | Filmode iOS giữ code đang chạy tới khi chuyển sang lõi cùng lúc với Studio iOS |
| C2.1 Khôi phục mua | MVP, trong C2 | FLC-E03-03, trong epic thanh toán | Cùng module `:core:billing` |
| C2.2 Đăng nhập tùy chọn | V1 | Xóa tài khoản là `MVP` (FLC-E02-05) | Filmode Vibe đã có đăng nhập Google cho board |
| C3.1 Pass sự kiện | MVP | Mua pass nằm trong FLC-E03-02 (`MVP`); xác minh server và consume là `V1` (FLC-E03-10) | Chế độ sự kiện của FMD (A7) là V1 |
| B4.1 Match v1 (App 2) | MVP của Studio | Thuật toán ở lõi, FLC-E01-18, `MVP`; bản Swift FLC-E01-32, `V1` | Match Photo trên Android của FMD (A11.1) là MVP; Studio MVP (FMS-E04-01) và FCM F6.2 cũng dùng; Studio iOS và Filmode iOS phải ra cùng kết quả với Android |
| B5.1 Bảo vệ tông da (App 2), photobooth (App 1) | Ở app | FLC-E01-22, `V1` | Hai app dùng cùng tách nền người |
| A2.4, B7.1 Ultra HDR | Ở app | FLC-E06-04, `V1` | Hai app dùng |
| A7.2 Web camera sự kiện | Ở App 1 | Renderer WebGL2 ở lõi, FLC-E01-23, `V1` | Để web camera dùng đúng định dạng look |
| B2.1 Mô hình công thức (App 2) | Ở app | Ba trường `adjust` mới và tông nền dùng chung ở lõi (FLC-E01-27, -28, FLC-E02-11) | Để QR công thức của Studio ra cùng màu trong cả ba app |
| F2.3 Ghi sạch + LUT xem, F3 Log/HDR (App 3) | Ở app | Hai `CameraEffect`, `previewOnly`, đường 10-bit, lưu sidecar, nhiệt khi quay ở lõi (FLC-E01-29…31, FLC-E05-10, FLC-E06-08) | Là phần của wrapper camera, đồ thị pass và media; FMD sẽ dùng khi quay video dài |
| A3 Ảnh động (App 1) | Ở app | Ở FMD (`:filmode:motion`), không vào lõi | Chỉ Filmode dùng (mục 1.1) |
| — | — | Epic mới FLC-E07, FLC-E08 | Xem mục 6 |

## 10. Rủi ro, spike và việc cần xác minh

| Rủi ro | Ảnh hưởng | Cách xử lý |
|---|---|---|
| Lõi 94 ngày cộng Filmode 92,5 ngày trong 12 tuần của giai đoạn 1 | Lỡ Tết Nguyên đán 2027 | 3 dev Android + dev hợp đồng 8 tuần; cut-line ở mục 8; giai đoạn 0 làm trên code đang chạy; chỉ có 2 dev thì theo phương án dự phòng ở README chung |
| Phần `V1` của lõi cho Studio, sự kiện, iOS và FilCam (khoảng 68,5 ngày) dồn vào T1–T4/2027, cùng lúc Studio MVP, sự kiện FMD và FilCam | Studio hoặc FilCam trễ vì chờ lõi | Làm theo hạn ở mục 8; dev D, dev web/backend và dev iOS vào từ T1/2027; theo dõi hạn lõi ở mỗi buổi lập kế hoạch sprint của app |
| CameraX ép stream sharing hoặc không nhận hai effect trên một số máy ⚠ | Mất "ghi sạch + LUT xem" của FilCam | FLC-E01-29 báo trước khi bind; spike FCM-E02-01; recorder dự phòng FCM-E02-17 |
| Code đang chạy khó tách thành module hơn dự tính ⚠ | Mục `Có sẵn` vượt ước tính | Đọc code tuần đầu, ước lại trước khi chốt sprint |
| GPU Mali/PowerVR thiếu `highp`; GLES chạy qua ANGLE trên máy Android 15+ | Lệch màu, banding, preview khác ảnh xuất | Golden test trên ma trận (FLC-E07-03); spike FLC-E05-03 |
| XMP → LUT lệch so với Lightroom | Người dùng thấy "không giống" | Spike FLC-E01-07; báo cáo chuyển đổi; ghi rõ là bản gần đúng |
| Gom ba app vào một repo làm vỡ bản đang chạy | Mất LUT, công thức, board khi cập nhật | FLC-E02-03 chuyển dữ liệu; staged rollout (FLC-E07-02) |
| Ba app không cùng chứng chỉ ký | Không chia sẻ thư viện qua provider | Chốt khóa ký trước khi phát hành Studio; dự phòng bằng intent và đồng bộ (FLC-E02-08, FLC-E02-06) |
| Chi phí lưu trữ khi sự kiện và đồng bộ tăng | Chi phí vượt doanh thu | Hạn mức mỗi người, cảnh báo ngân sách (FLC-E08-02) |
| Người dùng đặt tên nhãn hiệu cho look công khai | App bị gỡ vì vi phạm nhãn hiệu | `NameGuard` ở app và server; gỡ theo khiếu nại (FLC-E08-03) |

**Spike:** FLC-E01-07 (độ lệch XMP → LUT, 1 ngày) và FLC-E05-03 (hiệu năng trên 8 máy, 2 ngày). FLC-E05-03 làm ngay khi có nguyên mẫu đồ thị pass, trước khi chốt tier.

**Việc cần xác minh ⚠** (xong trong sprint đầu của giai đoạn 1, trừ ghi chú khác):
- Code đang chạy: ngôn ngữ, UI (Compose hay View), preview dùng CameraX hay Camera2, minSdk thật của Filmode Vibe, backend của Cloud Boards.
- targetSdk mà Play bắt buộc lúc phát hành (dự kiến API 36); lịch ngừng các bản Play Billing Library cũ; tên API của PBL 8 (tự kết nối lại, `showInAppMessages`).
- `SingleColorLut` của Media3: nội suy gì, nhận đầu vào tuyến tính hay gamma.
- `Gainmap` (API 34) cho Ultra HDR JPEG; Ultra HDR trong HEIC (API 36).
- Hành vi App Links khi nhiều app cùng xác minh một đường dẫn; Universal Links cho nhiều app iOS.
- Dùng chung một khóa ký cho ba app khi bật Play App Signing (cần cho signature permission).
- Phân loại Firebase Analytics và Crashlytics trong Data safety và App Privacy; có phải hỏi đồng ý ở EEA/UK không.
- Quy định đăng nhập của Apple khi app có đăng nhập Google (Guideline 4.8); yêu cầu xóa tài khoản của Play (trong app và qua web).
- Play Developer API để đặt giá theo vùng và giữ giá cũ cho người đang thuê bao.
- Sức chứa QR phiên bản 20 mức M; cạnh tối thiểu của QR in trên thẻ công thức.
- Ngưỡng Play Vitals cho crash và ANR.
- iOS tối thiểu: Filmode iOS đang khai iOS 13.0+; package mới đề xuất iOS 17+. Cần xem tỉ lệ người dùng iOS < 17 trước khi nâng.
- Model cụ thể của máy OPPO và Vivo trong ma trận.
- Flash màn hình của CameraX (`FLASH_MODE_SCREEN`, `ScreenFlashView`) cho FLC-E01-16.
- Hai `CameraEffect` với target riêng và điều kiện CameraX tự bật stream sharing (FLC-E01-29); `SurfaceProcessor` với luồng HLG 10-bit (FLC-E01-31).
- Anonymous Auth và App Check cho web (reCAPTCHA Enterprise) và Android (Play Integrity) trên nền backend đã chọn (FLC-E08-02).
- `MediaStore.Files` vào `Documents/` cho file không phải media trên API 29+ (FLC-E06-08).
- "Film simulation" có phải nhãn hiệu đăng ký không (FLC-E04-02); tên tiếng Anh "Classic Negative", "Nostalgic Negative" của hai tông nền Studio.

## 11. Yêu cầu của app đã đưa vào lõi

Ba app ghi yêu cầu với lõi ở mục "Điều chỉnh lõi" của `epics-features.md` ([FMD](01-filmode/epics-features.md#điều-chỉnh-lõi), [FMS](02-filmode-studio/epics-features.md#điều-chỉnh-lõi), [FCM](03-filcam/epics-features.md#điều-chỉnh-lõi)). Bảng dưới là cách lõi xử lý từng yêu cầu. "Mở rộng" là sửa mô tả, tiêu chí nghiệm thu và có thể cả số ngày của feature đã có; "mới" là feature thêm vào cuối epic.

| App, # | Yêu cầu | Lõi xử lý | Ưu tiên | Ngày thêm |
|---|---|---|---|---|
| FMD #1 | `EffectPass` xin các khung đầu ra trước đó và thời điểm trong clip | Mở rộng FLC-E01-11 | MVP | 1 |
| FMD #2 | Móc mã hóa lại JPEG trước khi lưu (khối JPEG của máy CCD, VGA) | Mở rộng FLC-E01-15; chất lượng JPEG truyền cho FLC-E06-02 | MVP | 0,5 |
| FMD #3 | Chữ date stamp do app cung cấp (âm lịch, OSD và timecode DV) | Mở rộng FLC-E01-14 (`DateStampFormatter`, `x-<app>:<tên>`) | MVP | 0,5 |
| FMD #4 | Flash màn hình của CameraX, khung trước flash và khung flash | Mở rộng FLC-E01-16 | MVP | 0,5 |
| FMD #5 | Ai sở hữu trình ghi Motion Photo | Không đổi lõi: FMD sở hữu (mục 1.1) | — | 0 |
| FMD #6 | Tài khoản ẩn danh cho khách web và App Check | Mở rộng FLC-E08-02 | V1 | 1 |
| FMD #7 | Sự kiện thử miễn phí không cần giao dịch; hoàn tiền khóa sự kiện chưa bắt đầu | Mở rộng FLC-E03-10 | V1 | 0,5 |
| FMD #8 | Map SKU đổi tên ("Pro-Mist" → "Soft Mist") và SKU ngừng bán (3 tháng iOS) | Mở rộng FLC-E03-04 | MVP | 0 |
| FMD #9 | WebGL2 xong trước pilot sự kiện | FLC-E01-23 xếp hạn 15/2/2027 (mục 8) | V1 | 0 |
| FMS #1 | `adjust.colorDepth`, `colorDepthBlue`, `toneRange`, khóa ngắn, render giống nhau trên GPU, CPU, WebGL, Metal | Mới FLC-E01-27 (định dạng), FLC-E01-28 (GPU, CPU); mở rộng FLC-E01-23 (WebGL), FLC-E01-24 (Swift), FLC-E01-26 (Metal) | V1 | 3 |
| FMS #2 | 16 tông nền `fm:base/*` có trong cả ba app hoặc tải được | Mới FLC-E02-11; mở rộng FLC-E02-10 (iOS) | V1 | 1,5 |
| FMS #3 | Match v1 bản Swift trong `LUTIO` | Mới FLC-E01-32 | V1 | 2 |
| FMS #4 | Server từ chối tải lên công khai look `license: personal` | Mở rộng FLC-E08-03; FLC-E02-09 chỉ chia sẻ trong máy | V1 | 0,5 |
| FMS #5 | Lược đồ `x-fms` trong `spec/look/` | FLC-E01-27 | V1 | (trong FMS #1) |
| FMS #6 | `origin.importedFrom: "text"` | FLC-E01-27 | V1 | (trong FMS #1) |
| FMS #7 | Trang `/r` đọc `x-fms.recipe`, nhận `?app=fms` | Mở rộng FLC-E02-08 | V1 | 0,5 |
| FMS #8 | Chuyển `:studio:raw` vào lõi khi FilCam cần | Chưa làm (mục 1.1) | — | 0 |
| FMS #9 | Lint tên cho phép riêng bảng map tên kiểu nền của parser (chỉ nhận đầu vào) | Mở rộng FLC-E04-03 (danh sách ngoại lệ) | MVP | 0 |
| FCM #1 | Hai `CameraEffect` theo target, báo stream sharing, `Camera2CameraControl`; luồng HLG 10-bit | Mới FLC-E01-29; phần HLG ở FLC-E01-31 | V1 | 2,5 |
| FCM #2 | Cờ `previewOnly` và điểm cắm trước LUT sáng tạo | Mới FLC-E01-30 | V1 | 1 |
| FCM #3 | `inputTransform.from` thêm `hlg`; `fm-log` trỏ tới đặc tả FM-Log v1 | FLC-E01-27; tên nguồn FM-Log 10-bit để V2 của FCM | V1 | (trong FMS #1) |
| FCM #4 | Xuất .cube có trước FilCam MVP | FLC-E01-19 ghi "cần cho FCM MVP", xếp vào giai đoạn 3 (mục 8) | V1 | 0 |
| FCM #5 | `LookGlEffect` nhận đầu vào 10-bit, chạy sau tone map HDR → SDR | Mới FLC-E01-31 | V1 | 2 |
| FCM #6 | API lưu file sidecar (`.cube`, `.flook`, `.json`) | Mới FLC-E06-08 | V1 | 1 |
| FCM #7 | Dò thêm năng lực video (TONEMAP, encoder, hai nhánh) | Không đổi lõi: ở FCM-E07-01 (mục 1.1) | — | 0 |
| FCM #8 | Callback nhiệt `CRITICAL`, dự báo headroom | Mới FLC-E05-10 | V1 | 1 |
| FCM #9 | Mục FilCam trong `free-tier.json` | Mở rộng FLC-E03-04 (mỗi app một mục) | MVP | 0 |
| FCM #10 | Endpoint báo lỗi theo máy; hosting trang danh sách máy | Mới FLC-E08-04 | V1 | 1,5 |
| FCM #11 | Thêm máy tier A/B vào ma trận | Mở rộng FLC-E05-05 và mục 4.4 | MVP | 0 |
| FCM #12 | Tiếng Đức khi mở thị trường DE | Mở rộng FLC-E04-01 (thêm locale chỉ là thêm file chuỗi) | MVP | 0 |
| **Tổng** | | | | **MVP 2,5; V1 18** |

Danh sách nhãn hiệu của `NameGuard` (FLC-E04-02) gộp mọi tên các app đã nêu: Kodak, Portra, Ektar, Fujifilm, Fuji, Velvia, Provia, Classic Chrome, Polaroid, Instax, Leica, Contax, Canon, Lomo, Lomography, Holga, CineStill, Ilford, Tiffen, Pro-Mist, Blackmagic, DaVinci, Apple, Samsung, CapCut, VSCO, Lightroom, Dazz, Sora, Snap và các tên đã có trước. "Film simulation" là từ khóa ASO chưa rõ có phải nhãn hiệu ⚠: lint chỉ cảnh báo, chưa chặn.
