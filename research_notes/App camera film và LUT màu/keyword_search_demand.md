# Search demand & keyword trends — film camera apps, film filters, presets and LUTs (Google, Google Play, App Store, TikTok, YouTube, Reddit) — status 2026-09-27

Scope: what users search for around film-camera apps, film filters, presets and LUTs, which intents are growing or declining, and which keywords a new film camera / preset / LUT app should target in ASO. The benchmark apps are Filmode (`app.filmode`) and Filmode FilCam (`app.filmode.filcam`). Unless stated otherwise, all data below was pulled on **2026-09-27**. Raw scraping (Google Trends through the unofficial pytrends client; Google Play through google-play-scraper; App Store through Apple's public MZSearchHints endpoint; Google/YouTube autocomplete through suggestqueries.google.com) was done from a US-egress machine.

## 1. Google Trends: which search intents are really growing or declining (5-year and 12-month; Worldwide, US, VN, JP, KR, ID, BR, DE), after correcting for the 2025–26 "everything is trending" distortion

### Takeaway
Measured on the clean window (Oct-2021→Jun-2025, before the distortion), the Google intents that really grew are: **digicam** (≈6× worldwide; 7–19× in US/ID/DE), **Fujifilm recipes / film simulation** (2.3–5.4×), **dazz cam** (1.8× WW, 2.3× BR, but flat in ID and falling in VN since 2024), **color grading** (≈1.9×), **luts / cube lut** (1.6–2.0×), **disposable camera app** (2.8×) and a fad-type spike for **y2k camera** (spring 2026).

YouTube-search data, which shows no Aug-2025 artefact, gives the same picture: digicam 9.6×, fuji recipe 1.9× and still rising in 2026, lightroom presets 0.41×.

Declining intents: **vsco** (0.5× WW; 0.1× VN; 0.16× ID), **vsco filter**, **lightroom presets / preset lightroom** (0.66× WW, 0.52× VN, 0.28× ID), **picsart**, **huji cam** and **film look**. In Vietnam, the generic Google queries "app chụp ảnh", "app chỉnh màu" and "công thức màu" are also falling.

The large 2025–26 jumps in **film camera app, film filter, film filter app, photo filter app, retro/vintage camera app, film grain and film simulation** are mostly the Google Trends artefact. They are **not a real rise**.

### Cited Findings

**Data-quality check: the distortion is real, and I measured it with neutral control keywords**
- Industry commentary: Nick Malekos (Marketing Experts Hub, 2026-06-23) wrote that "Everything is trending. That's the problem," and that Google Trends shows "near-vertical spikes to 100 for terms that have no business moving." He tested 31 keywords, but the detail sits behind a paywall. — [Google Trends is Broken, Why does it Matter?](https://b2b.marketingexpertshub.com/p/google-trends-is-broken-why-does)
- Another 2026 source says Google Trends added a Gemini-powered Explore page and an official Trends API in 2026. That change could relate to the scaling differences, but this is unverified. — [StudioHawk](https://studiohawk.com.au/blog/google-trends/)
- My control measurements (worldwide, 5-yr weekly, pulled 2026-09-27):
  - The neutral head term **"calculator"** did not inflate: post-Aug-2025 ÷ pre ratio = 0.87. — [GT](https://trends.google.com/trends/explore?date=today%205-y&q=calculator)
  - The neutral **app** queries stepped up about 2× in **Aug-2025** and spiked again **Mar–Jun-2026**. Their post-Aug-2025 inflation was **3.0× for "weather app"**, **2.5× for "calculator app"** and **2.2× for "flashlight app"**. — [weather app](https://trends.google.com/trends/explore?date=today%205-y&q=weather%20app); [calculator app](https://trends.google.com/trends/explore?date=today%205-y&q=calculator%20app); [flashlight app](https://trends.google.com/trends/explore?date=today%205-y&q=flashlight%20app)
- Low-volume **English** queries were inflated far more than the controls, often in a single month. Worldwide monthly means: "film camera app" went 6→20→77 (Jun→Jul→Aug 2025), "film filter" went 9→24→71 and "photo filter app" went 19→30→73. Head terms such as lightroom, vsco and calculator did not jump (monthly table below). — [film camera app](https://trends.google.com/trends/explore?date=today%205-y&q=film%20camera%20app); [film filter](https://trends.google.com/trends/explore?date=today%205-y&q=film%20filter)
- **Local-language app queries show little or no inflation.** Post-Aug-25 inflation for each:
  - VN: "app thời tiết" 1.53×, "app máy tính" 0.98×
  - JP: "天気 アプリ" 1.19×, "電卓 アプリ" 0.80×
  - ID: "aplikasi cuaca" 1.26×
  - DE: "wetter app" 1.27×

  In the same countries, the sparse **English** control "weather app" jumped 10.9× (VN), 20.6× (JP), 49× (KR) and 7.5× (DE). The artefact therefore hits sparse English queries hardest, including in non-English markets. — e.g. [app thời tiết VN](https://trends.google.com/trends/explore?date=today%205-y&q=app%20th%E1%BB%9Di%20ti%E1%BA%BFt&geo=VN); [weather app JP](https://trends.google.com/trends/explore?date=today%205-y&q=weather%20app&geo=JP)
- Signs of non-human or odd traffic:
  - The worldwide "rising" related queries for **film grain** (12-mo) are dominated by translation requests of AI-image-prompt text, e.g. "terjemahkan shadows are open and lifted in the foreground from flash fill … visible but controlled film grain throughout dari inggris" (+58,550%), plus gaming queries such as "re9 film grain" (+53,750%) and "resident evil requiem film grain". — [film grain related queries](https://trends.google.com/trends/explore?date=today%2012-m&q=film%20grain)
  - "digicam" rising queries include "cason digicam" (+21,150%) and "sliding digicam" (+2,450%). — [digicam](https://trends.google.com/trends/explore?date=today%2012-m&q=digicam)
- **Rule applied in the tables:**
  - "pre-anomaly ratio" = average of Oct-2024–Jun-2025 ÷ average of Oct-2021–Jun-2022. This is the clean 3-year trend.
  - "post-Aug-25 inflation" = average of Aug-2025–Sep-2026 ÷ average of Oct-2024–Jul-2025. Compare it with the control for the same market. When a keyword's post-2025 rise is not above the control, or the keyword was flat before the anomaly and then jumped, it is labelled **NOT A REAL RISE / spike-inflated**.
  - "Aug–Sep 26 ÷ Aug–Sep 24" is the latest same-season check, taken after the spring-2026 spike faded.
  - Values are Google Trends 0–100 indices, normalised **per keyword** (5-yr weekly, 2021-09-26→2026-09-27). Absolute levels therefore cannot be compared across rows; see the relative-volume tables for that.
  - Trends matches query words in any order ("lightroom presets" = "presets lightroom", which gave identical series in BR). It also includes longer queries that contain the words, so "film filter" also captures movie and CapCut "filter film" searches.

**Worldwide monthly means showing the Aug-2025 break and Mar–Jun-2026 spike** (2026-09 is a partial month) — source: the per-keyword GT links in the tables below

| keyword (WW, 5-yr weekly index, monthly mean) | 2024-07 | 2025-01 | 2025-06 | 2025-07 | 2025-08 | 2025-09 | 2025-12 | 2026-02 | 2026-03 | 2026-04 | 2026-05 | 2026-06 | 2026-07 | 2026-08 | 2026-09 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| calculator | 76 | 88 | 71 | 71 | 77 | 78 | 65 | 69 | 75 | 84 | 79 | 63 | 59 | 59 | 56 |
| weather app | 20 | 19 | 23 | 31 | 53 | 52 | 53 | 50 | 65 | 72 | 81 | 82 | 58 | 49 | 36 |
| calculator app | 14 | 16 | 14 | 18 | 33 | 32 | 22 | 23 | 38 | 60 | 76 | 66 | 48 | 42 | 26 |
| photo filter app | 14 | 13 | 19 | 30 | 73 | 86 | 46 | 40 | 50 | 55 | 59 | 55 | 34 | 27 | 22 |
| film camera app | 5 | 5 | 6 | 20 | 77 | 77 | 58 | 42 | 55 | 59 | 71 | 65 | 45 | 27 | 16 |
| film filter | 6 | 7 | 9 | 24 | 71 | 60 | 58 | 76 | 73 | 78 | 84 | 85 | 57 | 39 | 30 |
| film simulation | 14 | 14 | 18 | 25 | 63 | 55 | 62 | 79 | 76 | 82 | 97 | 85 | 81 | 41 | 29 |
| film grain | 11 | 13 | 15 | 19 | 40 | 38 | 39 | 58 | 61 | 84 | 80 | 66 | 52 | 40 | 39 |
| y2k camera | 3 | 2 | 3 | 2 | 5 | 6 | 6 | 11 | 33 | 83 | 76 | 21 | 7 | 15 | 11 |
| ccd camera | 22 | 23 | 23 | 26 | 36 | 35 | 32 | 56 | 54 | 86 | 86 | 52 | 38 | 41 | 28 |
| digicam | 29 | 62 | 44 | 60 | 57 | 54 | 77 | 61 | 76 | 83 | 77 | 73 | 75 | 87 | 78 |
| dazz cam | 37 | 36 | 46 | 56 | 55 | 48 | 61 | 43 | 77 | 52 | 55 | 48 | 52 | 46 | 44 |
| fujifilm recipes | 26 | 27 | 40 | 42 | 50 | 45 | 63 | 56 | 62 | 77 | 87 | 67 | 60 | 54 | 44 |
| luts | 41 | 50 | 53 | 54 | 64 | 66 | 68 | 67 | 71 | 77 | 80 | 73 | 68 | 63 | 58 |
| color grading | 28 | 36 | 41 | 44 | 64 | 66 | 63 | 66 | 74 | 84 | 84 | 80 | 66 | 53 | 47 |
| lightroom presets | 59 | 50 | 53 | 56 | 61 | 58 | 51 | 48 | 53 | 66 | 61 | 53 | 42 | 39 | 35 |
| vsco | 52 | 40 | 37 | 38 | 36 | 34 | 33 | 31 | 32 | 31 | 30 | 29 | 29 | 29 | 28 |

**Worldwide, 5-year (weekly) — pulled 2026-09-27**

| keyword | 2022 avg | 2024 avg | 2026 YTD | pre-anomaly ratio | post-Aug-25 inflation | Aug–Sep 26 ÷ Aug–Sep 24 | peak week | zero wks | verdict / notes | src |
|---|---|---|---|---|---|---|---|---|---|---|
| calculator | 77.6 | 84.8 | 68.4 | 1.11 | 0.87 | 0.67 | 2024-01-28 | 0% | CONTROL (non-app, high volume): flat/declining → no inflation of big head terms | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=calculator) |
| weather app | 20.0 | 16.8 | 61.7 | 0.92 | 3.01 | 2.62 | 2026-05-31 | 0% | CONTROL (app query): step-up Aug-2025 + Mar–Jun-2026 spike = baseline inflation ≈2.2–3.0× | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=weather%20app) |
| calculator app | 14.2 | 14.9 | 45.3 | 1.11 | 2.53 | 2.28 | 2026-05-31 | 0% | CONTROL (app query): same artefact (2.5×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=calculator%20app) |
| flashlight app | 37.2 | 26.2 | 64.8 | 0.73 | 2.22 | 1.51 | 2026-05-03 | 0% | CONTROL (app query): same artefact (2.2×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=flashlight%20app) |
| photo editor app | 41.3 | 31.6 | 47.4 | 0.75 | 1.67 | 1.12 | 2025-09-14 | 0% | Category control: DECLINE pre-anomaly; post-2025 rise ≤ control → not real | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=photo%20editor%20app) |
| photo filter app | 16.9 | 13.7 | 42.4 | 0.87 | 3.17 | 1.81 | 2025-08-31 | 0% | Category control: flat pre-anomaly; +3.2× post-Aug-25 → NOT A REAL RISE | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=photo%20filter%20app) |
| film camera app | 5.0 | 4.9 | 47.9 | 1.11 | 8.28 | 4.81 | 2025-08-31 | 0% | FLAT 2022–mid-2025 (≈5/100); jumped 5→77 in Aug-2025 in one month → NOT A REAL RISE (spike-inflated, 8.3× vs control 2.5×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=film%20camera%20app) |
| film camera | 27.1 | 25.9 | 59.8 | 1.01 | 2.15 | 1.74 | 2026-03-29 | 0% | FLAT pre-anomaly (mostly hardware intent); post-2025 rise ≤ control → not real | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=film%20camera) |
| film filter | 6.7 | 6.9 | 64.6 | 1.08 | 7.29 | 5.18 | 2026-03-29 | 0% | FLAT pre-anomaly (≈7); 7→71 in Aug-Sep-2025 → NOT A REAL RISE (spike-inflated). Query also matches video/CapCut/movie "filter film" searches | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=film%20filter) |
| film filter app | 1.8 | 0.5 | 45.3 | 0.29 | 22.04 | 28.00 | 2025-08-31 | 54% | SPARSE; declining pre-anomaly; post-2025 jump is artefact → NOT A REAL RISE | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=film%20filter%20app) |
| dazz cam | 27.9 | 32.2 | 51.9 | 1.79 | 1.31 | 1.59 | 2026-03-15 | 0% | REAL RISE (1.8× pre-anomaly); post-2025 not above control. Rising related: "apps like dazz cam", "dazz cam for android" | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=dazz%20cam) |
| dazz | 39.2 | 45.2 | 65.1 | 1.48 | 1.22 | 1.40 | 2026-03-15 | 0% | REAL RISE (1.5×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=dazz) |
| huji | 56.4 | 52.7 | 45.7 | 0.96 | 0.90 | 0.88 | 2022-10-23 | 0% | CONTAMINATED: 100% of top-country interest = Israel (Hebrew University, HUJI) → ignore | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=huji) |
| huji cam | 42.2 | 18.4 | 37.6 | 0.44 | 1.92 | 1.40 | 2023-05-07 | 19% | DECLINE (0.44× pre-anomaly) – 2017–19 era app fading | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=huji%20cam) |
| 1998 cam | 25.8 | 21.6 | 67.6 | 0.89 | 2.83 | 1.98 | 2026-06-21 | 0% | FLAT pre-anomaly; post-2025 rise (2.8×) ≈ control → not a real rise | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=1998%20cam) |
| digicam | 7.9 | 28.8 | 75.5 | 5.96 | 1.58 | 2.77 | 2026-09-27 | 0% | STRONG REAL RISE: 5.96× pre-anomaly (2022 avg 7.9 → 2024 28.8), still at 5-yr high in Sep-2026 while controls fell back | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=digicam) |
| ccd camera | 18.2 | 21.6 | 52.8 | 1.30 | 1.97 | 1.70 | 2026-04-05 | 0% | Mild rise (1.3×); post-2025 ≈ control. Mixed intent (sensor/astronomy/"sony ccd camera") | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=ccd%20camera) |
| y2k camera | 0.5 | 2.6 | 30.0 | 52.50 | 7.93 | 4.76 | 2026-05-10 | 21% | REAL RISE from tiny base (52× pre-anomaly) + viral spike Mar–May-2026 (33→83→76 then 7) → spike-inflated; treat as fad-prone | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=y2k%20camera) |
| disposable camera app | 10.3 | 23.9 | 46.2 | 2.83 | 1.57 | 1.55 | 2025-04-20 | 9% | REAL RISE (2.8× pre-anomaly), peak Apr-2025 (pre-anomaly); post-2025 ≈ control. Much of intent = event/wedding "disposable camera" apps | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=disposable%20camera%20app) |
| retro camera app | 0.1 | 0.5 | 34.8 | 6.67 | 20.42 | 14.38 | 2026-05-10 | 72% | SPARSE (72% zero weeks) → unreliable; post-2025 jump is artefact | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=retro%20camera%20app) |
| vintage camera app | 1.7 | 2.4 | 38.5 | 3.10 | 7.74 | 7.65 | 2026-04-05 | 28% | SPARSE-ish; rise pre-anomaly from tiny base; post-2025 7.7× → spike-inflated | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=vintage%20camera%20app) |
| polaroid filter | 30.9 | 27.0 | 46.3 | 0.86 | 1.77 | 1.18 | 2025-09-14 | 0% | FLAT pre-anomaly; post-2025 rise ≈ control → not real | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=polaroid%20filter) |
| fuji recipe | 8.2 | 15.1 | 41.3 | 2.34 | 2.03 | 1.64 | 2026-05-03 | 0% | REAL RISE (2.3× pre-anomaly); post-2025 ≈ control | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=fuji%20recipe) |
| fujifilm recipes | 8.5 | 23.6 | 62.6 | 5.44 | 1.86 | 2.06 | 2026-05-10 | 5% | STRONG REAL RISE (5.4× pre-anomaly: 2022 avg 8.5 → 2024 23.6); post-2025 ≈ control | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=fujifilm%20recipes) |
| fujifilm simulation | 14.2 | 30.5 | 66.3 | 3.10 | 2.14 | 1.10 | 2026-05-24 | 0% | REAL RISE (3.1× pre-anomaly); post-2025 ≈ control | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=fujifilm%20simulation) |
| film simulation | 7.9 | 14.1 | 70.5 | 2.35 | 4.19 | 2.77 | 2026-05-17 | 0% | REAL RISE (2.35× pre-anomaly) but post-2025 4.2× > control → later part spike-inflated | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=film%20simulation) |
| kodak portra filter | 1.9 | 0.0 | 0.3 | 0.00 | ∞ | ∞ | 2022-01-30 | 98% | Below threshold (98% zero weeks) → negligible Google demand | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=kodak%20portra%20filter) |
| film grain | 11.7 | 13.2 | 58.1 | 1.33 | 3.48 | 3.14 | 2026-04-26 | 0% | Mild real rise (1.33×) but post-2025 3.5× > control → spike-inflated; related rising queries dominated by gaming (Resident Evil Requiem "film grain" setting) and AI-prompt translations | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=film%20grain) |
| film look | 14.4 | 12.1 | 33.2 | 0.72 | 2.67 | 2.39 | 2021-12-26 | 0% | DECLINE pre-anomaly (0.72×); post-2025 ≈ control | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=film%20look) |
| lut | 57.3 | 61.0 | 85.3 | 1.12 | 1.34 | 1.28 | 2025-11-16 | 0% | CONTAMINATED (LUT University in Finland, Romanian "lut"=clay, Hindi song "Lut Le Gaya" 2026) – use "luts"/"cube lut" instead; flat | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lut) |
| luts | 33.4 | 43.5 | 69.6 | 1.60 | 1.40 | 1.40 | 2025-11-16 | 0% | REAL RISE (1.6×); post-2025 ≈ control | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=luts) |
| cube lut | 18.5 | 25.4 | 57.7 | 2.04 | 1.90 | 1.72 | 2026-06-14 | 6% | REAL RISE (2.0×); post-2025 ≈ control | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=cube%20lut) |
| lut app | 5.0 | 11.0 | 65.9 | 3.43 | 4.56 | 3.11 | 2026-05-31 | 16% | REAL RISE from small base (3.4× pre-anomaly) but post-2025 4.6× > control → partly inflated | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lut%20app) |
| color grading | 22.1 | 30.3 | 68.5 | 1.88 | 1.84 | 1.71 | 2026-06-07 | 0% | REAL RISE (1.9× pre-anomaly); post-2025 ≈ control | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=color%20grading) |
| lightroom presets | 82.1 | 60.6 | 49.4 | 0.66 | 0.97 | 0.64 | 2022-05-01 | 0% | DECLINE (0.66× pre-anomaly; 2022 avg 82 → 2026 YTD 49) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lightroom%20presets) |
| free presets | 77.1 | 66.4 | 69.4 | 0.89 | 1.13 | 0.81 | 2026-04-05 | 0% | FLAT/slight decline (0.89×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=free%20presets) |
| vsco | 69.2 | 47.9 | 30.3 | 0.51 | 0.79 | 0.57 | 2021-12-26 | 0% | DECLINE (0.51×; 2022 avg 69 → 2026 YTD 30) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=vsco) |
| vsco filter | 64.1 | 24.6 | 28.9 | 0.26 | 1.44 | 0.98 | 2022-01-02 | 3% | STEEP DECLINE (0.26×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=vsco%20filter) |
| lightroom | 80.1 | 81.3 | 79.0 | 1.03 | 1.07 | 0.85 | 2025-10-19 | 0% | FLAT brand (1.03×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lightroom) |
| picsart | 74.5 | 53.7 | 44.0 | 0.72 | 0.90 | 0.69 | 2022-01-02 | 0% | DECLINE (0.72×; 74.5 → 44.0) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=picsart) |
| snapseed | 18.2 | 18.4 | 15.1 | 0.83 | 1.05 | 0.61 | 2023-11-26 | 0% | FLAT/slight decline (0.83×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=snapseed) |
| filmode | 0 | 0 | 0 | – | – | – | – | 100% | Below Trends threshold (no measurable Google demand for the brand) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=filmode) |

