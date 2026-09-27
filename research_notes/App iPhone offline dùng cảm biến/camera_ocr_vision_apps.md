# iPhone camera / computer-vision apps: downloads, revenue, chart ranks and offline capability (dataset as of 27 Sep 2026; Europe prioritized, plus Global, US and Vietnam)

## Q1. Which camera/vision apps have the most iOS downloads and revenue (global, US, Europe, Vietnam)?

### Takeaway
Sensor Tower's public estimates for **August 2026** (worldwide, iOS App Store only) put the top revenue earners among camera-led apps as follows. PictureThis leads pure vision apps at about $9M/month, and CamScanner follows at $8M/month with 3M downloads. Yazio ($5M), iScanner ($4M), Translate Now ($3M), the Turkish "Scanner App – Scan PDF & Docs" ($3M), Adobe Scan, Cal AI and Foodvisor (about $2M each) come next. MyFitnessPal ($12M) is larger but is a hybrid calorie tracker, not a camera-first app. By downloads, the Google app (which contains Lens) leads at about 8M/month, then CamScanner at 3M and Google Translate at 2M. Document scanning is the largest pure-camera segment at about $22M/month across the 19 scanner apps tracked. Plant ID follows at about $10.7M, photo-first AI calorie apps at about $6M and camera translators at about $5.8M.

### Cited Findings

