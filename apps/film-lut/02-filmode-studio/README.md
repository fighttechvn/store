# 02 · Filmode Studio: công thức màu và LUT cho ảnh (mã `FMS`)

App sửa ảnh cho người muốn **biến ảnh đã chụp thành màu film theo một công thức**. Người dùng chọn ảnh, chọn một công thức tham số kiểu máy ảnh (tông nền, hạt, độ sâu màu, lệch cân bằng trắng, dải động, vùng sáng và vùng tối…), tinh chỉnh, rồi chia sẻ công thức thành **thẻ ảnh có mã QR**. App nhập được preset và LUT người dùng đã mua (.cube, .3dl, HALD, .xmp, .dng, zip), sao chép màu từ ảnh mẫu, áp hàng loạt cho cả feed và xuất LUT cho app video. Mọi xử lý chạy trên máy, không quảng cáo, không watermark.

Quy ước ID, ưu tiên, gói và ước tính theo [README chung](../README.md). Phần dùng chung lấy từ [lõi Filmode Core](../filmode-core.md) và không định nghĩa lại ở đây.

| File | Nội dung |
|---|---|
| [epics-features.md](epics-features.md) | 13 epic, 106 feature, ước tính, tiêu chí nghiệm thu, điều chỉnh lõi, nội dung cần dựng, lộ trình sprint |
| [backlog.csv](backlog.csv) | Danh sách feature để nhập Jira, Linear hoặc GitHub Projects |

## 1. Tóm tắt

