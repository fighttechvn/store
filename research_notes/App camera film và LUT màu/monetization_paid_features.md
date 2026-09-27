# Monetization, pricing and paid features of film-camera / film-filter / preset / LUT apps (state as of 2026-09-27)

Scope and method notes (read first):
- All App Store prices below were scraped on 2026-09-27 from each app's public product page (`https://apps.apple.com/{cc}/app/id{ID}`), block "In-App Purchases". Apple only lists up to 10 IAP SKUs per page, and it does not say whether a SKU is weekly/monthly/yearly unless the developer put it in the SKU name. Durations are therefore only what the SKU name says.
- Google Play prices are the "$x – $y per item" range that the Play web listing embeds for a `gl=` country (`https://play.google.com/store/apps/details?id={pkg}&hl=en&gl={CC}`), scraped on 2026-09-27. Play does not list individual SKUs on the web. For `gl=DE` and `gl=GB` the listing returned **no** price range for any app, so there is no EUR/GBP Play data.
- The "Released" date in the Play data is the listing's first-release date, not the last update.
- Revenue and download estimates come from the public meta description of Sensor Tower overview pages ("Last month's estimates were …"), fetched 2026-09-27, so "last month" is probably Aug 2026. The figures were identical for `country=US`, `VN` and `JP`, so they are **worldwide, per platform** (iOS page vs Android page) and not per country. They are **estimates**.
- The reference apps (Filmode on iOS, Filmode Vibe `app.filmode`, FilCam `app.filmode.filcam`) are published by "Tran Trung Hieu" / "Trung-Hieu Tran", the same team this research is for.
- Official Dazz Cam (DAZZ PTE. LTD.) exists on iOS only. On Google Play, "Dazz Cam" (`com.vintage.camera.pro`, MA CLO APPS) and "Dazzil Cam" (`com.camerafilm.lofiretro`) are look-alike apps from other developers. At least one web review (parallaxaview.com) describes such a clone as "Dazz Cam", so third-party Dazz price claims are unreliable.

## Q1. Paywall matrix: what each app gives free vs what is paid

### Takeaway
Almost every film-camera/filter app is freemium. The free tier is a small starter set of looks or cameras. The paywall gates the full catalogue of looks/cameras, plus some of: import from gallery, pro tools (masks, curves, RAW, batch), video export or 4K, and AI tools. Watermarks and ads are used by lower-tier clones and by Asian "cute cam" apps (FIMO, OldRoll, ProCCD, 1998 Cam on Android). Premium Western editors (VSCO, Darkroom, Tezza, Afterlight, RNI, Dehancer) do not use watermarks; they gate by content and export. Several indies explicitly advertise "no watermark / no ads" as a differentiator: Filmode, FilCam, 1998 Cam on iOS, VN, and Hipstamatic ("NO ADS. NO TRACKING").

### Cited Findings

