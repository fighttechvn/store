# Kế hoạch top 5 app iOS dùng cảm biến, ưu tiên châu Âu

Kế hoạch này dựa trên báo cáo [App iPhone offline dùng cảm biến](App%20iPhone%20offline%20d%C3%B9ng%20c%E1%BA%A3m%20bi%E1%BA%BFn.md) (dữ liệu thu ngày 27/9/2026). Số thị trường lấy từ báo cáo đó. Mốc thời gian, số tuần xây dựng và các mục tiêu nội bộ là **ước tính của kế hoạch**, giả định 1–2 dev iOS.

## Tóm tắt

- Làm 5 app theo thứ tự: **(1) Sổ chứng từ riêng tư → (3) Kiểm kê LiDAR → (2) Nhãn dị ứng → (4) Scan-to-Print → (5) Hái nấm**. Số trong ngoặc là thứ hạng trong báo cáo. Đề xuất số 6 (tiền khảo sát cải tạo nhà) được gộp vào app 3 làm module Pro.
- Cả 5 app dùng chung một lõi: chụp, OCR, trích xuất có cấu trúc, xuất file, paywall StoreKit 2, bản địa hóa và cam kết không thu dữ liệu.
- Lịch ra mắt bám mùa cao điểm tìm kiếm: app 1 ra đầu 12/2026 để kịp mùa thuế tháng 1–2; app 2 ra tháng 5/2027 trước mùa du lịch; app 5 ra cuối 7/2027 trước mùa nấm tháng 8–10.
- **Quảng cáo Apple Ads chỉ hoàn vốn năm đầu khi tỷ lệ tải → trả tiền cao cỡ hard paywall.** Ở mức freemium trung vị Tây Âu (2,0%), không app nào hoàn vốn. App 2 và app 5 có giá thấp nên phải tăng trưởng bằng ASO, cộng đồng và mùa vụ.
- Việc đầu tiên là lấy volume từ khóa thật bằng Google Ads Keyword Planner. Đây là khoảng trống dữ liệu lớn nhất của nghiên cứu.

## 1. Tổng hợp số liệu cho 5 app

| # | App | Cầu tìm kiếm (Google, thay đổi 2 năm) | Doanh thu tham chiếu (Sensor Tower, iOS toàn cầu, T8/2026) | Thiết bị tiếp cận | Thị trường đợt 1 | Giá neo |
|---|---|---|---|---|---|---|
| 1 | Sổ chứng từ riêng tư | "scan to pdf" 8–20K/tháng, +186%\*; "ocr app" +643%; "receipt scanner" +20% (dưới nền); DE "Dokumente scannen" +23% | Bể quét tài liệu $22,1M/tháng (19 app); iScanner $4M; Genius Scan $300k | Mọi iPhone iOS 26; phần trích xuất bằng AI cần iPhone 15 Pro+ | UK, DE, FR, EN-US; chế độ VN | $/£/€29.99–49.99/năm hoặc €39–59 một lần |
| 2 | Nhãn thành phần và dị ứng | "food scanner" 3–8K, +331%\*; "nutrition scanner" +917%\* | Yuka $1M/tháng iOS ($11,9M premium năm 2025); Foodvisor $2M/tháng | Mọi iPhone (Live Text 24 ngôn ngữ) | FR, DE, IT, ES, NL, UK | $/€9.99–19.99/năm |
| 3 | Kiểm kê LiDAR và biên bản nhà thuê | "lidar app" +475%; "floor plan app" +238%; "room scanner" +129%\*; nhóm 3D tăng ở cả 6 nước EU | magicplan top grossing DE #49, FR #64; Polycam top grossing ở US/UK/DE/FR | RoomPlan cần LiDAR (25–35% máy, ước tính); máy khác dùng ảnh + đo AR | UK, DE, FR, NL | €14,99/nhà một lần hoặc €39,99/năm |
| 4 | Scan-to-Print 3D | "3d scanner app" +86%; FR/IT "scanner 3d" +43–44%; autocomplete "3d scanner stl", "3d scanner 3d druck" | 3d Scanner App $69.99/năm; KIRI $49.99/năm; Polycam bản free chỉ xuất GLTF | Chỉ máy LiDAR | DE, UK, US, FR, IT | $14.99–29.99 một lần |
| 5 | Đồng hành hái nấm | "mushroom identifier" −10% (US); IT "riconoscere funghi" −13%, biên độ mùa vụ 19,9×; autocomplete ở DE, FR, IT, ES, UK | Picture Mushroom $200k/tháng; #4 Grossing Education ở DK, #10 ở DE | Mọi iPhone | DE/AT/CH, FR, IT, PL, Bắc Âu | €7,99–14,99 một lần theo vùng |

