# Niche opportunities for offline-first iPhone apps using on-device hardware (camera, OCR, LiDAR, depth, motion, mic, Neural Engine), as of Sept 2026

Scope note: research done 2026-09-27 with web search and page fetches. Revenue numbers are labeled **[self-reported]**, **[company-reported]** or **[third-party estimate]**. Sensor Tower/AppMagic "last month" figures are snapshots shown on the pages when retrieved in Sept 2026. The exact month is not always shown, so treat them as order-of-magnitude figures. Several sources are competitor or affiliate blogs, and they are flagged where it matters.

---

## Key Question 1 — What do users complain about in leading scanner / identifier / 3D apps?

### Takeaway
The same complaints come up across document scanners, identifier apps and 3D/LiDAR apps. The most common are (1) aggressive weekly subscriptions and deceptive "free trials", (2) paywalls on basic outputs (watermarks, export formats, lock-out of old work), (3) distrust of cloud upload and privacy, and (4) inaccuracy in edge cases such as regional plants, mixed dishes and portion size, or measurements off by several inches. Each of these complaints gives a new app a way to position itself: offline, one-time or fair pricing, no lock-in, and accuracy in one niche.

### Cited Findings
**Document scanners**
- Reddit sentiment on CamScanner, as aggregated by a 2026 blog, is "consistently negative": "CamScanner is not free anymore", the free tier watermarks every scan and limits monthly scans, and users ask "Why would I pay $5/month for something Notes does for free?" iPhone subreddits are "nearly unanimous" in recommending the built-in Notes scanner — [WildandFree Tools, "Best Document Scanner App in 2026 — What Reddit Actually Recommends"](https://wildandfreetools.com/blog/best-document-scanner-app-reddit-2026/) (secondary aggregator, 2026).
- The same source says many third-party scanner apps use weekly subscriptions priced at about $3.99–$9.99/week — [WildandFree Tools, 2026](https://wildandfreetools.com/blog/best-document-scanner-app-reddit-2026/).
- The privacy distrust has a history. In Aug–Sep 2019 Kaspersky found the trojan dropper "Trojan-Dropper.AndroidOS.Necro.n" in CamScanner's Android app, which had 100M+ Google Play downloads. It came from an ad library that could show intrusive ads or sign users up for paid subscriptions. Google removed the app, and a fixed version returned on Sept 5, 2019 — [Kaspersky blog](https://www.kaspersky.com/blog/camscanner-malicious-android-app/28156/); [Security Affairs](https://securityaffairs.com/90454/malware/camscanner-app-malware.html). (Android only. No iOS malware was reported. The brand damage lasts.)
- Many "offline OCR, no subscription" utilities now position against this, for example Off Lens (VisionKit, "no uploads, no tracking, no ads"), IND Text Scanner – Offline OCR ("no signup, no subscription") and OnDevice OCR Pro, and a Show HN (Aug 2025) turned the iPhone into a local OCR server using Vision — [Off Lens, App Store](https://apps.apple.com/us/app/off-lens/id6755901773); [IND Text Scanner, App Store](https://apps.apple.com/us/app/ind-text-scanner-offline-ocr/id1448584617); [Show HN: OCR Server, Hacker News, Aug 2025](https://news.ycombinator.com/item?id=44879659). The "offline OCR" positioning on its own is therefore already crowded (see Q5).
- Genius Scan (The Grizzly Labs, Paris) markets "100% on-device processing… no data ever leaves the device unless you decide it should", and if you don't create an account, "your documents remain on your device" — [Genius Scan privacy policy](https://help.geniusscan.com/security-and-privacy/privacy-policy); [The Grizzly Labs Enterprise](https://thegrizzlylabs.com/enterprise/).

**Identifier apps (plants etc.)**
- PictureThis complaints: the "free trial is not really free", users report unauthorized subscription charges and hard cancellation, and identification and disease diagnosis are inaccurate. Specific complaints mention Japanese plants, rice and succulents, and "when it was wrong… none of the suggestions were even close" — [ComplaintsBoard](https://www.complaintsboard.com/picturethis-plant-identifier-b149857); [Unstar, Plant ID apps ranked 2026](https://unstar.app/blog/plant-identification-apps-ranked-picturethis-plantin-plantnet-2026); [JustUseApp reviews 2026](https://justuseapp.com/en/app/1252497129/picturethis-plant-identifier/reviews) (review aggregators).
- PictureThis costs $39.99/year — [identifythis.app blog](https://identifythis.app/blog/picture-this-plant-identification-app) (competitor blog).

**3D / LiDAR apps**
- On Polycam's free tier, exports are GLTF only. OBJ, FBX, STL, PLY and LAS (the formats needed for CAD, GIS and 3D printing) need a paid plan — [SkyeBrowse, "Polycam Review"](https://www.skyebrowse.com/news/posts/polycam-review) (competitor-authored review).
- Trustpilot reviewers say Polycam "more than doubled the price for the same functionality" and that $149/year is "basically worthless for basic functionality". One reviewer wrote that instead of "€26 for Polycam PRO with 1000 pictures and every export format" they now get "€35 for BASIC with 300 pictures and missing formats", and asked whether students should pay €300 to capture and export one project. Other reviewers say they were charged before the trial ended and got no support replies — [Trustpilot: poly.cam reviews](https://www.trustpilot.com/review/poly.cam) (via search snippets).
- magicplan (LiDAR/AR floor plans): users say they were locked out of plans created over 3–4 years after the move to subscription-only, and report measurement errors of 6–8 inches that "broke" the plan when corrected. The free tier is limited to 2 projects — [App Store reviews, magicplan](https://apps.apple.com/us/app/magicplan/id427424432?see-all=reviews); [JustUseApp magicplan reviews 2025](https://justuseapp.com/en/app/427424432/magicplan/reviews).

**AI calorie apps**
- Cal AI "has no published validation against weighed references" and its accuracy claims are "marketing rather than measured". Users report that calories are often wrong because the app cannot measure weight, and that branded items and sauces (e.g., marinades, sodium) are poorly handled — [Clinical Nutrition Report, "Best AI Calorie Tracker on Reddit?" 2026](https://clinicalnutritionreport.com/articles/best-ai-calorie-tracker-reddit-2026/). **Caution:** the same page promotes a competitor (PlateLens, "±1.1% MAPE in the May 2026 DAI six-app benchmark"). That benchmark could not be verified and the site may be affiliate-driven.
- Cal AI's founders themselves claim "90% accurate" recognition, and TechCrunch could not validate their metrics — [TechCrunch, 2025-03-16](https://techcrunch.com/2025/03/16/photo-calorie-app-cal-ai-downloaded-over-a-million-times-was-built-by-two-teenagers/). MyFitnessPal's CEO said Cal AI prioritizes speed over accuracy ("There is an audience of people that want it fast") — [TechCrunch, 2026-03-02](https://techcrunch.com/2026/03/02/myfitnesspal-has-acquired-cal-ai-the-viral-calorie-app-built-by-teens/).

**Accessibility apps**
- Blind users on AppleVis like the detail in Seeing AI / Be My Eyes descriptions but are uneasy about "not knowing where the apps are sending their pictures". They would feel more comfortable if analysis ran on-device — [AppleVis forum "Through the AIs of the Blind"](https://www.applevis.com/forum/ios-ipados/through-ais-blind) (via search summary). Be My AI supports 36 languages and runs in the cloud. Be My Eyes has 500K+ blind users and 7M+ volunteers — [AppleVis: Be My Eyes](http://www.applevis.com/apps/ios/lifestyle/be-my-eyes-helping-blind-see).

**Home inventory**
- Encircle retired its free consumer home-inventory app on Dec 17, 2025 to focus on paid restoration-contractor tools. This left a gap that many 2026 competitor blogs now target — [Re_Tera "Encircle alternative"](https://getretera.com/encircle-alternative); [HomeProof blog 2026](https://homeproofvault.com/blog/best-home-inventory-apps-compared/) (both competitor blogs; the date has not been confirmed by Encircle directly).

### Inferences
- "Offline + no weekly subscription + no lock-in of your own data" is table stakes for new entrants in these categories. It is not a differentiator by itself, because many cheap "offline OCR" apps already claim it. It must be paired with a vertical, such as a document type, a language, a profession or an output format.
- Paywalling export formats (Polycam) and locking users out of old work (magicplan) are the most emotionally charged complaints. A model with "free export in all formats, pay once for Pro workflow" or "pay per project" is a credible wedge for 3D/LiDAR.
- Identifier and calorie apps lose trust through inaccuracy in regional or long-tail cases. That points to localized models or catalogs (Vietnamese/SEA foods, tropical plants) as a defensible niche. This is an inference, and no Vietnamese-specific accuracy data was found.

### Gaps
- Could not retrieve raw 1–2 star App Store reviews in bulk (App Store pages aren't easily fetchable). The complaint themes come from review aggregators and blogs.
- No quantitative study found on how often users choose apps because they are "offline" or "private" (as opposed to anecdotes).
- Complaints about Vietnamese-language OCR quality in incumbent apps (CamScanner, Adobe Scan, Microsoft Lens) were not found in English or Vietnamese sources in this session.

---

## Key Question 2 — Indie/small-team success stories 2023–2026 with disclosed revenue: what made them work?

### Takeaway
The biggest camera-first successes, Cal AI and Umax, were tiny teams that paired one "snap a photo → instant AI answer" feature with a weekly or annual subscription and mass micro-influencer or UGC distribution on TikTok and Instagram. Both used cloud LLM APIs rather than on-device models. Identifier apps (plants, coins) still earn millions per month according to estimates. But the median indie app earns very little, so distribution and niche choice matter more than the tech.

### Cited Findings
**Cal AI (photo calorie tracker)**
- Launched May 2024 by teenagers Zach Yadegari and Henry Langmack. More than 5M downloads in 8 months and "over $2 million last month" (Feb 2025), both **[self-reported]**. "TechCrunch couldn't validate his download and revenue claims". Rated 4.8★ with 66K App Store reviews, retention >30% [self-reported], 8 full-time staff at the time. It uses "models from Anthropic and OpenAI and RAG… trained on open source food calorie and image databases", and the team found "different models are better with different foods". COO Jake Castillo runs influencer marketing — [TechCrunch, 2025-03-16](https://techcrunch.com/2025/03/16/photo-calorie-app-cal-ai-downloaded-over-a-million-times-was-built-by-two-teenagers/).
- $600K+ MRR with fewer than 5 staff **[self-reported]**, as of Dec 29, 2024 — [Consumer Startups Substack, "lightweight AI consumer utility apps"](https://consumerstartups.substack.com/p/lightweight-ai-consumer-utility-apps).
- Growth used a high-volume micro-influencer strategy (fitness, food and lifestyle creators, reportedly about 150 working with the app regularly), and the core users are aged 15–25 — [secondary playbook write-ups: Starter Story](https://www.starterstory.com/cal-ai-breakdown); [Stormy AI blog](https://stormy.ai/blog/cal-ai-tiktok-marketing-playbook-2026) (secondary; the influencer count is not confirmed by TechCrunch).
- Acquired by MyFitnessPal. The deal closed in Dec 2025 and was announced Mar 2, 2026: 15M+ downloads and $30M+ annual revenue in under 2 years **[company-reported]**, 7 employees retained, terms undisclosed. MyFitnessPal tracks about 70 competitors, and Cal AI and MyFitnessPal are "neck-and-neck in the top rankings in their category" — [TechCrunch, 2026-03-02](https://techcrunch.com/2026/03/02/myfitnesspal-has-acquired-cal-ai-the-viral-calorie-app-built-by-teens/).
- Getlatka lists "$40M ARR" for 2026 — [Getlatka](https://getlatka.com/companies/calai.app) (aggregator, low reliability; conflicts with the $30M company-reported figure).

**Umax (AI face rating / "looksmaxxing")**
- "We hit $6 million annual recurring revenue in just 3.5 months" — founder Blake Anderson **[self-reported]**, X post, Apr 2024 — [X/@8teAPi interview clip](https://x.com/8teAPi/status/1780278714573693110?lang=en).
- About $500K/month in subscription revenue ("could not be independently verified"), $3.99/week, 7M downloads per Anderson, 90% of users male aged 16–45. Psychologists warn these apps are worsening youth mental health — [Fortune, 2024-07-01](https://fortune.com/2024/07/01/looksmaxxing-apps-rate-teen-boys-faces-mental-health/).
- A later figure puts Umax at "350 to 400k a month" **[self-reported, via newsletter]** — [Scale Nuggets](https://scalenuggets.beehiiv.com/p/23yearold-whos-making-11myear-ai-apps) (secondary).

**Other small AI consumer utilities (Consumer Startups, Dec 29, 2024)**
- BoldVoice (accent/pronunciation training, uses the microphone) $500K+ MRR with fewer than 15 staff **[self-reported]**. PDF.AI (chat with PDFs) $50K+ MRR, solo **[self-reported]**. InteriorAI $30K+ MRR, solo **[self-reported]**. InkGen (tattoo) $10K+ MRR **[self-reported]**. Plug AI/RizzGPT $200K+ MRR **[self-reported]**. The success pattern described: a real consumer pain point, "1–2 killer features", a very small team, and riding a trend — [Consumer Startups Substack](https://consumerstartups.substack.com/p/lightweight-ai-consumer-utility-apps).

**Identifier apps (third-party estimates)**
- PictureThis (Glority): about 700K downloads and $5M revenue last month on the US App Store, about 400K / $3M in Canada, and about 1M downloads / $700K on US Google Play **[Sensor Tower estimates, snapshot retrieved Sept 2026]**. 100M+ total downloads claimed — [Sensor Tower US iOS](https://app.sensortower.com/overview/1252497129?country=US); [Sensor Tower CA](https://sensortower.com/ios/ca/glority-global-group-ltd/app/picturethis-plant-identifier/1252497129). The Canada figure looks high relative to the US and should be treated with caution.
- CoinSnap – Coin Identifier: about 300K downloads and $400K revenue per month. Coin ID: about 80K downloads and $100K per month **[Sensor Tower estimates, snapshot]** — [Sensor Tower CoinSnap](https://app.sensortower.com/overview/com.coinidentifyer.ai?country=US); [Adapty paywall library: Coin ID](https://adapty.io/paywall-library/coin-id-coin-value-identifier/). A privacy-focused indie coin identifier (on-device, no account, no tracking) also exists — [Emory Wheel, 2025-12-27](https://emorywheel.com/article/top-10-free-coin-identifier-and-value-apps-20251227).

**Privacy/on-device incumbent**
- Genius Scan (bootstrapped, 100% on-device processing) is cited in its press materials for "Bootstrapping a Subscription App to 5M MAU and 2X+ Revenue Growth" (Jan 2025) — [The Grizzly Labs press page](https://thegrizzlylabs.com/press/) (headline only; revenue not disclosed).

**Base rates (sobering)**
- The median indie iOS app earns under $500/month. The top 5% exceed $10K/month and the top 1% exceed $50K. Subscription apps earn about 4.5x more lifetime revenue per user than one-time-purchase apps. Only about 4.6% of new subscription apps reach $10K MRR within 2 years (attributed to RevenueCat's 2025 State of Subscription Apps) — [The Swift Kit blog, 2026](https://theswiftk.it.com/blog/how-to-monetize-ios-app-indie-developer); [Indie Hackers/secondary](https://theswiftk.it.com/blog/zero-to-10k-mrr-indie-ios-app) (secondary citations of RevenueCat; the primary report was not fetched).
- An Indie Hackers post describes an app portfolio reaching $60K/month after Apple froze the developer's account **[self-reported]** — [Indie Hackers](https://www.indiehackers.com/post/tech/building-an-app-portfolio-to-60k-mo-after-apple-froze-his-developer-account-LD7oNYzKSmWucRfKV1AO).

**3D / Gaussian splatting pricing example**
- Scantic (on-device Gaussian splats): free base app with standard export. High-quality exports cost €4.99 per scan or €29.99/year. It works fully offline with no account, and processing takes "a couple of minutes". Requires iOS 17+ and an A12 chip or later. SPZ export is "planned" — [Digital Production, 2026-08-20](https://digitalproduction.com/2026/08/20/gaussian-splats-on-the-iphone/).

### Inferences
- The proven formula is **one killer camera moment → instant result → paywall → creator/UGC distribution**. Cal AI and Umax are both "scan yourself or your stuff → score or number" apps. None of the big winners was offline. Offline and on-device is a *cost and privacy advantage* (no per-scan API bill, which suits low-ARPU markets like Vietnam), not a growth engine in itself.
- For a solo Vietnamese developer, portfolio or niche plays are more realistic ($1K–$20K MRR range) than Cal AI-scale outcomes. The base rates above argue for choosing niches with **high intent search keywords** (ASO) plus a cheap content channel (TikTok demos of a satisfying scan).
- Hybrid pricing (free core + per-project/per-scan IAP + annual) as used by Scantic fits "pro-sumer" sensor apps better than weekly subscriptions, and it answers the Polycam and magicplan complaints.
- Face-rating ("looksmaxxing") revenue is real, but it carries reputational and review risk (mental-health criticism). Not recommended for a developer who wants a durable brand.

### Gaps
- No disclosed revenue was found for any indie LiDAR app (3D Scanner App, LiDAR Scanner 3D, RoomScan Pro, SiteScape). The category's size is unknown from public sources.
- No 2025–2026 case study was found of a paid, *offline-only* app with disclosed revenue above $10K MRR. Genius Scan is the closest, and its revenue is not disclosed.
- The primary RevenueCat 2025/2026 report was not fetched. The base-rate stats come from secondary blogs.

---

## Key Question 3 — Emerging 2025–2026 trends and the enabling on-device tech

### Takeaway
Two platform shifts make "offline AI" apps practical in 2026. The first is Apple's free on-device ~3B-parameter LLM (Foundation Models framework, iOS 26). The second is broader Vision OCR (structured document recognition in iOS 26, with Vietnamese among Live Text languages). Apple Intelligence also added Vietnamese in iOS 26.1. The fastest-moving capture trend is on-device Gaussian splatting, but that niche filled up quickly in 2026. Accessibility (LiDAR obstacle detection), pet health, notes-to-flashcards, AI voice notes and home inventory are all active. Most of them are served by cloud-dependent or free apps.

### Cited Findings
**Platform / tech**
- Foundation Models framework (iOS 26) gives direct Swift access to Apple's on-device ~3B-parameter LLM: "No API keys. No cloud costs. No internet required." It covers generation, summarization, classification, semantic search and a tool-calling protocol. It requires Apple Intelligence hardware (iPhone 15 Pro and newer, M-series iPads/Macs) — [DEV Community](https://dev.to/arshtechpro/apples-foundation-models-framework-run-ai-on-device-with-just-a-few-lines-of-swift-lbp); [AppCoda](https://www.appcoda.com/foundation-models/); [Blake Crosley, Tool protocol](https://blakecrosley.com/blog/foundation-models-on-device-llm).
- At WWDC26 (June 2026), Apple presented "Bring an LLM provider to the Foundation Models framework". One secondary summary says Anthropic and Google will ship Swift packages that plug Claude and Gemini into the same API — [Apple Developer WWDC26 session 339](https://developer.apple.com/videos/play/wwdc2026/339/) (session title confirmed; details only from a search summary).
- Apple Intelligence gained Vietnamese (plus Danish, Dutch, Norwegian, Portuguese (Portugal), Swedish, Turkish and Traditional Chinese) in iOS 26.1 — [9to5Mac, 2025-11-11](https://9to5mac.com/2025/11/11/ios-26-1-brings-apple-intelligence-to-these-eight-new-languages/); [MacRumors, 2025-09-22](https://www.macrumors.com/2025/09/22/ios-26-1-apple-intelligence-languages/); [Vietnam.vn](https://www.vietnam.vn/en/cap-nhat-ios-26-1-de-su-dung-apple-intelligence-tieng-viet).
- Live Text supports 24 languages across 46 locale combinations, **including Vietnamese**, per Apple's iOS 26 feature-availability page (checked Aug 9, 2026) — [Textora, "Every Language Apple's Live Text Can Read"](https://textora.app/blog/live-text-supported-languages/).
- The iOS 26 Vision `RecognizeDocumentsRequest` recognizes text in 26 languages and returns structure: paragraphs, tables and lists, embedded QR/barcodes, emails, phone numbers and URLs — [WWDC25 "Read documents using the Vision framework"](https://developer.apple.com/videos/play/wwdc2025/272/); [Apple docs](https://developer.apple.com/documentation/vision/recognizedocumentsrequest).

**Market-level AI app trends**
- AI apps grew gross monthly revenue 37x in two years. Consumer spend passed $1.4B in 2024 and was projected above $2B in 2025. AI voice-recorder apps made only $24M but grew 2,270% in 2024 — [Appfigures, "Rise of AI Apps: Trends Shaping 2025"](https://land.appfigures.com/rise-of-ai-apps-report-2025); [Appfigures PDF](https://resources-cdn.appfigures.com/industry-reports/appfigures-report-rise-of-ai-apps-key-trends-shaping-2025.pdf).
- An Analysis Group study (published June 2026) says the App Store ecosystem facilitated $1.4T in 2025, and AI-integrated apps grew revenue about 4x faster than other apps — [Báo Pháp luật VN via Baomoi, June 2026](https://baomoi.com/app-store-dat-doanh-thu-1-400-ty-usd-nam-2025-ung-dung-ai-dan-dat-da-tang-truong-c55328013.epi).

**Gaussian splatting / 3D capture**
- As of early 2026, four mature mobile capture-to-splat apps existed, all cloud-processed freemium: Scaniverse (Niantic, free), Polycam, KIRI Engine and Luma AI — [Polyvia3D guide](https://www.polyvia3d.com/guides/gaussian-splatting-mobile-capture).
- 2026 brought a wave of on-device and LiDAR-assisted splat apps: SplatCam (LiDAR poses and point cloud), Scantic (fully on-device), Gaussian SplatKing (free on-device capture), GaussianCapture, Voxelio (trains small scenes on iPhone) and MetalSplatter (viewer) — [SplatCam, App Store](https://apps.apple.com/us/app/splatcam-lidar-capture/id6759800588); [RadianceFields: SplatKing](https://radiancefields.com/splatking); [GaussianCapture, App Store](https://apps.apple.com/us/app/gaussiancapture/id6765473250); [Voxelio](https://www.voxelio.app/modes/gaussian-splatting-capture); [Digital Production, 2026-08-20](https://digitalproduction.com/2026/08/20/gaussian-splats-on-the-iphone/).
- Limitation: splats are not polygon meshes. Production pipelines still need topology, UVs or rigging, and users lack desktop-level reconstruction controls — [Digital Production, 2026-08-20](https://digitalproduction.com/2026/08/20/gaussian-splats-on-the-iphone/).
- LiDAR app categories now include general 3D toolkits, floor plan tools, AEC point-cloud capture and scan-to-CAD. Established apps include 3D Scanner App, LiDAR Scanner 3D (Marek Simonik, exports USDZ/OBJ/STL/PLY/DXF/LAS), SiteScape, Dot3D and RoomScan Pro — [Scanbrix, 2026](https://www.scanbrix.com/blog/best-iphone-lidar-scanner-apps-2026); [KIRI Engine blog, 2026](https://www.kiriengine.app/blog/best-lidar-3d-scanner-apps-iphone-2026); [LiDAR Scanner 3D, App Store](https://apps.apple.com/us/app/lidar-scanner-3d/id1504307090).

**Accessibility**
- EyeGuide (launched Oct 2025) is a free app that uses iPhone LiDAR for obstacle and collision detection, human presence sensing and voice/haptic feedback, and it works in darkness — [TechCabal, 2025-10-24](https://techcabal.com/2025/10/24/eyeguide-uses-lidar-to-help-blind-people-navigate-public-spaces/). GuideDog Nav detects obstacles, walls and stairs with LiDAR, camera and AI, and gives distance announcements on non-LiDAR iPhones too — [App Store](https://apps.apple.com/us/app/guidedog-nav/id6761731954). Super Lidar is free and comes from an MIT spinoff — [AppleVis](https://www.applevis.com/apps/ios/productivity/super-lidar-lidar-blind). Mobilio is a Harvard research app — [Harvard SEAS](https://seas.harvard.edu/news/smartphone-navigation-app-people-blindness-and-low-vision).
- HelpUSee markets scene description "completely offline", with all processing on-device — [AppleVis](https://www.applevis.com/apps/ios/utilities/helpusee-you-are-my-eyes).

**Pet health**
- CatsMe (Carelogy, Japan) uses the Feline Grimace Scale on cat face photos and adds a litter, stool, weight and food log. Its Android listing shows about 18K downloads, with about 250 in the last 30 days — [App Store](https://apps.apple.com/us/app/catsme-ai-health-for-cats/id6478842291); [AppBrain](https://www.appbrain.com/app/catsme-ai-cat-pain-detector/com.carelogy_japan.cpd.twa). New entrants in 2025–2026 include Cat Pain Check AI (5 face indicators, 5 free scans), VetPati (photo symptoms) and Pet Check AI — [Cat Pain Check AI](https://apps.apple.com/us/app/cat-pain-check-ai/id6758533689); [VetPati](https://apps.apple.com/us/app/vetpati-dog-cat-ai-health/id6760646762); [Pet Check AI](https://petcheckai.com/).

**Education (notes → flashcards)**
- Flashka claims 1.5M+ students and turns handwritten notes, PDFs and photos into flashcards. Kahoot lets students scan handwritten notes with the phone camera. Quizlet launched LLM "Course-Powered" study guides in 2025 — [Flashka, App Store](https://apps.apple.com/us/app/flashka-ai-flashcards-maker/id6748599950); [Kahoot notes-to-flashcards](https://kahoot.com/kahoot-study/notes-to-flashcards/); [Quizlet, Wikipedia](https://en.wikipedia.org/wiki/Quizlet).

**Receipts / expenses**
- Smart Receipts is described as "the only open-source, offline-first" receipt option, with unlimited storage and CSV export free. Wave allows offline receipt capture that uploads later. Genius Scan does on-device OCR — [Tailride, 2026](https://tailride.so/blog/best-free-receipt-scanner-app); [Foreceipt, 2026](https://foreceipt.com/blogs/best-receipt-scanner-apps-for-2026-compare-pricing-ocr-accuracy-and-irs-cra-recordkeeping/); [Expensesorted blog](https://www.expensesorted.com/blog/120_best_receipt_scanner_apps_without_subscription_free_alternatives_that_protect_your_privacy) (competitor blogs).

**Home inventory**
- Sortly (a business inventory tool adapted for home, with QR labels) and Encircle (free consumer app retired Dec 2025) were the leaders. New 2025–2026 entrants include HomeProof, Vorby, Scanlily, Kept, Re_Tera and Real Estate Ledger — [ValuePenguin](https://www.valuepenguin.com/homeowners-insurance-inventory-checklist); [HomeProof 2026](https://homeproofvault.com/blog/best-home-inventory-apps-compared/); [Kept](https://getkeptapp.com/blog/home-inventory-app/); [Scanlily](https://www.scanlily.com/en/blog/scanlily_alternative_to_encircle). No LiDAR-specific consumer home-inventory feature was found in the results.

### Inferences
- The Foundation Models framework removes the per-call API cost that made Cal AI-style apps expensive to run. That makes **low-price or one-time-purchase AI features viable** for the first time, especially in low-ARPU markets. The catch is device coverage: it needs an iPhone 15 Pro or newer, so it should be treated as an enhancement with a Vision/Core ML fallback.
- Because Vietnamese is now supported by both Live Text/Vision OCR and Apple Intelligence (iOS 26.1), a Vietnamese developer can build **Vietnamese document understanding fully on-device**: OCR, then LLM field extraction and summarization. Global incumbents are unlikely to specialize in this.
- Gaussian splatting went from gap to crowded within about 8 months of 2026. The remaining opportunity is **vertical output** (listing tours, heritage, 3D-print-ready meshes), not another general capture app.
- Accessibility apps show clear demand for privacy (on-device), but the LiDAR navigation incumbents are free, often academic or NGO projects. It is an impact niche with weak direct monetization.
- Pet-health camera apps are early, and demand is unproven (CatsMe has only about 250 Android installs per month).

### Gaps
- It could not be confirmed whether Apple Vision's **handwriting** recognition supports Vietnamese. Apple's handwriting-language list was not retrieved, and this is critical for any Vietnamese handwriting-notes idea.
- Foundation Models' language support was not confirmed from Apple docs, specifically whether the on-device model handles Vietnamese well when called from third-party apps. It is only inferred from Apple Intelligence's Vietnamese support.
- No search-interest data (Google Trends, Exploding Topics) was retrieved for "gaussian splatting app", "LiDAR scanner" or "pet pain app".
- No data was found on market size for pill-identification or skin-analysis apps. These were not researched deeply because of medical-claim review risk.

---

## Key Question 4 — Vietnam/SEA-specific opportunities, how Vietnamese users pay, and global-first strategy

### Takeaway
Vietnam has concrete, date-driven document pain points. The biggest is that household businesses (hộ kinh doanh) must move from lump-sum tax (thuế khoán) to self-declaration from **Jan 1, 2026**, which requires invoices, bank-flow records and bookkeeping. Others are CCCD/ID handling and fake bank-transfer "bills". On-device Vietnamese OCR plus an LLM is now technically feasible. iPhone is a minority of Vietnamese smartphone sales, prices start at 25,000 VND, and SEA monetization leans toward ads. So the best strategy is a **global-first app with a Vietnamese vertical**, or a VN-only B2C/SMB tool with low one-time or annual pricing and near-zero server cost.

### Cited Findings
**Regulatory / demand drivers**
- Lump-sum tax (thuế khoán) for household businesses ends Jan 1, 2026. Households move to self-declaration based on e-invoices, eTax Mobile and bank cash-flow data. Households expecting revenue above 1 billion VND should register for e-invoices. Decree 141/2026/NĐ-CP abolished per-transaction e-invoice issuance by tax offices. Households with revenue of 500M VND or more in 2026 (the taxable threshold) must set up accounting books. The tax authority says the early phase focuses on support rather than penalties — [VietnamNet](https://vietnamnet.vn/bo-thue-khoan-sang-ke-khai-7-viec-ho-kinh-doanh-can-lam-truoc-1-1-2026-2473487.html); [Tuổi Trẻ/NLĐ, Feb 2026](https://tuoitre.vn/nld/buoc-ngoat-bo-thue-khoan-voi-ho-kinh-doanh-mo-loi-len-doi-doanh-nghiep-196260216225448722.htm); [einvoice.vn](https://einvoice.vn/tin-tuc/hkd-chuyen-sang-ke-khai-thue-tu-nam-2026); [Kế toán Việt Hưng, "Ghi sổ TT 152"](https://ketoanviethung.vn/ke-toan-ho-kinh-doanh-2026.html).
- Fake bank-transfer screenshots ("bill chuyển khoản giả") are a widespread scam against sellers. Police and press advise that the only reliable check is confirming the credit in the seller's own account — [Nhân Dân special report](https://nhandan.vn/special/gia-mao-bien-lai-chuyen-tien-thanh-cong/index.html); [Cảnh sát QLHC về TTXH](https://canhsatquanlyhanhchinh.gov.vn/tin-tuc/canh-giac-lua-dao-gia-mao-bien-lai-chuyen-tien-thanh-cong-2649); [Tuổi Trẻ/NLĐ, 2025-08-16](https://tuoitre.vn/nld/chu-cua-hang-tai-tp-hcm-ngo-ngang-vi-khong-ngo-bi-lua-boi-thu-doan-nay-19625081611544839.htm); [Báo Đắk Lắk, Mar 2026](https://baodaklak.vn/van-hoa-xa-hoi/phap-luat/202603/bill-chuyen-khoan-gia-nan-nhan-that-a1e16da/).

**CCCD / ID**
- Reading the CCCD chip over NFC on iPhone (iPhone X or later, SE 2/3) is done through the government VNeID app. Zalo can scan the CCCD QR code — [Thegioididong](https://www.thegioididong.com/hoi-dap/cach-quet-nfc-cccd-tren-iphone-1591248); [CellphoneS](https://cellphones.com.vn/sforum/cach-quet-ma-qr-cccd).
- An indie app already exists: "Quét CCCD, pass Wifi, OCR" (developer Nguyen Pham Tuan Hoang) scans CCCD, copies the data, and keeps a searchable history by ID number or name — [App Store VN](https://apps.apple.com/vn/app/qu%C3%A9t-cccd-pass-wifi-ocr/id6476883015).

**Vietnamese OCR requirements and incumbents**
- A Vietnamese OCR buyer's guide says OCR must handle diacritics and legacy encodings (Unicode, VNI, TCVN3), printed and handwritten text, >95% accuracy on clean print and 85–90% on invoices, IDs and contracts. Named tools include FPT.AI Reader (enterprise) — [Lạc Việt, 2026](https://lacviet.vn/en/phan-mem-ocr/); [FPT Shop](https://fptshop.com.vn/tin-tuc/thu-thuat/nhung-ung-dung-giup-bien-chu-viet-tay-anh-thanh-van-ban-53210). VietOCR offers Vietnamese and handwriting OCR on the web — [vocr.vn](https://vocr.vn/). Google Lens and OneNote are the common consumer fallbacks — [FPT Shop](https://fptshop.com.vn/tin-tuc/thu-thuat/nhung-ung-dung-giup-bien-chu-viet-tay-anh-thanh-van-ban-53210).
- Apple Live Text/Vision supports Vietnamese (iOS 26 list), and Apple Intelligence supports Vietnamese from iOS 26.1 — [Textora](https://textora.app/blog/live-text-supported-languages/); [9to5Mac, 2025-11-11](https://9to5mac.com/2025/11/11/ios-26-1-brings-apple-intelligence-to-these-eight-new-languages/).

**iPhone share and pricing in Vietnam**
- Q1 2025 Vietnam smartphone shipment share: Samsung 28%, Xiaomi 19%, Apple 18%, Oppo 17%, Realme 6%. Apple's sales grew about 37% in Q1 and it had 20% share for full-year 2024 — [VnExpress](https://vnexpress.net/iphone-la-dong-luc-chinh-giup-thi-truong-smartphone-tang-truong-4932838.html); [Bạch Long Mobile](https://bachlongmobile.com/news/tin-cong-nghe/doanh-so-iphone-tang-vot-37-tai-viet-nam/). **Conflict:** another search summary claimed "about 39% iPhone share by mid-2025". Its source was unclear and it may refer to installed base or value, so it was not verified. About 2 million iPhones are sold per year in Vietnam — [Znews](https://znews.vn/ly-do-apple-danh-gia-cao-thi-truong-viet-nam-post1559082.html).
- App Store Vietnam price tiers start at 25,000 VND (tier 1), then 49,000 and 79,000 VND. There are 87 levels, introduced when Apple began collecting VAT and corporate income tax in Vietnam — [Vietnam Insider](https://vietnaminsiders.com/apple-to-raise-all-apps-price-in-vietnam/) (older article, likely 2021–22). Apple's later global pricing update allows much finer price points (e.g., lowest supported prices of $0.10–$0.29 equivalent) and per-storefront localization — [Apple Newsroom PDF, App Store Pricing Update](https://www.apple.com/newsroom/pdfs/App-Store-Pricing-Update.pdf); [Apple Developer News](https://developer.apple.com/news/?id=e1b1hcmv).
- In SEA, IAP revenue ranked 7th globally at $625M in Q1 2025 (games). In developing countries most mobile-game revenue comes from ads rather than IAP. Vietnam had 329M game downloads in Q1 2025 — [Sensor Tower SEA 2025](https://sensortower.com/blog/southeast-asia-mobile-gaming-2025). Sensor Tower (via e27, Oct 2025) reports that non-gaming apps have become SEA's leading revenue genre — [e27](https://e27.co/sensortower-non-gaming-mobile-apps-have-taken-over-sea-as-revenue-generating-genre-20251029/) (headline only).
- Vietnamese indie game studios: GenK notes most indie titles never recoup their development cost — [GenK, 2025-05-31](https://genk.vn/gap-go-nhung-studio-game-indie-viet-nam-dang-chinh-phuc-app-store-20250531181821936.chn).

### Inferences
- **Hộ kinh doanh bookkeeping (2026) is the strongest Vietnam-specific, time-bound demand signal found.** Millions of small shops suddenly need to capture paper receipts, supplier invoices and bank flows, and many owners are older and phone-first. An offline Vietnamese OCR ledger that exports to the required book formats could sell as a one-time or annual purchase (e.g., 199K–499K VND/year). The market size in households and their iPhone share is an inference and was not quantified.
- An app that claims to "detect fake transfer bills" from a screenshot is **not recommended**. Forensics on screenshots is unreliable and could give false reassurance, and authorities say to check the actual account. A safer adjacent feature is order/payment reconciliation *checklists*.
- Because iPhone is a minority of Vietnamese sales and SEA spend leans to ads, a Vietnamese developer should **build global-first** (English UI, USD pricing, TikTok/Reels creators in the US and EU) and **add Vietnamese as a localized vertical**, rather than depending on Vietnam revenue. Local pricing should use Apple's per-storefront tiers (25K–79K VND for one-time unlocks) because on-device processing costs nothing per user.
- CCCD scanning is already partly served (VNeID for chip reading, Zalo for QR, one indie OCR app). A standalone CCCD scanner is thin and likely to hit Guideline 4.3. It is better as a feature inside a broader "family documents" or "guest check-in" product. Handling ID data also raises personal-data-protection obligations (see Gaps).

### Gaps
- No verified ARPU or conversion data specific to Vietnamese App Store users was found, and no Vietnam-specific IAP revenue totals for non-game apps.
- Vietnam's personal-data rules (Decree 13/2023/NĐ-CP and the 2025 Personal Data Protection Law) and how they apply to apps storing CCCD images locally were not researched in this session. A legal review is needed before building ID or guest-register features.
- No evidence was found on how many homestays or mini-hotels use phones for guest registration (khai báo lưu trú). The guest check-in idea is inference only.
- Vietnamese tech press (Tinhte, GenK, VnExpress Số hóa) coverage of user complaints about Vietnamese OCR or scanner apps was not found.

---

## Key Question 5 — Which categories are saturated (Guideline 4.3 spam risk) and should be avoided or differentiated?

### Takeaway
Apple tightened Guideline 4.3 in June 2026. It now explicitly allows removal of apps in oversaturated categories that aren't updated or don't attract users. Generic QR scanners, "offline OCR" utilities, generic document scanners, Cal AI clones, coin/plant identifiers and general LiDAR "3D scanner" apps are crowded with look-alikes. A new app needs a clearly different vertical, workflow or output.

### Cited Findings
- June 9, 2026 guideline update: dating, flashlight, sound effects, wallpaper, simple timers and fortune-telling apps will be rejected unless they offer "a meaningfully different or improved experience". Apps in oversaturated categories "may be removed from the App Store going forward if they are not updated, improved, or do not attract customers". Fart, burp, Kama Sutra and drinking-game apps are called "mediocre, low-quality, or low-effort", and repeated submissions can lead to removal from the Developer Program — [MacRumors, 2026-06-09](https://www.macrumors.com/2026/06/09/app-store-guidelines-low-quality-apps/).
- Developer-side guides list categories that often get 4.3(b) rejections: simple games, calculators and converters, flashlights, **QR code scanners**, basic to-do lists "and other utilities where the App Store already has hundreds of near-identical entries". Reviewers report seeing "hundreds of similar submissions per week through 2025 and into 2026" — [ezscreenshots blog](https://ezscreenshots.com/blog/design-spam-rejection-4-3b); [App Store Launch Club](https://www.applaunchclub.co/blog/app-store-rejection-guideline-4-3); [PTKD Journal on AI apps and 4.3](https://ptkd.com/journal/rejection-guideline-4-3-ai-spam) (secondary).
- Evidence of clone density in AI calorie apps: an App Store search returns many look-alikes (Snap food, Cal Tracker – Calorie AI, Fit AI, Calorica AI, Dr. Cal AI, CalApp, AI Calorie…), and MyFitnessPal says it tracks about 70 competitors — [App Store listings via search](https://apps.apple.com/us/app/calapp-ai-calorie-tracker/id6621263391); [TechCrunch, 2026-03-02](https://techcrunch.com/2026/03/02/myfitnesspal-has-acquired-cal-ai-the-viral-calorie-app-built-by-teens/).
- Evidence of density in document scanners: App Store search returns many generic "PDF Scanner / Scan & OCR / Clear Scan" apps, often with weekly plans — [e.g., Smart Scanner](https://apps.apple.com/us/app/id6744928240); [Camera Scanner: Clear Scan](https://apps.apple.com/us/app/id1493265495); [WildandFree Tools 2026](https://wildandfreetools.com/blog/best-document-scanner-app-reddit-2026/). Offline OCR utilities: [Off Lens](https://apps.apple.com/us/app/off-lens/id6755901773), [Offline OCR Scanner](https://apps.apple.com/us/app/offline-ocr-scanner/id6757244979), [OnDevice OCR Pro](https://apps.apple.com/us/app/ondevice-ocr-pro/id6756887557?mt=12), [IND Text Scanner](https://apps.apple.com/us/app/ind-text-scanner-offline-ocr/id1448584617).
- Generic LiDAR scanners: 3D LiDAR Scanner, LiDAR Scanner 3D, 3D Scanner App, Vision Capture AR ($9.99), 3D Modeling Lidar Scanner, and others — [App Store: 3D LiDAR Scanner](https://apps.apple.com/us/app/3d-lidar-scanner/id1642329012); [Vision Capture AR](https://apps.apple.com/dz/app/id6739468754); [KIRI 2026 list](https://www.kiriengine.app/blog/best-lidar-3d-scanner-apps-iphone-2026).
- Coin identifiers: at least CoinSnap, Coin ID, Coinoscope, Coin Identifier: Snap & Value and CoinHix — [Emory Wheel, 2025-12-27](https://emorywheel.com/article/top-10-free-coin-identifier-and-value-apps-20251227); [Finance Monthly](https://www.finance-monthly.com/9-free-coin-identifier-and-value-apps/).
- AI companion apps: 337 revenue-generating apps, 128 of them released in H1 2025 alone — [TechCrunch, 2025-08-12](https://techcrunch.com/2025/08/12/ai-companion-apps-on-track-to-pull-in-120m-in-2025/) (off-scope, but a saturation signal).
- Face rating: Umax-style apps face psychologist criticism over teen mental health — [Fortune, 2024-07-01](https://fortune.com/2024/07/01/looksmaxxing-apps-rate-teen-boys-faces-mental-health/).

### Inferences
- **Avoid or only enter with strong differentiation:** QR scanners, generic PDF scanners and "offline OCR", flashlight/measure/level tools (Apple ships Measure), generic "AI calorie from photo", generic plant/coin/rock/bug identifiers, generic LiDAR "3D scanner", generic Gaussian-splat capture, face rating, and white-label AI chat wrappers.
- **How to differentiate so App Review sees a "meaningfully different experience":** (a) a named vertical workflow (e.g., "Vietnamese household-business receipts → tax book export"), (b) a unique output (e.g., watertight STL scaled by LiDAR, insurance-claim PDF), (c) language or regional specialization, and (d) no template reuse across multiple near-identical apps from the same account, because portfolio "reskins" are the classic 4.3 trigger.

### Gaps
- Apple's exact revised 4.3 text was seen only through MacRumors. The primary guideline page was not fetched.
- No data was found on 4.3 rejection rates by category.

---

## Key Question 6 — Shortlist: 20 concrete app opportunities combining demand evidence with weak or complacent competition

### Takeaway
The best fits for a Vietnamese solo developer (tier A) are sensor-plus-on-device-AI tools that solve a *specific document or measurement workflow*. Several are Vietnam-specific but built to work globally too. They are, in order: Vietnamese household-business receipt ledger, family document vault, scan-to-3D-print with free exports, LiDAR home-inventory/rental condition report, offline Vietnamese voice notes, and an English pronunciation coach for Vietnamese speakers. Trend-driven ideas such as Gaussian splats, calorie AI and identifiers are tier B/C because they are crowded.

### Cited Findings
(All evidence for the cards below is cited inline and repeats sources from Q1–Q5.)
- Tax regime change for household businesses on 2026-01-01 — [VietnamNet](https://vietnamnet.vn/bo-thue-khoan-sang-ke-khai-7-viec-ho-kinh-doanh-can-lam-truoc-1-1-2026-2473487.html)
- Vietnamese supported in Live Text/Vision and Apple Intelligence — [Textora](https://textora.app/blog/live-text-supported-languages/); [9to5Mac](https://9to5mac.com/2025/11/11/ios-26-1-brings-apple-intelligence-to-these-eight-new-languages/)
- Polycam export paywall — [SkyeBrowse](https://www.skyebrowse.com/news/posts/polycam-review); magicplan lock-out — [App Store reviews](https://apps.apple.com/us/app/magicplan/id427424432?see-all=reviews)
- Encircle retired free consumer app (Dec 2025) — [Re_Tera](https://getretera.com/encircle-alternative)
- Cal AI $30M+/yr [company-reported], about 70 competitors — [TechCrunch 2026-03-02](https://techcrunch.com/2026/03/02/myfitnesspal-has-acquired-cal-ai-the-viral-calorie-app-built-by-teens/)
- BoldVoice $500K+ MRR [self-reported]; PDF.AI $50K+ MRR [self-reported] — [Consumer Startups](https://consumerstartups.substack.com/p/lightweight-ai-consumer-utility-apps)
- AI voice recorder apps grew 2,270% in 2024 — [Appfigures](https://land.appfigures.com/rise-of-ai-apps-report-2025)

### Inferences
Each card lists: **Target user · Core sensor/tech · Evidence of demand · Competitor weaknesses · Monetization · Risk/notes.** Demand evidence is cited. Everything else is analyst inference.

#### Tier A — strongest fit (demand evidence + clear wedge + feasible for a solo developer)

**1. "Sổ thu chi" — offline receipt and invoice ledger for Vietnamese household businesses (hộ kinh doanh), with a global freelancer mode**
- Target: owners of VN household businesses and small shops moving off thuế khoán in 2026. Globally, freelancers and sole traders doing taxes.
- Tech: VisionKit document camera + `RecognizeDocumentsRequest` (tables, QR on e-invoices) + Vietnamese OCR + Foundation Models to extract vendor, amount, VAT and date; Core Data/SwiftData; export to Excel/PDF in book formats.
- Demand evidence: lump-sum tax abolished from 2026-01-01, with mandatory declaration based on e-invoices and bank data, and books required at ≥500M VND revenue — [VietnamNet](https://vietnamnet.vn/bo-thue-khoan-sang-ke-khai-7-viec-ho-kinh-doanh-can-lam-truoc-1-1-2026-2473487.html); [Tuổi Trẻ/NLĐ](https://tuoitre.vn/nld/buoc-ngoat-bo-thue-khoan-voi-ho-kinh-doanh-mo-loi-len-doi-doanh-nghiep-196260216225448722.htm). Globally, privacy/offline receipt apps are a recognized niche (Smart Receipts, Genius Scan) — [Tailride 2026](https://tailride.so/blog/best-free-receipt-scanner-app).
- Competitor weaknesses: VN e-invoice and accounting vendors (einvoice.vn, EasyInvoice, FAST) are web/B2B oriented and not photo-first — [einvoice.vn](https://einvoice.vn/tin-tuc/hkd-chuyen-sang-ke-khai-thue-tu-nam-2026); [FAST](https://fast.com.vn/bo-thue-khoan-tu-1-1-2026-ho-kinh-doanh-can-chuan-bi-gi-de-chuyen-sang-ke-khai-thue-thuan-loi/) (inference from their positioning). Global receipt apps are cloud-first or subscription-heavy.
- Monetization: freemium with an annual plan (e.g., 199K–499K VND; USD $19–39 globally) or a one-time "Pro" unlock. Zero server cost.
- Risk: accounting and tax correctness. Needs an accountant's review of export templates, and the iPhone share among household-business owners is unknown.

**2. "Hồ sơ gia đình" — offline family document vault with smart Vietnamese field extraction and expiry reminders**
- Target: Vietnamese families (and overseas Vietnamese) managing CCCD, driver licences, vehicle registration and inspection (đăng kiểm), health-insurance cards, land titles, birth certificates, school records, warranties. Globally, "family paperwork vault".
- Tech: VisionKit scan, Vietnamese OCR, Foundation Models extraction, Face ID-locked encrypted local store, CCCD QR parsing, reminders.
- Demand evidence: widespread CamScanner distrust and the "use Notes instead" sentiment — [WildandFree Tools 2026](https://wildandfreetools.com/blog/best-document-scanner-app-reddit-2026/); an existing VN indie CCCD scanner shows local demand — [App Store VN](https://apps.apple.com/vn/app/qu%C3%A9t-cccd-pass-wifi-ocr/id6476883015); Vietnamese OCR is now available on-device — [Textora](https://textora.app/blog/live-text-supported-languages/).
- Competitor weaknesses: generic scanners don't understand Vietnamese document types or expiry dates, many use weekly subscriptions and watermarks, and they upload to the cloud.
- Monetization: a one-time unlock (49K–99K VND in VN, $4.99–9.99 globally) plus optional encrypted iCloud sync.
- Risk: 4.3 (it's a "scanner"), so the vertical workflow must be obvious in screenshots. Personal-data law compliance for stored IDs is not researched.

**3. "Scan-to-Print" — LiDAR/photogrammetry object capture producing watertight, correctly scaled STL/3MF with free export**
- Target: 3D-printing hobbyists, makers, cosplay and replacement-part makers.
- Tech: Apple Object Capture (on-device photogrammetry) + LiDAR/depth for scale, mesh repair (hole filling, flat base), on-device processing.
- Demand evidence: Polycam paywalls STL/OBJ exports, and users complain about a price more than doubling and €300 per project for students — [SkyeBrowse](https://www.skyebrowse.com/news/posts/polycam-review); [Trustpilot](https://www.trustpilot.com/review/poly.cam). LiDAR scan-to-CAD is a recognized category — [Scanbrix 2026](https://www.scanbrix.com/blog/best-iphone-lidar-scanner-apps-2026).
- Competitor weaknesses: generic 3D scanners output meshes that aren't print-ready, and export-format paywalls push users away.
- Monetization: free export of standard quality, with a one-time $14.99–29.99 Pro (print repair, 3MF, measurement) or per-scan IAP (the Scantic model: €4.99 per scan / €29.99 per year — [Digital Production](https://digitalproduction.com/2026/08/20/gaussian-splats-on-the-iphone/)).
- Risk: Object Capture quality on iPhone varies. Positioning must show "print-ready" as the differentiator, not "3D scanner".

**4. LiDAR home inventory and rental condition report (insurance, moving, deposits)**
- Target: US/EU/AU homeowners and renters (insurance claims), landlords and Airbnb/homestay hosts doing move-in/move-out reports.
- Tech: RoomPlan (LiDAR) room outline + object photos + OCR of receipts and serial numbers + on-device categorization + claim-ready PDF.
- Demand evidence: Encircle retired its free consumer app on Dec 17, 2025, and a wave of 2026 alternatives followed — [Re_Tera](https://getretera.com/encircle-alternative); [HomeProof 2026](https://homeproofvault.com/blog/best-home-inventory-apps-compared/). Insurers advise keeping inventories — [ValuePenguin](https://www.valuepenguin.com/homeowners-insurance-inventory-checklist).
- Competitor weaknesses: Sortly is business-oriented, and no consumer app in the results uses LiDAR room capture. Most competitors are cloud accounts.
- Monetization: a one-time unlock plus an annual plan for multiple properties or landlord mode.
- Risk: the category is filling in 2026 (many new blogs and apps). LiDAR is only on Pro iPhones, so a non-LiDAR photo fallback is needed.

**5. Offline Vietnamese voice notes, meeting recorder and summarizer**
- Target: Vietnamese students, office workers, journalists, doctors; privacy-sensitive professionals.
- Tech: microphone + on-device speech recognition + Foundation Models summarization (Apple Intelligence Vietnamese, iOS 26.1+).
- Demand evidence: AI voice-recorder apps grew 2,270% in 2024 — [Appfigures](https://land.appfigures.com/rise-of-ai-apps-report-2025). Vietnamese Apple Intelligence support shipped Nov 2025 — [9to5Mac](https://9to5mac.com/2025/11/11/ios-26-1-brings-apple-intelligence-to-these-eight-new-languages/).
- Competitor weaknesses: the leading AI note-takers are cloud-based and English-first (inference; no Vietnamese-accuracy comparison found).
- Monetization: annual subscription at a VN-localized price. Offline removes transcription API costs.
- Risk: on-device Vietnamese speech-recognition quality is unverified (gap). Voice notes are crowded in English, so the differentiation is Vietnamese plus offline.

**6. English pronunciation and accent coach for Vietnamese (and SEA) speakers**
- Target: Vietnamese learners (IELTS candidates, workers heading to Australia, Japan or Korea).
- Tech: microphone + on-device phoneme/pronunciation scoring (Core ML model), targeting Vietnamese-specific errors such as final consonants and word stress (inference).
- Demand evidence: BoldVoice at $500K+ MRR **[self-reported]** shows willingness to pay for accent training — [Consumer Startups](https://consumerstartups.substack.com/p/lightweight-ai-consumer-utility-apps).
- Competitor weaknesses: global accent apps are not tuned to Vietnamese L1 errors (inference).
- Monetization: annual subscription, localized pricing.
- Risk: needs a speech-scoring model, which is significant ML work. No VN-specific market data was found.

#### Tier B — real demand but crowded or harder to monetize; needs a sharp wedge

**7. Floor plans and quantity takeoff for Vietnamese contractors and interior designers**
- Target: VN renovation contractors, interior shops, painters and tilers. Globally, handymen.
- Tech: RoomPlan/LiDAR → m² of walls and floors, paint and tile estimates, DXF/PDF export, VN units and material presets.
- Demand evidence: magicplan users complain about subscription lock-out, 6–8 inch errors, and a free tier capped at 2 projects — [App Store reviews](https://apps.apple.com/us/app/magicplan/id427424432?see-all=reviews); [JustUseApp](https://justuseapp.com/en/app/427424432/magicplan/reviews).
- Weaknesses: no VN-localized estimator was found (inference).
- Monetization: pay per project, or a one-time unlock.
- Risk: LiDAR needs Pro iPhones. Accuracy liability.

**8. Construction punch-list and site-report with LiDAR measurements (global)**
- Target: small contractors and inspectors.
- Tech: photo + LiDAR distance annotations + offline PDF report.
- Evidence: pro apps (SiteScape, Dot3D) target point clouds, not simple reports — [Scanbrix 2026](https://www.scanbrix.com/blog/best-iphone-lidar-scanner-apps-2026). Direct demand data not found (gap).
- Monetization: annual per seat.

**9. Handwritten notes → flashcards/quizzes, offline (Vietnamese + English)**
- Target: high-school and university students.
- Tech: Vision OCR + Foundation Models question generation + spaced repetition.
- Evidence: Flashka claims 1.5M+ students, and Kahoot and Quizlet added the feature — [Flashka](https://apps.apple.com/us/app/flashka-ai-flashcards-maker/id6748599950); [Kahoot](https://kahoot.com/kahoot-study/notes-to-flashcards/).
- Weaknesses: cloud-based, and it is unknown whether any handles Vietnamese handwriting.
- Monetization: low annual price.
- Risk: **depends on Vietnamese handwriting OCR, which is unverified** (gap). Heavy competition in English.

**10. Vertical Gaussian-splat tours (homestays, small real estate, heritage sites)**
- Target: VN/SEA homestay owners, small agents, museums.
- Tech: on-device splat capture + web-viewer link/embed.
- Evidence: rapid 2026 growth of splat apps and the maturity of Scaniverse/Polycam/KIRI/Luma — [Polyvia3D](https://www.polyvia3d.com/guides/gaussian-splatting-mobile-capture); [Digital Production](https://digitalproduction.com/2026/08/20/gaussian-splats-on-the-iphone/).
- Weaknesses: general-purpose apps don't provide a listing or booking workflow (inference).
- Monetization: per-tour hosting fee. Note that this needs a server, which breaks "offline-only".
- Risk: crowded capture layer, and willingness to pay among homestays is unproven.

**11. Offline Vietnamese reader and scene describer for blind, low-vision and elderly users**
- Target: blind and low-vision Vietnamese users, and elderly parents reading bills and medicine labels.
- Tech: Vision OCR (Vietnamese) + AVSpeech Vietnamese TTS + Foundation Models description + LiDAR obstacle haptics.
- Evidence: AppleVis users want on-device processing — [AppleVis](https://www.applevis.com/forum/ios-ipados/through-ais-blind). LiDAR navigation apps exist but are free or academic — [TechCabal](https://techcabal.com/2025/10/24/eyeguide-uses-lidar-to-help-blind-people-navigate-public-spaces/).
- Weaknesses: Be My AI is cloud-based. No Vietnamese-first offline reader was found (inference).
- Monetization: weak. Free with a tip jar, "gift for parents" one-time purchase, grants/NGOs. Good for brand and Apple featuring (inference).

**12. Asian and Vietnamese cuisine photo calorie tracker with depth-based portions**
- Target: Vietnamese and SEA gym-goers, diaspora.
- Tech: Core ML food classifier for VN dishes + TrueDepth/LiDAR volume estimate + offline food DB.
- Evidence: Cal AI $30M+/yr **[company-reported]** — [TechCrunch 2026](https://techcrunch.com/2026/03/02/myfitnesspal-has-acquired-cal-ai-the-viral-calorie-app-built-by-teens/). Accuracy complaints stem from unknown weight and mixed dishes — [Clinical Nutrition Report](https://clinicalnutritionreport.com/articles/best-ai-calorie-tracker-reddit-2026/) (caution: affiliate risk).
- Weaknesses: incumbents use cloud LLMs and Western databases (inference).
- Monetization: subscription.
- Risk: about 70 competitors (MyFitnessPal), heavy clone density, high 4.3 risk. Needs a cuisine dataset.

**13. Private "chat with your documents" (on-device LLM) for professionals**
- Target: lawyers, doctors, accountants, students with confidential PDFs.
- Tech: PDFKit + Vision OCR + Foundation Models retrieval (tool calling).
- Evidence: PDF.AI $50K+ MRR **[self-reported]** (cloud) — [Consumer Startups](https://consumerstartups.substack.com/p/lightweight-ai-consumer-utility-apps). A free on-device LLM is available — [AppCoda](https://www.appcoda.com/foundation-models/).
- Weaknesses: cloud tools send documents off-device.
- Monetization: a one-time Pro unlock.
- Risk: the 3B model's context and quality limits, and Apple may bundle similar features.

**14. Niche identifier with an offline catalog and honest pricing (e.g., SEA/Vietnamese coins and banknotes, tropical plants and crop pests)**
- Evidence: CoinSnap about $400K/month and Coin ID about $100K/month **[Sensor Tower estimates]**; PictureThis about $5M/month on US iOS **[estimate]** — [Sensor Tower](https://app.sensortower.com/overview/com.coinidentifyer.ai?country=US); [Sensor Tower](https://app.sensortower.com/overview/1252497129?country=US). Accuracy complaints for regional plants — [Unstar 2026](https://unstar.app/blog/plant-identification-apps-ranked-picturethis-plantin-plantnet-2026).
- Weaknesses: deceptive trials and weekly subscriptions — [ComplaintsBoard](https://www.complaintsboard.com/picturethis-plant-identifier-b149857).
- Monetization: a one-time unlock or low annual price.
- Risk: very high clone density and 4.3 exposure. Regional niches may be small (and Vietnamese farmers skew to Android, which is an inference).

#### Tier C — speculative or high-risk; include only with caveats

**15. Pet health camera log (cat grimace scale, stool and body-condition photos)**
- Evidence: several 2025–2026 entrants, but CatsMe shows only about 250 Android installs per month — [AppBrain](https://www.appbrain.com/app/catsme-ai-cat-pain-detector/com.carelogy_japan.cpd.twa).
- Risk: veterinary-claim risk, and demand is unproven.

**16. Skin and skincare progress tracker (consistent-capture photos + on-device metrics, not "attractiveness scores")**
- Evidence: Umax $6M ARR **[self-reported]** shows willingness to pay for face analysis — [X, Apr 2024](https://x.com/8teAPi/status/1780278714573693110?lang=en). There is mental-health backlash against face ratings — [Fortune 2024](https://fortune.com/2024/07/01/looksmaxxing-apps-rate-teen-boys-faces-mental-health/).
- Risk: medical-claim review and ethics.

**17. Medication label and prescription (đơn thuốc) reader with reminders for elderly users and caregivers**
- Evidence: not researched (gap). The inference rests on the general accessibility demand above.
- Risk: health liability. Avoid pill *identification by appearance*.

**18. Offline camera translator for Vietnamese workers and students abroad (Korean, Japanese, Chinese documents ↔ Vietnamese)**
- Tech: Live Text supports vi/ja/ko/zh — [Textora](https://textora.app/blog/live-text-supported-languages/).
- Risk: strong free incumbents (Google Translate, Apple Translate). Differentiation would need a workflow such as a document glossary for labor contracts. No demand data was found (gap).

**19. Guest check-in register for homestays and mini-hotels (CCCD QR or passport → offline guest log/export)**
- Evidence: an indie CCCD scanner with history and search exists — [App Store VN](https://apps.apple.com/vn/app/qu%C3%A9t-cccd-pass-wifi-ocr/id6476883015). Homestay demand is unverified (gap).
- Risk: personal-data law, and it overlaps with idea 2.

**20. Motion-sensor apps (e.g., vibration or road-quality logger, rehab range-of-motion goniometer)**
- Evidence: none found in this session (gap). Listed only for completeness. Not recommended without validation.

#### Cross-cutting go-to-market notes (inference, grounded in Q2)
- Distribution: short-form demo videos of the "magic scan moment" via micro-creators (the Cal AI pattern) — [TechCrunch 2025](https://techcrunch.com/2025/03/16/photo-calorie-app-cal-ai-downloaded-over-a-million-times-was-built-by-two-teenagers/); [Starter Story](https://www.starterstory.com/cal-ai-breakdown). In Vietnam, TikTok and Facebook groups for household businesses, contractors and students (inference).
- Pricing: on-device means near-zero marginal cost, so a developer can undercut weekly-subscription incumbents with a one-time or annual price and still keep margin. Localize the VN price to the 25K/49K/79K VND tiers — [Vietnam Insider](https://vietnaminsiders.com/apple-to-raise-all-apps-price-in-vietnam/).
- Review safety: one strong app per vertical, not reskins — [MacRumors 2026-06-09](https://www.macrumors.com/2026/06/09/app-store-guidelines-low-quality-apps/).

### Gaps
- Search-volume and ASO keyword difficulty data (e.g., "quét hóa đơn", "sổ thu chi hộ kinh doanh", "3D scan STL", "home inventory app") were not collected. That is needed to rank tier-A ideas quantitatively.
- The number of Vietnamese household businesses using iPhones, and their willingness to pay, is unknown.
- Vietnamese handwriting OCR and on-device Vietnamese speech-recognition accuracy are unverified. These decide whether ideas 5 and 9 are feasible.
- No revenue data was found for LiDAR home-inventory, floor-plan or scan-to-print apps.
- Motion-sensor and pill/medication opportunities were not researched in depth.
