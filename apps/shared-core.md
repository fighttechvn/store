# Lõi dùng chung `SensorCore` (mã `CORE`)

`SensorCore` là một Swift package gồm nhiều library product, dùng chung cho `ReceiptBook` (SCT), `AllergenLens` (NDU) và `RoomLedger` (KKL). Lõi được xây cùng lúc với app 1 (10–11/2026). App 3 và app 2 dùng lại, chỉ bổ sung khi cần.

Đọc [README](README.md) trước để nắm quy ước ID, ưu tiên và ước tính.

## 1. Cấu trúc repo đề xuất

```
SensorSuite/                     # 1 Xcode workspace cho cả 3 app
├── Packages/
│   └── SensorCore/              # Swift package, Swift 6, iOS 26+
│       ├── Package.swift
│       ├── Sources/
│       │   ├── CoreCapture/     # camera, tài liệu, live scanner, nhập ảnh/PDF
│       │   ├── CoreOCR/         # nhận dạng chữ, bảng, dữ liệu phát hiện
│       │   ├── CoreExtraction/  # trích xuất có cấu trúc (Foundation Models + luật)
│       │   ├── CoreStore/       # SwiftData, kho file, bảo vệ dữ liệu, audit log
│       │   ├── CoreExport/      # PDF, CSV, ZIP, chia sẻ
│       │   ├── CorePaywall/     # StoreKit 2, quyền lợi, màn paywall
│       │   ├── CoreSecurity/    # Face ID, khóa app, băm SHA-256
│       │   ├── CoreDesign/      # design system SwiftUI, accessibility
│       │   ├── CoreLocalization/# định dạng số, tiền, ngày theo locale
│       │   ├── CoreIntents/     # App Intents, Spotlight, hỗ trợ widget
│       │   ├── CoreDevice/      # dò năng lực thiết bị (LiDAR, FM, DataScanner)
│       │   ├── CoreDiagnostics/ # OSLog, MetricKit, không gửi dữ liệu ra ngoài
│       │   └── CoreCompliance/  # disclaimer, nhãn AI, chuỗi privacy
│       └── Tests/               # Swift Testing
├── Apps/
│   ├── ReceiptBook/             # app 01 + Share Extension + Widget
│   ├── AllergenLens/            # app 02 + Widget
│   └── RoomLedger/              # app 03
├── Tools/
│   ├── ocr-bench/               # CLI macOS chạy Vision trên bộ ảnh mẫu, đo độ chính xác
│   └── lexicon-build/           # CLI dựng từ điển dị ứng cho app 02
└── ci/                          # Xcode Cloud scripts, fastlane metadata
```

Vì sao dùng một package nhiều product: mỗi app chỉ link module nó cần, test chạy nhanh theo module, và `Tools/ocr-bench` trên macOS dùng lại đúng code OCR của app (Vision và Foundation Models đều có trên macOS 26).

## 2. Nguyên tắc kiến trúc

| Nguyên tắc | Cách làm |
|---|---|
| UI | SwiftUI + Observation (`@Observable`). UIKit chỉ khi bọc view controller của hệ thống (VisionKit, RoomPlan). |
| Luồng dữ liệu | Mỗi feature có `View` + `@Observable` model + service qua protocol. Service tiêm qua `Environment` để test được. |
| Đồng thời | Swift 6 strict concurrency. Service xử lý ảnh là `actor` hoặc `Sendable` struct. Không chặn main thread. |
| Lưu trữ | SwiftData cho metadata; ảnh, PDF, USDZ lưu thành file trong Application Support với `FileProtectionType.complete`. |
| Mạng | **MVP không gọi `URLSession` nào.** CI có bước grep chặn `URLSession`, `WKWebView` tải URL ngoài, và SDK bên thứ ba gửi dữ liệu. StoreKit và Background Assets do hệ thống quản lý. |
| Năng lực thiết bị | Mọi tính năng phụ thuộc phần cứng hỏi `CoreDevice.Capabilities` trước, luôn có đường dự phòng. |
| Lỗi | Lỗi hiển thị cho người dùng phải nói rõ chuyện gì xảy ra và cách sửa; lỗi kỹ thuật ghi OSLog, không gửi đi. |

