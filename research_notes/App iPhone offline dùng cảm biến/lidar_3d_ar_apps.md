# LiDAR / Depth / ARKit / RoomPlan / Object Capture / Gaussian-splat / AR-measure apps on iPhone: ranked dataset (global, Europe priority; data pulled 2026-09-27)

**How the data was collected (read first)**
- All ratings, rating counts, sellers, prices, release and update dates, and in-app-purchase (IAP) price lists come straight from Apple, pulled on **2026-09-27**. Sources: the iTunes Lookup/Search API (`https://itunes.apple.com/lookup?id=<ID>&country=<cc>`) and the App Store listing pages (`https://apps.apple.com/<cc>/app/id<ID>`). They are **disclosed platform data, not estimates**. `userRatingCount` is the lifetime rating count in that one storefront.
- Chart ranks come from Apple's legacy per-category iTunes RSS feeds, e.g. `https://itunes.apple.com/de/rss/topgrossingapplications/limit=200/genre=6008/json`. The feeds were timestamped 2026-09-27T01:14 PT but return only the **top 100**, so "not ranked" means "not in the top 100 of the categories checked". I checked 8 categories (Utilities, Photo & Video, Productivity, Lifestyle, Graphics & Design, Business, Shopping, Health & Fitness) × top-free and top-grossing × US, GB, DE, FR and VN.
- **Third-party download and revenue estimates (Sensor Tower, Appfigures, AppMagic, data.ai) could not be collected.** The session's web-search budget ran out before this task began, and those platforms are paywalled. Every download or revenue figure below is therefore either (a) disclosed by the company, (b) a chart-rank signal, or (c) an explicitly labelled proxy, namely lifetime rating counts. Where nothing was found, the field says "n/a".

## Q1. Which LiDAR/3D/AR apps lead on iOS by downloads, revenue and chart rank? (ranked dataset)

### Takeaway
There is no public, citable download or revenue estimate for this niche. The measurable signals are rating counts and top-grossing ranks. On those signals, **Polycam is the only pure 3D-scanning app that ranks in any top-grossing chart**: US Photo & Video #89, GB #58, DE #53, FR #42 on 2026-09-27. By rating volume the scanning leaders are Polycam (43.6K US ratings), 3d Scanner App (16.1K) and Scaniverse (11.7K). The floor-plan leader is **magicplan** (41.1K US ratings; top-grossing in DE Productivity #49 and FR #64). Much bigger rating bases belong to general AR-measure utilities (Tape Measure by Level Labs, 88.8K) and to home-design apps (Houzz, IKEA, Home Design 3D, Planner 5D, Room Planner), where AR or LiDAR is a secondary feature.

### Cited Findings
**A. Master table: ratings by storefront, ranked by US + EU-7 rating count (a popularity proxy, not downloads). Data as of 2026-09-27. Source for every cell: iTunes Lookup API `https://itunes.apple.com/lookup?id=<id>&country=<cc>` and `https://apps.apple.com/<cc>/app/id<id>`.**

