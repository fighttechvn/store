# Europe market and optimization for an offline-first, sensor-based iPhone app (camera, OCR, scanning, identification, LiDAR, on-device AI), as of September 2026

Research date: 2026-09-27. Every number and rule below has a source and date. "n/a" means no reliable source was found. Where a figure came from a search-result snippet or a small-model page summary and not from a primary document, it is marked "(snippet)" or "(unverified)".

---

## 1. iOS share and App Store spending by European country (2025–2026): where ARPU and willingness to subscribe are highest

### Takeaway
iOS has about 37% of mobile web traffic in Europe overall (StatCounter, Aug 2026). The share is far higher in the Nordics (Sweden, Norway, Denmark about 59–63%), Switzerland (about 58%) and the UK (about 51%) than in Germany, Spain, the Netherlands and Poland (about 27–31%). Sensor Tower names the UK, Germany and France as Europe's top revenue markets. RevenueCat puts Western Europe second only to North America on most subscription metrics, and at the top on one: first-year revenue per payer. The Nordics, Switzerland and the UK are therefore the iPhone-heavy, high-spending storefronts. Germany and France matter for absolute revenue, not iOS share.

### Cited Findings
**Mobile OS share (StatCounter, share of mobile web page views, August 2026):**
- Europe overall: iOS 37.25%, Android 62.73% — [StatCounter Europe](https://gs.statcounter.com/os-market-share/mobile/europe)
- United Kingdom: iOS 51.47% / Android 48.51% — [StatCounter UK](https://gs.statcounter.com/os-market-share/mobile/united-kingdom)
- Germany: iOS 27.54% / Android 72.44% — [StatCounter DE](https://gs.statcounter.com/os-market-share/mobile/germany). This conflicts with the 37.56% that World Population Review gives for Oct 2024–Nov 2025, citing StatCounter-type data — [WPR](https://worldpopulationreview.com/country-rankings/iphone-market-share-by-country). A single StatCounter month can swing by several points.
- France: iOS 36.26% / Android 63.73% — [StatCounter FR](https://gs.statcounter.com/os-market-share/mobile/france)
- Italy: iOS 34.96% / Android 65.03% — [StatCounter IT](https://gs.statcounter.com/os-market-share/mobile/italy)
- Spain: iOS 31.35% / Android 68.64% — [StatCounter ES](https://gs.statcounter.com/os-market-share/mobile/spain)
- Netherlands: iOS 30.75% / Android 69.24% — [StatCounter NL](https://gs.statcounter.com/os-market-share/mobile/netherlands). WPR gives 38.07% for Oct 2024–Nov 2025 — [WPR](https://worldpopulationreview.com/country-rankings/iphone-market-share-by-country)
- Switzerland: iOS 57.58% / Android 42.41% — [StatCounter CH](https://gs.statcounter.com/os-market-share/mobile/switzerland)
- Sweden: iOS 60.16% / Android 39.84% — [StatCounter SE](https://gs.statcounter.com/os-market-share/mobile/sweden)
- Norway: iOS 59.38% / Android 40.6% — [StatCounter NO](https://gs.statcounter.com/os-market-share/mobile/norway)
- Denmark: iOS 62.84% / Android 37.13% — [StatCounter DK](https://gs.statcounter.com/os-market-share/mobile/denmark)
- Poland: iOS 30.64% / Android 69.3% — [StatCounter PL](https://gs.statcounter.com/os-market-share/mobile/poland)
- Other countries, from WPR (period Oct 2024–Nov 2025): Austria 45.19%, Belgium 46.38%, Ireland 48.38%, Portugal 34.4%, Finland 30.62% — [WPR](https://worldpopulationreview.com/country-rankings/iphone-market-share-by-country)
- Method caveat: StatCounter measures page views across more than 1M websites. It does not measure installed base or sales — [StatCounter / WPR summary](https://worldpopulationreview.com/country-rankings/iphone-market-share-by-country)

**Consumer spending (Sensor Tower and others):**
- Worldwide IAP and paid-app revenue reached $167B in 2025 (+10.6% YoY). Non-game apps earned $85.6B (+21% YoY), more than games ($81.8B) for the first time — [Sensor Tower press release, State of Mobile 2026, Jan 2026](https://sensortower.com/press/press-release-boosted-by-gen-ai-services-consumers-spent-more-money-in-apps-than-games-for-first-time)
- "Western European markets also contributed to the rapid growth, led by the United Kingdom, Germany, and France." Time spent grew in the UK, was flat in France and fell in Germany (the gaming context) — [Sensor Tower State of Mobile 2026 blog, Jan 2026](https://sensortower.com/blog/state-of-mobile-2026)
- "IAP revenue across Europe climbed 24% year-over-year, roughly double the global figure." This came from a snippet that appeared with Sensor Tower Digital Market Index results. The quarter was not confirmed by reading the full page (snippet, unverified) — [Sensor Tower Q2 2025 DMI](https://sensortower.com/blog/q2-2025-digital-market-index)
- Older reference point: in 2021 Sensor Tower forecast UK App Store plus Google Play spending of $8.1B in 2025 (from $2.9B in 2020) and $42B across the European region by 2025. These are forecasts, not actuals — [Sensor Tower 5-year forecast](https://sensortower.com/blog/sensor-tower-app-market-forecast-2025)
- 2025–2026 App Store consumer spending by country (DE, FR, IT, ES, NL, CH, Nordics, PL): n/a. Sensor Tower and data.ai country tables are paywalled.

**Subscription willingness (RevenueCat State of Subscription Apps 2026; sample 115,000+ apps, $16B revenue, mostly 2025 data):**
- Western Europe median download-to-paid conversion by day 35 is 2.0%, against 2.6% in North America and 1.4% in India/SEA. The top quartile is above 4.3% — [RevenueCat SOSA 2026](https://www.revenuecat.com/state-of-subscription-apps)
- Western Europe trial-to-paid median is 29.7% (North America 34.2%). Download-to-trial by day 30 is 5.0% (North America 7.1%) — [RevenueCat SOSA 2026](https://www.revenuecat.com/state-of-subscription-apps) (page summary, unverified)
- Western Europe median first-year realized LTV per payer: $25 according to the snippet, or $26.64 according to the page summary, which calls it "highest among all regions". North America is $32 in the snippet. The two readings conflict, so treat this as roughly $25–27 — [RevenueCat SOSA 2026](https://www.revenuecat.com/state-of-subscription-apps)
- Western Europe median prices: weekly $7.03, monthly $9.99, annual $39.44. Plan mix by subscriptions sold: monthly 41%, yearly 35%, weekly 17% — [RevenueCat SOSA 2026](https://www.revenuecat.com/state-of-subscription-apps) (page summary, unverified)
- Hard paywalls convert about 5x better than freemium (10.7% vs 2.1%), with similar first-year retention. This figure is likely global, not EU-specific — [RevenueCat SOSA 2026](https://www.revenuecat.com/state-of-subscription-apps)
- Higher-priced apps convert about 2x better: median 2.8% for high-priced, 2.0% for mid-priced and 1.4% for low-priced apps (global) — [RevenueCat SOSA 2026](https://www.revenuecat.com/state-of-subscription-apps)

### Inferences
- Where iOS share is highest: Denmark, Sweden, Norway, Switzerland and the UK are the European storefronts where iPhone users are the majority. They also have high incomes, so they are strong candidates for launch, press outreach and early paid tests.
- Where absolute revenue is: iOS share in Germany and France is low, but their large populations still put them among the top revenue markets, as Sensor Tower's statement shows. German and French localization is essential even though the iPhone share there is below 40%.
- Poland, Spain and the Netherlands (about 31% iOS in Aug 2026) are secondary markets for a paid iOS-only app.
- Western Europe converts slightly less than North America, but first-year revenue per payer is comparable. A $/€9.99 monthly or $/€39.99 annual anchor matches the regional medians.

### Gaps
- Per-country App Store consumer spending and ARPU for 2025 or 2026: not found in public sources. Sensor Tower, data.ai (now Sensor Tower) and Appfigures country tables are paywalled.
- A country-by-country ranking of subscription willingness within Europe (for example Nordics vs DACH vs Southern Europe): not found. RevenueCat reports only "Western Europe".
- Kantar Worldpanel iOS sales share by country for 2025–2026: not retrieved.

---

## 2. Which camera, OCR, scanner, identifier and 3D apps lead in Europe, and European success stories with disclosed numbers

### Takeaway
Europe has an unusually strong set of homegrown scanner and identifier apps: Yuka (FR), Genius Scan (FR), Pl@ntNet (FR), Flora Incognita (DE), CodeCheck (CH), Vivino (DK), ObsIdentify (NL) and the Scanbot SDK (DE). Several of them are publicly funded or run as non-profits and are free, which pulls down the price users expect for basic identification. Global subscription players such as PictureThis (Glority) earn the large revenue. Public per-storefront chart data (Top Free/Top Grossing by category) for these apps is not available without paid tools.

### Cited Findings
**Food and product scanning**
- Yuka (France): 2025 revenue shown on its English "Independence" page is "Premium Subscriptions: $11,884,771" and "Books & Calendars: $57,694". The currency is as the page displays it; the company is French. Yuka is 100% financed by users, takes no money from brands, runs with "a small team of 20", and publishes its balance sheet — [Yuka Independence page](https://yuka.io/en/independence/)
- Yuka is reported to have 73M users (snippet; an earlier figure was 55M users across 12 countries) — [Glossy](https://www.glossy.co/beauty/yuka-beauty-wellness-product-scanning-app/); [US Chamber CO—](https://www.uschamber.com/co/good-company/the-leap/yuka-app-organic-growth). The US Chamber piece says Yuka grew with "no marketing strategy" (organic and word of mouth) — [US Chamber CO—](https://www.uschamber.com/co/good-company/the-leap/yuka-app-organic-growth)
- CodeCheck (Zurich, CH; ETH Zurich roots): the company reported more than 10M downloads and 4.5M users in its 2021 "About" document. No 2025 figure was found — [CodeCheck About PDF, 2021](https://codecheck-app.com/wp-content/uploads/2021/01/About_CodeCheck-EN.pdf)
- Vivino (Copenhagen, DK; wine-label scanning): 74M+ users and 3.26B+ scanned labels, per a secondary source citing Vivino's About page, 2025/26 — [Expanded Ramblings](https://expandedramblings.com/index.php/vivino-facts-statistics/)
- Too Good To Go (Copenhagen, DK; not a camera app, but a European consumer-app success): 120M registered users, 180,000 partners, 21 countries — [TGTG 2025 Impact Report](https://www.toogoodtogo.com/en-us/impact-report) (snippet)

**Plant and nature identification**
- Pl@ntNet (France; built by the IRD, CIRAD, INRA(E), INRIA and Tela Botanica): app launched in 2013, identifies more than 77,000 species, available in 19 languages, 10M downloads as of 2019, more than a billion photos processed. The Horizon Europe projects MAMBO and GUARDEN have funded improvements since 2022 — [Wikipedia Pl@ntNet](https://en.wikipedia.org/wiki/Pl@ntNet)
- AppBrain lists about 49M Android downloads for Pl@ntNet (snippet, about Aug–Sep 2026) — [AppBrain](https://www.appbrain.com/app/plantnet-plant-identification/org.plantnet). An older Interreg page gives more than 20M downloads, 2.2M accounts and 300–500k daily active users — [Interreg Europe](https://www.interregeurope.eu/good-practices/plntnet)
- Flora Incognita (Germany; TU Ilmenau with the Max Planck Institute for Biogeochemistry Jena): more than 5M downloads since 2018, more than 300,000 identification requests a day, 18 languages. It is publicly funded by BMBF, BfN, BMU and the state of Thuringia — [floraincognita.com](https://floraincognita.com/); [TU Ilmenau](https://www.tu-ilmenau.de/en/news/tu-ilmenau-new-ai-for-flora-incognita). AppBrain shows 7.9M Android downloads (snippet) — [AppBrain](https://www.appbrain.com/app/flora-incognita/com.floraincognita.app.floraincognita)
- ObsIdentify (Netherlands; Observation International with Naturalis and Natuurpunt): free, identifies wild plants, animals and fungi in Europe; 1.4M Android downloads, about 770 a day (AppBrain, snippet) — [AppBrain](https://www.appbrain.com/app/obsidentify/org.observation.obsidentify); [App Store](https://apps.apple.com/us/app/obsidentify/id1464543488)
- PictureThis (Glority, China; the global leader in paid plant ID): Sensor Tower estimates about $5M a month on the App Store and $700k on Google Play (snippet, Sensor Tower public overview; geography unclear) — [Sensor Tower app overview](https://app.sensortower.com/overview/1252497129?country=US)
- Market-research estimates put plant-ID apps at $285M in 2024 and Europe at 16.85% of the global market in 2025. These come from low-quality market-research sites and should not be relied on — [DataHorizzon](https://datahorizzonresearch.com/global-plant-identification-apps-market-48763); [Cognitive Market Research](https://www.cognitivemarketresearch.com/plant-identification-apps-market-report)

**Document scanning and OCR**
- Genius Scan (The Grizzly Labs, Paris, France): independent and bootstrapped with no funding rounds — [Tracxn](https://tracxn.com/d/companies/thegrizzlylabs/__KRwTQzmT1UfBqhX17U6OLwNu5UYJrp6ukujNAmIjYGI); [Grizzly Labs About](https://thegrizzlylabs.com/about/). It reports 5M MAU and more than 2x revenue growth (Sub Club podcast, Jan 2025) — [Sub Club](https://subclub.com/episode/bootstrapping-a-subscription-app-to-5m-mau-and-2x-revenue-growth-bruno-virlet-genius-scan) — and "tens of millions" of downloads — [Grizzly Labs](https://thegrizzlylabs.com/genius-scan/)
- Scanbot SDK (Bonn, DE; formerly doo GmbH; B2B scanning, barcode and OCR SDK): acquired by Apryse (Thoma Bravo portfolio) in July 2025 — [Apryse blog](https://apryse.com/blog/apryse-acquires-scanbot-and-accusoft); [Crunchbase, 2025-07-10](https://www.crunchbase.com/acquisition/pdftron-acquires-scanbot--6da55d86). Revenue estimates conflict ($2.6M from GetLatka vs $14.6M from Growjo). Both are unreliable estimators — [GetLatka](https://getlatka.com/companies/scanbot); [Growjo](https://growjo.com/company/Scanbot_SDK)

**LiDAR and 3D**
- magicplan uses the iPhone/iPad LiDAR sensor to capture 2D and 3D floor plans in real time — [magicplan Help](https://help.magicplan.app/how-does-lidar-scan-work). A competitor's comparison says LiDAR-based magicplan scans are "sufficient for renovation planning and energy audits", while non-LiDAR scans need manual correction — [Amrax blog](https://amrax.ai/blog/magicplan-alternative/). No Europe user or revenue numbers were found.

### Inferences
- Europe rewards trust-first, independent scanner apps. Yuka (brand-independent, user-funded), Pl@ntNet and Flora Incognita (academic, free, ad-free) and Genius Scan (bootstrapped, privacy-minded) each built multi-million user bases largely organically.
- A new paid identifier app competes against free public-interest apps (Pl@ntNet, Flora Incognita, ObsIdentify) in DE, FR and NL. It needs a clear premium reason to pay: fully offline, no account, speed, multiple categories, or LiDAR measurement.
- Yuka's roughly $11.9M in 2025 revenue from about 73M users shows how low monetization per user is for mass-market consumer scanners. Niche professional uses (renovation measurement, document workflows) likely earn more per user.

### Gaps
- Actual Top Free/Top Grossing ranks for scanner, identifier, 3D and LiDAR apps in DE, FR, UK, IT, ES, NL, Nordic and PL storefronts (Productivity, Utilities, Photo & Video, Education, Food & Drink, Health & Fitness): n/a. This needs Sensor Tower, AppMagic, Appfigures or a manual App Store chart check.
- User or revenue numbers for Scaniverse, magicplan (Europe share), Readdle Scanner Pro, Adobe Scan and CamScanner in Europe: n/a.
- DeepL (Germany) camera-translation usage numbers: not researched or found.
- Current 2025–2026 user counts for CodeCheck, Flora Incognita and Pl@ntNet from company sources: n/a. Only older figures and AppBrain Android counts were found.

---

## 3. EU-specific regulation and App Store rules as of September 2026 (enacted vs proposed)

### Takeaway
A Vietnamese indie developer selling through the EU App Store must deal with six sets of rules:
- **Apple's EU terms under the DMA (enacted):** new unified terms take effect on 1 Oct 2026. IAP commission is 26%, or 15% for Small Business Program members and for subscriptions after year one.
- **DSA trader status (enacted):** public address, phone number and email on the product page, or the app is removed from EU storefronts.
- **GDPR (enacted):** makes "Data Not Collected" and on-device processing a genuine differentiator.
- **European Accessibility Act (applies since 28 Jun 2025):** covers e-commerce services in apps, but microenterprises are exempt for services.
- **AI Act Article 50 (applies since 2 Aug 2026):** transparency duties hit only chatbot, generative and emotion or biometric-categorization features, not plain classification or OCR.
- **EU "withdrawal button" (from 19 Jun 2026) and Germany's §312k BGB "Kündigungsbutton":** these apply mainly if the developer sells outside Apple IAP.

The Digital Fairness Act is still only a proposal, expected in Q4 2026.

### Cited Findings
**DMA and Apple EU business terms**
- On 23 Apr 2025 the European Commission found Apple in breach of the DMA's anti-steering obligations and fined it €500M. Apple had 60 days to comply — [EC press release IP/25/1085](https://ec.europa.eu/commission/presscorner/detail/en/ip_25_1085); [Record](https://therecord.media/eu-fines-apple-steering-meta-data-privacy-dma). Apple appealed in July 2025 — [CNBC, 7 Jul 2025](https://www.cnbc.com/2025/07/07/apple-appeal-eu-fine-app-store.html)
- **26 Jun 2025 terms (superseded):** developers could communicate and promote offers outside the app. Fees were a 2% initial acquisition fee, a store services fee of 13% (Tier 2) or 5% (Tier 1), and a 5% Core Technology Commission (CTC). That totals 20% or 12%; for Small Business Program members, 15% or 10%. The per-install Core Technology Fee (CTF) was to move to the CTC by 1 Jan 2026 — [RevenueCat, Jun 2025](https://www.revenuecat.com/blog/growth/apple-eu-dma-update-june-2025); [Apple Developer News](https://developer.apple.com/news/?id=awedznci). RevenueCat's reading: for Small Business Program developers "it does not make economic sense to adopt anything other than in-app purchases" — [RevenueCat](https://www.revenuecat.com/blog/growth/apple-eu-dma-update-june-2025)
- **18 Aug 2026 announcement: unified EU terms effective 1 Oct 2026** — [Apple Newsroom, 18 Aug 2026](https://www.apple.com/newsroom/2026/08/apple-announces-changes-for-apps-in-the-european-union/); [Apple Developer: apps in the EU](https://developer.apple.com/support/apps-in-the-eu); [9to5Mac](https://9to5mac.com/2026/08/18/apple-overhauls-app-store-fees-in-the-eu-with-new-unified-terms/)
  - App Store with Apple IAP: 26% standard. 15% for the Small Business Program, Mini Apps and Video Partner Programs, and auto-renewing subscriptions after the first year.
  - App Store with alternative payment processing inside the app: 20% standard, 10% reduced.
  - App Store with link-outs to web offers: 15% standard, 10% reduced.
  - Apps distributed outside the App Store (alternative marketplaces or web distribution): 5% CTC, which replaces the per-install CTF.
  - The initial acquisition fee and the store services fee are eliminated.
  - IAP can now be offered alongside alternative payment options, which the EU terms previously did not allow.
  - Developers must keep their chosen payment option(s) for 12 months — [Apple Developer support](https://developer.apple.com/support/apps-in-the-eu)
  - Eligibility for alternative or web distribution widens from 1 Oct 2026. An EU legal entity is no longer required. Qualifying criteria include a Dun & Bradstreet stability score, venture funding, an audit, a $1M stand-by letter of credit, or 1M first annual installs worldwide — [Apple Developer support](https://developer.apple.com/support/apps-in-the-eu)
  - The CTC is waived for small marketplace operators with less than €10M global revenue and less than €1M lifetime EU marketplace revenue. Developers must report CTC transactions monthly, within 15 days of month end — [Apple Developer support](https://developer.apple.com/support/apps-in-the-eu)
- A European developer coalition argued that the June 2025 terms still breach the DMA — [mobilegamer.biz](https://mobilegamer.biz/apples-new-eu-app-store-terms-still-breach-the-dma-says-european-developer-coalition/). Whether the Commission formally accepts the Oct 2026 terms is n/a. Apple says they came from "close collaboration with the European Commission" — [Apple Newsroom](https://www.apple.com/newsroom/2026/08/apple-announces-changes-for-apps-in-the-european-union/)

**DSA trader status (enacted; enforced by Apple)**
- DSA Articles 30 and 31 require Apple to verify and display trader contact details (address, phone number, email) on EU product pages — [App Store Connect Help](https://developer.apple.com/help/app-store-connect/manage-compliance-information/manage-european-union-digital-services-act-trader-requirements/)
- Since 16 Oct 2024 trader status has been required to submit updates. Apps without it were removed from EU storefronts on 17–18 Feb 2025 until status is provided and verified — [Apple Developer News](https://developer.apple.com/news/?id=einwn76m); [Apple upcoming requirements](https://developer.apple.com/news/upcoming-requirements/?id=02172025a)

**GDPR and privacy as a selling point**
- GDPR (Regulation (EU) 2016/679) applies to non-EU developers who process EU residents' personal data. Fines reach €20M or 4% of worldwide turnover (Art. 83) — [EUR-Lex GDPR](https://eur-lex.europa.eu/eli/reg/2016/679/oj)
- German users actively restrict app permissions (Bitkom survey): 52% of smartphone users have changed location settings, 38% have changed photo-access settings (44% of 14–29-year-olds vs 4% of those 65+), and 25% have changed contacts access — [Bitkom press release](https://www.bitkom.org/Presse/Presseinformation/Datenschutz-bei-Smartphone-Apps-im-Blick-behalten.html). Two-thirds of Germans trust domestic IT companies with their data, and most are concerned about data online — [Bitkom](https://www.bitkom.org/Presse/Presseinformation/Datenschutz-groesstes-Vertrauen-in-deutsche-Anbieter) (survey years not confirmed in snippet)
- Apple's App Privacy labels let an app that collects nothing show "Data Not Collected" on its product page — [Apple App Privacy Details](https://developer.apple.com/app-store/app-privacy-details/)

**European Accessibility Act (Directive (EU) 2019/882; national laws apply from 28 Jun 2025)**
- The Act defines e-commerce services as "a service provided at a distance, through websites and mobile device-based services, by electronic means and at the individual request of a consumer, with a view to concluding a consumer contract". Recital 43 extends this to the online sale of any product or service — [EUR-Lex 2019/882](https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX%3A32019L0882); [Bird & Bird 2025 guide](https://www.twobirds.com/en/insights/2025/a-guide-to-navigating-the-european-accessibility-act-for-online-retailers-service-providers-and-plat)
- Mobile apps are in scope, and the Act applies to non-EU providers serving EU consumers — [Level Access](https://www.levelaccess.com/blog/eu-accessibility-requirements-and-eaa-compliance/)
- Microenterprises (fewer than 10 employees AND annual turnover or balance sheet of no more than €2M) are exempt from the service accessibility requirements. The exemption covers services, not products — [Level Access](https://www.levelaccess.com/compliance-overview/european-accessibility-act-eaa/); [QualiBooth FAQ](https://www.qualibooth.com/resources/european-accessibility-act-faq/)

**EU AI Act (Regulation (EU) 2024/1689)**
- Article 50 transparency duties apply from 2 Aug 2026:
  - AI systems that interact directly with people, such as chatbots, must tell users they are dealing with AI.
  - Generative systems producing synthetic audio, images, video or text must mark outputs in a machine-readable way.
  - Deployers must disclose deepfakes and must inform people exposed to emotion-recognition or biometric-categorization systems.
  — [Goodwin, Aug 2026](https://www.goodwinlaw.com/en/insights/publications/2026/08/alerts-technology-dpc-eu-ai-act-transparency-obligations-now-in-force); [Morgan Lewis, Aug 2026](https://www.morganlewis.com/blogs/sourcingatmorganlewis/2026/08/eu-ai-acts-transparency-rules-what-went-into-effect-on-2-august)
- The AI Omnibus entered into force on 27 Jul 2026. It moved standalone (Annex III) high-risk obligations to 2 Dec 2027 and product-embedded (Annex I) obligations to 2 Aug 2028. Generative systems already on the market get until 2 Dec 2026 for Art. 50(2) marking. The Art. 50 transparency duties themselves were not delayed — [Goodwin](https://www.goodwinlaw.com/en/insights/publications/2026/08/alerts-technology-dpc-eu-ai-act-transparency-obligations-now-in-force); [Gibson Dunn](https://www.gibsondunn.com/eu-ai-act-omnibus-agreement-postponed-high-risk-deadlines-and-other-key-changes/)
- Fines for Art. 50 breaches reach €15M or 3% of worldwide turnover, whichever is higher — [Goodwin](https://www.goodwinlaw.com/en/insights/publications/2026/08/alerts-technology-dpc-eu-ai-act-transparency-obligations-now-in-force)

**Consumer protection and subscriptions**
- The EU withdrawal function (Directive (EU) 2023/2673) applies from 19 Jun 2026 to B2C distance contracts concluded through an online interface, "website, mobile app, or other software-based purchasing environment". Requirements:
  - A button labelled "withdraw from the contract here" or equivalent.
  - Available throughout the 14-day withdrawal period.
  - A two-step confirmation.
  - Automatic acknowledgment on a durable medium.
  — [Arnold & Porter, May 2026](https://www.arnoldporter.com/en/perspectives/advisories/2026/05/eu-withdrawal-button-uk-subscription-rules-and-data-protection-risks-for-us-online-sellers); [Winston Taylor](https://www.winstontaylor.com/insights/eu-withdrawal-buttons-required-for-consumer-online-contracts-from-june-19-2026-are-you-ready)
- Germany's §312k BGB "Kündigungsbutton" has applied since 1 Jul 2022 to consumer subscriptions (continuing obligations) that can be concluded online. It requires a "Jetzt kündigen" button (or equally clear wording), permanently available, with no login needed to start cancelling. Courts actively enforce it — [gesetze-im-internet §312k](https://www.gesetze-im-internet.de/bgb/__312k.html); [Bird & Bird case-law review 2025](https://www.twobirds.com/de/insights/2025/germany/k%C3%BCndigungsbutton-nach-%C2%A7-312k-bgb-%E2%80%93-eine-rechtsprechungs%C3%BCbersicht)
- For App Store purchases, Apple's EU Media Services terms (seller: Apple Distribution International, Cork) provide the 14-day right of withdrawal and refunds. This is lost for digital content once delivery starts with the consumer's consent and acknowledgment — [Apple Media Services Terms (IE)](https://www.apple.com/legal/internet-services/itunes/ie/terms.html); [Osborne Clarke](https://www.osborneclarke.com/insights/apple-introduces-14-day-refunds-what-does-that-mean-for-virtual-content-providers)
- UK subscription contract rules under the DMCC Act are expected to start in spring 2027. They require pre-contract disclosures, two 14-day cooling-off periods (at sign-up and after a trial or renewal), renewal reminders and easy cancellation, and they apply to non-UK businesses targeting UK consumers — [Arnold & Porter](https://www.arnoldporter.com/en/perspectives/advisories/2026/05/eu-withdrawal-button-uk-subscription-rules-and-data-protection-risks-for-us-online-sellers)
- The Digital Fairness Act is PROPOSED, not enacted. The Commission work programme lists a legislative initiative for Q4 2026 covering dark patterns, subscription and cancellation flows, drip pricing and addictive design. It is a headline item of the 2030 Consumer Agenda adopted 19 Nov 2025 — [EP Legislative Train](https://www.europarl.europa.eu/legislative-train/theme-protecting-our-democracy-upholding-our-values/file-digital-fairness-act); [digitalfairnessact.com](https://digitalfairnessact.com/)

**VAT**
- Under EU VAT rules, digital platforms that control pricing, terms and payment are treated as "deemed suppliers" (snippet) — [Bloomberg Tax](https://news.bloombergtax.com/daily-tax-report-international/eu-court-clarifies-vat-rules-for-app-stores-in-landmark-case). If a developer uses alternative payment options, the developer must provide tax information and handles the tax — [App Store Connect Help](https://developer.apple.com/help/app-store-connect/manage-tax-information/provide-tax-information-for-alternative-payment-options/)

### Inferences
- **Stay on Apple IAP in the EU.** From 1 Oct 2026, a Small Business Program developer (under $1M a year) pays 15% on EU IAP. A web link-out costs 10% plus payment-processor fees, VAT/OSS filing, and full exposure to the EU withdrawal button, Germany's Kündigungsbutton and the EAA as the direct trader. For a solo Vietnamese developer the saving is marginal and the compliance burden high. Alternative marketplaces and web distribution are not worth it at launch.
- **Plan for DSA trader status before submission.** A monetized app makes the developer a "trader", so an address, phone number and email are shown publicly on every EU product page. Use a business address or registered company (for example a Vietnamese company, or a virtual office or phone number) rather than a home address.
- **Make "offline and private" the headline.** On-device processing with no account and no analytics SDKs lets the product page show "Data Not Collected" and the app minimise GDPR obligations. That supports "Keine Daten verlassen dein iPhone" or "Vos données restent sur votre iPhone" messaging, which fits Bitkom's evidence of permission-conscious German users. Collecting photos server-side would create GDPR obligations (legal basis, DPA, cross-border transfers).
- **AI Act:** an offline classifier, OCR engine or LiDAR measurer is generally outside Art. 50. If the app adds an on-device chat assistant (for example Apple Foundation Models) or generates images or text, it must disclose AI interaction and machine-readable marking may apply. The provider-vs-deployer split when building on Apple's model is not settled in the sources. Label AI outputs as "AI-generated / KI-generiert" anyway.
- **EAA:** a one-person developer is very likely a microenterprise and exempt for services. Supporting VoiceOver, Dynamic Type and contrast is still cheap insurance and helps European press and editorial reviews. Accessibility is itself a product opportunity: camera plus OCR text-to-speech for low-vision users.
- **Subscription UX:** even though Apple handles cancellation for IAP, add an in-app "Manage/cancel subscription" link that deep-links to Apple subscription settings. Show clear renewal terms before purchase. This anticipates the Digital Fairness Act and the UK DMCC rules.
- **Mushroom and plant ID liability:** add safety disclaimers ("never eat based on the app") in every locale, given German poison-centre warnings (see section 5).

### Gaps
- Official Commission assessment of Apple's 1 Oct 2026 terms (compliant or not) and the status of Apple's appeal of the €500M fine: n/a.
- Whether Apple IAP subscriptions sold to German users count as Apple's contract (so Apple, not the developer, bears §312k duties): no authoritative source found. The inference is that Apple is the seller of record under its Media Services terms, but this is not confirmed for §312k specifically.
- Apple's handling of the new EU withdrawal-button requirement inside the App Store purchase flow: n/a.
- Whether Apple's "Accessibility Nutrition Labels" (reportedly announced in 2025) are live on EU product pages: not verified in this research.

---

## 4. Localization priorities: languages, storefront indexing, cultural and pricing preferences

### Takeaway
Every European App Store storefront except the UK and Ireland indexes English (U.K.) as an extra locale. So EN-UK metadata is a "free" second keyword slot across the EU, and it also serves as the default for Belgium and Ireland. The core set of languages is EN (UK plus US), DE, FR, IT, ES, NL, then SV, DA, NB, PL and PT-PT. Switzerland indexes DE, FR, IT and EN-UK, and Belgium indexes EN-UK, NL and FR, so these multilingual storefronts reward full coverage.

### Cited Findings
- Storefront default and additional App Store localizations, from Apple's reference table — [Apple App Store localizations reference](https://developer.apple.com/help/app-store-connect/reference/app-store-localizations):

| Storefront | Default language | Additional languages |
|---|---|---|
| United Kingdom | English (U.K.) | none |
| Ireland | English (U.K.) | none |
| Germany | German | English (U.K.) |
| Austria | German | English (U.K.) |
| Switzerland | German | English (U.K.), French, Italian |
| France | French | English (U.K.) |
| Belgium | English (U.K.) | Dutch, French |
| Italy | Italian | English (U.K.) |
| Spain | Spanish (Spain) | Catalan, English (U.K.) |
| Portugal | Portuguese (Portugal) | English (U.K.) |
| Netherlands | Dutch | English (U.K.) |
| Sweden | Swedish | English (U.K.) |
| Norway | Norwegian | English (U.K.) |
| Denmark | Danish | English (U.K.) |
| Finland | Finnish | English (U.K.) |
| Poland | Polish | English (U.K.) |

- Apple's list runs to about 50 localizations. The fetched summary said "47" but listed 50 names, including newly added Indian languages. It includes Vietnamese, Croatian, Czech, Greek, Hungarian, Romanian, Slovak, Slovenian and Ukrainian — [Apple reference](https://developer.apple.com/help/app-store-connect/reference/app-store-localizations)
- ASO practice: cross-localization means keywords from at least two locales are indexed per territory, and one localization can index in other storefronts where it is supported but not primary. Locales and storefronts are not one-to-one; EN-UK serves many storefronts — [AppFollow](https://appfollow.io/app-store-keywords-localizations); [aso.dev](https://aso.dev/metadata/cross-localization/); [MobileAction](https://www.mobileaction.co/blog/app-store-cross-localization/)
- Existing European apps' language breadth sets the benchmark: Pl@ntNet 19 languages — [Wikipedia](https://en.wikipedia.org/wiki/Pl@ntNet); Flora Incognita 18 languages — [TU Ilmenau](https://www.tu-ilmenau.de/en/news/tu-ilmenau-new-ai-for-flora-incognita)
- Western Europe median subscription prices: monthly $9.99, annual $39.44, weekly $7.03 — [RevenueCat SOSA 2026](https://www.revenuecat.com/state-of-subscription-apps) (page summary)

### Inferences
- **Priority order for a Europe-first iPhone app:**
  - Tier 1: EN-US, EN-UK, DE and FR. These cover the UK, Germany, Austria, Switzerland, France, Belgium and the biggest revenue markets.
  - Tier 2: IT, ES, NL, SV, DA and NB. Large markets, plus the Nordics with 59–63% iOS share.
  - Tier 3: PL, PT-PT and FI. Lower iOS share, but cheap to add.
- **Use the EN-UK locale strategically.** It is indexed in nearly every EU storefront, so its keyword field (100 characters) can carry English terms for "scanner", "plant identifier" and so on that complement the local-language metadata. It can also hold extra local-language brand or long-tail terms where this is permitted and makes sense.
- **Localize the app UI, not just the metadata.** The ML output needs localizing too: plant and mushroom names in DE, FR, PL and the Nordic languages (vernacular plus Latin) and OCR language packs (Latin-script Vision OCR). Include Swiss conventions (CHF, "ss" instead of "ß" in Swiss German).
- **Pricing:** set a EUR anchor that ends in .99 (€4.99 a month, €29.99–39.99 a year). Check Apple's automatically equalized GBP, CHF, SEK, NOK, DKK and PLN tiers. Consider a lifetime or one-time unlock alongside the subscription for privacy- and subscription-averse users (particularly DACH). This is an inference; no hard data on a German one-time-purchase preference was found.

### Gaps
- Share of European App Store revenue by language: n/a, no public source.
- Hard evidence that German users prefer one-time purchases over subscriptions: not found. It is an anecdotal belief only.
- Apple's exact EUR, GBP and CHF price points for each USD tier, and VAT-inclusive pricing mechanics, as of 2026: not fetched.

---

## 5. Europe-specific demand signals: foraging, food scanning, tax receipts, renovation and energy, accessibility

### Takeaway
Europe has concrete, regulation- or culture-driven demand for:
- mushroom and plant identification (a strong foraging culture, but health authorities warn against relying on apps);
- product and food-label scanning (Yuka in FR, CodeCheck in DE and CH);
- wine-label scanning (Vivino);
- LiDAR room and floor-plan capture tied to the EU building-renovation agenda (EPBD recast: renovation passports and enhanced Energy Performance Certificates due by 29 May 2026).

### Cited Findings
- **Mushroom foraging in Germany:**
  - 2025 was a good mushroom year and many amateurs are using identification apps. Poison centres (GIZ Nord) record about 1,000 mushroom-poisoning cases or suspected cases a year. Experts and the Deutsche Leberstiftung warn against relying on an app alone, citing lookalikes such as death cap vs champignon — [agrarheute](https://www.agrarheute.com/land-leben/pilzvergiftungen-giftnotruf-warnt-pilz-apps-585983); [Europe Online Magazine](https://www.europeonline-magazine.eu/risiko-pilzvergiftung-nicht-allein-auf-apps-verlassen); [ad-hoc-news](https://www.ad-hoc-news.de/wissenschaft/pilzsammeln-smartphone-apps-sind-lebensgefaehrlich-bei-der-bestimmung/70136708)
  - German-language mushroom guide apps exist as paid titles, for example "Pilzführer PRO" on the German App Store — [App Store DE](https://apps.apple.com/de/app/pilzf%C3%BChrer-pro/id523607704)
- **Plant ID:** Flora Incognita handles more than 300,000 identification requests a day — [floraincognita.com](https://floraincognita.com/). Pl@ntNet has processed more than a billion photos — [Wikipedia](https://en.wikipedia.org/wiki/Pl@ntNet)
- **Food and product scanning:** Yuka earned about $11.9M from premium subscriptions in 2025 — [Yuka](https://yuka.io/en/independence/). CodeCheck had more than 10M downloads by 2021 — [CodeCheck](https://codecheck-app.com/wp-content/uploads/2021/01/About_CodeCheck-EN.pdf)
- **Wine:** Vivino counts 3.26B+ scanned labels — [Expanded Ramblings](https://expandedramblings.com/index.php/vivino-facts-statistics/)
- **Renovation and energy (enacted directive; transposition deadline 29 May 2026):**
  - Member States must set up a renovation passport scheme (Annex VIII framework), and Energy Performance Certificates are to be enhanced and harmonised (Annex V) by 29 May 2026 — [EPBD summaries: GlobalABC](https://globalabc.org/resources/publications/accelerating-deep-renovation-eu-renovation-passports); [McCann FitzGerald](https://www.mccannfitzgerald.com/knowledge/environmental-and-planning/legal-regulation-of-energy-performance-of-buildings); [BUILD UP (EC)](https://build-up.ec.europa.eu/en/resources-and-tools/articles/epbd-aligned-data-model-building-renovation-passports-oneclickreno)
  - The recast also introduces digital building logbooks — [Net Zero Compare](https://netzerocompare.com/policies/eu-energy-performance-of-buildings-directive-epbd)
  - LiDAR floor plans (magicplan) are considered adequate for energy audits and renovation planning — [Amrax](https://amrax.ai/blog/magicplan-alternative/)
- **Scanner B2B demand in Germany:** Scanbot SDK customers include AXA, Generali, Telekom and DATEV (DATEV is Germany's tax-adviser software cooperative) (snippet) — [search summary of Scanbot sources](https://growjo.com/company/Scanbot_(by_doo_GmbH)); [Apryse](https://apryse.com/blog/apryse-acquires-scanbot-and-accusoft)

### Inferences
- **Best Europe-specific feature ideas for an offline sensor app:**
  - Offline mushroom and plant ID for foragers in DE, PL, the Nordics, CH and AT, working without mobile signal in forests, with strong lookalike and poison warnings.
  - Offline food-label and additive or allergen scanning using OCR of ingredient lists, which avoids the need for a barcode database.
  - LiDAR room measurement with export (PDF/DXF/area tables) for homeowners preparing renovation or energy-certificate (Energieausweis) consultations.
  - Receipt and document scanning with on-device OCR for tax filing (DE "Belege für die Steuererklärung", FR "notes de frais").
- **The offline advantage is real in Europe.** Forests, mountains and roaming situations (holiday travel across borders) are where cloud-based identifier apps fail.

### Gaps
- Quantified search or download demand for "Pilze bestimmen", "grzyby rozpoznawanie", "Belege scannen" and "Energieausweis app": n/a. Keyword tools such as AppTweak or Sensor Tower keyword volumes were not accessible.
- Polish and Nordic mushroom-foraging app usage statistics: not found.
- Evidence of consumer (not professional) LiDAR-app demand for the EPBD or Energieausweis: none found. The link is inferred from the regulation.

---

## 6. Marketing channels that work in Europe for utility apps

### Takeaway
Apple Ads (formerly Apple Search Ads) covers every major European storefront, and it now reaches 91 markets after the Dec 2024 expansion added Baltic and Central European countries. Per-locale ASO (section 4) is the core channel. The European success cases, Yuka and Genius Scan, grew mostly organically through word of mouth, press and trust positioning. Public data on TikTok effectiveness and on Apple editorial featuring in Europe was not found.

### Cited Findings
- Apple Search Ads expanded on 3 Dec 2024 by 21 countries to 91 markets. New European markets were Bulgaria, Cyprus, Estonia, Iceland, Latvia, Luxembourg, Slovakia, Slovenia and Türkiye. Existing European coverage included Austria, Belgium, Croatia, Czechia, Denmark, Finland, France, Germany, Greece, Hungary, Ireland, Italy, the Netherlands, Norway, Poland, Portugal, Romania, Spain, Sweden, Switzerland, Ukraine and the UK — [PPC Land](https://ppc.land/apple-search-ads-expands-to-21-new-countries-across-europe-asia-and-africa/); [Apple Ads countries](https://ads.apple.com/app-store/countries-and-regions)
- SplitMetrics reports a further "46 additional countries" for Apple Ads storefronts (date and details not verified) — [SplitMetrics](https://splitmetrics.com/blog/apple-search-ads-storefronts/)
- Yuka built a leading health app "with no marketing strategy" — [US Chamber CO—](https://www.uschamber.com/co/good-company/the-leap/yuka-app-organic-growth). Genius Scan bootstrapped to 5M MAU — [Sub Club](https://subclub.com/episode/bootstrapping-a-subscription-app-to-5m-mau-and-2x-revenue-growth-bruno-virlet-genius-scan)
- Sensor Tower advises that "country-specific forces – like local competition, tariffs, and regulations – make deep market knowledge critical" — [Sensor Tower SoM 2026](https://sensortower.com/blog/state-of-mobile-2026)

### Inferences
- **Launch sequence:** run Apple Ads exact-match campaigns per storefront in local-language keywords. Start in DE, FR, UK and the Nordics, where iOS share and ARPU are high and CPTs are likely lower than in the US (not verified).
- **Pitch local press with a privacy and offline angle:** heise, t3n, Caschys Blog, iphone-ticker.de and Macwelt in DE; Frandroid, iPhon.fr and Numerama in FR; Macitynet in IT; Applesfera in ES; iCulture in NL; Feber in SE; iMore UK. Apple editorial teams feature well-localized, accessible, privacy-respecting apps that use new iOS hardware features such as LiDAR, Vision and on-device ML.
- **Seasonal pushes:** mushroom and plant ID in spring and autumn, and mushroom season from September to October in DE and PL. Tax-receipt scanning before filing deadlines. Renovation and measurement around EPBD-related national news.

### Gaps
- Apple Ads CPT and CPA benchmarks per European country for 2025–2026: n/a.
- TikTok or Instagram effectiveness data for utility apps in Europe: n/a.
- How Apple App Store editorial featuring works per European storefront (local editorial teams, nomination via the App Store Connect "featuring nominations" form): not researched in this pass.

---

## 7. Concrete recommendations for optimizing a new offline-first sensor app for Europe

### Takeaway
Position the app as "private, offline, on-device" (Data Not Collected). Localize into EN-UK, DE and FR first and use the EU cross-indexing rules. Stay on Apple IAP (15% under the Small Business Program from 1 Oct 2026). Complete DSA trader status before submission. Keep AI features to classification and OCR, or disclose them. Target Europe-specific use cases: foraging ID, food-label OCR, LiDAR renovation measurement and tax-receipt scanning.

### Cited Findings
- EU IAP commission is 15% for Small Business Program members and for subscriptions after year one, from 1 Oct 2026 — [Apple Newsroom](https://www.apple.com/newsroom/2026/08/apple-announces-changes-for-apps-in-the-european-union/)
- DSA trader details are displayed publicly, and apps without them are removed from EU storefronts — [Apple Developer News](https://developer.apple.com/news/?id=einwn76m)
- EN-UK is an additional localization in almost every EU storefront; DE, FR and IT are indexed in Switzerland; NL and FR in Belgium — [Apple localization reference](https://developer.apple.com/help/app-store-connect/reference/app-store-localizations)
- iOS share is highest in DK, SE, NO, CH and UK (Aug 2026) — [StatCounter](https://gs.statcounter.com/os-market-share/mobile/europe)
- Western Europe first-year RLTV per payer is about $25–27, with median monthly $9.99 and annual about $39 — [RevenueCat SOSA 2026](https://www.revenuecat.com/state-of-subscription-apps)
- AI Act Art. 50 transparency duties have applied since 2 Aug 2026, with fines up to €15M or 3% — [Goodwin](https://www.goodwinlaw.com/en/insights/publications/2026/08/alerts-technology-dpc-eu-ai-act-transparency-obligations-now-in-force)

### Inferences (recommendations)
1. **Store listing:**
   - Screenshot 1 in each locale should carry the privacy and offline promise ("100% offline – keine Daten verlassen dein iPhone", "Fonctionne hors ligne – aucune donnée collectée").
   - Ship with a "Data Not Collected" privacy label, which means no third-party analytics or ads SDKs, or only privacy-preserving ones with truthful labels.
   - Show "Made without account / ohne Konto".
2. **Localization order:** EN-US and EN-UK, then DE and FR at launch; IT, ES, NL, SV, DA and NB within 1–3 months; PL, PT-PT and FI after that. Use distinct keyword sets per locale and exploit EN-UK cross-indexing.
3. **Monetization:**
   - A free tier with a clear premium unlock.
   - Test a hard paywall with a trial against freemium (RevenueCat: hard paywalls convert about 5x better, with similar retention).
   - EUR anchors of €4.99 a month and €29.99–39.99 a year, plus an optional lifetime unlock for DACH users.
   - Use Apple IAP only in the EU. Skip alternative PSPs and link-outs at this scale.
4. **Compliance checklist before EU submission:**
   - DSA trader status with a business address, phone and email.
   - A GDPR-compliant privacy policy in each language, even if nothing is collected.
   - Accessibility basics (VoiceOver, Dynamic Type), even if exempt as a microenterprise.
   - AI disclosure for any chat or generative feature.
   - Mushroom and plant safety disclaimers.
   - A "Manage subscription" link and clear renewal terms before purchase, in anticipation of the Digital Fairness Act and the UK DMCC rules (spring 2027).
5. **Features that differentiate in Europe:** offline species packs (European flora and fungi), multilingual OCR of ingredient labels and receipts, LiDAR room plans with m² tables and PDF export (metric-first), and Swiss, Nordic and Polish name localization.
6. **Go-to-market:** Apple Ads exact-match per storefront (DE, FR, UK and Nordics first), local tech press with the privacy and offline angle, seasonal campaigns (mushroom season Sep–Oct), and Apple featuring nominations timed to iOS releases.

### Gaps
- No public A/B data on privacy-message conversion uplift in European storefronts.
- No verified CPT or CPA data per country to size the Apple Ads budget.
