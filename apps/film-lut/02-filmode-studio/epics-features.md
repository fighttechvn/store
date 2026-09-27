# Epic và feature · Filmode Studio (`FMS`)

Quy ước ID, ưu tiên, gói, ước tính và dấu ⚠ / 🧪 theo [README chung](../README.md). Tổng quan sản phẩm, mô hình công thức, danh mục công thức khởi đầu, giá và KPI ở [README của Studio](README.md). Bản CSV: [backlog.csv](backlog.csv).

Ước tính là ngày công của 1 dev Android có kinh nghiệm (dev iOS cho `FMS-E12`), đã gồm unit test. **Không gồm** thiết kế UI, dịch thuật, dựng nội dung (tông nền, công thức, ảnh mẫu, bài hướng dẫn) và rà soát pháp lý; phần nội dung ước riêng ở mục [Nội dung](#nội-dung).

Feature của lõi (`FLC-…`) chỉ được tham chiếu trong cột "Phụ thuộc", không làm lại ở đây. Studio không phụ thuộc feature của Filmode (`FMD`) hay FilCam (`FCM`). Khi Studio cần lõi thay đổi, yêu cầu nằm ở mục [Điều chỉnh lõi](#điều-chỉnh-lõi).

Module Android: `:app:studio` là app shell; module tính năng là `:studio:editor`, `:studio:raw`, `:studio:recipe`, `:studio:import`, `:studio:match`, `:studio:mask`, `:studio:batch`, `:studio:export`, `:studio:community`, `:studio:market`, `:studio:onboarding`. Module `:studio:*` chỉ phụ thuộc `:core:*`, không phụ thuộc nhau vòng tròn. iOS: target `StudioiOS/<Area>` trên `FilmodeCoreKit`. `(backend)` và `(web)` là phần server và trang web tĩnh dựng trên hạ tầng chung FLC-E08.

Mọi thứ Studio làm với ảnh chạy trên máy. Ảnh chỉ rời máy khi người dùng tự công khai công thức kèm ảnh mẫu (FMS-E08-02). Studio không xin quyền `CAMERA` hay `READ_MEDIA_*`.

## Tổng quan epic

| ID | Epic | ↔ Báo cáo | Mục tiêu | Module | Feature | MVP (ngày) | Tổng (ngày) |
|---|---|---|---|---|---|---|---|
| FMS-E01 | Trình chỉnh sửa film | B1 | Sửa ảnh không phá hủy, preview giống ảnh xuất, đủ công cụ màu và mô phỏng film; RAW ở V1 | `:app:studio`, `:studio:editor`, `:studio:raw` | 14 | 22,5 | 33 |
| FMS-E02 | Công thức màu | B2 | Công thức tham số kiểu máy ảnh, tên tự đặt, thư viện 20 Free + Pro, thẻ QR; dán công thức dạng chữ ở V1 | `:studio:recipe` | 11 | 16 | 22,5 |
| FMS-E03 | Nhập preset và LUT đã có | B3 | Nhập được mọi gói preset/LUT người dùng đã mua (.cube, .3dl, HALD, .xmp, .dng, zip), có báo cáo, và không làm lộ LUT của người khác | `:studio:import` | 7 | 7,5 | 9 |
| FMS-E04 | Sao chép màu từ ảnh mẫu | B4 | Match v1 miễn phí cho ảnh đang sửa, lưu thành look là Pro; tinh chỉnh ở V1; Match v2 bằng AI chạy trên máy ở V2 sau khi rà giấy phép | `:studio:match`, `(tools)` | 6 | 3,5 | 19 |
| FMS-E05 | Mặt nạ và tông da | B5 | Giữ màu da khi áp look mạnh (V1); mask bầu trời, cọ và vùng chuyển (V2) | `:studio:mask` | 6 | 0 | 15 |
| FMS-E06 | Hàng loạt và feed | B6 | Cả một feed có chung một look: dán thiết lập, áp hàng loạt có chuẩn hóa phơi sáng, lưới 3×3 | `:studio:batch` | 4 | 0 | 10 |
| FMS-E07 | Xuất | B7 | Xuất ảnh đủ độ phân giải không watermark; xuất look .cube/HALD và mở thẳng trong Filmode, FilCam | `:studio:export` | 6 | 4,5 | 8 |
| FMS-E08 | Cộng đồng | B8 | Chia sẻ bằng link và mã chữ; trang công thức công khai để lên Google; khám phá, remix, kiểm duyệt ở V2 | `:studio:community`, `(backend)`, `(web)` | 8 | 0 | 24,5 |
| FMS-E09 | Chợ look của creator | B9 | Creator bán gói look qua IAP, đội chia doanh thu và chi trả ngoài store; gói mang thương hiệu creator ở V3 | `:studio:market`, `(backend)`, `(web)` | 10 | 0 | 31 |
| FMS-E10 | Kiếm tiền | B10 | Gói Free cố định, Studio Pro trọn đời và năm, gói lẻ; paywall đúng checklist lõi | `:app:studio`, `:studio:market` | 6 | 5 | 8 |
| FMS-E11 | Onboarding và hướng dẫn | B11 | Người mới lưu được ảnh đẹp đầu tiên trong vòng một phút; gợi ý công thức theo phong cách và cảnh; bài hướng dẫn song ngữ | `:studio:onboarding` | 3 | 1,5 | 7,5 |
| FMS-E12 | iOS Studio | mới (Bảng 13: iOS Q2/2027) | Ra Studio trên iOS khoảng một quý sau Android, dựng trên `FilmodeCoreKit` và dùng lại trình sửa, Match Photo, bộ nhập .xmp của Filmode iOS khi được | `StudioiOS/*`, `(qa)` | 20 | 0 | 51 |
| FMS-E13 | Chất lượng và phát hành | mới | Phát hành Studio Android đúng hạn, không lệch màu giữa preview và ảnh xuất, qua được Play và beta kín | `(ci)`, `(qa)`, `:app:studio` | 5 | 7,5 | 7,5 |
| | **Tổng** | | | | **106** | **68** | **246** |

`FMS-E01`…`FMS-E11` khớp 1:1 với B1–B11 của Bảng 11. Hai epic thêm:
- **FMS-E12 iOS Studio.** Bảng 13 đặt bản iOS ở Q2/2027, dựng từ trình sửa, Match Photo và bộ nhập .xmp của Filmode iOS. Gom thành một epic để thấy khối lượng của dev iOS và các phụ thuộc vào lõi iOS.
- **FMS-E13 Chất lượng và phát hành.** Phần kiểm thử và phát hành riêng của Studio (golden cho tông nền và công thức, ảnh 50–200 MP, beta kín). Tách riêng để không bị cắt khi trễ hạn.

### Chia theo nền tảng

| Nền tảng | Feature | MVP | V1 | V2 | V3 | Tổng (ngày) |
|---|---|---|---|---|---|---|
| Android | 72 | 62 | 50,5 | 36,5 | 4 | 153 |
| iOS | 20 | 0 | 37 | 14 | 0 | 51 |
| Web, backend | 9 | 0 | 8 | 23 | 0 | 31 |
| Công cụ, QA, CI | 5 | 6 | 0 | 5 | 0 | 11 |
| **Tổng** | **106** | **68** | **95,5** | **78,5** | **4** | **246** |

"Công cụ, QA, CI" không gồm `(qa)` của iOS (FMS-E12-14, tính vào iOS).

## FMS-E01 · Trình chỉnh sửa film

Mục tiêu: sửa ảnh không phá hủy, preview giống ảnh xuất, đủ công cụ màu và mô phỏng film; RAW ở V1.

Ánh xạ Bảng 11: B1.1 → 02, 03 · B1.2 → 05–08 · B1.3 → 09, 10 · B1.4 → 12–14. Thêm: 01 (khung app), 04 (preview), 11 (cắt xoay).

Gói theo Bảng 11 là "Free một phần/Pro", nên công cụ màu và mô phỏng film tách hai dòng: phần Free (05, 06, 09) và phần Pro (07, 10). Người dùng miễn phí vẫn xem trước công cụ Pro; paywall chỉ hiện khi lưu hoặc xuất.

Trình sửa của Filmode Vibe có thể dùng lại một phần ⚠ (chưa rõ code viết bằng gì). Ước tính ở đây giả định viết mới trên `:core:gpu`.

Khối lượng: 14 feature · MVP 22,5 ngày · V1 10,5 ngày · tổng **33 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FMS-E01-01 | `:app:studio` | Khung app Studio: package `app.filmode.studio` ⚠, điều hướng Compose (Ảnh → Trình sửa → Xuất), theme riêng trên design system lõi, chọn ngôn ngữ trong app, album `Pictures/Filmode Studio`, cổng nhận deep link | — | MVP | 1,5 | FLC-E07-01; FLC-E07-06; FLC-E04-01 | Khi build `:app:studio` thì ra AAB riêng với package `app.filmode.studio`; khi đổi ngôn ngữ trong app sang tiếng Việt thì mọi màn Studio đổi ngay; khi bật TalkBack thì đọc được mọi nút ở màn chính |
| FMS-E01-02 | `:studio:editor` | Phiên sửa không phá hủy (B1.1): mở ảnh qua Photo Picker, giữ URI gốc; trạng thái sửa là `look.json` cộng khối `x-fms` (crop, mask, tham chiếu ảnh gốc); tự lưu nháp vào Room, mở lại đúng chỗ | Free | MVP | 2,5 | FLC-E06-01; FLC-E01-01; FMS-E01-01 | Khi sửa ảnh rồi kill app thì mở lại thấy đúng mọi thanh trượt; khi xuất ảnh thì file gốc trong thư viện không đổi byte nào; khi ảnh gốc đã bị xóa khỏi máy thì bản nháp báo "Không tìm thấy ảnh gốc" và không crash |
| FMS-E01-03 | `:studio:editor` | Lịch sử thao tác (undo/redo 50 bước), so sánh trước/sau (giữ để xem ảnh gốc, thanh chia đôi kéo được), bản sao ảo cho cùng một ảnh gốc | Free | MVP | 2 | FMS-E01-02; FLC-E01-17 | Khi làm 60 thao tác rồi undo thì quay lại được 50 bước gần nhất; khi tạo 3 bản sao ảo thì mỗi bản giữ thiết lập riêng và chỉ tốn thêm dung lượng JSON, không nhân bản ảnh |
| FMS-E01-04 | `:studio:editor` | Preview GPU của trình sửa: ảnh proxy cạnh dài ≤ 2048 px cho màn chính; khi zoom 1:1 thì render tile đủ độ phân giải cho vùng đang xem; chất lượng pass theo tier máy | Free | MVP | 2,5 | FLC-E01-11; FLC-E01-15; FLC-E05-04 | Khi kéo thanh trượt trên ảnh 50 MP ở máy tầm trung chuẩn thì preview ≥ 30 fps; khi zoom 1:1 thì vùng đang xem hiện chi tiết đủ độ phân giải < 500 ms; khi so preview với ảnh xuất thì ΔE trung bình < 2 |
| FMS-E01-05 | `:studio:editor` | Công cụ màu cơ bản (B1.2, phần Free): phơi sáng, nhiệt độ, tint, tương phản, vùng sáng, vùng tối, bão hòa, fade, cường độ look; ghi thẳng vào `adjust` và `intensity` | Free | MVP | 1,5 | FMS-E01-04 | Khi mọi thanh trượt về 0 thì ảnh ra trùng ảnh vào (ảnh 8-bit); khi lưu rồi mở công thức đó trong Filmode thì các giá trị `adjust` giống hệt |
| FMS-E01-06 | `:studio:editor` | Đường cong tone tổng (RGB), tối đa 16 điểm; bake vào LUT 33³ bằng pipeline CPU của lõi khi lưu | Free | MVP | 2 | FMS-E01-05; FLC-E01-06 | Khi đặt đường cong chữ S rồi lưu thì look có `lut.cube` 33³ và render lệch preview ΔE trung bình < 1; khi đường cong là đường thẳng thì không sinh `lut.cube` |
| FMS-E01-07 | `:studio:editor` | Công cụ màu Pro (B1.2): đường cong từng kênh R/G/B, HSL 8 dải màu (sắc độ, bão hòa, độ sáng), bánh xe màu 3 vùng (tối, trung, sáng), tách tông; bake chung vào LUT 33³ | Pro | MVP | 4,5 | FMS-E01-06 | Khi kéo bão hòa dải xanh lá về −100 thì chỉ vùng lá cây mất màu, vùng da không đổi (ΔE < 2); khi người dùng miễn phí dùng HSL thì xem trước được, paywall chỉ hiện lúc lưu hoặc xuất |
| FMS-E01-08 | `:studio:editor` | Bake chỉnh sửa màu thành look: có đường cong, HSL hoặc bánh xe màu thì gộp với LUT tông nền thành một `lut.cube`; không có thì giữ công thức thuần tham số (`base.ref`) để còn chia sẻ bằng QR | — | MVP | 1,5 | FMS-E01-07; FLC-E01-02 | Khi công thức chỉ dùng thanh trượt `adjust` và tông nền thì look lưu ra không có `lut.cube` và tạo được QR; khi có HSL thì look có `lut.cube`, app chuyển sang chia sẻ file hoặc link và nói rõ lý do |
| FMS-E01-09 | `:studio:editor` | Mô phỏng film phần Free (B1.3): grain (độ mạnh, kích thước), vignette, halation mức có sẵn; dùng pass của lõi | Free | MVP | 1,5 | FLC-E01-12; FLC-E01-13; FMS-E01-04 | Khi bật grain rồi xuất cùng ảnh hai lần thì hai file giống hệt từng bit; khi so vùng trời ở preview và ảnh xuất thu về cùng cỡ thì SSIM ≥ 0,95 |
| FMS-E01-10 | `:studio:editor` | Mô phỏng film phần Pro: grain nâng cao (độ thô, hạt màu, kiểu đáp ứng), bloom, quang sai màu, halation chỉnh bán kính, ngưỡng và màu | Pro | MVP | 1 | FMS-E01-09 | Khi đổi màu halation sang cam thì quầng quanh đèn đổi màu ở cả preview và ảnh xuất; khi người dùng miễn phí thử thì xem trước được, trả khi lưu |
| FMS-E01-11 | `:studio:editor` | Cắt, xoay 90°, lật, làm thẳng ±45°, tỉ lệ 1:1, 4:5, 3:2, 16:9, 9:16; không phá hủy, lưu trong `x-fms.crop` | Free | MVP | 2 | FMS-E01-02 | Khi cắt 4:5 rồi xuất thì ảnh đúng tỉ lệ và đúng hướng; khi áp cùng công thức cho ảnh khác thì crop không bị chép theo trừ khi người dùng chọn |
| FMS-E01-12 | `:studio:raw` | 🧪 Spike 2 ngày RAW: giải mã DNG bằng `ImageDecoder` (Skia, API 28+ ⚠) so với LibRaw qua NDK (LGPL-2.1 hoặc CDDL ⚠ giấy phép); đo thời gian, bộ nhớ, màu với DNG 12/50 MP, CR3, NEF, ARW, RAF; chốt hướng | — | V1 | 2 | FMS-E01-04 | Khi xong spike thì có bảng định dạng × máy × thời gian × bộ nhớ, kết luận giấy phép và quyết định thư viện cho FMS-E01-13 và FMS-E01-14 |
| FMS-E01-13 | `:studio:raw` | RAW DNG và ProRAW dạng .dng (B1.4): giải mã 16-bit, demosaic, WB theo Kelvin trước LUT, tone mặc định; pipeline RGBA16F trên GPU | Pro | V1 | 5 | FMS-E01-12; FLC-E01-15 | Khi mở DNG 12 MP của FilCam trên máy tầm trung chuẩn thì preview đầu < 2 giây; khi kéo WB từ 3200 K lên 6500 K thì vùng sáng không bệt màu; khi mở DNG 50 MP thì không OOM |
| FMS-E01-14 | `:studio:raw` | RAW máy ảnh (CR3, NEF, ARW, RAF, ORF, RW2) qua thư viện chốt ở spike; danh sách máy hỗ trợ công khai; máy chưa hỗ trợ thì dùng ảnh JPEG nhúng và báo rõ | Pro | V1 | 3,5 | FMS-E01-13 | Khi mở 10 file mẫu của 5 hãng thì cả 10 file hiện ảnh; khi file thuộc máy chưa hỗ trợ thì app mở ảnh JPEG nhúng kèm thông báo "Đang dùng ảnh xem trước, chưa giải mã RAW" |

## FMS-E02 · Công thức màu

Mục tiêu: công thức tham số kiểu máy ảnh, tên tự đặt, thư viện 20 Free + Pro, thẻ QR; dán công thức dạng chữ ở V1.

Ánh xạ Bảng 11: B2.1 → 01, 02, 04, 05 · B2.2 → 03, 06, 09 · B2.3 → 10, 11 · B2.4 → 07, 08.

Mô hình công thức, bảng ánh xạ tham số → trường `look.json` → pass GPU, 16 tông nền và danh mục công thức khởi đầu nằm ở [README mục 5.2](README.md#52-công-thức-màu-fms-e02).

FMS-E02-01 cần ba trường `adjust` mới trong lõi (Điều chỉnh lõi #1) và tông nền dùng chung (Điều chỉnh lõi #2). Không có hai điều chỉnh này thì công thức quét QR trong Filmode hoặc FilCam sẽ ra màu khác Studio.

Khối lượng: 11 feature · MVP 16 ngày · V1 6,5 ngày · tổng **22,5 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FMS-E02-01 | `:studio:recipe` | Mô hình công thức (B2.1): 15 tham số theo thang máy ảnh (tông nền, độ mạnh và kích thước hạt, độ sâu màu, độ sâu xanh lam, kiểu WB, lệch WB R/B, dải động, vùng sáng, vùng tối, màu, độ nét, độ trong, giảm nhiễu, bù sáng) ↔ trường `look.json` theo bảng ánh xạ README mục 5.2; giá trị thang gốc giữ trong `x-fms.recipe`; cần 3 trường `adjust` mới (Điều chỉnh lõi #1) | Free | MVP | 2 | FLC-E01-01; FLC-E01-03 | Khi chuyển 50 công thức mẫu sang `look.json` rồi ngược lại thì mọi tham số giữ nguyên; khi mở công thức từ QR trong Filmode (bỏ qua `x-fms`) thì ảnh render giống Studio với ΔE trung bình < 1 |
| FMS-E02-02 | `:studio:recipe` | 🧪 Spike 2 ngày hiệu chỉnh thang: 30 cặp ảnh RAW + JPEG chụp với công thức trên máy ảnh thật ⚠ (mượn máy); chốt hệ số đổi nấc vùng sáng, vùng tối, màu, dải động, độ sâu màu sang `adjust`; chốt ngưỡng ΔE | — | MVP | 2 | FMS-E02-01 | Khi xong spike thì có bảng hệ số cho từng tham số, ΔE trung bình trên 30 cặp và ngưỡng ghi vào golden test FMS-E13-02 |
| FMS-E02-03 | `:studio:recipe` | 16 tông nền dựng sẵn `fm:base/<slug>` (LUT 33³ tự dựng, manifest nguồn gốc `owned`) và 20 công thức miễn phí; lọc theo phong cách (máy phim, compact, điện ảnh, chân dung, đen trắng) và cảnh (nắng, đêm, trong nhà, biển); ghi vào `free-tier.json` | Free | MVP | 3 | FLC-E02-01; FLC-E02-02; FLC-E03-04; FLC-E04-03 | Khi cài app rồi bật chế độ máy bay thì 16 tông nền và 20 công thức dùng được; khi một PR chuyển một trong 20 công thức sang Pro thì CI fail; khi CI chạy lint thì không có tên nhãn hiệu nào trong tên, mô tả, tên file |
| FMS-E02-04 | `:studio:recipe` | Màn chỉnh công thức: thanh trượt theo nấc (−4…+4; dải động 3 nấc; độ sâu màu 3 nấc), lưới lệch WB R/B 19×19, chọn tông nền bằng carousel có thumbnail; preview trực tiếp; đặt lại từng tham số | Free | MVP | 3 | FMS-E02-01; FMS-E01-04 | Khi đổi một nấc bất kỳ thì preview cập nhật < 100 ms trên máy tầm trung chuẩn; khi chạm hai lần vào tên tham số thì tham số về mặc định; khi bật TalkBack thì nghe được "Vùng sáng, cộng 2" |
| FMS-E02-05 | `:studio:recipe` | Lưu công thức thành look: tên riêng tự do, `NameGuard` chạy khi chia sẻ; `revision` tăng mỗi lần sửa; mục "Công thức của tôi" | Free | MVP | 1 | FMS-E02-04; FLC-E04-02 | Khi lưu công thức tên "Kodak Gold" để dùng riêng thì được; khi tạo QR cho công thức đó thì app bắt đổi tên và gợi ý 3 tên thay thế; khi sửa rồi lưu thì `revision` tăng 1 và ID giữ nguyên |
| FMS-E02-06 | `:studio:recipe` | Thư viện công thức Pro (B2.2): ≥ 60 công thức lúc ra mắt, 6 nhóm; xem trước trên ảnh của người dùng; khóa lúc lưu hoặc xuất ("thử trước, trả khi lưu") | Pro | MVP | 1 | FMS-E02-03; FLC-E03-06 | Khi người dùng miễn phí chọn công thức Pro thì preview hiện ngay và paywall chỉ mở khi bấm Lưu; khi đã có Pro thì không bao giờ thấy khóa |
| FMS-E02-07 | `:studio:recipe` | Thẻ công thức (B2.4): ảnh 1080×1350 và 1080×1920, 3 bố cục; gồm ảnh mẫu, tên, tác giả, bảng tham số theo thang, QR `filmode.app/r/1#…` cạnh ≥ 28% chiều rộng thẻ ⚠, dòng "Quét bằng Filmode Studio"; chia sẻ qua share sheet | Free | MVP | 2,5 | FMS-E02-05; FLC-E01-03 | Khi tạo thẻ rồi quét QR bằng camera điện thoại khác thì mở đúng công thức; khi thẻ bị nén qua Zalo và Messenger rồi quét lại từ ảnh nhận được thì vẫn đọc được; khi công thức có LUT riêng thì thẻ thay QR bằng mã chữ (V1) hoặc báo "Công thức này cần gửi file" |
| FMS-E02-08 | `:studio:recipe` | Đọc QR công thức không cần quyền camera: quét từ ảnh chụp màn hình qua Photo Picker (ML Kit Barcode ⚠) hoặc Google code scanner ⚠; mở link `/r/1#…` qua App Links | Free | MVP | 1,5 | FMS-E02-07; FLC-E02-08 | Khi chọn ảnh chụp màn hình bài Threads có thẻ công thức thì công thức mở trong ≤ 2 giây; khi QR hỏng thì báo "Mã không hợp lệ"; khi kiểm merged manifest thì không có quyền `CAMERA` |
| FMS-E02-09 | `:studio:recipe` | Bộ sưu tập theo mùa tải về không cần cập nhật app (Hè, Mùa cưới, Trung thu, Noel, Tết Nguyên đán): danh mục qua remote config, `.flook` tải từ hosting, cache offline | Pro | V1 | 2 | FMS-E02-06; FLC-E05-09; FLC-E08-02 | Khi remote config bật bộ "Tết Nguyên đán" thì bộ hiện trong thư viện mà không cần cập nhật app; khi đã tải rồi bật chế độ máy bay thì vẫn dùng được; chuỗi hiển thị không bao giờ có "Chinese New Year" |
| FMS-E02-10 | `:studio:recipe` | Parser công thức dạng chữ (B2.3): chuẩn hóa văn bản (EN, VI, có hoặc không dấu, emoji, gạch đầu dòng, dấu `\|`), nhận khoảng 20 khóa và từ đồng nghĩa, map tên kiểu nền sang tông nền gần nhất, trả kết quả kèm độ tin cậy từng dòng và danh sách dòng chưa hiểu | Free | V1 | 3 | FMS-E02-01 | Khi chạy bộ 60 bài mẫu (kiểu Fuji X Weekly, Threads VN, blog) thì ≥ 95% trường nhận đúng; khi bài có "WB: Daylight, +2 Red & -4 Blue" thì ra `wbShift {r: 2, b: -4}`; khi gặp dòng không hiểu thì trả dòng đó trong danh sách "chưa nhận", không đoán |
| FMS-E02-11 | `:studio:recipe` | Luồng dán công thức: nhận chữ từ clipboard hoặc share (`ACTION_SEND` text/plain) từ Threads, Facebook, trình duyệt; màn xác nhận từng tham số, sửa tay; tên gốc có nhãn hiệu thì đề xuất tên tự đặt | Free | V1 | 1,5 | FMS-E02-10; FLC-E04-02 | Khi chia sẻ một bài Threads có công thức sang Studio thì màn xác nhận hiện ≤ 1 giây với các tham số đã điền; khi tên gốc là "Kodachrome 64" thì tên gợi ý không chứa nhãn hiệu |

## FMS-E03 · Nhập preset và LUT đã có

Mục tiêu: nhập được mọi gói preset/LUT người dùng đã mua (.cube, .3dl, HALD, .xmp, .dng, zip), có báo cáo, và không làm lộ LUT của người khác.

Ánh xạ Bảng 11: B3.1 → 01–03, 05, 07 · B3.2 → 04, 06.

Bộ nhập nằm ở lõi (FLC-E01-04, FLC-E01-05, FLC-E01-08). Studio chỉ làm màn nhập, báo cáo, xử lý gói zip và luật chia sẻ.

Khối lượng: 7 feature · MVP 7,5 ngày · V1 1,5 ngày · tổng **9 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FMS-E03-01 | `:studio:import` | Màn nhập hợp nhất (B3.1): chọn nhiều file qua `ACTION_OPEN_DOCUMENT` (.cube, .3dl, HALD .png, .xmp, .dng, .zip, .flook) hoặc nhận share intent; gọi bộ nhập của lõi; chạy nền, có tiến độ | Free | MVP | 2 | FLC-E01-04; FLC-E01-05; FLC-E01-08 | Khi chia sẻ một file .zip 40 preset từ Zalo sang Studio thì app nhập nền và báo tiến độ; khi đang nhập mà thoát app thì lần mở sau nhập tiếp, không nhân đôi look |
| FMS-E03-02 | `:studio:import` | Báo cáo nhập: từng file thành công, lỗi kèm lý do, phần không chuyển được (làm nét, khử nhiễu, mask, lens profile); phân biệt preset .dng với ảnh RAW .dng và đưa ảnh RAW sang trình sửa | Free | MVP | 1,5 | FMS-E03-01; FLC-E07-06 | Khi nhập 10 file .xmp có dehaze thì báo cáo ghi "dehaze không chuyển được" cho đúng 10 file; khi file .dng là ảnh chụp thì app hỏi "Mở ảnh này để chỉnh?" thay vì báo lỗi |
| FMS-E03-03 | `:studio:import` | Gói zip đã mua: giải nén một cấp zip lồng, bỏ `__MACOSX`, file ẩn, PDF và ảnh hướng dẫn; tạo thư mục theo tên gói; gán `license: personal` và nguồn nhập | Free | MVP | 1 | FMS-E03-01 | Khi nhập zip mua trên Gumroad có thư mục DNG, XMP và PDF thì chỉ preset được nhập và nằm chung một thư mục; khi zip có mật khẩu thì báo "File có mật khẩu, hãy giải nén trước" |
| FMS-E03-04 | `:studio:import` | Thư viện look (B3.2): thư mục, thẻ, yêu thích, tìm theo tên, sắp xếp; lưới xem trước mọi look trên chính ảnh đang sửa hoặc "ảnh mẫu của tôi" | Free | MVP | 2 | FLC-E02-01; FLC-E02-02 | Khi thư viện có 300 look thì lưới thumbnail trên ảnh của người dùng hiện ảnh đầu < 300 ms và cuộn không giật; khi đổi "ảnh mẫu của tôi" thì mọi thumbnail làm mới |
| FMS-E03-05 | `:studio:import` | Bảo vệ LUT của người khác: look nhập có `license` là `personal` hoặc `unknown` chỉ chia sẻ được phần công thức (không kèm LUT), không công khai được, không xuất .cube được; hiện lời nhắc bản quyền | — | MVP | 1 | FMS-E03-03; FLC-E01-03 | Khi chọn "Chia sẻ" cho một LUT mua trên Gumroad thì app không gửi `lut.cube` và giải thích lý do; khi thử công khai look đó thì bị chặn |
| FMS-E03-06 | `:studio:import` | Look từ app anh em trên cùng máy: mục "Từ Filmode", "Từ FilCam" trong thư viện, không cần tài khoản | Free | V1 | 1 | FLC-E02-09; FMS-E03-04 | Khi lưu look trong Filmode thì Studio trên cùng máy thấy look đó trong ≤ 5 giây sau khi mở thư viện |
| FMS-E03-07 | `:studio:import` | Trợ giúp theo ngữ cảnh khi nhập lỗi: cách lấy .xmp từ Lightroom desktop, DNG từ Gumroad/Etsy, .cube từ Resolve; nội dung song ngữ tải qua remote config | Free | V1 | 0,5 | FMS-E03-02; FLC-E05-09 | Khi nhập file .lrtemplate thì app hiện hướng dẫn chuyển sang .xmp thay vì chỉ báo "định dạng không hỗ trợ" |

## FMS-E04 · Sao chép màu từ ảnh mẫu

Mục tiêu: match v1 miễn phí cho ảnh đang sửa, lưu thành look là Pro; tinh chỉnh ở V1; Match v2 bằng AI chạy trên máy ở V2 sau khi rà giấy phép.

Ánh xạ Bảng 11: B4.1 → 01, 02 · B4.2 → 04–06 · B4.3 → 03.

Thuật toán Match v1 là FLC-E01-18 (lõi). Studio làm UI, gói bán và phần tinh chỉnh. Nếu lõi cắt FLC-E01-18 khỏi MVP theo cut-line "1 dev" thì MVP của Studio bị chặn ⚠.

Báo cáo ước Match v2 là 6–10 tuần-người kể cả huấn luyện. Ở đây là 13 ngày vì giả định dùng lại được mã nghiên cứu hoặc chỉ tinh chỉnh mô hình nhỏ; nếu spike FMS-E04-04 kết luận phải tự huấn luyện từ đầu thì ước lại.

Khối lượng: 6 feature · MVP 3,5 ngày · V1 2,5 ngày · V2 13 ngày · tổng **19 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FMS-E04-01 | `:studio:match` | Match v1 (B4.1): chọn ảnh mẫu qua Photo Picker, cắt vùng mẫu (bỏ viền, chữ, logo), gọi thuật toán lõi, preview trên ảnh đang sửa, thanh cường độ; áp cho ảnh đang sửa và xuất ảnh là miễn phí | Free | MVP | 2,5 | FLC-E01-18; FMS-E01-04 | Khi chọn ảnh mẫu thì preview kết quả < 1 giây trên máy tầm trung chuẩn; khi ảnh mẫu đen trắng hoặc gần như một màu thì app cảnh báo trước khi match |
| FMS-E04-02 | `:studio:match` | Lưu kết quả match thành look (Pro): LUT 33³, `origin.type = match`, tên, thumbnail; dùng lại cho ảnh khác và cho lô | Pro | MVP | 1 | FMS-E04-01; FLC-E03-06 | Khi người dùng miễn phí bấm "Lưu thành look" thì paywall mở và kết quả chưa lưu vẫn còn khi đóng paywall; khi có Pro thì look xuất hiện trong thư viện ngay |
| FMS-E04-03 | `:studio:match` | Tinh chỉnh sau match (B4.3): khóa độ sáng (chỉ chuyển màu, giữ L*), độ mạnh riêng cho tone và cho màu, giữ tông da | Pro | V1 | 2,5 | FMS-E04-02; FMS-E05-01 | Khi bật khóa độ sáng thì L* của ảnh kết quả lệch ảnh gốc < 1 trên ramp xám; khi bật giữ tông da thì vùng da lệch ảnh gốc ΔE < 3 |
| FMS-E04-04 | `:studio:match` | 🧪 Spike 3 ngày Match v2 (B4.2): rà giấy phép mã và trọng số của Neural Preset và Deep Analog (chưa ghi giấy phép ⚠); chuyển thử sang LiteRT; đo thời gian suy luận trên máy tầm trung; so với v1 trên 30 cặp ảnh | — | V2 | 3 | FMS-E04-01 | Khi xong spike thì có kết luận giấy phép (dùng thương mại được hay phải tự huấn luyện), số ms suy luận trên 3 máy và bảng ΔE v1 so với v2 |
| FMS-E04-05 | `(tools)` | Huấn luyện mô hình dự đoán LUT của đội (nếu giấy phép không cho dùng thương mại): tạo cặp dữ liệu từ look tự sở hữu × ảnh CC0 hoặc tự chụp, huấn luyện, lượng tử hóa, xuất LiteRT | — | V2 | 5 | FMS-E04-04 | Khi đánh giá trên tập kiểm thử 200 cặp thì ΔE trung bình tốt hơn v1 ít nhất 20%; khi kiểm manifest dữ liệu thì mọi ảnh huấn luyện có nguồn và giấy phép |
| FMS-E04-06 | `:studio:match` | Match v2 trong app: mô hình tải theo yêu cầu (Play Asset Delivery ⚠), suy luận một lần mỗi ảnh mẫu, sinh LUT 33³ chạy trên pipeline thường; tự lùi về v1 khi máy yếu hoặc lỗi; A/B v1 và v2 qua remote config | Pro | V2 | 5 | FMS-E04-05; FLC-E05-09 | Khi chạy trên máy tier C thì app dùng v1 mà không báo lỗi; khi dùng v2 trên máy tầm trung chuẩn thì có LUT trong ≤ 1 giây; khi remote config tắt v2 thì lần mở sau dùng v1 |

## FMS-E05 · Mặt nạ và tông da

Mục tiêu: giữ màu da khi áp look mạnh (V1); mask bầu trời, cọ và vùng chuyển (V2).

Ánh xạ Bảng 11: B5.1 → 01, 02 · B5.2 → 03–06.

Tách nền người và pass trộn theo mask là FLC-E01-22 (lõi, V1). Báo cáo ước tông da 2–4 tuần-người; ở đây chỉ 3,5 ngày vì phần nặng đã ở lõi.

Khối lượng: 6 feature · V1 3,5 ngày · V2 11,5 ngày · tổng **15 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FMS-E05-01 | `:studio:mask` | Bảo vệ tông da (B5.1): bật và chỉnh mức; mask người tính một lần mỗi ảnh ở cạnh ≤ 512 px rồi phóng lên có feather; dùng cho preview, xuất và lô | Pro | V1 | 2 | FLC-E01-22; FMS-E01-04 | Khi áp công thức đỏ mạnh lên 20 ảnh chân dung thì vùng da lệch ảnh gốc ΔE < 3; khi ảnh không có người thì công tắc báo "Không thấy người trong ảnh" |
| FMS-E05-02 | `:studio:mask` | Xem và sửa mask da: lớp phủ màu, cọ thêm và bớt, độ mềm viền | Pro | V1 | 1,5 | FMS-E05-01 | Khi tô thêm vùng tay bị sót thì vùng đó giữ màu gốc ở ảnh xuất; khi bấm "Đặt lại" thì mask về kết quả tự động |
| FMS-E05-03 | `:studio:mask` | 🧪 Spike 1,5 ngày mask bầu trời: MediaPipe multiclass hoặc mô hình bầu trời khác ⚠ giấy phép; đo thời gian trên máy tier C và độ chính xác viền cây | — | V2 | 1,5 | FMS-E05-01 | Khi xong spike thì có bảng thời gian trên 3 máy, IoU trên 30 ảnh và quyết định mô hình |
| FMS-E05-04 | `:studio:mask` | Mặt nạ bầu trời (B5.2): tự nhận bầu trời, chỉnh cục bộ phơi sáng, nhiệt độ, bão hòa | Pro | V2 | 3 | FMS-E05-03 | Khi giảm phơi sáng bầu trời −1 EV thì tòa nhà không tối đi (ΔE < 2 ngoài mask); khi ảnh không có trời thì công cụ báo rõ |
| FMS-E05-05 | `:studio:mask` | Cọ vẽ mask và chỉnh cục bộ (phơi sáng, nhiệt độ, bão hòa, độ trong); mask lưu trong `x-fms` của bản sửa, không vào look chia sẻ; bake khi xuất theo tile | Pro | V2 | 5 | FMS-E01-04; FLC-E01-15 | Khi tô mask trên ảnh 50 MP rồi xuất thì không thấy đường nối tile; khi chia sẻ công thức từ ảnh có mask thì QR không chứa mask |
| FMS-E05-06 | `:studio:mask` | Vùng tròn và vùng chuyển (radial, linear), đảo mask, cộng và trừ mask | Pro | V2 | 2 | FMS-E05-05 | Khi đặt vùng chuyển trên nửa trên ảnh thì hiệu ứng giảm dần mượt, không thấy dải màu (banding) trên ảnh 8-bit |

## FMS-E06 · Hàng loạt và feed

Mục tiêu: cả một feed có chung một look: dán thiết lập, áp hàng loạt có chuẩn hóa phơi sáng, lưới 3×3.

Ánh xạ Bảng 11: B6.1 → 02, 03 · B6.2 → 01, 04.

Thuật toán chuẩn hóa phơi sáng mô tả ở [README mục 5.6](README.md#56-hàng-loạt-và-feed-fms-e06).

Khối lượng: 4 feature · V1 10 ngày · tổng **10 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FMS-E06-01 | `:studio:batch` | Sao chép và dán thiết lập (B6.2): chọn nhóm (công thức, màu, film, crop) rồi dán cho một hoặc nhiều ảnh | Free | V1 | 1 | FMS-E01-02 | Khi dán riêng nhóm "công thức" thì crop của ảnh đích giữ nguyên; khi dán cho 5 ảnh thì 5 bản sửa được tạo và undo được từng ảnh |
| FMS-E06-02 | `:studio:batch` | Áp hàng loạt (B6.1): chọn tới 100 ảnh, một công thức, xuất nền bằng WorkManager foreground, tiến độ, hủy, tiếp tục sau khi bị kill; lưu qua hàng đợi bền của lõi | Pro | V1 | 3 | FMS-E06-01; FLC-E06-02; FLC-E01-15 | Khi xuất 100 ảnh 12 MP trên máy tầm trung chuẩn thì xong < 3 phút và không OOM; khi kill app ở ảnh 40 thì mở lại tiếp tục từ ảnh 41 và không trùng file |
| FMS-E06-03 | `:studio:batch` | Chuẩn hóa phơi sáng và WB từng ảnh trong lô: đo trung vị độ sáng (bỏ 1% hai đầu) trên proxy 256 px, tính ΔEV về đích (trung vị lô hoặc ảnh chuẩn), giới hạn ±1,5 EV; WB gray-world có giới hạn (tùy chọn); lưới trước/sau, sửa riêng từng ảnh | Pro | V1 | 4 | FMS-E06-02 | Khi lô 20 ảnh lệch sáng nhau 2 EV thì sau chuẩn hóa độ lệch trung vị độ sáng ≤ 0,3 EV; khi một ảnh đêm được khóa khỏi chuẩn hóa thì ảnh đó giữ nguyên phơi sáng |
| FMS-E06-04 | `:studio:batch` | Lưới feed 3×3 (B6.2): xem trước 9–30 ảnh như trang cá nhân, kéo đổi thứ tự, đánh dấu ảnh lệch màu so với lô (ΔE trung bình vượt ngưỡng) | Free | V1 | 2 | FMS-E06-01 | Khi một ảnh trong lưới dùng công thức khác thì ảnh đó được đánh dấu "lệch màu"; khi kéo đổi thứ tự thì thứ tự giữ nguyên sau khi mở lại |

## FMS-E07 · Xuất

Mục tiêu: xuất ảnh đủ độ phân giải không watermark; xuất look .cube/HALD và mở thẳng trong Filmode, FilCam.

Ánh xạ Bảng 11: B7.1 → 01–03, 06 · B7.2 → 04, 05.

Ultra HDR (FLC-E06-04) và xuất LUT (FLC-E01-19) nằm ở lõi.

Khối lượng: 6 feature · MVP 4,5 ngày · V1 3,5 ngày · tổng **8 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FMS-E07-01 | `:studio:export` | Xuất ảnh (B7.1): JPEG, HEIF, PNG đủ độ phân giải, không watermark; chọn chất lượng; render theo tile; lưu album `Pictures/Filmode Studio`; giữ EXIF, thêm `Software`; xóa GPS khi chia sẻ; chia sẻ nhanh sang Threads, Instagram, Zalo, Messenger với cạnh dài 2048 hoặc 1080 px | Free | MVP | 3 | FLC-E01-15; FLC-E06-02; FLC-E06-03 | Khi xuất ảnh 50 MP thì file ra đủ 50 MP và không có watermark; khi chia sẻ với "xóa vị trí" bật thì exiftool không thấy GPS; khi xuất ảnh 12 MP trên máy tầm trung chuẩn thì p90 < 1,5 giây |
| FMS-E07-02 | `:studio:export` | Ultra HDR: ảnh gốc Ultra HDR thì xuất Ultra HDR có look (gain map chỉnh theo); máy không hỗ trợ thì xuất SDR | Free | MVP | 1 | FLC-E06-04; FMS-E07-01 | Khi sửa ảnh Ultra HDR chụp trên Pixel rồi xuất thì Google Photos hiện ảnh HDR và vùng sáng không đổi màu so với bản SDR |
| FMS-E07-03 | `:studio:export` | Gửi look dạng file `.flook` qua share sheet (Zalo, Messenger, Bluetooth), không cần mạng | Free | MVP | 0,5 | FLC-E01-02; FMS-E03-05 | Khi gửi `.flook` qua Zalo rồi mở trên máy khác có Studio thì look nhập được; khi look là LUT mua thì chỉ gửi được phần công thức |
| FMS-E07-04 | `:studio:export` | Xuất look (B7.2): .cube 33/65, HALD PNG, kèm hướng dẫn ngắn cho CapCut desktop, VN, DaVinci Resolve, Blackmagic Camera; liệt kê hiệu ứng không đi theo LUT | Pro | V1 | 1,5 | FLC-E01-19; FMS-E03-05 | Khi xuất .cube 33 rồi nhập vào app VN trên cùng máy thì màu khớp (kiểm tay); khi look là LUT có `license: personal` thì nút xuất bị ẩn |
| FMS-E07-05 | `:studio:export` | Mở thẳng trong Filmode hoặc FilCam: nút "Dùng trong máy ảnh Filmode", "Dùng khi quay FilCam" (intent `.flook`, thư viện dùng chung); chưa cài thì mở trang Play | Free | V1 | 1 | FLC-E02-08; FLC-E02-09 | Khi bấm "Dùng khi quay FilCam" trên máy đã cài FilCam thì FilCam mở màn nhập look mà không cần mạng; khi chưa cài thì mở trang FilCam trên Play |
| FMS-E07-06 | `:studio:export` | Xuất 16-bit cho ảnh RAW: PNG 16-bit (bộ mã hóa riêng ⚠ nếu `Bitmap.compress` chỉ ra 8-bit) và JPEG chất lượng cao | Pro | V1 | 1 | FMS-E01-13; FMS-E07-01 | Khi xuất PNG 16-bit từ DNG rồi mở bằng công cụ kiểm tra thì độ sâu là 16 bit mỗi kênh |

## FMS-E08 · Cộng đồng

Mục tiêu: chia sẻ bằng link và mã chữ; trang công thức công khai để lên Google; khám phá, remix, kiểm duyệt ở V2.

Ánh xạ Bảng 11: B8.1 → 01–04 · B8.2 → 05, 06 · B8.3 → 07, 08.

Link cloud `/l/<id>` và API look công khai là FLC-E08-03 (lõi). Mã chữ của Studio chính là `id` 8 ký tự đó.

Công khai là việc duy nhất ở V1 cần đăng nhập. Mọi thứ khác chạy không tài khoản.

Khối lượng: 8 feature · V1 11,5 ngày · V2 13 ngày · tổng **24,5 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FMS-E08-01 | `:studio:community` | Chia sẻ bằng link cloud và mã chữ (B8.1): tải `.flook` lên API look công khai, nhận link `filmode.app/l/<id>` và mã 8 ký tự; ô "Nhập mã" trong app; dùng cho công thức có LUT riêng | Free | V1 | 1,5 | FLC-E08-03; FMS-E02-05 | Khi gửi mã 8 ký tự qua tin nhắn rồi nhập trên máy khác thì look tải về trong ≤ 3 giây trên 4G; khi look có tên nhãn hiệu thì server trả lỗi và app gợi ý đổi tên |
| FMS-E08-02 | `(backend)` | Xuất bản công thức công khai: metadata (tên, tác giả, tham số, 2–4 ảnh mẫu ≤ 2048 px đã xóa EXIF, mô tả, thẻ), `NameGuard` phía server, hạn mức, trạng thái chờ duyệt → công khai; slug ổn định | Free | V1 | 3 | FLC-E08-02; FLC-E08-03; FLC-E04-02 | Khi đăng công thức kèm ảnh có GPS thì ảnh lưu trên server không còn EXIF; khi đăng tên "Velvia Vibes" thì bị từ chối kèm lý do; khi đổi tên công thức thì slug cũ chuyển hướng 301 sang slug mới |
| FMS-E08-03 | `:studio:community` | Luồng "Công khai công thức" trong app: chọn ảnh mẫu, mô tả, thẻ; xác nhận ảnh là của mình; đăng nhập Google chỉ bắt buộc khi công khai; xem, sửa, gỡ công thức đã đăng | Free | V1 | 2 | FMS-E08-02; FLC-E02-04 | Khi chưa đăng nhập mà bấm "Công khai" thì app xin đăng nhập Google, còn mọi tính năng khác vẫn dùng không cần tài khoản; khi gỡ công thức thì trang web trả 410 trong ≤ 5 phút |
| FMS-E08-04 | `(web)` | Trang web công thức cho SEO: `/cong-thuc/<slug>` (vi) và `/recipes/<slug>` (en) dựng tĩnh; tiêu đề "Công thức màu film <tên> – chỉnh màu film cho ảnh điện thoại"; bảng tham số, ảnh trước/sau, QR, nút mở app, JSON-LD, hreflang, sitemap; trang danh mục theo phong cách và cảnh | Free | V1 | 5 | FMS-E08-02; FLC-E02-08 | Khi kiểm URL bằng Google Search Console thì trang được lập chỉ mục và không có lỗi dữ liệu có cấu trúc; khi mở trên điện thoại 4G thì LCP < 2,5 giây; khi quét QR trên trang thì mở đúng công thức trong app |
| FMS-E08-05 | `:studio:community` | Khám phá (B8.2): công thức thịnh hành (lượt lưu 7 ngày), mới, theo phong cách và cảnh; thử lên ảnh của mình trước khi lưu | Free | V2 | 3 | FMS-E08-02 | Khi mở tab Khám phá thì danh sách hiện < 1 giây từ cache và làm mới nền; khi offline thì hiện danh sách lần trước |
| FMS-E08-06 | `:studio:community` | Hồ sơ creator, theo dõi, remix có ghi tên (`remixOf`); chuỗi remix hiện trong app và trên trang web | Free | V2 | 4 | FMS-E08-05 | Khi remix công thức của A rồi đăng thì trang công thức mới ghi "Remix từ <A>" kèm link; khi theo dõi một creator thì công thức mới của họ hiện đầu tab Theo dõi |
| FMS-E08-07 | `:studio:community` | Kiểm duyệt (B8.3): báo cáo vi phạm trong app và trên web (nhãn hiệu, ảnh không phải của mình, nội dung nhạy cảm), chặn người dùng, ẩn nội dung bị báo; đáp ứng quy định nội dung người dùng tạo của Play và App Store (guideline 1.2 ⚠) | — | V2 | 2,5 | FMS-E08-02 | Khi 3 người báo cáo cùng một công thức thì công thức bị ẩn chờ duyệt; khi chặn một người thì không còn thấy nội dung của người đó |
| FMS-E08-08 | `(backend)` | Công cụ quản trị và gỡ theo khiếu nại: hàng chờ duyệt, gỡ, khôi phục, nhật ký; quy trình thông báo và gỡ (notice and takedown) trả lời trong 72 giờ ⚠; lọc ảnh nhạy cảm tự động trước khi công khai (Cloud Vision SafeSearch ⚠ hoặc mô hình trên máy) | — | V2 | 3,5 | FMS-E08-07 | Khi quản trị gỡ một công thức thì app, trang web và link cloud đều hiện "Nội dung đã bị gỡ" trong ≤ 5 phút; khi ảnh mẫu bị gắn cờ nhạy cảm thì không tự công khai |

## FMS-E09 · Chợ look của creator

Mục tiêu: creator bán gói look qua IAP, đội chia doanh thu và chi trả ngoài store; gói mang thương hiệu creator ở V3.

Ánh xạ Bảng 11: B9.1 → 02, 03, 05, 06 · B9.2 → 01, 04, 07–09 · B9.3 → 10.

Mọi chi tiết luồng tiền, thuế và chính sách store là ⚠ và phải qua spike FMS-E09-01 cùng rà soát pháp lý trước khi code. Báo cáo ước chợ creator 10–16 tuần-người Android cộng 4 cho iOS; ở đây 31 ngày cho E09 và 13 ngày V2 của E08, khoảng 9 tuần-người, vì hạ tầng tài khoản, lưu trữ, xác minh mua và link look đã ở lõi.

Khối lượng: 10 feature · V2 27 ngày · V3 4 ngày · tổng **31 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FMS-E09-01 | `(backend)` | 🧪 Spike 2 ngày thiết kế luồng tiền ⚠: bán gói creator qua IAP (đội là người bán), chia doanh thu ngoài store; rà chính sách Play Payments, App Store 3.1.1 và 3.2 ⚠; kênh chi trả (chuyển khoản VN; Wise hoặc PayPal cho creator nước ngoài ⚠); khấu trừ thuế TNCN cho cá nhân VN ⚠; khung thỏa thuận creator (rà pháp lý không tính) | — | V2 | 2 | FLC-E03-10 | Khi xong spike thì có sơ đồ luồng tiền, bảng phí và thuế theo nước, danh sách câu hỏi cho luật sư và tỷ lệ chia đề xuất |
| FMS-E09-02 | `:studio:market` | SKU gói creator: sản phẩm một lần theo bậc giá $1.99, $2.99, $3.99 tạo sẵn (`fms.pack.c.<n>`, tạo qua Play Developer API ⚠); gán gói ↔ SKU trên server; quyền `pack:<id>` qua `Entitlements`; gói creator không nằm trong Pro | IAP | V2 | 2,5 | FLC-E03-03; FLC-E03-08; FMS-E09-01 | Khi thêm gói creator mới thì không cần phát hành app; khi người có Pro mở gói creator thì vẫn thấy giá; khi cài lại app thì gói đã mua khôi phục mà không cần tài khoản |
| FMS-E09-03 | `(backend)` | Nhận và duyệt gói: tải `.flook` (5–30 look), ảnh mẫu, mô tả; kiểm định dạng, `NameGuard`, trùng checksum với LUT công khai hoặc gói khác (chống bán lại LUT người khác), khai quyền sở hữu; nháp → duyệt → phát hành; gỡ gói nhưng người đã mua giữ quyền | — | V2 | 4,5 | FLC-E08-03; FLC-E04-03; FMS-E09-01 | Khi gói có LUT trùng checksum một HaldCLUT công khai thì bị từ chối kèm tên file; khi gỡ một gói đã bán thì người đã mua vẫn tải và dùng được |
| FMS-E09-04 | `(web)` | Cổng creator: đăng nhập, tải gói, theo dõi trạng thái duyệt, đồng ý thỏa thuận creator (lưu phiên bản và thời điểm), thông tin nhận tiền và mã số thuế ⚠ | — | V2 | 4 | FMS-E09-03 | Khi creator đồng ý thỏa thuận thì server lưu phiên bản điều khoản và thời điểm; khi thiếu thông tin nhận tiền thì gói vẫn duyệt được nhưng chi trả bị giữ |
| FMS-E09-05 | `:studio:market` | Cửa hàng trong app: danh sách gói creator, hồ sơ, ảnh mẫu trước/sau, thử gói trên ảnh của mình (bản xem trước độ phân giải thấp, không tải LUT đầy đủ), mua qua IAP, khôi phục | IAP | V2 | 3 | FMS-E09-02; FLC-E03-06 | Khi thử gói chưa mua thì preview dùng được trên ảnh của mình nhưng không lưu được; khi mua xong thì look có trong thư viện ≤ 10 giây |
| FMS-E09-06 | `:studio:market` | Tải gói đã mua: server chỉ cấp URL tải có hạn khi xác minh được giao dịch; look gắn `license: personal` và `x-fms.packId`, không chia sẻ lại LUT, không xuất .cube | IAP | V2 | 2 | FLC-E03-10; FMS-E09-05; FMS-E03-05 | Khi gửi giao dịch giả thì server từ chối cấp URL; khi người mua bấm chia sẻ một look trong gói thì chỉ chia sẻ được link tới trang gói |
| FMS-E09-07 | `(backend)` | Sổ doanh thu: nhận RTDN và App Store Server Notifications, ghi giao dịch theo gói và nước, trừ phí store 15% và thuế store thu hộ, xử lý hoàn tiền; tính phần creator theo tỷ lệ (đề xuất 50% doanh thu thực nhận ⚠) | — | V2 | 3 | FLC-E03-10; FMS-E09-02 | Khi có một giao dịch $2.99 ở VN rồi bị hoàn tiền thì sổ ghi cả hai dòng và phần creator về 0; khi đối soát tháng với báo cáo của Play thì lệch ≤ 1% |
| FMS-E09-08 | `(web)` | Bảng điều khiển creator (B9.2): doanh số theo ngày và nước, lượt dùng gộp ẩn danh, số dư chờ, lịch sử chi trả, tải chứng từ | — | V2 | 3 | FMS-E09-07; FMS-E09-04 | Khi creator mở bảng điều khiển thì số liệu mới nhất không cũ hơn 24 giờ; khi lượt dùng của một gói < 10 thì chỉ hiện "< 10" để không lộ người dùng |
| FMS-E09-09 | `(backend)` | Chi trả hằng tháng: giữ 45 ngày chờ hoàn tiền, ngưỡng tối thiểu (500.000 ₫ hoặc $20 ⚠), khấu trừ thuế theo quy định ⚠, xuất file chuyển khoản, khóa chi trả khi có tranh chấp bản quyền | — | V2 | 3 | FMS-E09-07 | Khi số dư dưới ngưỡng thì chuyển sang tháng sau; khi gói đang bị khiếu nại thì phần chi trả của gói đó bị giữ và creator thấy lý do |
| FMS-E09-10 | `:studio:market` | Gói mang thương hiệu creator (B9.3): trang riêng `filmode.app/c/<handle>` và màn chào mang tên creator, bộ look cập nhật hằng tháng, mã quà tặng để creator tặng follower | IAP | V3 | 4 | FMS-E09-05; FLC-E03-05 | Khi mở link `filmode.app/c/<handle>` trên máy đã cài thì app mở thẳng trang creator; khi nhập mã quà hợp lệ thì gói mở mà không phải trả tiền |

## FMS-E10 · Kiếm tiền

Mục tiêu: gói Free cố định, Studio Pro trọn đời và năm, gói lẻ; paywall đúng checklist lõi.

Ánh xạ Bảng 11: B10.1 → 02 · B10.2 → 01, 03, 05 · B10.3 → 06. Thêm: 04 (đo phễu).

Billing, `Entitlements`, paywall và bảng giá theo vùng nằm ở lõi (FLC-E03-*). Studio chỉ khai SKU, nội dung gói và điểm gọi paywall.

Khối lượng: 6 feature · MVP 5 ngày · V1 3 ngày · tổng **8 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FMS-E10-01 | `:app:studio` | Bảng SKU và giá theo vùng: `fms.pro.lifetime` $19.99, `fms.pro.yearly` $14.99 (dùng thử 7 ngày chỉ ở gói năm ⚠), gói lẻ; VN 229.000 ₫ trọn đời, 149.000 ₫/năm; ID, TH, PH, BR, IN khoảng 40–50% giá Mỹ; map quyền `pro`, `pack:<id>` | — | MVP | 1,5 | FLC-E03-03; FLC-E03-08 | Khi chạy script giá thì Play Console có đúng 229.000 ₫ và 149.000 ₫ cho VN; khi mua gói năm bằng license tester thì quyền `pro` bật và khôi phục được sau khi cài lại |
| FMS-E10-02 | `:app:studio` | Gói miễn phí cố định (B10.1) trong `free-tier.json` của Studio: trình sửa lõi, 16 tông nền, 20 công thức, nhập .cube/.3dl/HALD/.xmp/.dng/zip, dán công thức, thẻ QR, xuất đủ độ phân giải không watermark, match cho ảnh đang sửa; CI chặn thu hẹp | Free | MVP | 0,5 | FMS-E10-01; FLC-E03-04 | Khi một PR chuyển "nhập .xmp" sang Pro thì CI fail và nêu tên mục; khi đọc `free-tier.json` thì có đủ các mục đã liệt kê |
| FMS-E10-03 | `:app:studio` | Paywall Studio (B10.2) trên `:core:paywall`: gói trọn đời nổi bật, gói năm, danh sách Pro mở gì và thứ vẫn miễn phí; điểm gọi: lưu hoặc xuất ảnh dùng công cụ Pro, lưu match, lưu công thức Pro, lô, RAW, xuất LUT, tông da | Pro | MVP | 2 | FLC-E03-06; FMS-E10-01 | Khi chạy screenshot test 7 ngôn ngữ thì checklist paywall 4.3 đạt 100%; khi người dùng mới mở app thì không có paywall nào chặn trước khi họ sửa được một ảnh |
| FMS-E10-04 | `:app:studio` | Đo phễu Studio: `edit_open`, `recipe_apply`, `recipe_card_create`, `qr_open`, `import_done`, `match_preview`, `save`, `paywall_view` (kèm điểm gọi), `purchase_success`; không gửi tên công thức người dùng đặt | — | MVP | 1 | FLC-E05-07 | Khi đi hết luồng mở ảnh → áp công thức → tạo thẻ → lưu → paywall → mua thì DebugView hiện đủ sự kiện đúng thứ tự; khi kiểm payload thì không có tên look người dùng đặt |
| FMS-E10-05 | `:app:studio` | Thử A/B giá: VN trọn đời 199.000 ₫ so với 263.000 ₫; gói năm có và không có dùng thử | — | V1 | 1 | FLC-E03-07; FMS-E10-03 | Khi remote config gán nhóm B thì paywall hiện giá nhóm B và mọi sự kiện paywall mang `variant=B`; người đã có Pro không vào thử nghiệm |
| FMS-E10-06 | `:studio:market` | Gói lẻ của đội (B10.3): gói công thức theo mùa hoặc chủ đề $1.99–3.99 (VN 49.000–99.000 ₫ ⚠), mua một lần; người có Pro đã có sẵn; màn cửa hàng gói | IAP | V1 | 2 | FMS-E10-01; FMS-E02-09 | Khi người dùng miễn phí mua gói "Mùa cưới" thì chỉ gói đó mở, thư viện Pro vẫn khóa; khi người có Pro mở cửa hàng thì gói của đội hiện "Đã có trong Pro" |

## FMS-E11 · Onboarding và hướng dẫn

Mục tiêu: người mới lưu được ảnh đẹp đầu tiên trong vòng một phút; gợi ý công thức theo phong cách và cảnh; bài hướng dẫn song ngữ.

Ánh xạ Bảng 11: B11.1 → 02 · B11.2 → 03. Thêm: 01 (lần mở đầu, MVP).

Khối lượng: 3 feature · MVP 1,5 ngày · V1 6 ngày · tổng **7,5 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FMS-E11-01 | `:studio:onboarding` | Lần mở đầu: 3 bước chọn ảnh (hoặc ảnh mẫu có sẵn) → áp công thức → lưu; không paywall chặn; 3 ảnh mẫu tự sở hữu cho người chưa muốn chọn ảnh và cho người duyệt store | Free | MVP | 1,5 | FMS-E01-02; FMS-E02-03 | Khi mở app lần đầu ở chế độ máy bay thì đi hết 3 bước bằng ảnh mẫu và lưu được ảnh; khi bấm "Bỏ qua" ở bất kỳ bước nào thì vào thẳng màn chính |
| FMS-E11-02 | `:studio:onboarding` | Gợi ý phong cách (B11.1): 3 câu hỏi (ấm hay lạnh, tương phản, hạt) để sắp xếp thư viện; gợi ý công thức theo cảnh bằng nhận diện trên máy (ML Kit Image Labeling ⚠: trời, biển, đồ ăn, đêm, người, trong nhà) | Free | V1 | 4 | FMS-E11-01; FMS-E02-03 | Khi mở ảnh bãi biển thì 3 gợi ý đầu thuộc nhóm "Biển" hoặc "Nắng"; khi nhận diện chạy thì không có ảnh nào rời máy (kiểm bằng proxy) |
| FMS-E11-03 | `:studio:onboarding` | Hướng dẫn song ngữ (B11.2): trình đọc bài (Markdown đóng gói, tải thêm qua remote config), nút "Thử công thức này" mở đúng công thức trên ảnh đang sửa | Free | V1 | 2 | FLC-E05-09; FMS-E02-04 | Khi thêm bài mới qua remote config thì bài hiện mà không cần cập nhật app; khi bấm "Thử công thức này" thì trình sửa mở với công thức đã áp |

## FMS-E12 · iOS Studio

Mục tiêu: ra Studio trên iOS khoảng một quý sau Android, dựng trên `FilmodeCoreKit` và dùng lại trình sửa, Match Photo, bộ nhập .xmp của Filmode iOS khi được.

Epic mới. Bảng 11 không có epic iOS riêng, nhưng Bảng 13 đặt Studio iOS ở Q2/2027 với 4–8 tuần-người. Gom phần iOS thành một epic để thấy rõ khối lượng của dev iOS và phần phụ thuộc vào lõi iOS (FLC-E01-24, -25, -26, FLC-E02-10, FLC-E03-09, FLC-E06-07).

Ưu tiên `V1` là bản ra mắt iOS (bản tiếp theo của Studio, trong một quý sau Android). Bản iOS đầu gồm mọi mục MVP của Android cộng RAW (rẻ trên iOS nhờ `CIRAWFilter`) và dán công thức. Lô, tông da, xuất LUT, cộng đồng, chợ creator trên iOS là `V2`.

Target iOS ghi dạng `StudioiOS/<Area>` (app package `StudioKit` ⚠ tên chốt khi dựng project). Dùng lại code Filmode iOS là ⚠ cho tới khi xong spike FMS-E12-02.

Khối lượng: 20 feature · V1 37 ngày · V2 14 ngày · tổng **51 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FMS-E12-01 | `StudioiOS/App` | App iOS Studio: bundle mới ⚠, SwiftUI, target dùng `FilmodeCoreKit`, String Catalog 7 ngôn ngữ, App Group chung, Universal Links, UTType `.flook` | — | V1 | 2 | FLC-E07-05; FLC-E02-10 | Khi build thì app chạy trên iOS 17 ⚠ và không có cảnh báo concurrency; khi mở link `filmode.app/r/1#…` trên iPhone đã cài Studio thì app mở đúng công thức |
| FMS-E12-02 | `StudioiOS/Editor` | 🧪 Spike 2 ngày khảo sát trình sửa, Match Photo và bộ nhập .xmp của Filmode iOS 1.4.4 (UIKit hay SwiftUI, Core Image hay Metal, mô hình state) ⚠; quyết định phần nào gom sang Studio, phần nào viết lại trên `LookRender` | — | V1 | 2 | FMS-E12-01 | Khi xong spike thì có danh sách file dùng lại, file viết lại và ước tính lại FMS-E12-03 đến FMS-E12-10 |
| FMS-E12-03 | `StudioiOS/Editor` | Trình sửa không phá hủy trên `LookRender`: phiên sửa, tự lưu nháp, undo/redo, trước/sau, bản sao ảo, cắt xoay; mở ảnh bằng PhotosPicker | Free | V1 | 5 | FMS-E12-02; FLC-E01-26; FLC-E06-07 | Khi kéo thanh trượt trên ảnh 48 MP ở iPhone 12 thì preview ≥ 30 fps; khi so ảnh xuất iOS với Android cùng công thức thì ΔE trung bình < 1 |
| FMS-E12-04 | `StudioiOS/Editor` | Công cụ phần Free: màu cơ bản, đường cong tổng, grain, vignette, halation cơ bản | Free | V1 | 3 | FMS-E12-03 | Khi mọi thanh trượt về 0 thì ảnh ra trùng ảnh vào; khi xuất cùng ảnh hai lần có grain thì hai file giống hệt |
| FMS-E12-05 | `StudioiOS/Editor` | Công cụ phần Pro: HSL, đường cong từng kênh, bánh xe màu, tách tông, grain nâng cao, bloom, CA; bake LUT 33³ như Android | Pro | V1 | 3 | FMS-E12-04 | Khi lưu cùng một chỉnh HSL trên iOS và Android thì hai `lut.cube` lệch nhau ΔE trung bình < 0,5 |
| FMS-E12-06 | `StudioiOS/Recipe` | Công thức trên iOS: mô hình và bảng ánh xạ dùng chung fixture với Kotlin, màn chỉnh theo nấc, 16 tông nền, 20 công thức miễn phí, thư viện Pro xem trước được | Free | V1 | 3,5 | FMS-E12-03; FLC-E01-24 | Khi chạy bộ fixture 50 công thức thì Swift và Kotlin cho cùng `look.json`; khi bật chế độ máy bay thì 20 công thức miễn phí dùng được |
| FMS-E12-07 | `StudioiOS/Recipe` | Thẻ công thức, đọc QR từ ảnh (Vision `VNDetectBarcodesRequest`), dán công thức dạng chữ (parser Swift chạy chung bộ 60 bài mẫu với Kotlin) | Free | V1 | 4 | FMS-E12-06; FMS-E02-10 | Khi chạy bộ 60 bài mẫu thì Swift nhận đúng ≥ 95% trường như Kotlin; khi quét thẻ tạo trên Android thì iPhone mở đúng công thức |
| FMS-E12-08 | `StudioiOS/Import` | Nhập .cube, .3dl, HALD, .xmp, .dng, zip qua `LUTIO`, báo cáo nhập, nhận file từ Files và share sheet; thư viện look | Free | V1 | 2 | FLC-E01-25; FMS-E12-03 | Khi nhập 20 preset mẫu trên iPhone thì báo cáo giống Android; khi mở file `.flook` nhận qua Zalo thì Studio nhập được look |
| FMS-E12-09 | `StudioiOS/Match` | Match v1 trên iOS: gom Match Photo đang có của Filmode iOS hoặc dùng bản Swift của thuật toán lõi (Điều chỉnh lõi #3); vùng mẫu; áp cho ảnh đang sửa miễn phí | Free | V1 | 2,5 | FMS-E12-02; FMS-E12-03 | Khi match cùng một cặp ảnh trên iOS và Android thì LUT lệch nhau ΔE trung bình < 1; khi chọn ảnh mẫu thì preview < 1 giây trên iPhone 12 |
| FMS-E12-10 | `StudioiOS/Raw` | RAW qua `CIRAWFilter` (DNG, ProRAW, RAW máy ảnh Apple hỗ trợ), xử lý 16-bit | Pro | V1 | 3 | FMS-E12-03 | Khi mở ProRAW 48 MP trên iPhone 15 Pro thì preview đầu < 2 giây; khi mở file CR3 của máy có trong danh sách Apple hỗ trợ thì ảnh hiện đúng |
| FMS-E12-11 | `StudioiOS/Export` | Xuất JPEG, HEIC, PNG đủ độ phân giải, giữ EXIF, xóa GPS khi chia sẻ, lưu add-only vào album | Free | V1 | 2 | FLC-E06-07; FMS-E12-03 | Khi lưu lần đầu thì iOS chỉ hỏi quyền "Chỉ thêm ảnh"; khi xuất ảnh 48 MP thì file đủ độ phân giải và không watermark |
| FMS-E12-12 | `StudioiOS/Store` | SKU và paywall Studio iOS trên `StoreCore`: trọn đời, năm, `free-tier.json` chung, điểm gọi paywall như Android, giá theo vùng | Pro | V1 | 2 | FLC-E03-09; FMS-E10-01 | Khi chụp màn hình paywall trên iPhone SE và Pro Max ở VI, EN thì checklist 4.3 đạt 100%; khi mua trên iPhone rồi cài lại thì khôi phục được qua `AppStore.sync()` |
| FMS-E12-13 | `StudioiOS/Onboarding` | Onboarding 3 bước với ảnh mẫu; hướng dẫn song ngữ | Free | V1 | 1 | FMS-E12-06 | Khi mở app lần đầu ở chế độ máy bay thì đi hết 3 bước và lưu được ảnh |
| FMS-E12-14 | `(qa)` | Kiểm thử và nộp iOS: iPhone 12, iPhone 15 hoặc 16, một máy Pro, iPhone SE; TestFlight 2 tuần; ghi chú App Review nêu khác biệt với Filmode iOS (tránh 4.3 ⚠) | — | V1 | 2 | FMS-E12-12; FLC-E05-08 | Khi nộp bản 1.0 thì có bảng kết quả trên 4 iPhone và ghi chú App Review; khi bị từ chối theo 4.3 thì có sẵn bản trả lời nêu tính năng khác biệt |
| FMS-E12-15 | `StudioiOS/Batch` | Áp hàng loạt và chuẩn hóa phơi sáng như Android | Pro | V2 | 3 | FMS-E06-03; FMS-E12-03 | Khi xuất 100 ảnh 12 MP trên iPhone 12 thì xong < 3 phút; khi app bị đóng giữa chừng thì lần mở sau tiếp tục |
| FMS-E12-16 | `StudioiOS/Batch` | Sao chép và dán thiết lập, lưới feed 3×3 | Free | V2 | 1,5 | FMS-E06-04; FMS-E12-03 | Khi dán nhóm "công thức" cho 5 ảnh thì crop của 5 ảnh giữ nguyên; khi một ảnh lệch màu thì lưới feed đánh dấu ảnh đó |
| FMS-E12-17 | `StudioiOS/Mask` | Giữ tông da bằng Vision `VNGeneratePersonSegmentationRequest` | Pro | V2 | 2,5 | FMS-E05-01; FMS-E12-03 | Khi áp công thức đỏ mạnh lên 20 ảnh chân dung thì vùng da lệch ảnh gốc ΔE < 3 như trên Android |
| FMS-E12-18 | `StudioiOS/Export` | Xuất .cube 33/65 và HALD qua `LUTIO` | Pro | V2 | 1 | FLC-E01-25; FMS-E12-11 | Khi xuất .cube trên iPhone rồi nhập lại vào Studio Android thì phần màu lệch ΔE trung bình < 1 |
| FMS-E12-19 | `StudioiOS/Community` | Link và mã chữ, công khai công thức, báo cáo, chặn người dùng (guideline 1.2 ⚠) | Free | V2 | 3 | FMS-E08-07; FLC-E02-07 | Khi công khai công thức trên iPhone thì trang web hiện công thức giống bản đăng từ Android; khi chặn một người thì không còn thấy nội dung của họ |
| FMS-E12-20 | `StudioiOS/Market` | Cửa hàng gói creator bằng StoreKit 2, tải gói đã mua | IAP | V2 | 3 | FMS-E09-06; FMS-E12-12 | Khi mua gói creator trên iPhone thì server xác minh giao dịch và look có trong thư viện ≤ 10 giây; khi cài lại app thì gói khôi phục được |

## FMS-E13 · Chất lượng và phát hành

Mục tiêu: phát hành Studio Android đúng hạn, không lệch màu giữa preview và ảnh xuất, qua được Play và beta kín.

Epic mới. Lõi đã có CI, golden test và ma trận máy (FLC-E07, FLC-E05-05); epic này chỉ gồm phần riêng của Studio: lane phát hành, golden cho 16 tông nền và 20 công thức, ảnh rất lớn, beta kín. Tách riêng để việc kiểm thử không bị cắt khi trễ hạn (báo cáo khuyên dành 20–25% công sức cho kiểm thử thiết bị).

Khối lượng: 5 feature · MVP 7,5 ngày · tổng **7,5 ngày**.

| ID | Module | Feature | Gói | Ưu tiên | Ngày | Phụ thuộc | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|---|
| FMS-E13-01 | `(ci)` | Lane phát hành Studio: tag `fms-v*` → AAB lên internal track, staged rollout; listing 7 locale qua fastlane; ảnh chụp màn hình tự động theo locale | — | MVP | 1 | FLC-E07-02; FLC-E04-04 | Khi gắn tag `fms-v1.0.0` thì AAB Studio lên internal track không cần thao tác tay; khi tiêu đề vượt 30 ký tự hoặc có từ cấm thì lane dừng |
| FMS-E13-02 | `(qa)` | Golden test Studio: 16 tông nền và 20 công thức miễn phí trên bộ ảnh chuẩn; so preview với ảnh xuất; QR round-trip của cả 20 công thức; chạy hằng đêm | — | MVP | 1,5 | FLC-E07-03; FMS-E02-03; FMS-E02-02 | Khi một PR làm một công thức lệch ΔE trung bình > 1 thì job fail kèm ảnh diff; khi giải mã QR của 20 công thức thì ra đúng `look.json` |
| FMS-E13-03 | `(qa)` | Ma trận thiết bị Studio: 8 máy của lõi; ảnh 12, 50 và 200 MP ⚠, HEIF 10-bit, Ultra HDR, DNG; bộ nhớ khi xuất; checklist trước phát hành | — | MVP | 2 | FLC-E05-05; FMS-E07-01 | Khi phát hành thì có bảng kết quả trên ≥ 8 máy; khi bất kỳ máy nào OOM với ảnh 50 MP thì bản đó không được phát hành |
| FMS-E13-04 | `:app:studio` | Hiệu năng trình sửa: Baseline Profile, macrobenchmark mở ảnh vào trình sửa; kích thước tải về ≤ 30 MB ⚠ (tông nền và công thức đóng gói dạng nén) | — | MVP | 1,5 | FLC-E05-06; FMS-E01-04 | Khi chạy macrobenchmark trên máy tầm trung chuẩn thì từ lúc chọn ảnh tới khung preview đầu p90 ≤ 1,5 giây; khi build AAB thì bundle size report không vượt ngưỡng |
| FMS-E13-05 | `(qa)` | Beta kín và tuân thủ: closed testing 2 tuần với 30–50 người (creator công thức VN, người đang dùng Fimii hoặc VSCO); kiểm paywall theo checklist 4.3; Data safety của Studio; không có quyền `READ_MEDIA_*` và `CAMERA` | — | MVP | 1,5 | FMS-E13-01; FMS-E10-03; FLC-E06-06 | Khi kết thúc beta thì có bảng lỗi đã phân loại và tỉ lệ phiên không crash ≥ 99,5%; khi kiểm merged manifest thì không có quyền đọc ảnh và quyền camera |

## Tổng theo ưu tiên

| Epic | MVP | V1 | V2 | V3 | Tổng | Số feature |
|---|---|---|---|---|---|---|
| FMS-E01 Trình chỉnh sửa film | 22,5 | 10,5 | 0 | 0 | 33 | 14 |
| FMS-E02 Công thức màu | 16 | 6,5 | 0 | 0 | 22,5 | 11 |
| FMS-E03 Nhập preset và LUT đã có | 7,5 | 1,5 | 0 | 0 | 9 | 7 |
| FMS-E04 Sao chép màu từ ảnh mẫu | 3,5 | 2,5 | 13 | 0 | 19 | 6 |
| FMS-E05 Mặt nạ và tông da | 0 | 3,5 | 11,5 | 0 | 15 | 6 |
| FMS-E06 Hàng loạt và feed | 0 | 10 | 0 | 0 | 10 | 4 |
| FMS-E07 Xuất | 4,5 | 3,5 | 0 | 0 | 8 | 6 |
| FMS-E08 Cộng đồng | 0 | 11,5 | 13 | 0 | 24,5 | 8 |
| FMS-E09 Chợ look của creator | 0 | 0 | 27 | 4 | 31 | 10 |
| FMS-E10 Kiếm tiền | 5 | 3 | 0 | 0 | 8 | 6 |
| FMS-E11 Onboarding và hướng dẫn | 1,5 | 6 | 0 | 0 | 7,5 | 3 |
| FMS-E12 iOS Studio | 0 | 37 | 14 | 0 | 51 | 20 |
| FMS-E13 Chất lượng và phát hành | 7,5 | 0 | 0 | 0 | 7,5 | 5 |
| **Tổng** | **68** | **95,5** | **78,5** | **4** | **246** | **106** |

Số feature theo ưu tiên: MVP 39, V1 40, V2 26, V3 1. Theo gói: Free 48, Pro 25, IAP 6, — 27. Có 6 spike 🧪: FMS-E01-12, FMS-E02-02, FMS-E04-04, FMS-E05-03, FMS-E09-01, FMS-E12-02.

Bảng 13 ước phần Studio Android là: công thức 4–6 tuần-người, match v1 2–3, tông da 2–4. Ở đây công thức (FMS-E02) là 22,5 ngày; match v1 và tinh chỉnh là 6 ngày cộng 3 ngày lõi (FLC-E01-18); tông da là 3,5 ngày cộng 2,5 ngày lõi (FLC-E01-22). Bản iOS 37 ngày, nằm trong khoảng 4–8 tuần-người của Bảng 13.

Phần lõi Studio dùng lại (không tính ở trên): định dạng look và codec QR (FLC-E01-01..03), bộ nhập (FLC-E01-04, -05, -08), pipeline CPU và GPU (FLC-E01-06, -09..-15), bộ chọn look (FLC-E01-17), Match v1 (FLC-E01-18), xuất LUT (FLC-E01-19), tông da (FLC-E01-22), thư viện và deep link (FLC-E02-01, -02, -04, -08, -09), billing và paywall (FLC-E03-03..-10), `NameGuard` và lint (FLC-E04-02, -03), listing (FLC-E04-04), thiết bị và đo lường (FLC-E05-04..-09), media (FLC-E06-01..-04, -06), CI và golden (FLC-E07-01..-03, -06), backend và link look (FLC-E08-02, -03); phía iOS là FLC-E01-24..26, FLC-E02-07, -10, FLC-E03-09, FLC-E05-08, FLC-E06-07, FLC-E07-05.

## Điều chỉnh lõi

Các thay đổi Studio cần ở lõi. Người điều phối đưa vào `filmode-core.md` và `filmode-core-backlog.csv`; ngày công dưới đây là ước tính của lõi, **không** tính vào tổng của Studio.

| # | Lõi cần gì | Feature lõi liên quan | Vì sao Studio cần | Ước tính lõi | Cần xong trước |
|---|---|---|---|---|---|
| 1 | Thêm ba trường tùy chọn vào `adjust`: `colorDepth` 0–1 (độ sâu màu: giảm độ sáng màu có độ bão hòa cao), `colorDepthBlue` 0–1 (như trên, chỉ dải xanh lam), `toneRange` 0–1 (dải động: vai mềm ở vùng sáng). Thêm khóa ngắn vào `share-keys-v1.json` (chỉ thêm, không đổi khóa cũ); cài trong pass `adjust` của GPU, pipeline CPU, WebGL2 và Metal; fixture chung | FLC-E01-01, FLC-E01-03, FLC-E01-06, FLC-E01-11, FLC-E01-23, FLC-E01-26 | Ba tham số của công thức kiểu máy ảnh (Color Chrome, Color Chrome Blue, Dynamic Range) không biểu diễn được bằng trường hiện có. Nếu để trong `x-fms` thì Filmode và FilCam sẽ bỏ qua, và công thức quét QR ra màu khác Studio. Thêm trường tùy chọn không tăng `formatVersion` (mục 5.3 của lõi) | Android 1,5; web 0,5; iOS 0,5 | FMS S2 (18/1/2027); phần iOS trước I1 |
| 2 | Tông nền dùng chung: 16 look `fm:base/<slug>` do Studio định nghĩa được đóng gói trong cả ba app (khoảng 1,5 MB nén ⚠), hoặc tải theo yêu cầu từ `filmode.app/b/<slug>@<rev>.flook` khi app thiếu | FLC-E02-01, FLC-E02-08 | Công thức Studio chia sẻ bằng QR tham chiếu tông nền bằng `base.ref`. App nào nhận QR mà không có tông nền đó thì không render được | 1,5 | FMS S2 |
| 3 | Match v1 bản Swift trong `LUTIO`, chạy chung fixture với FLC-E01-18 | FLC-E01-18, FLC-E01-25 | FLC-E01-25 chưa có Match. Studio iOS và Filmode iOS phải cho cùng kết quả với Android; Match Photo đang chạy trên Filmode iOS có thể khác thuật toán ⚠ | iOS 2 | FMS I4 (17/5/2027) |
| 4 | Tôn trọng `license: personal`: FLC-E08-03 từ chối tải lên công khai look có `license` là `personal` hoặc `unknown` kèm `lut.cube`; FLC-E02-09 chỉ chia sẻ trong máy | FLC-E08-03, FLC-E02-09 | Chặn phía server để LUT mua từ Gumroad, Etsy hay gói creator không bị phát tán qua link công khai, kể cả từ bản app cũ | 0,5 | FMS S9 |
| 5 | Đăng ký lược đồ `x-fms` trong `spec/look/` (khối `recipe`, `crop`, `mask`, `packId`, `publishedId`) để fixture Kotlin, Swift, JS kiểm được việc giữ nguyên khi ghi lại | FLC-E01-02, FLC-E07-04 | Filmode và FilCam phải giữ nguyên `x-fms` khi sửa rồi lưu một look của Studio | 0,5 | FMS S1 |
| 6 | Thêm giá trị `text` cho `origin.importedFrom` | FLC-E01-01 | Đánh dấu công thức tạo từ bài viết dạng chữ (FMS-E02-11) | 0 (một giá trị enum) | FMS S7 |
| 7 | Trang `/r` của FLC-E02-08 đọc `x-fms.recipe` để hiện tham số theo thang công thức; nhận gợi ý `?app=fms` | FLC-E02-08 | Người chưa cài app quét QR thẻ công thức phải thấy đúng các nấc như trên thẻ | web 0,5 | FMS S4 |
| 8 | Chưa cần làm: nếu FilCam cần mở DNG trong trình chỉnh clip thì chuyển `:studio:raw` vào `:core:media` | — | Theo nguyên tắc 1.1 của lõi: app thứ hai cần thì chuyển vào lõi | — | — |

Điều chỉnh #1 và #2 **chặn MVP của Studio**. Tổng lõi thêm khoảng 7,5 ngày (Android 4, web 1, iOS 2,5). Ngoài ra, cut-line "1 dev Android" của lõi có dời FLC-E01-18 (Match v1) sang V1; nếu làm vậy thì MVP của Studio mất Match v1 (FMS-E04-01, -02) và phải dời theo ⚠.

## Nội dung

Không tính vào ngày công dev. Ngày nội dung là ước tính cho một người dựng look có kinh nghiệm (Resolve hoặc Lightroom, ColorChecker), gồm dựng, ảnh mẫu, đặt tên hai ngôn ngữ và chạy lint tên.

| Nội dung | Số lượng | Ngày nội dung (ước) | Cần trước |
|---|---|---|---|
| Tông nền `fm:base/<slug>` (LUT 33³ tự dựng từ ColorChecker và ramp xám, manifest nguồn gốc `owned`) | 16 | 8 | S2 (MVP) |
| Công thức Free (tên VI/EN tự đặt, mô tả, 2 ảnh mẫu mỗi công thức) | 20 | 5 | S4 (MVP) |
| Công thức Pro lúc ra mắt, 6 nhóm | 60 | 12 | S5 (MVP) |
| Công thức Pro thêm ở V1 | 40 | 8 | Q2/2027 |
| Bộ sưu tập theo mùa (Hè, Mùa cưới, Trung thu, Noel, Tết Nguyên đán), 6–8 công thức mỗi bộ | 5 bộ | 8 | Trước từng mùa |
| Bộ 60 bài công thức dạng chữ làm fixture cho parser (tự viết theo khuôn các bài phổ biến, không chép nguyên văn) | 60 | 1,5 | S7 |
| Bài hướng dẫn song ngữ "làm màu film X trên điện thoại" (VI, EN) | 10 | 5 | V1 (S11) |
| Nội dung trang SEO cho 30 công thức đầu (mô tả, ảnh trước/sau, VI và EN) | 30 | 4 | V1 (S10) |
| Ảnh mẫu tự sở hữu cho onboarding và App Review | 3 | 0,5 | S6 |
| Tài liệu cho creator (hướng dẫn dựng gói, tiêu chuẩn ảnh mẫu, chính sách tên) | 1 bộ | 2 | V2 |
| **Tổng** | | **54** | |

Chụp ảnh mẫu nên dùng người mẫu và địa điểm có giấy đồng ý, vì ảnh mẫu xuất hiện trên thẻ công thức, trang web và listing.

## Chỗ lệch so với Bảng 11

| Mục trong báo cáo | Báo cáo | Backlog Studio | Lý do |
|---|---|---|---|
| B4.1 Match v1 | MVP của Studio | Thuật toán ở lõi (FLC-E01-18); Studio làm UI và gói (FMS-E04-01, -02) | FMD A11.1 và FCM F6.2 cũng dùng (lõi mục 9) |
| B4.1 Gói của Match | "Xem trước Free; lưu thành look là Pro" | Áp match cho ảnh đang sửa và xuất ảnh đó là Free; lưu thành look để dùng lại, áp lô, xuất LUT là Pro | Rõ ràng hơn ranh giới "xem trước": người dùng miễn phí vẫn có ảnh kết quả, giá trị Pro là dùng lại. Khớp cách Filmode iOS đang bán "biến Match thành LUT" |
| B5.1 Bảo vệ tông da | Ở app | Tách nền và pass trộn ở lõi (FLC-E01-22); Studio làm UI (FMS-E05-01, -02) | Filmode dùng cùng tách nền cho photobooth |
| B7.1 Ultra HDR | Ở app | Ở lõi (FLC-E06-04); Studio chỉ nối vào luồng xuất (FMS-E07-02) | FMD A2.4 cũng dùng |
| B1.2, B1.3 "Free một phần/Pro" | Một dòng | Tách: FMS-E01-05/06 Free và 07 Pro; FMS-E01-09 Free và 10 Pro | Quy ước README chung: phần Free và phần trả phí tách dòng |
| B2.1 Mô hình công thức | Chỉ ở app | Cần ba trường `adjust` mới và tông nền dùng chung ở lõi (Điều chỉnh lõi #1, #2) | Để QR công thức ra cùng màu trong cả ba app |
| B8.1 Mã chữ | Ở app | Mã chữ là `id` 8 ký tự của link look cloud (FLC-E08-03) | Một hệ mã cho cả ba app |
| B10.2 Studio Pro | Trọn đời và năm | Giữ đúng: không có gói tháng | Bảng 8 chỉ có $19.99 trọn đời và $14.99/năm; gói tháng làm loãng giá neo trọn đời |
| — | — | Epic mới FMS-E12 (iOS), FMS-E13 (chất lượng) | Xem [Tổng quan epic](#tổng-quan-epic) |
| — | — | Thêm FMS-E11-01 (lần mở đầu) vào MVP | B11 toàn bộ là V1, nhưng MVP vẫn cần một luồng lần đầu có ảnh mẫu cho App Review và người chưa muốn cấp ảnh |

## Lộ trình sprint

Bảng 13 đặt Studio Android ở Q1/2027 và iOS ở Q2/2027. Sprint 2 tuần. Lõi phải xong trước S1 các mục MVP liên quan và các mục `V1` "cần cho FMS" ở [lộ trình lõi](../filmode-core.md#8-lộ-trình) (FLC-E01-05, -07, -08, FLC-E02-08, FLC-E06-04, FLC-E08-02), cộng Điều chỉnh lõi #1 và #2 trước S2.

### Android MVP (Q1/2027)

| Sprint | Ngày | Mục tiêu | Feature | Ngày công |
|---|---|---|---|---|
| S1 | 4/1 – 15/1/2027 | Khung app, phiên sửa, preview, mô hình công thức, spike thang, lane phát hành | FMS-E01-01, FMS-E01-02, FMS-E01-04, FMS-E02-01, FMS-E02-02 🧪, FMS-E13-01 | 11,5 |
| S2 | 18/1 – 29/1/2027 | Công cụ màu Free, grain, tông nền và 20 công thức, màn chỉnh công thức | FMS-E01-03, FMS-E01-05, FMS-E01-06, FMS-E01-09, FMS-E02-03, FMS-E02-04 | 13 |
| S3 | 1/2 – 12/2/2027 (nghỉ Tết Nguyên đán khoảng 4–10/2) | Lưu công thức, nhập preset/LUT, thư viện, cắt xoay | FMS-E02-05, FMS-E03-01, FMS-E03-02, FMS-E03-03, FMS-E03-04, FMS-E01-11 | 9,5 |
| S4 | 15/2 – 26/2/2027 | Công cụ Pro, bake LUT, thẻ công thức QR, đọc QR, bảo vệ LUT | FMS-E01-07, FMS-E01-08, FMS-E01-10, FMS-E02-07, FMS-E02-08, FMS-E03-05 | 12 |
| S5 | 1/3 – 12/3/2027 | Match v1, xuất, Ultra HDR, `.flook`, thư viện Pro, SKU, gói Free; build beta | FMS-E04-01, FMS-E04-02, FMS-E07-01, FMS-E07-02, FMS-E07-03, FMS-E02-06, FMS-E10-01, FMS-E10-02 | 11 |
| S6 | 15/3 – 26/3/2027 | Paywall, đo phễu, onboarding, golden, ma trận máy, hiệu năng; beta kín chạy song song trên bản S5 | FMS-E10-03, FMS-E10-04, FMS-E11-01, FMS-E13-02, FMS-E13-03, FMS-E13-04, FMS-E13-05 | 11 |
| **Tổng** | | | | **68** |

Ghi chú lịch:
- Beta kín (FMS-E13-05) chạy 15/3–26/3 trên bản build cuối S5, song song với S6. Phát hành staged rollout 29/3–31/3/2027 (20% → 100% trong tuần đầu tháng 4), kịp mốc Q1.
- S3 trùng Tết Nguyên đán (mùng 1 là 6/2/2027), nên chỉ khoảng 60% công suất.
- Việc không tính ngày công nhưng phải xong trước S5: 16 tông nền, 20 công thức Free, 60 công thức Pro, ảnh mẫu, chuỗi 7 ngôn ngữ, metadata store, ảnh chụp màn hình (mục [Nội dung](#nội-dung)).

### Android V1 (Q2/2027)

| Sprint | Ngày | Mục tiêu | Feature | Ngày công |
|---|---|---|---|---|
| S7 | 5/4 – 16/4/2027 | Sửa lỗi sau ra mắt (khoảng nửa sprint); thử giá; dán công thức; look từ app anh em | FMS-E10-05, FMS-E02-10, FMS-E02-11, FMS-E03-06, FMS-E03-07 | 7 |
| S8 | 19/4 – 30/4/2027 | Hàng loạt và feed | FMS-E06-01, FMS-E06-02, FMS-E06-03, FMS-E06-04 | 10 |
| S9 | 3/5 – 14/5/2027 | Link và mã chữ, xuất bản công khai, xuất LUT, mở trong Filmode/FilCam | FMS-E08-01, FMS-E08-02, FMS-E08-03, FMS-E07-04, FMS-E07-05 | 9 |
| S10 | 17/5 – 28/5/2027 | Trang web công thức cho SEO, bộ sưu tập theo mùa, gói lẻ | FMS-E08-04, FMS-E02-09, FMS-E10-06 | 9 |
| S11 | 31/5 – 11/6/2027 | Tông da, tinh chỉnh match, gợi ý phong cách và cảnh, hướng dẫn | FMS-E05-01, FMS-E05-02, FMS-E04-03, FMS-E11-02, FMS-E11-03 | 12 |
| S12 | 14/6 – 25/6/2027 | RAW | FMS-E01-12 🧪, FMS-E01-13, FMS-E01-14, FMS-E07-06 | 11,5 |
| **Tổng** | | | | **58,5** |

Thứ tự V1 theo giá trị: dán công thức và hàng loạt trước (hai việc người dùng xin nhiều nhất), rồi chia sẻ công khai và trang SEO (kênh khám phá), sau cùng RAW. Nếu KPI 8 tuần chưa đạt ngưỡng "đẩy mạnh" (README mục 10) thì dừng sau S10 và dồn sức cho listing, giá.

### iOS (Q2/2027)

| Sprint | Ngày | Mục tiêu | Feature | Ngày công |
|---|---|---|---|---|
| I1 | 5/4 – 16/4/2027 | Dựng app, khảo sát code Filmode iOS, trình sửa | FMS-E12-01, FMS-E12-02 🧪, FMS-E12-03 | 9 |
| I2 | 19/4 – 30/4/2027 | Công cụ Free, công thức | FMS-E12-04, FMS-E12-06 | 6,5 |
| I3 | 3/5 – 14/5/2027 | Công cụ Pro, thẻ QR, dán công thức | FMS-E12-05, FMS-E12-07 | 7 |
| I4 | 17/5 – 28/5/2027 | Nhập, Match v1, xuất | FMS-E12-08, FMS-E12-09, FMS-E12-11 | 6,5 |
| I5 | 31/5 – 11/6/2027 | RAW, StoreKit, onboarding; TestFlight | FMS-E12-10, FMS-E12-12, FMS-E12-13 | 6 |
| I6 | 14/6 – 25/6/2027 | Kiểm thử 4 iPhone, nộp App Review, trả lời review | FMS-E12-14 | 2 |
| **Tổng** | | | | **37** |

Nộp App Review chậm nhất 18/6/2027; ra mắt dự kiến 28/6–2/7/2027 tùy thời gian duyệt ⚠. Phần iOS của lõi (22,5 ngày) phải xong trong T2–T3/2027, trước I1.

### V2 và V3 (nửa cuối 2027 trở đi)

V2 (78,5 ngày) chỉ mở khi đạt tiêu chí "đẩy mạnh" ở README mục 10. Thứ tự đề xuất: (1) cộng đồng khám phá, remix, kiểm duyệt (FMS-E08-05..08, 13 ngày) vì chợ creator cần nó trước; (2) spike luồng tiền FMS-E09-01 và rà soát pháp lý; (3) chợ creator FMS-E09-02..09 (25 ngày); (4) mask cục bộ FMS-E05-03..06 (11,5 ngày); (5) Match v2 FMS-E04-04..06 (13 ngày) nếu spike giấy phép đạt; (6) iOS V2 FMS-E12-15..20 (14 ngày). V3 (4 ngày) là gói mang thương hiệu creator (FMS-E09-10), chỉ làm khi đã có creator bán được hàng.

## Nhân sự

**Android MVP (Q1/2027): cần 2 dev Android.** MVP là 68 ngày trong 6 sprint (12 tuần). Một dev có tối đa 60 ngày danh nghĩa trong 12 tuần, thực tế khoảng 45–50 ngày vì còn sửa lỗi Filmode sau đợt Tết, review code và làm việc với nội dung. Vì vậy:
- **2 dev: vừa lịch.** Mỗi sprint dùng khoảng 55–60% công suất cho backlog; phần còn lại cho tích hợp UI, sửa lỗi beta và 20–25% kiểm thử thiết bị như Bảng 13 khuyên. Gợi ý chia: dev A làm trình sửa, preview, xuất, hiệu năng (FMS-E01, FMS-E07, FMS-E13); dev B làm công thức, nhập, match, paywall, onboarding (FMS-E02, FMS-E03, FMS-E04, FMS-E10, FMS-E11). Trong S1–S2 dev B có thể còn bận Filmode; khi đó dồn FMS-E13-01 và FMS-E02-02 sang dev A.
- **1 dev: không vừa Q1.** Chọn một trong hai: (a) lùi ra mắt khoảng 4 tuần sang cuối T4/2027 và lùi iOS tương ứng; hoặc (b) cắt khoảng 9,5 ngày sang V1: FMS-E01-07 (HSL, bánh xe màu, 4,5), FMS-E01-10 (1), FMS-E07-02 (Ultra HDR, 1), FMS-E01-03 phần bản sao ảo (khoảng 0,5), FMS-E13-04 phần Baseline Profile (khoảng 1) và FMS-E02-08 (đọc QR từ ảnh, 1,5; vẫn mở được bằng link). Phương án (b) còn khoảng 58,5 ngày, nên thực tế cần kết hợp (a) và (b). **Không được cắt:** FMS-E02-07 (thẻ QR, là vòng lặp chia sẻ), FMS-E03-05 (bảo vệ LUT người khác), FMS-E10-02 và FMS-E10-03 (gói Free cố định, paywall tuân thủ), FMS-E13-02 (golden).

**Android V1 (Q2/2027): 1 dev Android** cho 50,5 ngày Android và QA trong 12 tuần, cộng khoảng 8 ngày web và backend (FMS-E08-02, FMS-E08-04). Phần web và backend do dev Android làm hoặc thuê một dev fullstack bán thời gian. Dev Android thứ hai trở lại FilCam (Q2–Q3/2027).

**iOS (Q2/2027): 1 dev iOS.** 37 ngày Studio iOS trong 12 tuần, sau khi phần iOS của lõi (22,5 ngày) xong trong T2–T3/2027. Nếu spike FMS-E12-02 cho thấy code Filmode iOS không dùng lại được thì trình sửa iOS (FMS-E12-03..05) tăng khoảng 5 ngày và ra mắt iOS lùi sang giữa T7/2027 ⚠.

**V2 (nửa cuối 2027):** 78,5 ngày, gồm 23 ngày web và backend cho chợ creator và kiểm duyệt. Cần 1 dev Android và 1 dev fullstack trong khoảng một quý, cộng 14 ngày iOS. Chỉ mở khi đạt tiêu chí "đẩy mạnh".