**United States**

| keyword | 2022 avg | 2024 avg | 2026 YTD | pre-anomaly ratio | post-Aug-25 inflation | Aug–Sep 26 ÷ Aug–Sep 24 | peak week | zero wks | verdict / notes | src |
|---|---|---|---|---|---|---|---|---|---|---|
| calculator | 77.9 | 79.2 | 57.1 | 1.01 | 0.83 | 0.62 | 2022-04-24 | 0% | CONTROL | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=calculator&geo=US) |
| weather app | 29.1 | 23.7 | 49.8 | 0.87 | 1.59 | 1.51 | 2026-01-18 | 0% | CONTROL app query (1.59× post-Aug-25) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=weather%20app&geo=US) |
| calculator app | 45.9 | 45.7 | 65.1 | 1.03 | 1.30 | 0.88 | 2026-04-05 | 0% | CONTROL (1.30×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=calculator%20app&geo=US) |
| flashlight app | 54.5 | 42.0 | 72.5 | 0.87 | 1.39 | 1.05 | 2025-07-20 | 0% | CONTROL (1.39×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=flashlight%20app&geo=US) |
| photo editor app | 44.6 | 37.4 | 56.5 | 0.86 | 1.31 | 0.89 | 2025-07-27 | 0% | Category control: flat; post ≈ control | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=photo%20editor%20app&geo=US) |
| film camera app | 3.0 | 3.5 | 37.1 | 2.18 | 4.13 | 5.50 | 2025-07-27 | 47% | SPARSE (47% zero weeks); post-2025 4.1× > control → NOT A REAL RISE | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=film%20camera%20app&geo=US) |
| film filter | 5.9 | 6.8 | 50.1 | 1.26 | 3.81 | 2.02 | 2026-05-17 | 0% | FLAT pre-anomaly (1.26×); post 3.8× > control → NOT A REAL RISE | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=film%20filter&geo=US) |
| dazz cam | 5.4 | 4.8 | 34.2 | 3.46 | 1.77 | 19.93 | 2025-07-27 | 49% | SPARSE in US (49% zero weeks) – small US Google demand (Dazz is iOS-first) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=dazz%20cam&geo=US) |
| huji | 59.6 | 45.2 | 67.4 | 0.83 | 1.17 | 1.16 | 2022-06-12 | 3% | Partly contaminated (Hebrew Univ.) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=huji&geo=US) |
| digicam | 2.4 | 13.1 | 41.1 | 19.09 | 1.54 | 2.99 | 2025-07-27 | 16% | STRONG REAL RISE (19× pre-anomaly from tiny 2022 base; 2024 13.1 → 2026 41.1) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=digicam&geo=US) |
| ccd camera | 9.8 | 10.2 | 32.7 | 1.21 | 2.21 | 1.40 | 2026-04-05 | 0% | FLAT pre-anomaly; post 2.2× > control and spike Apr-2026 → spike-inflated | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=ccd%20camera&geo=US) |
| y2k camera | 0.1 | 0.9 | 22.1 | ∞ | 10.82 | 15.00 | 2026-04-05 | 66% | SPARSE; viral spike Apr-2026 → spike-inflated fad | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=y2k%20camera&geo=US) |
| polaroid filter | 13.0 | 9.5 | 29.0 | 0.64 | 3.23 | 0.59 | 2026-04-12 | 43% | SPARSE; DECLINE pre-anomaly; post-2025 spike → not real | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=polaroid%20filter&geo=US) |
| fuji recipe | 14.2 | 21.2 | 43.9 | 1.71 | 1.69 | 1.23 | 2026-04-12 | 4% | REAL RISE (1.7×); post-2025 slightly > control | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=fuji%20recipe&geo=US) |
| film grain | 18.1 | 18.7 | 59.8 | 1.24 | 2.35 | 1.76 | 2026-04-05 | 0% | FLAT pre-anomaly (1.24×); post 2.35× > control → spike-inflated | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=film%20grain&geo=US) |
| lut | 40.0 | 54.5 | 85.2 | 1.55 | 1.31 | 1.49 | 2026-06-21 | 0% | RISE (1.55×) – less contaminated in US; post ≈ control | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lut&geo=US) |
| color grading | 26.0 | 34.6 | 74.3 | 1.84 | 1.50 | 1.65 | 2026-03-22 | 0% | REAL RISE (1.84×); post ≈ control | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=color%20grading&geo=US) |
| lightroom presets | 66.7 | 56.0 | 51.6 | 0.81 | 0.93 | 0.72 | 2026-04-12 | 0% | Slow DECLINE (0.81×; 66.7 → 51.6) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lightroom%20presets&geo=US) |
| vsco | 74.9 | 59.7 | 39.3 | 0.62 | 0.82 | 0.63 | 2021-12-26 | 0% | DECLINE (0.62×; 74.9 → 39.3) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=vsco&geo=US) |
| lightroom | 72.7 | 77.0 | 82.2 | 1.13 | 1.05 | 1.00 | 2024-10-20 | 0% | FLAT/up (1.13×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lightroom&geo=US) |
| picsart | 49.5 | 44.2 | 37.9 | 0.84 | 0.97 | 0.74 | 2022-03-20 | 0% | Slow DECLINE (0.84×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=picsart&geo=US) |

**Vietnam** (priority market; local-language controls)

| keyword | 2022 avg | 2024 avg | 2026 YTD | pre-anomaly ratio | post-Aug-25 inflation | Aug–Sep 26 ÷ Aug–Sep 24 | peak week | zero wks | verdict / notes | src |
|---|---|---|---|---|---|---|---|---|---|---|
| calculator | 43.8 | 65.6 | 55.2 | 1.44 | 0.86 | 0.67 | 2026-05-31 | 0% | CONTROL (non-app) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=calculator&geo=VN) |
| thời tiết | 57.2 | 58.9 | 71.6 | 1.01 | 1.20 | 1.29 | 2026-09-13 | 0% | CONTROL (VN, non-app): flat | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=th%E1%BB%9Di%20ti%E1%BA%BFt&geo=VN) |
| app thời tiết | 25.1 | 27.1 | 33.4 | 0.97 | 1.53 | 0.79 | 2024-09-01 | 2% | CONTROL (VN "weather app"): 1.53× post-Aug-25 | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=app%20th%E1%BB%9Di%20ti%E1%BA%BFt&geo=VN) |
| app máy tính | 65.6 | 75.1 | 71.4 | 1.13 | 0.98 | 0.90 | 2025-09-14 | 0% | CONTROL (VN "calculator app"): 0.98× → Vietnamese-language app queries show NO 2025–26 inflation | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=app%20m%C3%A1y%20t%C3%ADnh&geo=VN) |
| weather app | 0.6 | 1.0 | 15.3 | 2.33 | 10.90 | 6.27 | 2026-05-31 | 55% | English control is SPARSE in VN (55% zero weeks) and jumped 10.9× → the anomaly hits sparse English queries hardest | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=weather%20app&geo=VN) |
| app chụp ảnh | 39.4 | 24.3 | 19.2 | 0.51 | 0.93 | 0.87 | 2022-01-30 | 0% | DECLINE (0.51×; 39.4 → 19.2) – generic "camera app" searches on Google falling | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=app%20ch%E1%BB%A5p%20%E1%BA%A3nh&geo=VN) |
| app chụp ảnh đẹp | 30.0 | 11.9 | 6.3 | 0.28 | 0.70 | 0.63 | 2022-01-30 | 6% | DECLINE (0.28×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=app%20ch%E1%BB%A5p%20%E1%BA%A3nh%20%C4%91%E1%BA%B9p&geo=VN) |
| app chỉnh ảnh | 32.4 | 18.0 | 16.0 | 0.50 | 0.97 | 0.94 | 2022-01-30 | 0% | DECLINE (0.50×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=app%20ch%E1%BB%89nh%20%E1%BA%A3nh&geo=VN) |
| app chỉnh màu | 27.7 | 10.6 | 5.4 | 0.26 | 0.92 | 0.70 | 2022-01-30 | 21% | STEEP DECLINE (0.26×; 27.7 → 5.4); related top queries: "…ảnh" (100), "…video" (23), "…film" (11), "…tóc" (hair, 10) → film intent is a minority | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=app%20ch%E1%BB%89nh%20m%C3%A0u&geo=VN) |
| app chụp ảnh film | 0.0 | 0.0 | 2.6 | ∞ | ∞ | ∞ | 2026-02-08 | 100% | SPARSE (virtually all weeks zero; a few non-zero weeks in 2026) – exists in autocomplete but tiny Google volume | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=app%20ch%E1%BB%A5p%20%E1%BA%A3nh%20film&geo=VN) |
| app máy ảnh film | 0 | 0 | 0 | – | – | – | – | 100% | Below threshold | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=app%20m%C3%A1y%20%E1%BA%A3nh%20film&geo=VN) |
| chụp ảnh film | 29.9 | 6.8 | 14.7 | 0.05 | 7.94 | 1.82 | 2022-01-16 | 80% | SPARSE; decline from 2022 peak | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=ch%E1%BB%A5p%20%E1%BA%A3nh%20film&geo=VN) |
| ảnh film | 59.9 | 51.4 | 67.3 | 0.93 | 1.19 | 1.44 | 2026-02-01 | 0% | FLAT (0.93×) but Aug–Sep-2026 1.44× vs 2024; peak Feb-2026 → stable/slightly up | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=%E1%BA%A3nh%20film&geo=VN) |
| màu film | 55.7 | 48.0 | 52.9 | 0.88 | 1.17 | 1.09 | 2023-01-22 | 12% | FLAT (0.88×) – stable aesthetic intent ("màu film kodak gold 200", "màu film fuji") | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=m%C3%A0u%20film&geo=VN) |
| máy ảnh film | 44.6 | 38.5 | 48.0 | 1.02 | 1.03 | 1.74 | 2026-08-30 | 2% | FLAT (1.02×) but 5-yr peak week 2026-08-30 (Aug–Sep-26 = 1.74× 2024) → film-camera HARDWARE interest at a high | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=m%C3%A1y%20%E1%BA%A3nh%20film&geo=VN) |
| filter film | 0.0 | 0.0 | 19.8 | ∞ | 29.20 | ∞ | 2026-02-15 | 91% | SPARSE; post-2025 jump = artefact + movie/CapCut "filter film korea" contamination → NOT A REAL RISE | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=filter%20film&geo=VN) |
| preset lightroom | 31.4 | 18.6 | 6.9 | 0.52 | 0.51 | 0.20 | 2022-01-30 | 12% | DECLINE (0.52×; 31.4 → 6.9) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=preset%20lightroom&geo=VN) |
| preset | 41.6 | 36.4 | 43.4 | 0.93 | 1.10 | 1.16 | 2026-07-19 | 0% | FLAT (0.93×) – but mixed intent (Xiaomi camera "preset", audio) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=preset&geo=VN) |
| công thức màu | 35.5 | 19.7 | 12.0 | 0.39 | 0.79 | 0.68 | 2022-03-13 | 0% | DECLINE (0.39×) and AMBIGUOUS (hair-dye colour formulas dominate autocomplete: "công thức màu nâu lạnh"); only "công thức màu fujifilm" is photo intent | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=c%C3%B4ng%20th%E1%BB%A9c%20m%C3%A0u&geo=VN) |
| lut màu | 1.6 | 3.1 | 37.7 | 4.15 | 6.59 | 11.30 | 2025-11-23 | 74% | REAL RISE from small base (4.2× pre-anomaly; SPARSE 74% zero); rising related "lut màu blackmagic camera" (+1,950% WW) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lut%20m%C3%A0u&geo=VN) |
| lut | 14.8 | 20.4 | 18.5 | 1.17 | 1.21 | 0.58 | 2024-09-08 | 0% | CONTAMINATED ("lụt" = flood typed without diacritics) → ignore | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lut&geo=VN) |
| dazz cam | 4.2 | 11.4 | 9.9 | 3.34 | 1.07 | 0.84 | 2023-07-30 | 25% | REAL RISE 2022→2024 (3.3×) then FLAT/down in 2025–26 (latest 0.84×); peak Jul-2023. Top related: "dazz cam apk", "dazz cam android", rising "cách tải dazz cam cho android" (+150%) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=dazz%20cam&geo=VN) |
| vsco | 34.3 | 7.8 | 5.1 | 0.10 | 0.79 | 0.35 | 2021-10-24 | 11% | COLLAPSE (0.10×; 34.3 → 5.1) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=vsco&geo=VN) |
| lightroom | 32.8 | 22.5 | 16.2 | 0.55 | 0.84 | 0.56 | 2022-01-30 | 0% | DECLINE (0.55×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lightroom&geo=VN) |
| picsart | 60.7 | 31.5 | 21.9 | 0.44 | 0.89 | 0.45 | 2022-01-30 | 0% | DECLINE (0.44×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=picsart&geo=VN) |
| digicam | 0.0 | 0.8 | 6.3 | ∞ | 0.56 | 4.79 | 2025-01-12 | 95% | SPARSE (95% zero) – Vietnamese say "máy ảnh ccd"/"máy ảnh kỹ thuật số" instead | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=digicam&geo=VN) |
| color grading | 1.9 | 8.8 | 37.3 | 7.28 | 2.47 | 4.36 | 2026-04-19 | 77% | SPARSE English query; post-2025 jump is artefact | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=color%20grading&geo=VN) |
| film grain | 1.0 | 1.2 | 16.8 | 1.20 | 8.25 | ∞ | 2026-03-08 | 95% | SPARSE; artefact | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=film%20grain&geo=VN) |

**Japan**