## 3. API và interface chính

Đoạn code dưới là phác thảo interface để thống nhất giữa các app, không phải code cuối cùng. Tên API Apple lấy từ ghi chú nghiên cứu; chi tiết chữ ký hàm phải đối chiếu tài liệu Xcode 26.

### 3.1 CoreDevice (CORE-E14-01)

```swift
public struct Capabilities: Sendable {
    public let hasLiDAR: Bool              // ARWorldTrackingConfiguration.supportsSceneReconstruction(.mesh)
    public let roomPlan: Bool              // RoomCaptureSession.isSupported
    public let objectCapture: Bool         // ObjectCaptureSession.isSupported
    public let liveScanner: Bool           // DataScannerViewController.isSupported && .isAvailable
    public let onDeviceLLM: LLMStatus      // SystemLanguageModel.default.availability
    public let ocrLanguages: [Locale.Language] // supportedRecognitionLanguages của request đang dùng
}
public enum LLMStatus: Sendable { case available, notEnabled, deviceNotEligible, modelNotReady, unsupportedLanguage }
```

### 3.2 CoreCapture

| Nguồn | API Apple | Ghi chú |
|---|---|---|
| Tài liệu nhiều trang | `VNDocumentCameraViewController` (VisionKit) | Tự nắn phối cảnh, trả về ảnh từng trang |
| Quét trực tiếp chữ/mã | `DataScannerViewController` | Cần kiểm tra `isSupported`, `isAvailable`; hỗ trợ vùng quan tâm |
| Ảnh có sẵn | `PhotosPicker` (PhotosUI) | Không cần quyền thư viện ảnh đầy đủ |
| File PDF/XML | `fileImporter` (SwiftUI) | Dùng cho e-invoice ở app 01 |
| Kiểm tra ống kính bẩn | `DetectLensSmudgeRequest` (iOS 26) | Độ tin cậy 0–1; nhắc "lau camera" khi vượt ngưỡng |

```swift
public protocol CaptureSource: Sendable {
    func capture() async throws -> [CapturedPage]   // ảnh đã chuẩn hóa hướng, có metadata thời điểm chụp
}
public struct CapturedPage: Sendable { public let imageURL: URL; public let capturedAt: Date; public let smudgeScore: Double? }
```

### 3.3 CoreOCR

```swift
public protocol TextRecognizer: Sendable {
    func recognize(_ page: CapturedPage, languages: [Locale.Language]) async throws -> RecognizedDocument
}
public struct RecognizedDocument: Sendable {
    public var lines: [Line]              // chữ + bounding box + độ tin cậy
    public var tables: [Table]            // từ RecognizeDocumentsRequest (iOS 26)
    public var detected: [DetectedValue]  // ngày, số tiền, số điện thoại, email, URL…
    public var languageHints: [Locale.Language]
}
```

- `DocumentRecognizer` dùng `RecognizeDocumentsRequest` (iOS 26): đọc bảng, danh sách, đoạn văn, mã QR và dữ liệu như ngày, số tiền. Apple nói hỗ trợ 26 ngôn ngữ nhưng chưa công bố danh sách, nên **phải kiểm tra lúc chạy** ⚠ cần xác minh.
- `LineRecognizer` dùng `VNRecognizeTextRequest` (`.accurate`, `usesLanguageCorrection`) làm dự phòng và cho tiếng Việt: phải đặt `recognitionLanguages` rõ ràng, mã tiếng Việt là `vi-VT` theo ghi chú nghiên cứu ⚠ cần xác minh trên máy thật.
- Chọn recognizer theo ngôn ngữ và loại tài liệu. Chạy thử cả hai trên bộ ảnh mẫu trong `ocr-bench` để quyết định.

### 3.4 CoreExtraction

```swift
public protocol FieldExtractor: Sendable {
    associatedtype Output: Sendable
    func extract(from doc: RecognizedDocument, context: ExtractionContext) async throws -> Extracted<Output>
}
public struct Extracted<T: Sendable>: Sendable {
    public var value: T
    public var fieldConfidence: [String: Double]  // 0–1 theo từng trường
    public var source: Source                      // .rules, .llm, .merged, .user
}
```