\* spike-inflated: đỉnh tháng 4–6/2026 cao gấp 3 lần trở lên so với trung vị trước đó, nên mức tăng thật có thể nhỏ hơn.

## 2. Lộ trình 12 tháng (10/2026 – 9/2027)

| Hạng mục | T10 | T11 | T12 | T1/27 | T2 | T3 | T4 | T5 | T6 | T7 | T8 | T9 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Xác thực và thủ tục | ■ | | | | | | | | | | | |
| Lõi dùng chung | ■ | ■ | | | | | | | | | | |
| 1 · Sổ chứng từ | ■ | ■ | ◆ ra mắt | đo ● | đo ● | | | | | | | |
| 3 · Kiểm kê LiDAR | | | | ■ | ■ | ◆ ra mắt | đo | | | | | |
| 2 · Nhãn dị ứng | | | | | | ■ | ■ | ◆ ra mắt | đo | | | |
| 4 · Scan-to-Print | | | | | | | | ■ | ■ ◆ | đo | đo | |
| 5 · Hái nấm | | | | | | nội dung | nội dung | nội dung | ■ | ■ ◆ | đo ● | đo ● |

■ xây dựng · ◆ ra mắt · ● mùa cao điểm tìm kiếm. Mỗi app có 8 tuần đo lường trước khi quyết định dừng hay đẩy mạnh (mục 6).

Lý do thứ tự:
- **App 1 trước:** chạy trên mọi iPhone, bám bể doanh thu lớn nhất, có mốc quy định lặp lại (ngưỡng UK MTD hạ xuống £30K năm 2027 và £20K năm 2028), và đối thủ ở Đức không xử lý on-device.
- **App 3 thứ hai:** dùng lại phần OCR và xuất PDF của app 1; có từ khóa tăng nhanh nhất; lấp khoảng trống Encircle để lại khi bỏ app kiểm kê phổ thông (17/12/2025).
- **App 2 thứ ba:** phạm vi rộng nhất nhưng có rủi ro sức khỏe, cần thời gian dựng từ điển 9 ngôn ngữ cẩn thận.
- **App 4 thứ tư:** nhỏ, dùng lại phần LiDAR của app 3.
- **App 5 cuối:** phụ thuộc mùa vụ và nội dung theo vùng. Nội dung cần chuẩn bị song song từ tháng 3.

## 3. Lõi dùng chung

| Module | API Apple | Dùng ở app |
|---|---|---|
| Chụp và nhận dạng chữ | `VNDocumentCameraViewController`, `DataScannerViewController`, `RecognizeDocumentsRequest` (iOS 26), `VNRecognizeTextRequest` với mã `vi-VT` cho tiếng Việt | 1, 2, 3, 5 |
| Trích xuất có cấu trúc | Foundation Models `@Generable`, kiểm tra `SystemLanguageModel.default.availability`; luật cố định cho máy không có Apple Intelligence | 1, 2, 3 |
| Xuất file | PDFKit / `UIGraphicsPDFRenderer`, CSV, ModelIO (USDZ, OBJ, STL) | Cả 5 |
| Paywall | StoreKit 2; gói năm mặc định + trial 7 ngày; gói tháng; offer code; win-back offer; không dùng toggle | Cả 5 |
| Quyền riêng tư | Không SDK analytics hay quảng cáo; LocalAuthentication (Face ID); `PrivacyInfo.xcprivacy`; nhãn "Data Not Collected" | Cả 5 |
| Bản địa hóa | String Catalog; metadata EN-US, EN-UK, DE, FR trước; Translation framework cho nội dung offline | Cả 5 |
| LiDAR và 3D | RoomPlan, ARKit `sceneReconstruction`, Object Capture; kiểm tra `isSupported` và có chế độ dự phòng | 3, 4 |

