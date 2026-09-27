# Preset / Filter / LUT (color-grading) editor apps — market scan (data as of 2026-09-27)

Method note (applies to every table below): Google Play numbers were pulled on 2026-09-27 from the US listing (`hl=en&gl=US`) with the open-source `google-play-scraper` library. It reads the public Play page. "Installs band" is the public band. The number in brackets is the exact install counter that Play embeds in the page (`maxInstalls`). Play does not display that counter, so treat it as store-reported but unofficial. Ratings are Play's global rating count. For iOS, rating counts come from the iTunes Lookup API (`country=us`, and `country=vn` where noted). iOS price points are the "In-App Purchases" list scraped from the apps.apple.com US product page on 2026-09-27. Apple shows at most 10 items, which can repeat or reflect A/B price tests. Chart positions are a one-day snapshot from 2026-09-27. Google Play charts cover the top 50 per list, pulled via the same library's `list()` call against the Play web top-charts endpoint. iOS charts are the Photo & Video genre (6008) top 100 from Apple's legacy RSS feed (e.g. `https://itunes.apple.com/vn/rss/topgrossingapplications/limit=200/genre=6008/json`; the feed returns 100 entries). Developer countries in brackets come from the legal-entity name or common knowledge and are marked "(inferred)" unless a source states them.

## Q1. Photo preset / filter editors: who they are, scale, pricing, free vs paid

### Takeaway
Scale in the "apply a look to an existing photo" segment splits into three tiers:
- **All-in-one giants.** Picsart has 1.4B Play installs. Lightroom has 471M, Snapseed 446M, VSCO 165M, Meitu 142M, Hypic 123M and Lumii 109M.
- **Dedicated preset/filter apps.** FLTR, Koloro, Afterlight, Lightleap, Polarr, Tezza and Prequel each sit at 5–63M Play installs.
- **Film-emulation apps.** RNI Films, Dehancer, Darkroom, Mattebox and Fimii are small, mostly iOS, and serve prosumers.

Monetization is almost universally freemium. Weekly, monthly and yearly subscriptions are standard: roughly $4–15/month and $15–70/year in the US. Smaller indie and film apps often add a lifetime or one-time unlock ($9.99–$99.99). Dedicated "Lightroom preset" apps with 10M+ installs rely heavily on ads and do not reach any Google Play top-50 grossing list.

### Cited Findings

**Statistics table A — photo preset / filter editors (Google Play US listing + App Store US, pulled 2026-09-27)**