- `LLMExtractor` dùng Foundation Models: `LanguageModelSession` với instructions ngắn, `respond(to:generating:)` trả về struct `@Generable` có `@Guide`. Chỉ chạy khi `LLMStatus == .available` và ngôn ngữ nằm trong `SystemLanguageModel.supportedLanguages`. Ngữ cảnh tối đa 4.096 token mỗi phiên trên iOS 26, nên phải cắt văn bản OCR theo khối.
- `RuleExtractor` dùng regex, `NSDataDetector` và dữ liệu `detected` từ OCR. Chạy trên mọi máy.
- `MergedExtractor` chạy luật trước, dùng LLM để lấp trường thiếu hoặc phân xử khi luật mâu thuẫn. Trường nào LLM đưa ra mà luật không kiểm chứng được thì hạ độ tin cậy và đánh dấu "cần xem lại".
- Quy định sử dụng Foundation Models của Apple cấm dùng cho dịch vụ y tế, pháp lý, tài chính có quản lý. Chỉ dùng cho trích xuất và phân loại, không đưa ra tư vấn.

### 3.5 CoreStore

- SwiftData `ModelContainer` riêng cho từng app, schema có version (`VersionedSchema`, `SchemaMigrationPlan`).
- `BlobStore` lưu file theo UUID trong Application Support; ghi với `FileProtectionType.complete`; ảnh gốc giữ nguyên, bản xem trước tạo riêng.
- `AuditLog`: mọi sửa đổi trường quan trọng ghi (thời điểm, trường, giá trị cũ, giá trị mới, nguồn). App 01 cần cho yêu cầu lưu trữ chứng từ; app 03 cần cho biên bản.
- Sao lưu: dữ liệu nằm trong backup iCloud/Finder của thiết bị. Đồng bộ CloudKit là `V1.1`, phải kiểm tra lại nhãn quyền riêng tư trước khi bật ⚠ cần xác minh.

### 3.6 CoreExport

| Định dạng | Cách làm |
|---|---|
| PDF | `UIGraphicsPDFRenderer` với template SwiftUI → ảnh vector; PDFKit để ghép PDF nhập vào |
| CSV | Writer riêng: UTF-8 có BOM (để Excel mở đúng), dấu phân cách theo locale (`;` cho DE/FR, `,` cho UK/US), số thập phân theo locale |
| ZIP | `NSFileCoordinator` với tùy chọn `.forUploading` để nén thư mục thành zip |
| Chia sẻ | `ShareLink`, `fileExporter` |
| Dấu vân tay | SHA-256 (CryptoKit) cho từng file và cho cả gói, in vào trang cuối PDF |

### 3.7 CorePaywall

- StoreKit 2: `Product.products(for:)`, `purchase()`, lắng nghe `Transaction.updates`, tính quyền lợi từ `Transaction.currentEntitlements`.
- `Entitlements` là `@Observable`, app hỏi `entitlements.has(.export)`… thay vì hỏi sản phẩm cụ thể.
- Màn paywall tự dựng theo luật đã chốt trong kế hoạch:
  - các gói đặt cạnh nhau, không dùng toggle;
  - số tiền thực và chu kỳ là chữ lớn nhất;
  - hiện mốc "Ngày 7: bị tính tiền";
  - nút đóng hiện rõ;
  - chỉ một lối từ chối.
- Có offer code (`presentOfferCodeRedeemSheet`), win-back offer, link "Quản lý gói" (`AppStore.showManageSubscriptions`), khôi phục mua (`AppStore.sync()`).
- StoreKit Configuration file cho test local; test tự động bằng `StoreKitTest` (`SKTestSession`).

### 3.8 CoreSecurity

- Khóa app bằng `LAContext.evaluatePolicy(.deviceOwnerAuthentication)` khi mở và khi quay lại sau N phút; che nội dung trong app switcher.
- Không lưu bí mật trong app. Không có tài khoản người dùng trong MVP, nên không cần luồng xóa tài khoản.