| # | App | Category | App Store seller (2026-09-27) | US rating / count | UK | DE | FR | IT | ES | NL | PL | EU-7 ratings sum | VN | US+EU-7 sum |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | IKEA (id1452164827) | Retail + AR/Kreativ | Inter IKEA Systems B.V. | 4.79 / 148,391 | 4.74 / 64,229 | 4.72 / 97,897 | 4.74 / 59,331 | 4.75 / 47,147 | 4.75 / 52,005 | 4.65 / 27,743 | 4.85 / 27,218 | 375,570 | absent | 523,961 |
| 2 | Houzz (id399563465) | Home design marketplace + AR View in My Room | Houzz Inc. | 4.84 / 324,095 | 4.77 / 20,583 | 4.74 / 7,078 | 4.73 / 14,107 | 4.73 / 7,554 | 4.72 / 5,004 | 4.62 / 439 | 4.74 / 332 | 55,097 | 4.84 / 673 | 379,192 |
| 3 | Home Design 3D (id463768717) | Home design | Home Design 3D srl | 4.32 / 104,824 | 4.29 / 20,597 | 4.19 / 18,058 | 4.25 / 24,821 | 4.28 / 9,347 | 4.3 / 7,321 | 4.21 / 6,887 | 4.38 / 1,655 | 88,686 | 4.58 / 6,441 | 193,510 |
| 4 | Home Planner AI (Room Planner Ltd) (id1076159017) | Home design + 3D scanner | Room Planner Ltd | 4.6 / 46,138 | 4.49 / 10,598 | 4.4 / 13,983 | 4.59 / 12,168 | 4.63 / 9,474 | 4.64 / 9,538 | 4.46 / 4,625 | 4.66 / 4,120 | 64,506 | 4.76 / 4,411 | 110,644 |
| 5 | Tape Measure (Level Labs) (id1271546805) | AR measure | Level Labs, LLC | 4.43 / 88,823 | 4.26 / 10,750 | 4.34 / 195 | 4.26 / 163 | 4.52 / 138 | 4.27 / 256 | 4.14 / 91 | 4.33 / 104 | 11,697 | 4.39 / 571 | 100,520 |
| 6 | magicplan (id427424432) | Floor plan / estimating (pro) | Technologies magicplan Inc. | 4.66 / 41,136 | 4.64 / 7,542 | 4.58 / 14,719 | 4.53 / 9,672 | 4.63 / 4,233 | 4.64 / 6,726 | 4.5 / 2,545 | 4.69 / 993 | 46,430 | 4.73 / 656 | 87,566 |
| 7 | Polycam (id1532482376) | 3D scan (LiDAR+photogrammetry+splat), floor plans | Polycam Inc. | 4.65 / 43,579 | 4.64 / 8,453 | 4.52 / 8,254 | 4.61 / 4,508 | 4.64 / 4,343 | 4.62 / 2,773 | 4.58 / 1,834 | 4.69 / 2,499 | 32,664 | 4.78 / 2,045 | 76,243 |
| 8 | Shapr3D (id1091675654) | CAD (RoomPlan/LiDAR import) | Shapr 3D Zartkoruen Mukodo R… (Hungarian Zrt. form) | 4.74 / 34,082 | 4.68 / 6,481 | 4.68 / 13,883 | 4.68 / 4,835 | 4.7 / 6,268 | 4.64 / 3,967 | 4.58 / 1,622 | 4.79 / 1,316 | 38,372 | 4.88 / 1,583 | 72,454 |
| 9 | Planner 5D (id606173978) | Home design | Planner5D, UAB | 4.36 / 41,374 | 4.15 / 5,035 | 4.11 / 4,627 | 4.36 / 4,456 | 4.36 / 5,084 | 4.36 / 3,892 | 4.14 / 1,056 | 4.31 / 1,536 | 25,686 | 4.69 / 9,044 | 67,060 |
| 10 | Tape Measure (AI Photo Editor Lab) (id1437807477) | AR measure | AI Photo Editor Lab SRL | 4.58 / 45,286 | 4.54 / 3,589 | 4.42 / 129 | 4.64 / 50 | 4.58 / 78 | 4.43 / 46 | 4.54 / 52 | 4.19 / 26 | 3,970 | 4.76 / 112 | 49,256 |
| 11 | Ruler (Tue Nguyen Minh) (id623207505) | AR/on-screen ruler | Tue Nguyen Minh | 4.33 / 35,101 | 4.29 / 2,883 | 4.23 / 634 | 4.14 / 415 | 4.28 / 803 | 4.25 / 324 | 4.12 / 89 | 4.11 / 134 | 5,282 | 4.45 / 346 | 40,383 |
| 12 | CamToPlan (id1292176208) | AR tape measure / plan | Tasmanic Editions | 4.67 / 16,608 | 4.54 / 2,140 | 4.47 / 2,703 | 4.49 / 6,026 | 4.55 / 1,874 | 4.56 / 2,153 | 4.4 / 626 | 4.59 / 483 | 16,005 | 4.6 / 2,484 | 32,613 |
| 13 | 3d Scanner App (id1419913995) | 3D scan (LiDAR/TrueDepth/Object Capture) | AI Photo Editor Lab SRL | 4.47 / 16,090 | 4.45 / 2,294 | 4.32 / 3,475 | 4.43 / 1,857 | 4.47 / 2,520 | 4.43 / 1,390 | 4.32 / 529 | 4.52 / 635 | 12,700 | 4.57 / 436 | 28,790 |
| 14 | CamToPlan PRO (paid) (id1300697619) | AR measure / plan | Tasmanic Editions | 4.59 / 12,002 | 4.53 / 2,942 | 4.51 / 4,328 | 4.41 / 4,159 | 4.47 / 1,820 | 4.45 / 1,878 | 4.29 / 930 | 4.65 / 569 | 16,626 | 4.57 / 599 | 28,628 |
| 15 | Scaniverse (id1541433223) | 3D scan / Gaussian splat | Niantic Spatial, Inc. | 4.79 / 11,745 | 4.76 / 2,367 | 4.72 / 3,327 | 4.75 / 1,844 | 4.77 / 1,526 | 4.77 / 947 | 4.68 / 732 | 4.86 / 745 | 11,488 | 4.88 / 121 | 23,233 |
| 16 | Nomad Sculpt (id1519508653) | 3D sculpting (3D print) | Hexanomad | 4.82 / 14,162 | 4.83 / 2,075 | 4.77 / 1,433 | 4.86 / 1,271 | 4.79 / 1,124 | 4.84 / 1,004 | 4.82 / 411 | 4.86 / 508 | 7,826 | 4.88 / 485 | 21,988 |
| 17 | MeThreeSixty (id1472541261) | 3D body scan | Size Stream LLC | 4.75 / 18,419 | 4.66 / 2,012 | 4.39 / 62 | 4.36 / 47 | 4.63 / 27 | 4.46 / 41 | 4.91 / 54 | 4.38 / 16 | 2,259 | 4.8 / 5 | 20,678 |
| 18 | JigSpace (id1111193492) | AR presentations | JigSpace Inc. | 4.81 / 8,447 | 4.78 / 1,134 | 4.77 / 1,337 | 4.67 / 300 | 4.73 / 722 | 4.72 / 502 | 4.63 / 148 | 4.8 / 146 | 4,289 | 4.85 / 295 | 12,736 |
| 19 | ArcSite (id986274256) | CAD floor plans + AR room scan | Arctuition LLC | 4.72 / 9,086 | 4.61 / 974 | 4.14 / 255 | 4.46 / 191 | 4.44 / 196 | 4.47 / 294 | 4.57 / 72 | 4.48 / 29 | 2,011 | 4.91 / 46 | 11,097 |
| 20 | RoomScan Classic (id673673795) | Floor plan (touch) | Locometric Ltd | 4.29 / 4,956 | 4.29 / 1,685 | 4.16 / 1,340 | 4.3 / 552 | 4.27 / 322 | 4.37 / 491 | 4.06 / 93 | 4.66 / 56 | 4,539 | 4.31 / 51 | 9,495 |
| 21 | Homestyler (id601137449) | Home design + AR | Homestyler (Shanghai) Technology Co., Ltd. | 4.42 / 5,562 | 4.34 / 612 | 4.02 / 233 | 4.31 / 902 | 4.23 / 780 | 4.32 / 796 | 4.2 / 84 | 4.08 / 124 | 3,531 | 4.73 / 176 | 9,093 |
| 22 | ZOZOFIT (id1636398776) | 3D body scan (suit) | ZOZO Apparel USA, Inc. | 4.74 / 7,752 | absent | absent | absent | absent | absent | absent | absent | 0 | absent | 7,752 |
| 23 | CamToPlan 3D Scanner & LiDAR (id1547594886) | LiDAR 3D scan | Tasmanic Editions | 4.65 / 2,776 | 4.54 / 513 | 4.43 / 752 | 4.49 / 1,286 | 4.6 / 891 | 4.55 / 479 | 4.46 / 196 | 4.67 / 293 | 4,410 | 4.68 / 293 | 7,186 |
| 24 | Matterport (id701086043) | Digital twin / virtual tour | Matterport Inc | 4.72 / 4,153 | 4.62 / 508 | 4.43 / 318 | 4.66 / 584 | 4.36 / 248 | 4.67 / 286 | 4.47 / 68 | 4.8 / 40 | 2,052 | 4.06 / 16 | 6,205 |
| 25 | CamPlan (id6444421373) | Floor plan + AI design | CamPlan AI Ltd | 4.7 / 2,355 | 4.56 / 155 | 4.46 / 133 | 4.58 / 337 | 4.52 / 65 | 4.69 / 608 | 4.48 / 108 | 4.55 / 73 | 1,479 | 4.86 / 607 | 3,834 |
| 26 | Qlone (id1229460906) | Object 3D scan (mat/cloud) | EyeCue Vision Technologies LTD | 3.9 / 1,584 | 3.91 / 347 | 3.67 / 485 | 3.71 / 381 | 3.99 / 288 | 3.72 / 162 | 3.84 / 122 | 3.8 / 66 | 1,851 | 4.61 / 57 | 3,435 |
| 27 | Luma 3D Capture (id1615849914) | NeRF / splat capture (legacy) | Luma AI, Inc. | 4.51 / 1,849 | 4.46 / 285 | 4.41 / 367 | 4.43 / 249 | 4.37 / 153 | 4.55 / 285 | 4.47 / 90 | 4.54 / 95 | 1,524 | 4.7 / 322 | 3,373 |
| 28 | RoomScan Pro LiDAR (id1504050801) | Floor plan (LiDAR/RoomPlan) | Locometric Ltd | 4.27 / 2,115 | 4.01 / 327 | 3.83 / 280 | 4.22 / 199 | 4.16 / 221 | 4.18 / 108 | 3.98 / 54 | 4.39 / 38 | 1,227 | 4.55 / 20 | 3,342 |
| 29 | Tripo AI (id6748596826) | AI image-to-3D | HOLYMOLLY LIMITED | 4.63 / 2,357 | 4.63 / 189 | 4.6 / 156 | 4.63 / 152 | 4.63 / 75 | 4.64 / 176 | 4.72 / 36 | 4.8 / 30 | 814 | 4.8 / 161 | 3,171 |
| 30 | MagiScan (id1617601717) | AI 3D scan (3D print/NVIDIA Omniverse) | Magiscan Inc. | 4.47 / 1,415 | 4.46 / 183 | 4.39 / 625 | 4.42 / 379 | 4.53 / 230 | 4.53 / 127 | 4.18 / 57 | 4.54 / 110 | 1,711 | 4.56 / 48 | 3,126 |
| 31 | Apple Measure (id1383426740) | AR measure (preinstalled) | Apple Inc. | 3.06 / 1,805 | 2.99 / 312 | 3.42 / 329 | 3.69 / 197 | 3.09 / 170 | 3.31 / 98 | 3.29 / 75 | 3.28 / 79 | 1,260 | 3.17 / 250 | 3,065 |
| 32 | KIRI Engine (id1577127142) | Photogrammetry / splat / LiDAR | KIRI Innovation (Hongkong) Limited | 4.42 / 1,232 | 4.45 / 256 | 4.31 / 185 | 4.3 / 161 | 4.67 / 84 | 4.36 / 132 | 4.51 / 69 | 4.39 / 69 | 956 | 4.81 / 32 | 2,188 |
| 33 | AR Code Object Capture (id1488198492) | Object Capture / AR QR | AR Code Pte. Ltd. | 4.49 / 1,090 | 4.39 / 206 | 4.32 / 170 | 4.44 / 361 | 4.53 / 122 | 4.29 / 97 | 4.5 / 42 | 4.53 / 43 | 1,041 | 4.54 / 28 | 2,131 |
| 34 | AR Plan (Grymala) (id1459846158) | AR measure / plan | Grymala sp. z o.o. | 4.37 / 1,392 | 4.31 / 58 | 3.94 / 145 | absent | 4.44 / 50 | 4.28 / 72 | 4.36 / 11 | absent | 336 | 4.66 / 128 | 1,728 |
| 35 | SiteScape (FARO) (id1524700432) | LiDAR AEC scan | FARO Technologies Inc. | 4.65 / 938 | 4.4 / 155 | 4.28 / 179 | 4.46 / 104 | 4.65 / 153 | 4.74 / 61 | 4.4 / 45 | 4.69 / 35 | 732 | 5 / 11 | 1,670 |
| 36 | Abound (ex-Metascan) (id1472387724) | 3D scan | Abound Labs Inc. | 4.54 / 856 | 4.57 / 225 | 4.36 / 139 | 4.41 / 140 | 4.59 / 156 | 4.58 / 52 | 4.73 / 48 | 4.36 / 42 | 802 | 5 / 9 | 1,658 |
| 37 | AR Ruler (Grymala) (id1326773975) | AR measure | Grymala sp. z o.o. | 4.65 / 973 | 4.33 / 54 | 3.85 / 78 | 4.14 / 74 | 4.41 / 49 | 4.53 / 43 | 4.09 / 11 | 4.56 / 16 | 325 | 4.6 / 533 | 1,298 |
| 38 | Twindo (ex-Canvas, Occipital) (id1169235377) | Scan-to-CAD service | Occipital, Inc. | 4.76 / 1,102 | 4.22 / 36 | 4 / 10 | 4.14 / 21 | 2.8 / 5 | 4 / 13 | 3.67 / 6 | 3.67 / 3 | 94 | 1 / 1 | 1,196 |
| 39 | Metaroom (id1637077163) | LiDAR room scan -> BIM | Synthetic Dimension GmbH | 4.46 / 80 | 4.48 / 87 | 4.58 / 547 | 4.4 / 15 | 4.52 / 21 | 4.41 / 22 | 4.47 / 19 | 4.85 / 27 | 738 | 5 / 1 | 818 |
| 40 | RealityScan Mobile (Epic) (id1584832280) | Photogrammetry | Epic Games International, S.a.r.l. | 3.76 / 332 | 3.66 / 86 | 3.92 / 76 | 4.43 / 65 | 3.66 / 41 | 4.51 / 45 | 4.21 / 28 | 3.89 / 46 | 387 | 4.89 / 9 | 719 |
| 41 | Heges (id1382310112) | Face/body scan (TrueDepth/LiDAR) | Marek Simonik | 2.82 / 303 | 2.95 / 57 | 3.1 / 193 | 2.7 / 43 | 2.75 / 40 | 3.29 / 21 | 2.48 / 27 | 2.18 / 28 | 409 | 3 / 6 | 712 |
| 42 | PIX4Dcatch (id1511483044) | LiDAR/photogrammetry survey | Pix4D SA | 4.65 / 263 | 4.72 / 32 | 4.32 / 115 | 4.71 / 38 | 4.38 / 29 | 4.65 / 37 | 4.61 / 18 | 4.73 / 15 | 284 | 2.67 / 3 | 547 |
| 43 | Recon-3D (id1594797748) | LiDAR+photogrammetry (insurance/forensics) | Recon-3D Inc. | 4.85 / 277 | 4.91 / 11 | 4.31 / 13 | 3 / 1 | 3.6 / 5 | 4.5 / 2 | 1 / 1 | 5 / 1 | 34 | 0 | 311 |
| 44 | Moasure (id1561726410) | Motion-sensor measure (hardware companion) | 3D technologies Ltd | 4.03 / 126 | 4.7 / 27 | 4.04 / 26 | 4.47 / 15 | 4.75 / 16 | 4.89 / 9 | 3.67 / 3 | 5 / 2 | 98 | 5 / 1 | 224 |
| 45 | Dot3D (DotProduct) (id1641016966) | LiDAR AEC scan | DotProduct LLC | 4.67 / 99 | 4.7 / 20 | 4.51 / 41 | 4 / 12 | 4.18 / 11 | 4.44 / 9 | 4.77 / 13 | 4.27 / 11 | 117 | 0 | 216 |
| 46 | Record3D (id1477716895) | RGBD video (LiDAR/TrueDepth) | Marek Simonik | 4.22 / 64 | 4.65 / 17 | 4.33 / 18 | 4.36 / 11 | 5 / 2 | 4.2 / 5 | 3.67 / 3 | 2.88 / 8 | 64 | 0 | 128 |
| 47 | CapCam (id6737015770) | 3D scan / splat / LiDAR | Tuyou Computing (Shanghai) Information Technology Co., Ltd | 4.97 / 32 | 5 / 1 | 3.67 / 3 | 4.86 / 7 | 4 / 1 | 5 / 3 | 0 | 5 / 1 | 16 | 5 / 1 | 48 |