#### Data sources and method (read before using the numbers)
- **Downloads and revenue**: these come from Sensor Tower's public app-overview JSON (`worldwide_last_month_downloads`, `worldwide_last_month_revenue`), fetched 27 Sep 2026, so "last month" means **August 2026**. The figures are **worldwide, iOS App Store only (iPhone+iPad), gross consumer spend before Apple's cut**, and they are **estimates**. Changing the `country` parameter (US or VN) did not change the worldwide figure. Example source: [Sensor Tower – CamScanner overview](https://app.sensortower.com/overview/388627783?country=US), whose meta text reads "Last month's estimates were 3m downloads and $8m revenue". Every app name in the main table links to its Sensor Tower page.
- **Floor values**: Sensor Tower's public figures are heavily rounded. A value of exactly 1,000 downloads or $1,000 is the minimum bucket and is shown below as **"<5k\*" / "<$5k\*"**. Treat it as "not meaningful or very low". Several apps show a floor download value alongside material revenue (ScanGuru, Tiny Scanner, Plantum, Chegg Study, Evernote Scannable, SwiftScan). Those download figures are **suspect/n/a**, not true near-zero values.
- **Ratings and rating counts per country**: these come from the Apple iTunes Lookup API (e.g., [lookup CamScanner VN](https://itunes.apple.com/lookup?id=388627783&country=vn)), fetched 27 Sep 2026.
- **Chart ranks**: these come from the Apple App Store RSS top-100 feeds (iPhone), updated 27 Sep 2026 01:07 PDT (e.g., [DE Productivity top grossing feed](https://itunes.apple.com/de/rss/topgrossingapplications/limit=100/genre=6007/json)). They cover 12 stores (US, VN, DE, GB, FR, IT, ES, NL, SE, NO, DK, FI) × 14 categories + overall × Top Free and Top Grossing. They are one-day snapshots.
- "Annualized" = August 2026 × 12. It is a simple run-rate I calculated from Sensor Tower estimates, **not a disclosed figure**.

#### Segment totals (Sensor Tower, worldwide iOS, Aug-2026; only apps tracked here)
| Segment | # apps tracked | Sum WW iOS revenue Aug-2026 (ST est.) | Sum WW iOS downloads Aug-2026 (ST est.) |
|---|---|---|---|
| Doc scanner/OCR | 19 | $22.1M | 6.2M |
| Calorie tracker (hybrid, has photo logging) | 4 | $18.8M | 1.3M |
| Plant ID | 9 | $10.7M | 1M |
| Photo-first AI calorie | 11 | $6M | 1.9M |
| Camera translate | 12 | $5.8M | 3.9M |
| Homework solver | 11 | $2M | 913k |
| Coin ID | 3 | $1.2M | 620k |
| Barcode product scan | 4 | $1M | 877k |
| Visual search/translate | 4 | $1M | 8.2M |
| QR/barcode | 4 | $1M | 260k |
| Rock ID | 1 | $800k | 200k |
| TCG card scan | 3 | $640k | 430k |
| Insect ID | 1 | $400k | 60k |
| Antique ID | 1 | $400k | 200k |
| Wine label scan | 1 | $300k | 100k |
| Business card | 2 | $220k | 6k |
| Bird ID | 2 | $200k | 340k |
| Mushroom ID | 1 | $200k | 20k |
| Receipt scan | 3 | $170k | 20k |
| Resale item ID | 1 | $90k | 30k |
| Record ID | 1 | $40k | 10k |
| Skin scan | 2 | $7k | 30k |
| Text OCR | 2 | <$5k* | <5k* |
| Nature ID | 2 | <$5k* | 80k |
| Animal ID | 1 | <$5k* | 6k |
| Accessibility vision | 2 | <$5k* | 70k |
| Receipt scan (rewards) | 1 | <$5k* | 600k |

#### Main ranked dataset: 108 apps sorted by estimated worldwide iOS revenue, Aug-2026
(Sources: each app links to its Sensor Tower overview; IAP price points come from Sensor Tower's `top_in_app_purchases.US` field, which mirrors the App Store listing. Publisher HQ is Sensor Tower's `publisher_country`.)

| # | App | Segment | Publisher (HQ per ST) | WW iOS downloads, Aug-2026 (ST est.) | WW iOS revenue, Aug-2026 (ST est., gross) | Annualized rev (×12, est.) | Top-3 countries (ST) | iOS launch | US IAP price points (examples) |
|---|---|---|---|---|---|---|---|---|---|
| 1 | [MyFitnessPal](https://app.sensortower.com/overview/341232718?country=US) | Calorie tracker (hybrid, has photo logging) | MyFitnessPal, Inc. (US) | 600k | $12M | $144M | US,GB,CA | 2009-12 | MyFitnessPal Monthly Premium $19.99; MyFitnessPal Yearly Premium $79.99; MyFitnessPal Premium (Monthly) $9.99 |
| 2 | [PictureThis](https://app.sensortower.com/overview/1252497129?country=US) | Plant ID | Glority Global Group Ltd. (China) | 700k | $9M | $108M | US,GB,JP | 2017-09 | PictureThis Pro (Annual) $39.99; PictureThis Pro (Annual) $39.99; PictureThis Pro (Monthly) $7.99 |
| 3 | [CamScanner](https://app.sensortower.com/overview/388627783?country=US) | Doc scanner/OCR | INTSIG Information Co., Ltd (China) | 3M | $8M | $96M | CN,US,BR | 2010-08 | Premium Account(1 year) $59.99; Premium Account (Monthly) $4.99; CamScanner Premium (Weekly) $6.99 |
| 4 | [Yazio](https://app.sensortower.com/overview/946099227?country=US) | Calorie tracker (hybrid, has photo logging) | YAZIO (Germany) | 500k | $5M | $60M | DE,RU,FR | 2015-01 | 12 Months $23.90; YAZIO PRO (Annual) $32.99; 12 Months $47.90 |
| 5 | [iScanner (BPMobile)](https://app.sensortower.com/overview/1040093707?country=US) | Doc scanner/OCR | BPMobile (US) | 300k | $4M | $48M | US,DE,FR | 2015-09 | 1 week Pro 100Gb storage $4.99; Premium Scanner & PDF editor (Monthly) $12.99; Premium (Weekly) $3.99 |
| 6 | [Scanner App - Scan PDF & Docs](https://app.sensortower.com/overview/1568660349?country=US) | Doc scanner/OCR | TAPSUITE YAZILIM HIZMETLERI ANONIM SIRKETI (Turkey) | 800k | $3M | $36M | US,BR,IN | 2021-12 | Picture to Text Converter Weekly $11.99; Photo to PDF Weekly $9.99; Scanner Weekly Pro Subscription $14.99 |
| 7 | [Translate Now](https://app.sensortower.com/overview/1348028646?country=US) | Camera translate | Air Apps Systems (Portugal) | 500k | $3M | $36M | US,CN,JP | 2018-03 | Air Apps Pro (Weekly) $14.99; Air Apps One Welcome - 1 Week $9.99; Air Apps One Welcome - 1 Week $14.99 |
| 8 | [Adobe Scan](https://app.sensortower.com/overview/1199564834?country=US) | Doc scanner/OCR | Adobe Inc. (US) | 700k | $2M | $24M | US,IN,JP | 2017-05 | Adobe Scan Premium - Monthly $9.99; Adobe Scan Premium (Monthly) $9.99; Adobe PDF Pack (Monthly) $9.99 |
| 9 | [Cal AI](https://app.sensortower.com/overview/6480417616?country=US) | Photo-first AI calorie | Viral Development LLC (US) | 500k | $2M | $24M | US,GB,CA | 2024-04 | Unlimited (Annual) $29.99; Unlimited Plan (Annual) $19.99; Unlimited (Monthly) $9.99 |
| 10 | [Foodvisor](https://app.sensortower.com/overview/1064020872?country=US) | Photo-first AI calorie | Foodvisor (France) | 400k | $2M | $24M | FR,US,DE | 2016-02 | Foodvisor Premium (Annual) $23.99; 1 month of Foodvisor $14.99; Foodvisor Premium (Annual) $83.99 |
| 11 | [Yuka](https://app.sensortower.com/overview/1092799236?country=US) | Barcode product scan | Yuca (France) | 800k | $1M | $12M | US,FR,GB | 2017-01 | Premium Member (Annual) $10.00; Premium Member (Annual) $15.00; Premium Member (Annual) $20.00 |
| 12 | [Traductor GO](https://app.sensortower.com/overview/1570134612?country=US) | Camera translate | MATdev (n/a) | 300k | $1M | $12M | US,JP,FR | 2021-06 | 1 Week Elite $10.99; 1 Week Extended $9.99; 1 Week Elite Pro $10.99 |
| 13 | [Lose It!](https://app.sensortower.com/overview/297368629?country=US) | Calorie tracker (hybrid, has photo logging) | FitNow (US) | 100k | $1M | $12M | US,GB,CA | 2015-10 | Lose It! Premium Features (Annual) $39.99; Lose It! Premium (Annual) $19.99; Lose It! Premium (Annual) $29.99 |
| 14 | [iTranslate](https://app.sensortower.com/overview/288113403?country=US) | Camera translate | Mosaic S.r.l. (US) | 100k | $900k | $10.8M | US,CN,DE | 2008-10 | iTranslate PRO - 1 month $12.99; Weekly with free trial $9.99; iTranslate PRO - 1 year $99.99 |
| 15 | [PlantIn](https://app.sensortower.com/overview/1527399597?country=US) | Plant ID | Vortemol Limited (Ukraine) | 90k | $900k | $10.8M | US,FR,TR | 2020-08 | Weekly Premium Plant Care $6.99; Premium Access Weekly $7.99; Lifetime Premium Plant Care $49.99 |
| 16 | [Gauth](https://app.sensortower.com/overview/1542571008?country=US) | Homework solver | GAUTHTECH PTE. LTD. (Singapore) | 400k | $800k | $9.6M | US,VN,GB | 2020-12 | Quarterly - 3-Day Free Trial $31.99; Quarterly - 2022 (for new users) $31.99; Monthly $11.99 |
| 17 | [Calo: AI Food Calorie Counter](https://app.sensortower.com/overview/6447434453?country=US) | Photo-first AI calorie | Next Vision Limited (China) | 300k | $800k | $9.6M | US,GB,FR | 2023-04 | Calo Premium (Annual) $39.99; Calo Premium (Annual) $19.99; Calo Premium (Annual) $39.99 |
| 18 | [Rock Identifier](https://app.sensortower.com/overview/1546796934?country=US) | Rock ID | Next Vision Limited (China) | 200k | $800k | $9.6M | US,GB,CA | 2021-01 | Rock Identifier Premium (Annual) $39.99; Rock Identifier Premium (Annual) $39.99; Rock Identifier Premium (Annual) $39.99 |
| 19 | [Lifesum](https://app.sensortower.com/overview/286906691?country=US) | Calorie tracker (hybrid, has photo logging) | Lifesum AB (Sweden) | 80k | $800k | $9.6M | US,DE,RU | 2008-08 | Lifesum Premium 1 year $119.99; Lifesum Premium 3 Months $39.99; Lifesum Premium 3 Months $39.99 |
| 20 | [ScanGuru](https://app.sensortower.com/overview/1040149161?country=US) | Doc scanner/OCR | GM UniverseApps Limited (Ukraine) | <5k* | $800k | $9.6M | US,BR,JP | 2015-09 | Unlimited Access (Weekly) $6.99; Unlimited Access (Weekly) $7.99; Premium (Weekly) $6.99 |
| 21 | [QR Code Reader (AIR APPS)](https://app.sensortower.com/overview/1226650677?country=US) | QR/barcode | Air Apps Systems (Portugal) | 80k | $700k | $8.4M | US,CN,DE | 2017-04 | Air Apps Pro - 1 Week $11.99; Air Apps One Welcome - 1 Week $11.99; Air Apps One Welcome - 1 Week $9.99 |
| 22 | [Scan Shot PDF Scanner](https://app.sensortower.com/overview/1575194801?country=US) | Doc scanner/OCR | Scanner App PDF Tool (Spain) | 20k | $700k | $8.4M | US,DE,FR | 2021-08 | 1 Week Elite $9.99; 1 Week Express $7.99; 1 Week Advanced $9.99 |
| 23 | [CoinSnap](https://app.sensortower.com/overview/1634551626?country=US) | Coin ID | Next Vision Limited (China) | 300k | $600k | $7.2M | US,DE,FR | 2022-10 | Coin Identifier Premium (Annual) $39.99; Coin Identifier Premium (Weekly) $3.99; Coin Identifier Premium (Annual) $39.99 |
| 24 | [Scanner Pro (Readdle)](https://app.sensortower.com/overview/333710667?country=US) | Doc scanner/OCR | Readdle Technologies Limited (Ukraine) | 40k | $600k | $7.2M | US,DE,CN | 2009-10 | Fax Pack 1 $0.99; Scanner Pro Plus (Weekly) $7.99; Scanner Pro Plus (Annual) $29.99 |
| 25 | [Tiny Scanner](https://app.sensortower.com/overview/595563753?country=US) | Doc scanner/OCR | TinyWork Apps (China) | <5k* | $600k | $7.2M | US,GB,CA | 2013-01 | Premium Plan - Monthly $4.99; Premium Plan - Weekly $4.99; Upgrade to Tiny Scanner Plus $4.99 |
| 26 | [Scanner App: Scan Documents (VN #2)](https://app.sensortower.com/overview/6753972326?country=US) | Doc scanner/OCR | UNITEMAN TECHNOLOGY (HK) LIMITED (Hong Kong) | 900k | $500k | $6M | MY,VN,PH | 2025-10 | weekly Access $9.99; Yeayly Access (Annual) $89.99 |
| 27 | [CoinIn](https://app.sensortower.com/overview/1672111368?country=US) | Coin ID | Vortemol Limited (Ukraine) | 300k | $500k | $6M | US,IT,FR | 2023-03 | Premium Access (Weekly) $9.99; Premium Access Weekly $17.99; Premium Pro Access (Weekly) $15.99 |
| 28 | [Translate AI - Live Translate](https://app.sensortower.com/overview/6738304985?country=US) | Camera translate | HEYOS (Turkey) | 200k | $500k | $6M | US,DE,BR | 2025-01 | Premium Access (Weekly) $12.99; Weekly Subs Trial $12.99; Weekly Pro Access $12.99 |
| 29 | [BitePal](https://app.sensortower.com/overview/6479529917?country=US) | Photo-first AI calorie | Reface Lithuania UAB (Lithuania) | 100k | $500k | $6M | US,GB,FR | 2024-06 | Weekly Subscription $3.99; Annual Subscription $35.99; Annual Subscription $35.99 |
| 30 | [TapScanner](https://app.sensortower.com/overview/1382564905?country=US) | Doc scanner/OCR | SMART MEDIA INTERNET MARKETING LTD (Israel) | 100k | $500k | $6M | IN,ID,US | 2018-05 | Unlimited Access - Weekly $6.99; Unlimited access (Weekly) $4.99; Unlimited access (Weekly) $4.99 |
| 31 | [HoloDex - TCG Scan](https://app.sensortower.com/overview/6747442689?country=US) | TCG card scan | MAVELLI FZCO (n/a) | 300k | $400k | $4.8M | US,GB,CA | 2025-09 | Monthly plan HoloDex $12.99; HoloDex Deal (Annual) $34.99; HoloDex Pro (Monthly) $7.99 |
| 32 | [AntiqSnap](https://app.sensortower.com/overview/6752929120?country=US) | Antique ID | Next Vision Limited (China) | 200k | $400k | $4.8M | US,CA,GB | 2025-10 | AntiqSnap Premium (Annual) $39.99; AntiqSnap Premium (Annual) $39.99; AntiqSnap Premium (Weekly) $3.99 |
| 33 | [Scanner - Luni](https://app.sensortower.com/overview/1291962681?country=US) | Doc scanner/OCR | Luni (France) | 100k | $400k | $4.8M | US,FR,DE | 2017-10 | Premium (Monthly) $9.99; Premium (Monthly) $12.99; Premium (Monthly) $14.99 |
| 34 | [Lens Scan: Identify Anything](https://app.sensortower.com/overview/6560107458?country=US) | Visual search/translate | EvenEdge (Turkey) | 100k | $400k | $4.8M | US,DE,NL | 2024-09 | Lens Scan Pro Yearly $79.99; Lens Scan Pro Yearly $79.99; Lens Scan Pro Monthly $79.99 |
| 35 | [Picture Insect](https://app.sensortower.com/overview/1461694973?country=US) | Insect ID | Next Vision Limited (China) | 60k | $400k | $4.8M | US,DE,JP | 2019-05 | Picture Insect Premium (Annual) $39.99; Picture Insect Premium (Annual) $39.99; Picture Insect Premium (Annual) $39.99 |
| 36 | [Scan Hero](https://app.sensortower.com/overview/1017261655?country=US) | Doc scanner/OCR | Mosaic S.r.l. (US) | 6k | $400k | $4.8M | US,CN,MX | 2016-02 | Monthly Premium Subscription $22.00; Upgrade to Pro! (Annual) $89.99; Document & Text Scanner + OCR (Monthly) $16.00 |
| 37 | [Welmi](https://app.sensortower.com/overview/6741707862?country=US) | Photo-first AI calorie | T-SHAPED APPS LTD (n/a) | 300k | $300k | $3.6M | FR,UA,MX | 2025-02 | Yearly $47.99; Yearly $35.99; Monthly $11.99 |
| 38 | [Genius Scan](https://app.sensortower.com/overview/377672876?country=US) | Doc scanner/OCR | The Grizzly Labs (France) | 200k | $300k | $3.6M | US,FR,DE | 2010-06 | Genius Scan Ultra (Monthly) $4.99; Genius Scan Plus (Monthly) $0.99; Genius Scan Ultra (Annual) $39.99 |
| 39 | [Photomath](https://app.sensortower.com/overview/919087726?country=US) | Homework solver | Google (US) | 200k | $300k | $3.6M | US,RU,IT | 2014-10 | Photomath Plus (Monthly) $9.99; Photomath Plus (Monthly) $5.99; Photomath Plus (Monthly) $7.99 |
| 40 | [FoodPilot AI Calorie Tracker](https://app.sensortower.com/overview/6738115267?country=US) | Photo-first AI calorie | Hong Kong Radiant Limited (Hong Kong) | 200k | $300k | $3.6M | US,IT,FR | 2024-11 | FoodPilot Yearly Premium $29.99; FoodPilot Yearly Premium $39.99; FoodPilot Premium (Weekly) $9.99 |
| 41 | [Vivino](https://app.sensortower.com/overview/414461255?country=US) | Wine label scan | Vivino ApS (Denmark) | 100k | $300k | $3.6M | US,FR,BR | 2011-01 | Vivino Premium (Monthly) $4.99; Vivino Premium (Annual) $47.90; Vivino Premium (Annual) $47.90 |
| 42 | [InstantTranslator: AI Translate](https://app.sensortower.com/overview/6636468891?country=US) | Camera translate | APPLABS LIMITED (Hong Kong) | 100k | $300k | $3.6M | US,DE,BR | 2024-08 | Rapid translation with AI (Weekly) $7.99; InstantTranslator_week $7.99; Instant Translator Weekly Plan $6.99 |
| 43 | [QR Reader for iPhone (TapMedia)](https://app.sensortower.com/overview/368494609?country=US) | QR/barcode | TapMedia Ltd (United Kingdom) | 80k | $300k | $3.6M | US,GB,BR | 2010-05 | TapMedia PRO - 1 month $4.99; TapMedia PRO - 1 Month $4.99; Database Scanner (1 month) $0.99 |
| 44 | [EveryScan (LensAI) Identifier](https://app.sensortower.com/overview/1663862037?country=US) | Visual search/translate | Conlan Limited (Cyprus) | 7k | $300k | $3.6M | US,BR,GB | 2023-03 | Scanner Pro: 1 week $9.99; Object Identifier - 1 Week $8.99; AI Identifier: Weekly Access $9.99 |
| 45 | [Google app (Lens)](https://app.sensortower.com/overview/284815942?country=US) | Visual search/translate | Google (US) | 8M | $200k | $2.4M | US,JP,BR | 2008-07 | 100 GB (Monthly) $1.99; Google AI Plus (2 TB) (Monthly) $9.99; 200 GB (Monthly) $2.99 |
| 46 | [Gizmo: AI Tutor](https://app.sensortower.com/overview/1610516671?country=US) | Homework solver | Save All (United Kingdom) | 200k | $200k | $2.4M | US,PH,GB | 2022-02 | Gizmo Unlimited (Weekly) $6.99; Gizmo Unlimited (Annual) $77.99; Gizmo Unlimited (Weekly) $14.99 |
| 47 | [FoilSnap: TCG Card Scanner](https://app.sensortower.com/overview/6752642525?country=US) | TCG card scan | Next Vision Limited (China) | 100k | $200k | $2.4M | US,GB,DE | 2025-09 | FoilSnap Premium (Annual) $39.99; FoilSnap Pro (Annual) $29.99; FoilSnap Premium (Weekly) $3.99 |
| 48 | [PlantAI: Identifier & Diagnose](https://app.sensortower.com/overview/1664437810?country=US) | Plant ID | Glority Global Group Ltd. (China) | 60k | $200k | $2.4M | US,GB,IT | 2023-04 | PlantAI Premium (Annual) $29.99; PlantAI Premium (Annual) $49.99; PlantAI Premium (Annual) $29.99 |
| 49 | [Question.AI](https://app.sensortower.com/overview/6449486871?country=US) | Homework solver | 3HOUSE (Singapore) | 40k | $200k | $2.4M | US,ID,VN | 2023-05 | Question.AI Plus-Monthly $11.99; Question.AI Plus-Weekly $6.99; Question.AI DPro - Monthly $9.99 |
| 50 | [Picture Bird](https://app.sensortower.com/overview/1474586978?country=US) | Bird ID | Next Vision Limited (China) | 40k | $200k | $2.4M | US,GB,FR | 2019-08 | Picture Bird Premium (Annual) $39.99; Picture Bird Premium (Annual) $39.99; Picture Bird Premium (Annual) $39.99 |
| 51 | [Plant App](https://app.sensortower.com/overview/1595795215?country=US) | Plant ID | SCALEUP YAZILIM HIZMETLERI (Turkey) | 30k | $200k | $2.4M | US,GB,IN | 2022-04 | 1 Week Plant Identifier Subs $6.99; 1 Week Plant Identifier Subs $9.99; 1 Week Plant Identifier Subs $14.99 |
| 52 | [Picture Mushroom](https://app.sensortower.com/overview/1474578078?country=US) | Mushroom ID | Next Vision Limited (China) | 20k | $200k | $2.4M | US,DE,FR | 2019-08 | Picture Mushroom Premium (Annual) $29.99; Picture Mushroom Premium (Annual) $29.99; Picture Mushroom Premium (Annual) $29.99 |
| 53 | [CamCard](https://app.sensortower.com/overview/349447615?country=US) | Business card | INTSIG Information Co., Ltd (China) | 6k | $200k | $2.4M | CN,JP,US | 2010-02 | Premium Account (Monthly) $4.49; Yearly Subscribe for Premium $49.99; Yearly subscribe for Premium $49.99 |
| 54 | [Evernote Scannable](https://app.sensortower.com/overview/883338188?country=US) | Doc scanner/OCR | Evernote Corporation (US) | <5k* | $200k | $2.4M | US,CN,JP | 2015-01 | Weekly Plan with Free Trial $2.99; Weekly Plan $2.99; Yearly with Free Trial $49.99 |
| 55 | [Chegg Study](https://app.sensortower.com/overview/385758163?country=US) | Homework solver | Chegg, Inc. (US) | <5k* | $200k | $2.4M | US,CA,SA | 2010-08 | Chegg Study (Monthly) $15.99; Chegg Study (Monthly) $15.99; Chegg Study (Monthly) $15.99 |
| 56 | [Plantum](https://app.sensortower.com/overview/1476047194?country=US) | Plant ID | AIBY (US) | <5k* | $200k | $2.4M | US,FR,CA | 2019-08 | Plant Identification (Weekly) $6.99; Premium membership (1 month) $6.99; Plant Identification (Annual) $59.99 |
| 57 | [Lens AI & Reverse Image Search](https://app.sensortower.com/overview/6753348682?country=US) | Visual search/translate | HEYOS (Turkey) | 100k | $100k | $1.2M | US,BR,GB | 2025-12 | Weekly Premium Access $9.99; Weekly Premium Access $9.99; FREE Lens AI & Reverse Image Search (Weekly) $9.99 |
| 58 | [SnapCal](https://app.sensortower.com/overview/6747375157?country=US) | Photo-first AI calorie | Scan App (n/a) | 60k | $100k | $1.2M | US,GB,DE | 2025-07 | SnapCal Annual Membership $36.99; SnapCal Annual Membership $29.99; SnapCal Annual Membership $29.99 |
| 59 | [Coin ID (AIBY)](https://app.sensortower.com/overview/1665672552?country=US) | Coin ID | AIBY (US) | 20k | $100k | $1.2M | US,DE,FR | 2023-02 | Weekly access (3 days trial) $6.99; Weekly access (3 days trial) $5.99; Weekly access $6.99 |
| 60 | [Planto](https://app.sensortower.com/overview/1531728753?country=US) | Plant ID | Appagon (France) | 20k | $100k | $1.2M | US,IT,FR | 2020-10 | Unlimited weekly access $4.99; Weekly premium features $4.99; Unlimited weekly access $4.99 |
| 61 | [Brainly](https://app.sensortower.com/overview/745089947?country=US) | Homework solver | Brainly sp. z o o (Poland) | 10k | $100k | $1.2M | US,BR,MX | 2013-11 | Brainly Plus, Monthly $9.99; Brainly Plus, Annual $39.99; Brainly Tutor, Monthly $29.99 |
| 62 | [Quizard AI](https://app.sensortower.com/overview/1667996582?country=US) | Homework solver | Quizard AI, Inc. (US) | 30k | $90k | $1.1M | US,CA,RU | 2023-01 | Unlimited answers weekly $6.99; Unlimited answers weekly $9.99; quizard pro - monthly $17.99 |
| 63 | [ThriftAI: Profit Identifier](https://app.sensortower.com/overview/6746565278?country=US) | Resale item ID | smallstack ApS (n/a) | 30k | $90k | $1.1M | US,CA,GB | 2025-06 | Premium (Yearly) $39.99; Multi Mode (Weekly) $4.99; Sell Though Rate (Annual) $39.99 |
| 64 | [DeepL](https://app.sensortower.com/overview/1552407475?country=US) | Camera translate | DeepL SE (Germany) | 200k | $80k | $960k | DE,JP,CN | 2021-04 | Monthly $10.49; Monthly $13.00; Monthly $23.99 |
| 65 | [Dext](https://app.sensortower.com/overview/418327708?country=US) | Receipt scan | Dext Software Limited (United Kingdom) | 10k | $80k | $960k | GB,AU,FR | 2011-02 | Business Plus (Monthly) $25.49; Business (Monthly) $12.99; Business - 5 users, 250 docs (Monthly) $34.99 |
| 66 | [Blossom](https://app.sensortower.com/overview/1487453649?country=US) | Plant ID | Mosaic S.r.l. (US) | <5k* | $80k | $960k | US,DE,GB | 2020-02 | Blossom Premium (1 Year) $79.99; Blossom Premium (1 Year) $69.99; Blossom Premium (1 Month) $5.99 |
| 67 | [Mathway](https://app.sensortower.com/overview/467329677?country=US) | Homework solver | Chegg, Inc. (US) | 7k | $70k | $840k | US,MX,SA | 2012-09 | Steps (Monthly) $9.99; Steps (Monthly) $9.99; Steps (Monthly) $19.99 |
| 68 | [Answer.AI](https://app.sensortower.com/overview/6446047896?country=US) | Homework solver | ANSWER AI LAB INC (US) | 10k | $60k | $720k | US,CA,PH | 2023-03 | Answer.AI Pro-Monthly $9.99; Answer.AI Pro-Monthly $9.99; Answer.AI Pro-Yearly $71.90 |
| 69 | [SimplyWise](https://app.sensortower.com/overview/1538521095?country=US) | Receipt scan | SimplyWise, Inc. (US) | <5k* | $50k | $600k | US,CA,BE | 2020-12 | SimplyWise Pro (Annual) $89.99; SimplyWise (Annual 9) $23.99; SimplyWise (Annual 10) $59.99 |
| 70 | [MonPrice: Card Value Scanner](https://app.sensortower.com/overview/6741683137?country=US) | TCG card scan | Programacion Viktor Seraleev EIRL (Chile) | 30k | $40k | $480k | DE,US,IT | 2025-03 | Card Value Scanner Collector (Weekly) $6.99; Dex ID Annual Premium $49.99; Annual Offer $29.99 |
| 71 | [Expensify](https://app.sensortower.com/overview/471713959?country=US) | Receipt scan | Expensify, Inc. (US) | 10k | $40k | $480k | US,GB,CA | 2011-10 | Monthly Subscription $4.99 |
| 72 | [VinylSnap](https://app.sensortower.com/overview/6748595105?country=US) | Record ID | Next Vision Limited (China) | 10k | $40k | $480k | US,GB,IT | 2025-07 | Vinylsnap Premium (Annual) $29.99; Vinylsnap Premium (Annual) $29.99; Vinylsnap Premium (Annual) $39.99 |
| 73 | [SwiftScan (ex-Scanbot)](https://app.sensortower.com/overview/834854351?country=US) | Doc scanner/OCR | Maple Media Apps, LLC (US) | <5k* | $40k | $480k | DE,US,FR | 2014-04 | SwiftScan VIP Monthly $5.99; SwiftScan Pro-Full Scanner App $6.99; SwiftScan Plus Monthly $7.99 |
| 74 | [SnapCalorie](https://app.sensortower.com/overview/1574239307?country=US) | Photo-first AI calorie | Perception Labs, Inc. (US) | 50k | $30k | $360k | US,GB,CA | 2021-11 | SnapCalorie Premium (Annual) $79.99; SnapCalorie Premium (Annual) $15.99; SnapCalorie Premium (Annual) $149.00 |
| 75 | [TurboScan (free)](https://app.sensortower.com/overview/1017559099?country=US) | Doc scanner/OCR | Piksoft Inc. (US) | <5k* | $30k | $360k | US,RU,CA | 2015-07 | TurboScan Premium $14.99 |
| 76 | [SCAN ACE](https://app.sensortower.com/overview/556500145?country=US) | Doc scanner/OCR | NEO PIXEL LABS PTE. LTD. (n/a) | <5k* | $30k | $360k | US,DE,CN | 2012-10 | Premium Plan - Monthly $2.99; Premium Plan - Weekly $5.99; Premium Plan - Weekly $4.99 |
| 77 | [Photo Translator (EVOLLY)](https://app.sensortower.com/overview/1350347947?country=US) | Camera translate | EVOLLY.APP (Vietnam) | <5k* | $30k | $360k | US,VN,TH | 2018-04 | 1 Year Premium with Free Trial $49.99; Yearly Premium with Free Trial $49.99; 1 Month Premium $9.99 |
| 78 | [Document Scan: PDF Scanner App (VN #4)](https://app.sensortower.com/overview/1588273103?country=US) | Doc scanner/OCR | Pretty Boa Media Ltd (n/a) | 20k | $20k | $240k | VN,TH,SA | 2022-02 | Weekly PRO $9.99; PRO subscription monthly $9.99; Pro subscription weekly $4.99 |
| 79 | [CodeCheck](https://app.sensortower.com/overview/359351047?country=US) | Barcode product scan | Producto Check GmbH (Germany) | 7k | $20k | $240k | DE,AT,CH | 2010-03 | 1 Month: CodeCheck Pro $2.99; 12 Months: CodeCheck Pro $17.99; 12 Months: CodeCheck Pro $13.49 |
| 80 | [ABBYY Business Card Reader](https://app.sensortower.com/overview/898215947?country=US) | Business card | ABBYY USA Software House Inc (Russia) | <5k* | $20k | $240k | US,RU,DE | 2014-09 | BCR Premium monthly $7.99; BCR Premium yearly $29.99; BCR Premium yearly $29.99 |
| 81 | [TurboScan Pro (paid)](https://app.sensortower.com/overview/342548956?country=US) | Doc scanner/OCR | Piksoft Inc. (US) | <5k* | $10k | $120k | US,RU,CA | 2009-12 | none listed (free/ads or no IAP) |
| 82 | [Symbolab](https://app.sensortower.com/overview/876942533?country=US) | Homework solver | Symbolab (Israel) | 6k | $7k | $84k | US,MX,CA | 2014-05 | Universal Weekly Subscription $2.49; Universal Monthly Subscription $7.99; All features with no ads $7.99 |
| 83 | [Miiskin](https://app.sensortower.com/overview/1214795331?country=US) | Skin scan | Miiskin (Denmark) | <5k* | $7k | $84k | US,GB,DK | 2017-06 | Miiskin Premium Yearly $29.99; Miiskin Subscription (Monthly) $5.99; Miiskin Premium Light 3 Months $2.99 |
| 84 | [Google Translate](https://app.sensortower.com/overview/414706506?country=US) | Camera translate | Google (US) | 2M | <$5k* | n/a | US,JP,CN | 2011-02 | none listed (free/ads or no IAP) |
| 85 | [Fetch](https://app.sensortower.com/overview/1182474649?country=US) | Receipt scan (rewards) | Fetch Rewards, LLC (US) | 600k | <$5k* | n/a | US | n/a | none listed (free/ads or no IAP) |
| 86 | [Naver Papago](https://app.sensortower.com/overview/1147874819?country=US) | Camera translate | NAVER Corp. (South Korea) | 300k | <$5k* | n/a | KR,JP,CN | 2016-09 | none listed (free/ads or no IAP) |
| 87 | [Merlin Bird ID](https://app.sensortower.com/overview/773457673?country=US) | Bird ID | Cornell University (US) | 300k | <$5k* | n/a | US,GB,CA | 2013-12 | none listed (free/ads or no IAP) |
| 88 | [Yandex Translate](https://app.sensortower.com/overview/584291439?country=US) | Camera translate | Direct Cursus Computer Systems Trading (Russia) | 100k | <$5k* | n/a | RU,TR,KZ | 2012-12 | none listed (free/ads or no IAP) |
| 89 | [QR Code Reader (Komorebi)](https://app.sensortower.com/overview/1080558159?country=US) | QR/barcode | Komorebi Inc. (Japan) | 100k | <$5k* | n/a | JP,US,KR | 2016-03 | none listed (free/ads or no IAP) |
| 90 | [Microsoft Translator](https://app.sensortower.com/overview/1018949559?country=US) | Camera translate | Microsoft Corporation (US) | 90k | <$5k* | n/a | US,CN,JP | 2015-08 | none listed (free/ads or no IAP) |
| 91 | [PlantNet](https://app.sensortower.com/overview/600547573?country=US) | Plant ID | Cirad-France (France) | 90k | <$5k* | n/a | FR,US,DE | 2013-02 | none listed (free/ads or no IAP) |
| 92 | [Seek by iNaturalist](https://app.sensortower.com/overview/1353224144?country=US) | Nature ID | iNaturalist (US) | 70k | <$5k* | n/a | US,GB,CA | 2018-03 | none listed (free/ads or no IAP) |
| 93 | [Be My Eyes](https://app.sensortower.com/overview/905177575?country=US) | Accessibility vision | Be My Eyes (Denmark) | 70k | <$5k* | n/a | US,CN,GB | 2014-09 | none listed (free/ads or no IAP) |
| 94 | [Bobby Approved](https://app.sensortower.com/overview/1571725006?country=US) | Barcode product scan | BA Global Holdings, LLC (US) | 60k | <$5k* | n/a | US,CA,BG | n/a | none listed (free/ads or no IAP) |
| 95 | [Flora Incognita](https://app.sensortower.com/overview/1297860122?country=US) | Plant ID | Patrick Maeder (Germany) | 30k | <$5k* | n/a | DE,CH,SE | 2018-04 | none listed (free/ads or no IAP) |
| 96 | [Skan](https://app.sensortower.com/overview/6449196562?country=US) | Skin scan | Skan Beauty Inc (Canada) | 30k | <$5k* | n/a | US,GB,DE | 2023-10 | Weekly Premium Access $5.99; Skan Premium Monthly $9.99; Skan Premium (Yearly) $39.99 |
| 97 | [CalSnap](https://app.sensortower.com/overview/6748605019?country=US) | Photo-first AI calorie | Trinh Muoi (n/a) | 20k | <$5k* | n/a | VN,JP,SG | 2025-07 | Premium (Annual) $39.99; Premium (Monthly) $9.99; Premium (Annual) $29.99 |
| 98 | [ObsIdentify](https://app.sensortower.com/overview/1464543488?country=US) | Nature ID | Observation International (Netherlands) | 10k | <$5k* | n/a | NL,BE,DE | 2023-01 | none listed (free/ads or no IAP) |
| 99 | [Open Food Facts](https://app.sensortower.com/overview/588797948?country=US) | Barcode product scan | Open Food Facts (France) | 10k | <$5k* | n/a | FR,GB,DE | 2013-01 | none listed (free/ads or no IAP) |
| 100 | [AI Hay (VN)](https://app.sensortower.com/overview/1567885193?country=US) | Homework solver | AI HAY JOINT STOCK COMPANY (Vietnam) | 10k | <$5k* | n/a | VN,SG,US | 2021-05 | AI Hay Pro Monthly $2.99; 3000 Stars $0.99; 900 Stars $0.99 |
| 101 | [Caloer (VN)](https://app.sensortower.com/overview/6474173293?country=US) | Photo-first AI calorie | Nguyen Hai Anh (Vietnam) | 10k | <$5k* | n/a | VN,SG,JP | 2023-12 | Gói Caloer Premium 12 tháng (Annual) $14.99; Gói Caloer Premium 3 tháng (Quarterly) $7.99; Gói Caloer Premium 6 tháng (6 Month) $12.99 |
| 102 | [Dog Scanner](https://app.sensortower.com/overview/1447489158?country=US) | Animal ID | Siwalu Software GmbH (Germany) | 6k | <$5k* | n/a | US,GB,DE | 2019-01 | All Access (Weekly) $1.49; All Access (Monthly) $2.99; Dog Scanner Premium $13.99 |
| 103 | [AI Scanner: Image to Text](https://app.sensortower.com/overview/1225032527?country=US) | Text OCR | Govarthani Rajesh (n/a) | <5k* | <$5k* | n/a | SA,US,ID | 2017-04 | Unlimited Scans Monthly $7.99; Unlimited Scans Yearly $59.99; Premium Monthly Saver $3.99 |
| 104 | [Prizmo Go](https://app.sensortower.com/overview/1183367390?country=US) | Text OCR | Creaceed SRL (Belgium) | <5k* | <$5k* | n/a | DK,US,DE | 2017-04 | Pro Plan (monthly) $7.99; Essential Pack $23.99; Pro Plan (yearly) $19.99 |
| 105 | [Apple Translate](https://app.sensortower.com/overview/1514844618?country=US) | Camera translate | Apple (US) | <5k* | <$5k* | n/a | TW,PL,KR | 2020-06 | none listed (free/ads or no IAP) |
| 106 | [Seeing AI](https://app.sensortower.com/overview/999062298?country=US) | Accessibility vision | Microsoft Corporation (US) | <5k* | <$5k* | n/a | US,GB,JP | 2017-07 | none listed (free/ads or no IAP) |
| 107 | [ShopSavvy](https://app.sensortower.com/overview/338828953?country=US) | QR/barcode | ShopSavvy, Inc. (US) | <5k* | <$5k* | n/a | US,GB,CA | 2009-11 | ShopSavvy Pro (Monthly) $2.99; ShopSavvy Pro (Annual) $29.99; ShopSavvy Enterprise All (Monthly) $69.99 |
| 108 | [Calife: AI Calorie Tracker](https://app.sensortower.com/overview/6779546212?country=US) | Photo-first AI calorie | Core AI (Singapore) | <5k* | <$5k* | n/a | IT,PL,DK | 2026-07 | Premium Yearly $39.99; Premium Yearly $19.99; Premium Yearly $39.99 |

#### Other cross-checks and third-party estimates
- Earlier Sensor Tower snapshots (from search-engine snippets of the same pages) give CamScanner 3M downloads/$7M in Feb 2026 against $8M in Aug 2026, and Adobe Scan 800k/$2M in Mar 2026 against 700k/$2M in Aug 2026 — [Sensor Tower CamScanner](https://app.sensortower.com/overview/388627783?country=US); [Sensor Tower Adobe Scan](https://app.sensortower.com/overview/1199564834?country=US)
- An undated older snippet showed PictureThis at about $5M/month on iOS and $700k on Google Play. It is $9M in Aug 2026 — [Sensor Tower PictureThis](https://sensortower.com/ios/us/glority-global-group-ltd/app/picturethis-plant-identifier/1252497129/)
- A 2026 article citing Sensor Tower put MyFitnessPal at "roughly 900K downloads and $13M in revenue per month". The August 2026 public estimate is 600k and $12M — [The Next Web](https://thenextweb.com/news/nnovative-calorie-tracking-apps-2026)
- Appfigures (May 2025) found consumer spending on **identifier apps** reached **$27M in one month** across the App Store and Google Play, from **1,328** identifier apps. Coin identifiers were 9% of apps but 13% of revenue ($3.5M/month). Rock/gem identifiers were just over $1M (4%) — [Appfigures Insights, 9 May 2025](https://appfigures.com/resources/insights/20250509?f=1)
- Microsoft Lens, a formerly major scanner, had 50M Google Play downloads and about 142k App Store ratings when Microsoft retired it — [BleepingComputer](https://www.bleepingcomputer.com/news/microsoft/microsoft-is-retiring-the-lens-scanner-app-for-ios-android/)

#### User and download claims made in App Store listings (self-reported by publishers, not audited)
- CamScanner "Trusted by 300M+ users"; iScanner "trusted by 145M+ users"; Scanner (Luni) "30M+ users"; iTranslate "200 million downloads and over 1 million App Store reviews"; Symbolab "over 300 million users"; Foodvisor "over 15 million users"; Lose It! "57 million users"; Lifesum "65 million users"; Yuka "85 million users" (database of 4M food and 2M cosmetic products); Vivino "70 million wine lovers"; QR Reader for iPhone (TapMedia) "over 100 million users"; Expensify "more than 15 million people"; Answer.AI "6 million+ learners"; Picture Insect "over 3 million insect enthusiasts"; Be My Eyes "more than 7 million volunteers" — all from the App Store descriptions as mirrored on each app's [Sensor Tower page](https://app.sensortower.com/overview/1040093707?country=US) (full_description field, fetched 27 Sep 2026)
- Photomath: 220M downloads globally as of 2021, before Google's acquisition (announced May 2022) — [Wikipedia – Photomath (citing TechCrunch 2021)](https://en.wikipedia.org/wiki/Photomath)
- Flora Incognita: more than 10 million downloads since its 2018 launch (as of May 2026) — [Max-Planck-Gesellschaft](https://www.mpg.de/26484618/flora-incognita)
- Pl@ntNet: used by more than 32 million users (Jan 2026); its API reached 100 million identifications (Feb 2026) — [Pl@ntNet](https://plantnet.org/en/2026/02/02/the-plntnet-api-reaches-100-million-identifications/)
- Gauth (ByteDance): 2M peak global DAU in 2024 and about 700,000 downloads/day by March 2024 — [Forbes, Apr 2024](https://www.forbes.com/sites/emilybaker-white/2024/04/03/gauth-bytedance-tiktok-homework-app/); #1 in US Education downloads for six consecutive days in Q3 2025 — [FoxData](https://foxdata.com/en/blogs/bytedances-gauth-ai-study-companion-dominates-2025-us-education-charts-as-top-ai-homework-helper/)

#### Ratings and rating counts by storefront (Apple iTunes Lookup API, 27 Sep 2026; format = average stars (number of ratings); App names link to the US App Store listing)
| App | US rating (count) | VN | DE | GB | FR | IT | ES | NL | SE |
|---|---|---|---|---|---|---|---|---|---|
| [MyFitnessPal](https://apps.apple.com/us/app/id341232718) | 4.71 (2,365,555) | 4.8 (6,551) | 4.52 (79,803) | 4.7 (471,491) | 4.62 (51,834) | 4.58 (32,864) | 4.63 (30,518) | 4.55 (41,197) | 4.41 (10,986) |
| [PictureThis](https://apps.apple.com/us/app/id1252497129) | 4.8 (1,116,384) | 4.72 (1,015) | 4.63 (96,216) | 4.74 (167,262) | 4.68 (70,250) | 4.64 (43,488) | 4.64 (32,551) | 4.61 (20,457) | 4.59 (5,506) |
| [CamScanner](https://apps.apple.com/us/app/id388627783) | 4.84 (1,922,433) | 4.83 (403,823) | 4.67 (88,934) | 4.8 (125,029) | 4.74 (187,380) | 4.77 (112,820) | 4.79 (146,220) | 4.72 (11,703) | 4.77 (5,870) |
| [Yazio](https://apps.apple.com/us/app/id946099227) | 4.7 (50,831) | 4.81 (6,742) | 4.62 (443,452) | 4.68 (12,244) | 4.67 (143,596) | 4.63 (99,315) | 4.65 (34,713) | 4.59 (27,892) | 4.51 (9,110) |
| [iScanner (BPMobile)](https://apps.apple.com/us/app/id1040093707) | 4.76 (1,403,273) | 4.8 (26,512) | 4.6 (220,528) | 4.68 (163,825) | 4.59 (287,500) | n/a | n/a | 4.54 (43,699) | 4.55 (15,548) |
| [Scanner App - Scan PDF & Docs](https://apps.apple.com/us/app/id1568660349) | 4.61 (35,192) | 4.77 (2,113) | 4.39 (2,078) | 4.54 (4,045) | 4.5 (2,109) | 4.57 (1,434) | 4.56 (2,412) | 4.32 (661) | 4.37 (387) |
| [Translate Now](https://apps.apple.com/us/app/id1348028646) | 4.7 (366,814) | 4.62 (52,540) | 4.57 (29,605) | 4.66 (22,777) | 4.51 (20,262) | 4.63 (14,136) | 4.56 (7,277) | 4.52 (5,194) | 4.55 (2,917) |
| [Adobe Scan](https://apps.apple.com/us/app/id1199564834) | 4.88 (1,593,738) | 4.86 (71,967) | 4.78 (326,722) | 4.83 (194,820) | 4.78 (232,994) | 4.8 (223,609) | 4.81 (112,136) | 4.74 (55,714) | 4.74 (26,133) |
| [Cal AI](https://apps.apple.com/us/app/id6480417616) | 4.8 (366,884) | 4.89 (2,342) | 4.71 (10,286) | 4.73 (27,144) | 4.71 (12,079) | 4.71 (7,915) | 4.75 (17,205) | 4.68 (3,496) | 4.7 (3,021) |
| [Foodvisor](https://apps.apple.com/us/app/id1064020872) | 4.59 (17,610) | 4.76 (117) | 4.44 (6,054) | 4.56 (3,467) | 4.58 (72,303) | 4.55 (5,102) | 4.58 (5,167) | 4.51 (3,993) | 4.46 (1,987) |
| [Yuka](https://apps.apple.com/us/app/id1092799236) | 4.82 (99,975) | n/a | 4.79 (11,505) | 4.84 (27,727) | 4.72 (295,537) | 4.81 (46,480) | 4.77 (47,330) | n/a | n/a |
| [Traductor GO](https://apps.apple.com/us/app/id1570134612) | 4.4 (20,237) | 4.64 (3,135) | 4.2 (2,872) | 4.32 (3,092) | 4.3 (3,611) | 4.36 (2,035) | 4.31 (2,256) | 4.21 (648) | 4.13 (630) |
| [Lose It!](https://apps.apple.com/us/app/id297368629) | 4.77 (778,599) | 4.75 (936) | 4.58 (3,969) | 4.69 (41,385) | 4.6 (1,723) | 4.59 (1,543) | 4.58 (1,820) | 4.52 (2,005) | 4.51 (959) |
| [iTranslate](https://apps.apple.com/us/app/id288113403) | 4.73 (530,225) | 4.66 (16,793) | 4.57 (88,634) | 4.65 (58,788) | 4.56 (85,257) | 4.61 (64,712) | 4.59 (41,823) | 4.45 (12,792) | 4.49 (11,018) |
| [PlantIn](https://apps.apple.com/us/app/id1527399597) | 4.56 (229,362) | 4.75 (255) | 4.37 (5,186) | 4.4 (6,150) | 4.45 (10,481) | 4.46 (4,211) | 4.44 (4,819) | 4.33 (1,476) | 4.34 (1,428) |
| [Gauth](https://apps.apple.com/us/app/id1542571008) | 4.83 (1,505,433) | 4.74 (122,410) | 4.73 (9,050) | 4.76 (163,474) | 4.74 (14,442) | 4.68 (37,996) | 4.76 (5,045) | 4.77 (437) | 4.74 (775) |
| [Calo: AI Food Calorie Counter](https://apps.apple.com/us/app/id6447434453) | 4.71 (25,057) | 5 (1) | 4.49 (1,914) | 4.63 (4,915) | 4.48 (2,381) | 4.41 (1,310) | 4.45 (704) | 4.41 (924) | 4.44 (1,636) |
| [Rock Identifier](https://apps.apple.com/us/app/id1546796934) | 4.65 (80,725) | 4.59 (173) | 4.55 (3,182) | 4.58 (8,049) | 4.58 (3,355) | 4.58 (1,600) | 4.61 (1,598) | 4.51 (1,371) | 4.53 (862) |
| [Lifesum](https://apps.apple.com/us/app/id286906691) | 4.65 (150,759) | 4.72 (883) | 4.55 (81,588) | 4.6 (28,110) | 4.55 (34,050) | 4.55 (27,266) | 4.45 (9,850) | 4.55 (23,754) | 4.54 (69,387) |
| [ScanGuru](https://apps.apple.com/us/app/id1040149161) | 4.6 (93,187) | 4.53 (7,853) | 4.42 (7,442) | 4.49 (10,734) | 4.4 (26,569) | 4.43 (12,698) | 4.4 (12,352) | 4.36 (1,918) | 4.39 (2,100) |
| [QR Code Reader (AIR APPS)](https://apps.apple.com/us/app/id1226650677) | 4.66 (72,430) | 4.6 (11,032) | 4.53 (37,333) | 4.58 (14,040) | 4.43 (6,731) | 4.57 (2,272) | 4.44 (8,008) | 4.37 (1,657) | 4.38 (745) |
| [Scan Shot PDF Scanner](https://apps.apple.com/us/app/id1575194801) | 4.7 (61,661) | 4.74 (4,329) | 4.54 (12,319) | 4.65 (9,970) | 4.62 (18,192) | 4.67 (8,439) | 4.65 (6,467) | 4.56 (1,246) | 4.58 (506) |
| [CoinSnap](https://apps.apple.com/us/app/id1634551626) | 4.72 (304,375) | 4.67 (100) | 4.65 (15,314) | 4.72 (11,489) | 4.68 (13,771) | 4.69 (7,600) | 4.68 (6,275) | 4.7 (1,158) | 4.61 (438) |
| [Scanner Pro (Readdle)](https://apps.apple.com/us/app/id333710667) | 4.87 (335,941) | 4.87 (3,637) | 4.75 (87,797) | 4.81 (29,178) | 4.75 (30,542) | 4.77 (26,745) | 4.78 (14,631) | 4.71 (11,648) | 4.74 (5,277) |
| [Tiny Scanner](https://apps.apple.com/us/app/id595563753) | 4.82 (182,442) | 4.77 (1,439) | 4.66 (10,468) | 4.76 (19,725) | 4.68 (6,744) | 4.67 (6,050) | 4.65 (1,911) | 4.62 (4,388) | 4.64 (3,372) |
| [Scanner App: Scan Documents (VN #2)](https://apps.apple.com/us/app/id6753972326) | 4.58 (1,430) | 4.64 (2,069) | 4.44 (70) | 4.59 (130) | 4.48 (60) | 4.48 (42) | 4.8 (41) | 4.53 (30) | 4.89 (9) |
| [CoinIn](https://apps.apple.com/us/app/id1672111368) | 4.67 (101,016) | 4.6 (48) | 4.58 (2,469) | 4.64 (2,909) | 4.62 (3,001) | 4.6 (2,315) | 4.66 (353) | 4.55 (108) | 4.42 (40) |
| [Translate AI - Live Translate](https://apps.apple.com/us/app/id6738304985) | 4.3 (4,071) | 4.71 (554) | 4.08 (1,050) | 4.23 (775) | 4.31 (870) | 4.29 (422) | 4.33 (387) | 4.09 (266) | 4.05 (127) |
| [BitePal](https://apps.apple.com/us/app/id6479529917) | 4.66 (55,390) | 4.83 (167) | 4.37 (4,532) | 4.45 (8,054) | 4.44 (7,254) | 4.29 (6,116) | 4.45 (7,025) | 4.39 (1,318) | 4.4 (574) |
| [TapScanner](https://apps.apple.com/us/app/id1382564905) | 4.66 (26,809) | 4.73 (13,527) | 4.58 (3,621) | 4.61 (5,886) | 4.59 (8,750) | 4.62 (4,031) | 4.61 (4,530) | 4.53 (1,272) | 4.53 (842) |
| [HoloDex - TCG Scan](https://apps.apple.com/us/app/id6747442689) | 4.82 (23,294) | 4.85 (130) | 4.74 (864) | 4.8 (2,535) | 4.79 (513) | 4.71 (465) | 4.81 (379) | 4.74 (1,274) | 4.78 (298) |
| [AntiqSnap](https://apps.apple.com/us/app/id6752929120) | 4.68 (31,382) | 0 (0) | 4.42 (399) | 4.57 (1,121) | 4.49 (1,016) | 4.56 (871) | 4.5 (410) | 4.38 (465) | 4.58 (36) |
| [Scanner - Luni](https://apps.apple.com/us/app/id1291962681) | 4.73 (222,631) | 4.67 (8,135) | 4.58 (40,213) | 4.63 (33,979) | 4.6 (182,651) | 4.63 (34,043) | 4.59 (45,217) | 4.59 (3,336) | 4.59 (729) |
| [Lens Scan: Identify Anything](https://apps.apple.com/us/app/id6560107458) | 4.63 (18,691) | 4.91 (11) | 4.49 (2,190) | 4.6 (1,190) | 4.57 (1,605) | 4.59 (663) | 4.57 (1,265) | 4.5 (1,810) | 4.34 (332) |
| [Picture Insect](https://apps.apple.com/us/app/id1461694973) | 4.65 (44,527) | 4.75 (118) | 4.55 (4,771) | 4.56 (4,021) | 4.61 (3,278) | 4.6 (977) | 4.57 (719) | 4.55 (786) | 4.37 (79) |
| [Scan Hero](https://apps.apple.com/us/app/id1017261655) | 4.68 (241,999) | 4.69 (17,655) | 4.49 (16,481) | 4.58 (32,057) | 4.47 (29,690) | 4.58 (21,596) | 4.54 (21,042) | 4.48 (6,339) | 4.47 (4,442) |
| [Welmi](https://apps.apple.com/us/app/id6741707862) | 4.77 (20,118) | 4.72 (58) | 4.73 (7,410) | 4.77 (1,228) | 4.66 (15,725) | 4.68 (2,720) | 4.73 (5,711) | 4.66 (983) | 4.7 (277) |
| [Genius Scan](https://apps.apple.com/us/app/id377672876) | 4.9 (1,364,863) | 4.84 (29,421) | 4.8 (118,859) | 4.84 (100,453) | 4.79 (174,602) | 4.8 (79,733) | 4.8 (29,769) | 4.76 (28,806) | 4.78 (18,132) |
| [Photomath](https://apps.apple.com/us/app/id919087726) | 4.77 (733,141) | 4.66 (22,436) | 4.77 (48,446) | 4.6 (22,225) | 4.76 (54,317) | 4.65 (88,479) | 4.76 (45,777) | 4.77 (6,732) | 4.8 (15,341) |
| [FoodPilot AI Calorie Tracker](https://apps.apple.com/us/app/id6738115267) | 4.67 (2,615) | 4.18 (11) | 4.09 (311) | 4.53 (325) | 3.98 (270) | 3.74 (191) | 4.16 (164) | 3.5 (28) | 4.38 (37) |
| [Vivino](https://apps.apple.com/us/app/id414461255) | 4.84 (137,612) | 4.88 (502) | 4.67 (25,104) | 4.78 (29,387) | 4.7 (36,256) | 4.72 (34,055) | 4.74 (21,268) | 4.67 (21,893) | 4.68 (14,843) |
| [InstantTranslator: AI Translate](https://apps.apple.com/us/app/id6636468891) | 4.4 (4,199) | 4.59 (340) | 3.5 (433) | 3.99 (152) | 4.07 (241) | 4.21 (204) | 4.13 (183) | 3.96 (52) | 3.96 (53) |
| [QR Reader for iPhone (TapMedia)](https://apps.apple.com/us/app/id368494609) | 4.71 (1,435,746) | 4.64 (2,599) | 4.59 (21,205) | 4.67 (55,412) | 4.5 (12,803) | 4.65 (46,747) | 4.6 (45,602) | 4.51 (43,309) | 4.5 (36,775) |
| [EveryScan (LensAI) Identifier](https://apps.apple.com/us/app/id1663862037) | 4.33 (9,903) | n/a | 3.76 (202) | 4.05 (304) | 4.05 (119) | 4.39 (79) | 3.78 (32) | 4.48 (25) | 3.83 (24) |
| [Google app (Lens)](https://apps.apple.com/us/app/id284815942) | 4.65 (5,134,466) | 4.51 (549,765) | 4.49 (453,391) | 4.6 (621,005) | 4.53 (532,858) | 4.57 (334,029) | 4.6 (294,489) | 4.44 (107,441) | 4.48 (92,479) |
| [Gizmo: AI Tutor](https://apps.apple.com/us/app/id1610516671) | 4.76 (13,819) | 4.78 (295) | 4.6 (839) | 4.64 (12,816) | 4.67 (1,647) | 4.57 (388) | 4.63 (471) | 4.61 (658) | 4.66 (1,152) |
| [FoilSnap: TCG Card Scanner](https://apps.apple.com/us/app/id6752642525) | 4.76 (13,771) | 5 (3) | 4.55 (969) | 4.69 (1,252) | 4.6 (318) | 4.71 (513) | 4.79 (375) | 4.6 (81) | 5 (3) |
| [PlantAI: Identifier & Diagnose](https://apps.apple.com/us/app/id1664437810) | 4.55 (9,306) | 4.62 (13) | 4.25 (318) | 4.6 (1,047) | 4.42 (458) | 4.46 (953) | 4.44 (923) | 4 (79) | 4.09 (45) |
| [Question.AI](https://apps.apple.com/us/app/id6449486871) | 4.7 (162,747) | 4.44 (3,846) | 4.71 (202) | 4.6 (994) | 4.61 (683) | 4.65 (167) | 4.68 (141) | 4.8 (55) | 4.6 (62) |
| [Picture Bird](https://apps.apple.com/us/app/id1474586978) | 4.73 (40,261) | 4.85 (41) | 4.53 (2,610) | 4.53 (4,300) | 4.63 (3,903) | 4.69 (906) | 4.67 (812) | 4.45 (1,392) | 4.31 (195) |
| [Plant App](https://apps.apple.com/us/app/id1595795215) | 4.7 (55,454) | 4.8 (3,524) | 4.64 (4,104) | 4.72 (14,110) | 4.64 (6,997) | 4.7 (4,321) | 4.7 (4,672) | 4.55 (2,604) | 4.56 (1,022) |
| [Picture Mushroom](https://apps.apple.com/us/app/id1474578078) | 4.72 (24,349) | 4.94 (18) | 4.54 (7,303) | 4.65 (5,599) | 4.55 (6,238) | 4.63 (2,047) | 4.6 (1,159) | 4.64 (892) | 4.64 (298) |
| [CamCard](https://apps.apple.com/us/app/id349447615) | 4.7 (90,277) | 4.78 (2,292) | 4.54 (11,044) | 4.61 (7,084) | 4.5 (9,889) | 4.59 (3,298) | 4.6 (3,805) | 4.47 (3,398) | 4.47 (394) |
| [Evernote Scannable](https://apps.apple.com/us/app/id883338188) | 4.85 (417,937) | 4.82 (20,330) | 4.74 (35,486) | 4.79 (63,916) | 4.75 (53,545) | 4.76 (14,627) | 4.75 (19,798) | 4.7 (32,789) | 4.72 (10,155) |
| [Chegg Study](https://apps.apple.com/us/app/id385758163) | 4.69 (204,663) | 4.46 (666) | 4.1 (202) | 4.59 (1,610) | 4.57 (275) | 4.7 (94) | 4.62 (100) | 4.38 (81) | 4.71 (177) |
| [Plantum](https://apps.apple.com/us/app/id1476047194) | 4.59 (119,276) | 4.68 (1,829) | 4.46 (2,681) | 4.48 (7,731) | 4.5 (6,237) | 4.57 (3,777) | 4.49 (2,455) | 4.4 (1,070) | 4.31 (514) |
| [Lens AI & Reverse Image Search](https://apps.apple.com/us/app/id6753348682) | 3.94 (467) | 5 (7) | 3.85 (52) | 3.68 (47) | 4.09 (32) | 4.32 (22) | 3.5 (10) | 4.4 (5) | 5 (2) |
| [SnapCal](https://apps.apple.com/us/app/id6747375157) | 4.82 (12,581) | 4.75 (85) | 4.7 (2,470) | 4.78 (4,867) | 4.67 (1,545) | 4.77 (84) | 4.74 (973) | 4.7 (213) | 4.72 (99) |
| [Coin ID (AIBY)](https://apps.apple.com/us/app/id1665672552) | 4.49 (44,322) | 4.35 (17) | 4.45 (669) | 4.48 (560) | 4.51 (464) | 4.46 (354) | 4.54 (375) | 4.41 (81) | 4.59 (41) |
| [Planto](https://apps.apple.com/us/app/id1531728753) | 4.69 (8,420) | 4.5 (32) | 4.61 (2,396) | 4.68 (1,023) | 4.65 (3,311) | 4.69 (4,779) | 4.41 (319) | 4.52 (1,784) | 4.49 (2,419) |
| [Brainly](https://apps.apple.com/us/app/id745089947) | 4.72 (284,174) | 4.51 (330) | 4.74 (872) | 4.6 (4,923) | 4.76 (70,299) | 4.66 (529) | 4.72 (7,927) | 4.66 (126) | 4.5 (86) |
| [Quizard AI](https://apps.apple.com/us/app/id1667996582) | 4.73 (58,781) | 4.51 (202) | 4.6 (122) | 4.72 (387) | 4.31 (13) | 4.71 (260) | 4.58 (337) | 4.83 (109) | 4.62 (116) |
| [ThriftAI: Profit Identifier](https://apps.apple.com/us/app/id6746565278) | 4.77 (20,472) | 5 (2) | 4.61 (51) | 4.7 (491) | 4.52 (90) | 4.33 (52) | 4.81 (21) | 4.2 (55) | 4.5 (48) |
| [DeepL](https://apps.apple.com/us/app/id1552407475) | 4.77 (13,279) | 4.51 (160) | 4.76 (30,935) | 4.76 (3,062) | 4.78 (12,845) | 4.8 (4,038) | 4.81 (4,944) | 4.72 (2,275) | 4.67 (443) |
| [Dext](https://apps.apple.com/us/app/id418327708) | 4.78 (7,451) | 4.56 (9) | 4.76 (67) | 4.78 (28,110) | 4.78 (19,995) | 4.93 (61) | 4.8 (88) | 4.5 (123) | 5 (18) |
| [Blossom](https://apps.apple.com/us/app/id1487453649) | 4.61 (68,761) | 4.65 (379) | 4.34 (2,928) | 4.56 (6,453) | 4.42 (2,214) | 4.39 (793) | 4.24 (1,507) | 4.41 (1,048) | 4.3 (627) |
| [Mathway](https://apps.apple.com/us/app/id467329677) | 4.88 (424,606) | 4.63 (2,815) | 4.76 (1,139) | 4.83 (5,453) | 4.82 (1,572) | 4.54 (1,103) | 4.72 (1,331) | 4.91 (160) | 4.75 (209) |
| [Answer.AI](https://apps.apple.com/us/app/id6446047896) | 4.69 (166,312) | 4.42 (74) | 4.62 (39) | 4.65 (173) | 4.47 (53) | 4.37 (41) | 4.6 (43) | 4.69 (26) | 4.56 (16) |
| [SimplyWise](https://apps.apple.com/us/app/id1538521095) | 4.85 (37,677) | n/a | n/a | n/a | n/a | n/a | n/a | n/a | n/a |
| [MonPrice: Card Value Scanner](https://apps.apple.com/us/app/id6741683137) | 4.76 (802) | 4.89 (73) | 4.46 (221) | 4.76 (78) | 4.65 (246) | 4.56 (138) | 4.56 (193) | 4.52 (120) | 4.39 (82) |
| [Expensify](https://apps.apple.com/us/app/id471713959) | 4.63 (157,133) | 4.86 (128) | 4.48 (1,418) | 4.55 (12,747) | 4.64 (1,565) | 4.58 (706) | 4.69 (1,141) | 4.42 (876) | 4.37 (457) |
| [VinylSnap](https://apps.apple.com/us/app/id6748595105) | 4.66 (3,395) | 0 (0) | 4.53 (371) | 4.63 (644) | 4.65 (476) | 4.54 (564) | 4.62 (210) | 4.47 (151) | 4.55 (95) |
| [SwiftScan (ex-Scanbot)](https://apps.apple.com/us/app/id834854351) | 4.76 (18,941) | 4.76 (1,365) | 4.62 (36,582) | 4.74 (6,107) | 4.66 (15,256) | 4.73 (7,722) | 4.69 (2,881) | 4.59 (3,681) | 4.63 (923) |
| [SnapCalorie](https://apps.apple.com/us/app/id1574239307) | 4.73 (6,679) | 4.78 (55) | 4.56 (389) | 4.69 (954) | 4.58 (274) | 4.61 (89) | 4.62 (224) | 4.66 (103) | 4.61 (132) |
| [TurboScan (free)](https://apps.apple.com/us/app/id1017559099) | 4.91 (102,537) | 4.86 (96) | 4.83 (1,759) | 4.86 (3,613) | 4.83 (1,549) | 4.84 (1,263) | 4.83 (1,468) | 4.78 (1,283) | 4.8 (590) |
| [SCAN ACE](https://apps.apple.com/us/app/id556500145) | 4.84 (39,200) | 4.8 (81) | 4.7 (3,018) | 4.8 (2,951) | 4.74 (1,243) | 4.75 (1,475) | 4.76 (522) | 4.66 (727) | 4.69 (247) |
| [Photo Translator (EVOLLY)](https://apps.apple.com/us/app/id1350347947) | 4.4 (26,857) | 4.6 (31,723) | 4.3 (1,464) | 4.33 (2,690) | 4.36 (1,763) | 4.46 (506) | 4.4 (613) | 4.32 (449) | 4.28 (275) |
| [Document Scan: PDF Scanner App (VN #4)](https://apps.apple.com/us/app/id1588273103) | 4.42 (829) | 4.6 (19,238) | 4.57 (35) | 4.65 (92) | 4.67 (66) | 4.33 (67) | 4.22 (18) | 4.07 (27) | 0 (0) |
| [CodeCheck](https://apps.apple.com/us/app/id359351047) | n/a | n/a | 4.64 (28,012) | n/a | n/a | n/a | n/a | 4.09 (53) | n/a |
| [ABBYY Business Card Reader](https://apps.apple.com/us/app/id898215947) | 4.6 (20,572) | 4.77 (492) | 4.55 (4,522) | 4.55 (3,885) | 4.5 (3,042) | 4.54 (3,473) | 4.51 (2,312) | 4.37 (1,934) | 4.33 (227) |
| [TurboScan Pro (paid)](https://apps.apple.com/us/app/id342548956) | 4.92 (296,630) | 4.81 (106) | 4.85 (2,985) | 4.88 (7,885) | 4.84 (1,823) | 4.84 (3,104) | 4.82 (5,140) | 4.79 (3,764) | 4.8 (1,548) |
| [Symbolab](https://apps.apple.com/us/app/id876942533) | 4.57 (26,206) | 4.41 (580) | 4.09 (175) | 4.37 (874) | 4.59 (297) | 4.35 (402) | 4.42 (884) | 4.36 (59) | 4.59 (117) |
| [Miiskin](https://apps.apple.com/us/app/id1214795331) | 4.52 (1,723) | 4.86 (7) | 3.71 (62) | 4.46 (698) | 4.06 (54) | 3.87 (120) | 3.97 (29) | 3.6 (99) | 3.9 (21) |
| [Google Translate](https://apps.apple.com/us/app/id414706506) | 4.29 (83,764) | 3.99 (21,351) | 3.99 (12,549) | 4.18 (8,916) | 4.12 (9,202) | 4.1 (7,803) | 4.17 (4,980) | 3.88 (2,720) | 4.04 (2,908) |
| [Fetch](https://apps.apple.com/us/app/id1182474649) | 4.85 (7,699,352) | n/a | n/a | n/a | n/a | n/a | n/a | n/a | n/a |
| [Naver Papago](https://apps.apple.com/us/app/id1147874819) | 4.69 (3,461) | 4.65 (2,166) | 4.62 (137) | 4.61 (229) | 4.6 (311) | 4.51 (72) | 4.81 (57) | 4.67 (40) | 4.54 (35) |
| [Merlin Bird ID](https://apps.apple.com/us/app/id773457673) | 4.86 (112,955) | 4.69 (13) | 4.77 (2,174) | 4.83 (11,086) | 4.85 (1,283) | 4.86 (259) | 4.85 (802) | 4.76 (1,772) | 4.82 (995) |
| [Yandex Translate](https://apps.apple.com/us/app/id584291439) | 4.69 (7,423) | 4.73 (92) | 4.67 (3,668) | 4.69 (965) | 4.64 (1,268) | 4.67 (698) | 4.7 (815) | 4.73 (226) | 4.59 (243) |
| [QR Code Reader (Komorebi)](https://apps.apple.com/us/app/id1080558159) | 4.66 (161,634) | 4.35 (3,580) | 4.63 (9,178) | 4.7 (2,179) | 4.67 (4,577) | 4.69 (735) | 4.63 (1,006) | 4.54 (778) | 4.54 (581) |
| [Microsoft Translator](https://apps.apple.com/us/app/id1018949559) | 4.75 (158,101) | 4.72 (8,134) | 4.63 (55,275) | 4.73 (24,195) | 4.61 (29,379) | 4.67 (16,233) | 4.63 (17,804) | 4.56 (6,412) | 4.62 (5,534) |
| [PlantNet](https://apps.apple.com/us/app/id600547573) | 4.59 (7,044) | 4.57 (30) | 4.62 (4,772) | 4.72 (2,413) | 4.63 (9,918) | 4.71 (3,946) | 4.68 (2,400) | 4.53 (1,668) | 4.69 (251) |
| [Seek by iNaturalist](https://apps.apple.com/us/app/id1353224144) | 4.75 (30,911) | 4.2 (20) | 4.65 (1,051) | 4.73 (3,682) | 4.62 (1,734) | 4.42 (388) | 4.61 (198) | 4.65 (665) | 4.7 (432) |
| [Be My Eyes](https://apps.apple.com/us/app/id905177575) | 4.78 (11,330) | 4.94 (117) | 4.74 (635) | 4.76 (1,388) | 4.83 (818) | 4.72 (497) | 4.75 (362) | 4.75 (183) | 4.63 (95) |
| [Bobby Approved](https://apps.apple.com/us/app/id1571725006) | 4.86 (162,041) | n/a | n/a | n/a | n/a | n/a | n/a | n/a | n/a |
| [Flora Incognita](https://apps.apple.com/us/app/id1297860122) | 4.79 (579) | 5 (1) | 4.8 (26,540) | 4.84 (649) | 4.76 (417) | 4.71 (429) | 4.84 (283) | 4.67 (252) | 4.77 (1,865) |
| [Skan](https://apps.apple.com/us/app/id6449196562) | 4.79 (9,813) | 4.92 (38) | 4.63 (731) | 4.67 (1,684) | n/a | 4.58 (250) | 4.58 (208) | 4.61 (412) | 4.65 (312) |
| [CalSnap](https://apps.apple.com/us/app/id6748605019) | 4.91 (180) | 4.82 (12,347) | 4.67 (21) | 4.82 (11) | 4.25 (4) | 0 (0) | 0 (0) | 0 (0) | 5 (5) |
| [ObsIdentify](https://apps.apple.com/us/app/id1464543488) | 2 (5) | 0 (0) | 3.9 (116) | 4.21 (19) | 4.85 (13) | 4 (1) | 3 (1) | 3.67 (215) | 4.67 (3) |
| [Open Food Facts](https://apps.apple.com/us/app/id588797948) | 4.38 (141) | 4 (4) | 4.12 (145) | 4.69 (395) | 4.45 (994) | 4.42 (38) | 4.31 (54) | 3.9 (21) | 3.33 (6) |
| [AI Hay (VN)](https://apps.apple.com/us/app/id1567885193) | 4.72 (1,556) | 4.74 (122,058) | 4.75 (52) | 4.68 (41) | 4.72 (18) | 0 (0) | 5 (4) | 4.83 (6) | 4.25 (8) |
| [Caloer (VN)](https://apps.apple.com/us/app/id6474173293) | 4.36 (72) | 4.72 (4,968) | 4.73 (11) | 5 (4) | 4.14 (7) | 0 (0) | 0 (0) | 0 (0) | 5 (3) |
| [Dog Scanner](https://apps.apple.com/us/app/id1447489158) | 4.63 (36,683) | 4.35 (37) | 4.43 (2,621) | 4.49 (2,142) | 4.44 (899) | 4.49 (736) | 4.51 (631) | 4.46 (258) | 4.41 (130) |
| [AI Scanner: Image to Text](https://apps.apple.com/us/app/id1225032527) | 4.62 (9,182) | 4.72 (1,006) | 4.54 (613) | 4.64 (723) | 4.66 (621) | 4.54 (153) | 4.56 (107) | 4.36 (84) | 4.52 (124) |
| [Prizmo Go](https://apps.apple.com/us/app/id1183367390) | 4.36 (278) | 5 (2) | 3.56 (192) | 3.94 (100) | 3.93 (150) | 4.12 (78) | 3.61 (56) | 3.67 (46) | 3.73 (41) |
| Apple Translate | 2.35 (9,959) | 2.33 (1,111) | 2.17 (2,593) | 2.27 (1,364) | 2.51 (1,515) | 2.06 (1,168) | 1.82 (830) | 2.26 (349) | 1.54 (291) |
| [Seeing AI](https://apps.apple.com/us/app/id999062298) | 4.3 (631) | n/a | 4.06 (159) | 3.95 (150) | 4.1 (83) | 4.27 (84) | 4.01 (72) | 3.44 (34) | 4.45 (22) |
| [ShopSavvy](https://apps.apple.com/us/app/id338828953) | 4.43 (9,986) | 0 (0) | 0 (0) | 3.59 (39) | 2.67 (6) | 0 (0) | 1 (2) | 1 (2) | 1 (1) |
| [Calife: AI Calorie Tracker](https://apps.apple.com/us/app/id6779546212) | 4.69 (62) | 5 (10) | 4.88 (17) | 4.91 (23) | 4.81 (16) | 3.83 (6) | 4.75 (8) | 4.3 (23) | 4.61 (18) |

#### Vietnam-specific highlights (rating counts via [iTunes Lookup VN](https://itunes.apple.com/lookup?id=388627783&country=vn); charts via [VN RSS feeds](https://itunes.apple.com/vn/rss/topgrossingapplications/limit=100/genre=6000/json), 27 Sep 2026)
- Largest VN rating bases among the tracked apps are the Google app (Lens) at 549,765, CamScanner at 403,823, Gauth at 122,410, AI Hay (a Vietnamese AI app) at 122,058, Adobe Scan at 71,967, Translate Now at 52,540, Photo Translator by EVOLLY (Vietnam-based publisher) at 31,723, Genius Scan at 29,421, iScanner at 26,512 and Photomath at 22,436 — [iTunes Lookup API, country=vn](https://itunes.apple.com/lookup?id=388627783&country=vn)
- Sensor Tower lists **Vietnam among the top-3 countries** for Gauth (US, VN, GB), Question.AI (US, ID, VN), Photo Translator EVOLLY (US, VN, TH), "Scanner App: Scan Documents" by Uniteman (MY, VN, PH; 900k worldwide downloads/month) and "Document Scan: PDF Scanner App" (VN, TH, SA) — [Sensor Tower Gauth](https://app.sensortower.com/overview/1542571008?country=US); [Sensor Tower Uniteman Scanner](https://app.sensortower.com/overview/6753972326?country=US)

### Inferences
- **Document scanning is the largest and most crowded camera-app revenue pool.** At least 19 apps each earn $10k to $8M a month on iOS. The segment is split between big brands (CamScanner, Adobe Scan, iScanner, Scanner Pro, Genius Scan) and many ad-driven "weekly-subscription" clones from Turkey, Ukraine, Hong Kong and Spain (TapSuite, ScanGuru, Scan Shot, Uniteman). Those clones reach $0.5M to $3M a month with small rating bases, which points to paid user acquisition rather than organic demand.
- **Identifier apps are dominated by one Chinese group.** Next Vision Limited publishes CoinSnap, Rock Identifier, Picture Insect, Bird and Mushroom, AntiqSnap, FoilSnap, VinylSnap and Calo. Its sibling Glority publishes PictureThis and PlantAI. Adding their Sensor Tower estimates gives roughly **$12.8M/month on iOS** (Glority ≈$9.2M, Next Vision ≈$3.6M across 9 apps) for the two brands together (my arithmetic from the table).
- **Free, non-profit or big-tech vision apps have large reach but earn almost nothing on iOS.** Google Translate (2M downloads/month), Merlin (300k), Papago (300k), PlantNet (90k), Seek (70k) and Be My Eyes (70k) all show floor-level revenue. Among offline-capable, privacy-first apps, revenue is concentrated in scanners (Genius Scan, iScanner, ScanGuru, SwiftScan) and in Yuka's offline Premium.
- Sensor Tower's Cal AI estimate ($2M/month iOS gross, about $24M a year) is below the publicly reported $30–50M revenue/ARR (see Q3). Either Sensor Tower under-estimates this app or much of its revenue comes from Android or web billing. **Treat Sensor Tower figures as order-of-magnitude values.**

### Gaps
- No lifetime iOS download totals were available from free sources for most apps. The only lifetime figures are publisher claims (above) or dated press figures. Lifetime downloads are **n/a** for most rows.
- **US-only and Vietnam-only download and revenue estimates** were not available. Sensor Tower's public field is worldwide only, and the paid per-country data sits behind a login. Europe-per-country revenue is likewise n/a; use the chart ranks (Q4) and rating counts as proxies.
- Sensor Tower's public figures are rounded to one significant figure. Precise figures (e.g., $2.4M vs $2M) need a paid Sensor Tower, Appfigures or AppMagic account.
- Microsoft Lens could not be measured because it was removed from the App Store on 9 Feb 2026.

## Q2. Which features run fully on-device/offline and which need the cloud?

### Takeaway
Offline capability splits cleanly by category. **Scanning, OCR, translation and a few nature identifiers work offline.** Examples are Apple's built-in Live Text/Translate, Google Translate with downloaded language packs, Genius Scan, iScanner, ScanGuru, SwiftScan, Prizmo Go, Seek, Merlin Photo ID, PlantNet's embedded mode, Yuka Premium's offline mode and Dog Scanner Premium. **Most high-grossing AI identifier, homework and calorie apps depend on the cloud.** Examples are Cal AI (OpenAI/Anthropic models), Flora Incognita (server-side identification), Adobe Scan OCR (Document Cloud) and Google Lens homework.

### Cited Findings

#### Offline / on-device status matrix
| App | Core camera/vision function | Offline status (as documented) | Evidence |
|---|---|---|---|
| Apple Translate + Live Text (built into iOS) | Camera text translation, text recognition | **Fully on-device** for downloaded languages ("On-device mode – Enable a fully offline experience"); translations run on the Neural Engine | [App Store listing via Sensor Tower](https://app.sensortower.com/overview/1514844618?country=US); [Wikipedia – Translate (Apple)](https://en.wikipedia.org/wiki/Translate_(Apple)) |
| Apple Visual Look Up (iOS Photos) | Identify plants, pets, landmarks, art | "Uses Apple's on-device intelligence" (some features US-only) | [The Mac Observer 2026 guide](https://www.macobserver.com/tips/how-to/visual-lookup-the-google-lens-alternative-for-iphone-2025-guide/) |
| Google Translate | Instant camera translation | **Offline after downloading language packs**, including camera translation for downloaded languages | [Google Translate Help – iOS offline](https://support.google.com/translate/answer/6142473?hl=en&co=GENIE.Platform%3DiOS); listing: "Offline: Translate with no internet connection" ([ST](https://app.sensortower.com/overview/414706506?country=US)) |
| Google app / Google Lens | Visual search, homework, translate | Cloud; third-party guides report that Lens math/homework solving needs an active connection (weak source) | [How-To Geek](https://www.howtogeek.com/696271/how-to-solve-math-problems-using-google-lens/) |
| InstantTranslator | Camera/text translate | Offline via "downloaded on-device language models"; "Offline translation is powered by Google Translate" | [ST listing](https://app.sensortower.com/overview/6636468891?country=US) |
| Translate Now, Traductor GO, Translate AI – Live Translate, Photo Translator (EVOLLY) | Camera/voice translate | Each lists an "Offline Mode" in its App Store description | [Translate Now](https://app.sensortower.com/overview/1348028646?country=US); [Traductor GO](https://app.sensortower.com/overview/1570134612?country=US); [Translate AI](https://app.sensortower.com/overview/6738304985?country=US); [EVOLLY](https://app.sensortower.com/overview/1350347947?country=US) |
| Naver Papago | Photo/text translate | Offline **text** translation only is advertised | [ST listing](https://app.sensortower.com/overview/1147874819?country=US) |
| Yandex Translate | Photo/text translate | Offline for selected languages into English (download in Settings) | [ST listing](https://app.sensortower.com/overview/584291439?country=US) |
| iTranslate | Camera/voice translate | Partial: offline mode needs language-pack downloads, yet the listing also says "An internet connection is required to use the app" | [ST listing](https://app.sensortower.com/overview/288113403?country=US) |
| DeepL | Photo/text translate | No offline mode advertised in the listing (inferred cloud) | [ST listing](https://app.sensortower.com/overview/1552407475?country=US) |
| Genius Scan (France) | Doc scan + OCR | **On-device**: "On-device document processing"; SDK: "all the SDK treatments, including text recognition, run offline on-device" | [ST listing](https://app.sensortower.com/overview/377672876?country=US); [Genius Scan SDK privacy](https://geniusscansdk.com/legal/privacy-security/) |
| iScanner (BPMobile) | Doc scan, edit | **Offline**: "scanning, editing, and viewing files all work offline; only cloud sync and backup" need internet | [ST listing FAQ](https://app.sensortower.com/overview/1040093707?country=US) |
| ScanGuru | Doc scan | "You don't need an Internet connection as all scans are stored locally" | [ST listing](https://app.sensortower.com/overview/1040149161?country=US) |
| SwiftScan (ex-Scanbot) | Doc scan, QR | "All document-related activity happens on your device, or with the cloud backup provider you choose" | [ST listing](https://app.sensortower.com/overview/834854351?country=US) |
| Prizmo Go (Belgium) | Text OCR | "Robust neural network-based on-device OCR (works without internet connection) + Apple OCR", with optional cloud OCR | [ST listing](https://app.sensortower.com/overview/1183367390?country=US) |
| Adobe Scan | Doc scan + OCR | **Conflicting/unverified.** The listing says scans are "automatically saved to Adobe Document Cloud". A search-engine summary said OCR needs Document Cloud (internet), but the only page found, a low-quality LifeTips article from Jan 2026, claims Adobe Scan OCR runs locally in 47 languages | [ST listing](https://app.sensortower.com/overview/1199564834?country=US); [LifeTips (Alibaba), 8 Jan 2026](https://lifetips.alibaba.com/tech-efficiency/free-offline-ocr-for-any-language) |
| Microsoft Lens | Doc scan + OCR | **Retired**: removed from stores 9 Feb 2026, scanning stopped 9 Mar 2026; Microsoft points users to OneDrive scan (which saves only to OneDrive) | [BleepingComputer](https://www.bleepingcomputer.com/news/microsoft/microsoft-is-retiring-the-lens-scanner-app-for-ios-android/); [Microsoft Support](https://support.microsoft.com/en-us/lens/retirement-of-microsoft-lens) |
| Seek by iNaturalist | Species ID (live camera) | **Fully offline**: "the only app that does not require internet access to operate"; real-time evaluation of the live video feed | [iNaturalist post #56](https://www.inaturalist.org/posts/44986-56-seek-offline-database-no-wifi-google-lens-plantnet-flora-incognita-plant-id) |
| Merlin Bird ID (Cornell) | Bird photo ID | "Photo ID works completely offline", covering 6,900+ species; downloadable Bird Packs | [Merlin Photo ID help](https://support.ebird.org/en/support/solutions/articles/48000966224-merlin-photo-id); [Bird Packs](https://support.ebird.org/en/support/solutions/articles/48000966223-my-offline-birds) |
| Pl@ntNet (France) | Plant ID | **Offline/embedded mode**: a compressed identification model, mobile app only, with optional regional flora thumbnails | [Pl@ntNet docs](https://docs.plantnet.org/en/tutorials/install-the-offline-embedded-mode/); [Pl@ntNet 2022](https://plantnet.org/en/2022/10/18/plntnet-offline-embedded-identify-plants-anywhere-without-connection/) |
| Flora Incognita (Germany) | Plant ID | **Cloud**: identification needs internet; offline mode only saves observations as "unknown herb or shrub" for later ID | [Flora Incognita blog 2023](https://floraincognita.com/blog/2023/04/04/flora-incognita-now-with-offline-mode/); [FAQ](https://floraincognita.com/faq/) |
| PlantIn | Plant/fungi ID | Claims "a technology for offline id" (fungi) | [ST listing](https://app.sensortower.com/overview/1527399597?country=US) |
| Dog Scanner (Germany) | Dog breed ID | Offline scanning in the **Premium** version | [ST listing](https://app.sensortower.com/overview/1447489158?country=US) |
| Yuka (France) | Barcode food/cosmetic scan | Offline mode is **Premium only**; it downloads the 100,000 most-scanned products; the free version needs internet | [Yuka Help](https://help.yuka.io/l/en/article/ur4x5k32qg-database-in-offline-mode); [Yuka paid features](https://help.yuka.io/l/en/article/dop80j54bb-paid-version-features) |
| Cal AI | Food photo → calories | **Cloud LLMs**: relied on OpenAI GPT and Anthropic models plus RAG | [CNBC, Sep 2025](https://www.cnbc.com/2025/09/06/cal-ai-how-a-teenage-ceo-built-a-fast-growing-calorie-tracking-app.html) (via search summary) |
| Photomath (Google) | Math photo solver | Android Central: "it works even without an internet connection" (third-party; Photomath Plus is $9.99/month or $69.99/year; AI word-problem features are likely online) | [Android Central](https://www.androidcentral.com/apps-software/google-unveils-photomath-app) |
| Next Vision apps (CoinSnap, Rock ID, Picture Insect, AntiqSnap, etc.) | Collectible/nature ID | Shared image-recognition engine that compares user photos against a library of millions of images (implies server-side) | [Sterling Currency blog](https://www.sterlingcurrency.com.au/blog/news-research/the-fine-art-of-numismatics/coinsnap-a-fantastic-app-thats-not-fit-for-purpose/) (via search summary) |
| Dext, SimplyWise | Receipt OCR | Cloud-based ("cloud-based easy expense management"; "secure and unlimited cloud") | [Dext ST](https://app.sensortower.com/overview/418327708?country=US); [SimplyWise ST](https://app.sensortower.com/overview/1538521095?country=US) |

- A comparison published by iNaturalist of Seek, Google Lens, PlantNet, Flora Incognita and Plant.id found that Seek is conservative: it identifies only to the level it is confident of, often genus or family, and had "the lowest error rate of all apps tested" — [iNaturalist post #56](https://www.inaturalist.org/posts/44986-56-seek-offline-database-no-wifi-google-lens-plantnet-flora-incognita-plant-id)

### Inferences
- **Offline is a real product differentiator but has rarely been a revenue driver.** The top-grossing identifier apps (PictureThis, Next Vision's apps) and homework apps (Gauth, Question.AI) are cloud apps. The offline-first leaders are either free and science-funded (Seek, Merlin, PlantNet) or are scanners where offline is a privacy selling point (Genius Scan, iScanner, SwiftScan). Yuka and Dog Scanner show a working pattern of **putting offline mode behind the paywall**.
- Apple's built-in on-device features compete directly with paid translate and scanner apps: the Translate app, Live Text in the Camera app, Visual Look Up and (not verified here) the Notes/Files document scanner. The Apple Translate app's own US rating is only 2.35 from 9,959 ratings. Even so, paid camera-translator clones (Translate Now at $3M/month, Traductor GO at $1M) still monetize heavily through weekly subscriptions.
- For Europe (GDPR-sensitive markets), "on-device processing / no upload" claims appear mostly in European-made apps: Genius Scan (FR), Prizmo (BE), PlantNet (FR) and Yuka (FR). This suggests positioning around privacy works in the EU.

### Gaps
- No primary documentation was found on whether PictureThis, CamScanner, Gauth, Question.AI, Vivino, SnapCalorie, Foodvisor or Scanner Pro work offline. They are marked n/a or inferred cloud. Scanner Pro and CamScanner very likely scan and store offline, but their OCR/AI behaviour was not verified.
- Photomath's offline capability after the Google acquisition could not be confirmed from a primary Google source.
- Seeing AI and Be My Eyes offline behaviour was not verified.

## Q3. Which apps are growing fastest in 2025–2026, and are there MRR/ARR disclosures?

### Takeaway
The fastest growth is in **AI photo-calorie trackers** and **new "snap-to-value" identifiers**: collectibles, trading cards, antiques, resale items and vinyl. Several apps launched in 2025 reached $100k–$500k/month on iOS within months. Examples are AntiqSnap, HoloDex, FoilSnap, Translate AI, Welmi, SnapCal, ThriftAI and a Hong Kong scanner clone with 900k downloads a month. Cal AI is the standout disclosed case: from $1M in its first 4 months, to $1.4M/month (Sep 2025), to over $30–40M annual revenue (early 2026). MyFitnessPal then acquired it (announced 2 Mar 2026). Glority (PictureThis) is reported at $173M ARR.

### Cited Findings

#### Disclosed or reported revenue figures (label = disclosed/reported, not Sensor Tower)
| Company / app | Figure | Date | Type | Source |
|---|---|---|---|---|
| Cal AI | $1M revenue and 100,000 downloads in first 4 months (launched May 2024) | 2024 | Founder-reported | [What a Startup (Substack)](https://whatastartup.substack.com/p/two-gen-z-founders-bootstrapped-cal-ai) |
| Cal AI | "over $1.4 million per month after app store cuts"; 8.3M downloads as of July 2025; claimed 90% accuracy | Sep 2025 | Founder-reported to press | [CNBC](https://www.cnbc.com/2025/09/06/cal-ai-how-a-teenage-ceo-built-a-fast-growing-calorie-tracking-app.html) |
| Cal AI | >15M downloads, >$30M annual revenue, 7 employees; deal closed Dec 2025, announced 2 Mar 2026; terms undisclosed | Mar 2026 | Press (company-confirmed) | [TechCrunch](https://techcrunch.com/2026/03/02/myfitnesspal-has-acquired-cal-ai-the-viral-calorie-app-built-by-teens/); [GlobeNewswire](https://www.globenewswire.com/news-release/2026/03/02/3247439/0/en/MyFitnessPal-Acquires-Cal-AI-Expanding-on-its-Position-as-the-Leading-Player-in-Digital-Nutrition-Tracking.html) |
| Cal AI | ">$40 million in sales in the last 12 months" | Mar 2026 | Press | [Dealroom](https://app.dealroom.co/news/note/myfitnesspal-acquires-teen-built-cal-ai-after-40m-in-annual-sales) |
| Cal AI | $50M ARR (as of 2 Mar 2026); another tracker lists $40M ARR (updated 10 Sep 2026) | 2026 | Third-party trackers (lower reliability) | [ARR Club](https://www.arr.club/signal/cal-ai-reaches-30m-arr); [GetLatka](https://getlatka.com/companies/calai.app) |
| Cal AI (Sensor Tower) | $2M/month worldwide iOS gross, 500k downloads/month; #10 Free and #11 Grossing in US Health & Fitness | Aug/Sep 2026 | Estimate | [Sensor Tower](https://app.sensortower.com/overview/6480417616?country=US) |
| Glority (PictureThis, PlantAI, Plant Parent…) | $173M ARR, ranked #20 in Unique Research's top-100 private AI companies by ARR | 2025 | Third-party ranking | [Tech Buzz China – State of Chinese AI Apps 2025](https://techbuzzchina.substack.com/p/the-state-of-chinese-ai-apps-2025) |
| INTSIG (CamScanner, CamCard) | 2025 revenue RMB 1.81B (+25.8% YoY); consumer revenue RMB 1.544B (+28.11%); consumer MAU 190M (+11.11%); paying users 9.8776M (+32.78%) | FY2025 | Listed-company results (STAR 688615), via broker note | [Futubull – 2025 annual results note](https://news.futunn.com/en/post/70173970/hehe-information-688615-strong-growth-momentum-in-the-2025-annual) |
| DeepL | Reported ~€300M ARR in 2025 (another estimate: $185.2M for 2024); weighing an IPO at up to $5B; about 1K staff in 2026, down from 1.6K after restructuring | 2025–26 | Press/third-party estimates | [GetLatka](https://getlatka.com/companies/deepl.com); [SiliconANGLE](https://siliconangle.com/2025/10/02/ai-translation-startup-deepl-reportedly-weighing-5b-ipo/); [Startup Fortune](https://startupfortune.com/deepls-25-percent-staff-cut-is-europes-ai-translation-leader-adapting-to-generalist-model-pressure/) |
| Identifier-app category | $27M consumer spend in one month (App Store + Google Play); coin IDs $3.5M/month | May 2025 | Appfigures estimate | [Appfigures](https://appfigures.com/resources/insights/20250509?f=1) |
| Next Vision Limited (CoinSnap, Rock ID…) | 17 Android apps, ~50M total Google Play installs; CoinSnap and Rock Identifier each 10M+ installs | 2025–26 | AppBrain directory | [AppBrain](https://www.appbrain.com/dev/Next+Vision+Limited/) |

#### New entrants launched 2025–2026 that already reach meaningful iOS revenue (Sensor Tower, Aug-2026, worldwide iOS)
- **AntiqSnap** (Next Vision; launched Oct 2025): 200k downloads and $400k a month. #9 Free and #10 Grossing in US Reference; #6 Grossing in IT Reference — [Sensor Tower](https://app.sensortower.com/overview/6752929120?country=US); [US Reference RSS](https://itunes.apple.com/us/rss/topgrossingapplications/limit=100/genre=6006/json)
- **HoloDex – TCG Scan** (MAVELLI FZCO; Sep 2025): 300k downloads and $400k a month. **#1 Grossing in NL Reference**, #3 in NO — [Sensor Tower](https://app.sensortower.com/overview/6747442689?country=US)
- **FoilSnap: TCG Card Scanner** (Next Vision; Sep 2025): 100k downloads and $200k a month. **#1 Grossing in IT Reference** — [Sensor Tower](https://app.sensortower.com/overview/6752642525?country=US)
- **Translate AI – Live Translate** (HEYOS, Turkey; Jan 2025): 200k downloads and $500k a month. #3–5 Grossing in Reference across DE, GB, FR, ES, NL, SE, NO, DK and FI — [Sensor Tower](https://app.sensortower.com/overview/6738304985?country=US)
- **Scanner App: Scan Documents** (Uniteman, Hong Kong; Oct 2025): **900k downloads** and $500k a month. #2 Grossing in VN Business — [Sensor Tower](https://app.sensortower.com/overview/6753972326?country=US)
- **Welmi** (Feb 2025; photo calorie app with top market FR): 300k downloads and $300k a month. #24 Grossing in FR Health & Fitness — [Sensor Tower](https://app.sensortower.com/overview/6741707862?country=US)
- **ThriftAI: Profit Identifier** (Jun 2025): $90k a month. **#5 Grossing in US Shopping**, #8 in GB — [Sensor Tower](https://app.sensortower.com/overview/6746565278?country=US)
- **SnapCal** (Jul 2025): 60k downloads and $100k a month — [Sensor Tower](https://app.sensortower.com/overview/6747375157?country=US)
- **Lens AI & Reverse Image Search** (HEYOS; Dec 2025): 100k downloads and $100k a month — [Sensor Tower](https://app.sensortower.com/overview/6753348682?country=US)
- **Calife: AI Calorie Tracker** (Core AI, Singapore; Jul 2026): already #6 Free in DK Health & Fitness and #13 in FI; revenue still below Sensor Tower's floor — [Sensor Tower](https://app.sensortower.com/overview/6779546212?country=US); [DK H&F RSS](https://itunes.apple.com/dk/rss/topfreeapplications/limit=100/genre=6013/json)
- **BitePal** (Reface, Lithuania; Jun 2024): 100k downloads and $500k a month; **Calo** (Next Vision; 2023): 300k downloads and $800k a month, #10 Grossing in FI H&F and #13 in DK — [Sensor Tower BitePal](https://app.sensortower.com/overview/6479529917?country=US); [Sensor Tower Calo](https://app.sensortower.com/overview/6447434453?country=US)

#### Market context
- Sensor Tower's State of Mobile 2026 reports consumer app spending reached $167B, with apps out-earning games for the first time, driven by generative AI — [Sensor Tower press release](https://sensortower.com/press/press-release-boosted-by-gen-ai-services-consumers-spent-more-money-in-apps-than-games-for-first-time)
- Generative-AI apps earned $1.87B in in-app revenue in H1 2025, against $932M in H2 2024 — [Sensor Tower State of AI Apps 2025](https://sensortower.com/blog/state-of-ai-apps-report-2025)

### Inferences
- The 2025–26 wave follows one template: **"point the camera at X, get a value or answer."** It uses a generic cloud vision model, a weekly paywall ($4–18/week) and heavy paid acquisition. It spreads quickly into new verticals (trading cards, antiques, resale, vinyl, stamps). Publishers who already own a vision engine (Next Vision/Glority) launch new verticals fastest.
- Cal AI's reported revenue is roughly 1.3–2× Sensor Tower's iOS run-rate. That makes Sensor Tower's figures for fast-growing, web-to-app-funnel apps likely **conservative**.
- Photo calorie tracking is consolidating. MyFitnessPal (the #1 US Health & Fitness grossing app) bought Cal AI, while European incumbents Yazio (DE) and Lifesum (SE) now carry "AI" in their store names. This points to photo logging becoming table stakes.

### Gaps
- No verified year-over-year Sensor Tower or Appfigures growth series for 2025→2026 was accessible. Growth is inferred from launch dates plus current run-rates, and from a few dated snapshots.
- No MRR/ARR disclosures were found for BPMobile (iScanner), Readdle (Scanner Pro), The Grizzly Labs (Genius Scan), Next Vision, AIBY (Plantum, Coin ID), Vortemol (PlantIn, CoinIn), Yuka, Foodvisor or Yazio in this research pass. The web-search budget was exhausted, so no further searches could be made.
- Claims such as Next Vision ">$10M/year" appeared only in low-quality secondary summaries and are excluded as unverified.

## Q4. Top Grossing / Top Free chart positions in the US, Vietnam and European App Stores

### Takeaway
On 27 Sep 2026, camera-vision apps hold top-10 **grossing** positions in their categories across Europe:
- **Business**: iScanner #2–5; Adobe Scan #3–6 (DE, IT, NL, Nordics); Scanner Pro #6–10 (DE, FR, IT, NL, SE, NO, DK)
- **Reference**: CoinSnap, CoinIn, Translate Now and Translate AI in the top 10; HoloDex #1 NL; FoilSnap #1 IT
- **Education**: PictureThis #2–5; Picture Mushroom in the top 10 in DE and DK
- **Food & Drink**: Vivino #1–3 in NO, SE, DK and NL
- **Health & Fitness**: Yazio #2 DE and #3 FI; Foodvisor #5 FR; Lifesum #2 SE

In Vietnam, Business top-grossing is almost entirely scanners, Reference top-grossing is entirely AI translators, and Gauth is #2 Free in Education.

### Cited Findings

#### Chart positions by storefront (Apple RSS top-100 iPhone feeds, snapshot 27 Sep 2026)
Format: **F** = Top Free, **G** = Top Grossing. "#63 overall" means the overall (all-categories) chart; otherwise the rank is in the named category. "–" = not in the top 100 of any tracked category. Categories: Bus=Business, Prod=Productivity, Util=Utilities, Edu=Education, Ref=Reference, H&F=Health & Fitness, Food=Food & Drink, Shop=Shopping, Fin=Finance, Med=Medical, Life=Lifestyle. Sources: e.g., [US Business top grossing](https://itunes.apple.com/us/rss/topgrossingapplications/limit=100/genre=6000/json), [VN Education top free](https://itunes.apple.com/vn/rss/topfreeapplications/limit=100/genre=6017/json), [FR H&F top grossing](https://itunes.apple.com/fr/rss/topgrossingapplications/limit=100/genre=6013/json); the same URL pattern applies for all 12 countries × 14 genres.

| App | US | VN | DE | GB | FR | IT | ES | NL | SE | NO | DK | FI |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| [MyFitnessPal](https://apps.apple.com/us/app/id341232718) | F #18 H&F / G #63 overall, #1 H&F | F #77 H&F / G #37 H&F | F #57 H&F / G #11 H&F | F #14 H&F / G #48 overall, #5 H&F | F #61 H&F / G #15 H&F | F #49 H&F / G #14 H&F | F #41 H&F / G #10 H&F | F #28 H&F / G #96 overall, #6 H&F | F #66 H&F / G #22 H&F | F #48 H&F / G #11 H&F | F #44 H&F / G #10 H&F | F #50 H&F / G #13 H&F |
| [PictureThis](https://apps.apple.com/us/app/id1252497129) | F #8 Edu / G #3 Edu | – | F #12 Edu / G #86 overall, #3 Edu | F #12 Edu / G #81 overall, #2 Edu | F #24 Edu / G #5 Edu | F #20 Edu / G #5 Edu | F #10 Edu / G #88 overall, #2 Edu | F #15 Edu / G #3 Edu | F #20 Edu / G #14 Edu | F #47 Edu / G #15 Edu | F #22 Edu / G #10 Edu | F #31 Edu / G #22 Edu |
| [CamScanner](https://apps.apple.com/us/app/id388627783) | F #30 Prod / G #7 Prod | F #11 Prod / G #51 overall, #5 Prod | F #69 Prod / G #16 Prod | F #32 Prod / G #18 Prod | F #25 Prod / G #8 Prod | F #19 Prod / G #73 overall, #7 Prod | F #19 Prod / G #54 overall, #7 Prod | F – / G #31 Prod | F #96 Prod / G #23 Prod | F – / G #35 Prod | F – / G #38 Prod | F #77 Prod / G #20 Prod |
| [Yazio](https://apps.apple.com/us/app/id946099227) | – | F #78 H&F / G #56 H&F | F #4 H&F / G #20 overall, #2 H&F | – | F #14 H&F / G #74 overall, #4 H&F | F #13 H&F / G #99 overall, #4 H&F | F #32 H&F / G #8 H&F | F #21 H&F / G #9 H&F | F #79 H&F / G #38 H&F | F #77 H&F / G #39 H&F | F #39 H&F / G #23 H&F | F #32 H&F / G #53 overall, #3 H&F |
| [iScanner (BPMobile)](https://apps.apple.com/us/app/id1040093707) | F #91 Bus / G #3 Bus | F – / G #7 Bus | F #32 Bus / G #94 overall, #2 Bus | F #91 Bus / G #5 Bus | F #40 Bus / G #3 Bus | – | – | F #28 Bus / G #3 Bus | F #44 Bus / G #3 Bus | F #96 Bus / G #4 Bus | F #94 Bus / G #3 Bus | F – / G #4 Bus |
| [Scanner App - Scan PDF & Docs](https://apps.apple.com/us/app/id1568660349) | F #27 Bus / G #8 Bus | F #86 Bus / G #15 Bus | F #15 Bus / G #12 Bus | F #16 Bus / G #10 Bus | F #30 Bus / G #12 Bus | F #7 Bus / G #5 Bus | F #12 Bus / G #9 Bus | F #60 Bus / G #14 Bus | F #38 Bus / G #6 Bus | F #93 Bus / G #13 Bus | F #58 Bus / G #7 Bus | F – / G #25 Bus |
| [Translate Now](https://apps.apple.com/us/app/id1348028646) | F #8 Ref / G #1 Ref | F #12 Ref / G #4 Ref | F #12 Ref / G #2 Ref | F #10 Ref / G #3 Ref | F #23 Ref / G #16 Ref | F #18 Ref / G #5 Ref | F #24 Ref / G #10 Ref | F #39 Ref / G #14 Ref | F #50 Ref / G #9 Ref | F #37 Ref / G #7 Ref | F #25 Ref / G #4 Ref | F #29 Ref / G #15 Ref |
| [Adobe Scan](https://apps.apple.com/us/app/id1199564834) | F #36 Bus / G #12 Bus | F #65 Bus / G #12 Bus | F #10 Bus / G #4 Bus | F #33 Bus / G #11 Bus | F #21 Bus / G #8 Bus | F #9 Bus / G #3 Bus | F #15 Bus / G #10 Bus | F #17 Bus / G #5 Bus | F #32 Bus / G #5 Bus | F #19 Bus / G #5 Bus | F #36 Bus / G #6 Bus | F #24 Bus / G #3 Bus |
| [Cal AI](https://apps.apple.com/us/app/id6480417616) | F #10 H&F / G #11 H&F | – | F #63 H&F / G #59 H&F | F #39 H&F / G #19 H&F | F – / G #51 H&F | F – / G #78 H&F | F #19 H&F / G #7 H&F | F – / G #61 H&F | F #98 H&F / G #50 H&F | F #73 H&F / G #66 H&F | F #92 H&F / G #30 H&F | F – / G #65 H&F |
| [Foodvisor](https://apps.apple.com/us/app/id1064020872) | F #96 H&F / G #46 H&F | F – / G #18 H&F | F #33 H&F / G #26 H&F | F #44 H&F / G #54 H&F | F #17 H&F / G #84 overall, #5 H&F | F #46 H&F / G #28 H&F | F #26 H&F / G #31 H&F | F #11 H&F / G #13 H&F | F #12 H&F / G #18 H&F | F #19 H&F / G #21 H&F | F #12 H&F / G #12 H&F | F #11 H&F / G #99 overall, #7 H&F |
| [Yuka](https://apps.apple.com/us/app/id1092799236) | F #4 H&F / G #25 H&F | – | F #12 H&F / G #79 H&F | F #6 H&F / G #30 H&F | F #8 H&F / G #16 H&F | F #3 H&F / G #16 H&F | F #6 H&F / G #28 H&F | – | – | – | – | – |
| [Traductor GO](https://apps.apple.com/us/app/id1570134612) | F #68 Prod / G #21 Prod | F #57 Prod / G #25 Prod | F #67 Prod / G #28 Prod | F #30 Prod / G #23 Prod | F #53 Prod / G #28 Prod | F #48 Prod / G #27 Prod | F #39 Prod / G #20 Prod | F #38 Prod / G #29 Prod | F #25 Prod / G #16 Prod | F #24 Prod / G #10 Prod | F #32 Prod / G #11 Prod | F #31 Prod / G #17 Prod |
| [Lose It!](https://apps.apple.com/us/app/id297368629) | F #60 H&F / G #20 H&F | – | – | F – / G #41 H&F | – | – | F – / G #36 H&F | F – / G #94 H&F | F – / G #86 H&F | – | – | F – / G #84 H&F |
| [iTranslate](https://apps.apple.com/us/app/id288113403) | F – / G #30 Prod | F – / G #100 Prod | F #79 Prod / G #26 Prod | F – / G #41 Prod | F – / G #35 Prod | F – / G #26 Prod | F – / G #27 Prod | F – / G #44 Prod | F – / G #34 Prod | F #79 Prod / G #23 Prod | F #58 Prod / G #17 Prod | F – / G #27 Prod |
| [PlantIn](https://apps.apple.com/us/app/id1527399597) | F #96 Edu / G #16 Edu | – | F #50 Edu / G #67 Edu | F #37 Edu / G #60 Edu | F #56 Edu / G #65 Edu | F #60 Edu / G #41 Edu | F #26 Edu / G #67 Edu | F #44 Edu / G #77 Edu | F – / G #65 Edu | F – / G #43 Edu | F – / G #43 Edu | – |
| [Gauth](https://apps.apple.com/us/app/id1542571008) | F #4 Edu / G #10 Edu | F #49 overall, #2 Edu / G #43 Edu | – | F #19 Edu / G #69 Edu | – | F #96 overall, #7 Edu / G #23 Edu | F #77 Edu / G – | – | – | – | – | – |
| [Calo: AI Food Calorie Counter](https://apps.apple.com/us/app/id6447434453) | F #63 H&F / G #52 H&F | – | F – / G #67 H&F | F #21 H&F / G #22 H&F | F #54 H&F / G #39 H&F | F #31 H&F / G #17 H&F | F #67 H&F / G #44 H&F | F #62 H&F / G #53 H&F | F #21 H&F / G #17 H&F | F #46 H&F / G #31 H&F | F #27 H&F / G #13 H&F | F #47 H&F / G #10 H&F |
| [Rock Identifier](https://apps.apple.com/us/app/id1546796934) | F #75 Edu / G #27 Edu | – | F – / G #63 Edu | F – / G #49 Edu | F – / G #70 Edu | F – / G #36 Edu | F – / G #71 Edu | F #87 Edu / G #31 Edu | F – / G #70 Edu | F #81 Edu / G #96 Edu | F #70 Edu / G #27 Edu | F – / G #47 Edu |
| [Lifesum](https://apps.apple.com/us/app/id286906691) | – | – | F #99 H&F / G #18 H&F | – | F – / G #85 H&F | F – / G #58 H&F | – | F #100 H&F / G #30 H&F | F #22 H&F / G #44 overall, #2 H&F | F #33 H&F / G #61 overall, #3 H&F | F #24 H&F / G #50 overall, #4 H&F | F – / G #29 H&F |
| [ScanGuru](https://apps.apple.com/us/app/id1040149161) | F – / G #28 Bus | F – / G #5 Bus | F – / G #29 Bus | F – / G #49 Bus | F – / G #13 Bus | F – / G #11 Bus | F – / G #16 Bus | F – / G #29 Bus | F – / G #39 Bus | F – / G #17 Bus | F – / G #22 Bus | F – / G #11 Bus |
| [QR Code Reader (AIR APPS)](https://apps.apple.com/us/app/id1226650677) | F – / G #43 Util | – | F – / G #29 Util | F – / G #62 Util | – | – | – | – | – | – | F – / G #72 Util | – |
| [Scan Shot PDF Scanner](https://apps.apple.com/us/app/id1575194801) | F – / G #31 Bus | F – / G #36 Bus | F – / G #11 Bus | F – / G #19 Bus | F – / G #16 Bus | F – / G #16 Bus | F – / G #26 Bus | F – / G #35 Bus | F – / G #36 Bus | F – / G #8 Bus | F – / G #30 Bus | F – / G #62 Bus |
| [CoinSnap](https://apps.apple.com/us/app/id1634551626) | F #10 Ref / G #7 Ref | – | F #10 Ref / G #3 Ref | F #12 Ref / G #8 Ref | F #13 Ref / G #6 Ref | F #8 Ref / G #2 Ref | F #12 Ref / G #3 Ref | F #20 Ref / G #13 Ref | F #42 Ref / G #25 Ref | F #55 Ref / G #27 Ref | F #50 Ref / G #5 Ref | F #41 Ref / G #17 Ref |
| [Scanner Pro (Readdle)](https://apps.apple.com/us/app/id333710667) | F – / G #21 Bus | F – / G #14 Bus | F – / G #6 Bus | F – / G #22 Bus | F – / G #10 Bus | F – / G #7 Bus | F – / G #18 Bus | F – / G #9 Bus | F – / G #7 Bus | F – / G #6 Bus | F – / G #10 Bus | F – / G #14 Bus |
| [Tiny Scanner](https://apps.apple.com/us/app/id595563753) | F – / G #19 Bus | F – / G #56 Bus | F – / G #27 Bus | F – / G #26 Bus | F – / G #40 Bus | F – / G #18 Bus | F – / G #57 Bus | F – / G #15 Bus | F – / G #9 Bus | F – / G #10 Bus | F – / G #15 Bus | F – / G #36 Bus |
| [Scanner App: Scan Documents (VN #2)](https://apps.apple.com/us/app/id6753972326) | F #80 Bus / G #58 Bus | F #48 Bus / G #2 Bus | F #51 Bus / G #37 Bus | F – / G #77 Bus | F – / G #57 Bus | F #58 Bus / G #32 Bus | F #95 Bus / G #30 Bus | F #67 Bus / G #50 Bus | F #56 Bus / G #37 Bus | F #51 Bus / G #27 Bus | F #39 Bus / G #37 Bus | F #55 Bus / G #40 Bus |
| [CoinIn](https://apps.apple.com/us/app/id1672111368) | F #14 Ref / G #8 Ref | – | F #3 Ref / G #4 Ref | F #3 Ref / G #6 Ref | F #5 Ref / G #13 Ref | F #19 Ref / G #3 Ref | F #3 Ref / G #18 Ref | F #52 Ref / G #43 Ref | F #22 Ref / G #16 Ref | F #40 Ref / G #34 Ref | F #19 Ref / G #38 Ref | F #31 Ref / G #16 Ref |
| [Translate AI - Live Translate](https://apps.apple.com/us/app/id6738304985) | F #31 Ref / G #14 Ref | F #28 Ref / G #6 Ref | F #9 Ref / G #5 Ref | F #17 Ref / G #4 Ref | F #22 Ref / G #4 Ref | F #17 Ref / G #7 Ref | F #23 Ref / G #5 Ref | F #13 Ref / G #5 Ref | F #15 Ref / G #4 Ref | F #9 Ref / G #4 Ref | F #9 Ref / G #3 Ref | F #6 Ref / G #4 Ref |
| [BitePal](https://apps.apple.com/us/app/id6479529917) | – | – | F – / G #97 H&F | F – / G #88 H&F | F – / G #67 H&F | F #69 H&F / G #41 H&F | F – / G #72 H&F | – | F – / G #82 H&F | – | – | F – / G #80 H&F |
| [TapScanner](https://apps.apple.com/us/app/id1382564905) | F – / G #88 Bus | F #66 Bus / G #11 Bus | F – / G #53 Bus | F – / G #52 Bus | F – / G #36 Bus | F #64 Bus / G #23 Bus | F #75 Bus / G #25 Bus | F – / G #25 Bus | F #97 Bus / G #16 Bus | F – / G #14 Bus | F #70 Bus / G #4 Bus | F – / G #39 Bus |
| [HoloDex - TCG Scan](https://apps.apple.com/us/app/id6747442689) | F #15 Ref / G #13 Ref | F – / G #88 Ref | F #16 Ref / G #20 Ref | F #7 Ref / G #9 Ref | F #38 Ref / G #27 Ref | F #12 Ref / G #21 Ref | F #16 Ref / G #22 Ref | F #2 Ref / G #1 Ref | F #8 Ref / G #12 Ref | F #3 Ref / G #3 Ref | F #5 Ref / G #6 Ref | F #22 Ref / G #71 Ref |
| [AntiqSnap](https://apps.apple.com/us/app/id6752929120) | F #9 Ref / G #10 Ref | – | F #43 Ref / G #24 Ref | F #35 Ref / G #31 Ref | F #17 Ref / G #11 Ref | F #10 Ref / G #6 Ref | F #19 Ref / G #20 Ref | F #16 Ref / G #19 Ref | F #60 Ref / G #32 Ref | F – / G #14 Ref | F #67 Ref / G #27 Ref | F – / G #45 Ref |
| [Scanner - Luni](https://apps.apple.com/us/app/id1291962681) | F – / G #47 Bus | F – / G #28 Bus | F #34 Bus / G #13 Bus | F – / G #30 Bus | F #16 Bus / G #7 Bus | F #50 Bus / G #13 Bus | F #39 Bus / G #15 Bus | F #76 Bus / G #20 Bus | F – / G #33 Bus | F – / G #31 Bus | – | F #15 Bus / G #9 Bus |
| [Lens Scan: Identify Anything](https://apps.apple.com/us/app/id6560107458) | F – / G #52 Util | – | F – / G #52 Util | F – / G #60 Util | F – / G #73 Util | F – / G #43 Util | F #73 Util / G #21 Util | F #39 Util / G #8 Util | F – / G #21 Util | F – / G #18 Util | F #69 Util / G #95 Util | F #21 Util / G #6 Util |
| [Picture Insect](https://apps.apple.com/us/app/id1461694973) | F – / G #50 Edu | – | F – / G #48 Edu | F – / G #65 Edu | – | – | – | – | – | – | – | – |
| [Scan Hero](https://apps.apple.com/us/app/id1017261655) | F – / G #44 Bus | F – / G #18 Bus | F – / G #59 Bus | F – / G #31 Bus | F – / G #47 Bus | F – / G #47 Bus | F – / G #33 Bus | F – / G #47 Bus | – | F – / G #19 Bus | F – / G #16 Bus | F – / G #23 Bus |
| [Welmi](https://apps.apple.com/us/app/id6741707862) | – | – | F #74 H&F / G #65 H&F | – | F #36 H&F / G #24 H&F | F #60 H&F / G #38 H&F | F #25 H&F / G #34 H&F | – | – | – | – | – |
| [Genius Scan](https://apps.apple.com/us/app/id377672876) | F #81 Bus / G #35 Bus | F #93 Bus / G #81 Bus | F #49 Bus / G #17 Bus | F – / G #45 Bus | F #52 Bus / G #32 Bus | F #44 Bus / G #26 Bus | F – / G #24 Bus | F #64 Bus / G #24 Bus | F #64 Bus / G #11 Bus | F #67 Bus / G #11 Bus | F #54 Bus / G #14 Bus | F – / G #35 Bus |
| [Photomath](https://apps.apple.com/us/app/id919087726) | F – / G #36 Edu | – | F #80 Edu / G – | – | – | F #36 Edu / G #31 Edu | F #43 Edu / G – | – | F #93 Edu / G – | F #44 Edu / G #90 Edu | – | F #40 Edu / G – |
| [Vivino](https://apps.apple.com/us/app/id414461255) | F – / G #6 Food | F – / G #3 Food | F #55 Food / G #14 Food | F #93 Food / G #9 Food | F #22 Food / G #8 Food | F #38 Food / G #5 Food | F #41 Food / G #9 Food | F #11 Food / G #2 Food | F #32 Food / G #2 Food | F #24 Food / G #1 Food | F #15 Food / G #3 Food | F #26 Food / G #7 Food |
| [InstantTranslator: AI Translate](https://apps.apple.com/us/app/id6636468891) | F #68 Ref / G #36 Ref | F #9 Ref / G #2 Ref | F #33 Ref / G #19 Ref | F #63 Ref / G #57 Ref | F #52 Ref / G #18 Ref | F #15 Ref / G #14 Ref | F #5 Ref / G #2 Ref | F #40 Ref / G #6 Ref | F #24 Ref / G #34 Ref | F #27 Ref / G #22 Ref | F #37 Ref / G #43 Ref | F #50 Ref / G #11 Ref |
| [QR Reader for iPhone (TapMedia)](https://apps.apple.com/us/app/id368494609) | F – / G #50 Util | – | – | – | – | – | F – / G #75 Util | F – / G #33 Util | F – / G #12 Util | F – / G #11 Util | F #88 Util / G #11 Util | F – / G #13 Util |
| [EveryScan (LensAI) Identifier](https://apps.apple.com/us/app/id1663862037) | F – / G #22 Ref | – | F – / G #51 Ref | F – / G #35 Ref | F – / G #48 Ref | F – / G #27 Ref | F – / G #66 Ref | F – / G #46 Ref | F – / G #14 Ref | F – / G #20 Ref | F – / G #19 Ref | F – / G #28 Ref |
| [Google app (Lens)](https://apps.apple.com/us/app/id284815942) | F #17 overall, #1 Util / G – | F #21 overall, #2 Util / G #41 Util | F #15 overall, #1 Util / G #62 Util | F #25 overall, #2 Util / G – | F #22 overall, #1 Util / G – | F #34 overall, #2 Util / G – | F #33 overall, #2 Util / G #46 Util | F #30 overall, #1 Util / G #75 Util | F #25 overall, #2 Util / G – | F #42 overall, #3 Util / G – | F #31 overall, #1 Util / G – | F #35 overall, #1 Util / G – |
| [Gizmo: AI Tutor](https://apps.apple.com/us/app/id1610516671) | F #19 Edu / G #41 Edu | – | – | F #30 Edu / G #41 Edu | F #100 Edu / G – | – | – | F #81 Edu / G – | F #26 Edu / G – | F #21 Edu / G – | – | F #50 Edu / G – |
| [FoilSnap: TCG Card Scanner](https://apps.apple.com/us/app/id6752642525) | F #18 Ref / G #19 Ref | – | F #8 Ref / G #6 Ref | F #8 Ref / G #7 Ref | F #41 Ref / G #29 Ref | F #5 Ref / G #1 Ref | F #8 Ref / G #6 Ref | F #42 Ref / G #42 Ref | F #37 Ref / G #57 Ref | F #58 Ref / G – | F #17 Ref / G #36 Ref | F #71 Ref / G – |
| [PlantAI: Identifier & Diagnose](https://apps.apple.com/us/app/id1664437810) | F – / G #65 Ref | – | F – / G #38 Ref | F – / G #40 Ref | F #83 Ref / G #40 Ref | F #71 Ref / G #19 Ref | F #61 Ref / G #24 Ref | F #80 Ref / G #67 Ref | F #59 Ref / G #23 Ref | – | F #86 Ref / G #28 Ref | – |
| [Question.AI](https://apps.apple.com/us/app/id6449486871) | F – / G #49 Edu | – | – | – | – | – | – | – | – | – | – | – |
| [Picture Bird](https://apps.apple.com/us/app/id1474586978) | F – / G #55 Ref | – | F – / G #30 Ref | F #49 Ref / G #36 Ref | F #96 Ref / G #22 Ref | F – / G #24 Ref | F – / G #50 Ref | F #54 Ref / G #29 Ref | – | F #68 Ref / G – | F #95 Ref / G #34 Ref | – |
| [Plant App](https://apps.apple.com/us/app/id1595795215) | – | – | – | F – / G #93 Edu | – | – | – | – | – | F – / G #87 Edu | F – / G #62 Edu | – |
| [Picture Mushroom](https://apps.apple.com/us/app/id1474578078) | F – / G #68 Edu | – | F #6 Edu / G #10 Edu | F #60 Edu / G #22 Edu | F – / G #33 Edu | F #19 Edu / G #14 Edu | F – / G #63 Edu | F #58 Edu / G #42 Edu | F #15 Edu / G #12 Edu | F #32 Edu / G #48 Edu | F #3 Edu / G #4 Edu | F #18 Edu / G #25 Edu |
| [CamCard](https://apps.apple.com/us/app/id349447615) | F – / G #98 Bus | F – / G #26 Bus | F – / G #68 Bus | F – / G #76 Bus | F – / G #43 Bus | F – / G #28 Bus | F – / G #37 Bus | F – / G #21 Bus | F – / G #19 Bus | F – / G #68 Bus | – | F – / G #34 Bus |
| [Evernote Scannable](https://apps.apple.com/us/app/id883338188) | – | F – / G #98 Prod | – | – | – | – | – | F – / G #74 Prod | – | – | – | – |
| [Chegg Study](https://apps.apple.com/us/app/id385758163) | F – / G #63 Edu | – | – | – | – | – | – | – | – | – | – | – |
| [Plantum](https://apps.apple.com/us/app/id1476047194) | F – / G #69 Edu | – | – | – | – | – | – | – | – | – | – | – |
| [Lens AI & Reverse Image Search](https://apps.apple.com/us/app/id6753348682) | F #43 Ref / G #38 Ref | – | F #15 Ref / G #22 Ref | F #26 Ref / G #16 Ref | F #26 Ref / G #23 Ref | F – / G #34 Ref | F – / G #76 Ref | F #21 Ref / G #18 Ref | F #27 Ref / G #42 Ref | F #17 Ref / G #35 Ref | F #21 Ref / G #20 Ref | F #10 Ref / G #21 Ref |
| [SnapCal](https://apps.apple.com/us/app/id6747375157) | – | – | – | – | – | – | F #96 H&F / G – | – | – | – | – | – |
| [Coin ID (AIBY)](https://apps.apple.com/us/app/id1665672552) | F – / G #39 Ref | – | F – / G #67 Ref | F – / G #100 Ref | F – / G #89 Ref | F #67 Ref / G #35 Ref | F – / G #70 Ref | – | – | – | – | F – / G #94 Ref |
| [Planto](https://apps.apple.com/us/app/id1531728753) | – | – | – | – | – | – | – | – | F #60 Edu / G #22 Edu | F #34 Edu / G #5 Edu | F #17 Edu / G #7 Edu | – |
| [Quizard AI](https://apps.apple.com/us/app/id1667996582) | F – / G #83 Edu | – | – | – | – | – | – | – | – | – | – | – |
| [ThriftAI: Profit Identifier](https://apps.apple.com/us/app/id6746565278) | F – / G #5 Shop | F – / G #81 Shop | F – / G #15 Shop | F – / G #8 Shop | F – / G #23 Shop | F – / G #20 Shop | F – / G #68 Shop | F – / G #23 Shop | F – / G #13 Shop | – | F – / G #40 Shop | F – / G #16 Shop |
| [DeepL](https://apps.apple.com/us/app/id1552407475) | F #67 Ref / G – | F #31 Ref / G #21 Ref | F #4 Ref / G #12 Ref | F #39 Ref / G #99 Ref | F #14 Ref / G #38 Ref | F #22 Ref / G #23 Ref | F #14 Ref / G #31 Ref | F #14 Ref / G #32 Ref | F #19 Ref / G – | F #41 Ref / G – | F #18 Ref / G #81 Ref | F #9 Ref / G #57 Ref |
| [Dext](https://apps.apple.com/us/app/id418327708) | – | – | – | F – / G #25 Bus | F – / G #88 Bus | – | – | – | – | – | – | – |
| [SimplyWise](https://apps.apple.com/us/app/id1538521095) | F – / G #31 Fin | – | – | – | – | – | – | – | – | – | – | – |
| [MonPrice: Card Value Scanner](https://apps.apple.com/us/app/id6741683137) | – | F #62 Ref / G #51 Ref | F #59 Ref / G #34 Ref | – | F #74 Ref / G #34 Ref | F #61 Ref / G #31 Ref | F #28 Ref / G #36 Ref | F #37 Ref / G #11 Ref | F #21 Ref / G #11 Ref | F #31 Ref / G #15 Ref | F #14 Ref / G #8 Ref | F – / G #43 Ref |
| [Expensify](https://apps.apple.com/us/app/id471713959) | – | – | – | – | – | – | F – / G #94 Bus | F – / G #88 Bus | – | – | – | – |
| [VinylSnap](https://apps.apple.com/us/app/id6748595105) | F – / G #72 Ref | – | F – / G #42 Ref | F #93 Ref / G #26 Ref | F – / G #20 Ref | F – / G #20 Ref | – | F – / G #17 Ref | F – / G #30 Ref | F #96 Ref / G #45 Ref | F #100 Ref / G #18 Ref | – |
| [SwiftScan (ex-Scanbot)](https://apps.apple.com/us/app/id834854351) | – | – | F – / G #35 Util | – | F – / G #91 Util | – | – | – | – | – | – | – |
| [ABBYY Business Card Reader](https://apps.apple.com/us/app/id898215947) | – | F – / G #70 Bus | – | – | – | F – / G #57 Bus | F – / G #53 Bus | – | – | F – / G #24 Bus | F – / G #49 Bus | – |
| [Miiskin](https://apps.apple.com/us/app/id1214795331) | – | F – / G #63 Med | – | F – / G #71 Med | – | F – / G #35 Med | – | – | – | – | – | F – / G #66 Med |
| [Google Translate](https://apps.apple.com/us/app/id414706506) | F #1 Ref / G – | F #1 Ref / G – | F #1 Ref / G – | F #1 Ref / G – | F #2 Ref / G – | F #3 Ref / G – | F #2 Ref / G – | F #1 Ref / G – | F #1 Ref / G – | F #1 Ref / G – | F #1 Ref / G – | F #1 Ref / G – |
| [Fetch](https://apps.apple.com/us/app/id1182474649) | F #84 overall, #14 Shop / G – | – | – | – | – | – | – | – | – | – | – | – |
| [Naver Papago](https://apps.apple.com/us/app/id1147874819) | F #53 Ref / G – | F #15 Ref / G – | F #32 Ref / G – | F #50 Ref / G – | F #49 Ref / G – | F #60 Ref / G – | F #43 Ref / G – | F #34 Ref / G – | F #44 Ref / G – | F #36 Ref / G – | F #36 Ref / G – | F #36 Ref / G – |
| [Merlin Bird ID](https://apps.apple.com/us/app/id773457673) | F #13 Ref / G – | – | F #13 Ref / G – | F #2 Ref / G – | F #16 Ref / G – | F #59 Ref / G – | F #18 Ref / G – | F #3 Ref / G – | F #10 Ref / G – | F #8 Ref / G – | F #4 Ref / G – | F #26 Ref / G – |
| [Yandex Translate](https://apps.apple.com/us/app/id584291439) | – | F #65 Ref / G – | – | – | – | – | – | – | – | – | – | F #91 Ref / G – |
| [QR Code Reader (Komorebi)](https://apps.apple.com/us/app/id1080558159) | – | – | – | – | – | – | – | – | – | – | F #68 Prod / G – | – |
| [Microsoft Translator](https://apps.apple.com/us/app/id1018949559) | – | – | – | – | – | – | – | – | – | – | – | F #86 Prod / G – |
| [PlantNet](https://apps.apple.com/us/app/id600547573) | – | – | – | – | F #38 Edu / G – | F #78 Edu / G – | F #62 Edu / G – | F #24 Edu / G – | F #91 Edu / G – | – | F #42 Edu / G – | F #39 Edu / G – |
| [Seek by iNaturalist](https://apps.apple.com/us/app/id1353224144) | – | – | – | – | – | – | – | – | F #73 Edu / G – | – | F #11 Edu / G – | – |
| [Be My Eyes](https://apps.apple.com/us/app/id905177575) | – | – | F #75 Life / G – | – | – | – | – | – | – | – | – | – |
| [Bobby Approved](https://apps.apple.com/us/app/id1571725006) | F #99 Food / G – | – | – | – | – | – | – | – | – | – | – | – |
| [Flora Incognita](https://apps.apple.com/us/app/id1297860122) | – | – | F #22 Edu / G – | – | – | – | – | – | F #75 Edu / G – | – | – | – |
| [ObsIdentify](https://apps.apple.com/us/app/id1464543488) | – | – | – | – | – | – | – | F #9 Edu / G – | – | – | – | – |
| [Calife: AI Calorie Tracker](https://apps.apple.com/us/app/id6779546212) | – | F #29 H&F / G #32 H&F | F #73 H&F / G – | F #86 H&F / G – | F #60 H&F / G – | F #25 H&F / G #74 H&F | F #69 H&F / G #60 H&F | F #15 H&F / G #87 H&F | F #15 H&F / G #39 H&F | F #18 H&F / G #59 H&F | F #6 H&F / G #22 H&F | F #13 H&F / G #32 H&F |

#### Vietnam App Store: category top-15 snapshots (27 Sep 2026)
- **VN Business – Top Grossing**: #2 Scanner App: Scan Documents, #4 Document Scan: PDF Scanner App, #5 ScanGuru, #7 iScanner, #8 PDF & Document Scanner., #11 TapScanner, #12 Adobe Scan, #14 Scanner Pro, #15 Scanner App – Scan PDF & Docs. #1 is LinkedIn — [VN Business grossing RSS](https://itunes.apple.com/vn/rss/topgrossingapplications/limit=100/genre=6000/json)
- **VN Productivity**: CamScanner is #11 Top Free and #5 Top Grossing (#51 overall grossing in VN) — [VN Productivity grossing RSS](https://itunes.apple.com/vn/rss/topgrossingapplications/limit=100/genre=6007/json)
- **VN Reference – Top Grossing**: #1 Live Translator-AI Translate, #2 InstantTranslator, #3 Translate One, #4 Translate Now, #5 Translator – Live AI Translate, #7 AR Translator: Translate Photo. **VN Reference – Top Free**: #1 Google Translate, #15 Naver Papago — [VN Reference grossing RSS](https://itunes.apple.com/vn/rss/topgrossingapplications/limit=100/genre=6006/json)
- **VN Education – Top Free**: #2 Gauth (#49 overall free) and #12 AI Hay. VN Education grossing is led by language-learning apps (Duolingo, ELSA, etc.), not photo solvers — [VN Education free RSS](https://itunes.apple.com/vn/rss/topfreeapplications/limit=100/genre=6017/json)
- **VN Health & Fitness**: AI Calorie Tracker – FoodPilot is #2 Grossing and #9 Free; Caloer (Vietnamese developer) #10 Free; CalSnap #11 Free / #15 Grossing; Dietfit AI #5 Grossing; Calog #10 Grossing — [VN H&F grossing RSS](https://itunes.apple.com/vn/rss/topgrossingapplications/limit=100/genre=6013/json)
- **VN Food & Drink**: Vivino is #3 Grossing — [VN Food & Drink grossing RSS](https://itunes.apple.com/vn/rss/topgrossingapplications/limit=100/genre=6023/json)

#### Sensor Tower's own US category ranks (fetched with the dataset, US iPhone, late Sep 2026)
- CamScanner #7 Grossing Productivity (#143 overall grossing); iScanner #3 Grossing Business (#166 overall); PictureThis #3 Grossing Education (#109 overall); MyFitnessPal #1 Grossing H&F (#63 overall); Google app #1 Free Utilities (#20 overall); Google Translate #1 Free Reference; Translate Now #1 Grossing Reference; Gauth #4 Free Education — [Sensor Tower CamScanner](https://app.sensortower.com/overview/388627783?country=US); [Sensor Tower PictureThis](https://app.sensortower.com/overview/1252497129?country=US)

### Inferences
- **Across Europe, Reference is now the category most crowded with camera-vision apps.** Coin, trading-card, antique, vinyl and "identify anything" apps plus AI translators fill most of the top-20 grossing slots in DE, GB, IT, ES, NL and the Nordics. For a new camera app targeting Europe, Reference is lucrative but highly contested. Education (plant and mushroom ID) and Business (scanners) are the other main battlegrounds.
- Vietnam behaves differently from Europe. Free utility/translation reach dominates (Google, Google Translate, CamScanner, Gauth), and the grossing slots go to aggressive weekly-subscription scanners and translators. There are few local camera-vision players; the exceptions found are EVOLLY (Photo Translator), AI Hay, Caloer and CalSnap.
- In Business, iScanner outranks Adobe Scan and CamScanner on grossing in most of Europe and the US (#2–5), even though it has fewer downloads than CamScanner. This reflects its higher price points (up to $12.99/month and weekly plans).

### Gaps
- The RSS feeds are **iPhone-only, top-100, single-day snapshots**. They do not show chart history, rank volatility or iPad ranks.
- Top Paid charts were not pulled. TurboScan Pro ($12.99 paid) is #5 in US Business Top Paid per Sensor Tower's ranking field only — [Sensor Tower TurboScan Pro](https://app.sensortower.com/overview/342548956?country=US)
- The Photo & Video category contained no identifier or scanner apps in the top 100 of any tracked store (it is dominated by editors and camera-filter apps).

## Q5. Europe focus: which European publishers/apps are strong, and how do they perform in major EU stores?

### Takeaway
European-built camera/vision apps are strongest in nutrition, product scanning, translation, document scanning and science-backed nature ID:
- **Nutrition**: Yazio (DE), Foodvisor (FR), Lifesum (SE)
- **Product scanning**: Yuka (FR), CodeCheck (DE)
- **Translation**: DeepL (DE), Translate Now/Air Apps (PT)
- **Document scanning**: Genius Scan (FR), Luni Scanner (FR), Scan Shot (ES)
- **Nature ID**: PlantNet (FR), Flora Incognita (DE), ObsIdentify (NL)

Most high-grossing identifier and scanner apps in Europe, however, come from Chinese, Turkish, Ukrainian and US publishers.

### Cited Findings

#### European-headquartered publishers (HQ per Sensor Tower `publisher_country`), iOS worldwide Aug-2026 estimates and EU chart peaks (27 Sep 2026)
| App (publisher, country) | WW iOS DL / revenue (ST, Aug-26) | Strongest EU chart positions (RSS, 27 Sep 2026) | EU rating base (Lookup API) | Offline |
|---|---|---|---|---|
| [Yazio](https://app.sensortower.com/overview/946099227?country=US) (YAZIO, DE) | 500k / $5M | DE #20 overall grossing, #2 H&F grossing, #4 H&F free; FR #74 overall / #4 H&F grossing; IT #4, FI #3 H&F grossing | DE 443,452; FR 143,596 | n/a |
| [Foodvisor](https://app.sensortower.com/overview/1064020872?country=US) (Foodvisor, FR) | 400k / $2M | FR #84 overall / #5 H&F grossing; FI #99 overall / #7 H&F grossing; NL #13, DK #12 H&F grossing | FR 72,303 | n/a |
| [Lifesum](https://app.sensortower.com/overview/286906691?country=US) (Lifesum AB, SE) | 80k / $800k | SE #44 overall / #2 H&F grossing; NO #61 overall / #3; DK #50 overall / #4; DE #18 H&F grossing | DE 81,588; SE 69,387 | n/a |
| [Yuka](https://app.sensortower.com/overview/1092799236?country=US) (Yuca, FR) | 800k / $1M | IT #3, GB #6, ES #6, FR #8, DE #12 H&F **free**; FR #16, IT #16 H&F grossing | FR 295,537; DE 11,505 | Premium offline (100k products) |
| [CodeCheck](https://app.sensortower.com/overview/359351047?country=US) (Producto Check, DE) | 7k / $20k | not in top-100 | DE 28,012 | n/a |
| [Open Food Facts](https://app.sensortower.com/overview/588797948?country=US) (FR non-profit) | 10k / <$5k | not in top-100 | FR 994 | n/a |
| [DeepL](https://app.sensortower.com/overview/1552407475?country=US) (DeepL SE, DE) | 200k / $80k | DE #4 Reference free, #12 grossing; FI #9, FR #14, ES #14, NL #14 Reference free | n/a in table (US 13,279) | No offline advertised |
| [Translate Now](https://app.sensortower.com/overview/1348028646?country=US) (Air Apps, PT) | 500k / $3M | #2 DE, #3 GB, #4 DK, #5 IT Reference grossing | GB/DE in ratings table | Offline mode listed |
| [QR Code Reader](https://app.sensortower.com/overview/1226650677?country=US) (Air Apps, PT) | 80k / $700k | DE #29 Utilities grossing | – | QR decode (inferred on-device) |
| [Genius Scan](https://app.sensortower.com/overview/377672876?country=US) (The Grizzly Labs, FR) | 200k / $300k | SE #11, NO #11, DK #14, DE #17 Business grossing | DE 118,859; FR 174,602 | **On-device** |
| [Scanner – Luni](https://app.sensortower.com/overview/1291962681?country=US) (Luni, FR) | 100k / $400k | FR #7 Business grossing, #16 free; FI #9 grossing, #15 free; DE #13 grossing | FR 182,651 | n/a |
| [Scan Shot](https://app.sensortower.com/overview/1575194801?country=US) (Scanner App PDF Tool, ES) | 20k / $700k | NO #8, DE #11 Business grossing | – | n/a |
| [Vivino](https://app.sensortower.com/overview/414461255?country=US) (Vivino ApS, DK) | 100k / $300k | **NO #1**, NL #2, SE #2, DK #3 Food & Drink grossing | – | n/a |
| [PlantNet](https://app.sensortower.com/overview/600547573?country=US) (Cirad/Pl@ntNet consortium, FR) | 90k / <$5k (free) | NL #24, FR #38, FI #39 Education free | DE 4,772; NL 1,668 | **Embedded offline model** |
| [Flora Incognita](https://app.sensortower.com/overview/1297860122?country=US) (TU Ilmenau / MPI-BGC team, DE) | 30k / <$5k (free) | DE #22 Education free | DE 26,540 | Cloud ID (offline only saves observations) |
| [ObsIdentify](https://app.sensortower.com/overview/1464543488?country=US) (Observation International, NL) | 10k / <$5k (free) | **NL #9 Education free** | NL 215 | n/a |
| [Dog Scanner](https://app.sensortower.com/overview/1447489158?country=US) (Siwalu, DE) | 6k / <$5k | not in top-100 | – | Premium offline |
| [Be My Eyes](https://app.sensortower.com/overview/905177575?country=US) (DK) | 70k / <$5k | DE #75 Lifestyle free | – | n/a |
| [Miiskin](https://app.sensortower.com/overview/1214795331?country=US) (DK) | <5k / $7k | IT #35 Medical grossing | – | n/a |
| [BitePal](https://app.sensortower.com/overview/6479529917?country=US) (Reface Lithuania, LT) | 100k / $500k | IT #41 H&F grossing | – | n/a |
| [Planto](https://app.sensortower.com/overview/1531728753?country=US) (Appagon, FR) | 20k / $100k | NO #5, DK #7 Education grossing | – | n/a |
| [Prizmo Go](https://app.sensortower.com/overview/1183367390?country=US) (Creaceed, BE) | <5k / <$5k | – | – | **On-device OCR** |
| [TapMedia QR Reader](https://app.sensortower.com/overview/368494609?country=US) (TapMedia, UK) | 80k / $300k | NO #11, DK #11, SE #12, FI #13 Utilities grossing | GB 55,412 | n/a |
| [Dext](https://app.sensortower.com/overview/418327708?country=US) (Dext Software, UK) | 10k / $80k | GB #25 Business grossing | – | Cloud |
| [Gizmo: AI Tutor](https://app.sensortower.com/overview/1610516671?country=US) (Save All, UK) | 200k / $200k | NO #21, SE #26, GB #30 Education free | – | n/a |
| [Brainly](https://app.sensortower.com/overview/745089947?country=US) (Brainly, PL) | 10k / $100k | not in EU top-100 | FR 70,299 | n/a |

(Rating counts: [iTunes Lookup API](https://itunes.apple.com/lookup?id=946099227&country=de), 27 Sep 2026; chart positions: Apple RSS feeds, e.g., [SE H&F grossing](https://itunes.apple.com/se/rss/topgrossingapplications/limit=100/genre=6013/json).)

#### Non-European publishers that dominate European charts (27 Sep 2026)
- **Scanners, Business grossing**: iScanner (BPMobile) is #2 DE (#94 overall DE), #3 FR/NL/SE/DK and #4 NO/FI. Adobe Scan is #3 IT/FI, #4 DE and #5 NL/SE/NO. Scanner Pro (Readdle, Ukraine) is #6 DE/NO and #7 IT/SE. "Scanner App – Scan PDF & Docs" (TapSuite, Turkey) is #5 IT, #6 SE and #7 DK — [DE Business grossing RSS](https://itunes.apple.com/de/rss/topgrossingapplications/limit=100/genre=6000/json)
- **Identifiers, Reference/Education grossing**: CoinSnap is #2 IT and #3 DE/ES. CoinIn (Vortemol, Ukraine) is #3 Free in DE, GB and ES, and #3 IT / #4 DE Grossing. PictureThis is #2 GB/ES Education grossing and #81–88 overall grossing in GB, DE and ES. Picture Mushroom is #3 DK and #6 DE Education free and #4 DK grossing — [IT Reference grossing RSS](https://itunes.apple.com/it/rss/topgrossingapplications/limit=100/genre=6006/json); [DK Education free RSS](https://itunes.apple.com/dk/rss/topfreeapplications/limit=100/genre=6017/json)
- **Scanbot/SwiftScan**: SwiftScan (publisher Maple Media Apps, US) has Germany as its #1 country (top countries DE, US, FR; DE rating base 36,582; #35 DE Utilities grossing), but earns only about $40k a month on iOS worldwide. That SwiftScan is the former German Scanbot consumer app is background knowledge, not re-verified in this pass. The "Scanbot SDK, Inc." listings in the DE store are SDK demo apps (27 and 15 ratings) — [Sensor Tower SwiftScan](https://app.sensortower.com/overview/834854351?country=US); [iTunes search DE "Scanbot"](https://itunes.apple.com/search?term=Scanbot&entity=software&country=de)

### Inferences
- European strength is concentrated in **"trust" categories**: nutrition science (Yazio, Lifesum, Foodvisor), product transparency (Yuka, CodeCheck, Open Food Facts), privacy-first scanning (Genius Scan) and publicly funded science ID (PlantNet, Flora Incognita, ObsIdentify). In fast-follow "identify anything" and weekly-paywall scanner clones, non-EU publishers dominate the grossing charts.
- The Nordics (SE, NO, DK, FI) consistently place identifier and QR/scanner apps higher in grossing ranks than larger EU markets. Examples: Genius Scan #11 SE/NO, TapMedia QR #11–13, Calo #10–13 FI/DK, Picture Mushroom #3–4 DK. This suggests high willingness to pay per user in the Nordics.
- For a privacy-first, offline camera app aimed at Europe, the whitespace appears to be **offline identifiers**. Only PlantNet, Seek and Merlin do this well today, and all three are free/non-profit. Paid offline OCR/translation is the other gap, since Apple's built-in features are the main competition there.

### Gaps
- Country-level download and revenue estimates for DE, GB, FR, IT, ES, NL and the Nordics were **not available** from free sources. Only ranks and rating counts are given as proxies.
- No figures were found for Scanbot SDK licensing revenue, Genius Scan company revenue, Yuka revenue or subscriber counts, or Foodvisor/Yazio disclosed ARR.
- Poland, Portugal, Austria and Switzerland charts were not pulled. CodeCheck's top countries are DE, AT and CH per Sensor Tower, so the DACH region matters for CodeCheck.