### 3.9 CoreLocalization

- String Catalog (`.xcstrings`), đợt 1: `en`, `en-GB`, `de`, `fr`; `vi` cho app 01.
- `LocaleFormatters`: tiền tệ, ngày, số thập phân theo storefront, không theo ngôn ngữ UI. Ví dụ người Đức dùng UI tiếng Anh vẫn cần `1.234,56 €`.
- Metadata App Store quản lý bằng fastlane `deliver` trong `ci/metadata/<locale>/`, có từ khóa riêng cho từng locale.

### 3.10 CoreIntents

- App Intents: mỗi app khai báo `AppShortcutsProvider` với 2–3 lệnh chính.
- `IndexedEntity` để đưa nội dung vào Spotlight (chỉ index trên máy).
- Tích hợp Visual Intelligence và nút Camera Control qua App Intents là `V1.1` ⚠ cần xác minh API trên iOS 26.

### 3.11 CoreDiagnostics

- `Logger` (OSLog) theo subsystem/category; không log nội dung chứng từ hay thành phần.
- MetricKit nhận báo cáo hiệu năng và crash trên máy; không gửi đi. Crash thực tế xem trong Xcode Organizer. Cần kiểm tra ảnh hưởng tới nhãn quyền riêng tư ⚠ cần xác minh.
- Đo lường sản phẩm dùng App Store Connect Analytics và báo cáo Apple Ads; không có sự kiện tự thu.

### 3.12 CoreCompliance

- `Disclaimer` component dùng chung: văn bản theo ngữ cảnh (thuế, sức khỏe, đo đạc), bản địa hóa, hiện lần đầu và trong Cài đặt.
- `AIGeneratedLabel`: nhãn "Do AI tạo / AI-generated / KI-generiert / Généré par IA" cho mọi văn bản do Foundation Models sinh ra (AI Act Điều 50, áp dụng từ 2/8/2026).
- `PrivacyInfo.xcprivacy` mẫu với lý do API bắt buộc (UserDefaults, file timestamp, disk space).
- Mẫu Review Notes cho App Review: điểm khác biệt, cách test IAP, máy nào có tính năng nào.

## 4. Ma trận năng lực thiết bị

| Năng lực | Điều kiện | Dùng ở | Khi không có |
|---|---|---|---|
| OCR tài liệu (Vision) | Mọi máy iOS 26 | SCT, NDU, KKL | Không áp dụng; đây là lõi |
| Live scanner | `DataScannerViewController.isSupported` | NDU, SCT | Chụp ảnh tĩnh rồi OCR |
| Foundation Models | iPhone 15 Pro trở lên, Apple Intelligence bật, ngôn ngữ được hỗ trợ | SCT, NDU, KKL | Luật cố định; ẩn phần giải thích AI |
| LiDAR / RoomPlan | iPhone 12 Pro – 18 Pro | KKL | Chế độ ảnh + đo AR + nhập kích thước tay |
| Ước tính tỷ lệ máy | Apple Intelligence khoảng 35–50%, LiDAR khoảng 25–35% (ước tính của báo cáo) | | Lõi không được phụ thuộc hai năng lực này |

## 5. Hiệu năng và kích thước

| Chỉ số | Ngân sách | Đo bằng |
|---|---|---|
| OCR 1 trang A4 | ≤ 1,5 giây trên iPhone 12 | `ocr-bench` + XCTest `measure` |
| Trích xuất bằng LLM | ≤ 3 giây trên iPhone 15 Pro, có trạng thái chờ | Signpost (`OSSignposter`) |
| Mở app lạnh | ≤ 1 giây tới màn hình đầu | MetricKit launch metrics |
| Gói cài | < 200 MB (không bị cảnh báo tải qua mạng di động) | App Store Connect |
| Bộ nhớ khi xử lý ảnh | Xử lý từng trang, giải phóng ảnh gốc sau khi tạo bản xem trước | Instruments |

Các ngân sách trên là mục tiêu thiết kế, cần hiệu chỉnh sau spike đầu tiên.