**Reference apps (own team)**
- **Filmode – Film & LUT Editor (iOS, id6791145420).**
  - Free: 12-frame "roll" shooting; Basic/Cinematic/Film/Selfie collections, each previewed on the user's own photo; import of your own **.cube and .xmp** files; color-match preview. "Free looks export at full size with no watermark. No sign-up."
  - Pro: "every look, batch edit, lens optics, 24 and 36-frame rolls, 4K video and watermark-free video export", and it "turns the [color] match into a reusable look or exports it as a LUT". So video export is watermarked on the free tier.
  - Plans: Annual (free trial "when offered"), Monthly, Lifetime.
  - [App Store US](https://apps.apple.com/us/app/id6791145420)
- **Filmode Vibe — Film Camera (Android, `app.filmode`).**
  - Free: "No ads and no watermark, ever"; the cameras, effects, editor, photobooth, board and **18 looks (Basic and Retro)**, plus imported .cube LUTs and presets.
  - Pro: "adds 25 more looks (Cinematic, Film and Selfie) and the two frame-stacking drives, long exposure and light trails". Every Pro look "previews live in the viewfinder first; only keeping the shot asks", so the paywall triggers at save.
  - Plans: Pro is "monthly, yearly, or a one-time lifetime unlock". Clips are capped at 15 s by design (a product limit, not a paywall).
  - [Google Play](https://play.google.com/store/apps/details?id=app.filmode&hl=en&gl=US)
- **FilCam: Pro Manual RAW Camera (Android, `app.filmode.filcam`).**
  - Free: "Manual controls, RAW DNG and film LUTs are free", plus .cube import; no ads or watermark.
  - Pro: night mode, bracketing, focus stacking, intervalometer, long exposure (up to 30 s) and light trails.
  - Plans: "monthly, yearly with a 7-day free trial, or a one-time lifetime unlock".
  - [Google Play](https://play.google.com/store/apps/details?id=app.filmode.filcam&hl=en&gl=US)

**Retro / film "camera" apps**
- **Dazz Cam (iOS, DAZZ PTE. LTD., id1422471180).**
  - Paid: "Join Dazz Pro to access all cameras and accessories". Cameras and accessories are also sold one by one ("Dazz S Classic", "Dazz Camera NT16", "Dazz Exp Camera", "Dazz Inst SQ", "Dazz Black Camera"; accessories "Dazz Flash Color", "Dazz ND Filter", "Dazz Fisheye Lens"), alongside "Dazz Pro" and "Dazz Pro One-Time Purchase".
  - Free: the exact number of free cameras is not stated on the store page.
  - [App Store US](https://apps.apple.com/us/app/id1422471180)
- **Huji Cam (Manhole, Inc.).**
  - Free: the camera itself.
  - Paid: a single IAP "Extra Options" ($0.99), which reportedly unlocks "Multiple Selection, Remove AD, and Import Photos" ([hujicam.com FAQ, via search snippet; page not fetched directly](https://hujicam.com/php/faq.php)).
  - Ads: the Android listing carries the "Contains ads" label ([Play](https://play.google.com/store/apps/details?id=kr.co.manhole.hujicam&hl=en&gl=US)).
  - The iOS app was last updated 2024-12-11 ([iTunes lookup](https://itunes.apple.com/lookup?id=781383622&country=us)).
- **1998 Cam – Vintage Camera (AAAI Studio LLC).**
  - iOS: "accessing Pro features—including all premium filters and effects—requires a paid subscription". It markets "No Watermark" and "100+ filters" ([App Store US](https://apps.apple.com/us/app/id1450480287)).
  - Android: "Some premium filters, effects, editing tools, layouts, templates, and exports may require a paid plan"; HD export "with no watermark"; the listing carries "Contains ads" ([Play](https://play.google.com/store/apps/details?id=com.aaai.cam1998&hl=en&gl=US)).
- **NOMO CAM.**
  - Model: per-camera shop ("all the cameras that you can purchase, download and use"). Several cameras are priced $0.00 (NOMO TOY F, ROMA, TOY K, FR2, 2007); others cost $0.99–$1.99.
  - NOMO PRO (1-year, "renewal price … USD 24.99") = use all cameras "unlimitedly", "exclusive membership-only cameras", "importing photos, turning off the film development time of INS cameras" ([App Store US](https://apps.apple.com/us/app/id1362548649)).
- **Kapi Cam – Y2K & CCD Camera (TETRAS.AI / "Sensevideo" on Play).**
  - Plans: weekly, monthly, yearly and "Life-time" subscription SKUs ([App Store US](https://apps.apple.com/us/app/id6740760807)).
  - Reported change: review aggregators report user complaints that "previously free camera filters" were locked behind the subscription, plus "pervasive ads" ([marlvel.ai review summary, secondary/aggregator](https://marlvel.ai/apps/com-future-kapi)).
- **FIMO – Analog Camera.**
  - Model: per-film IAPs ("GOLD 200", "Portra 160NC", …) plus "fimo pro for 1 year".
  - Pro: "access to all features and paid editing materials. **Watermark and advertisements will be removed automatically**" ([App Store US](https://apps.apple.com/us/app/id1454219307)).
- **OldRoll – Vintage Film Camera.**
  - iOS: "Subscribe for unlimited access to all features and content"; per-camera SKUs such as "Unlock TOY S camera" ([App Store US](https://apps.apple.com/us/app/id1570093460)).
  - Android: listing labelled "Contains ads" ([Play](https://play.google.com/store/apps/details?id=com.accordion.analogcam&hl=en&gl=US)).
- **ProCCD – Digital Film Camera.**
  - Model: VIP weekly/yearly (SKU names include "Yearly VIP with Trial"), lifetime, and per-camera SKUs ("Original2", "IXUS210", "F71").
  - Ads: Android listing labelled "Contains ads" ([App Store US](https://apps.apple.com/us/app/id1616113199); [Play](https://play.google.com/store/apps/details?id=com.cerdillac.proccd&hl=en&gl=US)).
- **Hipstamatic Analog Camera.**
  - "The camera is free. Join the Hipstamatic® Camera Club to open the whole shelf. Every lens, every film, every camera … Your first month is on us." "NO ADS. NO TRACKING." ([App Store US](https://apps.apple.com/us/app/id1450672436)).
  - Classic Hipstamatic is paid upfront ($4.99) plus $0.99–$1.99 "HipstaPaks" ([App Store US](https://apps.apple.com/us/app/id342115564)).
- **FILCA – Vintage Film Camera.**
  - Paid upfront ($3.99 US), then more IAPs on top: "UPGRADE PRO" and film "SERIES" packs ([App Store US](https://apps.apple.com/us/app/id1436429074)).
- **DAZE CAM.** "Premium gives you full access to all features"; the free tier allows creating your own presets ([App Store US](https://apps.apple.com/us/app/id1464359734)).
- **Vintage Film Camera – Digicam (`filmcamera.vintagecamera.digitalcamera.retrocamera`, ZANKHANA PTE LTD).** 1M+ installs; "Contains ads" plus IAP $0.99–$19.99 ([Play](https://play.google.com/store/apps/details?id=filmcamera.vintagecamera.digitalcamera.retrocamera&hl=en&gl=US)).

**Preset / film-emulation editors**
- **VSCO.**
  - Starter (free): "16 of our most popular filters for free … without in-app purchases or subscriptions" ([Play](https://play.google.com/store/apps/details?id=com.vsco.cam&hl=en&gl=US)). The web plans page says "Edit with 15 of VSCO's most popular presets" ([vsco.co plans](https://www.vsco.co/subscribe/plans)); the two official pages disagree (15 vs 16).
  - Plus: "Advanced mobile editing with 200+ presets", video editing, "Ad-free experience".
  - Pro: "Unlimited AI Lab" (AI Remove/Upscale), client galleries, portfolio site, VSCO Canvas; "Pro available on iOS and desktop only". Free 7-day trial on both paid tiers ([vsco.co plans](https://www.vsco.co/subscribe/plans); [App Store US](https://apps.apple.com/us/app/id588013838)).
  - VSCO Capture (live-preset camera, RAW) is a separate free app with no IAP list ([App Store US](https://apps.apple.com/us/app/id6741483219)).
- **Lightroom (Adobe).**
  - Free: capture, organize and share, plus most basic editing and presets.
  - Premium: masking, Lens Blur, Generative Remove, RAW import from other cameras, cloud storage/sync ([PictureCorrect, secondary](https://www.picturecorrect.com/exploring-lightroom-mobile-free-features-vs-premium/); [nocamerabag review, secondary](https://nocamerabag.com/blog/review-adobe-lightroom-mobile-premium/)). I could not fetch Adobe's own FAQ (HTTP 403).
  - The iOS IAP list shows storage-tiered "Premium" plans (40GB/100GB, weekly/monthly/yearly) and a one-off "AI Photo Enhancer & Blur" SKU ([App Store US](https://apps.apple.com/us/app/id878783582)).
- **Tezza.** "40+ presets"; subscribers "get access to everything currently in the Tezza app as well as all new features, filters, photo/video effects". Tiers: Tezza, Tezza Pro, Tezza Luxe, Ambassador ([App Store US](https://apps.apple.com/us/app/id1393061654); [Play](https://play.google.com/store/apps/details?id=org.tezza&hl=en&gl=US)).
- **Afterlight.**
  - "300+ film-inspired presets", "30+ pro editing tools", dust/light-leak overlays and instant-film frames ([App Store US](https://apps.apple.com/us/app/id1293122457); [Play](https://play.google.com/store/apps/details?id=com.fueled.afterlight&hl=en&gl=US)).
  - PRO reportedly gives "300+ Filters including the new Film Presets and unlimited Fusion", with a 7-day free trial ([creatoreconomytools, secondary](https://creatoreconomytools.com/tool/afterlight)). Older reviews (Afterlight 2 era) said presets were free and only overlay/texture packs were paid ([colesclassroom, older](https://colesclassroom.com/afterlight-2-app-review/)); this is outdated.
- **Polarr.** LUT support is listed among global adjustments. Subscriptions: "Polarr Lite: $1.99 per month, $11.99 per year; Polarr Studio: $3.99 per month, or $23.99 per year", both "with a free trial" ([App Store US](https://apps.apple.com/us/app/id988173374)).
- **RNI Films.**
  - Free: "a generous introductory package of free film filters"; more "filter packages can be added via in-app purchase"; RAW editing ([App Store US](https://apps.apple.com/us/app/id1017098672)).
  - Pro: reported as "79 pence a month or a tenner a year", unlocking all film packs; saved presets limited to 2 without Pro ([myphotoyear, secondary, undated](https://myphotoyear.com/rni-films-app-pro/)).
- **Dehancer Film Emulation.**
  - Features: "86 film presets", Grain/Bloom/Halation, batch editing, RAW (beta), video editing ([App Store US](https://apps.apple.com/us/app/id6443648413)).
  - Gating is by export count. SKUs are "Unlimited Photo Export" and "Unlimited Export" (photo+video). A 2023 review said "exporting more than ten images requires a paid subscription" ([Dominey blog, Jan 2023 – older](https://blog.dominey.photography/2023/01/09/dehancer-for-ios-film-emulation-on-the-go/)).
- **Darkroom.** "Try every premium tool for as long as you like. **Export needs Darkroom+**." Plans: yearly $39.99 (free trial, Family Sharing), monthly $9.99 ("No trial"), one-time $99.99 ([darkroom.co/darkroom+](https://darkroom.co/darkroom+)). Old à-la-carte SKUs survive as "Legacy - …" IAPs ([App Store US](https://apps.apple.com/us/app/id953286746)).
- **Foodie (SNOW).** Subscription SKUs are "Foodie PRO Monthly" and "Foodie PRO annual subscription" ([App Store US](https://apps.apple.com/us/app/id1076859004)). Which features Foodie PRO gates was not found.
- **Prequel.** The description lists "FREE FEATURES" vs "PREQUEL GOLD SUBSCRIPTION: unlimited full access to all Prequel effects and filters" ([App Store US](https://apps.apple.com/us/app/id1325756279)).
- **Hipstamatic Classic.** Pro camera with RAW, "Always full resolution", "Share any favorite preset with other photographers", iCloud preset sync; paid upfront ([App Store US](https://apps.apple.com/us/app/id342115564)).

**Big all-in-one editors (AI-led)**
- **Picsart.** Tiers: "Picsart Plus: premium content, templates, and extra retouch features. Picsart Pro: more AI tools, extra team seats … more storage" ([App Store US](https://apps.apple.com/us/app/id587366035)). The web pricing is credit-based ("credits/month"): Pro "$15 → $10.5/mo billed yearly", 5x Pro "$47 → $37.5/mo" ([picsart.com/pricing](https://www.picsart.com/pricing/)). The Android listing carries "Contains ads" ([Play](https://play.google.com/store/apps/details?id=com.picsart.studio&hl=en&gl=US)).
- **Hypic (ByteDance).** Only "monthly-HypicPro" and "yearly-HypicPro" SKUs are visible ([App Store US](https://apps.apple.com/us/app/id1644042837)). Feature gating could not be verified from official sources; only mod-APK sites discuss it.
- **CapCut.**
  - Free tier and paid SKUs: the iOS SKUs are "Standard Monthly Subscription" and "Pro Monthly Subscription" ([App Store US](https://apps.apple.com/us/app/id1500855883)). A watermark appears "when you keep a Pro-locked template … or when you export certain AI-generated clips" ([BIGVU, secondary](https://bigvu.tv/blog/capcut-free-vs-pro-what-2026s-restructure-actually-gives-you/)).
  - 2025–26 restructure: CapCut split its old single Pro tier into Standard and a new, pricier Pro ([BIGVU, secondary](https://bigvu.tv/blog/capcut-free-vs-pro-what-2026s-restructure-actually-gives-you/)).
- **VN (Ubiquiti Labs).** "Free with No Watermark", "import LUTs", "Export up to 4K resolution at 60fps" ([App Store US](https://apps.apple.com/us/app/id1343581380)). Paid: "VN Pro" plus AI "Credits" (100 Credits $1.00 … 1000 Credits $10.00). The Android listing carries "Contains ads" ([Play](https://play.google.com/store/apps/details?id=com.frontrow.vlog&hl=en&gl=US)).

**Pro video cameras**
- **Blackmagic Camera.** Free, with no IAP on either store: ProRes/H.264/H.265, "add 3D LUTs to recreate film looks", recording to Blackmagic Cloud ([App Store US](https://apps.apple.com/us/app/id6449580241); [Play](https://play.google.com/store/apps/details?id=com.blackmagicdesign.android.blackmagiccam&hl=en&gl=US)).
- **mcpro24fps (Android).** Paid upfront: the US listing shows a "$19.99 Buy" button, plus IAPs of $0.99–$5.49. A free "mcpro24fps demo" app (1M+ installs) lets users test features on their phone first. Log profiles and technical LUTs are included ([Play](https://play.google.com/store/apps/details?id=lv.mcprotector.mcpro24fps&hl=en&gl=US); [demo](https://play.google.com/store/apps/details?id=lv.mcprotector.mcpro24fps.demo&hl=en&gl=US)).
- **Halide Mark III.** "Halide is a paid app. Try it free for 7 days with an annual membership, or buy it outright with a one-time purchase" ([App Store US](https://apps.apple.com/us/app/id885697368)).

**Condensed paywall matrix**

Y = free, P = paid/Pro only, "–" = feature not offered or not stated. Built only from the sources above.

| App | Free starter content | Individual camera/film/pack purchase | All-access sub | Lifetime / one-time | Watermark on free | Ads in free | Import .cube / .xmp | RAW | Video/4K gate | AI features gated |
|---|---|---|---|---|---|---|---|---|---|---|
| Filmode (iOS) | some collections | yes (packs, "passes") | yes | yes | video only | no | Y (.cube+.xmp) | – | 4K + clean video = P | color-match→LUT = P |
| Filmode Vibe (Android) | 18 looks | – | yes | yes | no | no | Y (.cube, presets) | – | – | – |
| FilCam (Android) | manual + LUTs | – | yes (7-day trial yearly) | yes | no | no | Y (.cube) | Y (DNG free) | – | – |
| Dazz Cam (iOS) | some cameras | yes ($0.99–$2.99) | yes (Dazz Pro) | yes ($19.99) | – | – | – | – | – | – |
| Huji Cam | camera | – | – | $0.99 "Extra Options" | – | yes (Android) | – | – | – | – |
| 1998 Cam | some filters | – | yes | yes | no | yes (Android) | – | – | exports may be gated | – |
| NOMO CAM | some cameras free | yes | yes (1-yr) | – | – | – | – | – | – | – |
| FIMO | few films | yes | yes (1-yr) | – | yes | yes | – | – | – | – |
| Kapi Cam | some cameras | – | yes (weekly→yearly) | yes | – | reported | – | – | – | – |
| OldRoll / ProCCD | some cameras | yes | yes | yes | – | yes (Android) | – | – | – | – |
| Hipstamatic Analog | base camera | – | yes (Club) | – | – | no | – | – | – | – |
| VSCO | 15–16 presets | – | Plus / Pro | – | – | Plus = ad-free | – | – | video in Plus | AI Lab = Pro |
| Lightroom | core edit | – | Premium | – | – | no | presets | RAW import = P | – | Gen Remove / Lens Blur = P |
| Darkroom | all tools (no export) | legacy only | yes | $99.99 | – | – | – | Y | video export = P | – |
| Dehancer | ~10 exports (2023) | – | yes | non-renewing 1 mo / 1 yr | – | – | – | beta | video export = P | – |
| RNI Films | intro film pack | yes ($3.99 packs) | yes | yes ("RNI Mobile Pro") | – | – | – | Y | – | – |
| Afterlight | some presets | – | yes | yes | – | – | – | – | – | – |
| Polarr | basic | – | Lite / Studio | – | – | yes (Android) | LUT | – | – | – |
| Picsart / Hypic / CapCut | broad | – | tiered | – | template/AI outputs (CapCut) | yes (Picsart) | – | – | – | AI = P / credits |
| VN | nearly all | – | VN Pro | – | no | yes (Android) | Y (LUT) | – | 4K60 free | AI credits |
| Blackmagic Camera | everything | – | – | – | no | no | Y (3D LUT) | – | free | – |
| mcpro24fps | demo app | – | – | $19.99 app | no | no | tech LUTs | – | – | – |

### Inferences
- The dominant gate in this niche is the size of the look/camera catalogue plus save or export. Several apps let users preview premium looks live and only charge at save: Filmode Vibe ("only keeping the shot asks"), Darkroom ("Export needs Darkroom+") and Dehancer (export count). This is the "try-then-pay at save" pattern.
- Watermarks and ads mostly appear in high-volume Asian/clone camera apps and on Android. Premium-positioned apps use "no watermark, no ads" as a selling point. For a new entrant that is table stakes rather than a differentiator.
- .cube import is free wherever it exists (Filmode, FilCam, VN, Blackmagic). Pro tiers gate *creating or exporting* LUTs (Filmode's color-match→LUT) or pro drive modes, not import.
- RAW/DNG capture is usually free (FilCam, VSCO Capture, Halide trial). RAW editing and masking are the premium gates in editors (Lightroom, Darkroom).

### Gaps
- I did not find an official count of free cameras for Dazz Cam, Kapi Cam, OldRoll or ProCCD (in-app shops are not visible on the web).
- Hypic, Foodie and Kapi feature gating were not verifiable from official pages (Hypic results were mod-APK sites only).
- Adobe's Lightroom mobile FAQ returned HTTP 403, so the Lightroom feature list comes from secondary reviews.
- Dehancer's current free export limit (the 2023 figure was 10 images) and trial length were not confirmed; dehancer.com pricing pages did not render.
- Rewarded-ad "unlock a filter for 24h" was found only as a generic pattern ([Verve](https://verve.com/blog/rewarded-video-ads-beyond-gaming-apps/); [VaporCam listing mentions ads to unlock stickers/frames](https://apps.apple.com/us/app/vaporcam-retro-filter-camera/id1246175190)). No major film-camera app was confirmed to use it.

## Q2. Exact price points by storefront (USD, VND, JPY, KRW, EUR, GBP, IDR, BRL)

### Takeaway
Typical US anchors in this niche:
- **Retro-camera apps:** per-camera unlocks $0.99–$2.99; all-access subscriptions $1.99–$5.99 per month and $9.99–$29.99 per year; lifetime $13.99–$39.99.
- **Premium editors (VSCO, Darkroom, Tezza, Picsart):** $39.99–$89.99 per year.
- **Aggressive weekly pricing:** mostly in AI/big-publisher apps (Kapi $4.99/wk, Picsart $4.99–$11.99/wk, Prequel $4.99–$5.99/wk, Tezza Pro $4.99/wk). Lightroom also sells a $3.99 weekly plan.

Vietnam prices on the App Store follow Apple's tier ladder (US $0.99 ≈ 29.000đ, $1.99 ≈ 59.000đ, $19.99 ≈ 599.000đ, $49.99 ≈ 1.499.000đ). ByteDance, Picsart, Kapi and Dazz set VN prices well below that equalized ladder.

### Cited Findings
**Free-trial lengths and intro offers seen:**
- VSCO: 7-day trial on Plus and Pro ([vsco.co](https://www.vsco.co/subscribe/plans)).
- Hipstamatic Camera Club: "first month is on us" ([App Store](https://apps.apple.com/us/app/id1450672436)).
- FilCam: 7-day trial on the yearly plan ([Play](https://play.google.com/store/apps/details?id=app.filmode.filcam&hl=en&gl=US)).
- Halide: 7-day trial with the annual membership ([App Store](https://apps.apple.com/us/app/id885697368)).
- Darkroom: trial on yearly only; monthly has "No trial" ([darkroom.co](https://darkroom.co/darkroom+)).
- Afterlight PRO: 7-day trial (secondary: [creatoreconomytools](https://creatoreconomytools.com/tool/afterlight)).
- SKU names that imply yearly-with-trial: OldRoll "Yearly VIP-Trial" ($12.99–$19.99) and ProCCD "Yearly VIP with Trial" ($5.99/$8.99) ([OldRoll](https://apps.apple.com/us/app/id1570093460); [ProCCD](https://apps.apple.com/us/app/id1616113199)).
- Discount SKUs: Darkroom "Discounted Yearly Subscription" $32.99, Afterlight "Yearly Afterlight PRO Special" $15.99, Prequel "Gold Weekly Special" $2.99. These look like intro, win-back or promo offers ([Darkroom](https://apps.apple.com/us/app/id953286746); [Afterlight](https://apps.apple.com/us/app/id1293122457); [Prequel](https://apps.apple.com/us/app/id1325756279)).

**Web vs in-app price gap:** VSCO's own website charges less than its iOS IAPs.
- Web: Plus $29.99/yr or $7.99/mo; Pro $59.99/yr or $12.99/mo ([vsco.co plans](https://www.vsco.co/subscribe/plans)).
- iOS US: Yearly Plus $39.99, Monthly Plus $9.99, Yearly Pro $69.99, Monthly Pro $14.99 ([App Store US](https://apps.apple.com/us/app/id588013838)).

**Prices stated in descriptions (US):**
- Tezza iOS: "$6.99 per month, $39.99 per year, $9.99 per month, $59.99 per year" ([App Store](https://apps.apple.com/us/app/id1393061654)).
- Tezza Android: "$5.99/month … $39.99/year" ([Play](https://play.google.com/store/apps/details?id=org.tezza&hl=en&gl=US)).
- NOMO PRO renewal "USD 24.99" per year ([App Store](https://apps.apple.com/us/app/id1362548649)).
- Polarr Lite $1.99/mo or $11.99/yr; Studio $3.99/mo or $23.99/yr ([App Store](https://apps.apple.com/us/app/id988173374)).
- Darkroom+ $39.99/yr, $9.99/mo, $99.99 lifetime ([darkroom.co](https://darkroom.co/darkroom+)).

**Paid-upfront apps:**
- mcpro24fps: $19.99 on Google Play US ([Play](https://play.google.com/store/apps/details?id=lv.mcprotector.mcpro24fps&hl=en&gl=US)).
- Classic Hipstamatic: $4.99; FILCA: $3.99 (iTunes Search API, US, 2026-09-27: [search API](https://itunes.apple.com/search?term=hipstamatic&entity=software&country=us)).

**App Store In-App Purchase lists by storefront**

Scraped 2026-09-27. Subscription, lifetime and "pro" SKUs are listed first, then up to 3 per-item SKUs. Duplicate names at different prices are separate SKUs (A/B price tests, legacy prices or intro offers).
- **Filmode (iOS)** (App Store id6791145420):
  - US ([store](https://apps.apple.com/us/app/id6791145420)): Yearly $14.99; Wedding Pass $49.99; Party Pass $9.99; Group Pass $2.99; Pro-Mist $0.99; Monthly $1.99; Lifetime $19.99; 3 Months $4.99; Cinematic Pack $2.99; Y2K Digicam $1.99
  - VN ([store](https://apps.apple.com/vn/app/id6791145420)): Monthly 59.000đ; Yearly 499.000đ; Wedding Pass 1.499.000đ; Party Pass 299.000đ; Group Pass 99.000đ; Pro-Mist 29.000đ; Lifetime 599.000đ; 3 Months 149.000đ; Cinematic Pack 99.000đ; Y2K Digicam 59.000đ
  - JP ([store](https://apps.apple.com/jp/app/id6791145420)): Yearly ¥2,500; Wedding Pass ¥8,000; Party Pass ¥1,500; Group Pass ¥500; Pro-Mist ¥150; Monthly ¥300; Lifetime ¥3,000; 3 Months ¥800; Cinematic Pack ¥500; Y2K Digicam ¥300
  - KR ([store](https://apps.apple.com/kr/app/id6791145420)): Yearly ￦25,000; Wedding Pass ￦77,000; Party Pass ￦17,000; Group Pass ￦4,400; Pro-Mist ￦1,100; Monthly ￦3,300; Lifetime ￦33,000; 3 Months ￦7,700; Cinematic Pack ￦4,400; Y2K Digicam ￦3,300
  - DE ([store](https://apps.apple.com/de/app/id6791145420)): Yearly 17,99 €; Wedding Pass 59,99 €; Party Pass 9,99 €; Group Pass 2,99 €; Pro-Mist 0,99 €; Monthly 1,99 €; Lifetime 22,99 €; 3 Months 5,99 €; Cinematic Pack 2,99 €; Y2K Digicam 1,99 €
  - GB ([store](https://apps.apple.com/gb/app/id6791145420)): Yearly £14.99; Wedding Pass £49.99; Party Pass £9.99; Group Pass £2.99; Pro-Mist £0.99; Monthly £1.99; Lifetime £19.99; 3 Months £4.99; Cinematic Pack £2.99; Y2K Digicam £1.99
  - ID ([store](https://apps.apple.com/id/app/id6791145420)): Yearly Rp 299ribu; Wedding Pass Rp 999ribu; Party Pass Rp 199ribu; Group Pass Rp 59ribu; Pro-Mist Rp 19ribu; Monthly Rp 29ribu; Lifetime Rp 399ribu; 3 Months Rp 89ribu; Cinematic Pack Rp 59ribu; Y2K Digicam Rp 39ribu
  - BR ([store](https://apps.apple.com/br/app/id6791145420)): Yearly R$ 99,90; Wedding Pass R$ 299,90; Party Pass R$ 59,90; Group Pass R$ 19,90; Pro-Mist R$ 6,90; Monthly R$ 12,90; Lifetime R$ 129,90; 3 Months R$ 29,90; Cinematic Pack R$ 19,90; Y2K Digicam R$ 12,90
- **Dazz Cam** (App Store id1422471180):
  - US ([store](https://apps.apple.com/us/app/id1422471180)): Dazz Pro $6.99; Dazz Pro One-Time Purchase $19.99; Dazz Flash Color $0.99; Dazz ND Filter $0.99; Dazz S Classic $1.99; (+5 more per-item SKUs)
  - VN ([store](https://apps.apple.com/vn/app/id1422471180)): Dazz Pro 99.000đ; Dazz Pro One-Time Purchase 299.000đ; Dazz ND Filter 29.000đ; Dazz S Classic 59.000đ; Dazz Camera NT16 59.000đ; (+5 more per-item SKUs)
  - JP ([store](https://apps.apple.com/jp/app/id1422471180)): Dazz Pro ¥900; Dazz Pro One-Time Purchase ¥2,200; Dazz Exp Camera ¥500; Dazz Camera NT16 ¥300; Dazz ND Filter ¥150; (+5 more per-item SKUs)
  - KR ([store](https://apps.apple.com/kr/app/id1422471180)): Dazz Pro ￦9,900; Dazz Pro One-Time Purchase ￦29,000; Dazz Exp Camera ￦4,400; Dazz Camera NT16 ￦3,300; Dazz ND Filter ￦1,100; (+5 more per-item SKUs)
  - DE ([store](https://apps.apple.com/de/app/id1422471180)): Dazz Pro 6,99 €; Dazz Pro One-Time Purchase 17,99 €; Dazz ND Filter 0,99 €; Dazz Flash Color 0,99 €; Dazz Black Camera 0,99 €; (+5 more per-item SKUs)
  - GB ([store](https://apps.apple.com/gb/app/id1422471180)): Dazz Pro £6.99; Dazz Pro One-Time Purchase £19.99; Dazz ND Filter £0.99; Dazz Flash Color £0.99; Dazz S Classic £1.99; (+5 more per-item SKUs)
  - ID ([store](https://apps.apple.com/id/app/id1422471180)): Dazz Pro Rp 69ribu; Dazz Pro One-Time Purchase Rp 199ribu; Dazz Flash Color Rp 19ribu; Dazz ND Filter Rp 19ribu; Dazz Exp Camera Rp 59ribu; (+5 more per-item SKUs)
  - BR ([store](https://apps.apple.com/br/app/id1422471180)): Dazz Pro R$ 19,90; Dazz Pro One-Time Purchase R$ 69,90; Dazz ND Filter R$ 6,90; Dazz Black Camera R$ 6,90; Dazz Flash Color R$ 6,90; (+5 more per-item SKUs)
- **Huji Cam** (App Store id781383622):
  - US ([store](https://apps.apple.com/us/app/id781383622)): Extra Options $0.99
  - VN ([store](https://apps.apple.com/vn/app/id781383622)): Extra Options 29.000đ
  - JP ([store](https://apps.apple.com/jp/app/id781383622)): 追加オプション ¥150
  - KR ([store](https://apps.apple.com/kr/app/id781383622)): 추가 옵션 ￦1,100
  - DE ([store](https://apps.apple.com/de/app/id781383622)): Zusätzliche Optionen 0,99 €
  - GB ([store](https://apps.apple.com/gb/app/id781383622)): Extra Options £0.99
  - ID ([store](https://apps.apple.com/id/app/id781383622)): Extra Options Rp 19ribu
  - BR ([store](https://apps.apple.com/br/app/id781383622)): Opções Extra R$ 6,90
- **1998 Cam** (App Store id1450480287):
  - US ([store](https://apps.apple.com/us/app/id1450480287)): 1998 Cam Premium - Monthly $2.99; 1998 Cam Premium - Yearly $29.99; 1998 Cam Premium - Yearly $17.99; 1998 Cam Premium - Monthly $5.99; 1998 Cam Pro - Lifetime $39.99; 1998 Cam Premium - Lifetime $39.99; 1998 Cam Premium - Monthly $1.99; 1998 Cam Premium - Monthly $3.99; 1998 Cam Premium - Yearly $15.99
  - VN ([store](https://apps.apple.com/vn/app/id1450480287)): 1998 Cam Premium - Monthly 69.000đ; 1998 Cam Pro - Lifetime 1.199.000đ; 1998 Cam Premium - Yearly 419.000đ; 1998 Cam Premium - Monthly 47.000đ; 1998 Cam Premium - Lifetime 1.199.000đ; 1998 Cam Premium - Monthly 99.000đ; 1998 Cam Premium - Yearly 369.000đ; 1998 Cam Premium - Monthly 199.000đ; 1998 Cam Premium - Yearly 999.000đ
  - JP ([store](https://apps.apple.com/jp/app/id1450480287)): 1998 Cam プレミアム - 月額 ¥300; 1998 Cam プレミアム - 年額 ¥1,950; 1998 Cam プレミアム - 年額 ¥5,000; 1998 Cam Pro - 買い切り ¥6,000; 1998 Cam プレミアム - 月額 ¥1,000; 1998 Cam プレミアム - 月額 ¥200; 1998 Cam プレミアム - 月額 ¥600; 1998 Cam プレミアム - 年額 ¥1,700; 1998 Cam プレミアム - 買い切り ¥6,000
  - KR ([store](https://apps.apple.com/kr/app/id1450480287)): 1998 Cam 프리미엄 - 월간 ￦4,000; 1998 Cam 프리미엄 - 연간 ￦24,000; 1998 Cam Pro - 평생 ￦66,000; 1998 Cam 프리미엄 - 월간 ￦2,500; 1998 Cam 프리미엄 - 월간 ￦5,500; 1998 Cam 프리미엄 - 월간 ￦8,800; 1998 Cam 프리미엄 - 연간 ￦25,000; 1998 Cam 프리미엄 - 연간 ￦21,000; 1998 Cam 프리미엄 - 평생 ￦66,000
  - DE ([store](https://apps.apple.com/de/app/id1450480287)): 1998 Cam Premium - Monatlich 3,49 €; 1998 Cam Premium - Jährlich 34,99 €; 1998 Cam Pro - Für immer 44,99 €; 1998 Cam Premium - Jährlich 19,49 €; 1998 Cam Premium - Monatlich 6,99 €; 1998 Cam Premium - Monatlich 1,99 €; 1998 Cam Premium - Für immer 44,99 €; 1998 Cam Premium - Monatlich 3,99 €; 1998 Cam Premium - Jährlich 17,49 €
  - GB ([store](https://apps.apple.com/gb/app/id1450480287)): 1998 Cam Premium - Monthly £2.99; 1998 Cam Premium - Yearly £29.99; 1998 Cam Pro - Lifetime £39.99; 1998 Cam Premium - Monthly £5.99; 1998 Cam Premium - Yearly £17.49; 1998 Cam Premium - Monthly £1.99; 1998 Cam Premium - Lifetime £39.99; 1998 Cam Premium - Monthly £3.99; 1998 Cam Premium - Yearly £15.49
  - ID ([store](https://apps.apple.com/id/app/id1450480287)): 1998 Cam Premium - Monthly Rp 45ribu; 1998 Cam Pro - Lifetime Rp 799ribu; 1998 Cam Premium - Yearly Rp 259ribu; 1998 Cam Premium - Monthly Rp 29ribu; 1998 Cam Premium - Lifetime Rp 799ribu; 1998 Cam Premium - Monthly Rp 99ribu; 1998 Cam Premium - Monthly Rp 69ribu; 1998 Cam Premium - Yearly Rp 229ribu; 1998 Cam Premium - Yearly Rp 499ribu
  - BR ([store](https://apps.apple.com/br/app/id1450480287)): 1998 Cam Premium - Mensal R$ 12,90; 1998 Cam Premium - Anual R$ 74,90; 1998 Cam Pro - Vitalício R$ 249,90; 1998 Cam Premium - Mensal R$ 39,90; 1998 Cam Premium - Mensal R$ 8,50; 1998 Cam Premium - Anual R$ 199,90; 1998 Cam Premium - Mensal R$ 19,90; 1998 Cam Premium - Vitalício R$ 249,90; 1998 Cam Premium - Anual R$ 65,90
- **NOMO CAM** (App Store id1362548649):
  - US ([store](https://apps.apple.com/us/app/id1362548649)): NOMO PRO (1 Year) $24.99; NOMO TOY F $0.00; NOMO ROMA $0.00; NOMO TOY K $0.00; (+6 more per-item SKUs)
  - VN ([store](https://apps.apple.com/vn/app/id1362548649)): NOMO PRO (1 Year) 579.000đ; NOMO FR2 0đ; NOMO ROMA 0đ; NOMO TOY F 0đ; (+6 more per-item SKUs)
  - JP ([store](https://apps.apple.com/jp/app/id1362548649)): NOMO PRO (1 Year) ¥2,700; NOMO TOY F ¥0; NOMO FR2 ¥0; NOMO TOY K ¥0; (+6 more per-item SKUs)
  - KR ([store](https://apps.apple.com/kr/app/id1362548649)): NOMO PRO (1 Year) ￦33,000; NOMO TOY F ￦0; NOMO TOY K ￦0; NOMO ROMA ￦0; (+6 more per-item SKUs)
  - DE ([store](https://apps.apple.com/de/app/id1362548649)): NOMO PRO (1 Year) 27,49 €; NOMO TOY F 0,00 €; NOMO ROMA 0,00 €; NOMO TOY K 0,00 €; (+6 more per-item SKUs)
  - GB ([store](https://apps.apple.com/gb/app/id1362548649)): NOMO PRO (1 Year) £24.49; NOMO TOY F £0.00; NOMO ROMA £0.00; NOMO TOY K £0.00; (+6 more per-item SKUs)
  - ID ([store](https://apps.apple.com/id/app/id1362548649)): NOMO PRO (1 Year) Rp 359ribu; NOMO TOY F Rp 0; NOMO FR2 Rp 0; NOMO ROMA Rp 0; (+6 more per-item SKUs)
  - BR ([store](https://apps.apple.com/br/app/id1362548649)): NOMO PRO (1 Year) R$ 102,90; NOMO TOY F R$ 0,00; NOMO ROMA R$ 0,00; NOMO FR2 R$ 0,00; (+6 more per-item SKUs)
- **Kapi Cam** (App Store id6740760807):
  - US ([store](https://apps.apple.com/us/app/id6740760807)): Monthly $9.99; Yearly $69.99; Weekly $4.99; Life-time $149.00; Yearly $89.99; Monthly $12.99
  - VN ([store](https://apps.apple.com/vn/app/id6740760807)): Monthly 79.000đ; Weekly 19.000đ; Yearly 599.000đ; Monthly 199.000đ; Life-time 1.499.000đ; Yearly 1.499.000đ
  - JP ([store](https://apps.apple.com/jp/app/id6740760807)): Monthly ¥500; Yearly ¥3,000; Weekly ¥150; Monthly ¥1,000; Life-time ¥8,000; Yearly ¥8,000
  - KR ([store](https://apps.apple.com/kr/app/id6740760807)): Monthly ￦4,400; Weekly ￦1,100; Yearly ￦29,000; Life-time ￦66,000; Yearly ￦77,000; Monthly ￦9,900
  - DE ([store](https://apps.apple.com/de/app/id6740760807)): Monthly 9,99 €; Weekly 1,99 €; Yearly 79,99 €; Life-time 179,99 €; Yearly 99,99 €; Monthly 14,99 €
  - GB ([store](https://apps.apple.com/gb/app/id6740760807)): Monthly £9.99; Weekly £1.99; Yearly £69.99; Life-time £149.99; Yearly £89.99; Monthly £12.99
  - ID ([store](https://apps.apple.com/id/app/id6740760807)): Monthly Rp 39ribu; Yearly Rp 349ribu; Weekly Rp 9ribu; Monthly Rp 99ribu; Life-time Rp 799ribu; Yearly Rp 799ribu
  - BR ([store](https://apps.apple.com/br/app/id6740760807)): Monthly R$ 14,90; Yearly R$ 129,90; Weekly R$ 4,90; Life-time R$ 299,90; Yearly R$ 299,90; Monthly R$ 39,90
- **FIMO** (App Store id1454219307):
  - US ([store](https://apps.apple.com/us/app/id1454219307)): GOLD 200 $0.99; fimo pro for 1 year $29.99; New Year 2020 $1.99; Morandi200 $0.99; X-Mas 25T $1.99; Aesthetic400 $0.99; (+4 more per-item SKUs)
  - VN ([store](https://apps.apple.com/vn/app/id1454219307)): GOLD 200 29.000đ; NewYear2020Lunar 29.000đ; Morandi200 29.000đ; Aesthetic400 29.000đ; Yummy 100 29.000đ; (+5 more per-item SKUs)
  - JP ([store](https://apps.apple.com/jp/app/id1454219307)): GOLD 200 ¥150; fimo pro for 1 year ¥3,400; New Year 2020 ¥300; Morandi200 ¥150; X-Mas 25T ¥300; Portra 160NC ¥300; (+4 more per-item SKUs)
  - KR ([store](https://apps.apple.com/kr/app/id1454219307)): GOLD 200 ￦1,100; New Year 2020 ￦3,300; fimo pro for 1 year ￦38,000; Morandi200 ￦1,100; X-Mas 25T ￦3,300; Natura 1600 ￦1,100; (+4 more per-item SKUs)
  - DE ([store](https://apps.apple.com/de/app/id1454219307)): GOLD 200 0,99 €; fimo pro for 1 year 30,99 €; New Year 2020 1,99 €; Morandi200 0,99 €; X-Mas 25T 1,99 €; Portra 160NC 1,99 €; (+4 more per-item SKUs)
  - GB ([store](https://apps.apple.com/gb/app/id1454219307)): GOLD 200 £0.99; New Year 2020 £1.99; fimo pro for 1 year £26.49; X-Mas 25T £1.99; Morandi200 £0.99; Portra 160NC £1.99; (+4 more per-item SKUs)
  - ID ([store](https://apps.apple.com/id/app/id1454219307)): GOLD 200 Rp 19ribu; New Year 2020 Rp 39ribu; Morandi200 Rp 19ribu; Aesthetic400 Rp 19ribu; Yummy 100 Rp 19ribu; (+5 more per-item SKUs)
  - BR ([store](https://apps.apple.com/br/app/id1454219307)): GOLD 200 R$ 6,90; fimo pro for 1 year R$ 167,90; New Year 2020 R$ 12,90; Morandi200 R$ 6,90; X-Mas 25T R$ 12,90; Natura 1600 R$ 6,90; (+4 more per-item SKUs)
- **Hipstamatic Analog** (App Store id1450672436):
  - US ([store](https://apps.apple.com/us/app/id1450672436)): Hipstamatic Camera Club $29.99; Hipstamatic Camera Club $7.99; Hipstamatic Camera Club $19.99
  - VN ([store](https://apps.apple.com/vn/app/id1450672436)): Hipstamatic Camera Club 799.000đ; Hipstamatic Camera Club 199.000đ; Hipstamatic Camera Club 499.000đ
  - JP ([store](https://apps.apple.com/jp/app/id1450672436)): Hipstamatic カメラクラブ ¥900; Hipstamatic カメラクラブ ¥4,000; Hipstamatic カメラクラブ ¥3,000
  - KR ([store](https://apps.apple.com/kr/app/id1450672436)): Hipstamatic 카메라 클럽 ￦39,000; Hipstamatic 카메라 클럽 ￦9,900; Hipstamatic 카메라 클럽 ￦29,000
  - DE ([store](https://apps.apple.com/de/app/id1450672436)): Hipstamatic Camera Club 29,99 €; Hipstamatic Camera Club 19,99 €; Hipstamatic Camera Club 7,99 €
  - GB ([store](https://apps.apple.com/gb/app/id1450672436)): Hipstamatic Camera Club £29.99; Hipstamatic Camera Club £19.99; Hipstamatic Camera Club £7.99
  - ID ([store](https://apps.apple.com/id/app/id1450672436)): Hipstamatic Camera Club Rp 499ribu; Hipstamatic Camera Club Rp 99ribu; Hipstamatic Camera Club Rp 349ribu
  - BR ([store](https://apps.apple.com/br/app/id1450672436)): Hipstamatic Camera Club R$ 99,90; Hipstamatic Camera Club R$ 39,90
- **Hipstamatic Classic** (App Store id342115564):
  - US ([store](https://apps.apple.com/us/app/id342115564)): Williamsburg Starter HipstaPak $0.99; Portland HipstaPak $0.99; Shibuya HipstaPak $0.99; (+7 more per-item SKUs)
  - VN ([store](https://apps.apple.com/vn/app/id342115564)): Williamsburg Starter HipstaPak 29.000đ; Portland HipstaPak 29.000đ; Shibuya HipstaPak 29.000đ; (+7 more per-item SKUs)
  - JP ([store](https://apps.apple.com/jp/app/id342115564)): Williamsburg Starter HipstaPak ¥150; Portland HipstaPak ¥150; Shibuya HipstaPak ¥150; (+7 more per-item SKUs)
  - KR ([store](https://apps.apple.com/kr/app/id342115564)): Williamsburg Starter HipstaPak ￦1,100; Portland HipstaPak ￦1,100; Shibuya HipstaPak ￦1,100; (+7 more per-item SKUs)
  - DE ([store](https://apps.apple.com/de/app/id342115564)): Portland HipstaPak 0,99 €; Williamsburg Starter HipstaPak 0,99 €; Shibuya HipstaPak 0,99 €; (+7 more per-item SKUs)
  - GB ([store](https://apps.apple.com/gb/app/id342115564)): Portland HipstaPak £0.99; Williamsburg Starter HipstaPak £0.99; Shibuya HipstaPak £0.99; (+7 more per-item SKUs)
  - ID ([store](https://apps.apple.com/id/app/id342115564)): Williamsburg Starter HipstaPak Rp 19ribu; Shibuya HipstaPak Rp 19ribu; Portland HipstaPak Rp 19ribu; (+7 more per-item SKUs)
  - BR ([store](https://apps.apple.com/br/app/id342115564)): Williamsburg Starter HipstaPak R$ 6,90; Portland HipstaPak R$ 6,90; Shibuya HipstaPak R$ 6,90; (+7 more per-item SKUs)
- **VSCO** (App Store id588013838):
  - US ([store](https://apps.apple.com/us/app/id588013838)): Yearly Plus $39.99; Monthly Plus $9.99; Monthly Pro $14.99; Yearly Pro $69.99; The Aesthetic Series $0.00; Hypebeast / HB $0.00; Distortia Pack $0.00; (+2 more per-item SKUs)
  - VN ([store](https://apps.apple.com/vn/app/id588013838)): Yearly Plus 799.000đ; The Aesthetic Series 0đ; Hypebeast / HB 0đ; Krochet Kids intl. 0đ; (+6 more per-item SKUs)
  - JP ([store](https://apps.apple.com/jp/app/id588013838)): 年間Plus ¥6,000; 月間Plus ¥1,500; Yearly Plus ¥6,000; The Aesthetic Series ¥0; Hypebeast / HB ¥0; We the Creators ¥0; (+4 more per-item SKUs)
  - KR ([store](https://apps.apple.com/kr/app/id588013838)): 연간 Plus ￦55,000; Yearly Plus ￦55,000; 월간 Plus ￦14,000; The Aesthetic Series ￦0; Hypebeast / HB ￦0; Krochet Kids intl. ￦0; (+4 more per-item SKUs)
  - DE ([store](https://apps.apple.com/de/app/id588013838)): Jahresabo Plus 34,99 €; Monatsabo Plus 9,99 €; Yearly Plus 34,99 €; Jahresabo Pro 79,99 €; The Aesthetic Series 0,00 €; Hypebeast / HB 0,00 €; We the Creators 0,00 €; (+3 more per-item SKUs)
  - GB ([store](https://apps.apple.com/gb/app/id588013838)): Yearly Plus £29.99; Monthly Plus £9.99; Monthly Pro £14.99; The Aesthetic Series £0.00; Hypebeast / HB £0.00; Krochet Kids intl. £0.00; (+3 more per-item SKUs)
  - ID ([store](https://apps.apple.com/id/app/id588013838)): Yearly Plus Rp 499ribu; Yearly Pro Rp 999ribu; The Aesthetic Series Rp 0; Hypebeast / HB Rp 0; Krochet Kids intl. Rp 0; (+4 more per-item SKUs)
  - BR ([store](https://apps.apple.com/br/app/id588013838)): Anual Plus R$ 149,90; Mensal Plus R$ 39,90; Yearly Plus R$ 149,90; Anual Pro R$ 399,90; The Aesthetic Series R$ 0,00; Hypebeast / HB R$ 0,00; Krochet Kids intl. R$ 0,00; (+3 more per-item SKUs)
- **VSCO Capture** (App Store id6741483219): no In-App Purchase list shown on the store page (free, no IAP)
- **Lightroom** (App Store id878783582):
  - US ([store](https://apps.apple.com/us/app/id878783582)): Premium Monthly 100GB $6.99; Premium yearly 100GB $49.99; Premium Monthly 100GB $7.99; Premium Weekly 100GB $3.99; Premium monthly 40GB $1.99; Premium Yearly 40GB $19.99; Premium Weekly 100GB $7.99; Lightroom plan 1TB $9.99; AI Photo Enhancer & Blur $49.99
  - VN ([store](https://apps.apple.com/vn/app/id878783582)): Premium monthly 40GB 47.000đ; Premium Yearly 40GB 469.000đ; Premium Monthly 100GB 109.000đ; Premium yearly 100GB 1.159.000đ; Premium Monthly 100GB 119.000đ; Premium weekly 40GB 29.000đ; Premium weekly 40GB 59.000đ; Premium Yearly 40GB 459.000đ; Premium Monthly 40GB 69.000đ; Photo enhancer & erase objects 1.149.000đ
  - JP ([store](https://apps.apple.com/jp/app/id878783582)): プレミアム (100 GB/月) ¥550; プレミアム (100 GB/月) ¥990; プレミアム (100 GB/年) ¥5,880; プレミアム (40 GB/月) ¥200; プレミアム (40 GB/年) ¥2,100; 編集　レタッチ　ぼかし　削除 ¥5,880; プレミアム 週次 100GB ¥600; プレミアム ¥550
  - KR ([store](https://apps.apple.com/kr/app/id878783582)): 프리미엄 월간 100GB ￦6,500; 프리미엄 월간 100GB ￦6,000; Premium yearly 100GB ￦66,000; 프리미엄 월간 100GB ￦9,900; Premium 주간 100GB ￦5,500; 프리미엄 연간 100GB ￦61,000; 프리미엄 월간 40GB ￦2,500; 프리미엄 연간 40GB ￦27,000; Premium 주간 100GB ￦11,000
  - DE ([store](https://apps.apple.com/de/app/id878783582)): Premium monatlich 100 GB 5,49 €; Premium monatlich 100 GB 4,99 €; Premium jährlich 100 GB 54,99 €; Premium monatlich 100 GB 7,99 €; Premium-KI Foto bearbeitung 49,99 €; Premium monatlich 40 GB 1,99 €; Premium wöchentlich 100 GB 3,99 €; Premium jährlich 40 GB 21,99 €; Premium jährlich 100 GB 38,99 €
  - GB ([store](https://apps.apple.com/gb/app/id878783582)): Premium Monthly 100GB £6.99; Premium yearly 100GB £48.99; Premium monthly 40GB £1.99; Premium Weekly 100GB £3.99; Premium Yearly 40GB £19.49; Premium Weekly 100GB £7.99; Photo enhancer & erase objects £43.99
  - ID ([store](https://apps.apple.com/id/app/id878783582)): Premium monthly 40GB Rp 33ribu; Premium Yearly 40GB Rp 330ribu; Premium Monthly 100GB Rp 65ribu; Premium weekly 40GB Rp 9ribu; Premium Monthly 100GB Rp 69ribu; Premium yearly 100GB Rp 709ribu; Premium weekly 40GB Rp 29ribu; Premium Yearly 40GB Rp 319ribu; Lightroom plan 1TB Rp 149ribu; Photo enhancer & erase objects Rp 799ribu
  - BR ([store](https://apps.apple.com/br/app/id878783582)): Premium mensal de 40 GB R$ 9,90; Premium anual de 40 GB R$ 99,90; Premium mensal de 100 GB R$ 18,90; Premium mensal de 100 GB R$ 7,90; Premium semanal 40 GB R$ 4,90; Premium mensal de 100 GB R$ 20,90; Premium anual de 100 GB R$ 204,90; Premium semanal 40 GB R$ 12,90; Premium mensal de 40 GB R$ 15,90; Premium anual de 40 GB R$ 107,90
- **Tezza** (App Store id1393061654):
  - US ([store](https://apps.apple.com/us/app/id1393061654)): Tezza Pro Monthly $6.99; Tezza Pro Weekly $4.99; Tezza Monthly $3.99; Tezza Pro Yearly $39.99; Tezza Luxe Monthly $9.99; Tezza Monthly Ambassador $5.99; Tezza Yearly $19.99; Tezza Luxe Yearly $59.99; Tezza Yearly Ambassador $39.99
  - VN ([store](https://apps.apple.com/vn/app/id1393061654)): Tezza Pro Monthly 199.000đ; Tezza Pro Weekly 129.000đ; Tezza Pro Yearly 929.000đ; Tezza Monthly 92.000đ; Tezza Luxe Monthly 249.000đ; Tezza Monthly Ambassador 139.000đ; Tezza Luxe Yearly 1.499.000đ; Tezza Yearly 459.000đ; Tezza Yearly Ambassador 919.000đ
  - JP ([store](https://apps.apple.com/jp/app/id1393061654)): Tezza Pro Monthly ¥1,000; Tezza Monthly ¥450; Tezza Pro Weekly ¥800; Tezza Pro Yearly ¥4,500; Tezza Luxe Monthly ¥1,500; Tezza Monthly Ambassador ¥680; Tezza Yearly ¥2,200; Tezza Luxe Yearly ¥9,000; Tezza Yearly Ambassador ¥4,400
  - KR ([store](https://apps.apple.com/kr/app/id1393061654)): Tezza Pro Monthly ￦9,900; Tezza Pro Weekly ￦6,600; Tezza Pro Yearly ￦50,000; Tezza Monthly ￦5,000; Tezza Luxe Monthly ￦14,000; Tezza Monthly Ambassador ￦7,500; Tezza Yearly ￦24,500; Tezza Luxe Yearly ￦88,000; Tezza Yearly Ambassador ￦51,000
  - DE ([store](https://apps.apple.com/de/app/id1393061654)): Tezza Pro Monthly 7,99 €; Tezza Pro Weekly 5,99 €; Tezza Monthly 3,99 €; Tezza Pro Yearly 42,99 €; Tezza Luxe Monthly 9,99 €; Tezza Monthly Ambassador 5,99 €; Tezza Yearly 20,49 €; Tezza Luxe Yearly 69,99 €; Tezza Yearly Ambassador 40,99 €
  - GB ([store](https://apps.apple.com/gb/app/id1393061654)): Tezza Pro Monthly £6.99; Tezza Pro Weekly £4.99; Tezza Monthly £3.49; Tezza Pro Yearly £36.99; Tezza Luxe Monthly £9.99; Tezza Monthly Ambassador £5.49; Tezza Yearly £17.99; Tezza Luxe Yearly £59.99; Tezza Yearly Ambassador £34.99
  - ID ([store](https://apps.apple.com/id/app/id1393061654)): Tezza Pro Monthly Rp 69ribu; Tezza Pro Weekly Rp 29ribu; Tezza Monthly Rp 65ribu; Tezza Pro Yearly Rp 349ribu; Tezza Luxe Monthly Rp 169ribu; Tezza Yearly Rp 279ribu; Tezza Monthly Ambassador Rp 95ribu; Tezza Luxe Yearly Rp 999ribu; Tezza Yearly Ambassador Rp 639ribu
  - BR ([store](https://apps.apple.com/br/app/id1393061654)): Tezza Pro Monthly R$ 39,90; Tezza Pro Weekly R$ 24,90; Tezza Pro Yearly R$ 154,90; Tezza Monthly R$ 21,90; Tezza Luxe Monthly R$ 49,90; Tezza Monthly Ambassador R$ 32,90; Tezza Yearly R$ 74,90; Tezza Luxe Yearly R$ 299,90; Tezza Yearly Ambassador R$ 204,90
- **Afterlight** (App Store id1293122457):
  - US ([store](https://apps.apple.com/us/app/id1293122457)): Monthly Afterlight PRO $2.99; Yearly Afterlight PRO $17.99; Yearly Afterlight PRO $23.99; Monthly Afterlight PRO $3.99; Lifetime Afterlight PRO $39.99; Weekly Afterlight PRO $1.99; Yearly Afterlight PRO Special $15.99; Afterlight PRO - Lifetime $19.99
  - VN ([store](https://apps.apple.com/vn/app/id1293122457)): Monthly Afterlight PRO 69.000đ; Yearly Afterlight PRO 419.000đ; Yearly Afterlight PRO 599.000đ; Monthly Afterlight PRO 99.000đ; Lifetime Afterlight PRO 1.199.000đ; Weekly Afterlight PRO 59.000đ; Yearly Afterlight PRO Special 399.000đ; Afterlight PRO - Lifetime 599.000đ
  - JP ([store](https://apps.apple.com/jp/app/id1293122457)): Monthly Afterlight PRO ¥300; Yearly Afterlight PRO ¥1,900; Yearly Afterlight PRO ¥3,500; Monthly Afterlight PRO ¥600; Lifetime Afterlight PRO ¥6,000; Weekly Afterlight PRO ¥300; Yearly Afterlight PRO Special ¥2,500; Afterlight PRO - Lifetime ¥3,000
  - KR ([store](https://apps.apple.com/kr/app/id1293122457)): Monthly Afterlight PRO ￦4,000; Yearly Afterlight PRO ￦23,500; Yearly Afterlight PRO ￦33,000; Monthly Afterlight PRO ￦5,500; Lifetime Afterlight PRO ￦66,000; Weekly Afterlight PRO ￦3,300; Yearly Afterlight PRO Special ￦22,000; Afterlight PRO - Lifetime ￦33,000
  - DE ([store](https://apps.apple.com/de/app/id1293122457)): Monthly Afterlight PRO 3,49 €; Yearly Afterlight PRO 19,49 €; Yearly Afterlight PRO 24,99 €; Monthly Afterlight PRO 3,99 €; Lifetime Afterlight PRO 44,99 €; Weekly Afterlight PRO 1,99 €; Afterlight PRO - Lifetime 22,99 €; Yearly Afterlight PRO Special 17,99 €
  - GB ([store](https://apps.apple.com/gb/app/id1293122457)): Monthly Afterlight PRO £2.99; Yearly Afterlight PRO £17.99; Monthly Afterlight PRO £3.99; Yearly Afterlight PRO £22.99; Lifetime Afterlight PRO £39.99; Weekly Afterlight PRO £1.99; Yearly Afterlight PRO Special £14.99; Afterlight PRO - Lifetime £19.99
  - ID ([store](https://apps.apple.com/id/app/id1293122457)): Yearly Afterlight PRO Rp 259ribu; Monthly Afterlight PRO Rp 45ribu; Yearly Afterlight PRO Rp 399ribu; Monthly Afterlight PRO Rp 69ribu; Weekly Afterlight PRO Rp 29ribu; Lifetime Afterlight PRO Rp 799ribu; Yearly Afterlight PRO Special Rp 299ribu; Afterlight PRO - Lifetime Rp 399ribu
  - BR ([store](https://apps.apple.com/br/app/id1293122457)): Monthly Afterlight PRO R$ 11,90; Yearly Afterlight PRO R$ 69,90; Yearly Afterlight PRO R$ 119,90; Monthly Afterlight PRO R$ 19,90; Weekly Afterlight PRO R$ 12,90; Lifetime Afterlight PRO R$ 249,90; Yearly Afterlight PRO Special R$ 99,90; Afterlight PRO - Lifetime R$ 129,90
- **Polarr** (App Store id988173374):
  - US ([store](https://apps.apple.com/us/app/id988173374)): Polarr Monthly $3.99; Polarr Studio $9.99; Polarr Yearly $23.99; Polarr Lite $7.99; Polarr Studio $34.99; Polarr Lite $24.99; Polarr Studio $7.99; Polarr Studio $29.99; Polarr Lite $3.99; Polarr Lite $17.99
  - VN ([store](https://apps.apple.com/vn/app/id988173374)): Polarr Yearly 559.000đ; Polarr Lite 149.000đ; Polarr Studio 249.000đ; Polarr Monthly 95.000đ; Polarr Lite 289.000đ; Polarr Studio 569.000đ; Polarr Studio 199.000đ; Polarr Lite 249.000đ; Polarr Studio 499.000đ
  - JP ([store](https://apps.apple.com/jp/app/id988173374)): Polarr 毎月の支払額 ¥550; Polarr Studio ¥1,500; Polarr 年払い ¥3,300; Polarr Lite ¥900; Polarr Studio ¥3,400; Polarr Lite ¥1,700; Polarr Studio ¥3,000; Polarr Lite ¥600; Polarr Lite ¥1,500; Polarr Studio ¥2,500
  - KR ([store](https://apps.apple.com/kr/app/id988173374)): Polarr Studio ￦14,000; Polarr Lite ￦8,800; Polarr Lite ￦18,500; Polarr Studio ￦37,000; Polarr 연간 ￦35,000; Polarr Lite ￦14,000; Polarr Studio ￦29,000; Polarr Lite ￦5,500; Polarr Studio ￦11,000; Polarr 월별 ￦5,900
  - DE ([store](https://apps.apple.com/de/app/id988173374)): Polarr Monatliche 4,99 €; Polarr Studio 9,99 €; Polarr Lite 6,99 €; Polarr Studio 28,99 €; Polarr Lite 14,49 €; Polarr Lite 9,99 €; Polarr Studio 22,99 €; Polarr Studio 8,99 €; Polarr Studio 19,99 €; Polarr Jährlich 28,49 €
  - GB ([store](https://apps.apple.com/gb/app/id988173374)): Polarr Monthly £3.99; Polarr Studio £9.99; Polarr Lite £5.99; Polarr Yearly £24.49; Polarr Studio £25.49; Polarr Lite £12.99; Polarr Studio £19.99; Polarr Lite £9.99; Polarr Lite £3.99; Polarr Studio £8.99
  - ID ([store](https://apps.apple.com/id/app/id988173374)): Polarr Yearly Rp 399ribu; Polarr Lite Rp 99ribu; Polarr Studio Rp 169ribu; Polarr Monthly Rp 65ribu; Polarr Lite Rp 199ribu; Polarr Studio Rp 399ribu; Polarr Lite Rp 169ribu; Polarr Studio Rp 349ribu; Polarr Lite Rp 69ribu; Polarr Studio Rp 499ribu
  - BR ([store](https://apps.apple.com/br/app/id988173374)): Polarr Lite R$ 29,90; Polarr Anual R$ 122,90; Polarr Studio R$ 49,90; Polarr Mensal R$ 20,90; Polarr Studio R$ 122,90; Polarr Lite R$ 61,90; Polarr Lite R$ 49,90; Polarr Studio R$ 99,90; Polarr Lite R$ 19,90; Polarr Studio R$ 39,90
- **RNI Films** (App Store id1017098672):
  - US ([store](https://apps.apple.com/us/app/id1017098672)): Monthly RNI Pro Subscription $1.99; Monthly RNI Pro Subscription $0.99; Yearly RNI Pro Subscription $9.99; Negative Films Pack #1 $3.99; Vintage Films Pack #1 $3.99; Negative Films Pack #2 $3.99; (+2 more per-item SKUs)
  - VN ([store](https://apps.apple.com/vn/app/id1017098672)): Monthly RNI Pro Subscription 22.000đ; Monthly RNI Pro Subscription 52.000đ; Yearly RNI Pro Subscription 229.000đ; RNI Mobile Pro 799.000đ; Negative Films Pack #1 119.000đ; Vintage Films Pack #1 119.000đ; Negative Films Pack #2 119.000đ; (+1 more per-item SKUs)
  - JP ([store](https://apps.apple.com/jp/app/id1017098672)): Monthly RNI Pro Subscription ¥100; Monthly RNI Pro Subscription ¥280; Yearly RNI Pro Subscription ¥1,100; Negative Films Pack #1 ¥600; Negative Films Pack #2 ¥600; Vintage Films Pack #1 ¥600; (+2 more per-item SKUs)
  - KR ([store](https://apps.apple.com/kr/app/id1017098672)): Monthly RNI Pro Subscription ￦1,200; Monthly RNI Pro Subscription ￦3,000; Yearly RNI Pro Subscription ￦12,500; RNI Mobile Pro ￦44,000; Negative Films Pack #1 ￦6,600; Negative Films Pack #2 ￦6,600; Vintage Films Pack #1 ￦6,600; (+1 more per-item SKUs)
  - DE ([store](https://apps.apple.com/de/app/id1017098672)): Monthly RNI Pro Subscription 0,99 €; Monthly RNI Pro Subscription 2,49 €; Yearly RNI Pro Subscription 9,99 €; RNI Mobile Pro 29,99 €; Negative Films Pack #1 3,99 €; Negative Films Pack #2 3,99 €; Vintage Films Pack #1 3,99 €; (+1 more per-item SKUs)
  - GB ([store](https://apps.apple.com/gb/app/id1017098672)): Monthly RNI Pro Subscription £0.79; Monthly RNI Pro Subscription £1.99; Yearly RNI Pro Subscription £8.49; Negative Films Pack #1 £3.99; Negative Films Pack #2 £3.99; Vintage Films Pack #1 £3.99; (+2 more per-item SKUs)
  - ID ([store](https://apps.apple.com/id/app/id1017098672)): Monthly RNI Pro Subscription Rp 35ribu; Monthly RNI Pro Subscription Rp 16ribu; Yearly RNI Pro Subscription Rp 159ribu; Negative Films Pack #1 Rp 79ribu; Vintage Films Pack #1 Rp 79ribu; Negative Films Pack #2 Rp 79ribu; (+2 more per-item SKUs)
  - BR ([store](https://apps.apple.com/br/app/id1017098672)): Monthly RNI Pro Subscription R$ 9,90; Monthly RNI Pro Subscription R$ 4,90; Yearly RNI Pro Subscription R$ 49,90; Vintage Films Pack #1 R$ 24,90; Negative Films Pack #1 R$ 24,90; Negative Films Pack #2 R$ 24,90; (+2 more per-item SKUs)
- **Dehancer** (App Store id6443648413):
  - US ([store](https://apps.apple.com/us/app/id6443648413)): Unlimited Export (Monthly) $9.99; Unlimited Photo Export Month $4.99; Unlimited Export (Annual) $89.99; Unlimited Photo Export Year $49.99; Non-Renewable 1 Year Dehancer $150.00; Non-Renewable 1 Month Dehancer $9.99
  - VN ([store](https://apps.apple.com/vn/app/id6443648413)): Unlimited Export (Monthly) 249.000đ; Unlimited Photo Export Month 129.000đ; Unlimited Export (Annual) 2.299.000đ; Unlimited Photo Export Year 1.299.000đ; Non-Renewable 1 Year Dehancer 4.999.000đ; Non-Renewable 1 Month Dehancer 299.000đ
  - JP ([store](https://apps.apple.com/jp/app/id6443648413)): Unlimited Export (Monthly) ¥1,500; Unlimited Photo Export Month ¥700; Unlimited Export (Annual) ¥13,000; Unlimited Photo Export Year ¥7,000; Non-Renewable 1 Year Dehancer ¥25,000; Non-Renewable 1 Month Dehancer ¥1,500
  - KR ([store](https://apps.apple.com/kr/app/id6443648413)): Unlimited Export (Monthly) ￦14,000; Unlimited Photo Export Month ￦6,600; Unlimited Export (Annual) ￦129,000; Unlimited Photo Export Year ￦66,000; Non-Renewable 1 Year Dehancer ￦229,000; Non-Renewable 1 Month Dehancer ￦17,000
  - DE ([store](https://apps.apple.com/de/app/id6443648413)): Unlimited Export (Monthly) 9,99 €; Unlimited Photo Export Month 5,99 €; Unlimited Export (Annual) 99,99 €; Unlimited Photo Export Year 59,99 €; Non-Renewable 1 Year Dehancer 179,00 €; Non-Renewable 1 Month Dehancer 9,99 €
  - GB ([store](https://apps.apple.com/gb/app/id6443648413)): Unlimited Export (Monthly) £9.99; Unlimited Photo Export Month £4.99; Unlimited Export (Annual) £89.99; Unlimited Photo Export Year £49.99; Non-Renewable 1 Year Dehancer £150.00; Non-Renewable 1 Month Dehancer £9.99
  - ID ([store](https://apps.apple.com/id/app/id6443648413)): Unlimited Export (Monthly) Rp 169ribu; Unlimited Photo Export Month Rp 89ribu; Unlimited Export (Annual) Rp 1,499juta; Unlimited Photo Export Year Rp 799ribu; Non-Renewable 1 Year Dehancer Rp 2,999juta; Non-Renewable 1 Month Dehancer Rp 199ribu
  - BR ([store](https://apps.apple.com/br/app/id6443648413)): Unlimited Export (Monthly) R$ 49,90; Unlimited Photo Export Month R$ 24,90; Unlimited Export (Annual) R$ 499,90; Unlimited Photo Export Year R$ 249,90; Non-Renewable 1 Year Dehancer R$ 999,90; Non-Renewable 1 Month Dehancer R$ 59,90
- **Darkroom** (App Store id953286746):
  - US ([store](https://apps.apple.com/us/app/id953286746)): Monthly Subscription $9.99; Yearly Subscription $39.99; Legacy - Unlock Everything $9.99; Unlock Everything Forever $99.99; Legacy - All Premium Filters $7.99; Legacy - XPRO $3.99; Discounted Yearly Subscription $32.99; Legacy - All Tools $7.99; Legacy - Portrait Filters $3.99; Legacy - Black & White Filters $3.99
  - VN ([store](https://apps.apple.com/vn/app/id953286746)): Yearly Subscription 499.000đ; Monthly Subscription 149.000đ; Legacy - Unlock Everything 299.000đ; Legacy - All Premium Filters 249.000đ; Unlock Everything Forever 2.999.000đ; Legacy - XPRO 119.000đ; Discounted Yearly Subscription 899.000đ; Legacy - All Tools 249.000đ; Legacy - Landscape Filters 119.000đ; Legacy - Portrait Filters 119.000đ
  - JP ([store](https://apps.apple.com/jp/app/id953286746)): 年間サブスクリプション ¥3,000; 毎月のサブスクリプション ¥1,000; Legacy - Unlock Everything ¥1,500; Legacy - All Premium Filters ¥1,300; Legacy - XPRO ¥600; 割引年間サブスク ¥5,000; Legacy - All Tools ¥1,300; すべて永久的にアンロック ¥15,000; Legacy - Portrait Filters ¥600; (+1 more per-item SKUs)
  - KR ([store](https://apps.apple.com/kr/app/id953286746)): 연간 구독 ￦33,000; 월간 구독 ￦8,800; Legacy - Unlock Everything ￦17,000; Legacy - All Premium Filters ￦12,000; Legacy - XPRO ￦6,600; 할인 연간 구독 ￦44,000; 모든 항목 영원히 잠금 해제 ￦149,000; Legacy - All Tools ￦12,000; Legacy - Portrait Filters ￦6,600; (+1 more per-item SKUs)
  - DE ([store](https://apps.apple.com/de/app/id953286746)): Jahresabonnement 44,99 €; Monatliches Abo 9,99 €; Legacy - Unlock Everything 9,99 €; Legacy - All Premium Filters 8,99 €; Ermäßigtes Jahresabo 39,99 €; Legacy - XPRO 3,99 €; Legacy - All Tools 8,99 €; Alles für immer freischalten 99,99 €; Legacy - Portrait Filters 3,99 €; (+1 more per-item SKUs)
  - GB ([store](https://apps.apple.com/gb/app/id953286746)): Yearly Subscription £29.99; Monthly Subscription £5.99; Legacy - Unlock Everything £9.99; Unlock Everything Forever £99.99; Legacy - All Premium Filters £7.99; Discounted Yearly Subscription £29.99; Legacy - XPRO £3.99; Legacy - All Tools £7.99; Legacy - Landscape Filters £3.99; Legacy - Portrait Filters £3.99
  - ID ([store](https://apps.apple.com/id/app/id953286746)): Yearly Subscription Rp 399ribu; Monthly Subscription Rp 105ribu; Legacy - Unlock Everything Rp 199ribu; Legacy - All Premium Filters Rp 149ribu; Unlock Everything Forever Rp 1,999juta; Legacy - XPRO Rp 79ribu; Legacy - All Tools Rp 149ribu; Legacy - Portrait Filters Rp 79ribu; Legacy - Landscape Filters Rp 79ribu; (+1 more per-item SKUs)
  - BR ([store](https://apps.apple.com/br/app/id953286746)): Assinatura Anual R$ 149,90; Assinatura mensal R$ 36,90; Legacy - Unlock Everything R$ 59,90; Legacy - All Premium Filters R$ 49,90; Legacy - XPRO R$ 24,90; Legacy - All Tools R$ 49,90; Desbloqueie tudo para sempre R$ 599,90; Legacy - Portrait Filters R$ 24,90; (+2 more per-item SKUs)
- **Picsart** (App Store id587366035):
  - US ([store](https://apps.apple.com/us/app/id587366035)): Picsart Gold - Annual $57.00; Picsart Pro Annual $83.99; Picsart Gold - Monthly $12.99; Picsart Gold Yearly $57.00; Picsart Pro Monthly $13.99; Picsart Pro Weekly $11.99; Picsart Gold Weekly $4.99; Picsart Plus - Annual $64.99; Picsart Plus - Monthly $11.99
  - VN ([store](https://apps.apple.com/vn/app/id587366035)): Picsart Gold - Annual 399.000đ; Picsart Pro Annual 519.000đ; Picsart Gold - Monthly 67.000đ; Picsart Pro Weekly 47.000đ; Picsart Gold Yearly 399.000đ; Picsart Pro Monthly 87.000đ; Picsart Plus - Annual 399.000đ; Picsart Gold 6 Months 329.000đ
  - JP ([store](https://apps.apple.com/jp/app/id587366035)): Picsart Gold - Monthly ¥950; Picsart Gold - Annual ¥6,290; Picsart Pro Annual ¥9,300; Picsart Gold Yearly ¥6,290; Picsart Pro Monthly ¥1,500; Picsart Pro Weekly ¥1,050; Picsart Plus - Annual ¥7,190; Picsart Gold Weekly ¥580; Make Awesome Photos ¥950
  - KR ([store](https://apps.apple.com/kr/app/id587366035)): Picsart Gold - Annual ￦61,900; Picsart Gold - Monthly ￦9,900; Picsart Pro Weekly ￦4,100; Picsart Pro Annual ￦39,000; Picsart Gold 6 Months ￦24,500; Picsart Pro Monthly ￦5,900; Picsart Pro Monthly ￦12,900; Picsart Plus - Annual ￦61,900; Picsart Plus - Weekly ￦3,400
  - DE ([store](https://apps.apple.com/de/app/id587366035)): Picsart Gold - Annual 45,49 €; Picsart Pro Annual 57,99 €; Picsart Gold - Monthly 9,99 €; Picsart Pro Weekly 7,69 €; Picsart Pro Monthly 10,99 €; Picsart Plus - Annual 44,99 €; Picsart Gold Weekly 5,49 €; Picsart Plus - Monthly 8,99 €
  - GB ([store](https://apps.apple.com/gb/app/id587366035)): Picsart Gold - Annual £65.99; Picsart Pro Annual £85.99; Picsart Gold - Monthly £10.99; Picsart Gold Yearly £65.99; Picsart Pro Weekly £9.99; Picsart Gold Weekly £4.49; Picsart Plus - Annual £65.99; Picsart Pro Monthly £14.00; Credits £8.99
  - ID ([store](https://apps.apple.com/id/app/id587366035)): Picsart Gold - Annual Rp 299ribu; Picsart Pro Annual Rp 389ribu; Picsart Gold - Monthly Rp 39ribu; Picsart Pro Weekly Rp 35ribu; Picsart Pro Monthly Rp 50ribu; Picsart Plus - Annual Rp 299ribu; Picsart Plus - Monthly Rp 39ribu; Picsart Gold Yearly Rp 299ribu; Make Awesome Photos Rp 19.500
  - BR ([store](https://apps.apple.com/br/app/id587366035)): Picsart Gold - Annual R$ 162,90; Picsart Pro Annual R$ 264,90; Picsart Gold - Monthly R$ 31,90; Picsart Plus - Annual R$ 191,90; Picsart Pro Weekly R$ 34,99; Picsart Pro Monthly R$ 49,90; Picsart Gold Yearly R$ 162,90; Picsart Plus - Monthly R$ 37,99; Make Awesome Photos R$ 25,90
- **Hypic** (App Store id1644042837):
  - US ([store](https://apps.apple.com/us/app/id1644042837)): monthly-HypicPro $10.99; yearly-HypicPro $69.99; monthly-HypicPro $6.99
  - VN ([store](https://apps.apple.com/vn/app/id1644042837)): monthly-HypicPro 133.000đ; yearly-HypicPro 850.000đ; monthly-HypicPro 69.000đ
  - JP ([store](https://apps.apple.com/jp/app/id1644042837)): monthly-HypicPro ¥1,190; yearly-HypicPro ¥7,580
  - KR ([store](https://apps.apple.com/kr/app/id1644042837)): monthly-HypicPro ￦10,900; yearly-HypicPro ￦69,500
  - DE ([store](https://apps.apple.com/de/app/id1644042837)): monthly-HypicPro 9,99 €; yearly-HypicPro 36,99 €; yearly-HypicPro 64,99 €
  - GB ([store](https://apps.apple.com/gb/app/id1644042837)): monthly-HypicPro £8.99; yearly-HypicPro £37.99; yearly-HypicPro £55.99
  - ID ([store](https://apps.apple.com/id/app/id1644042837)): yearly-HypicPro Rp 540ribu; monthly-HypicPro Rp 85ribu
  - BR ([store](https://apps.apple.com/br/app/id1644042837)): monthly-HypicPro R$ 35,90; yearly-HypicPro R$ 229,90
- **Foodie** (App Store id1076859004):
  - US ([store](https://apps.apple.com/us/app/id1076859004)): Foodie PRO Monthly $6.99; Foodie PRO annual subscription $34.99; Foodie PRO annual subscription $31.99
  - VN ([store](https://apps.apple.com/vn/app/id1076859004)): Foodie PRO annual subscription 299.000đ; Foodie PRO Monthly 59.000đ; Foodie PRO annual subscription 269.000đ
  - JP ([store](https://apps.apple.com/jp/app/id1076859004)): Foodie PRO 月間購入 ¥750; Foodie PRO 年間購入 ¥3,600; Foodie PRO 年間購入 ¥3,300
  - KR ([store](https://apps.apple.com/kr/app/id1076859004)): Foodie PRO 월간 구독 ￦7,500; Foodie PRO 연간 구독 ￦36,000; Foodie PRO 연간 구독 ￦33,000
  - DE ([store](https://apps.apple.com/de/app/id1076859004)): Foodie PRO annual subscription 39,99 €; Foodie PRO Monthly 7,99 €; Foodie PRO annual subscription 34,99 €
  - GB ([store](https://apps.apple.com/gb/app/id1076859004)): Foodie PRO Monthly £6.99; Foodie PRO annual subscription £34.99; Foodie PRO annual subscription £29.99
  - ID ([store](https://apps.apple.com/id/app/id1076859004)): Foodie PRO annual subscription Rp 199ribu; Foodie PRO Monthly Rp 49ribu; Foodie PRO annual subscription Rp 179ribu
  - BR ([store](https://apps.apple.com/br/app/id1076859004)): Foodie PRO annual subscription R$ 199,90; Foodie PRO monthly R$ 39,90; Foodie PRO annual subscription R$ 229,90
- **CapCut** (App Store id1500855883):
  - US ([store](https://apps.apple.com/us/app/id1500855883)): Standard Monthly Subscription $9.99; Pro Monthly Subscription $19.99; Monthly Subscription $19.99; Yearly Subscription $89.99; Monthly Subscription $7.99
  - VN ([store](https://apps.apple.com/vn/app/id1500855883)): Standard Monthly Subscription 117.000đ; Pro Monthly Subscription 222.000đ; Monthly Subscription 150.000đ; Standard Yearly Subscription 700.000đ; Monthly Subscription 189.000đ
  - JP ([store](https://apps.apple.com/jp/app/id1500855883)): 毎月のサブスクリプション ¥1,080; Standard Monthly Subscription ¥1,080; Pro Monthly Subscription ¥2,180; Yearly Subscription ¥9,900; Monthly Subscription ¥1,080
  - KR ([store](https://apps.apple.com/kr/app/id1500855883)): Pro Monthly Subscription ￦19,800; 월간 구독 ￦9,900; Standard Monthly Subscription ￦9,900; Yearly Subscription ￦89,000
  - DE ([store](https://apps.apple.com/de/app/id1500855883)): Standard Monthly Subscription 11,99 €; Monatsabonnement 11,99 €; Pro Monthly Subscription 23,99 €; Yearly Subscription 109,99 €; Monatsabonnement 9,49 €
  - GB ([store](https://apps.apple.com/gb/app/id1500855883)): Standard Monthly Subscription £10.99; Monthly Subscription £10.99; Pro Monthly Subscription £21.99; Yearly Subscription £99.99; Purchased Credits £1.19
  - ID ([store](https://apps.apple.com/id/app/id1500855883)): Standard Monthly Subscription Rp 75ribu; Pro Monthly Subscription Rp 144ribu; Monthly Subscription Rp 103ribu; Standard Yearly Subscription Rp 455ribu
  - BR ([store](https://apps.apple.com/br/app/id1500855883)): Monthly Subscription R$ 32,90; Standard Monthly Subscription R$ 32,90; Inscrição mensal R$ 32,90; Pro Monthly Subscription R$ 65,90; Standard Yearly Subscription R$ 234,90; Inscrição mensal R$ 40,90
- **VN** (App Store id1343581380):
  - US ([store](https://apps.apple.com/us/app/id1343581380)): VN Pro $7.99; VN Pro $69.99; 100 Credits $1.00; 300 Credits $3.00; 1000 Credits $10.00; (+1 more per-item SKUs)
  - VN ([store](https://apps.apple.com/vn/app/id1343581380)): VN Pro 89.000đ; VN Pro 579.000đ; 100 Credits 29.000đ; 300 Credits 99.000đ; 1000 Credits 299.000đ; (+1 more per-item SKUs)
  - JP ([store](https://apps.apple.com/jp/app/id1343581380)): VN Pro ¥1,280; VN Pro ¥8,900; 100 Credits ¥150; 300 Credits ¥500; 1000 Credits ¥1,500; (+1 more per-item SKUs)
  - KR ([store](https://apps.apple.com/kr/app/id1343581380)): VN Pro ￦11,000; VN Pro ￦97,000; 100 Credits ￦1,100; 300 Credits ￦4,400; 1000 Credits ￦17,000; (+1 more per-item SKUs)
  - DE ([store](https://apps.apple.com/de/app/id1343581380)): VN Pro 8,99 €; VN Pro 78,99 €; 100 Credits 1,00 €; 300 Credits 3,00 €; 1000 Credits 10,00 €; (+1 more per-item SKUs)
  - GB ([store](https://apps.apple.com/gb/app/id1343581380)): VN Pro £7.99; VN Pro £66.99; 100 Credits £1.00; 300 Credits £3.00; 500 Credits £5.00; (+1 more per-item SKUs)
  - ID ([store](https://apps.apple.com/id/app/id1343581380)): VN Pro Rp 45ribu; VN Pro Rp 229ribu; 100 Credits Rp 19ribu; 300 Credits Rp 59ribu; 500 Credits Rp 99ribu; (+1 more per-item SKUs)
  - BR ([store](https://apps.apple.com/br/app/id1343581380)): VN Pro R$ 14,90; VN Pro R$ 79,90; 100 Credits R$ 6,90; 300 Credits R$ 19,90; 500 Credits R$ 29,90; (+1 more per-item SKUs)
- **Blackmagic Camera** (App Store id6449580241): no In-App Purchase list shown on the store page (free, no IAP)
- **OldRoll** (App Store id1570093460):
  - US ([store](https://apps.apple.com/us/app/id1570093460)): monthly rss $4.49; Yearly VIP-Trial4 $13.99; VIP-Monthly1 $4.99; Yearly VIP-Trial5 $19.99; Yearly VIP-Trial2 $12.99; vip forever $17.99; VIP|Forever $19.99; VIP-Yearly4 $13.99; Yearly VIP-Trial $13.99; VIP-Forever-1 $27.99
  - VN ([store](https://apps.apple.com/vn/app/id1570093460)): Yearly VIP-Trial 399.000đ; monthly rss 109.000đ; Unlock TOY S camera 29.000đ; vip forever 499.000đ; yearly rss 329.000đ; Yearly VIP-Trial2 349.000đ; VIP-Forever9 499.000đ; INS G-0 0đ; Quatre 29.000đ; BOX-OFFER2 29.000đ
  - JP ([store](https://apps.apple.com/jp/app/id1570093460)): monthly rss ¥500; Yearly VIP-Trial4 ¥1,900; VIP|Forever ¥3,000; yearly rss ¥1,900; vip forever ¥3,000; Unlock TOY S camera ¥150; VIP-Yearly4 ¥2,000; CCD Z ¥500; Digi ¥500; INS G-0 ¥0
  - KR ([store](https://apps.apple.com/kr/app/id1570093460)): monthly rss ￦5,900; Yearly VIP-Trial ￦19,000; vip forever ￦29,000; Yearly VIP-Trial2 ￦19,000; yearly rss ￦20,500; Unlock TOY S camera ￦1,100; CCD Z ￦4,400; INS G-0 ￦0; 4008N ￦4,400; (+1 more per-item SKUs)
  - DE ([store](https://apps.apple.com/de/app/id1570093460)): Yearly VIP-Trial 14,99 €; monthly rss 4,49 €; vip forever 19,99 €; Yearly VIP-Trial2 14,99 €; yearly rss 16,99 €; VIP-Forever9 17,99 €; INS G-0 0,00 €; Digi 2,99 €; Super8 0,99 €; (+1 more per-item SKUs)
  - GB ([store](https://apps.apple.com/gb/app/id1570093460)): monthly rss £3.99; Yearly VIP-Trial £12.99; Yearly VIP-Trial5 £19.99; VIP-Monthly1 £4.99; vip forever £17.99; Yearly VIP-Trial2 £12.99; yearly rss £14.49; VIP-Forever-1 £27.99; INS G-0 £0.00; Digi £2.99
  - ID ([store](https://apps.apple.com/id/app/id1570093460)): monthly rss Rp 75ribu; Yearly VIP-Trial4 Rp 219ribu; vip forever Rp 349ribu; VIP|Forever Rp 319ribu; Unlock TOY S camera Rp 19ribu; VIP-Forever9 Rp 299ribu; INS G-0 Rp 0; Digi Rp 59ribu; Quatre Rp 19ribu; (+1 more per-item SKUs)
  - BR ([store](https://apps.apple.com/br/app/id1570093460)): monthly rss R$ 22,90; Yearly VIP-Trial R$ 69,90; yearly rss R$ 71,90; Yearly VIP-Trial2 R$ 69,90; vip forever R$ 119,90; VIP-Forever9 R$ 99,90; INS G-0 R$ 0,00; Digi R$ 19,90; Quatre R$ 6,90; (+1 more per-item SKUs)
- **FILCA** (App Store id1436429074):
  - US ([store](https://apps.apple.com/us/app/id1436429074)): UPGRADE PRO $5.99; UPGRADE PRO VERSION $89.99; UPGRADE PRO $49.99; UPGRADE PRO (Discount) $59.99; KODAK SERIES FILM $5.99; RETRO SERIES FILM $4.99; FUJI SERIES FILM $4.99; (+3 more per-item SKUs)
  - VN ([store](https://apps.apple.com/vn/app/id1436429074)): UPGRADE PRO VERSION 2.999.000đ; UPGRADE PRO 199.000đ; UPGRADE PRO 1.499.000đ; UPGRADE PRO (Discount) 1.999.000đ; KODAK SERIES FILM 199.000đ; FUJI SERIES FILM 149.000đ; RETRO SERIES FILM 149.000đ; (+3 more per-item SKUs)
  - JP ([store](https://apps.apple.com/jp/app/id1436429074)): UPGRADE PRO ¥1,000; UPGRADE PRO VERSION ¥15,000; UPGRADE PRO ¥8,000; UPGRADE PRO (Discount) ¥10,000; KODAK SERIES FILM ¥1,000; FUJI SERIES FILM ¥800; RETRO SERIES FILM ¥800; (+3 more per-item SKUs)
  - KR ([store](https://apps.apple.com/kr/app/id1436429074)): UPGRADE PRO VERSION ￦149,000; UPGRADE PRO ￦8,800; UPGRADE PRO ￦77,000; ALL SERIES UNLOCK ￦33,000; KODAK SERIES FILM ￦9,900; RETRO SERIES FILM ￦7,700; FUJI SERIES FILM ￦7,700; (+3 more per-item SKUs)
  - DE ([store](https://apps.apple.com/de/app/id1436429074)): UPGRADE PRO VERSION 99,99 €; UPGRADE PRO 6,99 €; UPGRADE PRO 59,99 €; UPGRADE PRO (Discount) 69,99 €; KODAK SERIES FILM 6,99 €; RETRO SERIES FILM 5,99 €; FUJI SERIES FILM 5,99 €; (+3 more per-item SKUs)
  - GB ([store](https://apps.apple.com/gb/app/id1436429074)): UPGRADE PRO VERSION £89.99; UPGRADE PRO £5.99; UPGRADE PRO £49.99; UPGRADE PRO (Discount) £59.99; KODAK SERIES FILM £5.99; RETRO SERIES FILM £4.99; FUJI SERIES FILM £4.99; (+3 more per-item SKUs)
  - ID ([store](https://apps.apple.com/id/app/id1436429074)): UPGRADE PRO VERSION Rp 1,799juta; UPGRADE PRO Rp 99ribu; UPGRADE PRO Rp 799ribu; UPGRADE PRO (Discount) Rp 1,199juta; KODAK SERIES FILM Rp 119ribu; RETRO SERIES FILM Rp 99ribu; FUJI SERIES FILM Rp 99ribu; (+3 more per-item SKUs)
  - BR ([store](https://apps.apple.com/br/app/id1436429074)): UPGRADE PRO R$ 39,90; UPGRADE PRO VERSION R$ 599,90; UPGRADE PRO R$ 299,90; KODAK SERIES FILM R$ 39,90; RETRO SERIES FILM R$ 29,90; FUJI SERIES FILM R$ 29,90; (+4 more per-item SKUs)
- **DAZE CAM** (App Store id1464359734):
  - US ([store](https://apps.apple.com/us/app/id1464359734)): Premium Monthly $3.99; Premium $5.99; Premium Yearly $34.99; Premium Monthly $5.99; Premium Yearly $19.99; Premium $3.99; Premium $19.99
  - VN ([store](https://apps.apple.com/vn/app/id1464359734)): Premium Monthly 92.000đ; Premium 199.000đ; Premium Yearly 999.000đ; Premium Yearly 469.000đ; Premium Monthly 149.000đ; Premium 469.000đ; Premium 92.000đ
  - JP ([store](https://apps.apple.com/jp/app/id1464359734)): Premium Monthly ¥550; Premium ¥1,000; Premium Yearly ¥6,000; Premium Yearly ¥2,700; Premium Monthly ¥1,000; Premium ¥550; Premium ¥2,700
  - KR ([store](https://apps.apple.com/kr/app/id1464359734)): Premium Monthly ￦5,900; Premium ￦9,900; Premium Yearly ￦49,000; Premium Yearly ￦29,000; Premium Monthly ￦8,800; Premium ￦29,000; Premium ￦5,900
  - DE ([store](https://apps.apple.com/de/app/id1464359734)): Premium Monthly 4,49 €; Premium Yearly 39,99 €; Premium Monthly 6,99 €; Premium 6,99 €; Premium Yearly 23,49 €; Premium 4,49 €; Premium 23,49 €
  - GB ([store](https://apps.apple.com/gb/app/id1464359734)): Premium Monthly £3.99; Premium £5.99; Premium Yearly £34.99; Premium Monthly £5.99; Premium Yearly £19.99; Premium £3.99; Premium £19.99
  - ID ([store](https://apps.apple.com/id/app/id1464359734)): Premium Monthly Rp 65ribu; Premium Rp 119ribu; Premium Yearly Rp 599ribu; Premium Yearly Rp 329ribu; Premium Monthly Rp 99ribu; Premium Rp 329ribu; Premium Rp 65ribu
  - BR ([store](https://apps.apple.com/br/app/id1464359734)): Premium Monthly R$ 20,90; Premium R$ 39,90; Premium Yearly R$ 199,90; Premium Monthly R$ 29,90; Premium Yearly R$ 104,90; Premium R$ 104,90; Premium R$ 20,90
- **ProCCD** (App Store id1616113199):
  - US ([store](https://apps.apple.com/us/app/id1616113199)): VIP Weekly $2.99; Yearly VIP with Trial2 $8.99; Yearly VIP with Trial $5.99; VIP Yearly2 $5.99; VIP Yearly3 $8.99; VIP Yearly $5.99; Lifetime Purchase4 $17.99; New Lifetime Purchase $13.99; New Lifetime Purchase3 $14.99; Original2 $0.99
  - VN ([store](https://apps.apple.com/vn/app/id1616113199)): Yearly VIP with Trial 149.000đ; VIP Yearly2 149.000đ; VIP Yearly 149.000đ; New Lifetime Purchase2 399.000đ; New Lifetime Purchase 399.000đ; Lifetime Purchase Promo 299.000đ; Yearly VIP with Trial2 229.000đ; F71 59.000đ; Original2 29.000đ; IXUS210 29.000đ
  - JP ([store](https://apps.apple.com/jp/app/id1616113199)): VIP Weekly ¥500; Yearly VIP with Trial2 ¥1,500; VIP Yearly ¥900; VIP Yearly2 ¥900; Yearly VIP with Trial ¥900; VIP Yearly3 ¥1,500; Lifetime Purchase4 ¥3,000; New Lifetime Purchase ¥2,200; Original2 ¥150; IXUS210 ¥150
  - KR ([store](https://apps.apple.com/kr/app/id1616113199)): VIP Weekly ￦4,400; Yearly VIP with Trial2 ￦12,000; Yearly VIP with Trial ￦8,800; VIP Yearly ￦8,800; VIP Yearly2 ￦8,800; VIP Yearly3 ￦12,000; Lifetime Purchase Promo3 ￦22,000; Lifetime Purchase4 ￦29,000; New Lifetime Purchase ￦22,000; New Lifetime Purchase3 ￦25,000
  - DE ([store](https://apps.apple.com/de/app/id1616113199)): VIP Weekly 2,99 €; Yearly VIP with Trial2 9,99 €; Yearly VIP with Trial 6,99 €; VIP Yearly2 6,99 €; VIP Yearly 6,99 €; VIP Yearly3 9,99 €; Lifetime Purchase4 19,99 €; VIP Weekly3 3,99 €; New Lifetime Purchase 14,99 €; New Lifetime Purchase3 17,99 €
  - GB ([store](https://apps.apple.com/gb/app/id1616113199)): VIP Weekly £2.99; Yearly VIP with Trial2 £8.99; Yearly VIP with Trial £5.99; VIP Yearly £5.99; VIP Yearly2 £5.99; VIP Yearly3 £8.99; New Lifetime Purchase £12.99; Lifetime Purchase4 £17.99; New Lifetime Purchase3 £14.99; Original2 £0.99
  - ID ([store](https://apps.apple.com/id/app/id1616113199)): Yearly VIP with Trial Rp 99ribu; VIP Yearly2 Rp 99ribu; VIP Yearly Rp 99ribu; Yearly VIP with Trial2 Rp 149ribu; New Lifetime Purchase2 Rp 299ribu; Lifetime Purchase Promo Rp 179ribu; New Lifetime Purchase Rp 299ribu; VIP Monthly4 Rp 69ribu; IXUS210 Rp 19ribu; Original2 Rp 19ribu
  - BR ([store](https://apps.apple.com/br/app/id1616113199)): Yearly VIP with Trial R$ 29,90; VIP Yearly2 R$ 29,90; Yearly VIP with Trial2 R$ 59,90; VIP Yearly R$ 29,90; New Lifetime Purchase2 R$ 99,90; VIP Monthly3 R$ 24,90; Lifetime Purchase Promo R$ 59,90; VIP Monthly4 R$ 24,90; VIP Yearly3 R$ 59,90; Original2 R$ 6,90
- **Prequel** (App Store id1325756279):
  - US ([store](https://apps.apple.com/us/app/id1325756279)): Prequel Gold Weekly $5.99; Prequel Gold Weekly Special $2.99; Prequel Gold Weekly $4.99; Prequel Gold Yearly $14.99
  - VN ([store](https://apps.apple.com/vn/app/id1325756279)): Prequel Gold Weekly 119.000đ; Prequel Gold Weekly 79.000đ; Prequel Gold Yearly 399.000đ; Prequel Gold Weekly Special 69.000đ; Prequel Gold Weekly 99.000đ; Prequel Gold Yearly 699.000đ
  - JP ([store](https://apps.apple.com/jp/app/id1325756279)): Prequel Gold Weekly ¥550; Prequel Gold Weekly ¥400; Prequel Gold Weekly ¥600; Prequel Gold Weekly Special ¥350; Prequel Gold Yearly ¥3,500; Prequel Gold Yearly ¥2,200; Prequel Gold Yearly ¥2,500
  - KR ([store](https://apps.apple.com/kr/app/id1325756279)): Prequel Gold 주간 ￦6,500; Prequel Gold Weekly ￦4,400; Prequel Gold Weekly ￦6,500; Prequel Gold Weekly ￦5,500; Prequel Gold Yearly ￦33,000; Prequel Gold Weekly Special ￦3,900; Prequel Gold Yearly ￦22,000
  - DE ([store](https://apps.apple.com/de/app/id1325756279)): Prequel Gold Weekly 5,49 €; Prequel Gold Weekly 7,99 €; Prequel Gold Weekly Special 2,99 €; Prequel Gold Yearly 14,99 €; Prequel Gold Yearly 39,99 €
  - GB ([store](https://apps.apple.com/gb/app/id1325756279)): Prequel Gold Weekly £4.99; Prequel Gold Weekly £2.99; Prequel Gold Weekly Special £2.79; Prequel Gold Weekly £5.99; Prequel Gold Yearly £29.99; Prequel Gold Yearly £14.99
  - ID ([store](https://apps.apple.com/id/app/id1325756279)): Prequel Gold Weekly Rp 69ribu; Prequel Gold Weekly Rp 49ribu; Prequel Gold Weekly Rp 29ribu; Prequel Gold Weekly Special Rp 45ribu; Prequel Gold Weekly Rp 169ribu; Prequel Gold Yearly Rp 249ribu; Prequel Gold Yearly Rp 499ribu; Aesthetic Editor (Annual) Rp 499ribu
  - BR ([store](https://apps.apple.com/br/app/id1325756279)): Prequel Gold Weekly R$ 20,90; Prequel Gold Weekly R$ 19,90; Prequel Gold Weekly Special R$ 11,90; Prequel Gold Yearly R$ 79,90; Prequel Gold Yearly R$ 99,90; Prequel Gold Yearly R$ 144,90
- **Halide** (App Store id885697368):
  - US ([store](https://apps.apple.com/us/app/id885697368)): Pro Camera, Editor, and Lessons $19.99; Pro Camera, Editor, and Lessons $9.99; One Time Purchase $69.99
  - VN ([store](https://apps.apple.com/vn/app/id885697368)): Pro Camera, Editor, and Lessons 499.000đ; Pro Camera, Editor, and Lessons 249.000đ; One Time Purchase 1.999.000đ
  - JP ([store](https://apps.apple.com/jp/app/id885697368)): 1年間 ¥3,000; Pro Camera, Editor, and Lessons ¥1,500; 一回払い ¥11,000
  - KR ([store](https://apps.apple.com/kr/app/id885697368)): 연간 ￦29,000; Pro Camera, Editor, and Lessons ￦14,000; 결제는 한 번만 ￦110,000
  - DE ([store](https://apps.apple.com/de/app/id885697368)): Pro Camera, Editor, and Lessons 9,99 €; Jährlich 22,99 €; Einmaliger Kauf 79,99 €
  - GB ([store](https://apps.apple.com/gb/app/id885697368)): Pro Camera, Editor, and Lessons £19.99; Pro Camera, Editor, and Lessons £9.99; One Time Purchase £69.99
  - ID ([store](https://apps.apple.com/id/app/id885697368)): Pro Camera, Editor, and Lessons Rp 349ribu; Pro Camera, Editor, and Lessons Rp 169ribu; One Time Purchase Rp 1,299juta
  - BR ([store](https://apps.apple.com/br/app/id885697368)): Pro Camera, Editor, and Lessons R$ 59,90; Pro Camera, Editor, and Lessons R$ 49,90; One Time Purchase R$ 499,90

**Google Play "per item" IAP price ranges by country**

Scraped 2026-09-27. `gl=DE` and `gl=GB` returned no range, so they are omitted.
| Package (Play title, developer) | Installs (exact) | "Contains ads" label | US | VN | JP | KR | ID | BR |
|---|---|---|---|---|---|---|---|---|
| [app.filmode](https://play.google.com/store/apps/details?id=app.filmode&hl=en&gl=US) (Filmode Vibe — Film Camera; Trung-Hieu Tran) | 50+ (69) | not shown | $2.99 - $29.99 | ₫78,000 - ₫777,000 | ¥500 - ¥5,100 | ₩4,400 - ₩44,000 | Rp 53.000 - Rp 499.000 | R$14.99 - R$154.99 |
| [app.filmode.filcam](https://play.google.com/store/apps/details?id=app.filmode.filcam&hl=en&gl=US) (FilCam: Pro Manual RAW Camera; Trung-Hieu Tran) | 100+ (327) | not shown | $0.99 - $9.99 | ₫26,000 - ₫260,000 | ¥170 - ¥1,720 | ₩1,500 - ₩15,000 | Rp 18.000 - Rp 179.000 | R$4.99 - R$51.99 |
| [kr.co.manhole.hujicam](https://play.google.com/store/apps/details?id=kr.co.manhole.hujicam&hl=en&gl=US) (Huji Cam; Manhole, Inc.) | 10,000,000+ (46,158,827) | yes | $0.99 | ₫21,000 | ¥100 | ₩1,100 | Rp 13.000 | R$3.39 |
| [com.aaai.cam1998](https://play.google.com/store/apps/details?id=com.aaai.cam1998&hl=en&gl=US) (1998 Cam - Vintage Camera; AAAI Studio LLC) | 100,000+ (136,898) | yes | $1.99 - $39.99 | ₫79,000 - ₫1,050,000 | ¥520 - ¥7,000 | ₩4,800 - ₩65,000 | Rp 51.000 - Rp 690.000 | R$14.99 - R$199.99 |
| [com.blink.academy.nomopro](https://play.google.com/store/apps/details?id=com.blink.academy.nomopro&hl=en&gl=US) (NOMO CAM - Point and Shoot; Beijing Lingguang Zaixian Information Technology) | 5,000,000+ (9,748,244) | not shown | $0.99 - $24.99 | ₫23,000 - ₫580,000 | ¥110 - ¥2,720 | ₩1,100 - ₩32,000 | Rp 14.000 - Rp 349.000 | R$3.79 - R$104.99 |
| [com.sensemobile.action](https://play.google.com/store/apps/details?id=com.sensemobile.action&hl=en&gl=US) (Kapi Cam - Y2K & CCD Camera; Sensevideo) | 10,000,000+ (16,329,211) | not shown | $1.98 - $89.99 | ₫26,000 - ₫1,800,000 | ¥150 - ¥11,900 | ₩1,600 - ₩110,000 | Rp 16.000 - Rp 1.190.000 | R$5.99 - R$364.99 |
| [com.fimo.camera](https://play.google.com/store/apps/details?id=com.fimo.camera&hl=en&gl=US) (FIMO - Analog Camera; FIMO Studio) | 5,000,000+ (5,948,643) | not shown | $0.99 - $89.99 | ₫23,000 - ₫2,200,000 | ¥110 - ¥13,500 | ₩1,100 - ₩130,000 | Rp 14.000 - Rp 1.390.000 | R$5.49 - R$444.99 |
| [com.accordion.analogcam](https://play.google.com/store/apps/details?id=com.accordion.analogcam&hl=en&gl=US) (OldRoll - Vintage Film Camera; accordion) | 10,000,000+ (40,051,082) | yes | $0.49 - $94.99 | ₫11,000 - ₫2,200,000 | ¥70 - ¥13,200 | ₩700 - ₩140,000 | Rp 7.000 - Rp 1.390.000 | R$2.39 - R$519.99 |
| [filmcamera.vintagecamera.digitalcamera.retrocamera](https://play.google.com/store/apps/details?id=filmcamera.vintagecamera.digitalcamera.retrocamera&hl=en&gl=US) (Vintage Film Camera - Digicam; ZANKHANA PTE LTD) | 1,000,000+ (4,632,093) | yes | $0.99 - $19.99 | ₫26,000 - ₫521,000 | ¥170 - ¥3,160 | ₩1,600 - ₩30,000 | Rp 17.000 - Rp 329.000 | R$5.49 - R$109.99 |
| [com.vsco.cam](https://play.google.com/store/apps/details?id=com.vsco.cam&hl=en&gl=US) (VSCO: Photo Editor; VSCO) | 100,000,000+ (164,548,166) | not shown | $0.99 - $29.99 | ₫21,000 - ₫736,000 | ¥99 - ¥4,500 | ₩1,041 - ₩44,000 | Rp 4.000 - Rp 469.000 | R$2.51 - R$149.99 |
| [com.adobe.lrmobile](https://play.google.com/store/apps/details?id=com.adobe.lrmobile&hl=en&gl=US) (Lightroom Photo & Video Editor; Adobe) | 100,000,000+ (470,934,374) | not shown | $0.49 - $499.99 | ₫13,000 - ₫13,150,000 | ¥90 - ¥87,700 | ₩800 - ₩500,000 | Rp 8.500 - Rp 8.490.000 | R$2.59 - R$2,599.99 |
| [org.tezza](https://play.google.com/store/apps/details?id=org.tezza&hl=en&gl=US) (Tezza: Aesthetic Editor; Tezza) | 5,000,000+ (9,960,781) | not shown | $1.99 - $39.99 | ₫52,000 - ₫927,000 | ¥350 - ¥4,380 | ₩3,000 - ₩50,000 | Rp 35.000 - Rp 590.000 | R$9.99 - R$164.99 |
| [com.fueled.afterlight](https://play.google.com/store/apps/details?id=com.fueled.afterlight&hl=en&gl=US) (Afterlight: Film Photo Editor; Afterlight Collective, Inc.) | 10,000,000+ (11,393,540) | not shown | $0.99 - $39.99 | ₫21,000 - ₫1,050,000 | ¥102 - ¥7,000 | ₩1,006 - ₩60,000 | Rp 12.000 - Rp 690.000 | R$2.55 - R$204.99 |
| [photo.editor.polarr](https://play.google.com/store/apps/details?id=photo.editor.polarr&hl=en&gl=US) (Polarr: Photo Filters & Editor; Polarrcan) | 10,000,000+ (37,142,675) | yes | $0.99 - $34.99 | ₫23,000 - ₫573,000 | ¥110 - ¥3,460 | ₩1,300 - ₩38,000 | Rp 15.000 - Rp 369.000 | R$4.99 - R$124.99 |
| [com.picsart.studio](https://play.google.com/store/apps/details?id=com.picsart.studio&hl=en&gl=US) (Picsart AI Photo Editor, Video; PicsArt, Inc.) | 1,000,000,000+ (1,435,771,274) | yes | $0.99 - $429.99 | ₫5,000 - ₫11,150,000 | ¥60 - ¥74,300 | ₩600 - ₩600,000 | Rp 1.699 - Rp 7.690.000 | R$1.20 - R$2,199.99 |
| [com.xt.retouchoversea](https://play.google.com/store/apps/details?id=com.xt.retouchoversea&hl=en&gl=US) (Hypic - Photo Editor & AI Art; Bytedance Pte. Ltd.) | 100,000,000+ (122,665,658) | not shown | $2.99 - $159.99 | ₫69,000 - ₫3,800,000 | ¥400 - ¥21,600 | ₩4,100 - ₩210,000 | Rp 44.000 - Rp 2.390.000 | R$13.99 - R$829.99 |
| [com.linecorp.foodcam.android](https://play.google.com/store/apps/details?id=com.linecorp.foodcam.android&hl=en&gl=US) (Foodie - Filter & Film Camera; SNOW Corporation) | 10,000,000+ (42,274,345) | not shown | $6.99 - $34.99 | ₫59,000 - ₫299,000 | ¥750 - ¥3,600 | ₩7,500 - ₩36,000 | Rp 49.000 - Rp 199.000 | R$39.99 - R$199.99 |
| [com.lemon.lvoverseas](https://play.google.com/store/apps/details?id=com.lemon.lvoverseas&hl=en&gl=US) (CapCut - Video Editor; Bytedance Pte. Ltd.) | 1,000,000,000+ (2,009,892,307) | not shown | $0.49 - $900.00 | ₫1,400 - ₫23,499,000 | ¥12 - ¥144,800 | ₩80 - ₩600,000 | Rp 2.000 - Rp 15.999.000 | R$0.90 - R$4,599.00 |
| [com.frontrow.vlog](https://play.google.com/store/apps/details?id=com.frontrow.vlog&hl=en&gl=US) (VN: Photo & Video Editor; Ubiquiti Labs, LLC) | 100,000,000+ (333,932,593) | yes | $0.99 - $109.99 | ₫25,000 - ₫2,900,000 | ¥150 - ¥19,600 | ₩1,500 - ₩190,000 | Rp 16.000 - Rp 1.990.000 | R$4.99 - R$569.99 |
| [lv.mcprotector.mcpro24fps](https://play.google.com/store/apps/details?id=lv.mcprotector.mcpro24fps&hl=en&gl=US) (mcpro24fps manual video camera; Chantal Pro SIA) | 10,000+ (16,241) | not shown | $0.99 - $5.49 | ₫26,000 - ₫127,000 | ¥140 - ¥600 | ₩1,500 - ₩7,000 | Rp 16.000 - Rp 75.000 | R$5.49 - R$23.99 |
| [com.cerdillac.proccd](https://play.google.com/store/apps/details?id=com.cerdillac.proccd&hl=en&gl=US) (ProCCD - Digital Film Camera; cerdillac) | 10,000,000+ (22,229,436) | yes | $0.29 - $23.99 | ₫7,000 - ₫632,000 | ¥40 - ¥4,180 | ₩400 - ₩39,000 | Rp 4.400 - Rp 409.000 | R$1.39 - R$124.99 |
| [com.prequel.app](https://play.google.com/store/apps/details?id=com.prequel.app&hl=en&gl=US) (PREQUEL: Photo Editor, Filters; Prequel Inc.) | 50,000,000+ (63,128,065) | not shown | $0.49 - $49.99 | ₫11,111 - ₫1,200,000 | ¥60 - ¥8,900 | ₩700 - ₩85,000 | Rp 7.500 - Rp 890.000 | R$2.59 - R$999.99 |
| [com.vintage.camera.pro](https://play.google.com/store/apps/details?id=com.vintage.camera.pro&hl=en&gl=US) (Dazz Cam; MA CLO APPS) | 100,000+ (149,558) | not shown | $6.99 - $14.99 | ₫182,000 - ₫391,000 | ¥1,240 - ¥2,640 | ₩11,000 - ₩23,000 | Rp 119.000 - Rp 269.000 | R$35.99 - R$77.99 |
| [com.camerafilm.lofiretro](https://play.google.com/store/apps/details?id=com.camerafilm.lofiretro&hl=en&gl=US) (Dazzil Cam - Vintage Camera; DZ Film Cam - Retro & Vintage Studio) | 10,000,000+ (20,346,012) | yes | $1.99 - $69.99 | ₫52,000 - ₫1,800,000 | ¥350 - ¥12,100 | ₩3,000 - ₩100,000 | Rp 35.000 - Rp 1.290.000 | R$9.99 - R$359.99 |
| [com.camera.loficam](https://play.google.com/store/apps/details?id=com.camera.loficam&hl=en&gl=US) (LoFi Cam: Film Digital Camera; PixelPunk Inc.) | 1,000,000+ (2,476,984) | not shown | $2.49 - $14.99 | ₫43,000 - ₫254,000 | ¥270 - ¥1,620 | ₩2,600 - ₩15,000 | Rp 27.000 - Rp 159.000 | R$8.99 - R$53.99 |
| [com.ginnypix.kujicam](https://play.google.com/store/apps/details?id=com.ginnypix.kujicam&hl=en&gl=US) (Kuji Cam; GinnyPix) | 10,000,000+ (32,834,667) | yes | $0.99 - $2.29 | ₫13,000 - ₫54,000 | ¥100 - ¥460 | ₩1,000 - ₩2,600 | Rp 8.000 - Rp 34.000 | R$2.09 - R$9.49 |

### Inferences
- **Apple's default VN mapping, derived from apps using equalized tiers** (Filmode, Dazz single cameras, FIMO, Hipstamatic): $0.99→29.000đ, $1.99→59.000đ, $2.99→99.000đ, $4.99→149.000đ, $14.99→499.000đ, $19.99→599.000đ, $49.99→1.499.000đ.
- **Apps that deliberately under-price Vietnam, measured against that ladder:**
  - Dazz Pro: 99.000đ vs $6.99.
  - Kapi Weekly: 19.000đ vs $4.99.
  - Picsart Gold Annual: 399.000đ vs $57.
  - Hypic yearly: 850.000đ vs $69.99.
  - CapCut Standard monthly: 117.000đ vs $9.99.
  - RNI monthly: 22.000đ.
  - Big publishers therefore run regional price localization. Smaller Western apps (Tezza, Afterlight, VSCO) leave VN near parity.
- **Default JP/KR/BR mappings, observed on Filmode:**
  - JP: $0.99→¥150, $1.99→¥300, $14.99→¥2,500, $19.99→¥3,000.
  - KR: $0.99→₩1,100, $14.99→₩25,000.
  - BR: $0.99→R$6,90, $14.99→R$99,90.
  - EUR prices tend to be nominally higher than USD (Filmode yearly $14.99 vs 17,99 €; Dazz lifetime $19.99 vs 17,99 € is the exception).
- **The reference Filmode iOS pricing** ($1.99/mo, $4.99/3 mo, $14.99/yr, $19.99 lifetime) sits at the low end of the category. Kapi, VSCO, Tezza, Darkroom and Picsart are all 2–5x higher per year.

### Gaps
- Apple shows at most 10 IAPs per page, so some apps' full SKU sets (e.g. Dazz's weekly/yearly split, 1998 Cam's many variants) are incomplete. Durations are unknown where SKU names omit them (e.g. "Dazz Pro $6.99", "VN Pro $7.99 / $69.99", "Hipstamatic Camera Club $7.99/$19.99/$29.99").
- No Google Play EUR/GBP ranges, and no per-SKU Play prices, are available from the web listing.
- Trial lengths for Dazz, Kapi, 1998 Cam, Picsart, Hypic and CapCut were not found on official pages.

## Q3. Business-model patterns (subscription vs one-time vs per-camera vs ads), hybrids, price changes and backlash

### Takeaway
The category has moved from per-item packs (Hipstamatic HipstaPaks, FIMO films, NOMO cameras, Huji "Extra Options", Darkroom's "Legacy" à-la-carte) to **subscription + lifetime hybrids**. Photo & Video is the category where "subscription + lifetime" is most common: 33.0% of apps (RevenueCat). The best-grossing retro-camera app, Dazz, keeps a hybrid: subscription + one-time "Pro" + $0.99–$2.99 single cameras. Ads are mostly a volume/Android layer for Asian camera apps. Big AI editors add weekly plans and credits. Price hikes and tier restructurings (VSCO, CapCut, Kapi) consistently drew user backlash.

### Cited Findings
- **Monetization mix (RevenueCat, 2025 data):** across categories, apps are 63.5% subscription-only, 23.2% subscription+lifetime, 10.7% subscription+consumables and 2.5% all three. "Photo & Video has highest lifetime combo usage at 33.0%." "Only 10% apps run true hybrid models, largely in gaming" ([RevenueCat SOSA 2026](https://www.revenuecat.com/state-of-subscription-apps)).
- **Plan display (RevenueCat):** weekly plans appear on 33% of Photo & Video paywalls, the highest of any category; monthly is shown least in Photo & Video. More Photo & Video paywalls are low-text-density (27%) and non-scrolling (41%) than in any other category. Cancel-assurance appears on only 25.0% of Photo & Video paywalls, "~8pp below the next-lowest category" ([RevenueCat](https://www.revenuecat.com/state-of-subscription-apps)).
- **AI:** 61.4% of Photo & Video subscription apps are "AI-powered", more than 2x the 27.1% all-category average. AI apps convert trials better (median 8.5% vs 5.6%) but churn faster and see higher refunds (4.2% vs 3.5%) ([RevenueCat](https://www.revenuecat.com/state-of-subscription-apps)).
- **Hard paywall vs freemium (all categories, RevenueCat):** D35 download-to-paid is 10.7% for hard paywalls vs 2.1% for freemium. D14 revenue per install is $2.32 vs $0.27 for low-priced freemium. Y1 retention barely differs (27% vs 28% on yearly plans) ([RevenueCat](https://www.revenuecat.com/state-of-subscription-apps)).
- **Weekly plans' share of revenue (Adapty):** weekly plans produced 55.5% of all subscription revenue in 2025, up from 43.3% two years earlier. Monthly fell from 21.1% to 11.7% and annual from 29.2% to 22.5%. A weekly+trial cohort grows from $7.40 LTV at D0 to $54.50 at D380; annual+trial grows from $42.08 to $49.92 ([Adapty blog, Mar 2026](https://adapty.io/blog/mobile-app-monetization-2026/)).
- **Who uses which model in this niche (store pages, 2026-09-27):**
  - Per-camera + subscription + lifetime: Dazz, NOMO, OldRoll, ProCCD, FIMO.
  - Subscription + lifetime: Filmode, 1998 Cam, Kapi, Afterlight, Darkroom, RNI.
  - Subscription only: VSCO, Tezza, Hypic, Foodie, Prequel, Picsart (plus credits).
  - Subscription + AI credits: VN ("100 Credits $1.00"), Picsart (credits).
  - Paid upfront: mcpro24fps, Classic Hipstamatic, FILCA (FILCA adds IAP on top).
  - Free with no IAP: Blackmagic Camera, VSCO Capture.
  - Sources: see the per-app store links in Q1/Q2.
- **Ads + IAP hybrids on Android** (Play "Contains ads" label): Huji, 1998 Cam, OldRoll, ProCCD, Vintage Film Camera–Digicam, Dazzil Cam, Kuji Cam, Picsart, Polarr, VN ([Play listings](https://play.google.com/store/apps/details?id=com.accordion.analogcam&hl=en&gl=US); table in Q2).
- **VSCO repricing:** users reacted to the move from "$19.99/year flat pricing to tiered Plus ($39.99/year) and Pro ($59.99/year)" as a "100% price increase for Plus". Android users complain they "pay the same subscription but receive fewer features" ([checkthat.ai review summary – aggregator, secondary](https://checkthat.ai/brands/vsco/reviews)). The official page confirms Pro is "available on iOS and desktop only" ([vsco.co](https://www.vsco.co/subscribe/plans)).
- **VSCO business signal:** Bloomberg-reported profitability, 200M sign-ups and 160,000 Pro subscribers; "25% of its revenue now comes from VSCO Pro, which costs $59.99 per year"; VSCO said it "isn't even advertising its pro subscription" ([PetaPixel, May 2024 – older](https://petapixel.com/2024/05/20/vsco-is-now-profitable-thanks-to-200-million-users-and-160000-pro-subs/)).
- **CapCut restructure (late 2025 / early 2026):** "Pro pricing nearly doubling from about $9.99/month ($77.99/year) to $19.99/month ($179.99/year)". The old Pro became "Standard", and some previously free templates became paid ([BIGVU, secondary](https://bigvu.tv/blog/capcut-free-vs-pro-what-2026s-restructure-actually-gives-you/); [SocialRails, secondary](https://socialrails.com/blog/capcut-pricing-guide)). The iOS SKUs now read "Standard Monthly Subscription $9.99" and "Pro Monthly Subscription $19.99" ([App Store US](https://apps.apple.com/us/app/id1500855883)).
- **Kapi Cam:** users complain of "aggressive monetization shifts that lock previously free camera filters behind a subscription paywall" ([marlvel.ai – aggregator](https://marlvel.ai/apps/com-future-kapi)).
- **Darkroom's migration:** all Darkroom+ options, "including the one time purchase option, unlock all features now and moving forward" ([search summary of darkroom.co](https://darkroom.co/darkroom+)). Old purchases persist as "Legacy - Unlock Everything $9.99", "Legacy - XPRO $3.99" etc. ([App Store US](https://apps.apple.com/us/app/id953286746)).
- **Rewarded ads:** AdMob positions rewarded ads for non-games as a way to unlock premium content or trials ([AdMob](https://admob.google.com/home/resources/rewarded-ads-win-for-everyone/); [Verve](https://verve.com/blog/rewarded-video-ads-beyond-gaming-apps/)). Rewarded video pays the most per impression and hurts retention the least ([RevenueLab 2026](https://www.revenuelab.fyi/blog/admob-ecpm-benchmarks-2026)).

### Inferences
- Top-grossing apps in this niche (see Q6) are all subscription-led: Dazz, Tezza, VSCO, Lightroom, Hypic, Prequel. Pure per-item or ads-first retro cams (Huji, FIMO, Kuji, NOMO on Android) now earn under $5k–$30k/month despite millions of lifetime installs. Per-camera IAP works as an *add-on* to a subscription, not as the main model.
- A lifetime option is normal for Photo & Video (33% of apps). A $14.99–$39.99 lifetime next to a $9.99–$29.99 annual matches both the category norm and Dazz and 1998 Cam.
- Restructuring a free tier after launch (VSCO, CapCut, Kapi) creates visible backlash in reviews. Apple guideline 3.1.2(a) also says not to take away functionality existing users paid for (see Q5). The free/Pro line should be set at launch and kept.

### Gaps
- No verified data on how many camera/filter apps use rewarded-ad "unlock for 24h". This remains a pattern claim, not a measured one.
- No official Dazz price-change history. The Reddit/TikTok quotes surfaced by search could not be verified.

## Q4. Benchmarks: conversion, trials, retention, refunds, prices, ads (Photo & Video focus)

### Takeaway
Photo & Video is a high-install, low-conversion, short-trial, weekly-heavy category:
- Lowest median trial-to-paid of all categories: 22.2%, and only 17.1% on Google Play.
- 68% of trials are 4 days or shorter.
- Yet it has the best early revenue traction: median $124/month revenue one year after launch, versus $72 across all categories.

iOS converts downloads to payers about 2.9x better than Google Play, but Year-1 LTV per payer converges (about $23 vs $22). Tier-3 markets like Vietnam monetize at roughly 5–20% of US levels, for both subscriptions and ads.

### Cited Findings
**RevenueCat "State of Subscription Apps 2026"** (published March 2026; 2025 data; 115,000+ apps, $16B+ revenue) — [report](https://www.revenuecat.com/state-of-subscription-apps); [summary blog](https://www.revenuecat.com/blog/growth/subscription-app-trends-benchmarks-2026). Figures below are all from the report.

*Photo & Video category figures:*
- **Trial-to-paid:** median 22.2%, the lowest category; top quartile above 33.1%. By comparison, Travel is 43.5% and Health & Fitness 37.7%. On Google Play, Photo & Video is the lowest category at 17.1%; the global median is 32.0% on iOS vs 32.5% on Google Play.
- **Trial length:** 68.2% of Photo & Video trials are 4 days or shorter. Across categories, trials under 4 days convert at 25.5% vs 42.5% for 17+ day trials, and "55% of all 3-day trial cancellations happen on Day 0".
- **Post-launch revenue:** median monthly revenue one year after launch is $124 for Photo & Video, the highest category (all categories ~$72; top 10% above $2,574). Photo & Video's top 10% exceeds $3,600.
- **Revenue milestones:** within 2 years of launch, 21.4% of new Photo & Video apps hit $1K monthly revenue and 7.3% hit $10K. For all categories the figures are 17.3% and 4.6%.
- **Refunds:** most categories cluster at 3–4% median refund rate. Photo & Video is among the higher ones, "including higher p75 & outlier". Refunds rise with price: 2.7% (low price) → 3.9% (mid) → 4.5% (high).
- **Reactivation:** "Photo & Video monthly (20%) outperforms annual (8%) with project-based workflows".

*All-category figures (also RevenueCat 2026):*
- **Store gap:**
  - D35 download-to-paid: 2.6% on iOS vs 0.9% on Google Play (about 2.9x).
  - D60 revenue per install: $0.42 vs $0.16. In IN/SEA: iOS $0.15, Android $0.04.
  - Year-1 realized LTV per payer: App Store $23.38 vs Google Play $21.62. IN/SEA: $17.46 on iOS, $11.52 on Google Play.
- **Median prices, all categories:** weekly $5–$5.90, monthly $8, yearly $34.80 (up from $31.60). Most common price points are $5, $10 and $30.
- **Median prices by region:** IN/SEA prices sit at 46–54% of top markets. Monthly median is $3.75 in IN/SEA vs $9.99 in North America; yearly is $18.32 vs $39.99.
- **Retention:** yearly-plan Y1 retention is 28% (2024 cohort), monthly 8%, weekly 1.2%. Weekly 1st renewal is 55% in North America vs 37% in IN/SEA.
- **Offers:** intro offers are used by 72.9% of Google Play projects vs 41.2% on the App Store. 0% of Google Play projects use promo or win-back offers.
- **Cancellation reasons:** billing errors cause 32.2% of Google Play cancellations vs 15.2% on the App Store.
- **Platform shift:** iOS accounts for about 77% of new subscription-app launches.

**Adapty "State of In-App Subscriptions 2026"** (16,000 apps, $3B revenue; blog March 2026) — [blog](https://adapty.io/blog/mobile-app-monetization-2026/); [report page](https://adapty.io/state-of-in-app-subscriptions/):
- **Trial timing:** 89.4% of trial starts happen on Day 0; for Photo & Video it is 91.2%.
- **Android share:** Android captures 15.25% of global subscription revenue despite about 70% of users.
- **Revenue of new apps:** true median monthly revenue fell to $492 (from $627). 57.7% of new subscription apps earn under $1,000 in total, and only 7.9% pass $100,000.
- **What to test:** locale tests (translation + currency) give the largest LTV uplift (62.3%); price changes give the lowest (45.5%).
- **Weekly price tiers:** $5.71–$6.96 / $6.99–$7.65 / $7.99–$8.94 ([report page](https://adapty.io/state-of-in-app-subscriptions/)).
- **Photo & Video trial refunds:** "Photo & Video leads in trial refunds at 6.4% globally, spiking to 14.1% in APAC", attributed to Korea's refund rules. This is a search snippet of [adapty.io/state-of-in-app-subscriptions-report](https://adapty.io/state-of-in-app-subscriptions-report/); the gated report was not opened directly.

**Ad eCPM benchmarks (AdMob-style, 2026)** — aggregated by [RevenueLab, June 17, 2026](https://www.revenuelab.fyi/blog/admob-ecpm-benchmarks-2026) from AppLovin, ironSource, Unity and AdMob public reports:
- **US / Tier 1:**
  - Rewarded $14–$22.
  - Interstitial $9–$14.
  - App-open $4–$8.
  - Adaptive banner $0.40–$0.80.
- **Tier 3 (IN, ID, BR, PH, VN, …):**
  - Rewarded $2.00–$3.00.
  - Interstitial $1.00–$2.00.
  - Banner $0.06–$0.14.
  - eCPM index of 0.05–0.18x the US.
- **"Photo & video utilities" vertical (US):**
  - Rewarded $10–$15.
  - Interstitial $7–$11.
  - Typical ARPDAU $0.04–$0.09.
- **Other effects:** non-personalized ads pay 60–80% less; mediation lifts ARPDAU 18–22%.
- **Appodeal Q4 2024 Android (older, via search snippet):** US interstitial $14.08, US rewarded $16.49 ([Maf.ad summary of Appodeal](https://maf.ad/en/blog/mobile-ads-ecpm/)).

### Inferences
- For a Vietnamese team going Google Play first:
  - The same funnel earns roughly 2.5–3x less per install on Android than on iOS through D60.
  - Android is only about 15% of global subscription revenue.
  - Photo & Video trial conversion on Google Play (17.1%) is the worst cell in RevenueCat's table.
  - So Android should carry volume and ad revenue, while iOS carries subscription revenue.
- **Ad-revenue scale:** at Tier-3 rewarded eCPM of $2–3 and about 1–2 rewarded views per DAU, 10,000 VN/IN-heavy DAU yields only ~$20–60/day from rewarded ads. That is why Asian camera apps stack interstitials and banners and still earn little (Q6).
- **Paywall design:** Day-0 trial starts (91% in Photo & Video) and short trials argue for an onboarding paywall with a 3–7 day trial on the yearly plan. The weekly-plan data (Adapty) is strong for impulse/AI apps. Refund exposure is higher in Photo & Video, especially in APAC/Korea.

### Gaps
- RevenueCat's Photo & Video-specific price medians, download-to-paid, and refund medians are only in interactive charts; they were not in the page text and could not be extracted.
- No Superwall, Airbridge or Sensor Tower category report with Photo & Video subscription metrics was retrieved.
- No Vietnam-specific AdMob eCPM figure from a primary network report was found; Vietnam is only covered inside "Tier 3".

## Q5. Store fees and policies affecting what a developer keeps

### Takeaway
For a small developer (under $1M a year):
- **Google Play:** keeps 85% on almost everything worldwide. Since June 30, 2026 in the US, EEA and UK, the Play fee is 10% service + 5% billing on the first $1M (also 15% in total). Subscriptions are 10% (+5% billing) at any scale. Using external links or alternative billing lowers the fee, but Google now charges fees on those transactions too. Japan and Korea get the new model by end of 2026, the rest of the world in September 2027.
- **Apple:** keeps 85% via the Small Business Program. The EU moves to new terms on October 1, 2026 (15% for SBP on IAP, 10% for link-outs or alternative payments). The US link-out commission is still being litigated; Apple has proposed 5% for SBP apps.
- **Vietnam-based individual developers:** Apple withholds 2% personal income tax and 5% foreign-contractor tax on its commission. Google charges and remits 5% VAT on Vietnamese buyers' purchases for individuals and business households, and pays out in USD/EUR by wire (US$100 minimum).

### Cited Findings
**Google Play service fees** ([Play Console Help: Service fees](https://support.google.com/googleplay/android-developer/answer/112622?hl=en), fetched 2026-09-27):
- **EEA / UK / US, from June 30, 2026:**
  - First $1M of annual earnings: 10% + 5% billing fee.
  - Standard rates: auto-renewing subscriptions 10% + 5% billing fee; other transactions from new installs 20% + 5%; from existing installs 25% + 5%, "OR 20% for external web links".
  - With the Apps Experience or Play Games Level Up programs: subscriptions 10% + 5%; new-install transactions 15% + 5%; existing-install transactions 20% + 5% or 15% for external links.
  - The billing fee "applies when a user completes a purchase … using Google Play Billing".
- **All other markets, until the global rollout:**
  - 15% on the first $1M, then 30%.
  - Subscriptions 15% regardless of revenue.
  - Alternative billing in South Korea or India: the fee is reduced by 4%.
- **Rollout schedule:** EEA, UK and US by June 30, 2026; Australia in September; Japan and South Korea by end of 2026; "the rest of the world follows in September 2027" ([Help Net Security, Mar 5 2026](https://www.helpnetsecurity.com/2026/03/05/google-play-store-changes-android-app-distribution/)).
- **US timeline** ([Play Console Help](https://support.google.com/googleplay/android-developer/answer/15582165?hl=en)):
  - Since October 29, 2025 (Epic injunction), Google does not require Play Billing in the US and allows link-outs.
  - March 4, 2026: new settlement with Epic.
  - July 22, 2026: developers in the US external-links and alternative-billing programs "will need to report transactions and pay the relevant service fees starting on October 1, 2026".
  - September 17, 2026: the external-content-links deadline for reporting downloads moved to December 1, 2026.
- **User choice billing:** available in the EEA, UK, Japan, Australia, Brazil, Indonesia, South Africa, South Korea, India and the US, with the "service fee reduced by 4%" when the user pays through the alternative system ([Play Console Help: user choice billing](https://support.google.com/googleplay/android-developer/answer/13821247?hl=en)).

**Google Play subscription policy** (rejection risks) — [Play Policy: Subscriptions](https://support.google.com/googleplay/android-developer/answer/9900533?hl=en):
- Must disclose "the cost of your subscription, the frequency of your billing cycle, the automatic renewal terms, whether a subscription is required to use the app".
- Explicitly non-compliant examples:
  - A missing or unclear dismiss button.
  - Headline pricing shown "in terms of monthly breakdown cost, rather than what the users will actually be charged".
  - Showing only the introductory price.
  - Non-localized language or currency.
  - Emphasizing "free trial" so the charge is hard to read.
  - SKU names like "Free Trial" for auto-renewing products.
- Must explain how and when a trial converts and how to cancel, and must provide an in-app, easy online cancellation path.

**Apple:**
- **Small Business Program:** "reduced commission rate of 15% on paid apps and Apple In-App Purchases" for developers with up to $1M in proceeds in the prior calendar year (and new developers); above $1M the standard rate applies ([Apple SBP](https://developer.apple.com/app-store/small-business-program/)).
- **EU, from October 1, 2026** ([Apple Newsroom, Aug 2026](https://www.apple.com/newsroom/2026/08/apple-announces-changes-for-apps-in-the-european-union/)):
  - App Store IAP: 26% standard; 15% for the Small Business Program and "for auto-renewing subscriptions after their first year".
  - Alternative payment processing: 20% (10% for SBP).
  - Link-out: 15% (10% for SBP).
  - Alternative marketplaces or the web: 5% "Core Technology Commission", replacing the per-install Core Technology Fee.
- **US link-outs:** Apple's August 2026 proffer for off-App Store purchase commissions is 15% for standard apps, 10% for subscription renewals and partner programs, and 5% for Small Business Program apps. The district-court fee-setting is ongoing; the Supreme Court declined to pause it while it reviews the contempt question ([9to5Mac, Aug 13 2026](https://9to5mac.com/2026/08/13/apple-proposes-commissions-of-up-to-15-for-off-app-store-purchases-in-the-us/)). The Supreme Court granted Apple's petition on June 30, 2026 (per a search snippet of Apple's [10-Q for the quarter ended June 27, 2026](https://www.sec.gov/Archives/edgar/data/0000320193/000032019326000020/aapl-20260627.htm); not opened directly).
- **Japan (MSCA, in force December 18, 2025):**
  - Apple: "up to 26% total fees (21% App Store + 5% payment processing)", and it now allows alternative marketplaces.
  - Google: "dropped external-billing restrictions … but kept 30%/15% core fees".
  - JFTC compliance reports were published February 17, 2026 ([Abe International Law Office](https://abe-legal.jp/en/news/smartphone-act-implementation-2026)).
- **Apple guidelines:**
  - 3.1.2(a): a subscription must provide ongoing value and last at least 7 days. "If you are changing your existing app to a subscription-based business model, you should not take away the primary functionality existing users have already paid for."
  - 3.1.2(c): "Before asking a customer to subscribe, you should clearly describe what the user will get for the price."
  - [App Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)

**Vietnam-specific tax and payouts:**
- **Apple, effective August 21, 2025** ([Apple Developer News](https://developer.apple.com/news/?id=yo2104n5)):
  - "Individual developers based in Vietnam: Personal income tax (PIT) introduction of 2%, replacing the corporate income tax (CIT). FCT of 5% introduced on Apple's commission."
  - "Organizations based in Vietnam: Apple will no longer remit foreign contractor tax (FCT) on sales to end customers. FCT of 5% introduced on Apple's commission."
  - Foreign organizations: Vietnam VAT goes from 5% to 10%.
  - Apple has collected and remitted Vietnam taxes since the 2022 change ([Apple Developer News, 2022 – older](https://developer.apple.com/news/?id=e1b1hcmv)).
- **Google** ([Play Console Help: tax rates](https://support.google.com/googleplay/android-developer/answer/138000?hl=en)):
  - Vietnam-based "business household or individual": Google "will charge and remit a 5% VAT" on Vietnamese customers' purchases.
  - Other Vietnam-based entities must handle VAT themselves.
  - Google charges and remits 5% VAT on its service fee.
  - Developers must submit a 12-digit Vietnam tax code (PIN).
  - Developers outside Vietnam: Google remits 10% VAT on Vietnamese customers' purchases.
- **Payouts:** Vietnam supports Google Play developer and merchant registration. Buyers pay in VND, but "Developers in these countries will be paid in USD or EUR" ([Play Console Help: supported locations](https://support.google.com/googleplay/android-developer/answer/9306917?hl=en)). Payouts happen monthly, around the 15th; the minimum is US$100 for USD wire transfers and US$1 for local-currency payouts ([Play Console Help: payouts](https://support.google.com/googleplay/android-developer/answer/137997?hl=en)).
- **Enforcement context:** Vietnamese press (2021, older) reported that the Hanoi tax department collected over 203 billion VND in tax from individuals writing apps for Apple and Google ([VietNamNet](https://vietnamnet.vn/nhieu-nguoi-viet-ung-dung-cho-apple-store-vao-tam-ngam-cuc-thue-thu-203-ti-dong-tien-thue-i392144.html); headline via search, not opened).

### Inferences
- **Worked example: a $14.99/year subscription from a US user** for a Vietnam-based individual under $1M:
  - Google Play (from June 30, 2026): 10% + 5% billing = 15% → about $12.74 before Vietnamese income tax.
  - Apple (SBP): 15% commission → about $12.74, minus the 2% PIT withholding (about $0.30 if applied to the $14.99 sale; Apple does not state the base) and 5% FCT on Apple's $2.25 commission (about $0.11), leaving roughly $12.3 net. This is my arithmetic from the cited rates; it ignores sales tax/VAT, which stores deduct first where applicable.
- **Lifetime / one-time purchases on Google:** in the US, EEA and UK they sit under the "First $1M" row (10% + 5%) for small developers. Above $1M they cost 20–25% + 5%, versus 10% + 5% for subscriptions. At scale Google's fee structure favors subscriptions over lifetime unlocks.
- **Paywall design constraint:** "$1.25/mo" headline pricing for a yearly plan is explicitly cited as deceptive by Google. Show the real billed amount first.

### Gaps
- I did not verify whether Apple pays Vietnamese developers in VND or USD, or Apple's minimum payment threshold.
- Korea- and India-specific Apple alternative-payment rates were not researched here.
- The final US Apple link-out commission (pending in court) and the exact Google fees for Japan and Korea after their end-2026 rollout are not yet published.

## Q6. Revenue signals: public estimates for film-camera / preset / LUT apps

### Takeaway
All figures are **ESTIMATES**: Sensor Tower public overview meta descriptions, "last month", fetched 2026-09-27, worldwide per platform. Revenue is concentrated on iOS:
- Dazz Cam: ~2M downloads and ~$900k revenue a month on iOS alone.
- Tezza and VSCO: ~$2M/month each on iOS.
- Lightroom: ~$5M/month on iOS.

Android film-camera apps with huge install bases earn little:
- Kapi Cam: ~1M downloads → ~$9k.
- ProCCD: 600k → $8k.
- OldRoll: 400k → $20k.

### Cited Findings
iOS (App Store, worldwide estimate, last month; source = `https://app.sensortower.com/overview/{id}?country=US`):
- Dazz Cam: 2m downloads / $900k revenue ([ST](https://app.sensortower.com/overview/1422471180?country=US)).
- Tezza: 300k / $2m ([ST](https://app.sensortower.com/overview/1393061654?country=US)).
- VSCO: 400k / $2m ([ST](https://app.sensortower.com/overview/588013838?country=US)).
- Lightroom: 1m / $5m ([ST](https://app.sensortower.com/overview/878783582?country=US)).
- Prequel: 700k / $2m ([ST](https://app.sensortower.com/overview/1325756279?country=US)).
- Hypic: 1m / $800k ([ST](https://app.sensortower.com/overview/1644042837?country=US)).
- CapCut: 11m / $58m ([ST](https://app.sensortower.com/overview/1500855883?country=US)).
- VN: 1m / $200k ([ST](https://app.sensortower.com/overview/1343581380?country=US)).
- Foodie: 30k / $100k ([ST](https://app.sensortower.com/overview/1076859004?country=US)).
- OldRoll: 200k / $90k ([ST](https://app.sensortower.com/overview/1570093460?country=US)).
- Polarr: 40k / $80k ([ST](https://app.sensortower.com/overview/988173374?country=US)).
- ProCCD: 200k / $60k ([ST](https://app.sensortower.com/overview/1616113199?country=US)).
- NOMO CAM: 20k / $30k ([ST](https://app.sensortower.com/overview/1362548649?country=US)).
- Darkroom: <5k / $30k ([ST](https://app.sensortower.com/overview/953286746?country=US)).
- Afterlight: <5k / $20k ([ST](https://app.sensortower.com/overview/1293122457?country=US)).
- RNI Films: 8k / $20k ([ST](https://app.sensortower.com/overview/1017098672?country=US)).
- Dehancer: <5k / $20k ([ST](https://app.sensortower.com/overview/6443648413?country=US)).
- 1998 Cam: 80k / $10k ([ST](https://app.sensortower.com/overview/1450480287?country=US)).
- Kapi Cam: 300k / $7k ([ST](https://app.sensortower.com/overview/6740760807?country=US)).
- FILCA: <5k / $5k ([ST](https://app.sensortower.com/overview/1436429074?country=US)).
- Huji Cam: 90k / <$5k ([ST](https://app.sensortower.com/overview/781383622?country=US)).
- DAZE CAM: 20k / <$5k ([ST](https://app.sensortower.com/overview/1464359734?country=US)).
- Hipstamatic Analog: <5k / <$5k ([ST](https://app.sensortower.com/overview/1450672436?country=US)).
- Classic Hipstamatic: <5k / <$5k ([ST](https://app.sensortower.com/overview/342115564?country=US)).
- Blackmagic Camera: 1m downloads, no revenue shown ([ST](https://app.sensortower.com/overview/6449580241?country=US)).
- Filmode (iOS): <5k downloads ([ST](https://app.sensortower.com/overview/6791145420?country=US)).

Android (Google Play, worldwide estimate, last month):
- CapCut: 22m / $15m ([ST](https://app.sensortower.com/overview/com.lemon.lvoverseas?country=US)).
- Lightroom: 6m / $1m ([ST](https://app.sensortower.com/overview/com.adobe.lrmobile?country=US)).
- Hypic: 3m / $200k ([ST](https://app.sensortower.com/overview/com.xt.retouchoversea?country=US)).
- Prequel: 300k / $200k ([ST](https://app.sensortower.com/overview/com.prequel.app?country=US)).
- VN: 5m / $70k ([ST](https://app.sensortower.com/overview/com.frontrow.vlog?country=US)).
- VSCO: 300k / $60k ([ST](https://app.sensortower.com/overview/com.vsco.cam?country=US)).
- OldRoll: 400k / $20k ([ST](https://app.sensortower.com/overview/com.accordion.analogcam?country=US)).
- Tezza: 30k / $10k ([ST](https://app.sensortower.com/overview/org.tezza?country=US)).
- Foodie: 30k / $10k ([ST](https://app.sensortower.com/overview/com.linecorp.foodcam.android?country=US)).
- Kapi Cam: 1000k / $9k ([ST](https://app.sensortower.com/overview/com.sensemobile.action?country=US)).
- Vintage Film Camera–Digicam: 600k / $9k ([ST](https://app.sensortower.com/overview/filmcamera.vintagecamera.digitalcamera.retrocamera?country=US)).
- ProCCD: 600k / $8k ([ST](https://app.sensortower.com/overview/com.cerdillac.proccd?country=US)).
- Polarr: 40k / $7k ([ST](https://app.sensortower.com/overview/photo.editor.polarr?country=US)).
- 1998 Cam (AAAI): 30k / <$5k ([ST](https://app.sensortower.com/overview/com.aaai.cam1998?country=US)).
- NOMO CAM: 20k / <$5k ([ST](https://app.sensortower.com/overview/com.blink.academy.nomopro?country=US)).
- Huji Cam: 10k / <$5k ([ST](https://app.sensortower.com/overview/kr.co.manhole.hujicam?country=US)).
- Kuji Cam: <5k / <$5k ([ST](https://app.sensortower.com/overview/com.ginnypix.kujicam?country=US)).
- Afterlight: <5k / <$5k ([ST](https://app.sensortower.com/overview/com.fueled.afterlight?country=US)).
- FIMO: <5k / <$5k ([ST](https://app.sensortower.com/overview/com.fimo.camera?country=US)).
- mcpro24fps: <5k / <$5k ([ST](https://app.sensortower.com/overview/lv.mcprotector.mcpro24fps?country=US)).
- Dazzil Cam: 100k downloads, no revenue shown ([ST](https://app.sensortower.com/overview/com.camerafilm.lofiretro?country=US)).
- Blackmagic Camera: 300k downloads ([ST](https://app.sensortower.com/overview/com.blackmagicdesign.android.blackmagiccam?country=US)).
- Filmode Vibe and FilCam: <5k downloads each ([ST](https://app.sensortower.com/overview/app.filmode?country=US); [ST](https://app.sensortower.com/overview/app.filmode.filcam?country=US)).

Other signals:
- Cumulative Google Play installs (exact counter from the Play listing, 2026-09-27):
  - Huji: 46,158,827.
  - OldRoll: 40,051,082.
  - Kuji Cam: 32,834,667.
  - ProCCD: 22,229,436.
  - Dazzil Cam: 20,346,012.
  - Kapi Cam: 16,329,211.
  - NOMO: 9,748,244.
  - FIMO: 5,948,643.
  - VSCO: 164,548,166.
  - Lightroom: 470,934,374.
  - Hypic: 122,665,658.
  - Picsart: 1,435,771,274.
  - CapCut: 2,009,892,307.
  - Sources: the Q2 table links.
- iOS rating counts (US, iTunes lookup, 2026-09-27): Dazz Cam 114,851; VSCO 277,508; 1998 Cam 40,249; NOMO 48,176; Tezza 47,293; Afterlight 20,664; Huji 11,960 ([iTunes Search API](https://itunes.apple.com/search?term=dazz+cam&entity=software&country=us)).
- VSCO's 2025 revenue "estimated $85–95 million" (unsourced estimate in an aggregator; weak) ([Expanded Ramblings](https://expandedramblings.com/index.php/vsco-statistics-and-facts/)).
- Sensor Tower's U.S. snapshot for November 2024 (older): Canva >$8.5M, Facetune ~$4.8M, Remini ~$3.9M monthly U.S. revenue (via search snippet of a [Statista page](https://statista.com/statistics/1351014/top-grossing-fhoto-and-video-apps-us); not opened).

### Inferences
- **Revenue per download** in the retro-camera niche is roughly 10–100x higher on iOS than on Android:
  - Dazz iOS: about $0.45 per download.
  - Kapi Android: about $0.009.
  - ProCCD Android: about $0.013.
  - OldRoll: iOS $0.45 vs Android $0.05.
  - This is consistent with RevenueCat's 2.6–2.9x iOS advantage at category level, amplified in markets where film-cam apps are popular (Asia, Brazil).
- **Winning model:** the most successful indie-scale film-camera app (Dazz, one iOS app, ~$10M/yr run-rate if the estimate holds) uses cheap all-access Pro, a one-time lifetime and $0.99–$2.99 single cameras, with no ads. The high-install Android apps that lean on ads plus weekly/VIP subscriptions earn under $25k/month.
- **Room for mid-sized apps:** premium "film emulation" editors (Dehancer, RNI, Darkroom, Afterlight) each gross roughly $20–30k/month on iOS. A focused niche app can reach five figures a month without mass-market installs.

### Gaps
- Sensor Tower meta descriptions are rounded, give no month label, and have no per-country split. AppMagic and Appfigures pages returned nothing without login or JS (AppMagic returned empty content; Appfigures returned HTTP 403). Picsart's Sensor Tower pages returned no estimate text.
- No independent (press or company) revenue disclosure was found for Dazz, Kapi, 1998 Cam, OldRoll or ProCCD.
