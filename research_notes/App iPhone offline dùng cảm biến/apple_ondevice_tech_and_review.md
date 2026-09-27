# Apple on-device hardware, frameworks and App Store review rules for offline-first iPhone apps (status: late September 2026)

Research date: 2026-09-27. Status labels: **SHIPPED** means it is in a public release (iOS 26.x, or iOS 27, which shipped on Sep 14, 2026). **NEW IN iOS 27** means it shipped on Sep 14, 2026, so few users have it yet. **UNVERIFIED** means it comes from one secondary source only. Apple's developer documentation pages (developer.apple.com/documentation/...) are rendered by JavaScript and could not be fetched in this session. Facts marked "[Apple doc, not re-fetched]" are well-established API behavior. The URL points to the page to check before publishing.

---

## 1. Hardware: which sensors and chips iPhones have (A17 Pro → A20 Pro, iPhone 17 lineup, iPhone Air, iPhone 18 Pro)

### Takeaway
Every iPhone since the iPhone 15 Pro has at least a 16-core Neural Engine and 8 GB of RAM, which is enough for Apple Intelligence and the Foundation Models framework. LiDAR is **still only on Pro models** (iPhone 12 Pro → iPhone 18 Pro). The iPhone Air, iPhone 17, iPhone 17e and the new foldable do not have it. The newest models add GPU "Neural Accelerators" (A19 family) and a "Dual 16-core Neural Engine" (A20 Pro, iPhone 18 Pro only). The A19 Pro devices (iPhone 17 Pro/Pro Max, iPhone Air) have 12 GB of RAM, which is now a hardware threshold for some iOS 27 AI features.

