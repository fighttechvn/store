# Film / retro / CCD / disposable camera apps: Filmode profile + competitor statistics (as of 2026-09-27)

Method note (applies to every section): all store data was pulled live on 2026-09-27.
- Google Play: store pages (`hl=en&gl=US` and `gl=VN`). Fields were parsed with the `google-play-scraper` library. "real" installs = the exact install count Google embeds in the page data. It is not shown to users, but it is store-derived, not an estimate.
- iOS: iTunes Lookup/Search API and apps.apple.com pages (for in-app purchase lists).
- Charts: Apple's iTunes RSS feed for the Photo & Video top 100 (genre 6008) and AppBrain's Google Play Photography rankings.
- Download and revenue figures: Sensor Tower public overview pages, from the "Last month's estimates" meta text. These are **ESTIMATES**. The month is most likely Aug 2026. Scope is probably worldwide but the page does not say.
- Install milestone dates: AndroidRank. These are third-party tracking, not store data.

Store URLs follow the patterns `https://play.google.com/store/apps/details?id=<pkg>&hl=en&gl=US`, `https://itunes.apple.com/lookup?id=<id>&country=<cc>`, `https://apps.apple.com/us/app/id<id>`, `https://app.sensortower.com/overview/<id or pkg>?country=US` and `https://www.androidrank.org/application/x/<pkg>`. Each row below links its own source.

---

## Q1. Filmode (app.filmode) and Filmode FilCam (app.filmode.filcam): full profile

### Takeaway
Both reference apps are brand-new Vietnamese solo/indie releases by "Trung-Hieu Tran" (FightTech, Vietnam). The developer contact on the FilCam page matches the requesting user's own account email, so these are almost certainly the team's own apps.
- Filmode Vibe: launched 22 Jul 2026, 50+ installs (69 exact).
- FilCam: launched 4 Sep 2026, 100+ installs (327 exact).
- Neither has a public rating yet (2 reviews each, all 5★).
- Both are ad-free freemium. Pro is sold monthly, yearly or lifetime, and on-device film LUTs are the core feature.
- Only Filmode has an iOS version ("Filmode - Film & LUT Editor", 0 ratings). On iOS it is a much larger product: 200+ looks, Film Roll, Match Photo and event passes.

### Cited Findings

