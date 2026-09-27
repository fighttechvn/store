# 03 · FilCam: máy quay LUT và RAW (mã `FCM`)

FilCam (`app.filmode.filcam`) hiện là "FilCam: Pro Manual RAW Camera": máy ảnh chỉnh tay, RAW DNG miễn phí, LUT film in thẳng vào JPEG. Kế hoạch này nâng FilCam thành **máy quay LUT và RAW**: quay video với LUT hiện ngay trên màn hình, đổi LUT và cường độ trong kính ngắm, in LUT vào file hoặc ghi sạch để chỉnh sau, hồ sơ Log riêng (FM-Log) và HLG 10-bit, chỉnh màu clip có sẵn và xuất LUT. Android trước; iOS sau khi bản Android đạt mốc đo.

Quy ước ID, ưu tiên, gói và ước tính theo [README chung](../README.md). Phần dùng chung lấy từ [lõi Filmode Core (`FLC`)](../filmode-core.md) và không định nghĩa lại ở đây. Nguồn: [báo cáo](../../../reports/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u.md), mục "App 3 — FilCam: máy quay LUT và RAW cho Android", Bảng 8, 12, 13; ghi chú nghiên cứu trong `research_notes/App camera film và LUT màu/`.

| File | Nội dung |
|---|---|
| [epics-features.md](epics-features.md) | 11 epic, 107 feature, ước tính, tiêu chí nghiệm thu, điều chỉnh lõi, nội dung, lộ trình sprint |
| [backlog.csv](backlog.csv) | Danh sách feature để nhập Jira, Linear hoặc GitHub Projects |

## 1. Tóm tắt

- **Vấn đề:** người quay video bằng Android tầm trung không có app nào vừa cho **đổi LUT và chỉnh cường độ ngay trên màn quay**, vừa chạy ngoài danh sách máy flagship. Blackmagic Camera miễn phí nhưng chỉ hỗ trợ một danh sách máy flagship; mcpro24fps là công cụ pro trả trước; 3DLUT mobile ngừng cập nhật từ 29/7/2024; CapCut bản điện thoại không nhập được .cube (theo hướng dẫn bên thứ ba ⚠).
- **Cơ hội:** "lut màu" tăng 4,15 lần ở Việt Nam, "cube lut" 2,04 lần và "color grading" 1,88 lần toàn cầu. Trên Play, app #1 cho từ khóa "lut" chỉ có 13.685 lượt cài. Trên iOS, app LUT nhỏ bán được $35–60/năm.
- **Lời hứa:** "Quay có LUT ngay trên màn hình. 1080p có LUT, chỉnh tay và RAW DNG miễn phí mãi. Không quảng cáo, không watermark, mua đứt được."
- **Thiết bị:** mọi tính năng video hỏi năng lực máy trước và ẩn thứ máy không làm được, như FilCam đang làm với phần ảnh. Ma trận 10–13 máy chia tier A/B/C; danh sách máy hỗ trợ được công bố (mục 5.8).
- **Lịch:** 2 dev Android làm từ 5/4/2027; ra mắt cuối 7/2027 (Q3, khớp Bảng 13); V1 trong 8–10/2027; iOS (V2) chỉ khi đạt mốc đo, dự kiến Q1/2028 ⚠.
- **Nguồn lực:** Có sẵn + MVP **103 ngày công**; V1 75 ngày; V2 43 ngày (37 ngày iOS). Tổng 221 ngày, 107 feature. Thêm khoảng 37,5 ngày nội dung (look, LUT kỹ thuật, bài học).

## 2. Hiện trạng FilCam 1.0.21