| keyword | 2022 avg | 2024 avg | 2026 YTD | pre-anomaly ratio | post-Aug-25 inflation | Aug–Sep 26 ÷ Aug–Sep 24 | peak week | zero wks | verdict / notes | src |
|---|---|---|---|---|---|---|---|---|---|---|
| calculator | 37.3 | 51.1 | 64.2 | 1.44 | 1.24 | 0.72 | 2026-04-12 | 0% | CONTROL | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=calculator&geo=JP) |
| 天気 | 56.8 | 50.0 | 64.7 | 0.90 | 1.26 | 1.39 | 2026-09-06 | 0% | CONTROL (JP weather): 1.26× | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=%E5%A4%A9%E6%B0%97&geo=JP) |
| 天気 アプリ | 51.0 | 34.2 | 38.6 | 0.68 | 1.19 | 1.16 | 2022-09-18 | 0% | CONTROL (JP "weather app"): 1.19× | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=%E5%A4%A9%E6%B0%97%20%E3%82%A2%E3%83%97%E3%83%AA&geo=JP) |
| 電卓 アプリ | 67.5 | 63.3 | 48.2 | 0.91 | 0.80 | 0.89 | 2021-10-24 | 0% | CONTROL (JP "calculator app"): 0.80× → no inflation in Japanese-language app queries | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=%E9%9B%BB%E5%8D%93%20%E3%82%A2%E3%83%97%E3%83%AA&geo=JP) |
| weather app | 0.4 | 1.4 | 52.7 | 14.17 | 20.63 | 5.94 | 2026-01-25 | 53% | English control SPARSE in JP (53% zero), jumped 20× → artefact | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=weather%20app&geo=JP) |
| フィルムカメラ | 78.0 | 68.2 | 55.3 | 0.88 | 0.86 | 0.79 | 2022-05-01 | 0% | Slow DECLINE (0.88×; 78 → 55) – hardware/film-camera interest cooling | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=%E3%83%95%E3%82%A3%E3%83%AB%E3%83%A0%E3%82%AB%E3%83%A1%E3%83%A9&geo=JP) |
| フィルムカメラ アプリ | 48.6 | 10.0 | 3.5 | 0.24 | 0.38 | 1.95 | 2022-05-22 | 58% | DECLINE (0.24× pre-anomaly; SPARSE) – "film camera app" searches on Google shrinking | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=%E3%83%95%E3%82%A3%E3%83%AB%E3%83%A0%E3%82%AB%E3%83%A1%E3%83%A9%20%E3%82%A2%E3%83%97%E3%83%AA&geo=JP) |
| 写ルンです アプリ | 8.7 | 1.1 | 0.7 | 0.40 | 0.14 | ∞ | 2025-05-25 | 93% | DECLINE (0.40×; SPARSE) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=%E5%86%99%E3%83%AB%E3%83%B3%E3%81%A7%E3%81%99%20%E3%82%A2%E3%83%97%E3%83%AA&geo=JP) |
| フィルム風 アプリ | 0.0 | 0.0 | 3.9 | ∞ | ∞ | ∞ | 2026-09-20 | 99% | Below/near threshold | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=%E3%83%95%E3%82%A3%E3%83%AB%E3%83%A0%E9%A2%A8%20%E3%82%A2%E3%83%97%E3%83%AA&geo=JP) |
| フィルムシミュレーション | 38.5 | 33.8 | 55.1 | 1.03 | 1.39 | 2.57 | 2026-03-01 | 18% | FLAT pre-anomaly (1.03×) but 2026 up (Aug–Sep-26 = 2.57× 2024; post 1.39× > control 0.99×) → GENUINE 2026 uptick; peak Mar-2026 | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=%E3%83%95%E3%82%A3%E3%83%AB%E3%83%A0%E3%82%B7%E3%83%9F%E3%83%A5%E3%83%AC%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3&geo=JP) |
| フィルムレシピ | 35.6 | 19.9 | 38.1 | 0.87 | 1.48 | 2.17 | 2026-03-29 | 45% | FLAT pre-anomaly; 2026 up (2.17× vs 2024); peak Mar-2026 → genuine uptick (SPARSE 45%) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=%E3%83%95%E3%82%A3%E3%83%AB%E3%83%A0%E3%83%AC%E3%82%B7%E3%83%94&geo=JP) |
| オールドデジカメ | 1.2 | 11.9 | 0.6 | 2.17 | 0.12 | 0.30 | 2024-04-28 | 93% | SPARSE; spike 2024 then faded | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=%E3%82%AA%E3%83%BC%E3%83%AB%E3%83%89%E3%83%87%E3%82%B8%E3%82%AB%E3%83%A1&geo=JP) |
| lut | 33.8 | 52.2 | 70.8 | 1.66 | 1.27 | 1.09 | 2026-09-20 | 0% | REAL RISE (1.66×; 33.8 → 70.8); peak week 2026-09-20 – video/Log LUT intent (e.g., "lumix lut") | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lut&geo=JP) |
| lightroom | 61.4 | 75.1 | 68.9 | 1.25 | 0.98 | 0.75 | 2025-11-23 | 0% | FLAT (1.25× pre) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lightroom&geo=JP) |
| vsco | 64.5 | 34.4 | 29.0 | 0.41 | 1.09 | 0.52 | 2022-08-14 | 5% | DECLINE (0.41×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=vsco&geo=JP) |
| picsart | 62.6 | 33.8 | 25.6 | 0.48 | 0.85 | 0.66 | 2022-03-20 | 0% | DECLINE (0.48×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=picsart&geo=JP) |
| digicam | 0.0 | 3.4 | 19.2 | ∞ | 1.19 | ∞ | 2025-02-16 | 90% | SPARSE English term (Japanese use デジカメ) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=digicam&geo=JP) |
| film filter | 0.0 | 0.0 | 41.6 | ∞ | ∞ | ∞ | 2025-12-07 | 84% | SPARSE English; artefact | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=film%20filter&geo=JP) |
| color grading | 0.0 | 1.8 | 52.4 | ∞ | 21.48 | ∞ | 2026-03-15 | 82% | SPARSE English; artefact | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=color%20grading&geo=JP) |

**South Korea** (Google is a minority engine in KR, so most Korean app queries fall below the Trends threshold)

| keyword | 2022 avg | 2024 avg | 2026 YTD | pre-anomaly ratio | post-Aug-25 inflation | Aug–Sep 26 ÷ Aug–Sep 24 | peak week | zero wks | verdict / notes | src |
|---|---|---|---|---|---|---|---|---|---|---|
| calculator | 34.8 | 56.9 | 36.0 | 1.35 | 0.75 | 0.38 | 2026-04-12 | 0% | CONTROL | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=calculator&geo=KR) |
| 날씨 | 45.1 | 37.6 | 70.5 | 0.80 | 1.58 | 1.67 | 2026-07-12 | 0% | CONTROL (KR weather): 1.58× | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=%EB%82%A0%EC%94%A8&geo=KR) |
| 날씨 어플 | 24.5 | 9.1 | 17.0 | 0.69 | 1.74 | 6.60 | 2025-07-13 | 69% | CONTROL (KR "weather app"): sparse (69% zero) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=%EB%82%A0%EC%94%A8%20%EC%96%B4%ED%94%8C&geo=KR) |
| 필름카메라 | 70.2 | 61.1 | 66.9 | 1.03 | 0.98 | 0.96 | 2022-04-03 | 0% | FLAT (1.03×; 70 → 67) – hardware + app mixed intent | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=%ED%95%84%EB%A6%84%EC%B9%B4%EB%A9%94%EB%9D%BC&geo=KR) |
| 필름카메라 어플 | 0 | 0 | 0 | – | – | – | – | 100% | Below threshold on Google (Koreans search Naver) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=%ED%95%84%EB%A6%84%EC%B9%B4%EB%A9%94%EB%9D%BC%20%EC%96%B4%ED%94%8C&geo=KR) |
| 필카 어플 | 0.0 | 0.0 | 2.5 | ∞ | ∞ | ∞ | 2025-08-17 | 99% | SPARSE/below threshold | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=%ED%95%84%EC%B9%B4%20%EC%96%B4%ED%94%8C&geo=KR) |
| 필름 필터 | 5.2 | 0.0 | 3.1 | 1.41 | 0.65 | ∞ | 2022-07-17 | 96% | SPARSE | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=%ED%95%84%EB%A6%84%20%ED%95%84%ED%84%B0&geo=KR) |
| 라이트룸 프리셋 | 8.0 | 7.5 | 3.8 | 0.61 | 0.53 | 0.70 | 2022-02-13 | 91% | SPARSE; DECLINE | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=%EB%9D%BC%EC%9D%B4%ED%8A%B8%EB%A3%B8%20%ED%94%84%EB%A6%AC%EC%85%8B&geo=KR) |
| 빈티지 디카 | 0.0 | 0.0 | 4.1 | 1.25 | 1.24 | ∞ | 2021-11-14 | 97% | SPARSE | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=%EB%B9%88%ED%8B%B0%EC%A7%80%20%EB%94%94%EC%B9%B4&geo=KR) |
| lut | 31.7 | 38.8 | 64.7 | 1.53 | 1.48 | 1.00 | 2025-12-07 | 2% | REAL RISE (1.53×; 31.7 → 64.7) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lut&geo=KR) |
| lightroom | 6.1 | 12.1 | 13.3 | 1.75 | 2.02 | 0.38 | 2025-11-23 | 0% | RISE (1.75×) from small base | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lightroom&geo=KR) |
| vsco | 37.5 | 23.0 | 17.5 | 0.29 | 1.54 | 0.17 | 2022-08-14 | 55% | DECLINE (0.29×; SPARSE) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=vsco&geo=KR) |
| dazz cam | 0.0 | 0.0 | 1.8 | ∞ | ∞ | ∞ | 2023-04-23 | 98% | SPARSE (98% zero) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=dazz%20cam&geo=KR) |
| digicam | 0.0 | 0.7 | 1.3 | ∞ | 0.18 | 0.31 | 2025-01-12 | 97% | SPARSE | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=digicam&geo=KR) |

**Indonesia**

| keyword | 2022 avg | 2024 avg | 2026 YTD | pre-anomaly ratio | post-Aug-25 inflation | Aug–Sep 26 ÷ Aug–Sep 24 | peak week | zero wks | verdict / notes | src |
|---|---|---|---|---|---|---|---|---|---|---|
| calculator | 66.9 | 68.0 | 51.3 | 1.04 | 0.86 | 0.67 | 2023-07-02 | 0% | CONTROL | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=calculator&geo=ID) |
| cuaca | 56.9 | 70.1 | 86.5 | 1.27 | 1.09 | 1.26 | 2026-01-11 | 0% | CONTROL (ID weather) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=cuaca&geo=ID) |
| aplikasi cuaca | 64.4 | 45.3 | 60.3 | 0.62 | 1.26 | 1.66 | 2022-01-09 | 0% | CONTROL (ID "weather app"): 1.26× | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=aplikasi%20cuaca&geo=ID) |
| aplikasi kalkulator | 22.0 | 21.3 | 13.2 | 0.74 | 0.85 | 0.72 | 2024-06-23 | 0% | CONTROL (ID "calculator app"): 0.85× | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=aplikasi%20kalkulator&geo=ID) |
| aplikasi kamera | 76.3 | 53.2 | 51.6 | 0.65 | 1.01 | 0.99 | 2022-05-08 | 0% | DECLINE (0.65×) – generic camera-app searches falling | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=aplikasi%20kamera&geo=ID) |
| aplikasi kamera film | 6.1 | 0.0 | 0.7 | 0.00 | ∞ | ∞ | 2022-06-05 | 97% | SPARSE | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=aplikasi%20kamera%20film&geo=ID) |
| kamera jadul | 47.0 | 42.4 | 55.7 | 1.04 | 1.14 | 2.12 | 2025-09-14 | 13% | FLAT (1.04×) but Aug–Sep-26 = 2.1× 2024; peak Sep-2025 → "old camera" look rising lately | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=kamera%20jadul&geo=ID) |
| dazz cam | 34.4 | 31.0 | 32.5 | 1.04 | 1.09 | 0.94 | 2022-04-24 | 0% | FLAT (1.04×) – mature; top related "dazz cam web", "dazz cam android", "apk dazz cam" | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=dazz%20cam&geo=ID) |
| digicam | 5.0 | 38.2 | 74.7 | 13.73 | 1.26 | 1.77 | 2026-03-22 | 12% | STRONG REAL RISE (13.7×; 5.0 → 74.7); Indonesia is #3 country for "digicam" interest | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=digicam&geo=ID) |
| color grading | 41.8 | 49.2 | 69.0 | 1.45 | 1.14 | 1.64 | 2026-08-30 | 0% | REAL RISE (1.45×; 41.8 → 69.0); peak Aug-2026 | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=color%20grading&geo=ID) |
| lut | 55.9 | 52.4 | 80.4 | 0.96 | 1.30 | 1.70 | 2022-02-20 | 0% | FLAT (0.96×) pre; 2026 up 1.7× (mixed intent) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lut&geo=ID) |
| preset lightroom | 47.3 | 19.8 | 10.2 | 0.28 | 0.67 | 0.52 | 2022-05-01 | 0% | STEEP DECLINE (0.28×; 47.3 → 10.2) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=preset%20lightroom&geo=ID) |
| lightroom presets | 32.8 | 23.7 | 26.1 | 0.62 | 1.81 | 0.34 | 2025-12-21 | 29% | DECLINE (0.62×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lightroom%20presets&geo=ID) |
| lightroom | 53.3 | 36.8 | 26.1 | 0.53 | 0.86 | 0.72 | 2022-05-01 | 0% | DECLINE (0.53×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lightroom&geo=ID) |
| vsco | 34.3 | 10.8 | 5.3 | 0.16 | 0.72 | 0.44 | 2021-12-05 | 0% | COLLAPSE (0.16×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=vsco&geo=ID) |
| picsart | 52.8 | 30.4 | 16.0 | 0.47 | 0.64 | 0.46 | 2022-01-02 | 0% | DECLINE (0.47×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=picsart&geo=ID) |
| filter film | 18.3 | 8.2 | 36.7 | 0.57 | 3.40 | 4.72 | 2026-02-15 | 40% | SPARSE; also matches movie searches ("film" = movie) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=filter%20film&geo=ID) |

**Brazil**

| keyword | 2022 avg | 2024 avg | 2026 YTD | pre-anomaly ratio | post-Aug-25 inflation | Aug–Sep 26 ÷ Aug–Sep 24 | peak week | zero wks | verdict / notes | src |
|---|---|---|---|---|---|---|---|---|---|---|
| calculator | 47.7 | 61.4 | 58.6 | 1.57 | 0.84 | 0.91 | 2025-06-15 | 0% | CONTROL | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=calculator&geo=BR) |
| previsão do tempo | 64.9 | 40.5 | 57.8 | 0.62 | 1.40 | 1.83 | 2023-11-12 | 0% | CONTROL (BR weather) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=previs%C3%A3o%20do%20tempo&geo=BR) |
| app de clima | 40.1 | 34.7 | 63.0 | 0.96 | 1.72 | 1.72 | 2026-01-18 | 3% | CONTROL (BR "weather app"): 1.72× | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=app%20de%20clima&geo=BR) |
| calculadora | 68.7 | 80.2 | 64.5 | 1.28 | 0.85 | 0.70 | 2025-03-30 | 0% | CONTROL | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=calculadora&geo=BR) |
| filtro de filme | 32.0 | 27.2 | 46.1 | 1.09 | 1.55 | 1.32 | 2025-10-19 | 20% | FLAT (1.09×); post ≈ control; ambiguous (movie filters "filtro de filme de terror", CapCut) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=filtro%20de%20filme&geo=BR) |
| dazz cam | 20.1 | 19.3 | 49.1 | 2.31 | 1.50 | 2.54 | 2025-12-28 | 3% | REAL RISE (2.3×; 20.1 → 49.1); peak Dec-2025 | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=dazz%20cam&geo=BR) |
| color grading | 5.3 | 10.8 | 24.9 | 4.57 | 1.53 | 1.52 | 2026-04-19 | 27% | REAL RISE (4.6× from small base) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=color%20grading&geo=BR) |
| lut | 40.3 | 48.6 | 71.5 | 1.29 | 1.33 | 1.57 | 2026-06-21 | 0% | RISE-ish (1.29×; 40 → 71.5); BR "luta"/"luto" autocomplete noise | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lut&geo=BR) |
| presets lightroom | 56.4 | 32.2 | 20.7 | 0.53 | 0.68 | 0.59 | 2022-01-02 | 0% | DECLINE (0.53×; 56.4 → 20.7) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=presets%20lightroom&geo=BR) |
| lightroom | 73.0 | 75.5 | 72.0 | 1.04 | 0.97 | 0.90 | 2023-01-15 | 0% | FLAT (1.04×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lightroom&geo=BR) |
| vsco | 67.9 | 62.6 | 49.5 | 0.82 | 0.85 | 0.84 | 2021-12-26 | 0% | FLAT/slow decline (0.82×) – VSCO still relatively strong in BR | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=vsco&geo=BR) |
| picsart | 70.3 | 53.8 | 34.7 | 0.75 | 0.72 | 0.52 | 2022-03-20 | 0% | DECLINE (0.75×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=picsart&geo=BR) |
| digicam | 0.0 | 1.7 | 8.6 | 8.33 | 1.05 | ∞ | 2025-01-12 | 92% | SPARSE | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=digicam&geo=BR) |

**Germany**

| keyword | 2022 avg | 2024 avg | 2026 YTD | pre-anomaly ratio | post-Aug-25 inflation | Aug–Sep 26 ÷ Aug–Sep 24 | peak week | zero wks | verdict / notes | src |
|---|---|---|---|---|---|---|---|---|---|---|
| calculator | 67.0 | 79.5 | 68.7 | 1.28 | 0.89 | 0.76 | 2024-02-04 | 0% | CONTROL | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=calculator&geo=DE) |
| wetter | 56.5 | 44.5 | 58.3 | 0.82 | 1.25 | 1.14 | 2022-08-14 | 0% | CONTROL (DE weather) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=wetter&geo=DE) |
| wetter app | 42.1 | 32.3 | 43.6 | 0.75 | 1.27 | 1.07 | 2023-06-18 | 0% | CONTROL (DE "weather app"): 1.27× | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=wetter%20app&geo=DE) |
| taschenrechner app | 52.8 | 39.4 | 39.8 | 0.68 | 1.11 | 0.76 | 2022-09-25 | 6% | CONTROL | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=taschenrechner%20app&geo=DE) |
| weather app | 3.3 | 3.7 | 34.0 | 1.27 | 7.46 | 3.86 | 2026-06-28 | 1% | English control in DE: 7.5× → artefact | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=weather%20app&geo=DE) |
| digicam | 10.2 | 39.6 | 57.8 | 6.94 | 1.29 | 1.65 | 2026-08-30 | 30% | STRONG REAL RISE (6.9×; 10.2 → 57.8); 5-yr peak week 2026-08-30 (partly "DigiCamper" noise) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=digicam&geo=DE) |
| color grading | 32.3 | 38.1 | 56.1 | 1.92 | 1.22 | 0.92 | 2026-06-28 | 4% | REAL RISE (1.9×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=color%20grading&geo=DE) |
| lut | 49.5 | 57.5 | 74.5 | 1.39 | 1.22 | 1.15 | 2026-06-28 | 0% | REAL RISE (1.39×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lut&geo=DE) |
| lightroom presets | 75.8 | 61.5 | 42.2 | 0.79 | 0.84 | 0.49 | 2022-07-24 | 0% | Slow DECLINE (0.79×; 75.8 → 42.2) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lightroom%20presets&geo=DE) |
| lightroom | 72.5 | 77.4 | 68.4 | 1.12 | 0.97 | 0.77 | 2024-10-27 | 0% | FLAT | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lightroom&geo=DE) |
| vsco | 72.5 | 53.7 | 35.2 | 0.62 | 0.79 | 0.52 | 2022-01-02 | 0% | DECLINE (0.62×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=vsco&geo=DE) |
| picsart | 45.7 | 38.8 | 37.3 | 0.76 | 1.05 | 0.79 | 2022-03-20 | 0% | DECLINE (0.76×) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=picsart&geo=DE) |
| film filter | 2.8 | 4.7 | 46.1 | 0.81 | 15.85 | 5.95 | 2026-06-28 | 53% | SPARSE; post 15.9× → artefact | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=film%20filter&geo=DE) |
| film grain | 2.0 | 1.7 | 47.7 | 0.45 | 15.74 | 11.30 | 2026-08-30 | 77% | SPARSE; artefact | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=film%20grain&geo=DE) |
| analog filter | 0.8 | 0.0 | 14.4 | 2.64 | 4.56 | ∞ | 2026-08-30 | 93% | SPARSE | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=analog%20filter&geo=DE) |
| analogkamera | 10.9 | 5.0 | 3.7 | 0.00 | ∞ | 0.64 | 2024-09-08 | 95% | SPARSE | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=analogkamera&geo=DE) |