## 6. Kiểm thử và CI

- **Unit test:** Swift Testing cho từng module; mock `TextRecognizer`, `FieldExtractor`.
- **Bộ dữ liệu vàng:** ảnh thật đã xóa thông tin cá nhân, có nhãn trường. `ocr-bench` xuất precision/recall theo trường và theo ngôn ngữ; CI chạy mỗi PR vào `main` và fail nếu tụt quá 2 điểm phần trăm.
- **UI test:** XCUITest cho luồng chính; StoreKit test session cho paywall.
- **Thiết bị test tối thiểu:** một máy không có Apple Intelligence (ví dụ iPhone 12/13), một máy có (15 Pro trở lên), một máy Pro có LiDAR, một máy không LiDAR đời mới (ví dụ iPhone 17 hoặc Air).
- **CI:** Xcode Cloud. Workflow PR (build + test), workflow `main` (bench OCR), workflow release (archive, TestFlight, fastlane metadata).
- **Kiểm tra quyền riêng tư:** grep `URLSession`, danh sách SDK trong `Package.resolved`, xác nhận `PrivacyInfo.xcprivacy` trước mỗi release.

## 7. Epic và feature của lõi

| ID | Epic | Module | Feature | Ưu tiên | Ngày | Tiêu chí nghiệm thu |
|---|---|---|---|---|---|---|
| CORE-E01-01 | Nền tảng | (repo) | Workspace, package `SensorCore`, 3 app target rỗng, Swift 6 strict concurrency | MVP | 1 | Khi build cả 3 target thì không có cảnh báo concurrency |
| CORE-E01-02 | Nền tảng | (ci) | Xcode Cloud: PR build + test; bước grep chặn `URLSession` | MVP | 1 | Khi PR thêm `URLSession` thì CI fail |
| CORE-E01-03 | Nền tảng | (ci) | fastlane `deliver` cho metadata đa locale | MVP | 1 | Khi chạy lane thì metadata 4 locale được đẩy lên App Store Connect |
| CORE-E02-01 | Chụp | CoreCapture | Bọc `VNDocumentCameraViewController` → `[CapturedPage]` | MVP | 1 | Khi quét 3 trang thì nhận 3 `CapturedPage` đúng thứ tự |
| CORE-E02-02 | Chụp | CoreCapture | Bọc `DataScannerViewController` với vùng quan tâm (xây cùng app 02, 3/2027; app 01 không dùng) | MVP | 2 | Khi máy không hỗ trợ thì trả lỗi `.unsupported` và UI chuyển sang chụp tĩnh |
| CORE-E02-03 | Chụp | CoreCapture | Nhập ảnh (`PhotosPicker`) và file (`fileImporter`) | MVP | 1 | Khi chọn HEIC/JPEG/PDF thì chuyển thành `CapturedPage` |
| CORE-E02-04 | Chụp | CoreCapture | Kiểm tra ống kính bẩn (`DetectLensSmudgeRequest`) | V1.1 | 1 | Khi điểm > ngưỡng thì hiện nhắc lau camera |
| CORE-E03-01 | OCR | CoreOCR | `DocumentRecognizer` dùng `RecognizeDocumentsRequest` | MVP | 3 | Khi OCR hóa đơn mẫu thì trả về dòng, bảng và giá trị ngày/tiền |
| CORE-E03-02 | OCR | CoreOCR | `LineRecognizer` dùng `VNRecognizeTextRequest`, chọn ngôn ngữ rõ ràng (gồm `vi-VT`) | MVP | 1,5 | Khi OCR hóa đơn tiếng Việt thì giữ đúng dấu ở ≥ 95% ký tự của bộ mẫu |
| CORE-E03-03 | OCR | CoreOCR | Bộ chọn recognizer theo ngôn ngữ + danh sách ngôn ngữ hỗ trợ lúc chạy | MVP | 1 | Khi ngôn ngữ không hỗ trợ thì báo rõ và dùng dự phòng |
| CORE-E03-04 | OCR | CoreOCR | Tùy chọn cho `LineRecognizer`: vùng quan tâm, bật/tắt `usesLanguageCorrection`, `customWords`, trả top-N ứng viên mỗi dòng (cần cho app 02 và 03) | MVP | 1 | Khi bật top-N thì mỗi dòng trả tối đa N ứng viên kèm độ tin cậy; khi đặt vùng quan tâm thì chữ ngoài vùng bị bỏ |
| CORE-E04-01 | Trích xuất | CoreExtraction | `RuleExtractor` khung chung (regex, `NSDataDetector`) | MVP | 2 | Có test cho ngày, tiền, mã số thuế mẫu |
| CORE-E04-02 | Trích xuất | CoreExtraction | `LLMExtractor` khung chung (Foundation Models, `@Generable`, cắt khối theo token) | MVP | 3 | Khi FM không khả dụng thì không crash và trả `.unavailable` |
| CORE-E04-03 | Trích xuất | CoreExtraction | `MergedExtractor` + độ tin cậy theo trường | MVP | 2 | Khi luật và LLM mâu thuẫn thì trường bị đánh dấu "cần xem lại" |
| CORE-E05-01 | Lưu trữ | CoreStore | `ModelContainer` có version + kế hoạch migration | MVP | 1 | Khi nâng schema thì dữ liệu cũ vẫn mở được |
| CORE-E05-02 | Lưu trữ | CoreStore | `BlobStore` với file protection `.complete` | MVP | 1 | Khi khóa máy thì file không đọc được từ tiến trình nền |
| CORE-E05-03 | Lưu trữ | CoreStore | `AuditLog` | MVP | 1 | Khi sửa trường quan trọng thì có bản ghi cũ/mới/nguồn |
| CORE-E06-01 | Xuất | CoreExport | Renderer PDF từ template SwiftUI | MVP | 2 | PDF A4 và Letter đúng lề, chữ chọn được |
| CORE-E06-02 | Xuất | CoreExport | CSV writer theo locale (BOM, dấu phân cách, thập phân) | MVP | 1 | Khi mở bằng Excel DE/FR thì cột và số đúng |
| CORE-E06-03 | Xuất | CoreExport | Gói ZIP + SHA-256 cho từng file | MVP | 1 | Hash in trong PDF khớp hash tính lại |
| CORE-E07-01 | Paywall | CorePaywall | Store service StoreKit 2 + `Entitlements` | MVP | 2 | Khi mua/khôi phục thì quyền lợi cập nhật ngay, kể cả khi app khởi động lại |
| CORE-E07-02 | Paywall | CorePaywall | Màn paywall tuân thủ (không toggle, giá thực nổi nhất, mốc trial) | MVP | 2 | Checklist paywall trong kế hoạch đạt 100% |
| CORE-E07-03 | Paywall | CorePaywall | Offer code, win-back offer | V1.1 | 1 | Khi nhập offer code thì quyền lợi kích hoạt |
| CORE-E07-04 | Paywall | CorePaywall | Link "Quản lý gói" (`AppStore.showManageSubscriptions`) trên paywall và trong Cài đặt | MVP | 0,5 | Khi bấm "Quản lý gói" thì trang quản lý thuê bao của Apple mở ra |
| CORE-E08-01 | Bảo mật | CoreSecurity | Khóa Face ID + che nội dung trong app switcher | MVP | 1 | Khi bật khóa và quay lại sau 5 phút thì phải xác thực |
| CORE-E09-01 | Thiết kế | CoreDesign | Token màu, chữ, khoảng cách; component nút, thẻ, danh sách; Dynamic Type | MVP | 3 | Mọi màn chính dùng được ở cỡ chữ lớn nhất accessibility |
| CORE-E09-02 | Thiết kế | CoreDesign | Nhãn VoiceOver, thông báo trạng thái xử lý | MVP | 1 | Luồng chính dùng được chỉ bằng VoiceOver |
| CORE-E10-01 | Bản địa hóa | CoreLocalization | String Catalog + `LocaleFormatters` theo storefront | MVP | 1 | Khi đổi region thì tiền/ngày/số đổi đúng |
| CORE-E11-01 | Intents | CoreIntents | Khung App Shortcuts + `IndexedEntity` | V1.1 | 2 | Khi tìm trong Spotlight thì thấy mục của app |
| CORE-E12-01 | Chẩn đoán | CoreDiagnostics | Logger, signpost, MetricKit (không gửi đi) | MVP | 1 | Không có log chứa nội dung người dùng |
| CORE-E12-02 | Chẩn đoán | (tools) | `ocr-bench` CLI + bộ dữ liệu vàng + báo cáo precision/recall | MVP | 3 | CI in bảng precision/recall theo trường và ngôn ngữ |
| CORE-E13-01 | Tuân thủ | CoreCompliance | `Disclaimer`, `AIGeneratedLabel`, `PrivacyInfo.xcprivacy`, mẫu Review Notes | MVP | 1,5 | Mọi văn bản do FM sinh ra có nhãn AI |
| CORE-E14-01 | Năng lực thiết bị | CoreDevice | `Capabilities`: LiDAR, RoomPlan, Object Capture, live scanner, Foundation Models, ngôn ngữ OCR | MVP | 1 | Khi chạy trên Simulator hoặc máy không LiDAR thì các cờ phần cứng trả `false` và app không crash |