Số liệu ngày 27/9/2026, từ [Google Play – FilCam](https://play.google.com/store/apps/details?id=app.filmode.filcam&hl=en&gl=US), [trang FilCam](https://trunghieuvn.github.io/filmode-camera/) và ghi chú nghiên cứu `film_camera_apps.md`, `tech_feasibility_opportunities.md`, `keyword_search_demand.md`.

| Mục | Hiện trạng |
|---|---|
| Listing | "FilCam: Pro Manual RAW Camera", danh mục Photography, nhà phát triển Trung-Hieu Tran (FightTech) |
| Phát hành | 4/9/2026; bản 1.0.21 cập nhật 26/9/2026; Android 8.0+ (theo trang web); iOS "Coming soon" |
| Lượt cài, đánh giá | 327 lượt cài; 2 đánh giá 5★, chưa đủ để hiện điểm. Một người báo không lưu được ảnh (8/9), một người khen chỉnh tay và RAW DNG (21/9) |
| Miễn phí | Chế độ P/S/I/M; ISO, tốc độ, EV, WB theo Kelvin, lấy nét tay; khóa AE/AF/AWB; đo sáng; **RAW DNG** ghi từ hiệu chuẩn cảm biến của máy, kèm JPEG/HEIF/PNG; 43 look LUT 64³ render trên GPU và in vào JPEG; nhập .cube; trình sửa có lưu công thức; tên file và thư mục tùy chỉnh; EXIF, geotag; phím âm lượng; histogram RGB, lưới, thước cân bằng. Trang web nêu thêm focus peaking, false color, zebra, waveform ⚠ |
| Pro | Phơi sáng dài tới 30 giây; vệt sáng 15 giây–5 phút; bracketing 3/5/7; focus stacking; chụp đêm; intervalometer |
| Giá | Mục trong app $0.99–9.99 (VN 26.000–260.000 ₫); Pro theo tháng, năm (dùng thử 7 ngày) hoặc trọn đời; "No ads and no watermark, ever" |
| Data safety | Không chia sẻ; thu (tùy chọn) Device or other IDs, App interactions, Crash logs, Diagnostics; mã hóa khi truyền; xóa được |
| Thứ hạng | #1 cho "filcam"; **#24 "raw camera"** và **#29 "manual camera"** ở Mỹ; ngoài top 30 cho mọi từ khóa film và LUT |
| Chưa có | Quay video; Log/HLG; chỉnh màu clip; xuất LUT |

Kỹ thuật khó nhất đã có: LUT 64³ trên GPU, điều khiển tay qua Camera2, ghi DNG, "ẩn thứ máy không hỗ trợ". Ghi chú nghiên cứu không nói code viết bằng gì và preview dùng Camera2 hay CameraX ⚠; spike FCM-E01-01 đọc code ở tuần đầu.

## 3. Người dùng mục tiêu và job-to-be-done

| Nhóm | Tình huống | Việc cần làm ("khi … tôi muốn … để …") | Đầu ra | Trả tiền? | Bằng chứng |
|---|---|---|---|---|---|
| Người quay video bằng điện thoại (vlog, du lịch, sự kiện nhỏ, quay thuê) | Android tầm trung đến cao | Khi quay, tôi muốn thấy màu cuối ngay trên màn hình và có file sạch để chỉnh sau, để không phải mua máy quay hay iPhone Pro | Clip 1080p/4K in LUT hoặc sạch kèm `.cube` sidecar; FM-Log | Có: 4K, ghi sạch, Log | Người dùng Blackmagic xin "chọn và xem trước LUT trên màn quay" (297 lượt hữu ích) và "thanh cường độ" (105); Blackmagic chỉ chạy trên danh sách flagship |
| Creator TikTok và Reels | Clip ngắn 9:16, đăng ngay | Khi quay clip ngắn, tôi muốn áp LUT mình thích ngay lúc quay rồi đăng luôn, vì CapCut bản điện thoại không nhập được .cube ⚠ | Clip 1080p in LUT, khung 9:16 và vùng an toàn | Phần lớn dùng Free; một phần mua gói look Pro | Gợi ý YouTube "lut cube capcut"; #colorgrading 902 triệu lượt xem (ảnh chụp không ghi ngày) |
| Sinh viên học quay phim và chỉnh màu | Học color grading, ít tiền | Khi học chỉnh màu, tôi muốn thử Log → Rec.709, scopes và xuất LUT sang Resolve ngay trên điện thoại, với giá hợp túi sinh viên | Bài học tiếng Việt, clip mẫu, `.cube` | Có thể: gói năm VN 249.000 ₫ | "lut màu" 4,15× ở VN; "lut màu blackmagic camera" +1.950%; "color grading" 1,88× |
| Người chụp ảnh muốn RAW + look | Chụp phố, du lịch | Khi chụp, tôi muốn chỉnh tay, có DNG sạch và JPEG có look film cùng lúc, miễn phí | DNG + JPEG/HEIF có look | Ít; chế độ chuyên sâu là Pro | FilCam đứng #24 "raw camera", #29 "manual camera" (Mỹ); đánh giá khen chỉnh tay và DNG |
| Người có máy quay được Log (Galaxy S25, iPhone Pro) | Đã quay Log bằng camera gốc | Khi đã quay Log, tôi muốn đưa về Rec.709 và áp look ngay trên điện thoại, không cần máy tính | Clip đã chỉnh, xuất hàng loạt | Có: Log → 709, hàng loạt | Galaxy S25 có Log trong camera gốc; có chợ LUT Apple Log (Absoluts, ypresets); "apple log lut" +100% |

Ngoài ra nhóm người dùng máy ảnh film vui cũng muốn quay video với đúng filter mình thích ([Google Play – OldRoll](https://play.google.com/store/apps/details?id=com.accordion.analogcam)); nhóm này dùng look ảnh sẵn có của FilCam cho video.

## 4. Định vị và đối thủ

**Câu định vị:** máy quay LUT cho **Android tầm trung**: đổi LUT và cường độ ngay trên màn quay, 1080p có LUT miễn phí, Log riêng không cần hãng máy mở, chỉnh màu clip và xuất LUT ngay trên điện thoại. Có tiếng Việt, giá theo vùng, mua đứt được.

| App | Loại và giá | Lượt cài, đánh giá | Điểm yếu mình khai thác | FilCam khác ở đâu |
|---|---|---|---|---|
| [Blackmagic Camera](https://play.google.com/store/apps/details?id=com.blackmagicdesign.android.blackmagiccam&hl=en&gl=US) | Quay chuyên nghiệp, **miễn phí**, không IAP; từ bản 3.1 nhập .cube để xem hoặc in vào clip, có LUT Samsung Log | 3,92 triệu lượt cài; 4,59★ (14,6K); iOS 23.056 đánh giá ở Mỹ | [Chỉ hỗ trợ một danh sách flagship](https://www.blackmagicdesign.com/products/blackmagiccamera/techspecs/W-APP-02) (Samsung S21–S25, Z Fold; Pixel 6–9; OnePlus 11/12; Xiaomi 13/14; Sony Xperia); người dùng xin chọn LUT trên màn quay và thanh cường độ; 28% đánh giá là 1–2★ và 40% trong số đó nhắc tên hãng máy | Chạy trên máy tầm trung theo năng lực thật; đổi LUT + cường độ trên màn quay; chỉnh clip và xuất LUT; tiếng Việt |
| [mcpro24fps](https://play.google.com/store/apps/details?id=lv.mcprotector.mcpro24fps&hl=en&gl=US) | Quay chuyên nghiệp, **$19.99 trả trước** (có app demo); Log bằng đường cong GPU, LUT xem trên màn, LUT kỹ thuật | 16.241 lượt cài; 4,57★ (4.013) | Công cụ khó cho người mới; [cần Camera2 LIMITED trở lên, một số tính năng cần hãng cho phép](https://www.mcpro24fps.com/full-specification/); demo "không quay được" bị chê | Freemium, 1080p có LUT miễn phí; FM-Log cùng ý tưởng nhưng kèm false color, zebra và bài học tiếng Việt |
| [3DLUT mobile](https://play.google.com/store/apps/details?id=com.lutmobile.lut&hl=en&gl=US) | Áp LUT cho ảnh/video; IAP $0.99–20.99 | 17,4 triệu lượt cài; 3,88★ (29,6K) | **Cập nhật cuối 29/7/2024**; phụ thuộc phần mềm máy tính 3D LUT Creator | App LUT Android được cập nhật; quay, chỉnh và xuất LUT trong một app |
| [PeekLut](https://apps.apple.com/us/app/id6473661560) (iOS) | Áp LUT, xuất bản chỉnh thành LUT; $2.99/tuần, $4.99/tháng, **$34.99/năm** | 654 đánh giá ở Mỹ, 4,69★ | Chỉ có iOS | Android trước; giá năm thấp hơn |
| [LUT Studio](https://apps.apple.com/us/app/id6479377583) (iOS) | Xem LUT thời gian thực; $9.99/tháng, **$29.99–49.99/năm** | 725 đánh giá, 4,71★ | Chỉ có iOS | Như trên |
| [Filmic Pro](https://play.google.com/store/apps/details?id=com.filmic.filmicpro&hl=en&gl=US) | Quay chuyên nghiệp, thuê bao (iOS $39.99/năm) | 3,46 triệu lượt cài; **2,34★** trên Play (17,8K); bản Android cập nhật cuối 4/11/2025 | [Đội phát triển bị cho nghỉ 11/2023](https://www.videomaker.com/news/uncertain-future-for-filmic-pro-as-entire-team-has-been-laid-off/), chuyển sang thuê bao, mất lòng tin | Cập nhật đều; có gói trọn đời; không thu hồi thứ đã miễn phí |
| Tham khảo: [VN](https://play.google.com/store/apps/details?id=com.frontrow.vlog&hl=en&gl=US), [CapCut](https://play.google.com/store/apps/details?id=com.lemon.lvoverseas&hl=en&gl=US) | Dựng video | VN 333,9 triệu lượt cài, nhập LUT miễn phí; CapCut 2,01 tỷ, bản điện thoại [không nhập .cube](https://cinem8.co/blogs/blog/how-to-use-luts-in-capcut-for-color-grading) ⚠ | — | FilCam không làm app dựng phim; FilCam **xuất .cube** cho VN và CapCut bản máy tính (FCM-E06-03) |

Protake (4,2 triệu lượt cài, 3,50★, quay ALEXA Log C) là đối thủ phụ. Các app LUT mới 2025–2026 (CameLUT, ColorShaper, Modipix) đều dưới 10 nghìn lượt cài. Nhập .cube miễn phí ở mọi app có hỗ trợ (Filmode, FilCam, VN, Blackmagic), nên FilCam không thu tiền phần nhập.

**Không làm:** app dựng phim nhiều lớp; quay Log của hãng (Samsung Log, Log của Xiaomi) khi quay, vì không có API chung và Blackmagic có được là nhờ hợp tác riêng ⚠; ProRes; AI sinh ảnh; tài khoản bắt buộc.

## 5. Mô tả tính năng theo epic

Bảng feature đầy đủ, ước tính và tiêu chí nghiệm thu ở [epics-features.md](epics-features.md). Mục này mô tả thiết kế để dev hiểu vì sao ước như vậy. Mọi tên API chưa kiểm trên tài liệu chính thức mang ⚠.

### 5.1 Máy ảnh thủ công và RAW (FCM-E01)

- **Giữ nguyên** mọi thứ 1.0.21 đang có, gom vào module `:filcam:manual` và `:filcam:photo` (ưu tiên `Có sẵn`). Phiên chụp thường chuyển sang wrapper CameraX 1.6 của lõi (FLC-E01-16) với `CameraEffect` LUT; điều khiển tay qua Camera2Interop (FCM-E01-02). Chế độ cần session Camera2 riêng (phơi sáng dài, vệt sáng, bracketing, xếp chồng) vẫn ở `:filcam:photo` nhưng render look qua `:core:gpu`.
- **Một bộ điều khiển phơi sáng cho ảnh và video** (`ExposureController`, FCM-E01-10). Ở video, khi tắt AE thì đặt `SENSOR_EXPOSURE_TIME`, `SENSOR_SENSITIVITY` và `SENSOR_FRAME_DURATION` = 1/fps để giữ fps. Khóa AE/AF/AWB miễn phí ở cả ảnh và video.
- **Công cụ đo viết lại thành pass GPU** (`:filcam:monitor`) gắn cờ "chỉ preview", để không bao giờ lọt vào ảnh hay file quay: zebra 2 ngưỡng, focus peaking (Sobel trên luma ở ½ độ phân giải), false color, histogram, waveform. Scopes dùng chung renderer với trình chỉnh màu (mục 5.5).
- Android 16: hybrid AE và nhiệt độ màu/tint chính xác thay vòng AE tự viết ở chế độ S/I (V1).

### 5.2 Quay video có LUT (FCM-E02)

**Đường video hai nhánh.** Camera mở hai luồng qua `SessionConfig` của CameraX 1.6: luồng preview (≤ 1080p) và luồng ghi (1080p hoặc 4K). Mỗi luồng có một `CameraEffect` riêng dùng `SurfaceProcessor` của `:core:gpu`.

```
                  CameraX 1.6: SessionConfig(Preview + VideoCapture<Recorder>), kiểm bằng isSessionConfigSupported
                         │                                                   │
          luồng PREVIEW (≤ 1080p)                                 luồng VIDEO_CAPTURE (1080p / 4K)
                         │                                                   │
      CameraEffect "xem" (target PREVIEW)                     CameraEffect "ghi" (target VIDEO_CAPTURE), theo chế độ:
      inputTransform → look (trilinear)                        • In LUT: inputTransform → look (tetrahedral ở tier A)
      → zebra, peaking, false color, scopes                    • Ghi sạch: không gắn effect
        (EffectPass previewOnly)                               • FM-Log GPU (V1): tuyến tính hóa → FM-Log → dither
                         │                                                   │
                      màn hình                                  Recorder (MediaCodec + Media3 Muxer của CameraX 1.6)
                                                                             │
                                                  MP4 → MediaStore Movies/FilCam; sidecar .cube/.flook/.fcm.json
```

| Chế độ ghi | Nhánh preview | Nhánh ghi | Gói | Khi máy không chạy được hai nhánh |
|---|---|---|---|---|
| In LUT vào file | look + công cụ đo | look (không công cụ đo) | Free (1080p), Pro (4K) | Một effect cho cả PREVIEW và VIDEO_CAPTURE (stream sharing): preview giống hệt file; công cụ đo chỉ hiện khi chưa ghi |
| Ghi sạch + LUT chỉ để xem | look + công cụ đo | không effect; ghi sidecar | Pro | Recorder dự phòng (V1) hoặc ẩn |
| FM-Log qua ISP (V1) | FM-Log → 709 + look | không effect (đường cong nằm trong ISP) | Pro | Như trên |
| FM-Log qua GPU (V1) | look trên luồng 709 | FM-Log + dither | Pro | Như trên |
| HLG 10-bit (V1) | HLG → 709 + look | không effect, HEVC Main10 | Pro | Ẩn |

**Cách có "ghi sạch + LUT xem" trên CameraX 1.6 ⚠.** Một `CameraEffect` nhắm cả PREVIEW và VIDEO_CAPTURE làm CameraX dùng stream sharing: effect chạy một lần rồi mới tách cho màn hình và recorder, nên preview và file luôn giống nhau. Điều đó đúng cho "in LUT" nhưng sai cho "ghi sạch".
- **Cách A (chính):** hai effect với target riêng. Nhánh ghi không gắn effect (ghi sạch) hoặc gắn graph "ghi". Hai luồng PRIV (preview + record) là cấu hình mọi app camera dùng khi quay, nên đa số máy chạy được. Rủi ro: CameraX tự bật stream sharing khi số use case vượt khả năng máy (ví dụ thêm `ImageCapture`), hoặc không nhận hai effect cùng lúc trên một số máy ⚠. FilCam không bind `ImageCapture` ở chế độ video, dựng `SessionConfig` và gọi `isSessionConfigSupported` trước khi bind. Chi phí GPU thêm khoảng ¼ khi ghi 4K (thêm một pass 1080p cho preview).
- **Cách B (dự phòng, FCM-E02-17, V1):** chỉ bind `Preview`; `SurfaceProcessor` vẽ khung camera hai lần, một lần có look ra màn hình, một lần sạch (hoặc FM-Log) ra input surface của `MediaCodec` riêng; tiếng qua `AudioRecord`; mux bằng Media3 Muxer. Tự chủ codec, profile, bitrate, micro, nhưng phải tự lo đồng bộ tiếng và khôi phục file khi app bị kill.
- **Spike FCM-E02-01** (S1, 3 ngày) đo cả hai cách trên 8 máy. Nếu cách A chạy trên dưới 6/8 máy thì cách B lên MVP. Máy không chạy được cách nào thì ẩn "ghi sạch", và màn "Máy của bạn" nêu lý do.

**Độ phân giải và fps theo tier.** Tier do benchmark của lõi quyết định (FLC-E05-04), không theo tên máy. Ngưỡng chốt sau spike FLC-E05-03 và FCM-E02-03.

| | Tier A | Tier B | Tier C |
|---|---|---|---|
| Preview có LUT | 1080p30 (60 khi quay 60) | 1080p30 | 1080p30; 720p nếu benchmark kém |
| Quay 1080p in LUT (Free) | 24/25/30/60 | 24/25/30; 60 nếu benchmark đạt | 24/25/30 |
| Quay 4K in LUT (Pro) | 24/25/30; 4K60 khi `isSessionConfigSupported` xác nhận và benchmark đạt ⚠ | 24/25/30 nếu spike FCM-E02-03 đạt, không grain/halation | Không |
| Ghi sạch + LUT xem (Pro) | 1080p, 4K | 1080p; 4K nếu spike đạt | 1080p khi hai nhánh chạy |
| Nội suy LUT nhánh ghi | Tetrahedral | Trilinear | Trilinear |
| Grain, halation khi quay (Pro, V1) | Có (halation ¼) | Grain; halation ⅛ | Tắt |
| FM-Log (Pro, V1) | ISP hoặc GPU | ISP hoặc GPU | GPU, nếu spike FCM-E03-01 đạt |
| HLG 10-bit (Pro, V1) | Khi máy xác nhận | Hiếm, theo máy | Không |

Chỉ hiện fps mà máy báo có dải AE [n, n] (24 fps thường thiếu trên máy tầm thấp). 25 fps là mặc định ở VN vì điện lưới 50 Hz.

**Codec và bitrate.** H.264 mặc định. H.265 khi `Recorder` của CameraX cho chọn ⚠; nếu không thì có ở V1 qua recorder dự phòng. Bitrate đề xuất (Mbps), kẹp theo `VideoCapabilities.getBitrateRange()` của encoder; H.265 dùng khoảng 70% con số H.264. `Recorder.Builder.setTargetVideoEncodingBitRate` ⚠.

| Độ phân giải @ fps | Tiêu chuẩn | Cao | Tối đa | Dung lượng ở mức Tiêu chuẩn |
|---|---|---|---|---|
| 1080p @ 24–30 | 16 | 24 | 40 | khoảng 120 MB/phút |
| 1080p @ 60 | 24 | 36 | 60 | khoảng 180 MB/phút |
| 4K @ 24–30 | 45 | 70 | 100 | khoảng 340 MB/phút |
| 4K @ 60 | 70 | 100 | 150 | khoảng 525 MB/phút |

FM-Log cần bitrate tối thiểu cao hơn Rec.709 để hạn chế banding; con số chốt ở spike FCM-E03-01.

**Âm thanh.** MVP: ghi tiếng AAC (48 kHz, stereo khi máy có ⚠ theo mặc định của `Recorder`), chỉ xin `RECORD_AUDIO` khi người dùng bật tiếng (FLC-E06-05). V1 Pro: đồng hồ mức peak/RMS có giữ đỉnh và cảnh báo khi vượt −1 dBFS (`AudioStats` của `VideoRecordEvent` ⚠); liệt kê micro bằng `AudioManager.getDevices(GET_DEVICES_INPUTS)`; mic USB-C (bộ thu micro không dây) và tai nghe có dây thường được Android tự chọn; chọn mic cụ thể (`setPreferredDevice`) qua recorder dự phòng khi `Recorder` không cho ⚠. Người dùng Blackmagic than không chọn được micro không dây làm nguồn tiếng (424 lượt hữu ích). Android không có API tăng giảm gain micro chung; FilCam không hứa chỉnh gain.

**Góc màn trập (V1 Pro).** Thời gian phơi sáng t = (góc / 360) × (1 / fps). Góc tối đa 360° vì t không vượt thời lượng khung. Chống nhấp nháy: chọn t là bội của 1/(2 × tần số lưới), tức 1/100 s hoặc 1/50 s ở VN (50 Hz), 1/120 s hoặc 1/60 s ở Mỹ (60 Hz).

| fps | 180° | 172,8° | 90° | An toàn với đèn 50 Hz |
|---|---|---|---|---|
| 24 | 1/48 s (20,8 ms) | 1/50 s | 1/96 s | 172,8° (1/50) |
| 25 | 1/50 s | 1/52 s | 1/100 s | 180° (1/50), 90° (1/100) |
| 30 | 1/60 s | 1/62,5 s | 1/120 s | 216° (1/50), 108° (1/100) |
| 60 | 1/120 s | 1/125 s | 1/240 s | 216° (1/100) |

Góc cố định thì bù sáng bằng ISO. Khi ISO thấp nhất vẫn dư sáng thì app báo "Cần ND n nấc" (n = log₂ của phần dư). Tốc độ nhập tay khi quay vẫn miễn phí; phần Pro là chế độ góc, trợ lý chống nhấp nháy và cảnh báo ND.

**Sidecar của clip ghi sạch (MVP Pro).** Mỗi clip ghi sạch có ba file cùng tên gốc:
- `<clip>.cube`: LUT 33³ đã bake `inputTransform` + look + cường độ (cường độ bake được vì trộn với ảnh gốc là một hàm theo màu). Mở thẳng trong DaVinci Resolve, VN, CapCut bản máy tính.
- `<clip>.flook`: look đầy đủ (kể cả grain, halation mà LUT không mang theo).
- `<clip>.fcm.json`: thông số quay, ví dụ:

```json
{
  "format": "filcam.clip", "version": 1,
  "clip": "FC_20270715_143210.mp4",
  "video": { "width": 3840, "height": 2160, "fps": 25, "codec": "hevc", "bitDepth": 8, "bitrateMbps": 45 },
  "recordMode": "clean",
  "source": { "profile": "fm-log", "curve": "fm-log-v1", "path": "isp" },
  "look": { "ref": "fm:teal@3", "name": "Teal", "intensity": 0.8 },
  "lut": { "file": "FC_20270715_143210.cube", "size": 33, "bakes": ["inputTransform", "look", "intensity"] },
  "exposure": { "iso": 100, "shutterAngle": 180, "exposureTimeNs": 20000000, "wbKelvin": 5600, "tint": 0 },
  "lens": "back-wide", "device": { "model": "SM-A556E", "tier": "B" }, "app": "FilCam 2.0.0"
}
```

Không ghi GPS. File sidecar không phải media nên không vào `Movies/` qua MediaStore Video; đề xuất `Documents/FilCam/` qua `MediaStore.Files` ⚠ (cần lõi thêm API, xem [Điều chỉnh lõi](epics-features.md#điều-chỉnh-lõi)). FilCam giữ bảng nối clip ↔ sidecar, nên mở clip trong trình chỉnh màu thì look tự áp. CameraX `Recorder` chưa cho ghi metadata tùy ý vào MP4 ⚠, nên chưa nhúng thông tin vào file video.

**Màn quay.** Dải look vuốt ngang, thanh cường độ, giữ để xem gốc, chia đôi A/B; đồng hồ, phút còn lại (theo bitrate và dung lượng trống), pin, nhiệt; tạm dừng/tiếp tục; khung tỉ lệ 2.39:1, 1.85:1, 4:5, 1:1, 9:16 và vùng an toàn TikTok/Reels chỉ ở preview; chọn ống kính 0.5×/1×/tele theo thứ máy mở cho app bên thứ ba; dừng ghi an toàn khi còn 500 MB.

### 5.3 Log và HDR (FCM-E03)

**Vì sao cần FM-Log.** Không có API Log chung giữa các hãng Android. Samsung Log có trong camera gốc Galaxy S25 và trong Blackmagic Camera nhờ hợp tác; chưa thấy nguồn chính thức nào cho thấy Pixel hay Xiaomi mở Log cho app khác ⚠. mcpro24fps tự làm Log bằng đường cong GPU. FilCam làm tương tự và đặt tên **FM-Log** (khớp giá trị `fm-log` của `inputTransform.from` trong định dạng look của lõi).

**Đường cong FM-Log v1** (đề xuất; đóng băng sau spike FCM-E03-01). x là tín hiệu tuyến tính tương đối (1 = trắng của ISP), y là giá trị mã hóa 0–1 (full range, trước khi encoder đổi sang YUV):

```
y = 0,06 + 0,90 · log₉(1 + 8x)            (x ≥ 0)
x = (9^((y − 0,06) / 0,90) − 1) / 8       (hàm ngược, dùng cho LUT kỹ thuật)
```

| Mức | x | Chênh so với xám 18% | y (FM-Log) | Rec.709 để so |
|---|---|---|---|---|
| Đen | 0 | — | 0,060 | 0,000 |
| Xám −3 EV | 0,0225 | −3 | 0,128 | 0,100 |
| Xám −1 EV | 0,09 | −1 | 0,282 | 0,273 |
| **Xám 18%** | **0,18** | **0** | **0,425** | 0,409 |
| Xám +1 EV (da sáng) | 0,36 | +1 | 0,615 | 0,595 |
| Xám +2 EV | 0,72 | +2 | 0,843 | 0,849 |
| Trắng 90% | 0,90 | +2,3 | 0,922 | 0,949 |
| Trắng ISP | 1,0 | +2,47 | 0,960 | 1,000 |

Nguyên tắc: nâng đen lên 0,06 để không bị cắt khi nén; xám 18% ở 0,425, gần mốc của các đường Log phổ biến (khoảng 0,39–0,42); không có "vai" cứng ở vùng sáng như đường cong mặc định của ISP; chừa 0,04 ở đỉnh. FM-Log **không tăng dải động của cảm biến**; nó làm ảnh phẳng và phân bổ lại mã để chỉnh sau. App và bài học nói rõ điều này.

**Hai cách tạo FM-Log.**
- **Qua ISP (ưu tiên):** đặt `CaptureRequest.TONEMAP_MODE = TONEMAP_MODE_CONTRAST_CURVE` và `TONEMAP_CURVE` lấy mẫu FM-Log (tối đa `TONEMAP_MAX_CURVE_POINTS`, thường ≥ 64 ⚠) qua `Camera2CameraControl`. ISP áp đường cong ở độ chính xác cao trước khi lượng tử 8-bit, nên ít banding hơn. Đường cong áp cho mọi luồng, nên nhánh preview phải chạy FM-Log → 709 + look, còn nhánh ghi không gắn effect. Chỉ dùng khi máy báo có `CONTRAST_CURVE` và spike thấy ISP thật sự áp nó cho luồng video ⚠.
- **Qua GPU (dự phòng):** nhánh ghi tuyến tính hóa luồng Rec.709 (ngược OETF), áp FM-Log, thêm dither blue-noise ±0,5 LSB. Đường cong và vai sáng của ISP đã nằm trong dữ liệu nên độ mềm vùng sáng kém hơn cách ISP. Sidecar ghi `path: gpu` để phân biệt.

**LUT kỹ thuật** (sinh bằng code từ công thức, 33³ và 65³, manifest `owned`, miễn phí, tải được từ app và web): `FM-Log_to_Rec709_Neutral.cube` (FM-Log ngược rồi OETF Rec.709) và `FM-Log_to_Rec709_Contrast.cube` (thêm đường cong S nhẹ giống ảnh mặc định của điện thoại). HLG → Rec.709 theo BT.2408 ⚠. Trong FilCam, LUT kỹ thuật vào `inputTransform` và được gộp với look thành một texture (FLC-E01-20).

**Hướng dẫn phơi sáng cho Log.** Khi quay FM-Log, zebra mặc định ở 0,90 và false color dùng bảng riêng:

| Dải tín hiệu | Màu false color | Nghĩa (FM-Log) | Bảng Rec.709 tương ứng |
|---|---|---|---|
| < 0,10 | Tím | Đen, gần như mất chi tiết (dưới xám khoảng −3,8 EV) | < 2% |
| 0,10–0,20 | Xanh dương | Bóng tối | 2–10% |
| 0,40–0,45 | Xanh lá | Xám 18% phơi đúng | 38–44% |
| 0,52–0,62 | Hồng | Tông da (sáng hơn xám 0,5–1 EV) ⚠ chỉnh theo da người Việt | 55–70% |
| 0,88–0,92 | Vàng | Gần cháy | 90–95% |
| > 0,92 | Đỏ | Cháy | > 95% |

Có chấm đo điểm (spot) hiện giá trị tín hiệu và mốc "xám 18% = 0,425"; chọn đo trên tín hiệu Log hay trên ảnh sau LUT.

**HLG 10-bit (V1 Pro).** Chỉ hiện khi máy xác nhận cấu hình, kiểm trước khi bind:

```kotlin
val recorder = Recorder.Builder().setQualitySelector(QualitySelector.from(Quality.UHD)).build()
val video = VideoCapture.Builder(recorder).setDynamicRange(DynamicRange.HLG_10_BIT).build()
val config = SessionConfig(useCases = listOf(preview, video), effects = listOf(previewEffect)) // ⚠ chữ ký API
val hlgOk = cameraInfo.isSessionConfigSupported(config)   // ⚠ tên API; có thể dùng nhóm tính năng HLG
```

Ghi HEVC Main10, BT.2020, HLG, không in look (V1). Preview đổi HLG → SDR bằng LUT kỹ thuật rồi áp look. Effect trên luồng 10-bit là rủi ro nên có spike FCM-E03-06 trước. Trình chỉnh màu tone map HLG → SDR khi xuất (mục 5.5).

### 5.4 Quản lý LUT (FCM-E04)

- Một thư viện look cho ảnh, video và chỉnh clip, dùng kho của lõi (FLC-E02-01). Nhập .cube 17/33/65, .3dl, HALD, nhiều file từ .zip, có báo cáo file lỗi (FLC-E01-05). Nhập luôn miễn phí.
- Hai nhóm: **Sáng tạo** (look) và **Kỹ thuật** (Log → 709). App gợi ý nhóm theo tên file, `TITLE` và dải đầu vào; người dùng sửa được. Chọn "Nguồn" trên màn quay thì LUT kỹ thuật tự gắn vào `inputTransform`.
- Thumbnail render trên khung hình camera hiện tại, cập nhật mỗi 2 giây khi mở bộ chọn.
- Bộ khởi đầu: 43 look ảnh hiện có + 12 look điện ảnh mới (Free), 24 look điện ảnh Pro (xem trước được, khóa khi bấm quay hoặc xuất). Tên look tự đặt, qua `NameGuard`.
- V1: nhận look từ Filmode và Studio trên cùng máy (FLC-E02-09), mở `.flook`/QR/link (FLC-E02-08), đồng bộ khi đăng nhập (FLC-E02-06), quét QR ngay trong app. Khối look FilCam chưa áp khi quay (khung, date stamp) thì báo "Chưa áp khi quay: khung".

### 5.5 Chỉnh màu clip có sẵn (FCM-E05)

**Luồng xử lý.** Photo Picker (video, không xin `READ_MEDIA_VIDEO`) → đọc thông số bằng `MediaExtractor` → xem trước bằng ExoPlayer + `setVideoEffects(LookGlEffect)` → xuất bằng Media3 Transformer + cùng `LookGlEffect` → MediaStore `Movies/FilCam`. Preview và file xuất dùng một shader (FLC-E01-21), không dùng thẳng `SingleColorLut` vì chưa rõ nó nhận RGB tuyến tính hay gamma ⚠.

**Chọn nguồn (Log → Rec.709, V1 Pro):**

| Nguồn | Nhận diện tự động | LUT kỹ thuật | Ghi chú |
|---|---|---|---|
| Rec.709 | Mặc định | — | |
| FM-Log | Sidecar `.fcm.json` của FilCam | FM-Log → Rec.709 | Look đã dùng khi quay tự áp |
| HLG | `KEY_COLOR_TRANSFER` = HLG | HLG → Rec.709 hoặc tone map của Transformer | |
| PQ (HDR10) | `KEY_COLOR_TRANSFER` = ST 2084 | Tone map của Transformer | |
| Samsung Log | Người dùng chọn; gợi ý khi clip 10-bit từ Galaxy S24/S25 ⚠ | Samsung Log → Rec.709 tự làm, chỉ khi spike FCM-E05-09 đạt ⚠ | Quay bằng camera gốc Samsung |
| Apple Log | Người dùng chọn; gợi ý theo metadata iPhone ⚠ | Apple Log → Rec.709 theo đặc tả công khai của Apple ⚠ | Chỉ clip HEVC; ProRes không giải mã được trên Android, app báo trước ⚠ |

Clip Log thường là 10-bit nhưng gắn nhãn SDR. Media3 có thể giải mã về 8-bit trong GL và làm mất lợi ích của Log ⚠; spike FCM-E05-09 kiểm việc này.

**Công cụ chỉnh:** look + cường độ; phơi sáng, nhiệt độ màu/tint, tương phản, highlights/shadows, bão hòa (khối `adjust` của look); đường cong master và R/G/B, spline đơn điệu, preview bằng texture 1D 256 và bake vào LUT 33³ khi lưu; cắt đầu cuối (MVP). Bánh xe lift/gamma/gain + offset kiểu ASC CDL, nhập/xuất `.cdl` (V1 Pro). Mọi chỉnh sửa lưu được thành look để dùng lại trên kính ngắm.

**Scopes trên GPU** (renderer chung với kính ngắm, `:filcam:monitor`):
- Khung được thu về 256×144 (hoặc 320×180) bằng một pass.
- Máy có GLES 3.1+: compute shader, mỗi pixel `imageAtomicAdd` vào texture `r32ui` (waveform 256×256, parade 3 cột, vectorscope 256×256 theo Cb/Cr BT.709, histogram 256×1).
- GLES 3.0: vertex shader đọc pixel bằng `texelFetch` theo `gl_VertexID`, vẽ điểm với additive blending vào texture R16F (`EXT_color_buffer_half_float` ⚠, dự phòng RGBA8 thang thô hơn).
- Hiển thị bằng thang log; histogram đọc 256 bin về CPU 10 lần/giây để báo "% cháy". Trên kính ngắm cập nhật 15 Hz; trong trình chỉnh màu cập nhật từng khung khi tạm dừng. Ngân sách ≤ 1,5 ms GPU mỗi khung ở tier B ⚠.
- Kính ngắm (Free): histogram và waveform luma. Trình chỉnh màu (Pro, V1): thêm RGB parade, vectorscope có đường tông da và ô 75%.

**Xuất và hàng đợi.**
- Một clip (MVP): `Transformer` + `EditedMediaItem` (clip, `ClippingConfiguration`, `Effects(videoEffects = [LookGlEffect])`); tiếng chép nguyên khi không cắt; H.264/H.265; bitrate như gốc hoặc tự chọn; ghi file tạm trong cache rồi chuyển vào MediaStore với `IS_PENDING` (FLC-E06-02). Miễn phí: clip ≤ 60 giây và ≤ 1080p. Pro: không giới hạn, 4K.
- Tone map HDR → SDR (V1 Pro): `HDR_MODE_TONE_MAP_HDR_TO_SDR_USING_OPEN_GL` (API 29+) hoặc `…_USING_MEDIACODEC` (API 31+) ⚠, rồi mới áp look.
- Hàng loạt (V1 Pro): hàng đợi trong Room (`export_job`: clip, look, thiết lập, trạng thái, tiến độ, file ra, lỗi). Một `CoroutineWorker` của WorkManager chạy **từng job một** (tránh tranh encoder), gọi `setForeground` với loại `FOREGROUND_SERVICE_TYPE_MEDIA_PROCESSING` trên API 35+ và `DATA_SYNC` trên API 29–34 ⚠ (khai `foregroundServiceType` cho `SystemForegroundService`, quyền `FOREGROUND_SERVICE_*`, hỏi `POST_NOTIFICATIONS` trên API 33+ lúc người dùng bấm xuất). Thông báo có tiến độ từ `Transformer.getProgress`. App bị kill thì job dở chạy lại từ đầu và file tạm bị xóa. Giữa hai job, kiểm nhiệt: `SEVERE` thì tạm dừng; pin < 15% không sạc thì chờ. Play yêu cầu khai loại foreground service trong Console ⚠.

### 5.6 Tạo và xuất LUT (FCM-E06, V1)

- Lưu bản chỉnh (clip hoặc khung camera) thành look; xuất .cube 33/65 và HALD qua FLC-E01-19. Chọn "gồm LUT kỹ thuật" (Log → look, áp thẳng lên clip Log) hay "chỉ look" (709 → look). Màn xuất liệt kê phần không đi theo LUT (grain, halation, vignette).
- Hồ sơ xuất cho CapCut bản máy tính, VN, DaVinci Resolve, LumaFusion, app camera có nhập LUT (kích thước lưới, tên file ASCII không dấu, `DOMAIN` ⚠ từng app), gói .zip kèm hướng dẫn.
- LUT từ ảnh mẫu bằng Match v1 của lõi (FLC-E01-18); LUT Maker trên khung camera đóng băng. Chia sẻ look qua QR/link miễn phí. V2: LUT hiệu chỉnh máy bằng thẻ màu 24 ô.

### 5.7 Kiếm tiền (FCM-E08)

Billing, paywall, thử giá và bảng giá vùng là của lõi (FLC-E03-*). FilCam khai quyền `pro`, `free-tier.json` (mục 6), SKU và giá (mục 7), chỗ gọi paywall (chọn 4K, ghi sạch, FM-Log/HLG, xuất clip > 60 giây, xuất LUT, chế độ chuyên sâu, look Pro) và sự kiện phễu video (`record_start`, `record_stop`, `grade_export`, `lut_export`, `pro_gate`). Không chặn người mới trước khi họ quay được clip đầu.

### 5.8 Tương thích thiết bị (FCM-E07)

**Ma trận thiết bị.** Tối thiểu 10 máy mỗi bản phát hành (FCM-E07-06), rộng hơn 8 máy của lõi vì quay 4K và HLG cần thêm máy tier A và B. Tier cuối cùng theo benchmark; tên máy dưới là ví dụ phổ biến ở VN, chốt khi mua ⚠.

| Tier | Đặc điểm (ví dụ SoC ⚠) | Máy trong ma trận | FilCam video |
|---|---|---|---|
| A | Flagship 2024+ (Snapdragon 8 Gen 3, 8 Elite; Exynos 2400; Tensor G3, G4); Camera2 FULL hoặc LEVEL_3 | Galaxy S24, Galaxy S25 (clip Samsung Log mẫu), Pixel 8, Pixel 9 (máy tham chiếu CameraX) | 1080p 24–60, 4K 24–30 in LUT và ghi sạch; HLG; FM-Log qua ISP; grain, halation |
| B | Tầm trung khá (Exynos 1380, 1480; Dimensity 7300; Snapdragon 7 Gen 3); LIMITED trở lên | Galaxy A55, Galaxy A35 (máy tầm trung chuẩn của lõi), Redmi Note 14 Pro 5G, OPPO Reno12 hoặc Reno13, Vivo V30 hoặc V40 | 1080p 24–30 (60 nếu đạt); 4K30 nếu spike đạt; ghi sạch 1080p; FM-Log |
| C | Phổ thông (Helio G99, Snapdragon 685, Exynos 1330); LIMITED hoặc LEGACY | Galaxy A16 hoặc A15, Redmi Note 13 4G (lõi đang tạm coi Redmi Note 13 là máy tầm trung chuẩn ⚠; tier chốt theo benchmark), một máy OPPO A, một máy Vivo Y | 1080p 24–30 in LUT; không 4K; ghi sạch nếu hai nhánh chạy |
| Clip mẫu | — | iPhone 15 Pro (Apple Log), Galaxy S24 Ultra hoặc S25 (Samsung Log) | Chỉ để có clip test trình chỉnh màu |

Checklist mỗi bản: quay 1080p và 4K 10 phút, đổi look khi quay, ghi sạch và sidecar, tiếng, xoay bốn hướng, ống kính, nhiệt, kill app khi đang quay, lưu file, cập nhật từ bản cũ. Máy tier A hoặc B nào "mất file quay" thì không phát hành.

**Năng lực và chính sách.** `CameraCapabilities` của lõi cộng phần dò riêng cho video (mức Camera2, fps theo kích thước, encoder HEVC/Main10 và bitrate tối đa, `TONEMAP`, kết quả `isSessionConfigSupported` cho các cấu hình FilCam). Bảng chính sách (FCM-E07-02) quyết định 4K, 60 fps, ghi sạch, nội suy, grain/halation, FM-Log, HLG theo tier; remote config chặn hoặc mở từng tính năng theo model (kill switch) mà không cần phát hành bản mới.

**Nhiệt và pin khi quay** (`PowerManager.addThermalStatusListener`, `getThermalHeadroom` từ API 30):

| Trạng thái | FilCam làm gì |
|---|---|
| `NONE`, `LIGHT` | Bình thường |
| `MODERATE` | Tắt grain/halation và tetrahedral ở nhánh ghi; scopes còn 5 Hz; peaking ở ¼ độ phân giải |
| `SEVERE` | Cảnh báo; preview còn 24 fps; không cho bắt đầu clip 4K mới; gợi ý hạ 1080p; hàng đợi xuất tạm dừng |
| `CRITICAL` trở lên | Dừng ghi an toàn (đóng file), báo lý do |
| Pin ≤ 10% | Cảnh báo; ≤ 5% không sạc thì dừng ghi an toàn |
| Dung lượng ≤ 1 GB | Cảnh báo; ≤ 500 MB thì dừng ghi an toàn |
| Headroom dự báo 30 giây ≥ 1,0 (V1) | Báo "máy sắp nóng", gợi ý hạ cấu hình trước khi vào `SEVERE` |

**Danh sách máy công khai (V1)** ở `filmode.app/filcam/devices` ⚠: model, tier, 1080p LUT, 4K LUT, ghi sạch, FM-Log, HLG, lỗi đã biết, trạng thái "Đã kiểm", "Người dùng báo chạy", "Chưa kiểm". Script sinh trang từ kết quả ma trận và dữ liệu năng lực ẩn danh (tắt được), cập nhật mỗi bản phát hành.

**Báo lỗi theo máy ngay trong app (MVP).** Màn "Máy của bạn" liệt kê tính năng có/không kèm lý do. Nút "Báo lỗi máy này" gửi model, SoC, bản Android, tier, bảng năng lực, cấu hình phiên camera cuối và 200 dòng log; không ảnh, không video, không đường dẫn hay tên file. Gửi qua backend của lõi (FLC-E08-02) ⚠; offline thì xếp hàng. Dữ liệu này cộng Crashlytics (khóa model, tier) cho ra bảng crash và quay lỗi theo hãng, là mốc đo của Bảng 13.

### 5.9 Hướng dẫn (FCM-E09)

Onboarding 3 bước (MVP): chọn mục đích (quay video có LUT, chụp RAW, chỉnh clip), gợi ý thiết lập theo tier máy, xin quyền đúng lúc, mẹo lần đầu cho đổi LUT, zebra, ghi sạch. V1: bài học offline VI/EN trong app, nút "Thử ngay" đặt sẵn cấu hình; bài "Quay Log và dùng lut màu trên Android"; bài thực hành với clip FM-Log mẫu (người dùng miễn phí làm được hết bài); trang web song ngữ cho SEO và tải LUT kỹ thuật.

### 5.10 FilCam iOS (FCM-E10, V2)

Chỉ làm khi Android đạt tiêu chí "đẩy mạnh" (mục 10). Dùng `FilmodeCoreKit` (renderer Metal, chuỗi LUT, thư viện, StoreKit 2). `AVCaptureSession` + `AVCaptureVideoDataOutput` → Metal → `AVAssetWriter`; kính ngắm có look, chỉnh tay, ghi 1080p in look (Free), 4K và ghi sạch + sidecar (Pro); **Apple Log** (`AVCaptureColorSpace.appleLog`, iPhone 15 Pro trở lên) với preview Apple Log → 709 + look; công cụ đo trên Metal; RAW; chỉnh màu clip bằng `AVVideoComposition`. Sidecar và look đọc được chéo giữa Android và iOS. Khoảng 37 ngày dev iOS (spike 2 ngày trước).

### 5.11 Spike 🧪

| ID | Câu hỏi | Ngày | Khi nào | Quyết định phụ thuộc |
|---|---|---|---|---|
| FCM-E01-01 | Code 1.0.21 viết thế nào, tách module được không? | 1 | S1 | Ước lại các dòng `Có sẵn` |
| FCM-E02-01 | "Ghi sạch + LUT xem" chạy bằng hai effect (cách A) hay phải tự ghi (cách B) trên bao nhiêu máy? | 3 | S1 | Recorder dự phòng lên MVP hay giữ V1 |
| FCM-E02-03 | 4K30 có LUT trên tier B có giữ fps và nhiệt không? | 2 | S3 | 4K cho tier B hay chỉ tier A |
| FCM-E03-01 | FM-Log 8-bit banding tới đâu (ISP, GPU, dither, bitrate)? | 2 | S9 | Đường mặc định, tham số FM-Log v1, bitrate tối thiểu |
| FCM-E03-06 | Effect có chạy trên luồng 10-bit HLG không? | 2 | S10 | Phạm vi HLG ở V1 |
| FCM-E05-09 | Bật được Samsung Log từ app khác không; đường cong Samsung Log; giấy phép LUT hãng; Media3 có giữ 10-bit không? | 3 | S9 | Có LUT Samsung Log hay không; cách xử lý clip Log 10-bit |
| FCM-E10-01 | iOS: 4K30 có look và Apple Log + ghi sạch trên iPhone 12, 15 Pro | 2 | V2 | Kiến trúc ghi iOS |

## 6. Gói miễn phí và Pro

Mọi mục ở cột "Miễn phí" được ghi vào `free-tier.json` (FCM-E08-02) và **không bao giờ chuyển sang Pro** (FLC-E03-04). Người đã mua FilCam Pro ở bản 1.0.21 giữ quyền (FCM-E08-01).

| Nhóm | Miễn phí | FilCam Pro |
|---|---|---|
| Chụp ảnh | P/S/I/M, ISO, tốc độ, EV, WB Kelvin, lấy nét tay, khóa AE/AF/AWB; RAW DNG + JPEG/HEIF/PNG có look; tên file, thư mục, EXIF, geotag, phím âm lượng | Phơi sáng dài, vệt sáng, bracketing, chụp đêm, focus stacking, intervalometer |
| Quay video | 1080p 24/25/30 (60 khi máy hỗ trợ) **in LUT vào file**; chọn H.264/H.265 và bitrate; tiếng; chọn ống kính; tốc độ và khóa phơi sáng nhập tay | 4K; **ghi sạch + LUT chỉ để xem + sidecar .cube**; góc màn trập và trợ lý chống nhấp nháy; rack focus; đồng hồ âm thanh và chọn micro; chống rung; grain và halation khi quay |
| Kính ngắm | **Đổi LUT, thanh cường độ, A/B ngay trên màn quay**; chồng LUT kỹ thuật; zebra, peaking, false color, histogram, waveform, lưới, thước cân bằng, khung tỉ lệ | False color và zebra cho Log, chấm đo Log |
| Log và HDR | LUT kỹ thuật (FM-Log, HLG, Apple Log, Samsung Log ⚠) dạng file .cube tải về | FM-Log (ISP, GPU); HLG 10-bit |
| Look | 43 look ảnh + 12 look điện ảnh; nhập .cube/.3dl/HALD không giới hạn; thư mục, yêu thích; nhận look từ Filmode/Studio; QR, link | Gói 24 look điện ảnh (xem trước được, khóa khi quay/xuất) |
| Chỉnh màu clip | Look, chỉnh cơ bản, đường cong, cắt; **xuất clip ≤ 60 giây và ≤ 1080p** | Không giới hạn thời lượng, 4K; Log → Rec.709; bánh xe màu/CDL; parade và vectorscope; tone map HDR; xuất hàng loạt |
| Tạo LUT | Chia sẻ look qua QR, link, `.flook` | Xuất .cube/HALD; hồ sơ xuất cho app khác; LUT từ ảnh mẫu; LUT Maker; hiệu chỉnh thẻ màu (V2) |
| Khác | Bài học, onboarding, "Máy của bạn", báo lỗi theo máy; không quảng cáo, không watermark | — |

## 7. Giá

Giá là đề xuất của Bảng 8, cần thử A/B (FCM-E08-03). Neo giá: mcpro24fps $19.99 một lần; Halide $19.99/năm, $69.99 một lần; PeekLut $34.99/năm; LUT Studio $29.99–49.99/năm; Filmic Pro $39.99/năm (iOS); công cụ LUT chuyên nghiệp $35–60/năm (Bảng 6).

| Gói | Mỹ | Việt Nam | Ghi chú |
|---|---|---|---|
| Tháng | $2.99–3.99 | khoảng 69.000–79.000 ₫ ⚠ (Bảng 8 không nêu giá tháng VN) | Không dùng thử |
| Năm | $19.99–24.99, **dùng thử 7 ngày** | 249.000–299.000 ₫ | A/B hai mức $19.99 và $24.99 (VN 249.000 và 299.000 ₫) |
| Trọn đời | $39.99 | khoảng 499.000 ₫ | Đặt nổi bật trên Android (32,2% lượt hủy thuê bao trên Play đến từ lỗi thanh toán) |
| SKU FilCam đang bán | Giữ | Giữ | Map vào `pro`, không bao giờ xóa dòng |

Giá ID, BR và các vùng khác theo bảng giá vùng của lõi (FLC-E03-08), khoảng 40–50% giá Mỹ. Paywall theo [checklist của lõi](../filmode-core.md#43-checklist-paywall): chữ lớn nhất là "249.000 ₫/năm"; dòng dùng thử ghi "Miễn phí 7 ngày, sau đó 249.000 ₫/năm, tự gia hạn. Bị trừ tiền ngày … nếu không hủy trước."; liệt kê những gì vẫn miễn phí.

## 8. Phạm vi theo bản

Chi tiết từng feature ở [epics-features.md](epics-features.md). Số ngày là ngày công dev, chưa gồm thiết kế UI, dịch, nội dung và rà soát pháp lý.

| Bản | Ngày công | Nội dung chính |
|---|---|---|
| **Có sẵn** (gom vào lõi, kiểm lại) | 10 | Chỉnh tay, RAW DNG và định dạng, công cụ kính ngắm, chế độ chuyên sâu, 43 look và dữ liệu cũ, SKU cũ, đưa app vào monorepo |
| **MVP** (ra mắt cuối 7/2027) | 93 | Chuyển app ảnh lên wrapper CameraX của lõi; pipeline video hai nhánh; 1080p có LUT (Free), 4K (Pro); codec, bitrate, tiếng; đổi LUT + cường độ + A/B trên màn quay; chồng LUT kỹ thuật; in LUT hoặc ghi sạch + sidecar; màn quay, ống kính, khung tỉ lệ; công cụ đo GPU chỉ ở preview; thư viện LUT, bộ look Free và Pro; chỉnh màu clip (cơ bản, đường cong, cắt, xuất ≤ 60 giây Free); năng lực máy, chính sách tier, dừng ghi an toàn, "Máy của bạn", báo lỗi theo máy; giá, paywall, phễu; onboarding; test tự động, benchmark, chạy thử 2 tuần, listing; 3 spike |
| **V1** (8–10/2027) | 75 | FM-Log (ISP, GPU) + LUT kỹ thuật + hướng dẫn phơi sáng; HLG 10-bit; góc màn trập, rack focus, âm thanh và micro ngoài, chống rung, grain/halation khi quay; recorder dự phòng; Log → 709 (Samsung Log ⚠, Apple Log), bánh xe màu, scopes clip, tone map HDR, xuất hàng loạt; xuất LUT, hồ sơ xuất, LUT từ ảnh mẫu, LUT Maker, chia sẻ; nhận look từ Filmode/Studio, quét QR; nhiệt nâng cao, trang danh sách máy, đo ổn định theo hãng; bài học; Android 16 hybrid AE; 3 spike |
| **V2** (sau mốc đo 12 tuần) | 43 | FilCam iOS với Apple Log (37); FM-Log 10-bit; hiệu chỉnh màu bằng thẻ 24 ô |

## 9. ASO

Tiêu đề theo Bảng 8. Độ dài đã đếm: tiêu đề ≤ 30, mô tả ngắn ≤ 80 ký tự. Không dùng tên hãng (Blackmagic, Apple, Samsung, CapCut, DaVinci, iPhone) trong tiêu đề, mô tả ngắn, ảnh chụp màn hình hay tên look; mô tả dài chỉ nêu định dạng tương thích (".cube") ⚠ rà soát pháp lý.

| | EN (US, SG, AU) | VI |
|---|---|---|
| Tiêu đề | FilCam: LUT Video & RAW Camera (30) | FilCam: Quay LUT màu & RAW (26) |
| Mô tả ngắn | Shoot video with live LUTs, Log & RAW. Import .cube, grade clips, export LUTs. (78) | Quay có LUT màu ngay trên màn hình, chụp RAW, chỉnh màu clip và xuất file .cube. (80) |
| Từ khóa chính | lut camera, 3d lut, cube lut, video lut, color grading, log camera | lut màu, lut màu cho điện thoại, chỉnh màu video, quay log |
| Từ khóa phụ | raw camera, manual camera, cinematic camera, pro camera, film look video | máy quay chuyên nghiệp, quay phim điện ảnh, chụp raw, máy ảnh chỉnh tay |
| Ảnh chụp màn hình (thứ tự) | Change LUTs while recording · Clean record, LUT preview · Log to Rec.709 on your phone · Zebra, false color, waveform · RAW + film look photos · Export .cube | Đổi LUT ngay khi quay · Ghi sạch, xem LUT · Log sang Rec.709 trên điện thoại · Zebra, false color, waveform · Chụp RAW kèm màu film · Xuất file .cube |

**Cầu tìm kiếm** (Google Trends, tỉ lệ trước giai đoạn dữ liệu nhiễu, Bảng 1 và `keyword_search_demand.md`):

| Từ khóa | Thị trường | Xu hướng | Dùng |
|---|---|---|---|
| lut màu | VN | 4,15× (nền nhỏ); "lut màu blackmagic camera" +1.950% | Từ khóa chính VN |
| cube lut, luts, lut app | TG, US, JP, KR, DE | 2,04×; 1,6×; 3,4× | Chính EN; "lut" đứng một mình bị lẫn nghĩa (Lutron, "lụt") nên luôn ghép "lut camera", "3d lut", "cube lut" |
| color grading | TG, US, ID, BR, DE | 1,88× (BR 4,6×, ID 1,45×) | Phụ EN; gợi ý liên quan "color grading app" |
| apple log lut | TG | +100% | Chỉ ở web và bài học, không ở listing |
| raw camera, manual camera | US | FilCam #24, #29 | Giữ trong mô tả, là chỗ đứng duy nhất hiện có |

Thị trường theo README chung: VN, US, ID, BR đợt 1; JP, KR, DE sau (DE cần thêm ngôn ngữ vào lõi ⚠). Khoản chi đầu tiên đáng làm là một tháng công cụ ASO trả phí để có số lượt tìm thật cho Play Mỹ và Việt Nam (kết luận báo cáo).

## 10. KPI và tiêu chí dừng hoặc đẩy mạnh

Mốc đo của Bảng 13 cho FilCam: **tỉ lệ crash theo hãng máy** và **tỉ lệ chuyển sang Pro**.

| KPI | Ngưỡng | Nguồn ngưỡng | Cách đo |
|---|---|---|---|
| Tỉ lệ crash người dùng thấy, **theo từng hãng** (Samsung, Xiaomi, OPPO, Vivo, Google) | < 1,09% mỗi hãng; mục tiêu < 0,5% | Ngưỡng "bad behavior" của Play Vitals ⚠; mốc đo Bảng 13 | Play Console + Crashlytics khóa model, tier (FCM-E07-09) |
| ANR theo hãng | < 0,47% | Play Vitals ⚠ | Như trên |
| Quay thành công (file phát được / `record_start`) theo hãng | ≥ 99,5% | Nội bộ | `record_stop.result` (FCM-E08-05) |
| Báo lỗi theo máy tier A/B chưa phản hồi quá 7 ngày | 0 | Nội bộ | FCM-E07-04 |
| Phiên có quay video | ≥ 40% ⚠ | Nội bộ | Phễu |
| Cài → bắt đầu dùng thử | ≥ 3% ⚠ | Nội bộ | Play Console |
| Dùng thử → trả tiền | ≥ 17,1% | RevenueCat, trung vị Photo & Video trên Play | Play Console |
| Doanh thu | $1K/tháng trong 6–12 tháng | Kết luận báo cáo (mốc đầu cho mỗi app) | Play Console |
| Thứ hạng | Top 10 "lut màu" (VN), top 30 "lut camera" (US) sau 3 tháng ⚠ | Nội bộ | Tra tay hoặc công cụ ASO |

**Quyết định ở mốc 12 tuần sau ra mắt** (khoảng cuối 10/2027):
- **Đẩy mạnh:** mọi hãng trong top 5 dưới ngưỡng crash, quay thành công ≥ 99,5%, dùng thử → trả tiền ≥ 17%, doanh thu tăng đều. Mở V2 (iOS, FM-Log 10-bit), thêm JP, KR, DE, thuê công cụ ASO.
- **Sửa:** một hãng vượt ngưỡng crash thì thu video Pro của hãng đó về danh sách cho phép (FCM-E07-02) và phát hành bản sửa trong 2 tuần. Dùng thử → trả tiền 8–17% thì thử giá và paywall; không bao giờ thu hẹp gói miễn phí.
- **Dừng đầu tư:** sau 2 bản sửa mà Samsung hoặc Xiaomi vẫn vượt ngưỡng crash, hoặc doanh thu dưới $300/tháng sau 6 tháng ⚠. Giữ FilCam ở chế độ bảo trì (sửa lỗi, nâng target API), không làm V2 và iOS; dồn lực cho Filmode và Studio.

## 11. Rủi ro

| Rủi ro | Ảnh hưởng | Cách xử lý |
|---|---|---|
| **Phân mảnh thiết bị**: 29% đánh giá 1–2★ của Blackmagic Camera và mcpro24fps nhắc tên một hãng máy (Samsung, Xiaomi, Pixel dẫn đầu) | Điểm Play giảm, hoàn tiền | Dò năng lực + chính sách tier + kill switch theo model (FCM-E07-01, -02); ma trận ≥ 10 máy; "Máy của bạn" và báo lỗi theo máy ở MVP; danh sách máy công khai; 20–25% công sức cho kiểm thử |
| Ghi sạch + LUT xem không chạy khi CameraX ép stream sharing ⚠ | Mất tính năng Pro chính trên một phần máy | Spike FCM-E02-01 ở S1; recorder dự phòng (FCM-E02-17); ẩn khi không chạy |
| **Nhiệt** khi quay 4K có LUT trên máy tầm trung | Máy tự tắt camera, file hỏng | Dừng ghi an toàn ở MVP (FCM-E07-05); 4K theo tier; spike FCM-E02-03; Media3 Muxer của CameraX 1.6 giữ file khi app chết |
| **Samsung hạn chế Camera2** cho app bên thứ ba (ZSL, DCG, fps cao ở ống tele theo bài đăng của người dùng ⚠); Samsung Log chỉ qua đối tác | Samsung là hãng lớn nhất VN (26% năm 2025) | Không hứa Samsung Log khi quay; FM-Log cho mọi máy; chỉnh clip Samsung Log quay bằng camera gốc (V1, sau spike); nói rõ trong "Máy của bạn" |
| **Không có API Log chung** | Không có "Log thật" trên Android | FM-Log qua ISP, dự phòng GPU; nói rõ FM-Log không tăng dải động; HLG 10-bit khi máy có |
| **Banding 8-bit** khi quay FM-Log | Trời, tường bị sọc sau khi chỉnh | Spike FCM-E03-01; ưu tiên ISP; dither; bitrate tối thiểu; gợi ý H.265 hoặc HLG khi máy có |
| API chưa chắc: effect trên luồng 10-bit, `Recorder` chọn HEVC/micro, `SingleColorLut` nhận tuyến tính, Media3 giải mã 10-bit ⚠ | Màu sai, thiếu tùy chọn | `LookGlEffect` của lõi; spike FCM-E03-06, FCM-E05-09; recorder dự phòng |
| Blackmagic Camera miễn phí và đã có LUT | Khó thu tiền | Khác biệt ở máy tầm trung, đổi LUT + cường độ trên màn quay, chỉnh clip và xuất LUT trên máy, tiếng Việt; gói miễn phí rộng |
| Chính sách Play cho foreground service (`mediaProcessing`, `dataSync`) ⚠ | Hàng đợi xuất bị từ chối khi review | Khai đúng loại trong manifest và Play Console; chỉ chạy khi người dùng bấm xuất |
| Nhãn hiệu trong listing, tên look, tên LUT kỹ thuật | Listing bị gỡ | `NameGuard`, lint của lõi; không dùng tên hãng trong tiêu đề, mô tả ngắn, ảnh chụp màn hình; tên LUT kỹ thuật mô tả định dạng ⚠ rà soát |
| Người dùng cũ mất LUT, công thức hay Pro khi cập nhật lên bản dùng lõi | 1★, hoàn tiền | FLC-E02-03, FCM-E04-01, FCM-E08-01; test cập nhật trong FCM-E11-05; staged rollout |
| Nguồn lực: FilCam trùng V1 của Filmode và Studio | Lỡ Q3/2027 | 2 dev Android riêng cho FilCam; cut-line ở [epics-features.md mục Nhân sự](epics-features.md#nhân-sự); V2 chỉ khi đạt mốc |

## 12. Nội dung cần làm

Khoảng **37,5 ngày** của người làm màu và nội dung, không tính vào ngày công dev: 12 look điện ảnh Free và 24 look Pro, kiểm 43 look ảnh trên video, LUT kỹ thuật FM-Log, HLG, Apple Log, Samsung Log ⚠, khoảng 20 clip mẫu, 5 bài hướng dẫn VI/EN, 3 video ngắn. 25 ngày phải xong trước MVP. Bảng chi tiết ở [epics-features.md mục Nội dung](epics-features.md#nội-dung-không-tính-vào-ngày-công-dev).

## 13. Liên kết

- [README chung](../README.md), [lõi Filmode Core](../filmode-core.md), [backlog lõi](../filmode-core-backlog.csv)
- [Báo cáo "Lõi LUT của Filmode đủ nuôi ba app"](../../../reports/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u.md): mục "App 3 — FilCam", Bảng 3, 6, 8, 12, 13 và phần rủi ro
- Ghi chú nghiên cứu `research_notes/App camera film và LUT màu/`: `film_camera_apps.md` (hồ sơ FilCam), `tech_feasibility_opportunities.md` (CameraX 1.6, Media3, Log, Samsung), `user_sentiment_pain_points.md` (yêu cầu của người dùng Blackmagic, phân mảnh), `preset_lut_editor_apps.md` (đối thủ LUT và video), `monetization_paid_features.md` (giá), `keyword_search_demand.md` (từ khóa)
