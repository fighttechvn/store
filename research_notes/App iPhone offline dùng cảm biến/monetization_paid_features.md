# Monetization models and paid features of iPhone camera / OCR / scanner / identifier / LiDAR-3D / on-device-AI utility apps (global, Europe priority; US, UK, Germany and Vietnam prices; data collected 27 Sept 2026)

Scope note: the research covers the whole world, with Europe as the priority market. US App Store prices are the main reference. UK (GBP), Germany (EUR, as the EU proxy) and Vietnam (VND) storefront prices were pulled on 2026-09-27 straight from each app's apps.apple.com page ("In-App Purchases" section). **How to read the storefront data:**
- Apple shows at most about 10 "top" in-app purchases (IAPs) per app.
- IAP names are chosen by the developer, and the page usually does not show the billing period. Where a name does not state the period, I do not assume one.
- GBP and EUR prices on the App Store include VAT.
- Several apps list many price variants under the same name. These are almost certainly A/B-test, promotional or legacy price points.

---

## Key Question 1 — What exactly is free vs. behind the paywall in the leading apps? (feature matrix)

### Takeaway
Almost every leading app gives away **basic capture** (scan, identify, or 3D capture) plus a basic export. The paywall goes on four kinds of feature:
- **Output quality and format**: OCR/searchable PDF, Office export, watermark removal, pro 3D formats such as OBJ/FBX/USDZ/STL/point clouds/DXF, and floor plans.
- **Volume**: unlimited scans, exports, identifications or projects.
- **Cloud and compute**: sync, backup, cloud processing and AI chat.
- **Expert or AI "depth"**: plant or insect experts, AI tutors, diagnosis.

A minority use a hard paywall on the core result: Cal AI's food-scan result, and the AIBY/Next Vision identifier apps, which push weekly or yearly trials.

The most privacy/offline-oriented apps are Genius Scan, TurboScan and Scaniverse. They keep on-device core features free, or sell them once, and charge for OCR, cloud, advanced exports or cloud processing.

### Cited Findings