**Tổng lõi:** khoảng 48,5 ngày công, trong đó MVP khoảng 44,5 ngày. Phần lớn làm song song với app 01 trong 10–11/2026; nếu chỉ có 1 dev thì đây là rủi ro lịch lớn nhất (xem mục 8).

Bản CSV: [shared-core-backlog.csv](shared-core-backlog.csv).

## 8. Rủi ro và spike của lõi

| Rủi ro | Ảnh hưởng | Cách xử lý |
|---|---|---|
| 1 dev không kịp lõi + app 01 trước đầu 12/2026 | Lỡ mùa thuế tháng 1–2 | Cắt `V1.1` khỏi lõi; thuê thêm 1 dev 6–8 tuần; hoặc ra mắt UK trước, DE/FR sau 2–3 tuần |
| `RecognizeDocumentsRequest` không hỗ trợ một ngôn ngữ cần thiết (tiếng Việt chưa được xác nhận) | OCR kém ở thị trường đó | 🧪 spike 2 ngày: chạy cả hai recognizer trên bộ mẫu EN/DE/FR/VI |
| Foundation Models trả sai trường hoặc chậm | Người dùng mất niềm tin | Luật chạy trước; LLM chỉ lấp chỗ trống; luôn có màn xem lại |
| Chữ ký API iOS 26/27 khác ghi chú | Trễ lịch | Mọi mục ⚠ phải xác minh trong tuần 1 |
| Nhãn "Data Not Collected" bị ảnh hưởng bởi CloudKit/MetricKit | Mất lợi thế định vị | Giữ MVP không sync; hỏi kỹ hướng dẫn App Privacy trước `V1.1` |

## 9. Điều chỉnh sau khi thiết kế chi tiết 3 app

Thiết kế chi tiết của 3 app chỉ ra 4 chỗ lõi còn thiếu. Đã xử lý như sau:

| Vấn đề | App phát hiện | Cách xử lý |
|---|---|---|
| `CoreDevice` chưa có ID trong backlog | KKL | Thêm CORE-E14-01 (MVP, 1 ngày) |
| Checklist paywall cần link "Quản lý gói" ngay bản đầu, nhưng CORE-E07-03 là V1.1 | SCT | Tách thành CORE-E07-04 (MVP, 0,5 ngày); CORE-E07-03 còn offer code và win-back |
| `LineRecognizer` cần vùng quan tâm, tắt sửa chính tả, `customWords`, top-N ứng viên | NDU, KKL | Thêm CORE-E03-04 (MVP, 1 ngày) |
| App 01 không dùng live scanner | SCT | CORE-E02-02 vẫn là MVP của lõi nhưng xây cùng app 02 (3/2027) |

Còn để ở app, chưa đưa vào lõi: camera chụp ảnh thường (AVFoundation) do KKL-E03-01 xây. Có thể chuyển vào `CoreCapture` khi app thứ hai cần.