Nguyên tắc kỹ thuật chung:
- Mức tối thiểu iOS 26 (chạy trên 79% iPhone theo Apple, 6/2026). API chỉ có trên iOS 27 bọc trong `if #available(iOS 27, *)`.
- Lõi phải chạy trên mọi iPhone bằng Vision và VisionKit. Foundation Models và LiDAR chỉ là lớp nâng cấp.
- Gói cài dưới 200 MB; model hoặc dữ liệu lớn tải qua Background Assets và phải hỏi người dùng trước (Guideline 4.2.3(ii)).
- Đo lường bằng App Store Connect Analytics và báo cáo Apple Ads. Thêm SDK như Firebase hay Crashlytics sẽ làm mất nhãn "Data Not Collected".

## 4. Kế hoạch từng app

### App 1 · Sổ chứng từ riêng tư

- **Người dùng:** người làm tự do, chủ nhà cho thuê và doanh nghiệp siêu nhỏ ở Anh (Making Tax Digital), Đức (Belege, Kleinunternehmer) và Pháp (notes de frais). Không nhắm người làm công ăn lương ở Đức, vì họ đã có MeinElster+ miễn phí.
- **Định vị:** "Chứng từ của bạn không rời iPhone." Đối thủ Đức WISO lưu trên server, còn SteuerGO gửi dữ liệu sang OpenAI ở Mỹ.
- **MVP (8 tuần):**
  1. Chụp bằng VisionKit.
  2. `RecognizeDocumentsRequest` lấy ngày, tổng tiền, VAT và người bán.
  3. Phân loại chi phí bằng Foundation Models; máy cũ dùng luật cố định.
  4. Đọc hóa đơn điện tử XRechnung/ZUGFeRD (XML).
  5. Xuất CSV và PDF theo quý.
  6. Khóa Face ID; không cần tài khoản.
- **Để sau:** chế độ hộ kinh doanh Việt Nam (tự kê khai từ 1/1/2026), nhiều doanh nghiệp, mẫu xuất cho từng phần mềm kế toán.
- **Paywall:** chụp và lưu miễn phí không giới hạn, xuất PDF đơn miễn phí. Thu tiền cho xuất cho kế toán, gói theo quý, tự phân loại, nhiều doanh nghiệp. $/£/€29.99–49.99/năm, trial 7 ngày; thêm gói mua một lần €39–59 cho khối nói tiếng Đức. VN 49.000–499.000₫.
- **ASO khởi điểm:** EN "receipt scanner for taxes", "scan to pdf", "pdf scanner app"; DE "dokumente scannen", "scanner app kostenlos"; FR "scanner pdf"; VN "quét tài liệu miễn phí".
- **Rủi ro:** head term rất khó (KD 82); cầu "receipt scanner" yếu; quy tắc lưu trữ GoBD ở Đức. Không được tuyên bố được HMRC công nhận.

### App 3 · Kiểm kê LiDAR và biên bản nhà thuê

- **Người dùng:** người thuê và chủ nhà khi nhận hoặc trả nhà, người cần hồ sơ đồ đạc cho bảo hiểm, người chuyển nhà.
- **MVP (8 tuần):**
  1. RoomPlan quét từng phòng, tính diện tích m².
  2. Chụp ảnh từng món đồ, OCR số serial hoặc hóa đơn.
  3. Xuất PDF biên bản có dấu thời gian.
  4. Xuất PDF và USDZ miễn phí.
  5. Máy không có LiDAR dùng chế độ ảnh kèm đo AR.