### Cited Findings
**Current lineup (September 2026)**
- iPhone 18 Pro and iPhone 18 Pro Max were announced on Sep 9, 2026, with pre-orders from Sep 12 and availability from Sep 18 in 65+ countries and regions (20 more on Sep 25). Prices start at $1,199 and $1,299. They ship with iOS 27, a free update released Sep 14, 2026. — [Apple Newsroom: Apple debuts iPhone 18 Pro and iPhone 18 Pro Max](https://www.apple.com/newsroom/2026/09/apple-debuts-iphone-18-pro-and-iphone-18-pro-max/)
- A20 Pro: 2 nm process, "6‑core CPU with 2 super cores and 4 efficiency cores", "7‑core GPU with Neural Accelerators", "Dual 16‑core Neural Engine" ("32 total cores for double the AI processing power of A19 Pro"), 50% more memory bandwidth than A19 Pro, GPU up to 40% faster. — [Apple iPhone 18 Pro specs](https://www.apple.com/iphone-18-pro/specs/); [Apple Newsroom](https://www.apple.com/newsroom/2026/09/apple-debuts-iphone-18-pro-and-iphone-18-pro-max/)
- iPhone 18 Pro sensors: "Face ID, LiDAR Scanner, Barometer, High dynamic range gyro, High-g accelerometer, Proximity sensor, Dual ambient light sensors". It also has Camera Control, the "Apple second-generation Ultra Wideband chip", NFC with reader mode and the Apple N1 wireless chip (Wi‑Fi 7, Bluetooth 6, Thread). Cameras: 48MP main with **variable aperture ƒ/1.48–ƒ/4.0**, 48MP ultra wide (120°), 48MP 4x telephoto (100 mm), and an 18MP Center Stage front camera. — [Apple iPhone 18 Pro specs](https://www.apple.com/iphone-18-pro/specs/)
- iPhone 18 Pro also adds a "Reference Mode", described as "signed sensor data" through Private Cloud Compute for authenticity, and AI detection of generated photos. — [Apple Newsroom](https://www.apple.com/newsroom/2026/09/apple-debuts-iphone-18-pro-and-iphone-18-pro-max/); [Fox Business](https://www.foxbusiness.com/technology/apple-unveils-first-foldable-iphone-iphone-18-pro-lineup-new-watches-annual-launch-event)
- A first foldable iPhone was announced at the same Sep 9 event. Fox Business calls it **"iPhone Duo"**, starting at $1,999, with Touch ID in the side button, dual 48MP main and ultra-wide cameras, and Apple Pencil support. Pre-event reports called it "iPhone Ultra" or "iPhone Fold". LiDAR is not mentioned. — [Fox Business](https://www.foxbusiness.com/technology/apple-unveils-first-foldable-iphone-iphone-18-pro-lineup-new-watches-annual-launch-event); name conflict with [9to5Mac pre-event invitation article ("foldable iPhone Ultra")](https://9to5mac.com/2026/08/26/apple-officially-announces-iphone-18-pro-foldable-event/). **The name and specs are not confirmed from an Apple primary source.**
- There is no base iPhone 18 this fall. Reports say the base iPhone 18, iPhone Air 2 and iPhone 18e are planned for spring 2027 (**rumor**). — [Yahoo Tech summary](https://tech.yahoo.com/phones/breaking-news/article/what-to-know-about-the-iphone-18-lineup-before-the-september-apple-event-today-iphone-18-pro-iphone-duo-prices-and-more-175120221.html)

**iPhone 17 generation (September 2025)**
- A19 and A19 Pro both have a 6-core CPU (2P+4E) and a 16-core Neural Engine. GPU: A19 has 4 cores in the iPhone 17e and 5 cores in the iPhone 17. A19 Pro has 5 cores in the iPhone Air and 6 cores in the iPhone 17 Pro/Pro Max. **RAM: A19 = 8 GB, A19 Pro = 12 GB.** The GPU cores contain "Neural Accelerators" (tensor units for matrix math). — [Wikipedia: Apple A19](https://en.wikipedia.org/wiki/Apple_A19)
- iPhone 17 Pro spec sheet: "6‑core GPU with Neural Accelerators", "16‑core Neural Engine", 48MP main + 48MP ultra wide + 48MP 4x telephoto (8x optical-quality), 18MP Center Stage front camera, **LiDAR Scanner**, Face ID/TrueDepth, barometer, high-g accelerometer, gyroscope, proximity and dual ambient light sensors, second-generation UWB, **NFC with reader mode**, Thread, Wi‑Fi 7, Bluetooth 6, ProRes RAW, Apple Log 2, genlock. — [Apple Support: iPhone 17 Pro Tech Specs](https://support.apple.com/en-us/125090)
- The iPhone Air (A19 Pro, 5-core GPU) **has no LiDAR**. LiDAR "ships on Pro devices only, and only from the iPhone 12 Pro onward". The iPhone 17, 17e, Air and all SE models have no LiDAR. — [RoomKit guide: Which iPhones have LiDAR (2026)](https://caseadri.com/roomkit/guides/which-iphones-have-lidar/); [iDownloadBlog: iPhone Air drawbacks](https://www.idownloadblog.com/2025/09/10/iphone-air-drawbacks/)

**Neural Engine TOPS by chip**
- A17 Pro: 16-core Neural Engine, **35 TOPS**. A18/A18 Pro and A19/A19 Pro are also listed at **35 TOPS**. Apple's messaging for the A19 generation attributes AI speed-ups to memory bandwidth and the GPU Neural Accelerators, not to a higher NE TOPS figure. — [Wikipedia: Apple A17 Pro](https://en.wikipedia.org/wiki/Apple_A17_Pro); [Wikipedia: Apple A18](https://en.wikipedia.org/wiki/Apple_A18); [Wikipedia: Apple A19](https://en.wikipedia.org/wiki/Apple_A19)
- A search snippet (MacRumors/Wikipedia-derived) says the A19 Pro's GPU Neural Accelerators offer "4x the peak compute of the A18 Pro". **UNVERIFIED against Apple's press release.** — [MacRumors iPhone 17 Pro roundup](https://www.macrumors.com/roundup/iphone-17-pro/)

### Inferences
- **Hardware capability map (for the report)**:

| Sensor / hardware | Framework / API | What works offline | Models |
|---|---|---|---|
| Rear cameras (48MP), variable aperture (18 Pro) | AVFoundation, Vision, VisionKit | Capture, OCR, barcode, document/table recognition, classification | All iOS 26/27-capable iPhones (iPhone 11+) |
| LiDAR Scanner | ARKit (sceneReconstruction, sceneDepth), RoomPlan, Object Capture | Room/object 3D scanning, mesh, accurate distance measurement | iPhone 12 Pro → 18 Pro (Pro only) |
| TrueDepth (front) | ARKit face tracking, AVFoundation depth | Face mesh, front depth, portrait effects | All Face ID models (not the foldable, which uses Touch ID per Fox Business) |
| Neural Engine 16-core / "Dual 16-core" + GPU Neural Accelerators | Core ML, Foundation Models, Core AI (iOS 27) | On-device ML inference, 3B LLM | Foundation Models: iPhone 15 Pro and later |
| UWB (U1 / 2nd gen) | Nearby Interaction | Distance and direction between devices/accessories | iPhone 11+ (most models; see Gaps) |
| Barometer | Core Motion (CMAltimeter) | Relative altitude, pressure | Present on Pro models (spec sheets); widely available |
| Accelerometer / gyro / magnetometer | Core Motion, Core Location heading | Motion, step counting, orientation, compass | All |
| Microphone | Speech (SpeechAnalyzer), Sound Analysis | Speech-to-text, sound classification | All |
| Camera Control button | AVCaptureControl, LockedCameraCapture | Custom camera controls, lock-screen launch | iPhone 16/16 Plus/16 Pro, 17/17 Pro/Air, 18 Pro (not 16e) |
| NFC reader mode | Core NFC | Read/write NDEF tags, ISO7816/ISO15693 tags | iPhone 7+ |

  Camera Control, Core NFC and the UWB rows come from the Apple doc pages listed in Section 2, not re-fetched this session.
- The A20 Pro's "double the AI processing power of A19 Pro" suggests roughly 70 TOPS if Apple's 35 TOPS baseline holds. This is an **inference**; Apple did not publish a TOPS number in the materials read.

### Gaps
- iPhone Duo/Ultra (foldable): exact chip, RAM, sensors, LiDAR and ship date could not be confirmed from Apple's newsroom.
- Exact sensor lists for iPhone 17e and iPhone Air (barometer, UWB, Camera Control) were not checked against Apple's spec pages. Reports say the iPhone 16e has no Camera Control or UWB, but this was not verified.
- Apple does not publish the RAM of the iPhone 18 Pro on its spec page.

---

## 2. Frameworks: what each one enables offline, and minimum iOS / device

### Takeaway
The iOS 26/27 SDK is enough to build a fully offline camera, scanner, identifier, 3D or AI app. Vision and VisionKit cover OCR, documents, tables, barcodes and classification. Core ML (and the new Core AI in iOS 27) runs custom models. Foundation Models gives a free on-device ~3B LLM with structured output and tool calling. In iOS 27 that LLM also accepts images, and there are built-in OCR and barcode tools. ARKit, RoomPlan and Object Capture (LiDAR only) handle 3D. Translation, Speech and Natural Language cover language work. App Intents plugs the app into Siri, Spotlight and Visual Intelligence.

### Cited Findings
**Vision / VisionKit (iOS 26: SHIPPED)**
- `RecognizeDocumentsRequest` (new in iOS 26, Swift Vision API) recognizes text "in 26 languages". It detects tables (cells in rows and columns), lists and paragraphs, reads barcodes and QR codes, and finds data such as emails, phone numbers, URLs, dates, times, measurements, currency amounts, tracking numbers, payment identifiers and flight numbers. It runs on iOS, macOS, iPadOS, tvOS and visionOS. — [WWDC25 session 272 "Read documents using the Vision framework"](https://developer.apple.com/videos/play/wwdc2025/272/)
- iOS 26 also added `DetectLensSmudgeRequest`, which returns a 0–1 confidence that the photo was taken through a smudged lens. It is useful for scanner apps to prompt "clean your lens". The hand-pose model was replaced by a smaller, more accurate one with 21 joints, so existing hand-pose classifiers should be retrained. — [WWDC25 session 272](https://developer.apple.com/videos/play/wwdc2025/272/)
- `VNRecognizeTextRequest` / `RecognizeTextRequest`: `supportedRecognitionLanguages` for revision 3 (accurate) returns … "zh-Hans, zh-Hant, yue-Hans, yue-Hant, ko-KR, ja-JP, ru-RU, uk-UA, th-TH, **vi-VT**, ar-SA, ars-SA". This was observed on macOS 15.7.5. Note that Apple uses the non-standard code "vi-VT", not "vi-VN". — [GitHub issue quoting runtime output](https://github.com/ShawnPana/phone-harness/issues/91); API reference: [supportedRecognitionLanguages](https://developer.apple.com/documentation/vision/vnrecognizetextrequest/supportedrecognitionlanguages())
- VisionKit: `DataScannerViewController` (iOS 16+; live camera text and barcode scanning, `isSupported` requires A12 Bionic or later), `VNDocumentCameraViewController` (iOS 13+; edge detection and perspective correction), and `ImageAnalysisInteraction` (iOS 16+; Live Text on any image, with subject lifting). — [Apple doc, not re-fetched: DataScannerViewController](https://developer.apple.com/documentation/visionkit/datascannerviewcontroller); [VNDocumentCameraViewController](https://developer.apple.com/documentation/visionkit/vndocumentcameraviewcontroller); [ImageAnalysisInteraction](https://developer.apple.com/documentation/visionkit/imageanalysisinteraction)

**Foundation Models framework (on-device LLM)**
- iOS 26 (SHIPPED): an "approximately 3-billion-parameter model", 2 bits per weight via quantization-aware training (embeddings 4-bit, KV cache 8-bit). It is designed to "support 15 languages". It "excels at … summarization, entity extraction, text understanding, refinement, short dialog, generating creative content" but "is not designed to be a chatbot for general world knowledge". Features: guided generation via `@Generable` (constrained decoding), tool calling handled automatically, and rank-32 LoRA adapters trained with a Python toolkit. — [Apple ML Research: Apple Foundation Models 2025 updates](https://machinelearning.apple.com/research/apple-foundation-models-2025-updates)
- Context window: **4,096 tokens per session** in iOS 26 (instructions, prompts, tool I/O and output combined). Exceeding it throws `GenerationError.exceededContextWindowSize`. iOS 26.4 added a `contextSize` property and `tokenCount(for:)`. — [TN3193 (Apple)](https://developer.apple.com/documentation/technotes/tn3193-managing-the-on-device-foundation-model-s-context-window) (title only fetched; figure corroborated by [Apple Developer Forums](https://developer.apple.com/forums/thread/806542) and [InfoQ, March 2026](https://infoq.com/news/2026/03/apple-foundation-models-context)); the WWDC26 example prints `contextSize` = **8192**, likely for the new iOS 27 model — [WWDC26 session 241](https://developer.apple.com/videos/play/wwdc2026/241/)
- iOS 27 (**NEW IN iOS 27**; shipped Sep 14, 2026):
  - A rebuilt on-device model ("more intelligent… better at logic and tool calling").
  - **Image input** through `Attachment(UIImage/CGImage/CVPixelBuffer/URL…)` at any size or aspect ratio.
  - New system tools **`BarcodeReaderTool`** and **`OCRTool`**, plus a Spotlight-powered search tool for local RAG.
  - Dynamic Profiles for agent-style workflows, and an Evaluations framework.
  - A `LanguageModel` protocol, so the same session code can use `SystemLanguageModel`, `PrivateCloudComputeLanguageModel`, open-source `CoreAILanguageModel`/`MLXLanguageModel`, or Anthropic/Google Swift packages.
  - The framework itself is being open-sourced.

  — [WWDC26 session 241 "What's new in the Foundation Models framework"](https://developer.apple.com/videos/play/wwdc2026/241/)
- Private Cloud Compute via Foundation Models (iOS 27): a larger model with a 32K context and reasoning levels `.light`/`.deep`. It is **free for developers with fewer than 2 million first-time App Store downloads**, with daily per-user limits and higher limits for iCloud+ subscribers. No API key or account is needed. **It requires a network connection, so it is not offline.** — [WWDC26 session 241](https://developer.apple.com/videos/play/wwdc2026/241/); [MacRumors, June 9, 2026](https://www.macrumors.com/2026/06/09/apple-outlines-major-ai-and-developer-tool-updates/)
- **Core AI** (new at WWDC26) is a framework for running custom on-device models, with ahead-of-time compilation, dedicated Instruments and Python tools to convert PyTorch models. It "powers Siri under the hood". — [MacRumors, June 9, 2026](https://www.macrumors.com/2026/06/09/apple-outlines-major-ai-and-developer-tool-updates/)
- **Acceptable-use rules for Foundation Models**: the framework may not be used for regulated healthcare, legal or financial services, classifying individuals from biometric data, employment or criminal-justice assessments, sexual content, self-harm and similar uses. Developers must keep "reasonable guardrails". — [Acceptable use requirements for the Foundation Models framework](https://developer.apple.com/apple-intelligence/acceptable-use-requirements-for-the-foundation-models-framework/)

**Visual Intelligence integration (App Intents)**
- Apps implement `IntentValueQuery`, receive a `SemanticContentDescriptor` (with a `pixelBuffer` of the camera or screenshot capture), and return `AppEntity` results. `OpenIntent` deep-links into the app, and the `semanticContentSearch` schema continues the search inside the app. On iPhone, the entry points are the camera (Camera Control) and screenshots. WWDC26 added Visual Intelligence on iPad and Mac, plus actions such as adding contacts, saving multiple calendar events and medical-device logging. — [WWDC26 session 297 "Best practices for integrating visual intelligence in your app"](https://developer.apple.com/videos/play/wwdc2026/297/)
- iOS 27 App Intents: apps can add content to Spotlight's **semantic index**, and a new **View Annotations API** lets Siri act on on-screen content. — [MacRumors, June 9, 2026](https://www.macrumors.com/2026/06/09/apple-outlines-major-ai-and-developer-tool-updates/)

**3D / AR (LiDAR-dependent)**
- RoomPlan requires a LiDAR sensor (iPhone 12 Pro and later, or iPad Pro) and iOS 16+. — [DEV Community: Wrapping Apple's LiDAR Room Scanner](https://dev.to/toddsullivan/wrapping-apples-lidar-room-scanner-as-a-native-expo-module-cip); [WWDC22 RoomPlan session](https://developer.apple.com/videos/play/wwdc2022/10127/)
- Object Capture on iOS (iOS 17+) offers a fully automated scan-to-USDZ flow and "works only on LiDAR enabled phones". — [WWDCNotes: Meet Object Capture for iOS (WWDC23)](https://wwdcnotes.com/documentation/wwdcnotes/wwdc23-10191-meet-object-capture-for-ios/)
- ARKit iOS 27: object tracking (previously visionOS-only) is now available on iOS, and reference objects trained in Create ML work on both platforms. — [WWDC26 visionOS 27 session 287](https://developer.apple.com/videos/play/wwdc2026/287/)
- ARKit `sceneReconstruction` (mesh) and `sceneDepth` frame semantics require LiDAR. — [Apple doc, not re-fetched: ARWorldTrackingConfiguration.supportsSceneReconstruction](https://developer.apple.com/documentation/arkit/arworldtrackingconfiguration/supportsscenereconstruction(_:))

**Camera APIs**
- WWDC26 camera sessions: high-resolution 24MP/48MP capture (RAW, bracketed, processed) on the Main, Tele and Ultra Wide cameras (session 304); responsive launch with "Deferred Start" (session 303); Center Stage front camera APIs such as `AVCaptureSmartFramingMonitor` (session 341). iOS 26 added `dynamicAspectRatio` on `AVCaptureDevice`. — [WWDC26 session 304](https://developer.apple.com/videos/play/wwdc2026/304/); [WWDC26 session 341](https://developer.apple.com/videos/play/wwdc2026/341/); [Blake Crosley: Responsive camera app in iOS 27](https://blakecrosley.com/blog/responsive-camera-app-ios-27)
- WWDC25 "Enhancing your camera experience with capture controls" covers physical capture controls, Camera Control and AirPods remote capture. — [WWDC25 session 253](https://developer.apple.com/videos/play/wwdc2025/253/)

**Speech / Translation**
- `SpeechAnalyzer` / `SpeechTranscriber` (new in iOS 26) run on-device. Language assets download through a system asset catalog, not inside the app. `SpeechTranscriber.supportedLocales` covers 42 locales in 22 languages. `DictationTranscriber` is the fallback for other locales. — [WWDC25 session 277](https://developer.apple.com/videos/play/wwdc2025/277/); [LoroNote, 2026](https://loronote.com/en/blog/apple-speechanalyzer-vs-whisper)
- The Translation framework (`TranslationSession`, `.translationTask`) translates in-app content with on-device models that work offline once the language is downloaded. — [Create with Swift](https://www.createwithswift.com/using-the-translation-framework-for-language-to-language-translation/); [Wikipedia: Translate (Apple)](https://en.wikipedia.org/wiki/Translate_(Apple))

**Other frameworks (SHIPPED; well-established, not re-fetched)**
- Core ML / Create ML (custom image, object, sound and text classifiers, trained on a Mac): [developer.apple.com/documentation/coreml](https://developer.apple.com/documentation/coreml)
- Sound Analysis (built-in sound classifier, `SNClassifySoundRequest`): [developer.apple.com/documentation/soundanalysis](https://developer.apple.com/documentation/soundanalysis)
- Natural Language (language ID, tokenization, tagging, embeddings): [developer.apple.com/documentation/naturallanguage](https://developer.apple.com/documentation/naturallanguage)
- Core Motion (accelerometer, gyro, magnetometer, `CMAltimeter`): [developer.apple.com/documentation/coremotion](https://developer.apple.com/documentation/coremotion)
- Nearby Interaction (UWB): [developer.apple.com/documentation/nearbyinteraction](https://developer.apple.com/documentation/nearbyinteraction)
- Core NFC: [developer.apple.com/documentation/corenfc](https://developer.apple.com/documentation/corenfc)
- PDFKit: [developer.apple.com/documentation/pdfkit](https://developer.apple.com/documentation/pdfkit)
- WidgetKit and ActivityKit (Live Activities): [developer.apple.com/documentation/activitykit](https://developer.apple.com/documentation/activitykit)
- LockedCameraCapture (lock-screen camera extension, iOS 18): [developer.apple.com/documentation/lockedcameracapture](https://developer.apple.com/documentation/lockedcameracapture)

### Inferences
- A typical offline "scan → recognize → structure → act" pipeline works on every iOS 26+ device except for the LLM step:
  1. VisionKit document camera / DataScanner
  2. `RecognizeDocumentsRequest` (tables, lists, data detectors)
  3. Foundation Models `@Generable` to turn the text into typed Swift structs
  4. Translation for Vietnamese↔English
  5. App Intents so the result appears in Spotlight, Siri and Visual Intelligence

  Steps 1, 2 and 4 run on all iOS 26+ devices. Step 3 needs iPhone 15 Pro or later.
- In iOS 27, the Foundation Models `OCRTool`/`BarcodeReaderTool` and image attachments mean an "identifier" feature (photo → description) can be built without training a custom model. Accuracy and device coverage for the new vision-capable on-device model still need to be checked (see Gaps).
- Because Private Cloud Compute is free under 2M downloads, a hybrid design is possible: offline by default, with PCC as an optional online fallback for heavy reasoning. This weakens the "100% offline" claim, so the report should present PCC as an optional mode.

### Gaps
- It is not confirmed whether the iOS 27 rebuilt on-device model with image input runs on every Apple Intelligence device (8 GB: iPhone 15 Pro, 16, 17, 17e) or only on the 12 GB devices. Apple says the "most powerful on-device model" is limited to iPhone 17 Pro/Pro Max/Air on iOS 27 (see Section 5). How this maps to `SystemLanguageModel` was not documented in the sources read.
- The WWDC26 Vision-framework-specific "what's new" session was not found. iOS 27 changes to Vision itself (other than via Foundation Models tools) are unconfirmed.
- The exact built-in class count for Sound Analysis and Natural Language's per-language support were not verified this session.

---

## 3. Vietnamese language support in each framework

### Takeaway
Vietnamese is well supported offline across Apple's stack as of iOS 26.1+/27: Live Text/Vision OCR (`vi-VT`), Translate/Translation, on-device dictation, SpeechTranscriber (reported), and Apple Intelligence / Foundation Models (since iOS 26.1). The main exceptions are Live Captions, call transcription and Personal Voice, which do not support Vietnamese. Whether the new iOS 26 `RecognizeDocumentsRequest` includes Vietnamese among its 26 languages is **not confirmed**.

### Cited Findings
- **Apple Intelligence / Foundation Models**: iOS 26.1 added eight languages, including Vietnamese. The full list is now 16 languages: English, Danish, Dutch, French, German, Italian, Norwegian, Portuguese, Spanish, Swedish, Turkish, Chinese (Simplified), Chinese (Traditional), Japanese, Korean and Vietnamese. — [9to5Mac, Nov 11, 2025](https://9to5mac.com/2025/11/11/ios-26-1-brings-apple-intelligence-to-these-eight-new-languages/); [Apple Support 121115](https://support.apple.com/en-us/121115) ("some features may not be available in all regions or languages")
- The on-device foundation model is multilingual and supports the languages Apple Intelligence supports. Developers should check `SystemLanguageModel.supportedLanguages` at runtime. — [Create with Swift: Exploring the Foundation Models framework](https://www.createwithswift.com/exploring-the-foundation-models-framework/); [WWDC25 "Meet the Foundation Models framework"](https://developer.apple.com/videos/play/wwdc2025/286/)
- **iOS 27 feature availability (Apple)**: Vietnamese is listed for Writing Tools, Genmoji, Image Playground, Visual Intelligence (plants & animals), **Live Translation in Messages**, Siri Product Knowledge, the Translate app ("Vietnamese (Vietnam)"), Dictation and **on-device dictation**. It is **not** listed for Live Captions, call transcription/recording or Personal Voice. — [Apple iOS feature availability](https://www.apple.com/ios/feature-availability/)
- **Vision OCR / Live Text**: Live Text supports 24 languages, including Vietnamese and Thai (per Apple's feature availability page, as compiled by Textora). `VNRecognizeTextRequest` revision 3 returns `vi-VT`. — [Textora: Live Text supported languages](https://textora.app/blog/live-text-supported-languages/); [GitHub issue with runtime output](https://github.com/ShawnPana/phone-harness/issues/91)
- **RecognizeDocumentsRequest**: "26 languages", but no list is given in the session. — [WWDC25 session 272](https://developer.apple.com/videos/play/wwdc2025/272/)
- **Translate / Translation framework**: Vietnamese was added to Apple Translate in 2022, and all Translate languages can be downloaded for offline use. — [Wikipedia: Translate (Apple)](https://en.wikipedia.org/wiki/Translate_(Apple)); Vietnamese is also listed on [Apple feature availability](https://www.apple.com/ios/feature-availability/)
- **SpeechTranscriber**: the 22 supported languages include Vietnamese (plus Thai, Malay and others). — [LoroNote, 2026](https://loronote.com/en/blog/apple-speechanalyzer-vs-whisper) (**single secondary source**)

### Inferences
- A Vietnamese developer can build Vietnamese-first OCR → translation → LLM summarization entirely on-device. The LLM step needs an Apple Intelligence device (iPhone 15 Pro or later) running iOS 26.1 or later, with Apple Intelligence enabled and the Vietnamese assets downloaded.
- Vietnamese diacritics (for example ạ, ử, ễ) are a known pain point for OCR. Apps should set `recognitionLanguages = ["vi-VT"]` explicitly, since the GitHub issue shows non-set languages produce gibberish. Accuracy should be tested on real Vietnamese receipts and documents.
- Vietnamese text uses more tokens per word than English in most tokenizers. Combined with the 4K context window in iOS 26, this limits long-document summarization, so chunking is needed. This is an inference; no Vietnamese-specific token ratio was found.

### Gaps
- No authoritative Apple list of `RecognizeDocumentsRequest`'s 26 languages was found. Check at runtime with `supportedRecognitionLanguages` on iOS 26.
- The SpeechTranscriber Vietnamese claim comes from one secondary source. Verify with `SpeechTranscriber.supportedLocales` on a device.
- No quality benchmarks were found for Apple's on-device LLM in Vietnamese. The tech report compares multilingual quality in aggregate only.

---

## 4. WWDC 2026 / iOS 27: shipped vs beta vs rumored

### Takeaway
WWDC26 (June 8–9, 2026) announced iOS 27, and **iOS 27 shipped publicly on Sep 14, 2026**. For on-device apps, the key additions are Foundation Models image input with OCR and barcode tools, a rebuilt on-device model, Core AI, Private Cloud Compute access, Visual Intelligence expansion, the Spotlight semantic index, and ARKit object tracking on iOS. Parts of the new Siri remain limited (English beta first, not in the EU at launch).

### Cited Findings
- iOS 27 was released on Sep 14, 2026. — [Apple Newsroom (iPhone 18 Pro)](https://www.apple.com/newsroom/2026/09/apple-debuts-iphone-18-pro-and-iphone-18-pro-max/)
- WWDC26 Platforms State of the Union announced:
  - free PCC Foundation Models access for developers under 2M first-time downloads
  - image input
  - third-party models (Claude, Gemini) through the same Swift API
  - Dynamic Profiles
  - open-sourcing the framework "later this summer"
  - Core AI
  - Spotlight semantic index contributions
  - the View Annotations API
  - Xcode 27 (Apple silicon only, agentic coding)
  - iPhone apps resizable on iPad

  — [MacRumors, June 9, 2026](https://www.macrumors.com/2026/06/09/apple-outlines-major-ai-and-developer-tool-updates/)
- On-demand resources (ODR) are **deprecated** as of iOS 27, iPadOS 27, tvOS 27 and visionOS 27. Apple recommends migrating to Background Assets. — [App Store Connect Help: On-demand resources size limits](https://developer.apple.com/help/app-store-connect/reference/app-uploads/on-demand-resources-size-limits)
- The new Siri is described as "profoundly more personal, capable, and conversational", with a Siri mode in the Camera app, rolling out as a beta in English first. — [Apple Newsroom](https://www.apple.com/newsroom/2026/09/apple-debuts-iphone-18-pro-and-iphone-18-pro-max/). "Siri AI won't be available on any iPhone or iPad in the European Union at launch." — [MacRumors, Sep 9, 2026](https://www.macrumors.com/2026/09/09/which-iphones-support-every-ios-27-feature/)
- A "iPhone Duo SDK" for iOS 27.1 is reported, with `AVCaptureDeviceDirectionCoordinator` for a foldable's front/back camera direction. **UNVERIFIED; possibly beta.** — [ecorpit.com](https://ecorpit.com/iphone-duo-sdk-new-apis-xcode-27-1-developer-guide-2026/)

### Inferences
- A "technical feasibility" section written for launch in late 2026 or 2027 should target **iOS 26 as the minimum**. Apple's own June 2026 figures put iOS 26 on 79% of all iPhones. iOS 27-only APIs (FM vision, OCRTool, Core AI) should be optional enhancements behind `if #available(iOS 27, *)`, because iOS 27 was only two weeks old at research time.

### Gaps
- iOS 27 adoption figures are not yet available (released two weeks ago).
- The open-source release status of the Foundation Models framework ("later this summer") was not confirmed.

---

## 5. How many iPhones can run this: iOS 26/27, Apple Intelligence, LiDAR

### Takeaway
iOS 26 was on **79% of all iPhones and 86% of iPhones from the last four years in June 2026** (Apple's figures). iOS 27 supports the same devices as iOS 26 (iPhone 11 and later). Apple Intelligence and Foundation Models require **iPhone 15 Pro/Pro Max or any iPhone 16/17/18 model**. There is **no reliable official figure** for the Apple Intelligence-capable or LiDAR-equipped share of active iPhones. Estimates suggest well under half for Apple Intelligence and a minority for LiDAR.

### Cited Findings
- June 2026 (Apple data): iOS 26 on 79% of all iPhones and 86% of iPhones from the last four years. Comparable iOS 18 figures a year earlier were 82% and 88%. 14% were still on iOS 18 and 7% on older versions. — [AppleInsider, June 10, 2026](https://appleinsider.com/articles/26/06/10/fewer-iphone-users-are-updating-to-ios-26-than-they-did-with-ios-18)
- February 2026 (Apple data): 66% of all iPhones and 74% of the last four years on iOS 26. — [MacRumors, Feb 13, 2026](https://www.macrumors.com/2026/02/13/apple-shares-ios-26-adoption-stats/); [Daring Fireball](https://daringfireball.net/2026/02/apple_releases_ios_26_adoption_rates)
- iOS 27 keeps compatibility with iPhone 11 and later, including iPhone SE (2nd gen and later). — [AppleInsider, June 8, 2026](https://appleinsider.com/articles/26/06/08/ios-27-keeps-iphone-11-and-newer-compatibility)
- iOS 27 tiers:
  - **Top tier (12 GB RAM)**: iPhone 17 Pro/Pro Max and iPhone Air get "every new Siri AI feature", "higher accuracy for speech-to-text dictation" and expressive Siri voices.
  - **Standard Apple Intelligence**: iPhone 16 lineup (including 16e), iPhone 15 Pro/Pro Max, and iPhone 17/17e (8 GB).
  - **No Apple Intelligence**: iPhone 11 through iPhone 15/15 Plus.

  — [MacRumors, Sep 9, 2026](https://www.macrumors.com/2026/09/09/which-iphones-support-every-ios-27-feature/); [AppleInsider, June 8, 2026](https://appleinsider.com/articles/26/06/08/major-new-apple-intelligence-features-limited-to-the-newest-iphones-macs). The iPhone 18 Pro likely belongs in the top tier, but this was not stated in the sources.
- Apple Intelligence needs up to 14 GB of free storage on the newer Pro/Air models and up to 8 GB on other supported iPhones. It does not work on devices bought in mainland China with a mainland China account. — [Apple Support 121115](https://support.apple.com/en-us/121115)
- Apple reported more than 2.5 billion active devices (all types) in January 2026. — [AppleInsider, Jan 29, 2026](https://appleinsider.com/articles/26/01/29/apple-reaches-25-billion-active-devices-after-record-breaking-quarter)
- "Apple Intelligence enabled on ~940 million devices (iPhone+iPad+Mac) as of Q1 2026" comes from an aggregator. **UNVERIFIED and should not be used as fact.** — [Presenc AI](https://presenc.ai/research/apple-intelligence-usage-statistics-2026)
- LiDAR proxy: in the US, Pro/Pro Max models made up 38% of iPhone sales in Q1 2025 (iPhone 16 Pro series), down from 45% a year earlier (iPhone 15 Pro series). — [9to5Mac citing CIRP, Apr 23, 2025](https://9to5mac.com/2025/04/23/iphone-16-pro-is-the-surprise-loser-in-apples-recent-sales/); [Patently Apple](https://www.patentlyapple.com/2025/04/cirp-reports-that-apples-q1-25-us-sales-data-shows-the-iphone-16-basic-models-were-strong-while-pro-models-share-declined.html)

### Inferences
- **Apple Intelligence-capable share (estimate)**: capable models started in September 2023 (15 Pro) and cover every model from September 2024 onward. Given typical 3–4+ year replacement cycles and a mix of older phones still in use, the capable share of active iPhones in late 2026 is plausibly in the **~35–50%** range. It is higher in the US and other rich markets and lower in markets like Vietnam, where older and used iPhones are common. **This is an estimate, not a sourced figure.**
- **LiDAR share (estimate)**: Pro models are roughly 35–45% of new US sales (CIRP), and LiDAR has shipped only since iPhone 12 Pro (2020), so LiDAR phones are probably **a minority (~25–35%) of active iPhones** worldwide. **Estimate.** LiDAR-dependent features (RoomPlan, Object Capture, scene mesh) should therefore be premium or optional, with photogrammetry or ARKit plane detection as a fallback.
- For Vietnam specifically, the used-iPhone market (iPhone 11–14 are very popular) means that Vision, VisionKit, Core ML and Translation features (available to all iOS 26 devices) should be the core. Foundation Models features should be an enhancement.

### Gaps
- Apple does not publish the Apple Intelligence-capable or LiDAR share of its active base. No reliable Vietnam-specific iPhone model mix was found.
- No iOS 27 adoption data yet.

---

## 6. App Review guidelines and submission requirements checklist (camera, scanner, identifier, 3D, AI apps)

### Takeaway
The biggest risks for a scanner, identifier or AI utility are:
- **4.3(b) spam / saturated categories**, tightened again on June 8, 2026
- **4.2 minimum functionality**
- **2.1 completeness** (crashes, broken IAP)
- **5.1.1 privacy**: purpose strings, privacy policy, account deletion
- **3.1.x IAP/subscription rules**
- **1.4.1 medical accuracy** for health-related identifiers

Required admin items: age-rating questionnaire (deadline Jan 31, 2026), Xcode 26 / iOS 26 SDK (since Apr 28, 2026), privacy manifest and required-reason APIs, EU DSA trader status, and a privacy nutrition label. Accessibility Nutrition Labels are voluntary for now.

### Cited Findings
**Guideline text (current)**
- **2.1 App Completeness**: submissions must be final, with no placeholder content, tested on-device, with a demo account if there is a login. "We will reject incomplete app bundles and binaries that crash." Configured IAPs must be visible and functional for review. — [App Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)
- **2.3.1(a)**: no hidden, dormant or undocumented features. New features must be "described with specificity in the Notes for Review". The guideline also bans misleading marketing, for example "iOS-based virus and malware scanners". — [App Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)
- **2.5.2**: apps may not "download, install, or execute code which introduces or changes features or functionality of the app". — [App Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)
- **4.2.3(ii)**: "If your app needs to download additional resources in order to function on initial launch, disclose the size of the download and prompt users before doing so." This applies directly to downloading ML models or language packs. — [App Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)
- **4.2 Minimum Functionality**: an app must be "useful, unique, or 'app-like'" and provide "lasting entertainment value or adequate utility". — [App Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)
- **4.3(b) Spam** (updated June 8, 2026): "Don't submit apps that are indistinguishable from what's already widely available…"
  - "dating, flashlight, sound effects, wallpaper, simple timers, and fortune telling" will not be accepted "unless they offer a meaningfully different or improved experience".
  - New in June 2026: "We may remove these apps from the App Store going forward if they are not updated, improved, or do not attract customers."
  - Low-effort categories (for example drinking games and fart apps) can lead to removal from the Developer Program.

  — [App Review Guidelines](https://developer.apple.com/app-store/review/guidelines/); [9to5Mac, June 9, 2026](https://9to5mac.com/2026/06/09/apple-tightens-app-review-guidelines-against-apps-that-do-not-add-value-to-the-app-store/); [TechCrunch, June 9, 2026](https://techcrunch.com/2026/06/09/apple-says-it-may-remove-apps-from-the-app-store-if-they-dont-attract-users/)
- QR code scanners, calculators, converters and flashlights are reported (by third-party compliance blogs, **not Apple's text**) as the categories that most often get 4.3(b) rejections. — [AppCompliance: 4.3 spam](https://appcompliance.io/blog/apple-guideline-4-3-spam-rejection/); [ezscreenshots: 4.3(b)](https://ezscreenshots.com/blog/design-spam-rejection-4-3b)
- The other 2026 guideline revisions are:
  - February 6, 2026: random/anonymous chat apps fall under 1.2 UGC.
  - June 8, 2026: 4.3 tightening; 4.5.3 bars Live Activities for spam, phishing or unsolicited messages; clarified requirements for the Sensitive Content Analysis framework, Suggested Actions API and Trust Insights framework.

  — [Apple Developer News](https://developer.apple.com/news/?id=a233fmpw); [AppCompliance: 2026 changes](https://appcompliance.io/blog/apple-2026-app-review-guideline-changes/)
- **3.1.1 IAP**: unlocking features requires IAP, and license keys or QR codes may not unlock functionality. Free trials for non-subscription apps use a $0 non-consumable "XX-day Trial". **3.1.2(a)** subscriptions must give "ongoing value", last at least 7 days and work across devices. **3.1.1(a)**: in the US storefront, external purchase links and buttons are allowed. Elsewhere, only through regional entitlements. — [App Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)
- **5.1.1(i)**: a privacy policy link is required both in App Store Connect and in the app. **(ii)** consent is required, and "Ensure your purpose strings clearly and completely describe your use of the data". **(v)** "If your app supports account creation, you must also offer account deletion within the app", and apps should not force a login without significant account-based features. **(ix)** regulated fields (healthcare, finance) must be submitted by a legal entity. — [App Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)
- **5.1.2(i)**: "You must clearly disclose where personal data will be shared with third parties, including with third-party AI, and obtain explicit permission before doing so." ATT permission is required for tracking. — [App Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)
- **1.4.1 Medical**: apps that could give inaccurate data, or be used for diagnosis, get greater scrutiny. Apps "that claim to take x-rays, measure blood pressure, body temperature, blood glucose levels, or blood oxygen levels using only the sensors on the device are not permitted". Apps should remind users to consult a doctor. — [App Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)
- **Foundation Models acceptable-use rules** apply in addition to the guidelines (no regulated health, legal or financial services, no biometric classification of people, and so on). — [Acceptable use requirements](https://developer.apple.com/apple-intelligence/acceptable-use-requirements-for-the-foundation-models-framework/)

**Submission requirements (with dates)**
- Since April 28, 2026, apps must be built with **Xcode 26+ and the iOS 26 SDK**. Since September 9, 2026, iOS/iPadOS apps must target iOS 13 or later. — [Apple: Upcoming requirements](https://developer.apple.com/news/upcoming-requirements/)
- **Age ratings**:
  - New bands 4+, 9+, **13+, 16+, 18+** (12+ and 17+ removed).
  - New required questions on in-app controls, capabilities, medical/wellness topics and violent themes.
  - Answers were due **January 31, 2026**, otherwise app updates are interrupted.
  - Ratings are per country or region, and developers may set a higher rating.

  — [Apple Developer News: Updated age ratings](https://developer.apple.com/news/?id=ks775ehf); [TechCrunch, July 25, 2025](https://techcrunch.com/2025/07/25/apple-broadens-app-stores-age-rating-system)
- **EU DSA trader status**: required to submit updates for EU distribution since October 16, 2024. Apps without verified status have been removed from the EU App Store since February 17, 2025. — [Apple: Upcoming requirements](https://developer.apple.com/news/upcoming-requirements/)
- **Privacy manifests**: since May 1, 2024, approved reasons are required for "required reason APIs" (for example UserDefaults, file timestamps, system boot time, disk space) in the app and SDKs. Commonly used third-party SDKs must include privacy manifests and signatures when added as binaries. — [Apple: Upcoming requirements](https://developer.apple.com/news/upcoming-requirements/); [Apple News: Privacy updates for App Store submissions](https://developer.apple.com/news/?id=3d8a9yyh); [Adding a privacy manifest](https://developer.apple.com/documentation/bundleresources/adding-a-privacy-manifest-to-your-app-or-third-party-sdk)
- **Accessibility Nutrition Labels** (announced 2025): voluntary for now, with Apple saying they will become required in the future. They cover VoiceOver, Voice Control, larger text, dark interface, sufficient contrast, reduced motion, captions and more. Developers declaring support must verify that all common tasks can be completed with the feature. — [Apple Support: accessibility information in the App Store](https://support.apple.com/en-us/123073); [App Store story](https://apps.apple.com/us/story/id1814164299)
- **Rejection statistics**: in 2024 Apple rejected 1,931,400 submissions (about 25% of those reviewed). "Performance" (2.1) was the top reason, followed by legal/privacy and design (4.2/4.3). — [MacRumors on the 2024 App Store Transparency Report](https://www.macrumors.com/2025/05/30/app-store-2024-transparency-report/); [Apple 2024 Transparency Report PDF](https://www.apple.com/legal/more-resources/docs/2024-App-Store-Transparency-Report.pdf)

**Permission purpose strings (Info.plist; Apple doc, not re-fetched)**
- `NSCameraUsageDescription` (camera). Without it the app crashes on access, which is a 2.1 rejection.
- `NSPhotoLibraryUsageDescription` / `NSPhotoLibraryAddUsageDescription` (photos). `PHPickerViewController` needs no photo permission.
- `NSMicrophoneUsageDescription` (microphone) and `NSSpeechRecognitionUsageDescription` (speech recognition).
- `NFCReaderUsageDescription` (NFC), plus the NFC entitlement.
- `NSNearbyInteractionUsageDescription` (UWB), `NSMotionUsageDescription` (motion) and `NSLocationWhenInUseUsageDescription` (location).

Source: [Apple doc: Requesting access to protected resources](https://developer.apple.com/documentation/uikit/requesting-access-to-protected-resources)

### Inferences
- **Common rejection patterns for scanner/identifier apps**:
  1. 4.3(b): a "yet another QR/document scanner" with no clear difference.
  2. 3.1.2: a paywall that blocks basic scanning, or a weekly subscription without "ongoing value".
  3. 5.1.1(ii): vague purpose strings such as "App needs camera".
  4. 2.3.x: screenshots or claims that overstate accuracy, for example "identify any disease".
  5. 1.4.1: skin, mole or pill identifiers presented as diagnosis.
  6. 2.1: a crash when permission is denied, or on devices without LiDAR. Gate LiDAR features with `isSupported` checks, or declare the `UIRequiredDeviceCapabilities` key.
  7. 4.2.3(ii): a large model download on first launch without disclosure.
- **Differentiation that helps pass 4.3**: fully offline processing, Vietnamese-specific OCR and data extraction (CCCD/receipts/invoices), table-to-spreadsheet export, a Visual Intelligence/App Intents integration, and on-device LLM structuring. Apple's 4.3(b) language rewards a "meaningfully different or improved experience".
- An offline-only app with no accounts avoids 5.1.1(v) account deletion and ATT entirely. It must still provide a privacy policy URL.
- Mushroom or plant toxicity identifiers are not named in 1.4.1, but they fall under "physical harm" logic. Disclaimers are advisable (inference).

### Gaps
- The exact wording of the new age-rating questions (for example, whether they ask about AI chatbots or generative AI) was not retrieved.
- There is no official Apple list of "saturated" categories beyond the 4.3(b) examples. QR/scanner saturation is known only from third-party reports.
- A 2025 App Store Transparency Report (covering 2025 data) was not found. The latest found is the 2024 report.
- There is no explicit guideline on downloading Core ML models after install. Apple's 2.5.2 bans code that changes functionality. Updating model weights as data is common practice, but no Apple statement was found that explicitly allows it.

---

## 7. Practical offline advantages and limits (privacy label, cost, app size, asset delivery)

### Takeaway
Doing all processing on-device lets an app honestly claim "Data Not Collected", avoid server and API costs (including free on-device LLM inference), and work without connectivity. The limits are:
- a 4 GB app bundle (iOS 18+)
- a 200 MB cellular download prompt threshold
- a 4K-token LLM context (iOS 26)
- Apple Intelligence's own 8–14 GB storage requirement
- device fragmentation (Apple Intelligence and LiDAR)

Large custom models should use **Background Assets**. Apple-hosted Background Assets offer up to 200 GB per app from iOS 26, and on-demand resources are deprecated in iOS 27.

### Cited Findings
- App bundle limit: **4 GB for iOS 18 or later** (2 GB earlier). ODR asset packs up to 8 GB each and 70 GB hosted on iOS 18+. ODR is deprecated in iOS 27, and Apple recommends Background Assets. — [App Store Connect Help: size limits](https://developer.apple.com/help/app-store-connect/reference/app-uploads/on-demand-resources-size-limits)
- **Apple-hosted Background Assets** (iOS 26+): Apple hosts up to **200 GB** of assets per app as part of the Developer Program membership. The system downloads asset packs automatically when needed, and this suits ML models. — [WWDC25 "Discover Apple-Hosted Background Assets" (notes)](https://wwdcnotes.com/documentation/wwdcnotes/wwdc25-325-discover-applehosted-background-assets/); [Background Assets docs](https://developer.apple.com/documentation/backgroundassets)
- The cellular download alert threshold is 200 MB, and Background Assets downloads count toward it. — [Adapty glossary](https://adapty.io/glossary/app-size/); [Apple Developer Forums: Background Assets](https://developer.apple.com/forums/tags/background-assets?sortBy=oldest) (secondary)
- Foundation Models on-device inference is free, needs no API key, and runs offline. PCC (online) is free under 2M first-time downloads. — [WWDC26 session 241](https://developer.apple.com/videos/play/wwdc2026/241/)
- Speech language assets are downloaded by the system, not bundled in the app, so they do not add to app size. — [LoroNote](https://loronote.com/en/blog/apple-speechanalyzer-vs-whisper)
- Apple Intelligence needs up to 14 GB (newer Pro/Air) or up to 8 GB (others) of free storage. The user must have it enabled, so the model may be unavailable even on capable devices. — [Apple Support 121115](https://support.apple.com/en-us/121115)
- Privacy label definition: "collect" means transmitting data off the device in a way that lets the developer or partners access it for longer than needed to service the request in real time. Data processed only on-device does not need to be disclosed. — [Apple: App privacy details on the App Store](https://developer.apple.com/app-store/app-privacy-details/) (Apple doc, not re-fetched)

### Inferences
- **Positioning for the report**: "100% offline, no data leaves the phone" can be backed by the "Data Not Collected" label if no analytics or crash SDK sends data. Adding Firebase or Crashlytics would change the label. Apple's own privacy messaging reinforces this positioning.
- **Cost model**: the marginal cost per user is close to zero (no GPU, OCR or translation API bills). This favors one-time purchases or cheap subscriptions. However, 3.1.2 requires "ongoing value" for subscriptions, which is harder to justify without a cloud service. Regular model and feature updates or new document templates can justify it.
- **Design for availability**: check `SystemLanguageModel.default.availability` (device not eligible, Apple Intelligence not enabled, model not ready) and fall back to non-LLM logic. For LiDAR features use `ARWorldTrackingConfiguration.supportsSceneReconstruction`, `RoomCaptureSession.isSupported` and `ObjectCaptureSession.isSupported`.
- Keep the base bundle small (well below 200 MB if possible) so users on cellular data are not prompted. Ship Core ML models larger than about 100 MB as Background Assets, with disclosure per 4.2.3(ii).

### Gaps
- An Apple primary source confirming the exact 200 MB cellular threshold was not fetched in this session (only secondary sources).
- Energy and thermal limits for sustained on-device LLM or vision use on older A17 Pro/A18 devices were not researched.
