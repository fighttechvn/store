# User sentiment, unmet needs and pain points: mobile film-camera, filter/preset and LUT apps (2024–2026)

> Research date: 2026-09-27. Researcher notes for the report writer.
>
> **Primary dataset (collected for this note).** I pulled **~26,800 Google Play review rows** with the open-source `google-play-scraper` (newest plus most-relevant sorts, en-US and vi-VN locales) for 25 listings. That count includes duplicates across sorts. I deduplicated them and kept reviews dated from 2024-01-01 to 2026-09-26, which left **~13,900 unique reviews** across the 22 listings that had enough to analyse. I then tagged every 1–2★ and 4–5★ review with keyword/regex theme dictionaries in English and Vietnamese.
> - Percentages below mean "% of that app's 1–2★ reviews (2024+) that mention the theme", unless the text says otherwise. Keyword tagging is approximate: one review can hit several themes, sarcasm and misspellings are missed, and "video" is trivially high for video apps.
> - Newest-sorted samples are weighted toward mid-2025 to 2026.
> - App Store (iOS) customer-review RSS feeds returned **empty for most apps** in Sept 2026. Only Lapse (US, 150 reviews), Tezza (US, 50), VSCO (VN, 50), Lightroom (VN, 50) and 1998 Cam (VN, 50) came back. For Dazz, Hipstamatic, RNI, Dehancer and Blackmagic iOS I used the ~10 reviews that the apps.apple.com "see all reviews" pages show. That page does not print the year for recent reviews.
> - Reddit blocked both direct fetches and the JSON API (HTTP 403). Voz and Tinhte thread pages also returned 403. Community evidence therefore comes from search snippets, articles and store reviews, and these gaps are flagged below.
>
> Store pages cited as sources (the review text quoted is from the listing's public reviews):
> - Kapi Cam https://play.google.com/store/apps/details?id=com.sensemobile.action
> - OldRoll https://play.google.com/store/apps/details?id=com.accordion.analogcam
> - ProCCD https://play.google.com/store/apps/details?id=com.cerdillac.proccd
> - Dazzil https://play.google.com/store/apps/details?id=com.camerafilm.lofiretro
> - Huji https://play.google.com/store/apps/details?id=kr.co.manhole.hujicam
> - Kuji https://play.google.com/store/apps/details?id=com.ginnypix.kujicam
> - NOMO https://play.google.com/store/apps/details?id=com.blink.academy.nomopro
> - FIMO https://play.google.com/store/apps/details?id=com.fimo.camera
> - 1998 Cam https://play.google.com/store/apps/details?id=com.aaai.cam1998
> - VSCO https://play.google.com/store/apps/details?id=com.vsco.cam
> - Lightroom https://play.google.com/store/apps/details?id=com.adobe.lrmobile
> - Polarr https://play.google.com/store/apps/details?id=photo.editor.polarr
> - Tezza https://play.google.com/store/apps/details?id=org.tezza
> - Hypic https://play.google.com/store/apps/details?id=com.xt.retouchoversea
> - CapCut https://play.google.com/store/apps/details?id=com.lemon.lvoverseas
> - VN https://play.google.com/store/apps/details?id=com.frontrow.vlog
> - Blackmagic Camera https://play.google.com/store/apps/details?id=com.blackmagicdesign.android.blackmagiccam
> - mcpro24fps https://play.google.com/store/apps/details?id=lv.mcprotector.mcpro24fps and the demo at https://play.google.com/store/apps/details?id=lv.mcprotector.mcpro24fps.demo
> - POV https://play.google.com/store/apps/details?id=com.untitledshows.pov
> - Retro https://play.google.com/store/apps/details?id=io.lonepalm.retro
> - Filmode https://play.google.com/store/apps/details?id=app.filmode
> - FilCam https://play.google.com/store/apps/details?id=app.filmode.filcam
> - Lapse iOS reviews RSS https://itunes.apple.com/us/rss/customerreviews/id=1636699256/sortBy=mostRecent/json

---

## 1. Per-app praise and complaint themes (what users love / what earns 1-star reviews)

### Takeaway
Across every category, the #1 cause of 1–2★ reviews is **monetization change**, meaning features that "used to be free" moving behind a paywall or subscription. It is 33% of film-camera-app negatives, 43% of photo-editor negatives and 29% of CapCut/VN negatives. Crashes and bugs come second, and ads are third for the free film-cam apps. Complaints the brief anticipated (weekly subscriptions, watermark, low resolution, fake look, skin tones) are **rare** in mass-market reviews, each under 3%. What users love is a one-tap nostalgic "real camera" look, a usable free tier, and (on Android) iPhone-style features such as Live Photo and 0.5× lens support. Pro video apps (Blackmagic, mcpro24fps) are the exception: their pain is **device-specific breakage**, not price.

### Cited Findings

**Category aggregates (Google Play, 2024-01 → 2026-09, my tagging)**

| Group (apps) | Reviews | 1–2★ share | Top complaint themes (% of 1–2★) |
|---|---|---|---|
| Film-camera apps (Kapi, OldRoll, ProCCD, Dazzil, Huji, Kuji, NOMO, FIMO) | 4,825 | 1,096 (23%) | paywall/subscription 33% · ads 16% · crash/bug 10% · login 4% · "update broke it" 3% · lost purchase/restore 3% · save fail 3% · quality/resolution 3% · pay-per-camera 2% |
| Photo editors (VSCO, Lightroom, Polarr, Tezza, Hypic) | 4,336 | 2,187 (50%) | paywall 43% · crash 9% · login/account 7% · lag 3% · update broke 3% · ads 3% · AI 2% |
| Video editors (CapCut, VN) | 2,509 | 753 (30%) | paywall 29% · crash 15% · lag 13% · ads 9% · login 5% · AI 5% |
| Pro video cams (Blackmagic, mcpro24fps + demo) | 1,511 | 375 (25%) | **names a specific phone brand 29%** · crash 20% · lens access 9% · LUT 8% · manual controls 5% |
| Social/event (Retro, POV) | 635 | 201 (32%) | **login/account 23%** · paywall 16% · crash 10% · save 4% |

Source: Play listings above.

**Film-camera apps**

- **Kapi Cam** (Play 4.58★, 66,388 ratings, 10M+, released 2024-01-23; "Y2K & CCD"). n=961 (94 in Vietnamese). 1–2★ = 24%.
  - Negatives: paywall 47%, ads 11%, quality 7%, video 5%.
  - 28 reviews use "was free → now paid" wording, 11 complain about watching ads to save, and 57 mention Live Photo.
  - Praise: "Probably one of the best out of all the digicams… It also supports my 0.5x camera even on live photo with flash (crazy!!)" (5★, 2025-10-28, 519 helpful).
  - Churn: "earlier it was free… Nevermind!! …the prices are ridiculous… they got greedy" (2★, 2025-12-06, 319 helpful).
  - Churn: "you have to watch 3 whole ads to get just a single picture on a premium filter" (2★, 2026-04-03).
  - Churn: "no flash for front camera no more, even favouriting a camera now is premium, absolutely unnecessary ai features" (2★, 2026-09-17).
  - Vietnamese: "lúc chưa chụp nhìn ảnh đẹp lắm mà chụp thì nó xấu quắc… giảm chất lượng ảnh" ("preview looks great but the captured photo looks ugly, like quality is reduced", 2★, 2026-05-28).
  - Source: [Play – Kapi](https://play.google.com/store/apps/details?id=com.sensemobile.action)
- **OldRoll** (4.27★, 213,230 ratings, 10M+). n=1,119 (265 in Vietnamese). 1–2★ = 17%.
  - Negatives: paywall 49%, lost purchase 4%, ads 3%.
  - 39 reviews mention lifetime or one-time purchase. They are mixed: some are satisfied buyers, others lost access.
  - Praise: "gives you that nostalgic, retro effects & you can even mess around with your own editing" (5★, 2025-09-13, 411 helpful).
  - Praise: "Not all the cameras are free to use! So what?… you don't need to do long editing" (4★, 2024-02-20, 234 helpful).
  - Pain: "I bought the life-time subscription… I can't access the pro version services anymore" (1★, 2024-06-16).
  - Pain: "₹850 has been deducted… yearly subscription that had a 3 days free trial" (1★, 2024-01-31).
  - Shutter-lag anecdote: "when you want to click a photo suddenly like photo of a bird… before it flew" (4★, 2024-11-07, 142 helpful).
  - Vietnamese users objected to a "Chinese New Year" label: "không phải Chinese New Year mà là Lunar New Year" ("it's Lunar New Year, not Chinese New Year", 1★, 2026-02-16).
  - Source: [Play – OldRoll](https://play.google.com/store/apps/details?id=com.accordion.analogcam)
- **ProCCD** (4.83★, 198,138 ratings, 10M+). n=1,096. Only 9% are 1–2★.
  - Negatives: paywall 43%, crash 7%, save failures 7%, per-camera purchases 5%, lost purchase 5%.
  - 102 reviews mention **Live Photo**, the highest count in the dataset.
  - Praise: "exactly what I was looking for to get that nostalgic, early 2000s digital camera aesthetic" (5★, 2025-06-07, 523 helpful).
  - Praise: "better than my system camera… redmi note 10s… when it comes to filters they failed" (5★, 2025-03-17).
  - Churn: "you can't get two minutes to explore the app without being hounded to buy something" (1★, 2025-02-25).
  - Churn: "'BUY PREMIUM NOW' popups… feels like a mascot horror game… playing on my nostalgia" (1★, 2026-07-09).
  - Churn: "each filter has to be purchased separately" (1★, 2024-09-06).
  - Users suspect review manipulation: "Its either all the reviews are fake/paid" (1★, 2024-08-10, 104 helpful). The rating histogram shows 178k 5★ out of 198k.
  - Source: [Play – ProCCD](https://play.google.com/store/apps/details?id=com.cerdillac.proccd)
- **FIMO** (3.09★, 11,738 ratings, 5M+). n=187. **58% are 1–2★**, with paywall in 52% of them.
  - Around 2025 it switched from per-film-roll purchases to a subscription: "they changed to a subscription model… I've bought all the films that I liked" (2★, 2025-08-25, 100 helpful).
  - Vietnamese legacy buyers were angry: "những người cũ đã mua lẻ trước đó muốn dùng gói pro lại phải trả phí cho toàn bộ" ("old users who bought rolls individually must pay for everything again to get Pro", 1★, 2025-03-19, 67 helpful).
  - Offline: "some of the rolls take too long to download or don't work properly if you're not online; it doesn't let you import images" (2★, 2025-06-07).
  - Lost purchase: "I payed $29.99 for the one year of Pro and I'm still stuck in the free mode" (1★, 2026-08-26).
  - Source: [Play – FIMO](https://play.google.com/store/apps/details?id=com.fimo.camera)
- **Huji Cam** (3.59★, 190,485 ratings, 10M+). n=167. Negatives: crash 32%, paywall 28% (mostly failed purchases), flash bugs 11%, lost purchase 11%.
  - Praise: "I like the fact that the effects are random, close to emulating old cameras instead of having you choose" (2★, 2026-03-23).
  - Flash: "can't capture a photo in dark places because all it shows is black even with the flash on" (1★, 2026-02-11).
  - Flash: "Flash not working in first click… SAMSUNG S24" (1★, 2026-02-05).
  - Source: [Play – Huji](https://play.google.com/store/apps/details?id=kr.co.manhole.hujicam)
- **Kuji Cam** (3.97★, 179,847 ratings). Negatives: ads 28%, paywall 17%, crash 17%.
  - "It runs an ad on startup and then immediately shuts down" (1★, 2024-03-16).
  - "doesn't work on my Redmi 13c" (1★, 2024-03-17).
  - Source: [Play – Kuji](https://play.google.com/store/apps/details?id=com.ginnypix.kujicam)
- **NOMO CAM** (3.73★, 13,555 ratings, 5M+; last updated 2026-04). Negatives: **login/account 26%**, paywall 15%, crash 11%, lost purchase 8%.
  - "took away my PRO functions and demanded to subscribe and pay for pro again" (1★, 2024-11-09).
  - Vietnamese: "đăng nhập sđt nhưng không được, sau đó hàng loạt số spam gửi tin nhắn" ("couldn't log in with my phone number, then a flood of spam SMS", 2★, 2024-07-12).
  - "doesn't seem to use the android camera hdr features. Seems wide angle and super wide angle are the wrong way around in Pixel phones" (4★, 2026-01-15).
  - Source: [Play – NOMO](https://play.google.com/store/apps/details?id=com.blink.academy.nomopro)
- **Dazzil** (4.14★, 86k ratings, a Dazz-like app with ads). Negatives: **ads 39%**, crash 15%.
  - "it even took me out of editing a picture to show an ad… the edits were gone" (1★, 2025-03-10).
  - Vietnamese crash-on-open reviews: "vào cứ bị văng ra" ("keeps crashing when I open it", 1★, 2024-10-19, 126 helpful).
  - Source: [Play – Dazzil](https://play.google.com/store/apps/details?id=com.camerafilm.lofiretro)
- **Dazz Cam.** The official app has a very strong iOS reputation (4.8★, 115K ratings): "Worth 5 stars just because you can actually buy the app!" (5★, Apr 15, year not shown). [App Store – Dazz](https://apps.apple.com/us/app/1422471180?see-all=reviews&platform=iphone)
  - Vietnamese guides describe Dazz as optimised for iPhone. [GearVN](https://gearvn.com/blogs/thu-thuat-giai-dap/dazz-cam)
  - On Play, the listings titled "Dazz Cam" in Sept 2026 come from other developers:
    - "MA CLO APPS", released 2026-08-30, 3.5★. 76% of its 58 reviews are 1–2★, for example "why the camera is always upside down? I've subscribed…" (2★, 2026-09-18). [Play](https://play.google.com/store/apps/details?id=com.vintage.camera.pro)
    - "Monova Tech", released 2026-07-27, 50k+ installs: "grain is static, just an overlaid image" (1★, 2026-09-06). [Play](https://play.google.com/store/apps/details?id=app.grain.camera)
- **1998 Cam, Android.** It was relisted on 2026-04-21, and previous buyers were asked to pay again. 6 of its 11 negative reviews are about this:
  - "I already paid for the lifetime membership before it was delisted and now it's telling me I have to buy it again" (1★, 2026-09-12).
  - "i paid for the pro version… back in 2021. now i dont own it anymore because they switched their model to subscription" (1★, 2026-07-23).
  - Source: [Play – 1998 Cam](https://play.google.com/store/apps/details?id=com.aaai.cam1998)
- **Hipstamatic** (iOS 4.6★, 2.8K ratings): "Paid 4 App + Almost All Hipstapaks Now U Want a Paid Subscription?!" (2★, 2024-07-05). Also "Doesn't focus… Will not focus or meter light correctly on iPhone 13" (1★, 06/28, year not shown). [App Store – Hipstamatic](https://apps.apple.com/us/app/1450672436?see-all=reviews&platform=iphone)

**Preset / filter editors**

- **VSCO** (Play 3.62★, 1.33M ratings, 100M+). n=929. **67% are 1–2★**. Negatives: paywall 29%, **login/account 21%**, crash 12%, video 8%. 34 reviews mention cancelling or being charged.
  - "Whenever I export photos… they show as a black image" (1★, 2024-11-20, 576 helpful).
  - "Everything is behind a paywall, including previously owned presets. No cross-platform account compatibility" (1★, 2025-12-28).
  - "Used to be $20… a year… Now it costs double" (1★, 2025-07-01).
  - Vietnamese: "tải để slow mà vào mới biết slow vid mất tiền" ("downloaded it for slow-mo, only to find slow-mo video is now paid", 1★, 2025-09-27, 61 helpful).
  - A Vietnamese iOS review asked for Vietnamese UI: "Kh có tiếng việt bất tiện" (1★, 2026-05-03). [iOS RSS VN](https://itunes.apple.com/vn/rss/customerreviews/id=588013838/sortBy=mostRecent/json)
  - A Vietnamese iOS review asked for recipe sharing: "Mong phần công thức có thể lưu lại dưới dạng mã QR" ("wish recipes could be saved as a QR code", 5★, 2025-08-25). Same source.
  - Current pricing, per a third-party pricing summary that I did not verify on VSCO's own page: Plus $29.99/yr, Pro $59.99/yr. [checkthat.ai](https://checkthat.ai/brands/vsco/pricing), [VSCO plans](https://www.vsco.co/subscribe/plans)
  - Source: [Play – VSCO](https://play.google.com/store/apps/details?id=com.vsco.cam)
- **Lightroom Mobile** (4.47★, 3.66M ratings). n=1,048. 1–2★ = 32%. Negatives: paywall 33%, crash 18%, **"update broke it" 10%**, AI 7%.
  - "a new update has made editing almost impossible if cropping is needed" (2★, 2026-08-09, **2,858 helpful**).
  - "Stop pushing features 'AI' features and let people customize their own art!" (1★, 2026-08-11).
  - "forgot to cancel… there is an 89.00$ cancelation fee" (1★, 2025-11-02, 659 helpful).
  - Consistency praise: "I can copy my edits for certain photos within a group, so they all look relatively uniform" (4★, 2024-01-10, 1,103 helpful).
  - Vietnamese: "không có màu profile Chép theo mẫu của Canon r6 mark ii" ("no colour profile copying the Canon R6 Mark II look", 1★, 2026-02-07).
  - Source: [Play – Lightroom](https://play.google.com/store/apps/details?id=com.adobe.lrmobile)
- **Polarr** (3.85★, 146k ratings). Praise mentions filters in 21% of 4–5★ reviews. Negatives: paywall 40%, ads 8%.
  - "have to watch ads just to save our photos" (1★, 2024-07-04).
  - "only being allowed to save three filters" (1★, 2025-01-29, 175 helpful).
  - Source: [Play – Polarr](https://play.google.com/store/apps/details?id=photo.editor.polarr)
- **Tezza** (3.66★ Play). 50% are 1–2★. Negatives: paywall 38%, crash 16%.
  - "android version is behind… we never were so behind apple users" (2★, 2024-10-20, 101 helpful). [Play – Tezza](https://play.google.com/store/apps/details?id=org.tezza)
  - iOS US, May–Sep 2026: 19 of 50 reviews are 1–2★, for example "You want me to pay $40 or $60 to edit my photo with a filter on top?" (2★, 2026-09-12). [iOS RSS](https://itunes.apple.com/us/rss/customerreviews/id=1393061654/sortBy=mostRecent/json)
- **Hypic** (ByteDance; 3.09★, 262k ratings, 100M+). **81% are 1–2★**, and paywall appears in 56% of those. 71 reviews use "was free → paid" wording.
  - "seemed completely free… I couldn't even save my work unless I subscribed to VIP" (4★, 2025-04-12, **10,470 helpful**).
  - "at least use ads if you still want people to try" (1★, 2026-05-23, 628 helpful).
  - Vietnamese: "không biết app có nghĩ đến những học sinh, sinh viên" ("does the app not think about students?", 1★, 2026-09-09).
  - Source: [Play – Hypic](https://play.google.com/store/apps/details?id=com.xt.retouchoversea)
- **RNI Films** (iOS 4.8★, 9.1K ratings): "HSL adjustments barely move the needle" (3★, Apr 24, year not shown). Also "want customizable date stamp formatting… and B&W grain options" (5★, 2025-04-09). [App Store – RNI](https://apps.apple.com/us/app/1017098672?see-all=reviews&platform=iphone)
- **Dehancer** (iOS 4.3★, 430 ratings):
  - "Overall the app performs amazingly well" but "lacks batch editing and lifetime purchase option" (4★, Apr 5, year not shown).
  - "The emulations are top notch… but the execution… is clunky" (3★, May 8).
  - "Probably the best film emulation app around" despite export frame-rate issues (4★, 2024-06-21).
  - Source: [App Store – Dehancer](https://apps.apple.com/us/app/6443648413?see-all=reviews&platform=iphone)

**Video editors used for LUTs and filters**

- **CapCut** (3.56★, 13.0M ratings, 1B+). Negatives: paywall 33%, crash 14%, lag 11%, ads 9%.
  - "effects that was free before were also moved to the PRO" (1★, 2025-04-11, 12,240 helpful).
  - "extracting audio, fliters, transitions… that used to be free are now limited" (1★, 2025-08-05, 6,653 helpful).
  - Vietnamese: "quảng cáo vừa nhiều vừa bắt trả phí đủ thứ" ("tons of ads and they make you pay for everything", 1★, 2026-09-15).
  - Source: [Play – CapCut](https://play.google.com/store/apps/details?id=com.lemon.lvoverseas)
- **VN** (4.71★, 5.5M ratings). Only 10% are 1–2★. Praise: easy 12%, free 11%.
  - "completely free with no watermark, which is rare these days" (5★, 2026-08-31).
  - "Colour grading needs improvement" (4★, 2026-07-15, 3,883 helpful).
  - Vietnamese: "riết chán thằng Cúc Cúc [CapCut] làm giá… ngay cả output mà nó cũng giới hạn chất lượng" ("fed up with CapCut's pricing… it even limits output quality", 5★, 2026-01-03).
  - Source: [Play – VN](https://play.google.com/store/apps/details?id=com.frontrow.vlog)

**Pro video / LUT cameras** (see Section 3 for detail)

- **Blackmagic Camera, Android** (4.59★, 14,570 ratings, 1M+). 28% are 1–2★, and 40% of those name a phone brand. Across all ratings, 72 reviews mention LUTs and 65 mention lenses.
  - Praise: "It features the same interface as Blackmagic's expensive, high-end film cameras" (5★, 2026-01-06, 645 helpful). [Play – Blackmagic](https://play.google.com/store/apps/details?id=com.blackmagicdesign.android.blackmagiccam)
- **mcpro24fps** (4.57★). Praise: "10 bit LOG HLG2 Rec.2020 at 240Mbps… Pixel 9 Pro" (5★, 2025-09-15). [Play – mcpro24fps](https://play.google.com/store/apps/details?id=lv.mcprotector.mcpro24fps)
  - Its demo (4.22★) collects churn: "This so called 'demo' does literally nothing… you cannot make any recordings" (1★, 2025-12-24). [Play – demo](https://play.google.com/store/apps/details?id=lv.mcprotector.mcpro24fps.demo)

**Reference apps (the team's own)**

- **Filmode Vibe** (`app.filmode`): released 2026-07-22, 50+ installs, IAP $2.99–$29.99, no ads. [Play](https://play.google.com/store/apps/details?id=app.filmode)
- **FilCam** (`app.filmode.filcam`): released 2026-09-04, 100+ installs, IAP $0.99–$9.99. Its listing says "No ads and no watermark, ever. Manual controls, RAW DNG and film LUTs are free". [Play](https://play.google.com/store/apps/details?id=app.filmode.filcam)
- iOS Filmode (id 6791145420) has 0 ratings.
- Only two unique reviews each could be retrieved. Both praise live LUT preview and manual controls, and **both apps have a 2026-09-08 "cannot save picture/error" report**:
  - "whenever I captured an image, I cannot save it, it says error" (Filmode 5★, 2026-09-08)
  - "I cannot save a picture :'(" (FilCam 5★, 2026-09-08)
  - These are anecdotes, not a pattern.

### Inferences
- The strongest signal for churn and 1★ reviews is **retroactive paywalling**: taking away something free or previously bought. Launching with a subscription is not the main trigger. Users accept a "some cameras are paid" model when the free tier is genuinely usable (OldRoll and Kapi 4–5★ reviews say so explicitly).
- Honouring legacy purchases, and not changing tiers after launch, is a differentiator. FIMO, 1998 Cam, NOMO, Hipstamatic, VSCO and OldRoll all drew "pay again" anger.
- Pay-per-camera IAP is not itself hated (2% of negatives). What users hate is **moving a favourite camera** (the Kapi "Nokia"/S5 and ProCCD "2000s phone" cases) into the paid tier.
- Brief hypotheses that did **not** show up at scale in Play reviews:
  - weekly subscriptions (≈0 mentions in these apps)
  - watermark (under 1%, apart from POV)
  - low export resolution (about 3%)
  - "fake/over-processed" look (under 2%)
  - skin tones (under 2%)

  These may still matter to enthusiasts, whose voice is on Reddit and YouTube, but they are not what drives mass-market ratings.

### Gaps
- iOS review volume is thin because Apple's RSS returned empty for most apps. I have no systematic iOS counts for Dazz, Huji, NOMO, Hipstamatic, RNI, Dehancer, Blackmagic iOS or CapCut.
- There are no official Android listings for Dazz Cam or Hipstamatic. The 1998 Cam and "Dazz Cam" Android listings have dubious provenance, so their reviews partly reflect clone quality.
- I did not scrape Google Play's "Vietnam most relevant" reviews for apps with few Vietnamese reviews (Huji, Kuji, Tezza).

---

## 2. What makes users pay vs. churn (monetization sentiment)

### Takeaway
Users pay for:
- **ownership**: one-time or lifetime purchases, praised in Dazz iOS, Hipstamatic and OldRoll reviews
- **a clearly better look they have already tried**
- **pro video capability** (mcpro24fps is paid and rated 4.57★)

They churn over:
- bait-and-switch ("was free")
- hard save/export walls
- forced multi-ad unlocks
- billing and cancellation traps
- lost purchases after reinstall or relisting

Students (explicitly in Vietnamese reviews) will accept one rewarded ad per save but not a subscription.

### Cited Findings
- **"Was free → now paid"** wording appears in 156 reviews across the dataset: CapCut 23, Hypic 71, Kapi 28, OldRoll 8, VSCO 6, ProCCD 5. Some are among the most-upvoted reviews on Play; one CapCut review has 12,240 helpful votes. [Play – CapCut](https://play.google.com/store/apps/details?id=com.lemon.lvoverseas), [Play – Hypic](https://play.google.com/store/apps/details?id=com.xt.retouchoversea), [Play – Kapi](https://play.google.com/store/apps/details?id=com.sensemobile.action)
- **One-time / lifetime** purchases come up in 110 reviews, as requests or as praise:
  - OldRoll 39, ProCCD 15, FIMO 10.
  - "Worth 5 stars just because you can actually buy the app!" (Dazz iOS, 5★). [App Store – Dazz](https://apps.apple.com/us/app/1422471180?see-all=reviews&platform=iphone)
  - "$30 lifetime membership was no-brainer" (Hipstamatic, 5★, 2020). [App Store – Hipstamatic](https://apps.apple.com/us/app/1450672436?see-all=reviews&platform=iphone)
  - Dehancer users ask for a "lifetime purchase option". [App Store – Dehancer](https://apps.apple.com/us/app/6443648413?see-all=reviews&platform=iphone)
  - "The subscription-only pricing model is a major downside… less appealing for casual users" (Lightroom 3★, 2024-12-03). [Play – Lightroom](https://play.google.com/store/apps/details?id=com.adobe.lrmobile)
- **Ads to save** (27 reviews): users tolerate one ad but not several.
  - "watch an ad just to save a one photo" (Kapi 4★, 2026-02-03).
  - "watch 3 whole ads to get just a single picture" (Kapi 2★, 2026-04-03).
  - "I genuinely would rather watch 40 ads and be able to use the app" (Hypic 1★, 2026-06-28).
  - Vietnamese: "Học sinh, sinh viên Xem quảng cáo thì được Chứ trả phí thì chịu rồi" ("Students: watching ads is fine, paying we can't", Polarr 4★, 2026-03-14).
  - Sources: [Play – Kapi](https://play.google.com/store/apps/details?id=com.sensemobile.action), [Play – Hypic](https://play.google.com/store/apps/details?id=com.xt.retouchoversea), [Play – Polarr](https://play.google.com/store/apps/details?id=photo.editor.polarr)
- **Billing, trial and cancellation traps** (cancel/charged/refund mentions): Kapi 41, CapCut 40, VSCO 34, Hypic 19, OldRoll 17, Lightroom 15.
  - Lightroom's "$89.00 cancelation fee" review has 659 helpful votes.
  - Vietnamese: "đã huỷ nhưng vẫn trừ tiền… không hoàn tiền" ("cancelled but was still charged… no refund", Lightroom iOS VN, 1★, 2026-03-03). [iOS RSS VN – Lightroom](https://itunes.apple.com/vn/rss/customerreviews/id=878783582/sortBy=mostRecent/json)
  - Vietnamese: "Đăng kí gói dùng thử miễn phí và bị gia hạn trừ tiền vô cớ" ("signed up for the free trial and got auto-renewed and charged", NOMO 1★, 2026-06-09). [Play – NOMO](https://play.google.com/store/apps/details?id=com.blink.academy.nomopro)
- **Lost purchases, restore and relisting** (35 reviews in the film-cam group, plus clusters in 1998 Cam and FIMO):
  - "They said I can use the app on 3 devices but it couldn't restore the purchases even on just one" (NOMO 1★, 2025-05-27). [Play – NOMO](https://play.google.com/store/apps/details?id=com.blink.academy.nomopro)
  - "purchased the annual subscription, but the camera options are not downloadable" (ProCCD 1★, 2025-11-18). [Play – ProCCD](https://play.google.com/store/apps/details?id=com.cerdillac.proccd)
- **Hard paywall before a user has seen value:**
  - "Why does this app even exist if I need to pay for it to even open" (Tezza 1★, 2024-02-28). [Play – Tezza](https://play.google.com/store/apps/details?id=org.tezza)
  - "LET ME SEE THE APP FIRST TO DECIDE IF I WANT TO PAY" (ProCCD 1★, 2025-02-25). [Play – ProCCD](https://play.google.com/store/apps/details?id=com.cerdillac.proccd)
- **Free and generous wins trust.**
  - VN is rated 4.71★ with 10% 1–2★, and users praise "free with no watermark". [Play – VN](https://play.google.com/store/apps/details?id=com.frontrow.vlog)
  - Blackmagic Camera: "Awesome software completely free… Nothing shady about the free software offering" (iOS 5★). [App Store – Blackmagic](https://apps.apple.com/us/app/6449580241?see-all=reviews&platform=iphone)
- **Price points seen by reviewers:**
  - Prequel £4.99/week; Dazz Pro £4.99/yr. The winner of The Tab's test was DAZE CAM at **£2.99 one-off for unlimited imports** (3 free), rated "Probably as good as imitating disposables on your phone can get". [The Tab, Francesca Eke, 2025-04-22](https://thetab.com/2025/04/22/right-i-tested-apps-that-make-your-photos-look-like-film-to-see-which-actually-work)
  - Tezza iOS user: "$40 or $60 to edit my photo with a filter" (2026-09-12). [iOS RSS – Tezza](https://itunes.apple.com/us/rss/customerreviews/id=1393061654/sortBy=mostRecent/json)
  - POV: "$70 so the 200 some guests… can take 25 photos" (1★, 2024-01-25, 122 helpful). [Play – POV](https://play.google.com/store/apps/details?id=com.untitledshows.pov)

### Inferences
- A pricing design that avoids the top churn triggers would have these parts:
  - a generous free tier that never shrinks
  - a lifetime unlock alongside the subscription
  - purchases restorable without an account, via Play/App Store receipts
  - at most one rewarded ad per premium save
  - transparent trial terms
- This matches the brief's own "no ads, no watermark" positioning for FilCam.
- In Vietnam, price sensitivity among students is explicit (the Hypic, Polarr and CapCut Vietnamese reviews). Localized low price points, one rewarded ad per save and one-time "mua đứt" (buy outright) purchases fit that market.

### Gaps
- I found no public conversion or retention data for these apps. Willingness to pay is inferred from review text only.
- I did not verify actual current Dazz, Kapi or OldRoll price tables. The Play metadata only gives per-item ranges (Kapi $1.98–$89.99, OldRoll $0.49–$94.99, ProCCD $0.29–$23.99).

---

## 3. Android-specific pain: third-party camera quality and device fragmentation

### Takeaway
Structurally, third-party Android camera apps can only reach what each phone maker exposes through Camera2/CameraX. Lenses, night/HDR processing, stabilization and Log profiles vary by model, so pro apps generate brand-specific 1★ reviews: 29% of pro-video negatives name a brand, led by Samsung, Xiaomi and Pixel. Casual film-cam users complain far less about image quality. They care about **iPhone-parity features on Android**, chiefly Live Photo, 0.5× ultrawide and flash, and about **basic reliability** (orientation, flash, crashes).

### Cited Findings
- **Structural cause.** Android Police explains why third-party Android camera apps underperform (Tyler Lacoma & Taylor Kerns, 2023-05-20; older than the 2024 window but still the standard explanation):
  - "Support for Camera2, CameraX, and Camera HAL isn't mandatory… OEMs aren't required to expose camera features."
  - Third-party apps "often miss important support for things like a new telephoto lens."
  - Moment's co-founder cited lacking "engineering bandwidth" to support Android.
  - Source: [Android Police](https://www.androidpolice.com/why-third-party-android-camera-apps-awful/)
- **Samsung exposure.** The same article notes Samsung (from the S22 onward) gives third-party developers access to camera extensions (Auto, Bokeh, HDR, Night, Face Retouch) and to all three sensors through one logical camera, which is better than Pixel. [Android Police](https://www.androidpolice.com/why-third-party-android-camera-apps-awful/)
- **Blackmagic's limited launch.** It launched on Android in June 2024 for Samsung and Pixel only; Notebookcheck headlined it "your phone probably can't run it". [Notebookcheck, 2024-06-24](https://www.notebookcheck.net/Blackmagic-s-pro-level-video-app-lands-on-Android-but-your-phone-probably-can-t-run-it.852185.0.html)
  - OnePlus and Xiaomi support came later. [GSMArena](https://www.gsmarena.com/blackmagic_camera_app_updated_with_new_features_oneplus_and_xiaomi_phone_support-news-63804.php)
  - Samsung Log LUTs came in v3.1 (Oct 2025). [AlternativeTo](https://alternativeto.net/news/2025/10/blackmagic-camera-3-1-for-android-adds-open-gate-shooting-function-buttons-and-samsung-luts)
- **Blackmagic device-specific Play reviews:**
  - "Not all lenses work on my Xiaomi 13T pro! The main lens… just a green screen… i miss the log options, which exist on my phone app" (1★, 2025-10-11).
  - "All lenses work except the 3x telephoto… Autofocus doesn't work" (Nothing Phone 3a Pro, 2★, 2025-12-16).
  - "Samsung Flip 7… Samsung Log is only available in one resolution" (2★, 2025-12-28).
  - "issues on my Samsung S24+… lost all my footage" (2★, 2024-10-27).
  - "Videos turn out overly sharpened… sharpening keeps turning on and off randomly" (1★, 2024-08-26, 156 helpful).
  - "records footage from my front camera upside-down" (Xiaomi 14, 4★, 2024-07-29).
  - Positive counter-example: "Moto Edge 60 Pro… All lenses work well… 4K at 60fps, whereas the stock camera is limited to 4K at 30fps" (5★, 2025-10-19, 450 helpful).
  - Source: [Play – Blackmagic](https://play.google.com/store/apps/details?id=com.blackmagicdesign.android.blackmagiccam)
- **iPhone-first feature gap** (Blackmagic): "I can't seem to get my DJI Mic 2 to be the audio source… most apps are more geared to iPhones than Androids" (2★, 2024-10-15, 424 helpful). [Play – Blackmagic](https://play.google.com/store/apps/details?id=com.blackmagicdesign.android.blackmagiccam)
- **mcpro24fps device bugs:**
  - "causes audio distortion on Samsung devices" (1★, 2025-06-26).
  - "Xiaomi 14 Ultra… iris keeps opening and closing… black screen" (1★, 2024-06-16).
  - "pixel 9 pro, it completely restarts my phone" (1★, 2024-10-23).
  - Source: [Play – mcpro24fps](https://play.google.com/store/apps/details?id=lv.mcprotector.mcpro24fps)
- **Film-cam lens and HDR access:**
  - Kapi's 0.5× support is its most-upvoted praise (519 helpful).
  - "letting us use an ultra wide camera… not just the normal camera or by zooming in" (OldRoll 5★, 2026-09-22).
  - "doesn't seem to use the android camera hdr features… wide angle and super wide angle are the wrong way around in Pixel phones" (NOMO 4★, 2026-01-15).
  - "Works only with selfie camera on Android" (NOMO 2★, 2024-11-03).
  - "mine stuck on the ultra wide" (Kuji 5★, 2024-12-21).
  - Sources: [Play – Kapi](https://play.google.com/store/apps/details?id=com.sensemobile.action), [Play – OldRoll](https://play.google.com/store/apps/details?id=com.accordion.analogcam), [Play – NOMO](https://play.google.com/store/apps/details?id=com.blink.academy.nomopro), [Play – Kuji](https://play.google.com/store/apps/details?id=com.ginnypix.kujicam)
- **Live Photo on Android** is a recurring pull factor: 102 ProCCD and 57 Kapi mentions.
  - "Kapi Cam is a great app for android users to have Live Photo" (4★, 2026-04-09).
  - "it can give you the experience of having a i phone" (ProCCD 3★, 2025-09-11).
  - Vietnamese: "rất tốt cho máy cái đth nào mà ko có live photo" ("great for any phone without Live Photo", ProCCD 5★, 2026-08-14).
  - Complaint: "lưu về nó ra 1 vd và 1 ảnh, k live photo như quảng cáo" ("it saves as one video + one photo, not a Live Photo as advertised", ProCCD 2★, 2026-09-04).
  - Sources: [Play – ProCCD](https://play.google.com/store/apps/details?id=com.cerdillac.proccd), [Play – Kapi](https://play.google.com/store/apps/details?id=com.sensemobile.action)
- **Flash and orientation bugs by brand:**
  - Huji flash on Samsung S24 (2026-02-05).
  - Kapi flash behaviour changed on Samsung A16 (4★, 2026-06-26).
  - Dazz-clone photos upside down (2026-09-18).
  - OldRoll imports "turned out stretched" after an update (4★, 2024-05-24, 225 helpful).
  - Sources: [Play – Huji](https://play.google.com/store/apps/details?id=kr.co.manhole.hujicam), [Play – Kapi](https://play.google.com/store/apps/details?id=com.sensemobile.action), [Play – OldRoll](https://play.google.com/store/apps/details?id=com.accordion.analogcam)
- **Lightroom on Android:**
  - "photos are showing up as giant pixelated blocks… Unless you have a perfect internet connection" (1★, 2026-09-15, 235 helpful).
  - "glitched image of colored rectangles" after the June 2026 update (1★, 2026-06-19).
  - Source: [Play – Lightroom](https://play.google.com/store/apps/details?id=com.adobe.lrmobile)
- **Android parity is a named pain** in Tezza reviews: "android version is behind… Paying for the app for years, but we never were so behind apple users" (2★, 2024-10-20). [Play – Tezza](https://play.google.com/store/apps/details?id=org.tezza)
- **Brand mentions in the film-cam group** are low (≈1–3% of negatives). Low-end devices appear repeatedly: Redmi 13C (Kuji), Redmi Note 10s (ProCCD), Samsung A16 (Kapi). [Play – Kuji](https://play.google.com/store/apps/details?id=com.ginnypix.kujicam)

### Inferences
- For a casual film-cam app on Android, the most valuable engineering investments, judged by review evidence, are:
  - reliable ultrawide (0.5×) and front-camera support with flash (a screen flash for selfies)
  - an Android "Live Photo"-style motion capture that actually saves in a shareable format
  - WYSIWYG: the captured image must match the preview, per the Kapi "preview looks better than the result" complaint
  - correct orientation on every brand

  Raw resolution matters less to this audience than to pros.
- For pro/LUT apps, a per-device capability matrix (which lenses, frame rates and Log modes work on which phone) and graceful fallbacks are the difference between 5★ and 1★. Samsung and Xiaomi are the priority test devices.

### Gaps
- I found no quantitative benchmark of third-party versus stock camera image quality on 2025–2026 Android flagships, for example whether Samsung's Camera Extensions for Night/HDR are used by film-cam apps.
- Oppo, Vivo, realme and Tecno are almost absent from English reviews, and I could not find Vietnamese reviews that name these brands specifically.

---

## 4. Underserved jobs-to-be-done

### Takeaway
The evidence best supports these jobs:
1. **iPhone-parity "vibe" capture on Android**: Live Photo, 0.5× lens, flash, Y2K/CCD digicam looks.
2. **Real-time LUT preview while filming**, with in-viewfinder switching and intensity control, and a way to use your own or camera-maker LUTs (Samsung/Apple Log).
3. **Make phone photos look like my Fujifilm/Ricoh/Canon.** This lives in an enthusiast recipe ecosystem (Fuji X Weekly, Camset, FujiStyle) and the Vietnamese "công thức màu" (colour recipe) culture.
4. **A consistent look across a feed or batch**, including photos and video.
5. **Share or sell my recipe/preset.** Vietnamese users group-buy Lightroom presets and ask for recipe QR codes.
6. **Event and shared disposable cameras** without app installs or opaque pricing.

"Date-stamp authenticity" and "photo dump" show up weakly in reviews.

### Cited Findings
- **Real-time LUT preview and control while filming:**
  - "It would be nice if I could select and preview LUTs on the video screen" (Blackmagic 4★, 2024-07-29, 297 helpful).
  - "I'd love to be able to switch luts from the main recording screen… having an intensity adjustment would be great" (4★, 2024-10-11, 105 helpful).
  - "i downloaded extra lut and imported it, still the lut is not working" (S25 FE, 1★, 2026-04-23).
  - "Can't use log with 8k or in open gate. The existing and uploaded LUTs don't work" (S25 Ultra, 1★, 2026-04-02).
  - Source: [Play – Blackmagic](https://play.google.com/store/apps/details?id=com.blackmagicdesign.android.blackmagiccam)
  - On iOS, Blackmagic Camera supports importing LUTs for live preview. However, the LUT preview disappears when stabilization is set to Cinematic/Extreme, and a creator blog documents workarounds. [Tobia Montanari](https://www.tobiamontanari.com/blackmagic-camera-lut-preview-not-working/), [Epic Tutorials](https://epictutorials.com/blogs/articles/how-to-use-luts-in-blackmagic-camera-iphone)
  - A market of Apple Log LUT packs exists (Absoluts, ypresets, Gumroad), which indicates paid demand for "Log → look" conversion on phones. [Absoluts](https://absoluts-store.com/blogs/blog/best-iphone-luts-apple-log), [ypresets](https://www.ypresets.com/products/iphone-apple-log-luts)
- **Use your phone maker's Log with LUTs:**
  - "i miss the log options, which exist on my phone app" (Xiaomi 13T Pro, 2025-10-11).
  - "I hope a log profile of some sort is added" (Pixel 8, 4★, 2024-08-27).
  - "Samsung Log is only available in one resolution" (Flip 7, 2025-12-28).
  - Source: [Play – Blackmagic](https://play.google.com/store/apps/details?id=com.blackmagicdesign.android.blackmagiccam)
  - Blackmagic added Samsung Log LUTs in v3.1 (Oct 2025). [AlternativeTo](https://alternativeto.net/news/2025/10/blackmagic-camera-3-1-for-android-adds-open-gate-shooting-function-buttons-and-samsung-luts)
- **Look like my Fujifilm/Ricoh/Canon:**
  - A cluster of recipe apps exists (Fuji X Weekly, FujiStyle, Camset "Fuji & Ricoh Recipes", FxjiMate), and Fujifilm lets users send film simulations from an iPhone to the camera. [Camset App Store](https://apps.apple.com/app/id6502640665), [FxjiMate](https://apps.apple.com/us/app/id6469689080), [DPReview](https://www.dpreview.com/news/fujifilm-users-can-now-send-film-simulations-to-their-camera-from-their-iphone/)
  - Vietnamese Threads account @congthucmau recommended ProCCD's F100 as the "must-have" Fuji-colour app on iPhone (2026-01-25): 606 likes, 82 reposts, 104 shares, ~50.5K views. [Threads](https://www.threads.com/@congthucmau/post/DT9WDPzidyR/)
  - TikTok has Vietnamese discovery pages for "chỉnh màu Fujifilm trên iPhone / điện thoại" (Fujifilm colour editing on iPhone / phone) and "app chỉnh màu như Fujifilm" (an app that edits colour like Fujifilm). [TikTok](https://www.tiktok.com/discover/ch%E1%BB%89nh-m%C3%A0u-fujifilm-tr%C3%AAn-%C4%91i%E1%BB%87n-tho%E1%BA%A1i), [TikTok](https://www.tiktok.com/discover/app-ch%E1%BB%89nh-m%C3%A0u-nh%C6%B0-fujifilm)
  - Vietnamese blogs publish iPhone Photos-app "công thức" (numeric edit recipes). [Cardina](https://cardina.vn/blogs/chup-hinh/cong-thuc-chinh-anh-tren-iphone-khong-can-app)
  - Lightroom Vietnamese review: "không có màu profile Chép theo mẫu của Canon r6 mark ii" (2026-02-07). [Play – Lightroom](https://play.google.com/store/apps/details?id=com.adobe.lrmobile)
  - However, "fuji|ricoh|recipe|film simulation" appears in only ≤4 reviews per app in mass-market Play reviews (e.g. OldRoll 4, VSCO 4, NOMO 3). This is an enthusiast and creator job, not a mass-review theme. [Play – OldRoll](https://play.google.com/store/apps/details?id=com.accordion.analogcam)
- **Share or sell my preset:**
  - Vietnamese forum Voz has threads titled "Chia sẻ presets Lightroom" ("Sharing Lightroom presets") and "50k mua chung presets Lightroom của HPPhotoshop" ("group-buying HPPhotoshop's Lightroom presets for 50k VND"). [Voz](https://voz.vn/t/chia-se-presets-lightroom.170880/), [Voz](https://voz.vn/t/50k-mua-chung-presets-lightroom-cua-hpphotoshop.321187/)
  - Vietnamese camera shops sell "preset màu film" (film colour presets). [Dương Cường Camera](https://duongcuong.com/preset-mau-film/)
  - VSCO user: "Mong phần công thức có thể lưu lại dưới dạng mã QR" (2025-08-25). [iOS RSS VN – VSCO](https://itunes.apple.com/vn/rss/customerreviews/id=588013838/sortBy=mostRecent/json)
  - A Lightroom iOS Vietnamese reviewer bought a "gói dùng màu ảnh vĩnh viễn" ("lifetime colour pack") from a "đội ngũ tư vấn" ("sales/consulting team") and felt scammed: "CẢM THẤY NHƯ BỊ LỪA ĐẢO" ("feel like I was scammed", 1★, 2026-07-08). This suggests a grey market in preset reselling. [iOS RSS VN – Lightroom](https://itunes.apple.com/vn/rss/customerreviews/id=878783582/sortBy=mostRecent/json)
- **Consistent look across a batch or feed:** "I can copy my edits for certain photos within a group, so they all look relatively uniform" (Lightroom 4★, 1,103 helpful). Dehancer users ask for batch editing. [Play – Lightroom](https://play.google.com/store/apps/details?id=com.adobe.lrmobile), [App Store – Dehancer](https://apps.apple.com/us/app/6443648413?see-all=reviews&platform=iphone)
- **Same look on photo and video:**
  - "I love h35 camera so much. I'd like to have a video recording feature using that filter" (OldRoll 5★, 2026-07-23). [Play – OldRoll](https://play.google.com/store/apps/details?id=com.accordion.analogcam)
  - Lightroom iOS VN: "subscribed… mainly to apply video presets, but importing HDR videos automatically changes the exposure" (1★, 2026-03-07). [iOS RSS VN – Lightroom](https://itunes.apple.com/vn/rss/customerreviews/id=878783582/sortBy=mostRecent/json)
  - VN user: "Colour grading needs improvement" (3,883 helpful). [Play – VN](https://play.google.com/store/apps/details?id=com.frontrow.vlog)
- **Y2K digicam look for friends** (the core Kapi and ProCCD job): "nostalgic, early 2000s digital camera aesthetic… variety of 'cameras'… each with a distinct feel" (ProCCD 5★, 523 helpful). The Nokia and S5 "phone camera" presets were favourites, and paywalling them triggered churn. [Play – ProCCD](https://play.google.com/store/apps/details?id=com.cerdillac.proccd), [Play – Kapi](https://play.google.com/store/apps/details?id=com.sensemobile.action)
- **Date stamp:**
  - RNI users asked for "customizable date stamp formatting" (2025-04-09), and RNI earlier "Fixed time stamp" after backlash (2022). [App Store – RNI](https://apps.apple.com/us/app/1017098672?see-all=reviews&platform=iphone)
  - The Tab noted a date overlay "reveals digital origin" in DAZE CAM. [The Tab](https://thetab.com/2025/04/22/right-i-tested-apps-that-make-your-photos-look-like-film-to-see-which-actually-work)
  - A competitor markets real EXIF data (camera, aperture, ISO) "unlike Dazz Cam's fake timestamps". This is a vendor claim. [SHOTON blog](https://shoton.app/blog/dazz-cam-alternative)
- **Authenticity beats heavy effects:**
  - "grain is static, just an overlaid image" (1★, 2026-09-06). [Play – Dazz Cam (Monova)](https://play.google.com/store/apps/details?id=app.grain.camera)
  - Huji's random effects are praised as "close to emulating old cameras" (2026-03-23). [Play – Huji](https://play.google.com/store/apps/details?id=kr.co.manhole.hujicam)
  - Kamon was docked for "The light flare is very extreme and there is no option to go back and edit". [The Tab](https://thetab.com/2025/04/22/right-i-tested-apps-that-make-your-photos-look-like-film-to-see-which-actually-work)

### Inferences
- The three jobs with the clearest evidence, and which map naturally onto three separate apps, are:
  - **(a)** an Android-first "vibe cam" (Y2K/CCD/film looks, Live Photo-style motion, 0.5×/selfie flash, fair paywall)
  - **(b)** a live-LUT video and photo camera (import .cube files, switch and adjust intensity in the viewfinder, maker-Log support, the same LUT for photo and video)
  - **(c)** a recipe/preset studio (camera-maker look recipes such as Fuji/Ricoh/Canon, shareable via QR/link, a creator marketplace, batch "same look" application)
- The Vietnamese preset-selling culture (group-buys, shop presets, "công thức" posts) suggests creator monetization or a sharing layer could find early traction locally.

### Gaps
- I could not access Reddit threads (r/fujifilm, r/analog, r/colorists, r/videography) directly, so enthusiast sentiment about "fake" film looks, Fuji recipe accuracy and phone-LUT workflows is under-sampled.
- I could not quantify the "photo dump" and "colour match a reference image" jobs from reviews: there were almost no mentions.
- I could not retrieve YouTube comparison videos or comments (2024–2026).

---

## 5. Community voices (Reddit, YouTube, TikTok, Vietnamese communities)

### Takeaway
Direct community sampling was limited: Reddit, Voz and Tinhte pages returned 403. The accessible evidence shows two things:
- Vietnamese users care about **free/cheap access for students, Vietnamese UI, Live Photo, Fuji-style colour recipes and preset sharing**, and react strongly to cultural mislabelling ("Chinese New Year").
- Mainstream English press and blog tests rank apps on realism, price model and editability.

### Cited Findings
- **The Tab's hands-on test** (2025-04-22) scored:
  - DAZE CAM 10/10 (one-off £2.99)
  - Dazz Cam 8/10 ("subtle but convincing, adding a nostalgic hue"; the free "Inst C" camera is "popular on TikTok")
  - Prequel 7/10 (£4.99/week)
  - Kamon 3.5/10
  - Simple Disposable 0/10 ("Shocking, not convincing at all")
  - Source: [The Tab](https://thetab.com/2025/04/22/right-i-tested-apps-that-make-your-photos-look-like-film-to-see-which-actually-work)
- **Vietnamese Play-review signals** (vi-VN locale, 2024–2026):
  - Hypic: 130 of 138 substantive Vietnamese reviews are 1–2★, mostly paywall complaints: "cái gì cũng bắt nạp" ("everything forces you to top up"). [Play – Hypic](https://play.google.com/store/apps/details?id=com.xt.retouchoversea)
  - VSCO: 38 of 44 Vietnamese reviews are 1–2★ (login and paid slow-mo). [Play – VSCO](https://play.google.com/store/apps/details?id=com.vsco.cam)
  - ProCCD: 43 of 49 are 4–5★, praising Live Photo. [Play – ProCCD](https://play.google.com/store/apps/details?id=com.cerdillac.proccd)
  - OldRoll: 52 of 66 are 4–5★, but "mấy cái kia mất phí nhiều quá" ("the other cameras cost too much", 4★, 2024-12-21, 36 helpful). [Play – OldRoll](https://play.google.com/store/apps/details?id=com.accordion.analogcam)
  - Dazzil: 25 of 37 are 1–2★ (crash on open). [Play – Dazzil](https://play.google.com/store/apps/details?id=com.camerafilm.lofiretro)
- **Localization and culture:**
  - OldRoll's "Chinese New Year" label drew Vietnamese 1★ reviews: "What the hell is 'Chinese New Year'… Vietnam and other countries celebrate Lunar New Year too" (2026-02-12). [Play – OldRoll](https://play.google.com/store/apps/details?id=com.accordion.analogcam)
  - "Kh có tiếng việt bất tiện" (no Vietnamese UI, VSCO iOS VN, 2026-05-03). [iOS RSS VN – VSCO](https://itunes.apple.com/vn/rss/customerreviews/id=588013838/sortBy=mostRecent/json)
- **Vietnamese how-to media** (GearVN, CellphoneS Sforum, VJShop, Điện máy Chợ Lớn, ColorMe) repeatedly features Dazz Cam as the go-to film app and notes it is iPhone-optimised. [GearVN](https://gearvn.com/blogs/thu-thuat-giai-dap/dazz-cam), [Sforum](https://cellphones.com.vn/sforum/cach-su-dung-dazz-cam), [VJShop](https://vjshop.vn/tin-tuc/cong-nghe/cach-su-dung-dazz-cam), [ColorMe](https://colorme.vn/blog/review-5-ung-dung-chup-anh-film-hot-nhat)
- A Tinhte thread "Các bác cho em xin vài app chụp ảnh vintage với ạ" ("could you recommend some vintage photo apps?") exists, but its content returned 403. [Tinhte](https://tinhte.vn/thread/cac-bac-cho-em-xin-vai-app-chup-anh-vintage-voi-a.3119216/)
- **Vietnamese "công thức màu" (colour recipe) creators** on Threads, Instagram and TikTok drive app discovery. The @congthucmau ProCCD post had about 50.5K views. [Threads](https://www.threads.com/@congthucmau/post/DT9WDPzidyR/), [Instagram](https://www.instagram.com/p/DVqBfyKjRIJ/)
- **Social critique of Lapse** (Product Hunt): "my friends and I already talk in group chats. If we want to share photos, we know how to do so." [Product Hunt](https://www.producthunt.com/p/lapse-3/lapse-a-cautionary-tale-for-social-products-that-prioritize-disposable-sharing)

### Inferences
- In Vietnam, discovery is creator-led: recipe and "công thức" posts on Threads, TikTok and Facebook. An app that makes a recipe shareable as a link or QR code and previewable live on Android could ride this channel.
- Vietnamese UI, correct cultural labels (Tết / Lunar New Year) and student-friendly pricing are low-cost differentiators against Chinese and Korean incumbents.

### Gaps
- No Reddit, YouTube-comment or Facebook-group content could be fetched (403s and login walls), so frequencies there are unknown.
- The Spiderum search returned nothing relevant.
- I found no 2024–2026 YouTube comparison video that I could verify.

---

## 6. Social film apps (Lapse, Dispo, POV/event cameras, Retro): growth and decline

### Takeaway
The "delayed-develop disposable plus friends" mechanic grows fast through forced invites and novelty, then struggles with running costs and with users preferring group chats.
- **Lapse** removed Feed, Profile and Chat on 2025-11-03, and its 2026 iOS reviews are dominated by "bring back social" and lost photos.
- **Dispo** never recovered from its 2021 founder scandal but still ships updates.
- **Retro** users punish added paywalls (a "key" feature, Premium) and removed video.
- **POV/event-camera** users like the concept but hit per-guest photo caps, forced app installs, opaque pricing and reliability failures on the one day that matters.

### Cited Findings
- **Lapse announcement.** On 2025-11-03 Lapse said "as the community has grown, so too have the costs of running the platform". It removed Feed, Profile and Chat and kept Memories synced to iOS Photos. [Product Hunt](https://www.producthunt.com/p/lapse-3/lapse-a-cautionary-tale-for-social-products-that-prioritize-disposable-sharing), [Wikipedia](https://en.wikipedia.org/wiki/Lapse_(social_network)), [Threads user reaction](https://www.threads.com/@_mliu/post/DQnQp5NAApi/sad-that-lapse-is-removing-the-social-features-within-the-app-for-the-last?hl=en)
- **Lapse growth history.** It topped the App Store by forcing users to invite friends (TechCrunch, 2023-09-26) and raised $30M (TechCrunch, 2024-02-27). [TechCrunch](https://techcrunch.com/2023/09/26/photo-sharing-app-lapse-hits-top-of-the-app-store-by-forcing-you-to-invite-your-friends/embed), [TechCrunch](https://techcrunch.com/2024/02/27/lapse-the-app-turning-your-phone-into-an-old-school-camera-snaps-up-30m)
- **Lapse iOS US reviews, 2026-03-16 → 2026-09-24** (n=150): 68 (45%) are 1–2★.
  - 114 (76%) mention social, friends or feed.
  - 66 (44%) say "bring back", "used to" or "go back".
  - 36 (24%) mention lost, deleted or gone photos.
  - "the social aspect and interactive aspects have been completely removed" (1★, 2026-09-23).
  - "my best friend died three years ago and now I can't get any important pictures from the app" (1★, 2026-09-07).
  - "the original files were only available till Ju[ne]" (4★, 2026-09-17).
  - Source: [iOS RSS – Lapse](https://itunes.apple.com/us/rss/customerreviews/id=1636699256/sortBy=mostRecent/json)
- **Dispo.** Co-founder David Dobrik left in March 2021 amid Vlog Squad allegations, and Spark Capital severed ties. [CBC](https://www.cbc.ca/news/entertainment/david-dobrik-dispo-1.5959360), [TheWrap](https://www.thewrap.com/david-dobrik-steps-down-dispo/)
  - It later raised a Series A without him. [dot.la](https://dot.la/dispo-app-2653281618.html)
  - The app is still updated (v3.1 on 2025-03-11) and rated 4.29★ from 8,161 US ratings. [App Store – Dispo](https://apps.apple.com/us/app/dispo-retro-disposable-camera/id1491684197)
- **POV** (Play 4.80★ overall, but 45% of the 2024–2026 sample is 1–2★):
  - Negatives: login/account 27%, paywall 22%, crash 12%, save 8%.
  - "charge me 70 bucks so the 200 some guests at my wedding can take 25 photos" (1★, 2024-01-25, 122 helpful).
  - "The limit was 25 pics per person. The app allowed to take only 5… Still didn't get my refund" (1★, 2024-05-20, 95 helpful).
  - "after 41 photos it gave an error that it was full… We should've gone with the disposal cameras" (1★, 2024-05-27).
  - "Its forcing you to download the app… 'credential manager is not supported on your device'" (1★, 2024-02-09, 73 helpful).
  - "the need not to download the app only works on iphone users" (2★, 2024-10-28).
  - "to understand pricing, it was necessary to: Download the app, Integrate an account, Set up a (dummy) event…" (1★, 2024-09-30).
  - Positive: "easy to set up and easy to download all of the photos using the export all button… price was not converted to aud" (4★, 2024-04-19, 124 helpful).
  - Positive: "option to remove the 'POV Camera' watermark… I would pay extra" (4★, 2026-03-06).
  - Source: [Play – POV](https://play.google.com/store/apps/details?id=com.untitledshows.pov)
- **Browser-based alternatives.** Competitors now market no-install, browser-based event cameras (JoinMyMoment, Once, Scene). Those pages are vendor comparisons. [JoinMyMoment blog](https://blog.joinmymoment.com/pov-camera-app-review/), [Scene](https://scenedisposable.com/alternatives/disposable-camera-apps), [Once App Store](https://apps.apple.com/app/id6754265953)
- **Retro** (Play 4.71★; 27% of the 2024–2026 sample is 1–2★). Negatives: login 20%, paywall 12%.
  - "the recent update of removing videos has dropped the rating significantly" (2★, 2025-04-25).
  - "the 'key' feature completely ruined the experience… only three key holders" (1★, 2025-04-26).
  - "why would you put price tags on something that was completely free" (2★, 2025-05-03).
  - "cannot sign up without adding the friends you recommended" (1★, 2026-04-18).
  - Phone-number-only login locks out people who lose their SIM (5★, 2026-04-15).
  - Praise: "The AI-free feed makes it feel so personal and genuine" (5★, 2024-10-08).
  - Praise: "retro focuses on keeping things small and non-addictive" (5★, 2025-11-09).
  - Source: [Play – Retro](https://play.google.com/store/apps/details?id=io.lonepalm.retro)

### Inferences
- A shared "disposable camera" for events is best built as:
  - a **no-install web/App Clip/Instant App join** (QR → browser)
  - with **transparent upfront per-event pricing** in local currency
  - **generous or no per-guest caps**
  - **offline capture with later sync**
  - one-tap "export all"
  - an optional paid watermark removal

  Wedding and party use in Vietnam (large guest counts, many Android phones) makes the Android no-install path critical.
- For an indie team, standing social feeds are costly to run and churn-prone (Lapse). Event-scoped, time-boxed albums avoid the ongoing moderation and infrastructure costs.

### Gaps
- I have no user counts or revenue for POV, Retro or Lapse after the pivot, and no Vietnamese-market data on event disposable-camera apps.
- iOS POV reviews were not retrievable through RSS.

---

## 7. Privacy, permissions, account requirements and offline expectations

### Takeaway
Explicit privacy or location complaints are rare (about 1–2% of negatives). **Forced accounts and login failures** are a major pain, however: 21% of VSCO negatives, 26% of NOMO's, 27% of POV's and 20% of Retro's. Users also expect a camera or filter app to **work offline**, and online-only asset downloads (FIMO) or cloud dependence (Lightroom) draw complaints. Phone-number sign-up in Vietnam has been linked by users to spam.

### Cited Findings
- **Login and account as share of 1–2★:** VSCO 21%, NOMO 26%, POV 27%, Retro 20%, Lightroom 5%, CapCut 5%.
  - VSCO: "đăng nhập kiểu gì cũng không được" ("can't log in no matter what", 1★, 2025-06-11, 42 helpful).
  - VSCO: "don't know why they make it so difficult to delete an account" (1★, 2025-10-10).
  - Sources: [Play – VSCO](https://play.google.com/store/apps/details?id=com.vsco.cam), [Play – NOMO](https://play.google.com/store/apps/details?id=com.blink.academy.nomopro), [Play – POV](https://play.google.com/store/apps/details?id=com.untitledshows.pov), [Play – Retro](https://play.google.com/store/apps/details?id=io.lonepalm.retro)
- **Account needed just to buy or restore:**
  - "This app doesn't let me sign in, so in app purchases are gone out of the window" (NOMO 2★, 2024-01-08).
  - "'Request Too Frequently' and 'Network Error'" on sign-in (NOMO 2★, 2024-01-22).
  - Source: [Play – NOMO](https://play.google.com/store/apps/details?id=com.blink.academy.nomopro)
- **Phone-number login linked to spam:** NOMO Vietnamese review, 2024-07-12, quoted above. [Play – NOMO](https://play.google.com/store/apps/details?id=com.blink.academy.nomopro)
- **Privacy trust:** "i don't trust its security or privacy promise" (Retro 2★, 2026-01-01). [Play – Retro](https://play.google.com/store/apps/details?id=io.lonepalm.retro)
- **Permissions:**
  - Blackmagic "asks me for certain permissions which I give it, and then the app crashes" (1★, 2024-09-19, 213 helpful). [Play – Blackmagic](https://play.google.com/store/apps/details?id=com.blackmagicdesign.android.blackmagiccam)
  - Blackmagic iOS: "locked out after permission request despite already granting camera/microphone access" (4★, Apr 16). [App Store – Blackmagic](https://apps.apple.com/us/app/6449580241?see-all=reviews&platform=iphone)
- **Offline and cloud dependence:**
  - FIMO rolls "don't work properly if you're not online" (2★, 2025-06-07). [Play – FIMO](https://play.google.com/store/apps/details?id=com.fimo.camera)
  - Lightroom: "Unless you have a perfect internet connection all the time you can forget about using" (1★, 2026-09-15, 235 helpful). [Play – Lightroom](https://play.google.com/store/apps/details?id=com.adobe.lrmobile)
  - CapCut: "it needs a internet connection to wo[rk]" (4★, 2026-07-30). [Play – CapCut](https://play.google.com/store/apps/details?id=com.lemon.lvoverseas)
  - ProCCD: "camera options are not downloadable… failed to download" after paying (1★, 2025-11-18). [Play – ProCCD](https://play.google.com/store/apps/details?id=com.cerdillac.proccd)
- **Data loss:**
  - CapCut: "when I transferred my data from my old phone… all of my projects got deleted" (2★, 2025-06-23, 2,883 helpful). [Play – CapCut](https://play.google.com/store/apps/details?id=com.lemon.lvoverseas)
  - Lapse: lost memories after the pivot (24% of 2026 iOS reviews). [iOS RSS – Lapse](https://itunes.apple.com/us/rss/customerreviews/id=1636699256/sortBy=mostRecent/json)
  - NOMO Vietnamese: "chụp đẹp nhưng kbt lưu ở đâu" ("photos look great but I don't know where they're saved", 5★, 2026-05-14, 21 helpful). [Play – NOMO](https://play.google.com/store/apps/details?id=com.blink.academy.nomopro)
- **Location and privacy keywords** matched only about 1% of film-cam and editor negatives, and 2% of social-app negatives, across the dataset (my tagging). [Play listings above]

### Inferences
- "No account required, works fully offline, all looks bundled or cached, photos saved straight to the gallery in a clearly named album, purchases restored through the store" directly addresses a measurable share of 1★ reviews. For a no-server indie team it is also cheaper to run.
- If a sharing or event feature needs identity, use Google/Apple sign-in or a link/QR join rather than phone-number OTP. Vietnamese users associate phone-number sign-up with spam.

### Gaps
- I found no reviews that specifically complain about location permission or EXIF GPS stripping in film apps.
- I did not audit Play "Data safety" declarations of competitors.