- **Để sau:** module tiền khảo sát cải tạo nhà và heat pump (đo cửa sổ, OCR tem radiator, xuất IFC). Không tuyên bố tuân thủ DIN EN 12831 hay MCS.
- **Paywall:** một bất động sản miễn phí. Nhiều bất động sản, gói chủ nhà cho thuê và mẫu PDF có thương hiệu: khoảng €14,99/nhà mua một lần hoặc €39,99/năm (mức giá suy luận).
- **ASO khởi điểm:** "lidar room scanner", "room scanner", "floor plan scanner", "3d scan room"; DE "lidar scanner 3d"; FR "lidar plan"; NL "meten met camera".
- **Rủi ro:** chỉ khoảng 25–35% máy đang dùng có LiDAR (ước tính); Apple Ads không nhắm được theo model máy; mảng vẽ mặt bằng ở Đức đã đông.

### App 2 · Máy quét nhãn thành phần và dị ứng

- **Người dùng:** người dị ứng, người bị coeliac, người ăn chay thuần, gia đình có trẻ dị ứng, người đi du lịch trong EU.
- **Định vị:** đọc trực tiếp danh sách thành phần bằng OCR thay vì dựa vào mã vạch như Yuka (khoảng 90% sản phẩm của Yuka do người dùng thêm vào). Chạy offline bằng mọi ngôn ngữ EU.
- **MVP (8 tuần):**
  1. OCR danh sách thành phần.
  2. Từ điển on-device gồm 14 chất gây dị ứng theo Quy định EU 1169/2011, số E và từ đồng nghĩa ở 9 ngôn ngữ.
  3. Tô sáng theo hồ sơ người dùng.
  4. Thẻ dị ứng offline dịch bằng Translation framework.
- **Để sau:** giải thích bằng Foundation Models (phải gắn nhãn AI theo AI Act Điều 50); hồ sơ gia đình.
- **Paywall:** một hồ sơ, quét không giới hạn miễn phí. Hồ sơ gia đình, thẻ du lịch, lịch sử: $/€9.99–19.99/năm.
- **ASO khởi điểm:** "food scanner", "nutrition scanner", "food scanner good or bad free"; từ khóa địa phương cần đo bằng Apple Ads sau khi ra mắt.
- **Rủi ro:** trách nhiệm sức khỏe (Guideline 1.4.1). Luôn ghi "công cụ hỗ trợ, luôn đọc lại nhãn".

### App 4 · Scan-to-Print 3D

- **Người dùng:** người chơi in 3D, maker, người cần bản sao hoặc linh kiện thay thế.
- **MVP (6 tuần):**
  1. Chụp theo hướng dẫn bằng Object Capture.
  2. Lấy tỷ lệ thật từ LiDAR.
  3. Vá mesh cho kín nước và tạo đế phẳng.
  4. Xuất STL và USDZ.
- **Để sau:** định dạng 3MF; lượt quét chất lượng cao bán theo lượt.
- **Paywall:** chụp, xem trước và một lượt xuất miễn phí. Mua Pro một lần $14.99–29.99, hoặc €4,99/lượt quét chất lượng cao.
- **ASO khởi điểm:** "3d scanner app for 3d printer", "3d scanner stl"; DE "3d scanner 3d druck"; IT "lidar scanner 3d gratis"; ES "escaner 3d gratis".
- **Rủi ro:** tên "3D scanner" chung chung dễ dính Guideline 4.3, nên định vị rõ "sẵn để in". Chỉ phục vụ máy Pro.

### App 5 · Đồng hành hái nấm, an toàn trước

