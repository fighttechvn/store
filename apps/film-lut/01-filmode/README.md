# 01 · Filmode: máy ảnh digicam, film và sự kiện (mã `FMD`)

Filmode là app chụp ảnh "có vibe" cho Gen Z: mở app là vào kính ngắm của một chiếc máy có tính cách (digicam CCD đầu 2000, máy phim ngắm-chụp, máy dùng một lần, máy lấy liền, máy đồ chơi, điện thoại đời đầu, máy quay DV), mỗi máy có một **hiệu ứng chữ ký** đủ lạ để khoe lên TikTok. App có ảnh động thật cho Android, cuộn phim tráng trễ và **chế độ sự kiện** cho đám cưới, bữa tiệc (khách quét QR, chụp trong trình duyệt, không cài app).

App dựng lại trên [Filmode Core](../filmode-core.md) (`FLC`) từ hai listing đang có: **Filmode Vibe** trên Google Play (`app.filmode`) và **Filmode - Film & LUT Editor** trên App Store (id 6791145420, bundle `app.filmode`). Quy ước ID, ưu tiên, gói và ước tính theo [README chung](../README.md). Nguồn: [báo cáo](../../../reports/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u.md) mục "App 1 — Filmode" và Bảng 8, 10, 13; ghi chú nghiên cứu trong `research_notes/App camera film và LUT màu/`.

| File | Nội dung |
|---|---|
| [epics-features.md](epics-features.md) | 13 epic, 123 feature, gói, ước tính, phụ thuộc, tiêu chí nghiệm thu, lộ trình sprint, nhân sự, điều chỉnh lõi |
| [backlog.csv](backlog.csv) | Cùng danh sách feature dạng CSV để nhập Jira, Linear hoặc GitHub Projects |

## 1. Tóm tắt