**Relative search volume between keywords (same-request comparisons, chained through shared anchors; "lightroom" = 100 in each market)**

The distorted window (last 12 months, Sep-2025→Sep-2026) is compared with the clean window (Jul-2024→Jun-2025). Method: 7 batches of 5 keywords per request.
- Batch 1 = vsco, lightroom, picsart, lightroom presets, color grading.
- Batch 2 is linked to batch 1 through "lightroom presets".
- Batches 3–7 are linked only through "dazz cam".
- Each keyword's window mean is rescaled so that lightroom = 100 within that market.

These are **derived estimates** (method stated here).
- Where dazz cam's raw mean is below 2 (US, VN in the clean window; JP, KR, DE), the batch 3–7 rows in that column carry large rounding error.
- JP/KR clean-window rows for batches 3–7 are missing because dazz cam was 0 there.
- Compare numbers within a column, not across columns: each column is normalised to that market's own lightroom interest.
- Comparing the two tables is itself a distortion check. Worldwide, "film filter" goes from 1.9 → 16 and "film camera app" from 0.3 → 2.9 against a flat "lightroom", while the control "weather app" goes 33 → 109.

Example source request: [WW 12-m batch](https://trends.google.com/trends/explore?date=today%2012-m&q=dazz%20cam,film%20camera%20app,huji,fuji%20recipe,ccd%20camera); [WW clean-window batch 1](https://trends.google.com/trends/explore?date=2024-07-01%202025-06-30&q=vsco,lightroom,picsart,lightroom%20presets,color%20grading).

*CLEAN window Jul-2024→Jun-2025 (pre-anomaly); lightroom = 100 per market; B3–B7 keywords are linked through dazz cam*

| keyword | WW | US | VN | JP | KR | ID | BR | DE |
|---|---|---|---|---|---|---|---|---|
| (raw weekly mean of dazz cam in its batch; <2 ⇒ column unreliable) | 8.5 | 1.1 | 1.5 | 0.0 | 0.0 | 19.7 | 45.1 | 0.6 |
| lightroom | 100 | 100 | 100 | 100 | 100 | 100 | 100 | 100 |
| dazz cam | 3.3 | 0.4 | 8.7 | 0 | 0 | 11 | 13 | 0.2 |
| weather app | 33 | 66 | 3.5 | – | – | 1.4 | 2.3 | 7.8 |
| picsart | 55 | 27 | 53 | 23 | 7.4 | 110 | 72 | 15 |
| vsco | 40 | 77 | 9.0 | 5.0 | 9.0 | 16 | 66 | 13 |
| lut | 32 | 30 | 114 | 23 | 70 | 20 | 22 | 24 |
| luts | 11 | 12 | 6.3 | – | – | 8.9 | 12 | 9.0 |
| color grading | 5.6 | 7.0 | 1.9 | 0.3 | 0.5 | 11 | 4.1 | 6.3 |
| film filter | 1.9 | 3.3 | 0.1 | – | – | 1.5 | 0 | 0.8 |
| film simulation | 1.6 | 2.1 | 0 | – | – | 0.3 | 0.1 | 0.9 |
| film grain | 1.8 | 3.0 | 0.1 | 0 | 0 | 0.2 | 0 | 0.2 |
| digicam | 4.7 | 2.9 | 1.2 | 0.6 | 2.5 | 35 | 0.5 | 3.9 |
| lightroom presets | 7.3 | 7.7 | 1.3 | 0.2 | 1.9 | 2.7 | 9.7 | 7.6 |
| free presets | 5.8 | 4.9 | 0.4 | – | – | 1.5 | 3.3 | 4.7 |
| calculator app | 22 | 36 | 2.1 | – | – | 2.0 | 2.0 | 3.2 |
| film camera app | 0.3 | 0.3 | 0 | – | – | 0 | 0 | 0 |
| ccd camera | 1.4 | 1.7 | 0.5 | – | – | 0.08 | 0.06 | 0 |
| huji | 2.6 | 1.0 | 0.3 | – | – | 0 | 0 | 0 |
| y2k camera | 0.2 | 0.3 | 0.7 | – | – | 0 | 0 | 0.06 |
| fujifilm simulation | 0.7 | 1.1 | 0 | – | – | 0.07 | 0 | 0.10 |
| fuji recipe | 0.6 | 1.2 | 0.1 | – | – | 0 | 0 | 0 |
| 1998 cam | 0.4 | 0.8 | 0 | – | – | 0 | 0 | 0 |
| lut app | 0.1 | 0.06 | 0 | – | – | 0 | 0 | 0.06 |
| polaroid filter | 0.3 | 0.2 | 0 | – | – | 0 | 0.07 | 0 |
| cube lut | 0.2 | 0.02 | 0 | – | – | 0 | 0.07 | 0.07 |
| disposable camera app | 0.3 | 0.5 | 0.1 | – | – | 0.07 | 0 | 0 |
| retro camera app | 0.01 | 0.01 | 0.2 | – | – | 0 | 0.09 | 0 |
| vsco filter | 0.2 | 0.1 | 0 | – | – | 0 | 0 | 0.05 |
| kodak portra filter | 0 | 0.01 | 0 | – | – | 0 | 0.05 | 0.06 |

*LAST 12 MONTHS Sep-2025→Sep-2026 (distorted window); lightroom = 100 per market; B3–B7 keywords are linked through dazz cam*

| keyword | WW | US | VN | JP | KR | ID | BR | DE |
|---|---|---|---|---|---|---|---|---|
| (raw weekly mean of dazz cam in its batch; <2 ⇒ column unreliable) | 9.1 | 2.2 | 3.1 | 0.2 | 1.0 | 17.7 | 51.8 | 0.7 |
| lightroom | 100 | 100 | 100 | 100 | 100 | 100 | 100 | 100 |
| dazz cam | 4.5 | 1.1 | 5.7 | 0.1 | 0.8 | 15 | 23 | 0.3 |
| weather app | 109 | 270 | 23 | 57 | 163 | 22 | 27 | 77 |
| picsart | 46 | 26 | 54 | 19 | 14 | 80 | 51 | 17 |
| vsco | 27 | 55 | 7.5 | 5.1 | 4.9 | 13 | 57 | 9.6 |
| lut | 43 | 40 | 70 | 35 | 53 | 35 | 31 | 32 |
| luts | 16 | 13 | 7.8 | 6.1 | 9.7 | 16 | 17 | 12 |
| color grading | 11 | 11 | 7.3 | 5.2 | 13 | 17 | 7.2 | 8.7 |
| film filter | 16 | 19 | 2.8 | 7.7 | 22 | 6.5 | 5.3 | 12 |
| film simulation | 7.3 | 6.7 | 1.5 | 6.3 | 14 | 2.0 | 1.9 | 5.9 |
| film grain | 6.8 | 7.8 | 1.0 | 3.3 | 6.9 | 4.5 | 2.9 | 3.7 |
| digicam | 8.3 | 5.3 | 0.4 | 1.1 | 0.3 | 60 | 0.7 | 5.3 |
| lightroom presets | 6.5 | 6.8 | 0.03 | 1.0 | 1.2 | 5.3 | 6.8 | 6.2 |
| free presets | 6.1 | 4.9 | 0.4 | 0.9 | 2.6 | 4.8 | 2.8 | 5.0 |
| calculator app | 60 | 111 | 12 | 14 | 54 | 12 | 7.9 | 18 |
| film camera app | 2.9 | 2.4 | 0.3 | 1.0 | 1.7 | 0 | 0.1 | 2.1 |
| ccd camera | 2.9 | 3.6 | 0.3 | 0.3 | 1.2 | 0.5 | 0.5 | 1.0 |
| huji | 2.3 | 1.2 | 0.07 | 0.9 | 0 | 0.2 | 0.09 | 0.02 |
| y2k camera | 2.0 | 3.9 | 0 | 0 | 0 | 0.01 | 0.06 | 0.6 |
| fujifilm simulation | 1.5 | 1.6 | 0.09 | 1.0 | 0.4 | 0.1 | 0.07 | 0.5 |
| fuji recipe | 1.3 | 2.0 | 0.08 | 0.01 | 0 | 0.01 | 0.1 | 0.4 |
| 1998 cam | 1.1 | 2.8 | 0 | 0 | 0.2 | 0 | 0.07 | 0.1 |
| lut app | 1.3 | 0.2 | 0.10 | 0.07 | 0.4 | 0 | 0.07 | 0.4 |
| polaroid filter | 0.5 | 0.8 | 0 | 0 | 0 | 0.02 | 0 | 0 |
| cube lut | 0.4 | 0.1 | 0.02 | 0.08 | 0.4 | 0.02 | 0.02 | 0.01 |
| disposable camera app | 0.4 | 0.5 | 0 | 0 | 0 | 0 | 0 | 0 |
| retro camera app | 0.4 | 0.3 | 0 | 0 | 0.2 | 0 | 0.1 | 0.05 |
| vsco filter | 0.2 | 0.2 | 0.08 | 0.07 | 0 | 0.08 | 0 | 0.1 |
| kodak portra filter | 0 | 0 | 0.08 | 0.06 | 0.3 | 0 | 0 | 0 |

*VN local terms, CLEAN window; dazz cam (VN) = 100*

| keyword | relative | 
|---|---|
| công thức màu | 1,170.1 |
| app chụp ảnh | 475.9 |
| ảnh film | 280.0 |
| máy ảnh film | 155.7 |
| preset lightroom | 126.4 |
| dazz cam | 100.0 |
| màu film | 96.9 |
| app chỉnh màu | 74.0 |
| lut màu | 14.4 |
| chụp ảnh film | 4.9 |
| filter film | 1.4 |
| app chụp ảnh film | 0.0 |
| app máy ảnh film | 0.0 |

*VN local terms, LAST 12 MONTHS; dazz cam (VN) = 100*

| keyword | relative | 
|---|---|
| công thức màu | 895.8 |
| app chụp ảnh | 372.6 |
| ảnh film | 301.6 |
| máy ảnh film | 148.7 |
| dazz cam | 100.0 |
| màu film | 99.7 |
| lut màu | 99.5 |
| preset lightroom | 54.5 |
| filter film | 49.6 |
| app chỉnh màu | 48.4 |
| chụp ảnh film | 15.8 |
| app chụp ảnh film | 1.5 |
| app máy ảnh film | 0.0 |

**Related queries (Google Trends, 12-month, pulled 2026-09-27)**
- **dazz cam (WW)**
  - Top: dazz cam app (100), apk dazz cam (65), dazz cam android (53), dazz camera (42), dazz cam iphone (24), dazz cam pro (23)
  - Rising: "what is dazz cam" +200%, "dazz cam app" +190%, "dazz cam app for android" +130%, "how to use dazz cam" +100%, "**apps like dazz cam**" +100%, "dazz cam online" +60%

  — [GT](https://trends.google.com/trends/explore?date=today%2012-m&q=dazz%20cam)
- **dazz cam (VN)**
  - Top: dazz cam apk (100), dazz cam android (82), dazz cam app (79), dazz cam pro (45)
  - Rising: "**cách tải dazz cam cho android**" +150%

  — [GT](https://trends.google.com/trends/explore?date=today%2012-m&q=dazz%20cam&geo=VN)
- **dazz cam (ID)**
  - Top: dazz cam web (100), dazz cam android (79), apk dazz cam (78), dazz cam pro (77)
  - Rising: "download dazz cam iphone for android" +28,250%

  — [GT](https://trends.google.com/trends/explore?date=today%2012-m&q=dazz%20cam&geo=ID)
- **lut (WW)**
  - Top: lut 2026, lut free, what is lut, sony lut, lut dji, lut blackmagic, iphone lut, apple lut
  - Rising: "**lut màu blackmagic camera**" +1,950% (a Vietnamese query rising worldwide), "富士 lut" +450%, "lut blackmagic camera" +300%, "apple log lut" +100%, "freshluts" +200%
  - Contamination: "lut le gaya dhurandhar" (a Hindi song) +32,250%

  — [GT](https://trends.google.com/trends/explore?date=today%2012-m&q=lut)
- **lightroom presets (WW)**
  - Top: lightroom free presets, free presets, presets for lightroom, lightroom presets download, mobile lightroom presets
  - Rising: "film presets for lightroom" +90%, "film lightroom presets" +70%, "best free lightroom presets" +110%

  — [GT](https://trends.google.com/trends/explore?date=today%2012-m&q=lightroom%20presets)
- **color grading (WW)**
  - Top: color grading video, davinci color grading, color grading ai (64), color grading film, color grading lightroom, **color grading app (37)**
  - Rising: color grading photography +110%, cinematic color grading +80%, color grading ai +50%

  — [GT](https://trends.google.com/trends/explore?date=today%2012-m&q=color%20grading)
- **digicam (WW)**
  - Top: digicam camera, digicam sony, canon digicam, vintage digicam, samsung digicam
  - Rising: holo digicam +900%, digicamfx +120%, vintage digicam +120%, digicam effect +50%, fujifilm x100vi +60%

  — [GT](https://trends.google.com/trends/explore?date=today%2012-m&q=digicam)
- **Other markets and terms**
  - ccd camera (WW): top "sony ccd camera", "best ccd camera", "ccd camera price". These are hardware-buying intents. — [GT](https://trends.google.com/trends/explore?date=today%2012-m&q=ccd%20camera)
  - film camera app (WW): only "best film camera app". — [GT](https://trends.google.com/trends/explore?date=today%2012-m&q=film%20camera%20app)
  - fuji recipe (WW): top "fuji recipes". — [GT](https://trends.google.com/trends/explore?date=today%2012-m&q=fuji%20recipe)
  - preset lightroom (ID):
    - Top: preset lightroom pc, gratis, mobile, iphone, wedding
    - Rising: "cara membuat preset lightroom" +700%, "cara import preset lightroom mobile" +150%

    — [GT](https://trends.google.com/trends/explore?date=today%2012-m&q=preset%20lightroom&geo=ID)
  - app chỉnh màu (VN): top "app chỉnh màu ảnh" (100), "…ảnh đẹp" (25), "…video" (23), "…film" (11), "…tóc" (hair, 10). — [GT](https://trends.google.com/trends/explore?date=today%2012-m&q=app%20ch%E1%BB%89nh%20m%C3%A0u&geo=VN)
  - chụp ảnh film (VN): top "app chụp ảnh film". — [GT](https://trends.google.com/trends/explore?date=today%2012-m&q=ch%E1%BB%A5p%20%E1%BA%A3nh%20film&geo=VN)

**Interest by country (5-yr, WW request, top countries; 100 = highest share of searches)**
- digicam: Philippines 100, Singapore 85, Indonesia 48, Slovenia 17, Malaysia 16. — [GT](https://trends.google.com/trends/explore?date=today%205-y&q=digicam)
- dazz cam: Myanmar 100, Philippines 71, Iraq 42, … Indonesia 29, Mongolia 29, **Vietnam 27**, Laos 23. — [GT](https://trends.google.com/trends/explore?date=today%205-y&q=dazz%20cam)
- ccd camera: Hong Kong 100, Singapore 66, Malaysia 66, China 63, … South Korea 20, Taiwan 20. — [GT](https://trends.google.com/trends/explore?date=today%205-y&q=ccd%20camera)
- fuji recipe: Singapore 100, then Australia, US, Switzerland, NZ and China at 42. — [GT](https://trends.google.com/trends/explore?date=today%205-y&q=fuji%20recipe)
- lightroom presets: Bangladesh 100, Sri Lanka 80, Nepal 77, Pakistan 57, Philippines 43, India 37, Myanmar 34. — [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lightroom%20presets)
- Contaminated series:
  - "lut": Finland 100 (LUT University), Azerbaijan 62, Romania 46 ("lut" = clay).
  - "huji": Israel 100 (Hebrew University).
  - "vsco": Kosovo 100.
  - "film camera app" and "film filter" peak in St Helena (100), which is small-sample noise.

  — [lut](https://trends.google.com/trends/explore?date=today%205-y&q=lut); [huji](https://trends.google.com/trends/explore?date=today%205-y&q=huji)

**YouTube search (Google Trends, property = YouTube search, WW, 5-yr)**

| keyword (YouTube search) | 2022 | 2023 | 2024 | 2025 | 2026 YTD | pre-anomaly ratio | post-Aug-25 ratio | peak week | verdict | src |
|---|---|---|---|---|---|---|---|---|---|---|
| digicam | 2.6 | 5.3 | 9.5 | 19.1 | 18.8 | 9.62 | 0.94 | 2025-01-12 | STRONG REAL RISE (9.6×), plateau at high level 2025–26; no post-2025 inflation | [GT-YT](https://trends.google.com/trends/explore?date=today%205-y&gprop=youtube&q=digicam) |
| film simulation | 36.6 | 60.5 | 66.0 | 60.3 | 55.6 | 2.05 | 0.89 | 2024-02-25 | Rise 2022→2024 (2.05×), easing since 2024 | [GT-YT](https://trends.google.com/trends/explore?date=today%205-y&gprop=youtube&q=film%20simulation) |
| color grading | 35.8 | 60.8 | 59.2 | 64.8 | 60.2 | 1.91 | 0.96 | 2026-02-22 | Rise 2022→2023 (1.9×), plateau since | [GT-YT](https://trends.google.com/trends/explore?date=today%205-y&gprop=youtube&q=color%20grading) |
| fuji recipe | 24.2 | 39.6 | 51.5 | 52.1 | 55.5 | 1.90 | 1.06 | 2026-06-14 | REAL RISE (1.9×) and still rising in 2026 (5-yr peak week 2026-06-14) | [GT-YT](https://trends.google.com/trends/explore?date=today%205-y&gprop=youtube&q=fuji%20recipe) |
| film grain | 43.3 | 65.1 | 72.8 | 63.4 | 58.7 | 1.60 | 0.87 | 2024-05-12 | Rise to 2024 peak, easing 2025–26 | [GT-YT](https://trends.google.com/trends/explore?date=today%205-y&gprop=youtube&q=film%20grain) |
| luts | 51.9 | 83.7 | 78.3 | 74.2 | 66.2 | 1.48 | 0.93 | 2023-10-08 | Rise 2022→2023, slow decline since 2023 | [GT-YT](https://trends.google.com/trends/explore?date=today%205-y&gprop=youtube&q=luts) |
| film look | 65.3 | 70.5 | 68.0 | 62.9 | 60.8 | 0.97 | 0.94 | 2021-12-26 | FLAT | [GT-YT](https://trends.google.com/trends/explore?date=today%205-y&gprop=youtube&q=film%20look) |
| dazz cam | 26.8 | 24.4 | 17.7 | 25.8 | 35.2 | 0.93 | 1.33 | 2026-03-15 | Flat/dip 2024, uptick 2026 (peak Mar-2026) | [GT-YT](https://trends.google.com/trends/explore?date=today%205-y&gprop=youtube&q=dazz%20cam) |
| lut | 52.1 | 39.5 | 35.3 | 32.9 | 53.8 | 0.47 | 1.51 | 2021-10-17 | LIKELY CONTAMINATED in 2026 (web-search related queries show the Hindi song "Lut Le Gaya" / Dhurandhar surging); ignore the 2026 rise | [GT-YT](https://trends.google.com/trends/explore?date=today%205-y&gprop=youtube&q=lut) |
| lightroom presets | 83.9 | 68.9 | 41.8 | 29.7 | 18.3 | 0.41 | 0.60 | 2022-07-10 | STEEP DECLINE (0.41×; 83.9 → 18.3) | [GT-YT](https://trends.google.com/trends/explore?date=today%205-y&gprop=youtube&q=lightroom%20presets) |

- Unlike web search, the YouTube-search series show **no Aug-2025 step-up**: the post-Aug-25 ratio is 0.87–1.06 for most terms. YouTube is therefore a cleaner 2025–26 trend signal for this niche. (Worldwide, 5-yr weekly, pulled 2026-09-27.)

**Google web autocomplete (suggestqueries, 2026-09-27) — how users phrase queries**
- VN "app chụp ảnh film" → miễn phí, đẹp, android, **có con thỏ**, ios, **lắc tay**, **trung quốc**, màu film. — [suggest](https://suggestqueries.google.com/complete/search?client=firefox&hl=vi&gl=vn&q=app%20ch%E1%BB%A5p%20%E1%BA%A3nh%20film)
- VN "công thức màu" → **fujifilm** (top) and then mostly **hair-dye** colours (nâu lạnh, nâu tây, trà sữa…). The keyword is ambiguous. — [suggest](https://suggestqueries.google.com/complete/search?client=firefox&hl=vi&gl=vn&q=c%C3%B4ng%20th%E1%BB%A9c%20m%C3%A0u)
- VN "màu film" → kodak, kodak gold 200, fuji, fuji 400, lucky 200, kodak ultramax 400. — [suggest](https://suggestqueries.google.com/complete/search?client=firefox&hl=vi&gl=vn&q=m%C3%A0u%20film)
- VN "preset lightroom" → free, **trong trẻo**, miễn phí, mobile, **fujifilm free**, màu tươi sáng, 2026. — [suggest](https://suggestqueries.google.com/complete/search?client=firefox&hl=vi&gl=vn&q=preset%20lightroom)
- VN "lut" → lutein… and "**lut màu blackmagic camera**". VN "máy ảnh ccd" → là gì, digital camera, miffy, nội địa trung, m11, giá bao nhiêu. — [suggest](https://suggestqueries.google.com/complete/search?client=firefox&hl=vi&gl=vn&q=m%C3%A1y%20%E1%BA%A3nh%20ccd)
- US "fuji recipe" → fuji recipes app, x100vi, for portraits, reddit, cuban negative, portra 400, 2026, film simulation app. US "film simulation" → lightroom presets, luts, iphone (YT). — [suggest](https://suggestqueries.google.com/complete/search?client=firefox&hl=en&gl=us&q=fuji%20recipe)
- US "lightroom presets" → free, free download, for portraits, reddit, **that look like film**, film. US "dazz cam" → app, for android, filters, apk, settings, pro. — [suggest](https://suggestqueries.google.com/complete/search?client=firefox&hl=en&gl=us&q=lightroom%20presets)
- JP "フィルムカメラ アプリ" → おすすめ, 無料, iphone, android, 人気, **dazz**, 動画, **日本製**. JP "フィルムシミュレーション" → ライカ風, レシピ, 対応表, カスタムレシピ, 比較. — [suggest](https://suggestqueries.google.com/complete/search?client=firefox&hl=ja&gl=jp&q=%E3%83%95%E3%82%A3%E3%83%AB%E3%83%A0%E3%82%AB%E3%83%A1%E3%83%A9%20%E3%82%A2%E3%83%97%E3%83%AA)
- KR "필름카메라 어플" → 디시, 추천, 더쿠, 날짜, 아이폰, 안드로이드, 갤럭시, 무료. KR "디카 어플" → 추천, 느낌, 보정, 필터, 감성, and on YT "**아일릿 민주 디카 어플**" (a K-pop idol's digicam-look app). — [suggest](https://suggestqueries.google.com/complete/search?client=firefox&hl=ko&gl=kr&q=%EB%94%94%EC%B9%B4%20%EC%96%B4%ED%94%8C&ds=yt)
- ID "preset lightroom" → free, gratis, pc, aesthetic, wedding, iphone, android. BR "presets lightroom" → grátis, free, grátis para celular, download, telegram, drive. — [suggest ID](https://suggestqueries.google.com/complete/search?client=firefox&hl=id&gl=id&q=preset%20lightroom); [suggest BR](https://suggestqueries.google.com/complete/search?client=firefox&hl=pt&gl=br&q=presets%20lightroom)

### Inferences
- **Growing and real:**
  - The digicam / "CCD" / Y2K look (strongest in PH, SG, ID, US and DE).
  - Fujifilm-recipe and film-simulation intent.
  - LUTs and colour grading, driven by video and the Log workflows of iPhone and Blackmagic Camera.
  - Dazz-style retro cameras on **Android**. Dazz queries carry heavy "android / apk / apps like" modifiers. This is an Android gap: the original Dazz Cam is iOS-first, and Play results are clones.
- **Declining:** VSCO and generic "preset lightroom / lightroom presets" demand (especially VN and ID), Picsart, Huji-era apps, and generic Vietnamese "app chụp ảnh / app chỉnh màu" searches on Google.
- **Stable:** in VN, the aesthetic/film-stock queries ("màu film", "ảnh film"), with film-camera hardware ("máy ảnh film") at a 5-year high in Aug-2026.
- **Not real:** the apparent 2025–26 explosion of "film camera app / film filter / film filter app / photo filter app / retro camera app" on Google Trends. It fails the control test, so it should not justify prioritising these as "rising" keywords. They remain relevant **store** keywords (see §2), but not growth signals.
- For Vietnam, Google web search is a weak proxy for app discovery. VN generic app queries fell 50–75% over 3 years, while store autocomplete shows rich VN phrasing. So Vietnamese ASO keyword choice should rely more on store autocomplete and ranking data than on Google Trends.

### Gaps
- Google Trends only gives relative indices. No absolute Google search volumes were available: Google Keyword Planner requires a logged-in Google Ads account and was not accessed, and no public source quotes Keyword Planner volumes for these terms.
- The official Google Trends API (2026) was not accessed. Data came from the unofficial pytrends client. Values can differ slightly between pulls because Trends samples.
- The cause of the Aug-2025 / Mar–Jun-2026 distortion is not publicly documented; the Malekos article is paywalled. My characterisation comes from my own control-keyword measurements.
- In KR, most Korean-language app queries are below the Google Trends threshold, because Naver dominates Korean search. Naver DataLab was not queried.

## 2. Store search: Google Play & App Store autocomplete, and which apps rank top 10 for core terms (US, VN, plus JP/KR/ID)

### Takeaway
Store autocomplete confirms a stable set of store-native intents:
- **film camera** (+ "app", "free", "filter", "video", "vintage", "light meter")
- **retro camera** (+ "film vintage", "vintage filter", "offline")
- **dazz** (dazz cam app / dazz camera app)
- **ccd cam / ccd camera**, **digicam** (+ "y2k", "filter", "editor")
- **disposable camera** (+ "app", "filter", "events")
- **y2k camera / y2k photo editor**
- **film filter** (+ "photo editor", "camera", "video")
- **lightroom presets** (+ "free", "app")
- **vintage camera**, **grain**

On Google Play, **OldRoll, ProCCD and "Vintage Film Camera – Digicam" (ZANKHANA) dominate almost every film-camera term in both US and VN**. Filmode and FilCam do not rank in the top ~30 for any generic term.

### Cited Findings

**Google Play autocomplete (google-play-scraper `suggest`, 2026-09-27)** — source: Google Play search, e.g. [play.google.com/store/search?q=film%20camera&c=apps&gl=US](https://play.google.com/store/search?q=film%20camera&c=apps&gl=US)

| seed | US suggestions (in order) | VN suggestions (in order) |
|---|---|---|
| film | filmora, filmoir, filmrise, filmic pro, film | **film cam**, film, filmora, filmic pro, film camera |
| film camera | film camera, film camera app, film camera video, film camera vintage camera, film camera light meter | film camera, film camera free, film camera app, film camera video, film camera filter |
| dazz | dazz cam app, dazzly, dazz camera app, dazz cam camera, dazz | dazz camera, dazz, dazzle design, dazz camera app iphone, **dazz cam chụp ảnh** |
| retro camera | retro camera, retro camera app, retro camera film vintage, retro camera vintage filter, retro camera offline | retro camera, retro camera film, retro camera app, retro camera free, retro camera film vintage |
| preset | presets, presets for lightroom, presets for chase bliss, preset & filters for lightroom.apk, preset and filters for lightroom | preset, **preset xiaomi**, **preset xiaomi camera**, preset lightroom, presets & filters – koloro |
| lut | lutron, lutron caseta… (no photo intent) | luts chat, lotte cinema, lotus chat, lut, lutot chat (no photo intent) |
| lightroom preset | lightroom presets, lightroom presets free, lightroom presets photo editing, lightroom presets app, lightroom presets zone | lightroom preset(s), lightroom presets app, lightroom presets free, lightroom presets zone |
| vsco | vsco, vscode, vscode for android, vsco app, vsco droid | vsco, vsco a4, vscode, vsco cam, vscode for android |
| fuji | fujifilm app, fujifilm, fujifilm kiosk…, fuji, fujifilm camera remote app | fujimart, fujimart việt nam, fujifilm, fujifilm camera remote, fuji |
| kodak | kodak photo printer, kodak, kodak step printer…, kodak digital frame, kodak instant printer | kodak, kodak photo printer, kodak mobile film scanner, **kodak gold 200**, **kodak camera** |
| polaroid | polaroid, polaroid hi print…, polaroid camera, polaroid zip, polaroid app | polaroid, **polaroid frame**, polaroid camera, **polaroid dazz cam**, polaroid office |
| ccd | ccd, ccdt club car, **ccd camera**, ccdt, **ccd cam** | ccd, **ccd pro**, **ccd cam**, ccd camera, ccdt |
| digicam | digicam, digicamfx, digicampus, digicam app android, digicam editor | digicam, digicamfx, digicam camera, **digicam y2k**, digicampus 2.0 |
| grain | grainger… (no photo intent), grain | grain, **grainy 2**, **grainy**, **grainy 3**, **grain camera** |
| vintage | vintage, vintage camera, vintage app, vintage photo editor, vintage color by number | vintage camera, vintage story, vintage, vintage camera hd retro filter, vintage photobooth |
| disposable camera | disposable camera app, disposable camera oldroll, disposable camera, disposable camera filter, disposable camera app free | disposable camera, disposable camera app, disposable camera oldroll, disposable camera events, disposable camera filter |
| film filter | film filter, film filter photo editor, film filter app, film filter editor, film filter camera | film filter, film filter camera, film filter photo editor, film filter app, film filter video |
| y2k | y2k, y2k 200s photo editor, y2k photo editor 2000s, y2k app, y2k camera | y2k, y2k 2000s photo editor, y2k app, y2k camera, y2k game |
| VN-only seeds | — | "máy ảnh film" → máy ảnh film analog, máy ảnh màu film · "chụp ảnh film" → app chụp ảnh film, chụp ảnh màu film · "ảnh film" → chụp ảnh film, máy ảnh film, app chụp ảnh film, máy ảnh film analog · "app chụp ảnh" → đẹp, **có filter**, live photo, **có ngày giờ địa điểm** · "app chỉnh màu" → ảnh đẹp, ảnh, tóc, video · "filter" → filter chụp ảnh, filter snapchat, filter tiktok · "công thức màu" → no suggestions |

**Google Play autocomplete, other markets**
- JP: "フィルムカメラ" → 無料, フィルムカメラアプリ, フィルムカメラ風, dazz フィルムカメラ · "写ルンです" → 写ルンですプラス, 写ルンです風, 写ルンですカメラ · "デジカメ" → デジカメ風カメラ, デジカメ風, デジカメアプリ · "レトロカメラ" → 無料, アプリ
- KR: "필름카메라" → 필름카메라어플, 무료, 필름카메라 필터, dazz 필름카메라 · "디카" → 디카 필터, 디카앱 · "빈티지 카메라" → 빈티지 카메라앱, 빈티지 필터 카메라
- ID: "kamera film" → vintage, video, cam, live · "kamera jadul" → burik, 1990, nokia, aplikasi kamera jadul · "filter film" → film grain filter, vintage film filter
- BR: "film camera" → **film cam**, film camera app, film cam – câmera vintage
- DE: "film camera" → app, editor, vintage camera, video. "lut" gives no photo intent in any market.

— [Google Play search JP](https://play.google.com/store/search?q=%E3%83%95%E3%82%A3%E3%83%AB%E3%83%A0%E3%82%AB%E3%83%A1%E3%83%A9&c=apps&gl=JP)

**Google Play top-10 for core terms (US, VN; 2026-09-27)** — source: `play.google.com/store/search?q=<term>&c=apps&gl=<US|VN>`. Package IDs are in brackets the first time; "(ZANKHANA) Vintage Film Camera – Digicam" = `filmcamera.vintagecamera.digitalcamera.retrocamera`, localised in VN as "Film Cam – Máy ảnh cổ điển".
- **film camera**
  - US: 1 Vintage Film Camera–Digicam, 2 OldRoll [`com.accordion.analogcam`], 3 ProCCD [`com.cerdillac.proccd`], 4 Super 16, 5 Foodie, 6 LoFi Cam, 7 Film Simulator, 8 Filmory, 9 Film35, 10 FIMO
  - VN: 1 OldRoll, 2 Film Cam–Máy ảnh cổ điển, 3 ProCCD, 4 Foodie, 5 LoFi Cam, 6 FIMO, 7 Filmory, 8 NeoFilm, 9 Film35, 10 Film Simulator

  — [US](https://play.google.com/store/search?q=film%20camera&c=apps&gl=US) · [VN](https://play.google.com/store/search?q=film%20camera&c=apps&gl=VN)
- **film camera app**
  - US: OldRoll, Vintage Film Camera–Digicam, ProCCD, LoFi Cam, Foodie, Super 16, FIMO, Kapi Cam, Film Simulator, NeoFilm
  - VN: OldRoll, ProCCD, Film Cam, Foodie, LoFi, NeoFilm, Ferrey, FIMO, Filmroll, Super 16

  — [US](https://play.google.com/store/search?q=film%20camera%20app&c=apps&gl=US)
- **film filter**
  - US: OldRoll, Vintage Film Camera–Digicam, Foodie, ProCCD, VSCO, Camera360, PREQUEL, B612, BeautyPlus, Vintify
  - VN: OldRoll, Foodie, PREQUEL, Camera360, B612, ProCCD, Film Cam, VSCO, PICFX, Afterlight

  — [US](https://play.google.com/store/search?q=film%20filter&c=apps&gl=US)
- **dazz cam**
  - US: 1 "Dazz Cam" [`com.vintage.camera.pro`, MA CLO APPS, released 2026-08-30], 2 Dazzil Cam, 3 Dazzle Cam, 4 Dazz Camera [`tej.digicam.filter`], 5 Dazzy Cam, 6 Dazz Cam [`com.khursheed.dazzcam2`], 7 OldRoll, 8 Dazzo Cam, 9 Vintage Film Camera–Digicam, 10 Dazzify Film Cam
  - VN: Dazz Cam (MA CLO), Dazzle Cam, Dazz Camera, OMO Roll, Dazzy Cam, OldRoll, Film Cam, ProCCD, **Fomz**, B612
  - The top slots are look-alike apps named after Dazz, not the original iOS developer.

  — [US](https://play.google.com/store/search?q=dazz%20cam&c=apps&gl=US)
- **retro camera**
  - US: OldRoll, Vintage Film Camera–Digicam, ProCCD, OldReel, Bebo Cam, LoFi Cam, Filmroll, CAM135, RetroCam, FIMO
  - VN: OldRoll, RetroCam, Film Cam, ProCCD, OldReel, Bebo Cam, Vintage Camera, Retro Cam, LoFi Cam, 1998 Cam

  — [US](https://play.google.com/store/search?q=retro%20camera&c=apps&gl=US)
- **vintage camera**
  - US: OldRoll, Vintage Film Camera–Digicam, OldReel, 1998 Cam, Filmroll, ProCCD, Bebo Cam, CAM135, Vintage Camera, Tapee
  - VN: OldRoll, Film Cam, OldReel, Vintage Cam Filter, Film Cam–Vintage Roll, Filmroll, ProCCD, Vintage Camera, 1998 Cam, Bebo Cam

  — [US](https://play.google.com/store/search?q=vintage%20camera&c=apps&gl=US)
- **ccd camera**
  - US: ProCCD, CCD Cam–Y2K Retro, Y2K Camera: CCD, Film & VHS, Kapi Cam (×2 listings), Cameroll CCD, Locam, LoFi Cam, Vintage Film Camera–Digicam, Pixel Camera
  - VN: ProCCD, CCD Cam, Y2K Camera, LoFi, Kapi Cam ×2, Cameroll CCD, Film Cam, Camera Pixel, DS cam

  — [US](https://play.google.com/store/search?q=ccd%20camera&c=apps&gl=US)
- **digicam**
  - US: ProCCD, Vintage Film Camera–Digicam, OldRoll, LoFi Cam, digicamfx, Cam10, OldReel, BeautyCam, Retrica, Y2K Cam
  - VN: ProCCD, Film Cam, OldRoll, digicamfx, BeautyCam, Cam10, LoFi, OldReel, Retrica, Dazz Cam

  — [US](https://play.google.com/store/search?q=digicam&c=apps&gl=US)
- **y2k camera**
  - US: y2k: 2000s photo editor, Y2K Camera: CCD, Film & VHS, Y2KCam, Y2K Photo Editor & Filter Camera, digicamfx, Y2K Cam, ProCCD, CCD Cam, Kapi Cam, Y2K Vintage Photo Editor

  — [US](https://play.google.com/store/search?q=y2k%20camera&c=apps&gl=US)
- **disposable camera**
  - US: POV–Disposable Camera Events, OldRoll, Disposable Camera App, Disposable camera, Poka Cam, Party Cam, Lense, Flashback, Scene, Reveal. This is mostly the **event / shared-album** intent, not the film look.

  — [US](https://play.google.com/store/search?q=disposable%20camera&c=apps&gl=US)
- **film grain**
  - US: Grain – Pro Film Camera, Vintage Film Camera–Digicam, Film Simulator, Filmic Firstlight, Film35, PICFX, OldRoll, Ferrey, Filmos, Filmic Pro
  - VN: Grain, OMO Roll, FIMO, Film35, Film Cam, Noir Pic, Film Simulator…

  — [US](https://play.google.com/store/search?q=film%20grain&c=apps&gl=US)
- **fuji film filter**
  - US: FUJIFILM XApp, **FujiStyle – Film Recipes Frame**, FUJIFILM Camera Remote, **Fuji X Weekly – Film Recipes**, WPS Photo Transfer, X half, instax WIDE Evo, Fujifilm Print, instax Link WIDE, **Fuji Recipes**
  - VN: FujiStyle is #1, and "Fuji Pic – Film Recipes" appears

  — [US](https://play.google.com/store/search?q=fuji%20film%20filter&c=apps&gl=US)
- **lightroom presets / preset**
  - US: Presets for Lightroom – FLTR [`com.feelty`], Lightroom, Presets For LR, Preset & Filter for Lightroom, ps.clix, Presets for Lightroom Mobile, Koloro, LR Presets, Presetly, Luminar
  - VN: FLTR (localised "Preset Lightroom, bộ lọc ảnh"), Lightroom, PREQUEL, Photoshop Express, Luminar, Polarr, Picsart, Prisma, Polish, **Fimii** ("Chỉnh Ảnh Film & Preset"). VN "preset" also brings Fimii at #7.

  — [US](https://play.google.com/store/search?q=lightroom%20presets&c=apps&gl=US) · [VN](https://play.google.com/store/search?q=preset%20lightroom&c=apps&gl=VN)
- **lut / lut app**
  - US: LUT Generator: Color Grading, 3DLUT mobile, AGC ToolKit, L.U.T: Color grading, 3DLUT mobile 2, ColorShaper, CameLUT, LUTS–Look Up The Sky, Blackmagic Camera, LutinRouge (irrelevant)
  - VN adds **Modipix: Film Lab & 3D LUT**
  - This is a thin, low-quality field: #1 LUT Generator has 10K+ installs; 3DLUT mobile has 10M+ but was last updated 2024-07-29.

  — [US](https://play.google.com/store/search?q=lut&c=apps&gl=US)
- **VN-language terms**
  - "máy ảnh film": Film Cam, OldRoll, ProCCD, **Fomz**, **NOMO CAM**, Foodie, LoFi, OldReel, B612, Camera Pixel
  - "chụp ảnh film": **NOMO CAM #1**, ProCCD, Film Cam, OldRoll, Fomz, VSCO, B612, Foodie, Protake, Camera Pixel
  - "app chụp ảnh film": ProCCD, OldRoll, Film Cam, Fomz, NOMO, B612, Camera360, Foodie, VSCO, Protake
  - "filter film": OldRoll, Foodie, B612, PREQUEL, Film Cam, Camera360, ProCCD, Afterlight, PICFX, VSCO

  — [VN máy ảnh film](https://play.google.com/store/search?q=m%C3%A1y%20%E1%BA%A3nh%20film&c=apps&gl=VN)
- **JP / KR / ID top-10**
  - JP "フィルムカメラ": ProCCD, FIMO, OldRoll, Foodie, Film Cam, フィルムカメラ-アナログフィルム, LoFi, Film35, **filmhwa**, NOMO
  - KR "필름카메라": ProCCD, OldRoll, Film Cam, **베리필름 Berryfilm**, **filmhwa (필름화)**, FIMO, Foodie, BeautyCam, LoFi, SNOW
  - ID "kamera film": OldRoll, Film Cam, ProCCD, LoFi, FIMO, Pixel Camera, OldReel…

  — [JP](https://play.google.com/store/search?q=%E3%83%95%E3%82%A3%E3%83%AB%E3%83%A0%E3%82%AB%E3%83%A1%E3%83%A9&c=apps&gl=JP) · [KR](https://play.google.com/store/search?q=%ED%95%84%EB%A6%84%EC%B9%B4%EB%A9%94%EB%9D%BC&c=apps&gl=KR)

**Google Play installs and ratings of the apps that rank (details pages, 2026-09-27)** — source: `play.google.com/store/apps/details?id=<package>`

| app (package) | installs band (scraper's exact count) | rating (count) | released | last update |
|---|---|---|---|---|
| Filmode Vibe — Film Camera ([app.filmode](https://play.google.com/store/apps/details?id=app.filmode)) | 50+ (69) | – | 2026-07-22 | 2026-09-22 |
| FilCam: Pro Manual RAW Camera ([app.filmode.filcam](https://play.google.com/store/apps/details?id=app.filmode.filcam)) | 100+ (327) | – | 2026-09-04 | 2026-09-26 |
| OldRoll ([com.accordion.analogcam](https://play.google.com/store/apps/details?id=com.accordion.analogcam)) | 10M+ (40.1M) | 4.27 (213K) | 2020-08-28 | 2026-09-17 |
| ProCCD ([com.cerdillac.proccd](https://play.google.com/store/apps/details?id=com.cerdillac.proccd)) | 10M+ (22.2M) | 4.83 (198K) | 2022-07-08 | 2026-08-13 |
| Vintage Film Camera – Digicam ([filmcamera.vintagecamera…](https://play.google.com/store/apps/details?id=filmcamera.vintagecamera.digitalcamera.retrocamera)) | 1M+ (4.6M) | 4.75 (109K) | **2025-07-11** | 2026-09-15 |
| Fomz ([com.imendon.fomz](https://play.google.com/store/apps/details?id=com.imendon.fomz)) | 10M+ (31.7M) | 4.51 (90K) | 2022-05-05 | 2026-05-21 |
| Dazzil Cam ([com.camerafilm.lofiretro](https://play.google.com/store/apps/details?id=com.camerafilm.lofiretro)) | 10M+ (20.3M) | 4.14 (86K) | 2020-09-28 | 2026-09-27 |
| Kapi Cam – Y2K & CCD ([com.sensemobile.action](https://play.google.com/store/apps/details?id=com.sensemobile.action)) | 10M+ (16.3M) | 4.58 (66K) | **2024-01-23** | 2026-09-15 |
| Foodie ([com.linecorp.foodcam.android](https://play.google.com/store/apps/details?id=com.linecorp.foodcam.android)) | 10M+ (42.3M) | 3.58 (132K) | 2016-02-01 | 2026-09-08 |
| NOMO CAM ([com.blink.academy.nomopro](https://play.google.com/store/apps/details?id=com.blink.academy.nomopro)) | 5M+ (9.7M) | 3.73 (13.6K) | 2018-05-23 | 2026-04-03 |
| FIMO ([com.fimo.camera](https://play.google.com/store/apps/details?id=com.fimo.camera)) | 5M+ (5.9M) | 3.09 (11.7K) | 2019-12-12 | 2025-10-21 |
| LoFi Cam ([com.camera.loficam](https://play.google.com/store/apps/details?id=com.camera.loficam)) | 1M+ (2.5M) | 3.61 (1.5K) | 2024-02-22 | 2026-09-23 |
| y2k: 2000s photo editor ([com.abel.y2k](https://play.google.com/store/apps/details?id=com.abel.y2k)) | 1M+ (1.1M) | 4.85 (22K) | **2025-12-14** | 2026-09-23 |
| Dazzle Cam ([com.camerafilter.tikfilm…](https://play.google.com/store/apps/details?id=com.camerafilter.tikfilm.retroimage.ss.android.ugc.aweme.mobile)) | 500K+ (653K) | 4.20 (1.9K) | 2024-10-11 | 2026-04-27 |
| "Dazz Cam" ([com.vintage.camera.pro](https://play.google.com/store/apps/details?id=com.vintage.camera.pro)) | 100K+ (150K) | 3.55 (242) | **2026-08-30** | 2026-09-17 |
| 1998 Cam ([com.aaai.cam1998](https://play.google.com/store/apps/details?id=com.aaai.cam1998)) | 100K+ (137K) | 4.44 (785) | 2026-04-21 (listing date) | 2026-09-07 |
| Grain – Pro Film Camera ([com.graincamera](https://play.google.com/store/apps/details?id=com.graincamera)) | 50K+ (92K) | 4.42 (297) | 2025-09-16 | 2026-08-05 |
| Fuji X Weekly — Film Recipes ([com.fujixweekly.FujiXWeekly](https://play.google.com/store/apps/details?id=com.fujixweekly.FujiXWeekly)) | 100K+ (408K) | 4.44 (875) | 2021-02-23 | 2026-09-17 |
| FujiStyle – Film Recipes Frame ([com.fujistylelead.global](https://play.google.com/store/apps/details?id=com.fujistylelead.global)) | 10K+ (22K) | 4.40 (632) | 2025-12-25 | 2026-06-12 |
| Presets for Lightroom – FLTR ([com.feelty](https://play.google.com/store/apps/details?id=com.feelty)) | 10M+ (30.0M) | 4.57 (419K) | 2019-06-25 | 2026-06-29 |
| Koloro ([com.cerdillac.persetforlightroom](https://play.google.com/store/apps/details?id=com.cerdillac.persetforlightroom)) | 10M+ (40.2M) | 4.80 (431K) | 2019-01-09 | **2024-06-27** |
| 3DLUT mobile ([com.lutmobile.lut](https://play.google.com/store/apps/details?id=com.lutmobile.lut)) | 10M+ (17.4M) | 3.88 (29.6K) | 2018-04-14 | **2024-07-29** |
| LUT Generator ([lut.generator.luts](https://play.google.com/store/apps/details?id=lut.generator.luts)) | 10K+ (13.7K) | 4.20 (88) | 2023-11-04 | 2026-09-03 |
| Modipix: Film Lab & 3D LUT ([com.duc_app_lab_ind.pic_trim_app](https://play.google.com/store/apps/details?id=com.duc_app_lab_ind.pic_trim_app)) | 5K+ (7.8K) | 4.30 (143) | 2024-03-30 | 2026-09-26 |
| Fimii: Film Presets & Editor ([com.ankii.fimii](https://play.google.com/store/apps/details?id=com.ankii.fimii)) | 5K+ (8.7K) | – | 2026-02-03 | 2026-09-25 |
| VSCO ([com.vsco.cam](https://play.google.com/store/apps/details?id=com.vsco.cam)) | 100M+ (164.5M) | 3.62 (1.33M) | 2013-12-03 | 2026-09-21 |
| Lightroom ([com.adobe.lrmobile](https://play.google.com/store/apps/details?id=com.adobe.lrmobile)) | 100M+ (470.9M) | 4.47 (3.66M) | 2015-01-14 | 2026-09-17 |
| Picsart ([com.picsart.studio](https://play.google.com/store/apps/details?id=com.picsart.studio)) | 1B+ (1.44B) | 3.96 (12.1M) | 2011-11-04 | 2026-09-23 |

**Filmode / FilCam store visibility (google-play-scraper search, up to ~30 results returned per query, 2026-09-27)**
- **app.filmode** ranks #2 (US) and #1 (VN) only for its brand term "filmode". It is **not in the top ~30** for film camera, film filter, film camera app, retro camera, vintage camera, film simulation, lut camera, máy ảnh film or app chụp ảnh film, in either US or VN.
- **app.filmode.filcam** ranks #1 for "filcam" in both markets, **#24 for "raw camera"** (US) and **#29 for "manual camera"** (US). It is not in the top ~30 for any film term.
- Filmode has no measurable Google Trends brand demand (the series is all zero).

— [Play search "filmode" US](https://play.google.com/store/search?q=filmode&c=apps&gl=US); [GT filmode](https://trends.google.com/trends/explore?date=today%205-y&q=filmode)

**App Store search hints (Apple MZSearchHints, storefront header, 2026-09-27)** — source: `https://search.itunes.apple.com/WebObjects/MZSearchHints.woa/wa/hints?clientApplication=Software&term=<term>` (it returns empty unless an `X-Apple-Store-Front` header such as `143441-1,29` for US is sent), e.g. [film](https://search.itunes.apple.com/WebObjects/MZSearchHints.woa/wa/hints?clientApplication=Software&term=film)
- **US**
  - film camera → film camera filter, film camera light meter, film camera, film camera simulator, film camera video, film camera edit, film camera settings, film camera filter free, lightwell: film camera, rolls — our film camera
  - retro camera → retro camera filter, retro camera, retro camera free, filmee, camcorder retro camera, retro camera: aesthetic video…
  - dazz → dazz cam, dazz, dazzly, dazz cam- vintage camera, dazz相机, …, dazzcam pro
  - ccd → ccd cam, ccd camera, ccd, pro ccd, dicalog – ccd digicam camera, ccd cam – digital dazz cam, ccd campro
  - digicam → digicamfx, digicam, digicam filter, digicamfx camera, molly: digicam photo filters, digicam free, dicalog
  - grain → … grain filter, grain: photo editor
  - vintage → vintage camera, vintage photo editor, vintage filter, vintage camera filter, vintage video camera
  - disposable camera → disposable camera filter, …wedding, …events, …scanner, POV, Scene…
  - y2k → y2k: 2000s photo editor, y2k camera, y2k photo editor, y2k filter, y2k editor
  - film filter → film filter free, film filter, vintage film filter, film filter video, free film filter, old film filter, picfx…, beluga, cinegrade: film filters
  - fuji → fujifilm, **fujixweekly**, fujifilm camera remote, **fujistyle**, fuji, …, **fuji recipes**
  - lut → luts studio, lut (the rest is Lutron)
  - lightroom preset → lightroom presets free, lightroom presets, …posica, lrpresets, presetify…
  - preset → presets, presets for lightroom, presets & filters, preset filters, photo presets free, free presets, lightroom presets
- **VN**
  - film → film camera, **filmhwa**, filmer, filmic pro, filmora, film, film cam, filmroll
  - dazz → dazz cam, dazzz cam, dazz, dazz cam original, **dazz chup anh dep**, dazza cam, dazz camera, dazz pro
  - preset → preset, preset lightroom, presets for lightroom – editor/fltr, koloro, …, **fimii: film presets & editor**
  - vsco → vsco, vsco a4, vsco cam, **vsco tiếng việt**
  - fuji → fujimart việt nam, fujifilm, fujifilm camera remote, **fuji style**, fujifilm xapp, fujixweekly, fuji x weekly — film recipes
  - kodak → kodak photo printer, **kodak cam**
  - polaroid → polaroid, polaroid frame, scan polaroid, **polaroid dazzcam**, ghép ảnh polaroid
  - vintage → vintage camera, vintage, vintage cam, fotojadul, **chụp ảnh vintage**, dazz cam – vintage camera, oldroll, fomz, filmroll
  - app chụp ảnh → có ngày giờ, đẹp, **app chụp ảnh film**, đẹp cho iphone…
  - chỉnh màu → chỉnh màu ảnh đẹp, chỉnh màu ảnh, chỉnh màu đèn led, **chỉnh màu film**, chỉnh màu video, chỉnh màu tóc, chỉnh màu trời
  - "máy ảnh film" and "chụp ảnh film" each only echo themselves; "công thức màu" gives no hints
- **JP**
  - film camera → … 1888 cam, 1970 cam, 35mm film camera pro, analogue
  - dazz → dazz カメラ, dazzカメラ, dazz cam, dazzカメラ 無料, dazzフィルムカメラ
  - フィルムカメラ → 無料, 加工, フィルムカメラアプリ, フィルムカメラ風, 動画, 露出計, dazz – フィルムカメラ, fomz – フィルムカメラアプリ
  - 写ルンです → 写ルンです＋, 写ルンですプラス
  - レトロ → レトロカメラ, レトロ写真, レトロカメラ無料, レトロフィルムカメラ
  - y2k → y2k カメラ, pixie+ y2k デジカメ風カメラ, y2kカメラ2003 デジカメ風プリクラ
  - lut → lut studio, video lut, luttie: log & lut color studio, lumix lut
- **KR**
  - 필름카메라 → 필름카메라 필터, 필름카메라 감성, dazz – 필름카메라 & 사진 편집, luzmo, filteros…
  - 필카 → 필카 필터, [필카 노출계], 필카소
  - 디카 → 디카 필터, 무료 디카, 디카로그 dicalog, 빈티지 디카, 디카 99 – y2k, 2000s y2k 디카
  - y2k → y2k 카메라, y2k 필터
  - ccd → ccd — y2k 레트로 디카, ccd diary: 빈티지 카메라

— raw output in the hints endpoint above with storefronts VN `143471`, JP `143462`, KR `143466`

### Inferences
- Store search is dominated by **generic + style** heads: film camera, retro camera, vintage camera, film filter, ccd, digicam, y2k camera, disposable camera, dazz. Precise pro terms (lut, grain, film simulation) have little or no store autocomplete, and "lut" is swamped by Lutron / Lotte / "luta".
- The same 3 apps (OldRoll, ProCCD, ZANKHANA's Vintage Film Camera–Digicam) take the top 3 for most film heads in US, VN, ID, JP and KR. Head terms are therefore very hard for a new app.
- Beatable fields where results are thin, old or low quality:
  - LUT apps: the leader is small (10K+ installs) or abandoned (3DLUT mobile, not updated since 2024-07).
  - Fuji-recipe apps: FujiStyle has 10K+ installs, Fuji Recipes 5K+.
  - "film grain", where #1 has 50K+ installs.
  - VN "preset"/"màu film", where a 5K-install app (Fimii) already ranks.
- The "ZANKHANA Vintage Film Camera – Digicam" (4.6M installs within about 14 months of its 2025-07-11 release), Kapi Cam (2024) and y2k: 2000s photo editor (1.1M+ since 2025-12) show that new entrants **can** break into the heads with keyword-stuffed titles ("Vintage Film Camera – Digicam", "Y2K & CCD Camera").

### Gaps
- Google Play gives no volume per suggestion. The order of suggestions is only a weak popularity signal.
- The scraper returns about 30 results per query, so Filmode's exact rank below 30 is unknown.
- App Store top-10 rankings per term were not scraped (Google Play was the priority).
- Apple Search Ads popularity scores were not accessible, since they need an Apple Search Ads account.

## 3. ASO keyword volume / difficulty figures available from public ASO tool pages and blogs

### Takeaway
Almost no public, dated keyword-volume data exists for this niche. The only free numbers found are undated ASOTools "search volume / KD" indices, which appear to use a 5–100 popularity scale. They rank the heads as follows: **vsco (63) > lightroom (59) > vntage/vintage (53) = muji/"huji" cluster (53) > dazz cam (52) > lightroom presets (44) ≈ preset lightroom (43) > disposable camera (41) > presets for lightroom (40) > film camera (37) = super 8 (37) > disposable (35) > free presets for lightroom (34) > fimo (31) = 35 mm film (31) > dazzcam (29)**. KDs are low-to-mid (13–45).

Google Keyword Planner volumes could not be obtained.

### Cited Findings
- ASOTools "film camera": "search volume … reached **37**, its difficulty level reached **18**, and the number of apps related … 250+". Related keywords with volume/KD:
  - disposable camera 41/20
  - 35 mm film 31/13
  - super 8 37/24
  - "vntage" 53/28
  - fimo 31/22
  - fujifilm camera 21/23
  - best film camera 19/30
  - movie camera 18/13
  - film roll camera 9/10
  - vintage film camera 6/10
  - instamatic 9/21

  The page names neither the store nor the date. It says "Google App Store", but the ranking apps (Cuji Cam, 1998 Cam, FIMO, Super 16, Huji) look like the iOS App Store. — [ASOTools: film camera](https://asotools.io/app-store-keywords/film-camera)
- ASOTools "lightroom presets": volume **44**, KD **20**, 248 related apps. Related keywords:
  - preset lightroom 43/20
  - presets for lightroom 40/30
  - free presets for lightroom 34/31
  - presets for lightroom free 34/28
  - free presets 27/20
  - lightroom 59/45
  - 123 presets 12/23
  - mastin labs 9/20
  - free presets for lightroom mobile 6/21

  — [ASOTools: lightroom presets](https://asotools.io/app-store-keywords/lightroom-presets); [ASOTools: presets for lightroom](https://asotools.io/app-store-keywords/presets-for-lightroom)
- ASOTools "disposable camera": volume **41**, KD **20**. Related keywords:
  - disposable 35/27
  - disposable camera filter 12/13
  - kodak camera 19/17
  - gudak 11/20
  - muji 53/57 (Huji Cam's top keyword)
  - lightsnap ≤5

  — [ASOTools: disposable camera](https://asotools.io/app-store-keywords/disposable-camera)
- ASOTools "vsco": volume **63**, KD **42**. Related keywords:
  - vsco girl 36/20
  - vsco wallpapers 33/4
  - vysco 41/36
  - lightroom 59/45

  — [ASOTools: vsco](https://asotools.io/app-store-keywords/vsco)
- ASOTools "grain": volume 44 / KD 43, but mostly Grainger and food-grain apps. Its photo intent "grain texture" is 23/20. — [ASOTools: grain](https://asotools.io/app-store-keywords/grain)
- ASOTools Dazz Cam keyword monitor:
  - "dazz cam" volume **52**
  - "dazzcam" **29** (KD 47)
  - "daz cam" 12
  - "dazz camm" 1

  Dazz ranks #1 on each. The KD "9981" shown for "dazz cam" is obviously a data error. — [ASOTools: Dazz Cam keywords](https://asotools.io/app-analytics/dazz-cam-keyword-monitoring)
- AppFollow defines Popularity Score as 5–100 relative search frequency in the store. Apple's Search Ads Popularity is the underlying source for iOS. — [AppFollow help](https://support.appfollow.io/hc/en-us/articles/360020832897-Keyword-Popularity-Score); [MobileAction guide](https://www.mobileaction.co/blog/aso-keyword-research/)
- Sensor Tower's public overview snippet for **Dazz Cam – Vintage Camera (iOS, US)** gives "last month's estimates" of **~3M downloads and ~$900k revenue**. The month is not stated, and the figure was seen via the search-result snippet because the page is JS-rendered. — [Sensor Tower: Dazz Cam](https://app.sensortower.com/overview/1422471180?country=US)
- Semrush's free keyword checker needs an account (5 requests/day). No free Semrush/Ahrefs snippet with a volume for "lightroom presets", "luts" or "film filter" was found. — [Semrush free tool](https://www.semrush.com/free-tools/keyword-search-volume-checker/)

### Inferences
- On the (probably iOS) ASOTools scale, film-camera heads (film camera 37, disposable camera 41, dazz cam 52) are **mid-popularity with low KD (18–20)**. That combination supports targeting them in the title and short description.
- Preset heads (lightroom presets 44 / preset lightroom 43) have similar popularity. However, Google Trends shows long-term decline and store results are saturated by FLTR and Koloro (10M+ each).
- Adding Google Play installs of the ranking apps gives a rough demand-weighting: film-camera and CCD apps reach 10–40M installs each, preset apps 30–40M, LUT apps mostly under 150K except the stale 3DLUT mobile. This is a derived proxy, not keyword volume.

### Gaps
- No dated, market-specific (US/VN) keyword volumes: AppTweak, AppFollow, Mobile Action, Astro and ASOMobile require logins or paid plans; Google Keyword Planner requires an Ads account; Apple Search Ads popularity requires an account.
- There is no public source with Vietnamese-language store keyword volumes ("máy ảnh film", "app chụp ảnh film", "preset lightroom").
- ASOTools figures lack the date and market, so treat them as rough relative indicators only.

## 4. Social demand — TikTok hashtags, YouTube search, Reddit communities, and the 2024–2026 trend narratives

### Takeaway
Social demand is far larger than Google demand and tilts to **film/digicam aesthetics and editing**. Undated HashtagRadar snapshots give these TikTok view counts:
- #y2k 26.6B, #vsco 13.7B, #lightroom 6.2B, #y2kaesthetic 4.4B
- #polaroid 2.2B, #filmphotography 1.5B, #digitalcamera 1.2B, #filmcamera 1.1B, #lightroompreset 1.1B
- #colorgrading 902M, #digicam 567M, #disposablecamera 553M, #lut 409M

Reddit film communities are large: r/analog 2.73M, r/analogcommunity 430K, r/fujifilm 330K.

The 2024–26 narratives are well documented:
- compact/digicam revival (CIPA compacts +30% in 2025, +17–48% per month in Jan–Apr 2026)
- X100VI / Fuji-recipe hype
- Kodak Charmera
- the Log/LUT video workflow (Apple Log 2 on iPhone 17 Pro; Blackmagic Camera LUTs)
- Apple adding texture and grain controls to Photographic Styles (iPhone 18 Pro only, Sep-2026)

### Cited Findings
**TikTok.** TikTok Creative Center was not accessible: the API returned `{"code":40101,"msg":"no permission"}` and the pages are JS-only. TikTok tag pages don't server-render counts. The figures below are therefore from **HashtagRadar (formerly tiktokhashtags.com)**, a "stored/cached dataset" with **no snapshot date**. The absence of #x100vi / #fujifilmx100vi (a camera launched Feb-2024) suggests the snapshot predates 2024. Treat these numbers as dated and as floors.

| hashtag | posts | views | avg views/post | src |
|---|---|---|---|---|
| #y2k | 1.7M | 26.6B | 16,015 | [HR](https://hashtagradar.com/hashtag/y2k/) |
| #vsco | 2.1M | 13.7B | 6,401 | [HR](https://hashtagradar.com/hashtag/vsco/) |
| #lightroom | 683K | 6.2B | 9,021 | [HR](https://hashtagradar.com/hashtag/lightroom/) |
| #y2kaesthetic | 230.5K | 4.4B | 19,246 | [HR](https://hashtagradar.com/hashtag/y2kaesthetic/) |
| #polaroid | 1.6M | 2.2B | 1,353 | [HR](https://hashtagradar.com/hashtag/polaroid/) |
| #filmphotography | 210.2K | 1.5B | 7,127 | [HR](https://hashtagradar.com/hashtag/filmphotography/) |
| #digitalcamera | 52.4K | 1.2B | 22,232 | [HR](https://hashtagradar.com/hashtag/digitalcamera/) |
| #filmcamera | 70K | 1.1B | 16,099 | [HR](https://hashtagradar.com/hashtag/filmcamera/) |
| #lightroompreset | 107.2K | 1.1B | 9,986 | [HR](https://hashtagradar.com/hashtag/lightroompreset/) |
| #35mm | 151.6K | 998.7M | 6,589 | [HR](https://hashtagradar.com/hashtag/35mm/) |
| #fujifilm | 119.7K | 924M | 7,722 | [HR](https://hashtagradar.com/hashtag/fujifilm/) |
| #colorgrading | 119.1K | 901.9M | 7,573 | [HR](https://hashtagradar.com/hashtag/colorgrading/) |
| #presets | 61K | 814.2M | 13,347 | [HR](https://hashtagradar.com/hashtag/presets/) |
| #digicam | 28.6K | 567.3M | 19,847 | [HR](https://hashtagradar.com/hashtag/digicam/) |
| #disposablecamera | 36.7K | 552.9M | 15,070 | [HR](https://hashtagradar.com/hashtag/disposablecamera/) |
| #lut | 37.9K | 408.5M | 10,778 | [HR](https://hashtagradar.com/hashtag/lut/) |
| #presetlightroom | 23.4K | 359.1M | 15,343 | [HR](https://hashtagradar.com/hashtag/presetlightroom/) |
| #analogphotography | 57.3K | 296.2M | 5,165 | [HR](https://hashtagradar.com/hashtag/analogphotography/) |
| #lightroompresets | 20.6K | 175.8M | 8,538 | [HR](https://hashtagradar.com/hashtag/lightroompresets/) |
| #ccd | 14.2K | 163.7M | 11,543 | [HR](https://hashtagradar.com/hashtag/ccd/) |
| #dazzcamera | 1.7K | 87.5M | – | [HR](https://hashtagradar.com/hashtag/dazzcamera/) |
| #filmlook | 6.2K | 58.6M | 9,436 | [HR](https://hashtagradar.com/hashtag/filmlook/) |
| #portra400 | 9.7K | 44.9M | – | [HR](https://hashtagradar.com/hashtag/portra400/) |
| #filmfilter | 2.5K | 41.6M | 16,612 | [HR](https://hashtagradar.com/hashtag/filmfilter/) |
| #kodakgold200 | 9.5K | 28.9M | – | [HR](https://hashtagradar.com/hashtag/kodakgold200/) |
| #vscofilter | 2.9K | 26.5M | 9,148 | [HR](https://hashtagradar.com/hashtag/vscofilter/) |
| #luts | 3.9K | 16.3M | 4,138 | [HR](https://hashtagradar.com/hashtag/luts/) |
| #huji | 3.9K | 16.2M | 4,191 | [HR](https://hashtagradar.com/hashtag/huji/) |
| #ccdcamera | – | 6.0M | 15,948 | [HR](https://hashtagradar.com/hashtag/ccdcamera/) |
| #kodakportra | 1.1K | 2.2M | 2,014 | [HR](https://hashtagradar.com/hashtag/kodakportra/) |

- HashtagRadar had no data for #dazzcam, #fujirecipe, #fujifilmrecipe, #fujifilmrecipes, #x100vi, #filmgrain, #filmcam or #chupanhfilm.
- Secondary (dated) TikTok claims:
  - A 2025 Adorama/42West piece says #digitalcamera has "tens of billions of views" and #y2k "100 billion". Another snippet on the same page says "#digitalcamera has 184 million views", which conflicts. — [Adorama 42West](https://www.adorama.com/alc/retro-digital-cameras-gen-z/)
  - Vietnamese media (CafeBiz, 2026-06-19) say #digitalcamera has "hàng tỷ lượt xem" and #digicam "hàng trăm nghìn video". — [CafeBiz](https://cafebiz.vn/tung-bi-smartphone-khai-tu-dong-may-anh-20-nam-tuoi-bat-ngo-hoi-sinh-gen-z-dang-tao-nen-thi-truong-trieu-usd-176260619070655028.chn)

**YouTube**
- The Google Trends YouTube-search series are summarised in §1.
- YouTube autocomplete (2026-09-27) shows tutorial and editor-integration intents:
  - "film filter" → **film filter capcut**, lightroom, premiere pro, iphone, **for video**, **davinci resolve**, after effects
  - "cube lut" → **lut cube free download**, **lut cube lightroom**, **lut cube capcut**, import cube lut premiere
  - "film grain" → overlay, sound effect, green screen, overlay 4k
  - "lightroom presets" → free download, tutorial, mobile, **cinematic**, **film**, **iphone**
  - "fuji recipe" → for portraits, **for video**, 2025, night, **for sony**
  - "dazz cam" → tutorial, settings, best filter, android, review
  - "digicam" → photography, vlog, recommendations, settings, review, collection
  - VN "màu film" → màu film lightroom, chỉnh màu film trên lightroom, cài màu film cho canon/sony
  - VN "preset lightroom" → cinematic, aesthetic, cinematic film
  - ID "preset lightroom" → **terbaru 2025**, aesthetic, cinematic
  - BR "presets lightroom" → grátis iphone, grátis celular, **2025**

  — [YT suggest film filter](https://suggestqueries.google.com/complete/search?client=firefox&hl=en&gl=us&ds=yt&q=film%20filter); [YT suggest cube lut](https://suggestqueries.google.com/complete/search?client=firefox&hl=en&gl=us&ds=yt&q=cube%20lut)

**Reddit community sizes** (reddapi.dev pages accessed 2026-09-27; reddit.com itself returned HTTP 403 from this environment; the snapshot date is not shown)

| community | members | src |
|---|---|---|
| r/photography | 5,648,466 | [reddapi](https://reddapi.dev/subreddits/photography/insights) |
| r/analog | 2,725,008 | [reddapi](https://reddapi.dev/subreddits/analog/insights) |
| r/videography | 455,100 | [reddapi](https://reddapi.dev/subreddits/videography/insights) |
| r/analogcommunity | 430,368 | [reddapi](https://reddapi.dev/subreddits/analogcommunity/insights) |
| r/fujifilm | 329,619 | [reddapi](https://reddapi.dev/subreddits/fujifilm/insights) |
| r/davinciresolve | 229,493 | [reddapi](https://reddapi.dev/subreddits/davinciresolve/insights) |
| r/Lightroom | 140,612 | [reddapi](https://reddapi.dev/subreddits/Lightroom/insights) |
| r/filmphotography | 137,394 | [reddapi](https://reddapi.dev/subreddits/filmphotography/insights) |
| r/y2kaesthetic | 111,733 | [reddapi](https://reddapi.dev/subreddits/y2kaesthetic/insights) |
| r/fujix | 96,901 | [reddapi](https://reddapi.dev/subreddits/fujix/insights) |
| r/colorists | 68,506 | [reddapi](https://reddapi.dev/subreddits/colorists/insights) |
| r/colorgrading | 60,826 | [reddapi](https://reddapi.dev/subreddits/colorgrading/insights) |
| r/editing | 57,790 | [reddapi](https://reddapi.dev/subreddits/editing/insights) |
| r/instax | 55,277 | [reddapi](https://reddapi.dev/subreddits/instax/insights) |
| r/x100v | 22,370 | [reddapi](https://reddapi.dev/subreddits/x100v/insights) |
| r/vsco | 11,457 | [reddapi](https://reddapi.dev/subreddits/vsco/insights) |
| r/postprocessing | not available on reddapi | – |

**Trend narratives 2024–2026 (dated)**
- **Compact/digicam revival**
  - CIPA 2025: shipments of built-in-lens cameras **grew ~30%** vs 2024, to 25.8% of all camera units. Total camera shipments rose 11%. DPReview notes this likely *undersells* the trend because Costco, Amazon and TikTok Shop sales aren't captured. — [DPReview, 2026-02-02](https://www.dpreview.com/articles/2386206926/cipa-data-2025-camera-lens-shipments-fixed-lens-cameras-interchangable/)
  - 2026 so far: built-in-lens shipments were **136% (Jan), 117% (Feb), 119% (Mar), 148% (Apr)** of 2025 levels. April 2026 alone "would have bested 11 months in 2025." — [PetaPixel, 2026-06-11](https://petapixel.com/2026/06/11/compact-camera-sales-are-still-booming-amid-growing-photo-industry/)
  - Vietnam: Gen Z are "reviving" old digicams. Used compacts cost 3–5 million VND, and rental costs about 1/10 of the purchase price. — [CafeBiz, 2026-06-19](https://cafebiz.vn/tung-bi-smartphone-khai-tu-dong-may-anh-20-nam-tuoi-bat-ngo-hoi-sinh-gen-z-dang-tao-nen-thi-truong-trieu-usd-176260619070655028.chn); [VietNamNet](https://vietnamnet.vn/chi-tien-trieu-de-hoi-sinh-may-anh-cu-gen-z-du-trend-vi-cam-xuc-kho-dien-ta-2400701.html)
  - K-pop idols' "digicam" photos are driving the VN trend. — [Harper's Bazaar VN](https://bazaarvietnam.vn/bat-trend-chup-anh-digicam-cung-cac-tuong-k-pop/)
  - The KR YouTube autocomplete "아일릿 민주 디카 어플" confirms the idol-driven digicam-app demand. — see §1 suggest link
- **Kodak Charmera** (a ~$30 keychain digicam) launched 2025-09-09 and sold out within 24 hours. Kodak "sold 10 times more … than it expected." — [Deseret News, 2025-09-13](https://www.deseret.com/lifestyle/2025/09/13/kodak-mini-camera-sold-out/); [Boing Boing, 2025-09-19](https://boingboing.net/2025/09/19/kodaks-charmera-keychain-camera-sells-out-in-hours.html)
- **Fujifilm X100VI and recipes**
  - The X100VI was backordered for over a year after its Feb-2024 launch, and Fujifilm doubled production. B&H moved it to an "end of May 2025" ship date. — [Digital Camera World](https://www.digitalcameraworld.com/cameras/compact-cameras/am-i-seeing-things-the-most-coveted-compact-camera-the-fujifilm-x100vi-finally-has-an-estimated-ship-date-at-this-retailer); [Fstoppers 2025](https://fstoppers.com/business/why-still-cant-buy-fujifilm-x100vi-or-ricoh-gr-iv-real-story-behind-shortages-717649)
  - Fuji X Weekly's most-viewed recipes for Jan 1–Jul 31 2026 barely changed from Q1. Recipes with **Kodak names (Kodachrome, Portra, Gold, Tri-X)** are most popular, and Classic Chrome is "king". — [Fuji X Weekly, 2026-08-03](https://fujixweekly.com/2026/08/03/top-26-most-popular-fujifilm-recipes-of-2026-so-far-summer-edition/)
  - The Fuji X Weekly app has 100K+ installs on Play (408K by the scraper's count). — [Play](https://play.google.com/store/apps/details?id=com.fujixweekly.FujiXWeekly)
- **Phone-native "film looks"**
  - iPhone 16 (2024-09-09) introduced next-gen Photographic Styles, which adjust colour, highlights and shadows locally in real time with an intensity slider. — [Apple Newsroom](https://www.apple.com/newsroom/2024/09/apple-introduces-iphone-16-and-iphone-16-plus/)
  - iPhone 18 Pro (announced 2026-09-09) adds **Texture and Grain controls** to Photographic Styles. — [MacRumors, 2026-09-09](https://www.macrumors.com/2026/09/09/texture-and-grain-controls-photographic-styles/)
  - Apple later restricted these controls to iPhone 18 Pro and iPhone Duo, excluding the iPhone 16/17 series. — [MacRumors, 2026-09-22](https://www.macrumors.com/2026/09/22/apple-backtracks-camera-feature-compatibility/)
- **Log/LUT video workflow**
  - Apple Log 2 arrived with iPhone 17 Pro. The Blackmagic Camera app supports Apple Log 2 and 17/33-point 3D LUTs, for monitoring or baked in. — [Blackmagic Camera (App Store)](https://apps.apple.com/us/app/blackmagic-camera/id6449580241); [Blackmagic Design](https://www.blackmagicdesign.com/products/blackmagiccamera)
  - Google Trends' rising "lut màu blackmagic camera" (+1,950%) and "apple log lut" (+100%) are consistent with this (see §1).
- **Local film-look app narratives**
  - JP: BeautyPlus added a film-camera feature on 2025-04-22 with 6 cameras and a 写ルンです-style look. — [BeautyPlus JP](https://www.beautyplus.com/ja/academy/best-film-camera-app)
  - KR: paid filter apps such as filmhwa (₩4,400 one-time) are recommended on Threads. — [Threads post](https://www.threads.com/@holymoly.mong/post/DTh0gMEgZ6E)
  - VN: guides recommend VSCO, NOMO, Dazz, Gudak and OldRoll for "màu film". — [CellphoneS](https://cellphones.com.vn/sforum/5-app-mau-film-cho-ios-hot-nhat-hien-nay)

### Inferences
- The social layer confirms the Google signals.
  - **Digicam/CCD/Y2K** has high engagement per post: #digicam ~19.8K avg views/post and #y2kaesthetic ~19.2K, against #vsco 6.4K and #lightroompresets 8.5K. That suggests under-supplied content demand.
  - **Colour grading / LUT** has a large, video-centric audience (#colorgrading 902M), and tutorials are tied to **CapCut, Lightroom, Premiere and DaVinci**.
  - VSCO-era hashtags are big but legacy.
- Apple adding grain/texture natively, only on iPhone 18 Pro, raises mainstream awareness of "film grain". It also leaves the huge installed base (all Android, iPhone ≤17) needing apps. This is favourable for Android-first film/grain apps.
- The idol/K-pop and Gen Z digicam narrative is strongest in Asia (PH, SG, ID, VN, KR). That fits a Vietnamese team shipping "digicam / CCD / Y2K" looks with Vietnamese and Korean localisation.

### Gaps
- No dated TikTok hashtag counts for 2025–26. Creative Center returned "no permission" and TikTok doesn't render counts server-side, so dated trends for #dazzcam, #fujirecipe, #fujifilmrecipe and #filmgrain are missing.
- No YouTube absolute search volumes; only the Trends YouTube-search index and autocomplete.
- Reddit data comes from a third-party mirror without a date; reddit.com was blocked (HTTP 403).

## 5. Synthesis: which search intents are growing or declining, and which keywords a new film camera / preset / LUT app should target in ASO (Google Play first)

### Takeaway
Target **store-native heads with rising underlying demand**:
- **digicam / ccd camera / y2k camera**
- **retro camera / vintage camera / film camera**
- **dazz cam–style "for android"** intents
- **film grain**
- **fuji recipe / film simulation**
- **LUT camera / LUT editor / color grading**

In Vietnamese: **máy ảnh film, chụp ảnh film, app chụp ảnh film, màu film, filter film, preset, lut màu, máy ảnh ccd / digicam**.

Treat **lightroom presets / preset lightroom / vsco filter / huji** as declining or legacy traffic. Treat the Google Trends "boom" in "film camera app / film filter" as an artefact, not a growth signal.

### Cited Findings (keyword table; each row cites where its evidence comes from)

| keyword (as typed) | market | relative demand (evidence) | 2–5 yr trend | notes for ASO | sources |
|---|---|---|---|---|---|
| digicam | WW, US, ID, PH, SG, DE | GT WW 12-m ≈ 1.8× "dazz cam"; Play suggest in US & VN ("digicam y2k"); iOS hint top | **Strong real rise** (WW 5.96×, US 19×, ID 13.7×, DE 6.9× pre-anomaly); at a 5-yr high Aug–Sep 2026 | High-priority title/short-description term; weak in VN Google (VN users say "máy ảnh ccd") | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=digicam); [Play](https://play.google.com/store/search?q=digicam&c=apps&gl=US) |
| ccd camera / ccd cam | WW (HK, SG, MY, CN), VN, JP, KR | Play suggest "ccd camera", "ccd cam", VN "ccd pro"; iOS hints in US/VN/JP/KR | Mild real rise (1.3× WW); spring-2026 spike inflated | Pair with digicam/y2k; ProCCD dominates (22M installs) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=ccd%20camera); [Play](https://play.google.com/store/search?q=ccd%20camera&c=apps&gl=VN) |
| y2k camera / y2k photo editor | US, WW, JP, KR | Play & iOS suggest "y2k camera", "y2k photo editor"; GT spike Apr–May 2026 | Real rise from a tiny base plus a **fad spike** (Mar–May 2026) | Secondary keyword; fad risk | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=y2k%20camera) |
| dazz cam / dazz camera / apps like dazz cam | WW (MM, PH, ID, VN), BR | ASOTools "dazz cam" 52; GT rising "apps like dazz cam" +100%, VN "cách tải dazz cam cho android" +150% | Real rise to 2024 (WW 1.8×, BR 2.3×); flat/down in VN/ID 2025–26 | Android gap: users search for an Android Dazz. Using "Dazz" in a title is a **trademark risk**; target "dazz"-adjacent terms (retro cam, vintage cam, CCD) and let the description mention "Dazz-style" only if legally safe | [GT](https://trends.google.com/trends/explore?date=today%2012-m&q=dazz%20cam); [ASOTools](https://asotools.io/app-analytics/dazz-cam-keyword-monitoring) |
| film camera | WW, US, VN, ID | ASOTools 37 / KD 18; top Play suggest in all markets | Google flat pre-anomaly (hardware intent); store demand stable | Core head, but top-3 locked by OldRoll/ProCCD/ZANKHANA | [ASOTools](https://asotools.io/app-store-keywords/film-camera); [Play](https://play.google.com/store/search?q=film%20camera&c=apps&gl=US) |
| film camera app | WW, US | Play suggest #2 for "film camera"; GT "best film camera app" | **Not a real rise** (GT 8.3× vs control 2.5×) | Still a valid long-tail for Play; don't read the GT jump as growth | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=film%20camera%20app) |
| retro camera / vintage camera | US, VN, JP | Play suggest (retro camera app/film vintage/offline); iOS hints | Store heads stable; GT "retro/vintage camera app" too sparse and inflated | Include "retro" and "vintage" in title/short description | [Play](https://play.google.com/store/search?q=retro%20camera&c=apps&gl=US) |
| film filter | WW, US, VN | Play suggest (photo editor/app/camera/video) | **Not a real rise** (GT flat → 7.3× jump in Aug-2025); also movie/CapCut intent | Use as secondary; VN "filter film" collides with movie searches | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=film%20filter) |
| film grain / grain camera / grainy | WW, US, VN | Play #1 "Grain" (50K+); VN suggest "grainy 2/3", "grain camera" | Mild real rise (1.33× WW) + spike inflation; iPhone 18 Pro native grain (Sep-2026) raises awareness | Good feature keyword; low competition | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=film%20grain); [MacRumors](https://www.macrumors.com/2026/09/09/texture-and-grain-controls-photographic-styles/) |
| disposable camera | US, WW | ASOTools 41 / KD 20; Play results dominated by event apps (POV 1M+) | Real rise to 2025 (2.8×) | Mixed intent (event sharing); use "disposable camera filter" | [ASOTools](https://asotools.io/app-store-keywords/disposable-camera) |
| fuji recipe(s) / fujifilm recipes / film simulation | US, SG, AU, WW; JP (フィルムシミュレーション, フィルムレシピ) | GT fujifilm recipes WW 5.4× pre-anomaly; iOS hints "fuji recipes", "fujixweekly", "fujistyle"; US suggest "fuji recipes app" | **Real rise** (2.3–5.4×); JP genuine 2026 uptick (2.2–2.6× vs 2024) | Niche with thin Play competition (FujiStyle 10K+). Use "film recipes", "film simulation"; avoid "Fujifilm" as a brand claim | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=fujifilm%20recipes); [Play](https://play.google.com/store/search?q=fuji%20film%20filter&c=apps&gl=US) |
| kodak portra filter / kodak gold filter | WW; VN ("màu film kodak gold 200") | GT below threshold; VN suggest "kodak gold 200"; Fuji X Weekly: Kodak-named recipes most viewed | Flat/negligible as an exact phrase | Use stock names (Portra, Gold 200, Ultramax) inside filter names and description, not as the title | [FXW](https://fujixweekly.com/2026/08/03/top-26-most-popular-fujifilm-recipes-of-2026-so-far-summer-edition/) |
| luts / cube lut / lut app / lut camera | WW, US, JP, KR, DE | GT luts 1.6×, cube lut 2.0×, lut app 3.4× pre-anomaly; YT "lut cube capcut/lightroom" | **Real rise** (video/Log-driven) | "lut" alone is ambiguous in stores (Lutron, Lotte) and in VN Google ("lụt"); use "LUT camera", "3D LUT", ".cube LUT", "color grading". LUT app field is thin | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=cube%20lut); [Play](https://play.google.com/store/search?q=lut&c=apps&gl=US) |
| color grading | WW, US, ID, BR, DE | GT related "color grading app" (37), "color grading ai" | **Real rise** (1.5–4.6×) | Good secondary term for LUT/pro app | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=color%20grading) |
| lightroom presets / preset lightroom / presets for lightroom | WW (BD, LK, NP, PK, PH, IN), VN, ID, BR | ASOTools 44 / 43 / 40; GT 12-m ≈ 1.4× "dazz cam" WW | **Decline** (WW 0.66×, VN 0.52×, ID 0.28×, BR 0.53×) | Still sizeable traffic, but saturated (FLTR 30M, Koloro 40M). The rising sub-intent is "film presets for lightroom" (+90%) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lightroom%20presets); [ASOTools](https://asotools.io/app-store-keywords/lightroom-presets) |
| vsco / vsco filter | WW, VN, ID | ASOTools vsco 63 / KD 42 | **Decline** (WW 0.51×; VN 0.10×; ID 0.16×); BR still 0.82× | Legacy term; avoid (brand) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=vsco) |
| huji / huji cam | WW | GT contaminated (Hebrew Univ.); huji cam 0.44× | **Decline** | Avoid | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=huji%20cam) |
| polaroid filter / polaroid frame | US, VN | Play/iOS suggest "polaroid frame", VN "polaroid dazz cam" | Flat (0.86×) | Secondary; frame feature | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=polaroid%20filter) |
| máy ảnh film | VN | GT VN clean-window volume (see table) above "dazz cam" | Flat, 5-yr peak Aug-2026 | Title/short description in VN listing | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=m%C3%A1y%20%E1%BA%A3nh%20film&geo=VN); [Play](https://play.google.com/store/search?q=m%C3%A1y%20%E1%BA%A3nh%20film&c=apps&gl=VN) |
| ảnh film / màu film | VN | GT stable, high relative volume | Flat/stable (0.88–0.93×) | Use in short description: "màu film Kodak Gold 200, Fuji 400" | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=m%C3%A0u%20film&geo=VN) |
| chụp ảnh film / app chụp ảnh film | VN | Play & iOS suggest; GT sparse | Low Google volume; store-native phrasing | Include both; NOMO/ProCCD rank top | [Play](https://play.google.com/store/search?q=ch%E1%BB%A5p%20%E1%BA%A3nh%20film&c=apps&gl=VN) |
| filter film / chỉnh màu film | VN | iOS hint "chỉnh màu film"; Play "app chỉnh màu" → ảnh đẹp | "app chỉnh màu" declining (0.26×) | Use "chỉnh màu film" rather than generic "app chỉnh màu" | [iOS hint](https://search.itunes.apple.com/WebObjects/MZSearchHints.woa/wa/hints?clientApplication=Software&term=ch%E1%BB%89nh%20m%C3%A0u) |
| preset / preset lightroom | VN | GT VN "preset" flat, "preset lightroom" declining 0.52× | Decline | Use "preset màu film", "preset fujifilm" (VN suggest "preset lightroom fujifilm free") | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=preset%20lightroom&geo=VN) |
| công thức màu | VN | GT declining 0.39×; ambiguous (hair dye) | Decline | Use only as "công thức màu fujifilm" | [suggest](https://suggestqueries.google.com/complete/search?client=firefox&hl=vi&gl=vn&q=c%C3%B4ng%20th%E1%BB%A9c%20m%C3%A0u) |
| lut màu | VN | GT rising from a small base (4.2×); rising "lut màu blackmagic camera" +1,950% | **Real rise** (small) | Good VN term for a LUT app ("lut màu cho điện thoại", "lut màu blackmagic") | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lut%20m%C3%A0u&geo=VN) |
| フィルムカメラ アプリ / フィルムカメラ風 / 写ルンです風 / デジカメ風 | JP | Play/iOS suggest; GT "フィルムカメラ アプリ" declining 0.24× | Google decline, store-native phrasing stable | JP listing keywords; "デジカメ風" matches the digicam trend | [Play JP](https://play.google.com/store/search?q=%E3%83%95%E3%82%A3%E3%83%AB%E3%83%A0%E3%82%AB%E3%83%A1%E3%83%A9&c=apps&gl=JP) |
| フィルムシミュレーション / フィルムレシピ | JP | GT 2026 uptick (2.2–2.6× vs 2024) | Real 2026 rise | For a recipe/simulation app | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=%E3%83%95%E3%82%A3%E3%83%AB%E3%83%A0%E3%82%B7%E3%83%9F%E3%83%A5%E3%83%AC%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3&geo=JP) |
| 필름카메라 / 필름카메라 어플 / 필카 / 디카 필터 | KR | Play suggest "필름카메라어플", "디카 필터", "디카앱"; GT 필름카메라 flat | Flat on Google (Naver not measured) | KR listing keywords; digicam-look idol trend | [Play KR](https://play.google.com/store/search?q=%ED%95%84%EB%A6%84%EC%B9%B4%EB%A9%94%EB%9D%BC&c=apps&gl=KR) |
| kamera film / kamera jadul / preset lightroom | ID | GT kamera jadul 2.1× vs 2024; preset lightroom 0.28× | kamera jadul up; presets down | ID listing: "kamera jadul", "kamera film vintage" | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=kamera%20jadul&geo=ID) |
| filtro de filme / câmera vintage | BR | GT flat (1.09×); dazz cam BR 2.3× | Flat | BR listing: "câmera vintage", "film cam" | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=filtro%20de%20filme&geo=BR) |
| raw camera / manual camera | US | FilCam ranks #24 / #29 | n/a | Only terms where FilCam currently ranks | [Play](https://play.google.com/store/search?q=raw%20camera&c=apps&gl=US) |

### Inferences
- **Growing intents to build around:**
  1. Digicam/CCD/Y2K looks (strongest real growth globally and in SE Asia).
  2. Film recipes / film simulation (Fuji-style), where the Play niche is thin.
  3. LUT / colour-grading tools for phone video (Log workflows), where the Play LUT field is weak and stale.
  4. Android demand for Dazz-like retro cameras.
- **Declining intents (don't lead with them):** VSCO-style filters, "lightroom presets / preset lightroom" and generic VN "app chỉnh màu / công thức màu". Huji-era disposable-camera apps are also fading; the "disposable camera" traffic now leans to event apps.
- **Suggested Google Play title / short-description stacks.** These are inferences for the team to validate with a paid ASO tool.
  - Film/digicam camera app: "Retro Film Camera – Digicam, CCD, Y2K" + short description "vintage camera, film grain, film filter, disposable camera look".
  - VN listing: "Máy ảnh film – Digicam CCD, màu film" + "app chụp ảnh film, filter film, Kodak Gold 200, Fuji 400".
  - Preset/recipe app: "Film Recipes & Presets – film simulation, film filter" (VN: "Preset màu film, công thức màu Fujifilm").
  - LUT app: "LUT Camera & Editor – 3D LUT, .cube, color grading" (VN: "lut màu, chỉnh màu film cho video").
- **Keywords whose Google Trends rise is spike-inflated (not above the control), so they should not be cited as "trending":** film camera app, film filter, film filter app, photo filter app, retro camera app, vintage camera app, and the post-Aug-2025 part of film grain, film simulation, lut app and y2k camera.
- Filmode currently has **no generic-term visibility** (outside the top ~30 for all film terms; brand not measurable on Google). Any ASO plan starts from zero ranking equity. FilCam's only generic foothold is "raw camera" / "manual camera".

### Gaps
- There are no absolute keyword volumes (Google Keyword Planner, AppTweak, Mobile Action, Sensor Tower keyword tools and Apple Search Ads are all login-gated). The "relative demand" column mixes Google Trends ratios, store autocomplete presence and undated ASOTools indices. It should be validated with one paid ASO tool for Google Play US and VN before finalising metadata.
- Trademark and brand-keyword risk ("Dazz", "Fujifilm", "Kodak", "VSCO", "Lightroom") was not researched. A legal and Play-policy check is needed before using them in metadata.