- **Người dùng:** người hái nấm ở Đức, Áo, Thụy Sĩ, Pháp, Ý, Ba Lan và Bắc Âu.
- **Định vị:** app đồng hành, không phải app nhận diện. **Không bao giờ kết luận "ăn được".** App AI nhận diện nấm tốt nhất chỉ đúng 49% (44% với nấm độc, Clinical Toxicology 2023). App kiểu sách tra (Meine Pilze) thắng bài kiểm tra của Hội Nấm học Đức.
- **MVP (6 tuần, cộng phần nội dung chuẩn bị từ tháng 3):**
  1. Nhật ký điểm hái bằng GPS, chạy offline.
  2. Lịch mùa theo vùng.
  3. Checklist đặc điểm: phiến, vòng, bao gốc, bào tử.
  4. Danh mục loài dễ nhầm.
  5. Xuất hồ sơ cho chuyên gia tư vấn nấm (Pilzberater).
- **Paywall:** nhật ký và nội dung cơ bản miễn phí. Gói vùng mua một lần €7,99–14,99.
- **ASO khởi điểm:** DE "pilze bestimmen kostenlos", "pilze erkennen"; FR "reconnaissance champignons gratuit"; IT "riconoscere funghi"; ES "setas"; UK "mushroom identifier".
- **Rủi ro:** an toàn tính mạng; bản quyền dữ liệu loài theo vùng; phụ thuộc mùa vụ.

## 5. Quảng cáo có hoàn vốn năm đầu không

Công thức:
- **Chi phí có 1 người trả tiền** = CPA Apple Ads ÷ tỷ lệ tải → trả tiền.
- **Tiền thực nhận năm đầu** = giá ÷ (1 + VAT) × 85%, tức sau phí Small Business Program 15%.
- **Bỏ qua:** gia hạn, hoàn tiền và trial.
- **Nguồn:** CPA theo Adapty (12 tháng tới 7/2026); tỷ lệ chuyển đổi theo RevenueCat 2026 (freemium trung vị Tây Âu 2,0%, hard paywall 10,7%).

| App | Thị trường | Giá (USD quy đổi) | Chi phí có 1 người trả tiền: freemium 2,0% / hard 10,7% | Tiền thực nhận năm đầu | Thu về so với chi phí (freemium / hard) |
|---|---|---|---|---|---|
| 1 | Đức (CPA $1.34, VAT 19%) | $39.99/năm | $67,00 / $12,52 | $28,56 | 43% / 228% |
| 1 | Anh (CPA $2.02, VAT 20%) | $39.99/năm | $101,00 / $18,88 | $28,33 | 28% / 150% |
| 3 | Hà Lan (CPA $1.07, VAT 21%) | $39.99/năm | $53,50 / $10,00 | $28,09 | 53% / 281% |
| 2 | Pháp (CPA $1.11, VAT 20%) | $14.99/năm | $55,50 / $10,37 | $10,62 | 19% / 102% |
| 4 | Đức | $19.99 một lần | $67,00 / $12,52 | $14,28 | 21% / 114% |
| 5 | Đức | $9.99 một lần | $67,00 / $12,52 | $7,14 | 11% / 57% |

Hệ quả:
- App 1 và app 3 chỉ nên chạy Apple Ads khi có paywall ở bước xuất và tỷ lệ chuyển đổi tiến gần mức hard paywall.
- App 2, app 4 và app 5 phải tăng trưởng bằng ASO, cộng đồng (subreddit in 3D, hội hái nấm), PR theo mùa và cơ hội được Apple giới thiệu.
- Trang web đi kèm có máy tính để thử các kịch bản khác.

## 6. KPI và tiêu chí dừng hay đẩy mạnh sau 8 tuần

Ngưỡng chung lấy theo trung vị Tây Âu (RevenueCat 2026):
- Tải → trả tiền trong 35 ngày ≥ 2,0%.
- Trial → trả tiền ≥ 29,7%.
- Doanh thu mỗi lượt cài ngày 14 (RPI D14) ≥ $0,25.
- Hoàn tiền dưới 3%.

Mục tiêu riêng từng app (mục tiêu nội bộ):
- **App 3:** ít nhất 60% phiên quét hoàn tất một phòng.
- **App 4:** ít nhất 70% lượt xuất STL thành công; ít nhất 3% mua Pro.
- **App 5:** ít nhất 3% mua gói vùng; không có đánh giá nào nêu vấn đề an toàn.

