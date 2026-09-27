# Biến cảm biến iPhone thành doanh thu châu Âu

Tiền trong mảng app iPhone dùng camera và cảm biến đang dồn vào các app "chụp là có kết quả" chạy trên cloud, chưa dồn vào app offline. Theo ước tính Sensor Tower (toàn cầu, chỉ iOS, tháng 8/2026), **PictureThis thu khoảng 9 triệu USD/tháng, CamScanner 8 triệu, iScanner 4 triệu**. Riêng 19 app quét tài liệu cộng lại đạt khoảng **22,1 triệu USD/tháng**, bể doanh thu lớn nhất. Trong khi đó các app offline thuần như Seek, Merlin hay PlantNet gần như không có doanh thu ([Sensor Tower](https://app.sensortower.com/overview/388627783?country=US)). Người dùng trả tiền cho **đầu ra**, không trả cho khoảnh khắc chụp: định dạng xuất (Office, OBJ/STL/DXF), OCR và PDF tìm kiếm được, số lượt không giới hạn, bỏ watermark, khóa bảo mật, lớp AI hoặc chuyên gia. Riêng LiDAR/3D kiếm tiền theo kiểu B2B, với magicplan tới $899.99/năm và Polycam Business $400/người/năm. Từ 2024 đến 2026, nhu cầu tìm kiếm tăng thật ở AI calorie/food scan, ở OCR ("ocr app" +643%, "offline ocr" mới xuất hiện) và ở LiDAR/floor plan ("lidar app" +475%, "floor plan app" +238%). Ngược lại, plant ID, QR và dịch ảnh đang giảm ở Mỹ, trên toàn cầu và ở cả sáu thị trường EU ưu tiên. Với một indie developer Việt Nam nhắm toàn cầu và ưu tiên châu Âu, hướng tốt nhất là **app dọc gắn với một quy trình cụ thể của châu Âu, dùng xử lý on-device làm lời hứa về niềm tin**. Theo thứ tự ưu tiên: (1) sổ chứng từ riêng tư cho UK Making Tax Digital và E-Rechnung Đức; (2) máy quét nhãn thành phần/dị ứng dựa trên OCR, chạy offline bằng mọi ngôn ngữ EU; (3) quét phòng bằng LiDAR để kiểm kê đồ đạc và lập biên bản tình trạng nhà thuê; sau đó mới đến scan-to-print 3D và app đồng hành hái nấm theo nguyên tắc "an toàn trước". Ở EU nên dùng Apple IAP: phí chỉ 15% với Small Business Program theo điều khoản DMA hiệu lực từ 1/10/2026. Cần khai DSA trader status trước khi nộp, và tránh các danh mục bão hòa mà Guideline 4.3 đã siết từ 8/6/2026. Người đọc nên nhớ bốn giới hạn: mọi số tải và doanh thu là ước tính đã làm tròn; không có số riêng cho từng nước châu Âu; không có volume và CPC từ Keyword Planner; dữ liệu Google Trends 2025–2026 bị nhiễu. Search Console chỉ dùng được sau khi đã có website riêng.

## Bốn giới hạn dữ liệu cần biết trước khi đọc bảng số

Toàn bộ dữ liệu được thu từ nguồn công khai ngày **27/9/2026**, và có bốn giới hạn chi phối cách đọc.

**Thứ nhất, số tải và doanh thu từ trang overview công khai của Sensor Tower là ước tính toàn cầu, chỉ tính App Store iOS (iPhone+iPad).** Đó là doanh thu gộp trước phí Apple của tháng 8/2026. Đổi tham số quốc gia không làm đổi con số, nên không có số riêng cho Mỹ, Việt Nam hay từng nước châu Âu ([Sensor Tower – CamScanner](https://app.sensortower.com/overview/388627783?country=US)). Số được làm tròn đến một chữ số có nghĩa. Mức sàn 1.000 lượt tải hoặc $1.000 được ghi là "<5k\*" hoặc "<$5k\*", nghĩa là không đáng kể hoặc không đo được. Sensor Tower còn có xu hướng ước tính thấp các app tăng nhanh có bán qua web. Ví dụ, Cal AI được ước tính $2M/tháng (khoảng $24M/năm), trong khi công ty báo doanh thu năm trên $30M ([TechCrunch](https://techcrunch.com/2026/03/02/myfitnesspal-has-acquired-cal-ai-the-viral-calorie-app-built-by-teens/)). Mảng LiDAR/3D không có ước tính nào từ Sensor Tower hay Appfigures, nên chỉ dùng được số lượt đánh giá và thứ hạng.

**Thứ hai, không truy cập được Google Keyword Planner, Semrush, Ahrefs, Ubersuggest hay WordStream.** Các công cụ này đều đòi tài khoản, reCAPTCHA hoặc trả lỗi 403. Vì vậy **không có volume tuyệt đối, CPC hay độ khó SEO của Google cho bất kỳ từ khóa nào** ([Google Ads Help](https://support.google.com/google-ads/answer/3022575?hl=en)). Dải volume Mỹ trong báo cáo được quy đổi từ Google Trends bằng đúng một con số công khai của Semrush ("qr code scanner" ≈9.900 lượt/tháng), nên có thể lệch 2–3 lần ([FreeQR](https://freeqr.com/blog/qr-code-scanner-app)).

**Thứ ba, Google Trends 2025–2026 bị nhiễu nặng.** Nhiều truy vấn dạng "… app" cùng tăng từ cuối 2025 rồi vọt lên đỉnh vào tháng 3–6/2026, kể cả các từ khóa đối chứng không liên quan. Ví dụ, chỉ số "document scanner" ở Mỹ đi từ 53 lên 100, 93, 98 rồi rơi về 41. Một nhà phân tích gọi hiện tượng này là "Everything is trending" ([B2B Marketing Shots](https://b2b.marketingexpertshub.com/p/google-trends-is-broken-why-does)). Do đó, mọi mức tăng trong báo cáo được so với mức nền đối chứng: khoảng **+62% ở Mỹ và +166% toàn cầu sau 2 năm**. Từ khóa được gắn nhãn "spike-inflated" khi đỉnh tháng 4–6/2026 cao gấp 3 lần trở lên so với trung vị trước đó ([Google Trends](https://trends.google.com/trends/explore?date=2021-01-01%202026-09-20&geo=US&q=document%20scanner)). Dữ liệu phía Apple cũng hỏng trong cùng giai đoạn: từ 29/9/2025, số từ khóa Mỹ có Apple Ads popularity trên 5 giảm **77,4%** ([ASO.dev](https://aso.dev/blog/apple-ads-popularity-massive-drop/)).

**Thứ tư, Google Search Console chỉ báo cáo cho website đã xác minh quyền sở hữu.** Dự án hiện **không có dữ liệu GSC nào**, và công cụ này chỉ hữu ích sau khi đã có landing page ([Google: About Search Console](https://support.google.com/webmasters/answer/9128668?hl=en)).

Quy ước số: giá giữ đúng định dạng hiển thị trên từng storefront ($39.99, £34.99, 34,99 €, 689.000₫). Các số khác dùng quy ước Việt Nam, tức dấu chấm phân cách hàng nghìn và dấu phẩy thập phân.

| Nguồn | Đo gì | Phạm vi và ngày lấy | Giới hạn khi đọc |
|---|---|---|---|
| [Sensor Tower – overview công khai](https://app.sensortower.com/overview/388627783?country=US) | Lượt tải, doanh thu gộp "last month" | Toàn cầu, **chỉ iOS**, tháng 8/2026; lấy 27/9/2026 | Ước tính làm tròn; không có số theo nước; "<5k\*"/"<$5k\*" là mức sàn; có thể thấp hơn thực tế với app bán qua web |
| [Apple RSS top-100](https://itunes.apple.com/de/rss/topgrossingapplications/limit=100/genre=6007/json) | Hạng Top Free/Top Grossing theo danh mục | iPhone; 12 storefront × 14 danh mục (camera/OCR), 5 storefront × 8 danh mục (LiDAR); ảnh chụp một ngày 27/9/2026 | Chỉ top 100; không có lịch sử, không có iPad |
| [iTunes Lookup API](https://itunes.apple.com/lookup?id=388627783&country=vn) | Điểm và số lượt đánh giá trọn đời theo storefront | 27/9/2026 | Chỉ là proxy độ phổ biến, không phải lượt tải |
| [Trang App Store theo storefront](https://apps.apple.com/de/app/id1199564834) | Giá IAP | US, GB, DE (đại diện EU), VN; 27/9/2026 | Tối đa khoảng 10 IAP; không hiện chu kỳ nếu tên IAP không ghi; GBP/EUR đã gồm VAT; chưa lấy FR/IT/ES |
| [Google Trends](https://trends.google.com/trends/explore?date=2021-01-01%202026-09-20&geo=US&q=plant%20identifier) | Chỉ số tương đối 0–100 | Khoảng 300 chuỗi, 1/2021–9/2026, US/WW/VN/GB/DE/FR/ES/IT/NL | Không phải số lượt tìm; nhiễu 2025–26; "lidar" bị game Arc Raiders làm lệch |
| Keyword Planner, Semrush, Ahrefs, Ubersuggest | Volume tuyệt đối, CPC, độ khó SEO | Thử ngày 27/9/2026 | **Không truy cập được**; volume và CPC ghi n/a |
| [Apple Ads popularity / công cụ ASO](https://aso.dev/blog/apple-ads-popularity-massive-drop/) | Độ phổ biến từ khóa App Store | Chỉ vài head term có số công khai (Appfigures, Sonar) | Từ 29/9/2025 đa số từ khóa tầm trung rơi về mức sàn "5" |
| [Google Search Console](https://support.google.com/webmasters/answer/7576553?hl=en) | Click, impression, CTR, vị trí | Chỉ property đã xác minh | Chưa có website nên chưa có dữ liệu; impression bị thổi phồng từ 13/5/2025 đến 3/4/2026 |
| [RevenueCat SOSA 2026](https://www.revenuecat.com/state-of-subscription-apps), [Adapty 2026](https://adapty.io/state-of-in-app-subscriptions/) | Chuẩn chuyển đổi, giá, LTV | Dữ liệu 2025 (115.000+ app / 16.000 app) | Chỉ có số theo vùng "Tây Âu", không theo từng nước |
| [StatCounter](https://gs.statcounter.com/os-market-share/mobile/europe) | Thị phần iOS | Lượt xem trang web di động, 8/2026 | Không phải installed base; số của một tháng có thể lệch vài điểm |

## Quét tài liệu dẫn đầu doanh thu, còn offline chưa phải động cơ kiếm tiền

### Hai mươi lăm app camera kiếm nhiều nhất trên iOS

Trong 108 app camera và thị giác được theo dõi, **nhóm quét tài liệu/OCR là bể doanh thu lớn nhất, khoảng 22,1 triệu USD/tháng từ 19 app**. Tiếp theo là plant ID (10,7 triệu), AI calorie qua ảnh (6 triệu) và dịch qua camera (5,8 triệu) ([Sensor Tower](https://app.sensortower.com/overview/1252497129?country=US)).

Bảng dưới xếp hạng theo doanh thu. Tên app dẫn tới trang Sensor Tower tương ứng. Cột "Offline" tổng hợp từ mô tả App Store và tài liệu của từng hãng ([Genius Scan SDK](https://geniusscansdk.com/legal/privacy-security/), [Yuka Help](https://help.yuka.io/l/en/article/ur4x5k32qg-database-in-offline-mode), [CNBC về Cal AI](https://www.cnbc.com/2025/09/06/cal-ai-how-a-teenage-ceo-built-a-fast-growing-calorie-tracking-app.html)).

| # | App | Phân khúc | Nhà phát hành (trụ sở) | Tải WW iOS T8/2026 | Doanh thu WW iOS T8/2026 | Offline |
|---|---|---|---|---|---|---|
| 1 | [MyFitnessPal](https://app.sensortower.com/overview/341232718?country=US) | Calorie lai (có chụp ảnh) | MyFitnessPal (US) | 600k | $12M | n/a |
| 2 | [PictureThis](https://app.sensortower.com/overview/1252497129?country=US) | Plant ID | Glority (CN) | 700k | $9M | n/a, suy ra cloud |
| 3 | [CamScanner](https://app.sensortower.com/overview/388627783?country=US) | Quét tài liệu/OCR | INTSIG (CN) | 3M | $8M | n/a |
| 4 | [Yazio](https://app.sensortower.com/overview/946099227?country=US) | Calorie lai | YAZIO (DE) | 500k | $5M | n/a |
| 5 | [iScanner](https://app.sensortower.com/overview/1040093707?country=US) | Quét tài liệu/OCR | BPMobile (US) | 300k | $4M | Có (quét, sửa, xem) |
| 6 | [Scanner App – Scan PDF & Docs](https://app.sensortower.com/overview/1568660349?country=US) | Quét tài liệu/OCR | TapSuite (TR) | 800k | $3M | n/a |
| 7 | [Translate Now](https://app.sensortower.com/overview/1348028646?country=US) | Dịch qua camera | Air Apps (PT) | 500k | $3M | Có chế độ offline |
| 8 | [Adobe Scan](https://app.sensortower.com/overview/1199564834?country=US) | Quét tài liệu/OCR | Adobe (US) | 700k | $2M | Mâu thuẫn |
| 9 | [Cal AI](https://app.sensortower.com/overview/6480417616?country=US) | AI calorie qua ảnh | Viral Development (US) | 500k | $2M | Không (LLM cloud) |
| 10 | [Foodvisor](https://app.sensortower.com/overview/1064020872?country=US) | AI calorie qua ảnh | Foodvisor (FR) | 400k | $2M | n/a |
| 11 | [Yuka](https://app.sensortower.com/overview/1092799236?country=US) | Quét mã vạch sản phẩm | Yuca (FR) | 800k | $1M | Chỉ bản Premium |
| 12 | [Traductor GO](https://app.sensortower.com/overview/1570134612?country=US) | Dịch qua camera | MATdev | 300k | $1M | Có chế độ offline |
| 13 | [Lose It!](https://app.sensortower.com/overview/297368629?country=US) | Calorie lai | FitNow (US) | 100k | $1M | n/a |
| 14 | [iTranslate](https://app.sensortower.com/overview/288113403?country=US) | Dịch qua camera | Mosaic (US) | 100k | $900k | Một phần |
| 15 | [PlantIn](https://app.sensortower.com/overview/1527399597?country=US) | Plant ID | Vortemol (UA) | 90k | $900k | Tuyên bố có (nấm) |
| 16 | [Gauth](https://app.sensortower.com/overview/1542571008?country=US) | Giải bài tập | GauthTech (SG) | 400k | $800k | n/a |
| 17 | [Calo](https://app.sensortower.com/overview/6447434453?country=US) | AI calorie qua ảnh | Next Vision (CN) | 300k | $800k | n/a |
| 18 | [Rock Identifier](https://app.sensortower.com/overview/1546796934?country=US) | Nhận diện đá | Next Vision (CN) | 200k | $800k | Suy ra cloud |
| 19 | [Lifesum](https://app.sensortower.com/overview/286906691?country=US) | Calorie lai | Lifesum (SE) | 80k | $800k | n/a |
| 20 | [ScanGuru](https://app.sensortower.com/overview/1040149161?country=US) | Quét tài liệu/OCR | GM UniverseApps (UA) | <5k\* | $800k | Có (lưu cục bộ) |
| 21 | [QR Code Reader](https://app.sensortower.com/overview/1226650677?country=US) | QR/mã vạch | Air Apps (PT) | 80k | $700k | Suy ra on-device |
| 22 | [Scan Shot PDF Scanner](https://app.sensortower.com/overview/1575194801?country=US) | Quét tài liệu/OCR | Scanner App PDF Tool (ES) | 20k | $700k | n/a |
| 23 | [CoinSnap](https://app.sensortower.com/overview/1634551626?country=US) | Nhận diện xu | Next Vision (CN) | 300k | $600k | Suy ra cloud |
| 24 | [Scanner Pro](https://app.sensortower.com/overview/333710667?country=US) | Quét tài liệu/OCR | Readdle (UA) | 40k | $600k | n/a |
| 25 | [Tiny Scanner](https://app.sensortower.com/overview/595563753?country=US) | Quét tài liệu/OCR | TinyWork (CN) | <5k\* | $600k | n/a |

Xếp theo lượt tải, bức tranh khác hẳn. Lượt tải và doanh thu tách rời nhau ở các app miễn phí của big tech hoặc tổ chức phi lợi nhuận. Google app (chứa Lens) có 8 triệu lượt tải/tháng nhưng chỉ khoảng $200k doanh thu. Google Translate có 2 triệu lượt tải nhưng doanh thu ở mức sàn. Merlin, Papago, PlantNet, Seek và Be My Eyes cũng vậy ([Sensor Tower – Google Translate](https://app.sensortower.com/overview/414706506?country=US)).

| # | App | Tải WW iOS T8/2026 | Doanh thu | Ghi chú |
|---|---|---|---|---|
| 1 | [Google app (Lens)](https://app.sensortower.com/overview/284815942?country=US) | 8M | $200k | #1 Free Utilities ở US, DE, FR, NL, DK, FI |
| 2 | [CamScanner](https://app.sensortower.com/overview/388627783?country=US) | 3M | $8M | 403.823 lượt đánh giá ở VN |
| 3 | [Google Translate](https://app.sensortower.com/overview/414706506?country=US) | 2M | <$5k\* | #1 Free Reference ở 9/12 storefront |
| 4 | [Scanner App: Scan Documents](https://app.sensortower.com/overview/6753972326?country=US) | 900k | $500k | Ra mắt 10/2025; #2 Grossing Business ở VN |
| 5 | [Scanner App – Scan PDF & Docs](https://app.sensortower.com/overview/1568660349?country=US) | 800k | $3M | Chỉ 35.192 lượt đánh giá ở US |
| 6 | [Yuka](https://app.sensortower.com/overview/1092799236?country=US) | 800k | $1M | Top 10 Free H&F ở IT, GB, ES, FR |
| 7 | [PictureThis](https://app.sensortower.com/overview/1252497129?country=US) | 700k | $9M | |
| 8 | [Adobe Scan](https://app.sensortower.com/overview/1199564834?country=US) | 700k | $2M | |
| 9 | [MyFitnessPal](https://app.sensortower.com/overview/341232718?country=US) | 600k | $12M | #1 Grossing H&F ở US |
| 10 | [Fetch](https://app.sensortower.com/overview/1182474649?country=US) | 600k | <$5k\* | Quét hóa đơn lấy điểm thưởng |

Hai kiểu kinh tế học lộ ra rõ.

**Kiểu thứ nhất là các bản clone thuê bao theo tuần**, đến từ Thổ Nhĩ Kỳ, Ukraine, Hồng Kông và Tây Ban Nha. Ví dụ là TapSuite, ScanGuru, Scan Shot và Uniteman. Các app này đạt 0,5–3 triệu USD/tháng dù lượng đánh giá rất nhỏ, cho thấy doanh thu đến từ quảng cáo trả tiền chứ không từ cầu tự nhiên ([Sensor Tower – Scan Shot](https://app.sensortower.com/overview/1575194801?country=US)).

**Kiểu thứ hai là "động cơ nhận diện dùng chung"**, điển hình là hai công ty chị em Glority và Next Vision. Glority làm PictureThis và PlantAI. Next Vision làm CoinSnap, Rock Identifier, Picture Insect, Picture Bird, Picture Mushroom, AntiqSnap, FoilSnap, VinylSnap và Calo. Cộng các ước tính lại, hai công ty thu khoảng **12,8 triệu USD/tháng trên iOS** (phép cộng của nhóm nghiên cứu), và có thể mở ngách mới trong vài tháng ([Sensor Tower – AntiqSnap](https://app.sensortower.com/overview/6752929120?country=US)). Làn sóng 2025–2026 đi theo đúng khuôn này:
- AntiqSnap ra mắt 10/2025, đạt $400k/tháng.
- HoloDex ra mắt 9/2025, đạt $400k/tháng và đứng **#1 Grossing Reference ở Hà Lan**.
- FoilSnap đứng **#1 Grossing Reference ở Ý**.
- Translate AI ra mắt 1/2025, đạt $500k/tháng.

Nguồn: [Sensor Tower – HoloDex](https://app.sensortower.com/overview/6747442689?country=US).

### Bảng điểm phân khúc: nơi doanh thu gặp nhu cầu tìm kiếm

Ghép tổng doanh thu theo phân khúc với tín hiệu tìm kiếm Google cho thấy một điều quan trọng: **phân khúc kiếm nhiều nhất hôm nay chưa chắc có cầu đang tăng**. Plant ID vẫn thu 10,7 triệu USD/tháng trong khi cầu tìm kiếm giảm. LiDAR/3D chưa có số doanh thu công khai nhưng có từ khóa tăng nhanh nhất. Doanh thu lấy từ [Sensor Tower](https://app.sensortower.com/overview/388627783?country=US), cầu tìm kiếm lấy từ [Google Trends US](https://trends.google.com/trends/explore?date=2021-01-01%202026-09-20&geo=US&q=cal%20ai).

| Phân khúc | Số app | Doanh thu WW iOS T8/2026 | Tải | Từ khóa đại diện (dải volume Google US ước tính) | Xu hướng 2024→2026 | Đọc vị |
|---|---|---|---|---|---|---|
| Quét tài liệu/OCR | 19 | $22,1M | 6,2M | "scanner app" ≥20K; "scan to pdf" 8–20K; "image to text" ≥20K; "ocr app" 1–3K | "scan to pdf" tăng (spike-inflated); "ocr app" tăng rất nhanh; head term ngang nền | Bể lớn nhất nhưng bị thương hiệu lớn khóa chặt |
| Calorie tracker lai | 4 | $18,8M | 1,3M | "calorie counter" 8–20K | Yếu (dưới nền) | Thuộc các ông lớn |
| Plant ID | 9 | $10,7M | 1M | "plant identifier" 3–8K | **Giảm** (US −39%) | Tiền lớn nhưng cầu co lại |
| AI calorie qua ảnh | 11 | $6M | 1,9M | "cal ai" 8–20K; "food scanner" 3–8K | **Tăng rất nhanh** | Rất đông, khoảng 70 đối thủ |
| Dịch qua camera | 12 | $5,8M | 3,9M | "translate picture" 8–20K; "offline translator" 300–1K | **Giảm**; riêng "offline translator" tăng (spike-inflated) | Đang bị Apple Translate và Google thay thế |
| Giải bài tập | 11 | $2M | 913k | "math solver" ≥20K (khớp rộng) | Tăng rất nhanh | Google và ByteDance sở hữu |
| Nhận diện xu | 3 | $1,2M | 620k | "coin value app" 1–3K | Tăng | Ngách sưu tầm, sẵn lòng trả tiền |
| Quét mã vạch sản phẩm | 4 | $1M | 877k | "barcode scanner" 8–20K | Yếu | Yuka thống trị |
| QR/mã vạch | 4 | $1M | 260k | "qr code scanner" 8–20K | **Giảm** | Rủi ro 4.3 cao |
| Quét thẻ TCG | 3 | $640k | 430k | Related query "pokemon card scanner app" +950% | Tăng | Mới nổi |
| LiDAR/3D/đo | n/a | Không có ước tính | n/a | "measure app" 8–20K; "lidar app" 1–3K; "floor plan app" 1–3K; "3d scanner app" 300–1K | "lidar app", "floor plan app" **tăng rất nhanh** | Cạnh tranh thấp đến vừa, trả tiền kiểu B2B |

Cầu tìm theo thương hiệu cũng đi cùng hướng. Ở Mỹ, "cal ai" có mức tìm gấp khoảng bốn lần "camscanner" ([Google Trends](https://trends.google.com/trends/explore?date=2021-01-01%202026-09-20&geo=US&q=cal%20ai)). Exploding Topics xếp Polycam vào nhóm "exploding", còn PictureThis và Luma AI vào nhóm "peaked" ([Exploding Topics – Polycam](https://explodingtopics.com/topic/polycam)).

### Doanh thu công bố xác nhận quy mô, nhưng lệch khỏi ước tính

Những con số do công ty hoặc báo chí công bố xác nhận đây là thị trường nhiều trăm triệu USD. Chúng cũng cho thấy ước tính Sensor Tower thường thấp hơn thực tế ở các app bán qua kênh web.

| Công ty / app | Con số | Thời điểm | Loại | Nguồn |
|---|---|---|---|---|
| Cal AI | Trên $30M doanh thu/năm, trên 15M lượt tải, 7 nhân sự; MyFitnessPal mua lại (công bố 2/3/2026) | 3/2026 | Công ty xác nhận | [TechCrunch](https://techcrunch.com/2026/03/02/myfitnesspal-has-acquired-cal-ai-the-viral-calorie-app-built-by-teens/) |
| Cal AI | Trên $1,4M/tháng sau phí store; 8,3M lượt tải (7/2025) | 9/2025 | Founder công bố | [CNBC](https://www.cnbc.com/2025/09/06/cal-ai-how-a-teenage-ceo-built-a-fast-growing-calorie-tracking-app.html) |
| Glority (PictureThis, PlantAI) | ARR $173M | 2025 | Xếp hạng bên thứ ba | [Tech Buzz China](https://techbuzzchina.substack.com/p/the-state-of-chinese-ai-apps-2025) |
| INTSIG (CamScanner, CamCard) | Doanh thu 2025 đạt 1,81 tỷ NDT (+25,8%); 9,88 triệu người trả tiền (+32,78%) | FY2025 | Báo cáo của công ty niêm yết | [Futubull](https://news.futunn.com/en/post/70173970/hehe-information-688615-strong-growth-momentum-in-the-2025-annual) |
| Yuka | Premium subscriptions đạt $11.884.771 năm 2025; đội 20 người, không nhận tiền nhãn hàng | 2025 | Công ty công bố | [Yuka Independence](https://yuka.io/en/independence/) |
| Polycam | Gần 100.000 khách trả tiền, trên 10M lượt tải, Series A $18M | 2/2024 | Báo chí | [TechCrunch](https://techcrunch.com/2024/02/07/3d-scanning-app-polycam-gets-backing-from-youtube-co-founder/) |
| Matterport | Doanh thu $169,7M, 1,2M thuê bao; CoStar mua với giá khoảng $1,6 tỷ (hoàn tất 28/2/2025) | 2024–25 | Công ty/báo chí | [Wikipedia](https://en.wikipedia.org/wiki/Matterport) |
| 1.328 app nhận diện | $27M chi tiêu/tháng (App Store + Google Play); app nhận diện xu $3,5M | 5/2025 | Appfigures ước tính | [Appfigures](https://appfigures.com/resources/insights/20250509?f=1) |
| Genius Scan (Paris) | 5M MAU, doanh thu tăng hơn 2 lần, tự thân (bootstrapped) | 1/2025 | Podcast | [Sub Club](https://subclub.com/episode/bootstrapping-a-subscription-app-to-5m-mau-and-2x-revenue-growth-bruno-virlet-genius-scan) |

Doanh thu Cal AI tự công bố cao gấp khoảng 1,3–2 lần mức run-rate iOS của Sensor Tower. Vì vậy các bảng xếp hạng phía trên nên được xem là **mức sàn tương đối**, và dùng để so bậc độ lớn chứ không phải số kế toán.

Yuka là ví dụ ngược lại về mức kiếm trên mỗi người dùng. Công ty có khoảng 73 triệu người dùng nhưng chỉ thu khoảng 11,9 triệu USD. Điều đó cho thấy **app quét phổ thông kiếm rất ít trên mỗi người dùng**, trong khi các quy trình chuyên nghiệp kiếm nhiều hơn nhiều trên mỗi người trả tiền ([Glossy](https://www.glossy.co/beauty/yuka-beauty-wellness-product-scanning-app/)).

### LiDAR và 3D sống nhờ khách hàng chuyên nghiệp

Mảng LiDAR/3D không có ước tính tải hay doanh thu công khai. Tín hiệu đo được là số lượt đánh giá và thứ hạng.

**Polycam là app quét 3D thuần duy nhất lọt top grossing** ở bất kỳ nước nào được kiểm tra: #89 ở US, #58 ở GB, #53 ở DE và #42 ở FR, trong danh mục Photo & Video. **magicplan chỉ lọt top grossing ở DE (#49) và FR (#64)**, danh mục Productivity. Điều này cho thấy châu Âu, đặc biệt là khối nói tiếng Đức và Pháp, là thị trường trả tiền tốt cho công cụ đo và vẽ mặt bằng ([Apple RSS DE Productivity](https://itunes.apple.com/de/rss/topgrossingapplications/limit=200/genre=6007/json)).

Mảng quét 3D cho người dùng phổ thông đã co cụm lại. Scaniverse chuyển về Niantic Spatial, công ty được tách ra với vốn khởi điểm $250M ([Wikipedia – Niantic Spatial](https://en.wikipedia.org/wiki/Niantic_Spatial)). Luma để app 3D gần như bỏ ngỏ để tập trung vào video. Epic gộp sản phẩm thành RealityScan 2.0. CoStar mua Matterport. 3d Scanner App bị bán vào 7/2025 rồi chuyển sang thuê bao theo tuần ([Laan Labs](https://labs.laan.com/apps)).

| App | Loại | Lượt đánh giá US | Tổng EU-7 | Cần LiDAR? | Giá US | Xử lý |
|---|---|---|---|---|---|---|
| [Tape Measure (Level Labs)](https://apps.apple.com/us/app/id1271546805) | Đo AR | 88.823 | 11.697 | Không | Pro $9.99–$49.99 | n/a |
| [Polycam](https://apps.apple.com/us/app/id1532482376) | Quét 3D, splat, floor plan | 43.579 | 32.664 | Chỉ cho chế độ quét không gian | Basic $149.99/năm; Business $400/người/năm (web) | n/a |
| [magicplan](https://apps.apple.com/us/app/id427424432) | Floor plan chuyên nghiệp | 41.136 | 46.430 | Không bắt buộc | $129.99–$899.99/năm | n/a |
| [Shapr3D](https://apps.apple.com/us/app/id1091675654) | CAD (nhập RoomPlan) | 34.082 | 38.372 | Không để dựng CAD; nhập dữ liệu quét LiDAR/RoomPlan | Solo $249.99/năm | n/a |
| [CamToPlan](https://apps.apple.com/us/app/id1292176208) | Đo AR và vẽ mặt bằng | 16.608 | 16.005 | Không | $4.99–$49.99 (một lần) | Bản LiDAR xử lý on-device |
| [3d Scanner App](https://apps.apple.com/us/app/id1419913995) | Quét 3D | 16.090 | 12.700 | LiDAR hoặc TrueDepth | $2.99–$4.99/tuần; $29.99–$69.99/năm | On-device |
| [Scaniverse](https://apps.apple.com/us/app/id1541433223) | Gaussian splat | 11.745 | 11.488 | Không | Miễn phí trên App Store; gói cloud bán trên web | On-device miễn phí, cloud trả phí |
| [RoomScan Pro LiDAR](https://apps.apple.com/us/app/id1504050801) | Floor plan | 2.115 | 1.227 | RoomPlan cần; Touch Mode không cần | $119.99/năm | n/a |
| [KIRI Engine](https://apps.apple.com/us/app/id1577127142) | Photogrammetry, splat | 1.232 | 956 | Không bắt buộc | $29.99–$49.99/năm | 3DGS xử lý trên cloud |
| [SiteScape (FARO)](https://apps.apple.com/us/app/id1524700432) | Quét cho kiến trúc–xây dựng (AEC) | 938 | 732 | **Bắt buộc** | $499/năm | n/a |
| [Dot3D](https://apps.apple.com/us/app/id1641016966) | Quét cho kiến trúc–xây dựng (AEC) | 99 | 117 | **Bắt buộc** | $349.99/năm | On-device |
| [Metaroom](https://apps.apple.com/us/app/id1637077163) | LiDAR sang BIM (DE) | 80 | 738 | **Bắt buộc** | Gói Workspace | Cloud AWS tuân thủ GDPR |

EU-7 gồm GB, DE, FR, IT, ES, NL và PL. Số liệu lấy từ [iTunes Lookup API](https://itunes.apple.com/lookup?id=427424432&country=de) ngày 27/9/2026.

Giá trong mảng này chia ba tầng rõ rệt:
- **Công cụ SaaS cho xây dựng và bảo hiểm: $120–$900/người/năm.** Khách hàng là thợ cải tạo, bên phục hồi thiệt hại bảo hiểm và bất động sản. magicplan tích hợp Xactimate và nêu tên khách hàng Đức như Belfor Germany và Sân bay Hamburg ([magicplan.app](https://www.magicplan.app/)).
- **Người sáng tạo nội dung và người chơi in 3D: $30–$200/năm.**
- **App đo AR phổ thông: gói tuần $3–$13.** Nhóm này có nhiều lượt đánh giá nhất nhưng hiếm khi lọt top grossing.

### Offline tạo niềm tin, cloud tạo doanh thu

Bảng dưới cho thấy nghịch lý trung tâm của đề bài: app offline tốt nhất thường miễn phí, còn app kiếm nhiều nhất thường chạy trên cloud. Ngoại lệ đáng chú ý là các app quét tài liệu dùng offline làm điểm bán về quyền riêng tư, và các app **đặt chế độ offline sau paywall**. Yuka đưa 100.000 sản phẩm quét nhiều nhất vào chế độ offline chỉ cho bản Premium ([Yuka Help](https://help.yuka.io/l/en/article/ur4x5k32qg-database-in-offline-mode)). Dog Scanner cũng chỉ cho quét offline ở bản Premium.

| App | Chức năng | Tình trạng offline | Doanh thu T8/2026 | Nguồn |
|---|---|---|---|---|
| Seek by iNaturalist | Nhận diện loài qua camera | Hoàn toàn offline | <$5k\* | [iNaturalist](https://www.inaturalist.org/posts/44986-56-seek-offline-database-no-wifi-google-lens-plantnet-flora-incognita-plant-id) |
| Merlin Bird ID | Nhận diện chim qua ảnh | Photo ID hoàn toàn offline, hơn 6.900 loài | <$5k\* | [Merlin help](https://support.ebird.org/en/support/solutions/articles/48000966224-merlin-photo-id) |
| Pl@ntNet | Nhận diện cây | Có chế độ nhúng offline | <$5k\* | [Pl@ntNet docs](https://docs.plantnet.org/en/tutorials/install-the-offline-embedded-mode/) |
| Google Translate | Dịch qua camera | Offline sau khi tải gói ngôn ngữ | <$5k\* | [Google Help](https://support.google.com/translate/answer/6142473?hl=en&co=GENIE.Platform%3DiOS) |
| Genius Scan | Quét tài liệu + OCR | Xử lý on-device | $300k | [Sensor Tower](https://app.sensortower.com/overview/377672876?country=US) |
| ScanGuru | Quét tài liệu | Lưu cục bộ, không cần mạng | $800k | [Sensor Tower](https://app.sensortower.com/overview/1040149161?country=US) |
| iScanner | Quét, sửa | Offline; chỉ sync cần mạng | $4M | [Sensor Tower](https://app.sensortower.com/overview/1040093707?country=US) |
| Yuka | Quét mã vạch | Offline chỉ cho Premium | $1M | [Yuka Help](https://help.yuka.io/l/en/article/ur4x5k32qg-database-in-offline-mode) |
| Flora Incognita | Nhận diện cây | Nhận diện qua cloud | <$5k\* | [Flora Incognita FAQ](https://floraincognita.com/faq/) |
| Cal AI | Ảnh món ăn sang calo | LLM trên cloud (OpenAI, Anthropic) | $2M | [CNBC](https://www.cnbc.com/2025/09/06/cal-ai-how-a-teenage-ceo-built-a-fast-growing-calorie-tracking-app.html) |

Tính năng miễn phí sẵn có của Apple cạnh tranh trực tiếp với các app dịch và app quét trả phí. Dù vậy, app Apple Translate chỉ được 2,35 sao từ 9.959 lượt đánh giá ở US. Trong khi đó Translate Now vẫn thu 3 triệu USD/tháng bằng gói tuần ([Sensor Tower – Apple Translate](https://app.sensortower.com/overview/1514844618?country=US)). Như vậy "Apple đã có sẵn" không tự động giết một danh mục. Tuy nhiên nó kéo cầu tìm kiếm xuống, như phần 3 sẽ cho thấy.

## Châu Âu trả tiền nhiều nhất ở Reference, Business và Education

Ảnh chụp bảng xếp hạng ngày 27/9/2026 cho thấy mỗi danh mục châu Âu gắn với một nhóm app camera:
- **Reference** đông app camera nhất: nhận diện xu, thẻ TCG, đồ cổ và AI dịch chiếm phần lớn top 20 grossing ở DE, GB, IT, ES, NL và Bắc Âu.
- **Business** là sân của app quét tài liệu.
- **Education** là sân của nhận diện cây và nấm.
- **Food & Drink** do Vivino dẫn đầu, và Vivino đứng #1 ở Na Uy.

Các nước Bắc Âu liên tục xếp app nhận diện, QR và app quét cao hơn các thị trường EU lớn. Ví dụ, Genius Scan đứng #11 Business ở SE và NO, Calo đứng #10–13 H&F ở FI và DK, Picture Mushroom đứng #4 Education ở DK. Đây là dấu hiệu Bắc Âu sẵn lòng trả tiền cao trên mỗi người dùng ([Apple RSS DK Education](https://itunes.apple.com/dk/rss/topfreeapplications/limit=100/genre=6017/json)).

Bảng dưới là hạng **Top Grossing trong danh mục** ghi ở cột App, trên iPhone, ngày 27/9/2026. Dấu "–" nghĩa là ngoài top 100. "n/c" nghĩa là storefront đó không được kiểm tra. Nguồn: [Apple RSS feeds](https://itunes.apple.com/us/rss/topgrossingapplications/limit=100/genre=6000/json) theo cùng mẫu URL cho mọi nước và danh mục. Riêng Polycam, magicplan và Planner 5D lấy từ lần kiểm tra LiDAR ([Apple RSS FR](https://itunes.apple.com/fr/rss/topgrossingapplications/limit=200/genre=6008/json)).

| App (danh mục) | US | UK | DE | FR | IT | ES | NL | SE | NO | DK | FI | VN |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| iScanner (Business) | 3 | 5 | 2 | 3 | – | – | 3 | 3 | 4 | 3 | 4 | 7 |
| Adobe Scan (Business) | 12 | 11 | 4 | 8 | 3 | 10 | 5 | 5 | 5 | 6 | 3 | 12 |
| Scanner App – Scan PDF & Docs (Business) | 8 | 10 | 12 | 12 | 5 | 9 | 14 | 6 | 13 | 7 | 25 | 15 |
| Scanner Pro (Business) | 21 | 22 | 6 | 10 | 7 | 18 | 9 | 7 | 6 | 10 | 14 | 14 |
| Genius Scan (Business) | 35 | 45 | 17 | 32 | 26 | 24 | 24 | 11 | 11 | 14 | 35 | 81 |
| CamScanner (Productivity) | 7 | 18 | 16 | 8 | 7 | 7 | 31 | 23 | 35 | 38 | 20 | 5 |
| Translate Now (Reference) | 1 | 3 | 2 | 16 | 5 | 10 | 14 | 9 | 7 | 4 | 15 | 4 |
| Translate AI – Live Translate (Reference) | 14 | 4 | 5 | 4 | 7 | 5 | 5 | 4 | 4 | 3 | 4 | 6 |
| CoinSnap (Reference) | 7 | 8 | 3 | 6 | 2 | 3 | 13 | 25 | 27 | 5 | 17 | – |
| HoloDex – TCG Scan (Reference) | 13 | 9 | 20 | 27 | 21 | 22 | **1** | 12 | 3 | 6 | 71 | 88 |
| FoilSnap (Reference) | 19 | 7 | 6 | 29 | **1** | 6 | 42 | 57 | – | 36 | – | – |
| AntiqSnap (Reference) | 10 | 31 | 24 | 11 | 6 | 20 | 19 | 32 | 14 | 27 | 45 | – |
| PictureThis (Education) | 3 | 2 | 3 | 5 | 5 | 2 | 3 | 14 | 15 | 10 | 22 | – |
| Picture Mushroom (Education) | 68 | 22 | 10 | 33 | 14 | 63 | 42 | 12 | 48 | 4 | 25 | – |
| Vivino (Food & Drink) | 6 | 9 | 14 | 8 | 5 | 9 | 2 | 2 | **1** | 3 | 7 | 3 |
| MyFitnessPal (H&F) | **1** | 5 | 11 | 15 | 14 | 10 | 6 | 22 | 11 | 10 | 13 | 37 |
| Yazio (H&F) | – | – | 2 | 4 | 4 | 8 | 9 | 38 | 39 | 23 | 3 | 56 |
| Cal AI (H&F) | 11 | 19 | 59 | 51 | 78 | 7 | 61 | 50 | 66 | 30 | 65 | – |
| Calo (H&F) | 52 | 22 | 67 | 39 | 17 | 44 | 53 | 17 | 31 | 13 | 10 | – |
| Yuka (H&F) | 25 | 30 | 79 | 16 | 16 | 28 | – | – | – | – | – | – |
| Polycam (Photo & Video) | 89 | 58 | 53 | 42 | n/c | n/c | n/c | n/c | n/c | n/c | n/c | – |
| magicplan (Productivity) | – | – | 49 | 64 | n/c | n/c | n/c | n/c | n/c | n/c | n/c | – |
| Planner 5D (Lifestyle) | 48 | 43 | 17 | 33 | n/c | n/c | n/c | n/c | n/c | n/c | n/c | 21 |

App của nhà phát hành châu Âu mạnh ở các danh mục **"niềm tin"**:
- Dinh dưỡng: Yazio đứng #20 grossing toàn bảng xếp hạng Đức; Lifesum đứng #2 H&F ở Thụy Điển.
- Minh bạch sản phẩm: Yuka.
- Quét tài liệu đề cao quyền riêng tư: Genius Scan.
- Nhận diện khoa học được tài trợ công: PlantNet, Flora Incognita, ObsIdentify (#9 Free Education ở Hà Lan).

Ngược lại, top grossing ở mảng "nhận diện mọi thứ" và mảng clone quét theo tuần gần như hoàn toàn thuộc về nhà phát hành ngoài EU: BPMobile, Next Vision, Vortemol (Ukraine) và TapSuite (Thổ Nhĩ Kỳ). Nguồn: [Sensor Tower – Yazio](https://app.sensortower.com/overview/946099227?country=US), [Apple RSS DE Business](https://itunes.apple.com/de/rss/topgrossingapplications/limit=100/genre=6000/json).

Thị phần iOS quyết định giá trị thực của từng storefront. Bắc Âu, Thụy Sĩ và Anh là nơi iPhone chiếm đa số. Đức và Pháp có iOS dưới 40% nhưng vẫn nằm trong nhóm thị trường doanh thu lớn nhất châu Âu vì dân số lớn ([Sensor Tower State of Mobile 2026](https://sensortower.com/blog/state-of-mobile-2026)). Chi phí quảng cáo Apple Ads ở Đức, Pháp và Hà Lan chỉ bằng khoảng 41–55% mức của Mỹ ([Adapty](https://adapty.io/blog/apple-ads-benchmarks-2026/)).

| Thị trường | iOS share (StatCounter, 8/2026) | Apple Ads CPT / CPA (12 tháng tới 7/2026) | Ghi chú |
|---|---|---|---|
| Đan Mạch | 62,84% | n/a | iOS cao nhất châu Âu |
| Thụy Điển | 60,16% | n/a | |
| Na Uy | 59,38% | n/a | |
| Thụy Sĩ | 57,58% | n/a | Storefront index DE, FR, IT và EN-UK |
| Anh | 51,47% | $1.31 / $2.02 | |
| Pháp | 36,26% | $0.75 / $1.11 | Top 3 doanh thu châu Âu |
| Ý | 34,96% | n/a | |
| Tây Ban Nha | 31,35% | n/a | |
| Hà Lan | 30,75% (WPR: 38,07%) | $0.65 / $1.07 | |
| Ba Lan | 30,64% | n/a | Foundation Models chưa hỗ trợ tiếng Ba Lan |
| Đức | 27,54% (WPR: 37,56%) | $0.86 / $1.34 | Top 3 doanh thu châu Âu |
| Châu Âu chung | 37,25% | – | |
| Mỹ (đối chiếu) | – | $1.58 / $2.51 | |
| Việt Nam (đối chiếu) | Apple chiếm 18% lượng máy xuất xưởng Q1/2025 | n/a | [VnExpress](https://vnexpress.net/iphone-la-dong-luc-chinh-giup-thi-truong-smartphone-tang-truong-4932838.html) |

Nguồn: [StatCounter Europe](https://gs.statcounter.com/os-market-share/mobile/europe), [StatCounter UK](https://gs.statcounter.com/os-market-share/mobile/united-kingdom), [StatCounter DE](https://gs.statcounter.com/os-market-share/mobile/germany), [WPR](https://worldpopulationreview.com/country-rankings/iphone-market-share-by-country), [Adapty Apple Ads 2026](https://adapty.io/blog/apple-ads-benchmarks-2026/).

Việt Nam vận hành rất khác châu Âu.
- **Business grossing** gần như toàn app quét tài liệu: #2 Scanner App: Scan Documents, #4 Document Scan, #5 ScanGuru, #7 iScanner.
- **Reference grossing** hoàn toàn là app AI dịch: #1 Live Translator-AI Translate, #2 InstantTranslator.
- **Education:** Gauth đứng #2 Free.
- **Health & Fitness:** AI Calorie Tracker – FoodPilot đứng #2 Grossing.

Nguồn: [Apple RSS VN Reference](https://itunes.apple.com/vn/rss/topgrossingapplications/limit=100/genre=6006/json).

Có một số người chơi nội địa đáng kể. Photo Translator của EVOLLY có 31.723 lượt đánh giá ở VN, AI Hay có 122.058, ngoài ra còn Caloer và CalSnap ([iTunes Lookup VN](https://itunes.apple.com/lookup?id=388627783&country=vn)). Tuy nhiên, mức doanh thu trên mỗi lượt cài (RPI) ngày 14 của khối IN/SEA chỉ **$0.08, so với $0.25 ở Tây Âu**. Tỷ lệ hoàn tiền ở khối này lên tới **7,7%** ([RevenueCat SOSA 2026](https://www.revenuecat.com/state-of-subscription-apps)). Việt Nam vì thế nên là chế độ bản địa hóa của một sản phẩm toàn cầu, không phải thị trường chính.

## Nhu cầu tìm kiếm dịch chuyển sang AI calorie, OCR và LiDAR

### Google Trends ở Mỹ: cụm nào tăng thật, cụm nào mất cầu

Bảng dưới gồm các từ khóa chính ở Mỹ, lấy theo tháng từ 1/2021 đến 9/2026 và truy xuất ngày 27/9/2026.
- **Dải volume** là ước tính quy đổi từ Trends, không phải số của công cụ keyword.
- **Δ 2 năm** so trung vị giai đoạn 9/2025–8/2026 với 9/2023–8/2024.
- **Spike** là tỷ lệ giữa đỉnh tháng 4–6/2026 và trung vị trước đó.
- **Kết luận** so với mức nền đối chứng ≈+62%. Các từ đối chứng gồm "calculator app" +34%, "weather app" +115% và "translate" −27%.

Nguồn: [Google Trends US](https://trends.google.com/trends/explore?date=2021-01-01%202026-09-20&geo=US&q=plant%20identifier).

| Từ khóa | Cụm | Volume Google US/tháng (ước tính) | Δ 2 năm | Δ 1 năm | Spike T4–6/2026 | Kết luận |
|---|---|---|---|---|---|---|
| math solver | Bài tập | ≥20K | +1320% | +82% | 0,9× | Tăng rất nhanh (khớp rộng, lẫn truy vấn "calculator") |
| image to text | OCR | ≥20K | +54% | +34% | 1,3× | Ngang nền |
| scanner app | Quét | ≥20K | +46% | +48% | 1,2× | Ngang nền |
| scan to pdf | Quét | 8–20K | +186% | +144% | 3,1× | Tăng (spike-inflated) |
| barcode scanner | Mã | 8–20K | +16% | +16% | 2,4× | Yếu |
| measure app | 3D/AR | 8–20K | +100% | +94% | 1,7× | Ngang nền |
| qr code scanner | Mã | 8–20K | −19% | −3% | 1,0× | **Giảm** |
| calorie counter | Thực phẩm | 8–20K | +2% | −16% | 1,2× | Yếu |
| cal ai | Thực phẩm | 8–20K | +1140% | +182% | 1,6× | **Tăng rất nhanh** |
| translate picture | Dịch | 8–20K | −21% | −16% | 0,9× | **Giảm** |
| document scanner | Quét | 3–8K | +62% | +37% | 3,0× | Ngang nền (spike-inflated) |
| lidar scanner | 3D | 3–8K | +140% | +134% | 0,8× | Tăng (một phần do game Arc Raiders) |
| food scanner | Thực phẩm | 3–8K | +331% | +211% | 5,0× | Tăng rất nhanh (spike-inflated) |
| plant identifier | Nhận diện | 3–8K | −39% | −27% | 4,0× | **Giảm** |
| photo translate | Dịch | 3–8K | −7% | −4% | 1,0× | Yếu |
| gaussian splatting | 3D | 3–8K | +326% | +305% | 3,1× | Mới, ít dữ liệu |
| ocr app | OCR | 1–3K | +643% | +512% | 2,0× | **Tăng rất nhanh** |
| lidar app | 3D | 1–3K | +475% | +360% | 1,8× | **Tăng rất nhanh** |
| floor plan app | 3D | 1–3K | +238% | +184% | 1,6× | **Tăng rất nhanh** |
| text scanner | OCR | 1–3K | +131% | +112% | 1,7× | Tăng |
| pdf scanner app | Quét | 1–3K | +153% | +143% | 1,9× | Tăng |
| coin value app | Nhận diện | 1–3K | +119% | +54% | 0,9× | Tăng |
| room scanner | 3D | 1–3K | +129% | +72% | 3,8× | Tăng (spike-inflated) |
| receipt scanner | Quét | 1–3K | +20% | +23% | 2,3× | Yếu |
| 3d scanner app | 3D | 300–1K | +86% | +82% | 1,3× | Ngang nền |
| tape measure app | 3D/AR | 300–1K | +13% | +33% | 1,4× | Yếu |
| offline translator | Dịch | 300–1K | +217% | +138% | 5,9× | Tăng rất nhanh (spike-inflated) |
| nutrition scanner | Thực phẩm | 300–1K | +917% | +662% | 3,8× | Tăng rất nhanh (spike-inflated) |
| metal detector app | Cảm biến khác | 300–1K | +180% | +151% | 2,1× | Tăng |
| mushroom identifier | Nhận diện | 300–1K | −10% | −29% | 2,6× | Yếu |
| ai calorie tracker | Thực phẩm | 300–1K | n/a | +228% | 2,6× | Mới xuất hiện từ 2024 |
| offline ocr | OCR | <300 | n/a | n/a (T7–8/2026 so 2024: +533%) | 1,8× | Mới xuất hiện từ 2024 |

Trên phạm vi toàn cầu, mức nền cao hơn (≈+166% sau 2 năm), nhưng hướng đi giống ở Mỹ ([Google Trends worldwide](https://trends.google.com/trends/explore?date=2021-01-01%202026-09-20&q=plant%20identifier)).
- **Tăng mạnh:** "nutrition scanner" +2300%, "ocr app" +900%, "offline ocr" +667%, "lidar app" +622%, "floor plan app" +544%, "scan to pdf" +321%.
- **Giảm trong khi mức nền tăng:** "qr code scanner" −29%, "photo translate" −29%, "translate picture" −34%, "plant identifier" −21%. Đây là các cụm đang thật sự yếu đi.

Các truy vấn liên quan đang tăng cho thấy vì sao plant ID yếu đi: "google lens plant identifier" +140%, "ai plant identifier" +1300% và "free plant identifier app no subscription" +350%. Người dùng đang chuyển sang Google Lens và trợ lý AI, đồng thời phản ứng với giá, chứ không phải hết quan tâm đến việc nhận diện cây ([Google Trends related](https://trends.google.com/trends/explore?date=today%205-y&q=plant%20identifier)).

Hai ngoại lệ cần lưu ý khi đọc bảng. Thứ nhất, "math solver" khớp rộng: truy vấn liên quan hàng đầu là "calculator", nên con số bị thổi phồng. Thứ hai, đỉnh tháng 11/2025 của "lidar scanner" đến từ game Arc Raiders, không phải từ nhu cầu LiDAR trên iPhone ([Google Trends US lidar](https://trends.google.com/trends/explore?date=today%2012-m&geo=US&q=lidar)).

Mùa vụ cần tính khi lên lịch ra mắt và cập nhật ASO:

| Nhóm | Thời điểm cao điểm | Ghi chú |
|---|---|---|
| Nhận diện cây, côn trùng, chim | Tháng 5–8 | Biên độ 5–12 lần |
| Nấm | Tháng 8–10 | |
| Calorie | Tháng 1 (và tháng 3) | |
| Giải bài tập | Tháng 9–10 | |
| Hóa đơn, tài liệu | Tháng 1–2 | Mùa thuế |
| 3D/LiDAR | Tháng 11–12 | Mùa iPhone mới và lễ |

### Sáu thị trường EU tìm bằng ngôn ngữ địa phương

Ở châu Âu, người dùng gõ động từ và việc cần làm bằng tiếng địa phương, cộng thêm một từ về giá. Ví dụ: "Dokumente scannen", "Pflanzen erkennen", "traduire photo", "riconoscere piante", "meten met camera", đi kèm "kostenlos", "gratuit" hoặc "gratis".

Chỉ Đức có chuỗi đối chứng địa phương. Tại Đức, các truy vấn "… app" bằng tiếng Anh tăng vọt, ví dụ "weather app" +714%. Vì vậy các từ khóa tiếng Anh volume thấp ở Đức không đáng tin. Kết luận trong bảng dưới dùng ngưỡng cố định: giảm khi ≤−15%, tăng khi ≥+40%. Nguồn: [Google Trends DE](https://trends.google.com/trends/explore?date=2021-01-01%202026-09-20&geo=DE&q=Scanner%20App), [GB](https://trends.google.com/trends/explore?date=2021-01-01%202026-09-20&geo=GB&q=scanner%20app), [FR](https://trends.google.com/trends/explore?date=2021-01-01%202026-09-20&geo=FR&q=scanner%20document), [IT](https://trends.google.com/trends/explore?date=2021-01-01%202026-09-20&geo=IT&q=scanner%20documenti), [NL](https://trends.google.com/trends/explore?date=2021-01-01%202026-09-20&geo=NL&q=scanner%20app), [ES](https://trends.google.com/trends/explore?date=2021-01-01%202026-09-20&geo=ES&q=escáner%20de%20documentos).

| Thị trường | Tăng (Δ 2 năm) | Ngang | Giảm (Δ 2 năm) |
|---|---|---|---|
| Anh | scanner app +48%; document scanner +52%; measure app +62%; 3d scanner app +55% | calorie counter +13%; image to text +4%; qr code scanner −14% | plant identifier −25%; bird identifier −38%; plant identification app −47% |
| Đức | Scanner App +56%; 3D Scanner App +46% | Dokumente scannen +23%; Kalorienzähler +27%; Text aus Bild −12%; Foto übersetzen +6% | Kamera übersetzer −25%; Pflanzen erkennen −45%; Pflanzen bestimmen −38%; Pflanzen bestimmen app −59% |
| Pháp | scanner 3d +43% | scanner document +6%; application scanner +7%; application calorie +22%; traduire photo −12% | traduction photo −35%; image en texte −22%; identifier plante −33%; reconnaissance plante −52% |
| Tây Ban Nha | escáner 3d +222% (nền rất thấp) | app para medir +7%; traducir foto +7%; lector qr −6% | identificar plantas −43%; traductor de fotos −33% |
| Ý | app calorie +66%; scanner 3d +44% | app scanner +32%; da immagine a testo +33%; scanner documenti +20%; riconoscere funghi −13% (biên độ mùa vụ 19,9×) | traduttore foto −29%; riconoscere piante −37%; app riconoscimento piante −43% |
| Hà Lan | calorie app +263% (spike 4,1×); 3d scanner +82%; meet app +102%; scanner app +62% | document scannen +1%; qr code scanner +8% | foto vertalen −22%; planten herkennen −51% |

So cường độ tìm kiếm giữa các nước cho thấy ngôn ngữ nào đáng đầu tư trước. Mỗi con số là tỷ lệ trong tổng lượt tìm của chính nước đó, không phải volume tuyệt đối ([Google Trends](https://trends.google.com/trends/explore?date=2021-01-01%202026-09-20&geo=IT&q=scanner%20documenti)).
- **Dịch ảnh:** "traduttore foto" ở Ý gấp khoảng 36 lần "camera translator" ở Anh. "traduire photo" ở Pháp và "traducir foto" ở Tây Ban Nha gấp khoảng 9,5 lần.
- **Quét 3D:** "scanner 3d" ở Pháp và Ý gấp khoảng 10 lần "3d scanner app" ở Mỹ. Tuy nhiên từ này rộng hơn và gồm cả máy quét phần cứng.
- **Nhận diện cây:** "plant identifier" ở Anh ngang Mỹ. "identifier plante" ở Pháp chỉ bằng 14% mức của Anh.

App Store autocomplete ở mọi storefront EU xác nhận một họ truy vấn mới là **AI đếm calo qua ảnh**, cùng nhu cầu về LiDAR, quét 3D để in và nhận diện nấm ([Apple search hints](https://search.itunes.apple.com/WebObjects/MZSearchHints.woa/wa/hints?clientApplication=Software&term=scanner)).
- **DE:** "ki kalorienzähler per foto", "3d scanner 3d druck", "3d scan lidar", "pilze bestimmen kostenlos", "münzen wert scanner kostenlos".
- **FR:** "compteur calorie ia", "lidar scanner 3d gratuit", "reconnaissance champignons gratuit".
- **ES:** "contador de calorias gratis por foto", "setas pro con id por foto".
- **IT:** "conta calorie gratis con foto", "funghi: riconoscere dalle foto".
- **NL:** "meten met camera", "planten herkennen gratis".
- **UK:** "plant identifier free uk", "3d scanner stl".

### Việt Nam: cầu tìm kiếm dồn vào vài từ chung

Tại Việt Nam, cầu tìm trên Google tập trung vào vài cụm chung ([Google Trends VN](https://trends.google.com/trends/explore?date=2021-01-01%202026-09-20&geo=VN&q=d%E1%BB%8Bch%20%E1%BA%A3nh)). Các cụm dài hơn như "app scan tài liệu", "đo khoảng cách bằng iphone" hay "app đo diện tích" dưới ngưỡng báo cáo của Trends. Dù vậy, chúng có xuất hiện trong autocomplete App Store VN, cùng với "quét cccd", "đo diện tích đất", "chuyển ảnh sang pdf" và "tính calo đồ ăn" ([Apple search hints](https://search.itunes.apple.com/WebObjects/MZSearchHints.woa/wa/hints?clientApplication=Software&term=plant)).

| Từ khóa | Mức tương đối (dịch ảnh = 100) | Δ 2 năm | Kết luận |
|---|---|---|---|
| dịch ảnh | 100 | −23% | Giảm |
| scan | 78 | +21% | Ngang |
| dịch hình ảnh | 44 | −39% | Giảm |
| quét mã qr | 19 | −8% | Ngang |
| tính calo | 4,1 | −26% | Giảm |
| camscanner | 2,9 | +50% | Tăng |
| nhận diện cây | 1,8 | +37% | Ngang, nền nhỏ |
| quét tài liệu | 1,6 | +86% | Tăng (đỉnh tháng 11–12) |
| chuyển ảnh thành chữ | 1,4 | +41% | Tăng |
| dịch bằng camera | 0,5 | −64% | Giảm |
| scan cccd | ~0 | +73% | Mới, nền thấp (đỉnh tháng 9–10) |

### Dữ liệu tìm kiếm App Store: vài con số công khai và autocomplete

Cầu trên App Store phải đọc tách khỏi Google.

Apple Ads đo độ phổ biến trên thang 1–5, còn các công cụ ASO đo trên thang 5–100 ([Apple Ads Help](https://ads.apple.com/app-store/help/reporting/0023-reporting-options-and-definitions)). Chỉ số này hỏng từ 29/9/2025. Báo cáo Search Term Rank mới của Apple chỉ cập nhật mỗi tháng một lần và bỏ qua các từ có popularity dưới 35 ([ASO.dev](https://aso.dev/aso/search-term-rank/)). Vì vậy dữ liệu App Store dùng được hiện chỉ gồm vài head term có số công khai, cộng với autocomplete.

Các head term đó đều phổ biến nhưng rất khó. Top 10 kết quả của "pdf scanner" có trung bình **804.182 lượt đánh giá** ([Sonar](https://trysonar.app/keyword-difficulty/pdf-scanner/ios/us)).

| Từ khóa (US) | Popularity (Appfigures, 5–100) | Competitiveness / Sonar KD | Top app | Nguồn |
|---|---|---|---|---|
| scanner | 67 | 97 / n/a | PDF scanner | [Appfigures #54](https://appfigures.com/resources/keyword-teardowns/54-scanner) |
| calorie counter | 66 | 95 / 79 (Hard) | MyFitnessPal (2,35M đánh giá) | [Sonar](https://trysonar.app/keyword-difficulty/calorie-counter/ios/us) |
| pdf scanner | 61 | 96 / 82 (Very Hard) | Adobe Scan, CamScanner, Genius Scan, iScanner | [Appfigures #11](https://appfigures.com/resources/keyword-teardowns/11-pdf-scanner) |
| QR code reader | 61 | 93 / 75 (Hard) | Top 10 trung bình 265.379 đánh giá | [Sonar](https://trysonar.app/keyword-difficulty/qr-code-reader/ios/us) |
| math solver | n/a | n/a / 78 (Hard) | Gauth, Photomath, Mathway | [Sonar](https://trysonar.app/keyword-difficulty/math-solver/ios/us) |
| ruler | 54 | 64 / n/a | Số từ 2022 | [Appfigures #46](https://appfigures.com/resources/keyword-teardowns/46-ruler) |
| plant finder | 34 | 74 / n/a | "plant identification" phổ biến gần gấp đôi "plant identifier" | [Appfigures #61](https://appfigures.com/resources/keyword-teardowns/61-plant-finder) |

Autocomplete ở US xác nhận cầu App Store thật cho nhiều cụm chưa có số popularity công khai ([Apple search hints](https://search.itunes.apple.com/WebObjects/MZSearchHints.woa/wa/hints?clientApplication=Software&term=plant)):
- "lidar room scanner", "room scan lidar", "floor plan scanner", "3d scanner app for 3d printer";
- "receipt scanner for taxes", "ocr text scanner free";
- "offline translator";
- "food scanner good or bad free", "ai calorie tracker";
- "coin scanner: value identifier free".

Từ "free" và các bản dịch của nó ("kostenlos", "gratuit", "gratis", "miễn phí") xuất hiện trong gợi ý hàng đầu ở mọi thị trường. Người dùng tìm kiếm với ý định về giá ngay từ đầu.

Ghép cầu, xu hướng và cạnh tranh lại cho ra bảng cơ hội từ khóa dưới đây. Đây là suy luận, cần xác nhận lại bằng Keyword Planner và tài khoản Apple Ads riêng trước khi chốt.

| Hạng | Cụm từ khóa | Cầu Google US | Hướng 2024→2026 | Cạnh tranh App Store | Tín hiệu EU/VN |
|---|---|---|---|---|---|
| 1 | AI chụp món ăn / quét thực phẩm ("cal ai", "food scanner", "nutrition scanner") | 8–20K; 3–8K | Tăng rất nhanh | Khó (KD 79; MyFitnessPal, Cal AI, Yazio) | Autocomplete có ở DE/FR/ES/IT; VN "tính calo" giảm |
| 2 | OCR / ảnh sang chữ ("image to text", "ocr app", "text scanner", "offline ocr") | ≥20K; 1–3K | Tăng | Vừa | EU lẫn lộn; VN "chuyển ảnh thành chữ" +41% |
| 3 | LiDAR room / floor plan / đo / quét 3D | 8–20K ("measure app", khớp rộng); 1–3K | "lidar app", "floor plan app" tăng rất nhanh | Thấp đến vừa | Tăng ở cả sáu thị trường EU (+43% đến +82%) |
| 4 | Quét tài liệu ("scan to pdf", "pdf scanner app", "Dokumente scannen", "quét tài liệu") | ≥20K; 8–20K | Tăng hoặc ngang nền | Rất khó (KD 82) | EU ổn định hoặc tăng; VN "quét tài liệu" +86% |
| 5 | Định giá xu ("coin value app", "münzen wert scanner") | 1–3K | Tăng | Vừa, đã có người kiếm tiền | Có autocomplete ở DE |
| 6 | Bài tập ("math solver") | ≥20K (khớp rộng) | Tăng rất nhanh | Khó (Google, ByteDance) | n/a |
| 7 | Cảm biến khác (dò kim loại, decibel, thước thủy, nhịp tim qua camera) | 300–1K đến ≥20K | Lẫn lộn | Thấp | NL, UK: nhóm "đo" tăng |
| 8 | **Tránh làm định vị chính:** plant ID, QR, dịch ảnh, nhận diện giống chó | 3–20K | Giảm | Khó | Giảm ở mọi thị trường EU |

### Google Search Console làm được gì và không làm được gì

Search Console là **công cụ đo sau khi ra mắt, không phải công cụ nghiên cứu từ khóa trước khi ra mắt**. Nó cũng không bao giờ cho thấy hành vi tìm kiếm trên App Store. Hành vi đó phải đo trong App Store Connect (App Analytics → Sources → App Store Search) và trong báo cáo search term của Apple Ads.

| Hạng mục | GSC cung cấp | GSC không cung cấp / lưu ý |
|---|---|---|
| Phạm vi | Dữ liệu cho property đã xác minh (Domain qua DNS TXT hoặc URL-prefix) | Không có volume toàn thị trường; không có truy vấn của site bạn không sở hữu; không có dữ liệu trước ngày xác minh ([Google](https://support.google.com/webmasters/answer/9128668?hl=en)) |
| Chỉ số | Click, impression, CTR, vị trí trung bình ([Google](https://support.google.com/webmasters/answer/7042828?hl=en)) | Không có CPC, không có độ khó từ khóa |
| Chiều phân tích | Query, page, country, device, search appearance, date; loại web, image, video, news ([Performance report](https://support.google.com/webmasters/answer/7576553?hl=en)) | Query "ẩn danh" (ít hơn vài chục người dùng trong 2–3 tháng) bị loại khỏi bảng, nhưng vẫn tính trong tổng |
| Xuất dữ liệu | Giao diện xuất tối đa 1.000 dòng; API hoặc Looker Studio tới 50.000 dòng/ngày/site/loại tìm kiếm; bulk export sang BigQuery ([Search Central](https://developers.google.com/search/blog/2022/10/performance-data-deep-dive)) | Chỉ lưu 16 tháng cuốn chiếu; phải export để giữ dữ liệu cũ ([SEO Stack](https://www.seo-stack.io/blog/why-does-google-search-console-have-a-16-month-data-limit)) |
| Chất lượng dữ liệu | Click không bị ảnh hưởng | Impression bị thổi phồng từ 13/5/2025 đến 3/4/2026 ([SEOPress](https://www.seopress.org/newsroom/seo-news/april-2026/)); Google bỏ tham số &num=100 khoảng 12–14/9/2025, và 87,7% trong 319 site được phân tích mất impression ([Search Engine Land](https://searchengineland.com/google-num100-impact-data-462231)) |
| App Store | – | Hoàn toàn không có |

Quy trình dùng GSC sau khi ra mắt landing page gồm năm bước:
1. Xác minh một Domain property, cộng các URL-prefix property cho từng thư mục ngôn ngữ (/de/, /fr/, /it/, /es/, /nl/, /vi/). Nộp sitemap.
2. Bật BigQuery export ngay từ ngày đầu.
3. Sau 2–4 tuần, lọc query bằng regex theo cụm và theo quốc gia. Ví dụ: `scan|scanner|ocr|pdf`, `lidar|3d|measure|messen|mesure|meten|đo`, `identif|bestimmen|reconna|riconosc|herkennen|nhận diện`.
4. Ưu tiên sửa nội dung cho các query có nhiều impression và đang ở vị trí 8–20.
5. Viết lại title và meta cho các query có CTR thấp hơn nhiều so với trung bình của site.

Khi so impression GSC với Trends, chỉ nên so theo hướng đi, không so số tuyệt đối.

## Người dùng trả tiền cho đầu ra, không trả cho khoảnh khắc chụp

### Ma trận paywall: miễn phí gì, thu tiền gì

Gần như mọi app dẫn đầu đều cho miễn phí phần chụp cơ bản (quét, nhận diện, hoặc capture 3D) cùng một kiểu xuất cơ bản. Paywall đặt vào bốn nhóm:
- **Chất lượng và định dạng đầu ra:** OCR, PDF tìm kiếm được, file Office, bỏ watermark, định dạng 3D chuyên nghiệp.
- **Khối lượng:** không giới hạn lượt quét, lượt xuất, lượt nhận diện hoặc số dự án.
- **Cloud và năng lực tính toán:** sync, backup, xử lý trên cloud, AI chat.
- **"Chiều sâu" chuyên gia hoặc AI:** chuyên gia thực vật, gia sư AI, chẩn đoán bệnh cây.

Chỉ một thiểu số đặt hard paywall lên chính kết quả lõi. Cal AI ghi thẳng: "FOOD SCANNING ANALYSIS RESULTS REQUIRE A SUBSCRIPTION" ([App Store](https://apps.apple.com/us/app/id6480417616)).

| App | Miễn phí | Trả phí | Mô hình, trial |
|---|---|---|---|
| [Adobe Scan](https://www.adobe.com/devnet-docs/adobescan/ios/en/subscriptions.html) | Quét, cắt, bộ lọc, lưu PDF, chọn và copy chữ, danh thiếp sang danh bạ | Xuất Word/Excel/PowerPoint; gộp tới 20 file; mật khẩu PDF; tăng hạn mức OCR (listing ghi 5→100 trang, tài liệu cũ ghi 25→100) | Plus $4.99/tháng; Premium $9.99/tháng |
| [CamScanner](https://essexsoftware.com/scaniva/camscanner-free-vs-paid/) | Quét, PDF có watermark, quảng cáo, OCR chỉ xem trước, 200 MB cloud | Bỏ watermark, OCR đầy đủ, xuất độ phân giải gốc, 10 GB cloud, ký điện tử (nguồn là blog đối thủ) | Tuần, tháng, quý, năm |
| [Genius Scan](https://thegrizzlylabs.com/genius-scan/pricing) | Quét không giới hạn, không watermark, xử lý on-device, PDF nhiều trang | OCR và PDF tìm kiếm được, khóa Face ID, mã hóa PDF, tự xuất lên cloud, đặt tên thông minh, Genius Cloud | Ultra $39.99/năm; bản team $20–40/license/năm |
| [iScanner](https://apps.apple.com/us/app/id1040093707) | Quét, sửa, xem offline | OCR hơn 20 ngôn ngữ, AI Chat, xuất DOC/XLS/PPT, khóa PIN, cloud 10 hoặc 100 GB; bản free xuất 5 lần/ngày (nguồn bên thứ ba) | Chủ yếu gói tuần |
| [TurboScan](https://apps.apple.com/us/app/id1017559099) | Quét (theo bên thứ ba: 3 tài liệu) | Mở khóa một lần; "all scanning happens on your iPhone" | Trả một lần |
| [PictureThis](https://apps.apple.com/us/app/id1252497129) | Vài lượt nhận diện, có quảng cáo | Không giới hạn, chẩn đoán bệnh, hướng dẫn chăm sóc, chuyên gia 24/7 | Theo năm, trial 7 ngày |
| [Next Vision](https://apps.apple.com/us/app/id1461694973) (Picture Insect, Rock ID, CoinSnap) | Nhận diện có giới hạn | Không giới hạn, chuyên gia, bỏ watermark và quảng cáo | Theo năm, trial 7 ngày |
| [AIBY](https://apps.apple.com/us/app/id1665672552) (Coin ID, Plantum) | Có giới hạn | Không giới hạn | Gói tuần kèm trial 3 ngày là chủ đạo |
| [Photomath](https://support.google.com/photomath/answer/14330572?hl=en) | Giải không giới hạn, có từng bước | Video AI, giải thích sâu hơn, gợi ý | $9.99/tháng hoặc $69.99/năm ([Nibble](https://nibble-app.com/blog/photomath-app)) |
| [Gauth](https://apps.apple.com/us/app/id1542571008) | Có giới hạn | Mô hình mạnh nhất không giới hạn, gia sư, chuyên gia 24/7 | Trial 3 ngày; ưu đãi win-back |
| [Cal AI](https://apps.apple.com/us/app/id6480417616) | Chỉ phần onboarding | Kết quả quét món ăn (hard paywall) | Trial 3 ngày |
| [Yuka](https://help.yuka.io/l/en/article/dop80j54bb-paid-version-features) | Quét mã vạch online | Chế độ offline, tìm không cần mã vạch, cảnh báo dị ứng và không dung nạp | Khoảng $10–20/năm ([Glossy](https://www.glossy.co/beauty/yuka-beauty-wellness-product-scanning-app/)) |
| [Polycam](https://poly.cam/pricing) | Capture có giới hạn; **chỉ xuất GLTF**; 150 ảnh/model | Basic: nhiều định dạng mesh, splat không giới hạn. Business: point cloud, floor plan 2D/3D, đo nâng cao, AI report | Basic $149.99/năm; Business $400/người/năm |
| [KIRI Engine](https://apps.apple.com/us/app/id1577127142) | Quét không giới hạn; xuất ít nhất 3 lần/tuần | Tải lên từ camera roll, 3DGS | Pro $29.99–$49.99/năm |
| [magicplan](https://help.magicplan.app/using-magicplan-for-free) | Mọi tính năng, tối đa **2 dự án** | Không giới hạn dự án, team, tích hợp | $129.99–$899.99/năm |
| [Scaniverse](https://apps.apple.com/us/app/id1541433223) | Capture và xử lý splat on-device không giới hạn; xuất SPZ/PLY/GLB/FBX | Xử lý trên cloud, team, quét 360° | Plus $20/tháng hoặc $200/năm, bán trên web ([Niantic Spatial](https://www.nianticspatial.com/pricing)) |

Các tính năng trả phí lặp lại nhiều nhất, xếp theo tần suất:
1. Định dạng xuất nâng cao: Office, OBJ/FBX/USDZ/STL, point cloud, DXF, IFC.
2. Không giới hạn khối lượng.
3. Bỏ watermark.
4. OCR và PDF tìm kiếm được.
5. Bảo mật: Face ID, PDF có mật khẩu.
6. AI bổ sung: chat, tóm tắt, dịch, gia sư.
7. Chuyên gia thật.

Riêng app 3D đặt **đo đạc và floor plan ở tầng B2B cao nhất**. Vì vậy "đầu ra khảo sát chính xác" là ứng viên mạnh cho gói Pro.

Hai mẫu hợp nhất với app offline là Genius Scan và Scaniverse. Cả hai giữ phần chụp và xử lý on-device miễn phí, không giới hạn. Họ chỉ thu tiền cho đầu ra phục vụ công việc, hoặc cho thứ có chi phí biên thật như xử lý cloud. Đây cũng là câu chuyện dễ bảo vệ nhất trước người dùng và trước App Review.

Phàn nàn của người dùng xác nhận khoảng trống. Polycam bị chê "tăng giá hơn gấp đôi cho cùng tính năng" ([Trustpilot](https://www.trustpilot.com/review/poly.cam)). Người dùng magicplan than bị khóa khỏi các bản vẽ đã làm trong 3–4 năm, và gặp sai số 6–8 inch ([App Store reviews](https://apps.apple.com/us/app/magicplan/id427424432?see-all=reviews)). PictureThis bị tố "trial miễn phí không thật sự miễn phí" ([ComplaintsBoard](https://www.complaintsboard.com/picturethis-plant-identifier-b149857)).

### Giá theo storefront: Mỹ, Anh, EU và Việt Nam

Giá dưới đây là giá niêm yết trên storefront ngày 27/9/2026. GBP và EUR đã gồm VAT. Đức được dùng làm đại diện cho khu vực EUR. Mỗi ô dẫn nguồn theo mẫu `apps.apple.com/{us|gb|de|vn}/app/id…`, ví dụ [Adobe Scan VN](https://apps.apple.com/vn/app/id1199564834) và [Genius Scan DE](https://apps.apple.com/de/app/id377672876).

| App | Gói (tên IAP) | US | UK | EU (DE) | VN |
|---|---|---|---|---|---|
| Adobe Scan | Premium – monthly | $9.99 | £9.99 | 10,99 € | 229.000₫ |
| Adobe Scan | Plus – yearly | $19.99 | £19.99 | 22,99 € | 499.000₫ |
| CamScanner | Premium Account (1 year) | $59.99 | £58.99 | 66,99 € | 1.399.000₫ |
| Genius Scan | Ultra (năm) | $39.99 | £39.99 | 44,99 € | 999.000₫ |
| iScanner | 1 week Pro 100Gb | $4.99 | £4.99 | 4,99 € | 129.000₫ |
| iScanner | 1 year Pro 100Gb | n/a | £20.99 | 20,99 € | 599.000₫ |
| TurboScan (bản free) | Premium, trả một lần | $14.99 | £4.99 | 6,99 € | 49.000₫ |
| PictureThis | Pro (năm) | $39.99 | £34.99 | 34,99 € | 689.000₫ |
| Rock Identifier | Premium (năm) | $39.99 | £29.99 | 29,99 € | 699.000₫ |
| CoinSnap | Premium | $39.99 | £24.99 | 29,99 € | 699.000₫ |
| Coin ID (AIBY) | Weekly (3 days trial) | $6.99 | £6.99 | 7,99 € | 199.000₫ |
| Photomath | Plus (tháng) | $9.99 | £9.99 | 10,99 € | 229.000–299.000₫ |
| Gauth | Plus – monthly | $11.99 | £4.99 | 9,99 € | 49.000₫ |
| Cal AI | Unlimited (mức cao nhất) | $29.99 | £29.99 | 34,99 € | 799.000₫ |
| Polycam | Basic yearly | $149.99 | £149.99 | 179,99 € | 4.999.000₫ (bất thường) |
| Polycam | Pro yearly (gói cũ) | $199.99 | £149.99 | 199,99 € | 2.499.000₫ |
| KIRI Engine | Pro Annual | $49.99 | £43.99 | 50,99 € | 1.499.000₫ |
| 3d Scanner App | Weekly premium | $4.99 | £4.99 | 5,99 € | 149.000₫ |
| 3d Scanner App | Yearly premium | $69.99 | £69.99 | 79,99 € | 1.999.000₫ |
| magicplan | Sketch (1 năm) | $129.99 | £129.99 | 129,99 € | 1.499.000₫ |
| magicplan | Estimate (1 năm) | $899.99 | £899.99 | 899,99 € | 10.999.000₫ |

Ba khuôn mẫu định giá hiện ra. **Giá bằng EUR thường giữ nguyên chữ số của giá USD hoặc cao hơn một chút.** Next Vision là ngoại lệ, định giá gói năm ở Anh và Đức thấp hơn Mỹ. Ở Việt Nam, đa số app theo mức tự quy đổi của Apple. Một số app bản địa hóa mạnh: Gauth gói năm 299.000₫ so với $99.99 ở Mỹ, TurboScan 49.000₫, magicplan Sketch 149.000₫/tháng ([Gauth VN](https://apps.apple.com/vn/app/id1542571008)).

### Chuẩn chuyển đổi: châu Âu chuyển đổi thấp hơn Mỹ nhưng giữ khách lâu hơn

| Chỉ số | Toàn cầu / theo danh mục | Tây Âu | Bắc Mỹ | IN/SEA (đại diện VN) | Nguồn |
|---|---|---|---|---|---|
| Tải → trả tiền (D35) | Hard paywall 10,7% vs freemium 2,1%; H&F 2,9%; Business 2,6% | 2,0% | 2,6% | 1,4% | [RevenueCat 2026](https://www.revenuecat.com/state-of-subscription-apps) |
| Tải → trial (D30) | Business 9,1%; H&F 6,9%; Education và Utilities 6,5%; app AI 8,5% vs 5,6% | 5,0% | 7,1% | n/a | [RevenueCat](https://www.revenuecat.com/blog/growth/subscription-app-trends-benchmarks-2026) |
| Trial → trả tiền | H&F 37,7%; **Photo & Video 22,2%** (thấp nhất); trial ≤4 ngày 25,5%, 5–9 ngày 37,4%, 17–32 ngày 42,5% | 29,7% | 34,2% | Dưới một nửa Bắc Mỹ | [RevenueCat](https://www.revenuecat.com/state-of-subscription-apps) |
| RPI D14 | H&F $0.48; Business $0.31; Education $0.30; hard $2.32 vs freemium $0.27 | $0.25 | $0.38 | $0.08 | [RevenueCat](https://www.revenuecat.com/state-of-subscription-apps) |
| RPI D60 | Hard $3.09 vs freemium $0.38 | $0.33 | $0.55 | $0.11 | [RevenueCat](https://www.revenuecat.com/state-of-subscription-apps) |
| LTV thực năm đầu/người trả | H&F $35.64; Productivity $24.95; Education $22.82; app AI $30.16 vs $21.37 | $26.64 (các nguồn tóm tắt ghi $25–27) | ~$32 | $19.32 | [RevenueCat](https://www.revenuecat.com/state-of-subscription-apps) |
| Giá trung vị | Tuần $5.99; tháng $10; năm $34.80 | Tuần $7.03; tháng $9.99; năm $39.44 | Năm tới $39.99 | Khoảng 45–50% Bắc Mỹ | [RevenueCat](https://www.revenuecat.com/state-of-subscription-apps) |
| Hoàn tiền | 3–4% ở đa số danh mục; app AI 4,2% | Dưới 3% (báo cáo 2025) | 3,4% | 7,7% | [RevenueCat](https://www.revenuecat.com/state-of-subscription-apps) |
| Gia hạn lần đầu | Tuần 35–58%; tháng 53–61%; năm 23–40% | – | – | – | [RevenueCat](https://www.revenuecat.com/state-of-subscription-apps) |
| Cơ cấu doanh thu theo gói | Tuần 55,5%; năm 22,5%; tháng 11,7% | Gói năm chiếm ưu thế | – | – | [Adapty](https://adapty.io/blog/mobile-app-monetization-2026/) |
| Giá gói tháng | – | $15.25 (cao hơn Bắc Mỹ 39%; tăng 18%/năm) | $10.95 | – | [Adapty](https://adapty.io/blog/mobile-app-monetization-2026/) |
| Utilities | Cài → trial 13,8%; trial → trả tiền 26,2%; gia hạn đầu 61,7%; năm $38.42 | Giá năm Utilities châu Âu +70,5% trong 2 năm | – | – | [Adapty](https://adapty.io/blog/utilities-app-subscription-benchmarks/) |
| Hard vs soft paywall | LTV $41.90 vs $20.00; soft paywall chuyển đổi tốt hơn khoảng 50% | – | – | – | [Adapty](https://adapty.io/blog/high-performing-paywall-2026/) |
| Apple Ads | Trung vị 58 ngách CPA $1.43; ngách PDF Reader CPA $4.31 | UK $1.31/$2.02; DE $0.86/$1.34; FR $0.75/$1.11; NL $0.65/$1.07 (CPT/CPA) | $1.58/$2.51 | n/a | [Adapty](https://adapty.io/blog/apple-ads-benchmarks-by-niche/) |

Ba điểm thực dụng rút ra từ bảng.

**Thứ nhất, trial dài hơn chuyển đổi tốt hơn rõ rệt.** Trial 5–9 ngày đạt 37,4%, so với 25,5% của trial ≤4 ngày. Với trial 3 ngày, 55,4% bị hủy ngay ngày đầu. Tây Âu còn có "đuôi" chuyển đổi dài nhất: 21,2% lượt chuyển đổi đến từ tuần thứ 6 trở đi ([RevenueCat](https://www.revenuecat.com/blog/growth/subscription-app-trends-benchmarks-2026)). Với châu Âu, **gói năm kèm trial 7 ngày** hợp hơn gói tuần kèm trial 3 ngày.

**Thứ hai, gói tuần tạo nhiều doanh thu nhưng giữ khách kém.** Theo báo cáo 2025, chưa đến 5% người đăng ký gói tuần còn ở lại tới tháng thứ 6 ([RevenueCat 2025](https://www.revenuecat.com/state-of-subscription-apps-2025/)).

**Thứ ba, tỷ lệ thành công nền rất thấp.** 10% app đứng đầu chiếm 94,5% doanh thu ([Adapty](https://adapty.io/blog/mobile-app-monetization-2026/)). Ngay cả Photo & Video, danh mục có tỷ lệ cao nhất, cũng chỉ có 27,57% app mới đạt $1.000 doanh thu/tháng và 8,75% đạt $10.000/tháng trong vòng 2 năm ([RevenueCat 2025](https://www.revenuecat.com/state-of-subscription-apps-2025/)).

Có một mâu thuẫn chưa giải quyết giữa hai báo cáo. RevenueCat nói app AI bắt đầu trial nhiều hơn (8,5% vs 5,6%), còn Adapty nói ít hơn (5,31% vs 10,92%).

### Phí và luật thanh toán quyết định bạn giữ lại bao nhiêu

| Khu vực | Kênh | Phí Apple | Hệ quả cho indie dev | Nguồn |
|---|---|---|---|---|
| Toàn cầu | IAP qua Small Business Program (≤1 triệu USD proceeds năm trước, hoặc dev mới) | 15% | Mức mặc định nên đăng ký | [Apple SBP](https://developer.apple.com/app-store/small-business-program/) |
| Mỹ | Nút hoặc link ra web checkout | Hiện 0%. Apple đề xuất 15%/10%/5% (SBP 5%); Tòa Tối cao nhận xem xét 30/6/2026 | Vẫn phải có IAP: Cal AI bị gỡ 4/2026 vì chỉ dùng Stripe. Với SBP, web checkout làm giảm 9% tiền thực nhận trên mỗi người xem trong case study của Adapty | [MacRumors](https://www.macrumors.com/2026/04/21/apple-cal-ai-app-store-removal/), [Adapty](https://adapty.io/blog/app-to-web-paywalls-ios-one-year-data/), [AppleInsider](https://appleinsider.com/articles/26/09/14/apple-standing-its-ground-in-epics-app-store-fee-suit) |
| EU từ 1/10/2026 | IAP | 26%; **15% cho SBP** và cho thuê bao từ năm thứ hai | Kênh nên dùng | [Apple Newsroom](https://www.apple.com/newsroom/2026/08/apple-announces-changes-for-apps-in-the-european-union/) |
| EU | Xử lý thanh toán thay thế trong app | 20% / 10% | Dev tự lo VAT, cần EU VAT ID | [App Store Connect Help](https://developer.apple.com/help/app-store-connect/manage-tax-information/provide-tax-information-for-alternative-payment-options/) |
| EU | Link-out ra web | 15% / 10%, chỉ tính giao dịch trong 7 ngày sau khi bấm link | Dev thành người bán: phải lo VAT/OSS, nút rút lại hợp đồng, §312k | [Apple Developer](https://developer.apple.com/support/apps-in-the-eu) |
| EU | Phân phối ngoài App Store | Core Technology Commission 5% | Cần đạt điều kiện D&B, bảo lãnh 1 triệu USD, hoặc 1 triệu lượt cài | [Apple Developer](https://developer.apple.com/support/apps-in-the-eu) |
| EU | Phí cũ bị bãi bỏ | Core Technology Fee theo lượt cài, initial acquisition fee, store services fee | Phải giữ phương án thanh toán đã chọn trong 12 tháng | [Apple Developer](https://developer.apple.com/support/apps-in-the-eu) |

Ví dụ tính tay cho Đức: giá €9,99 đã gồm 19% VAT, tức khoảng €8,39 trước thuế. Sau phí SBP 15%, dev nhận khoảng **€7,13**. Với dev đang hưởng 15%, link-out chỉ tiết kiệm được 5 điểm phần trăm, trong khi gánh thêm phí cổng thanh toán, VAT và toàn bộ nghĩa vụ bảo vệ người tiêu dùng. **Nên dùng IAP ở EU.**

### Paywall kiểu nào bị Apple từ chối

Apple thực thi nguyên tắc "số tiền bị tính phải hiện rõ nhất". Guideline 3.1.2(c) yêu cầu mô tả rõ người dùng nhận được gì với mức giá đó. Guideline 5.6 cấm "raise prices in a tricky manner" và cấm lừa người dùng mua thứ họ không muốn ([App Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)).

Từ giữa tháng 1/2026, **paywall dạng toggle bị từ chối** mà không có báo trước. Đó là kiểu nút gạt chuyển giữa gói năm không trial và gói tuần có trial, mặc định để ở gói năm. Lý do Apple đưa ra là toggle "hides trials from users who don't engage with it" ([Adapty](https://adapty.io/blog/your-toggle-paywall-is-about-to-get-rejected/)).

Vụ gỡ Cal AI tháng 4/2026 liệt kê đủ các lỗi cần tránh ([MacRumors](https://www.macrumors.com/2026/04/21/apple-cal-ai-app-store-removal/)):
- bỏ IAP để dùng Stripe;
- hiển thị giá quy đổi theo tuần nổi bật hơn số tiền thực bị tính;
- toggle trial không nói rõ việc tự gia hạn;
- đẩy người vừa từ chối vào một luồng mua gói thứ hai.

## Một iPhone năm 2026 làm được gần hết mọi việc offline, trừ LiDAR và LLM trên máy cũ

Bộ SDK iOS 26/27 đủ để xây một app camera, quét, nhận diện, 3D hoặc AI hoàn toàn offline. Giới hạn nằm ở phần cứng: LiDAR chỉ có trên dòng Pro, và LLM on-device chỉ chạy trên máy có Apple Intelligence.

iOS 27 phát hành ngày 14/9/2026 và hỗ trợ từ iPhone 11 trở lên ([Apple Newsroom](https://www.apple.com/newsroom/2026/09/apple-debuts-iphone-18-pro-and-iphone-18-pro-max/), [AppleInsider](https://appleinsider.com/articles/26/06/08/ios-27-keeps-iphone-11-and-newer-compatibility)). Theo số của Apple tháng 6/2026, iOS 26 chạy trên **79% tổng số iPhone và 86% iPhone của 4 năm gần nhất** ([AppleInsider](https://appleinsider.com/articles/26/06/10/fewer-iphone-users-are-updating-to-ios-26-than-they-did-with-ios-18)). Vì vậy nên đặt **iOS 26 làm mức tối thiểu**. Các API chỉ có trên iOS 27 nên là phần nâng cấp, bọc trong `if #available(iOS 27, *)`.

| Phần cứng / API | Làm được gì offline | Thiết bị tối thiểu | Ngôn ngữ (VN / EU) | Hàm ý sản phẩm |
|---|---|---|---|---|
| Camera + VisionKit (`VNDocumentCameraViewController`, `DataScannerViewController`, `ImageAnalysisInteraction`) | Chụp tài liệu có nắn phối cảnh; đọc chữ và mã vạch trực tiếp; Live Text trên ảnh bất kỳ | iPhone 11+ (DataScanner cần A12 trở lên) | Live Text 24 ngôn ngữ, gồm VN, DE, FR, IT, ES, NL, DA, NO, SV, PL; **không có tiếng Phần Lan** ([Textora](https://textora.app/blog/live-text-supported-languages/)) | Lõi của mọi sản phẩm, chạy trên mọi iPhone |
| Vision `RecognizeDocumentsRequest` (iOS 26) | OCR 26 ngôn ngữ; nhận diện bảng, danh sách, đoạn văn, QR; tách email, số điện thoại, ngày, số tiền, mã vận đơn | iOS 26 | Danh sách 26 ngôn ngữ chưa công bố; kiểm tra lúc chạy ([WWDC25 #272](https://developer.apple.com/videos/play/wwdc2025/272/)) | Trích xuất hóa đơn và nhãn thành phần |
| `VNRecognizeTextRequest` | OCR; tiếng Việt dùng mã `vi-VT` | iOS 13+ | Phải đặt ngôn ngữ rõ ràng, nếu không dấu tiếng Việt bị đọc sai ([GitHub issue](https://github.com/ShawnPana/phone-harness/issues/91)) | Chế độ hóa đơn tiếng Việt |
| `DetectLensSmudgeRequest` (iOS 26) | Phát hiện ống kính bẩn (độ tin cậy 0–1) | iOS 26 | – | Nhắc "lau camera" trong app quét |
| Foundation Models (iOS 26) | LLM khoảng 3B tham số on-device; `@Generable` ép đầu ra có cấu trúc; gọi tool; LoRA; 4.096 token/phiên | **iPhone 15 Pro trở lên**, Apple Intelligence phải bật | 16 ngôn ngữ, gồm VN, DE, FR, IT, ES, NL, DA, NO, SV; **không có PL, FI** ([9to5Mac](https://9to5mac.com/2025/11/11/ios-26-1-brings-apple-intelligence-to-these-eight-new-languages/)) | Chuyển chữ thành struct Swift; phân loại chi phí; giải thích dị ứng |
| Foundation Models (iOS 27) | Nhận ảnh đầu vào; `OCRTool`, `BarcodeReaderTool`; RAG qua Spotlight; ví dụ WWDC26 in context 8.192 token | iOS 27 | – | Nhận diện mà không cần tự huấn luyện model; thiết bị hỗ trợ chưa xác nhận ([WWDC26 #241](https://developer.apple.com/videos/play/wwdc2026/241/)) |
| Private Cloud Compute qua Foundation Models | Model lớn hơn, context 32K; **cần mạng** | iOS 27 | – | Miễn phí cho dev dưới 2 triệu lượt tải đầu; chỉ nên là chế độ tùy chọn |
| Core ML / Core AI (iOS 27) | Chạy model tùy chỉnh; Core AI biên dịch trước (AOT) và chuyển từ PyTorch | Mọi máy iOS 26 (Core ML) | – | Model nhận diện nấm hoặc chất liệu riêng ([MacRumors](https://www.macrumors.com/2026/06/09/apple-outlines-major-ai-and-developer-tool-updates/)) |
| LiDAR: ARKit `sceneReconstruction`/`sceneDepth`, RoomPlan (iOS 16+), Object Capture (iOS 17+) | Quét phòng ra USD/USDZ; mesh; đo chính xác; quét vật thể ra USDZ | **Chỉ iPhone 12 Pro đến 18 Pro**; iPhone Air, 17, 17e không có | – | Gói cao cấp; cần phương án dự phòng ([Apple RoomPlan](https://developer.apple.com/augmented-reality/roomplan/), [WWDC23](https://developer.apple.com/videos/play/wwdc2023/10191/)) |
| TrueDepth (camera trước) | Mesh khuôn mặt, độ sâu phía trước | Máy có Face ID | – | Quét vật nhỏ không cần LiDAR |
| Translation framework | Dịch offline sau khi tải gói | Máy chạy iOS 26 (mức tối thiểu đề xuất) | Có VN và các ngôn ngữ EU chính ([Create with Swift](https://www.createwithswift.com/using-the-translation-framework-for-language-to-language-translation/)) | Thẻ dị ứng đa ngôn ngữ |
| `SpeechAnalyzer` / `SpeechTranscriber` (iOS 26) | Chuyển giọng nói thành chữ on-device, 42 locale | iOS 26 | Tiếng Việt chỉ có một nguồn thứ cấp xác nhận ([LoroNote](https://loronote.com/en/blog/apple-speechanalyzer-vs-whisper)) | Ghi chú giọng nói tại hiện trường |
| Core Motion, `CMAltimeter`, Core NFC, Nearby Interaction (UWB) | Chuyển động, độ cao tương đối, đọc thẻ NFC, khoảng cách và hướng giữa thiết bị | Mọi máy / barometer trên Pro / NFC từ iPhone 7 | – | Cảm biến phụ trợ |
| App Intents + Visual Intelligence | Nút Camera Control hoặc ảnh chụp màn hình → trả về `AppEntity` của app | Máy có Visual Intelligence | – | Được đưa vào Spotlight và Siri ([WWDC26 #297](https://developer.apple.com/videos/play/wwdc2026/297/)) |
| Background Assets do Apple lưu trữ | Tải model lớn, tới 200 GB/app; ODR bị deprecate từ iOS 27; gói cài tối đa 4 GB | iOS 26 | – | Giữ gói cài dưới 200 MB để tránh cảnh báo tải qua mạng di động ([App Store Connect](https://developer.apple.com/help/app-store-connect/reference/app-uploads/on-demand-resources-size-limits)) |

Apple không công bố tỷ lệ máy đang hoạt động hỗ trợ Apple Intelligence hay có LiDAR. Nhóm nghiên cứu ước tính khoảng **35–50%** iPhone đang dùng có Apple Intelligence và khoảng **25–35%** có LiDAR vào cuối 2026. Ước tính LiDAR dựa trên việc dòng Pro chỉ chiếm 38% doanh số iPhone ở Mỹ quý 1/2025, giảm từ 45% một năm trước ([9to5Mac dẫn CIRP](https://9to5mac.com/2025/04/23/iphone-16-pro-is-the-surprise-loser-in-apples-recent-sales/)). Ở Việt Nam, máy cũ và máy đã qua sử dụng phổ biến, nên tỷ lệ này có lẽ còn thấp hơn.

Hệ quả thiết kế rất rõ. Lõi sản phẩm phải chạy bằng Vision, VisionKit và Core ML trên mọi iPhone. Foundation Models và LiDAR là lớp nâng cấp, có kiểm tra `SystemLanguageModel.default.availability`, `RoomCaptureSession.isSupported` và `ObjectCaptureSession.isSupported`.

Lợi ích kinh tế của xử lý on-device là thật. Dữ liệu chỉ được xử lý trên máy thì không phải khai báo. Nhờ vậy app có thể gắn nhãn **"Data Not Collected"**, với điều kiện không có SDK analytics hay crash nào gửi dữ liệu đi ([Apple App Privacy](https://developer.apple.com/app-store/app-privacy-details/)). Chi phí biên trên mỗi người dùng cũng gần như bằng không.

## Sáu sản phẩm nên xây, xếp theo độ khớp với châu Âu

Thứ tự ưu tiên dưới đây dùng năm tiêu chí:
1. Lõi chạy trên mọi iPhone bằng Vision và VisionKit.
2. Gắn với một quy trình hoặc một quy định có ngày hiệu lực cụ thể ở châu Âu.
3. Có đầu ra đáng tiền.
4. Tránh các danh mục chung chung mà Guideline 4.3 đã siết.
5. Dùng tính năng offline làm lời hứa về niềm tin, không coi nó là tính năng chính.

Nhu cầu cho các sản phẩm đứng đầu dựa nhiều vào quy định và điểm yếu của đối thủ hơn là vào volume tìm kiếm đo được. Ví dụ, "receipt scanner" chỉ tăng 20% ở Mỹ, dưới mức nền. Vì vậy mọi lựa chọn đều cần kiểm chứng bằng Apple Ads và dữ liệu sau ra mắt.

| Hạng | Sản phẩm | Thiết bị tiếp cận | Bằng chứng nhu cầu | Cạnh tranh / rủi ro 4.3 | Rủi ro chính |
|---|---|---|---|---|---|
| **1** | **Sổ chứng từ riêng tư**: chụp hóa đơn, biên lai, e-invoice → phân loại → xuất cho kế toán. Nhắm UK MTD, Belege ở Đức, notes de frais ở Pháp; có chế độ VN cho hộ kinh doanh | Mọi iPhone iOS 26; phần trích xuất bằng LLM cần iPhone 15 Pro+ | UK MTD áp dụng từ 6/4/2026 cho khoảng 864.000 người có thu nhập trên £50K, ngưỡng hạ xuống £30K (2027) rồi £20K (2028) ([Wikipedia](https://en.wikipedia.org/wiki/Making_Tax_Digital), [ByteStart](https://www.bytestart.co.uk/news-insights/864000-sole-traders-and-landlords-face-new-mtd-reporting-rules-from-april-2026/)). Đức bắt buộc nhận e-invoice từ 1/1/2025 ([BMF](https://www.bundesfinanzministerium.de/Content/DE/FAQ/e-rechnung.html)). "scan to pdf" +186%, "ocr app" +643% | Head term rất khó (KD 82). Đối thủ ở Đức không xử lý on-device: WISO lưu trên server ([Buhl](https://www.buhl.de/steuer/app-belege-digitalisieren/)), SteuerGO gửi dữ liệu sang OpenAI ở Mỹ ([SteuerGO](https://www.steuergo.de/blog/intelliscan-die-revolution-der-steuererklaerung/)) | MeinElster+ miễn phí và chính thức ([heise](https://www.heise.de/news/MeinElster-Offizielle-App-zum-Einscannen-von-Rechnungen-verfuegbar-7531095.html)); quy tắc GoBD; không được tuyên bố được HMRC công nhận |
| **2** | **Máy quét nhãn thành phần và dị ứng dựa trên OCR**, offline bằng mọi ngôn ngữ EU (dị ứng, coeliac, thuần chay, du lịch) | Mọi iPhone (Live Text 24 ngôn ngữ) | "food scanner" +331%, "nutrition scanner" +917% (cả hai spike-inflated). Yuka thu $11,9M năm 2025, và đặt chế độ offline cùng cảnh báo dị ứng trong Premium ([Yuka](https://yuka.io/en/independence/), [FoodTimes](https://www.foodtimes.eu/consumers-and-health/yuka-app-nutrition-health-and-market-opportunities/)) | Yuka dựa vào mã vạch, cách chấm điểm bị chê thiếu minh bạch, khoảng 90% sản phẩm do người dùng thêm vào ([Glossy](https://www.glossy.co/beauty/yuka-beauty-wellness-product-scanning-app/)). App dị ứng (Alergio, AllergIQ) còn non trẻ | Trách nhiệm sức khỏe: phải định vị là "công cụ hỗ trợ, luôn đọc lại nhãn"; Guideline 1.4.1; danh sách 14 chất gây dị ứng của EU phải trích từ Quy định 1169/2011 trước khi dùng |
| **3** | **Quét phòng bằng LiDAR để kiểm kê đồ đạc và lập biên bản tình trạng nhà thuê** (PDF có dấu thời gian cho bảo hiểm, chuyển nhà, tiền cọc) | LiDAR (Pro) cho RoomPlan; ảnh và đo AR cho máy thường | "lidar app" +475%, "floor plan app" +238%, "room scanner" +129%. Nhóm 3D tăng ở cả sáu thị trường EU. Encircle bỏ app kiểm kê cho người dùng phổ thông ngày 17/12/2025 ([Re_Tera](https://getretera.com/encircle-alternative)) | Chưa thấy app phổ thông nào dùng LiDAR để quét phòng cho mục đích này. Mảng vẽ mặt bằng ở Đức đã đông (trên 5 app) | Chỉ khoảng 25–35% máy có LiDAR (ước tính); danh mục đang đầy dần trong 2026 |
| **4** | **Scan-to-Print**: file STL/3MF đúng tỷ lệ, kín nước, sẵn để in, xuất miễn phí | Object Capture trên iOS chỉ chạy trên máy LiDAR | Autocomplete có "3d scanner app for 3d printer", "3d scanner 3d druck", "3d scanner stl". Polycam chỉ cho xuất GLTF miễn phí ([Polycam pricing](https://poly.cam/pricing)). Có tiền lệ giá €4,99/lượt quét hoặc €29,99/năm ([Digital Production](https://digitalproduction.com/2026/08/20/gaussian-splats-on-the-iphone/)) | Một "3D scanner" chung chung dễ dính 4.3; phải nói rõ "sẵn để in" | Chất lượng của Object Capture; chỉ phục vụ được máy Pro |
| **5** | **App đồng hành hái nấm theo nguyên tắc an toàn trước**: nhật ký điểm hái offline, checklist đặc điểm có Vision hướng dẫn, cảnh báo loài dễ nhầm, xuất hồ sơ cho chuyên gia. **Không bao giờ kết luận "ăn được"** | Mọi iPhone; GPS và bản đồ offline | Autocomplete có ở DE, FR, IT, ES, UK. Picture Mushroom thu $200k/tháng, đứng #4 Grossing Education ở DK và #10 ở DE. Biên độ mùa vụ ở Ý là 19,9 lần | App nhận diện bằng AI đã đông. App kiểu sách tra kèm khóa định loại (Meine Pilze) thắng bài kiểm tra của Hội Nấm học Đức DGfM ([Utopia.de](https://utopia.de/ratgeber/pilze-bestimmen-3-apps-im-vergleich_175405/)) | App AI chỉ nhận đúng 49% mẫu, và 44% với nấm độc ([Clinical Toxicology](https://www.tandfonline.com/doi/abs/10.1080/15563650.2022.2162917)); phụ thuộc mùa vụ |
| **6** | **Gói "tiền khảo sát" cải tạo nhà và lắp heat pump cho chủ nhà**, làm module Pro của sản phẩm #3 | LiDAR + OCR tem thông số radiator | Chỉ thị EPBD yêu cầu hộ chiếu cải tạo và chứng chỉ năng lượng nâng cấp, hạn chuyển hóa vào luật quốc gia là 29/5/2026 ([BUILD UP](https://build-up.ec.europa.eu/en/resources-and-tools/articles/epbd-aligned-data-model-building-renovation-passports-oneclickreno)). Thợ ở Đức và Anh đã dùng công cụ LiDAR rộng rãi ([heiz.report](https://heiz.report/scannerapp.html), [Heat Engineer](https://heat-engineer.com/en/features/lidar-technology/)) | Phía thợ lắp đặt đã có SaaS B2B. **Cầu từ phía chủ nhà chưa được xác minh** | Không được tuyên bố tuân thủ DIN EN 12831 hay MCS |

### Phạm vi MVP, paywall và giá gợi ý

Giá gợi ý neo vào trung vị Tây Âu: tháng khoảng $9.99, năm khoảng $39.44 ([RevenueCat](https://www.revenuecat.com/state-of-subscription-apps)). Giá bằng bảng Anh và euro giữ cùng chữ số với giá USD. Giá Việt Nam dùng các bậc từ 49.000₫ đến 499.000₫. Những mức không có tiền lệ trực tiếp là suy luận của nhóm nghiên cứu.

| Sản phẩm | Phạm vi MVP | Miễn phí | Trả phí; giá gợi ý US / UK / EU / VN | Từ khóa ASO khởi điểm |
|---|---|---|---|---|
| 1. Sổ chứng từ | Chụp tài liệu bằng VisionKit → `RecognizeDocumentsRequest` lấy ngày, tổng tiền, VAT, người bán → phân loại bằng Foundation Models `@Generable` (máy cũ dùng luật cố định) → đọc XML ZUGFeRD/XRechnung → xuất CSV/Excel/PDF theo quý; khóa Face ID; không cần tài khoản | Chụp và lưu không giới hạn; xuất PDF đơn | Xuất cho kế toán, nhiều doanh nghiệp, tự phân loại, gói theo quý: **$/£/€29.99–49.99/năm** hoặc mua một lần €39–59; VN 49.000–499.000₫ | EN: "receipt scanner for taxes", "scan to pdf", "pdf scanner app". DE: "dokumente scannen", "scanner app kostenlos" ("Belege scannen" chưa có dữ liệu). FR/IT: "scanner pdf", "scanner documenti". VN: "quét tài liệu miễn phí" |
| 2. Nhãn dị ứng | OCR trực tiếp danh sách thành phần → từ điển on-device gồm các chất gây dị ứng EU, số E và từ đồng nghĩa đa ngôn ngữ → tô sáng theo hồ sơ → thẻ dị ứng offline dịch bằng Translation → giải thích bằng Foundation Models, có nhãn AI | Một hồ sơ, quét không giới hạn | Hồ sơ gia đình, thẻ du lịch, lịch sử: **$/£/€9.99–19.99/năm** (ngang mức Yuka) | EN: "food scanner", "nutrition scanner", "food scanner good or bad free". Từ khóa địa phương chưa có dữ liệu, phải đo bằng Apple Ads |
| 3. Kiểm kê LiDAR | RoomPlan theo từng phòng → mặt bằng có m² → ảnh từng món đồ, OCR số serial hoặc hóa đơn → PDF biên bản nhận/trả nhà có dấu thời gian → **xuất mọi định dạng miễn phí**; máy không LiDAR dùng ảnh kèm đo AR | Một bất động sản, xuất PDF và USDZ | Nhiều bất động sản, gói cho chủ nhà cho thuê, mẫu PDF có thương hiệu: mua một lần khoảng €14,99/nhà, hoặc khoảng €39,99/năm (suy luận) | "lidar room scanner", "room scanner", "floor plan scanner", "3d scan room". DE: "lidar scanner 3d". FR: "lidar plan". NL: "meten met camera", "afstand meten" |
| 4. Scan-to-Print | Hướng dẫn chụp bằng Object Capture → lấy tỷ lệ từ LiDAR → vá mesh cho kín nước, tạo đế phẳng → xuất STL/3MF/USDZ | Chụp, xem trước, một lượt xuất | Mua Pro một lần **$14.99–29.99**, hoặc €4,99/lượt quét chất lượng cao | "3d scanner app for 3d printer", "3d scanner stl", DE "3d scanner 3d druck", IT "lidar scanner 3d gratis", ES "escaner 3d gratis" |
| 5. Hái nấm an toàn | Nhật ký GPS offline, lịch mùa, checklist đặc điểm (phiến, vòng, bao gốc, bào tử), danh mục loài dễ nhầm, xuất hồ sơ cho chuyên gia tư vấn nấm (Pilzberater) | Nhật ký và nội dung cơ bản | Gói theo vùng (DE/AT/CH, FR, IT, PL, Bắc Âu), mua một lần **€7,99–14,99** | DE "pilze bestimmen kostenlos", "pilze erkennen". FR "reconnaissance champignons gratuit". IT "riconoscere funghi". ES "setas". UK "mushroom identifier" |
| 6. Tiền khảo sát cải tạo | Module của #3: kích thước cửa và cửa sổ, OCR tem radiator, diện tích sàn (Wohnfläche), xuất PDF/IFC cho thợ | Không có | **€9,99–19,99/nhà**, mua một lần | Chưa có dữ liệu; cần kiểm chứng |

**Nên xếp sổ chứng từ lên đầu vì bốn lý do.**
- Lõi chạy trên mọi iPhone.
- Nó bám vào bể doanh thu lớn nhất là quét tài liệu, với 22,1 triệu USD/tháng.
- Có các mốc quy định buộc người dùng phải số hóa, và các mốc này lặp lại khi ngưỡng MTD hạ vào 2027 và 2028.
- Ở Đức, cả hai đối thủ chính đều không xử lý on-device.

Khoảng 92% người châu Âu muốn ưu tiên quyền riêng tư và bảo mật ([Eurobarometer 2025](https://digital-strategy.ec.europa.eu/en/library/digital-decade-2025-special-eurobarometer)). Hơn nữa, **một codebase có thể phục vụ ba thị trường**: UK MTD, Belege ở Đức và sổ thu chi hộ kinh doanh ở Việt Nam. Từ 1/1/2026, hộ kinh doanh Việt Nam đã chuyển từ thuế khoán sang tự kê khai ([VietnamNet](https://vietnamnet.vn/bo-thue-khoan-sang-ke-khai-7-viec-ho-kinh-doanh-can-lam-truoc-1-1-2026-2473487.html)).

Có hai lập luận mạnh chống lại lựa chọn này. Thứ nhất, cầu tìm kiếm "receipt scanner" đang yếu. Thứ hai, ở Đức người làm công ăn lương đã có MeinElster+ miễn phí. Vì vậy nên nhắm vào người làm tự do, chủ nhà cho thuê và Kleinunternehmer (hộ kinh doanh nhỏ theo luật Đức), không nhắm người làm công ăn lương.

**Sản phẩm #2 và #3 bổ sung cho nhau.**
- #2 rộng hơn và chạy trên mọi máy, nhưng mang rủi ro sức khỏe.
- #3 hẹp hơn vì dựa vào LiDAR, nhưng có cầu tìm kiếm tăng nhanh nhất và ít đối thủ phổ thông trực tiếp.
- magicplan lọt top grossing ở Đức và Pháp, cho thấy người dùng khối nói tiếng Đức và Pháp trả tiền cho đo đạc.
- Chiêu "xuất miễn phí, thu tiền cho quy trình" đánh trúng lời phàn nàn cảm xúc nhất về Polycam và magicplan.

Hai hướng ở hạng B đáng cân nhắc nếu muốn xây thương hiệu hơn là tối đa doanh thu:
- **App đọc và mô tả cảnh offline cho người khiếm thị**, bằng các ngôn ngữ EU. Doanh thu trực tiếp yếu, nhưng tiềm năng được Apple giới thiệu cao. Người dùng khiếm thị trên AppleVis nói rõ họ lo "không biết app gửi ảnh đi đâu" ([AppleVis](https://www.applevis.com/forum/ios-ipados/through-ais-blind)).
- **Ghi âm và tóm tắt họp offline.** App ghi âm AI tăng 2.270% trong năm 2024 ([Appfigures](https://land.appfigures.com/rise-of-ai-apps-report-2025)).

### Những danh mục nên tránh

| Danh mục | Lý do tránh | Nếu vẫn làm, khác biệt bằng gì |
|---|---|---|
| Quét QR | Cầu Google giảm (US −19%, WW −29%); iPhone quét QR sẵn từ iOS 11; hay dính 4.3(b) ([FreeQR](https://freeqr.com/blog/qr-code-scanner-app), [AppCompliance](https://appcompliance.io/blog/apple-guideline-4-3-spam-rejection/)) | Không nên làm |
| Quét PDF hoặc "offline OCR" chung chung | KD 82; đối thủ có 1,4–1,9 triệu lượt đánh giá; đã có nhiều app "offline OCR, không thuê bao" (Off Lens, IND Text Scanner) ([Sonar](https://trysonar.app/keyword-difficulty/pdf-scanner/ios/us)) | Gắn với một quy trình cụ thể (sản phẩm #1) |
| Clone Cal AI | Khoảng 70 đối thủ; MyFitnessPal đã mua Cal AI; KD 79 ([TechCrunch](https://techcrunch.com/2026/03/02/myfitnesspal-has-acquired-cal-ai-the-viral-calorie-app-built-by-teens/)) | Chuyển sang dị ứng và thành phần (sản phẩm #2) |
| App nhận diện cây, xu, đá chung chung | Plant ID giảm ở mọi thị trường; Next Vision và Glority mở ngách mới trong vài tháng | Gói offline cho một vùng, giá minh bạch |
| App quét LiDAR 3D chung chung, app chụp splat | Trên 6 app splat mới trong 2026; đông ([Digital Production](https://digitalproduction.com/2026/08/20/gaussian-splats-on-the-iphone/)) | Đầu ra theo ngành dọc (sản phẩm #3, #4) |
| Nhận diện nấm "ăn được / độc" bằng AI | Độ chính xác 49%; ở San Diego có ca ngộ độc gắn với việc app nhận sai ([MushroomTracker](https://www.mushroomtracker.ca/blog/ai-mushroom-identification-safe-2026.html)) | Chỉ làm dạng đồng hành (sản phẩm #5) |
| Chấm điểm khuôn mặt, AI companion | Rủi ro danh tiếng; có 337 app AI companion đang có doanh thu ([Fortune](https://fortune.com/2024/07/01/looksmaxxing-apps-rate-teen-boys-faces-mental-health/), [TechCrunch](https://techcrunch.com/2025/08/12/ai-companion-apps-on-track-to-pull-in-120m-in-2025/)) | Không nên làm |

### Thiết kế paywall chung cho cả sáu sản phẩm

| Thành phần | Khuyến nghị | Căn cứ |
|---|---|---|
| Vị trí paywall | Cho chụp và xử lý miễn phí. Đặt paywall mềm đúng lúc người dùng xuất kết quả, kèm một ưu đãi ở màn onboarding | Mẫu Genius Scan và Scaniverse; paywall ở onboarding có trial chuyển đổi 1,35%, so với 0,89% khi đặt trong app ([Adapty](https://adapty.io/blog/high-performing-paywall-2026/)) |
| Hard hay soft | Thử A/B paywall cứng ở bước xuất so với freemium | Hard 10,7% so với freemium 2,1% ở D35, với tỷ lệ giữ chân năm đầu tương đương ([RevenueCat](https://www.revenuecat.com/state-of-subscription-apps)) |
| Gói | Gói năm là mặc định, thêm gói tháng. Ở châu Âu không dùng gói tuần. Có thêm tùy chọn mua trọn đời cho khối nói tiếng Đức | Cứ 4 app thì 1 app có gói trọn đời ([RevenueCat](https://www.revenuecat.com/state-of-subscription-apps)). Sở thích trả một lần của người Đức chỉ là giai thoại, chưa có dữ liệu |
| Trial | 7 ngày cho gói năm | Trial 5–9 ngày chuyển đổi 37,4%, so với 25,5% của trial ≤4 ngày |
| Hiển thị giá | Số tiền thực bị tính và chu kỳ ("€29,99/năm, tự gia hạn") phải là chữ lớn nhất. Giá quy đổi theo tháng chỉ là dòng phụ | Guideline 3.1.2(c) ([RevenueCat docs](https://www.revenuecat.com/docs/tools/paywalls/creating-paywalls/app-review)) |
| Bố cục | Đặt các gói cạnh nhau, **không dùng toggle**. Hiển thị mốc thời gian trial, ví dụ "Ngày 7: bị tính tiền". Nút đóng hiện rõ | Toggle bị từ chối từ giữa 1/2026 ([Adapty](https://adapty.io/blog/your-toggle-paywall-is-about-to-get-rejected/)) |
| Khi người dùng từ chối | Chỉ một lối ra, không đẩy tiếp sang gói thứ hai. Dùng win-back offer, offer code và Retention Messaging của Apple | Vụ Cal AI ([MacRumors](https://www.macrumors.com/2026/04/21/apple-cal-ai-app-store-removal/)); [Apple win-back](https://developer.apple.com/documentation/storekit/supporting-win-back-offers-in-your-app) |
| Hủy gói | Có link "Quản lý/hủy gói" dẫn thẳng tới phần cài đặt thuê bao của Apple | Chuẩn bị trước cho Digital Fairness Act và luật DMCC của Anh |
| Bản địa hóa paywall | A/B test bản dịch paywall trước khi A/B test giá | Test bản địa hóa có tỷ lệ thắng cao nhất, 62,3% ([Adapty](https://adapty.io/blog/high-performing-paywall-2026/)) |

## Checklist châu Âu và App Store trước ngày nộp

### Bản địa hóa theo storefront

Mọi storefront EU, trừ Anh và Ireland, đều index thêm tiếng Anh (U.K.) bên cạnh ngôn ngữ chính. Vì vậy metadata EN-UK là một **ô từ khóa thứ hai miễn phí** trên gần như toàn EU. Thụy Sĩ index cả DE, FR, IT và EN-UK. Bỉ index EN-UK, NL và FR ([Apple localizations reference](https://developer.apple.com/help/app-store-connect/reference/app-store-localizations)).

| Tier | Locale | Storefront chính (ngôn ngữ phụ được index) | Lưu ý |
|---|---|---|---|
| 1 (lúc ra mắt) | EN-US, EN-UK, DE, FR | UK (không có), IE (không có), DE (EN-UK), AT (EN-UK), CH (EN-UK, FR, IT), FR (EN-UK), BE (NL, FR) | Phủ Anh, khối nói tiếng Đức, Pháp và các thị trường doanh thu lớn nhất |
| 2 (1–3 tháng sau) | IT, ES, NL, SV, DA, NB | IT, ES (thêm Catalan), NL, SE, DK, NO; tất cả index thêm EN-UK | Bắc Âu có iOS 59–63%; Foundation Models hỗ trợ đủ các ngôn ngữ này |
| 3 | PL, PT-PT, FI, VI | PL, PT, FI, VN | Live Text **không có tiếng Phần Lan**; Foundation Models **không có tiếng Ba Lan và Phần Lan**; tiếng Việt được hỗ trợ đầy đủ |

Bản địa hóa không dừng ở metadata. Cần dịch cả giao diện và dữ liệu mà model trả ra: tên loài theo tên địa phương kèm tên Latin, đơn vị mét và m², quy ước của Thụy Sĩ (CHF, viết "ss" thay cho "ß"). Ảnh chụp màn hình đầu tiên nên nêu lời hứa offline bằng ngôn ngữ địa phương, ví dụ "100% offline – keine Daten verlassen dein iPhone". Nên dùng một bộ từ khóa riêng cho từng locale thay vì dịch nguyên văn.

### Checklist tuân thủ châu Âu

| # | Hạng mục | Trạng thái và mốc thời gian | Có áp dụng nếu chỉ bán qua Apple IAP? | Việc cần làm | Nguồn |
|---|---|---|---|---|---|
| 1 | **Điều khoản EU của Apple theo DMA** | Hiệu lực **1/10/2026** (công bố 18/8/2026); Attachment 14 của Apple Developer Program License Agreement thay thế các phụ lục EU cũ | Có | Đăng ký Small Business Program để IAP chỉ mất 15%. Chưa bật cổng thanh toán thay thế hay link-out, vì lựa chọn phải giữ trong 12 tháng | [Apple Newsroom](https://www.apple.com/newsroom/2026/08/apple-announces-changes-for-apps-in-the-european-union/), [Apple Developer](https://developer.apple.com/support/apps-in-the-eu) |
| 2 | **DSA trader status** | Bắt buộc từ 16/10/2024; app thiếu thông tin bị gỡ khỏi EU từ 17/2/2025 | Có: app có thu tiền thì dev là "trader" | Khai địa chỉ, số điện thoại, email đã xác minh; các thông tin này **hiển thị công khai**. Nên dùng địa chỉ doanh nghiệp hoặc văn phòng ảo, không dùng địa chỉ nhà riêng | [App Store Connect Help](https://developer.apple.com/help/app-store-connect/manage-compliance-information/manage-european-union-digital-services-act-trader-requirements/), [Apple News](https://developer.apple.com/news/?id=einwn76m) |
| 3 | **GDPR** | Đang áp dụng; phạt tới €20 triệu hoặc 4% doanh thu toàn cầu | Có, nếu xử lý dữ liệu cá nhân của người ở EU | Xử lý on-device, không dùng SDK analytics hay quảng cáo, để được nhãn "Data Not Collected". Có privacy policy ở mọi ngôn ngữ. Nếu gửi ảnh lên server thì cần cơ sở pháp lý, hợp đồng xử lý dữ liệu (DPA) và cơ chế chuyển dữ liệu ra ngoài EU | [EUR-Lex](https://eur-lex.europa.eu/eli/reg/2016/679/oj), [Apple](https://developer.apple.com/app-store/app-privacy-details/) |
| 4 | **European Accessibility Act (EAA)** | Áp dụng từ 28/6/2025; dịch vụ đã có trước được tới 28/6/2028 nếu không cập nhật lớn | Doanh nghiệp siêu nhỏ (dưới 10 người **và** doanh thu ≤€2 triệu) được miễn phần dịch vụ | Vẫn hỗ trợ VoiceOver, Dynamic Type, độ tương phản. Cân nhắc khai Accessibility Nutrition Labels | [EUR-Lex](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX%3A32019L0882), [Level Access](https://www.levelaccess.com/compliance-overview/european-accessibility-act-eaa/) |
| 5 | **AI Act Điều 50** | Áp dụng từ **2/8/2026**; phạt tới €15 triệu hoặc 3%. Hệ thống generative đã có trên thị trường được gia hạn tới 2/12/2026 cho yêu cầu đánh dấu theo Điều 50(2) | Chỉ khi có chatbot, nội dung sinh ra, nhận diện cảm xúc hoặc phân loại sinh trắc | OCR, phân loại và đo LiDAR thường nằm ngoài phạm vi. Nếu dùng Foundation Models để trò chuyện hay sinh văn bản thì phải báo người dùng đang tương tác với AI và gắn nhãn "AI-generated / KI-generiert" | [Goodwin](https://www.goodwinlaw.com/en/insights/publications/2026/08/alerts-technology-dpc-eu-ai-act-transparency-obligations-now-in-force), [Gibson Dunn](https://www.gibsondunn.com/eu-ai-act-omnibus-agreement-postponed-high-risk-deadlines-and-other-key-changes/) |
| 6 | **Nút rút lại hợp đồng EU** (Chỉ thị 2023/2673) | Áp dụng từ **19/6/2026** cho hợp đồng B2C ký qua website, app hoặc phần mềm | Chưa có hướng dẫn chính thức. Apple là bên bán chính thức (merchant of record) và đã có quyền rút 14 ngày qua Purchase History | Bắt buộc nếu bán qua web: nút "withdraw from the contract here" luôn khả dụng trong 14 ngày, xác nhận hai bước, gửi xác nhận trên phương tiện lưu trữ bền | [Arnold & Porter](https://www.arnoldporter.com/en/perspectives/advisories/2026/05/eu-withdrawal-button-uk-subscription-rules-and-data-protection-risks-for-us-online-sellers), [Heuking](https://www.heuking.de/en/news-events/newsletter-articles/detail/new-cancellation-button-what-companies-must-implement-by-june-19-2026.html) |
| 7 | **§312k BGB "Kündigungsbutton"** (nút hủy thuê bao, Đức) | Áp dụng từ 1/7/2022; tòa án Đức thực thi tích cực | Chưa có nguồn khẳng định cho IAP | Thêm link hủy gói dẫn sang cài đặt Apple. Nếu bán qua web thì phải có nút "Jetzt kündigen", không bắt đăng nhập | [§312k](https://www.gesetze-im-internet.de/bgb/__312k.html), [Bird & Bird](https://www.twobirds.com/de/insights/2025/germany/k%C3%BCndigungsbutton-nach-%C2%A7-312k-bgb-%E2%80%93-eine-rechtsprechungs%C3%BCbersicht) |
| 8 | Quyền rút 14 ngày trên App Store | Theo điều khoản Apple Media Services | Apple xử lý | Không cần tự hoàn tiền cho giao dịch IAP | [Apple UK terms](https://www.apple.com/uk/legal/internet-services/itunes/uk/terms.html) |
| 9 | VAT | Apple là bên bán chính thức với IAP, tự thu và nộp VAT | Apple xử lý | Dùng cổng thanh toán thay thế hoặc link-out thì cần EU VAT ID | [App Store Connect Help](https://developer.apple.com/help/app-store-connect/manage-tax-information/provide-tax-information-for-alternative-payment-options/) |
| 10 | Luật thuê bao DMCC của Anh | **Dự kiến** mùa xuân 2027; áp dụng cả với doanh nghiệp ngoài Anh | Chủ yếu với bán ngoài IAP | Công bố rõ giá sau trial, ngày gia hạn và cách hủy trước khi mua. Chuẩn bị nhắc gia hạn và hai kỳ cooling-off 14 ngày | [Arnold & Porter](https://www.arnoldporter.com/en/perspectives/advisories/2026/05/eu-withdrawal-button-uk-subscription-rules-and-data-protection-risks-for-us-online-sellers) |
| 11 | Digital Fairness Act | **Mới là đề xuất**, dự kiến quý 4/2026 | – | Không dùng dark pattern ngay từ đầu | [EP Legislative Train](https://www.europarl.europa.eu/legislative-train/theme-protecting-our-democracy-upholding-our-values/file-digital-fairness-act) |
| 12 | Quy định sử dụng Foundation Models | Đang áp dụng | Nếu dùng LLM của Apple | Không dùng cho dịch vụ y tế, pháp lý hay tài chính có quản lý; không phân loại người bằng dữ liệu sinh trắc | [Apple acceptable use](https://developer.apple.com/apple-intelligence/acceptable-use-requirements-for-the-foundation-models-framework/) |
| 13 | Cảnh báo theo ngành | – | – | Nấm và cây: "không bao giờ ăn chỉ dựa vào app" ([agrarheute](https://www.agrarheute.com/land-leben/pilzvergiftungen-giftnotruf-warnt-pilz-apps-585983)). Dị ứng: "công cụ hỗ trợ, luôn đọc lại nhãn". Thuế: không tuyên bố được HMRC công nhận. Heat-loss: không tuyên bố tuân thủ DIN EN 12831 hay MCS | [Wikipedia MTD](https://en.wikipedia.org/wiki/Making_Tax_Digital) |

### Checklist nộp App Store

| Hạng mục | Quy định / mốc | Rủi ro với app dùng cảm biến | Việc cần làm | Nguồn |
|---|---|---|---|---|
| **4.3(b) Spam** | Siết ngày **8/6/2026**: Apple có thể gỡ app trong danh mục bão hòa "if they are not updated, improved, or do not attract customers"; app làm cẩu thả có thể khiến dev bị loại khỏi Developer Program | App QR, máy tính và quét PDF chung chung là nhóm hay bị từ chối (theo bên thứ ba, không phải văn bản của Apple) | Mỗi ngách dọc một app mạnh, không làm bản reskin. Ghi rõ điểm khác biệt trong Review Notes. Cập nhật đều đặn | [App Review Guidelines](https://developer.apple.com/app-store/review/guidelines/), [9to5Mac](https://9to5mac.com/2026/06/09/apple-tightens-app-review-guidelines-against-apps-that-do-not-add-value-to-the-app-store/), [TechCrunch](https://techcrunch.com/2026/06/09/apple-says-it-may-remove-apps-from-the-app-store-if-they-dont-attract-users/) |
| 4.2 Tính năng tối thiểu | App phải "useful, unique, or app-like" | Wrapper mỏng quanh API của Apple | Làm trọn quy trình chụp → cấu trúc hóa → xuất | [Guidelines](https://developer.apple.com/app-store/review/guidelines/) |
| 2.1 Hoàn chỉnh | App crash bị từ chối; IAP phải hiển thị và hoạt động được khi review | Crash khi người dùng từ chối quyền, hoặc khi chạy trên máy không có LiDAR | Kiểm tra `isSupported` và `availability`; test trên máy không phải Pro; nếu cần thì khai `UIRequiredDeviceCapabilities` | [Guidelines](https://developer.apple.com/app-store/review/guidelines/) |
| 2.3 / 2.3.1(a) | Không có tính năng ẩn; không quảng cáo sai sự thật | Ảnh chụp màn hình phóng đại độ chính xác | Mô tả tính năng mới cụ thể trong Notes; không hứa kiểu "nhận diện mọi bệnh" | [Guidelines](https://developer.apple.com/app-store/review/guidelines/) |
| 4.2.3(ii) | Phải công bố dung lượng tải thêm và hỏi người dùng trước | Tải model hoặc gói ngôn ngữ ở lần mở đầu tiên | Dùng Background Assets do Apple lưu trữ; giữ gói cài dưới 200 MB | [Guidelines](https://developer.apple.com/app-store/review/guidelines/), [WWDC25 notes](https://wwdcnotes.com/documentation/wwdcnotes/wwdc25-325-discover-applehosted-background-assets/) |
| 2.5.2 | Không tải code làm thay đổi chức năng | Cập nhật trọng số model | Coi trọng số là dữ liệu. Apple chưa có tuyên bố rõ ràng cho phép hay cấm | [Guidelines](https://developer.apple.com/app-store/review/guidelines/) |
| 3.1.1 / 3.1.2 | Mở khóa tính năng phải qua IAP; thuê bao tối thiểu 7 ngày và phải có giá trị liên tục ("ongoing value") | Paywall chặn chức năng cơ bản; gói tuần không có giá trị liên tục | Theo bảng thiết kế paywall ở trên. Trial cho app không bán thuê bao dùng IAP non-consumable $0 đặt tên "XX-day Trial" | [Guidelines](https://developer.apple.com/app-store/review/guidelines/) |
| 5.6 Hành vi của dev | Không thao túng, không tăng giá kiểu đánh lừa | Chuỗi ưu đãi nối tiếp sau khi người dùng từ chối | Chỉ một lối từ chối | [Guidelines](https://developer.apple.com/app-store/review/guidelines/) |
| 5.1.1 Quyền riêng tư | Link privacy policy trong App Store Connect và trong app; purpose string phải rõ; nếu có tạo tài khoản thì phải cho xóa tài khoản trong app | Purpose string mơ hồ kiểu "App needs camera" bị từ chối | Viết cụ thể `NSCameraUsageDescription`, `NSPhotoLibraryUsageDescription`, `NSMicrophoneUsageDescription`, `NFCReaderUsageDescription`, `NSMotionUsageDescription`, `NSLocationWhenInUseUsageDescription`. Không bắt đăng nhập | [Guidelines](https://developer.apple.com/app-store/review/guidelines/), [Apple doc](https://developer.apple.com/documentation/uikit/requesting-access-to-protected-resources) |
| 5.1.2 | Phải công bố và xin phép trước khi chia sẻ dữ liệu với AI bên thứ ba | Chế độ online dùng Private Cloud Compute, hoặc Claude/Gemini qua Foundation Models | Chỉ bật chế độ online khi người dùng chủ động chọn, có xin phép rõ ràng | [Guidelines](https://developer.apple.com/app-store/review/guidelines/) |
| 1.4.1 Y tế | App có thể đưa dữ liệu sai hoặc dùng để chẩn đoán bị soát kỹ; cấm đo huyết áp, đường huyết... chỉ bằng cảm biến của máy | App dị ứng, soi da, nấm | Không chẩn đoán; nhắc người dùng hỏi bác sĩ hoặc chuyên gia | [Guidelines](https://developer.apple.com/app-store/review/guidelines/) |
| SDK và target | Xcode 26 + iOS 26 SDK bắt buộc từ **28/4/2026**; target tối thiểu iOS 13 từ **9/9/2026** | – | Build bằng Xcode 26 trở lên; Xcode 27 chỉ chạy trên máy Mac Apple silicon | [Apple upcoming requirements](https://developer.apple.com/news/upcoming-requirements/) |
| Phân loại độ tuổi | Nhãn mới 4+, 9+, 13+, 16+, 18+; bảng câu hỏi mới, hạn trả lời **31/1/2026** | Nếu chưa trả lời thì không cập nhật app được | Trả lời bảng câu hỏi; có thể đặt nhãn theo từng nước | [Apple Developer News](https://developer.apple.com/news/?id=ks775ehf) |
| Privacy manifest | Bắt buộc từ 1/5/2024 với các API "required reason" (UserDefaults, file timestamp, disk space...) | SDK bên thứ ba | Thêm `PrivacyInfo.xcprivacy`; SDK phổ biến phải có manifest và chữ ký | [Apple](https://developer.apple.com/documentation/bundleresources/adding-a-privacy-manifest-to-your-app-or-third-party-sdk) |
| Nhãn quyền riêng tư | "Data Not Collected" chỉ đúng khi không có dữ liệu nào rời máy | Thêm Firebase hoặc Crashlytics sẽ làm đổi nhãn | Không dùng SDK gửi dữ liệu ra ngoài | [Apple App Privacy](https://developer.apple.com/app-store/app-privacy-details/) |
| DSA trader status | Xem checklist EU, mục 2 | Thiếu thì không phát hành được ở EU | Hoàn tất trước khi nộp | [Apple](https://developer.apple.com/news/upcoming-requirements/) |
| Accessibility Nutrition Labels | Hiện tự nguyện; Apple cho biết sau này sẽ bắt buộc | – | Chỉ khai một tính năng khi mọi tác vụ chính dùng được với tính năng đó | [Apple Support](https://support.apple.com/en-us/123073) |
| Tỷ lệ từ chối (tham khảo) | Năm 2024 có 1.931.400 lượt nộp bị từ chối (khoảng 25%); 2.1 là lý do hàng đầu | – | Tự test kỹ trước khi nộp | [MacRumors](https://www.macrumors.com/2025/05/30/app-store-2024-transparency-report/) |

## Kết luận

Nghiên cứu này thay đổi cách nhìn "offline". Offline không phải là sản phẩm; nó là **đòn bẩy chi phí và niềm tin**. Tiền của mảng camera đang nằm ở các app nhận diện chạy trên cloud và các bản clone thu phí theo tuần. Những app offline có kiếm được tiền là nhờ bán đầu ra (Genius Scan, iScanner) hoặc đặt chính chế độ offline sau paywall (Yuka). Với một indie developer, bộ công cụ on-device của Apple xóa gần hết chi phí biên và rủi ro GDPR. Từ đó dev có thể thu tiền cho đúng sản phẩm cuối của quy trình: file CSV gửi kế toán, biên bản PDF có dấu thời gian, file STL sẵn để in.

Châu Âu có ba thứ Mỹ không có:
- các mốc quy định có ngày cụ thể và lặp lại, như ngưỡng MTD năm 2027 và 2028, E-Rechnung, EPBD;
- khoản trả thêm cho quyền riêng tư;
- chi phí Apple Ads thấp (CPT ở Đức chỉ bằng khoảng 54% ở Mỹ), khiến việc thử nghiệm ở EU trước rẻ hơn.

Lợi thế cấu trúc của một developer Việt Nam là Live Text và Foundation Models đã phủ tám ngôn ngữ EU ưu tiên cùng tiếng Việt, không tốn chi phí server theo ngôn ngữ. Vì vậy một codebase có thể phục vụ cả UK MTD, Belege ở Đức và sổ thu chi hộ kinh doanh ở Việt Nam.

Điểm yếu cần thừa nhận là bằng chứng cầu cho các sản phẩm hạng đầu dựa vào quy định và điểm yếu của đối thủ nhiều hơn vào volume đo được. Google Trends không thấy "Belege scannen", và "receipt scanner" đang dưới mức nền. Vì vậy giai đoạn sau ra mắt nên được coi là giai đoạn đo lường. Các công cụ đo gồm chiến dịch Apple Ads exact-match theo từng storefront; mục App Store Connect → Sources; và GSC trên landing page đa ngôn ngữ, có BigQuery export ngay từ ngày đầu. Số liệu thật từ các nguồn này sẽ thay cho các dải ước tính từ Trends. Nếu chúng không xác nhận được cầu ở Đức và Anh, nên chuyển engine sang sản phẩm #2 hoặc #3, vì cả ba dùng chung lõi Vision/OCR.