| App (developer, country) | Play package → installs band (exact counter) | Play rating (count) | Play first release / last update | Play IAP range; ads | iOS id → US rating (count); VN count | iOS first release | Sources |
|---|---|---|---|---|---|---|---|
| VSCO (VSCO / Visual Supply Co., US) | com.vsco.cam → 100M+ (164,548,166) | 3.62 (1,325,500) | 2013-12-03 / 2026-09-21 | $0.99–$29.99; no ads | 588013838 → 4.69 (277,508); VN 31,321 | 2013-06-06 | [GP](https://play.google.com/store/apps/details?id=com.vsco.cam&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id588013838), [lookup](https://itunes.apple.com/lookup?id=588013838&country=us) |
| Lightroom (Adobe, US) | com.adobe.lrmobile → 100M+ (470,934,374) | 4.47 (3,663,509) | 2015-01-14 / 2026-09-17 | $0.49–$499.99; no ads | 878783582 → 4.77 (336,826); VN 221,978 | 2014-06-22 | [GP](https://play.google.com/store/apps/details?id=com.adobe.lrmobile&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id878783582) |
| Snapseed (Google, US) | com.niksoftware.snapseed → 100M+ (446,381,067) | 4.80 (1,830,643) | 2012-12-06 / 2026-09-23 | no IAP; no ads | 439438619 → 4.86 (26,585); VN 3,710 | 2011-06-07 | [GP](https://play.google.com/store/apps/details?id=com.niksoftware.snapseed&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id439438619) |
| Polarr (Polarrcan Software Inc., US/Canada, inferred) | photo.editor.polarr → 10M+ (37,142,675) | 3.85 (146,623) | 2015-08-02 / 2026-02-03 | $0.99–$34.99; ads | 988173374 → 4.66 (66,954); VN 92,774 | 2015-06-25 | [GP](https://play.google.com/store/apps/details?id=photo.editor.polarr&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id988173374) |
| Picsart (PicsArt, Inc., US/Armenia, inferred) | com.picsart.studio → 1B+ (1,435,771,274) | 3.96 (12,135,361) | 2011-11-04 / 2026-09-23 | $0.99–$429.99; ads | 587366035 → 4.67 (1,195,457); VN 465,247 | 2013-01-02 | [GP](https://play.google.com/store/apps/details?id=com.picsart.studio&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id587366035) |
| Tezza (Tezza App LLC, US) | org.tezza → 5M+ (9,960,781) | 3.66 (12,911) | 2019-12-04 / 2026-08-24 | $1.99–$39.99; no ads | 1393061654 → 4.74 (47,293); VN 346 | 2018-07-07 | [GP](https://play.google.com/store/apps/details?id=org.tezza&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id1393061654) |
| Afterlight (Afterlight Collective, Inc.) | com.fueled.afterlight → 10M+ (11,393,540) | 2.71 (60,771) | 2014-08-14 / 2026-09-01 | $0.99–$39.99; no ads | 1293122457 → 4.74 (20,664); VN 1,254 | 2017-11-02 | [GP](https://play.google.com/store/apps/details?id=com.fueled.afterlight&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id1293122457) |
| Darkroom (Bergen Co., US) — iOS only; Play search found no listing | — | — | — | — | 953286746 → 4.78 (29,354); VN 1,313 | 2015-02-12 | [iOS](https://apps.apple.com/us/app/id953286746) |
| RNI Films (Really Nice Images LTD) — iOS; no Google Play listing found for "RNI Films" or "Really Nice Images" | — | — | — | — | 1017098672 → 4.79 (9,062); VN 9,350 | 2015-08-09 | [iOS](https://apps.apple.com/us/app/id1017098672) |
| Dehancer Film Emulation (Dehancer L.L.C-FZ, UAE, inferred) — iOS only | — | — | — | — | 6443648413 → 4.28 (430); VN 11 | 2022-10-10 | [iOS](https://apps.apple.com/us/app/id6443648413) |
| Mattebox (Syverson Industries LLC, US) — iOS only | — | — | — | — | 452438265 → 4.62 (32); last update 2024-11-16 | 2011-12-08 | [iOS](https://apps.apple.com/us/app/id452438265) |
| Lightleap (Lightricks, Israel) | com.lightricks.quickshot → 10M+ (19,535,751) | 4.00 (66,676) | 2020-07-05 / 2025-11-05 | $0.19–$79.99; no ads | 1254875992 → 4.72 (98,671); VN 101,357 | 2017-08-31 | [GP](https://play.google.com/store/apps/details?id=com.lightricks.quickshot&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id1254875992) |
| Hypic (Bytedance Pte. Ltd., Singapore/China) | com.xt.retouchoversea → 100M+ (122,665,658) | 3.09 (262,307) | 2023-01-03 / 2026-09-23 | $2.99–$159.99; no ads | 1644042837 → 4.58 (17,172); VN 76,110 | 2023-01-03 | [GP](https://play.google.com/store/apps/details?id=com.xt.retouchoversea&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id1644042837) |
| Meitu (Meitu, China) | com.mt.mtxx.mtxx → 100M+ (141,756,147) | 4.49 (1,487,197) | 2011-03-09 / 2026-09-24 | $0.49–$229.99; ads | 416048305 → 4.78 (79,805); VN 92,946 | 2011-02-15 | [GP](https://play.google.com/store/apps/details?id=com.mt.mtxx.mtxx&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id416048305) |
| Ulike (Bytedance Pte. Ltd.) — not listed in the US Play or App Store; pulled with gl=VN | com.gorgeous.liteinternational → 50M+ (78,504,765) | 4.71 in VN (716,363) | 2018-06-21 / 2025-02-11 | ₫29,000–₫829,000 (VN); no ads | 1398796436 → not in US store; VN count 725,262 | — | [GP VN](https://play.google.com/store/apps/details?id=com.gorgeous.liteinternational&hl=en&gl=VN), [lookup VN](https://itunes.apple.com/lookup?id=1398796436&country=vn) |
| Foodie (SNOW Corp., Korea) | com.linecorp.foodcam.android → 10M+ (42,274,345) | 3.58 (131,706) | 2016-02-01 / 2026-09-08 | $6.99–$34.99; no ads | 1076859004 → 4.74 (9,319); VN 100,718 | 2016-02-02 | [GP](https://play.google.com/store/apps/details?id=com.linecorp.foodcam.android&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id1076859004) |
| Fotor (Everimaging, China) | com.everimaging.photoeffectstudio → 10M+ (44,052,695) | 4.28 (731,518) | 2013-03-29 / 2026-09-22 | $0.99–$749.99; ads | 440159265 → 4.66 (42,347); VN 3,203 | 2011-07-24 | [GP](https://play.google.com/store/apps/details?id=com.everimaging.photoeffectstudio&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id440159265) |
| Presets for Lightroom — FLTR (Play dev "Mobile Presets & Filters"; iOS seller Onelight Apps CY Ltd, Cyprus, inferred) | com.feelty → 10M+ (29,968,205) | 4.57 (419,411) | 2019-06-25 / 2026-06-29 | $0.99–$69.99; ads | 1448103572 → 4.84 (81,073); VN 7,541 | 2019-06-15 | [GP](https://play.google.com/store/apps/details?id=com.feelty&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id1448103572) |
| Presets & Filters – Koloro (Play dev "cerdillac"; iOS seller "亚玲 查", China, inferred; same Play dev as ProCCD) | com.cerdillac.persetforlightroom → 10M+ (40,245,687) | 4.80 (431,060) | 2019-01-09 / **2024-06-27 (stale)** | $0.99–$99.99; ads | 1345159029 → 4.66 (2,335); VN 1,527 | 2018-02-07 | [GP](https://play.google.com/store/apps/details?id=com.cerdillac.persetforlightroom&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id1345159029) |
| Presets For LR – Photo Filters (Inspiring Apps LLC, US) | com.inspiringapps.lrpresets → 5M+ (5,053,710) | 4.09 (43,080) | 2020-06-27 / 2024-10-14 | $7.99–$24.99; no ads | — | — | [GP](https://play.google.com/store/apps/details?id=com.inspiringapps.lrpresets&hl=en&gl=US) |
| LR Presets – Photo Editor (Prometheus Interactive / ASAP Visuals; iOS "Edith") | com.asapvisuals.presetbox → 5M+ (7,783,046) | 4.32 (19,515) | 2021-02-08 / 2026-04-15 | $0.99–$99.99; ads | 1477761909 (Edith) → 4.81 (9,486) | 2019-09-23 | [GP](https://play.google.com/store/apps/details?id=com.asapvisuals.presetbox&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id1477761909) |
| Preset & Filters For LR (Sajjad IT) — free, ad-funded DNG preset library | com.sajjadit.freepreset → 10M+ (11,737,477) | 4.39 (87,691) | 2020-03-12 / 2026-01-12 | no IAP; ads | — | — | [GP](https://play.google.com/store/apps/details?id=com.sajjadit.freepreset&hl=en&gl=US) |
| PREQUEL (Prequel Inc.) | com.prequel.app → 50M+ (63,128,065) | 4.52 (394,349) | 2020-05-24 / 2026-09-16 | $0.49–$49.99; no ads | 1325756279 → 4.74 (343,946); VN 22,441 | 2018-03-29 | [GP](https://play.google.com/store/apps/details?id=com.prequel.app&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id1325756279) |
| Esti (Prequel Inc.) — "vintage camera filters", iOS | — | — | — | — | 6457366208 → 4.64 (18,612) | 2023-10-25 | [iOS](https://apps.apple.com/us/app/id6457366208) |
| Photoshop Express (Adobe) | com.adobe.psmobile → 100M+ (303,800,099) | 4.55 (2,594,264) | — / 2026-08-22 | $2.99–$99.99; no ads | 331975235 → 4.75 (741,103) | 2009-10-09 | [GP](https://play.google.com/store/apps/details?id=com.adobe.psmobile&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id331975235) |
| AI Photo Editor – Lumii (InShot) — no iOS twin found | photo.editor.photoeditor.filtersforpictures → 100M+ (108,527,423) | 4.75 (1,012,194) | 2018-09-30 / 2026-09-20 | $2.99–$29.99; ads | — | — | [GP](https://play.google.com/store/apps/details?id=photo.editor.photoeditor.filtersforpictures&hl=en&gl=US) |
| A Color Story (Midtone LLC, US) | com.acolorstory → 1M+ (2,618,954) | 3.79 (15,285) | 2016-05-12 / 2024-12-10 | $0.99–$24.99; no ads | 1015059175 → 4.77 (31,178) | 2016-01-19 | [GP](https://play.google.com/store/apps/details?id=com.acolorstory&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id1015059175) |
| PICFX Film Filters & Presets (Active Development, NZ, inferred) | nz.co.davidboyes.picfx_android → 500K+ (833,732) | 4.10 (919) | 2016-04-12 / 2026-07-25 | $0.99–$39.99; no ads | — | — | [GP](https://play.google.com/store/apps/details?id=nz.co.davidboyes.picfx_android&hl=en&gl=US) |
| Luminar mobile (Skylum) | com.skylum.luminar → 1M+ (3,036,493) | 4.43 (16,422) | 2025-04-30 / 2026-09-10 | $0.99–$179.99; no ads | — | — | [GP](https://play.google.com/store/apps/details?id=com.skylum.luminar&hl=en&gl=US) |
| **Fimii: Film Presets & Editor** (Play dev "anKii"; iOS seller "Khoa Le Nguyen"; solo indie developer — see Q5/Q6) | com.ankii.fimii → 5,000+ (8,736) | 4.89 in VN (229) | **2026-02-03** / 2026-09-25 | $9.99 (₫263,000 in VN); flagged as containing ads | 6755296366 → 4.83 (24); **VN 865** | 2026-02-12 | [GP](https://play.google.com/store/apps/details?id=com.ankii.fimii&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id6755296366), [site](https://fimii.app/about) |
| Ultralight (Uova Oy, Finland, inferred) — iOS | — | — | — | — | 972428565 → 4.71 (43,691) | 2015-06-08 | [iOS](https://apps.apple.com/us/app/id972428565) |
| PRESETS: Filters for Pictures (Gustas Brazaitis) — iOS | — | — | — | — | 1457445491 → 4.79 (10,085) | 2019-04-08 | [iOS](https://apps.apple.com/us/app/id1457445491) |
| Presets for Lightroom – Vidl (FELINE MARKETING) — iOS | — | — | — | — | 1490818231 → 4.67 (22,128); last update 2025-06-27 | 2020-01-05 | [iOS](https://apps.apple.com/us/app/id1490818231) |
| Presets for Lightroom – Editor (Scep Group) — iOS | — | — | — | — | 1487984717 → 4.67 (8,187); **VN 21,535** | 2019-11-24 | [iOS](https://apps.apple.com/us/app/id1487984717) |
| WayShot: Aesthetic Photo Editor (Romangic Lab LLC) — iOS, new in 2025 | — | — | — | — | 6749303003 → 4.69 (1,816) | 2025-08-10 | [iOS](https://apps.apple.com/us/app/id6749303003) |

New micro-apps on Google Play in 2026 show the long tail keeps filling. None has passed a few thousand installs yet:
- Presetly: 100+, released 2026-04-29 ([GP](https://play.google.com/store/apps/details?id=com.presetly.lightroompresets&hl=en&gl=US)).
- Lightroom Presets – Lumio: 100+, released 2026-06-10 ([GP](https://play.google.com/store/apps/details?id=com.lumio.lrpresets&hl=en&gl=US)).
- LR Preset Hub: 1,000+, released 2026-05-11 ([GP](https://play.google.com/store/apps/details?id=com.lrpresetfree.hub&hl=en&gl=US)).
- ps.clix: 500+, released 2026-07-04 ([GP](https://play.google.com/store/apps/details?id=com.profilixa.psclix&hl=en&gl=US)).

**Exact price points (App Store US in-app purchase list, 2026-09-27) and what is free vs paid**
- **VSCO**
  - App Store prices: Monthly Plus $9.99, Yearly Plus $39.99, Monthly Pro $14.99, Yearly Pro $69.99. Some free brand-collab packs show as $0.00, e.g. "The Aesthetic Series" and "Hypebeast / HB" ([App Store](https://apps.apple.com/us/app/id588013838)).
  - VSCO's own web plans page is **cheaper than the App Store**: Plus $7.99/mo or $29.99/yr; Pro $12.99/mo or $59.99/yr; VSCO One $499.99/yr ([vsco.co plans](https://www.vsco.co/subscribe/plans)).
  - Free "Starter" tier: 15 standard presets and 100 one-time AI credits; no video, batch or RAW ([vsco.co plans](https://www.vsco.co/subscribe/plans)).
  - Plus: 200+ presets, 250 AI credits a month, video editing, ad-free. Pro adds batch editing, RAW capture (iOS and desktop), unlimited AI Lab and 500 credits a month ([vsco.co plans](https://www.vsco.co/subscribe/plans)).
  - App description: "Edit 100 photos at once"; Recipes save and recreate edits; 200+ presets including "Film X" (Kodak/Fuji/Agfa-inspired) ([App Store](https://apps.apple.com/us/app/id588013838)).
  - VSCO also launched a separate capture app, "VSCO Capture: Preset Camera" (iOS, 2025-07-21, 222 US ratings, "200+ presets", RAW) ([App Store](https://apps.apple.com/us/app/id6741483219)).
- **Lightroom mobile**
  - App Store prices: Premium Weekly 100GB $3.99 / $7.99; Premium Monthly 100GB $6.99 / $7.99; Premium Yearly 100GB $49.99; Premium Monthly 40GB $1.99; Premium Yearly 40GB $19.99; Lightroom plan 1TB $9.99; "AI Photo Enhancer & Blur" $49.99 ([App Store](https://apps.apple.com/us/app/id878783582)).
  - Free vs premium: a secondary source says capture, organizing, sharing and most editing (exposure, color, presets) are free. Premium adds premium presets, healing, selective/masking, geometry, raw editing, Generative Remove, Lens Blur and AI presets. Adobe's own help page (helpx.adobe.com/lightroom-cc/using/premium-features.html) returned 403, so this is unverified against Adobe ([search summary incl. PictureCorrect/Photutorial](https://www.picturecorrect.com/exploring-lightroom-mobile-free-features-vs-premium/)).
  - The iOS description advertises community-shared presets and batch fixes ([App Store](https://apps.apple.com/us/app/id878783582)).
- **Snapseed:** entirely free — "30+ pro tools and filters - no subscriptions, purchases, ads, or watermarks". Includes realistic film simulations, Halation, Bloom, Grain, batch edit, RAW develop and a Snapseed Camera ([App Store](https://apps.apple.com/us/app/id439438619)).
- **Polarr**
  - App Store prices: Polarr Lite $3.99 / $7.99 / $17.99 / $24.99; Polarr Studio $7.99 / $9.99 / $29.99 / $34.99; Polarr Monthly $3.99; Polarr Yearly $23.99 ([App Store](https://apps.apple.com/us/app/id988173374)).
  - Features: HSL, curves, grain and **LUT** in its global adjustments; users can "Create and share your own Polarr filters" and "Scan or produce Polarr filters as QR codes" ([App Store](https://apps.apple.com/us/app/id988173374)).
- **Picsart:** Gold Weekly $4.99, Gold Monthly $12.99, Gold Annual $57.00; Pro Weekly $11.99, Pro Monthly $13.99, Pro Annual $83.99; Plus Monthly $11.99, Plus Annual $64.99 ([App Store](https://apps.apple.com/us/app/id587366035)).
- **Tezza**
  - App Store prices: Tezza Monthly $3.99 / Yearly $19.99; Tezza Pro Weekly $4.99 / Monthly $6.99 / Yearly $39.99; Tezza Luxe Monthly $9.99 / Yearly $59.99; "Tezza Monthly Ambassador" $5.99 and "Yearly Ambassador" $39.99 ([App Store](https://apps.apple.com/us/app/id1393061654)).
  - Features: "40+ presets made with love by our founder", batch editing, feed planner ([App Store](https://apps.apple.com/us/app/id1393061654)).
- **Afterlight:** Weekly $1.99; Monthly $2.99 / $3.99; Yearly $15.99–$23.99; **Lifetime $19.99 / $39.99**; "300+ film-inspired presets" (Kodak Gold, Portra, Agfa Vista, disposable) ([App Store](https://apps.apple.com/us/app/id1293122457)).
- **Darkroom**
  - App Store prices: Monthly $9.99; Yearly $39.99 (discounted yearly $32.99); "Unlock Everything Forever" $99.99; legacy packs $3.99–$9.99 ([App Store](https://apps.apple.com/us/app/id953286746)).
  - Features: RAW/ProRAW, batch editing, "8K color grading". Apple Design Award 2020 ([App Store](https://apps.apple.com/us/app/id953286746)).
- **RNI Films**
  - App Store prices: Monthly RNI Pro $0.99 / $1.99; Yearly RNI Pro $9.99; film packs (Negative, Vintage, Instant, BW) $3.99 each ([App Store](https://apps.apple.com/us/app/id1017098672)).
  - Features: RAW editor, film grain/bloom/halation engine, video grading in beta ([App Store](https://apps.apple.com/us/app/id1017098672)).
- **Dehancer mobile**
  - Pricing is export-based: Unlimited Export $9.99/mo or $89.99/yr; Unlimited Photo Export $4.99/mo or $49.99/yr; non-renewable 1 year $150.00 ([App Store](https://apps.apple.com/us/app/id6443648413)).
  - Features: 86 film presets (Kodak, Fuji, Cinestill), grain/bloom/halation, batch editing, RAW (beta), video. Company claims "Trusted by 1 million+ creators" (not verified) ([App Store](https://apps.apple.com/us/app/id6443648413)).
- **Mattebox**
  - Mattebox Pro: $3.99 / $17.99 / $29.99 ([App Store](https://apps.apple.com/us/app/id452438265)).
  - Users can save edits as a new filter and share it "as an App Clip, no install required". Works on ProRes Log video. **Pro can "Export filters as Adobe Lightroom Profiles or 3D LUTs"** ([App Store](https://apps.apple.com/us/app/id452438265)).
  - A "FilmBox by Photomyne" iOS app exists, but it is a film-negative scanner and unrelated ([lookup](https://itunes.apple.com/lookup?id=1495155880&country=us)).
- **Lightleap:** "unlimited access" SKUs from $3.99 to $77.99, plus a legacy "Quickshot unlimited access" at $199.99 ([App Store](https://apps.apple.com/us/app/id1254875992)).
- **Hypic:** monthly Hypic Pro $6.99 / $10.99; yearly $69.99. Positioned on "retro film, clean girl presets, soft glow filters", batch edit and AI art ([App Store](https://apps.apple.com/us/app/id1644042837)).
- **Meitu:** VIP Weekly $8.99; Monthly $11.99–$12.99; Yearly $41.99–$59.99; VIP+ Monthly $13.99. VIP removes watermarks and ads ([App Store](https://apps.apple.com/us/app/id416048305)).
- **Foodie:** PRO Monthly $6.99; PRO annual $31.99–$34.99 ([App Store](https://apps.apple.com/us/app/id1076859004)).
- **Fotor:** Pro Week $6.99, Monthly $8.99, Annual $47.99; some effect packs $0.00–$0.99 ([App Store](https://apps.apple.com/us/app/id440159265)).
- **FLTR**
  - App Store prices: FLTR PRO $4.99 / $51.99; 12 months $14.99–$29.99; **Lifetime $39.99**; preset box $9.99 / $11.99; **"Get 1 custom preset" $4.99**, a paid custom-preset service ([App Store](https://apps.apple.com/us/app/id1448103572)).
  - Play description: "1500+ Lightroom presets, 74 DNG packs". Its model is a DNG preset library for Lightroom Mobile, not a full editor ([GP](https://play.google.com/store/apps/details?id=com.feelty&hl=en&gl=US)).
- **Koloro**
  - App Store prices: monthly $2.99; yearly $17.99 ($13.99 with trial); one-time $21.99 ([App Store](https://apps.apple.com/us/app/id1345159029)).
  - Play description: "1000+ Presets and Overlays", "One-click share or import recipe with QR Code in Instagram", batch edit for photo & video, DNG export to Lightroom ([GP](https://play.google.com/store/apps/details?id=com.cerdillac.persetforlightroom&hl=en&gl=US)).
- **Prequel / Esti:** Prequel Gold Weekly $4.99–$5.99 (special $2.99), Gold Yearly $14.99 ([App Store](https://apps.apple.com/us/app/id1325756279)). Esti Premium Weekly $4.99–$6.99, Yearly $39.99, and a "Premium Guide" at $4.99 ([App Store](https://apps.apple.com/us/app/id6457366208)).
- **Photoshop Express:** Premium $2.99–$4.99/mo, $34.99/yr; bundle with Adobe Express $9.99/mo or $99.99/yr ([App Store](https://apps.apple.com/us/app/id331975235)).
- **A Color Story:** PRO Monthly $4.99, PRO Membership $39.99; packs from $0.99 to $10.99 ("Starter Collection"); "500+ filters" ([App Store](https://apps.apple.com/us/app/id1015059175)).
- **Ultralight:** Pro $16.99 / $24.99, Monthly $4.99; à-la-carte kits $0.99–$1.99, e.g. "Film Kit", "RGB Curves" ([App Store](https://apps.apple.com/us/app/id972428565)).
- **Other preset-app price points:**
  - PRESETS (Gustas Brazaitis): weekly $3.99–$4.99, yearly $9.99–$29.99, "Over 200 Presets" ([App Store](https://apps.apple.com/us/app/id1457445491)).
  - Vidl: lifetime $14.99 / $29.99, 1 week $3.99 ([App Store](https://apps.apple.com/us/app/id1490818231)).
  - Edith / Preset Box: lifetime $15.99; Preset Box premium $4.99–$29.99 ([App Store](https://apps.apple.com/us/app/id1477761909)).
  - WayShot: Pro Weekly $9.99, Yearly $59.99–$69.99, coins $9.99–$49.99, "30 film shots $9.99" ([App Store](https://apps.apple.com/us/app/id6749303003)).
- **Fimii (indie)**
  - Pricing: "Fimii Premium – Lifetime $9.99" (App Store US) ([App Store](https://apps.apple.com/us/app/id6755296366)); ₫263,000 on Google Play VN ([GP VN](https://play.google.com/store/apps/details?id=com.ankii.fimii&hl=en&gl=VN)). Description: "A one-time upgrade unlocks the premium extras. No subscription."
  - Features: handcrafted film-stock presets, true 16-bit RAW (DNG/ProRAW and major camera brands), three-way color wheels, HSL and curves, reference-photo color matching (AI moves sliders; it does not generate pixels), batch export at full resolution, community preset collections, and #fimii featuring with exclusive presets ([GP](https://play.google.com/store/apps/details?id=com.ankii.fimii&hl=en&gl=US)).
  - Developer: "built by an independent developer Le Nguyen Khoa (ankii98)"; the site does not state a country ([fimii.app/about](https://fimii.app/about)).

### Inferences
- Pure "Lightroom preset library" apps (FLTR, Koloro, Sajjad IT, Inspiring Apps) reached 5–40M Play installs, but most are ad-funded. None appears in any Play top-50 grossing list checked (US, VN, JP, KR, ID, BR, DE). Their user reviews are strong (Koloro 4.80 from 431K ratings; FLTR 4.57 from 419K), which suggests high install volume but low average revenue per user. Koloro's Play listing has not been updated since 2024-06-27, which suggests the dedicated-preset niche has cooled.
- Film-emulation "pro" editors are overwhelmingly iOS-first: Darkroom, RNI Films, Dehancer and Mattebox have no Android version, and Ultralight is iOS-only. That leaves Android film-grade editing mostly to Lightroom, Snapseed, VSCO and small apps (PICFX, Film Simulator, Fimii). This is a gap a Google Play–first indie team could target.
- Many indie and film apps offer lifetime or one-time pricing: Fimii $9.99, Afterlight $19.99–$39.99, Koloro $21.99, Vidl $14.99–$29.99, FLTR $39.99 and Darkroom $99.99. By contrast, VC- or AI-driven apps (Prequel, Esti, Hypic, WayShot, Picsart) push weekly plans at $4.99–$11.99 a week.
- Web checkout is cheaper than in-app pricing for VSCO (e.g. Pro $59.99/yr on the web vs $69.99/yr in-app). That points to an incentive to steer users to web payments where store rules allow.

### Gaps
- Adobe's official Lightroom mobile free-vs-premium page returned HTTP 403, so the feature split comes from secondary sources.
- The Play scraper returned no developer address, so countries are inferred.
- The US App Store in-app list shows at most 10 SKUs; full Android subscription prices in USD were not visible (Play shows only a per-item IAP range).
- No reliable per-app preset counts were found for Lightleap, Hypic or Meitu.
- No Google Play version of Darkroom, RNI Films, Dehancer or Mattebox was found (searches by name and developer returned nothing on 2026-09-27).

## Q2. Video LUT / color-grading apps (CapCut, VN, Videoleap, KineMaster, LumaFusion, Blackmagic Camera, mcpro24fps, Protake, Filmic Pro, camera-maker apps, dedicated LUT apps, preset→LUT converters)

### Takeaway
Mass-market video editors on mobile offer built-in filters, but **.cube LUT import is uneven**:
- VN and LumaFusion advertise LUT import.
- CapCut mobile reportedly does not import custom LUTs (desktop does).
- Blackmagic Camera (free, Android since June 2024) now supports .cube LUT import for preview or burn-in.

Dedicated mobile LUT apps are a thin niche:
- **Android:** 3DLUT mobile dominates with 17M installs but has been stale since 2024. The rest have fewer than 500K installs.
- **iOS:** small new apps with a few hundred ratings each (PeekLut, LUT Studio, VideoLUT) charge $35–60 a year.

Camera makers (Panasonic LUMIX Lab, Fujifilm XApp) now give away LUT and recipe ecosystems for free.

### Cited Findings

**Statistics table B — video editing, cine-camera and LUT apps (pulled 2026-09-27)**

| App (developer, country) | Play package → installs band (exact counter) | Play rating (count) | Play first release / last update | Play price / IAP; ads | iOS id → US rating (count) | Key LUT / grading facts | Sources |
|---|---|---|---|---|---|---|---|
| CapCut (Bytedance Pte. Ltd.) | com.lemon.lvoverseas → 1B+ (2,009,892,307) | 3.56 (13,045,589) | 2020-04-10 / 2026-09-24 | Free; $0.49–$900.00; no ads | 1500855883 → 4.61 (1,122,051); VN 756,546 | App Store: Standard Monthly $9.99, Pro Monthly $19.99, Monthly $7.99, Yearly $89.99. Third-party 2026 guides say mobile has **no custom LUT import** (built-in filters only); desktop imports .cube/.3dl | [GP](https://play.google.com/store/apps/details?id=com.lemon.lvoverseas&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id1500855883), [aaapresets guide](https://aaapresets.com/blogs/guide-to-luts/mastering-cinematic-color-grading-on-capcut-mobile-in-2025-a-comprehensive-guide-to-luts-and-beyond), [cinem8](https://cinem8.co/blogs/blog/how-to-use-luts-in-capcut-for-color-grading) |
| VN: Photo & Video Editor (Ubiquiti Labs, LLC) | com.frontrow.vlog → 100M+ (333,932,593) | 4.71 (5,496,521) | 2018-05-04 / 2026-09-24 | Free; $0.99–$109.99; ads | 1343581380 → 4.76 (317,787); VN 28,589 | "Apply built-in filters or **import LUTs**"; 4K60 export; iOS "No Watermark"; App Store VN Pro $7.99 / $69.99; credits $1–$10 | [GP](https://play.google.com/store/apps/details?id=com.frontrow.vlog&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id1343581380) |
| Videoleap (Lightricks, Israel) | com.lightricks.videoleap → 10M+ (21,256,476) | 4.47 (198,960) | 2021-07-27 / 2025-11-04 | Free; $3.99–$299.99; no ads | 1255135442 → 4.61 (145,563) | App Store: unlimited access $4.99–$9.99, $35.99, subscription $69.99. Description lists AI filters and effects; no LUT import mentioned | [GP](https://play.google.com/store/apps/details?id=com.lightricks.videoleap&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id1255135442) |
| KineMaster (KineMaster Corp., Korea) | com.nexstreaming.app.kinemasterfree → 500M+ (547,257,711) | 4.45 (6,105,588) | 2013-12-26 / 2026-09-27 | Free; $0.19–$77.77; ads | 1609369954 → 4.69 (42,669); old iOS app 261,726 | App Store: Premium Monthly $8.49–$11.99, Annual $49.99–$59.99. Description lists "Color Filters"; LUT import not mentioned | [GP](https://play.google.com/store/apps/details?id=com.nexstreaming.app.kinemasterfree&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id1609369954) |
| LumaFusion (LumaTouch, US) | com.luma_touch.lumafusion → 50K+ (65,245) | 4.13 (3,354) | 2023-02-20 / 2026-09-18 | **Paid $29.99**; IAP $9.99–$69.99 | 1062022008 → **paid $29.99**, 4.75 (24,768) | "Import and apply .cube or .3dl LUTs", scopes. App Store: Creator Pass $9.99/mo or $69.99/yr; add-ons $19.99 | [GP](https://play.google.com/store/apps/details?id=com.luma_touch.lumafusion&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id1062022008) |
| Blackmagic Camera (Blackmagic Design, Australia) | com.blackmagicdesign.android.blackmagiccam → 1M+ (3,923,850) | 4.59 (14,570) | **2024-06-03** / 2026-09-03 | Free; no IAP; no ads | 6449580241 → 4.82 (23,056) | Android 3.1 added custom .cube LUT import (preview-only or recorded to clip); LUT Manager; bundled free LUTs incl. Apple Log→Rec.709 | [GP](https://play.google.com/store/apps/details?id=com.blackmagicdesign.android.blackmagiccam&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id6449580241), [IndieFilmmakers](https://indiefilmmakers.eu/blackmagic-camera-for-android-3-1-update-adds-lut-support-and-performance-boosts/) |
| mcpro24fps (Chantal Pro SIA, Latvia, inferred) — Android only | lv.mcprotector.mcpro24fps → 10K+ (16,241) | 4.57 (4,013) | 2019-02-09 / 2026-09-16 | **Paid $19.99**; IAP $0.99–$5.49 | — | Log recording, on-screen LUT monitoring, free technical LUTs; free demo app offered to test before buying | [GP](https://play.google.com/store/apps/details?id=lv.mcprotector.mcpro24fps&hl=en&gl=US) |
| Protake (Beijing Lingguang Zaixian, China) | com.blink.academy.protake → 1M+ (4,199,889) | 3.50 (5,610) | 2020-04-28 / 2026-04-22 | Free; $0.99–$19.99 | 1498431506 → 4.49 (1,341); last iOS update 2025-11-11 | ALEXA Log C recording, "a dozen" cinematic looks | [GP](https://play.google.com/store/apps/details?id=com.blink.academy.protake&hl=en&gl=US), [lookup](https://itunes.apple.com/lookup?id=1498431506&country=us) |
| Filmic Pro (Bending Spoons, Italy) | com.filmic.filmicpro → 1M+ (3,455,507) | **2.34** (17,832) | 2015-12-23 / **2025-11-04** | Free; $0.99–$59.99 | 436577167 → 3.70 (10,131) | App Store: weekly $1.99–$2.99, yearly $39.99, Creator Weekly $9.99, Cinematographer Kit $13.99. Bending Spoons bought it in 2022, switched it to subscription, and laid off the whole team in Nov 2023 | [GP](https://play.google.com/store/apps/details?id=com.filmic.filmicpro&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id436577167), [Videomaker](https://www.videomaker.com/news/uncertain-future-for-filmic-pro-as-entire-team-has-been-laid-off/), [CineD](https://www.cined.com/filmic-pro-is-joining-forces-with-bending-spoons-new-subscription-model/) |
| Edits (Instagram/Meta) | com.instagram.basel → 100M+ (120,358,340) | 4.66 (1,724,757) | 2025-04-21 / 2026-09-22 | Free; IAP $0.99–$1,049.00 | 6738967378 → 4.79 (87,941) | Video filters and effects, no watermark; no LUT import found in description | [GP](https://play.google.com/store/apps/details?id=com.instagram.basel&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id6738967378) |
| Adobe Premiere mobile (Adobe) | com.adobe.premiere → 100K+ (124,042) | 4.30 (1,345) | **Android release 2026-09-21** / 2026-09-22 | Free; $7.99–$69.99 | 6742757464 → 4.82 (25,269); iOS release 2025-09-30 | App Store: Premiere Mobile Monthly $7.99, Yearly $69.99; free export without watermarks | [GP](https://play.google.com/store/apps/details?id=com.adobe.premiere&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id6742757464) |
| InShot (InShot Inc.) | com.camerasideas.instashot → 500M+ (954,095,366) | 4.84 (24,650,245) | 2014-03-05 / 2026-09-21 | Free; $0.99–$199.99; ads | 997362197 → 4.85 (2,498,480) | Filters (context) | [GP](https://play.google.com/store/apps/details?id=com.camerasideas.instashot&hl=en&gl=US) |
| PowerDirector / Filmora / Alight Motion (context) | 100M+ each (144,139,420 / 155,201,491 / 173,653,574) | 4.20 / 3.99 / 3.14 | — | IAP up to $249.99 / $119.99 / $79.99 | — | Context only | [GP PD](https://play.google.com/store/apps/details?id=com.cyberlink.powerdirector.DRA140225_01&hl=en&gl=US), [GP Filmora](https://play.google.com/store/apps/details?id=com.wondershare.filmorago&hl=en&gl=US), [GP Alight](https://play.google.com/store/apps/details?id=com.alightcreative.motion&hl=en&gl=US) |
| Panasonic LUMIX Lab | com.panasonic.jp.lumixlab → 100K+ (119,426) | 3.87 (1,275) | 2024-05-24 / 2026-07-18 | Free; no IAP | 6499262377 → 3.92 (249) | Edits save as LUTs; "Magic LUT" builds a LUT from a reference photo with AI; "around 200 LUTs created by over 40 well-known creators"; real-time LUT transfer to camera | [GP](https://play.google.com/store/apps/details?id=com.panasonic.jp.lumixlab&hl=en&gl=US), [iOS](https://apps.apple.com/us/app/id6499262377) |
| FUJIFILM XApp | com.fujifilm.xapp → 500K+ (780,923) | 3.95 (7,641) | 2023-05-14 / 2026-07-02 | Free | 1586089681 → 4.12 (3,362) | Camera companion (context for recipes) | [GP](https://play.google.com/store/apps/details?id=com.fujifilm.xapp&hl=en&gl=US) |
| 3DLUT mobile (RELU OÜ, Estonia, inferred) | com.lutmobile.lut → **10M+ (17,435,741)** | 3.88 (29,634) | 2018-04-14 / **2024-07-29** | Free; $0.99–$20.99; no ads | — | "Mobile client of desktop 3D LUT Creator"; LUT packs downloaded from its server; users create filters on desktop and upload them | [GP](https://play.google.com/store/apps/details?id=com.lutmobile.lut&hl=en&gl=US) |
| 3DLUT mobile 2 (RELU OÜ) | com.lutcreator.lutmobile2 → 1M+ (1,652,228) | 3.89 (2,017) | 2021-01-11 / 2026-07-17 | Free; $0.49–$19.99 | — | Successor app | [GP](https://play.google.com/store/apps/details?id=com.lutcreator.lutmobile2&hl=en&gl=US) |
| Photo Curves – Color Grading (Curved Nebula) | com.foreachi.photocurves → 1M+ (1,063,905) | 4.46 (4,199) | 2020-08-30 / 2026-08-07 | $4.99–$11.99; ads | — | Curves-focused | [GP](https://play.google.com/store/apps/details?id=com.foreachi.photocurves&hl=en&gl=US) |
| AGC ToolKit – Watermark LUT (for GCam users) | com.agc.gcam_tools → 100K+ (445,557) | 4.54 (8,205) | 2023-07-20 / 2026-08-29 | $0.99–$99.99; ads | — | Tools category | [GP](https://play.google.com/store/apps/details?id=com.agc.gcam_tools&hl=en&gl=US) |
| L.U.T: Color grading for Media (Dots Game) | colorgrading.lutpro.nodevideo.alight → 100K+ (126,476) | **2.47** (399) | 2022-08-15 / 2026-03-03 | $0.99–$6.99; ads | — | Low quality | [GP](https://play.google.com/store/apps/details?id=colorgrading.lutpro.nodevideo.alight&hl=en&gl=US) |
| LUT Generator: Color Grading (AppDadz) | lut.generator.luts → 10K+ (13,685) | 4.20 (88) | 2023-11-04 / 2026-09-03 | $0.49–$3.49; ads | — | — | [GP](https://play.google.com/store/apps/details?id=lut.generator.luts&hl=en&gl=US) |
| New 2025–26 Android LUT entrants: CameLUT, ColorShaper, Modipix | CameLUT 1K+ (2,533), released 2025-12-18; ColorShaper 1K+ (2,139), released 2025-10-02; Modipix 5K+ (7,825) | Modipix 4.30 (143) | — | CameLUT $1.99–$15.99; Modipix $1.99–$19.99 | — | "Professional LUT Cam"; "Photo & Lut Editor"; "Film Lab & 3D LUT" | [CameLUT](https://play.google.com/store/apps/details?id=com.hearsilent.camelut&hl=en&gl=US), [ColorShaper](https://play.google.com/store/apps/details?id=com.aylwin.color_shaper&hl=en&gl=US), [Modipix](https://play.google.com/store/apps/details?id=com.duc_app_lab_ind.pic_trim_app&hl=en&gl=US) |
| iOS LUT apps: PeekLut (Lauper Labs) | — | — | — | — | 6473661560 → 4.69 (654), released 2024-01-01 | Peek+ $2.99/wk, $4.99/mo, $34.99/yr; imports .cube and HaldCLUT; "Every grade exports as a reusable LUT" | [iOS](https://apps.apple.com/us/app/id6473661560) |
| iOS: LUT Studio (Phoneframes AG) | — | — | — | — | 6479377583 → 4.71 (725), released 2024-04-15 | $7.99/wk, $9.99/mo, annual $29.99–$49.99, "LUT Studio Pro" $39.99 / $59.99; real-time LUT preview | [iOS](https://apps.apple.com/us/app/id6479377583) |
| iOS: VideoLUT (Enrique Garcia) | — | — | — | — | 1082340556 → 4.28 (356), released 2016 | PRO $0.99 / $6.99 / $9.99; "over 2500 presets"; .cube and .3dl; share LUTs via QR codes | [iOS](https://apps.apple.com/us/app/id1082340556) |
| iOS 2026 micro-launches: LUT Designer, LumKit, Lumae | — | — | — | — | 4 / 1 / 0 US ratings (released 2026-05-31 / 2026-07-14 / 2026-06-17) | Evidence of new entrants | [search API](https://itunes.apple.com/search?term=Colorful%20LUT&entity=software&country=us) |

- Preset→LUT conversion on mobile:
  - Mattebox Pro exports filters as 3D LUTs or Lightroom profiles ([App Store](https://apps.apple.com/us/app/id452438265)).
  - PeekLut exports every grade as a reusable LUT ([App Store](https://apps.apple.com/us/app/id6473661560)).
  - LUMIX Lab saves edits as LUTs ([GP](https://play.google.com/store/apps/details?id=com.panasonic.jp.lumixlab&hl=en&gl=US)).
  - Koloro and FLTR go the other way, exporting DNG presets for Lightroom Mobile ([GP Koloro](https://play.google.com/store/apps/details?id=com.cerdillac.persetforlightroom&hl=en&gl=US)).
  - A Google Play search for "lightroom preset to LUT converter" (2026-09-27) returned only preset-library apps and no dedicated XMP→.cube converter ([Play search](https://play.google.com/store/search?q=lightroom%20preset%20to%20LUT%20converter&c=apps&hl=en&gl=US)).

### Inferences
- Android has no strong, maintained "mobile LUT studio" that imports .cube files, lets users build and export LUTs, and grades both photo and video. 3DLUT mobile proves demand (17M installs), but it was last updated 2024-07-29, is rated 3.88 and depends on a desktop product. Newer entrants (CameLUT, ColorShaper, Modipix) are tiny. On iOS the same job sells for $35–60 a year (PeekLut, LUT Studio). This is a plausible gap for a Google Play–first team.
- The CapCut mobile LUT gap (if the third-party claims hold) plus VN's LUT import explains why creators pass LUT packs around for VN and CapCut desktop. A mobile app that converts presets to .cube and exports to CapCut or VN could ride the CapCut installed base: #1–3 in Video Players & Editors on every Play market checked.
- Pro cine-camera apps on Android are either paid-upfront niches (mcpro24fps $19.99, 16K installs) or free manufacturer tools (Blackmagic, 3.9M installs). Filmic Pro's decline (Play 2.34★, no Android update for about 10 months) left space that Blackmagic Camera took for free.

### Gaps
- CapCut's mobile LUT support could not be confirmed from CapCut's own documentation; the claim rests on third-party guides.
- LUT import in KineMaster, Videoleap and Edits could not be confirmed (descriptions do not mention it).
- The LumaFusion Android Creator Pass price in USD was not visible (IAP range $9.99–$69.99).
- No public download or revenue estimates were found for LUT-specific apps.

## Q3. Public revenue, subscriber and download estimates (store-reported vs estimated)

### Takeaway
Hard financial disclosures exist only for listed companies:
- **Meitu (primary source):** 2025 revenue RMB 3.86B; 16.91M paying subscribers.
- **Adobe:** reports aggregate freemium MAU, not Lightroom-specific figures.

Private-company figures come from dated press or third-party estimates:
- **VSCO:** 200M users and 160K Pro subscribers (May 2024).
- **Hypic:** about $1M+/month (Appfigures estimate, late 2025).
- **Picsart:** 150M MAU; ARR estimates vary.

The only reliable, comparable scale metric across all apps is the Play install counter in Tables A and B.

### Cited Findings
- **VSCO (press, May 2024 — older than 12 months):** 200 million global sign-ups, 160,000 Pro subscriptions, about 1 million new sign-ups a month, now profitable, VSCO Pro ≈25% of revenue, Pro at $59.99/yr ([PetaPixel, 2024-05-20](https://petapixel.com/2024/05/20/vsco-is-now-profitable-thanks-to-200-million-users-and-160000-pro-subs/); original report by [Bloomberg](https://www.bloomberg.com/news/articles/2024-05-17/photo-app-vsco-s-200-million-users-profitability-are-signaling-a-turnaround)).
  - An aggregator estimates 2025 VSCO revenue at "$85–95M" and ARR ">$100M". This is **unverified, low-confidence and not company-disclosed** ([Expanded Ramblings](https://expandedramblings.com/index.php/vsco-statistics-and-facts/)).
- **Hypic (Appfigures estimates, published 2025-12-19; full page returned 403, figures taken from the search-result extract):**
  - ~37M estimated downloads in 2024 and ~44M expected in 2025.
  - Monthly consumer spending went from under $100K to $250K (April 2025), to just under $1M (August), then $1M+ every month. November 2025 was the best month at $1.3M pre-fee.
  - Jan–Nov 2025 pre-fee revenue ≈ $6.7M.
  - "VSCO, the closest competitor in terms of revenue, is more than 3x larger than Hypic."
  - Source: [Appfigures insight](https://appfigures.com/resources/insights/20251219?f=3).
- **Meitu (company results, FY2025, published 2026-03):**
  - Revenue from continuing operations RMB 3.86B (+28.8%); photo, video & design segment RMB 2.95B (+41.6%, 76.6% of revenue); adjusted net profit RMB 965M.
  - Paying subscribers 16.91M (+34.1%) at a 6.1% subscription rate; MAU 276M, with more than 100M outside mainland China.
  - Wink passed 40M MAU.
  - Source: [Meitu press release](https://www.meitu.com/en/media/436).
- **Adobe (FY2026 Q3, Sep 2026):**
  - "Creative freemium" MAU, covering Firefly, Express, and the web/mobile versions of Premiere, Photoshop and Lightroom, passed 100M, up ~70% YoY.
  - Total MAU across all businesses is above 1B. Q3 revenue $6.76B.
  - Lightroom-mobile-only MAU is **not disclosed**.
  - Sources: [Gokhshtein summary](https://gokhshtein.com/news/2026-09-10-adobe-hits-676b-in-q3-revenue-crosses-1b-maus-on-freemium), [Subscription Insider](https://www.subscriptioninsider.com/blog/adobe-freemium-growth-surges-but-conversion-metrics-are-missing) (secondary coverage of earnings).
- **Picsart:**
  - 150M MAU and "more than 2 billion downloads" (2025 company claim, via an aggregator) ([Expanded Ramblings](https://expandedramblings.com/index.php/picsart-statistics-and-facts/)).
  - Passed $100M ARR in 2021 ([TechCrunch 2021-08-26](https://techcrunch.com/2021/08/26/picsart-raises-130m-from-softbank-becomes-unicorn-on-the-back-of-its-visual-creator-tools/) — **older data**).
  - ">$200M ARR late 2024" appears only as an unattributed "industry estimate" (low confidence) ([search summary](https://expandedramblings.com/index.php/picsart-statistics-and-facts/)).
  - Store-reported: Play exact counter 1,435,771,274 installs ([GP](https://play.google.com/store/apps/details?id=com.picsart.studio&hl=en&gl=US)).
- **Store-reported install counters (Play, 2026-09-27)**, largest to smallest:
  - CapCut 2.01B
  - Picsart 1.44B
  - InShot 954M
  - KineMaster 547M
  - Lightroom 471M
  - Snapseed 446M
  - VN 334M
  - PS Express 304M
  - VSCO 165M
  - Meitu 142M
  - Hypic 123M
  - Edits 120M (in ~17 months since its 2025-04-21 release)
  - Lumii 109M
  - Prequel 63M
  - Fotor 44M
  - Foodie 42M
  - Koloro 40M
  - Polarr 37M
  - FLTR 30M
  - Videoleap 21M
  - Lightleap 20M
  - 3DLUT mobile 17M
  - Afterlight 11M
  - Tezza 10M
  - Blackmagic Camera 3.9M
  - Sources: Play pages linked in Tables A/B.
- The Play in-app price ceilings hint at the tiers each app sells:
  - Lightroom's ceiling is $499.99, likely Creative Cloud bundles.
  - CapCut's ceiling is $900.00.
  - Fotor's ceiling is $749.99.
  - FLTR's ceiling is $69.99.
  - Tezza's ceiling is $39.99.
  - Sources: [GP Lightroom](https://play.google.com/store/apps/details?id=com.adobe.lrmobile&hl=en&gl=US), [GP CapCut](https://play.google.com/store/apps/details?id=com.lemon.lvoverseas&hl=en&gl=US).

### Inferences
- Taking the Appfigures statement literally ("VSCO more than 3x Hypic"), VSCO's mobile gross revenue in late 2025 was probably above $3–4M a month. That is roughly consistent with the $85–95M/yr aggregator estimate, but both are estimates.
- Meitu's 6.1% paid rate (16.91M of 276M MAU) and VSCO's ~160K Pro out of ~200M sign-ups (Plus not counted) show how low conversion is in this category. A small team should plan for paid conversion in the low single digits.

### Gaps
- Sensor Tower, AppMagic and Appfigures app-profile pages were blocked (403) or not attempted. No per-app monthly revenue or download estimates were obtained for Lightroom mobile, Tezza, FLTR, Koloro, Polarr, Lightleap, VN, Videoleap, Blackmagic Camera or the LUT apps.
- VSCO's current total paid-member count (Plus + Pro) is not public; the only data point is 160K Pro in 2024.

## Q4. Creator economy: selling presets and LUTs outside the stores, and in-app sharing

### Takeaway
Preset and LUT selling is a large, fragmented, low-price digital-goods market:
- **Etsy:** bestseller bundles sell tens of thousands of copies at about $1–$5 each; desktop "pro" packs sell for about $55 each.
- **Gumroad:** about 1.3K–4.6K discoverable Lightroom-preset listings and about 600 LUT listings. The most-reviewed items are free lead magnets.
- **Fujifilm recipes:** a patronage model (Fuji X Weekly: 400+ recipes, $19.99/yr patron tier).

Creator economics are also moving into apps:
- **Sharing codes:** Polarr QR filters, Koloro QR recipes, VSCO Recipes, Lightroom Community/Remix, VideoLUT QR codes, Mattebox App Clips.
- **Creator LUT libraries:** LUMIX Lab (200 LUTs from 40+ creators).
- **Influencer-branded filter apps**, which chart in Korea (filmhwa, Berryfilm).

### Cited Findings
- **Etsy (EtsyHunt third-party estimates, data updated 2026-09-01):**
  - "10,000+ LIGHTROOM Presets Bundle" (shop KatherineDream): 40,172 total sales, about 45 a week, est. revenue $215,724 (≈$5.37 per sale).
  - "1000 FILM Vintage Lightroom Mobile & Desktop Presets" (FilAndEllieStudio): 7,026 sales, $31,617.
  - "25 Retro 90's Lightroom Presets" (CVRpresets): 6,870 sales, $9,412 (≈$1.37 per sale).
  - "MRP Desktop Presets" (MaliaRosePhotography): 1,548 sales, $85,140 (≈$55 per sale).
  - "12,000+ DaVinci Resolve Mega Bundle": 122 sales, $533.
  - Source: [EtsyHunt top presets](https://ehunt.ai/etsy-competitor-research/best-etsy-presets).
- A Jakesout "Best Sellers Lightroom Preset Bundle" (42 presets + 11 tools) has 10,046 Etsy favorites, according to the search-result extract ([Etsy listing](https://www.etsy.com/listing/834939903/best-sellers-lightroom-preset-bundle)). Etsy search and market pages returned 403, so **the total Etsy result count could not be retrieved**.
- **Gumroad Discover (queried 2026-09-27 via gumroad.com/products/search):**
  - Tag "lightroom presets": 1,304 products. Keyword "lightroom presets": 4,607 products. File types among the keyword results: DNG 2,474, ZIP 1,543, XMP 456.
  - Other tags: "luts" 595; "lut" 249; "davinci resolve" 503; "color grading" 197; "film presets" 114; "capcut" 10; "vsco" 10; "fujifilm recipes" 1.
  - Source: [Gumroad search API — lightroom presets](https://gumroad.com/products/search?tags=lightroom+presets&sort=most_reviewed), [luts](https://gumroad.com/products/search?tags=luts&sort=most_reviewed).
- **Most-reviewed Gumroad items are mostly free lead magnets:**
  - ProEdit "Free Cinematic LUT" (€0, 823 ratings).
  - BeArt "20 Free Lightroom Presets" ($0, 342).
  - RNI "All Films 5 – Demo" ($0, 327).
  - Paid examples:
    - PresetLove "300+ Preset Bundle" $6.99 (395 ratings).
    - Alex Ruskman "Kodak Vision Lab 2383 LUTs" €14 (228).
    - FUTC "Analog Vibes" Lightroom presets $10 (97).
    - Ellen Escapes single Lightroom Mobile presets £2.99 (e.g. "Fujifilm Preset", 42 ratings); an 8-preset bundle at £9.99.
    - Influencer "ULTIMATE PRESET COMBO (100+ presets)" $79.99.
  - Source: [Gumroad search](https://gumroad.com/products/search?tags=lightroom+presets&sort=most_reviewed).
- Self-reported case: one creator says Lightroom presets earned "over $200,000" across marketplaces over several years. The page body could not be fetched; the figure comes from the search-result extract ([Oliur](https://www.oliur.com/selling-lightroom-presets)). Marketing blogs claim "$500–$5,000+ per month" for top sellers (low-quality, promotional sources) ([Kamero](https://kamero.ai/biz-lab/photographer-passive-income-streams-2026)).
- **Fujifilm recipes:**
  - Fuji X Weekly's app has "more than 400 Fujifilm Recipes". On 2026-08-20 it added direct app-to-camera recipe transfer over USB-C (iOS first; Android by 2026-09-09). Patrons can "create and send sets of Recipes" ([Fuji X Weekly, 2026-08-20](https://fujixweekly.com/2026/08/20/new-send-recipes-to-your-camera-directly-from-the-fuji-x-weekly-app/)).
  - Patron tier $19.99/yr on the App Store ([App Store](https://apps.apple.com/us/app/id1539047257)). Play: 100K+ (407,926), 4.44 (875), IAP $19.99 ([GP](https://play.google.com/store/apps/details?id=com.fujixweekly.FujiXWeekly&hl=en&gl=US)).
  - Competitor FujiStyle – Film Recipes Frame (Turing Vision): Play 10K+ (21,872), released 2025-12-25 ([GP](https://play.google.com/store/apps/details?id=com.fujistylelead.global&hl=en&gl=US)); iOS 4.78 (363), $3.99/mo, $9.99/quarter, $14.99/yr ([App Store](https://apps.apple.com/us/app/id6504739559)).
  - Other Play recipe apps: Fuji Recipes, Filmsim Recipes, SOOC, Fuji Pic ([Play search](https://play.google.com/store/search?q=fujifilm%20recipes&c=apps&hl=en&gl=US)).
- **In-app sharing and creator features:**
  - VSCO Recipes save and share editing formulas (launched Nov 2017) ([PetaPixel 2017](https://petapixel.com/2017/11/08/vscos-recipes-let-share-editing-formulas-others/)).
  - Lightroom's Community "Remix" lets users edit others' shared photos and see their edits ([Adobe HelpX](https://helpx.adobe.com/sg/lightroom/mobile/get-started/remix-photos-in-community.html)). Its iOS listing promotes "presets shared by creators around the world" ([App Store](https://apps.apple.com/us/app/id878783582)).
  - Polarr lets users create and share filters and import them via QR codes ([App Store](https://apps.apple.com/us/app/id988173374)).
  - Koloro recipes can be shared or imported via QR or code on Instagram ([GP](https://play.google.com/store/apps/details?id=com.cerdillac.persetforlightroom&hl=en&gl=US)).
  - VideoLUT shares LUTs via QR codes ([App Store](https://apps.apple.com/us/app/id1082340556)).
  - Mattebox shares a filter as an App Clip ([App Store](https://apps.apple.com/us/app/id452438265)).
  - LUMIX Lab offers "around 200 LUTs created by over 40 well-known creators" ([GP](https://play.google.com/store/apps/details?id=com.panasonic.jp.lumixlab&hl=en&gl=US)).
  - 3DLUT mobile lets creators upload LUTs from the desktop 3D LUT Creator ([GP](https://play.google.com/store/apps/details?id=com.lutmobile.lut&hl=en&gl=US)).
  - Fimii adds community preset collections and sends exclusive presets to photographers it features ([GP](https://play.google.com/store/apps/details?id=com.ankii.fimii&hl=en&gl=US)).
  - FLTR sells a "Get 1 custom preset" IAP at $4.99 ([App Store](https://apps.apple.com/us/app/id1448103572)).
  - Tezza sells an "Ambassador" subscription tier ($5.99/mo, $39.99/yr) ([App Store](https://apps.apple.com/us/app/id1393061654)).
- **Influencer-branded filter apps (Korea):**
  - filmhwa: "the unique color of @hwa.min, an influencer loved by 1 million followers", new filters monthly. Paid $2.99 on iOS, 4.77 (432 US ratings), Korea iOS Photo & Video top grossing #62 on 2026-09-27 ([App Store](https://apps.apple.com/us/app/id6443723657)). The Android version is free, 10K+ (28,588) ([GP](https://play.google.com/store/apps/details?id=app.arttic.filmhwa&hl=en&gl=US)).
  - Berryfilm: by filter creator @berryveryloveyou ("60만 팬", 600K fans). 40+ soft Korean-style filters, new filters monthly, paid $1.99, KR iOS top grossing #59 ([App Store](https://apps.apple.com/us/app/id6741474933)).
  - Tezza is the US equivalent: an app built around founder Tezza's presets ([App Store](https://apps.apple.com/us/app/id1393061654)).

### Inferences
- Off-store sellers mostly sell DNG files (for Lightroom Mobile) rather than XMP or .cube. Gumroad has 2,474 DNG-tagged vs 456 XMP-tagged results for "lightroom presets", which confirms Lightroom Mobile as the dominant consumption surface. An app that imports DNG, XMP and .cube files people already bought could tap an existing installed base of purchased looks.
- Two monetization templates look replicable for a small team:
  - A **creator marketplace or white-label**: influencer-branded filter packs or apps, as in the Korea examples, with revenue share.
  - A **recipe library with patronage**: the Fuji X Weekly model, extendable to other camera brands such as Ricoh (Ritchie Roesch already has "Ricoh Recipes") ([Play search](https://play.google.com/store/search?q=Fuji%20X%20Weekly%20recipes&c=apps&hl=en&gl=US)).
- Volume is concentrated in mega-bundles ("10,000+ presets") at very low per-sale prices. Presets have become commoditized, and value is shifting to curation, film-accurate science and workflow (batch, RAW, video).

### Gaps
- Etsy and Creative Market result counts could not be retrieved (403); Creative Market price points are missing.
- No hard data was found on the "$10M influencer preset sales" claim; it appeared only in a low-quality listicle and was not included as fact.
- Fuji X Weekly patron counts are not published.
- No data was found on revenue shares paid to creators inside apps (e.g. LUMIX Lab creators, Tezza ambassadors).

## Q5. Chart positions (Top Free / Top Grossing, Photography and Video categories) — US, VN, JP, KR, ID, BR, DE, snapshot 2026-09-27

### Takeaway
The chart leaders are:
- **All markets:** Lightroom and Picsart are the only photo editors consistently in the Top 20 grossing on both stores. CapCut is #1–4 on both stores in every market.
- **Vietnam and Asia:** Meitu, Hypic, Ulike and Wink dominate VN, ID, JP and KR.
- **VSCO and Tezza** chart in iOS grossing (US #22 and #23) but are weak on Google Play grossing: VSCO appears only in BR (#32) and DE (#46); Tezza appears in no Play top-50 list.
- **Film looks in Vietnam:** a Vietnamese-built film-preset editor, Fimii, is #11 top free (iOS Photo & Video, VN) and #14 top free (Play Photography, VN), 7 months after launch. Film-look demand is also strong in Korea.
- **Google Play Photography grossing** lists are now crowded with AI generators (Momo, PixVerse, Hailuo, AI Mirror).

### Cited Findings
**Google Play top 50, pulled 2026-09-27** (lists: [US Photography](https://play.google.com/store/apps/category/PHOTOGRAPHY?hl=en&gl=US), [VN Photography](https://play.google.com/store/apps/category/PHOTOGRAPHY?hl=en&gl=VN), [Video Players & Editors](https://play.google.com/store/apps/category/VIDEO_PLAYERS?hl=en&gl=US); retrieved via google-play-scraper `list()`). Cells show free rank / grossing rank; "–" means outside the top 50.

| App | US | VN | JP | KR | ID | BR | DE |
|---|---|---|---|---|---|---|---|
| Lightroom (Photography) | 23 / 3 | 44 / 2 | 8 / 6 | 28 / 11 | 24 / 4 | **1** / 2 | 15 / 2 |
| Picsart | 12 / 2 | 6 / 3 | 23 / 10 | 50 / 14 | 6 / 2 | 6 / 5 | 5 / 3 |
| Snapseed | 33 / – | 41 / – | 28 / – | 36 / – | 18 / – | 48 / – | 13 / – |
| Meitu | – / 38 | 3 / 7 | 5 / 3 | 4 / 2 | 7 / 1 | 32 / 22 | – / 39 |
| Hypic | 18 / – | – / 30 | 16 / – | 41 / – | 4 / 6 | – / 12 | 10 / 45 |
| VSCO | – / – | – / – | – / – | – / – | – / – | 33 / 32 | – / 46 |
| Prequel | – / 35 | – / 34 | 35 / 43 | 30 / 23 | – / 43 | – / 27 | – / 32 |
| Photoshop Express | 48 / 34 | – / 37 | – / 40 | – / 38 | – / – | – / 41 | 45 / 26 |
| Fotor | – / 44 | – / – | – / 25 | – / – | – / – | – / – | – / 30 |
| Foodie | – | – | – / 42 | – / 20 | – | – | – |
| Ulike (Play) | – | 11 (free) | – / 46 | – / 16 | – | – | – |
| Polarr | – | – | – | – / 37 | – | – | – |
| Fimii | – | **14 (free)** | – | – | – | – | – |
| ProCCD (capture, context) | – | 10 (free) | – | – | 35 (free) | 45 (free) | – |
| Blackmagic Camera | – | 46 (free) | – | – | – | – | – |
| FLTR / Koloro / Tezza / Afterlight / Lightleap / 3DLUT mobile | – | – | – | – | – | – | – |
| CapCut (Video Players & Editors) | 1 / 1 | 2 / 2 | 3 / 3 | – / 3 | 2 / 2 | 2 / 1 | 1 / 1 |
| Edits (Video) | 5 / – | 36 / – | 10 / – | 7 / – | 19 / – | 4 / – | 2 / – |
| VN (Video) | 30 / 43 | – / 26 | 30 / – | – / – | – / 29 | – / – | 18 / – |
| KineMaster (Video) | – / 13 | – / 17 | – / 17 | 43 / 7 | – / 12 | – / 12 | – / 21 |
| Videoleap (Video) | – / 27 | – | – | – | – | – | – |
| Adobe Premiere (Video; Android launched 2026-09-21) | 10 / – | 22 / – | 12 / – | 26 / – | 50 / – | 20 / – | 5 / – |

- Play US Photography top grossing 1–10 (2026-09-27): Momo (AI), Picsart, Lightroom, AI Mirror, PixVerse, Photoroom, FaceApp, Hailuo AI, Shots, Private Photo Vault ([Play](https://play.google.com/store/apps/category/PHOTOGRAPHY?hl=en&gl=US)).
- Play VN Photography top grossing 1–10: FaceApp, Lightroom, Picsart, Hailuo AI, PixVerse, Photoroom, Meitu, Momo, AI Mirror, Shots ([Play VN](https://play.google.com/store/apps/category/PHOTOGRAPHY?hl=en&gl=VN)).

**iOS App Store Photo & Video top 100, pulled 2026-09-27** (feeds: `https://itunes.apple.com/{cc}/rss/topfreeapplications/limit=200/genre=6008/json` and `topgrossingapplications`, e.g. [VN grossing](https://itunes.apple.com/vn/rss/topgrossingapplications/limit=200/genre=6008/json), [US grossing](https://itunes.apple.com/us/rss/topgrossingapplications/limit=200/genre=6008/json)). Cells show free rank / grossing rank.

| App | US | VN | JP | KR | ID | BR | DE |
|---|---|---|---|---|---|---|---|
| CapCut | 2 / 4 | **1 / 1** | 3 / 4 | 4 / 4 | 2 / 1 | 1 / 3 | 1 / 4 |
| Lightroom | 23 / 13 | 39 / 17 | 42 / 13 | 38 / 18 | 19 / 10 | 25 / 12 | 20 / 10 |
| Picsart | 17 / 14 | 19 / 9 | 36 / 12 | 37 / 15 | 15 / 9 | 14 / 14 | 15 / 11 |
| VSCO | 78 / 22 | 32 / 34 | – / 35 | – / 31 | 63 / 23 | 21 / 22 | – / 32 |
| Tezza | 72 / 23 | – | – | – | 72 / 34 | 84 / 40 | – / 37 |
| Prequel | 40 / 25 | 85 / 24 | 71 / 36 | 43 / 34 | – / 52 | 63 / 25 | 52 / 17 |
| Esti (Prequel) | 77 / 47 | – | – | 82 / – | 53 / 55 | 74 / 80 | 85 / 41 |
| Hypic | 20 / – | **7 / 5** | 21 / 57 | 36 / 48 | 12 / 18 | 24 / 44 | 23 / 59 |
| Meitu | 46 / 34 | 2 / 3 | 9 / 6 | 6 / 3 | 1 / 4 | 49 / 36 | – / 33 |
| Wink (Meitu video) | 61 / – | 5 / 6 | 7 / 18 | 27 / 44 | 6 / 8 | 43 / – | – / 89 |
| Ulike | n/a (not in US store) | 20 / 16 | 69 / 46 | 75 / 30 | – | – | – |
| Foodie | – | 49 / 28 | – / 40 | 85 / 26 | – | – | – |
| Snapseed | 41 / – | 54 / – | 70 / – | 44 / – | 22 / – | 39 / – | 21 / – |
| **Fimii** | – | **11 / 49** | – | – | – | – | – |
| FujiStyle | – | – / 85 | – | – | – | – | – |
| FLTR | – | – / 99 | – | – | – | – | – |
| Berryfilm / filmhwa | – | – | – | – / 59 and – / 62 | – | – | – |
| WayShot | 39 / 81 | – | – | – | – | – | 87 / – |
| Fotor | – | – | – / 90 | – | – | – | – / 95 |
| Polarr | – | – | – | – / 46 | – | – | – |
| Photoshop Express | – / 37 | – / 72 | – / 38 | 97 / 32 | – / 54 | – / 61 | 95 / 29 |
| Edits | 8 / – | 51 / – | 16 / – | 7 / – | 20 / – | 2 / – | 5 / – |
| Blackmagic Camera | 32 / – | 28 / – | 76 / – | 34 / – | 32 / – | 22 / – | 27 / – |
| VN app | 76 / – | – | – | – | 42 / 53 | 88 / – | 55 / – |
| Videoleap | – / 45 | – | – / 73 | – | – / 68 | – / 71 | – / 50 |
| KineMaster | – | – | – | – / 68 | – / 89 | – | – |
| Adobe Premiere | 80 / – | – | 67 / – | 88 / – | – | – | – |
| Not in any top-100 list | Afterlight, Darkroom, RNI Films, Dehancer, Lightleap, Koloro, A Color Story, LumaFusion, Filmic Pro, Ultralight, Vidl, Edith | | | | | | |

- Context (capture-first apps, outside this scope but in the same charts):
  - Dazz Cam: US free #24, VN 14 / 30, BR 5 / 15.
  - 101cam – Film & Digital Camera: **KR free #1**, BR free #3, JP free #14, US free #54.
  - Other VN top-free film cameras: NOMO CAM #15, Fomz #56, OldRoll #52, Eluvo #78.
  - Source: [VN free feed](https://itunes.apple.com/vn/rss/topfreeapplications/limit=200/genre=6008/json), [KR free feed](https://itunes.apple.com/kr/rss/topfreeapplications/limit=200/genre=6008/json).
- iOS US Photo & Video top grossing 1–25 (2026-09-27): YouTube, Snapchat, Instagram, CapCut, Google Photos, Canva, Momo, Facetune, Twitch, FaceApp, Shots, Skylight, **Lightroom (13)**, **Picsart (14)**, AI Mirror, Airbrush, Runway, SCRL, Splice, Retake AI, Amazon Photos, **VSCO (22)**, **Tezza (23)**, Photoroom, **Prequel (25)** ([US grossing feed](https://itunes.apple.com/us/rss/topgrossingapplications/limit=200/genre=6008/json)).
- iOS VN Photo & Video top grossing 1–30 (2026-09-27): CapCut, YouTube, Meitu, Google Photos, **Hypic (5)**, Wink, Remini, Canva, Picsart, BeautyPlus, BeautyCam, Instagram, B612, SnapEdit, EPIK, **Ulike (16)**, **Lightroom (17)**, ElevenLabs, Photoroom, SODA, SNOW, Runway, FaceApp, **Prequel (24)**, PrettyUp, Instories, SCRL, **Foodie (28)**, Retake AI, Dazz Cam (30). VSCO is 34, Fimii 49 ([VN grossing feed](https://itunes.apple.com/vn/rss/topgrossingapplications/limit=200/genre=6008/json)).

### Inferences
- **Vietnam is a film and aesthetic-filter market.** Fimii (an indie VN developer by name, 7 months old, lifetime $9.99), Foodie, Dazz, ProCCD, NOMO, Fomz and FujiStyle all chart in VN. iOS VN rating counts are unusually high for filter apps: Lightleap 101K, Foodie 101K, Polarr 93K, Hypic 76K, Scep "Presets for Lightroom" 21.5K. Those VN counts rival or exceed their US counts, so VN is a large domestic test market for a Vietnamese team.
- For global revenue, Google Play grossing for pure preset or filter apps is hard: only Lightroom, Picsart, Meitu, Prequel, Hypic and PS Express show up. iOS grossing is more open to aesthetic subscription apps (VSCO #22, Tezza #23, Prequel #25, Esti #47 in the US). A Google Play–first launch should expect to monetize mainly through iOS or web later, or through lifetime unlocks and ads on Android.
- Korea shows a distinct niche for influencer and "Korean-tone" filter apps (filmhwa, Berryfilm) and film cameras (101cam #1). Japan and Korea favor beauty-plus-filter apps (Meitu, SNOW, Ulike, Foodie).

### Gaps
- Charts are a single-day snapshot. Play lists are top 50 only and iOS lists top 100 only, so lower ranks for FLTR, Koloro, Tezza (Play) and similar apps are unknown.
- Play "top grossing" as served on the web may differ from the in-app Play Store charts.
- No historical rank trend (e.g. Sensor Tower rank history) was collected.
- Ulike does not appear in the US stores, and the Android version has not been updated since 2025-02-11.

## Q6. Implications for a Vietnamese indie team picking 3 camera / preset / LUT apps (evidence-linked observations)

### Takeaway
The evidence points to four openings: an Android-first film-emulation editor, a mobile LUT studio, a creator-look distribution layer, and lifetime pricing. A solo Vietnamese developer (Fimii) has already shown in 2026 that a handcrafted film-preset editor with a one-time $9.99 unlock can reach the VN top 15 on both stores.

1. **Android-first "pro film" editor.** Darkroom, RNI, Dehancer and Mattebox are iOS-only.
2. **Mobile LUT studio (Android).** It would import .cube, XMP and DNG files, create and export LUTs, and grade photo and video. 3DLUT mobile shows demand (17M installs) but is stale, and CapCut mobile reportedly cannot import LUTs.
3. **Creator-look distribution layer.** QR or code sharing, creator packs, influencer-branded apps, and recipe libraries for Fujifilm, Ricoh and other brands.

### Cited Findings
- Fimii: Play 5,000+ installs, released 2026-02-03, VN rating 4.89 from 229 ratings; lifetime ₫263,000 / $9.99; "No subscription". It is VN iOS Photo & Video #11 free and #49 grossing, and Play VN Photography #14 free (2026-09-27). Built by "an independent developer Le Nguyen Khoa (ankii98)" ([GP](https://play.google.com/store/apps/details?id=com.ankii.fimii&hl=en&gl=VN), [App Store](https://apps.apple.com/us/app/id6755296366), [fimii.app](https://fimii.app/about), [VN feed](https://itunes.apple.com/vn/rss/topfreeapplications/limit=200/genre=6008/json)).
- iOS-only pro film editors: Darkroom (29,354 US ratings), RNI Films (9,062), Dehancer (430), Mattebox (32). No Play listings were found ([Darkroom](https://apps.apple.com/us/app/id953286746), [RNI](https://apps.apple.com/us/app/id1017098672), [Dehancer](https://apps.apple.com/us/app/id6443648413)).
- Android LUT: 3DLUT mobile has 17.4M installs and was last updated 2024-07-29 ([GP](https://play.google.com/store/apps/details?id=com.lutmobile.lut&hl=en&gl=US)). iOS LUT apps charge $34.99–$59.99 a year ([PeekLut](https://apps.apple.com/us/app/id6473661560), [LUT Studio](https://apps.apple.com/us/app/id6479377583)).
- Creator economy: Gumroad has 4,607 "lightroom presets" results, 2,474 of them DNG ([Gumroad](https://gumroad.com/products/search?query=lightroom%20presets)). The top Etsy bundle has about 40K sales ([EtsyHunt](https://ehunt.ai/etsy-competitor-research/best-etsy-presets)). Korean influencer filter apps chart in iOS grossing ([filmhwa](https://apps.apple.com/us/app/id6443723657), [Berryfilm](https://apps.apple.com/us/app/id6741474933)).

### Inferences
- Competing head-on with CapCut, Hypic, Meitu or Lightroom on general editing is unrealistic. The three evidence-backed wedges are Android film editing, Android LUT tooling, and creator/recipe distribution.
- Price anchors for a global launch (US):
  - Weekly: $2.99–$4.99.
  - Monthly: $2.99–$9.99.
  - Yearly: $14.99–$39.99.
  - Lifetime: $9.99–$39.99.
  - Per-pack: $0.99–$3.99 (RNI $3.99 packs).
  - Pro LUT tools: $35–60/yr.
  - VN local pricing: ₫29,000–₫829,000 (Ulike Play IAP range); ₫263,000 lifetime (Fimii).

### Gaps
- No retention or conversion data per app was found. Revenue for Fimii, Koloro, FLTR, Tezza and the LUT apps is unknown; Sensor Tower and AppMagic data were not accessible.