(EU-7 = GB+DE+FR+IT+ES+NL+PL. "absent" = the app is not available in that storefront. Example listing URLs: Polycam https://apps.apple.com/us/app/id1532482376 ; magicplan https://apps.apple.com/us/app/id427424432 ; Scaniverse https://apps.apple.com/us/app/id1541433223 ; 3d Scanner App https://apps.apple.com/us/app/id1419913995 ; KIRI https://apps.apple.com/us/app/id1577127142.)

**B. Chart ranks on 2026-09-27 (category top-100; any app not listed was not in the top 100 of the 8 categories checked in US/GB/DE/FR/VN).** Source: `https://itunes.apple.com/{us|gb|de|fr|vn}/rss/{topfreeapplications|topgrossingapplications}/limit=200/genre={6002,6008,6007,6012,6027,6000,6024,6013}/json`
| App | US | GB | DE | FR | VN |
|---|---|---|---|---|---|
| Polycam (Photo & Video) | grossing #89 | grossing #58 | free #82; grossing #53 | free #77; grossing #42 | – |
| magicplan (Productivity) | – | – | grossing #49 | grossing #64 | – |
| MagiScan (Graphics & Design) | – | free #89 | free #53; grossing #72 | free #52; grossing #91 | – |
| CamToPlan (Utilities) | – | – | – | grossing #86 | – |
| CamPlan (Graphics & Design) | – | – | grossing #69 | – | free #88 |
| Nomad Sculpt (Graphics & Design) | – | – | grossing #64 | – | grossing #53 |
| Tape Measure, Level Labs (Utilities) | grossing #63 | – | – | – | – |
| Planner 5D (Lifestyle) | grossing #48 | grossing #43 | free #83; grossing #17 | free #82; grossing #33 | free #91; grossing #21 |
| Home Planner AI / Room Planner (Lifestyle) | grossing #89 | grossing #84 | free #73; grossing #33 | free #85; grossing #46 | grossing #40 |
| IKEA (Shopping) | free #56 | free #18 | free #9 | free #15 | not in VN store |
- Not in any top-100 checked: Scaniverse, 3d Scanner App, KIRI Engine, Luma (both apps), RoomScan Pro, SiteScape, Dot3D, Metaroom, Shapr3D, JigSpace, Matterport, Apple Measure, AR Ruler/AR Plan, Houzz, Qlone, RealityScan — same RSS source as above.

**C. Pricing (IAP list prices as shown on the App Store on 2026-09-27; US / UK / DE). Several price points per tier usually mean intro, legacy or A/B offers.**
| App | Model | US (USD) | UK (GBP) | DE (EUR) | Source |
|---|---|---|---|---|---|
| Polycam | Subscription (B2C + B2B) | Basic $29.99/mo, $149.99/yr; Pro $26.99/mo, $199.99/yr. Web: Business $400/user/yr; Enterprise $1,200/user/yr (min 3 users) | Basic £29.99, £149.99/yr; Pro £22.99/mo, £149.99/yr | Basic €34.99, €179.99/yr; Pro €26.99/mo, €199.99/yr | [US](https://apps.apple.com/us/app/id1532482376), [GB](https://apps.apple.com/gb/app/id1532482376), [DE](https://apps.apple.com/de/app/id1532482376), [poly.cam/pricing](https://poly.cam/pricing) |
| magicplan | B2B subscription, 3 tiers | Sketch $12.99/mo, $129.99/yr; Report $39.99/mo, $399.99/yr; Estimate $89.99/mo, $899.99/yr | same figures in £ | same figures in € | [US](https://apps.apple.com/us/app/id427424432), [GB](https://apps.apple.com/gb/app/id427424432), [DE](https://apps.apple.com/de/app/id427424432) |
| KIRI Engine | Freemium + Pro subscription | Pro $9.99–$17.99/mo; $29.99–$49.99/yr | £8.99–£17.99/mo; £29.99–£49.99/yr | €10.49–€19.99/mo; €34.99–€50.99/yr | [US](https://apps.apple.com/us/app/id1577127142), [GB](https://apps.apple.com/gb/app/id1577127142), [DE](https://apps.apple.com/de/app/id1577127142) |
| 3d Scanner App | Weekly/yearly subscription | $2.99–$4.99/wk; $29.99–$69.99/yr | £2.99–£4.99/wk; £29.99–£69.99/yr | €2.99–€5.99/wk; €34.99–€79.99/yr | [US](https://apps.apple.com/us/app/id1419913995), [GB](https://apps.apple.com/gb/app/id1419913995), [DE](https://apps.apple.com/de/app/id1419913995) |
| Scaniverse | Free on the App Store (no IAP listed); paid cloud plans sold outside the store | Free | Free | Free | [US](https://apps.apple.com/us/app/id1541433223) |
| Luma 3D Capture | Free, no IAP | Free | – | – | [US](https://apps.apple.com/us/app/id1615849914) |
| Luma Dream Machine (the video-generation successor) | Subscription + credits | Lite $9.99/mo ($95.99/yr); Plus $29.99 ($289.99/yr); Unlimited $94.99 ($919.99/yr); credits $4 | n/a | n/a | [US](https://apps.apple.com/us/app/id6478852867) |
| RoomScan Pro LiDAR | Subscription | $9.99/mo; $119.99/yr | £9.99/mo; £119.99/yr | €9.99–€11.99/mo; €119.99/yr | [US](https://apps.apple.com/us/app/id1504050801), [GB](https://apps.apple.com/gb/app/id1504050801), [DE](https://apps.apple.com/de/app/id1504050801) |
| CamToPlan (AR tape) | Premium IAP / full version | $4.99 / $29.99; Full $49.99 | £4.99 / £29.99; Full £44.99 | €4.99 / €29.99; Full €49.99 | [US](https://apps.apple.com/us/app/id1292176208), [GB](https://apps.apple.com/gb/app/id1292176208), [DE](https://apps.apple.com/de/app/id1292176208) |
| CamToPlan PRO | Paid upfront | $39.99 | n/a | n/a | [US](https://apps.apple.com/us/app/id1300697619) |
| CamToPlan 3D Scanner & LiDAR | One IAP | $49.99 | £44.99 | €49.99 | [US](https://apps.apple.com/us/app/id1547594886) |
| AR Ruler (Grymala) | Weekly/monthly/annual subscription | $4.99–$12.99/wk; $19.99/mo; $44.99–$89.99/yr | £12.99/wk; £13/mo; £28–£57/yr; remove ads £7.99 | €14.99/wk; €13/mo; €29–€59/yr | [US](https://apps.apple.com/us/app/id1326773975), [GB](https://apps.apple.com/gb/app/id1326773975), [DE](https://apps.apple.com/de/app/id1326773975) |
| AR Plan (Grymala) | Subscription | $4.99–$12.99/wk; $19.99/mo; $49.99/3 mo; $44.99–$89.99/yr | n/a | n/a | [US](https://apps.apple.com/us/app/id1459846158) |
| Tape Measure (Level Labs) | "Pro" IAP | $9.99–$49.99 | n/a | n/a | [US](https://apps.apple.com/us/app/id1271546805) |
| Tape Measure (AI Photo Editor Lab) | Weekly/yearly subscription | $2.99–$4.99/wk; $29.99/yr | n/a | n/a | [US](https://apps.apple.com/us/app/id1437807477) |
| Ruler (Tue Nguyen Minh) | Low-price IAP | $1.99 (Pro or weekly) | n/a | n/a | [US](https://apps.apple.com/us/app/id623207505) |
| Apple Measure | Free, preinstalled | Free | Free | Free | [US](https://apps.apple.com/us/app/id1383426740) |
| Moasure | Free app, no subscription (needs Moasure hardware) | Free | Free | Free | [US](https://apps.apple.com/us/app/id1561726410) |
| SiteScape (FARO) | Pro subscription | $49.99/mo; $499/yr | £44.99/mo; £499/yr | €52.99/mo; €599/yr | [US](https://apps.apple.com/us/app/id1524700432), [GB](https://apps.apple.com/gb/app/id1524700432), [DE](https://apps.apple.com/de/app/id1524700432) |
| Dot3D | Pro subscription | $49.99/mo; $349.99/yr | £49.99/mo; £349.99/yr | €49.99/mo; €399.99/yr | [US](https://apps.apple.com/us/app/id1641016966), [GB](https://apps.apple.com/gb/app/id1641016966), [DE](https://apps.apple.com/de/app/id1641016966) |
| Shapr3D | Subscription, 3 tiers | Solo $32.99/mo, $249.99/yr; Pro $37.99, $299.99; Business $59.99, $499.99 | Solo £29.99, £249.99; Pro £39.99, £299.99; Business £53.99, £449.99 | Solo €39.99, €299.99; Pro €45.99, €349.99; Business €59.99, €499.99 | [US](https://apps.apple.com/us/app/id1091675654), [GB](https://apps.apple.com/gb/app/id1091675654), [DE](https://apps.apple.com/de/app/id1091675654) |
| Planner 5D | Subscription | $7.99/wk; $19.99/mo; $29.99–$119.99/yr; the description says "$9.99/month or $59.99/year (prices may vary)" | £7.99/wk; £19.99/mo; £29.99–£119.99/yr | €8.99/wk; €22.99/mo; €29.99–€119.99/yr | [US](https://apps.apple.com/us/app/id606173978), [GB](https://apps.apple.com/gb/app/id606173978), [DE](https://apps.apple.com/de/app/id606173978) |
| Home Planner AI (Room Planner) | IAP + subscription | $5.99–$74.99 (e.g. 6 months $29.99–$34.99; weekly business $17.99) | n/a | n/a | [US](https://apps.apple.com/us/app/id1076159017) |
| Home Design 3D | Subscription | $4.99/wk; $12.99–$22.99/mo; $44.99–$79.99/yr | n/a | n/a | [US](https://apps.apple.com/us/app/id463768717) |
| Homestyler | Subscription + AI credits | $2.99/wk; $9.99/mo; $69.99/yr; AI membership $19.99/mo | n/a | n/a | [US](https://apps.apple.com/us/app/id601137449) |
| Abound (formerly Metascan?) | Pro subscription | $14.99 / $79.99 | £14.99 / £79.99 | €17.99 / €89.99 | [US](https://apps.apple.com/us/app/id1472387724), [GB](https://apps.apple.com/gb/app/id1472387724), [DE](https://apps.apple.com/de/app/id1472387724) |
| MagiScan | Subscription + lifetime + scan packs | $5.49/wk; $13.49/mo; $78.90/yr; lifetime $209.99; packs $2.49–$149.99 | £4.99/wk; £12.99/mo; £79.90/yr | €5.99/wk; €14.99/mo; €89.90/yr; lifetime €229.99 | [US](https://apps.apple.com/us/app/id1617601717), [GB](https://apps.apple.com/gb/app/id1617601717), [DE](https://apps.apple.com/de/app/id1617601717) |
| Qlone | Premium IAP + cloud credits | $11.99–$29.99; 100 cloud credits $9.99; EDU edition $29.99 paid | n/a | n/a | [US](https://apps.apple.com/us/app/id1229460906) |
| Heges | One-time IAP | 3D Scanner $7.99 | n/a | n/a | [US](https://apps.apple.com/us/app/id1382310112) |
| Record3D | One-time IAP | $2.99–$4.99 | n/a | n/a | [US](https://apps.apple.com/us/app/id1477716895) |
| PIX4Dcatch | Pro IAP | Professional $159 | n/a | n/a | [US](https://apps.apple.com/us/app/id1511483044) |
| Recon-3D | B2B subscription + upload packs | $99.99/mo; $299.99–$599.99/yr; 5 uploads $49.99, 10 uploads $79.99 | n/a | n/a | [US](https://apps.apple.com/us/app/id1594797748) |
| ArcSite | B2B subscription | Draw Basic $14.99; Draw Pro $34.99; Advanced/Takeoff $119.99; Estimate $159.99 | n/a | n/a | [US](https://apps.apple.com/us/app/id986274256) |
| CamPlan | Subscription | PLUS $7.99–$14.99; PRO $19.99–$24.99 | n/a | n/a | [US](https://apps.apple.com/us/app/id6444421373) |
| Twindo (formerly Canvas) | Membership + pay-per-model service | Essentials $29.00; 2D drawings from $0.18/sq ft; 3D models from $0.26/sq ft | n/a | n/a | [US](https://apps.apple.com/us/app/id1169235377) |
| AR Code Object Capture | Subscription | $34.99/mo | n/a | n/a | [US](https://apps.apple.com/us/app/id1488198492) |
| CapCam (splat) | Subscription | $9.99; $19.99/mo; $59.99/yr | n/a | n/a | [US](https://apps.apple.com/us/app/id6737015770) |
| Nomad Sculpt | Paid upfront + IAP | $19.99 + Quad Remesher $15.99 | n/a | n/a | [US](https://apps.apple.com/us/app/id1519508653) |
| Tripo AI (image-to-3D) | Subscription | Pro $15.99; Advanced $38.99; Ultimate $89.99 | n/a | n/a | [US](https://apps.apple.com/us/app/id6748596826) |
| MeThreeSixty (body) | Subscription | $1.99–$4.99/mo; $19.99–$39.99/yr | n/a | n/a | [US](https://apps.apple.com/us/app/id1472541261) |
| ZOZOFIT (body) | Subscription + lifetime | $2.99–$4.99/mo; $19.99–$29.99/yr; lifetime $99.99 | not in store | not in store | [US](https://apps.apple.com/us/app/id1636398776) |
| ARki (AR architecture) | Subscription | Personal $5–$29; Pro $19.49/mo, $219.99/yr | n/a | n/a | [US](https://apps.apple.com/us/app/id700695106) |

**D. Which features need LiDAR versus any iPhone, and where processing happens. Sources: each app's own App Store description (US) or website.**
| App | Needs LiDAR? | Works on any iPhone? | On-device vs cloud | Source |
|---|---|---|---|---|
| Polycam | LiDAR "space captures" only on LiDAR iOS devices | Yes: "3D scanner … that works without LiDAR"; photogrammetry and Gaussian splats from photos/video; also Android and web | Not stated on the pricing page (n/a) | [App Store](https://apps.apple.com/us/app/id1532482376), [pricing](https://poly.cam/pricing) |
| Scaniverse | No explicit requirement ("works with your mobile device's cameras and sensors") | Yes, iOS and Android | "Unlimited on-device Gaussian splat capture and processing" on the free tier; "cloud processing" for splats and meshes on paid plans | [App Store](https://apps.apple.com/us/app/id1541433223), [Niantic Spatial](https://www.nianticspatial.com/products/capture) |
| 3d Scanner App | LiDAR or TrueDepth; RoomPlan mode; Photo Mode uses Apple Object Capture | Partly (TrueDepth covers Face ID phones) | On-device ("Capture On Device"; on-device editor) | [App Store](https://apps.apple.com/us/app/id1419913995), [3dscannerapp.com](https://3dscannerapp.com/) |
| KIRI Engine | LiDAR scan mode only on LiDAR devices | Yes: "Precision Without LiDAR"; photo scan, NeRF-based featureless-object scan, 3DGS from video; also Android and web | The KIRI site lists 3DGS, Featureless Object Scan and Auto-Rigging as cloud-processed | [App Store](https://apps.apple.com/us/app/id1577127142), [kiriengine.app](https://www.kiriengine.app/) |
| Luma 3D Capture | "No Lidar … necessary"; AR capture needs iPhone 11 or newer | Yes | n/a | [App Store](https://apps.apple.com/us/app/id1615849914) |
| magicplan | Uses LiDAR where present (per site reviews: iPhone 14 Pro Max, iPad Pro) | Yes: "just the camera of your mobile device (no extra hardware required)" | n/a | [App Store](https://apps.apple.com/us/app/id427424432), [magicplan.app](https://www.magicplan.app/) |
| RoomScan Pro | Apple RoomPlan + "Brick Mode" need LiDAR | "Touch Mode … works in dim light on any device"; also Bosch/Leica Bluetooth lasers | n/a | [App Store](https://apps.apple.com/us/app/id1504050801) |
| CamToPlan 3D Scanner & LiDAR | LiDAR scanner app | – | "All calculations are done securely on your device, no internet connection is required" | [App Store](https://apps.apple.com/us/app/id1547594886) |
| Apple Measure | Extra features "on the iPhone 12 Pro and iPhone 12 Pro Max (and later)"; LiDAR enables person-height measurement | Basic AR measuring on any supported iPhone | On-device (preinstalled) | [App Store](https://apps.apple.com/us/app/id1383426740), [Wikipedia iPhone 12 Pro](https://en.wikipedia.org/wiki/IPhone_12_Pro) |
| Abound (formerly Metascan?) | LiDAR room scanning | Photo capture on any device | "LiDAR scans are processed on your device, with no Internet required"; "Photos are deleted immediately after processing on our servers" (so photo scans are cloud-processed) | [App Store](https://apps.apple.com/us/app/id1472387724) |
| Qlone | No | Yes (scan on a printed mat) | Scanning without the mat "takes place on our Qlone Cloud" (credits) | [App Store](https://apps.apple.com/us/app/id1229460906) |
| Heges | TrueDepth (Face ID) and/or LiDAR; says TrueDepth is more accurate (0.5 mm setting) and LiDAR suits rooms, not small objects | Any Face ID iPhone | On-device, with a Wi-Fi server for transfer | [App Store](https://apps.apple.com/us/app/id1382310112) |
| SiteScape (FARO) | **Required** ("requires the new LiDAR sensor … iPhone 12/13/14 Pro …") | No | n/a | [App Store](https://apps.apple.com/us/app/id1524700432) |
| Dot3D | **Required** for scanning (iPhone Pro/Pro Max 12+, iPad Pro 2020+) | Viewing only | "No cloud uploads required (all processing happens locally on-device)" | [App Store](https://apps.apple.com/us/app/id1641016966) |
| Metaroom | **Required** (iPhone 12 Pro+, iPad Pro 2020+) | No | Capture in the app; "GDPR-compliant cloud storage on AWS"; exports via the Metaroom Workspace subscription | [App Store](https://apps.apple.com/us/app/id1637077163) |
| CamPlan | "LiDAR-based capture" | Design tools on any device | n/a | [App Store](https://apps.apple.com/us/app/id6444421373) |
| MagiScan | Point-cloud mode needs LiDAR (iPhone 12 Pro+) | AI photo scan on any device | Point cloud: "on-device processing"; photo scans upload when connected (implies cloud) | [App Store](https://apps.apple.com/us/app/id1617601717) |
| Recon-3D | Fuses photogrammetry + LiDAR (iPhone/iPad Pro) | No | "Processed on the cloud or … directly on the device only" | [App Store](https://apps.apple.com/us/app/id1594797748) |
| AR Code Object Capture | "Uses LiDAR when available" | Yes | "Otherwise processes via cloud photogrammetry"; Gaussian "AR Splat" | [App Store](https://apps.apple.com/us/app/id1488198492) |
| RealityScan Mobile (Epic) | No ("No special hardware") | Any iPhone/iPad on iOS 16+ | Uploads to Sketchfab; processing location n/a | [App Store](https://apps.apple.com/us/app/id1584832280) |
| Record3D | Face ID camera or LiDAR | Face ID phones | On-device (RGBD video; Wi-Fi streaming) | [App Store](https://apps.apple.com/us/app/id1477716895) |
| Splatcatcher (new, 2026) | **Required** (iPhone 12 Pro+) | No | Capture on the phone; splat training "generally requires a CUDA-capable PC" | [App Store](https://apps.apple.com/us/app/id6759800588) |
| Moasure | No (motion-based hardware sensor) | Yes (Bluetooth companion app) | Works "without the need for Wi-Fi, GPS, or cell phone signal" | [App Store](https://apps.apple.com/us/app/id1561726410), [moasure.com](https://www.moasure.com/) |
| Houzz | No ("View in My Room 3D" uses the camera) | Yes | n/a | [App Store](https://apps.apple.com/us/app/id399563465) |
| Twindo (formerly Canvas) | Scan, plan or point-cloud upload | – | Paid as-built models are ordered as a service ($/sq ft), i.e. processed off-device | [App Store](https://apps.apple.com/us/app/id1169235377) |
| Apple RoomPlan API (used by 3d Scanner App, RoomScan Pro, many floor-plan apps) | **Required**: "utilizes the camera and LiDAR Scanner on iPhone and iPad"; outputs USD/USDZ | No | Real-time on-device (implied, not stated verbatim) | [Apple RoomPlan](https://developer.apple.com/augmented-reality/roomplan/) |
| Apple Object Capture on iOS | "Available on iPhone 12 Pro, iPad Pro 2021, and the later models"; LiDAR used for low-texture objects | No | "On-device model reconstruction" (reduced detail on iOS; higher detail via Mac) | [WWDC23 10191](https://developer.apple.com/videos/play/wwdc2023/10191/) |

**E. Company-disclosed usage figures (disclosures, not estimates)**
- Polycam, App Store description (2026): "34 million scans. More than 10 million people. Over 2 billion square feet captured." — [App Store](https://apps.apple.com/us/app/id1532482376)
- Polycam, Feb 2024: 10M+ app downloads (iOS + Android) and nearly 100,000 paying customers — [TechCrunch 2024-02-07](https://techcrunch.com/2024/02/07/3d-scanning-app-polycam-gets-backing-from-youtube-co-founder/)
- 3d Scanner App: "downloaded by 11+ Million users" — [App Store](https://apps.apple.com/us/app/id1419913995)
- JigSpace: "more than 5M downloads"; "Featured in Apple's iPhone 12 launch keynote" — [App Store](https://apps.apple.com/us/app/id1111193492)
- Home Design 3D: "trusted by over 60 million users in more than 150 countries" — [App Store](https://apps.apple.com/us/app/id463768717)
- Houzz: 25M+ photos, 5M+ products, 3M+ home professionals — [App Store](https://apps.apple.com/us/app/id399563465)
- magicplan website: "4.7 stars from 290K+ ratings" (cross-platform); other counters on the page showed placeholders ("+0k") — [magicplan.app](https://www.magicplan.app/)
- Metaroom: "100K+ scans and exports already completed" — [App Store](https://apps.apple.com/us/app/id1637077163)
- Moasure: "100,000+ units sold" (hardware) — [moasure.com](https://www.moasure.com/)
- Matterport (now part of CoStar): 2024 revenue US$169.7M (+8%) and 1.2M subscribers — [Wikipedia: Matterport](https://en.wikipedia.org/wiki/Matterport)

### Inferences
- Polycam is very likely the highest-grossing pure 3D-scanning app on iOS in the US, UK, DE and FR. It is the only scanning app in any top-grossing top-100, and its FR/DE ranks (#42/#53) beat its US rank (#89). Europe therefore looks relatively strong for Polycam's store revenue. (Chart-based inference, not a revenue figure.)
- magicplan ranks in top-grossing only in DE and FR, not in the US or UK. Its DE rating count (14.7K) is also a much larger share of its US count (41.1K) than for most apps. Both point to Europe, and especially DACH and France, as an over-indexed revenue market for magicplan on iOS.
- Rating counts suggest the "Big 3" consumer scanners are Polycam, 3d Scanner App and Scaniverse. KIRI Engine has few iOS ratings (1.2K US) despite its web and Android presence, so its iOS scale is probably modest or skewed toward other platforms. No KIRI download figure was found.
- Generic AR-measure utilities (Level Labs Tape Measure, AI Photo Editor Lab Tape Measure, Ruler) have large rating counts. Only Level Labs appears in a top-grossing chart (US Utilities #63), so the big AR-measure audience monetizes weakly apart from a few aggressive weekly-subscription apps.
- Apple Measure's low rating (3.06, 1.8K ratings US) reflects that it ships preinstalled. Its rating count is not a usage proxy.

### Gaps
- Sensor Tower, Appfigures, AppMagic and data.ai download and revenue estimates for every app: **n/a**. The web-search budget was exhausted before this task started and the platforms are paywalled. The report writer should treat the rating counts and chart ranks above as the only quantitative popularity and revenue signals.
- Scandy Pro, Trnio, Widar, IKEA Place (id1279244498) and Snapchat LiDAR lenses: no app-level data. IKEA Place's ID returned no result from the US Lookup API on 2026-09-27 (see Q2).
- Google Play and Android data: not collected (iOS focus).

## Q2. State of the market 2025–2026: acquisitions, shutdowns, pivots, new entrants (Gaussian splats)

### Takeaway
The category has consolidated and pivoted toward B2B and "physical AI":
- Niantic sold its games to Scopely ($3.5B, closed May 29 2025) and spun Scaniverse into **Niantic Spatial** ($250M initial capitalization), which now sells cloud splat processing and VPS.
- Luma AI's 3D capture app is effectively in maintenance mode while the company focuses on video models (Ray 3.2, Dream Machine).
- Epic folded RealityCapture into **RealityScan 2.0** (June 2025).
- CoStar closed its **Matterport** acquisition (Feb 28 2025).
- Occipital renamed Canvas to **Twindo**.
- App Store sellers changed for 3d Scanner App (now "AI Photo Editor Lab SRL") and SiteScape (FARO).
- Polycam repositioned itself as a documentation tool for construction, insurance and real estate.
- New Gaussian-splat entrants appear every month but are tiny so far (fewer than 50 US ratings each).

### Cited Findings
- On Mar 12 2025 Niantic confirmed the sale of its games business to Scopely for $3.5B. It closed May 29 2025, and the geospatial business was spun off as Niantic Spatial Inc. — [Wikipedia: Niantic, Inc.](https://en.wikipedia.org/wiki/Niantic,_Inc.)
- Niantic Spatial was capitalized with $250M ($200M from Niantic's balance sheet plus a $50M Scopely investment). John Hanke is CEO. Snap made an undisclosed investment and a multi-year partnership to integrate Niantic Spatial scanning and VPS. Niantic Spatial offers Scaniverse on web and mobile for Gaussian splats, meshes and VPS maps, and added USDZ output in July 2026. Partners include ExxonMobil (pilot, July 2026) and Flexion/NVIDIA (robotics sim-to-real). — [Wikipedia: Niantic Spatial](https://en.wikipedia.org/wiki/Niantic_Spatial)
- The Scaniverse listing now describes "cloud processing" into Gaussian splats, NSDK 4.0 and VPS 2.0. The free tier has "limited cloud processing"; "paid plans unlock more processing, bigger teams, 360° camera scans, and enterprise support". The "classic" free experience keeps "unlimited on-device Gaussian splat capture and processing". Seller: Niantic Spatial, Inc. — [App Store](https://apps.apple.com/us/app/id1541433223)
- Luma 3D Capture was last updated 2026-01-14 (v1.3.14) and has no IAP. Luma's homepage now centers on "Ray 3.2" video generation, the "Uni-1" brand model and multimodal agents, with no mention of 3D capture. — [App Store](https://apps.apple.com/us/app/id1615849914), [lumalabs.ai](https://lumalabs.ai/)
- Luma Labs launched Dream Machine (text-to-video) in June 2024 and previously built "Genie, a 3D model generator". — [Wikipedia: Dream Machine](https://en.wikipedia.org/wiki/Dream_Machine_(text-to-video_model))
- Epic rebranded RealityCapture as RealityScan 2.0 in June 2025, unifying it with the RealityScan mobile app (released 2022). RealityScan 2.1 (Nov 2025) added SLAM scanner data. Since April 2024 it has been free for companies under US$1M revenue. — [Wikipedia: RealityCapture](https://en.wikipedia.org/wiki/RealityCapture)
- RealityScan Mobile has weak ratings: 3.76 from 332 ratings in the US, 3.92 from 76 in DE. — [App Store](https://apps.apple.com/us/app/id1584832280)
- Matterport: CoStar announced the acquisition in Apr 2024 (about US$1.6B) and completed it on Feb 28 2025. Matterport tours have been absent from Zillow since Oct 2025 amid a CoStar–Zillow dispute. — [Wikipedia: Matterport](https://en.wikipedia.org/wiki/Matterport)
- Occipital's app is now titled "Twindo (formerly Canvas)". It sells as-built models from $0.18/sq ft (2D) and $0.26/sq ft (3D). — [App Store](https://apps.apple.com/us/app/id1169235377)
- 3d Scanner App (id1419913995) lists "AI Photo Editor Lab SRL" as its App Store seller, yet 3dscannerapp.com still names Laan Labs (labs@laan.com). Laan Consulting Corp separately publishes a new app, "OpenPlan3D" (4 ratings, updated 2026-09-17). — [App Store](https://apps.apple.com/us/app/id1419913995), [3dscannerapp.com](https://3dscannerapp.com/), [OpenPlan3D](https://apps.apple.com/us/app/id6759076170)
- SiteScape's App Store seller is "FARO Technologies Inc." — [App Store](https://apps.apple.com/us/app/id1524700432)
- Polycam's App Store copy (2026) now leads with "floor plans, as-builts, estimates, roof reports, claims files". It adds drone and aerial capture, and its web pricing includes Business ($400/user/yr) and Enterprise ($1,200/user/yr) tiers. It claims to be "Trusted by half of the Fortune 500" (Zillow, Wayfair, CVS Health, Amazon, Adobe, Marriott). — [App Store](https://apps.apple.com/us/app/id1532482376), [poly.cam/pricing](https://poly.cam/pricing)
- 3D Gaussian splatting "exploded in popularity in 2023" after the Inria paper on real-time radiance-field rendering. — [Wikipedia: Gaussian splatting](https://en.wikipedia.org/wiki/Gaussian_splatting)
- New splat/LiDAR entrants on the US App Store (release date; US ratings as of 2026-09-27; source: iTunes Search API / App Store):
  - CapCam (Tuyou Computing, Shanghai; Dec 2024; 32) [link](https://apps.apple.com/us/app/id6737015770)
  - Teleport by Varjo (Jun 2024; 5) [link](https://apps.apple.com/us/app/id6450445339)
  - Gaussian SplatKing (Mar 2026; 12) [link](https://apps.apple.com/us/app/id6759175085)
  - Splatcatcher (Warpgate LLC; Mar 2026; 4) [link](https://apps.apple.com/us/app/id6759800588)
  - Aholo 3D Capture (Hangzhou Meijian; Mar 2026; 1) [link](https://apps.apple.com/us/app/id6760284620)
  - Splatcam (Jun 2026; 0) [link](https://apps.apple.com/us/app/id6758737104)
  - LuxBox (Tuyou; Jan 2026; 5) [link](https://apps.apple.com/us/app/id6754314326)
- AI image-to-3D is emerging next to scanning. Tripo AI (HOLYMOLLY LIMITED) launched Aug 2025 and has 2,357 US ratings; Abound added an "AI Mode" that turns a photo or text prompt into a 3D model. — [Tripo](https://apps.apple.com/us/app/id6748596826), [Abound](https://apps.apple.com/us/app/id1472387724)
- IKEA Place (id1279244498) returned no result from the US Lookup API on 2026-09-27. The main IKEA app (id1452164827) is live with 148,391 US ratings. — [Lookup](https://itunes.apple.com/lookup?id=1279244498&country=us), [IKEA app](https://apps.apple.com/us/app/id1452164827)
- Level of maintenance activity:
  - RoomScan Classic: last update 2023-08-09
  - Reality Composer (Apple): last update 2023-10-10
  - Nomad Sculpt: last update 2025-12-23
  - Tape Measure (AI Photo Editor Lab): last update 2025-11-12
  - Actively updated in Sep 2026: Polycam, Scaniverse, KIRI, magicplan, Metaroom, CamPlan
  - Source: iTunes Lookup API (see Q1 table).

### Inferences
- Consumer-only 3D scanning has not proven a standalone business. Survivors either moved up-market (Polycam B2B tiers, Scaniverse cloud/enterprise, magicplan and Metaroom as pro SaaS) or were absorbed into larger platforms (Scaniverse into Niantic Spatial, RealityScan into Epic, Matterport into CoStar, SiteScape under FARO).
- Gaussian splatting has become a checkbox feature in the incumbents (Polycam, Scaniverse, KIRI, AR Code, CapCam). No splat-first newcomer has meaningful App Store traction yet.
- Luma is the clearest pivot: the 3D app is left un-monetized while revenue efforts move to Dream Machine and Ray subscriptions.

### Gaps
- Luma AI's 2025 funding round (widely reported as a large Series C with Saudi-backed HUMAIN): **not verified**. No accessible primary source was found this session.
- Polycam post-2024 funding or ARR: not found.
- FARO's acquisition terms for SiteScape, and FARO's own ownership status in 2025–2026: not verified.
- Whether "Abound" is the renamed Metascan: same publisher (Abound Labs Inc.) but not confirmed by a primary source.
- Date or reason for IKEA Place's removal, and whether IKEA Kreativ scanning lives inside the IKEA app: not confirmed. The IKEA app's description did not mention "Kreativ".

## Q3. Who pays, and for what? B2B vs B2C, pricing tiers (including European B2B use cases)

### Takeaway
Pricing splits cleanly into three tiers:
1. **Pro/AEC/insurance SaaS at $120–$900 per user per year:** magicplan Estimate $899.99/yr; SiteScape $499/yr; Shapr3D Business $499.99/yr; Dot3D $349.99/yr; Recon-3D up to $599.99/yr; Polycam Business $400 and Enterprise $1,200 per user per year; RoomScan $119.99/yr.
2. **Prosumer creators and 3D-printing hobbyists at $30–$200/yr:** KIRI, Polycam Basic, Abound, MagiScan, 3d Scanner App.
3. **Consumer AR-measure utilities** monetized with $3–$13 weekly subscriptions (AR Ruler, AR Plan, 3d Scanner App, Tape Measure).

Insurance and restoration (Xactimate integrations), remodeling, construction documentation and real estate are the paying verticals most often named. European B2B examples include restoration firms (Belfor Germany), facility management (Hamburg Airport) and building-services CAD exports (DIALux, DDScad).

### Cited Findings
- magicplan targets "remodelers, restoration, and claims professionals", integrates with Xactimate® and CoreLogic, and has three tiers (Sketch, Report, Estimate) priced $129.99–$899.99/yr. — [App Store](https://apps.apple.com/us/app/id427424432)
- magicplan's site names customers in Germany (Belfor Germany, Brasa GmbH St. Ingbert) and facility management at Hamburg Airport. It integrates with Leica, Insta360, Ricoh360 and Tramex meters. — [magicplan.app](https://www.magicplan.app/)
- Polycam lists use cases: "Insurance, restoration, and damage assessment", construction documentation, BIM/CAD, drone site survey and factory layout. — [App Store](https://apps.apple.com/us/app/id1532482376)
- Polycam's pricing ladder: Free; Basic $150/yr or $30/mo ("freelancers and individual creators"); Business $400/user/yr (floor plans, measurements, point clouds, AI reports); Enterprise $1,200/user/yr (minimum 3; SSO, API, regional cloud storage). — [poly.cam/pricing](https://poly.cam/pricing)
- In Feb 2024 Polycam had nearly 100,000 paying customers, a $100/yr pro subscription, and was "cash flow positive for numerous months in 2023". — [TechCrunch](https://techcrunch.com/2024/02/07/3d-scanning-app-polycam-gets-backing-from-youtube-co-founder/)
- RoomScan Pro exports Xactimate ESX, Symbility FML, IFC, DXF, Metropix and more. It "calculates wall areas and heat loss parameters, great for contractors" and scans exteriors for appraisers' GLA (gross living area). — [App Store](https://apps.apple.com/us/app/id1504050801)
- Metaroom (Synthetic Dimension GmbH) targets architects, BIM managers, real-estate experts, insurance adjusters and trades. It exports 30+ formats including Revit, ArchiCAD, DIALux and Graphisoft DDScad (IFC), offers "GDPR-compliant cloud storage on AWS" and claims "90% time saved on site surveys". — [App Store](https://apps.apple.com/us/app/id1637077163)
- Dot3D targets "Real estate, AEC & BIM" and exports E57/LAS/LAZ point clouds to AutoCAD, Revit, ArchiCAD and Rhino. — [App Store](https://apps.apple.com/us/app/id1641016966)
- SiteScape calls itself "the #1 LiDAR 3D Scanning App for Architecture, Engineering, and Construction". — [App Store](https://apps.apple.com/us/app/id1524700432)
- Recon-3D charges $99.99/mo, $299.99–$599.99/yr, plus paid upload packs, and offers on-device-only processing "in case of sensitive data". — [App Store](https://apps.apple.com/us/app/id1594797748)
- Matterport's SaaS for real estate and property management became its largest revenue source (1.2M subscribers, $169.7M revenue in 2024). Its App Store copy targets "Insurance & Restoration". — [Wikipedia: Matterport](https://en.wikipedia.org/wiki/Matterport), [App Store](https://apps.apple.com/us/app/id701086043)
- Moasure targets landscaping, civil construction, asphalt, excavation, artificial grass, concrete, decking, fencing, pools and golf. It sells hardware kits and charges no app subscription, and it appears in the Deloitte EMEA Technology Fast 500 2025 (#335). — [moasure.com](https://www.moasure.com/), [App Store](https://apps.apple.com/us/app/id1561726410)
- Creators and 3D printing:
  - KIRI markets a "Functional Free Version … without paying a cent for subscriptions, a LiDAR sensor, or an expensive 3D Scanner", with Pro at $29.99–$49.99/yr. — [App Store](https://apps.apple.com/us/app/id1577127142)
  - MagiScan is compatible with NVIDIA Omniverse and sells lifetime ($209.99) and scan packs. — [App Store](https://apps.apple.com/us/app/id1617601717)
  - Bambu Handy (38,961 US ratings) and Creality Cloud (7,126) are adjacent 3D-printer companion apps. — [Bambu Handy](https://apps.apple.com/us/app/id1625671285), [Creality Cloud](https://apps.apple.com/us/app/id1577663728)
- Consumer AR-measure apps sell weekly subscriptions: AR Ruler $4.99–$12.99/wk; 3d Scanner App $2.99–$4.99/wk; Tape Measure (AI Photo Editor Lab) $2.99–$4.99/wk. — [AR Ruler](https://apps.apple.com/us/app/id1326773975), [3d Scanner App](https://apps.apple.com/us/app/id1419913995), [Tape Measure](https://apps.apple.com/us/app/id1437807477)
- Interior design and e-commerce:
  - Houzz "View in My Room 3D" (5M+ products, 3M+ pros). — [App Store](https://apps.apple.com/us/app/id399563465)
  - Homestyler "Live AR Preview – See IKEA, West Elm items in your room at 1:1 scale". — [App Store](https://apps.apple.com/us/app/id601137449)
  - Planner 5D and Room Planner run subscriptions and rank in Lifestyle top-grossing in the US, GB, DE, FR and VN (see Q1-B).
- Body and face scanning (health and e-commerce):
  - MeThreeSixty (18,419 US ratings) sells 3D body avatars with "GLP-1 dose and medication tracking" at $19.99–$39.99/yr. — [App Store](https://apps.apple.com/us/app/id1472541261)
  - ZOZOFIT is US-only (absent from GB/DE/FR/IT/ES/NL/PL/VN). — [Lookup](https://itunes.apple.com/lookup?id=1636398776&country=de)
  - Topology's "3-D Face Scan" uses the Face ID sensor to fit eyewear for retailers. — [App Store](https://apps.apple.com/us/app/id1110119242)

### Inferences
- B2B/prosumer apps (magicplan, Polycam, Shapr3D, SiteScape, Dot3D, Metaroom) likely earn most of the revenue on few ratings. B2C AR-measure apps collect most of the ratings but rarely reach top-grossing.
- Several of the most important B2B contracts (Polycam Enterprise, Scaniverse enterprise, Twindo as-built orders, Metaroom Workspace) are billed off-App-Store. App Store rank signals therefore understate their revenue.
- European demand shows up in product choices: GDPR-compliant storage (Metaroom), heat-loss parameters (RoomScan, UK), DIALux and DDScad exports (German-speaking building-services workflows), and magicplan's strong DE/FR rankings. This points to renovation and energy-retrofit surveys and insurance restoration as the European B2B wedge.

### Gaps
- No source found that ties specific apps to EU energy certificates (France DPE, UK EPC, Germany Energieausweis/GEG). This remains a hypothesis supported only by indirect signals (heat-loss parameters, MEP/lighting exports).
- B2B vs B2C revenue split for any app: not disclosed.

## Q4. Which iPhones have LiDAR, and what share of the active base is LiDAR-capable? (addressable market)

### Takeaway
LiDAR has been exclusive to the Pro and Pro Max tier from the iPhone 12 Pro (Oct 2020) through the iPhone 18 Pro (2026). The iPhone Air, iPhone 17 and iPhone 17e specs list no LiDAR, and neither do earlier base, mini, Plus, SE or "e" models. Apple's own LiDAR-dependent APIs (RoomPlan, on-device Object Capture) and pro apps (SiteScape, Dot3D, Metaroom) exclude every non-Pro iPhone. I found **no citable estimate** of the LiDAR-capable share of the active iPhone base. That is why leading consumer apps advertise "works without LiDAR".

### Cited Findings
- The iPhone 12 Pro and 12 Pro Max added the LiDAR sensor, released Oct 23 2020. It enables AR features such as measuring a person's height in the Measure app. — [Wikipedia: iPhone 12 Pro](https://en.wikipedia.org/wiki/IPhone_12_Pro)
- The iPhone 18 Pro / 18 Pro Max technical specifications list "LiDAR Scanner" under Sensors. — [Apple iPhone 18 Pro specs](https://www.apple.com/iphone-18-pro/specs/)
- The iPhone Air, iPhone 17 and iPhone 17e specification pages contain no LiDAR mention (checked 2026-09-27). — [iPhone Air specs](https://www.apple.com/iphone-air/specs/), [iPhone 17 specs](https://www.apple.com/iphone-17/specs/), [iPhone 17e specs](https://www.apple.com/iphone-17e/specs/)
- RoomPlan "utilizes the camera and LiDAR Scanner on iPhone and iPad". — [Apple Developer](https://developer.apple.com/augmented-reality/roomplan/)
- Object Capture on iOS "is available on iPhone 12 Pro, iPad Pro 2021, and the later models", with on-device reconstruction at reduced detail. — [WWDC23 session 10191](https://developer.apple.com/videos/play/wwdc2023/10191/)
- Pro apps that hard-require LiDAR:
  - Dot3D: "iPhone Pro / Pro Max (12 & up) or iPad Pro (2020 or later)". — [App Store](https://apps.apple.com/us/app/id1641016966)
  - Metaroom: "iPhone 12 Pro and newer". — [App Store](https://apps.apple.com/us/app/id1637077163)
  - SiteScape. — [App Store](https://apps.apple.com/us/app/id1524700432)
  - Splatcatcher. — [App Store](https://apps.apple.com/us/app/id6759800588)
- Heges lists support for "iPhone 18, 17, 16, 15, 14, 13, 12, 11, XS, XR, X (and all their Pro/Max/Plus/Air variants)" through the TrueDepth (Face ID) camera. The front depth sensor is a non-LiDAR depth path available on all Face ID iPhones. — [App Store](https://apps.apple.com/us/app/id1382310112)
- Apps that market LiDAR-free capture to widen reach:
  - Polycam: "works without LiDAR". — [link](https://apps.apple.com/us/app/id1532482376)
  - KIRI: "Precision Without LiDAR". — [link](https://apps.apple.com/us/app/id1577127142)
  - Luma: "No Lidar … all you need … is an iPhone 11 or newer". — [link](https://apps.apple.com/us/app/id1615849914)
  - RealityScan: "No special hardware!" — [link](https://apps.apple.com/us/app/id1584832280)
  - RoomScan Touch Mode: "works … on any device". — [link](https://apps.apple.com/us/app/id1504050801)
  - magicplan: "just the camera … (no extra hardware required)". — [link](https://apps.apple.com/us/app/id427424432)
- CIRP publishes iPhone model-mix data (the Pro/Pro Max share of US sales) only through paid Substack reports. — [cirpllc.com](https://www.cirpllc.com/)

### Inferences
- The LiDAR-capable addressable base is bounded by (Pro + Pro Max share of iPhone sales from late 2020 onward) × (the share of those units still active). Pre-2020 iPhones, every non-Pro model, and the 2025 Air/17/17e line-up are excluded. Pro-only features (RoomPlan, Object Capture on iOS, LiDAR scanning) therefore reach a minority of active iPhones. The exact share cannot be stated without CIRP or Counterpoint data.
- For a product strategy that must work on "any iPhone", the proven fallbacks are photogrammetry, splats from video (cloud or on-device), TrueDepth for faces and small objects, and camera-only ARKit for measurement. Keep LiDAR/RoomPlan as a Pro-only premium path.

### Gaps
- LiDAR-capable share of the active iPhone installed base (global, EU, Vietnam): **n/a**. I found no citable CIRP, Counterpoint or Kantar figure; web search was unavailable and CIRP is paywalled.
- iPad Pro LiDAR models are relevant to pro apps but were not quantified.

## Q5. Disclosed revenue, ARR, funding and user counts

### Takeaway
Hard disclosures are scarce:
- **Polycam:** $18M Series A (Feb 2024, led by Left Lane Capital, with Adobe Ventures and Chad Hurley). About 100K paying customers and 10M+ downloads in Feb 2024; "more than 10 million people" and 34M scans per its 2026 App Store copy.
- **Niantic Spatial** (Scaniverse): $250M at spin-out (2025).
- **Matterport:** $169.7M revenue in 2024 and 1.2M subscribers, before the CoStar acquisition.
- **3d Scanner App:** "11M+" downloads.
- **Moasure:** 100K+ devices sold.

No ARR or revenue disclosures were found for magicplan, KIRI, Scaniverse, 3d Scanner App, RoomScan, CamToPlan, SiteScape or Dot3D.

### Cited Findings
- Polycam raised an $18M Series A led by Left Lane Capital, with Adobe Ventures and YouTube co-founder Chad Hurley. At that point it had nearly 100,000 paying customers and 10M+ downloads (iOS + Android), was "cash flow positive for numerous months in 2023", and charged $100/yr for pro. — [TechCrunch, 2024-02-07](https://techcrunch.com/2024/02/07/3d-scanning-app-polycam-gets-backing-from-youtube-co-founder/)
- Polycam (2026 App Store copy): "34 million scans. More than 10 million people. Over 2 billion square feet captured." — [App Store](https://apps.apple.com/us/app/id1532482376)
- Niantic Spatial: $250M initial capitalization ($200M Niantic balance sheet + $50M Scopely); undisclosed Snap investment. — [Wikipedia: Niantic Spatial](https://en.wikipedia.org/wiki/Niantic_Spatial)
- Niantic funding history: $300M from Coatue at a $9B valuation (pre-spin-off). Niantic acquired Scaniverse in 2021 and 6D.ai in 2020. — [Wikipedia: Niantic, Inc.](https://en.wikipedia.org/wiki/Niantic,_Inc.)
- Matterport: 2024 revenue US$169.7M (+8% YoY), 1.2M subscribers, net loss US$256.6M. Acquired by CoStar for about US$1.6B (closed Feb 28 2025). — [Wikipedia: Matterport](https://en.wikipedia.org/wiki/Matterport)
- 3d Scanner App: "downloaded by 11+ Million users". — [App Store](https://apps.apple.com/us/app/id1419913995)
- JigSpace: "more than 5M downloads". — [App Store](https://apps.apple.com/us/app/id1111193492)
- Moasure: "100,000+ units sold"; Deloitte EMEA Fast 500 2025 (#335); Fast Company Most Innovative Companies 2026. — [moasure.com](https://www.moasure.com/)
- Metaroom: "100K+ scans and exports already completed". — [App Store](https://apps.apple.com/us/app/id1637077163)

### Inferences
- In Feb 2024 Polycam had about 100K payers at roughly $100–$150/yr. That implies store-plus-web subscription revenue on the order of US$10M+ per year at that time. This is an order-of-magnitude inference, not a disclosure. Its 2026 B2B tiers ($400–$1,200 per seat) suggest the target ARPU has risen since.

### Gaps
- magicplan revenue, funding, ownership and user counts: not found. The website counters rendered as placeholders.
- KIRI Engine users and revenue: not found (the site gives no numbers).
- Luma AI funding and valuation: not verified this session.
- Occipital/Twindo, Locometric (RoomScan), Tasmanic (CamToPlan), DotProduct and FARO SiteScape revenue: not found.

## Q6. Europe (priority market) and Vietnam: storefront data, EU pricing, EU-based players

### Takeaway
In Europe the most-rated LiDAR/3D/floor-plan apps on iOS are:
- **magicplan:** 46.4K EU-7 ratings; DE alone 14.7K; top-grossing DE #49 and FR #64.
- **Shapr3D** (seller uses a Hungarian Zrt. legal form): 38.4K EU-7 ratings; DE 13.9K.
- **Polycam:** 32.7K EU-7 ratings; top-grossing GB #58, DE #53, FR #42.
- **CamToPlan** (FR-heavy): the free and PRO apps each have about 16K EU-7 ratings; FR 6.0K.
- **3d Scanner App** (12.7K) and **Scaniverse** (11.5K).

Home-design apps with scanning or AR features are larger still: IKEA 375.6K EU-7 ratings, and Home Design 3D, Room Planner and Planner 5D, with Planner 5D at DE Lifestyle top-grossing #17. EU price points mostly mirror USD, but EUR prices run 0–20% higher (e.g. Polycam Basic €179.99 vs $149.99/yr; SiteScape €599 vs $499/yr).

Many sellers use European legal-entity forms: Shapr3D (Hungarian Zrt.), Planner5D UAB (Lithuanian), Grymala sp. z o.o. (Polish), Synthetic Dimension GmbH (Metaroom), Pix4D SA, Locometric Ltd and 3D technologies Ltd (Moasure).

Vietnam is a smaller store, but Planner 5D (9,044 VN ratings; VN Lifestyle top-grossing #21) and home-design apps dominate. Among scanners, CamToPlan (2,484) and Polycam (2,045) lead in VN.

### Cited Findings
- EU-7 rating totals and DE/FR/GB counts per app: see the Q1 master table. Source: iTunes Lookup API with `country=gb,de,fr,it,es,nl,pl,vn`, e.g. [magicplan DE](https://itunes.apple.com/lookup?id=427424432&country=de), [Polycam DE](https://apps.apple.com/de/app/id1532482376)
- EU/UK prices:
  - Polycam DE: Basic €34.99/mo, €179.99/yr; Pro €26.99/mo, €199.99/yr. — [DE](https://apps.apple.com/de/app/id1532482376)
  - Polycam GB: Pro £22.99/mo, £149.99/yr. — [GB](https://apps.apple.com/gb/app/id1532482376)
  - magicplan: identical numerals in USD, GBP and EUR (€129.99 / €399.99 / €899.99 per year). — [DE](https://apps.apple.com/de/app/id427424432)
  - SiteScape: €52.99/mo, €599/yr (vs $49.99 / $499). — [DE](https://apps.apple.com/de/app/id1524700432)
  - Dot3D: €399.99/yr (vs $349.99). — [DE](https://apps.apple.com/de/app/id1641016966)
  - Shapr3D: Solo €299.99/yr vs $249.99. — [DE](https://apps.apple.com/de/app/id1091675654)
  - KIRI: €34.99–€50.99/yr. — [DE](https://apps.apple.com/de/app/id1577127142)
  - RoomScan Pro: €119.99/yr. — [DE](https://apps.apple.com/de/app/id1504050801)
  - 3d Scanner App: €34.99–€79.99/yr. — [DE](https://apps.apple.com/de/app/id1419913995)
  - AR Ruler: €59/yr, £57/yr. — [DE](https://apps.apple.com/de/app/id1326773975), [GB](https://apps.apple.com/gb/app/id1326773975)
- Chart ranks in DE and FR on 2026-09-27: Polycam, magicplan, MagiScan, CamPlan, Nomad Sculpt, Planner 5D, Room Planner and IKEA. IKEA is Shopping top-free #9 in DE and #15 in FR. — [RSS example, DE Productivity grossing](https://itunes.apple.com/de/rss/topgrossingapplications/limit=200/genre=6007/json)
- MagiScan's European footprint is disproportionate: DE 625 and FR 379 ratings vs US 1,415. It ranks Graphics & Design top-free DE #53 and FR #52. — [Lookup DE](https://itunes.apple.com/lookup?id=1617601717&country=de)
- Metaroom (Synthetic Dimension GmbH) has more ratings in DE (547) than in the US (80). — [Lookup DE](https://itunes.apple.com/lookup?id=1637077163&country=de)
- CamToPlan's largest non-US base is France: FR 6,026 vs GB 2,140 and DE 2,703 for the free app; its 3D LiDAR app has FR 1,286. — [Lookup FR](https://itunes.apple.com/lookup?id=1292176208&country=fr)
- magicplan European customers: Belfor Germany, Brasa GmbH (St. Ingbert) and Hamburg Airport. — [magicplan.app](https://www.magicplan.app/)
- KIRI Engine in Europe: GB 256, DE 185, FR 161, IT 84 ratings, a small iOS footprint. No European usage statistics were published on its site. — [Lookup](https://itunes.apple.com/lookup?id=1577127142&country=gb), [kiriengine.app](https://www.kiriengine.app/)
- Dot3D (DotProduct LLC) in Europe: GB 20, DE 41, NL 13 ratings, a tiny iOS rating base consistent with a B2B tool. — [Lookup](https://itunes.apple.com/lookup?id=1641016966&country=de)
- Vietnam storefront:
  - Planner 5D 4.69 / 9,044 ratings; VN Lifestyle top-free #91 and top-grossing #21. — [Lookup VN](https://itunes.apple.com/lookup?id=606173978&country=vn)
  - Home Design 3D 6,441; Room Planner 4,411; CamToPlan 2,484; Polycam 2,045; Shapr3D 1,583; magicplan 656; AR Ruler 533; Scaniverse 121; KIRI 32.
  - The IKEA app is not in the VN storefront.
  - Source: iTunes Lookup API with `country=vn`.

### Inferences
- For a Europe-first product, the evidence points to pro floor-plan and survey workflows (magicplan and Metaroom are strong in DE, CamToPlan in FR) and to home-design subscriptions (Planner 5D, Room Planner) as the monetizing segments, more than to consumer object scanning.
- magicplan does not differentiate prices in Europe (the same numerals are charged in GBP and EUR, which makes it effectively pricier in the UK). Several US-origin apps apply a 10–20% EUR premium. EU App Store prices are normally VAT-inclusive while US prices exclude sales tax, so part of this gap is tax rather than list-price policy (general App Store convention; not separately sourced here).
- In Vietnam, rating volume sits with home-design apps. Pure 3D scanners have small bases (Polycam about 2K; KIRI 32), consistent with a low share of LiDAR-equipped Pro iPhones and low pro-SaaS spending. This is an inference; no VN device-mix data was found.

### Gaps
- DE/UK/FR download estimates and revenue per country: n/a (no Sensor Tower or Appfigures access).
- Headquarters countries: sourced only from legal-entity suffixes or App Store seller names, not from company registries. Examples: "Tasmanic Editions" (CamToPlan), "Hexanomad" (Nomad Sculpt), "AI Photo Editor Lab SRL". magicplan's corporate HQ (seller "Technologies magicplan Inc.") and any Sensopia/European entity were not verified.
- Evidence on energy-certificate workflows (DPE, EPC, Energieausweis) in these apps: not found.