- **Vấn đề:** người dùng Android tìm "Dazz cho Android" nhưng Dazz không có bản Android chính chủ; các app Android lớn (ProCCD, Kapi, OldRoll) có quảng cáo, paywall hồi tố, và thiếu những thứ "như iPhone": ảnh động thật, 0.5×, flash cho selfie, ảnh lưu giống kính ngắm.
- **Cơ hội:** "digicam" tăng 5,96 lần toàn cầu (19 lần ở Mỹ, 13,7 lần ở Indonesia) và đang ở đỉnh 5 năm vào T8–9/2026. Việt Nam có 8 app màu film trong top 100 grossing iOS. POV cho thấy app sự kiện thu $80k/tháng chỉ từ 100 nghìn lượt tải Android.
- **Lời hứa:** "Máy digicam và film thật sự cho điện thoại của bạn. Không quảng cáo, không watermark, thử mọi máy trước khi trả tiền, không bao giờ lấy lại thứ đã cho."
- **Hiện trạng:** kỹ thuật khó nhất đã có (LUT 64³ trên GPU ngay kính ngắm, 10 hiệu ứng thời gian thực, tách nền người, Cloud Boards). Phân phối gần như bằng 0: 69 lượt cài trên Play, xếp nhầm danh mục Productivity, không vào top 30 từ khóa nào.
- **Lịch:** giai đoạn 0 (sửa nền) 5–23/10/2026; bản dựng lại trên lõi 26/10/2026 – 15/1/2027, ra mắt 18/1/2027 kịp Tết Nguyên đán (Mùng 1 Tết là 6/2/2027). Chế độ sự kiện dời sang V1, **lệch Bảng 13** (lý do ở mục 4.7): lát cắt sự kiện 15/2 – 26/3/2027, pilot 3–5 đám cưới hoặc tiệc thật trong T3–T4/2027. Filmode iOS chuyển sang lõi T3–T4/2027; phần iOS V1 còn lại T7–T8/2027 ([lịch cả họ app](../README.md#lịch-và-nhân-sự-cả-họ-app)).
- **Khối lượng:** 123 feature, **219,5 ngày công**: Có sẵn 8,5, MVP 95, V1 109, V2 7. Android 137,5 ngày, iOS 37 ngày, web/backend/công cụ/QA 45 ngày. Lõi tính riêng ở [filmode-core.md](../filmode-core.md).
- **Nguồn lực:** trong S1–S6, lõi (94 ngày) cộng phần Android và công cụ của app (92,5 ngày) là 186,5 ngày, vượt 177 ngày danh nghĩa của 3 dev Android trong 12 tuần. Cần 3 dev Android + 1 dev hợp đồng khoảng 8 tuần + tester thiết bị 50% + dev iOS 50%, hoặc 3 dev và áp cut-line. Chỉ có 2 dev thì làm gói Tết trên code cũ và phát hành bản dựng lại T3/2027 ([epics-features.md, mục Nhân sự](epics-features.md#nhân-sự)).

## 2. Hiện trạng

Số liệu ngày 27/9/2026 từ [hồ sơ Filmode trong ghi chú nghiên cứu](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/film_camera_apps.md) và Bảng 5 của báo cáo.

| | Filmode Vibe (Android) | Filmode (iOS) |
|---|---|---|
| Listing | "Filmode Vibe — Film Camera", `app.filmode`, bản 1.5.9 (22/9/2026) | "Filmode - Film & LUT Editor", id 6791145420, bản 1.4.4 (19/9/2026), iOS 13.0+, 44,3 MB |
| Ra mắt | 22/7/2026 | 22/7/2026 |
| Lượt cài, đánh giá | 69 lượt cài; 2 đánh giá 5★, chưa đủ để hiện điểm | 0 đánh giá (US); Sensor Tower ước < 5k lượt tải/tháng |
| Danh mục | **Productivity** (sai; mọi đối thủ ở Photography) | Photo & Video |
| Look | 18 look Free (Basic, Retro) + 25 look Pro (Cinematic, Film, Selfie); 6 look chính Golden, Teal, Analog, Glow, Midnight, Mono | Hơn 200 look trong 10 gói |
| Máy và hiệu ứng | 3 kiểu máy Toy, Instant, Pro; 10 hiệu ứng thời gian thực (Rain, Halation, VHS, Frost, Grain, CCD, Flash, Dust, Leak, Star); chế độ Pro chỉnh tay, burst, bracketing, intervalometer, night, focus stacking | Có "LENS" máy ảo (theo filmode.app, chưa rõ chi tiết ⚠) |
| Tính năng khác | Trình sửa (LUT, preset, curves), nhập .cube và preset kiểu Lightroom; photobooth tách nền; video tối đa 15 giây; khung Polaroid ⚠, Booth, Cutie, Frame, Noir, Retro, Raw; pin-board và Cloud Boards (đăng nhập Google, mời bằng mã, web) | Cuộn phim 12/24/36 kiểu tráng trễ; Match Photo; nhập .cube và .xmp; video 4K; chỉnh hàng loạt; App Clip, web camera (filmode.app) |
| Ngôn ngữ | Anh, Việt | 20 ngôn ngữ |
| Giá | $2.99–29.99 mỗi mục (VN 78.000–777.000 ₫); Pro tháng, năm, trọn đời; Pro mở 25 look, phơi sáng dài, vệt sáng; paywall chỉ hiện khi lưu | Pro $1.99/tháng, $4.99/3 tháng, $14.99/năm, $19.99 trọn đời; gói Cinematic $2.99, Pro-Mist $0.99, Y2K Digicam $1.99; Group/Party/Wedding Pass $2.99/$9.99/$49.99. VN: 59.000 ₫/tháng, 499.000 ₫/năm, 599.000 ₫ trọn đời, Wedding Pass 1.499.000 ₫ |
| Quyền riêng tư | Không quảng cáo; Data safety khai tùy chọn: tên, email, ID người dùng, tương tác, nội dung người dùng tạo, ảnh, lịch sử mua, ID thiết bị | — |
| Vấn đề | Lỗi "không lưu được ảnh" (đánh giá 8/9/2026; dev trả lời bản 1.5.0 đã sửa); tên khung "Polaroid" là nhãn hiệu; sai danh mục | Nội dung khác xa bản Android; giá VN đắt gấp 3–5 lần các app dẫn đầu |

**Khoảng lệch Android và iOS.** Android thiếu 200+ look, cuộn phim, Match Photo, .xmp, video 4K, hàng loạt, pass sự kiện. iOS thiếu kiểu máy, hiệu ứng thời gian thực, photobooth và board ⚠ (chưa rõ iOS có board). FMD-E11 đóng khoảng lệch: look, Match, cuộn sang Android ở MVP; máy và hiệu ứng sang iOS khi iOS chuyển lõi (V1). Nhập .xmp và xuất .cube không sang Filmode Android mà nằm ở Studio (mục 3.3).

## 3. Người dùng mục tiêu, việc cần làm và định vị

### 3.1 Người dùng và job-to-be-done

| Nhóm | Tình huống | Việc cần làm xong ("khi … tôi muốn … để …") | Tính năng chính | Trả tiền? |
|---|---|---|---|---|
| Gen Z 16–25 ở VN, ID, TH, PH, BR (Android là chính) | Đi chơi, concert, Tết, du lịch với bạn | Khi đi chơi với bạn, tôi muốn chụp ảnh ra chất digicam đầu 2000 ngay trên điện thoại, để đăng TikTok và Instagram mà không phải mua máy cũ 3–5 triệu | Máy chữ ký, Flash Drift, 0.5×, flash màn hình, date stamp | Ít; mua lẻ 1–2 máy, gói Tết |
| Người dùng Android muốn "như iPhone" | Thấy bạn dùng Live Photo, Dazz | Khi chụp bằng Android, tôi muốn có ảnh động thật và ảnh lưu giống hệt khung ngắm, để không thua bạn dùng iPhone | Motion Photo, ảnh = kính ngắm, xoay đúng mọi hãng | Pro năm hoặc trọn đời nếu giá VN hợp lý |
| Người dùng iPhone ở VN | Đã quen trả tiền cho màu film (Dazz #30, Fimii #49 grossing VN) | Khi muốn màu film "xịn", tôi muốn một app không quảng cáo, mua đứt được, để dùng lâu dài | 200+ look, máy, cuộn phim, trọn đời | Có: trọn đời 299.000 ₫ |
| Người thích chậm, nhớ máy phim | Cuối tuần, du lịch | Khi đi du lịch, tôi muốn chụp một cuộn 24 kiểu và chỉ xem khi "tráng", để có cảm giác chờ đợi của máy phim | Cuộn phim, tráng trễ, photo dump | Pro (cuộn 24/36) |
| Cô dâu chú rể, chủ tiệc | Đám cưới, sinh nhật, tất niên, họp lớp | Khi tổ chức tiệc, tôi muốn khách quét QR là chụp được ảnh chung một kiểu máy mà không phải cài app, để có album thật từ góc nhìn của khách và tải hết một lần | Chế độ sự kiện, web camera, duyệt, ZIP, trình chiếu | Có: pass theo quy mô |
| Khách dự tiệc | Tại bàn tiệc | Khi được mời chụp, tôi muốn mở camera ngay từ QR, không đăng ký, để chụp vài tấm vui | Web camera, offline, không tài khoản | Không (miễn phí cho khách) |
| Creator "công thức màu" ở VN (Threads, TikTok) | Làm bài giới thiệu app, recipe | Khi làm bài hướng dẫn, tôi muốn một hiệu ứng chữ ký dễ tái tạo và mã QR để người xem chụp cùng máy | Thẻ công thức QR, trang hướng dẫn, mã khuyến mãi | Nhận mã tặng |

### 3.2 Đối thủ và khác biệt

Số liệu từ Bảng 2, 6 và 7 của báo cáo và [ghi chú đối thủ](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/film_camera_apps.md) (ST = ước tính Sensor Tower cho tháng gần nhất; lượt cài Play là số chính xác ngày 27/9/2026).

| App | Lượt cài Play, điểm | ST tháng: Android / iOS | Giá (US; VN) | Điểm yếu mình khai thác | Filmode khác gì |
|---|---|---|---|---|---|
| [Dazz Cam](https://apps.apple.com/us/app/id1422471180) | Không có bản Android chính chủ; iOS 114.851 đánh giá (4,75) | — / 2 triệu tải, **$900k** | Pro $6.99, trọn đời $19.99, mỗi máy $0.99–2.99; VN 99.000 ₫, 299.000 ₫ | Không có Android; "Dazz" trên Play là app mượn tên (Dazzil 20,3 triệu cài) | Bản Android thật với máy tên tự đặt; trọn đời cùng mức $19.99 |
| [ProCCD](https://play.google.com/store/apps/details?id=com.cerdillac.proccd) | 22,23 triệu; 4,83 | 600k tải, $8k / 200k, $60k | Tuần $2.99, năm $5.99–8.99, trọn đời $13.99–17.99; VN 149.000 ₫/năm, 299.000–399.000 ₫ trọn đời | Có quảng cáo trên Android; "Live photo" chỉ lưu 1 video + 1 ảnh; phàn nàn tự gia hạn | Motion Photo thật; không quảng cáo; giá VN ngang ProCCD |
| [Kapi Cam](https://play.google.com/store/apps/details?id=com.sensemobile.action) | 16,33 triệu; 4,58 | **1 triệu** tải, $9k / 300k, $7k | Tuần $4.99, năm $69.99–89.99, trọn đời $149; VN 19.000 ₫/tuần | Khóa lại filter từng miễn phí; "preview đẹp mà chụp xấu"; bắt xem quảng cáo để lưu | Ảnh = kính ngắm (golden test); `free-tier.json` không bao giờ thu hẹp |
| [OldRoll](https://play.google.com/store/apps/details?id=com.accordion.analogcam) | 40,05 triệu; 4,27 | 400k, $20k / 200k, $90k | Tháng $4.49–4.99, năm $12.99–19.99, trọn đời $17.99–27.99; VN 329.000–399.000 ₫/năm | Chỉ 2 máy miễn phí; quảng cáo trên Android | 8 máy miễn phí; thử mọi máy trước khi trả |
| [Vintage Film Camera – Digicam](https://play.google.com/store/apps/details?id=filmcamera.vintagecamera.digitalcamera.retrocamera) (ZANKHANA) | 4,63 triệu trong ~14 tháng; 4,75 | 600k, $9k / < 5k | $0.99–19.99 mỗi mục; có quảng cáo | #1 Play US cho "film camera" nhờ tiêu đề nhồi từ khóa; mất ảnh khi gỡ app | Tiêu đề theo từ khóa (FMD-E12-04); ảnh lưu thẳng vào album |
| [101cam](https://apps.apple.com/us/app/id6781998623) (SNOW) | Chỉ iOS; ra mắt 10/7/2026 | — / 60k, < $5k | $4.99/tháng, $13.99/năm | #1 top free Hàn Quốc sau 11 tuần; ngân sách lớn; chưa có Android | Android trước; bản địa hóa VN và giá VN |
| [POV](https://play.google.com/store/apps/details?id=com.untitledshows.pov) | 1,28 triệu; 4,80 (45% mẫu 2024–2026 là 1–2★) | 100k, **$80k** / — | $4.99–119.99 mỗi sự kiện | Đăng nhập 27% lời chê; "$70 để 200 khách mỗi người 25 tấm"; không cài app chỉ chạy trên iPhone; phải tạo sự kiện mới thấy giá; lỗi đúng ngày cưới | Web camera chạy cả Android; giá công khai bằng VND; hạn mức rộng; offline rồi đồng bộ; pilot trước khi mở rộng |

**Câu định vị:** "Máy ảnh digicam và film cho Android và iPhone: thử mọi máy ngay trên kính ngắm, ảnh động thật, không quảng cáo, không watermark, mua đứt được."

**Không làm:** dùng tên Dazz, Kodak, Fuji, Polaroid, Instax, Canon, Leica, Contax, Lomo, Holga ở tên máy, look, khung hay listing; quảng cáo; watermark; AI sinh ảnh; bắt tài khoản (trừ chủ tiệc); đăng nhập bằng OTP số điện thoại; mạng xã hội có feed (bài học Lapse).

### 3.3 Ranh giới với Filmode Studio (Apple 4.3)

Apple siết guideline 4.3 từ 9/6/2026: app "biến thể" của cùng nhà phát triển có thể bị từ chối. Filmode iOS đã có trình sửa, nên ranh giới với Studio phải rõ. Quy tắc này giống hệt ở [README chung](../README.md#ranh-giới-giữa-các-app) và [README Studio](../02-filmode-studio/README.md#2-vì-sao-là-một-app-riêng):

- **Filmode là máy ảnh + chỉnh nhanh:** áp máy hoặc look cho ảnh có sẵn, chỉnh cơ bản, khung, áp hàng loạt, Match Photo để tạo look cho kính ngắm. Chỉnh sâu đi qua nút "Mở trong Filmode Studio" (A6.2, FMD-E06-06).
- **Filmode iOS giữ mọi tính năng trình sửa người dùng đang có hoặc đã trả tiền** (trình sửa, Match Photo, Match → LUT, nhập .cube và .xmp, video 4K, chỉnh hàng loạt): giữ mãi, không gỡ, theo luật của Apple về tính năng đã trả tiền và cam kết không thu hồi (FLC-E03-04, FMD-E11-06). Filmode iOS không nhận thêm tính năng chỉnh sâu mới. Trình sửa đang có của Filmode Vibe trên Android (LUT, preset, curves, nhập .cube; FMD-E06-01) cũng được giữ như vậy.
- **Mọi tính năng chỉnh sâu mới làm ở Studio**, trên cả Android và iOS: công thức theo thang máy ảnh, HSL, bánh xe màu, RAW, xuất LUT, parser công thức dạng chữ, cộng đồng. Filmode Android không thêm màn xuất .cube; look Match được gửi sang Studio để xuất (FMD-E11-05).
- **Quyền Pro mua riêng từng app** (`fmd.*`, `fms.*`, `fcm.*`). Không có tài khoản thì không cấp quyền chéo giữa các package được. Gói chung nhiều app chỉ là phương án V2 ⚠, làm qua tài khoản tùy chọn; chưa có trong backlog.

## 4. Mô tả tính năng chi tiết

### 4.1 Danh mục máy (A1, A2)

Mỗi máy là một `CameraSpec`: look nền (LUT 33³/64³), chuỗi pass chữ ký cắm vào lõi qua `EffectPass`, tham số grain và halation của lõi, khung, date stamp, tỉ lệ và độ phân giải xuất kiểu thời kỳ. Tên máy đều tự đặt, đi qua `NameGuard` (FLC-E04-02) và cần tra cứu nhãn hiệu trước khi đưa lên store ⚠. Preview và ảnh lưu dùng chung pass và seed, nên "thử trên kính ngắm" là thấy đúng ảnh sẽ lưu.

| Máy | Dòng, đời | Hiệu ứng chữ ký (cụ thể) | Gói | Bản |
|---|---|---|---|---|
| **Mochi 32** | Digicam CCD 3,2 MP, 2003 | Nhiễu cảm biến nhỏ (nhiễu màu mạnh ở vùng tối), làm nét quá tay có quầng sáng, khối JPEG 8×8, vùng sáng cháy cứng không có vai film, ám lạnh và magenta ở bóng, flash gắt tắt nhanh về rìa, date stamp LED cam `'03 9 27` | Free | MVP |
| **Sunny 35** | Máy phim 35mm ngắm-chụp tự động, thập niên 1990 | Vàng ấm, bóng nâng nhẹ, grain ISO 400 theo độ sáng, halation đỏ quanh đèn, flash tự động mềm, date stamp cam tùy chọn | Free | MVP |
| **Paper 27** | Máy dùng một lần 27 kiểu | Điểm nóng flash ở giữa (tâm sáng hơn góc khoảng 1,5 EV), vignette nặng, góc mềm do ống nhựa lấy nét cố định, méo thùng nhẹ, ám xanh lục ở trung tính, light leak ở khung đầu và cuối cuộn | Free | MVP |
| **Pop Instant** (thay khung "Polaroid" và kiểu Instant cũ) | Ảnh lấy liền khổ vuông | Khung trắng dày phía dưới, đen nâng (≥ 20/255), tương phản thấp, ám cyan ở bóng và ấm ở vùng sáng, mép hóa chất loang không đều theo từng ảnh, ảnh hiện dần | Free | MVP |
| **Toy 120** (kiểu Toy cũ) | Máy đồ chơi phim 120 | Vignette rất nặng, góc tối và mềm, leak đỏ cam, màu cross-process bão hòa, khung vuông | Free | MVP |
| **Flip VGA** | Điện thoại nắp gập 2005, camera 0,3 MP | Ảnh 640×480 (tùy chọn phóng to thấy pixel vuông), dải tương phản hẹp, cháy sáng sớm, ám vàng xanh trong nhà, nhiễu màu, khối JPEG, viền tím | Free | MVP |
| **DV-99** | Máy quay DV cuối thập niên 1990, chế độ chụp ảnh | Xen dòng lệch giữa hai trường ở vật chuyển động, lem màu ngang, khung 4:3 kiểu 720×576, OSD "REC ●", timecode `00:00:12:08`, ngày `SEP.27.2026`; video DV ở V1 | Free | MVP |
| **Flash Drift** | Mẹo "ảnh chuyển động" (trend Dazz 2026) | Flash làm chủ thể gần sắc nét, đèn và nền kéo vệt theo hướng lia máy (trộn 8–12 khung preview theo gyro), grain cao, CA nhẹ | Free | MVP |
| Chế độ Pro (đang có) | Máy chỉnh tay | ISO, tốc độ, lấy nét, WB; burst, bracketing, intervalometer, night, focus stacking; phơi sáng dài và vệt sáng là Pro như bản 1.5.9 | Free (phơi sáng dài Pro) | Có sẵn |
| **Kira CCD** | Digicam CCD 2006 gắn kính lọc sao | Như CCD cộng sao 4 hoặc 6 cánh lấp lánh cầu vồng trên mọi điểm sáng (đèn LED, nến, phản chiếu) | Pro / IAP $1.99 | MVP |
| **Glam V** | Máy compact vlog 2016 | Sáng, trong, da ấm hồng, bloom nhẹ, nét, ít grain; flash màn hình cho selfie | Pro / IAP $1.99 | MVP |
| **Luxe 35** | Máy compact 35mm cao cấp thập niên 1990 | Tương phản vi mô cao, đen sâu, grain mịn, vignette nhẹ, sắc ở tâm, date stamp đỏ | Pro / IAP $1.99 | MVP |
| **Half 72** | Máy half-frame 72 kiểu | Mỗi lần bấm là một nửa khung dọc; hai lần bấm ghép thành ảnh 3:2 hai khung có vạch ngăn; ấm, grain | Pro / IAP $0.99 | MVP |
| **Pháo Hoa 27** (gói Tết Nguyên đán / Lunar New Year 2027) | Máy dùng một lần mùa Tết | Đỏ vàng ấm, halation và sao trên pháo hoa, date stamp âm lịch ("Mùng 1 Tết Đinh Mùi"), khung lì xì, câu đối, hoa mai | IAP gói Tết $1.99 (Pro có sẵn) | MVP |
| **Owl 03** | Digicam 2003 chế độ đêm | Xanh lục đơn sắc kiểu kính nhìn đêm, hoặc màu ISO cao nhiều nhiễu và quầng sáng trên da | Pro / IAP $0.99 | V1 |
| **Quad Shot** | Máy 4 ống kính | 4 khung trong 0,5 giây ghép lưới 2×2, vignette từng ô | Pro / IAP $1.99 | V1 |
| **Fish 180** | Ống mắt cá | Méo tròn 180° trong khung tròn, viền đen, vignette | Pro / IAP $0.99 | V1 |
| **Paper 27 Aqua** | Máy dùng một lần chụp dưới nước | Ám cyan, tương phản thấp, flash yếu, mềm toàn khung | Pro / IAP $0.99 | V1 |
| **Pop Wide** | Ảnh lấy liền khổ rộng | Như Pop Instant nhưng khổ ngang, khung mỏng hơn | Pro / IAP $0.99 | V1 |

Gói theo mùa (`SeasonPack`: máy + look + khung + kiểu date stamp, mở và ẩn qua remote config, người đã mua giữ mãi): Tết Nguyên đán 2027 (MVP), Trung thu 2027 và mùa cưới (V1), Noel 2027 (V2).

**Tùy biến máy (A1.3, V1):** cường độ look, lượng grain, bật tắt từng hiệu ứng (Free); chế độ ngẫu nhiên kiểu máy dùng một lần và date stamp tùy biến theo định dạng, màu, vị trí, lấy giờ từ EXIF (Free); lưu biến thể thành "Máy của tôi" và chia sẻ bằng QR (Pro).

### 4.2 Chụp thời gian thực (A2)

- **Ảnh = kính ngắm.** Ảnh lưu đi qua đúng đồ thị pass của preview, render theo tile (FLC-E01-15), seed grain theo `photoId`. Golden test mỗi máy: ΔE trung bình < 2 và SSIM ≥ 0,95 (≥ 0,9 với máy có khối JPEG) giữa khung preview lúc bấm và ảnh lưu.
- **Ống kính:** 0.5× siêu rộng, 1×, tele và camera trước theo `CameraCapabilities` (FLC-E05-02). Máy không mở ống siêu rộng cho app bên thứ ba thì không có nút 0.5×.
- **Flash:** flash sau (tắt, tự động, bật), **flash màn hình cho selfie** (CameraX `ScreenFlash` ⚠), flash màu gel (V1). Máy có flash chữ ký vẫn mô phỏng flash bằng pass khi tắt flash thật.
- **Xoay đúng:** khóa UI dọc, date stamp, khung và OSD đặt theo hướng ảnh cuối; test 4 hướng × 2 camera × 8 máy ma trận.
- **Tiện ích:** lưới, hẹn giờ 3/10 giây, chụp liên tiếp 10 tấm, nút âm lượng, chạm để lấy nét, kéo để bù sáng, khóa AE/AF.
- **Chất lượng tùy máy (V1):** Ultra HDR có look (FLC-E06-04), Night/HDR extensions cho ảnh tĩnh, low-light boost.

### 4.3 Ảnh động (A3)

Nút "Live" bật bộ đệm vòng mã hóa các khung **đã qua look**; bấm chụp giữ 1,5 giây trước và 1,5 giây sau (chỉnh 1,5–3 giây). Định dạng chính là **Motion Photo** thật (một JPEG có MP4 nối đuôi và XMP theo đặc tả của Google ⚠), mở được trong Google Photos và Samsung Gallery. "Lưu dạng…" cho MP4 lặp, GIF ≤ 8 MB và ảnh tĩnh riêng để gửi qua Zalo, Messenger, TikTok. Trên iOS là Live Photo thật (V1). Tất cả miễn phí.

### 4.4 Video ngắn và máy quay (A4, V1)

Clip 15 giây hiện có được giữ. V1 nâng lên 1080p30: 30 giây Free, 60 giây có tiếng Pro; máy DV-99 quay có timecode chạy 25 khung/giây và OSD; VHS, leak động, khung camcorder là Pro.

### 4.5 Cuộn phim và tráng phim (A5)

Chọn máy và cuộn 12 kiểu (Free) hoặc 24/36 (Pro); kính ngắm đếm khung còn lại và không cho xem ảnh đã chụp. Hết cuộn hoặc bấm "Tráng" thì ảnh vào album `Pictures/Filmode/<tên cuộn>`, có leak ở khung đầu và cuối. V1: tráng trễ 1 giờ, 24 giờ hoặc 8 giờ sáng hôm sau có thông báo; photo dump (collage, carousel Instagram 4:5, ZIP) là Pro.

### 4.6 Nhập ảnh và chỉnh nhanh (A6)

Chọn ảnh qua Photo Picker (không `READ_MEDIA_*`), áp máy hoặc look, date stamp lấy giờ EXIF. Hàng loạt: 5 ảnh mỗi lượt Free, 100 ảnh Pro. Chỉnh cơ bản (phơi sáng, nhiệt độ màu, tint, tương phản, cường độ, cắt). Trình sửa và nhập .cube, preset đang có vẫn miễn phí và được giữ. Khung: 7 khung cũ (khung "Polaroid" đổi tên thành "Instant") + Film strip miễn phí, 6 khung Pro. Photobooth tách nền giữ nguyên, V1 chuyển sang `:core:segment` và thêm dải 4 ảnh đếm ngược. Chỉnh sâu thuộc Filmode Studio (nút "Mở trong Filmode Studio", V1), theo quy tắc ranh giới ở mục 3.3.

### 4.7 Chế độ sự kiện (A7)

**Lệch Bảng 13.** Bảng 13 của báo cáo đặt "chế độ sự kiện chạy trên web" trong giai đoạn 1 (T10/2026–T1/2027). Filmode dời cả chế độ sự kiện sang V1: lát cắt đủ dùng làm 15/2 – 26/3/2027, rồi pilot 3–5 đám cưới hoặc tiệc thật trong T3–T4/2027 (FMD-E07-17); phần còn lại chỉ làm khi pilot đạt ngưỡng ở mục 9. Lý do: (1) giai đoạn 1 đã vượt sức 3 dev Android chỉ với bản dựng lại và gói Tết; (2) phần lõi sự kiện cần (WebGL2 FLC-E01-23, xác minh pass và sự kiện thử FLC-E03-10, backend FLC-E08-02) là `V1`, hạn 15/2/2027; (3) báo cáo ghi chưa có dữ liệu nhu cầu app sự kiện ở Việt Nam, nên phải thử nhỏ trước khi đầu tư lớn; (4) mùa cưới sau Tết (T3–T4) là lúc chạy pilot. README chung ghi cùng chỗ lệch này.

**Luồng đầy đủ**

1. **Chủ tiệc tạo sự kiện** trong app (đăng nhập Google chỉ cho chủ tiệc): tên, giờ bắt đầu và kết thúc, máy và look chung (mọi máy, kể cả máy trả phí), số ảnh mỗi khách, giờ tráng, có duyệt trước hay không. Thử miễn phí 5 khách × 10 ảnh, lưu 7 ngày, trước khi mua pass.
2. **Mua pass** trên màn so sánh 3 gói (giá từ store, bằng VND ở VN). Giá cũng công khai ở `filmode.app/events`, không phải cài app hay tạo sự kiện mới thấy. Server gắn pass với sự kiện rồi app mới consume (FLC-E03-10).
3. **QR và link** `filmode.app/e/<mã>`: in thẻ bàn A6, poster A4, gửi link qua Zalo. Đổi mã được nếu lộ.
4. **Khách tham gia không cài app:** quét QR → trang web → nhập tên → cho phép camera → kính ngắm có look của sự kiện qua WebGL2 (FLC-E01-23) chạy trên Chrome Android và Safari iOS. Trình duyệt nhúng của Zalo, Messenger, Facebook không cho camera thì trang hướng dẫn mở bằng Chrome/Safari. Khách đã cài Filmode thì link mở thẳng màn sự kiện trong app với camera native.
5. **Chụp với hạn mức rộng:** đếm "còn N tấm" rõ ràng; server đếm trong transaction và idempotent theo `clientPhotoId`, nên số đếm trên máy và server luôn khớp (lời chê POV: "giới hạn 25 mà chỉ cho chụp 5").
6. **Offline rồi đồng bộ:** ảnh vào hàng đợi IndexedDB (web) hoặc WorkManager (app), tự tải lên khi có mạng; trang hiện "Đã lưu trên máy, chờ mạng".
7. **Tráng trễ:** ảnh ẩn với mọi người, kể cả người chụp, tới giờ tráng (ví dụ 9 giờ sáng hôm sau); khách chỉ thấy bộ đếm như máy dùng một lần.
8. **Duyệt:** chủ tiệc ẩn, hiện, xóa, chặn khách (xóa mọi ảnh của khách đó); khách báo cáo ảnh.
9. **Xuất:** tải toàn bộ ZIP một chạm (chia phần 2 GB ⚠, link hết hạn 7 ngày), trình chiếu toàn màn hình cho máy chiếu tại tiệc (V1, sau pilot), PDF in 10×15 cm và contact sheet (V2).
10. **Lưu trữ và xóa:** hạn lưu theo pass, nhắc chủ tiệc 14 và 3 ngày trước khi xóa kèm nút tải ZIP. Không mất ảnh bất ngờ (bài học Lapse).

**Pass và hạn mức** (đề xuất, chốt sau pilot ⚠)

| Pass | Khách chụp tối đa | Ảnh mỗi khách | Lưu | Giá US | Giá VN |
|---|---|---|---|---|---|
| Thử | 5 | 10 | 7 ngày | Miễn phí | Miễn phí |
| Group | 15 | 30 | 30 ngày | $2.99 | 39.000 ₫ |
| Party | 60 | 30 | 90 ngày | $9.99 | 129.000 ₫ |
| Wedding | 500 | 40 | 365 ngày | $49.99 | 599.000 ₫ |

Ảnh khách tải lên tối đa 6 MB, cạnh dài ≤ 4096. Một đám cưới 300 khách × 20 ảnh khoảng 6 GB; lưu 1 năm và tải ZIP một lần ước dưới $5 chi phí lưu trữ và băng thông ⚠ (giá Firebase Storage cần kiểm lại), so với doanh thu khoảng $20 (VN) đến $42 (US, sau phí store).

**Chống lạm dụng và quyền riêng tư:** mã sự kiện 10 ký tự khó đoán; token khách ẩn danh, không email, không số điện thoại; App Check hoặc reCAPTCHA cho web ⚠; giới hạn tần suất; `NameGuard` và lọc từ tục cho tên sự kiện và tên khách; endpoint quản trị gỡ sự kiện; khách xem được "Ảnh gửi cho ai, lưu tới ngày nào" và tự xóa ảnh của mình. Nội dung do người dùng tạo phải đáp ứng chính sách UGC của Play và Guideline 1.2 của Apple ⚠.

**🧪 Pilot trước khi đầu tư lớn (FMD-E07-17).** Làm lát cắt đủ dùng (tạo sự kiện, web camera, offline, duyệt, ZIP, giá) rồi chạy với 3–5 đám cưới hoặc tiệc thật ở Việt Nam trong T3–T4/2027, tặng Wedding Pass, có người trực Zalo trong ngày tiệc. Đo: % khách mời tham gia, ảnh mỗi khách, tỉ lệ tải lên lỗi, thời gian ZIP, điểm hài lòng của chủ tiệc, mức giá họ sẵn lòng trả. Ngưỡng quyết định ở mục 9. Chỉ khi đạt mới làm trình chiếu, in, chủ tiệc trên iOS, nâng pass.

### 4.8 Board và chia sẻ (A8)

Pin-board cục bộ và Cloud Boards (đăng nhập Google, mời bằng mã, xem trên web) được giữ nguyên cho người dùng hiện có; xóa tài khoản xóa luôn board. V1: **thẻ công thức máy** (ảnh + tên máy, look, tham số + QR recipe `filmode.app/r/1#…` của lõi); bạn bè quét là mở đúng máy và tham số trên kính ngắm, chưa cài app thì trang web hiện tên máy và nút tải.

### 4.9 Đồng bộ Android–iOS (A11)

- MVP Android nhận 200+ look của iOS (chuyển sang `.flook` qua `look-cli`, đổi tên qua `NameGuard`, giữ Free/Pro như iOS), thư viện look theo 10 gói, Match Photo (Match v1 của lõi, FLC-E01-18) và cuộn phim.
- MVP iOS chạy trên code đang có: giữ mọi quyền đã bán (Pro tháng, 3 tháng, năm, trọn đời; 3 gói look; 3 pass), không gỡ tính năng đã bán hay đang dùng (trình sửa, Match Photo, Match → LUT, nhập .cube và .xmp, video 4K, hàng loạt) nhưng không thêm tính năng chỉnh sâu mới (mục 3.3), đổi tên "Polaroid" và "Pro-Mist" ⚠, thêm 8 máy miễn phí dạng look và gói Tết.
- V1-iOS-a (T3–T4/2027, cùng quý với Studio iOS): iOS chuyển sang `FilmodeCoreKit`; kính ngắm, kho máy, cuộn phim, StoreCore. V1-iOS-b (T7–T8/2027): pass chữ ký bằng Metal, Live Photo, DV/VHS, chủ tiệc sự kiện. Tách hai đợt vì trong Q2 dev iOS làm Studio iOS (nộp 18/6/2027).

## 5. Gói Free, Pro, IAP, Pass

Nguyên tắc (A9, [lập trường của lõi](../filmode-core.md#41-lập-trường-quyền-riêng-tư)): không quảng cáo, không watermark ở mọi gói; xem trước mọi thứ trả phí trên kính ngắm, chỉ trả khi lưu; mọi mục Free nằm trong `free-tier.json` (FMD-E09-01) và không bao giờ chuyển sang trả phí; Pro là cùng SKU và cùng giá trên Android và iOS.

| Mảng | Free (mãi mãi) | Pro (tháng, năm, trọn đời) | IAP (mua lẻ một lần) | Pass (một sự kiện) |
|---|---|---|---|---|
| Máy | 8 máy (Mochi 32, Sunny 35, Paper 27, Pop Instant, Toy 120, Flip VGA, DV-99, Flash Drift) và chế độ Pro chỉnh tay | Mọi máy, kể cả máy mới và máy của gói mùa | Từng máy $0.99–1.99; gói mùa (Tết $1.99) | Máy của sự kiện dùng được cho mọi khách |
| Look | 18 look (Basic, Retro) | Hơn 200 look trong 10 gói | Gói look Cinematic $2.99, Soft Mist $0.99, Y2K Digicam $1.99 | — |
| Hiệu ứng | 10 hiệu ứng đang có và mọi pass chữ ký của máy Free | Hiệu ứng video VHS, leak động, khung camcorder (V1) | — | — |
| Chụp | 0.5×, flash màn hình, flash màu (V1), hẹn giờ, liên tiếp, Ultra HDR, Night (V1) | Phơi sáng dài, vệt sáng (như bản 1.5.9) | — | — |
| Ảnh động | Đủ: Motion Photo, MP4, GIF, Live Photo iOS | — | — | — |
| Cuộn phim | Cuộn 12 kiểu, tráng, tráng trễ (V1) | Cuộn 24/36; photo dump (V1) | — | — |
| Video (V1) | 30 giây 1080p, máy DV | 60 giây có tiếng | — | — |
| Nhập và chỉnh | Áp máy cho ảnh có sẵn, hàng loạt 5 ảnh, chỉnh cơ bản, nhập .cube và preset, Match Photo; "Mở trong Filmode Studio" để chỉnh sâu hoặc xuất .cube (V1) | Hàng loạt 100 ảnh | — | — |
| Khung | 8 khung (Instant, Booth, Cutie, Frame, Noir, Retro, Raw, Film strip) | 6 khung Pro | Khung trong gói mùa | — |
| Chia sẻ | Board, Cloud Boards, thẻ công thức QR (V1), "Máy của tôi" chỉ dùng riêng | "Máy của tôi" lưu và chia sẻ (V1) | — | — |
| Sự kiện | Sự kiện thử 5 khách × 10 ảnh, 7 ngày; khách luôn miễn phí | — | — | Group, Party, Wedding |

## 6. Giá

Giá Mỹ theo Bảng 8 (giữ giá iOS hiện tại). Giá VN theo báo cáo: khoảng 149.000–199.000 ₫/năm và 299.000 ₫ trọn đời, tức 40–50% giá Mỹ, ngang ProCCD (149.000 ₫/năm, 299.000–399.000 ₫ trọn đời) và Dazz (99.000 ₫ Pro, 299.000 ₫ mua một lần). Báo cáo không có giá App 1 cho ID, PH, BR; các cột đó là **đề xuất** ⚠ neo vào giá ProCCD, Dazz và Filmode iOS hiện tại ở từng nước, cần thử A/B.

| SKU | US | VN | ID ⚠ | PH ⚠ | BR ⚠ |
|---|---|---|---|---|---|
| Pro tháng `fmd.pro.monthly` | $1.99 | 29.000 ₫ ⚠ | Rp 15ribu | ₱ 49 | R$ 9,90 |
| Pro năm `fmd.pro.yearly` (dùng thử 7 ngày) | $14.99 | 149.000 ₫ (nhóm A/B 199.000 ₫) | Rp 99ribu | ₱ 349 | R$ 49,90 |
| Pro trọn đời `fmd.pro.lifetime` | $19.99 | 299.000 ₫ | Rp 199ribu | ₱ 499 | R$ 69,90 |
| Một máy `fmd.camera.<slug>` | $0.99–1.99 | 19.000–39.000 ₫ | Rp 9–19ribu | ₱ 29–59 | R$ 4,90–9,90 |
| Gói mùa (Tết 2027) | $1.99 | 39.000 ₫ | Rp 19ribu | ₱ 59 | R$ 9,90 |
| Gói look (Cinematic, Soft Mist, Y2K Digicam) | $0.99–2.99 | 19.000–59.000 ₫ | Rp 9–29ribu | ₱ 29–89 | R$ 4,90–14,90 |
| Group / Party / Wedding Pass | $2.99 / $9.99 / $49.99 | 39.000 / 129.000 / 599.000 ₫ | Rp 29 / 99 / 449ribu | ₱ 89 / 299 / 1.490 | R$ 14,90 / 49,90 / 199,90 |

Tham chiếu hiện tại: Filmode iOS VN 59.000 ₫/tháng, 499.000 ₫/năm, 599.000 ₫ trọn đời, pass 99.000/299.000/1.499.000 ₫; ID Rp 29ribu/tháng, Rp 299ribu/năm, Rp 399ribu trọn đời; BR R$ 12,90/tháng, R$ 99,90/năm, R$ 129,90 trọn đời. ProCCD ID Rp 99ribu/năm, Rp 299ribu trọn đời; BR R$ 29,90/năm, R$ 99,90 trọn đời. Dazz ID Rp 69ribu Pro, Rp 199ribu mua một lần; BR R$ 19,90, R$ 69,90.

Ghi chú:
- Gói 3 tháng $4.99 của iOS ngừng bán cho người mới nhưng người đang có vẫn được gia hạn và giữ quyền (FLC-E03-04).
- Hạ giá VN (FMD-E12-05) không được làm tăng giá của người đang thuê bao; cách hai store áp giá mới cho thuê bao cũ cần kiểm ⚠.
- Paywall theo [checklist lõi mục 4.3](../filmode-core.md#43-checklist-paywall): chữ lớn nhất là "149.000 ₫/năm", dùng thử ghi ngày bị trừ tiền, cách hủy bằng tiếng Việt và tiếng Anh, nút đóng hiện ngay, trọn đời nổi bật trên Android.

## 7. Phạm vi theo bản

Chi tiết ở [epics-features.md](epics-features.md). Số ngày là ngày công của app, chưa gồm lõi, thiết kế UI, dịch, nội dung.

| Bản | Thời gian | Ngày công | Nội dung chính |
|---|---|---|---|
| **Giai đoạn 0** (trên code đang chạy) | 5/10 – 23/10/2026 | 7,5 | Sửa lỗi lưu ảnh và đo `save_failed`; danh mục Photography; đổi "Polaroid" → "Instant" và "Pro-Mist" → "Soft Mist" ⚠; tiêu đề mới hai store; giá VN theo vùng; kiểm kê iOS; kiểm quyền lợi iOS |
| **MVP** (bản dựng lại trên lõi) | 26/10/2026 – ra mắt 18/1/2027 | 96 | 13 máy (8 Free) với pass chữ ký CCD, flash, ống kính rẻ, instant, DV, VGA, kira, Flash Drift, half-frame; kho máy, thử trước trả khi lưu, mua lẻ; gói Tết có date stamp âm lịch; ảnh = kính ngắm; 0.5×, flash màn hình, xoay đúng; ảnh động Motion Photo + MP4/GIF; cuộn 12/24/36; áp máy cho ảnh có sẵn, hàng loạt, chỉnh cơ bản, khung; 200+ look và Match Photo sang Android; gói miễn phí cố định, bảng SKU chung, paywall; listing 7 ngôn ngữ; chuyển dữ liệu 1.5.9; golden và checklist thiết bị; iOS: 8 máy dạng look, gói Tết, giữ quyền lợi |
| **V1** | T2 – T8/2027 | 109 | Chế độ sự kiện (web camera, offline, tráng trễ, duyệt, ZIP, giá, chống lạm dụng) và 🧪 pilot T3–T4; trình chiếu nếu pilot đạt; video 30/60 giây, DV, VHS; 5 máy mới; tùy biến máy, ngẫu nhiên, date stamp; tráng trễ, photo dump; chia sẻ 9:16; flash màu; Ultra HDR, Night; thẻ công thức QR; nút mở Studio; creator, giới thiệu bạn; gói Trung thu và mùa cưới; Filmode iOS chuyển lõi T3–T4 (kính ngắm, kho máy, cuộn, StoreCore), phần iOS còn lại T7–T8 (pass Metal, Live Photo, DV/VHS, chủ tiệc) |
| **V2** | Sau mốc "đẩy mạnh" | 7 | Gói Noel 2027; in ảnh sự kiện; nâng pass giữa sự kiện; board trên iOS; win-back |
| **Tổng** | | **219,5** | 123 feature |

## 8. ASO

Nguồn: Bảng 1, Bảng 8 của báo cáo và [ghi chú từ khóa](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/keyword_search_demand.md). Cụm đầu (film camera, retro camera, digicam, ccd) bị OldRoll, ProCCD và ZANKHANA giữ top 3, nhưng ZANKHANA và Kapi cho thấy app mới vẫn chen vào được nhờ tiêu đề đủ từ khóa. Việc đầu tiên nên chi tiền theo báo cáo là thuê một công cụ ASO trả phí trong 1 tháng để lấy lượt tìm thật cho Play US và VN ⚠ trước khi chốt tiêu đề.

| Thị trường | Tiêu đề (≤ 30 ký tự) | Mô tả ngắn Play (≤ 80) hoặc subtitle iOS (≤ 30) |
|---|---|---|
| EN (US, PH, SG) | Filmode: Digicam & Film Camera | Play: "Y2K digicam, CCD & disposable film camera. Live photos, film rolls. No ads." · iOS: "Y2K CCD, disposable & instant" |
| VI | Filmode: Máy ảnh film, Digicam | Play: "Máy ảnh ccd, digicam, máy dùng một lần. Ảnh động, cuộn phim. Không quảng cáo." · iOS: "Máy ảnh ccd, chụp ảnh film" |
| ID | Filmode: Kamera Jadul Digicam | "kamera jadul", "kamera film vintage", "digicam" ⚠ |
| KO | Filmode: 디카 필터 & 필름카메라 | "필름카메라 어플", "디카 필터", "디카앱" ⚠ |
| JA | Filmode: デジカメ風フィルムカメラ | "フィルムカメラ アプリ", "デジカメ風", "写ルンです風" (không dùng làm tên máy) ⚠ |
| PT-BR | Filmode: Câmera Retrô Digicam | "câmera vintage", "film cam", "digicam" ⚠ |

**Từ khóa theo cụm**

| Cụm | EN | VI | Ghi chú |
|---|---|---|---|
| Đầu, khó | film camera, retro camera, vintage camera, digicam, ccd camera | máy ảnh film, chụp ảnh film, app chụp ảnh film, máy ảnh ccd | Đặt trong tiêu đề và mô tả ngắn |
| Đuôi dài, dễ hơn | y2k camera, disposable camera filter, film grain, grainy, live photo android, 0.5 camera, dual camera | digicam y2k, grainy, filter film, ảnh động, cuộn phim, máy dùng một lần | "disposable camera" nghiêng về app sự kiện |
| Sự kiện (V1) | disposable camera wedding, wedding camera app, party camera qr | chụp ảnh đám cưới qr, album cưới chung | Chưa có dữ liệu lượt tìm VN ⚠ |
| Tránh | dazz cam, polaroid, kodak gold, fuji, huji, vsco | "dazz cam", "polaroid", "kodak gold 200" | Nhãn hiệu; chỉ nhắm từ lân cận |

Ảnh chụp màn hình (FMD-E10-02): 1 hiệu ứng chữ ký (Flash Drift), 2 kho máy "8 máy miễn phí", 3 ảnh động, 4 0.5× và flash selfie, 5 cuộn phim, 6 "Không quảng cáo, không watermark", 7 gói Tết (đổi theo mùa), 8 sự kiện (từ V1). Lint của lõi (FLC-E04-03) chặn nhãn hiệu và "Chinese New Year" trong metadata.

## 9. KPI và tiêu chí dừng hoặc đẩy mạnh

Mốc đo của Bảng 13: giai đoạn 0 là "không còn báo lỗi lưu ảnh; bắt đầu có thứ hạng cho 'máy ảnh film' hoặc 'digicam' ở VN"; giai đoạn 1 là "tỷ lệ lưu ảnh mỗi phiên; tỷ lệ chuyển đổi ở paywall; số pass bán được". Mốc thành công đầu tiên của báo cáo: **$1K/tháng cộng một vị trí trong top từ khóa ở Việt Nam**.

| KPI | Ngưỡng | Nguồn ngưỡng | Đo bằng |
|---|---|---|---|
| Lỗi lưu ảnh | < 0,1% lượt lưu; 0 báo lỗi lưu mới trên store | Mốc giai đoạn 0 | `save_failed` (FMD-E12-01), đánh giá store |
| Phiên có ít nhất 1 ảnh lưu | ≥ 50% ⚠ | Mục tiêu nội bộ | Phễu `capture` → `save` (FLC-E05-07) |
| Crash, ANR | Dưới ngưỡng Play Vitals; crash-free ≥ 99,5% người dùng | Lõi mục 4.2 | Play Console, Crashlytics ⚠ |
| Tải → trả tiền sau 35 ngày | Play ≥ 0,9%, App Store ≥ 2,6% | RevenueCat, mọi danh mục | Store + phễu `purchase_success` |
| Dùng thử gói năm → trả tiền | Play ≥ 17,1%, iOS ≥ 22,2% | RevenueCat, Photo & Video | Play Console, App Store Connect |
| Doanh thu mỗi lượt cài sau 60 ngày | Play ≥ $0,04, iOS ≥ $0,15 (mức Đông Nam Á) | RevenueCat | Doanh thu thực nhận / lượt cài theo tháng |
| Paywall → mua | Android ≥ 1,5%, iOS ≥ 4% ⚠ | Mục tiêu nội bộ | Phễu `paywall_view` → `purchase_success` theo `variant` |
| Thứ hạng từ khóa | Top 10 Play VN cho ít nhất 1 trong "máy ảnh film", "app chụp ảnh film", "máy ảnh ccd", "digicam" | Báo cáo | Công cụ ASO trả phí ⚠ |
| Pass bán được | ≥ 20 pass/tháng sau pilot ⚠ | Mục tiêu nội bộ | Store, backend |
| Doanh thu | $1K/tháng thực nhận (hai store) | Báo cáo | Play Console, App Store Connect |

**Quyết định sau 12 tuần kể từ ra mắt (giữa T4/2027) và sau 6 tháng (giữa T7/2027):**
- **Đẩy mạnh** khi doanh thu ≥ $1K/tháng trong 2 tháng liên tiếp **và** có top 10 cho ít nhất 1 từ khóa VN: mở V2, tăng chương trình creator ở ID và PH, thêm ngôn ngữ.
- **Sửa** khi doanh thu $300–1K/tháng hoặc chỉ vào top 11–30: thử giá năm VN 149.000 ₫ và 199.000 ₫, thử listing trên Play, thêm máy chữ ký theo trend; giữ nhịp V1.
- **Dừng đầu tư mở rộng** khi dưới $300/tháng sau 6 tháng và không vào top 30 từ khóa nào: chỉ bảo trì (sửa lỗi, gói mùa qua remote config), dồn người sang Studio và FilCam.

**Ngưỡng pilot sự kiện (FMD-E07-17), 4 tiêu chí:** (1) ≥ 3/5 chủ tiệc nói sẽ trả ít nhất giá Party; (2) ≥ 40% khách có mặt chụp ít nhất 1 ảnh; (3) tải lên lỗi < 2%; (4) ZIP của cả sự kiện xong ≤ 15 phút. Đạt 4/4 hoặc 3/4 thì làm tiếp phần còn lại của FMD-E07. Đạt 2/4 thì sửa và pilot lại 2 sự kiện. Dưới 2/4 thì dừng ở phạm vi pilot, giữ pass cho người đã mua.

## 10. Rủi ro

| Rủi ro | Ảnh hưởng | Cách xử lý |
|---|---|---|
| MVP app cộng MVP lõi (186,5 ngày) vượt sức 3 dev Android (177 ngày) trước Tết | Lỡ mùa Tết 2027 | Dev hợp đồng 8 tuần; cut-line; phương án 2 dev là gói Tết trên code cũ ([Nhân sự](epics-features.md#nhân-sự)) |
| Chưa biết cấu trúc code của Filmode Vibe và Filmode iOS ⚠ | Mục `Có sẵn` và iOS vượt ước tính | FMD-E11-01 kiểm kê trong giai đoạn 0; ước lại trước S1 |
| Tên máy, khung hoặc gói trùng nhãn hiệu ("Polaroid", "Pro-Mist" của Tiffen ⚠) | App bị gỡ | `NameGuard` và lint (FLC-E04-02, -03); đổi tên ở giai đoạn 0; tra cứu nhãn hiệu cho 18 tên máy trước khi lên store ⚠ |
| Đổi gói làm người dùng thấy bị "lấy lại" | Đánh giá 1★ (33% lời chê của nhóm app film) | `free-tier.json` và CI (FMD-E09-01); map mọi SKU cũ (FMD-E09-02); không gỡ tính năng iOS đã bán (FMD-E11-06) |
| Motion Photo không được app thư viện của một số hãng nhận ⚠ | Lời chê "không phải live photo" | Spike FMD-E03-01 trên 4 app thư viện; luôn có MP4/GIF |
| Máy không mở ống siêu rộng hoặc flash trước cho app bên thứ ba | Lời chê "không có 0.5×" | Dò khả năng (FLC-E05-02), ẩn thay vì báo lỗi; ghi rõ trên trang hỗ trợ |
| Ảnh xuất lệch preview trên GPU Mali/PowerVR | Mất lời hứa "ảnh = kính ngắm" | Golden cấp app cho 13 máy (FMD-E13-03) trên ma trận thiết bị |
| Web camera không chạy trong trình duyệt nhúng Zalo/Messenger ⚠ | Khách bỏ cuộc ngay tại tiệc | Spike FMD-E07-01; hướng dẫn mở bằng Chrome/Safari (FMD-E07-07); in QR kèm câu hướng dẫn |
| Sự kiện lỗi đúng ngày cưới | Đánh giá 1★, hoàn tiền | Offline rồi đồng bộ; idempotent; pilot có người trực; staged rollout backend |
| Chi phí lưu trữ sự kiện tăng | Lỗ trên pass giá VN | Hạn mức khách và ảnh theo pass; ảnh ≤ 6 MB; hạn lưu; cảnh báo ngân sách (FLC-E08-02) |
| Nội dung xấu trong album sự kiện, chính sách UGC của Play và Apple ⚠ | Bị từ chối review hoặc gỡ | Duyệt trước, báo cáo, chặn khách, endpoint gỡ (FMD-E07-10, FMD-E07-16) |
| Chưa có dữ liệu nhu cầu app sự kiện ở VN | Đầu tư 41 ngày V1 không thu hồi | Pilot trước; phần sau pilot phụ thuộc kết quả |
| SNOW (101cam) và app Việt mới (Fimii, Rollie, Eluvo, DiscCam) | Khó lên hạng | Bản địa hóa VN, giá VN, Android trước, vòng chia sẻ QR |
| Thưởng giới thiệu bạn có thể vướng chính sách thưởng của Play ⚠ | Cảnh báo chính sách | Kiểm chính sách trước FMD-E10-06; không thưởng cho đánh giá |
| Lịch âm sai ngày | Gói Tết in sai "Mùng 1" | Test 30 ngày mẫu 2026–2028 (FMD-E01-07) |

## 11. Nội dung cần làm ngoài code

Không tính trong ngày công dev. Ước tính bằng "ngày nội dung" của người dựng look và thiết kế.

| Hạng mục | Số lượng | Ngày nội dung | Bản |
|---|---|---|---|
| Look nền và tham số pass cho máy MVP (dựng trên bộ ảnh chuẩn, duyệt golden) | 13 máy | ≈ 20 (1,5/máy) | MVP |
| Ảnh mẫu cho thẻ máy (người Việt, cảnh đường phố, cảnh Tết) | 3 ảnh × 13 máy + 1 buổi chụp | ≈ 3 | MVP |
| Gói Tết: 6 look, 3 khung (lì xì, câu đối, hoa mai), ảnh mẫu | 1 gói | ≈ 4 | MVP |
| Chuyển 200+ look iOS: đặt tên lại, manifest nguồn gốc, thumbnail | 200+ look | ≈ 4 | MVP |
| Khung mới: Film strip + 6 khung Pro | 7 khung | ≈ 2 | MVP |
| Ảnh chụp màn hình và video listing | 8 ảnh × 7 ngôn ngữ | ≈ 3 (chưa gồm dịch) | MVP |
| 5 máy V1 (look, tham số, ảnh mẫu) | 5 máy | ≈ 8 | V1 |
| Gói Trung thu và mùa cưới | 2 gói | ≈ 6 | V1 |
| Sự kiện: thẻ bàn A6, poster A4, trang giá, FAQ, kịch bản hỗ trợ ngày tiệc | 1 bộ | ≈ 3 | V1 |
| Trang hướng dẫn creator (video ngắn cho từng máy chữ ký) | 8 trang | ≈ 4 | V1 |
| Gói Noel | 1 gói | ≈ 2 | V2 |
| **Tổng** | | **≈ 36 MVP, ≈ 21 V1, ≈ 2 V2** | |

## 12. Liên kết

- [README chung](../README.md), [Filmode Core](../filmode-core.md), [backlog lõi](../filmode-core-backlog.csv)
- [Báo cáo: Lõi LUT của Filmode đủ nuôi ba app](../../../reports/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u.md), mục "App 1 — Filmode", Bảng 2, 5, 6, 8, 10, 13 và phần rủi ro
- Ghi chú nghiên cứu `research_notes/App camera film và LUT màu/`: [film_camera_apps.md](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/film_camera_apps.md), [user_sentiment_pain_points.md](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/user_sentiment_pain_points.md), [monetization_paid_features.md](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/monetization_paid_features.md), [keyword_search_demand.md](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/keyword_search_demand.md), [tech_feasibility_opportunities.md](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/tech_feasibility_opportunities.md)