- **Vấn đề:** người thích "màu film" đọc công thức trên blog, Threads, TikTok rồi phải tự dò lại bằng Lightroom hay app Ảnh. Người đã mua preset (DNG, XMP) hay LUT (.cube) thì cần Lightroom Mobile hoặc app desktop để dùng. Muốn cả feed cùng một màu thì phải chỉnh từng ảnh.
- **Cơ hội:** lượt tìm "fujifilm recipes" tăng 5,44 lần và "film simulation" 2,35 lần trong ba năm trước giai đoạn dữ liệu Google Trends bị nhiễu; trên YouTube, "fuji recipe" đạt đỉnh 5 năm tuần 14/6/2026 ([báo cáo, Bảng 1](../../../reports/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u.md)). Trên Google Play, mảng này còn mỏng: FujiStyle có 21.872 lượt cài, Fuji X Weekly 407.926. Darkroom, RNI Films và Dehancer không có bản Android. Fimii, một app preset film của lập trình viên độc lập, bán gói trọn đời $9.99 mà lên #11 top free iOS Việt Nam sau khoảng 7 tháng ([báo cáo, Bảng 3, 4](../../../reports/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u.md)).
- **Lời hứa:** "Công thức màu film cho ảnh điện thoại. Quét QR là có màu. Nhập preset đã mua. Không quảng cáo, không watermark, mua đứt được."
- **Nền tảng và lịch:** Android (`app.filmode.studio`, đề xuất ⚠) ra mắt cuối Q1/2027 (6 sprint từ 4/1/2027, staged rollout từ 29/3); iOS nộp App Review chậm nhất 18/6/2027, ra mắt cuối Q2/2027, dựng trên `FilmodeCoreKit` và dùng lại trình sửa, Match Photo, bộ nhập .xmp của Filmode iOS khi được ⚠. Thị trường đợt 1: VN, ID; tiếng Anh cho US, SG, AU; JP.
- **Nguồn lực:** MVP Android **68 ngày công** (lõi đã có). Cần **2 dev Android** trong Q1/2027; V1 gồm 58,5 ngày Android, web và backend cùng 37 ngày iOS trong Q2/2027 (xem [nhân sự](epics-features.md#nhân-sự)). MVP cần ba mục `V1` mới của lõi: FLC-E01-27, FLC-E01-28 (ba trường `adjust`) và FLC-E02-11 (tông nền dùng chung), khoảng 3,5 ngày Android, dev Studio làm trong S1–S2 ([Điều chỉnh lõi](epics-features.md#điều-chỉnh-lõi)). Hai dev Android là dev D (mới, từ 4/1/2027) và dev B của nhóm Filmode (từ 18/1/2027), theo [lịch cả họ app](../README.md#lịch-và-nhân-sự-cả-họ-app).

## 2. Vì sao là một app riêng

**Từ khóa khác.** Filmode (App 1) sống bằng "digicam", "ccd camera", "film camera", "máy ảnh film". Studio sống bằng "film recipes", "film simulation", "film presets", "preset màu film", "chỉnh màu film", "lut màu" (Bảng 8). Hai bộ từ khóa không trùng nhau, và một listing không thể đứng đầu cho cả hai.

**Người dùng và việc cần làm khác.** Filmode là máy ảnh: mở app là chụp, "có vibe" ngay. Studio là trình sửa cho ảnh đã có, kể cả ảnh chụp bằng máy ảnh thật hay điện thoại khác, và cho creator muốn chia sẻ hoặc bán công thức. Người mua cũng khác: Studio neo vào gói trọn đời $19.99 như Afterlight và Koloro, không có pass sự kiện hay máy lẻ.

**Rủi ro 4.3 "biến thể".** Apple siết guideline 4.3 từ 9/6/2026; ứng dụng "biến thể" của cùng nhà phát triển có thể bị từ chối ([MacRumors](https://www.macrumors.com/2026/06/09/app-store-guidelines-low-quality-apps/)). Filmode iOS hiện đã có trình sửa, Match Photo, nhập .cube và .xmp, "biến Match thành LUT" (Pro) và chỉnh hàng loạt ([hồ sơ Filmode](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/film_camera_apps.md)). Studio chỉ khác biệt rõ nếu:
- Studio có những thứ Filmode không có: mô hình công thức theo thang máy ảnh, thẻ QR, dán công thức dạng chữ, bộ nhập zip/DNG có báo cáo, RAW máy ảnh, xuất LUT, trang công thức công khai, chợ creator.
- Filmode giữ vai "máy ảnh + chỉnh nhanh" theo quy tắc ranh giới dưới đây.
- Ghi chú App Review của Studio nêu các khác biệt đó (FMS-E12-14).

**Ranh giới Filmode ↔ Studio (đã chốt).** Quy tắc này giống hệt ở [README chung](../README.md#ranh-giới-giữa-các-app) và [README Filmode mục 3.3](../01-filmode/README.md#33-ranh-giới-với-filmode-studio-apple-43):

- **Filmode là máy ảnh + chỉnh nhanh:** áp máy hoặc look cho ảnh có sẵn, chỉnh cơ bản, khung, áp hàng loạt, Match Photo để tạo look cho kính ngắm. Chỉnh sâu đi qua nút "Mở trong Filmode Studio" (A6.2, FMD-E06-06).
- **Filmode iOS giữ mọi tính năng trình sửa người dùng đang có hoặc đã trả tiền** (trình sửa, Match Photo, Match → LUT, nhập .cube và .xmp, video 4K, chỉnh hàng loạt): giữ mãi, không gỡ, theo luật của Apple về tính năng đã trả tiền và cam kết không thu hồi (FLC-E03-04, FMD-E11-06). Filmode iOS không nhận thêm tính năng chỉnh sâu mới. Trình sửa đang có của Filmode Vibe trên Android (LUT, preset, curves, nhập .cube; FMD-E06-01) cũng được giữ như vậy.
- **Mọi tính năng chỉnh sâu mới làm ở Studio**, trên cả Android và iOS: công thức theo thang máy ảnh, HSL, bánh xe màu, RAW, xuất LUT, parser công thức dạng chữ, cộng đồng. Filmode Android không thêm màn xuất .cube; look Match được gửi sang Studio để xuất (FMD-E11-05).
- **Quyền Pro mua riêng từng app** (`fmd.*`, `fms.*`, `fcm.*`). Không có tài khoản thì không cấp quyền chéo giữa các package được. Gói chung nhiều app chỉ là phương án V2 ⚠, làm qua tài khoản tùy chọn; chưa có trong backlog.

## 3. Người dùng mục tiêu và việc cần làm

| Nhóm | Tình huống | Việc cần làm xong ("khi … tôi muốn … để …") | Đầu ra | Trả tiền? |
|---|---|---|---|---|
| Gen Z Việt Nam theo trào lưu "công thức màu" | Thấy creator đăng công thức trên Threads, TikTok | Khi thấy một công thức đẹp, tôi muốn quét QR hoặc dán chữ là có đúng màu đó trên ảnh của mình, để đăng ảnh cùng "vibe" | Ảnh đã chỉnh; công thức lưu trong thư viện | Phần lớn không; một phần mua trọn đời khi giá khoảng 199–263 nghìn |
| Người chơi máy ảnh (có hoặc không có máy Fujifilm, Ricoh…), US, SG, AU, JP | Đọc blog công thức, chụp bằng cả điện thoại và máy ảnh | Khi đọc một công thức trên blog, tôi muốn áp nó lên ảnh điện thoại và ảnh máy khác, để cả feed đồng màu | Công thức tham số, ảnh xuất đủ độ phân giải, RAW | Có: toàn bộ thư viện, RAW, hàng loạt |
| Người đã mua preset hoặc LUT | Có gói DNG/XMP từ Gumroad, Etsy, hoặc "mua chung preset 50k" trên Voz | Khi có gói preset đã mua, tôi muốn dùng ngay trên Android mà không cần Lightroom Premium, để khỏi mua lại | Look trong thư viện, báo cáo nhập | Nhập là miễn phí; trả cho hàng loạt, RAW |
| Creator công thức và preset (VN, ID) | Đăng công thức, bán gói preset ngoài store | Khi đăng công thức, tôi muốn có thẻ đẹp với QR và một trang web để follower dùng ngay, và về sau bán được gói | Thẻ công thức, trang công khai, gói creator (V2) | Nhận tiền (V2) |
| Người làm video ngắn | Đã có màu ảnh ưng ý, muốn dùng cho clip | Khi đã có màu ưng ý, tôi muốn xuất .cube, để dùng trong CapCut desktop, VN, Resolve hay FilCam | File .cube 33/65, HALD, `.flook` | Có (xuất LUT là Pro) |
| Người chụp du lịch, sự kiện nhỏ | 50–100 ảnh một chuyến đi | Khi về nhà, tôi muốn áp một công thức cho cả lô và tự cân sáng từng ảnh, để đăng album trong vài phút | Lô ảnh cùng màu | Có (hàng loạt là Pro) |

Bằng chứng về nhu cầu lấy từ [ghi chú cảm nhận người dùng](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/user_sentiment_pain_points.md): người dùng VSCO Việt Nam xin "lưu công thức dưới dạng mã QR"; Voz có các chủ đề "Chia sẻ presets Lightroom" và "50k mua chung presets Lightroom"; một đánh giá Lightroom khen tính năng chép thiết lập để "cả nhóm ảnh trông đồng đều" có 1.103 lượt hữu ích; người dùng Dehancer xin chỉnh hàng loạt và gói trọn đời. Trên Gumroad, "lightroom presets" có 4.607 sản phẩm, trong đó 2.474 dạng DNG và 456 dạng XMP ([ghi chú preset và LUT](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/preset_lut_editor_apps.md)).

## 4. Định vị và đối thủ

**Câu định vị:** công thức màu film cho ảnh điện thoại trên Android, chia sẻ bằng QR, nhập được preset đã mua, xuất được LUT, mua đứt được.

Số liệu lấy từ báo cáo (Bảng 3, 4, 6) và [ghi chú preset và LUT](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/preset_lut_editor_apps.md), kéo ngày 27/9/2026. ST là ước tính Sensor Tower (lượt tải / doanh thu tháng gần nhất).

| App | Trọng tâm | Lượt cài Play; điểm (số đánh giá) | iOS: đánh giá ở Mỹ; ST iOS/tháng | Giá | Điểm yếu mình khai thác | Khác biệt của Studio |
|---|---|---|---|---|---|---|
| [Fimii](https://play.google.com/store/apps/details?id=com.ankii.fimii&hl=en&gl=VN) (indie VN) | Preset film tự dựng, RAW 16-bit, bánh xe màu, match ảnh mẫu, xuất hàng loạt | 8.736; 4,89 ở VN (229) | 24 (VN: 865); 10k / < $5k | $9.99 trọn đời (263.000 ₫ trên Play VN) | Không có mô hình công thức tham số, không có thẻ QR hay xuất LUT (theo mô tả store) | Công thức kiểu máy ảnh, QR, dán chữ, nhập zip/DNG, xuất .cube, liên thông Filmode/FilCam |
| [FujiStyle](https://play.google.com/store/apps/details?id=com.fujistylelead.global&hl=en&gl=US) | Công thức kiểu Fuji và khung | 21.872; 4,40 (632) | 363; < 5k / $10k | $3.99/tháng, $9.99/quý, $14.99/năm | Chỉ thuê bao; tên gắn nhãn hiệu Fuji | Trọn đời $19.99; tên tự đặt |
| [Fuji X Weekly](https://play.google.com/store/apps/details?id=com.fujixweekly.FujiXWeekly&hl=en&gl=US) | 400+ công thức cho máy Fujifilm, gửi công thức sang máy qua USB-C | 407.926; 4,44 (875) | —; — | Miễn phí, Patron $19.99/năm | Công thức chỉ để cài lên máy Fujifilm, không sửa ảnh điện thoại | Áp công thức lên mọi ảnh; parser đọc bài dạng chữ |
| [VSCO](https://play.google.com/store/apps/details?id=com.vsco.cam&hl=en&gl=US) | Preset, Recipes, cộng đồng | 164,5 triệu; 3,62 (1,33M) | 277.508; 400k / $2M | Plus $39.99/năm, Pro $69.99/năm; VN 799.000 ₫/năm | Lượt tìm VN còn 0,10 lần; 67% đánh giá mẫu là 1–2★, 29% vì paywall, 21% vì đăng nhập | Không tài khoản, Free không bao giờ bị thu hẹp, giá VN 149.000 ₫/năm |
| [Afterlight](https://play.google.com/store/apps/details?id=com.fueled.afterlight&hl=en&gl=US) | 300+ preset film | 11,4 triệu; 2,71 (60,8K) | 20.664; < 5k / $20k | $15.99–23.99/năm; trọn đời $19.99–39.99 | Điểm Play thấp; tên preset mang tên phim | Android làm tốt; tên tự đặt |
| [Koloro](https://play.google.com/store/apps/details?id=com.cerdillac.persetforlightroom&hl=en&gl=US) | 1000+ preset, công thức QR, xuất DNG cho Lightroom | 40,2 triệu; 4,80 (431K) | 2.335; n/a | $17.99/năm; $21.99 một lần; có quảng cáo | Bản Play ngừng cập nhật từ 27/6/2024 | Được cập nhật; không quảng cáo; nhập ngược DNG/XMP |
| [Lightroom](https://play.google.com/store/apps/details?id=com.adobe.lrmobile&hl=en&gl=US) | Trình sửa toàn diện, preset cộng đồng | 470,9 triệu; 4,47 (3,66M) | 336.826; 1M / $5M | $19.99/năm (40 GB) đến $49.99/năm; VN 469.000 ₫/năm | Masking, RAW máy khác là Premium; 33% lời chê là paywall | Mở preset DNG/XMP không cần Premium; công thức một chạm |

Đối thủ khác cần biết:
- **Darkroom, RNI Films, Dehancer** (giả lập film cao cấp) chỉ có trên iOS, mỗi app ước thu $20–30k/tháng (ST). Đây là khoảng trống Android mà Studio nhắm tới, và là đối thủ trực tiếp khi Studio lên iOS.
- **Snapseed** miễn phí hoàn toàn và đã có film simulation, halation, bloom, grain, chỉnh hàng loạt và RAW ([App Store](https://apps.apple.com/us/app/id439438619)). Studio không cạnh tranh bằng công cụ, mà bằng công thức, chia sẻ QR, nhập preset và xuất LUT.
- **FLTR** (30 triệu lượt cài) và các thư viện preset Lightroom khác sống bằng quảng cáo và không vào top grossing nào. Preset đã thành hàng phổ thông; giá trị nằm ở cách tuyển chọn, chia sẻ và quy trình.
- **Panasonic LUMIX Lab** miễn phí, lưu bản chỉnh thành LUT và có "Magic LUT" tạo LUT từ ảnh mẫu bằng AI. Nhà sản xuất máy ảnh đang cho không hệ sinh thái công thức cho người dùng của họ.

**Không làm:** tuyên bố "giống hệt" một loại phim hay một máy ảnh cụ thể; dùng tên phim hay nhãn hiệu trong tên công thức, tiêu đề hay ảnh chụp màn hình; đóng gói LUT CC BY-SA (RawTherapee, G'MIC); sinh ảnh bằng AI (AI chỉ dùng cho màu và mask, như báo cáo khuyến nghị).

## 5. Tính năng chi tiết

Mỗi mục trỏ về epic trong [epics-features.md](epics-features.md). Gói của từng tính năng ở mục 6.

### 5.1 Trình chỉnh sửa film (FMS-E01)

Trình sửa không phá hủy ảnh gốc. Trạng thái sửa của một ảnh là một `look.json` (định dạng chung của lõi, [filmode-core.md mục 5](../filmode-core.md#5-định-dạng-look-flook-v1)) cộng khối `x-fms` chứa phần chỉ thuộc về ảnh đó: vùng cắt, mask, tham chiếu ảnh gốc. Nhờ vậy "lưu thành công thức" chỉ là bỏ khối `x-fms` riêng của ảnh đi.

- **Preview:** ảnh proxy cạnh dài ≤ 2048 px render bằng `:core:gpu`; zoom 1:1 thì render tile đủ độ phân giải cho vùng đang xem. Preview và ảnh xuất dùng chung shader và seed grain, nên lệch ΔE trung bình < 2.
- **Công cụ Free:** phơi sáng, nhiệt độ, tint, tương phản, vùng sáng, vùng tối, bão hòa, fade, cường độ look, đường cong tổng, grain (độ mạnh, kích thước), vignette, halation mức sẵn, cắt xoay, undo/redo, trước/sau, bản sao ảo.
- **Công cụ Pro:** đường cong từng kênh, HSL 8 dải, bánh xe màu 3 vùng, tách tông, grain nâng cao (độ thô, hạt màu), bloom, quang sai màu, halation chỉnh sâu. Người dùng miễn phí dùng thử được; paywall chỉ hiện khi lưu hoặc xuất.
- **Bake vào LUT:** đường cong, HSL và bánh xe màu không có trường riêng trong `look.json`, nên khi lưu thì gộp với LUT tông nền thành một `lut.cube` 33³ bằng pipeline CPU của lõi. Look có LUT riêng không chia sẻ được bằng QR (giới hạn 600 ký tự của codec), mà phải gửi file `.flook` hoặc link cloud. App nói rõ điều này khi người dùng chia sẻ.
- **RAW (V1, Pro):** DNG và ProRAW dạng .dng trước, RAW máy ảnh (CR3, NEF, ARW, RAF, ORF, RW2) sau. Spike FMS-E01-12 chọn giữa `ImageDecoder` của Android (Skia, chỉ DNG ⚠) và LibRaw qua NDK (giấy phép LGPL-2.1 hoặc CDDL ⚠). Xử lý 16-bit bằng texture RGBA16F; WB theo Kelvin áp trước LUT.

### 5.2 Công thức màu (FMS-E02)

**Công thức là gì.** Một công thức là một look không có LUT riêng: tông nền tham chiếu bằng `base.ref`, cộng các tham số `adjust`, `grain`, `halation`, `vignette`. Vì không có LUT riêng nên công thức vừa QR (payload thường 150–300 ký tự) và mở được trong cả ba app. Giá trị theo thang máy ảnh (ví dụ "Vùng tối +2", "Dải động 400") giữ trong `x-fms.recipe` để Studio hiện đúng nấc và in lên thẻ. App khác bỏ qua khối này nhưng vẫn render đúng nhờ các trường chuẩn.

**Bảng ánh xạ tham số.** Hệ số đổi nấc (cột "Trường `look.json`") là giá trị khởi đầu, chốt lại sau spike FMS-E02-02 ⚠. Tên tham số trên app là tên tự đặt; cột "Khóa trong công thức gốc" chỉ dùng cho parser (mục dưới).

| # | Tham số trên app | Thang | Khóa trong công thức gốc | Trường `look.json` | Pass GPU | Ghi chú |
|---|---|---|---|---|---|---|
| 1 | Tông nền | 16 lựa chọn (bảng dưới) | Film Simulation | `base.ref = "fm:base/<slug>@<rev>"` | LUT 3D 33³: trilinear khi preview, tetrahedral khi xuất | Quyết định đường cong và bảng màu. Tông nền dùng chung ba app (FLC-E02-11) |
| 2 | Hạt: độ mạnh | Tắt / Nhẹ / Mạnh | Grain Effect (Off/Weak/Strong) | `grain.amount` 0 / 0,22 / 0,40 | Pass grain (FLC-E01-12) | Grain mạnh ở vùng trung tính, gần như không có ở bóng sâu và vùng cháy |
| 3 | Hạt: kích thước | Nhỏ / Lớn | Grain size (Small/Large) | `grain.size` 1,0 / 1,8; `grain.roughness` 0,5 / 0,7 | Pass grain | `size` tính ở ảnh chuẩn 12 MP; seed theo ảnh để preview giống ảnh xuất |
| 4 | Độ sâu màu | Tắt / Nhẹ / Mạnh | Color Chrome Effect | `adjust.colorDepth` 0 / 0,5 / 1 (trường mới, FLC-E01-27) | Pass `adjust`: giảm độ sáng theo trọng số độ bão hòa, trước LUT | Màu đậm (đỏ, cam, xanh lá) có chiều sâu hơn, không bị bệt |
| 5 | Độ sâu xanh lam | Tắt / Nhẹ / Mạnh | Color Chrome FX Blue | `adjust.colorDepthBlue` 0 / 0,5 / 1 (trường mới, FLC-E01-27) | Pass `adjust`: như trên, mask theo sắc độ khoảng 200–260° | Trời và nước xanh đậm hơn |
| 6 | Kiểu cân bằng trắng | Tự động, Nắng, Râm, Đèn sợi đốt, Huỳnh quang, Kelvin 2500–10000 K | White Balance | `adjust.temperature`, `adjust.tint` (dịch tương đối); RAW dùng Kelvin tuyệt đối trong `x-fms.recipe.wbKelvin` | Pass `adjust`: ma trận 3×3 trước LUT | Ảnh JPEG đã được máy cân trắng, nên chỉ dịch tương đối so với 5500 K ⚠ |
| 7 | Lệch cân bằng trắng | Đỏ −9…+9, Xanh lam −9…+9 | WB Shift R/B | `adjust.wbShift {r, b}` (đúng thang) | Pass `adjust`: nhân kênh R và B trước LUT | Hiện bằng lưới 19×19 như trên máy ảnh |
| 8 | Dải động | 100 / 200 / 400 | Dynamic Range (DR100/200/400) | `adjust.toneRange` 0 / 0,5 / 1 (trường mới, FLC-E01-27) | Pass `adjust`: vai mềm ở vùng sáng, giữ chi tiết mây và da sáng | Không đổi phơi sáng chung |
| 9 | Vùng sáng | −2…+4 | Highlight (Tone) | `adjust.highlights` = nấc × 18 | Pass `adjust` | Dương là vùng sáng sáng hơn, cứng hơn |
| 10 | Vùng tối | −2…+4 | Shadow (Tone) | `adjust.shadows` = nấc × −18 | Pass `adjust` | Dương là vùng tối sâu hơn, nên đổi dấu |
| 11 | Màu | −4…+4 | Color | `adjust.saturation` = nấc × 12 | Pass `adjust` | |
| 12 | Độ nét | −4…+4 | Sharpness | `adjust.sharpness` = nấc × 15 | Pass `adjust` (unsharp mask rẻ) | |
| 13 | Độ trong | −5…+5 | Clarity | `adjust.clarity` = nấc × 12 | Pass `adjust` (tương phản cục bộ trên ảnh thu nhỏ) | |
| 14 | Giảm nhiễu | −4…+4 | High ISO NR | Chỉ lưu ở `x-fms.recipe.nr` | Không render | Ảnh điện thoại đã được khử nhiễu. Giữ để thẻ đủ thông số và để người dùng máy ảnh cài lại đúng |
| 15 | Bù sáng gợi ý | −3…+3 EV | Exposure Compensation | `adjust.exposure` | Pass `adjust` | Công thức gốc thường ghi khoảng ("+1/3 đến +1"); lấy giữa khoảng |
| + | Cường độ, hạt màu, halation, vignette | 0–1 | (không có trong công thức máy ảnh) | `intensity`, `grain.chroma`, `halation`, `vignette` | Các pass tương ứng của lõi | Tùy chọn thêm của Studio |

ISO và các dòng khác trong công thức gốc (ví dụ "ISO: Auto up to 6400") không có ý nghĩa với ảnh đã chụp, nên chỉ ghi vào ghi chú của công thức.

Thứ tự pass do lõi cố định (FLC-E01-11): `adjust` (WB và lệch WB → phơi sáng → dải động → vùng sáng/tối → độ sâu màu → bão hòa → độ nét, độ trong) → LUT tông nền (hoặc LUT đã bake) → halation, bloom → grain → vignette, CA → khung. Giữ tông da (5.5) trộn ảnh gốc và ảnh có look theo mask sau cùng.

**16 tông nền.** LUT 33³ do đội tự dựng từ ColorChecker và ramp xám, manifest nguồn gốc `owned` (FLC-E04-03). Tên và mô tả không nhắc tên phim hay máy ảnh nào. Tên tiếng Anh "Classic Negative" và "Nostalgic Negative" gần với tên chế độ màu của một hãng máy ảnh ⚠: rà nhãn hiệu trước khi chốt, nếu là nhãn hiệu thì đổi tên và thêm vào `NameGuard` (FLC-E04-02).

| Slug | Tên (VI) | Tên (EN) | Phong cách |
|---|---|---|---|
| `std` | Chuẩn | Standard | Màu trung tính, tương phản vừa; điểm xuất phát |
| `slide-vivid` | Slide rực | Vivid Slide | Phim dương bản bão hòa cao, trời xanh đậm, tương phản cao |
| `slide-soft` | Slide dịu | Soft Slide | Dương bản bão hòa vừa, da mềm, hợp chân dung ngoài trời |
| `doc-muted` | Phóng sự trầm | Muted Documentary | Màu trầm, xanh lá ngả ô liu, vùng tối cứng, kiểu ảnh tạp chí cũ |
| `doc-warm` | Phóng sự ấm | Warm Documentary | Như trên nhưng vùng sáng ngả vàng |
| `neg-portrait` | Âm bản chân dung | Portrait Negative | Da ấm hồng, tương phản thấp, vùng sáng mềm |
| `neg-portrait-hi` | Âm bản chân dung đậm | Portrait Negative Hi | Như trên, tương phản cao hơn cho ánh sáng phẳng |
| `neg-classic` | Âm bản cổ điển | Classic Negative | Vùng tối ngả lục lam, đỏ trầm, bão hòa thấp, kiểu cuộn phim phổ thông thập niên 90 |
| `neg-nostalgic` | Âm bản hoài niệm | Nostalgic Negative | Vùng sáng hổ phách, vùng tối mềm, kiểu ảnh gia đình thập niên 70 |
| `neg-consumer` | Âm bản phổ thông ấm | Warm Consumer Negative | Vàng ấm, bão hòa vừa, kiểu cuộn phim ISO 200 phổ thông |
| `neg-natural` | Âm bản tự nhiên | Natural Negative | Màu trung thực, xanh lá tươi, da sạch |
| `cine-soft` | Điện ảnh mềm | Soft Cinema | Tương phản rất thấp, bão hòa thấp, vùng tối ngả xanh |
| `cine-bleach` | Điện ảnh tẩy bạc | Bleach Cinema | Bão hòa thấp, tương phản cao, ánh bạc |
| `mono` | Đơn sắc | Mono | Đen trắng tương phản vừa, dải xám mịn |
| `mono-hard` | Đơn sắc cứng | Hard Mono | Đen trắng tương phản cao, trời tối như dùng kính lọc đỏ |
| `sepia` | Nâu cổ | Sepia | Một màu nâu ấm |

**20 công thức miễn phí.** Ghi trong `free-tier.json`, không bao giờ chuyển sang Pro. Tham số viết tắt: H = hạt, ĐSM = độ sâu màu, ĐSX = độ sâu xanh lam, WB = lệch cân bằng trắng, DR = dải động, S/T = vùng sáng/vùng tối, M = màu, N = độ nét, Tr = độ trong, EV = bù sáng. Nấc cụ thể chốt khi dựng nội dung.

| # | Tên (VI) | Tên (EN) | Nhóm | Tông nền | Tham số chính | Hợp với |
|---|---|---|---|---|---|---|
| 1 | Nắng Vàng | Golden Sun | Máy phim | `neg-consumer` | H nhẹ nhỏ; WB R+3 B−4; DR200; S−1 T+1; M+2 | Nắng, du lịch |
| 2 | Phố Cũ | Old Street | Máy phim | `doc-muted` | H mạnh nhỏ; ĐSM mạnh; WB R+2 B−5; S−1 T+2; M−2 | Phố, kiến trúc |
| 3 | Slide Lạnh | Cool Slide | Máy phim | `slide-vivid` | H nhẹ; WB R−1 B+2; DR100; T+1; M+3 | Biển, trời |
| 4 | Âm Bản Mát | Cool Negative | Máy phim | `neg-classic` | H mạnh nhỏ; WB R−2 B+1; DR400; S−2 T+1; M+1 | Phố, hoàng hôn |
| 5 | Hoài Niệm | Nostalgia | Máy phim | `neg-nostalgic` | H nhẹ lớn; WB R+4 B−6; S−1 T−1 | Gia đình, kỷ niệm |
| 6 | Hạt Đen Trắng | Grain Mono | Đen trắng | `mono-hard` | H mạnh lớn; S+1 T+3; N+1 | Đường phố, đêm |
| 7 | Bỏ Túi 2003 | Pocket 2003 | Compact | `std` | Không hạt; WB R−3 B+3; M+3; N+3; Tr+2 | Bạn bè, đi chơi |
| 8 | Flash Tiệc | Party Flash | Compact | `slide-vivid` | H nhẹ; EV −0,3; S+2 T+2; M+2; vignette nhẹ | Tiệc tối |
| 9 | Cuộn Dùng Một Lần | One-Time Roll | Compact | `neg-consumer` | H mạnh lớn; WB R+2 B−2; S+1 T−1; N−2; vignette | Ngày thường |
| 10 | Chiều Điện Ảnh | Cine Dusk | Điện ảnh | `cine-soft` | H nhẹ; WB R+1 B−3; DR400; S−2 T−1; M−1; halation nhẹ | Hoàng hôn |
| 11 | Tẩy Bạc | Silver Bleach | Điện ảnh | `cine-bleach` | H mạnh nhỏ; S+1 T+2; M−3; Tr+3 | Đô thị |
| 12 | Đêm Neon | Neon Night | Điện ảnh | `cine-soft` | H mạnh; WB R−2 B+4; ĐSX mạnh; S−1 T+1; M+2; halation | Đêm, đèn đường |
| 13 | Da Mật | Honey Skin | Chân dung | `neg-portrait` | H nhẹ nhỏ; WB R+2 B−3; S−1 T−1; N−1 | Chân dung |
| 14 | Chân Dung Mềm | Soft Portrait | Chân dung | `slide-soft` | Không hạt; DR200; S−2 T−2; M−1; Tr−2 | Chân dung, cưới |
| 15 | Trong Veo | Clear Day | Chân dung | `neg-natural` | H nhẹ; M+1 | Ngoài trời |
| 16 | Biển Trưa | Noon Sea | Cảnh | `slide-vivid` | H nhẹ; WB R−1 B+1; DR400; S−1; M+2; ĐSX mạnh | Biển |
| 17 | Quán Ấm | Warm Café | Cảnh | `neg-consumer` | H mạnh; WB R+3 B−5; EV +0,7; T−1; M+1 | Quán cà phê, trong nhà |
| 18 | Mưa Phố | Rainy Street | Cảnh | `doc-muted` | H nhẹ; WB R−2 B+2; S−1 T+2; M−2 | Ngày mưa |
| 19 | Lá Xanh | Green Leaves | Cảnh | `neg-natural` | H nhẹ; ĐSM nhẹ; WB R+1 B−1; M+2 | Cây, công viên |
| 20 | Nâu Cổ | Old Sepia | Đen trắng | `sepia` | H mạnh lớn; S−1 T+1; vignette | Kỷ niệm |

**Thư viện Pro.** Ít nhất 60 công thức lúc ra mắt, thêm khoảng 40 ở V1 (tổng khoảng 100). Bộ sưu tập theo mùa nằm trong Pro và cũng bán lẻ cho người không có Pro (IAP).

| Nhóm | MVP | Thêm ở V1 | Ví dụ tên tự đặt |
|---|---|---|---|
| Máy phim mở rộng (âm bản, dương bản, phim đời cũ) | 15 | 10 | Cuộn 400 Ấm, Slide Sáng Sớm, Phố Cảng |
| Compact và digicam | 10 | 6 | Bỏ Túi Xanh, Flash 2006, Pin Yếu |
| Điện ảnh | 10 | 6 | Rạp Khuya, Chiều Lục Lam, Phim Nhựa |
| Chân dung và da | 10 | 6 | Má Hồng, Nắng Tóc, Da Sữa |
| Đen trắng | 8 | 4 | Than Chì, Báo Sáng, Mực Tàu |
| Cảnh (đêm, trong nhà, biển, đồ ăn, du lịch) | 7 | 8 | Chợ Đêm, Bàn Ăn, Ga Tàu |
| Theo mùa: Hè, Mùa cưới, Trung thu, Noel, Tết Nguyên đán | — | 6–8 mỗi bộ | Hè Muối, Áo Dài Đỏ, Đèn Lồng |
| **Tổng** | **60** | **khoảng 40 + bộ theo mùa** | |

**Dán công thức dạng chữ (V1, FMS-E02-10, -11).** Người dùng dán hoặc chia sẻ một bài viết sang Studio; parser nhận tham số, người dùng xác nhận từng dòng. Parser chỉ lấy tham số, không lưu hay tải văn bản gốc lên đâu, vì phần viết của tác giả công thức có bản quyền ([ghi chú khả thi](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/tech_feasibility_opportunities.md), Q7).

Ba dạng đầu vào phải đọc được (ví dụ do đội tự viết theo khuôn phổ biến, không chép nguyên văn):

```
Film Simulation: Classic Negative
Grain Effect: Strong, Small
Color Chrome Effect: Strong
Color Chrome FX Blue: Weak
White Balance: Daylight, +3 Red & -5 Blue
Dynamic Range: DR400
Highlight: -1
Shadow: +2
Color: +3
Sharpness: -2
High ISO NR: -4
Clarity: -2
ISO: Auto, up to ISO 6400
Exposure Compensation: +1/3 to +2/3 (typically)
```

```
Công thức màu "Sài Gòn chiều" 🌇
- Film sim: Nostalgic Neg
- DR: 400 | Grain: yếu, nhỏ
- CCE: mạnh · CCFxB: tắt
- WB: Auto, R +4, B -6
- Highlight -1, Shadow -1
- Color +2 / Sharp -1 / NR -4 / Clarity 0
- Bù sáng +1/3
```

```
Eterna, DR400, Hi -2 Sh -2, Col -2, WB 5500K R+1 B-3, grain weak small
```

Parser phải xử lý:
- **Khóa và từ đồng nghĩa (EN, VI, viết tắt):** Film Simulation / Film sim / FS; Grain Effect / Grain / Hạt; Color Chrome Effect / CCE / Độ sâu màu; Color Chrome FX Blue / CCFxB / CC Blue; White Balance / WB / Cân bằng trắng; WB Shift; Dynamic Range / DR / Dải động; Highlight / H / Hi / Vùng sáng; Shadow / S / Sh / Vùng tối; Color / Col / Màu; Sharpness / Sharp / Độ nét; High ISO NR / NR / Giảm nhiễu; Clarity / Độ trong; Exposure Compensation / EV / Bù sáng; ISO; Tone Curve (dạng "H-1 S+2").
- **Giá trị:** số có dấu (+2, −1, "-1" với dấu trừ Unicode), phân số (+1/3, +2/3), khoảng ("+1/3 to +1" lấy giữa), chữ (Off/Weak/Strong, Small/Large, tắt/yếu/nhẹ/mạnh, nhỏ/lớn), Kelvin ("5500K"), DR ("DR400", "400%", "DR-Auto" → 200).
- **Lệch WB:** "+3 Red & -5 Blue", "R+3 B-5", "R: +3, B: -5", "(+3R, -5B)", "Red 3, Blue -5".
- **Tên kiểu nền:** bảng map nội bộ từ tên phổ biến sang 16 tông nền (ví dụ "Classic Negative" → `neg-classic`, "Nostalgic Neg" → `neg-nostalgic`, "Eterna" → `cine-soft`). Bảng map là dữ liệu nhận đầu vào, không bao giờ hiện trên UI; UI chỉ hiện tên tự đặt ("Âm bản cổ điển"). Lint tên của lõi cho phép riêng file này qua danh sách ngoại lệ có lý do (FLC-E04-03).
- **Định dạng:** gạch đầu dòng, emoji, dấu `|`, `·`, `/`, dấu hai chấm toàn khổ, có dấu hoặc không dấu ("do net"), nhiều tham số trên một dòng, dòng tiêu đề đầu bài làm tên công thức (qua `NameGuard` trước khi chia sẻ).
- **Đầu ra:** công thức kèm độ tin cậy từng dòng, danh sách dòng chưa nhận; không đoán giá trị cho dòng không hiểu. Mục tiêu ≥ 95% trường đúng trên bộ 60 bài mẫu.

**Thẻ công thức và QR (FMS-E02-07, -08).** Thẻ 1080×1350 (4:5, cho feed) hoặc 1080×1920 (9:16, cho story):
- Nửa trên: ảnh mẫu đã áp công thức (tùy chọn chia đôi trước/sau).
- Tên công thức (chữ lớn nhất), tác giả `@handle`.
- Bảng hai cột 7–9 dòng theo thang công thức: tông nền, hạt, độ sâu màu, WB và lệch WB, dải động, vùng sáng/tối, màu, độ nét, độ trong, giảm nhiễu, bù sáng.
- QR ở góc dưới phải, cạnh ≥ 28% chiều rộng thẻ (khoảng 300 px ở 1080), vùng trắng 4 module, mức sửa lỗi M; payload thường cho QR phiên bản 8–13 ⚠. Mục tiêu: quét được sau khi ảnh bị Zalo và Messenger nén.
- Dòng chữ nhỏ "Quét bằng Filmode Studio · filmode.app"; từ V1 thêm mã chữ 8 ký tự khi công thức có link cloud.
- Ba bố cục: Tạp chí, Tối giản, Cuộn phim (viền có số khung). Ảnh thẻ xuất ra không có GPS.
- Đọc QR không cần quyền camera: quét từ ảnh chụp màn hình (ML Kit ⚠) hoặc Google code scanner ⚠; người chưa cài app quét bằng camera điện thoại thì mở trang `/r` của lõi (FLC-E02-08) có nút tải app.

### 5.3 Nhập preset và LUT (FMS-E03)

Một màn nhập nhận nhiều file hoặc một zip, từ trình chọn file hay từ share sheet (Zalo, Messenger, Drive). Bộ nhập là của lõi: .cube 17/33/65 và preset kiểu Lightroom (FLC-E01-04), HALD, .3dl, zip (FLC-E01-05), .xmp và preset .dng (FLC-E01-08). Studio thêm:
- **Báo cáo:** từng file thành công hay lỗi, lý do, phần không chuyển được (làm nét, khử nhiễu, mask, lens profile, dehaze). XMP → LUT là bản gần đúng; app nói rõ điều này.
- **Gói đã mua:** giải nén một cấp zip lồng, bỏ rác (`__MACOSX`, PDF, ảnh hướng dẫn), gom vào thư mục tên gói. File .dng là ảnh RAW thì mở trong trình sửa thay vì báo lỗi.
- **Bảo vệ LUT của người khác:** look nhập được gắn `license: personal`. Look này chỉ dùng riêng: chia sẻ chỉ gửi được phần công thức, không công khai, không xuất .cube. Lõi chặn thêm ở server (FLC-E08-03).
- **Thư viện:** thư mục, thẻ, yêu thích, tìm kiếm; lưới xem trước mọi look trên chính ảnh của người dùng; từ V1 thấy cả look lưu trong Filmode và FilCam trên cùng máy.

### 5.4 Sao chép màu từ ảnh mẫu (FMS-E04)

**Match v1 (MVP).** Luồng:
1. Trong trình sửa, bấm "Sao chép màu" và chọn ảnh mẫu qua Photo Picker.
2. Cắt vùng mẫu để bỏ viền, chữ, logo. Ảnh mẫu đen trắng hoặc gần như một màu thì app cảnh báo.
3. Thuật toán của lõi (FLC-E01-18) tính trung bình và độ lệch chuẩn trong không gian Lab của ảnh mẫu và ảnh đích (ảnh thu nhỏ khoảng 512 px), khớp phân phối tích lũy (CDF) từng kênh, giới hạn độ lệch ở vùng xám trung tính và vùng da, rồi bake thành LUT 33³ trong < 500 ms.
4. Preview ngay trên ảnh đang sửa, có thanh cường độ. Áp cho ảnh này và xuất ảnh là miễn phí.
5. "Lưu thành look" để dùng lại, áp cho lô, chia sẻ hay xuất .cube là Pro.

**Tinh chỉnh (V1, Pro):** khóa độ sáng (chỉ chuyển màu, giữ L*), độ mạnh riêng cho tone và cho màu, giữ tông da bằng mask người.

**Match v2 bằng AI (V2, Pro, 🧪).** Mô hình dự đoán LUT từ một ảnh mẫu, chạy trên máy bằng LiteRT, suy luận một lần mỗi ảnh mẫu rồi LUT chạy trên pipeline GPU thường. Hai hướng có mã công khai: Neural Preset (CVPR 2023, mã trên GitHub) và Deep Analog (arXiv 2608.14702, 8/2026, chưa ghi giấy phép) ([ghi chú khả thi](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/tech_feasibility_opportunities.md), Q5). Spike FMS-E04-04 rà giấy phép của cả mã lẫn trọng số ⚠. Nếu không dùng thương mại được thì đội tự huấn luyện trên look tự sở hữu và ảnh CC0 (FMS-E04-05). Ảnh không bao giờ gửi lên server. Máy yếu hoặc lỗi thì tự lùi về v1.

### 5.5 Mặt nạ và tông da (FMS-E05)

- **Giữ tông da (V1, Pro):** mask người của lõi (FLC-E01-22) tính một lần mỗi ảnh ở cạnh ≤ 512 px, phóng lên có feather, rồi trộn ảnh gốc với ảnh có look trong vùng da. Mục tiêu: da lệch ảnh gốc ΔE < 3 khi áp look đỏ mạnh, không viền sáng quanh tóc. GPU delegate trả mask rỗng thì lõi tự chuyển CPU. Người dùng xem và sửa mask bằng cọ.
- **Chỉnh cục bộ (V2, Pro):** mask bầu trời (sau spike chọn mô hình ⚠), cọ vẽ, vùng tròn và vùng chuyển, đảo và cộng trừ mask. Mask là của ảnh, lưu trong `x-fms`, không đi theo công thức chia sẻ.

### 5.6 Hàng loạt và feed (FMS-E06)

- **Sao chép/dán thiết lập (V1, Free):** chọn nhóm (công thức, màu, film, crop) rồi dán cho nhiều ảnh.
- **Áp hàng loạt (V1, Pro):** tới 100 ảnh, xuất nền bằng WorkManager foreground qua hàng đợi lưu bền của lõi, tiếp tục được sau khi app bị kill.
- **Chuẩn hóa phơi sáng từng ảnh (Pro).** Một công thức áp lên ảnh sáng tối khác nhau thì feed vẫn lệch. Thuật toán:
  1. Với mỗi ảnh, tạo proxy 256 px, tính độ sáng Y (Rec.709) và lấy trung vị sau khi bỏ 1% điểm tối nhất và sáng nhất.
  2. Chọn đích: trung vị của cả lô (mặc định) hoặc trung vị của một ảnh chuẩn người dùng chọn.
  3. ΔEV = log2(đích / trung vị ảnh), giới hạn ±1,5 EV; cộng vào `adjust.exposure` của bản sửa từng ảnh (không đổi công thức gốc).
  4. Tùy chọn cân WB bằng gray-world có giới hạn (tối đa ±5 nấc `temperature`), bỏ qua ảnh có màu chủ đạo mạnh (hoàng hôn, đèn neon).
  5. Người dùng khóa được ảnh không muốn chuẩn hóa (ví dụ cảnh đêm cố ý tối) và sửa riêng từng ảnh trên lưới trước/sau.
  Mục tiêu: lô lệch sáng 2 EV còn lệch trung vị ≤ 0,3 EV sau chuẩn hóa.
- **Lưới feed 3×3 (V1, Free):** xem 9–30 ảnh như trang cá nhân, kéo đổi thứ tự, đánh dấu ảnh lệch màu so với lô.

### 5.7 Xuất (FMS-E07)

Xuất JPEG, HEIF, PNG đủ độ phân giải, **không watermark, kể cả ở gói Free**. Giữ EXIF gốc, thêm thẻ `Software`, xóa GPS khi chia sẻ (mặc định bật). Ảnh gốc Ultra HDR thì xuất Ultra HDR (FLC-E06-04). Gửi look dạng file `.flook` qua Zalo, Messenger không cần mạng (Free). Xuất .cube 33/65 và HALD cho CapCut desktop, VN, DaVinci Resolve, Blackmagic Camera (V1, Pro); app liệt kê hiệu ứng không đi theo LUT (grain, halation, vignette). Nút "Dùng trong máy ảnh Filmode" và "Dùng khi quay FilCam" mở thẳng look trong app anh em (V1).

### 5.8 Cộng đồng và trang công thức công khai (FMS-E08)

- **Link và mã chữ (V1):** công thức có LUT riêng không vừa QR thì tải lên API look của lõi (FLC-E08-03) và nhận link `filmode.app/l/<id>`; `id` 8 ký tự cũng là mã chữ để đọc qua điện thoại hay gõ vào app.
- **Công khai công thức (V1):** người dùng chọn 2–4 ảnh mẫu, mô tả, thẻ, xác nhận ảnh là của mình. Đây là việc duy nhất ở V1 cần đăng nhập (Google, tùy chọn). Server xóa EXIF ảnh mẫu, chạy `NameGuard`, giới hạn tần suất.
- **Trang web cho SEO (V1).** "Công thức màu" trên Google Việt Nam còn 0,39 lần và lẫn với công thức màu nhuộm tóc; chỉ "công thức màu fujifilm" là ý định chụp ảnh ([ghi chú từ khóa](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/keyword_search_demand.md)). Vì vậy trang luôn ghép "công thức màu" với "film":
  - URL: `filmode.app/cong-thuc/<slug>` (vi) và `filmode.app/recipes/<slug>` (en), `hreflang` qua lại, canonical, sitemap.
  - Tiêu đề: "Công thức màu film <Tên> – chỉnh màu film cho ảnh điện thoại | Filmode Studio"; mô tả meta nêu 3 tham số chính.
  - Nội dung: ảnh trước/sau, bảng tham số theo thang, "Hợp với cảnh…", QR và nút mở app hoặc tải app, công thức liên quan, "Remix từ…" (V2).
  - Trang danh mục theo phong cách (máy phim, compact, điện ảnh, chân dung, đen trắng) và theo cảnh (nắng, đêm, trong nhà, biển).
  - JSON-LD (`CreativeWork`, `BreadcrumbList`) ⚠ loại schema chốt khi làm; LCP < 2,5 giây trên 4G.
  - Không dùng nhãn hiệu trong tiêu đề trang. Nhắc "đọc được công thức viết cho máy ảnh Fujifilm" trong thân bài chỉ khi đã rà pháp lý ⚠.
- **Khám phá, hồ sơ, remix, kiểm duyệt (V2):** thịnh hành theo lượt lưu 7 ngày, theo dõi creator, remix có ghi tên (`remixOf`), báo cáo và chặn người dùng, hàng chờ duyệt, quy trình thông báo và gỡ trong 72 giờ ⚠, lọc ảnh nhạy cảm trước khi công khai. Phần này cũng để đáp ứng quy định nội dung người dùng tạo của Play và App Store (guideline 1.2 ⚠).

### 5.9 Chợ look của creator (FMS-E09, V2–V3)

Mô hình theo Hàn Quốc: filmhwa (mua một lần $2.99) và Berryfilm ($1.99) là app filter mang tên influencer, đứng #62 và #59 top grossing iOS Hàn Quốc; trên Etsy, bộ preset bán chạy bán được hàng nghìn đến hàng chục nghìn bản, mỗi bản khoảng $1–5 ([báo cáo](../../../reports/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u.md), mục App 2). Mọi mục dưới đây là đề xuất, phải qua spike FMS-E09-01 và rà pháp lý ⚠.

- **Chỉ bán qua IAP.** Gói creator là sản phẩm một lần trên Play và App Store, đội là người bán. Không có link mua ngoài app. SKU tạo sẵn theo bậc giá ($1.99, $2.99, $3.99; VN khoảng 49.000–99.000 ₫ ⚠), gán gói ↔ SKU trên server để thêm gói không cần phát hành app. Gói creator **không** nằm trong Studio Pro.
- **Chia doanh thu.** Đề xuất creator nhận 50% doanh thu thực nhận (sau phí store 15% và thuế store thu hộ) ⚠. Ví dụ gói $2.99 ở Mỹ: store giữ khoảng $0.45, đội nhận khoảng $2.54, creator khoảng $1.27 trước thuế. Hoàn tiền trừ ngược vào phần của creator.
- **Chi trả.** Hằng tháng, sau 45 ngày chờ hoàn tiền; ngưỡng tối thiểu khoảng 500.000 ₫ hoặc $20 ⚠. Creator Việt Nam nhận chuyển khoản ngân hàng; creator nước ngoài qua Wise hoặc PayPal ⚠. Với cá nhân cư trú Việt Nam, đội có thể phải khấu trừ thuế TNCN (tham khảo mức 10% cho khoản chi từ 2 triệu đồng trở lên mỗi lần ⚠ cần xác minh), cấp chứng từ khấu trừ, và cần mã số thuế của creator. Việc Play và Apple cho phép chia doanh thu IAP với bên thứ ba ngoài store cần xác minh theo chính sách Payments của Play và guideline 3.1.1, 3.2 của Apple ⚠.
- **Kiểm duyệt trước khi bán.** Server kiểm định dạng, chạy `NameGuard` trên tên gói, tên look, mô tả, thẻ; so checksum LUT với các bộ HaldCLUT công khai (RawTherapee, G'MIC) và với gói đã có để chặn bán lại LUT của người khác; creator khai quyền sở hữu và cam kết trong thỏa thuận. Người duyệt xem ảnh mẫu (không logo máy ảnh hay bao phim).
- **Gỡ và khiếu nại.** Gỡ gói khỏi cửa hàng khi có khiếu nại hợp lệ; người đã mua **giữ quyền** (cam kết không thu hồi); phần chi trả của gói bị giữ trong lúc tranh chấp.
- **Bảo vệ gói đã mua.** Server chỉ cấp URL tải có hạn sau khi xác minh giao dịch (FLC-E03-10). Look trong gói gắn `license: personal`, không chia sẻ lại LUT, không xuất .cube; chia sẻ chỉ gửi link tới trang gói.
- **Bảng điều khiển creator (web):** doanh số theo ngày và nước, lượt dùng gộp ẩn danh (dưới 10 thì hiện "< 10"), số dư, lịch sử chi trả, chứng từ.
- **Gói mang thương hiệu creator (V3):** trang `filmode.app/c/<handle>`, màn chào mang tên creator, bộ look cập nhật hằng tháng, mã quà tặng.

### 5.10 Onboarding và hướng dẫn (FMS-E11)

Lần mở đầu có 3 bước: chọn ảnh (hoặc dùng 3 ảnh mẫu có sẵn) → áp một công thức → lưu. Không có paywall chặn và không bắt tài khoản. V1 thêm 3 câu hỏi phong cách (ấm hay lạnh, tương phản, hạt), gợi ý công thức theo cảnh bằng nhận diện trên máy (ML Kit Image Labeling ⚠), và bài hướng dẫn song ngữ "làm màu film X trên điện thoại" có nút "Thử công thức này".

### 5.11 iOS (FMS-E12)

Bản iOS dựng trên `FilmodeCoreKit` (V1 của lõi). Filmode iOS đã có trình sửa, Match Photo và bộ nhập .xmp; spike FMS-E12-02 quyết định phần nào dùng lại ⚠. Bản iOS đầu gồm mọi tính năng MVP của Android, cộng RAW qua `CIRAWFilter` và dán công thức dạng chữ. Lô, tông da (Vision), xuất LUT, cộng đồng và chợ creator trên iOS là V2. Công thức, QR và `.flook` giống hệt Android nhờ bộ fixture chung.

## 6. Free, Pro và IAP

Nguyên tắc theo Bảng 11 và lõi: nhập preset/LUT là miễn phí vì đó là mức tối thiểu của thị trường; mọi thứ Free nằm trong `free-tier.json` và không bao giờ chuyển sang Pro (FLC-E03-04); không quảng cáo, không watermark; người dùng miễn phí thử được công cụ và công thức Pro, paywall chỉ hiện khi lưu hoặc xuất.

| Tính năng | Free | Pro | IAP | Bản |
|---|---|---|---|---|
| Trình sửa không phá hủy, undo, trước/sau, bản sao ảo, cắt xoay | ✓ | ✓ | | MVP |
| Màu cơ bản, đường cong tổng, grain, vignette, halation mức sẵn | ✓ | ✓ | | MVP |
| HSL, đường cong từng kênh, bánh xe màu, tách tông, grain nâng cao, bloom, CA | Thử | ✓ | | MVP |
| 16 tông nền, màn chỉnh công thức, lưu công thức của mình | ✓ | ✓ | | MVP |
| 20 công thức dựng sẵn | ✓ | ✓ | | MVP |
| Thư viện Pro (60 lúc ra mắt, khoảng 100 ở V1) | Thử | ✓ | | MVP |
| Bộ sưu tập theo mùa và gói công thức của đội ($1.99–3.99) | Thử | ✓ (có sẵn) | ✓ | V1 |
| Gói creator | Thử | — (mua riêng) | ✓ | V2 |
| Nhập .cube, .3dl, HALD, .xmp, .dng, zip; báo cáo nhập; thư viện | ✓ | ✓ | | MVP |
| Dán công thức dạng chữ | ✓ | ✓ | | V1 |
| Thẻ công thức QR, đọc QR, gửi `.flook` | ✓ | ✓ | | MVP |
| Link cloud, mã chữ, công khai công thức, trang web | ✓ | ✓ | | V1 |
| Khám phá, theo dõi, remix | ✓ | ✓ | | V2 |
| Match v1: áp cho ảnh đang sửa và xuất ảnh | ✓ | ✓ | | MVP |
| Lưu match thành look; tinh chỉnh sau match | | ✓ | | MVP; V1 |
| Match v2 bằng AI | | ✓ | | V2 |
| Giữ tông da | | ✓ | | V1 |
| Mask bầu trời, cọ, vùng tròn và vùng chuyển | | ✓ | | V2 |
| Sao chép/dán thiết lập, lưới feed 3×3 | ✓ | ✓ | | V1 |
| Áp hàng loạt có chuẩn hóa phơi sáng | | ✓ | | V1 |
| Xuất ảnh đủ độ phân giải, không watermark, Ultra HDR, giữ EXIF, xóa GPS | ✓ | ✓ | | MVP |
| RAW (DNG, ProRAW, RAW máy ảnh), xuất 16-bit | | ✓ | | V1 |
| Xuất .cube 33/65, HALD | | ✓ | | V1 |
| Mở look trong Filmode, FilCam | ✓ | ✓ | | V1 |

"Thử" nghĩa là xem trước trên ảnh của mình được, nhưng lưu hoặc xuất thì cần mua.

## 7. Giá

Giá là đề xuất của báo cáo (Bảng 8), cần thử A/B sau ra mắt (FMS-E10-05). Không có gói tháng: Bảng 8 chỉ có trọn đời và năm, và gói trọn đời là giá neo.

| Gói | Mỹ | Việt Nam | Ghi chú |
|---|---|---|---|
| Studio Pro trọn đời | **$19.99** | **229.000 ₫** (thử 199.000 ₫ và 263.000 ₫) | Đặt nổi bật trên Android. Ngang Afterlight ($19.99–39.99), Koloro ($21.99); cao hơn Fimii ($9.99, 263.000 ₫ trên Play VN) vì có RAW, lô, xuất LUT, QR |
| Studio Pro năm | $14.99 (dùng thử 7 ngày ⚠) | 149.000 ₫ | Ngang FujiStyle ($14.99/năm); rẻ hơn nhiều VSCO (799.000 ₫/năm) và Lightroom (469.000 ₫/năm) ở VN |
| Gói công thức của đội | $1.99–3.99 | 49.000–99.000 ₫ ⚠ | Người có Pro đã có sẵn |
| Gói creator | $1.99 / $2.99 / $3.99 | 49.000–99.000 ₫ ⚠ | Không nằm trong Pro; chia doanh thu với creator (V2) |

Giá ID, TH, PH, BR, IN đặt khoảng 40–50% giá Mỹ qua bảng giá vùng của lõi (FLC-E03-08) ⚠. Giá VN theo mức 40–50% giá Mỹ như Bảng 8, khớp cách Dazz và ProCCD định giá ở Việt Nam. Theo ghi chú kiếm tiền, sau phí 15% của Play, một gói trọn đời $19.99 cho đội khoảng $17 trước thuế thu nhập tại Việt Nam; Google thu hộ 5% VAT trên giao dịch của người mua Việt Nam ([ghi chú kiếm tiền](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/monetization_paid_features.md)).

Paywall theo [checklist của lõi](../filmode-core.md#43-checklist-paywall): số tiền thực là chữ lớn nhất ("229.000 ₫ một lần", "149.000 ₫/năm"), điều khoản dùng thử có ngày, cách hủy bằng tiếng Việt và tiếng Anh, nút đóng thấy ngay, liệt kê rõ những gì vẫn miễn phí.

## 8. Phạm vi theo bản

Chi tiết từng feature ở [epics-features.md](epics-features.md). Số ngày là ngày công dev, chưa gồm thiết kế UI, dịch thuật, nội dung (khoảng 54 ngày nội dung, xem [Nội dung](epics-features.md#nội-dung)) và rà soát pháp lý.

| Bản | Thời gian | Ngày công | Nội dung chính |
|---|---|---|---|
| **MVP** (Android) | 4/1 – cuối 3/2027 | 68 (Android 62; CI, QA 6) | Trình sửa không phá hủy, preview GPU, công cụ màu Free và Pro, mô phỏng film; mô hình công thức, 16 tông nền, 20 công thức Free, 60 Pro; thẻ QR, đọc QR từ ảnh; nhập .cube/.3dl/HALD/.xmp/.dng/zip có báo cáo, bảo vệ LUT người khác; Match v1; xuất đủ độ phân giải, Ultra HDR, `.flook`; SKU, gói Free cố định, paywall; onboarding; golden, ma trận máy, beta kín |
| **V1** | Q2/2027 | 95,5 (Android 50,5; web và backend 8; iOS 37) | Android: dán công thức dạng chữ, bộ theo mùa, gói lẻ, thử giá, hàng loạt và chuẩn hóa phơi sáng, lưới feed, link và mã chữ, công khai công thức và trang SEO, xuất LUT, mở trong Filmode/FilCam, giữ tông da, tinh chỉnh match, gợi ý theo cảnh, hướng dẫn, RAW. **iOS 1.0** với mọi tính năng MVP cộng RAW và dán công thức |
| **V2** | Nửa cuối 2027, khi đạt tiêu chí "đẩy mạnh" | 78,5 (Android 36,5; web và backend 23; công cụ 5; iOS 14) | Khám phá, hồ sơ, remix, kiểm duyệt; chợ creator (SKU, duyệt gói, cửa hàng, sổ doanh thu, chi trả, bảng điều khiển); mask cục bộ; Match v2 bằng AI; iOS: lô, tông da, xuất LUT, cộng đồng, cửa hàng creator |
| **V3** | 2028 | 4 | Gói mang thương hiệu creator, trang creator, mã quà tặng |
| **Tổng** | | **246** | 106 feature |

## 9. ASO

Trên store, từ khóa đầu là "film camera", "film filter", "preset"; các từ chuyên như "film simulation", "lut", "grain" gần như không có gợi ý tự động ([ghi chú từ khóa](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/keyword_search_demand.md)). Với "fuji film filter", FujiStyle chỉ có hơn 10 nghìn lượt cài mà vẫn đứng đầu Play Mỹ, nghĩa là trường này còn mỏng. Chưa có số lượt tìm tuyệt đối; nên thuê một công cụ ASO trả phí một tháng trước khi chốt metadata, như báo cáo khuyên.

| Thị trường | Tiêu đề (≤ 30) | Mô tả ngắn Play (≤ 80) / phụ đề iOS (≤ 30) | Từ khóa chính |
|---|---|---|---|
| EN (US, SG, AU) | Filmode Studio: Film Recipes (28) | "Film recipes & film filters: grain, halation, LUT & XMP import. No ads." (71) / "Film recipes, grain & LUTs" (26) | film recipes, film simulation ⚠, film filter, film presets, film grain, recipe card, cube lut, xmp presets, analog |
| VI | Filmode Studio: Công thức màu (29) | "Công thức màu film, preset màu film, nhập LUT .cube và XMP. Không quảng cáo" (75) / "Công thức màu film và LUT" (25) | công thức màu film, preset màu film, chỉnh màu film, màu film, ảnh film, lut màu, hạt film |
| JA | Filmode Studio: フィルムレシピ (23) | Viết khi dịch | フィルムレシピ, フィルム風, フィルムシミュレーション ⚠ |
| ID | Filmode Studio: Resep Film (26) | "Resep film & preset: grain, LUT .cube dan XMP. Tanpa iklan, tanpa watermark" (75) | resep film, preset film, filter film, kamera film |

Trường từ khóa iOS (100 ký tự), bản EN: `film,recipe,simulation,filter,preset,grain,lut,cube,xmp,dng,analog,vintage,halation,qr,raw,batch` (96).

Quy tắc:
- Không có Fujifilm, Fuji, Kodak, Portra, VSCO, Lightroom trong tiêu đề, mô tả ngắn, từ khóa iOS, ảnh chụp màn hình và tên công thức (chính sách nhãn hiệu của Play; `NameGuard` và lint của lõi chặn). "Film Simulation" là thuật ngữ sản phẩm của Fujifilm; có phải nhãn hiệu đăng ký hay không cần xác minh trước khi đưa vào tiêu đề ⚠. Mô tả dài có thể nói "đọc được công thức viết cho máy ảnh" và "nhập preset XMP và DNG" mà không gọi tên hãng.
- "Công thức màu" đứng một mình trên Google bị lẫn với màu nhuộm tóc và đang giảm (0,39 lần); luôn ghép với "film". Người Việt tìm app trong store nhiều hơn trên Google, nên chọn từ theo gợi ý tự động và thứ hạng trong store.
- Ảnh chụp màn hình đầu tiên là thẻ công thức có QR, ảnh thứ hai là trước/sau, ảnh thứ ba là màn nhập zip preset.
- Kênh ngoài store: creator "công thức màu" trên Threads, TikTok, Instagram (bài ProCCD của @congthucmau đạt khoảng 50,5 nghìn lượt xem); trang công thức công khai (FMS-E08-04) cho từ khóa dài "công thức màu film <phong cách>".

## 10. KPI và tiêu chí quyết định

Ngưỡng có nguồn lấy từ RevenueCat qua báo cáo (Bảng 7); ngưỡng "nội bộ" là mục tiêu đội tự đặt ⚠. Đo bằng phễu của lõi (FLC-E05-07) và sự kiện riêng của Studio (FMS-E10-04).

| KPI (8 tuần sau ra mắt Android) | Ngưỡng | Nguồn ngưỡng | Cách đo |
|---|---|---|---|
| Phiên có lưu hoặc xuất ít nhất một ảnh | ≥ 40% | Nội bộ | `edit_open` → `save` |
| Người dùng tạo ít nhất một thẻ công thức trong 30 ngày | ≥ 10% người dùng hoạt động | Nội bộ | `recipe_card_create` |
| Lượt mở công thức từ QR hoặc link | ≥ 500 mỗi tuần vào tuần 8 | Nội bộ; Bảng 13 đo "số công thức được chia sẻ" | `qr_open` |
| Tải → trả tiền sau 35 ngày | ≥ 0,9% Android; ≥ 2,6% iOS (khi có) | RevenueCat, mọi danh mục | Play Console, App Store Connect |
| Doanh thu mỗi lượt cài sau 60 ngày | ≥ $0,04 ở VN/ĐNA, ≥ $0,16 ở Mỹ (Android) | RevenueCat | Play Console theo nước |
| Dùng thử → trả tiền (gói năm) | ≥ 17,1% Android | RevenueCat, Photo & Video trên Play | Play Console |
| Thứ hạng | Top 10 Play VN cho "công thức màu film" hoặc "preset màu film"; top 20 Play Mỹ cho "film recipes" | Nội bộ; Bảng 13 đo thứ hạng "công thức màu fujifilm" | Theo dõi tay hằng tuần hoặc công cụ ASO |
| Ổn định | Crash dưới 1,09%, ANR dưới 0,47% (ngưỡng Play Vitals ⚠); không có báo lỗi "không lưu được ảnh" | Lõi mục 4.2 | Play Console |

**Quyết định sau 8 tuần** (theo cách của báo cáo: mốc thành công đầu tiên là $1K/tháng cộng một vị trí top từ khóa ở Việt Nam):
- **Đẩy mạnh** khi đạt cả ba: doanh thu mỗi lượt cài đạt ngưỡng ở VN; ≥ 500 lượt mở QR mỗi tuần; vào top 10 cho một từ khóa VN. Làm tiếp: giữ lịch iOS, làm đủ V1, chuẩn bị V2 (cộng đồng trước, chợ creator sau).
- **Sửa** khi đạt một hoặc hai: thử A/B giá (199.000 ₫ và 263.000 ₫), paywall, ảnh chụp màn hình và tiêu đề; làm V1 đến hết S10 rồi dừng lại xem số.
- **Dừng đầu tư thêm** (chỉ bảo trì, không làm V2) khi sau hai vòng ASO và một vòng thử giá mà doanh thu mỗi lượt cài vẫn dưới 50% ngưỡng và lượt mở QR dưới 100 mỗi tuần.

**Điều kiện mở chợ creator (V2):** doanh thu Studio ≥ $1K/tháng (gộp hai nền tảng) trong 2 tháng liên tiếp; ≥ 1.000 công thức công khai; ≥ 30 creator có công thức được lưu nhiều đăng ký chờ bán; spike FMS-E09-01 và rà pháp lý xong ⚠.

## 11. Rủi ro chính

| Rủi ro | Ảnh hưởng | Cách xử lý |
|---|---|---|
| Nhãn hiệu trong tên công thức, tên tông nền, metadata (Kodak, Portra, Fujifilm, Classic Chrome, Velvia…). Kodak đã đổi Portra thành "Ektacolor Pro" 3/2026; Play cấm dùng nhãn hiệu gây nhầm lẫn | App bị gỡ, listing bị từ chối | Tên tự đặt cho mọi thứ; `NameGuard` trong app và server (FLC-E04-02, FLC-E08-03); lint CI (FLC-E04-03); bảng map tên kiểu nền của parser chỉ nhận đầu vào, không hiện trên UI ⚠ |
| Người dùng nhập gói preset/LUT trả phí (Gumroad, Etsy, "mua chung" trên Voz) rồi phát tán lại qua app | Khiếu nại bản quyền, gỡ app | Look nhập mang `license: personal`: chỉ chia sẻ phần công thức, không công khai, không xuất .cube (FMS-E03-05); server chặn (FLC-E08-03); quy trình gỡ theo khiếu nại (FMS-E08-08); không bao giờ lưu LUT của người khác trên server |
| Văn bản công thức trên blog có bản quyền của tác giả | Khiếu nại từ tác giả công thức | Parser chỉ lấy tham số, không lưu hay tải văn bản gốc; trang công khai chỉ hiện tham số và ảnh của người đăng |
| LUT mã nguồn mở share-alike (RawTherapee CC BY-SA, G'MIC CeCILL) lọt vào gói của đội hoặc gói creator | Phải mở giấy phép cho LUT của mình, hoặc vi phạm | Tông nền và công thức tự dựng có manifest `owned`; lint so checksum HaldCLUT công khai (FLC-E04-03, FMS-E09-03) |
| Giấy phép mô hình AI (Neural Preset, Deep Analog chưa ghi giấy phép), mô hình mask bầu trời, LibRaw (LGPL-2.1 hoặc CDDL) | Không dùng thương mại được, hoặc phải công bố mã | Spike giấy phép trước khi code (FMS-E04-04, FMS-E05-03, FMS-E01-12); phương án tự huấn luyện (FMS-E04-05); LibRaw liên kết động nếu dùng LGPL ⚠ |
| Chợ creator: chính sách store về chia doanh thu ngoài store, thuế TNCN khi trả cho cá nhân VN, chi trả ra nước ngoài, hoàn tiền và gian lận | Bị store từ chối, sai thuế, lỗ vì hoàn tiền | Chỉ bán qua IAP; spike luồng tiền và rà pháp lý (FMS-E09-01); giữ 45 ngày; khấu trừ thuế và chứng từ; chỉ mở khi đạt điều kiện ở mục 10 |
| Apple 4.3 coi Studio là biến thể của Filmode iOS (cùng có trình sửa, Match Photo, nhập .xmp) | Studio iOS bị từ chối | Tính năng riêng rõ (công thức, QR, parser, RAW máy ảnh, xuất LUT, cộng đồng); quy tắc ranh giới ở mục 2: Filmode giữ vai máy ảnh + chỉnh nhanh, giữ tính năng cũ nhưng không thêm chỉnh sâu mới, có nút "Mở trong Filmode Studio"; ghi chú App Review (FMS-E12-14) |
| Studio và Filmode tranh nhau người dùng và doanh thu | Doanh thu mỗi app thấp | Mỗi app một bộ từ khóa; Filmode đẩy người cần chỉnh sâu sang Studio; look đi lại giữa hai app nhờ định dạng chung |
| Fimii đã chiếm "preset" ở VN với giá 263.000 ₫ trọn đời; Snapseed miễn phí có film simulation, halation, RAW | Khó chuyển đổi ở VN | Cạnh tranh bằng công thức và QR, nhập preset, xuất LUT, gói Free rộng; thử giá 199.000 ₫ |
| Công thức quét QR trong Filmode hoặc FilCam ra màu khác Studio | Mất niềm tin vào vòng lặp chia sẻ | FLC-E01-27, FLC-E01-28 và FLC-E02-11 xong trước S2 (18/1/2027); golden test QR round-trip (FMS-E13-02) |
| MVP phụ thuộc mục `V1` của lõi (FLC-E01-27, -28, FLC-E02-11, bộ nhập, deep link, Ultra HDR) và Match v1 (FLC-E01-18) nằm trong cut-line của lõi | Trễ ra mắt Q1/2027 | Lõi giao theo hạn từng sprint FMS ([lõi mục 8](../filmode-core.md#8-lộ-trình)); nếu cắt FLC-E01-18 khỏi MVP của Filmode thì vẫn giao trước FMS S5 (1/3/2027); dev D làm FLC-E01-27, -28 trong S1–S2 |
| Ảnh 50–200 MP và RAW trên máy Android tầm trung (bộ nhớ, thời gian) | OOM, đánh giá 1★ | Render theo tile (FLC-E01-15); ma trận máy (FMS-E13-03); RAW là V1 sau spike |
| Số liệu thị trường: chưa có lượt tìm tuyệt đối, doanh thu là ước tính Sensor Tower, bảng xếp hạng là ảnh chụp một ngày | Chọn sai tiêu đề hoặc sai thị trường | Thuê công cụ ASO một tháng; thử nghiệm listing trên Play; quyết định theo KPI mục 10 |

## 12. Liên kết

- [README chung](../README.md), [lõi Filmode Core](../filmode-core.md), [backlog lõi](../filmode-core-backlog.csv)
- [Báo cáo "Lõi LUT của Filmode đủ nuôi ba app"](../../../reports/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u.md): mục "App 2 — Filmode Studio", Bảng 1, 3, 4, 6, 7, 8, 11, 13 và phần rủi ro
- Ghi chú nghiên cứu trong `research_notes/App camera film và LUT màu/`: [preset_lut_editor_apps.md](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/preset_lut_editor_apps.md), [user_sentiment_pain_points.md](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/user_sentiment_pain_points.md), [monetization_paid_features.md](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/monetization_paid_features.md), [keyword_search_demand.md](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/keyword_search_demand.md), [tech_feasibility_opportunities.md](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/tech_feasibility_opportunities.md), [film_camera_apps.md](../../../research_notes/App%20camera%20film%20v%C3%A0%20LUT%20m%C3%A0u/film_camera_apps.md)