**Document scanners**
- **Adobe Scan** (Business category, Adobe).
  - Free: scan; crop, rotate and reorder pages; filters; cleanup; save as PDF; search; select and copy text; business card → contact; share by link or email; JPEG export; print. Scans auto-save to Adobe Document Cloud — [Adobe Scan iOS docs](https://www.adobe.com/devnet-docs/adobescan/ios/en/subscriptions.html); [App Store listing](https://apps.apple.com/us/app/id1199564834)
  - Premium: export to Word/Excel/PowerPoint/RTF; combine up to 20 files into one PDF; password-protect PDFs — [Adobe Scan iOS docs](https://www.adobe.com/devnet-docs/adobescan/ios/en/subscriptions.html)
  - Premium also adds compress and edit text — [search summary of Adobe/Google Play listing](https://play.google.com/store/apps/details?id=com.adobe.scan.android&hl=en_US)
  - Subscriptions "work across Scan and Reader mobile apps and Acrobat on the web" — [App Store listing, v26.08.31, updated 2026-09-08](https://apps.apple.com/us/app/id1199564834)
  - **Conflict on the free OCR cap.** The current App Store description says a subscription "increase[s] OCR capacity from 5 to 100 pages" — [App Store listing](https://apps.apple.com/us/app/id1199564834). Adobe's developer docs (older) say the free limit is 25 pages, rising to 100 with a subscription — [Adobe docs](https://www.adobe.com/devnet-docs/adobescan/ios/en/subscriptions.html)
  - There are two tiers: "Adobe Scan Plus" ($4.99/mo, $19.99/yr) and "Adobe Scan Premium" ($9.99/mo). There are also several unnamed Premium price points ($29.99, $49.99, $69.99) — [App Store US IAP list](https://apps.apple.com/us/app/id1199564834)
- **CamScanner** (Productivity, INTSIG).
  - Free: scanning and PDF export, but with a watermark, ads, OCR limited to a preview, 200 MB of cloud storage and lower-resolution exports.
  - Premium: no watermark, full OCR, full-resolution exports, 10 GB of cloud, unlimited batch scanning, team folders, e-signature/PDF editing, no ads — [Essex Software/Scaniva comparison, 2026 (competitor blog, treat with care)](https://essexsoftware.com/scaniva/camscanner-free-vs-paid/)
  - The App Store description says: "subscribe to get unlimited access to all features… billed weekly, monthly, quarterly, or annually" — [App Store listing](https://apps.apple.com/us/app/id388627783)
  - IAP names include "CamScanner Premium (1 week)" (£4.99 / €4.99) and a pay-per-use "One-page Fax" ($0.99) — [GB](https://apps.apple.com/gb/app/id388627783), [US](https://apps.apple.com/us/app/id388627783)
- **Genius Scan** (Business, The Grizzly Labs, Paris).
  - Free, "unlimited and fully-functional, … without any watermark": auto detection; distortion, shadow and defect cleanup; batch scanning; merge/split; multi-page PDF; photo/PDF import; on-device processing; tags; metadata/content search; email export.
  - Premium ("[+]" features): Face ID lock; PDF password encryption; smart renaming/templates; export to Box/Dropbox/Evernote/Expensify/Google Drive/iCloud/OneDrive/OneNote/FTP/WebDAV; background auto-export; OCR text extraction; searchable PDF; business-card scanning; Genius Cloud backup/sync (sold separately) — [App Store listing](https://apps.apple.com/us/app/id377672876); [Genius Scan pricing page](https://thegrizzlylabs.com/genius-scan/pricing)
  - Ultra costs $39.99/yr. Team licences cost $20–$40 per licence per year with volume discounts — [pricing page](https://thegrizzlylabs.com/genius-scan/pricing)
- **Scanner Pro** (Readdle).
  - Marketed as "share as many scans as you want completely free".
  - Feature list: OCR and full-text search, iCloud sync, auto-upload to cloud services, editing, signing, translating PDFs into 20+ languages, expense reports, fax — [App Store listing](https://apps.apple.com/us/app/id333710667); [Readdle site](https://readdle.com/scannerpro)
  - The IAPs are "Scanner Pro Plus" ($3.99–$59.99) plus add-ons: "Fax Pack 1" ($0.99) and "Expense Report" ($4.99) — [App Store US](https://apps.apple.com/us/app/id333710667)
- **iScanner** (Business, BP Mobile).
  - Pro unlocks "all scanner features".
  - The listing shows: OCR in 20+ languages; AI Chat to summarize, translate, rewrite or Q&A on a document; export to PDF/JPG/DOC/XLS/PPT/TXT; password-protected PDFs; expiring shared links; decoy password; PIN/Face ID lock; AWS cloud sync plus a web version. Scanning, editing and viewing work offline — [App Store listing](https://apps.apple.com/us/app/id1040093707)
  - Third-party data says the free version exports 5 documents a day and shows ads and a watermark. Pro adds unlimited export, AI OCR, e-signature, batch scanning, math/count modes and 10 GB or 100 GB of cloud — [G2 via search](https://www.g2.com/products/iscanner/pricing)
  - The IAPs tie storage to price: "1 week Pro 10Gb storage" $3.99; "1 week Pro 100Gb storage" $4.99; "1 year Pro 100Gb" £20.99 / €20.99 — [US](https://apps.apple.com/us/app/id1040093707), [GB](https://apps.apple.com/gb/app/id1040093707)
  - A lifetime deal was sold via StackSocial ($25.97, against a stated $199.90 "regular" price) — [StackSocial](https://www.stacksocial.com/sales/iscanner-app-lifetime-subscription)
- **TurboScan** (Piksoft). Two apps:
  - TurboScan Pro is a paid-upfront app ($12.99) with no IAPs.
  - The free edition sells a single "TurboScan Premium" unlock ($14.99 / £4.99 / €6.99 / 49,000₫) — [App Store US lookup](https://apps.apple.com/us/app/id342548956); [free edition](https://apps.apple.com/us/app/id1017559099)
  - Third-party sources say the free edition allows scanning and sending up to 3 multi-page documents before the one-time unlock — [search summary: AppBrain / APKMirror](https://www.appbrain.com/app/turboscan-scan-documents-re/com.piksoft.turboscan.free)
  - "We do not collect any data… all scanning happens on your iPhone" — [App Store listing](https://apps.apple.com/us/app/id1017559099)
- **Tiny Scanner** (TinyWork Apps).
  - Features listed: OCR, watermark/markup tool, cloud sync "with free storage". "Weekly and annual subscriptions are available" — [App Store listing](https://apps.apple.com/us/app/id595563753)
  - The IAPs include explicit Weekly ($4.99/$5.99/$9.99), Monthly ($4.99/$6.99) and Yearly ($19.99/$49.99) plans, plus "Premium Reward Plan" discounts ($2.99/mo, $29.99/yr) — [App Store US](https://apps.apple.com/us/app/id595563753)
- **SwiftScan AI** (Utilities, Maple Media).
  - Free: "free, high-quality PDF or JPG scans" at 200 dpi or more.
  - Paid: AI Tools (translate, summarize, generate reports) and fax, plus VIP/Plus monthly and annual subscriptions. There are also one-time "Full Scanner App" unlocks ($6.99 / $8.99) and fax credits ($1.99) — [App Store listing and IAPs](https://apps.apple.com/us/app/id834854351)
- **Microsoft Lens** has been retired.
  - Retirement began 9 Jan 2026. The app was removed from the App Store and Google Play on 9 Feb 2026, and scanning stopped working on 9 Mar 2026. Microsoft points users to scanning in the OneDrive app — [Microsoft Support](https://support.microsoft.com/en-us/lens/retirement-of-microsoft-lens); [Windows Latest](https://www.windowslatest.com/2026/01/10/microsoft-lens-just-retired-on-ios-and-android-stops-working-march-9-as-the-company-wants-to-focus-on-copilot/)
  - An iTunes Search API query for "Microsoft Lens" (US) on 2026-09-27 returned no Microsoft app — [iTunes Search API](https://itunes.apple.com/search?term=Microsoft%20Lens&entity=software&country=us)

**Identifiers and AI camera apps**
- **PictureThis** (Education, Glority).
  - Free: a small number of identifications, with ads.
  - Premium: unlimited identifications, no ads, care guides, disease diagnosis, reminders, and expert consultation. The App Store describes the experts as "Chat with our experts 24/7".
  - 7-day free trial, then about $29.99–$39.99/yr — [IdentifyThis (competitor site, 2026)](https://identifythis.app/is-picture-this-app-free); [App Store listing](https://apps.apple.com/us/app/id1252497129)
  - IAPs: "PictureThis Pro" $39.99 (most variants), $7.99, $3.99; "Family Plan" $49.99. Germany also lists a cheaper "PictureThis Plus" tier (€24.99) — [US](https://apps.apple.com/us/app/id1252497129), [DE](https://apps.apple.com/de/app/id1252497129)
- **Picture Insect / Rock Identifier / CoinSnap** (Next Vision, a sister publisher of PictureThis).
  - The listings name the plan "Yearly Premium" with a "1 year (7 days trial)".
  - Picture Insect Premium "includes identifying insects without limits, getting answers from entomologists, studying insects with numerous info, and no watermarks or ads" — [Picture Insect listing](https://apps.apple.com/us/app/id1461694973)
  - Rock Identifier Premium gives "identifying rocks without limits… no watermarks or ads" — [Rock Identifier listing](https://apps.apple.com/us/app/id1546796934)
  - CoinSnap: "Yearly with Trial, 7 days trial… Unlock all Premium features" — [CoinSnap listing](https://apps.apple.com/us/app/id1634551626)
  - Small add-ons appear in the UK and Germany: "No Ads" £0.99 / €0.99, "Rock Unlock Fulltext" €1.99, "Unlock an eBook" £3.99, and a "Nature Education Bundle" (€79.99, or €22.99/month) — [GB](https://apps.apple.com/gb/app/id1546796934), [DE](https://apps.apple.com/de/app/id1461694973)
- **Plantum and Coin ID** (AIBY).
  - "Subscribe to … Premium to get unlimited access… Subscriptions are billed weekly, monthly, or annually" — [Plantum listing](https://apps.apple.com/us/app/id1476047194); [Coin ID listing](https://apps.apple.com/us/app/id1665672552)
  - Coin ID's IAPs are dominated by "Weekly access (3 days trial)" at $4.99–$7.99, plus yearly plans at $14.99–$39.99 — [App Store US](https://apps.apple.com/us/app/id1665672552)
- **Photomath** (Education, Google).
  - "Core Photomath features with step-by-step solutions to symbolic math will always remain free… solve as many problems as you need."
  - Plus adds "AI-powered animated tutorials [400+], deeper explanations and contextual hints".
  - Plans are monthly, 6-month and yearly. The yearly plan "works out to a 50% discount compared to a monthly plan" — [Photomath Help (Google)](https://support.google.com/photomath/answer/14330572?hl=en)
  - Plus is $9.99/mo or $69.99/yr — [search summary, Nibble / MyEngineeringBuddy 2026](https://nibble-app.com/blog/photomath-app)
- **Gauth** (Education, GauthTech/ByteDance).
  - Gauth Plus: "unlimited access to detailed explanations, enhanced AI accuracy, advanced interactive tutor sessions, 20M+ tutorial videos & 100M+ practice questions, and priority 24/7 expert guidance… unlimited top models" — [App Store listing](https://apps.apple.com/us/app/id1542571008)
  - The IAP names show the tactics: "Quarterly – 3-Day Free Trial" $31.99; "Annual – 3-Day Free Trial" $99.99; "Annual – 3Day Trial (Special Offer)" $49.99; "Monthly – Win Back Offer" $11.99; "Back-to-School"; and, in Vietnam, "Weekly – 3-Day Free Trial" 29,000₫ — [US](https://apps.apple.com/us/app/id1542571008), [VN](https://apps.apple.com/vn/app/id1542571008)
- **Cal AI** (Health & Fitness; owned by MyFitnessPal as of 2026).
  - "FOOD SCANNING ANALYSIS RESULTS REQUIRE A SUBSCRIPTION" — this is a hard paywall on the core AI result — [App Store listing](https://apps.apple.com/us/app/id6480417616)
  - 3-day free trial — [CNBC, 6 Sep 2025](https://www.cnbc.com/2025/09/06/cal-ai-how-a-teenage-ceo-built-a-fast-growing-calorie-tracking-app.html)
  - The IAPs include a consumable "Streak Restore" ($0.99) — [App Store US](https://apps.apple.com/us/app/id6480417616)
  - MyFitnessPal ownership — [MacRumors, 21 Apr 2026](https://www.macrumors.com/2026/04/21/apple-cal-ai-app-store-removal/)

**LiDAR / 3D / floor-plan apps**
- **Polycam** (Photo & Video). Plans per the official pricing page:
  - Free: "limited" object, space and AI captures; **GLTF-only export**; up to 150 images per model; public link sharing; no floor plans; single user.
  - **Basic** ($150/yr, or $12.50/mo billed annually, or $30/mo): unlimited captures including Gaussian splats; 6 mesh formats (GLTF, OBJ, FBX, DAE, USDZ, STL, PLY listed); 300 images per model; private sharing; ruler and pen measure.
  - **Business** ($400/user/yr): all formats including point clouds (PLY, LAS, Geo-LAS, PTS, XYZ, DXF); 2D/3D floor plans; advanced measurement; team library; AI reports; 2,000 images per model.
  - **Enterprise** ($1,200/user/yr, minimum 3 seats).
  - Polycam "is no longer offering the Pro plan" to new users — [Polycam pricing](https://poly.cam/pricing)
  - The App Store still lists "Polycam Pro Yearly" $199.99 and "Pro Monthly" $26.99 (legacy), next to "Basic Yearly" $149.99 and "Basic" $29.99 — [App Store US](https://apps.apple.com/us/app/id1532482376)
  - The App Store copy positions Polycam as a B2B tool: floor plans, as-builts, estimates, roof reports, claims files; exports .obj/.dae/.fbx/.stl/.dxf/.ply/.esx; Polycam Web "included free" — [App Store listing](https://apps.apple.com/us/app/id1532482376)
- **KIRI Engine**.
  - Free: "Upload unlimited 3D scans and export at least 3 times per week". Formats: OBJ, STL, FBX, GLTF, GLB, USDZ, PLY, XYZ.
  - Pro: camera-roll upload and 3D Gaussian Splatting, among other features — [App Store listing](https://apps.apple.com/us/app/id1577127142)
  - IAPs: Pro Monthly $9.99–$17.99 and Pro Yearly $29.99–$49.99. Their names reveal intro, sale and win-back pricing ("Newbie", "Sale23/24/25", "Return") — [App Store US](https://apps.apple.com/us/app/id1577127142)
- **3d Scanner App**.
  - Once Laan Labs' free LiDAR scanner. "Laan Labs sold the app in July 2025 to a private investor" — [Laan Labs](https://labs.laan.com/apps)
  - It is now published by "AI Photo Editor Lab SRL" with "weekly, yearly" subscriptions "to access premium app features": Weekly $2.99/$4.99; Yearly $29.99/$69.99 — [App Store listing and IAPs](https://apps.apple.com/us/app/id1419913995)
  - Exports listed: USDZ/AR QuickLook, OBJ, GLTF, GLB, DAE, STL, point clouds (PTS, PCD, PLY, XYZ, LAS, geo-referenced LAS) and DXF floor plans — [App Store listing](https://apps.apple.com/us/app/id1419913995)
- **magicplan** (Productivity).
  - Free "Starter Plan": all features, but only **2 projects** and up to 2 devices; no Workspaces/Teams, API or integrations; no time limit — [magicplan Help Center](https://help.magicplan.app/using-magicplan-for-free)
  - Paid in-app plans: Sketch ($12.99/mo, $129.99/yr), Report ($39.99/mo, $399.99/yr), Estimate ($89.99/mo, $899.99/yr) — [App Store US](https://apps.apple.com/us/app/id427424432)
  - Export formats include PDF, JPG, PNG, SVG, CSV, DXF, OBJ, USDZ and IFC — [magicplan Help (search summary)](https://help.magicplan.app/export-formats)
- **Scaniverse** (Niantic Spatial).
  - "unlimited on-device Gaussian splat capture and processing… Nothing's changed". Exports SPZ, PLY, GLB, FBX.
  - "Free tier for personal scanning… limited cloud processing… Paid plans unlock more processing, bigger teams, 360° camera scans" — [App Store listing](https://apps.apple.com/us/app/id1541433223)
  - Web pricing: Free = 20,000 credits/month (~10 minutes of mobile capture processing), 5 seats, top-ups at $1 per 1,800 credits; Plus = $20/mo or $200/yr (40,000 credits) — [Niantic Spatial pricing](https://www.nianticspatial.com/pricing)
  - Pro is about $50/mo — [search summary of Niantic Spatial blog](https://www.nianticspatial.com/en/blog/scaniverse-annual)
  - The App Store page showed no IAP list, which suggests billing happens off the App Store — [App Store US](https://apps.apple.com/us/app/id1541433223)
- **Luma 3D Capture**. The App Store page showed no IAP list. The app exports NeRFs and Gaussian splats, and was last updated 14 Jan 2026. Luma's current flagship iOS app is the separate "Luma Dream Machine" — [App Store listing](https://apps.apple.com/us/app/id1615849914); [iTunes Search API](https://itunes.apple.com/search?term=Luma%20AI&entity=software&country=us)

**Summary matrix** (✓ = free, P = paid, L = limited free quota; sources as above)

| App | Capture | OCR / searchable PDF | Office / pro formats | Watermark-free | Cloud sync | AI chat / translate / tutor | Security (lock, PDF password) | Volume limit on free | Expert / human help | Model |
|---|---|---|---|---|---|---|---|---|---|---|
| Adobe Scan | ✓ | L (5 or 25 pages per the source; 100 with Premium) | P (Word/Excel/PPT) | ✓ | ✓ (Adobe cloud) | P (Acrobat tier) | P (password) | — | — | Freemium, monthly/annual |
| CamScanner | ✓ | L (preview only) | P | P | L (200 MB) | P | P (e-sign) | — | — | Freemium, weekly/monthly/quarterly/annual |
| Genius Scan | ✓ unlimited | P | ✓ PDF (PDF/A listed in comparison table) | ✓ | P (Genius Cloud) | — | P | none | — | Generous freemium, annual |
| iScanner | ✓ | P | P | P | P (10/100 GB tiers) | P (AI Chat) | P | L (5 exports/day, third-party) | — | Freemium, weekly-heavy |
| TurboScan | ✓ | — | — | — | iCloud | — | ✓ Face ID | L (3 docs, third-party) | — | One-time unlock / paid app |
| PictureThis / Picture Insect / Rock ID | ✓ | n/a | n/a | P (Next Vision) | — | P (diagnosis) | — | L (few IDs) | P (botanists / entomologists) | Soft/hard paywall, yearly with 7-day trial |
| Coin ID / Plantum (AIBY) | ✓ | n/a | n/a | — | — | — | — | L | — | Weekly with 3-day trial dominant |
| Photomath | ✓ unlimited solves | n/a | n/a | — | — | P (animated tutorials, hints) | — | none | — | Generous freemium |
| Gauth | ✓ (limited) | n/a | n/a | — | — | P (unlimited top models, tutor) | — | L | P (24/7 experts) | Trials + win-back |
| Cal AI | onboarding only | n/a | n/a | — | — | P (scan result itself) | — | hard paywall | — | Hard paywall, 3-day trial |
| Polycam | L | n/a | P (OBJ/FBX/USDZ/STL on Basic; LAS/PTS/DXF on Business) | — | ✓ web viewer | P (AI reports, Business) | — | L (captures, 150 images/model) | — | Freemium, B2B tiers |
| KIRI | ✓ unlimited | n/a | ✓ many formats, L (≥3 exports/week) | — | — | P (3DGS) | — | L (exports) | — | Freemium |
| 3d Scanner App | ✓ | n/a | many formats (gating unclear) | — | — | — | — | ? | — | Weekly/yearly (since 2025 sale) |
| magicplan | ✓ | n/a | ✓ in 2 free projects | — | — | — | — | L (2 projects) | — | Project-limited freemium, B2B |
| Scaniverse | ✓ unlimited on-device | n/a | ✓ SPZ/PLY/GLB/FBX | ✓ | L (cloud credits) | — | — | cloud credits | — | Free app + web cloud plans |

### Inferences
- The two patterns that fit an **offline/on-device** app best are Genius Scan and Scaniverse. Both keep capture and on-device processing free (and unlimited). They charge for productivity output (OCR text layer, cloud exports, auto-export, encryption) or for things with a real marginal cost (cloud processing). This is the easiest story to defend to users and to App Review.
- The paid features that recur most often across all categories are:
  - Advanced or pro **export formats**: Office files, OBJ/FBX/USDZ/STL, point clouds, DXF, IFC.
  - **Unlimited volume** (scans, exports, identifications, projects).
  - **Watermark removal**.
  - **OCR/searchable PDF**.
  - **Security** (Face ID lock, password PDFs).
  - **AI extras** (chat, summarize, translate, tutor).
  - **Human experts**.
  In 3D apps, **measurement tools and floor plans** are placed in higher B2B tiers (Polycam Business, magicplan). This suggests "measurement precision/pro survey output" is a strong candidate for a pro tier.
- One-time "unlock" models still exist in scanners (TurboScan, SwiftScan "Full Scanner App"). Identifier apps have mostly moved to weekly or yearly plans with trials. 3d Scanner App moved from free to weekly/yearly subscriptions after its 2025 sale.

### Gaps
- Exact free quotas are not officially documented for PictureThis, Plantum, Coin ID, CamScanner and iScanner. The figures above come from third-party or competitor blogs.
- I could not find an official statement of which Scanner Pro features are "Plus" only, or what 3d Scanner App and Tiny Scanner gate today.
- I did not verify KIRI Engine's full Pro feature list (the kiri-innovation.com pricing page returned no content).
- Luma 3D Capture shows no IAPs, and its current monetization, if any, is unclear.

---

## Key Question 2 — Price points, trials, paywall types and lifetime options (US primary; GBP/EUR for Europe; VND for Vietnam)

### Takeaway
US anchors cluster around:
- **$4.99–$7.99 per week** (identifiers, 3D, iScanner, Tiny Scanner).
- **$9.99–$14.99 per month** (Adobe, CamScanner, Photomath, Gauth).
- **$29.99–$69.99 per year** (PictureThis, Next Vision, CamScanner, Genius Scan, 3d Scanner App, Cal AI).

B2B 3D and floor-plan tools charge far more: Polycam Basic $149.99/yr, legacy Pro $199.99/yr; magicplan up to $899.99/yr.

Trials are typically 3 days on weekly plans (AIBY, Gauth, Cal AI) and 7 days on yearly plans (Next Vision, PictureThis). UK and German prices generally reuse the **same digits in £/€** as in $, or go slightly higher in € (for example €10.99 against $9.99). Next Vision prices its yearly plans *lower* in the UK and Germany (£/€29.99–34.99 against $39.99). Vietnam prices mostly follow Apple's automatic equalization, but several apps localize aggressively (Gauth, magicplan, TurboScan).

### Cited Findings
- Full storefront IAP price lists (as displayed on 2026-09-27; up to 10 items per storefront; sources in the last column):

| App | US (USD) | UK (GBP, incl. VAT) | Germany (EUR, incl. VAT) | Vietnam (VND) | Source |
|---|---|---|---|---|---|
| Adobe Scan | Adobe Scan Premium - Monthly $9.99; Adobe Scan Premium $9.99; Adobe PDF Pack $9.99; Adobe Scan Premium $49.99; Adobe Scan Plus - Monthly $4.99; Adobe Scan Premium $69.99; Adobe Scan Plus - Yearly $19.99; Adobe Scan Premium $3.99; Scan premium - monthly $14.99; Adobe Scan Premium $29.99 | Scan premium -monthly £9.99; Adobe Scan Premium £8.99; Adobe Scan Premium £49.99; Adobe Scan Plus - Monthly £4.99; Adobe PDF Pack £9.99; Adobe Scan Premium £62.99; Adobe Scan Plus - Yearly £19.99; Adobe Scan Premium £39.99; Adobe Scan Premium £3.49; Adobe Scan Premium £26.99 | Scan premium - monatlich 10,99 €; Adobe Scan Premium 59,99 €; Adobe Scan Premium 10,49 €; Adobe Scan Plus – Monatlich 5,99 €; Adobe Scan Premium 74,99 €; Adobe Scan Plus – Jährlich 22,99 €; Adobe PDF Pack 11,49 €; Adobe Scan Premium 44,99 €; Adobe Scan Premium 31,99 €; Adobe Scan Premium 4,49 € | Scan premium -monthly 229.000đ; Adobe Scan Plus - Monthly 129.000đ; Adobe Scan Premium 229.000đ; Adobe Scan Premium 1.599.000đ; Adobe Scan Plus - Yearly 499.000đ; Adobe Scan Premium 679.000đ; Adobe Scan Premium 92.000đ; Adobe Scan Premium 1.499.000đ; Adobe PDF Pack 229.000đ; Adobe Scan Premium 1.199.000đ | [US](https://apps.apple.com/us/app/id1199564834) · [GB](https://apps.apple.com/gb/app/id1199564834) · [DE](https://apps.apple.com/de/app/id1199564834) · [VN](https://apps.apple.com/vn/app/id1199564834) |
| CamScanner | Premium Account(1 year) $59.99; Premium Account $4.99; CamScanner Premium $6.99; Premium Account(1 Month) $9.99; CamScanner Premium $49.99; Premium Account (1 year) $59.99; One-page Fax $0.99; CamScanner Premium $49.99; CamScanner Premium $69.99; Premium Account (1 month) $9.99 | Premium Account (1 year) £34.99; Premium Account(1 year) £58.99; Premium Account £3.99; CamScanner Premium £45.99; Premium Account(1 Month) £9.99; CamScanner Premium £49.99; CamScanner Premium £39.99; CamScanner Premium(1 week) £4.99; CamScanner Premium £6.99; Premium Account (1 month) £9.99 | Premium Account(1 year) 66,99 €; Premium-Konto 4,99 €; CamScanner Premium-Konto 53,99 €; Premium Account(1 Month) 10,99 €; CamScanner Premium 49,99 €; CamScanner Premium-Konto 49,99 €; CamScanner Premium(1 week) 4,99 €; Premium Account (1 year) 66,99 €; 1 Seite 0,99 €; CamScanner Premium 7,99 € | CamScanner Premium 1.159.000đ; Premium Account 119.000đ; CamScanner Premium 499.000đ; Premium Account (1 year) 929.000đ; Premium Account(1 year) 1.399.000đ; CamScanner Premium 199.000đ; Premium Account(1 Month) 229.000đ; Premium Account (1 year) 1.159.000đ; Premium Account (1 year) 1.499.000đ; Premium Account (1 month) 92.000đ | [US](https://apps.apple.com/us/app/id388627783) · [GB](https://apps.apple.com/gb/app/id388627783) · [DE](https://apps.apple.com/de/app/id388627783) · [VN](https://apps.apple.com/vn/app/id388627783) |
| Genius Scan | Genius Scan Ultra $4.99; Genius Scan Plus $0.99; Genius Scan Ultra $39.99; Genius Scan Ultra $39.99; Genius Scan Plus $11.99; Genius Scan Ultra $39.99; Genius Scan Ultra $49.99; Genius Scan Ultra $49.99 | Genius Scan Ultra £4.99; Genius Scan Plus £0.79; Genius Scan Ultra £39.99; Genius Scan Ultra £39.99; Genius Scan Plus £9.99; Genius Scan Ultra £39.99; Genius Scan Ultra £49.99; Genius Scan Ultra £49.99 | Genius Scan Ultra 5,99 €; Genius Scan Ultra 44,99 €; Genius Scan Plus 0,99 €; Genius Scan Ultra 44,99 €; Genius Scan Plus 12,99 €; Genius Scan Ultra 44,99 €; Genius Scan Ultra 59,99 €; Genius Scan Ultra 59,99 € | Genius Scan Ultra 999.000đ; Genius Scan Plus 22.000đ; Genius Scan Ultra 129.000đ; Genius Scan Ultra 1.499.000đ; Genius Scan Ultra 999.000đ; Genius Scan Plus 399.000đ; Genius Scan Ultra 999.000đ; Genius Scan Ultra 1.299.000đ | [US](https://apps.apple.com/us/app/id377672876) · [GB](https://apps.apple.com/gb/app/id377672876) · [DE](https://apps.apple.com/de/app/id377672876) · [VN](https://apps.apple.com/vn/app/id377672876) |
| Scanner Pro (Readdle) | Fax Pack 1 $0.99; Scanner Pro Plus $7.99; Scanner Pro Plus $29.99; Scanner Pro Plus $19.99; Expense Report $4.99; Scanner Pro Plus $3.99; Expense Report $4.99; Scanner Pro Plus $59.99; Scanner Pro Plus $6.99; Scanner Pro Plus $59.99 | Scanner Pro Plus £7.99; Scanner Pro Plus £26.99; Scanner Pro Plus £19.49; Fax Pack 1 £0.99; Expense Report £4.99; Scanner Pro Plus £3.49; Expense Report £4.99; Scanner Pro Plus £59.99; Scanner Pro Plus £6.99; Scanner Pro Plus £59.99 | Fax-Paket 1 0,99 €; Scanner Pro Plus 31,99 €; Scanner Pro Plus 8,99 €; Scanner Pro Plus 21,99 €; Scanner Pro Plus 3,99 €; Spesenabrechnung 5,99 €; Scanner Pro Plus 69,99 €; Spesenabrechnung 5,99 €; Scanner Pro Plus 7,99 €; Scanner Pro Plus 69,99 € | Scanner Pro Plus 249.000đ; Scanner Pro Plus 679.000đ; Scanner Pro Plus 469.000đ; Expense Report 129.000đ; Scanner Pro Plus 92.000đ; Fax Pack 1 29.000đ; Expense Report 129.000đ; Scanner Pro Plus 1.999.000đ; Scanner Pro Plus 199.000đ; Scanner Pro Plus 709.000đ | [US](https://apps.apple.com/us/app/id333710667) · [GB](https://apps.apple.com/gb/app/id333710667) · [DE](https://apps.apple.com/de/app/id333710667) · [VN](https://apps.apple.com/vn/app/id333710667) |
| iScanner (BP Mobile) | 1 week Pro 100Gb storage $4.99; Premium Scanner & PDF editor $12.99; Premium $3.99; Premium $9.99; Premium $4.99; Premium $4.99; Premium $4.99; Premium $9.99; Premium $19.99; 1 week Pro 10Gb storage $3.99 | 1 week Pro 100Gb storage £4.99; Premium £3.49; Premium Scanner & PDF editor £11.99; Premium £9.99; Premium £4.99; Premium £4.99; Premium £4.49; Premium £6.99; Premium £19.99; 1 year Pro 100Gb storage £20.99 | 1 week Pro 100Gb storage 4,99 €; Premium-Scanner und PDF-Editor 12,99 €; Premium 3,99 €; Premium 9,99 €; Premium 4,99 €; 1 year Pro 100Gb storage 20,99 €; Premium 4,99 €; Premium 19,99 €; Premium 4,99 €; 1 week Pro 10Gb storage 3,99 € | 1 week Pro 100Gb storage 129.000đ; Premium Scanner & PDF editor 299.000đ; Premium 249.000đ; Premium 129.000đ; Premium 129.000đ; Premium 92.000đ; 1 year Pro 100Gb storage 599.000đ; Premium 149.000đ; 1 week Pro 10Gb storage 99.000đ; Premium 469.000đ | [US](https://apps.apple.com/us/app/id1040093707) · [GB](https://apps.apple.com/gb/app/id1040093707) · [DE](https://apps.apple.com/de/app/id1040093707) · [VN](https://apps.apple.com/vn/app/id1040093707) |
| TurboScan (free edition) | TurboScan Premium $14.99 | TurboScan Premium £4.99 | TurboScan Premium 6,99 € | TurboScan Premium 49.000đ | [US](https://apps.apple.com/us/app/id1017559099) · [GB](https://apps.apple.com/gb/app/id1017559099) · [DE](https://apps.apple.com/de/app/id1017559099) · [VN](https://apps.apple.com/vn/app/id1017559099) |
| Tiny Scanner | Premium Plan - Monthly $4.99; Premium Plan - Weekly $4.99; Upgrade to Tiny Scanner Plus $4.99; Premium Plan - Weekly $5.99; Premium Reward Plan - Monthly $2.99; Premium Plan - Monthly $6.99; Premium Plan - Yearly $49.99; Premium Plan - Weekly $9.99; Premium Reward Plan - Yearly $29.99; Premium Plan - Yearly $19.99 | Premium Plan - Monthly £4.99; Upgrade to Tiny Scanner Plus £4.99; Premium Plan - Weekly £4.99; Premium Plan - Weekly £5.99; Premium Reward Plan - Monthly £2.99; Premium Plan - Monthly £6.99; Premium Plan - Yearly £48.99; Premium Reward Plan - Yearly £29.49; Premium Plan - Monthly £4.99; Premium Plan - Yearly £19.99 | Upgrade to Tiny Scanner Plus 5,99 €; Premium Plan - Weekly 5,99 €; Premium Plan - Monthly 5,49 €; Premium Plan - Weekly 6,99 €; Premium Reward Plan - Monthly 3,49 €; Premium Plan - Yearly 54,99 €; Premium Plan - Monthly 7,99 €; Premium Plan - Yearly 22,99 €; Premium Reward Plan - Yearly 32,99 €; Premium Plan - Weekly 9,99 € | Upgrade to Tiny Scanner Plus 149.000đ; Premium Plan - Weekly 129.000đ; Premium Plan - Monthly 119.000đ; Premium Plan - Weekly 149.000đ; Premium Reward Plan - Monthly 69.000đ; Premium Plan - Monthly 199.000đ; Premium Reward Plan - Yearly 699.000đ; Premium Plan - Yearly 1.159.000đ; Premium Plan - Monthly 249.000đ; Premium Plan - Monthly 199.000đ | [US](https://apps.apple.com/us/app/id595563753) · [GB](https://apps.apple.com/gb/app/id595563753) · [DE](https://apps.apple.com/de/app/id595563753) · [VN](https://apps.apple.com/vn/app/id595563753) |
| SwiftScan AI | SwiftScan VIP Monthly $5.99; SwiftScan Pro-Full Scanner App $6.99; SwiftScan Plus Monthly $7.99; Credits to Fax from iPhone $1.99; SwiftScan Plus Annual $59.99; SwiftScan VIP-Full Scanner App $8.99; SwiftScan VIP Annual $34.99; SwiftScan Pro 40 $3.99; SwiftScan Plus Monthly $9.99; SwiftScan Plus Annual $59.99 | SwiftScan VIP Monthly £5.99; SwiftScan Pro-Full Scanner App £6.99; SwiftScan Plus Monthly £6.99; SwiftScan Plus Annual £59.99; SwiftScan Pro 40 £3.99; SwiftScan VIP-Full Scanner App £8.99; SwiftScan VIP Annual £33.99; SwiftScan Plus Monthly £9.99; SwiftScan Pro £20.49; SwiftScan Lite-OCR & Annotate £4.99 | SwiftScanPro-Volle Scanner App 7,99 €; SwiftScan VIP Monthly 6,49 €; SwiftScan Pro 100 0,00 €; SwiftScan Plus Monats 7,99 €; SwiftScan Pro 40 3,99 €; SwiftScan Plus Jahres 69,99 €; Fax vom iPhone senden Münzen 1,99 €; SwiftScanVIP:Volle Scanner App 9,99 €; SwiftScan VIP Annual 37,99 €; SwiftScan Pro 23,99 € | SwiftScan VIP Monthly 139.000đ; SwiftScan Plus Monthly 99.000đ; SwiftScan Pro-Full Scanner App 199.000đ; SwiftScan Plus Annual 1.499.000đ; SwiftScan Plus Monthly 239.000đ; SwiftScan VIP-Full Scanner App 299.000đ; SwiftScan Plus Annual 1.499.000đ; SwiftScan Plus Annual 999.000đ; SwiftScan Plus Monthly 199.000đ; SwiftScan VIP Annual 809.000đ | [US](https://apps.apple.com/us/app/id834854351) · [GB](https://apps.apple.com/gb/app/id834854351) · [DE](https://apps.apple.com/de/app/id834854351) · [VN](https://apps.apple.com/vn/app/id834854351) |
| PictureThis | PictureThis Pro $39.99; PictureThis Pro $39.99; PictureThis Pro $7.99; PictureThis Pro $3.99; PictureThis Pro $39.99; PictureThis Pro $39.99; PictureThis Pro $39.99; PictureThis Pro $39.99; PictureThis Pro $39.99; PictureThis Family Plan $49.99 | PictureThis Pro £34.99; PictureThis Pro £34.99; PictureThis Pro £7.99; PictureThis Pro £3.99; PictureThis Pro £34.99; PictureThis Pro £34.99; PictureThis Pro £34.99; PictureThis Pro £39.99; PictureThis Family Plan £49.99; PictureThis Pro £34.99 | PictureThis Pro 34,99 €; PictureThis Pro 34,99 €; PictureThis Pro 8,99 €; PictureThis Pro 3,99 €; PictureThis Pro 34,99 €; PictureThis Pro 34,99 €; PictureThis Pro 34,99 €; PictureThis Pro 39,99 €; PictureThis Plus 24,99 €; PictureThis Family Plan 59,99 € | PictureThis Pro 689.000đ; PictureThis Pro 689.000đ; PictureThis Pro 199.000đ; PictureThis Family Plan 1.299.000đ; PictureThis Pro 689.000đ; PictureThis Pro 799.000đ; PictureThis Pro 909.000đ; PictureThis Pro 99.000đ; PictureThis Pro 799.000đ; PictureThis Plus 499.000đ | [US](https://apps.apple.com/us/app/id1252497129) · [GB](https://apps.apple.com/gb/app/id1252497129) · [DE](https://apps.apple.com/de/app/id1252497129) · [VN](https://apps.apple.com/vn/app/id1252497129) |
| Plantum (AIBY) | Plant Identification $6.99; Premium membership (1 month) $6.99; Plant Identification $59.99; Plant Identifier $29.99; Plantum PRO $39.99; Premium $19.99; Premium $1.99; Plantum PRO $7.99; Plantum PRO $34.99; Premium $6.99 | Plant Identification £6.99; Plant Identification £58.99; Plant Identifier £25.99; Premium £1.79; Premium membership (1 month) £6.99; Premium £17.49; Plant Finder £8.99; Premium £17.99; Plantum PRO £39.99; Premium £7.99 | Identifizierung von Pflanzen 7,99 €; Identifizierung von Pflanzen 64,99 €; Pflanzen-Bestimmungsapp 29,99 €; Plantum PRO 37,99 €; Premium 1,99 €; Premium 19,99 €; Premium-Mitgliedschaft (1 Mo.) 6,49 €; Premium 21,49 €; Pflanzen-Finder 10,49 €; Plantum PRO 8,99 € | Plant Identification 1.399.000đ; Plant Identification 199.000đ; Plant Identifier 689.000đ; Premium 189.000đ; Premium 1.499.000đ; Plant Care 109.000đ; Plant Finder 229.000đ; Plantum PRO 799.000đ; Premium membership (1 month) 139.000đ; Premium 229.000đ | [US](https://apps.apple.com/us/app/id1476047194) · [GB](https://apps.apple.com/gb/app/id1476047194) · [DE](https://apps.apple.com/de/app/id1476047194) · [VN](https://apps.apple.com/vn/app/id1476047194) |
| Picture Insect | Picture Insect Premium $39.99; Picture Insect Premium $39.99; Picture Insect Premium $39.99; Yearly Premium $39.99; Month Premium $5.99; Picture Insect Premium $2.99; Picture Insect Premium $39.99; Picture Insect Premium $39.99; Picture Insect Month Pro $9.99; Picture Insect Quarter Premium $14.99 | Picture Insect Premium £29.99; Picture Insect Premium £29.99; Yearly Premium £29.99; Month Premium £4.99; Picture Insect Premium £2.49; Picture Insect Premium £39.99; Picture Insect Quarter Premium £14.99; Picture Insect Premium £39.99; Picture Insect Month Pro £9.99; Unlock an eBook £3.99 | Picture Insect Premium 34,99 €; Picture Insect Premium 34,99 €; Yearly Premium 34,99 €; Picture Insect Premium 2,99 €; Month Premium 5,99 €; Picture Insect Premium 44,99 €; Nature Education Bundle Month 22,99 €; Picture Insect Month Pro 9,99 €; Nature Education Bundle 79,99 €; Picture Insect Premium 44,99 € | Picture Insect Premium 799.000đ; Picture Insect Premium 999.000đ; Picture Insect Premium 799.000đ; Picture Insect Premium 999.000đ; Picture Insect Premium 999.000đ; Yearly Premium 799.000đ; Nature Education Bundle 1.999.000đ; Nature Education Bundle 1.999.000đ; Picture Insect Quarter Premium 399.000đ; Unlock an eBook 119.000đ | [US](https://apps.apple.com/us/app/id1461694973) · [GB](https://apps.apple.com/gb/app/id1461694973) · [DE](https://apps.apple.com/de/app/id1461694973) · [VN](https://apps.apple.com/vn/app/id1461694973) |
| Coin ID (AIBY) | Weekly access (3 days trial) $6.99; Weekly access (3 days trial) $5.99; Weekly access $6.99; Yearly premium subscription $39.99; Weekly access (3 days trial) $4.99; Weekly access (3 days trial) $7.99; Monthly subscription $4.99; Weekly access $5.99; Yearly subscription_19.99 $24.99; Yearly subscription_14.99 $14.99 | Weekly access (3 days trial) £6.99; Weekly access (3 days trial) £5.99; Weekly access £6.99; Yearly premium subscription £39.99; Monthly subscription £4.99; Weekly access (3 days trial) £7.99; Weekly access (3 days trial) £4.99; Weekly access £5.99; Yearly subscription_19.99 £24.99; Yearly premium subscription £9.99 | Weekly access (3 days trial) 7,99 €; Weekly access (3 days trial) 6,99 €; Weekly access 7,99 €; Weekly access (3 days trial) 8,99 €; Yearly premium subscription 44,99 €; Monthly subscription 5,99 €; Yearly subscription_19.99 29,99 €; Weekly access (3 days trial) 5,99 €; Weekly access 6,99 €; Yearly premium subscription 9,99 € | Weekly access (3 days trial) 199.000đ; Yearly premium subscription 999.000đ; Weekly access (3 days trial) 149.000đ; Weekly access (3 days trial) 129.000đ; Premium 1.999.000đ; Yearly premium subscription 999.000đ; Yearly subscription Promo 1.199.000đ; Monthly subscription Promo 299.000đ; Weekly subscription Promo 199.000đ; Premium 5.999.000đ | [US](https://apps.apple.com/us/app/id1665672552) · [GB](https://apps.apple.com/gb/app/id1665672552) · [DE](https://apps.apple.com/de/app/id1665672552) · [VN](https://apps.apple.com/vn/app/id1665672552) |
| CoinSnap | Coin Identifier Premium $39.99; Coin Identifier Premium $3.99; Coin Identifier Premium $39.99; Coin Identifier Premium $39.99; Coin Identifier Premium $39.99; Coin Identifier Premium $39.99; Coin Identifier Plus $39.99; Coin Identifier Premium $6.99; Coin Identifier Premium $9.99; Coin Identifier Premium $7.99 | Coin Identifier Premium £24.99; Coin Identifier Premium £3.99; Coin Identifier Premium £24.99; Coin Identifier Premium £29.99; Coin Identifier Premium £24.99; Coin Identifier Premium £24.99; Coin Identifier Premium £24.99; Coin Identifier Premium £29.99; Coin Identifier Premium £6.99; Coin Identifier Plus £39.99 | Coin Identifier Premium 29,99 €; Coin Identifier Premium 3,99 €; Coin Identifier Plus 44,99 €; Coin Identifier Premium 29,99 €; Coin Identifier Premium 29,99 €; Coin Identifier Premium 29,99 €; Coin Identifier Premium 34,99 €; Coin Identifier Premium 44,99 €; Coin Identifier Premium 34,99 €; Coin Identifier Premium 29,99 € | Coin Identifier Premium 699.000đ; Coin Identifier Premium 699.000đ; Coin Identifier Premium 699.000đ; Coin Identifier Premium 699.000đ; Coin Identifier Premium 699.000đ; Coin Identifier Premium 699.000đ; Coin Identifier Premium 699.000đ; Coin Identifier Premium 249.000đ; Coin Identifier Premium 249.000đ; Coin Identifier Premium 249.000đ | [US](https://apps.apple.com/us/app/id1634551626) · [GB](https://apps.apple.com/gb/app/id1634551626) · [DE](https://apps.apple.com/de/app/id1634551626) · [VN](https://apps.apple.com/vn/app/id1634551626) |
| Rock Identifier | Rock Identifier Premium $39.99; Rock Identifier Premium $39.99; Rock Identifier Premium $39.99; Rock Identifier Premium $39.99; Rock Identifier Premium $39.99; Rock Identifier Premium $3.99; Rock Identifier Premium $7.99; Rock Identifier Premium $39.99; Rock Identifier Premium $29.99; Rock Identifier Premium $69.99 | Rock Identifier Premium £29.99; Rock Identifier Premium £29.99; Rock Identifier Premium £29.99; Rock Identifier Premium £29.99; Rock Identifier Premium £7.99; Rock Identifier Premium £3.99; Rock Identifier Premium £26.49; No Ads £0.99; Rock Identifier Premium £39.99; Rock Identifier Premium £49.99 | Rock Identifier Premium 29,99 €; Rock Identifier Premium 29,99 €; Rock Identifier Premium 29,99 €; Rock Identifier Premium 29,99 €; Rock Identifier Premium 8,99 €; Rock Identifier Premium 3,99 €; Rock Unlock Fulltext 1,99 €; Rock Identifier Premium 44,99 €; No Ads 0,99 €; Rock Identifier Premium 59,99 € | Rock Identifier Premium 699.000đ; Rock Identifier Premium 699.000đ; Rock Identifier Premium 119.000đ; Rock Identifier Premium 699.000đ; Rock Identifier Premium 799.000đ; Rock Identifier Premium 999.000đ; Rock Identifier Premium 699.000đ; Rock Unlock New Skin 59.000đ; Rock Identifier Premium 1.299.000đ; Rock Identifier Premium 1.999.000đ | [US](https://apps.apple.com/us/app/id1546796934) · [GB](https://apps.apple.com/gb/app/id1546796934) · [DE](https://apps.apple.com/de/app/id1546796934) · [VN](https://apps.apple.com/vn/app/id1546796934) |
| Photomath | Photomath Plus $9.99; Photomath Plus $5.99; Photomath Plus $7.99; Photomath Plus $9.99; Photomath Plus $9.99; Photomath Plus $9.99; Photomath Plus $9.99; Photomath Plus $9.99; Photomath Plus $9.99; Photomath Plus $9.99 | Photomath Plus £9.49; Photomath Plus £5.99; Photomath Plus £9.99; Photomath Plus £9.99; Photomath Plus (1 month) £9.99; Photomath Plus £8.99; Photomath Plus £8.99; Photomath Plus £9.99; Photomath Plus £9.99; Photomath Plus £9.99 | Photomath Plus 7,99 €; Photomath Plus 7,99 €; Photomath Plus 7,99 €; Photomath Plus 10,99 €; Photomath Plus 11,49 €; Photomath Plus 10,99 €; Photomath Plus 10,99 €; Photomath Plus 11,49 €; Photomath Plus 10,99 €; Photomath Plus 11,49 € | Photomath Plus 229.000đ; Photomath Plus 229.000đ; Photomath Plus 229.000đ; Photomath Plus 229.000đ; Photomath Plus 249.000đ; Photomath Plus 249.000đ; Photomath Plus 249.000đ; Photomath Plus 249.000đ; Photomath Plus 249.000đ; Photomath Plus 299.000đ | [US](https://apps.apple.com/us/app/id919087726) · [GB](https://apps.apple.com/gb/app/id919087726) · [DE](https://apps.apple.com/de/app/id919087726) · [VN](https://apps.apple.com/vn/app/id919087726) |
| Gauth | Quarterly - 3-Day Free Trial $31.99; Quarterly - 2022 (for new users) $31.99; Monthly $11.99; Gauth PLUS - Monthly $11.99; Annual - 3Day Trial (Special Offer) $49.99; Free Trial（only for newuser) $11.99; Annual - 3-Day Free Trial $99.99; Quarterly - Special Discount $26.99; Monthly - Win Back Offer $11.99; Quarterly - 2022 Back-to-School $31.99 | Quarterly - 3-Day Free Trial £11.99; Quarterly - 2022 (for new users) £11.99; Quarterl_basic £14.99; Free Trial（only for newuser) £4.99; Monthly £4.99; Gauth PLUS - Monthly £4.99; Monthly_basic £6.99; Quarterly - 2022 Back-to-School £11.99; Monthly - Win Back Offer £4.99; Annual - 3Day Trial (Special Offer) £14.99 | Quarterly - 3-Day Free Trial 19,99 €; Gauth PLUS - Monthly 9,99 €; Gauth PLUS - Quarterly 19,99 €; Monthly 1,99 €; Annual - 3Day Trial (Special Offer) 39,99 €; Gauth PLUS - Annual 59,99 €; Super Gauth AI 3 Month 3DFree 2021 19,99 €; Super Gauth AI 3 Month 3DFree 2020 9,99 €; Points 7,99 €; Quarterly - 2022 Back-to-School 5,99 € | Quarterly - 3-Day Free Trial 129.000đ; Super Gauth AI 3 Month 3DFree 2020 249.000đ; Gauth PLUS - Monthly 49.000đ; Annual - 3Day Trial (Special Offer) 149.000đ; Gauth PLUS - Quarterly 129.000đ; Super Gauth AI 1 Month 149.000đ; Monthly 49.000đ; Gauth PLUS - Annual 299.000đ; Annual - 3-Day Free Trial 299.000đ; Weekly - 3-Day Free Trial 29.000đ | [US](https://apps.apple.com/us/app/id1542571008) · [GB](https://apps.apple.com/gb/app/id1542571008) · [DE](https://apps.apple.com/de/app/id1542571008) · [VN](https://apps.apple.com/vn/app/id1542571008) |
| Cal AI | Unlimited $29.99; Unlimited Plan $19.99; Unlimited $9.99; Unlimited $19.99; Streak Restore $0.99; Unlimited $2.99; Unlimited $29.99; Unlimited $29.99; Unlimited $5.99; Unlimited $5.99 | Unlimited £29.99; Unlimited Plan £19.99; Unlimited £9.99; Unlimited £19.99; Streak Restore £0.99; Unlimited £2.99; Unlimited £5.99; Unlimited £5.99; Unlimited £37.00; Unlimited £29.99 | Unlimited 34,99 €; Unlimited Plan 22,99 €; Unlimited 9,99 €; Unlimited 22,99 €; Streak Restore 0,99 €; Unlimited 33,00 €; Unlimited 34,99 €; Unlimited 2,99 €; Unlimited 44,99 €; Unlimited 34,99 € | Unlimited 799.000đ; Unlimited Plan 499.000đ; Unlimited 249.000đ; Unlimited 499.000đ; Unlimited 47.000đ; Unlimited 150.000đ; Streak Restore 29.000đ; Unlimited 999.000đ; Unlimited 1.999.000đ; Unlimited 94.000đ | [US](https://apps.apple.com/us/app/id6480417616) · [GB](https://apps.apple.com/gb/app/id6480417616) · [DE](https://apps.apple.com/de/app/id6480417616) · [VN](https://apps.apple.com/vn/app/id6480417616) |
| Polycam | Polycam Pro Yearly $199.99; Polycam Pro Monthly $26.99; Polycam Basic Yearly $149.99; Polycam Basic $29.99 | Polycam Pro Yearly £149.99; Polycam Pro Monthly £22.99; Polycam Basic Yearly £149.99; Polycam Basic £29.99 | Polycam Pro Yearly 199,99 €; Polycam Pro Monthly 26,99 €; Polycam Basic Yearly 179,99 €; Polycam Basic 34,99 € | Polycam Pro Yearly 2.499.000đ; Polycam Pro Monthly 399.000đ; Polycam Basic Yearly 4.999.000đ; Polycam Basic 999.000đ | [US](https://apps.apple.com/us/app/id1532482376) · [GB](https://apps.apple.com/gb/app/id1532482376) · [DE](https://apps.apple.com/de/app/id1532482376) · [VN](https://apps.apple.com/vn/app/id1532482376) |
| KIRI Engine | KIRI Pro Monthly Renewal $17.99; KIRI Pro Yearly Renewal Newbie $47.99; KIRI Pro Monthly Renewal $9.99; KIRI Pro Monthly Renewal $14.99; KIRI Pro Yearly Renewal Newbie $35.99; KIRI Pro Yearly Renewal Sale24 $35.99; KIRI Pro Annual Renewal Sale23 $29.99; KIRI Pro Yearly Renewal Return $47.99; KIRI Pro Yearly Renewal Sale25 $35.99; KIRI Pro Annual Renewal $49.99 | KIRI Pro Monthly Renewal £17.99; KIRI Pro Yearly Renewal Newbie £49.99; KIRI Pro Monthly Renewal £8.99; KIRI Pro Monthly Renewal £14.99; KIRI Pro Yearly Renewal Newbie £34.99; KIRI Pro Yearly Renewal Sale24 £34.99; KIRI Pro Yearly Renewal Return £49.99; KIRI Pro Annual Renewal Sale23 £29.99; KIRI Pro Yearly Renewal Sale25 £34.99; KIRI Pro Annual Renewal £43.99 | KIRI Pro Yearly Renewal Newbie 49,99 €; KIRI Pro Monthly Renewal 19,99 €; KIRI Pro Monthly Renewal 17,99 €; KIRI Pro Monthly Renewal 10,49 €; KIRI Pro Yearly Renewal Newbie 39,99 €; KIRI Pro Yearly Renewal Sale24 39,99 €; KIRI Pro Annual Renewal Sale23 34,99 €; KIRI Pro Yearly Renewal Return 49,99 €; KIRI Pro Yearly Renewal Sale25 39,99 €; KIRI Pro Annual Renewal 50,99 € | KIRI Pro Monthly Renewal 499.000đ; KIRI Pro Yearly Renewal Newbie 1.299.000đ; KIRI Pro Yearly Renewal Newbie 999.000đ; KIRI Pro Monthly Renewal 249.000đ; KIRI Pro Yearly Renewal 1.499.000đ; KIRI Pro Monthly Renewal 399.000đ; KIRI Pro Yearly Renewal Sale24 999.000đ; KIRI Pro Monthly Renewal Anniv 199.000đ; KIRI Pro Yearly Renewal Sale25 999.000đ; KIRI Pro Yearly Renewal Return 1.299.000đ | [US](https://apps.apple.com/us/app/id1577127142) · [GB](https://apps.apple.com/gb/app/id1577127142) · [DE](https://apps.apple.com/de/app/id1577127142) · [VN](https://apps.apple.com/vn/app/id1577127142) |
| 3d Scanner App | Weekly premium $4.99; Weekly premium $2.99; Weekly premium $2.99; Weekly premium $4.99; Yearly premium $69.99; Yearly premium $29.99; Yearly premium $29.99; Yearly premium $69.99 | Weekly premium £4.99; Weekly premium £2.99; Weekly premium £4.99; Weekly premium £2.99; Yearly premium £69.99; Yearly premium £29.99; Yearly premium £29.99; Yearly premium £69.99 | Weekly premium 5,99 €; Weekly premium 2,99 €; Yearly premium 79,99 €; Weekly premium 2,99 €; Weekly premium 5,99 €; Yearly premium 34,99 €; Yearly premium 34,99 €; Yearly premium 79,99 € | Weekly premium 149.000đ; Weekly premium 79.000đ; Weekly premium 79.000đ; Weekly premium 149.000đ; Yearly premium 799.000đ; Yearly premium 1.999.000đ; Yearly premium 799.000đ; Yearly premium 1.999.000đ | [US](https://apps.apple.com/us/app/id1419913995) · [GB](https://apps.apple.com/gb/app/id1419913995) · [DE](https://apps.apple.com/de/app/id1419913995) · [VN](https://apps.apple.com/vn/app/id1419913995) |
| magicplan | Sketch Plan (1 Month) $12.99; Report Plan (1 Month) $39.99; Estimate Plan (1 Month) $89.99; Sketch Plan (1 Year) $129.99; Report Plan (1 Year) $399.99; Estimate Plan (1 Year) $899.99 | Sketch Plan (1 Month) £12.99; Report Plan (1 Month) £39.99; Sketch Plan (1 Year) £129.99; Estimate Plan (1 Month) £89.99; Report Plan (1 Year) £399.99; Estimate Plan (1 Year) £899.99 | Sketch Abo (1 Monat) 12,99 €; Report Abo (1 Monat) 39,99 €; Sketch Abo (1 Jahr) 129,99 €; Estimate Abo (1 Monat) 89,99 €; Report Abo (1 Jahr) 399,99 €; Estimate Abo (1 Jahr) 899,99 € | Sketch Plan (1 Month) 149.000đ; Report Plan (1 Month) 479.000đ; Sketch Plan (1 Year) 1.499.000đ; Estimate Plan (1 Year) 10.999.000đ; Report Plan (1 Year) 4.790.000đ; Estimate Plan (1 Month) 1.079.000đ | [US](https://apps.apple.com/us/app/id427424432) · [GB](https://apps.apple.com/gb/app/id427424432) · [DE](https://apps.apple.com/de/app/id427424432) · [VN](https://apps.apple.com/vn/app/id427424432) |

- Paid-upfront: TurboScan Pro costs $12.99 upfront — [iTunes lookup / App Store](https://apps.apple.com/us/app/id342548956)
- Apps with no App Store IAPs shown: Scaniverse (sells cloud plans on the web), Luma 3D Capture — [Scaniverse](https://apps.apple.com/us/app/id1541433223); [Luma](https://apps.apple.com/us/app/id1615849914)
- Trial lengths stated in IAP names or descriptions:
  - Coin ID: "Weekly access (3 days trial)" — [US](https://apps.apple.com/us/app/id1665672552)
  - Gauth: 3-day trials on quarterly, annual and (in Vietnam) weekly plans — [US](https://apps.apple.com/us/app/id1542571008)
  - Picture Insect, Rock Identifier, CoinSnap: yearly with a 7-day trial — [Picture Insect](https://apps.apple.com/us/app/id1461694973)
  - PictureThis: 7-day trial — [IdentifyThis](https://identifythis.app/is-picture-this-app-free)
  - Cal AI: 3-day trial — [CNBC](https://www.cnbc.com/2025/09/06/cal-ai-how-a-teenage-ceo-built-a-fast-growing-calorie-tracking-app.html)
- Europe pricing examples (same product, US / UK / Germany):

| Product | US | UK | Germany |
|---|---|---|---|
| Adobe Scan Premium monthly | $9.99 | £9.99 | €10.99 |
| CamScanner "Premium Account (1 year)" | $59.99 | £58.99 | €66.99 |
| Genius Scan Ultra | $39.99 | £39.99 | €44.99 |
| PictureThis Pro | $39.99 | £34.99 | €34.99 |
| Rock Identifier Premium | $39.99 | £29.99 | €29.99 |
| 3d Scanner App yearly | $69.99 | £69.99 | €79.99 |
| 3d Scanner App weekly | $4.99 | £4.99 | €5.99 |
| Polycam Basic yearly | $149.99 | £149.99 | €179.99 |
| Polycam Pro yearly | $199.99 | £149.99 | €199.99 |
| Cal AI top "Unlimited" | $29.99 | £29.99 | €34.99 |
| Coin ID weekly | $6.99 | £6.99 | €7.99 |
| magicplan (all plans) | $12.99 / $129.99 / $899.99 | £ same digits | € same digits |

  Source: [storefront pages as linked in the table above](https://apps.apple.com/de/app/id1199564834)
- Vietnam examples:
  - Photomath Plus 229,000–299,000₫ (US $9.99).
  - Adobe Scan Premium monthly 229,000₫; Plus monthly 129,000₫; Plus yearly 499,000₫.
  - Genius Scan Ultra 999,000₫.
  - PictureThis Pro 689,000–909,000₫.
  - Gauth monthly 49,000₫, annual 299,000₫, weekly trial 29,000₫ (US $11.99 / $99.99).
  - TurboScan Premium 49,000₫ (US $14.99).
  - magicplan Sketch 149,000₫/mo (US $12.99); Estimate 10,999,000₫/yr.
  - Polycam Pro Yearly 2,499,000₫, while "Basic Yearly" shows 4,999,000₫ (an anomaly).
  - 3d Scanner App weekly 79,000–149,000₫.
  - Coin ID weekly trial plans 129,000–199,000₫. Coin ID also lists "Premium" at 1,999,000₫ and 5,999,000₫, probably lifetime unlocks.

  Source: [VN storefront pages](https://apps.apple.com/vn/app/id1542571008)
- Lifetime or one-time options found:
  - TurboScan Premium (one-time) — [App Store](https://apps.apple.com/us/app/id1017559099)
  - SwiftScan "Pro/VIP – Full Scanner App" — [App Store](https://apps.apple.com/us/app/id834854351)
  - iScanner lifetime via StackSocial — [StackSocial](https://www.stacksocial.com/sales/iscanner-app-lifetime-subscription)
  - Coin ID's high-priced VN "Premium" items (my inference) — [VN](https://apps.apple.com/vn/app/id1665672552)
- RevenueCat's 2026 data backs lifetime offers: "One in four apps offer a lifetime plan". Photo & Video has the highest share of subscription + lifetime combinations (33.0%). Non-AI apps use lifetime combinations more than AI apps (25.3% vs 17.9%) — [RevenueCat SOSA 2026](https://www.revenuecat.com/state-of-subscription-apps)
- Paywall patterns seen:
  - Hard paywall on the core AI output (Cal AI) — [App Store](https://apps.apple.com/us/app/id6480417616)
  - Onboarding paywall with a trial. Cal AI's founder said 20–25% of users who complete onboarding convert to a paid plan or a trial. Moving sign-in to the end of onboarding cut drop-off the most — [CNBC](https://www.cnbc.com/2025/09/06/cal-ai-how-a-teenage-ceo-built-a-fast-growing-calorie-tracking-app.html); [search summary](https://superwall.com/case-studies/cal-ai)
  - Win-back and "Return" price points (Gauth "Monthly – Win Back Offer", KIRI "Yearly Renewal Return") — [Gauth](https://apps.apple.com/us/app/id1542571008), [KIRI](https://apps.apple.com/us/app/id1577127142)
- Cal AI economics: about $30M revenue in 2025 and about $5.7M in January 2026 (~$50M annualized) before its sale to MyFitnessPal — [Yuanchang blog (secondary)](https://yuanchang.org/en/posts/zach-yadegari-cal-ai-50m-exit/)
- Using Superwall paywall experiments, Cal AI improved trial-to-paid by 31% and grew monthly revenue more than 3× in 10 months — [Superwall case study (via search)](https://superwall.com/case-studies/cal-ai)

### Inferences
- Rough VND conversions assume about 26,000 VND = 1 USD (an approximate rate, not sourced here). On that basis, most apps charge Vietnam roughly the US price (Adobe 229,000₫ ≈ $8.8; Genius 999,000₫ ≈ $38). A few localize to about 10–30% of the US price: Gauth annual 299,000₫ ≈ $11.5 vs $99.99; TurboScan 49,000₫ ≈ $1.9 vs $14.99; magicplan Sketch 149,000₫ ≈ $5.7 vs $12.99.
- In Europe, € prices are usually equal to or slightly above the $ digits. Once VAT is removed (19% in Germany), net proceeds per € are lower than the headline figure suggests. For Europe-first positioning, annual plans priced at about €29.99–€44.99 with a 7-day trial match what incumbents charge.
- Listing many same-name price variants (PictureThis, Rock Identifier, Photomath, Cal AI "Unlimited") is standard practice for running price A/B tests through different product IDs.

### Gaps
- The App Store does not show billing periods for unnamed IAPs, so some cells (for example "Adobe Scan Premium $49.99" or "Scanner Pro Plus $19.99") cannot be mapped to a period with certainty.
- I did not capture France, Italy, Spain or other EU storefronts. Germany is used as the EUR proxy.
- There is no official VND FX rate in this note.

---

## Key Question 3 — Industry benchmarks: conversion, trial-to-paid, retention, refunds, RPI/LTV (with Europe and SEA/Vietnam)

### Takeaway
RevenueCat's 2026 report (published 19 Mar 2026, 2025 data, 115k+ apps, $16B+):
- Median D35 download-to-paid: **~2–2.6%** in Western Europe and North America, **1.4%** in IN/SEA.
- Hard paywalls convert **10.7% vs 2.1%** for freemium, and reach **$3.09 vs $0.38** revenue per install (RPI) at D60, with the same one-year retention.
- **Photo & Video has the worst trial-to-paid (22.2%)**, and 68% of its trials are 4 days or shorter. Longer trials convert better (42.5% for 17–32 days).
- Refunds cluster at **3–4%**, but reach 7.7% in IN/SEA.
- Western Europe has the highest Y1 realized LTV per payer by user geography ($26.64).

Adapty's 2026 report (16k apps, $3B):
- Weekly plans produce **55.5%** of revenue.
- Utilities: 13.8% install-to-trial and 26.2% trial-to-paid.
- Europe is now the **most expensive region**: monthly prices are 39% above North America.

### Cited Findings

**RevenueCat — State of Subscription Apps 2026** ([report](https://www.revenuecat.com/state-of-subscription-apps); [10-minute summary, 19 Mar 2026, updated 22 Apr 2026](https://www.revenuecat.com/blog/growth/subscription-app-trends-benchmarks-2026))

*Category buckets.* RevenueCat groups categories:
- "Utilities" = Weather, Reference, Utilities, Finance, Tools.
- "Productivity" = Graphics & Design, Art & Design, Developer tools.
- "Photo & Video" = Photo & Video, Photography, video editors.
- "Business" and "Education" are separate buckets.

Scanner apps sit mostly in the App Store Business category. Identifier and math apps sit in Education or Reference. 3D apps sit in Photo & Video — [iTunes lookup](https://itunes.apple.com/lookup?id=1199564834,1252497129,1532482376&country=us)

*Funnel*
- D30 download-to-trial medians:
  - By category: Business 9.1%, Health & Fitness 6.9%, Education 6.5%, Utilities 6.5%, Gaming 4.4%. Most non-gaming categories fall between 5% and 6%.
  - By region: Western Europe 5.0%.
- AI apps: 8.5% vs 5.6% for non-AI apps.
- Trial-to-paid medians:
  - By category: Travel 43.5%, Health & Fitness 37.7%, Gaming 25.0%, **Photo & Video 22.2%** (lowest; top quartile above 33.1%).
  - By region: **Western Europe 29.7%**. IN/SEA is below half the rate of North America, APAC and Western Europe.
  - By trial length: ≤4 days 25.5%; 5–9 days 37.4%; 17–32 days 42.5%.
- Trial-length usage: 46.5% of apps now use trials of 4 days or less (42.1% a year earlier). In Photo & Video, 68.2% of trials are 4 days or less.
- Trial cancellations:
  - 3-day trials: 55.4% cancelled on Day 0; 84% cancelled by Day 1.
  - 7-day trials: 39.8% cancelled on Day 0.
  - About 50.6% of paid conversions happen on Day 0. Western Europe has the longest tail: 21.2% of conversions come in week 6 or later.
- D35 download-to-paid:
  - Hard paywall 10.7% vs freemium 2.1%.
  - By category: Health & Fitness 2.9%, Business 2.6%, Gaming 1.0%.
  - By region: North America 2.6% (2.56%), **Western Europe 2.0%**, LatAm 1.5%, IN/SEA 1.4% (1.37%).

*Revenue per install and LTV*
- RPI D14: Health & Fitness $0.48; Business $0.31; Education $0.30; Gaming $0.08.
- RPI D14 by region: North America $0.38; APAC $0.28; **Western Europe $0.25**; IN/SEA $0.08.
- RPI D60 by region: North America $0.55; **Europe $0.33**; IN/SEA $0.11.
- RPI by paywall type: hard paywall $2.32 at D14 and $3.09 at D60, vs freemium $0.27 and $0.38.
- RPI by leading plan: apps where yearly is the most popular plan earn $0.36 at D14 and $0.46 at D60; weekly-led apps earn $0.19 and $0.32.
- Realized LTV (RLTV) per payer:
  - Y1 by category: Health & Fitness $35.64; Productivity $24.95; Education $22.82; Gaming $11.22.
  - By user region: **Western Europe $17.89 after month 1 and $26.64 after year 1** (just above North America); IN/SEA $10.59 and $19.32.
  - By developer HQ, Y1: North America $32; Western Europe $25; global $23; IN/SEA $14.
- AI apps have a Y1 RLTV of $30.16 vs $21.37 for non-AI apps, but churn about 30% faster. Photo & Video is 61.4% AI-powered.

*Pricing and plans*
- Median prices: weekly $5.99; monthly $10; yearly $34.80 (up from $31.60).
- By region:
  - Weekly $4.61–$7.03 (Western Europe highest).
  - Yearly up to $39.99 in North America; Western Europe $39.44.
  - IN/SEA prices are about 45–50% of North America's.
- Education has the highest yearly median ($44.99).
- Plans sold: 42% monthly and 34% yearly overall; Western Europe 41% monthly and 35% yearly.
- Paywall design in Photo & Video: weekly plans are shown on 33% of paywalls (highest of any category). Only 25.0% of its paywalls include cancel-assurance text.
- Intro-offer discounts: median −50.1%; Utilities −63%.

*Retention and renewals*
- First renewal: weekly 35–58%; monthly 53–61%; annual 23–40% (Productivity lowest at 23%, Business highest at 40%).
- Month 1 accounts for 35% of all annual-plan cancellations.
- Hard paywall vs freemium one-year retention: 27% vs 28%.

*Refunds*
- Most categories: 3–4%. Productivity 4.7% (highest); Travel 2.5%.
- By region: IN/SEA 7.7% vs North America 3.4%.
- Each step up in price tier adds about 1 point.
- AI 4.2% vs non-AI 3.5%.
- Hard paywall 2.5% vs freemium 2.9% ("probably just noise").
- App Store cancellations: 82.9% are voluntary unsubscribes, 15.2% billing errors.

*Web revenue*
- 3.2% of revenue globally; 4.9% in North America; 0.8% in IN/SEA.
- 41% of top-tier apps have some web revenue.

*Reactivation*
- Photo & Video: 20% on monthly plans vs 8% on annual.

**RevenueCat — State of Subscription Apps 2025** ([report](https://www.revenuecat.com/state-of-subscription-apps-2025/))
- Hard paywall D35 download-to-paid: 12.11% median vs 2.18% for freemium.
- 2–5% of payers claim a refund.
- **Hard paywall refunds 5.8% vs freemium 3.4%.** This contrasts with the 2026 finding of 2.5% vs 2.9%.
- Western Europe and APAC refund rates were below 3.0%.
- Weekly plans: fewer than 5% of subscribers reach month 6; 12-month retention is below 6.5%.
- Photo & Video had the highest milestone success: 27.57% of new apps reached $1k monthly revenue and 8.75% reached $10k within 2 years.
- Photo & Video iOS cost per install (CPI) was above $14 in the top quartile.

**Adapty — State of In-App Subscriptions 2026** ([report hub](https://adapty.io/state-of-in-app-subscriptions/); [key findings, 13 Mar 2026](https://adapty.io/blog/mobile-app-monetization-2026/))
- Revenue share by plan: weekly 55.5% (43.3% in 2023); annual 22.5%; monthly 11.7%.
- Install-to-trial at upper-mid pricing: weekly 9.8% vs annual 1.8%.
- Weekly + trial LTV grows from $7.40 at D0 to $54.50 at D380. Trial users renew weekly plans at R1 59.2% vs 37.0% for direct buyers.
- 89.4% of trials start on Day 0.
- Trial LTV premium: Utilities +85.1%; Productivity −13.7%.
- **Europe**:
  - Monthly price $15.25 vs North America $10.95 (+39%; the gap was 6% in 2023).
  - European prices rose 18% year over year. Europe is now the most expensive region.
  - Europe D380 annual retention 21.3% vs North America 20.0%.
  - Annual plans "win in Europe and APAC" (search summary).
- Top one-year LTV markets: Switzerland $28.5, Qatar $27.5, Israel $27.0.
- iOS takes 84.75% of subscription revenue.
- Top 10% of apps take 94.5% of revenue.
- Hard vs soft paywall — [Adapty, 13 Mar 2026](https://adapty.io/blog/high-performing-paywall-2026/):
  - Hard paywalls give 21% higher LTV (median $41.90 vs $20.00). Soft paywalls convert about 50% better.
  - Conversion by placement: onboarding with trial 1.35% vs in-app with trial 0.89%.
  - Web vs in-app checkout: in-app converts 1.60% vs 1.10% on web, with LTV $40.10 vs $35.80.
  - Localization tests have the highest reported LTV-uplift/win rate (62.3%). Price changes: 45.5%.
- **Utilities benchmarks** — [Adapty, 29 Jun 2026](https://adapty.io/blog/utilities-app-subscription-benchmarks/):
  - Install-to-trial 13.8%; trial-to-paid 26.2%; first renewal 61.7%.
  - Weekly plans give 74% of revenue.
  - Median prices: weekly $7.48, monthly $12.99, annual $38.42.
  - **Europe utilities annual prices +70.5% over two years.**
  - 84.7% of apps use trials. Discount usage is 1.2%.
  - Best setup: weekly $5.99 with a 3-day trial (1.5× average LTV).
  - Install LTV $1.09; 12-month trial LTV $68.90.
- **App-to-web in the US after the injunction** — [Adapty, 25 Jun 2026](https://adapty.io/blog/app-to-web-paywalls-ios-one-year-data/):
  - Case A (30% tier): web converted 26% worse (3.69% vs 4.95%), but web ARPPU was twice as high. Net proceeds per viewer +53%.
  - Case B (Small Business Program 15% tier): web converted 55% better, but ARPPU was 20% lower. Net proceeds per viewer −9%.
  - Adapty's conclusion: savings of about 25 points (30% vs roughly 5% for Stripe) justify web checkout. Savings of about 10 points under the Small Business Program often do not.

### Inferences
- If the planned app is filed in **Business or Utilities** (scanner/measurement), the reference medians are:
  - Download-to-trial about 6.5–9% (RevenueCat), or up to 13.8% for Utilities (Adapty, onboarding-heavy dataset).
  - Trial-to-paid about 26–30%.
  - D35 download-to-paid about 2–2.6%.
  - D14 RPI about $0.25–$0.38 (Western Europe / North America).
- If the app is filed in **Photo & Video** (3D/LiDAR), expect weaker trial-to-paid (about 22%) and a heavier weekly-plan mix.
- For a Europe-first launch:
  - Western Europe has lower RPI than North America ($0.25 vs $0.38 at D14) but slightly higher LTV per payer, and longer conversion tails.
  - Annual plans and longer trials are relatively favored in Europe.
  - European prices have risen quickly, which leaves room to price at the European medians rather than below US levels.
- SEA/Vietnam should be treated as a volume market (low RPI, 7.7% refunds, higher appetite for lifetime purchases), with localized prices at about 45–50% of US levels or lower.
- The two reports conflict on AI trial-start rates: RevenueCat says AI apps start more trials (8.5% vs 5.6%); Adapty says fewer (5.31% vs 10.92%). The report writer should present both.

### Gaps
- RevenueCat's online report does not break out trial-to-paid, retention or refunds for **Utilities, Business or Education** individually. The 330-page PDF has 11 category breakouts, but I did not access it.
- I found no Vietnam-specific benchmark (only the IN/SEA aggregate).
- I did not find Superwall's own quantitative benchmark report; only case studies are cited.
- Qonversion and Apphud 2025–2026 reports were not reviewed.

---

## Key Question 4 — Apple platform rules that shape monetization (Small Business Program, US anti-steering after Epic v. Apple, offer codes, win-back, retention offers)

### Takeaway
- The 15% Small Business Program rate is the default for new or small developers.
- In the US storefront, apps may now include buttons and links to web checkout with **0% Apple commission** for now. However, non-reader apps must still offer IAP alongside the web option, and paywalls must not be deceptive.
- The courts are still setting a future cost-based link-out commission. Apple has proposed 15% / 10% / 5%.
- Apple added retention offers in the Settings cancellation flow (2025) and broadened offer codes, and it retired IAP promo codes on 26 Mar 2026.

### Cited Findings
- **Small Business Program**: developers with up to $1M in proceeds in the prior calendar year, and new developers, pay a 15% commission on paid apps and IAP — [Apple Developer](https://developer.apple.com/app-store/small-business-program/)
- **US storefront steering**: Guideline 3.1.1(a) says link entitlements "are not required for developers to include buttons, external links, or other calls to action in their United States storefront apps". Guideline 3.1.3 exempts "apps on the United States storefront" from the ban on encouraging other purchase methods — [App Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)
- **Ninth Circuit, 11 Dec 2025**:
  - Upheld the contempt finding and the dynamic-link approval.
  - Reversed the total ban on commissions for linked-out purchases and on restrictions on how links look, calling them "overbroad".
  - Apple may charge a commission tied to genuine costs and may enforce link-parity rules — [Fenwick](https://www.fenwick.com/insights/publications/ninth-circuit-largely-upholds-ruling-in-epic-v-apple); [Justia opinion](https://law.justia.com/cases/federal/appellate-courts/ca9/25-2935/25-2935-2025-12-11.html)
- **Supreme Court**:
  - Agreed on 30 Jun 2026 to hear Apple's appeal on the contempt finding. The review is limited to the "spirit vs text" question, and arguments open in the October term — [AppleInsider, 14 Sep 2026](https://appleinsider.com/articles/26/09/14/apple-standing-its-ground-in-epics-app-store-fee-suit)
  - On 14 Aug 2026, Justice Kagan denied Apple's request for a stay, so the district court continues setting a "permissible commission rate" — [MacDailyNews, 14 Aug 2026](https://macdailynews.com/2026/08/14/u-s-supreme-court-clears-path-for-app-store-commission-showdown-as-apple-must-defend-its-rates-in-lower-court/)
  - Apple's August 2026 proposal: 15% standard; 10% for Video/News/Mini Apps partners and subscription renewals; 5% for Small Business Program apps. Epic rejected it. **Apple currently charges 0% on US link-out purchases** — [AppleInsider](https://appleinsider.com/articles/26/09/14/apple-standing-its-ground-in-epics-app-store-fee-suit); [MacDailyNews](https://macdailynews.com/2026/08/14/u-s-supreme-court-clears-path-for-app-store-commission-showdown-as-apple-must-defend-its-rates-in-lower-court/)
- **IAP must remain**: "apps that are not classified as reader apps also have to include an in-app purchase option". Cal AI was pulled in April 2026 for dropping IAP in favor of Stripe. It was reinstated after fixes — [MacRumors, 21 Apr 2026](https://www.macrumors.com/2026/04/21/apple-cal-ai-app-store-removal/); [TechCrunch](https://techcrunch.com/2026/04/21/apples-cal-ai-crackdown-signals-its-still-policing-the-app-store/)
- **Retention offers**: since July 2025, developers can show a static message, dynamic progress, or a special offer when a user tries to cancel in Settings → Subscriptions (the Retention Messaging API) — [9to5Mac, 23 Jul 2025](https://9to5mac.com/2025/07/23/apple-retention-offers-in-app-purchase/)
- **Offer codes, promo codes and win-back offers**:
  - Offer codes now work on consumables, non-consumables, auto-renewable and non-renewing subscriptions.
  - IAP promo codes were retired on 26 Mar 2026 in favor of offer codes — [Appbot (search summary)](https://appbot.co/blog/apple-offer-code/)
  - Win-back offers for lapsed subscribers are supported in StoreKit and App Store Connect — [Apple docs](https://developer.apple.com/documentation/storekit/supporting-win-back-offers-in-your-app)
- **Free trials for non-subscription apps**: allowed through a $0 non-consumable named "XX-day Trial". The app must state the trial length, what ends, and the downstream charges — [Guideline 3.1.1](https://developer.apple.com/app-store/review/guidelines/)

### Inferences
- A small offline-first developer on the 15% Small Business Program gains little by moving US users to web checkout. Adapty's case showed −9% net proceeds per viewer. Keeping IAP as the main path and using offer codes, win-back offers and retention messaging to protect renewals is likely to pay off better.

### Gaps
- The final US link-out commission rate is not decided (as of 27 Sep 2026). The Supreme Court's merits decision is still pending.

---

## Key Question 5 — EU-specific monetization rules (DMA terms, VAT, consumer law) and UK

### Takeaway
From **1 Oct 2026**, every EU developer moves to one set of Apple terms:
- IAP: **26%**, or **15%** for Small Business Program members and for subscriptions after year one.
- Alternative in-app payment processing: 20% / 10%.
- Link-out ("out-of-app offers"): 15% / 10%, charged only on sales within 7 days of the link tap.
- Alternative distribution: 5% Core Technology Commission.
- The per-install Core Technology Fee, the initial acquisition fee and the store services fee are abolished.

Apple remains merchant of record for IAP and handles VAT and the 14-day withdrawal right. A developer that sells through web checkout takes on VAT and the new **EU withdrawal-button** duty (in force from 19 Jun 2026) itself. The UK's DMCC subscription rules are expected in spring 2027.

### Cited Findings
- **Apple EU terms from 1 Oct 2026**:
  - IAP 26% standard; 15% for the Small Business Program, the Mini Apps and Video Partner programs, and auto-renewable subscriptions after the first year.
  - Alternative payment processing 20% / 10%.
  - Link-outs 15% / 10%.
  - 5% Core Technology Commission "on digital transactions in apps distributed outside the App Store".
  - "The new terms also eliminate the initial acquisition fee and store services fee" — [Apple Newsroom, Aug 2026](https://www.apple.com/newsroom/2026/08/apple-announces-changes-for-apps-in-the-european-union/)
- The Store Services Commission on out-of-app offers applies only to "sales made within 7 days of the link tap".
- Developers must keep their chosen payment options for 12 months.
- Small alternative-marketplace operators (under €10M global revenue and under €1M lifetime EU marketplace revenue) get a CTC waiver.
- Kids-category apps cannot link out. Users under 13 cannot be offered web purchases, and users aged 13–17 need a parental gate.
- The earlier "Alternative Terms Addendum" and the "External Purchase Link Entitlement (EU) Addendum" are superseded by Attachment 14 of the Apple Developer Program License Agreement — [Apple Developer: apps in the EU](https://developer.apple.com/support/apps-in-the-eu)
- The interim 2025 model (announced 26 Jun 2025) introduced Store Services Tier 1/Tier 2, an initial acquisition fee and a 5% CTC replacing the €0.50/install Core Technology Fee. A single business model was planned for 1 Jan 2026, but was delayed — [Michael Tsai](https://mjtsai.com/blog/2025/06/27/eu-app-store-tiers-and-core-technology-commission/)
- **VAT**: Apple acts as merchant of record for App Store sales and calculates, collects and remits VAT. Developer proceeds are calculated from the price after tax, so EU developers receive "just under 60%" of the displayed price at a 30% commission — [Adapty revenue & VAT guide (search summary)](https://adapty.io/blog/how-much-money-do-apps-make/)
- For EU alternative payments or link-outs, developers must provide an EU VAT ID showing they are registered to handle VAT — [App Store Connect Help](https://developer.apple.com/help/app-store-connect/manage-tax-information/provide-tax-information-for-alternative-payment-options/)
- **14-day withdrawal right on App Store purchases**:
  - Apple lets UK/EU customers cancel within 14 days of the receipt, through Purchase History, without giving a reason.
  - For subscriptions, "any refund will relate only to the period of access already paid for but not yet provided" — [Apple Media Services Terms (UK)](https://www.apple.com/uk/legal/internet-services/itunes/uk/terms.html); [Apple right of withdrawal PDF](https://www.apple.com/legal/internet-services/itunes/uk/rightofwithdrawal-uk.pdf)
- **EU withdrawal button (Directive (EU) 2023/2673)**:
  - Applies from **19 Jun 2026** (transposition deadline 19 Dec 2025).
  - Covers B2C contracts concluded through online interfaces, including websites, **mobile apps** and software, regardless of where the seller is based.
  - Requirements: a clearly labeled function (for example "withdraw from the contract here") available throughout the 14-day period, two-step confirmation, and confirmation on a durable medium without undue delay — [Arnold & Porter, 28 May 2026](https://www.arnoldporter.com/en/perspectives/advisories/2026/05/eu-withdrawal-button-uk-subscription-rules-and-data-protection-risks-for-us-online-sellers); [Heuking](https://www.heuking.de/en/news-events/newsletter-articles/detail/new-cancellation-button-what-companies-must-implement-by-june-19-2026.html)
- **UK DMCC Act subscription rules** (expected spring 2027):
  - Pre-contract disclosure of trial price, renewal date and how to cancel.
  - **Two 14-day cooling-off periods**: one at the start of the contract, one after the trial/discount ends or at renewal.
  - Renewal reminders and easy exit. Non-UK businesses targeting UK consumers are in scope, including mobile apps — [Arnold & Porter](https://www.arnoldporter.com/en/perspectives/advisories/2026/05/eu-withdrawal-button-uk-subscription-rules-and-data-protection-risks-for-us-online-sellers)

### Inferences
- For EU IAP sales, Apple is the seller of record, so Apple's Purchase History "cancel" flow and the App Store's own subscription management probably satisfy the withdrawal and cancellation duties for Apple-billed subscriptions. If the app adds EU or US **web checkout** (Stripe or Paddle), the developer becomes the seller and must implement VAT/OSS registration, the withdrawal button and, for UK customers from 2027, reminder and cooling-off flows.
- On an Apple-billed subscription after 1 Oct 2026, the EU link-out commission (15%, or 10% for SBP developers and year-two renewals) plus payment and VAT costs means web checkout saves little compared with IAP at 15% under the SBP.
- A worked example for Germany: a €9.99 price includes 19% VAT, so about €8.39 is net of VAT. After a 15% SBP commission, proceeds are about €7.13. (My own calculation, from the VAT and commission rules cited above.)

### Gaps
- I did not verify in this session the exact percentages of the interim 2025 EU fees (initial acquisition fee, Store Services Tier 1/Tier 2). They are superseded on 1 Oct 2026 in any case.
- I did not research country-specific rules such as Germany's "Kündigungsbutton" (§312k BGB) or France's cancellation rules.
- I found no authoritative guidance on whether the EU withdrawal-button duty applies to Apple, as merchant of record, rather than to the developer for IAP-billed subscriptions.
- I found no data on EU web-checkout conversion under the new terms (they take effect 1 Oct 2026).

---

## Key Question 6 — Which paywall patterns are considered deceptive and get rejected (Guidelines 3.1.2, 5.6)?

### Takeaway
Apple enforces "clear billed amount first".

Patterns that get rejected:
- Showing a normalized weekly or monthly price larger than the amount actually billed.
- **Trial toggles** (enforcement since mid-January 2026).
- Hiding auto-renewal.
- Chained second subscription offers after the user declines.
- Removing IAP in favor of web checkout.
- Bait-and-switch plans.

Guideline 5.6 also bans "raising prices in a tricky manner" and tricking users into unwanted purchases.

### Cited Findings
- Guideline 3.1.2(a): "Apps that attempt to scam users will be removed… This includes apps that attempt to trick users into purchasing a subscription under false pretenses or engage in bait-and-switch and scam practices". Subscriptions must last at least 7 days, and "If you are changing your existing app to a subscription-based business model, you should not take away the primary functionality existing users have already paid for" — [App Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)
- Guideline 3.1.2(c): "Before asking a customer to subscribe, you should clearly describe what the user will get for the price… How much cloud storage?… Ensure you clearly communicate the requirements described in Schedule 2" — [App Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)
- Guideline 5.6: "Apps should never prey on users or attempt to rip off customers, trick them into making unwanted purchases, force them to share unnecessary data, raise prices in a tricky manner, charge for features or content that are not delivered, or engage in any other manipulative practices within or outside of the app" — [App Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)
- Toggle paywalls, where a switch flips between annual with no trial and weekly with a trial and defaults to the paid annual plan, have been rejected under 3.1.2 since mid-January 2026 with no prior notice. Apple's reason: the toggle "hides trials from users who don't engage with it".
- Compliant alternatives Adapty lists: explicit trial timelines ("Day 7: you're charged"), side-by-side plans with trial badges, and segmented paywalls — [Adapty, 11 Feb 2026](https://adapty.io/blog/your-toggle-paywall-is-about-to-get-rejected/)
- A paywall that shows the weekly-calculated price more prominently than the billed amount violates 3.1.2(c). Font, size, color and location of the billed amount all count. Normalized prices (such as "$4.16/mo") are allowed only if the full billed amount ("$49.99/yr") is clearly shown — [RevenueCat docs: getting paywalls approved](https://www.revenuecat.com/docs/tools/paywalls/creating-paywalls/app-review); [RevenueFlo](https://revenueflo.com/blog/common-ios-paywall-rejections-and-the-fixes-that-work)
- The Cal AI takedown in April 2026 cited:
  - Bypassing IAP (Stripe only).
  - "Displaying the weekly calculated pricing more prominently than the amount the user would be billed".
  - "A free trial toggle that did not make the subscription's automatic renewal clear".
  - Prompting users who declined to enter "a second, different subscription purchase flow".
  
  The app was reinstated after fixes — [MacRumors](https://www.macrumors.com/2026/04/21/apple-cal-ai-app-store-removal/); [Adapty](https://adapty.io/blog/app-to-web-paywalls-ios-one-year-data/)

### Inferences
- A compliant paywall for the report's recommendation should have:
  - The billed amount and period as the largest price text ("€29.99/year, renews yearly").
  - The trial length plus the date and amount of the first charge.
  - Plans side by side (no toggle).
  - A visible close control on soft paywalls.
  - A single decline path (no chained offers, unless this is Apple's own win-back or retention-offer machinery).
  - A feature list that states limits in concrete terms (e.g., "unlimited exports, OBJ/USDZ/DXF, OCR in N languages").
- Converting an existing free app to a subscription (as 3d Scanner App did after its 2025 sale) is exposed to the "don't take away functionality existing users paid for" clause of 3.1.2(a), and to user backlash.

### Gaps
- Apple has not published official written guidance on the January 2026 toggle enforcement; evidence comes from developer reports (Adapty).
- I found no official Apple statistics on paywall-related rejection counts.
