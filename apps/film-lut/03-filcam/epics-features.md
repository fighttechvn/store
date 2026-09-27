# Epic và feature · FilCam (`FCM`)

Quy ước ID, ưu tiên, gói, ước tính và dấu ⚠ / 🧪 theo [README chung](../README.md). Ước tính là ngày công của 1 dev Android có kinh nghiệm (dev iOS cho `FilCamiOS/*`), đã gồm unit test. **Không gồm** thiết kế UI, dịch thuật, dựng look và LUT (xem mục [Nội dung](#nội-dung-không-tính-vào-ngày-công-dev)) và rà soát pháp lý.

Feature của lõi (`FLC-…`) chỉ được tham chiếu ở cột "Phụ thuộc", không làm lại ở đây ([filmode-core.md](../filmode-core.md)). Phần FilCam cần lõi đổi nằm ở mục [Điều chỉnh lõi](#điều-chỉnh-lõi). Thiết kế chi tiết của từng epic (đường video hai nhánh, FM-Log, sidecar, scopes, xuất hàng loạt, ma trận máy) nằm ở [README mục 5](README.md#5-mô-tả-tính-năng-theo-epic).

Module Android: `:app:filcam` và `:filcam:<tên>`: `:filcam:manual` (điều khiển tay qua Camera2Interop), `:filcam:photo` (chụp ảnh, chế độ chuyên sâu), `:filcam:video` (pipeline quay, recorder, encoder, âm thanh), `:filcam:monitor` (zebra, peaking, false color, histogram, waveform, khung tỉ lệ), `:filcam:log` (FM-Log, HLG), `:filcam:lutlib` (thư viện LUT), `:filcam:grade` (chỉnh màu clip, scopes, xuất Media3), `:filcam:lutmaker` (tạo và xuất LUT), `:filcam:devices` (năng lực máy, tier, nhiệt, báo lỗi), `:filcam:learn` (onboarding, bài học). iOS (V2): `FilCamiOS/App`, `FilCamiOS/Capture`, `FilCamiOS/Record`, `FilCamiOS/Log`, `FilCamiOS/Grade`, `FilCamiOS/Store` trên `FilmodeCoreKit`. Module giả: `(qa)`, `(ci)`, `(web)`.

Thiết bị: mọi tính năng phụ thuộc phần cứng hỏi `CameraCapabilities` (FLC-E05-01, FLC-E05-02) và chính sách FilCam (FCM-E07-02) trước. Máy không làm được thì ẩn tính năng, không hiện rồi báo lỗi.

## Tổng quan epic

| ID | Epic | ↔ Báo cáo | Mục tiêu | Module | Feature | Có sẵn | MVP | V1 | V2 | Tổng (ngày) |
|---|---|---|---|---|---|---|---|---|---|---|
| FCM-E01 | Máy ảnh thủ công và RAW | F1 | Giữ chỉnh tay, RAW DNG, LUT ảnh và chế độ chuyên sâu; chạy trên lõi; công cụ đo thành pass GPU chỉ ở preview | `:filcam:manual`, `:filcam:photo`, `:filcam:monitor`, `:app:filcam` | 11 | 7 | 12 | 1,5 | 0 | 20,5 |
| FCM-E02 | Quay video có LUT | F2 | Quay 1080p có LUT miễn phí, 4K và ghi sạch + LUT để xem cho Pro; đổi LUT và cường độ trên màn quay | `:filcam:video`, `:filcam:manual`, `:filcam:monitor`, (qa) | 20 | 0 | 32 | 14 | 0 | 46 |
| FCM-E03 | Log và HDR | F3 | FM-Log (đường cong riêng, không cần Log của hãng) và HLG 10-bit, kèm LUT kỹ thuật và hướng dẫn phơi sáng | `:filcam:log`, `:filcam:monitor`, (qa) | 8 | 0 | 0 | 15,5 | 3 | 18,5 |
| FCM-E04 | Quản lý LUT | F4 | Một thư viện LUT cho ảnh, video và chỉnh clip; nhập miễn phí; LUT sáng tạo tách LUT kỹ thuật | `:filcam:lutlib` | 8 | 1 | 5,5 | 4,5 | 0 | 11 |
| FCM-E05 | Chỉnh màu clip có sẵn | F5 | Chỉnh màu clip trên điện thoại: LUT, cơ bản, đường cong, Log → 709, scopes, xuất hàng loạt Media3 | `:filcam:grade`, (qa) | 14 | 0 | 12,5 | 17,5 | 0 | 30 |
| FCM-E06 | Tạo và xuất LUT | F6 | Xuất bản chỉnh thành .cube/HALD cho app khác; LUT từ ảnh mẫu; chia sẻ look | `:filcam:lutmaker` | 6 | 0 | 0 | 7,5 | 3 | 10,5 |
| FCM-E07 | Tương thích thiết bị | F7 | Biết trước máy làm được gì, ẩn thứ không làm được, dừng ghi an toàn khi nóng, đo lỗi theo hãng, công bố danh sách máy | `:filcam:devices`, (qa), (web) | 9 | 0 | 12 | 6,5 | 0 | 18,5 |
| FCM-E08 | Kiếm tiền | F8 | Giữ lời hứa miễn phí hiện có; bán FilCam Pro tháng, năm (dùng thử 7 ngày), trọn đời | `:app:filcam` | 6 | 0,5 | 5,5 | 1 | 0 | 7 |
| FCM-E09 | Hướng dẫn | F9 | Onboarding nhanh; bài tiếng Việt quay Log và dùng lut màu | `:filcam:learn`, (web) | 5 | 0 | 2,5 | 5,5 | 0 | 8 |
| FCM-E10 | FilCam iOS | mới (F3.3) | Bản iOS trên `FilmodeCoreKit`: kính ngắm LUT, ghi sạch, Apple Log → 709 + look, chỉnh clip | `FilCamiOS/*`, (qa) | 13 | 0 | 0 | 0 | 37 | 37 |
| FCM-E11 | Chất lượng và phát hành | mới | Monorepo, test tự động đường quay, chạy thử 2 tuần trên ma trận, staged rollout, listing | `:app:filcam`, (qa), (ci) | 7 | 1,5 | 11 | 1,5 | 0 | 14 |
| | **Tổng** | | | | **107** | **10** | **93** | **75** | **43** | **221** |

`FCM-E01`…`FCM-E09` khớp 1:1 với F1–F9 của Bảng 12. Hai epic thêm:
- **FCM-E10 FilCam iOS (V2).** Báo cáo xếp Apple Log (F3.3) ở V2 và ước "bản iOS 6–8 và 5–8 tuần-người" ở Bảng 13, nhưng không có epic iOS riêng. Gom phần iOS vào một epic để dễ quyết định làm hay không sau mốc đo. iOS dùng `FilmodeCoreKit` (renderer Metal, thư viện, StoreKit 2 đã có ở V1 của lõi), nên chỉ còn khoảng 37 ngày thay vì 11–16 tuần-người.
- **FCM-E11 Chất lượng và phát hành.** Bảng 13 yêu cầu chạy thử 2 tuần trên ma trận thiết bị trước khi cam kết, dành 20–25% công sức cho kiểm thử và lấy "tỉ lệ crash theo hãng máy" làm mốc đo. Các việc đó (monorepo, test tự động đường quay, beta kín, staged rollout, listing) không thuộc epic tính năng nào.

## FCM-E01 · Máy ảnh thủ công và RAW

Mục tiêu: giữ nguyên thứ FilCam 1.0.21 đang làm tốt (chỉnh tay, RAW DNG miễn phí, LUT in vào JPEG, chế độ chuyên sâu), chuyển lên lõi, và viết lại công cụ đo thành pass GPU để dùng chung cho ảnh và video.

Ánh xạ Bảng 12: F1.1 → 03, 10, 11 · F1.2 → 04 · F1.3 → 05, 06, 07 · F1.4 → 08, 09. Thêm: 01 (spike đọc code), 02 (chuyển sang wrapper CameraX của lõi).

Ước tính `Có sẵn` giả định code 1.0.21 là Kotlin và tách được thành module, giống giả định của lõi ⚠. Ghi chú nghiên cứu cho biết FilCam dùng Camera2 cho điều khiển tay, nên việc chuyển sang CameraX + Camera2Interop là một dòng `MVP` riêng (FCM-E01-02), không giấu trong các dòng `Có sẵn`. Focus peaking, zebra, false color và waveform có trên trang web FilCam nhưng không có trong mô tả Play ⚠; FCM-E01-05 kiểm lại. Không làm lại: wrapper CameraX (FLC-E01-16), dò khả năng (FLC-E05-01, FLC-E05-02), render ảnh tĩnh (FLC-E01-15), lưu MediaStore và EXIF (FLC-E06-02, FLC-E06-03).

Khối lượng: 11 feature · Có sẵn 7 ngày · MVP 12 ngày · V1 1,5 ngày · tổng **20,5 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FCM-E01-01 | `:app:filcam` | 🧪 Spike 1 ngày: đọc code FilCam 1.0.21 (ngôn ngữ, UI, Camera2 hay CameraX, cách render LUT và ghi DNG, billing, lưu file); lập bản đồ tính năng cũ → module `:filcam:*`; ước lại các dòng `Có sẵn` | — | MVP | 1 | FLC-E07-01 | Khi xong spike thì có bảng tính năng 1.0.21 → module, danh sách API Camera2 đang dùng và ước tính lại cho FCM-E01-02 đến FCM-E01-09; nếu lệch quá 30% thì người điều phối được báo trước sprint 2 |
| FCM-E01-02 | `:filcam:photo` | Chuyển phiên chụp ảnh sang wrapper CameraX 1.6 của lõi: Preview + ImageCapture có `CameraEffect` LUT; điều khiển tay qua Camera2Interop; chỉ giữ session Camera2 riêng cho chế độ chuyên sâu (phơi sáng dài, bracketing, xếp chồng) và render các chế độ đó qua `:core:gpu` | — | MVP | 3 | FLC-E01-16; FLC-E01-15; FCM-E01-01 | Khi chụp với 43 look trên 8 máy ma trận thì golden preview/ảnh xuất (FLC-E07-03) đạt và ảnh giống bản 1.0.21 (PSNR ≥ 40 dB); khi tìm trong code thì ngoài chế độ chuyên sâu của `:filcam:photo` không còn chỗ nào mở `CameraDevice` trực tiếp |
| FCM-E01-03 | `:filcam:manual` | Gom điều khiển tay đang chạy (F1.1): chế độ P/S/I/M; ISO, tốc độ, EV, cân bằng trắng theo Kelvin, lấy nét tay; khóa AE/AF/AWB; chế độ đo sáng; ẩn điều khiển máy không mở (thiếu `MANUAL_SENSOR`) | Free | Có sẵn | 1,5 | FCM-E01-02; FLC-E05-01 | Khi chụp ở M với ISO 400 và 1/50 s trên 8 máy ma trận thì EXIF ghi đúng ISO và tốc độ (lệch ≤ 1/3 EV); khi máy không có `MANUAL_SENSOR` thì S/I/M bị ẩn như bản 1.0.21 |
| FCM-E01-04 | `:filcam:photo` | Gom định dạng ảnh đang chạy (F1.2): RAW DNG (không áp look) kèm JPEG/HEIF/PNG có LUT 64³; tên file và thư mục tùy chỉnh; EXIF đầy đủ, geotag tùy chọn; chụp bằng phím âm lượng; lưu qua hàng đợi MediaStore của lõi | Free | Có sẵn | 1,5 | FCM-E01-02; FLC-E06-02; FLC-E06-03 | Khi chụp RAW + JPEG thì có hai file cùng tên gốc trong thư mục đã chọn và DNG mở được trong Lightroom, Snapseed với màu trung tính; khi máy không báo RAW (`getSupportedOutputFormats`) thì nút RAW bị ẩn; khi chụp 100 ảnh rồi kill app thì đủ 100 cặp file |
| FCM-E01-05 | `:filcam:monitor` | Gom công cụ kính ngắm đang chạy: histogram RGB, lưới, thước cân bằng; focus peaking, zebra, false color, waveform (trang web FilCam có nêu ⚠ kiểm trong code) | Free | Có sẵn | 1 | FCM-E01-02 | Khi mở kính ngắm ảnh thì mọi công cụ có ở 1.0.21 vẫn bật được và cho cùng kết quả trên ramp xám chuẩn |
| FCM-E01-06 | `:filcam:monitor` | Zebra (2 ngưỡng, mặc định 70% và 95%), focus peaking (Sobel trên luma ở ½ độ phân giải; 3 màu, 3 độ nhạy) và false color (bảng Rec.709 và bảng FM-Log) viết thành `EffectPass` GPU chỉ gắn vào nhánh preview; dùng chung cho ảnh và video; không bao giờ vào ảnh hay file quay (F1.3) | Free | MVP | 3 | FLC-E01-11; FCM-E02-02 | Khi quay với zebra, peaking và false color cùng bật thì khung trích từ file không có vạch zebra hay viền peaking; khi đưa ramp xám 0–100% vào thì zebra 95% chỉ phủ các ô ≥ 95%; khi bật cả ba ở 1080p30 trên máy tầm trung chuẩn thì preview vẫn ≥ 30 fps |
| FCM-E01-07 | `:filcam:monitor` | Scopes GPU cho kính ngắm (F1.3): histogram luma + RGB và waveform luma trên khung thu nhỏ 256×144; ES 3.1+ dùng compute shader + `imageAtomicAdd`, ES 3.0 dùng scatter điểm + additive blend vào texture R16F (`EXT_color_buffer_half_float` ⚠, dự phòng RGBA8); cập nhật 15 Hz; vẽ inset trên nhánh preview; renderer dùng lại cho scopes của trình chỉnh màu | Free | MVP | 3 | FCM-E01-06 | Khi đưa ramp xám chuẩn vào thì waveform là một đường chéo, lệch ≤ 1% thang; khi bật waveform trên máy tầm trung chuẩn thì fps preview giảm ≤ 2 fps và thời gian GPU thêm ≤ 1,5 ms/khung ⚠; khi 5% diện tích khung bị cháy thì histogram báo "Cháy 5%" |
| FCM-E01-08 | `:filcam:photo` | Gom phơi sáng dài tới 30 giây và vệt sáng 15 giây–5 phút (cộng khung kiểu lighten) vào module, render look qua `:core:gpu` (F1.4) | Pro | Có sẵn | 1,5 | FCM-E01-02 | Khi chụp 30 giây trên máy có `SENSOR_INFO_EXPOSURE_TIME_RANGE` ≥ 30 s thì EXIF ghi 30 s và ảnh có đúng look; khi chụp vệt sáng 60 giây thì kết quả giống bản 1.0.21 (kiểm tay); khi người dùng miễn phí chọn chế độ này thì paywall hiện và app không crash |
| FCM-E01-09 | `:filcam:photo` | Gom bracketing 3/5/7 khung, chụp đêm (ghép nhiều khung), focus stacking và intervalometer vào module (F1.4) | Pro | Có sẵn | 1,5 | FCM-E01-02 | Khi chụp bracketing 5 khung ±2 EV thì có 5 file với EV đúng thứ tự trong EXIF; khi chạy intervalometer 10 khung cách 5 giây thì đủ 10 ảnh, lệch nhịp ≤ 0,5 giây; kết quả focus stacking và chụp đêm giống bản 1.0.21 (kiểm tay) |
| FCM-E01-10 | `:filcam:manual` | `ExposureController` dùng chung cho ảnh và video: ISO, tốc độ, EV, WB Kelvin + tint, lấy nét tay có thước khoảng cách; khóa AE/AF/AWB miễn phí cả khi quay; ở video khi tắt AE thì đặt `SENSOR_EXPOSURE_TIME`, `SENSOR_SENSITIVITY`, `SENSOR_FRAME_DURATION` qua Camera2Interop; giữ giá trị khi đổi ảnh ↔ video | Free | MVP | 2 | FCM-E01-03; FLC-E01-16 | Khi đặt ISO 200 và 1/50 s ở video 25 fps thì `CaptureResult` đúng hai giá trị và file vẫn 25 fps; khi khóa AE rồi lia từ tối sang sáng thì độ sáng file không đổi; khi chuyển ảnh ↔ video thì ISO, WB, nét giữ nguyên |
| FCM-E01-11 | `:filcam:manual` | Android 16 (API 36): hybrid AE (khóa ISO hoặc tốc độ, phần còn lại tự động) thay vòng AE tự viết của chế độ S/I; nhiệt độ màu và tint chính xác bằng API mới ⚠ tên API; máy dưới API 36 giữ cách cũ | Free | V1 | 1,5 | FCM-E01-10 | Khi chạy trên Android 16 ở chế độ S với 1/100 s thì ISO tự đổi theo cảnh, tốc độ giữ nguyên và độ sáng không nhấp nháy; khi chạy trên Android 14 thì chế độ S vẫn như cũ |

## FCM-E02 · Quay video có LUT

Mục tiêu: quay 1080p có LUT miễn phí trên máy tầm trung; 4K và ghi sạch có LUT để xem cho Pro; đổi LUT và cường độ ngay trên màn quay, đúng hai yêu cầu nhiều lượt "hữu ích" nhất trên Blackmagic Camera (297 và 105).

Ánh xạ Bảng 12: F2.1 → 04, 05, 06 · F2.2 → 07, 08 · F2.3 → 09, 10, 11 · F2.4 → 15, 16, 18, 19, 20. Thêm: 01 và 03 (spike), 02 (pipeline hai nhánh), 12 (màn quay), 13 (ống kính), 14 (khung tỉ lệ), 17 (recorder dự phòng).

Khóa AE/AF/AWB khi quay là `Free` (FCM-E01-10) dù Bảng 12 xếp "khóa phơi sáng" vào F2.4 Pro, vì F1.1 đã cho khóa miễn phí và không được thu hồi. FCM-E02-17 lên `MVP` nếu spike FCM-E02-01 cho thấy cách A (hai effect, hai luồng) không chạy trên ít nhất 6/8 máy.

Khối lượng: 20 feature · MVP 32 ngày · V1 14 ngày · tổng **46 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FCM-E02-01 | (qa) | 🧪 Spike 3 ngày: "ghi sạch + LUT xem" trên CameraX 1.6. Cách A: hai `CameraEffect` target riêng (PREVIEW có look; VIDEO_CAPTURE không look hoặc chỉ đường cong ghi), hai luồng camera. Cách B: một luồng Preview, `SurfaceProcessor` vẽ hai lần (có look ra màn hình, không look ra input surface của `MediaCodec` riêng). Đo trên 8 máy: CameraX có ép stream sharing không (`isSessionConfigSupported`), fps, độ trễ, lệch tiếng, nhiệt sau 10 phút | — | MVP | 3 | FLC-E01-16; FLC-E05-02 | Khi xong spike thì có bảng 8 máy × 2 cách (chạy được hay không, fps 1080p/4K, nhiệt) và quyết định đường chính ghi vào README mục 5.2; nếu cách A chạy trên dưới 6/8 máy thì FCM-E02-17 chuyển lên MVP và người điều phối được báo |
| FCM-E02-02 | `:filcam:video` | `VideoPipeline` hai nhánh: CameraX `Preview` + `VideoCapture<Recorder>` qua `SessionConfig`; nhánh PREVIEW chạy graph "look + công cụ đo", nhánh VIDEO_CAPTURE chạy graph "ghi" (in look, FM-Log hoặc không effect); kiểm cấu hình bằng `isSessionConfigSupported` trước khi bind; đổi look không dựng lại session; máy bị ép stream sharing thì chạy chế độ một nhánh (chỉ in LUT) | — | MVP | 4 | FLC-E01-16; FLC-E01-11; FCM-E02-01; FCM-E07-01 | Khi đổi 10 look liên tục lúc đang quay thì file không có khung đen và tiếng không đứt; khi ở chế độ in LUT thì khung trích từ file khớp khung preview cùng thời điểm (ΔE trung bình < 2, không tính lớp công cụ đo); khi máy chỉ chạy được stream sharing thì app tự vào chế độ một nhánh và ẩn ghi sạch |
| FCM-E02-03 | (qa) | 🧪 Spike 2 ngày: 4K30 có LUT trên máy tier B (Galaxy A55, A35, Redmi Note 14 Pro ⚠, OPPO Reno ⚠): fps preview, tỉ lệ khung rơi trong file, nhiệt và pin sau 10 phút, có và không grain; chốt 4K cho tier nào | — | MVP | 2 | FCM-E02-02; FLC-E05-03 | Khi xong spike thì có bảng 4 máy (fps, khung rơi, `ThermalStatus` và % pin sau 10 phút) và quy tắc 4K theo tier được ghi vào chính sách FCM-E07-02 |
| FCM-E02-04 | `:filcam:video` | Quay 1080p 24/25/30 fps, 60 fps khi máy hỗ trợ (F2.1): `QualitySelector` FHD, dự phòng HD; khóa fps bằng dải [n, n] (`setTargetFrameRate`, `CONTROL_AE_TARGET_FPS_RANGE`); chỉ hiện fps máy báo có; tiếng AAC khi bật micro (xin `RECORD_AUDIO` lần đầu bật, FLC-E06-05); lưu MP4 vào `Movies/FilCam` qua `MediaStoreOutputOptions` | Free | MVP | 3,5 | FCM-E02-02; FLC-E06-02; FLC-E06-05 | Khi quay 1080p 24 fps 60 giây thì `ffprobe` báo 24 fps (± 0,1), thời lượng 60 ± 0,2 giây và khung rơi < 0,5%; khi máy không có dải [24, 24] thì nút 24 bị ẩn; khi kill app giữa lúc quay thì phần đã ghi vẫn phát được; khi tắt tiếng thì app không xin quyền micro |
| FCM-E02-05 | `:filcam:video` | Quay 4K UHD 24/25/30 (F2.1) khi `UHD_RECORDING` hoặc `isSessionConfigSupported` xác nhận và tier cho phép theo spike FCM-E02-03; 4K60 chỉ ở tier A khi cấu hình được xác nhận và benchmark đạt ⚠ | Pro | MVP | 2 | FCM-E02-04; FCM-E02-03; FCM-E07-02 | Khi máy tier A quay 4K30 có LUT 5 phút thì file 3840×2160 và khung rơi < 1%; khi người dùng miễn phí chọn 4K thì paywall hiện và vẫn quay 1080p được; khi máy tier C thì không có lựa chọn 4K |
| FCM-E02-06 | `:filcam:video` | Codec và bitrate (F2.1): H.264 mặc định; H.265 khi `Recorder` cho chọn ⚠ (không thì chờ FCM-E02-17); 3 mức bitrate Tiêu chuẩn, Cao, Tối đa theo bảng README mục 5.2, kẹp theo `VideoCapabilities.getBitrateRange()`; hiện MB mỗi phút và số phút còn lại theo dung lượng trống | Free | MVP | 2,5 | FCM-E02-04 | Khi quay 1080p30 H.264 mức Cao thì bitrate trung bình nằm trong ±15% của 24 Mbps; khi encoder không nhận bitrate đã chọn thì app hạ về mức tối đa của encoder và báo; khi còn 3 GB thì số phút hiển thị lệch thực tế ≤ 10% |
| FCM-E02-07 | `:filcam:video` | Đổi LUT ngay trên màn hình quay (F2.2): dải look vuốt ngang, thanh cường độ 0–100% (FLC-E01-17), giữ để xem gốc, chia đôi A/B hai look; đổi được cả khi đang quay (ở chế độ in LUT thì báo "look mới sẽ vào file") | Free | MVP | 2,5 | FLC-E01-17; FCM-E02-02; FCM-E04-02 | Khi đổi look thì khung mới hiện trong ≤ 2 khung (≤ 67 ms ở 30 fps); khi kéo cường độ về 0 thì preview trùng khung không look (ΔE < 1); khi chia đôi A/B thì mỗi nửa đúng look đã chọn; khi bật TalkBack thì nghe được tên look và cường độ |
| FCM-E02-08 | `:filcam:video` | Chồng LUT kỹ thuật lên LUT sáng tạo (F2.2): chọn "Nguồn" (Rec.709; LUT kỹ thuật tự nhập; FM-Log và HLG từ V1) → LUT kỹ thuật vào `inputTransform`, look sáng tạo chạy sau; cường độ chỉ áp cho look sáng tạo; hai LUT gộp thành một texture (FLC-E01-20) | Free | MVP | 1,5 | FLC-E01-20; FCM-E02-07 | Khi chọn một LUT kỹ thuật và look "Teal" thì preview khớp việc áp hai LUT tuần tự bằng CPU (ΔE trung bình < 1) và vẫn ≥ 30 fps; khi cường độ bằng 0 thì preview là ảnh sau LUT kỹ thuật, không phải ảnh gốc |
| FCM-E02-09 | `:filcam:video` | Chế độ in LUT vào file (F2.3): graph ghi = look (adjust, LUT, vignette; không có công cụ đo); nội suy trilinear, tetrahedral ở tier A; khối look chưa áp khi quay (grain, halation trước V1; khung, date stamp) thì báo "Chưa áp khi quay: …" | Free | MVP | 1,5 | FCM-E02-02 | Khi quay in LUT thì khung giữa file khớp ảnh chụp cùng look cùng cảnh (ΔE trung bình < 2); khi look có khung thì app báo "Chưa áp khi quay: khung" và file không có khung |
| FCM-E02-10 | `:filcam:video` | Ghi sạch + LUT chỉ để xem (F2.3): nhánh VIDEO_CAPTURE không effect (từ V1 có thể chỉ có đường cong FM-Log), nhánh PREVIEW có look; chỉ hiện khi `VideoPipeline` báo hai nhánh độc lập; ghi sidecar (FCM-E02-11) | Pro | MVP | 2 | FCM-E02-02; FCM-E02-01 | Khi quay ghi sạch với look "Teal" thì khung trích từ file lệch khung quay không effect cùng cảnh ΔE trung bình < 1, còn preview có Teal; khi máy chạy chế độ một nhánh thì lựa chọn bị ẩn và màn "Máy của bạn" nêu lý do |
| FCM-E02-11 | `:filcam:video` | Sidecar cho clip ghi sạch: `<clip>.cube` 33³ (bake `inputTransform` + look + cường độ), `<clip>.flook` và `<clip>.fcm.json` (nguồn, look id@rev, cường độ, fps, góc màn trập, ISO, WB, ống kính, model máy, bản app; không GPS); lưu ở `Documents/FilCam/` ⚠; bảng nội bộ nối clip ↔ sidecar để trình chỉnh màu tự áp | Pro | MVP | 2 | FCM-E02-10; FLC-E01-19; FLC-E01-02 | Khi áp `.cube` sidecar lên clip sạch trong DaVinci Resolve thì khung ra khớp preview lúc quay (ΔE trung bình < 2, kiểm tay); khi mở clip đó trong trình chỉnh màu FilCam thì look và cường độ tự được áp; khi clip bị xóa khỏi máy thì sidecar mồ côi được liệt kê để dọn |
| FCM-E02-12 | `:filcam:video` | Màn quay: nút ghi, đồng hồ thời lượng, phút còn lại, pin, trạng thái nhiệt; tạm dừng và tiếp tục (`Recording.pause/resume`); giữ màn hình sáng, khóa chạm khi quay; dừng an toàn khi còn 500 MB; xem lại clip vừa quay (ExoPlayer) và mở sang trình chỉnh màu | Free | MVP | 2,5 | FCM-E02-04 | Khi còn 500 MB thì app dừng ghi, file phát được và có thông báo lý do; khi tạm dừng và tiếp tục 3 lần thì file liền một mạch và lệch tiếng ≤ 1 khung (clap test); khi bấm "Xem lại" thì clip phát ngay trong app |
| FCM-E02-13 | `:filcam:video` | Chọn ống kính khi quay (0.5×, 1×, tele) theo camera vật lý hoặc zoom ratio mà FLC-E05-02 dò được; chỉ đổi khi chưa ghi; nhớ ống kính theo chế độ | Free | MVP | 1,5 | FCM-E02-02; FLC-E05-02 | Khi máy lộ ống siêu rộng thì nút 0.5× hiện và file quay có góc rộng hơn; khi máy không lộ tele cho app bên thứ ba thì không có nút tele; khi đổi ống kính thì look và công cụ đo giữ nguyên |
| FCM-E02-14 | `:filcam:monitor` | Khung ngắm tỉ lệ (2.39:1, 1.85:1, 16:9, 4:5, 1:1, 9:16) và vùng an toàn chữ/nút của TikTok và Reels, vẽ trên nhánh preview, không vào file | Free | MVP | 1,5 | FCM-E01-06 | Khi bật khung 2.39:1 thì hai dải mờ hiện trên preview còn file vẫn 16:9 đủ khung; khi bật vùng an toàn 9:16 thì vùng che khớp đo tay trên ảnh chụp màn hình của app đích ⚠ |
| FCM-E02-15 | `:filcam:manual` | Góc màn trập (F2.4): 45/90/144/172,8/180/216/270/360°, t = (góc / 360) / fps; kẹp theo `SENSOR_INFO_EXPOSURE_TIME_RANGE` và thời lượng khung; trợ lý chống nhấp nháy 50 Hz/60 Hz; bù sáng bằng ISO; báo "Cần ND n nấc" khi ISO thấp nhất vẫn dư sáng. Tốc độ nhập tay vẫn Free (FCM-E01-10) | Pro | V1 | 2 | FCM-E01-10; FCM-E02-04 | Khi đặt 180° ở 24 fps thì `SENSOR_EXPOSURE_TIME` là 20,8 ms (± 2%); khi bật chống nhấp nháy 50 Hz ở 30 fps thì app chọn 1/50 s (216°) hoặc 1/100 s (108°) và đèn huỳnh quang không có sọc (kiểm tay); khi ISO thấp nhất vẫn dư 1 EV thì hiện "Cần ND 1 nấc (ND2)" |
| FCM-E02-16 | `:filcam:manual` | Chuyển nét A → B (rack focus, F2.4): lưu hai điểm nét (khoảng cách lấy nét), chuyển trong 0,5–3 giây theo đường ease; chỉ trên máy có lấy nét tay | Pro | V1 | 1,5 | FCM-E01-10 | Khi bấm chuyển nét 2 giây thì `LENS_FOCUS_DISTANCE` trong `CaptureResult` đi từ A tới B trong 2 ± 0,2 giây; khi máy không có lấy nét tay thì tính năng bị ẩn |
| FCM-E02-17 | `:filcam:video` | Recorder dự phòng ("tee"): một luồng Preview; `SurfaceProcessor` vẽ hai lần (có look ra màn hình; sạch hoặc FM-Log ra input surface `MediaCodec`); `AudioRecord` + Media3 Muxer; đồng bộ tiếng theo timestamp; tự chọn codec, profile, GOP, bitrate, micro. Dùng khi máy không có hai nhánh độc lập hoặc khi `Recorder` không cho chọn HEVC hay micro ⚠ | — | V1 | 5 | FCM-E02-01; FCM-E02-02 | Khi quay 10 phút bằng recorder dự phòng thì lệch tiếng ở cuối clip ≤ 1 khung (clap test); khi kill app giữa lúc quay thì file vẫn phát được tới giây gần nhất ⚠; khi chạy trên máy bị ép stream sharing thì ghi sạch + LUT xem hoạt động |
| FCM-E02-18 | `:filcam:video` | Âm thanh nâng cao (F2.4): đồng hồ mức (peak, RMS, giữ đỉnh, đỏ khi > −1 dBFS); liệt kê micro (`AudioManager.getDevices(GET_DEVICES_INPUTS)`: mic trong, USB-C, tai nghe, Bluetooth), hiện mic đang dùng, chọn mic qua recorder dự phòng khi `Recorder` không cho chọn ⚠; báo khi mic bị rút giữa chừng | Pro | V1 | 2,5 | FCM-E02-04; FCM-E02-17 | Khi cắm bộ thu micro không dây qua USB-C thì app hiện tên thiết bị và tiếng trong file đến từ mic đó (kiểm bằng che mic trong); khi rút mic lúc đang quay thì app chuyển về mic trong, không dừng ghi và ghi mốc cảnh báo vào sidecar; khi tiếng vượt −1 dBFS thì đồng hồ chuyển đỏ |
| FCM-E02-19 | `:filcam:video` | Chống rung video (F2.4): tắt, chuẩn (`setVideoStabilizationEnabled`) hoặc preview stabilization (`setPreviewStabilizationEnabled`), nhóm tính năng `VIDEO_STABILIZATION` ⚠; báo mức crop; kiểm look vẫn hiện khi bật | Pro | V1 | 1,5 | FCM-E02-02; FCM-E07-01 | Khi bật chống rung trên máy hỗ trợ thì preview vẫn có look và file đúng chế độ ghi; khi máy không hỗ trợ thì lựa chọn bị ẩn; khi bật thì mức crop hiển thị khớp đo trên file (± 2%) |
| FCM-E02-20 | `:filcam:video` | Grain và halation động khi quay (F2.4): pass lõi trên nhánh ghi, seed = hash(clipId, số khung); halation ¼ độ phân giải ở tier A, ⅛ ở tier B, tắt ở tier C; tự tắt khi nhiệt ≥ `MODERATE` | Pro | V1 | 1,5 | FCM-E02-09; FLC-E01-12; FLC-E01-13; FCM-E07-05 | Khi quay 1080p30 với grain + halation trên máy tầm trung chuẩn thì khung rơi < 1%; khi so hai khung liên tiếp thì mẫu grain khác nhau; khi nhiệt lên `MODERATE` thì pass tắt và file không bị giật |

## FCM-E03 · Log và HDR

Mục tiêu: một hồ sơ Log chạy được trên mọi máy đủ điều kiện mà không cần Log của hãng (FM-Log, kiểu mcpro24fps), HLG 10-bit trên máy hỗ trợ, và luôn có LUT kỹ thuật tương ứng để chỉnh ở FilCam hay trên máy tính.

Ánh xạ Bảng 12: F3.1 → 01–05 · F3.2 → 06, 07 · F3.3 (Apple Log, iOS) → FCM-E10-07. Thêm: 08 (FM-Log 10-bit, V2).

Quay Samsung Log từ app bên thứ ba không nằm trong phạm vi: không có API Log chung giữa các hãng, và Samsung Log trong Blackmagic Camera đến từ hợp tác riêng ⚠. Spike FCM-E05-09 kiểm lại điều này; clip Samsung Log quay bằng camera gốc vẫn được chỉnh ở FCM-E05-11. Công thức, bảng tham chiếu và cách hướng dẫn phơi sáng ở [README mục 5.3](README.md#53-log-và-hdr-fcm-e03).

Khối lượng: 8 feature · V1 15,5 ngày · V2 3 ngày · tổng **18,5 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FCM-E03-01 | (qa) | 🧪 Spike 2 ngày: banding của pseudo-Log 8-bit. Quay trời xanh, tường trơn và ramp in bằng (a) đường cong ISP `TONEMAP_MODE_CONTRAST_CURVE`, (b) đường cong GPU trên luồng 8-bit có và không dither, (c) GPU trên luồng 10-bit khi có; chỉnh về 709 + look mạnh rồi đếm bậc banding; thử H.264/H.265 ở 3 mức bitrate; chốt đường mặc định, tham số FM-Log v1 và bitrate tối thiểu | — | V1 | 2 | FCM-E02-02 | Khi xong spike thì có bộ ảnh so sánh, bảng số bậc banding theo cách × bitrate trên 4 máy tier A và B, tham số FM-Log v1 được đóng băng và bitrate tối thiểu được ghi vào README mục 5.3 |
| FCM-E03-02 | `:filcam:log` | Đặc tả FM-Log v1 (`inputTransform.from = fm-log`): y = 0,06 + 0,90 · log₉(1 + 8x), hàm ngược, điểm tham chiếu; hằng số dùng chung Kotlin, GLSL, Swift; fixture đưa vào `spec/look/`; sinh LUT kỹ thuật FM-Log → Rec.709 (bản trung tính và bản tương phản; .cube 33³ và 65³) bằng pipeline CPU; manifest `owned` | Free | V1 | 2 | FCM-E03-01; FLC-E01-06; FLC-E04-03 | Khi chạy test thì f⁻¹(f(x)) = x (sai ≤ 1e-6) trên [0, 1] và f(0,18) = 0,425 ± 0,002; khi áp LUT FM-Log → Rec.709 lên ramp FM-Log thì ra đúng đường Rec.709 (sai ≤ 1/255); khi CI chạy lint thì hai LUT có manifest |
| FCM-E03-03 | `:filcam:log` | FM-Log qua ISP (F3.1): `TONEMAP_MODE_CONTRAST_CURVE` + `TonemapCurve` lấy mẫu FM-Log (tối đa `TONEMAP_MAX_CURVE_POINTS`) đặt bằng `Camera2CameraControl`; nhánh ghi không effect; nhánh preview = FM-Log → 709 + look; ghi `fm-log` vào sidecar; chỉ hiện khi máy có `CONTRAST_CURVE` và spike đạt | Pro | V1 | 2,5 | FCM-E03-02; FCM-E02-10; FCM-E07-01; FLC-E01-20 | Khi quay thẻ xám 18% phơi đúng thì mức tín hiệu trong file là 0,425 ± 0,03; khi áp LUT FM-Log → Rec.709 lên file thì ColorChecker lệch bản quay Rec.709 cùng cảnh không quá ngưỡng chốt ở spike (mục tiêu ΔE trung bình < 5 ⚠); khi đang quay thì preview trông như Rec.709 có look, không xám |
| FCM-E03-04 | `:filcam:log` | FM-Log qua GPU (dự phòng, F3.1): graph ghi = tuyến tính hóa (ngược OETF Rec.709) → FM-Log → dither blue-noise ±0,5 LSB; dùng khi máy không có `CONTRAST_CURVE` hoặc ISP bỏ qua đường cong; sidecar ghi `path: gpu` | Pro | V1 | 2 | FCM-E03-02; FCM-E02-02 | Khi quay thẻ xám 18% thì mức trong file là 0,425 ± 0,04; khi so ramp trời với bản không dither ở cùng bitrate thì số bậc banding thấy được giảm (cách đếm của spike); khi quay 1080p30 trên máy tầm trung chuẩn thì khung rơi < 1% |
| FCM-E03-05 | `:filcam:monitor` | Hướng dẫn phơi sáng cho Log (F3.1): false color theo bảng FM-Log (README mục 5.3), zebra mặc định 0,90 khi quay FM-Log, chọn đo trên tín hiệu Log hay trên ảnh sau LUT; chấm đo điểm hiện giá trị tín hiệu và mốc "xám 18% = 0,425" | Pro | V1 | 1,5 | FCM-E01-06; FCM-E03-03 | Khi chĩa vào thẻ xám 18% phơi đúng thì chấm đo hiện 0,42–0,43 và false color tô xanh lá; khi vùng trời vượt 0,92 thì false color tô đỏ; khi chọn "đo trên 709" thì các dải chuyển sang bảng Rec.709 |
| FCM-E03-06 | (qa) | 🧪 Spike 2 ngày: `CameraEffect`/`SurfaceProcessor` với luồng 10-bit HLG (EGL BT.2020 HLG ⚠, `GL_EXT_YUV_target` ⚠) trên 4 máy tier A: preview có look trên luồng HLG được không; in look vào file 10-bit được không; ghi sạch HLG + preview look | — | V1 | 2 | FCM-E02-02 | Khi xong spike thì có bảng 4 máy × 3 trường hợp và quyết định phạm vi của FCM-E03-07 (mặc định: ghi sạch HLG + preview look) |
| FCM-E03-07 | `:filcam:log` | HLG 10-bit (F3.2): `DynamicRange.HLG_10_BIT` trên `VideoCapture`, nhóm tính năng HLG ⚠, kiểm `isSessionConfigSupported` trước khi hiện; HEVC Main10; ghi sạch; preview = LUT kỹ thuật HLG → Rec.709 (theo BT.2408 ⚠) + look; ghi `hlg` vào sidecar | Pro | V1 | 3,5 | FCM-E03-06; FCM-E02-10; FCM-E07-01; FLC-E01-20 | Khi máy hỗ trợ (ví dụ Galaxy S24, Pixel 8) thì `ffprobe` báo hevc Main10, `bt2020`, `arib-std-b67`; khi `isSessionConfigSupported` trả false thì nút HLG bị ẩn; khi quay HLG thì preview có look, không bệt hay cháy trên màn SDR |
| FCM-E03-08 | `:filcam:log` | FM-Log 10-bit: từ luồng 10-bit (HLG) của camera tính FM-Log mở rộng cho vùng sáng trên trắng tham chiếu và ghi HEVC Main10; LUT kỹ thuật tương ứng; cần tên nguồn mới trong `inputTransform.from` ⚠ | Pro | V2 | 3 | FCM-E03-06; FCM-E03-04 | Khi quay cảnh có vùng sáng vượt trắng tham chiếu thì file FM-Log 10-bit giữ chi tiết ở vùng mà FM-Log 8-bit đã cháy (so khung); khi áp LUT kỹ thuật thì thẻ xám 18% về cùng mức với bản 8-bit (ΔE < 2) |

## FCM-E04 · Quản lý LUT

Mục tiêu: một thư viện LUT dùng cho cả ảnh, video và chỉnh clip; nhập mọi định dạng phổ biến miễn phí; tách LUT sáng tạo và LUT kỹ thuật.

Ánh xạ Bảng 12: F4.1 → 01, 02, 03 · F4.2 → 04, 05, 06 · F4.3 → 07. Thêm: 08 (quét QR ngay trong app).

Nhập .cube, .3dl, HALD luôn miễn phí (FLC-E01-04, FLC-E01-05). Dựng 12 look miễn phí, 24 look Pro và LUT kỹ thuật là việc nội dung, không tính ở đây.

Khối lượng: 8 feature · Có sẵn 1 ngày · MVP 5,5 ngày · V1 4,5 ngày · tổng **11 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FCM-E04-01 | `:filcam:lutlib` | Gom 43 look, LUT .cube đã nhập và công thức đã lưu của 1.0.21 vào thư viện lõi; chạy chuyển dữ liệu khi cập nhật | Free | Có sẵn | 1 | FLC-E02-01; FLC-E02-03; FLC-E01-04 | Khi cập nhật từ 1.0.21 có 10 LUT đã nhập và 3 công thức thì sau cập nhật đủ 13 mục và render giống bản cũ; khi chuyển lỗi thì file gốc còn nguyên |
| FCM-E04-02 | `:filcam:lutlib` | Thư viện LUT cho video (F4.1): nhập .cube 17/33/65, .3dl, HALD, nhiều file từ .zip (bộ nhập lõi); phân loại "Sáng tạo" hay "Kỹ thuật (Log → 709)" (gợi ý theo tên, `TITLE`, dải đầu vào; người dùng sửa được); thư mục, yêu thích, thẻ, tìm kiếm | Free | MVP | 2,5 | FLC-E01-05; FLC-E02-01 | Khi nhập zip 30 LUT có 2 file hỏng thì 28 look được tạo và báo cáo nêu tên, lý do của 2 file lỗi; khi nhập file tên "…Log to Rec709…" thì look được gợi ý vào nhóm Kỹ thuật; khi tìm "teal" thì ra đúng các look có tên hoặc thẻ chứa từ đó |
| FCM-E04-03 | `:filcam:lutlib` | Ảnh thu nhỏ look render trên khung hình hiện tại của camera (F4.1): lấy khung preview thu nhỏ mỗi 2 giây khi mở bộ chọn, render theo lô qua FLC-E02-02 | Free | MVP | 1 | FLC-E02-02; FCM-E02-02 | Khi mở bộ chọn 60 look lúc đang ngắm thì thumbnail đầu hiện < 300 ms và cả lưới < 2 giây trên máy tầm trung chuẩn; khi lia sang cảnh khác thì thumbnail cập nhật trong ≤ 2 giây |
| FCM-E04-04 | `:filcam:lutlib` | Bộ look khởi đầu miễn phí (F4.2): 12 look điện ảnh tự làm (tên tự đặt, qua `NameGuard`, manifest `owned`) + 43 look ảnh hiện có dùng được cho video; ghi vào `free-tier.json` | Free | MVP | 1 | FCM-E04-01; FLC-E03-04; FLC-E04-03 | Khi cài mới rồi bật chế độ máy bay thì 55 look miễn phí dùng được cho cả ảnh và video; khi PR chuyển một look trong danh sách này sang Pro thì CI fail |
| FCM-E04-05 | `:filcam:lutlib` | Gói 24 look điện ảnh Pro (F4.2): xem trước trên kính ngắm và trong trình chỉnh màu; chỉ khóa khi bấm quay, lưu ảnh hay xuất ("thử trước, trả khi lưu") | Pro | MVP | 1 | FCM-E04-04; FCM-E08-02 | Khi người dùng miễn phí chọn look Pro thì preview đổi ngay, còn khi bấm quay thì paywall hiện và đóng paywall thì look quay về look miễn phí trước đó; khi có Pro thì không bao giờ thấy paywall cho gói này |
| FCM-E04-06 | `:filcam:lutlib` | Bộ LUT kỹ thuật chuẩn (F4.2): FM-Log, HLG, Apple Log, Samsung Log ⚠ → Rec.709, có nhãn nguồn; chọn "Nguồn" thì LUT tự gắn vào `inputTransform`; lưu file .cube về máy để dùng ở app khác | Free | V1 | 1 | FCM-E03-02; FCM-E03-07; FCM-E05-10; FCM-E02-08 | Khi chọn Nguồn "FM-Log" thì preview tự dùng LUT FM-Log → Rec.709; khi bấm "Lưu file .cube" thì file vào `Download/FilCam` ⚠ và mở được trong DaVinci Resolve |
| FCM-E04-07 | `:filcam:lutlib` | Nhận look từ Filmode và Filmode Studio (F4.3): mục "Từ Filmode Studio", "Từ Filmode" qua provider dùng chung; mở `.flook`, QR, link; khối chưa áp khi quay thì báo tên; bật đồng bộ thư viện khi đã đăng nhập | Free | V1 | 2 | FLC-E02-08; FLC-E02-09; FLC-E02-06 | Khi lưu look trong Studio thì FilCam trên cùng máy thấy look đó mà không cần đăng nhập; khi mở look có khung thì FilCam áp phần màu và hiện "Chưa áp khi quay: khung"; khi đăng nhập trên máy thứ hai thì look đã đồng bộ hiện trong ≤ 1 phút |
| FCM-E04-08 | `:filcam:lutlib` | Quét QR look ngay trong app: chế độ "Quét mã" dùng `ImageAnalysis` (gỡ `VideoCapture` khi quét), giải mã bằng thư viện mã vạch chạy trên máy ⚠ (dung lượng APK) và codec của lõi | Free | V1 | 1,5 | FLC-E01-03; FCM-E02-02 | Khi quét QR recipe in cạnh 3 cm thì look mở trong ≤ 2 giây; khi QR hỏng thì báo "Mã không hợp lệ"; khi thoát chế độ quét thì camera quay lại cấu hình quay trước đó |

## FCM-E05 · Chỉnh màu clip có sẵn

Mục tiêu: chỉnh màu clip đã quay (bằng FilCam, camera gốc Samsung, iPhone) ngay trên điện thoại: LUT, chỉnh cơ bản, đường cong, chuyển Log → Rec.709, scopes, xuất hàng loạt bằng Media3.

Ánh xạ Bảng 12: F5.1 → 01–07 · F5.2 → 09, 10, 11 · F5.3 → 12 · F5.4 → 06, 13, 14. Thêm: 08 (bánh xe màu, không có trong F5.1).

"Free (giới hạn thời lượng)" của F5.1 được chốt là xuất clip ≤ 60 giây và ≤ 1080p; con số này ghi vào `free-tier.json` và không bao giờ giảm. Trình phát và xuất dùng `LookGlEffect` của lõi (FLC-E01-21), không dùng thẳng `SingleColorLut` vì chưa rõ nó nhận đầu vào tuyến tính hay gamma ⚠.

Khối lượng: 14 feature · MVP 12,5 ngày · V1 17,5 ngày · tổng **30 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FCM-E05-01 | `:filcam:grade` | Mở clip bằng Photo Picker (video) và đọc thông số (`MediaExtractor`): độ phân giải, fps, codec, bit depth, transfer, primaries, thời lượng, có tiếng hay không; báo trước clip không mở được (ProRes, codec máy không giải) ⚠ | Free | MVP | 1,5 | FLC-E06-01 | Khi chọn clip 4K HEVC 10-bit thì màn thông tin ghi đúng 3840×2160, 10-bit và transfer; khi chọn clip ProRes thì app báo "Máy không giải mã được định dạng này" thay vì crash; app không xin `READ_MEDIA_VIDEO` |
| FCM-E05-02 | `:filcam:grade` | Trình xem trước có look: ExoPlayer + `setVideoEffects(LookGlEffect)`; tua theo khung, lặp một đoạn, chia đôi trước/sau, giữ để xem gốc | Free | MVP | 2,5 | FLC-E01-21; FCM-E05-01 | Khi phát clip 1080p30 có look trên máy tầm trung chuẩn thì rơi không quá 1% khung; khi kéo thanh tua thì khung hiện < 200 ms; khi chia đôi thì nửa trái là gốc, nửa phải có look |
| FCM-E05-03 | `:filcam:grade` | Chỉnh cơ bản (F5.1): look + cường độ, phơi sáng, nhiệt độ màu/tint, tương phản, highlights/shadows, bão hòa (khối `adjust`); áp cả clip; lưu thiết lập thành look mới | Free | MVP | 2 | FCM-E05-02; FLC-E01-01 | Khi kéo phơi sáng +1 EV thì preview đổi theo từng khung, không giật; khi lưu thành look rồi dùng look đó trên kính ngắm thì màu khớp khung clip (ΔE trung bình < 2) |
| FCM-E05-04 | `:filcam:grade` | Đường cong (F5.1): master + R/G/B, tối đa 8 điểm mỗi kênh, spline đơn điệu; preview bằng texture 1D 256 qua `EffectPass` đặt trước LUT sáng tạo; bake vào LUT 33³ khi lưu (quy tắc `adjust` của lõi) | Free | MVP | 2,5 | FCM-E05-03; FLC-E01-06 | Khi kéo một điểm thì preview đổi trong 1 khung; khi lưu rồi mở lại thì look đã bake khớp preview lúc chỉnh (ΔE trung bình < 1); đường cong không đảo chiều ở mọi bộ điểm trong test |
| FCM-E05-05 | `:filcam:grade` | Cắt đầu và cuối clip trước khi xuất (`ClippingConfiguration`) | Free | MVP | 1 | FCM-E05-02 | Khi cắt đoạn 10–20 giây thì file xuất dài 10 ± 0,1 giây và tiếng khớp hình |
| FCM-E05-06 | `:filcam:grade` | Xuất một clip (F5.4, phần miễn phí): Media3 Transformer + `LookGlEffect`; giữ fps và tiếng (chép nguyên khi không cắt); H.264/H.265; bitrate như gốc hoặc tự chọn; lưu `Movies/FilCam` qua MediaStore; miễn phí cho clip ≤ 60 giây và ≤ 1080p (ghi vào `free-tier.json`) | Free | MVP | 2,5 | FCM-E05-03; FLC-E06-02 | Khi xuất clip 30 giây 1080p thì khung giữa khớp preview (ΔE trung bình < 2), tiếng giữ nguyên và file vào album FilCam; khi người dùng miễn phí xuất clip 90 giây thì app cho cắt về 60 giây hoặc mở Pro; khi hủy xuất thì không còn file rác |
| FCM-E05-07 | `:filcam:grade` | Bỏ giới hạn thời lượng và xuất 4K cho Pro (F5.1) | Pro | MVP | 0,5 | FCM-E05-06; FCM-E08-02 | Khi người có Pro xuất clip 4K 5 phút thì file 3840×2160 đủ 5 phút; khi người dùng miễn phí chọn 4K thì paywall hiện |
| FCM-E05-08 | `:filcam:grade` | Bánh xe màu lift/gamma/gain + offset kiểu ASC CDL (slope, offset, power, saturation); nhập và xuất `.cdl` ⚠; bake vào LUT khi lưu | Pro | V1 | 2,5 | FCM-E05-04 | Khi đặt slope, offset, power bằng giá trị mẫu thì kết quả khớp công thức CDL tính bằng CPU (sai ≤ 1/255); khi xuất `.cdl` rồi nhập lại thì giá trị giữ nguyên |
| FCM-E05-09 | (qa) | 🧪 Spike 3 ngày: (a) app bên thứ ba có bật được Samsung Log khi quay không (vendor tag, Camera2 ⚠); (b) đường cong và gamut Samsung Log từ tài liệu Samsung và clip mẫu Galaxy S24 Ultra, S25 để tự làm LUT Samsung Log → 709; (c) giấy phép LUT chính hãng; (d) Media3 có giữ 10-bit khi giải mã clip Log 10-bit gắn nhãn SDR và clip Apple Log HEVC không | — | V1 | 3 | FCM-E05-01 | Khi xong spike thì có kết luận có/không cho (a), đường cong và sai số LUT tự làm so với LUT chính hãng trên 5 clip (ΔE trung bình), kết luận giấy phép và bảng bit depth thực tế trong GL cho 4 loại clip |
| FCM-E05-10 | `:filcam:grade` | LUT kỹ thuật Apple Log → Rec.709 (theo đặc tả Apple Log công khai ⚠) và Samsung Log → Rec.709 (nếu spike đạt), sinh bằng pipeline CPU, manifest `owned`; dùng chung cho FilCam iOS | Free | V1 | 1,5 | FCM-E05-09; FLC-E01-06; FLC-E04-03 | Khi áp LUT Apple Log → 709 lên 5 clip Apple Log mẫu thì thẻ xám về 0,40–0,43 và ColorChecker lệch LUT tham chiếu không quá ngưỡng của spike; khi CI chạy lint thì hai LUT có manifest |
| FCM-E05-11 | `:filcam:grade` | Chuyển Log → Rec.709 (F5.2): chọn Nguồn (Rec.709, HLG, FM-Log, Samsung Log ⚠, Apple Log); tự nhận từ sidecar FilCam, từ `KEY_COLOR_TRANSFER` (HLG, PQ) và gợi ý Apple Log, Samsung Log theo metadata máy quay ⚠; LUT kỹ thuật vào `inputTransform` | Pro | V1 | 2,5 | FCM-E05-03; FCM-E05-10; FCM-E02-11; FLC-E01-20 | Khi mở clip FM-Log có sidecar thì Nguồn tự là FM-Log và look đã dùng lúc quay tự áp; khi mở clip HLG thì Nguồn tự là HLG; khi chọn Apple Log cho clip mẫu thì preview khớp áp LUT tham chiếu trong Resolve (ΔE trung bình < 2, kiểm tay) |
| FCM-E05-12 | `:filcam:grade` | Scopes cho clip (F5.3): waveform luma, RGB parade, vectorscope (đường tông da, ô 75%), histogram; dùng renderer FCM-E01-07; cập nhật từng khung khi tạm dừng | Pro | V1 | 2 | FCM-E01-07; FCM-E05-02 | Khi mở clip thanh màu SMPTE 75% thì các điểm vectorscope rơi vào đúng 6 ô mục tiêu; khi tăng đỏ thì cột R của parade đi lên tương ứng; khi phát 1080p30 có scopes thì rơi không quá 2% khung |
| FCM-E05-13 | `:filcam:grade` | Tone map HDR → SDR khi xuất (F5.4): clip HLG/PQ xuất ra SDR có look (`HDR_MODE_TONE_MAP_HDR_TO_SDR_USING_OPEN_GL` từ API 29, `…_USING_MEDIACODEC` từ API 31 ⚠); tùy chọn giữ HDR khi không áp look | Pro | V1 | 2 | FCM-E05-06; FCM-E05-11 | Khi xuất clip HLG thành SDR có look thì file là BT.709 8-bit và vùng sáng không bị bệt xám (so với cách Google Photos hiển thị, kiểm tay); khi máy dưới API 29 thì tùy chọn HDR bị ẩn |
| FCM-E05-14 | `:filcam:grade` | Xuất hàng loạt (F5.4): hàng đợi Room (clip + look + thiết lập); áp một look cho nhiều clip, chép và dán thiết lập; WorkManager `setForeground` với loại `mediaProcessing` (API 35+) hoặc `dataSync` ⚠; chạy lần lượt từng job; thông báo tiến độ; job dở dang chạy lại từ đầu sau khi app bị kill; tạm dừng khi nhiệt ≥ `SEVERE` hoặc pin < 15% không sạc | Pro | V1 | 4 | FCM-E05-06; FCM-E07-05 | Khi xếp 20 clip 1080p rồi tắt màn hình thì cả 20 xuất xong và có thông báo tổng kết; khi kill app ở clip 7 thì mở lại tiếp từ clip 7 và không còn file rác; khi máy nóng `SEVERE` thì hàng đợi tạm dừng và tự chạy lại khi mát |

## FCM-E06 · Tạo và xuất LUT

Mục tiêu: biến bản chỉnh thành LUT dùng được ở app khác (CapCut bản máy tính, VN, DaVinci Resolve), và tạo LUT từ ảnh mẫu.

Ánh xạ Bảng 12: F6.1 → 01, 05 · F6.2 → 02 · F6.3 → 03, 04. Thêm: 06 (hiệu chỉnh bằng thẻ màu, V2).

F6.2 dùng Match v1 của lõi (FLC-E01-18), không phụ thuộc module của Studio. Chia sẻ look qua QR và link là `Free` (lệch Bảng 12) vì codec QR và link look của lõi miễn phí ở cả ba app; xuất file .cube vẫn là `Pro`.

Khối lượng: 6 feature · V1 7,5 ngày · V2 3 ngày · tổng **10,5 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FCM-E06-01 | `:filcam:lutmaker` | Lưu bản chỉnh (clip, khung camera) thành look và xuất .cube 33/65 + HALD (F6.1): chọn "gồm LUT kỹ thuật" (Log → look) hay "chỉ look" (709 → look); ghi `TITLE`, tác giả; báo phần không đi theo LUT (grain, halation, vignette) | Pro | V1 | 1,5 | FLC-E01-19; FCM-E05-04 | Khi xuất .cube 33 "gồm LUT kỹ thuật" từ clip FM-Log rồi áp lên clip gốc trong DaVinci Resolve thì khớp preview FilCam (ΔE trung bình < 1,5, kiểm tay); khi look có grain thì màn xuất liệt kê "grain không đi theo LUT" |
| FCM-E06-02 | `:filcam:lutmaker` | LUT từ ảnh mẫu (F6.2): chọn ảnh tham chiếu (Photo Picker) và khung đích (khung camera hoặc khung clip) → Match v1 của lõi → LUT 33³; cường độ; lưu thành look | Pro | V1 | 2 | FLC-E01-18; FCM-E05-02 | Khi match từ ảnh mẫu tông cam thì LUT tạo xong < 500 ms trên máy tầm trung chuẩn và ô xám trung tính không lệch quá ngưỡng của lõi; khi lưu thì look dùng được ngay trên kính ngắm |
| FCM-E06-03 | `:filcam:lutmaker` | Hồ sơ xuất sang app khác (F6.3): CapCut bản máy tính, VN, DaVinci Resolve, LumaFusion, app camera có nhập LUT (lưới 17/33/65, tên file ASCII, `DOMAIN_MIN/MAX` ⚠ theo từng app); gói .zip kèm hướng dẫn ngắn; chia sẻ qua share sheet | Pro | V1 | 1,5 | FCM-E06-01 | Khi xuất hồ sơ "Resolve" thì .cube mở được và đúng màu trong Resolve; khi xuất hồ sơ "VN" thì file nhập được vào VN trên Android (kiểm tay); khi tên look có dấu tiếng Việt thì tên file xuất là ASCII không dấu |
| FCM-E06-04 | `:filcam:lutmaker` | Chia sẻ look qua QR và link (F6.3): recipe không có LUT riêng qua QR (FLC-E01-03); look có LUT riêng qua link cloud (FLC-E08-03) hoặc file `.flook` | Free | V1 | 1 | FLC-E01-03; FLC-E08-03 | Khi chia sẻ look dựng sẵn đã chỉnh cường độ thì QR mở đúng look trong Filmode và Studio; khi look có LUT riêng thì app đề nghị link hoặc file và link mở được trên máy chưa đăng nhập |
| FCM-E06-05 | `:filcam:lutmaker` | LUT Maker trên khung camera: đóng băng khung đang ngắm, dựng look bằng công cụ chỉnh màu (cơ bản, đường cong, bánh xe), lưu và dùng ngay khi quay | Pro | V1 | 1,5 | FCM-E05-08; FCM-E06-01 | Khi dựng look trên khung đóng băng rồi bấm "Dùng ngay" thì kính ngắm áp look đó trong ≤ 1 giây và khung quay sau đó khớp khung đóng băng cùng cảnh (ΔE < 2) |
| FCM-E06-06 | `:filcam:lutmaker` | Hiệu chỉnh màu bằng thẻ 24 ô: dò thẻ trên khung (chạm 4 góc), tính ma trận 3×3 + đường cong từng kênh → LUT hiệu chỉnh máy hoặc ống kính; dùng để khớp màu hai máy quay | Pro | V2 | 3 | FCM-E06-01 | Khi chụp thẻ trên hai máy khác hãng rồi áp LUT hiệu chỉnh thì ΔE trung bình giữa hai máy trên 24 ô giảm ít nhất một nửa |

## FCM-E07 · Tương thích thiết bị

Mục tiêu: không để một hãng máy kéo điểm app xuống. 29% đánh giá 1–2★ của Blackmagic Camera và mcpro24fps nhắc tên một hãng máy; FilCam phải biết trước máy làm được gì, ẩn thứ không làm được, đo lỗi theo hãng và công bố danh sách máy.

Ánh xạ Bảng 12: F7.1 → 01, 02, 03 · F7.2 → 04, 08 · F7.3 → 05, 07. Thêm: 06 (ma trận và quy trình test), 09 (đo độ ổn định theo hãng).

Hai phần được đưa sớm hơn Bảng 12: báo lỗi theo máy trong app (FCM-E07-04) và dừng ghi an toàn khi nóng (FCM-E07-05) lên `MVP`, vì lỗi theo máy và mất file xuất hiện ngay tuần đầu ra mắt. Tier A/B/C, quirk theo model và theo dõi nhiệt nền là của lõi (FLC-E05-04); FilCam chỉ thêm chính sách cho video.

Khối lượng: 9 feature · MVP 12 ngày · V1 6,5 ngày · tổng **18,5 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FCM-E07-01 | `:filcam:devices` | Hồ sơ năng lực video của FilCam (F7.1) trên `CameraCapabilities`: mức phần cứng Camera2 từng camera, fps theo độ phân giải, dải AE fps, encoder H.264/HEVC/Main10 và bitrate tối đa, HLG, UHD, chống rung, `TONEMAP` modes và số điểm, RAW, kết quả `isSessionConfigSupported` cho các cấu hình FilCam (hai nhánh 1080p/4K, HLG); cache theo build fingerprint | — | MVP | 2 | FLC-E05-02 | Khi chạy trên 10 máy ma trận FilCam thì bảng năng lực khớp kiểm tay (so với CameraX Info ⚠); khi mở lần hai thì đọc từ cache < 50 ms; khi xuất JSON thì không có thông tin cá nhân |
| FCM-E07-02 | `:filcam:devices` | Chính sách tính năng theo tier (A/B/C của lõi) + danh sách cho phép/chặn theo model qua remote config: bảng quyết định cho 4K, 60 fps, ghi sạch, nội suy nhánh ghi, grain/halation khi quay, FM-Log ISP/GPU, HLG; kill switch từng tính năng theo model; tính năng bị chặn thì ẩn, không hiện rồi báo lỗi | — | MVP | 2 | FCM-E07-01; FLC-E05-04; FLC-E05-09 | Khi remote config chặn 4K cho một model thì lần mở sau nút 4K bị ẩn trên máy đó; khi máy tier C thì không có 4K và không có grain khi quay; khi mở lần đầu lúc offline thì dùng bảng mặc định đóng gói |
| FCM-E07-03 | `:filcam:devices` | Màn "Máy của bạn": liệt kê tính năng có/không kèm lý do ngắn ("Hãng máy không mở 24 fps cho app khác"); nút sao chép báo cáo năng lực | — | MVP | 1 | FCM-E07-02 | Khi mở màn trên máy không có 24 fps thì dòng 24 fps ghi "Không có" kèm lý do; khi bấm sao chép thì clipboard có JSON năng lực, không có thông tin cá nhân |
| FCM-E07-04 | `:filcam:devices` | Báo lỗi theo máy ngay trong app (F7.2, đưa lên MVP): chọn tính năng lỗi, mô tả; tự gắn model, SoC, bản Android, tier, bảng năng lực, cấu hình phiên camera cuối và 200 dòng log (không ảnh, không đường dẫn, không tên file); gửi qua backend lõi ⚠ hoặc xếp hàng khi offline | — | MVP | 2 | FCM-E07-01; FLC-E05-06; FLC-E08-02 | Khi gửi báo lỗi thì bản ghi trên backend có model, tier và tính năng, không có đường dẫn file; khi offline thì báo cáo được xếp hàng và gửi khi có mạng; khi người dùng đã tắt chia sẻ chẩn đoán thì app hỏi lại trước khi gửi |
| FCM-E07-05 | `:filcam:devices` | Nhiệt và pin khi quay (F7.3, phần cơ bản đưa lên MVP): `addThermalStatusListener` + `getThermalHeadroom` (API 30+); `MODERATE` → giảm pass nhánh ghi và tần suất scopes; `SEVERE` → cảnh báo, preview 24 fps, không cho bắt đầu clip 4K mới; `CRITICAL` → dừng ghi an toàn; pin ≤ 5% không sạc → dừng ghi an toàn | — | MVP | 2 | FLC-E05-04; FCM-E02-02 | Khi giả lập `CRITICAL` (lệnh adb của thermalservice ⚠) lúc đang quay thì file được đóng và phát được; khi giả lập `SEVERE` thì cảnh báo hiện và nút 4K bị khóa; khi pin 5% không sạc thì ghi dừng và file còn nguyên |
| FCM-E07-06 | (qa) | Ma trận thiết bị FilCam (tier A/B/C, README mục 5.8) và quy trình test video mỗi bản phát hành: 1080p và 4K 10 phút, đổi look khi quay, ghi sạch, tiếng, xoay, nhiệt, kill app khi quay, lưu file; chạy thêm trên device farm ⚠ | — | MVP | 3 | FLC-E05-05; FCM-E07-02 | Khi phát hành một bản thì có bảng kết quả trên ≥ 10 máy; khi bất kỳ máy tier A hoặc B nào có lỗi "mất file quay" thì bản đó không được phát hành |
| FCM-E07-07 | `:filcam:devices` | Nhiệt và pin nâng cao (F7.3): dự báo "máy sắp nóng" từ `getThermalHeadroom(30)`; ước lượng phút quay còn lại theo pin, dung lượng và nhiệt; gợi ý hạ 1080p hoặc tắt công cụ đo; ghi thời gian tới `SEVERE` theo model vào analytics | — | V1 | 2 | FCM-E07-05; FLC-E05-07 | Khi headroom dự báo ≥ 1,0 thì app gợi ý hạ cấu hình trước khi máy vào `SEVERE`; khi quay 4K trên máy tier A thì số phút còn lại dự báo lệch thực tế ≤ 20% |
| FCM-E07-08 | (web) | Trang công khai danh sách máy hỗ trợ (F7.2): `filmode.app/filcam/devices` ⚠ sinh từ kết quả ma trận và dữ liệu năng lực ẩn danh; cột model, tier, 1080p LUT, 4K LUT, ghi sạch, FM-Log, HLG, lỗi đã biết; trạng thái "Đã kiểm", "Người dùng báo chạy", "Chưa kiểm"; cập nhật mỗi bản phát hành | — | V1 | 2 | FCM-E07-06; FCM-E07-09; FLC-E08-02 | Khi phát hành bản mới thì trang được script cập nhật trong 24 giờ, không sửa tay; khi tìm "A55" thì ra đúng dòng và trạng thái; trang đọc được trên điện thoại |
| FCM-E07-09 | `:filcam:devices` | Thu năng lực và độ ổn định ẩn danh (tắt được): gửi bảng năng lực, fps đo được, kết quả quay (thành công hay mã lỗi) theo model; bảng theo dõi crash, ANR, quay lỗi theo hãng và model để đo KPI | — | V1 | 2,5 | FCM-E07-01; FLC-E05-06; FLC-E05-07; FLC-E06-06 | Khi tắt "Chia sẻ dữ liệu sử dụng" thì không có request năng lực nào; khi mở bảng theo dõi thì thấy tỉ lệ crash và quay lỗi của 5 hãng lớn, lọc được theo model |

## FCM-E08 · Kiếm tiền

Mục tiêu: giữ lời hứa hiện tại (chỉnh tay, RAW DNG, LUT film miễn phí; không quảng cáo, không watermark), thêm 1080p có LUT vào gói miễn phí và bán FilCam Pro theo giá Bảng 8.

Ánh xạ Bảng 12: F8.1 → 02 · F8.2 → 01, 03, 04. Thêm: 05 (phễu video), 06 (ưu đãi theo mùa, V1).

Billing, `Entitlements`, paywall, thử A/B giá và bảng giá vùng là của lõi (FLC-E03-*). FilCam chỉ khai SKU, quyền và chỗ gọi paywall.

Khối lượng: 6 feature · Có sẵn 0,5 ngày · MVP 5,5 ngày · V1 1 ngày · tổng **7 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FCM-E08-01 | `:app:filcam` | Gom SKU FilCam Pro đang bán (tháng, năm có dùng thử 7 ngày, trọn đời; các mục $0.99–9.99) vào bảng map không thu hồi của lõi; người đã mua giữ quyền `pro` | — | Có sẵn | 0,5 | FLC-E03-01; FLC-E03-04 | Khi test với giao dịch giả của từng SKU FilCam cũ thì quyền `pro` được cấp; khi xóa một SKU cũ khỏi bảng map thì CI fail |
| FCM-E08-02 | `:app:filcam` | Quyền và gói miễn phí của FilCam (F8.1, F8.2): `pro` mở 4K, ghi sạch + sidecar, FM-Log/HLG, chỉnh màu Log, scopes clip, xuất hàng loạt, xuất LUT, chế độ chụp chuyên sâu, gói look Pro; `free-tier.json` của FilCam theo README mục 6 | — | MVP | 1,5 | FLC-E03-03; FLC-E03-04 | Khi đọc `free-tier.json` thì có đủ các mục ở README mục 6; khi PR chuyển "1080p có LUT" hay "đổi LUT và cường độ" sang Pro thì CI fail; khi offline 30 ngày thì Pro đã mua vẫn còn |
| FCM-E08-03 | `:app:filcam` | SKU và giá mới: base plan tháng $2.99–3.99, năm $19.99–24.99 kèm offer dùng thử 7 ngày, trọn đời $39.99; VN 249.000–299.000 ₫/năm, 499.000 ₫ trọn đời; bảng giá vùng (FLC-E03-08); thử A/B hai mức giá năm (FLC-E03-07) | — | MVP | 1,5 | FLC-E03-02; FLC-E03-07; FLC-E03-08 | Khi chạy script giá thì Play Console có đúng giá VND cho ba gói; khi remote config gán nhóm B thì paywall hiện base plan $24.99 và mọi sự kiện paywall mang `variant=B`; người đang thuê bao giữ giá cũ ⚠ |
| FCM-E08-04 | `:app:filcam` | Paywall FilCam (cấu hình FLC-E03-06): đạt checklist 4.3 của lõi; nêu Pro mở gì và những gì vẫn miễn phí; chỗ gọi: chọn 4K, ghi sạch, FM-Log/HLG, xuất clip > 60 giây, xuất LUT, chế độ chuyên sâu, look Pro; không chặn trước khi người dùng quay được clip đầu | — | MVP | 1,5 | FLC-E03-06; FCM-E08-02 | Khi chụp màn hình paywall ở VI và EN thì checklist 4.3 đạt 100%; khi gói năm là 249.000 ₫ thì chữ lớn nhất là "249.000 ₫/năm"; khi mở app lần đầu thì quay được clip 1080p có LUT mà không gặp paywall |
| FCM-E08-05 | `:app:filcam` | Sự kiện phễu cho video: `record_start`, `record_stop` (thời lượng, độ phân giải, chế độ ghi, kết quả), `grade_export`, `lut_export`, `pro_gate` (tên tính năng); dùng facade lõi; không gửi tên file hay tên look người dùng đặt | — | MVP | 1 | FLC-E05-07 | Khi đi hết luồng quay → xuất → paywall → mua bằng license tester thì các sự kiện hiện đúng thứ tự trong DebugView; khi kiểm payload thì không có tên file hay tên look tự đặt |
| FCM-E08-06 | `:app:filcam` | Ưu đãi theo mùa và giữ chân: offer cho người hủy dùng thử hoặc hết hạn (offer của Play ⚠), khuyến mãi mùa qua remote config; không hiện cho người đang có Pro | — | V1 | 1 | FCM-E08-03; FLC-E03-05 | Khi remote config bật khuyến mãi mùa thì paywall hiện offer có ngày kết thúc cụ thể; khi người dùng có Pro trọn đời thì không thấy offer nào |

## FCM-E09 · Hướng dẫn

Mục tiêu: người mới quay được clip có LUT trong vài chạm; người học chỉnh màu có bài tiếng Việt "quay Log và dùng lut màu trên Android" ngay trong app và trên web.

Ánh xạ Bảng 12: F9.1 → 02–05. Thêm: 01 (onboarding, `MVP`).

Khối lượng: 5 feature · MVP 2,5 ngày · V1 5,5 ngày · tổng **8 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FCM-E09-01 | `:filcam:learn` | Onboarding 3 bước: chọn mục đích (quay video có LUT, chụp RAW, chỉnh clip), gợi ý thiết lập theo tier máy, xin quyền đúng lúc; mẹo lần đầu (coach mark) cho đổi LUT, zebra, ghi sạch; bỏ qua được | Free | MVP | 2,5 | FLC-E06-05; FCM-E07-02 | Khi mở app lần đầu và chọn "Quay video" thì màn quay mở với 1080p30 và look mặc định trong ≤ 3 lần chạm; khi đã bỏ qua onboarding thì không hiện lại; khi bật TalkBack thì đọc được mọi bước |
| FCM-E09-02 | `:filcam:learn` | Khung bài học offline song ngữ VI/EN (F9.1): bài Markdown + ảnh và clip ngắn đóng gói hoặc tải theo bài ⚠ dung lượng; mục lục, đánh dấu đã đọc; nút "Thử ngay" mở thẳng màn hình với thiết lập mẫu | Free | V1 | 2 | FLC-E04-01; FLC-E07-06 | Khi bật chế độ máy bay thì bài đã đóng gói vẫn đọc được; khi bấm "Thử ngay" trong bài thì màn quay mở với thiết lập của bài |
| FCM-E09-03 | `:filcam:learn` | Bài "Quay Log và dùng LUT màu trên Android" (F9.1): FM-Log, 25 fps, 180°, zebra 0,90, thẻ xám; nút "Thử ngay" đặt sẵn cấu hình | Free | V1 | 1 | FCM-E09-02; FCM-E03-05 | Khi bấm "Thử ngay" thì camera ở FM-Log, 25 fps, 180°, zebra 0,90; khi máy không có FM-Log thì bài nói rõ và dùng Rec.709 |
| FCM-E09-04 | `:filcam:learn` | Bài thực hành chỉnh màu: clip FM-Log mẫu đóng gói (≤ 15 MB ⚠) mở trong trình chỉnh màu, làm theo 5 bước (Nguồn, phơi sáng, WB, đường cong, look); clip mẫu mở được Nguồn FM-Log cho cả người dùng miễn phí | Free | V1 | 1 | FCM-E09-02; FCM-E05-11 | Khi mở bài thì clip mẫu mở trong trình chỉnh màu với bước 1 được đánh dấu; khi làm xong 5 bước thì bài ghi "Đã xong"; người dùng miễn phí làm hết bài mà không gặp paywall |
| FCM-E09-05 | (web) | Trang hướng dẫn web song ngữ (SEO "lut màu", "quay log android", "chỉnh màu video trên điện thoại") dùng lại nội dung bài; cho tải LUT kỹ thuật FM-Log | Free | V1 | 1,5 | FCM-E09-02; FCM-E03-02 | Khi mở trang trên điện thoại thì đọc được và có link Google Play; khi tải LUT FM-Log từ trang thì file trùng checksum với file trong app |

## FCM-E10 · FilCam iOS (V2)

Epic mới (lý do ở [Tổng quan epic](#tổng-quan-epic)). Chỉ bắt đầu khi FilCam Android đạt tiêu chí "đẩy mạnh" ([README mục 10](README.md#10-kpi-và-tiêu-chí-dừng-hoặc-đẩy-mạnh)). Báo cáo nhận xét iOS đã có Blackmagic miễn phí, Apple Log gốc và nhiều app LUT, nên khoảng trống hẹp hơn; lý do để làm là Leica LUX cho thấy "camera pro kèm look" thu được khoảng $300k/tháng trên iOS.

Phụ thuộc lõi iOS (`FilmodeCoreKit`, V1 của lõi): FLC-E01-26 (renderer Metal và chuỗi LUT), FLC-E02-10 (thư viện), FLC-E03-09 (StoreKit 2), FLC-E06-07 (media), FLC-E05-08 (telemetry).

Khối lượng: 13 feature · V2 37 ngày · tổng **37 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FCM-E10-01 | `FilCamiOS/Record` | 🧪 Spike 2 ngày: `AVCaptureSession` + `AVCaptureVideoDataOutput` → renderer Metal của lõi → `AVAssetWriter`; đo 4K30 có look trên iPhone 12 và iPhone 15 Pro; thử Apple Log + preview look song song ghi sạch | — | V2 | 2 | FLC-E01-26; FLC-E07-05 | Khi xong spike thì có bảng fps, nhiệt, khung rơi trên 2 máy và quyết định kiến trúc ghi (`AVAssetWriter` hay `AVCaptureMovieFileOutput` + preview riêng) |
| FCM-E10-02 | `FilCamiOS/App` | App shell SwiftUI trên `FilmodeCoreKit` (LookLibrary, StoreCore, MediaKit, Telemetry): điều hướng Ảnh, Video, Chỉnh màu, Thư viện; quyền camera và micro; cài đặt | — | V2 | 2,5 | FLC-E02-10; FLC-E03-09; FLC-E06-07; FLC-E05-08 | Khi từ chối quyền camera thì app hiện hướng dẫn mở Cài đặt và không crash; khi bật chế độ máy bay thì thư viện look vẫn dùng đủ |
| FCM-E10-03 | `FilCamiOS/Capture` | Kính ngắm có look (Metal), đổi look + cường độ + A/B, chọn ống kính | Free | V2 | 3 | FCM-E10-01; FCM-E10-02 | Khi preview 1080p có look trên iPhone 12 thì ≥ 30 fps; khi so ảnh chụp trên iPhone và Android cùng look cùng cảnh thì ΔE trung bình < 2 |
| FCM-E10-04 | `FilCamiOS/Capture` | Điều khiển tay: ISO, tốc độ và góc màn trập, WB Kelvin + tint, lấy nét tay, khóa AE/AF/AWB (custom exposure của `AVCaptureDevice`) | Free | V2 | 3 | FCM-E10-03 | Khi đặt ISO 400 và 1/50 s thì metadata khung đúng hai giá trị; khi khóa AE rồi lia sang cảnh sáng thì độ sáng không đổi |
| FCM-E10-05 | `FilCamiOS/Record` | Quay 1080p 24/25/30/60 in look: `AVAssetWriter` H.264/HEVC, tiếng AAC, lưu add-only vào album FilCam; dừng ghi an toàn theo `thermalState` và pin | Free | V2 | 4,5 | FCM-E10-03 | Khi quay 1080p 24 fps 60 giây thì file đúng 24 fps và lệch tiếng ≤ 1 khung; khi `thermalState` là `.critical` thì file được đóng và phát được |
| FCM-E10-06 | `FilCamiOS/Record` | 4K, ghi sạch + look chỉ để xem, sidecar (.cube, .flook, .fcm.json) giống Android | Pro | V2 | 2,5 | FCM-E10-05; FCM-E02-11 | Khi quay ghi sạch thì file không có look còn preview có look; khi mở clip và sidecar trong FilCam Android thì cho cùng màu (ΔE < 2) |
| FCM-E10-07 | `FilCamiOS/Log` | Apple Log (F3.3): `AVCaptureColorSpace.appleLog` trên máy hỗ trợ (iPhone 15 Pro trở lên), định dạng và codec cho phép ⚠; preview = Apple Log → 709 + look (chuỗi LUT của lõi); false color và zebra theo bảng Apple Log; LUT kỹ thuật dùng chung FCM-E05-10 | Pro | V2 | 4 | FCM-E10-06; FCM-E05-10 | Khi quay Apple Log trên iPhone 15 Pro thì file có color space Apple Log và preview trông như Rec.709 có look; khi máy không hỗ trợ thì lựa chọn bị ẩn |
| FCM-E10-08 | `FilCamiOS/Capture` | Công cụ đo trên Metal, chỉ ở preview: histogram, waveform, zebra, peaking, false color | Free | V2 | 3 | FCM-E10-03 | Khi quay với công cụ đo bật thì file không có lớp đo; khi bật cả ba công cụ trên iPhone 12 thì preview ≥ 30 fps |
| FCM-E10-09 | `FilCamiOS/Capture` | Ảnh RAW (Bayer DNG, ProRAW khi có) kèm HEIF/JPEG có look | Free | V2 | 2,5 | FCM-E10-04 | Khi chụp RAW + JPEG thì có hai file trong album FilCam và DNG không có look |
| FCM-E10-10 | `FilCamiOS/Grade` | Chỉnh màu clip (phần miễn phí): PhotosPicker video, `AVVideoComposition` + renderer của lõi, chỉnh cơ bản + đường cong, cắt, xuất clip ≤ 60 giây và ≤ 1080p | Free | V2 | 4 | FCM-E10-02 | Khi xuất clip 30 giây có look thì khung giữa khớp preview (ΔE < 2) và tiếng giữ nguyên |
| FCM-E10-11 | `FilCamiOS/Grade` | Chỉnh màu clip (Pro): chuyển Log → 709 (Apple Log, FM-Log, HLG), không giới hạn thời lượng, 4K, xuất hàng loạt (`BGProcessingTask` ⚠) | Pro | V2 | 3 | FCM-E10-10; FCM-E05-10 | Khi chọn Apple Log cho clip mẫu thì preview khớp bản Android cùng clip (ΔE < 2); khi xếp 10 clip thì cả 10 xuất xong khi app ở tiền cảnh |
| FCM-E10-12 | `FilCamiOS/Store` | Paywall và SKU iOS qua StoreKit 2 của lõi; cùng quyền `pro`; giá US/VN như Android | — | V2 | 1 | FLC-E03-09; FCM-E08-02 | Khi chụp paywall trên iPhone SE và Pro Max ở VI, EN thì checklist 4.3 đạt 100%; khi khôi phục mua thì Pro hiện lại mà không cần đăng nhập |
| FCM-E10-13 | (qa) | Ma trận iPhone (12, 13, 15 Pro, 16, 17 Pro), TestFlight, ghi chú App Review nêu khác biệt với Filmode iOS (Guideline 4.3) | — | V2 | 2 | FCM-E10-05 | Khi phát hành TestFlight thì có bảng kết quả 5 máy; khi nộp review thì Review Notes có mô tả khác biệt và video demo |

## FCM-E11 · Chất lượng và phát hành

Epic mới (lý do ở [Tổng quan epic](#tổng-quan-epic)).

Khối lượng: 7 feature · Có sẵn 1,5 ngày · MVP 11 ngày · V1 1,5 ngày · tổng **14 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FCM-E11-01 | `:app:filcam` | Đưa FilCam 1.0.21 vào monorepo: `:app:filcam` trên `build-logic`, giữ package `app.filmode.filcam`, khóa ký và dãy `versionCode` | — | Có sẵn | 1,5 | FLC-E07-01 | Khi build `:app:filcam:bundleRelease` thì AAB cài đè được lên bản 1.0.21 trên máy thật mà không mất dữ liệu |
| FCM-E11-02 | `:app:filcam` | Điều hướng chính (Ảnh, Video, Chỉnh màu, Thư viện) và cài đặt (định dạng, thư mục, bitrate và âm thanh mặc định, quyền riêng tư); màn quay dùng được với TalkBack và cỡ chữ lớn, nút ≥ 48 dp, false color và zebra có chú giải chữ | — | MVP | 3 | FCM-E11-01; FLC-E07-06 | Khi xoay máy và đổi tab thì camera không mở lại quá 1 lần; khi bật TalkBack thì nghe được trạng thái ghi, thời lượng và tên look; khi cỡ chữ 200% thì màn cài đặt không bị cắt chữ |
| FCM-E11-03 | `:app:filcam` | Test tự động đường quay: instrumented test ghi 10 giây mỗi chế độ (in LUT, ghi sạch, 1080p, 4K khi có) trên máy thật hoặc device farm ⚠; trích khung bằng `MediaMetadataRetriever` và so ΔE với golden; kiểm fps, thời lượng, tiếng | — | MVP | 2,5 | FLC-E07-03; FCM-E02-09; FCM-E02-10 | Khi một PR làm khung quay in LUT lệch golden ΔE trung bình > 2 thì job fail và đính kèm khung diff; khi file quay thiếu tiếng thì test fail |
| FCM-E11-04 | `:app:filcam` | Baseline Profile + Macrobenchmark: mở app lạnh tới preview video ≤ 1,5 giây ⚠; từ lúc bấm ghi tới khung đầu trong file ≤ 500 ms ⚠ | — | MVP | 1,5 | FLC-E05-06; FCM-E02-04 | Khi chạy Macrobenchmark trên máy tầm trung chuẩn thì hai chỉ số đạt ngưỡng; khi vượt ngưỡng thì CI cảnh báo |
| FCM-E11-05 | (qa) | Chạy thử 2 tuần trên ma trận trước khi cam kết (Bảng 13): closed testing 30–50 người dùng VN; test cập nhật từ 1.0.21 (LUT, công thức, cài đặt, quyền Pro) trên 4 máy; go/no-go; staged rollout 5% → 20% → 100% với ngưỡng crash theo hãng | — | MVP | 3 | FCM-E07-06; FCM-E08-01; FLC-E02-03 | Khi hết 2 tuần thì có báo cáo lỗi theo máy và quyết định go/no-go; khi bản 5% có crash của một hãng vượt ngưỡng KPI thì rollout dừng |
| FCM-E11-06 | (ci) | Listing FilCam mới qua fastlane của lõi: tiêu đề và mô tả EN/VN (README mục 9), 7 ngôn ngữ, ảnh chụp màn hình theo locale, video giới thiệu; cập nhật Data safety (micro chỉ dùng trên máy, không thu) | — | MVP | 1 | FLC-E04-04; FLC-E06-06 | Khi chạy lane `metadata` thì listing 7 locale được đẩy lên và lint tên không báo lỗi; khi so Data safety với manifest và SDK thì khớp 100% |
| FCM-E11-07 | (qa) | Test dài: quay 30 phút 1080p, 10 phút 4K, xuất hàng loạt 20 clip trên máy tier A và B; theo dõi nhiệt, rò bộ nhớ, khung rơi | — | V1 | 1,5 | FCM-E07-05; FCM-E05-14 | Khi quay 30 phút 1080p trên máy tầm trung chuẩn thì không crash, khung rơi < 1% và bộ nhớ không tăng quá 10% sau phút thứ 5 |

## Tổng theo ưu tiên

| Epic | Có sẵn | MVP | V1 | V2 | Tổng | Số feature |
|---|---|---|---|---|---|---|
| FCM-E01 Máy ảnh thủ công và RAW | 7 | 12 | 1,5 | 0 | 20,5 | 11 |
| FCM-E02 Quay video có LUT | 0 | 32 | 14 | 0 | 46 | 20 |
| FCM-E03 Log và HDR | 0 | 0 | 15,5 | 3 | 18,5 | 8 |
| FCM-E04 Quản lý LUT | 1 | 5,5 | 4,5 | 0 | 11 | 8 |
| FCM-E05 Chỉnh màu clip có sẵn | 0 | 12,5 | 17,5 | 0 | 30 | 14 |
| FCM-E06 Tạo và xuất LUT | 0 | 0 | 7,5 | 3 | 10,5 | 6 |
| FCM-E07 Tương thích thiết bị | 0 | 12 | 6,5 | 0 | 18,5 | 9 |
| FCM-E08 Kiếm tiền | 0,5 | 5,5 | 1 | 0 | 7 | 6 |
| FCM-E09 Hướng dẫn | 0 | 2,5 | 5,5 | 0 | 8 | 5 |
| FCM-E10 FilCam iOS | 0 | 0 | 0 | 37 | 37 | 13 |
| FCM-E11 Chất lượng và phát hành | 1,5 | 11 | 1,5 | 0 | 14 | 7 |
| **Tổng** | **10** | **93** | **75** | **43** | **221** | **107** |

Số feature theo ưu tiên: Có sẵn 8, MVP 46, V1 38, V2 15. Trong đó có 7 spike 🧪 (FCM-E01-01, FCM-E02-01, FCM-E02-03, FCM-E03-01, FCM-E03-06, FCM-E05-09, FCM-E10-01), tổng 15 ngày.

**Chia theo nền tảng** (Android là module `:app:filcam`, `:filcam:*`; iOS là `FilCamiOS/*`; nhóm còn lại là `(qa)`, `(ci)`, `(web)`; FCM-E10-13 là QA iOS nên nằm ở nhóm thứ ba):

| Nền tảng | Feature | Có sẵn | MVP | V1 | V2 | Tổng (ngày) |
|---|---|---|---|---|---|---|
| Android | 83 | 10 | 81 | 63 | 6 | 160 |
| iOS | 12 | 0 | 0 | 0 | 35 | 35 |
| Web, CI, QA | 12 | 0 | 12 | 12 | 2 | 26 |

**Chia theo gói:**

| Gói | Feature | Ngày |
|---|---|---|
| Free | 42 | 85 |
| Pro | 30 | 64 |
| — | 35 | 72 |

**So với Bảng 13.** Báo cáo ước FilCam Android "camera video 8–12, chỉnh màu 6–10 tuần-người". Phần tương ứng ở đây: camera video là FCM-E02 cộng FCM-E03 (bỏ dòng V2) = 61,5 ngày, khoảng 12 tuần-người, ở mức trên của khoảng báo cáo vì có thêm recorder dự phòng (5 ngày) và 5 spike; chỉnh màu là FCM-E05 cộng FCM-E06 (bỏ dòng V2) = 37,5 ngày, khoảng 7,5 tuần-người, nằm trong khoảng. Phần còn lại (chuyển app ảnh lên lõi, công cụ đo GPU, thiết bị, kiếm tiền, hướng dẫn, phát hành) báo cáo không tính riêng. iOS 37 ngày thấp hơn "6–8 và 5–8 tuần-người" vì dùng lại `FilmodeCoreKit`.

## Chỗ lệch so với Bảng 12

| Mục trong Bảng 12 | Báo cáo | Backlog FilCam | Lý do |
|---|---|---|---|
| F1.3 Công cụ đo | Free, MVP | Histogram, lưới, thước cân bằng là `Có sẵn` (mô tả Play); peaking, zebra, false color, waveform cũng `Có sẵn` theo trang web ⚠ (FCM-E01-05). Phần `MVP` là viết lại thành pass GPU chỉ ở nhánh preview (FCM-E01-06, FCM-E01-07) | Ghi đúng thứ đã phát hành; công cụ đo không được lọt vào file quay |
| F1.4 Chế độ chuyên sâu | Pro, "Đã có" | `Có sẵn` (FCM-E01-08, FCM-E01-09) | Đã có trong 1.0.21 |
| F2.4 Khóa phơi sáng | Pro, V1 | Khóa AE/AF/AWB khi quay là `Free`, `MVP` (FCM-E01-10) | F1.1 đã cho khóa miễn phí; không thu hồi (FLC-E03-04) |
| F2.4 Shutter angle | Pro, V1 | Góc màn trập và trợ lý chống nhấp nháy là `Pro` (FCM-E02-15); tốc độ nhập tay khi quay vẫn `Free` | Như trên |
| F3.3 Apple Log | Pro, V2, trong F3 | FCM-E10-07, trong epic iOS | Gom mọi việc iOS vào một epic |
| F4.2 Bộ LUT khởi đầu | Free một phần/Pro, MVP | 12 look điện ảnh + 43 look ảnh `Free`, 24 look `Pro` ở `MVP`; bộ LUT kỹ thuật Log → 709 `Free`, `V1` (FCM-E04-06) | LUT kỹ thuật chỉ có nghĩa khi có FM-Log, HLG (V1) |
| F5.1 Chỉnh cơ bản | Free (giới hạn thời lượng)/Pro | Free: xuất ≤ 60 giây, ≤ 1080p (FCM-E05-06); Pro: không giới hạn, 4K (FCM-E05-07) | Chốt con số để ghi `free-tier.json` |
| F5.1 (không có) | — | Bánh xe màu lift/gamma/gain, CDL: `Pro`, `V1` (FCM-E05-08) | Công cụ chỉnh màu Log cần bánh xe; đường cong đã có ở `MVP` |
| F6.2 LUT từ ảnh mẫu | "Dùng chung module B4 của Studio" | Dùng Match v1 của lõi (FLC-E01-18) | Lõi đã chuyển Match v1 vào `:core:lut-io` |
| F6.3 Chia sẻ qua mã QR | Pro | `Free` (FCM-E06-04); xuất .cube vẫn `Pro` | Codec QR và link look của lõi miễn phí ở cả ba app |
| F7.2 Báo lỗi theo máy | V1 | `MVP` (FCM-E07-04); trang danh sách máy công khai giữ `V1` (FCM-E07-08) | Lỗi theo máy đến ngay tuần đầu; mốc đo của Bảng 13 là crash theo hãng |
| F7.3 Nhiệt độ và pin | V1 | Dừng ghi an toàn `MVP` (FCM-E07-05); dự báo và ước lượng `V1` (FCM-E07-07) | Quay 4K có LUT mà không dừng an toàn khi quá nóng thì có thể mất file |
| F9.1 Hướng dẫn | V1 | Bài học `V1`; onboarding `MVP` (FCM-E09-01) | Người mới cần vào được màn quay nhanh |
| — | — | Epic mới FCM-E10, FCM-E11 | Xem [Tổng quan epic](#tổng-quan-epic) |

## Điều chỉnh lõi

FilCam cần lõi đổi những điểm sau. Người điều phối đưa vào `filmode-core.md` và backlog lõi; FilCam không tự sửa module `:core:*`.

| # | Mục lõi | Cần đổi | FilCam dùng ở | Mức cần |
|---|---|---|---|---|
| 1 | FLC-E01-16 (wrapper CameraX) | Cho gắn hai `CameraEffect` với target riêng (PREVIEW, VIDEO_CAPTURE), mỗi nhánh một graph; báo khi CameraX ép stream sharing; mở `Camera2CameraControl` cho `TONEMAP_*`, `CONTROL_AE_TARGET_FPS_RANGE`, `SENSOR_*`; nhận luồng `DynamicRange.HLG_10_BIT` trong `SurfaceProcessor` ⚠ | FCM-E02-02, FCM-E03-03, FCM-E03-07 | Trước MVP FilCam (phần HLG trước V1) |
| 2 | FLC-E01-11 (đồ thị pass) | Cờ `previewOnly` cho `EffectPass` (công cụ đo không bao giờ vào file); vị trí cắm sau `inputTransform`, trước LUT sáng tạo (đường cong, bánh xe) | FCM-E01-06, FCM-E05-04, FCM-E05-08 | Trước MVP FilCam |
| 3 | Định dạng look (mục 5.2) | Thêm `hlg` vào `inputTransform.from`; `fm-log` trỏ tới đặc tả FM-Log v1 (FCM-E03-02) và fixture trong `spec/look/`; V2 cần thêm tên nguồn cho FM-Log 10-bit. Chỉ thêm giá trị, `formatVersion` giữ 1; app cũ gặp giá trị lạ thì báo "App này chưa hỗ trợ" | FCM-E02-08, FCM-E03-02, FCM-E03-07, FCM-E03-08 | Trước V1 FilCam |
| 4 | FLC-E01-19 (xuất .cube) | Đang ghi `V1` "cần cho FMS B7.2, FCM F6.1"; FilCam cần sớm hơn cho sidecar của ghi sạch | FCM-E02-11 | Trước MVP FilCam |
| 5 | FLC-E01-21 (`LookGlEffect`) | Nhận đầu vào 10-bit gắn nhãn SDR (clip Log) mà không mất độ chính xác ⚠; chạy sau tone map HDR → SDR của Transformer; seed grain theo khung | FCM-E05-02, FCM-E05-11, FCM-E05-13 | Trước MVP FilCam (phần 10-bit trước V1) |
| 6 | FLC-E06-02 (lưu media) | API lưu file không phải media (`.cube`, `.flook`, `.json`) cạnh video, qua `MediaStore.Files` hoặc thư mục `Documents/FilCam` ⚠ | FCM-E02-11, FCM-E04-06 | Trước MVP FilCam |
| 7 | FLC-E05-02 (dò khả năng) | Dò thêm `TONEMAP_AVAILABLE_TONE_MAP_MODES`, `TONEMAP_MAX_CURVE_POINTS`, dải AE fps theo kích thước, encoder HEVC/Main10 và bitrate tối đa, kết quả `isSessionConfigSupported` của cấu hình hai nhánh. FCM-E07-01 làm tạm ở app nếu lõi chưa kịp, rồi chuyển vào lõi khi FMD cần quay video dài | FCM-E07-01 | Nên có |
| 8 | FLC-E05-04 (nhiệt) | Callback riêng cho `CRITICAL`/`EMERGENCY` để dừng ghi trước khi hệ thống cắt; dự báo headroom | FCM-E07-05, FCM-E07-07 | Trước MVP FilCam |
| 9 | FLC-E03-04 (`free-tier.json`) | Thêm mục FilCam theo [README mục 6](README.md#6-gói-miễn-phí-và-pro) | FCM-E08-02 | Trước MVP FilCam |
| 10 | FLC-E08-02 (backend) | Endpoint nhận báo lỗi theo máy có giới hạn tần suất; hosting trang `filmode.app/filcam/devices` ⚠ | FCM-E07-04, FCM-E07-08 | Trước MVP FilCam (endpoint) |
| 11 | FLC-E05-05, mục 4.4 (ma trận máy) | Ma trận 8 máy của lõi thiếu máy tier A/B cho quay 4K và HLG; FilCam dùng 10–13 máy ([README mục 5.8](README.md#58-tương-thích-thiết-bị-fcm-e07)) | FCM-E07-06 | Trước MVP FilCam |
| 12 | FLC-E04-01 (ngôn ngữ) | Thị trường đợt 2 của FilCam có Đức; `de` chưa nằm trong 7 ngôn ngữ của lõi | FCM-E11-06 | Khi mở thị trường DE |

## Nội dung (không tính vào ngày công dev)

Ước theo ngày công của một người làm màu và nội dung (không phải dev). Mọi look và LUT đóng gói phải có manifest nguồn gốc `owned`, tên tự đặt qua `NameGuard` (FLC-E04-02, FLC-E04-03).

| Nội dung | Số lượng | Ngày | Cần cho | Ghi chú |
|---|---|---|---|---|
| Look điện ảnh miễn phí | 12 | 6 | FCM-E04-04 (MVP) | Thử trên Rec.709 và FM-Log; khoảng 0,5 ngày mỗi look |
| Look điện ảnh Pro | 24 | 12 | FCM-E04-05 (MVP) | Như trên |
| Kiểm 43 look ảnh hiện có trên video | 43 | 2 | FCM-E04-04 (MVP) | Look nào vỡ trên da hay trời khi quay thì sửa hoặc đánh dấu "chỉ ảnh" |
| LUT kỹ thuật FM-Log → Rec.709 (trung tính, tương phản) | 2 × (33³, 65³) | 0,5 | FCM-E03-02 (V1) | Sinh bằng code; chỉ kiểm mắt |
| LUT kỹ thuật HLG → Rec.709 | 1 | 1 | FCM-E03-07 (V1) | Theo BT.2408 ⚠ |
| LUT kỹ thuật Apple Log → Rec.709 | 1 | 1,5 | FCM-E05-10 (V1) | Theo đặc tả công khai của Apple ⚠ giấy phép |
| LUT kỹ thuật Samsung Log → Rec.709 | 1 | 2 | FCM-E05-10 (V1) | Chỉ khi spike FCM-E05-09 đạt ⚠ |
| Clip mẫu (FM-Log, HLG, Apple Log, Samsung Log, thanh màu, thẻ xám) | khoảng 20 clip | 2 | Test, FCM-E09-04 | Quay trên ma trận máy; clip bài học ≤ 15 MB |
| Bài hướng dẫn VI và EN | 5 bài | 7,5 | FCM-E09-02 đến FCM-E09-05 (V1) | "Quay Log và dùng lut màu trên Android"; "Phơi sáng với zebra và false color"; "Góc màn trập và chống nhấp nháy đèn 50 Hz"; "Chỉnh màu clip Log trên điện thoại"; "Xuất LUT sang app dựng phim"; 1 ngày bản VI + 0,5 ngày bản EN |
| Video ngắn cho TikTok và Reels | 3 | 3 | Ra mắt, ASO | Dùng lại clip mẫu |
| **Tổng** | | **37,5** | | Khoảng 7,5 tuần-người; 25 ngày cần xong trước MVP (look, kiểm look, clip mẫu, video ngắn), 12,5 ngày cho V1 |

## Lộ trình sprint

Bảng 13 đặt FilCam Android ở Q2–Q3/2027, sau Studio Android (Q1/2027). Lịch dưới giả định **2 dev Android** làm FilCam từ thứ Hai 5/4/2027, sprint 2 tuần. Mỗi sprint lên kế hoạch khoảng 13–16 ngày feature trên 20 ngày danh nghĩa; phần còn lại (20–25%, như Bảng 13 khuyên) dành cho chạy máy thật, sửa lỗi và review. Các mục lõi FilCam cần (FLC-E01-19, FLC-E01-20, FLC-E01-21, FLC-E02-09 và các điểm ở [Điều chỉnh lõi](#điều-chỉnh-lõi)) phải xong trước S2.

| Sprint | Ngày | Mục tiêu | Feature | Ngày công |
|---|---|---|---|---|
| S1 | 5/4 – 16/4/2027 | Nền: monorepo, đọc code cũ, chuyển app ảnh lên wrapper lõi, năng lực máy, spike ghi sạch | FCM-E11-01; FCM-E01-01 🧪, -02, -05; FCM-E04-01; FCM-E08-01; FCM-E07-01; FCM-E02-01 🧪 | 13 |
| S2 | 19/4 – 30/4/2027 | Kiểm lại tính năng ảnh trên lõi; pipeline video hai nhánh; chính sách tier; quyền và gói | FCM-E01-03, -04, -08, -10; FCM-E02-02; FCM-E07-02; FCM-E08-02 | 14 |
| S3 | 3/5 – 14/5/2027 | Quay 1080p có LUT, đổi LUT trên màn quay, zebra/peaking/false color, thư viện LUT; spike 4K tier B | FCM-E02-03 🧪, -04, -07, -09; FCM-E01-06; FCM-E04-02 | 15 |
| S4 | 17/5 – 28/5/2027 | Codec và bitrate, màn quay, ống kính, scopes kính ngắm, bộ look miễn phí, điều hướng | FCM-E02-06, -12, -13; FCM-E01-07; FCM-E04-03, -04; FCM-E11-02 | 14,5 |
| S5 | 31/5 – 11/6/2027 | Pro video: 4K, ghi sạch + sidecar, LUT kỹ thuật, khung tỉ lệ; dừng ghi an toàn; mở và xem clip | FCM-E02-05, -10, -11, -08, -14; FCM-E07-05; FCM-E05-01, -02 | 15 |
| S6 | 14/6 – 25/6/2027 | Trình chỉnh màu (cơ bản, đường cong, cắt, xuất); màn Máy của bạn, báo lỗi theo máy; giá và paywall | FCM-E05-03, -04, -05, -06, -07; FCM-E07-03, -04; FCM-E08-03, -04 | 14,5 |
| S7 | 28/6 – 9/7/2027 | Gói look Pro, phễu, onboarding, test tự động, benchmark, listing; kiểm lại bracketing, chụp đêm, focus stacking; chạy ma trận lần đầu | FCM-E04-05; FCM-E08-05; FCM-E09-01; FCM-E11-03, -04, -06; FCM-E01-09; FCM-E07-06 | 14 |
| S8 | 12/7 – 23/7/2027 | Chạy thử 2 tuần trên ma trận, closed testing, test cập nhật từ 1.0.21, go/no-go; chỉ sửa lỗi | FCM-E11-05 | 3 |
| Ra mắt | 26/7 – 6/8/2027 | Staged rollout 5% → 20% → 100% theo ngưỡng crash từng hãng | – | – |
| **Tổng MVP + Có sẵn** | | | | **103** |
| S9 | 9/8 – 20/8/2027 | V1: FM-Log (spike banding, đặc tả, ISP, GPU, hướng dẫn phơi sáng), góc màn trập; spike Samsung Log | FCM-E03-01 🧪, -02, -03, -04, -05; FCM-E02-15; FCM-E05-09 🧪 | 15 |
| S10 | 23/8 – 3/9/2027 | V1: HLG 10-bit; chuyển Log → 709 trong chỉnh màu; LUT kỹ thuật Apple Log, Samsung Log; bánh xe màu; scopes clip | FCM-E03-06 🧪, -07; FCM-E05-10, -11, -08, -12 | 14 |
| S11 | 6/9 – 17/9/2027 | V1: tone map HDR, xuất hàng loạt, xuất LUT, LUT từ ảnh mẫu, hồ sơ xuất, chia sẻ, LUT Maker, bộ LUT kỹ thuật | FCM-E05-13, -14; FCM-E06-01, -02, -03, -04, -05; FCM-E04-06 | 14,5 |
| S12 | 20/9 – 1/10/2027 | V1: recorder dự phòng, âm thanh và micro ngoài, chống rung, grain/halation khi quay, rack focus, nhiệt nâng cao, test dài | FCM-E02-17, -18, -19, -20, -16; FCM-E07-07; FCM-E11-07 | 15,5 |
| S13 | 4/10 – 15/10/2027 | V1: trang danh sách máy, đo ổn định theo hãng, nhận look từ Filmode/Studio, quét QR, bài học, hybrid AE, ưu đãi | FCM-E07-08, -09; FCM-E04-07, -08; FCM-E09-02, -03, -04, -05; FCM-E01-11; FCM-E08-06 | 16 |
| **Tổng V1** | | | | **75** |

Ghi chú lịch:
- Các ngày nghỉ lễ (Giỗ Tổ Hùng Vương giữa tháng 4 ⚠ ngày âm lịch, 30/4–1/5, 2/9) rơi vào S1, S2, S10; các sprint này đã để trống nhiều hơn.
- Nếu spike FCM-E02-01 (S1) không đạt, FCM-E02-17 (recorder dự phòng, 5 ngày) chuyển lên S3–S4 và FCM-E04-05, FCM-E09-01 lùi sang S8; ngày ra mắt lùi khoảng 1 tuần.
- S8 là 2 tuần chạy thử trên ma trận và closed testing (Bảng 13). Không nhận tính năng mới trong S8.
- Việc không tính ngày công nhưng phải xong trước S7: 12 look miễn phí và 24 look Pro, dịch 7 ngôn ngữ, ảnh chụp màn hình và video listing, trang quyền riêng tư cập nhật, mua đủ máy ma trận ([README mục 5.8](README.md#58-tương-thích-thiết-bị-fcm-e07)).
- **V2** (FCM-E03-08, FCM-E06-06, FCM-E10) chỉ bắt đầu khi đạt tiêu chí "đẩy mạnh" ở mốc 12 tuần sau ra mắt (khoảng cuối 10/2027). iOS cần 1 dev iOS khoảng 8 tuần, dự kiến Q1/2028 ⚠.

## Nhân sự

- **MVP + Có sẵn là 103 ngày công**, khoảng 21 tuần-người. Với 2 dev Android: 7 sprint làm tính năng + 1 sprint chạy thử, ra mắt cuối 7/2027 (Q3). Gợi ý chia: dev A làm camera và video (FCM-E01-02, FCM-E02, FCM-E07); dev B làm công cụ đo, thư viện, chỉnh màu, kiếm tiền, app shell (FCM-E01-05 đến FCM-E01-07, FCM-E04, FCM-E05, FCM-E08, FCM-E09, FCM-E11).
- **V1 là 75 ngày**, 5 sprint với 2 dev (8–10/2027), song song với V1 của Filmode và Studio; nếu chỉ còn 1 dev thì V1 kéo tới hết Q4/2027.
- **1 dev Android: không vừa Q3/2027.** Một dev làm khoảng 7,5 ngày feature mỗi sprint, nên 103 ngày cần khoảng 14 sprint cộng 1 sprint chạy thử; ra mắt khoảng đầu 11/2027 (Q4). Nếu vẫn muốn ra trong Q3 thì phải có thêm dev từ S3, hoặc cắt khoảng 20 ngày sang V1: FCM-E05-01 đến FCM-E05-07 (trình chỉnh màu, 12,5 ngày; ra mắt như camera thuần), FCM-E01-07 (scopes GPU, 3; histogram cũ vẫn chạy), FCM-E02-14 (khung tỉ lệ, 1,5), FCM-E11-04 (benchmark, 1,5), FCM-E04-03 (thumbnail khung hiện tại, 1). **Không được cắt:** FCM-E02-01 (spike ghi sạch), FCM-E07-01, FCM-E07-02, FCM-E07-05, FCM-E07-06 (năng lực máy, chính sách tier, dừng ghi an toàn, ma trận), FCM-E08-02, FCM-E08-04 (không thu hồi, paywall tuân thủ), FCM-E11-05 (chạy thử 2 tuần).
- Người làm màu và nội dung: khoảng 25 ngày trước MVP, 12,5 ngày cho V1 (mục [Nội dung](#nội-dung-không-tính-vào-ngày-công-dev)).