| Tình huống | Dấu hiệu | Hành động |
|---|---|---|
| Đẩy mạnh | RPI D14 ≥ $0,25 và chi phí có 1 người trả tiền thấp hơn tiền thực nhận năm đầu | Tăng ngân sách Apple Ads ở storefront đạt; mở bản địa hóa đợt 2 (IT, ES, NL, SV, DA, NB) |
| Sửa | Có lượt tải tự nhiên nhưng RPI D14 từ $0,10 đến $0,25 | A/B test bản dịch paywall trước (tỷ lệ thắng 62,3% theo Adapty), rồi mới test giá và vị trí paywall; thử hard paywall ở bước xuất |
| Dừng đầu tư | RPI D14 dưới $0,10 sau hai vòng ASO | Giữ app ở chế độ bảo trì; chuyển nguồn lực sang app kế tiếp (cùng lõi Vision/OCR) |

Ngân sách thử Apple Ads cho mỗi app, tính từ CPT trung bình: khoảng 300 lượt chạm mỗi thị trường.

| Thị trường | Phép tính | Chi phí |
|---|---|---|
| Anh | 300 × $1,31 | ≈ $393 |
| Đức | 300 × $0,86 | ≈ $258 |
| Pháp | 300 × $0,75 | ≈ $225 |
| Hà Lan | 300 × $0,65 | ≈ $195 |
| **Tổng 4 thị trường** | | **≈ $1.070/app** |

## 7. Tuân thủ và nộp app (áp dụng cho cả 5 app)

- **Trước khi nộp app đầu tiên:**
  - Đăng ký Small Business Program: IAP ở EU chỉ mất 15% theo điều khoản hiệu lực 1/10/2026.
  - Khai DSA trader status bằng địa chỉ doanh nghiệp, vì thông tin hiển thị công khai.
  - Trả lời bảng câu hỏi độ tuổi mới.
  - Build bằng Xcode 26 trở lên.
- **Ở EU dùng Apple IAP.** Chưa bật thanh toán thay thế hay link-out, vì lựa chọn phải giữ 12 tháng và dev sẽ phải tự lo VAT, nút rút hợp đồng và nút hủy §312k.
- **Paywall:**
  - Các gói đặt cạnh nhau, không dùng toggle.
  - Số tiền thực và chu kỳ là chữ lớn nhất.
  - Chỉ một lối từ chối.
  - Có link quản lý hoặc hủy gói dẫn sang cài đặt Apple.
- **Guideline 4.3 (siết 8/6/2026):** mỗi app phải là một quy trình dọc có đầu ra riêng, không làm bản reskin. Ghi rõ điểm khác biệt trong Review Notes và cập nhật đều.
- **App có yếu tố sức khỏe hoặc an toàn (app 2, app 5):**
  - Không chẩn đoán, không kết luận an toàn.
  - Nhắc người dùng hỏi chuyên gia.
  - Không dùng Foundation Models cho dịch vụ y tế có quản lý.

## 8. Hai tuần đầu tiên

1. **Lấy volume thật:** tạo tài khoản Google Ads, chạy Keyword Planner cho danh sách từ khóa EN, DE, FR của app 1 và app 3.
2. **Landing page đa ngôn ngữ** (/de/, /fr/, /vi/): xác minh Google Search Console và bật BigQuery export từ ngày đầu.
3. **Thủ tục Apple:** Small Business Program, DSA trader status, bảng câu hỏi độ tuổi.
4. **Chốt định vị app 1:** tên, subtitle và từ khóa cho EN-US, EN-UK, DE, FR; privacy policy mọi ngôn ngữ; ảnh chụp màn hình đầu tiên nêu lời hứa offline, ví dụ "100% offline – keine Daten verlassen dein iPhone".
5. **Dựng lõi dùng chung** và thử OCR trên 50 hóa đơn thật (Anh, Đức, Pháp, Việt) trước khi làm giao diện.