**Developer**
- Google Play developer name for both apps: "Trung-Hieu Tran", developer ID 7730541199735528284 — [Play: Filmode](https://play.google.com/store/apps/details?id=app.filmode&hl=en&gl=US); [Play: FilCam](https://play.google.com/store/apps/details?id=app.filmode.filcam&hl=en&gl=US)
- Contact details differ by app:
  - Filmode lists email fighttech.vn@gmail.com, website http://filmode.app and privacy policy https://filmode.app/privacy.html.
  - FilCam lists website https://trunghieuvn.github.io/filmode-camera/ and a personal Gmail that matches the requesting user's account email.
  - Source: [Play: Filmode](https://play.google.com/store/apps/details?id=app.filmode&hl=en&gl=US); [Play: FilCam](https://play.google.com/store/apps/details?id=app.filmode.filcam&hl=en&gl=US)
- The FilCam website names the developer as "FightTech (Vietnam)" and states Android 8.0+, with iOS "Coming soon" — [FilCam site](https://trunghieuvn.github.io/filmode-camera/)
- filmode.app shows "© 2026 FightTech" and lists iOS, Android and a web camera (camera.html) — [filmode.app](https://filmode.app)
- The iOS seller name is "Tran Trung Hieu" — [iTunes Search](https://itunes.apple.com/search?term=filmode&entity=software&country=us)
- Other apps from the same Play developer: 10 more, all released 18–26 Sep 2026 and all at 0+ installs — [Play developer page](https://play.google.com/store/apps/dev?id=7730541199735528284&hl=en&gl=US)
  - Sound Amplifier: Ear Booster
  - Auto Scroll: Hands-Free Reader
  - Back Button: Home & Recent Key
  - Flowjar: Budget & Bill Tracker
  - Ringtone Maker & MP3 Cutter
  - StoreBeacon: App Analytics
  - Touch Lock: Block Screen Touch
  - Typing Test: WPM & Accuracy
  - Volume Button: On-Screen Keys
  - Voice Changer: Funny Effects

**Filmode Vibe — Film Camera (app.filmode, Google Play)**
- Store basics — [Play US](https://play.google.com/store/apps/details?id=app.filmode&hl=en&gl=US)
  - Released Jul 22, 2026; "Updated on" Sep 22, 2026; version 1.5.9.
  - 50+ installs (69 exact); no public rating yet.
  - Content rating "Everyone"; genre **Productivity** (not Photography).
  - Free with in-app purchases ($2.99 – $29.99 per item, US); contains ads: No.
- VN storefront IAP range: ₫78,000 – ₫777,000 per item — [Play VN](https://play.google.com/store/apps/details?id=app.filmode&hl=en&gl=VN)
- Data safety — [Play Data safety](https://play.google.com/store/apps/datasafety?id=app.filmode&hl=en&gl=US)
  - "No data shared with third parties".
  - Collected, all marked optional: Name, Email, User IDs, App interactions, Other user-generated content, Photos, Purchase history, Device or other IDs.
  - Encrypted in transit; users can request deletion.
- Not shown on the Play web page: Android minimum version ("Varies with device") and app size — [Play US](https://play.google.com/store/apps/details?id=app.filmode&hl=en&gl=US)
- Features in the store description — [Play US](https://play.google.com/store/apps/details?id=app.filmode&hl=en&gl=US)
  - Looks: 6 hand-crafted live looks (Golden, Teal, Analog, Glow, Midnight, Mono), rendered on the GPU with a "real 64³ film LUT".
  - 10 real-time effects baked in at capture: Rain, Halation, VHS, Frost, Grain, CCD (Y2K digicam), Flash, Dust, light Leak, cross-screen Star.
  - 3 camera "skins": Toy, Instant (the print ejects and develops) and Pro.
  - Pro camera: manual ISO, shutter, focus, white balance and exposure compensation; 4:3 / 1:1 / 16:9 / full aspect ratios.
  - Drive modes: burst, bracketing, intervalometer, night mode, focus stacking, dual-camera shot.
  - Photo editor: LUTs, presets, curves; **import your own .cube LUTs and Lightroom-style presets**.
  - Photobooth with on-device selfie segmentation over 6 gradients.
  - Video clips up to 15 s with LUT, rain and grain encoded in.
  - Frames: Polaroid, Booth, Cutie, Frame, Noir, Retro, Raw.
  - Cork-board "pin-board" of shots, plus cloud boards via Google sign-in and a web app.
  - Languages: English and Vietnamese.
- Free vs paid (Play description) — [Play US](https://play.google.com/store/apps/details?id=app.filmode&hl=en&gl=US)
  - "No ads and no watermark, ever."
  - Free: all cameras, effects, editor, photobooth and board; 18 looks (Basic + Retro); imported .cube LUTs and presets.
  - Filmode Pro adds 25 more looks (Cinematic, Film, Selfie) plus long exposure and light trails.
  - Pro is sold "monthly, yearly, or a one-time lifetime unlock". Pro looks can be previewed live, and the paywall appears only when saving.

**Filmode — Film & LUT Editor (iOS, id 6791145420, bundle app.filmode)**
- Store basics — [iTunes Lookup](https://itunes.apple.com/lookup?id=6791145420&country=us)
  - Released 2026-07-22; current version 1.4.4 dated 2026-09-19.
  - 44.3 MB; iOS 13.0+; 4+; Photo & Video; free; 0 ratings (US).
- Subtitle "Vintage camera & 35mm filters" — [App Store](https://apps.apple.com/us/app/id6791145420)
- Features — [App Store](https://apps.apple.com/us/app/id6791145420)
  - 200+ looks in 10 packs as of v1.4.4.
  - Film Roll: 12/24/36-frame rolls with delayed "development".
  - Match Photo (colour-match to a reference image); .cube and **.xmp** import; 4K video with looks.
  - 20 languages, including Vietnamese.
- In-app purchases (US) — [App Store](https://apps.apple.com/us/app/id6791145420)
  - Subscriptions and unlocks: Filmode Pro Monthly $1.99; 3-Month $4.99; Pro Yearly $14.99; Pro Lifetime $19.99.
  - Passes: Wedding Pass $49.99; Party Pass $9.99; Group Pass $2.99.
  - Packs: Cinematic Pack $2.99; Pro-Mist $0.99; Y2K Digicam $1.99.
- App Store version history: 1.0.0 on Jul 23, then 1.3.0 on Sep 4 (Vietnamese added), 1.4.1 on Sep 8, 1.4.2 on Sep 12, 1.4.4 on Sep 19 — [App Store](https://apps.apple.com/us/app/id6791145420)
- filmode.app also advertises the following, but lists no prices — [filmode.app](https://filmode.app)
  - LUT collections: Basic, Cinematic, Film, Selfie.
  - "LENS virtual film-camera models", batch editing, an App Clip and a web camera.
- Sensor Tower estimates last month's downloads at "< 5k" on both iOS and Android (ESTIMATE) — [ST iOS](https://app.sensortower.com/overview/6791145420?country=US); [ST Android](https://app.sensortower.com/overview/app.filmode?country=US)

**FilCam: Pro Manual RAW Camera (app.filmode.filcam, Google Play)**
- Store basics — [Play US](https://play.google.com/store/apps/details?id=app.filmode.filcam&hl=en&gl=US)
  - Released Sep 4, 2026; updated Sep 26, 2026; version 1.0.21.
  - 100+ installs (327 exact); no public rating.
  - "Everyone"; Photography.
  - IAP $0.99 – $9.99 per item (US); no ads.
- VN storefront IAP range: ₫26,000 – ₫260,000 — [Play VN](https://play.google.com/store/apps/details?id=app.filmode.filcam&hl=en&gl=VN)
- Data safety — [Play Data safety](https://play.google.com/store/apps/datasafety?id=app.filmode.filcam&hl=en&gl=US)
  - No data shared.
  - Collected, optional: Device or other IDs, App interactions, Crash logs, Diagnostics.
  - Encrypted in transit; deletion available.
- Features (Play description) — [Play US](https://play.google.com/store/apps/details?id=app.filmode.filcam&hl=en&gl=US)
  - Full manual ISO, shutter, exposure compensation, white balance in Kelvin and manual focus, with P/S/I/M modes.
  - **RAW DNG free**, saved alongside the JPEG; JPEG/HEIF/PNG output.
  - Long exposure up to 30 s (Pro); light trails from 15 s to 5 min (Pro).
  - Bracketing at 3/5/7 frames, focus stacking, night mode and intervalometer (Pro).
  - Viewfinder: histogram, grids, level; metering modes; AE/AF/AWB locks.
  - Film looks as 64³ LUTs baked into the JPEG; **.cube import**; built-in editor with saved recipes; volume-key mapping.
- Monetisation: "No ads and no watermark, ever"; FilCam Pro is "monthly, yearly with a 7-day free trial, or a one-time lifetime unlock" — [Play US](https://play.google.com/store/apps/details?id=app.filmode.filcam&hl=en&gl=US)
- The FilCam website adds: 43 film looks, focus peaking, false colour, zebra, waveform, and "prices displayed in your currency before you pay" — [FilCam site](https://trunghieuvn.github.io/filmode-camera/)
- iOS: searching "filcam" on the US App Store returns no FilCam by this developer. The website says iOS is "Coming soon" — [iTunes Search "filcam"](https://itunes.apple.com/search?term=filcam&entity=software&country=us); [FilCam site](https://trunghieuvn.github.io/filmode-camera/)

**Review themes (Play, all reviews available on 2026-09-27)**
- Filmode (2 reviews, both 5★) — [Play US](https://play.google.com/store/apps/details?id=app.filmode&hl=en&gl=US)
  - Praise: "shoot with live cinematic LUTs and see exactly how the final photo will look" (Jul 25).
  - Bug report: "whenever I captured an image, I cannot save it, it says error" (Sep 8). The developer replied that v1.5.0 fixes saving.
- FilCam (2 reviews, both 5★) — [Play US](https://play.google.com/store/apps/details?id=app.filmode.filcam&hl=en&gl=US)
  - Praise for the manual controls and RAW DNG (Sep 21).
  - "nice UI… Although, I cannot save a picture" (Sep 8).

### Inferences
- Photo saving is the first bug users have reported in both apps.
- Positioning is split across two listings. Filmode is filed under "Productivity" on Play, which likely hurts discovery in the Photography charts where every competitor lives.
- The Android and iOS Filmode products have diverged. Play lists 18 free + 25 Pro = 43 looks; iOS has 200+ looks, Film Roll and passes. A decision is needed on whether Filmode Android should reach iOS parity.
- Filmode's prices (Pro Yearly $14.99, Lifetime $19.99, Monthly $1.99) sit at the low end of the segment:
  - Dazz Pro is $6.99 and Dazz Lifetime $19.99.
  - OldRoll yearly runs $12.99–$19.99.
  - Kapi yearly is $69.99–$89.99 and Kapi lifetime $149.
  - Sources: see the Q2 table.
- The 10 utility apps released 18–26 Sep 2026 point to a portfolio / volume-publishing strategy by the same account.

### Gaps
- The Android minimum version and APK size for Filmode are not shown on the Play web page. FilCam's minimum (Android 8.0+) comes from its website only.
- Exact Android subscription SKUs and prices (weekly/monthly/yearly) are not exposed on the Play web page; only the per-item range is.
- Screenshots were not analysed. The feature list above comes from the store descriptions only.
- No public rating exists yet on either store, because the review count is below Google's display threshold.

---

## Q2. Competitor statistics: capture-first film/retro/CCD/disposable/instant camera apps (Google Play first, iOS second)

### Takeaway
The segment is large, but ownership is concentrated among Chinese, Korean and Singapore publishers.
- **Play:** ~38 film/retro capture apps checked hold **~343M exact Play installs**. The top 12 account for ~299M.
- **2018 generation, now stagnant on Play:** Huji 46.2M, Kuji 32.8M, Foodie 42.3M.
- **Newer apps growing fast:**
  - Kapi Cam: 16.3M; 5M → 10M between Jan and Apr 2026.
  - ProCCD: 22.2M.
  - Fomz: 31.7M.
  - Zankhana's Vintage Film Camera – Digicam: 4.6M in about 14 months.
- **Where the money is:** iOS. Dazz Cam is the category's revenue leader at about **$900k/month** (Sensor Tower estimate), yet it has no official Android app. On Play the "Dazz" name belongs to third-party look-alikes.

### Cited Findings

**Table A — Google Play (US storefront, fetched 2026-09-27)**

- Columns: installs band and exact installs; rating and number of ratings; IAP range; whether the app shows ads; release date; last update; Sensor Tower Android estimate for last month (ESTIMATE).
- Source for each row: the Play page for that package, `https://play.google.com/store/apps/details?id=<pkg>&hl=en&gl=US`.
- Sensor Tower column source: `https://app.sensortower.com/overview/<pkg>?country=US`.

| App (package) | Developer (country if known) | Band / exact installs | Rating (count) | IAP range | Ads | Released | Updated | ST last-month est. (DL / rev) |
|---|---|---|---|---|---|---|---|---|
| [Huji Cam](https://play.google.com/store/apps/details?id=kr.co.manhole.hujicam&hl=en&gl=US) (kr.co.manhole.hujicam) | Manhole, Inc. (KR, per `kr.co` package; hujicam.com) | 10M+ / 46,158,827 | 3.59 (190,485) | $0.99 | Yes | 2018-03-22 | 2026-01-30 | 10k / <$5k |
| [Foodie](https://play.google.com/store/apps/details?id=com.linecorp.foodcam.android&hl=en&gl=US) | SNOW Corporation (KR) | 10M+ / 42,274,345 | 3.58 (131,706) | $6.99–$34.99 | No | 2016-02-01 | 2026-09-08 | 30k / $10k |
| [OldRoll](https://play.google.com/store/apps/details?id=com.accordion.analogcam&hl=en&gl=US) | accordion (iOS seller 梓杰 张, CN individual) | 10M+ / 40,051,082 | 4.27 (213,230) | $0.49–$94.99 | Yes | 2020-08-28 | 2026-09-17 | 400k / $20k |
| [Kuji Cam](https://play.google.com/store/apps/details?id=com.ginnypix.kujicam&hl=en&gl=US) | GinnyPix | 10M+ / 32,834,667 | 3.97 (179,847) | $0.99–$2.29 | Yes | 2017-12-30 | 2026-08-26 | <5k / <$5k |
| [Fomz](https://play.google.com/store/apps/details?id=com.imendon.fomz&hl=en&gl=US) | MagicDmStudio (iOS seller Guangzhou Mengdong, CN) | 10M+ / 31,671,446 | 4.51 (89,993) | $1.99–$9.99 | Yes | 2022-05-05 | 2026-05-21 | n/a |
| [ProCCD](https://play.google.com/store/apps/details?id=com.cerdillac.proccd&hl=en&gl=US) | cerdillac (iOS seller 亚玲 查, CN individual) | 10M+ / 22,229,436 | 4.83 (198,138) | $0.29–$23.99 | Yes | 2022-07-08 | 2026-08-13 | 600k / $8k |
| [Dazzil Cam](https://play.google.com/store/apps/details?id=com.camerafilm.lofiretro&hl=en&gl=US) (third-party, NOT Dazz Pte Ltd) | DZ Film Cam - Retro & Vintage Studio (site dazzcam.app) | 10M+ / 20,346,012 | 4.14 (86,401) | $1.99–$69.99 | Yes | 2020-09-28 (VN page: 2024-03-31) | 2026-09-27 | 100k / n/a |
| [Vintage Camera-Retro, Editor](https://play.google.com/store/apps/details?id=com.camerafilter.ulook&hl=en&gl=US) | "Analog Film Photo & Photo Editor & Camera" | 10M+ / 18,333,697 | 4.58 (48,159) | $2.49–$5.99 | Yes | 2018-09-04 | 2026-07-06 | <5k / <$5k |
| [Kapi Cam - Y2K & CCD](https://play.google.com/store/apps/details?id=com.sensemobile.action&hl=en&gl=US) | Sensevideo (iOS seller TETRAS.AI HONGKONG CO., LIMITED, HK) | 10M+ / 16,329,211 | 4.58 (66,388) | $1.98–$89.99 | No | 2024-01-23 | 2026-09-15 | **1000k** / $9k |
| [Koda Cam](https://play.google.com/store/apps/details?id=com.camerafilter.kedakcam.insta.yellowsun.retrofilter&hl=en&gl=US) | "Analog Film Photo…" | 10M+ / 13,212,039 | 4.63 (43,364) | $2.99 | Yes | 2019-01-08 | 2024-11-26 | n/a |
| [NOMO CAM](https://play.google.com/store/apps/details?id=com.blink.academy.nomopro&hl=en&gl=US) | Beijing Lingguang Zaixian Information Technology (CN) | 5M+ / 9,748,244 | 3.73 (13,555) | $0.99–$24.99 | No | 2018-05-23 | 2026-04-03 | 20k / <$5k |
| [FIMO](https://play.google.com/store/apps/details?id=com.fimo.camera&hl=en&gl=US) | FIMO Studio (iOS seller Guangzhou Hongxiao, CN) | 5M+ / 5,948,643 | 3.09 (11,738) | $0.99–$89.99 | No | 2019-12-12 | 2025-10-21 | <5k / <$5k |
| [Disposable Camera - Lapse Cam](https://play.google.com/store/apps/details?id=com.pinklook.camerafilter.analogfilm.carbonapp&hl=en&gl=US) | "Analog Film Photo…" | 5M+ / 5,949,154 | 4.72 (19,583) | $0.99–$2.99 | Yes | 2018-12-27 | 2025-08-01 | <5k |
| [Film Camera-Analog Film](https://play.google.com/store/apps/details?id=com.camerafilter.analogfilter.canoncam&hl=en&gl=US) | "Analog Film Photo…" | 5M+ / 5,910,864 | 4.71 (21,954) | $2.99 | Yes | 2019-01-29 | 2026-07-15 | <5k |
| [Hypocam](https://play.google.com/store/apps/details?id=com.xnview.hypocam&hl=en&gl=US) | XnView | 5M+ / 5,620,931 | 4.36 (22,670) | $0.99–$6.99 | Yes | 2016-11-22 | 2026-09-24 | <5k |
| [Vintage Film Camera - Digicam](https://play.google.com/store/apps/details?id=filmcamera.vintagecamera.digitalcamera.retrocamera&hl=en&gl=US) | ZANKHANA PTE LTD (SG-registered by name) | 1M+ / 4,632,093 | 4.75 (108,810) | $0.99–$19.99 | Yes | 2025-07-11 | 2026-09-15 | 600k / $9k |
| [Retro Cam: Vintage Camera Filt](https://play.google.com/store/apps/details?id=photoeditor.oldfilter.retroeffect.vintagecamera&hl=en&gl=US) | Selfie Photo Editor… (braincake.net) | 1M+ / 2,876,543 | 4.30 (19,067) | none | No | 2018-11-01 | 2020-07-24 | n/a |
| [RetroCam: Film Vintage Camera](https://play.google.com/store/apps/details?id=com.itg.photofilter.vintagefilter&hl=en&gl=US) | Inception Technologies Global | 1M+ / 2,833,303 | 3.91 (32,739) | none | Yes | 2025-11-13 | 2026-04-07 | n/a |
| [LoFi Cam](https://play.google.com/store/apps/details?id=com.camera.loficam&hl=en&gl=US) | PixelPunk Inc. (pixelpunk.cn → CN) | 1M+ / 2,476,984 | 3.61 (1,512) | $2.49–$14.99 | No | 2024-02-22 | 2026-09-23 | 30k / <$5k |
| [Retro — Photos with Friends](https://play.google.com/store/apps/details?id=io.lonepalm.retro&hl=en&gl=US) | Lone Palm Labs | 1M+ / 1,934,469 | 4.71 (18,746) | $1.99–$35.99 | No | 2023-12-06 | 2026-09-25 | n/a |
| [OldReel - Vintage Camcorder](https://play.google.com/store/apps/details?id=com.changpeng.oldreel.dv&hl=en&gl=US) | changpeng (iOS seller 亚玲 查, same as ProCCD iOS) | 1M+ / 1,707,515 | 4.48 (9,129) | $5.99–$6.99 | Yes | 2024-05-31 | 2025-02-20 | 20k / <$5k |
| [Cuji Cam](https://play.google.com/store/apps/details?id=com.cuji.cam.camera&hl=en&gl=US) | N Dev Team | 1M+ / 1,649,680 | 4.83 (26,126) | $4.99–$9.99 | Yes | 2019-03-19 | 2026-08-02 | <5k |
| [Vintage Camera - Snap Film 90s](https://play.google.com/store/apps/details?id=com.bw.filtercam&hl=en&gl=US) | TBS Solution | 1M+ / 1,515,201 | 4.36 (3,200) | $2.49–$10.99 | Yes | 2019-03-05 | 2026-09-13 | n/a |
| [POV – Disposable Camera Events](https://play.google.com/store/apps/details?id=com.untitledshows.pov&hl=en&gl=US) | Untitled Tech, Inc. | 1M+ / 1,281,810 | 4.80 (6,539) | $4.99–$119.99 | No | 2022-12-22 | 2026-09-23 | 100k / $80k |
| [Super 16](https://play.google.com/store/apps/details?id=com.dwsh.super16&hl=en&gl=US) | Dmitry Shatilov | 1M+ / 1,231,671 | 4.72 (12,762) | $2.49–$26.99 | Yes | 2019-11-25 | 2026-08-12 | <5k |
| [y2k: 2000s photo editor](https://play.google.com/store/apps/details?id=com.abel.y2k&hl=en&gl=US) | Brick and Yarn, LLC | 1M+ / 1,095,187 | 4.85 (22,282) | $1.99–$14.99 | No | 2025-12-14 | 2026-09-23 | 80k / <$5k |
| [VHS Old Vintage Camera - Tapee](https://play.google.com/store/apps/details?id=com.owner.tapee&hl=en&gl=US) | JelloLab | 500K+ / 839,711 | n/a | $3.49–$79.99 | Yes | n/a | n/a | n/a |
| [Film Cam - Vintage Roll Camera](https://play.google.com/store/apps/details?id=com.lm.rolls.gp&hl=en&gl=US) | CoolMind Studio | 500K+ / 656,005 | 4.46 (16,447) | $0.49–$11.99 | No | 2022-06-13 | 2024-08-09 | n/a |
| [Dazzle Cam](https://play.google.com/store/apps/details?id=com.camerafilter.tikfilm.retroimage.ss.android.ugc.aweme.mobile&hl=en&gl=US) | "Analog Film Photo…" | 500K+ / 653,497 | 4.20 (1,888) | $0.49–$7.99 | Yes | 2024-10-11 | 2026-04-27 | n/a |
| [Fuji X Weekly — Film Recipes](https://play.google.com/store/apps/details?id=com.fujixweekly.FujiXWeekly&hl=en&gl=US) (recipe app, not camera) | Ritchie Roesch | 100K+ / 407,926 | 4.44 (875) | $19.99 | No | 2021-02-23 | 2026-09-17 | <5k |
| [Rarevision VHS](https://play.google.com/store/apps/details?id=com.rarevision.vhscamcorder&hl=en&gl=US) (paid $4.99) | Rarevision | 100K+ / 234,289 | 4.82 (12,038) | none | No | 2016-02-17 | 2026-03-23 | n/a |
| [Dazzix Cam](https://play.google.com/store/apps/details?id=com.dazzcam.cameradazzcam&hl=en&gl=US) (Dazz look-alike) | Sidra Tech.ol | 100K+ / 172,600 | n/a | none | Yes | 2025-12-03 | n/a | n/a |
| ["Dazz Cam"](https://play.google.com/store/apps/details?id=com.vintage.camera.pro&hl=en&gl=US) (look-alike, not Dazz Pte Ltd) | MA CLO APPS | 100K+ / 149,558 | 3.55 (241) | $6.99–$14.99 | No | **2026-08-30** | n/a | <5k |
| [1998 Cam](https://play.google.com/store/apps/details?id=com.aaai.cam1998&hl=en&gl=US) (re-listed) | AAAI Studio LLC | 100K+ / 136,898 | 4.44 (785) | $1.99–$39.99 | Yes | 2026-04-21 (re-release) | 2026-09-07 | 30k / <$5k |
| [Dazzy Cam](https://play.google.com/store/apps/details?id=com.dazzycam.vintagecamera&hl=en&gl=US) | LVQ Studio | 100K+ / 111,942 | n/a | $1.99 | Yes | 2026-04-16 | n/a | n/a |
| [Bebo Cam: Retro Instant](https://play.google.com/store/apps/details?id=com.pixelpunk.bebocam&hl=en&gl=US) | PixelPunk Inc. | 50K+ / 92,535 | n/a | $1.49–$9.99 | Yes | 2024-12-09 | 2026-09-21 | n/a |
| [Grain - Pro Film Camera](https://play.google.com/store/apps/details?id=com.graincamera&hl=en&gl=US) | Grain Camera | 50K+ / 91,657 | 4.42 (297) | none | No | 2025-09-16 | 2026-08-05 | n/a |
| [CCD Cam-Y2K Retro](https://play.google.com/store/apps/details?id=com.filter.camera.ccd.pro&hl=en&gl=US) | BitDance AI Studio | 50K+ / 78,103 | 4.64 (755) | $1.49–$12.99 | Yes | 2024-05-10 | 2026-04-10 | n/a |
| [FujiStyle - Film Recipes Frame](https://play.google.com/store/apps/details?id=com.fujistylelead.global&hl=en&gl=US) | Turing Vision (iOS seller 罡 丁) | 10K+ / 21,872 | 4.40 (632) | $0.49–$28.99 | No | 2025-12-25 | n/a | n/a |
| [Y2K Camera: CCD, Film & VHS](https://play.google.com/store/apps/details?id=retro.rr.xx.camera&hl=en&gl=US) | JingSay | 10K+ / 30,017 | 4.40 (480) | $0.99–$5.99 | No | 2026-02-12 | n/a | n/a |

**Asian camera-filter apps with film modes (Play US, 2026-09-27)**

Same column meanings as Table A.

| App | Developer | Band / exact | Rating (count) | IAP range | Ads | Released | Updated |
|---|---|---|---|---|---|---|---|
| [B612](https://play.google.com/store/apps/details?id=com.linecorp.b612.android&hl=en&gl=US) | SNOW Corporation (KR) | 500M+ / 872,401,442 | 4.04 (7,190,487) | $0.99–$69.99 | No | 2014-10-09 | 2026-09-16 |
| [Retrica: Digicam Filter Camera](https://play.google.com/store/apps/details?id=com.venticake.retrica&hl=en&gl=US) | Retrica, Inc. | 100M+ / 372,502,874 | 3.51 (5,825,765) | $1.99–$59.99 | Yes | 2014-04-10 | 2026-09-22 |
| [SNOW](https://play.google.com/store/apps/details?id=com.campmobile.snow&hl=en&gl=US) | SNOW Corporation | 100M+ / 185,926,280 | 3.72 (1,459,921) | $0.99–$69.99 | No | 2015-11-03 | 2026-09-16 |
| [VSCO](https://play.google.com/store/apps/details?id=com.vsco.cam&hl=en&gl=US) (editor reference) | VSCO | 100M+ / 164,548,166 | 3.62 (1,325,500) | $0.99–$29.99 | No | 2013-12-03 | 2026-09-21 |
| [Hypic](https://play.google.com/store/apps/details?id=com.xt.retouchoversea&hl=en&gl=US) | Bytedance Pte. Ltd. | 100M+ / 122,665,658 | 3.09 (262,307) | $2.99–$159.99 | No | 2023-01-03 | 2026-09-23 |
| [Ulike](https://play.google.com/store/apps/details?id=com.gorgeous.liteinternational&hl=en&gl=US) | Bytedance Pte. Ltd. | 50M+ / 78,504,765 | 4.65 (716,363) | n/a | No | n/a | 2025-02-11 |
| [PREQUEL](https://play.google.com/store/apps/details?id=com.prequel.app&hl=en&gl=US) | Prequel Inc. | 50M+ / 63,128,065 | 4.52 (394,361) | $0.49–$49.99 | No | 2020-05-24 | 2026-09-16 |
| [SODA](https://play.google.com/store/apps/details?id=com.snowcorp.soda.android&hl=en&gl=US) | SNOW Corporation | 10M+ / 44,297,811 | 4.20 (180,306) | $9.99–$59.99 | No | 2018-10-10 | 2026-09-23 |

**Table B — iOS (US ratings via iTunes Lookup; IAP lists from the US App Store page; Sensor Tower iOS last-month ESTIMATES)**

- Lookup source: [iTunes Lookup (US)](https://itunes.apple.com/lookup?id=1422471180,781383622,1450480287,1362548649,6740760807,1570093460,1616113199,1454219307,1076859004,1636699256,1464359734,1597218253,1615744942,1079944301&country=us)
- Each app name links to its App Store page. The Sensor Tower source for each row is `https://app.sensortower.com/overview/<id>?country=US`.

| App (id) | Seller | US ratings (avg) | iOS launch | Last update | US IAP / price points (as shown) | ST est. last month (DL / rev) |
|---|---|---|---|---|---|---|
| [Dazz Cam](https://apps.apple.com/us/app/id1422471180) (1422471180) | DAZZ PTE. LTD. (SG, inc. 22 Feb 2023) | 114,851 (4.75) | 2018-08-17 | 2026-09-25 | Dazz Pro $6.99; Pro One-Time $19.99; single cameras/accessories $0.99–$2.99 | **2m / $900k** |
| [1998 Cam](https://apps.apple.com/us/app/id1450480287) (1450480287) | AAAI Studio LLC | 40,249 (4.80) | 2019-02-01 | 2026-09-26 | Monthly $1.99–$5.99; Yearly $15.99–$29.99; Lifetime $39.99 | 80k / $10k |
| [NOMO CAM](https://apps.apple.com/us/app/id1362548649) (1362548649) | Beijing Lingguang Zaixian (CN) | 48,176 (4.66) | 2018-04-22 | 2026-04-08 | NOMO PRO (1 Year) $24.99; per-camera $0.99–$1.99; some $0.00 | 20k / $30k |
| [Huji Cam](https://apps.apple.com/us/app/id781383622) (781383622) | Manhole, Inc. | 11,960 (4.22) | 2017-09-28 | 2024-12-11 | Extra Options $0.99 | 90k / <$5k |
| [OldRoll](https://apps.apple.com/us/app/id1570093460) (1570093460) | 梓杰 张 | 5,589 (4.71) | 2021-06-04 | 2026-09-17 | Monthly $4.49–$4.99; Yearly $12.99–$19.99; Forever $17.99–$27.99 | 200k / $90k |
| [ProCCD](https://apps.apple.com/us/app/id1616113199) (1616113199) | 亚玲 查 | 2,134 (4.74) | 2022-03-31 | 2026-09-21 | Weekly $2.99; Yearly $5.99–$8.99; Lifetime $13.99–$17.99 | 200k / $60k |
| [Kapi Cam](https://apps.apple.com/us/app/id6740760807) (6740760807) | TETRAS.AI HONGKONG CO., LIMITED | 1,657 (4.70) | 2025-03-03 | 2026-09-11 | Weekly $4.99; Monthly $9.99–$12.99; Yearly $69.99–$89.99; Life-time $149.00 | 300k / $7k |
| [Foodie](https://apps.apple.com/us/app/id1076859004) (1076859004) | SNOW Corporation | 9,319 (4.74) | 2016-02-02 | 2026-09-09 | PRO Monthly $6.99; annual $31.99–$34.99 | 30k / $100k |
| [ism: Retro Camera & Vintage](https://apps.apple.com/us/app/id1580668065) (1580668065) | MWM | 11,248 (4.73) | 2021-11-04 | 2026-09-17 | Weekly $3.99–$7.99; Yearly $19.99–$29.99 | 100k / $200k |
| [101cam - Film & Digital Camera](https://apps.apple.com/us/app/id6781998623) (6781998623) | SNOW Corporation | 89 (4.65) | **2026-07-10** | 2026-09-22 | 101 PRO monthly $4.99; annual $13.99 | 60k / <$5k |
| [Esti: Aesthetic Photo Editor](https://apps.apple.com/us/app/id6457366208) (vintage-camera filters) | Prequel Inc. | 18,612 (4.64) | 2023-10-25 | 2026-09-03 | Weekly $4.99–$6.99; Yearly $14.99 (trial) / $39.99 | 300k / $800k |
| [Fomz](https://apps.apple.com/us/app/id1615744942) (1615744942) | Guangzhou Mengdong (CN) | 1,215 (4.71) | 2022-04-18 | 2026-06-23 | Monthly $0.49–$0.99; Yearly $3.99–$4.49; Permanent $5.99–$6.99 | 200k / $10k |
| [radcam](https://apps.apple.com/us/app/id1079944301) (1079944301) | Going Merry LLC | 39,216 (4.49) | 2016-02-24 | 2026-09-19 | Weekly $3.99–$4.99; Yearly $29.99–$39.99; Unlock All $5.99–$29.99; credits | 70k / $10k |
| [DAZE CAM](https://apps.apple.com/us/app/id1464359734) (1464359734) | Half Tab Inc. | 11,931 (4.75) | 2019-08-19 | 2026-09-01 | Monthly $3.99–$5.99; Yearly $19.99–$34.99 | 20k / <$5k |
| [Lapse - Disposable Camera](https://apps.apple.com/us/app/id1636699256) (social) | Lapse Ltd | 118,276 (4.75) | 2022-07-28 | 2025-12-06 | (none listed) | <5k |
| [Retro — Photos with Friends](https://apps.apple.com/us/app/id6443709020) (social) | Lone Palm Labs | 15,626 (4.78) | 2023-07-13 | 2026-09-18 | Weekly $1.99; Monthly $4.99; Annual $35.99 | 600k / $30k |
| [Leica LUX](https://apps.apple.com/us/app/id6477182657) (pro manual + Leica looks) | Leica Camera AG | 7,619 (4.85) | 2024-06-05 | 2026-09-24 | PRO Monthly $6.99; Annual $69.99 | 60k / $300k |
| [flag7x: g7x style camera](https://apps.apple.com/us/app/id6747452095) | Ranjha, Inc. | 185 (4.58) | 2025-06-30 | 2026-09-23 | pro $4.99 / $19.99; Lifetime $24.99 | 50k / $10k |
| [Film Camera - Vintage Camera](https://apps.apple.com/us/app/id6740308477) (iOS twin of Zankhana's Play app) | Zankhana Pte Ltd | 128 (4.79) | 2025-05-25 | 2026-09-22 | Monthly $3.99; Yearly $6.99; Lifetime $13.99–$19.99; single cam $1.99–$2.99 | <5k / <$5k |
| [FIMO](https://apps.apple.com/us/app/id1454219307) | Guangzhou Hongxiao (CN) | 258 (3.97) | 2019-04-09 | 2025-12-17 | per-film $0.99–$1.99; pro 1 year $29.99 | <5k / <$5k |
| [Hipstamatic Analog Camera](https://apps.apple.com/us/app/id1450672436) | Hipstamatic, LLC | 2,788 (4.62) | 2019-10-01 | 2026-08-19 | Camera Club $7.99 / $19.99 / $29.99 | <5k / <$5k |
| [Classic Camera by Hipstamatic](https://apps.apple.com/us/app/id342115564) (paid $4.99) | Hipstamatic, LLC | 4,546 (4.74) | 2009-12-10 | 2026-05-01 | — | <5k / <$5k |
| [Kada Cam](https://apps.apple.com/us/app/id1597218253) | Hangzhou Yuhang Solo Tech Studio (CN) | 1,765 (4.68) | 2021-11-30 | 2026-08-30 | Monthly $1.99; Yearly $5.49; One-time $12.99 | <5k / <$5k |
| [FujiStyle](https://apps.apple.com/us/app/id6504739559) | 罡 丁 | 363 (4.78) | 2024-08-24 | 2026-09-18 | Monthly $3.99; Quarterly $9.99; Yearly $14.99 | <5k / $10k |
| [BeautyCam-Digicam](https://itunes.apple.com/lookup?id=592331499&country=us) (beauty + digicam) | Meitu | 22,264 (4.76) | 2013-01-27 | 2026-09-26 | — | 1m / $3m |
| [B612](https://itunes.apple.com/lookup?id=904209370&country=us) / [SNOW](https://itunes.apple.com/lookup?id=1022267439&country=us) / [Hypic](https://itunes.apple.com/lookup?id=1644042837&country=us) | SNOW / SNOW / ByteDance | 109,651 / 36,782 / 17,172 | 2014 / 2015 / 2023 | Sep 2026 | — | not fetched |

**New 2026 iOS entrants, several apparently Vietnamese (names and countries inferred, not verified)**

Source for the rows below: [iTunes Lookup](https://itunes.apple.com/lookup?id=6755296366,6783651335,6768155176,6809139786,6774289960&country=us); IAP lists from each app's App Store page. Sensor Tower lists Fimii's local title as "Fimii: Chỉnh Ảnh Film", which suggests a VN focus — [ST](https://app.sensortower.com/overview/6755296366?country=US)
- Fimii: Film Presets & Editor (seller Khoa Le Nguyen). Released 2026-02-12; 24 US ratings; IAP "Fimii Premium – Lifetime $9.99". Sensor Tower: 10k DL / <$5k (ESTIMATE). Also on Play by "anKii", 5,000+ installs.
- Rollie: Retro Digital Camera (SilverAI Joint Stock Company). Released 2026-06-28; IAP Monthly $0.99, Quarterly $1.99, Annual $5.99.
- Eluvo: Analog Film Camera (AIVORY COMPANY LIMITED). Released 2026-06-06; Weekly $1.99, Monthly $6.99, Annual $19.99/$49.99, Lifetime $49.99–$59.99.
- DiscCam: CD & Vinyl Camera (Nguyen Nhut Truong). Released 2026-09-22.
- Pixie+ — Y2K Digicam (appful Inc., JP). Released 2026-05-29.

**Not found or delisted**
- Gudak Cam (Screw Bar, KR, 2016–2017; "wait 3 days to develop"):
  - The Play package com.screwbar.gudakcamera returns 404, i.e. "App not found" — [Play](https://play.google.com/store/apps/details?id=com.screwbar.gudakcamera&hl=en&gl=US)
  - A search snippet says it was unpublished from Play on 11 Oct 2024, with the last update on 26 Jul 2020 — [AppBrain via search](https://www.appbrain.com/app/gudak-cam/com.screwbar.gudakcamera)
  - The US App Store page for id 1237692856 returns 404 — [App Store](https://apps.apple.com/us/app/id1237692856)
  - Original concept coverage — [Designboom 2017](https://www.designboom.com/technology/screw-bar-retro-gudak-cam-app-12-11-2017/)
- Dazz Cam on Android:
  - Searching Google Play (US) for "DAZZ PTE. LTD." / "Dazz" found no listing by DAZZ PTE. LTD. All "Dazz" results are other developers (Dazzil Cam, MA CLO APPS "Dazz Cam", Dazzy, Dazzix, Monova "Dazz Cam") — [Play search](https://play.google.com/store/search?q=dazz+cam&c=apps&hl=en&gl=US)
  - Conflict: TechTudo (22 Jun 2026) says Dazz Cam is officially on iOS and Android — [TechTudo](https://www.techtudo.com.br/guia/2026/06/dazz-cam-o-que-faz-e-como-usar-efeitos-nas-fotos-veja-se-apk-vale-a-pena-edapps.ghtml)
  - dazzcam.app (the site linked from Dazzil Cam's Play listing) says "On Android it recommends OMO Roll" — [dazzcam.app](https://dazzcam.app/)
- Kuji Cam (GinnyPix) appears to be Android-only. GinnyPix's iOS app is "KUNI Cam" (bundle com.ginnypix.kuni, seller NK Aviation Ab, 1,860 US ratings). The iOS "Kuji Cam" (seller 鑫 李) is an unrelated app — [iTunes Search "kuji cam"](https://itunes.apple.com/search?term=kuji+cam&entity=software&country=us)
- Lapse (Lapse Ltd): no Android listing by Lapse Ltd was found in a Play search for "Lapse disposable camera" — [Play search](https://play.google.com/store/search?q=lapse+disposable+camera&c=apps&hl=en&gl=US)

**Other publisher facts**
- DAZZ PTE. LTD. was incorporated in Singapore on 22 Feb 2023 (reg. 202306518K) — [SGPBusiness](https://www.sgpbusiness.com/company/Dazz-Pte-Ltd)
- 1998 Cam was delisted from Play and re-listed with a subscription model. Reviews complain that past lifetime purchases were lost: "I already paid for the lifetime membership before it was delisted and now it's telling me I have to buy it again" — [Play 1998 Cam](https://play.google.com/store/apps/details?id=com.aaai.cam1998&hl=en&gl=US)

**Competitor review themes: newest 200 Play US reviews per app, 1–2★ reviews keyword-tagged (my own tally)**

| App | Reviews sampled (period) | Average | 1–2★ | Main themes in 1–2★ reviews |
|---|---|---|---|---|
| [FIMO](https://play.google.com/store/apps/details?id=com.fimo.camera&hl=en&gl=US) | 200 (Oct 2023–Sep 2026) | 2.49 | 121 | Payment not recognised / "scam": 61 on paywall or subscription, 24 on crashes |
| [Dazzil Cam](https://play.google.com/store/apps/details?id=com.camerafilm.lofiretro&hl=en&gl=US) | 200 | 3.60 | 67 | Ads: 31; bugs: 10 |
| [NOMO](https://play.google.com/store/apps/details?id=com.blink.academy.nomopro&hl=en&gl=US) | 200 | 3.26 | 74 | Crashes: 17; paywall: 12; "doesn't offer a trial for the cameras before you buy" |
| [Huji](https://play.google.com/store/apps/details?id=kr.co.manhole.hujicam&hl=en&gl=US) | 200 | 3.60 | 59 | Crashes: 17; saving/import: 16 |
| [OldRoll](https://play.google.com/store/apps/details?id=com.accordion.analogcam&hl=en&gl=US) | 200 (Jul–Sep 2026) | 4.08 | 37 | Mostly paywall: 15, e.g. "only having two free" cameras |
| [ProCCD](https://play.google.com/store/apps/details?id=com.cerdillac.proccd&hl=en&gl=US) | 200 (Aug–Sep 2026) | 4.42 | 22 | Auto-renew and refunds: 10, e.g. "auto deduct. I lost 550 PHP" |
| [Kapi Cam](https://play.google.com/store/apps/details?id=com.sensemobile.action&hl=en&gl=US) | 200 (Aug–Sep 2026) | 4.16 | 32 | Saving/import: 7; paywall: 5; blur and crashes |
| [Zankhana Digicam](https://play.google.com/store/apps/details?id=filmcamera.vintagecamera.digitalcamera.retrocamera&hl=en&gl=US) | 200 (Sep 2026) | 4.76 | 8 | Few complaints; "no way to save footage… accidentally deleted the app and now all my footage is gone" |

### Inferences
- On Google Play, installs are dominated by ad-supported, cheap-IAP apps. Most of the top film apps contain ads, and "Analog Film Photo…" alone has ~44M installs across 5 apps. Sensor Tower's Android revenue estimates for even 10M+ apps are tiny ($8k–$20k per month; ESTIMATES).
- iOS carries the subscription revenue:
  - Dazz: $900k/month (ESTIMATE).
  - Esti: $800k (ESTIMATE).
  - Leica LUX: $300k (ESTIMATE).
  - ism: $200k (ESTIMATE).
  - Implication: a Google-Play-first team should expect ads plus small IAP on Android, and should build iOS early for subscription revenue.
- "Dazz" is the most valuable brand in the niche, and it is absent on Android. Brand-adjacent clones capture that demand:
  - Dazzil: 20.3M installs.
  - The MA CLO "Dazz Cam" reached 100K+ within a month of its 30 Aug 2026 launch and already ranks #42 top-grossing Photography in Brazil (see Q3).
  - Implication: Android users are searching for a Dazz-quality app. This is an opportunity for original apps with strong ASO, not a licence to use the name.
- Recurring complaints across competitors map to differentiators:
  - Paywall with no trial of each camera → Filmode's "preview Pro live, pay only to save" is a direct answer.
  - Photos trapped in the app vault or lost on uninstall → auto-save to gallery.
  - Auto-renew and refund anger → clear lifetime option.
  - Crashes.
- The launch cadence of 2026 Vietnamese entrants (Fimii, Rollie, Eluvo, DiscCam) indicates rising local competition. Fimii reached #11 top free Photo & Video in VN on iOS with a single $9.99 lifetime IAP.

### Gaps
- Android per-SKU subscription prices (weekly/monthly/yearly) are not visible on Play web pages; only ranges are shown.
- iOS ratings for Ulike were not retrieved: iTunes Search returned 403 rate-limits and I did not have a confirmed trackId.
- Sensor Tower estimates:
  - Scope (worldwide vs US) and exact month are not stated on the public meta text.
  - Several Android apps show no revenue figure (e.g., Dazzil).
  - Android revenue for ad-supported apps excludes ad revenue.
- AppMagic and Appfigures pages are JavaScript-rendered and could not be read. No AppMagic numbers are included.
- Developer countries are shown only when a store field, package or website makes them clear. Others (GinnyPix, MWM, Zankhana, AIVORY, SilverAI) were not verified.
- The Play content rating and app size were not collected per competitor.

---

## Q3. Chart positions (Sep 27, 2026) and 2024–2026 viral moments

### Takeaway
- **iOS charts:** Dazz Cam is the one film-camera app charting almost everywhere on iOS.
  - Top free Photo & Video: #5 BR, #9 ID, #13 TH, #14 VN, #18 KR, #24 US, #35 JP, #39 DE.
  - Top grossing: #15 BR, #15 ID, #29 KR, #30 VN, #32 TH, #52 JP, #100 DE. It is not in the US top-100 grossing.
- **SNOW's new 101cam** (launched 10 Jul 2026) is #1 free in Korea, #3 in Brazil and #14 in Japan within 11 weeks.
- **Google Play:** Kapi Cam, ProCCD, OldRoll and Zankhana's Digicam chart in BR/ID/JP/KR Photography. In the US Play top-100 free Photography, no pure film app was found.
- **Viral drivers:** Dazz's TikTok "moving photo" trick (2026), the digicam/CCD/Y2K trend, and Kapi Cam creator content (2025).

### Cited Findings

**App Store — Photo & Video (genre 6008) top 100, feed updated 2026-09-27**

Film/retro apps only. Sources:
- `https://itunes.apple.com/{cc}/rss/topfreeapplications/limit=100/genre=6008/json`
- `https://itunes.apple.com/{cc}/rss/topgrossingapplications/limit=100/genre=6008/json`

- US — [free](https://itunes.apple.com/us/rss/topfreeapplications/limit=100/genre=6008/json), [grossing](https://itunes.apple.com/us/rss/topgrossingapplications/limit=100/genre=6008/json)
  - Free: Dazz Cam #24, ism #50, 101cam #54, Huji Cam #71 (VSCO #78).
  - Grossing: ism #83, BeautyCam-Digicam #100. Dazz is not in the top 100.
- Vietnam — [free](https://itunes.apple.com/vn/rss/topfreeapplications/limit=100/genre=6008/json), [grossing](https://itunes.apple.com/vn/rss/topgrossingapplications/limit=100/genre=6008/json)
  - Free:
    - Film/retro apps: Fimii #11, Dazz #14, NOMO CAM #15, Foodie #49, OldRoll #52, Fomz #56, ProCCD #62, Rollie #73, Eluvo #78, DiscCam #86.
    - Camera-filter apps: BeautyCam #16, Ulike #20, B612 #25.
  - Grossing:
    - Film/retro apps: Foodie #28, Dazz #30, Fimii #49, OldRoll #80, Leica LUX #82, FujiStyle #85, Rollie #93, Eluvo #100.
    - Camera-filter apps: Hypic #5, BeautyCam #11, B612 #13, Ulike #16, SODA #20, SNOW #21.
- Japan — [free](https://itunes.apple.com/jp/rss/topfreeapplications/limit=100/genre=6008/json), [grossing](https://itunes.apple.com/jp/rss/topgrossingapplications/limit=100/genre=6008/json)
  - Free: 101cam #14, Pixie+ (Y2K digicam) #18, Dazz #35, OldRoll #73.
  - Grossing: Foodie #40, Dazz #52, Leica LUX #68, OldRoll #82.
- Korea — [free](https://itunes.apple.com/kr/rss/topfreeapplications/limit=100/genre=6008/json), [grossing](https://itunes.apple.com/kr/rss/topgrossingapplications/limit=100/genre=6008/json)
  - Free: **101cam #1**, Shardee mini vlog camera #3, Dazz #18, ProCCD #76, Foodie #85.
  - Grossing: Foodie #26, Dazz #29, 101cam #53, BerryFilm #59, iY2K #60, filmhwa #62, Oldi #84, @picn2k #87, ProCCD #88.
  - Several paid-upfront KR apps ($0.99–$2.99) chart in grossing.
- Indonesia — [free](https://itunes.apple.com/id/rss/topfreeapplications/limit=100/genre=6008/json), [grossing](https://itunes.apple.com/id/rss/topgrossingapplications/limit=100/genre=6008/json)
  - Free: Dazz #9, Kapi Cam #21, Esti #53, OldRoll #58, Fomz #59, ProCCD #68.
  - Grossing: Dazz #15, Esti #55, Leica LUX #75, OldRoll #92.
- Thailand — [free](https://itunes.apple.com/th/rss/topfreeapplications/limit=100/genre=6008/json), [grossing](https://itunes.apple.com/th/rss/topgrossingapplications/limit=100/genre=6008/json)
  - Free: Dazz #13, Fomz #34, Fleem Cam #53, Esti #57, ProCCD #65, FujiStyle #70, LoFi Cam #81, Kapi #96.
  - Grossing: Dazz #32, Foodie #42, Esti #50, Fomz #80.
- Brazil — [free](https://itunes.apple.com/br/rss/topfreeapplications/limit=100/genre=6008/json), [grossing](https://itunes.apple.com/br/rss/topgrossingapplications/limit=100/genre=6008/json)
  - Free: 101cam #3, Dazz #5, OldRoll #85, flag7x #98.
  - Grossing: Dazz #15.
- Germany — [free](https://itunes.apple.com/de/rss/topfreeapplications/limit=100/genre=6008/json), [grossing](https://itunes.apple.com/de/rss/topgrossingapplications/limit=100/genre=6008/json)
  - Free: Leica LUX #36, Dazz #39, Retro #49, Esti #85.
  - Grossing: Leica LUX #31, Esti #41, Dazz #100.

**Google Play — Photography top 100 (AppBrain, "updated September 27, 2026")**

Sources: `https://www.appbrain.com/stats/google-play-rankings/top_free/photography/{cc}` and `.../top_grossing/photography/{cc}`

- Brazil — [free](https://www.appbrain.com/stats/google-play-rankings/top_free/photography/br), [grossing](https://www.appbrain.com/stats/google-play-rankings/top_grossing/photography/br)
  - Free: Kapi Cam #26, VSCO #30, ProCCD #38, OldRoll #46, Zankhana Digicam #48.
  - Grossing: MA CLO "Dazz Cam" #42, OldRoll #54, Zankhana #68, Kapi #76.
- Indonesia — [free](https://www.appbrain.com/stats/google-play-rankings/top_free/photography/id), [grossing](https://www.appbrain.com/stats/google-play-rankings/top_grossing/photography/id)
  - Free: Kapi #13, Zankhana #26, ProCCD #34, OldRoll #64.
  - Grossing: OldRoll #41, Zankhana #46, Kapi #69.
- Japan — [free](https://www.appbrain.com/stats/google-play-rankings/top_free/photography/jp), [grossing](https://www.appbrain.com/stats/google-play-rankings/top_grossing/photography/jp)
  - Free: ProCCD #55, Retro #66, MA CLO "Dazz Cam" #68, Zankhana #75, OldRoll #92.
  - Grossing: Foodie #43.
- Korea — [free](https://www.appbrain.com/stats/google-play-rankings/top_free/photography/kr), [grossing](https://www.appbrain.com/stats/google-play-rankings/top_grossing/photography/kr)
  - Free: Zankhana #31, ProCCD #80, OldRoll #87.
  - Grossing: Foodie #20, BerryFilm (com.seesun.berryberryfilm) #53.
- Germany — [free](https://www.appbrain.com/stats/google-play-rankings/top_free/photography/de)
  - Free: Retro #40, MA CLO "Dazz Cam" #87.
- US — [free](https://www.appbrain.com/stats/google-play-rankings/top_free/photography/us)
  - The top free list is dominated by AI photo apps. The only relevant entry is Hypic #17; no pure film-camera app appears in the top 100.
- VN/TH: AppBrain's /vn and /th pages returned the **United States** list (the page heading says "…in the United States"). **Google Play chart data for Vietnam and Thailand is therefore not available** from this source — [AppBrain VN URL](https://www.appbrain.com/stats/google-play-rankings/top_free/photography/vn)

**Viral moments and trend evidence**
- Dazz Cam, 2026:
  - TechTudo (22 Jun 2026) says Dazz Cam returned to social networks in 2026 through a TikTok "moving photo" trick: flash, a high-grain filter and camera movement at capture. Tutorial videos "accumulated hundreds of thousands of likes", with appeal "particularly among ages 16–25" — [TechTudo](https://www.techtudo.com.br/guia/2026/06/dazz-cam-o-que-faz-e-como-usar-efeitos-nas-fotos-veja-se-apk-vale-a-pena-edapps.ghtml)
  - TechTudo's price notes: annual ~€5, lifetime ~€15; the free version "cannot save photos".
- Dazz Cam, earlier "moving photo / 3D gif" content: a TikTok tutorial from 2023 exists — [TikTok @hieubkfm](https://www.tiktok.com/@hieubkfm/video/7267382148980722945)
- Sensor Tower Dazz estimates (ESTIMATES):
  - A search-engine snippet of the Sensor Tower Dazz page (dated March 2026) showed "3 million downloads and $900,000 in revenue" for the last measured month — [Sensor Tower (search snippet)](https://app.sensortower.com/overview/1422471180?country=US)
  - The live page on 2026-09-27 shows "2m downloads and $900k revenue" — [Sensor Tower](https://app.sensortower.com/overview/1422471180?country=US)
- Kapi Cam, 2025: the brand's own TikTok and creator posts (Aug–Nov 2025, e.g. "our new fav digicam app", #kapicam #digicam) — [TikTok @kapi.cam](https://www.tiktok.com/@kapi.cam/video/7556141447041305874); [TikTok @xyl0vrr](https://www.tiktok.com/@xyl0vrr/video/7543583130318343432)
- Kapi Cam Play growth: 5M on 2026-01-03, then 10M on 2026-04-05 — [AndroidRank](https://www.androidrank.org/application/x/com.sensemobile.action)
- ProCCD: TikTok creators promote its "kira effect" for digicam looks (2024) — [TikTok @mikeeest](https://www.tiktok.com/@mikeeest/video/7332064086106066182)
- Digicam trend:
  - Back Market says it "initially sprouted on TikTok before migrating over to Instagram", naming Huji Cam, OldRoll, BeautyCam, Dazz Cam (for a Canon G7X look), LoFi Cam and Epik as apps used to mimic it — [Back Market](https://www.backmarket.com/en-us/c/photo-and-video/digicam-trend-nostalgia-social-media)
  - The flag7x app is literally a "g7x style camera" — [App Store](https://apps.apple.com/us/app/id6747452095)
- Low-quality aggregator claim: "#digitalcamera and #digicam have driven over 1.2 billion views on TikTok since early 2025". Unverified; do not rely on it — [Alibaba guide](https://electronics.alibaba.com/buyingguides/digicam-fx-guide-ccd-cameras-apps-for-gen-z-aesthetics)
- History:
  - Huji Cam was a "viral sensation" in summer 2018, with over 300,000 #huji Instagram posts at the time (TIME, 14 Aug 2018) — [TIME](https://time.com/5361833/what-is-huji-camera-photo-app/)
  - Huji and Kuji both passed 10M Play installs in Sep 2018 — [AndroidRank Huji](https://www.androidrank.org/application/x/kr.co.manhole.hujicam); [AndroidRank Kuji](https://www.androidrank.org/application/x/com.ginnypix.kujicam)

### Inferences
- Where the film look is a mainstream purchase: Vietnam, Indonesia, Thailand, Korea and Brazil are the strongest iOS markets for film/retro camera apps by both free and grossing rank. Dazz ranks top-15 free in VN/ID/TH/BR, and VN grossing includes six film/retro apps in the top 100.
- The US and Germany are weaker for pure film cameras and stronger for "pro camera + looks" (Leica LUX) and editors (Esti, VSCO).
- A large incumbent (SNOW with 101cam) entering in July 2026 and going #1 in KR signals the niche is still expanding in 2026. It also signals rising competition from well-funded Asian publishers.
- Virality comes from a specific, easily demonstrated capture trick (moving photo, kira/flash, G7X look). It does not come from filter count. A capture-first app should design one shareable "signature effect" per camera.

### Gaps
- Google Play top charts for VN and TH could not be retrieved (AppBrain fallback). Google Play's own web charts do not expose per-category, per-country lists.
- No verified TikTok hashtag view counts or download-spike data tied to specific viral dates. Sensor Tower and AppMagic history charts require login.
- iOS chart data is a single-day snapshot (2026-09-27), not a trend.

---

## Q4. Market size signals and 2023–2026 trend

### Takeaway
Film/retro capture is a large-install, moderate-revenue niche.

Installs (Play):
- ~343M exact Play installs across the 38 capture apps checked.
- ~124M of those are in apps launched in 2020 or later.
- ~3.0M Android downloads per month across the 13 capture apps with Sensor Tower Android figures (ESTIMATES).

iOS (Sensor Tower ESTIMATES):
- About 3.4M downloads per month across the core film-camera apps.
- About $1.4–1.5M per month in revenue across the same apps. Dazz alone is ~$0.9M of that.
- Adjacent "aesthetic editor / pro camera" apps add ~$1.1M+ per month (Esti $800k, Leica LUX $300k).

The trend is strongly positive for the 2022–2026 generation. The 2017–2018 first wave (Huji, Kuji, Foodie) has plateaued.

### Cited Findings

**Aggregate Play installs** (my sum of exact Play install counts from the 38 Table A capture apps; source: each app's Play page linked in Table A)
- All 38 apps: ~343.1M.
- Top 12 apps: ~299.1M. These are Huji, Foodie, OldRoll, Kuji, Fomz, ProCCD, Dazzil, Vintage Camera-Retro, Kapi, Koda, NOMO and Disposable Camera-Lapse Cam.
- Apps launched 2020 or later: ~123.7M. These are Kapi, ProCCD, Zankhana, OldRoll, Fomz, LoFi, OldReel, POV, Retro, y2k, the MA CLO "Dazz Cam" and the 1998 Cam re-listing.

**Monthly Sensor Tower ESTIMATES (public overview pages fetched 2026-09-27)**
- iOS core capture apps (Dazz, Huji, 1998 Cam, NOMO, Kapi, OldRoll, ProCCD, Foodie, DAZE, Fomz, radcam, ism, 101cam, flag7x):
  - ≈3.4M downloads per month.
  - ≈$1.44M per month in revenue: Dazz $900k, ism $200k, Foodie $100k, OldRoll $90k, ProCCD $60k, NOMO $30k, others ≤$10k each.
  - Sources: [ST Dazz](https://app.sensortower.com/overview/1422471180?country=US); [ST ism](https://app.sensortower.com/overview/1580668065?country=US); [ST Foodie](https://app.sensortower.com/overview/1076859004?country=US); [ST OldRoll](https://app.sensortower.com/overview/1570093460?country=US); [ST ProCCD](https://app.sensortower.com/overview/1616113199?country=US); [ST NOMO](https://app.sensortower.com/overview/1362548649?country=US); [ST Kapi iOS](https://app.sensortower.com/overview/6740760807?country=US); [ST 1998 Cam](https://app.sensortower.com/overview/1450480287?country=US); [ST Fomz](https://app.sensortower.com/overview/1615744942?country=US); [ST 101cam](https://app.sensortower.com/overview/6781998623?country=US)
- Android capture apps:
  - Downloads: Kapi 1,000k, ProCCD 600k, Zankhana 600k, OldRoll 400k, Dazzil 100k, POV 100k, y2k 80k, and 1998/LoFi/Foodie ~30k each.
  - Stated IAP revenue is tiny (≤$20k each, except POV at $80k).
  - Sources: [ST Kapi Android](https://app.sensortower.com/overview/com.sensemobile.action?country=US); [ST ProCCD Android](https://app.sensortower.com/overview/com.cerdillac.proccd?country=US); [ST Zankhana](https://app.sensortower.com/overview/filmcamera.vintagecamera.digitalcamera.retrocamera?country=US); [ST OldRoll Android](https://app.sensortower.com/overview/com.accordion.analogcam?country=US); [ST POV](https://app.sensortower.com/overview/com.untitledshows.pov?country=US)
- Adjacent monetisers:
  - Esti: 300k DL / $800k — [ST](https://app.sensortower.com/overview/6457366208?country=US)
  - Leica LUX: 60k / $300k — [ST](https://app.sensortower.com/overview/6477182657?country=US)
  - BeautyCam: 1m / $3m — [ST](https://app.sensortower.com/overview/592331499?country=US)
  - Retro (social): 600k / $30k — [ST](https://app.sensortower.com/overview/6443709020?country=US)
- Declined apps:
  - Lapse: <5k downloads last month despite 118,276 US ratings — [ST](https://app.sensortower.com/overview/1636699256?country=US); [iTunes Lookup](https://itunes.apple.com/lookup?id=1636699256&country=us)
  - Hipstamatic: <5k / <$5k — [ST](https://app.sensortower.com/overview/1450672436?country=US)
  - FIMO: <5k / <$5k — [ST](https://app.sensortower.com/overview/1454219307?country=US)

**Install-milestone trend (AndroidRank; milestone dates = date AndroidRank first recorded the threshold)**
- Kapi Cam: 5M on 2026-01-03, 10M on 2026-04-05 (Play launch Jan 2024) — [AndroidRank](https://www.androidrank.org/application/x/com.sensemobile.action)
- ProCCD: 1M on 2023-04-16, 5M on 2024-09-01, 10M on 2025-05-07 — [AndroidRank](https://www.androidrank.org/application/proccd_digital_film_camera/com.cerdillac.proccd)
- Fomz: 1M on 2023-06-03, 5M on 2024-09-01, 10M on 2025-03-01 — [AndroidRank](https://www.androidrank.org/application/x/com.imendon.fomz)
- Zankhana Vintage Film Camera - Digicam: 100K on 2025-10-01, 500K on 2025-12-04, 1M on 2026-02-01. It shows 4.63M exact now — [AndroidRank](https://www.androidrank.org/application/x/filmcamera.vintagecamera.digitalcamera.retrocamera); [Play](https://play.google.com/store/apps/details?id=filmcamera.vintagecamera.digitalcamera.retrocamera&hl=en&gl=US)
- OldRoll: 5M on 2022-09-03, 10M on 2023-04-01. It shows 40.05M exact now — [AndroidRank](https://www.androidrank.org/application/x/com.accordion.analogcam); [Play](https://play.google.com/store/apps/details?id=com.accordion.analogcam&hl=en&gl=US)
- OldReel: 1M on 2025-10-02 — [AndroidRank](https://www.androidrank.org/application/x/com.changpeng.oldreel.dv)
- POV: 1M on 2026-03-15 — [AndroidRank](https://www.androidrank.org/application/x/com.untitledshows.pov)
- Retro: 1M on 2026-06-10 — [AndroidRank](https://www.androidrank.org/application/x/io.lonepalm.retro)
- 1998 Cam (re-listed): 10K on 2026-06-10, 100K on 2026-09-01 — [AndroidRank](https://www.androidrank.org/application/x/com.aaai.cam1998)
- First wave:
  - Huji: 10M in Sep 2018 — [AndroidRank](https://www.androidrank.org/application/x/kr.co.manhole.hujicam)
  - Kuji: 10M in Sep 2018 — [AndroidRank](https://www.androidrank.org/application/x/com.ginnypix.kujicam)
  - Foodie: 10M in Dec 2017 — [AndroidRank](https://www.androidrank.org/application/x/com.linecorp.foodcam.android)
  - Their current Sensor Tower Android downloads are ≤30k per month (ESTIMATE).
- iOS new entrants in 2025–2026: Kapi Cam iOS (Mar 2025), flag7x (Jun 2025), Pixie+ (May 2026), Eluvo (Jun 2026), Rollie (Jun 2026), 101cam (Jul 2026) and DiscCam (Sep 2026) — [iTunes Lookup](https://itunes.apple.com/lookup?id=6740760807,6747452095,6774289960,6768155176,6783651335,6781998623,6809139786&country=us)
- Not usable: a physical "Film Camera Market" report ($277.91M in 2023 → $387.27M by 2030) covers hardware, not apps — [Cognitive Market Research](https://www.cognitivemarketresearch.com/film-camera-market-report)

### Inferences
- Growth has shifted from "vintage filter camera" (2017–2019) to "CCD/Y2K digicam + DV/camcorder + social disposable" (2022–2026). Every fast climber since 2023 is CCD, digicam or camcorder themed: Kapi, ProCCD, Fomz, Zankhana, OldReel, 101cam.
- The niche's revenue is highly concentrated: Dazz takes about 60% of the estimated iOS film-camera revenue. Most other apps make ≤$100k per month.
- An indie team can realistically reach millions of Play installs through ads plus cheap IAP. Zankhana went from 0 to 4.6M in 14 months. Meaningful subscription revenue, however, requires an iOS presence and a premium brand.
- Sensor Tower Android revenue figures probably understate total income for ad-supported apps, because ads revenue is not included.

### Gaps
- No public 2023–2026 time series of niche-wide downloads or revenue (AppMagic, Sensor Tower and Appfigures history is paywalled or JS-only). The trend above comes from install milestones and single-month snapshots.
- Sensor Tower's "last month" scope (worldwide vs US) is unconfirmed. The March 2026 Dazz figure comes only from a search-engine snippet.
- No ad-revenue estimates for ad-supported Android apps.
