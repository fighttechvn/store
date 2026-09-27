# Tech stack, feasibility, legal/policy constraints and opportunity gaps for film-camera / preset / LUT apps (Android first, iOS second), as of 2026-09-27

Scope note: these notes cover technology, platform policy, IP risk and opportunity gaps. Market sizing and competitor revenue are out of scope. Anything marked "(unverified)" or put under Gaps could not be confirmed from a primary source in this session.

## Q0. Benchmark apps: what Filmode (app.filmode) and FilCam (app.filmode.filcam) already do

### Takeaway
Both benchmark apps come from the same developer, "Trung-Hieu Tran". They are very new, with tiny install bases (50+ and 100+). Technically they already cover a lot: a live 64³ GPU LUT on the viewfinder, .cube import, Lightroom-style preset import, RAW DNG, Camera2 manual controls, selfie segmentation and effects baked into video. So the gap to competitors is distribution and differentiation rather than core tech.

### Cited Findings
- The Play listing for `app.filmode` is now titled **"Filmode Vibe — Film Camera"**. Its developer is shown as **Trung-Hieu Tran**. It shows 50+ downloads, "Updated on Sep 22, 2026", another listing date of Jul 22, 2026 (probably the release date; unverified) and in-app products at **$2.99–$29.99 per item** — [Google Play: Filmode Vibe](https://play.google.com/store/apps/details?id=app.filmode&hl=en_US)
- Filmode Vibe features, as the listing describes them:
  - six free "hand-crafted looks" (Golden, Teal, Analog, Glow, Midnight, Mono) rendered live "with a real 64³ film LUT on the GPU"
  - ten real-time effects baked in at capture: Rain, Halation, VHS, Frost, Grain, CCD "Y2K digicam", direct Flash, projector Dust, light Leak, cross-screen Star
  - Toy, Instant and Pro camera skins; Pro has manual ISO, shutter, focus, WB, burst, bracketing, intervalometer, night mode, focus stacking and dual-camera shot
  - a photo editor with **import of .cube LUTs and "Lightroom-style presets"**
  - a Photobooth using **on-device selfie segmentation**
  - video clips of **up to 15 s** with LUT, rain and grain encoded in
  - frames (Polaroid, Booth, Cutie, Frame, Noir, Retro, Raw)
  - a cork "pin-board" and **Google sign-in Cloud Boards shared by code or through a web app**
  - 18 free looks, plus Pro with 25 more looks (Cinematic/Film/Selfie), long exposure and light trails, sold monthly, yearly or lifetime
  - "No ads and no watermark"; English and Vietnamese

  — [Google Play: Filmode Vibe](https://play.google.com/store/apps/details?id=app.filmode&hl=en_US)
- The listing names a frame style "Polaroid". This is a registered trademark (see Q6) — [Google Play: Filmode Vibe](https://play.google.com/store/apps/details?id=app.filmode&hl=en_US)
- The `app.filmode.filcam` listing is titled **"FilCam: Pro Manual RAW Camera"**, also from developer Trung-Hieu Tran. It shows 100+ downloads, "Updated on Sep 26, 2026", another listing date of Sep 4, 2026, and in-app products at **$0.99–$9.99 per item** — [Google Play: FilCam](https://play.google.com/store/apps/details?id=app.filmode.filcam&hl=en_US)
- FilCam features, as the listing describes them:
  - Free: P/S/I/M-style manual control (ISO, shutter, EV, Kelvin WB, manual focus), **RAW DNG "written from your device's own sensor calibration"**, and "Real 64³ film LUTs rendered live on the GPU and baked into the JPEG"; the DNG always stays untouched.
  - Pro: long exposure "up to 30 seconds", light trails from 15 s to 5 min, 3/5/7-frame bracketing, focus stacking, night mode and intervalometer. Pro is sold monthly, yearly with a 7-day trial, or lifetime.
  - Output and hardware: JPEG/HEIF/PNG, custom filenames and folder, geotag plus full EXIF, volume-key mapping, live RGB histogram.
  - It "hides anything your device cannot deliver" because manual controls "depend on what your phone's manufacturer exposes through Camera2".

  — [Google Play: FilCam](https://play.google.com/store/apps/details?id=app.filmode.filcam&hl=en_US)

### Inferences
- Both apps already have the hard parts: a GPU LUT pipeline, a Camera2 manual stack, DNG writing, segmentation and encoding effects into video. For a follow-up product, extending that code (a video LUT tool, a preset marketplace, event boards) costs far less than a greenfield build.
- A 64³ RGBA8 3D texture is 64×64×64×4 B ≈ 1 MiB (arithmetic). Memory is not a concern even on low-end GPUs.
- The 15-second video cap in Filmode Vibe suggests video is not yet a full recording pipeline (no long 4K/HDR/Log). That is the natural gap for a third "video LUT/color" app.

### Gaps
- Play does not show a public rating or review count for either app (too few reviews). Retention and conversion data are unavailable.

---

## Q1. Android camera stack: CameraX vs Camera2, effects, extensions, RAW, Ultra HDR, HDR video, Log, ZSL, and the quality gap to OEM camera apps

### Takeaway
For a 1–3 person team in 2026, CameraX 1.6.x (stable, CameraPipe-based) is the right default: it now covers RAW/DNG, Ultra HDR, HLG feature groups, CameraEffect/OverlayEffect, low-light boost, high-speed video and vendor Extensions. Drop to Camera2 (via Camera2Interop, or directly) only for full manual and long exposure.

The structural quality gap to OEM camera apps remains. OEMs keep multi-frame pipelines, some lenses and resolutions, Log profiles and high-bitrate modes private or partner-only. Blackmagic and mcpro24fps live with this by maintaining per-device support lists and working with OEMs.

### Cited Findings

**Versions and platform changes**

CameraX versions and dates:

| Version | Date | Status |
|---|---|---|
| 1.6.2 | Aug 26, 2026 | latest stable |
| 1.6.0 | Mar 25, 2026 | stable |
| 1.5.0 | Sep 10, 2025 | stable |
| 1.7.0-alpha03 | Aug 12, 2026 | alpha |

What each release changed:
- **1.6** migrated CameraX to **CameraPipe**, "the same stack powering Pixel camera app". It integrated **Media3 Muxer** into VideoCapture by default ("protection against video file corruption during app crashes"), made **SessionConfig** and **HighSpeedVideoSessionConfig** stable, added **ExtensionSessionConfig**, fixed ZSL with multi-camera zoom, and raised the default **minSdk from 21 to 23**.
- **1.7 alphas** add GPU-based ImageAnalysis (`OUTPUT_IMAGE_FORMAT_PRIVATE`, `ImageProxy.getHardwareBuffer()`), a Night Mode Indicator API, QHD video quality, AE/AWB locking in FocusMeteringAction, and public mirror mode.

— [CameraX release notes](https://developer.android.com/jetpack/androidx/releases/camera)

**RAW, Ultra HDR, HDR video and low light**
- **RAW/DNG**: CameraX 1.5.0 added `OUTPUT_FORMAT_RAW` (Adobe DNG) and `OUTPUT_FORMAT_RAW_JPEG`, plus `ImageCapture#takePicture` with multiple `OutputFileOptions`. Support is queried with `ImageCaptureCapabilities#getSupportedOutputFormats()` — [CameraX release notes](https://developer.android.com/jetpack/androidx/releases/camera)
- **Ultra HDR photos**:
  - Android 14 added capture of Ultra HDR compressed images in the **JPEG_R** format, which is backward compatible with SDR JPEG — [AOSP Ultra HDR](https://source.android.com/docs/core/camera/ultra-hdr)
  - CameraX exposes it as `OUTPUT_FORMAT_JPEG_ULTRA_HDR`. Initial support came in 1.4.0-alpha05, announced at I/O 2024 — [Android Authority](https://www.androidauthority.com/android-ultra-hdr-camera-apps-3460456/)
  - CameraX 1.5 added Ultra HDR together with Extensions — [CameraX release notes](https://developer.android.com/jetpack/androidx/releases/camera)
- **Ultra HDR format details**:
  - A JPEG plus a gain map (recommended at ¼ resolution) plus `hdrgm` XMP metadata; JPEG quality 85–90 is recommended.
  - Android 15+ natively encodes and decodes ISO 21496-1 gain-map metadata; `libultrahdr` supports it.
  - Invalid metadata means the SDR image is shown.

  — [Android Ultra HDR image format](https://developer.android.com/media/platform/hdr-image-format)
- **Android 16 (API 36)**, via Camera2:
  - **hybrid auto-exposure** (manual ISO or exposure time plus AE)
  - **precise color temperature and tint** controls
  - **Ultra HDR in HEIC** (`ImageFormat.HEIC_ULTRAHDR`)
  - a night-mode indicator
  - Intent actions for motion photos

  — [Android 16 features](https://developer.android.com/about/versions/16/features); [Android 16 Beta 2 blog](https://android-developers.googleblog.com/2025/02/second-beta-android16.html)
- **HLG/10-bit video**: CameraX 1.5's Feature Group API (`SessionConfig.Builder#setPreferredFeatureGroup()` / `setRequiredFeatureGroup()`, `CameraInfo#isFeatureGroupSupported`) combines HLG, Ultra HDR and 60 fps safely. 1.6 adds `VIDEO_STABILIZATION` and `UHD_RECORDING` to feature groups — [CameraX release notes](https://developer.android.com/jetpack/androidx/releases/camera)
- **Low-light and high-speed**: CameraX 1.5 added `isLowLightBoostSupported()` / `enableLowLightBoostAsync()`, `Recorder#getHighSpeedVideoCapabilities` for 120/240 fps, and torch strength — [CameraX release notes](https://developer.android.com/jetpack/androidx/releases/camera)

**Effects pipeline**
- CameraEffect arrived in CameraX 1.3. An effect targets PREVIEW, VIDEO_CAPTURE or IMAGE_CAPTURE and supplies a `SurfaceProcessor` (OpenGL) — [CameraX 1.3 beta blog](https://android-developers.googleblog.com/2023/06/camerax-13-is-now-in-beta.html); [CameraEffect reference](https://developer.android.com/reference/androidx/camera/core/CameraEffect)
- CameraX 1.4 added `OverlayEffect`, which draws with Canvas on camera outputs using `Frame#getSensorToBufferTransform`, and the `camera-effects` artifact — [What's new in CameraX 1.4.0](https://android-developers.googleblog.com/2024/12/whats-new-in-camerax-140-and-jetpack-compose-support.html)
- The **camera-media3** adapter lets Media3 effects run in the CameraX CameraEffect/SurfaceProcessor pipeline, covering Preview, VideoCapture and ImageCapture — [camera-media3 releases](https://developer.android.com/jetpack/androidx/releases/camera-media3); [CameraX 1.4 blog](https://android-developers.googleblog.com/2024/12/whats-new-in-camerax-140-and-jetpack-compose-support.html)

**Vendor Extensions**
- The five modes are Auto, Bokeh, Face Retouch, HDR and Night. There is **no video, and they cannot be used with ImageAnalysis**. Camera2 and CameraX expose the same set of extensions — [Camera extensions](https://developer.android.com/media/camera/camera-extensions)
- The supported-device list was last updated 2026-09-16. OEMs on it: CMF by Nothing, Honor, Google Pixel, Meizu, Motorola, Nothing, OnePlus, OPPO, Realme, Samsung, Sony, TECNO, Vivo, Xiaomi. The list is "not exhaustive" and support per mode varies — [Supported devices](https://developer.android.com/training/camera/supported-devices)
- Pixel 6 exposes Night Sight to third parties through extensions. Samsung Galaxy devices since the S10 series, on Android 12, expose night, bokeh and beauty — [Open Camera blog, 2022](https://sourceforge.net/p/opencamera/blog/2022/06/open-camera-now-supports-camera-vendor-extensions---including-night-sight-on-pixel-6-bokeh-on-samsung-galaxy/)
- CameraX Info (open source) lists the extensions and video resolutions exposed on a given phone — [XDA](https://www.xda-developers.com/camerax-info-list-camera2-extensions-database/); [GitHub zacharee/CameraXInfo](https://github.com/zacharee/CameraXInfo)

**OEM gap (Samsung, Log, Blackmagic, mcpro24fps)**
- A user post on the Samsung EU community (not an official Samsung statement) says:
  - Samsung limits hardware support levels; front cameras lack LEVEL_3 and YUV_REPROCESSING, so third parties cannot use the ISP pipeline for noise reduction or **ZSL**.
  - DCG, unrestricted RAW frame rates and unfiltered sensor access are locked out of Camera2 for third parties.

  — [Samsung Community post](https://eu.community.samsung.com/t5/galaxy-s25-series/urgent-feedback-why-galaxy-flagships-are-losing-to-competitors/td-p/13789498) (search-snippet level; page blocked direct fetch)
- A second user thread reports the S25 Ultra 3× camera "can't shoot high fps in third-party apps" — [Samsung Community](https://eu.community.samsung.com/t5/galaxy-s25-series/s25-ultra-3x-camera-can-t-shoot-high-fps-in-third-party-apps/m-p/11991181)
- Galaxy S25 added **Log** recording in the stock Camera app (Advanced video options → Log) — [SamMobile](https://www.sammobile.com/news/galaxy-s25-record-videos-log-heres-how-it-works/)
- **Blackmagic Camera for Android**:
  - Official support covers Samsung S21–S25/Z Fold, Pixel 6–9 (not Fold), OnePlus 11/12, Xiaomi 13/14 and Sony Xperia 1/5/Pro-I — [Blackmagic tech specs](https://www.blackmagicdesign.com/products/blackmagiccamera/techspecs/W-APP-02)
  - 2.0 (Jan 2025) added S25-series support and multicam — [PetaPixel](https://petapixel.com/2025/01/30/blackmagic-camera-2-0-on-android-adds-new-tablet-and-phone-support/)
  - 3.1 (Oct 2025) added **open gate recording and Samsung Log LUTs in record mode**. The article does not say Samsung opened Log to third parties generally — [SammyFans](https://www.sammyfans.com/2025/10/15/blackmagic-camera-samsung-log-luts-open-gate/)
  - Users on the Blackmagic forum were still asking for Samsung Log support in the app — [Blackmagic Forum](https://forum.blackmagicdesign.com/viewtopic.php?f=2&t=218106)
- **mcpro24fps**:
  - Builds its own **Log profiles through GPU tone curves** rather than relying on OEM Log, and offers on-screen "Preview LUTs" plus technical LUTs for post — [mcpro24fps technical LUTs](https://www.mcpro24fps.com/technical-luts/); [mcpro24fps Play listing](https://play.google.com/store/apps/details?id=lv.mcprotector.mcpro24fps&hl=en)
  - Needs Camera2 Limited level or higher. Some features (very high bitrates, certain resolutions, stabilisation types) "require both device support and manufacturer approval for third party apps" — [mcpro24fps full spec](https://www.mcpro24fps.com/full-specification/)

### Inferences
- **Recommended architecture:** CameraX 1.6.x for session management, Preview, VideoCapture and Ultra HDR, with a custom `SurfaceProcessor` (GLES) that owns the LUT and film effects so preview, video and stills share one shader. Use Camera2Interop (redesigned in 1.7) for manual ISO, shutter, focus and WB. Use a raw Camera2 session only for long exposure and bracketing where CameraX falls short. FilCam's listing implies it already follows this Camera2-centric path.
- **Log on Android:** no cross-OEM public "Log" capture API was found. Realistic options are to:
  - build a pseudo-Log curve in the app's own GPU tone curve (the mcpro24fps approach, which works on any 10-bit capable device), or
  - apply LUTs to OEM Log footage in post (Samsung Log footage recorded in the stock app); or
  - partner with an OEM, as Blackmagic does (not feasible for an indie).
- **Expect a quality gap versus the stock camera on Samsung** (the largest brand in Vietnam; see Q2) in low light, HDR fusion and shutter lag. Mitigations are Extensions Night/HDR (stills only, and no LUT preview on the extension output unless a CameraEffect is applied afterwards), low-light boost, Ultra HDR, and positioning around "look" rather than "sharpest image".
- **Resolution:** third-party apps usually get the default binned output (for example 12 MP from a 50/200 MP sensor), not the OEM's full-resolution remosaic mode. See Gaps.

### Gaps
- No primary source was found for **Pixel or Xiaomi Log/10-bit Log capture available to third-party apps** in 2026. Treat it as unavailable until tested.
- No authoritative per-device table was found for **maximum still resolution available to third parties versus the stock app** (50/108/200 MP remosaic). Needs device testing with CameraX Info or Camera2 characteristics dumps.
- The ZSL restrictions quoted above come from a user post, not Samsung documentation.
- No verified list was found of which mid-range Samsung A-series, OPPO, Xiaomi Redmi or Vivo models expose Night/HDR Extensions.

---

## Q2. GPU pipeline on Android: GLES vs Vulkan vs AGSL, 3D LUTs, .cube/HALD, Media3 Transformer export, and mid-range performance

### Takeaway
Use **OpenGL ES 3.x with a 3D texture LUT inside a CameraX SurfaceProcessor**, and use Media3 Transformer effects for export. This shares shader code, and Media3's `SingleColorLut` accepts N³ cubes or HALD bitmaps directly.

AGSL (Android 13+) suits UI-side stills and editing previews, but it is not the camera or encoder path. Vulkan is where the platform is heading (Android 16 defaults to Vulkan, and GLES runs through ANGLE), but GLES stays fully supported and is what CameraX and Media3 use internally.

### Cited Findings

**Media3 effects and Transformer**
- **Media3 `SingleColorLut`** (`@UnstableApi`):
  - `createFromCube(int[][][] lutCube)` takes an N×N×N cube of ARGB_8888 ints.
  - `createFromBitmap(Bitmap lut)` takes a "flattened HALD image of width N and height N²".
  - `toGlShaderProgram(context, useHdr)`: with useHdr=true, colours are in **linear RGB BT.2020**; otherwise linear BT.709.

  — [SingleColorLut reference](https://developer.android.com/reference/androidx/media3/effect/SingleColorLut)
- Media3 Transformer builds `EditedMediaItem` objects (with effects) and exports through `Transformer`. The Mar 2025 Google benchmark gives these example times:

  | Operation | 10 s 720p H.264 | 4 s 8K H.265 |
  |---|---|---|
  | Transcode | ~1300 ms | ~2300 ms |
  | Resize | ~1200 ms | ~3700 ms |

  The device used is not specified in the summary. `CompositionPlayer` gives previews — [Android Developers Blog, Mar 2025](https://android-developers.googleblog.com/2025/03/media-processing-performance-jetpack-media3-transformer.html)
- **HDR in Transformer**:
  - Default `HDR_MODE_KEEP_HDR` falls back to OpenGL tone mapping if the device can't encode HDR.
  - `TONE_MAP_HDR_TO_SDR_USING_MEDIACODEC` needs API 31+ on some devices, or API 33+ on devices with HDR capture.
  - `USING_OPEN_GL` needs API 29+.
  - SDR→HDR tone mapping is unsupported in multi-asset compositions.

  — [Media3 tone mapping](https://developer.android.com/media/media3/transformer/tone-mapping)
- Media3 added OpenGL HDR→SDR tone mapping and `ExoPlayer.setVideoEffects` for previewing video effects — [Android Developers Blog, May 2023](https://android-developers.googleblog.com/2023/05/media-transcoding-and-editing-transform-and-roll-out.html)
- On Snapdragon, HDR editing decodes HDR, applies transforms in HDR space and re-encodes HDR through HEVC — [Qualcomm docs](https://docs.qualcomm.com/bundle/publicresource/topics/80-56386-10/hdr_editing.html)
- A Flutter plugin (`lut_transformer`) already wraps .cube LUT plus intensity for Android video on top of Media3 — [pub.dev lut_transformer](https://pub.dev/packages/lut_transformer)

**AGSL, Vulkan and ANGLE**
- **AGSL / RuntimeShader** needs API 33 (Android 13). It works within the Android rendering system to customise Canvas painting and filter View content — [AGSL docs](https://developer.android.com/develop/ui/views/graphics/agsl); [Using AGSL](https://developer.android.com/develop/ui/views/graphics/agsl/using-agsl)
- A 2023 Uppsala thesis analysed RuntimeShader performance — [Uppsala thesis PDF](https://uu.diva-portal.org/smash/get/diva2:1806968/FULLTEXT01.pdf) (details not extracted)
- Android 15 ships **ANGLE** as an optional GLES-on-Vulkan layer, with the goal that GLES is "only available through ANGLE" on more new devices — [Mishaal Rahman on Threads](https://www.threads.com/@mishaal_rahman/post/C6_zHMuRdK6)
- Vulkan is Android's recommended low-level API — [Vulkan overview](https://developer.android.com/games/develop/vulkan/overview)
- Secondary reports say Android 16 makes Vulkan the default, with GL apps running through ANGLE — [PhoneArena](https://www.phonearena.com/news/android-adds-vulkan-api-support_id168457)

**LUT interpolation**
- **Tetrahedral beats trilinear.** It reaches trilinear quality with a LUT about 20–25% smaller, and was best for SDR and HDR in tests. Trilinear uses 8 lattice points, tetrahedral uses 4 — [OCIO-dev "Tetrahedral is Best"](https://groups.google.com/g/ocio-dev/c/UyPlerRNkUs)
- Resolve users see visibly better results with tetrahedral — [Colorist Factory](https://coloristfactory.com/2022/08/05/luts-in-davinci-resolve-get-way-better-results-tetrahedral-interpolation-vs-trilinear-interpolation/)
- The .cube format is text: `LUT_3D_SIZE` plus optional `DOMAIN_MIN`/`DOMAIN_MAX`, then rows of RGB floats — [colour-science discussion](https://github.com/colour-science/colour/discussions/1295)

**Mid-range devices and market (Vietnam)**
- Counterpoint Q1 2025 shipments: Samsung 28%; Xiaomi growing on the Redmi Note 14 series — [Counterpoint Vietnam Q1 2025](https://counterpointresearch.com/en/insights/vietnam-smartphone-market-q1-2025)
- Full-year 2025 shares: Samsung 26%, Apple 20% (a record), OPPO 18%, Xiaomi 17% — [TelecomLead](https://telecomlead.com/smart-phone/vietnam-smartphone-market-2025-samsung-leads-with-26-share-as-premium-ai-and-security-drive-industry-shift-124714)

### Inferences

**Recommended LUT pipeline**
- Parse .cube (17/33/65) or HALD (level 8 = 64³, level 12 = 144³) on the CPU and resample to one internal size. 33³ or 64³ is fine; Filmode already uses 64³.
- Upload as `GL_TEXTURE_3D`, RGBA8 or RGBA16F. 65³×8 B ≈ 2.2 MB for 16F (arithmetic).
- Sample with hardware trilinear for preview. Use tetrahedral in the fragment shader for final stills and export (4 texel fetches plus branch logic) where quality matters.
- Apply the LUT in the colour space it was authored for: most creative LUTs expect gamma-encoded Rec.709/sRGB input. Media3 hands `SingleColorLut` linear RGB, so check whether it re-encodes before lookup, or write a custom `GlEffect` that controls the transfer function.

**Performance targets** (inference, not benchmarked). A single LUT pass plus grain at 1080p/30 fps preview is comfortably within budget on 2023–2025 mid-range GPUs (Adreno 6xx/7xx, Mali-G57/G68/G610). The costly parts are multi-pass effects: halation or bloom need separable blurs, ideally at ¼ resolution, and 4K encoding. Targets:

| Scenario | Target |
|---|---|
| Preview, mid-range | 1080p @ 30 fps |
| Stills processing | < 1.5 s |
| Live-effect recording, mid-range | 1080p @ 30 fps |
| Live-effect recording, flagships | 4K @ 30 fps |

**4K 60 fps with live effects** should be gated per device through `isSessionConfigSupported` / feature groups.

**Video export:** Media3 Transformer with custom `GlEffect`s (LUT, grain, halation) is the lowest-effort path to a robust exporter, including HDR→SDR tone mapping. FFmpeg is heavier and brings licence and size issues.

**AGSL use:** gallery thumbnails, editor sliders and Compose UI effects. Do not put it in the camera or encoder path.

### Gaps
- No published benchmarks were found for 3D-LUT shaders at 4K on specific mid-range SoCs (Helio G99, Dimensity 7xxx, Snapdragon 6/7 Gen x) popular in Vietnam and SE Asia. Test on a device matrix: Galaxy A15/A25/A35/A55, Redmi Note 13/14, OPPO A/Reno.
- Could not confirm whether `SingleColorLut` samples trilinear or tetrahedral, or how it handles the gamma of input LUTs.
- Could not fetch Google's official Android 16 "Vulkan default" statement; the PhoneArena and Threads sources are secondary.

---

## Q3. iOS equivalents: AVFoundation, Core Image, Metal, ProRAW/Apple Log, Photographic Styles, video LUT export

### Takeaway
iOS is technically easier for a film or LUT camera. Core Image `CIColorCubeWithColorSpace` gives LUTs up to 64³ natively. Apple Log is a public capture colour space. Since iOS 26 third parties get Cinematic video, and since iOS 27 (WWDC26) 24/48 MP RAW, bracketed and processed high-resolution capture plus deferred processing. Apple's **Photographic Styles themselves are not exposed** as an API (no evidence found). The main iOS risk is App Review Guideline 4.3 (spam), not tech.

### Cited Findings

**LUTs in Core Image**
- `CIColorCubeWithColorSpace` takes a `cubeDimension` between 2 and **64** — [cifilter.io reference](https://cifilter.io/CIColorCubeWithColorSpace/)
- Open-source helpers such as SwiftCube turn .cube files into Core Image filters — [GitHub SwiftCube](https://github.com/eerimoq/SwiftCube)

**Apple Log**
- Public as `AVCaptureColorSpace.appleLog` — [Apple docs](https://developer.apple.com/documentation/avfoundation/avcapturecolorspace/applelog)
- Apple Log uses BT.2020 primaries with an Apple Log transfer. It debuted on iPhone 15 Pro, and third-party posts describe an "Apple Log 2" on iPhone 17 Pro. Blackmagic Camera iOS offers LUT preview without baking into the file — [search summary: onelut.io](https://www.onelut.io/); [Notebookcheck](https://www.notebookcheck.net/Blackmagic-Camera-for-iOS-offers-pro-video-recording-features-for-grand-total-of-free-Apple-LOG-supported-on-iPhone-15-Pro-models.751503.0.html) ("Apple Log 2" naming unverified at primary source)

**iOS 26 (WWDC25)**
- A third-party **Cinematic video** API: `isCinematicVideoCaptureEnabled`, `simulatedAperture`. Supported on iPhone 13 and later, 1080p/4K at 24/25/30 fps — [WWDC25 session 319](https://developer.apple.com/videos/play/wwdc2025/319/); [MacRumors](https://www.macrumors.com/2025/06/21/ios-26-expands-cinematic-mode-recording/)
- Audio Mix API and AirPods remote shutter for third-party apps — [Tom's Guide](https://www.tomsguide.com/phones/iphones/ios-26-lets-third-party-apps-access-these-two-big-iphone-camera-features-what-we-know)
- Capture controls (physical buttons through `AVCaptureEventInteraction`) — [WWDC25 session 253](https://developer.apple.com/videos/play/wwdc2025/253/)
- In the WWDC25 lab, Apple said that for **Deferred Photo Processing**, apps that apply a CIFilter must filter the final image and re-insert it into the photo library as an adjustment — [Apple forums: WWDC25 lab summary](https://developer.apple.com/forums/thread/791234)

**iOS 27 (WWDC26)**
- "Implement high resolution photo capture" covers RAW, exposure-bracketed and fully processed capture at **24 MP and 48 MP across Main, Tele and Ultra Wide** — [WWDC26 session 304](https://developer.apple.com/videos/play/wwdc2026/304/)
- Secondary summaries say iOS 27 extends deferred processing for "balanced" captures on iPhone 16/17, and that Deferred Start comes free for `AVCaptureVideoPreviewLayer` apps built against iOS 26+ — [blakecrosley.com](https://blakecrosley.com/blog/responsive-camera-app-ios-27) (secondary; verify against Apple docs)

**Constant Color and Photographic Styles**
- The **Constant Color** API (`isConstantColorSupported` / `isConstantColorEnabled` on `AVCapturePhotoOutput`, WWDC24) gives colour-accurate captures regardless of ambient light — [Apple: Capturing consistent color images](https://developer.apple.com/documentation/avfoundation/capturing-consistent-color-images); [WWDC24 10162](https://developer.apple.com/videos/play/wwdc2024/10162/)
- Photographic Styles are a Camera-app feature documented only in the user guide — [Apple Support](https://support.apple.com/guide/iphone/use-photographic-styles-iph629d2cd37/ios)

**PhotonCam (competitor)**
- An iOS/macOS camera app that documents converting Lightroom XMP presets to .cube for import — [PhotonCam docs](https://juniperphoton.dev/photoncam/docs/CovnertXMPToCube/)

### Inferences

**iOS stack**
- Capture: `AVCaptureSession` with `AVCaptureVideoDataOutput`.
- Preview rendering: Metal (`MTKView`) or Core Image with a Metal-backed `CIContext`.
- Recording: `AVAssetWriter` for baked-look video.
- Offline video LUT: `AVVideoComposition(asset:applyingCIFiltersWithHandler:)` with `CIColorCubeWithColorSpace`.
- Log in, Rec.709 look out: capture Apple Log (Pro models only) and apply "Log→709 + creative" LUT chains in Metal.

**Porting:** move the Android GLSL to Metal Shading Language, or wrap shared GLSL via a cross-compiler (for example SPIRV-Cross). Budget about 4–8 person-weeks per app for a native Swift port of the camera and effects core (inference).

**LUT sizes:** above 64³, Core Image's cap forces a custom Metal 3D-texture path. In practice 33³ or 64³ is enough.

### Gaps
- Not verified: any public API in iOS 26/27 that lets third parties apply or read the user's **Photographic Style / Smart Style** during capture. One search result claimed otherwise, without a primary source, so it was excluded.
- The primary Apple page for "Apple Log 2" on iPhone 17 Pro was not fetched.
- WWDC26 session content beyond titles and summaries was not transcribed.

---

## Q4. Film emulation techniques and open-source references (with licences)

### Takeaway
A convincing film look is a pipeline, not one step:

`(white balance/exposure) → tone curve/LUT (colour) → halation/bloom (highlight-driven, red-biased) → grain (luminance-dependent, per-channel, deterministic seed) → vignette/CA/distortion → overlays (leaks, dust, date stamp, frame) → encode (JPEG artifacts for the CCD look).`

LUTs can only carry the colour and tone part. Grain, halation, sharpening, vignette and local adjustments must be separate shader passes. Most "film LUT" collections carry share-alike licences and trademarked stock names in their filenames, so ship your own LUTs.

### Cited Findings

**Grain and halation**
- Realistic grain peaks in the midtones and falls off in deep shadows and clipped highlights; "a uniform add over the frame is the giveaway". Generate grain in one pass at output resolution with a **deterministic seed** (photo ID plus op ID hashed per pixel), so preview and export match. Halation is a per-channel spread where **red spreads with a larger radius than blue** — [GitHub neoworks-dev/latent issue #54](https://github.com/neoworks-dev/latent/issues/54) (developer design notes, not peer-reviewed)
- A classic shader approach to grain: variable grain size, rotating the noise coordinates to avoid directional artifacts, and reducing grain by luminance — [Martins Upitis devlog](http://devlog-martinsh.blogspot.com/2013/05/image-imperfections-and-film-grain-post.html)

**Converting presets to LUTs**
- A LUT can only change colour, contrast, brightness and gamma, **not grain, noise reduction, vignette, sharpening, clarity or dehaze**. Disable Detail, Lens, Transform and Effects when rendering a HALD identity image through a Lightroom preset — [Micro Four Nerds](https://www.microfournerds.com/blog/how-to-convert-lightroom-presets-to-luts-for-real-time-use)
- Method for building a 3D LUT from any preset or filter by processing an identity image — [Color Science on Medium](https://colorscience.medium.com/get-any-preset-filter-look-in-minutes-fb7500c67315)
- Commercial LUT generators from Lightroom presets exist (IWLTBAP LUT Generator; John Ellis' Export LUT plugin) — [IWLTBAP](https://generator.iwltbap.com/); [Export LUT](https://johnrellis.com/lightroom/exportlut.htm)

**Open-source film LUT collections and licences**
- **RawTherapee Film Simulation Collection** (Pat David): more than 400 MB of HaldCLUTs based on classic stocks. Pat David's work is **CC BY-SA 4.0** — [Pat David, 2015](https://patdavid.net/2015/03/film-emulation-in-rawtherapee/). RawPedia's page was unavailable (HTTP 503) at fetch time — [RawPedia](https://rawpedia.rawtherapee.com/Film_Simulation)
- **G'MIC**: offers more than 1,100 colour CLUTs through "Color Presets" and "Simulate Film". G'MIC is dual-licensed **CeCILL-2.1 / CeCILL-C**, and sample images are CC BY-SA 2.0. Trademarked film names in HaldCLUT filenames are "for informational purposes only" — [G'MIC color presets](https://gmic.eu/color_presets/); [Pat David, G'MIC film emulation 2013](https://patdavid.net/2013/08/film-emulation-presets-in-gmic-gimp/)
- Aggregated "largest collection" HaldCLUT pages mix sources with varying licences — [marcrphoto](https://marcrphoto.wordpress.com/the-largest-collection-of-film-simulation-haldclut-luts-brought-together/)

**Fujifilm recipe community**
- Fuji X Weekly publishes 400+ film simulation recipes (for example Kodachrome, Portra, Tri-X styles) and has free iOS and Android apps (Android 8+) with Patron-only features — [Fuji X Weekly App](https://fujixweekly.com/app/); [Google Play](https://play.google.com/store/apps/details?id=com.fujixweekly.FujiXWeekly)
- On 2026-08-20 it added **App-to-Camera recipe transfer over USB-C** — [Fuji X Weekly, 2026-08-20](https://fujixweekly.com/2026/08/20/new-send-recipes-to-your-camera-directly-from-the-fuji-x-weekly-app/)
- Another iOS app, "Film Recipes App for Fujifilm", exists — [App Store](https://apps.apple.com/us/app/id6741566252)

**Scene Disposable**
- Scene markets "parametric Kodak-inspired simulations that replicate tonal response, grain, and split-toning" for event cameras — [Scene blog](https://scenedisposable.com/blog/best-disposable-camera-app)

### Inferences

**Effect cost tiers** (inference, per frame on GPU)

| Tier | Effects |
|---|---|
| Cheap | LUT, curves, vignette, CA (radial RGB offset), date stamp, frame overlay, static dust/leak textures |
| Medium | Grain with blue-noise or hash noise; lens distortion (one remap) |
| Expensive | Halation/bloom (threshold → downsample → separable Gaussian → red-tinted add-back); CCD look (downscale, oversharpen, chroma noise, real JPEG re-encode at low quality); animated leaks in video |

**Building owned looks (recommended):**
1. Shoot a ColorChecker and grey ramp.
2. Author the looks in Resolve, darktable or Lightroom.
3. Export identity HALD → .cube.
4. Pair each LUT with a JSON "recipe" of grain, halation and vignette parameters.

This makes looks portable across photo, video, Android and iOS, and it is the natural format for preset sync or a marketplace.

**Licensing of open collections:** if you bundle CC BY-SA LUTs (RawTherapee, G'MIC-derived), you must credit them and share derivative LUTs under the same licence. Also, many of those LUTs approximate commercial products, so their provenance is murky. Use them only as references, not shipped assets.

### Gaps
- Filmulator and darktable film-emulation internals and licences were not fetched this session. Both are GPL-family (from general knowledge, unverified here), which matters if any code is copied.
- No primary source was found on the exact provenance of the RawTherapee/G'MIC HaldCLUTs (which were reportedly derived from commercial preset packs). Treat it as a legal grey zone.

---

## Q5. On-device AI: look transfer, preset recommendation, skin-tone protection, segmentation, Gemini Nano

### Takeaway
"Copy this photo's look" is now practical on-device if the model **predicts a LUT or colour matrix** rather than generating pixels. It then runs at real-time rates and exports as .cube. Segmentation for skin or sky protection is feasible with MediaPipe, but GPU delegates are unreliable on mid-range Android. Gemini Nano (ML Kit GenAI) is limited to flagship devices and is useful only for text or description features (naming looks, captions), not pixel work.

### Cited Findings

**Look transfer research**
- **Neural Preset** (CVPR 2023) uses Deterministic Neural Color Mapping, a per-pixel image-adaptive colour matrix, plus a two-stage normalise/stylise design. It enables "stable 4K color style transfer in real-time without artifacts" and reuses extracted styles as presets. Code is on GitHub — [arXiv 2303.13511](https://arxiv.org/abs/2303.13511); [GitHub ZHKKKe/NeuralPreset](https://github.com/ZHKKKe/NeuralPreset)
- **Deep Analog** (arXiv 2608.14702, Aug 10, 2026) predicts residual 3D LUTs conditioned on a single reference frame (StyleLUTNet), generalises to unseen film stocks, and exports .cube. "The color path runs in 5.2 ms at 1080p (192 FPS)" (desktop hardware implied; mobile not discussed). Code: github.com/EtonMu/deep-analog, licence not stated — [arXiv 2608.14702](https://arxiv.org/abs/2608.14702)

**Segmentation (MediaPipe)**
- MediaPipe Image Segmenter covers selfie, hair and multiclass models — [MediaPipe Image Segmenter guide](https://ai.google.dev/edge/mediapipe/solutions/vision/image_segmenter)
- Reported latencies: selfie segmenter in livestream mode on the CPU delegate averages **90+ ms on a Pixel 9**. Official Pixel 6 hair segmenter figures are **58 ms CPU / 52 ms GPU**. Users report the GPU delegate failing or crashing on some devices — [GitHub mediapipe issue #5954](https://github.com/google-ai-edge/mediapipe/issues/5954); [mediapipe-samples issue #535](https://github.com/google-ai-edge/mediapipe-samples/issues/535)
- A developer found a mid-range Android GPU delegate that "says yes and does nothing": 5 ms runs returning empty masks — [DEV Community](https://dev.to/gabbrowick/the-gpu-that-says-yes-and-does-nothing-debugging-real-time-hair-segmentation-on-mid-range-android-2990)

**Gemini Nano (ML Kit GenAI)**
- ML Kit GenAI APIs run Gemini Nano on-device for summarisation, proofreading, rewriting and **image description** (English only at launch) — [ML Kit GenAI overview](https://developers.google.com/ml-kit/genai); [Android Developers Blog, May 2025](https://android-developers.googleblog.com/2025/05/on-device-gen-ai-apis-ml-kit-gemini-nano.html)
- Supported devices include the Pixel 9 series and Galaxy S25, and the latest Gemini Nano shipped on Pixel 10 — [Android Developers Blog, Aug 2025](https://android-developers.googleblog.com/2025/08/the-latest-gemini-nano-with-on-device-ml-kit-genai-apis.html)
- An alpha **Prompt API** for custom Gemini Nano prompts arrived in Oct 2025 — [Android Developers Blog, Oct 2025](https://android-developers.googleblog.com/2025/10/ml-kit-genai-prompt-api-alpha-release.html)
- Requirements include a supported device and a locked bootloader — [Capawesome docs](https://capawesome.io/docs/sdks/capacitor/mlkit/genai-image-description/)

**Filmode Vibe**
- Already ships on-device selfie segmentation in its Photobooth — [Google Play: Filmode Vibe](https://play.google.com/store/apps/details?id=app.filmode&hl=en_US)

### Inferences

**Practical AI roadmap** (inference, 1–3 developers)
1. **"Match this photo's look"**, v1 with no ML: build a LUT by histogram or colour transfer between a user's reference photo and a neutral render. Use Reinhard-style mean/std in Lab, or per-channel CDF matching baked into a 33³ LUT. Runs in milliseconds on the CPU. About 2–3 person-weeks.
2. **v2 with ML**: port a LUT-predicting network (Neural Preset DNCM or Deep Analog style) to LiteRT. Run inference once per reference (a few hundred ms is acceptable), then the LUT runs in the normal GPU path. About 6–10 person-weeks including training and licence checks.
3. **Skin-tone protection**: run segmentation on a downscaled frame (≤256 px) only at capture, or every N frames in preview. Blend original and LUT output inside the mask. Use a CPU fallback on mid-range devices. About 2–4 person-weeks.
4. **Preset recommendation**: a scene classifier (ML Kit image labelling or a small LiteRT model) mapped to look families. About 1–2 person-weeks.
5. **Gemini Nano**: nice-to-have only (auto captions or look names on Pixel 9+/S25+). Not a core feature for the Vietnam mid-range base.

Cost: all of the above is on-device with no per-call cloud cost. Cloud generative editing is not needed for colour work.

### Gaps
- No measured mobile latency was found for Neural Preset or Deep Analog. The code licences of both must be checked before commercial use.
- No 2026 figure was found for the size of the Gemini Nano device base in Vietnam.

---

## Q6. Legal and policy risks: trademarks in filter names, LUT copyright, Google Play policies, Apple 4.3, EXIF

### Takeaway
Do not put brand or film-stock trademarks (Kodak, Portra, Fujifilm, Velvia, Classic Chrome, Polaroid, Instax, Ilford, Leica, CineStill) in **app titles, icons, store listings or look names**. Use owned coined names ("Golden", "Teal", "Instant") and keep any "inspired by" mention descriptive, if used at all. Big players (VSCO) name stocks explicitly only with a non-affiliation disclaimer, and they have brand and legal budgets an indie lacks.

Photo Picker, subscription disclosure and Apple 4.3 are the enforceable platform risks.

### Cited Findings

**Trademarks and brand naming**
- Google Play IP policy: "We don't allow apps that infringe on others' trademarks." This covers use of "logos or brand names without permission and/or in a way that could confuse users" across titles, icons, descriptions and in-app content — [Play IP policy](https://support.google.com/googleplay/android-developer/answer/9888072?hl=en)
- Developers report app removals for "alleged trademark infringement" after rights-holder complaints — [Play Developer Community thread](https://support.google.com/googleplay/android-developer/thread/225382353/app-removal-alleged-trademark-infringement?hl=en)
- **VSCO names**: preset codes such as KP1–KP9 ("Portra 160 … Portra 800"), KG1/KG2 (Gold), KC25 (Kodachrome) and KX4/KT32 (Tri-X/T-Max), with the disclaimer: "independently developed by VSCO and are neither affiliated with, sponsored by, nor endorsed by Kodak or Eastman Kodak Company… used here for descriptive purposes only" — [VSCO Kodak presets](https://www.vsco.co/features/film-filters/kodak-presets)
- **Kodak brand shift (March 2026)**: Kodak renamed **Portra → "Ektacolor Pro"** and **T-Max → "Ektapan"**. The reason given is the post-2012 split between Eastman Kodak (manufacturing) and Kodak Alaris (consumer film distribution and branding), which left trademark control complicated — [Fuji X Weekly, 2026-03-26](https://fujixweekly.com/2026/03/26/kodak-renames-portra-and-t-max/)
- **Polaroid vs Fujifilm**: Polaroid sent Fujifilm a cease-and-desist over the Instax Square format and presentation. This shows instant-film trade dress is actively policed — [Light Stalking](https://www.lightstalking.com/polaroid-fujifilm-clashing-instant-film-trademarks/)
- "roidizer", a Polaroid-effect app, was pulled from Google Play by its developer over "copyright issues" (low-quality source; details unverified) — [AlternativeTo](https://alternativeto.net/software/roidizer/about)
- Fujifilm uses "Film Simulation" as its own product term and brand page — [Fujifilm X film simulation](http://www.fujifilm-x.com/en-us/products/film-simulation/)

**Copyright and licences of LUTs**
- The RawTherapee/Pat David collection is **CC BY-SA 4.0** and G'MIC is CeCILL, so shipping derived LUTs imposes attribution and share-alike duties (see Q4) — [Pat David](https://patdavid.net/2015/03/film-emulation-in-rawtherapee/); [G'MIC](https://gmic.eu/color_presets/)

**Google Play: photos, storage and EXIF**
- **Photo & Video Permissions policy**:
  - Apps may request `READ_MEDIA_IMAGES`/`READ_MEDIA_VIDEO` only if system pickers are insufficient for core functionality.
  - Qualifying core use is exemplified by gallery or photo-management apps; **photo editors are not listed** as automatically qualifying.
  - Everyone else must use the Photo Picker.
  - Enforcement started Jan 22, 2025, and full compliance was mandatory by **May 28, 2025**.

  — [Play Console Help: Photo & Video permissions](https://support.google.com/googleplay/android-developer/answer/14115180?hl=en); [Play Console Help: Jan 22, 2025 actions](https://support.google.com/googleplay/android-developer/answer/15800983?hl=en); [Android Authority](https://www.androidauthority.com/google-force-android-photo-picker-3491650/)
- Android 14 added **partial access to photos and videos** (user-selected subset) — [Android 14 partial access](https://developer.android.com/about/versions/14/changes/partial-photo-video-access)
- On Android 10+, apps "don't need storage-related permissions to access and modify media files that your app owns". A camera app can save its own shots to MediaStore without READ_MEDIA_*. Unredacted EXIF GPS from other apps' photos needs `ACCESS_MEDIA_LOCATION` — [Android: Access media files](https://developer.android.com/training/data-storage/shared/media)
- Google's 2025 blog frames Photo Picker as the privacy default — [Android Developers Blog, Apr 2025](https://android-developers.googleblog.com/2025/04/google-play-empowering-developers-to-build-user-trust-through-privacy.html)

**Google Play: subscriptions**
- Offers must disclose price, billing frequency, auto-renewal, trial conversion and whether a subscription is required. The dismiss button must be visible.
- Explicitly prohibited:
  - showing a monthly breakdown when the charge is annual upfront
  - showing only intro prices
  - "Free Trial" SKU names on auto-renewing subscriptions
  - subscriptions for one-time benefits
  - multi-screen flows that trick users into subscribing
  - incomplete localisation of terms
- Subscriptions must provide "sustained or recurring value".

— [Play Console Help: Subscriptions](https://support.google.com/googleplay/android-developer/answer/9900533?hl=en)

**Apple App Review**
- The **June 9, 2026** guideline update tightened 4.3. Apps in oversaturated categories "may be removed from the App Store going forward if they are not updated, improved, or do not attract customers", and "opportunistically creating variants of existing app categories… degrades App Store discovery". Named categories include dating, flashlight, sound effects, wallpaper, simple timers and fortune telling; camera filters are not explicitly named — [MacRumors, 2026-06-09](https://www.macrumors.com/2026/06/09/app-store-guidelines-low-quality-apps/)
- Commentary on 2026 4.3(b) enforcement and appeals: appeal with concrete differentiators — [AppCompliance](https://appcompliance.io/blog/apple-2026-app-review-guideline-changes/); [AppCompliance 4.3(a)](https://appcompliance.io/blog/apple-guideline-4-3-spam-rejection/)

### Inferences

**Naming policy for the team**
- Coined look names; no stock or brand names in titles, keywords, screenshots or look names.
- If "inspired-by" copy is used, keep it in long-form help text, never in the store title, with a VSCO-style disclaimer.
- Rename frames like "Polaroid" to "Instant" (the Filmode Vibe listing currently uses "Polaroid" as a frame name).
- Avoid replicating the Instax/Polaroid frame proportions plus logo placement exactly (trade dress).
- The Kodak renaming shows even Kodak's own marks are in flux, so there is no upside to using them.

**Monetising three apps under one developer**
- Differentiate each app clearly (camera vs editor vs video) to avoid Apple 4.3 "variants" findings.
- On iOS, consider one app with modes, or clearly separate value propositions.
- A shared paywall SDK must meet Play's disclosure rules in Vietnamese and English (localisation of terms is explicitly required).

**Photo editors**
- Use the Photo Picker (Android 11+ backport via Google Play services) for "open a photo".
- Do not request `READ_MEDIA_IMAGES` unless building a full gallery. Filmode Vibe's gallery-style "board" may tempt broad access, but its own shots do not need it.

**EXIF**
- Preserve EXIF for own captures and add a Software tag.
- Offer "strip location on share".
- Only request `ACCESS_MEDIA_LOCATION` if re-exporting imported photos with GPS intact.

### Gaps
- No documented **cease-and-desist or takedown** against a mobile filter app specifically for naming a look "Portra", "Velvia", "Classic Chrome" or "Leica" was found. Absence of evidence is not safety.
- The exact Google Play "Impersonation" policy text was not fetched (only the IP policy).
- Vietnamese IP law aspects (trademark registration of Kodak/Fujifilm marks in Vietnam, NOIP enforcement) were not researched.

---

## Q7. Opportunity gaps: feasible in 2026, poorly served, with rough effort for a 1–3 developer team

### Takeaway
The best-evidenced gaps are those Android platform changes (CameraX 1.5/1.6 RAW, HLG and effects; Media3 LUT effects; Android 16 hybrid AE) now make cheap, but mainstream film-camera apps still ignore:
- real-time LUT preview on **Android video** with pseudo-Log/HLG and a matching exporter
- one **portable look format** shared across photo and video and across Android and iOS
- **"copy this photo's look" to .cube**
- **event/shared disposable cameras with film looks**, a validated market (POV, Lense, Scene) with little Vietnam/SEA localisation

### Cited Findings
- Blackmagic Camera (Android) offers LUT preview only on its supported flagship list, and its Android LUTs are Rec.709 — [Blackmagic tech specs](https://www.blackmagicdesign.com/products/blackmagiccamera/techspecs/W-APP-02); [search summary incl. Blackmagic 3.x LUT notes](https://www.sammyfans.com/2025/10/15/blackmagic-camera-samsung-log-luts-open-gate/)
- mcpro24fps offers Preview LUTs and GPU Log curves, but it is a pro-oriented manual video tool — [mcpro24fps technical LUTs](https://www.mcpro24fps.com/technical-luts/)
- Media3 offers `SingleColorLut` and HDR tone mapping, so a LUT exporter needs no FFmpeg — [SingleColorLut](https://developer.android.com/reference/androidx/media3/effect/SingleColorLut); [Media3 tone mapping](https://developer.android.com/media/media3/transformer/tone-mapping)
- CameraX feature groups (HLG, 60 fps, UHD, stabilisation), high-speed video and CameraEffect support in SessionConfig are now stable (1.6) — [CameraX release notes](https://developer.android.com/jetpack/androidx/releases/camera)
- **Event disposable-camera apps**:
  - POV: a QR code opens a disposable camera with no app download, host approval, photobooks and video — [POV](https://pov.camera/); [App Store](https://apps.apple.com/us/app/pov-disposable-camera-events/id1636032890)
  - Lense: QR code with no download; claims "over 100,000" couples, planners and venues — [Lense](https://lense.app/)
  - Scene: "parametric Kodak-inspired simulations" — [Scene](https://scenedisposable.com/blog/best-disposable-camera-app)
- The Fujifilm recipe community is large (400+ recipes) and now pushes recipes to real Fujifilm cameras. The recipes are JPEG settings for Fujifilm bodies, not phone looks — [Fuji X Weekly App](https://fujixweekly.com/app/); [Fuji X Weekly, 2026-08-20](https://fujixweekly.com/2026/08/20/new-send-recipes-to-your-camera-directly-from-the-fuji-x-weekly-app/)
- PhotonCam (iOS) already imports Lightroom XMP presets converted to .cube, and Filmode Vibe imports ".cube LUTs and Lightroom-style presets" — [PhotonCam](https://juniperphoton.dev/photoncam/docs/CovnertXMPToCube/); [Filmode Vibe](https://play.google.com/store/apps/details?id=app.filmode&hl=en_US)
- Deep Analog (Aug 2026) and Neural Preset show reference-to-LUT prediction is a solved research problem with public code — [arXiv 2608.14702](https://arxiv.org/abs/2608.14702); [arXiv 2303.13511](https://arxiv.org/abs/2303.13511)
- Filmode Vibe already has Google-sign-in Cloud Boards joinable by code, plus a web viewer — [Filmode Vibe](https://play.google.com/store/apps/details?id=app.filmode&hl=en_US)

### Inferences

**Opportunity table.** All effort figures are inferences. Person-weeks (pw) assume developers familiar with the existing Filmode/FilCam codebase, with Android first; iOS ports are listed separately.

| # | Opportunity | Why underserved (evidence above) | Feasibility 2026 | Android effort | iOS port | Key risks |
|---|---|---|---|---|---|---|
| 1 | **Video LUT camera for everyone**: live LUT, grain and halation on 1080p/4K video recording (not 15 s clips) with a pseudo-Log or HLG profile toggle | Blackmagic is limited to its flagship list with Rec.709 LUTs; mcpro24fps is pro-only; mainstream film apps cap or skip video | High: CameraX VideoCapture + CameraEffect + feature groups | 8–12 pw (reuses the existing LUT shader) | 6–8 pw (AVAssetWriter + Metal) | Mid-range thermals at 4K; per-device QA; audio sync |
| 2 | **Video LUT/color tool (editor)**: apply .cube, look recipes and Log→709 (Samsung Log, Apple Log, pseudo-Log) to existing clips; batch export via Media3 | Most phone editors support only basic filters; Samsung Log users need LUTs (Samsung itself adds Log LUTs only in One UI 8.5 editing) | High: Media3 Transformer + `SingleColorLut`/custom `GlEffect` + HDR tone mapping | 6–10 pw | 5–8 pw (AVVideoComposition + CIColorCube) | HDR edge cases; long 4K export time; Photo Picker for video input |
| 3 | **Portable look format + cross-device sync (photo and video)**: one "look" = .cube + JSON recipe (grain, halation, vignette, frame) shared across all three apps and platforms | No mainstream app syncs one look across camera, photo and video on both OSes (inference from the feature lists reviewed) | High | 3–5 pw (schema, Firebase/Supabase sync, import/export) | 2–3 pw | Account friction; sync conflicts |
| 4 | **"Copy this photo's look" → .cube** | Research code exists (Neural Preset, Deep Analog); consumer apps rarely export a real LUT | Medium–High | v1 statistical: 2–3 pw; v2 ML: 6–10 pw | +2–4 pw | Model licence; users uploading copyrighted reference photos is fine for private use, but a public marketplace of "copied looks" needs moderation |
| 5 | **Creator preset/LUT marketplace** (VN/SEA creators sell looks; revenue share) | Presets are mostly sold off-platform (Etsy, creators' sites); in-app sale of digital looks must use Play Billing/IAP | Medium (payments, payouts, moderation, IP takedowns) | 10–16 pw including backend and admin | +4 pw | Play/App Store billing rules for creator payouts; trademark-named uploads (a notice-and-takedown process is needed); Apple 1.2 UGC duties (June 2026) |
| 6 | **Event/wedding shared disposable camera** with film looks, delayed "develop", host moderation, QR join, web capture | POV, Lense and Scene prove demand; no evidence of Vietnamese-localised players; Filmode already has Cloud Boards | High (the web camera via getUserMedia + WebGL LUT is simpler than native) | 6–10 pw (web capture + board moderation + print/export) | Web covers iOS guests | Storage/bandwidth cost per event; privacy of guest photos; Apple 1.2 UGC rules |
| 7 | **Fujifilm-recipe-style camera for any phone**: parametric recipes (film sim base, grain roughness, colour chrome, WB shift, DR, highlight/shadow tone) mapped to shaders; import community recipes as text | Recipe apps only serve Fujifilm bodies | Medium–High technically; **legal: must avoid Fujifilm names ("Classic Chrome", "Velvia", "Film Simulation")** | 4–6 pw on top of the existing camera | 3–4 pw | Trademark; recipe authors' copyright in their write-ups (use parameters, not text) |
| 8 | **Skin-tone-protected looks** (portrait-safe LUTs via segmentation) | Filmode already has segmentation; rare in film apps | Medium (GPU delegate reliability on mid-range) | 2–4 pw | 2 pw (Vision person segmentation) | Latency on low-end devices; halo artefacts |
| 9 | **Ultra HDR film photos** (look applied to both the SDR base and the gain map) | Ultra HDR is supported in CameraX; film apps output SDR JPEG only (inference) | Medium: must edit base and gain map consistently (ISO 21496-1) | 3–5 pw | iOS gain-map HEIC: 3–4 pw | Viewer support; banding |

**Suggested 3-app scoping**, given the existing assets:
- **App A**, a real-time film camera: Filmode Vibe/FilCam, adding opportunities 1, 7 and 9.
- **App B**, a preset/LUT photo editor: extend the existing editor with opportunities 3, 4, 8, and later 5.
- **App C**, a video LUT/color tool: opportunity 2, sharing the look format from opportunity 3.

Opportunity 6 (event camera) is a strong alternative to App C if the team prefers B2C2B revenue (couples and planners) over creator subscriptions.

**Performance and QA budget:** reserve about 20–25% of each app's effort for a device matrix. At minimum: Samsung Galaxy A-series and S-series, Xiaomi Redmi Note, OPPO A/Reno, Vivo Y/V, and one Pixel. These cover about 80% of Vietnam's Android shipments by brand (Samsung 26%, OPPO 18%, Xiaomi 17% in 2025) — [TelecomLead](https://telecomlead.com/smart-phone/vietnam-smartphone-market-2025-samsung-leads-with-26-share-as-premium-ai-and-security-drive-industry-shift-124714). The ~80% figure is an inference that also counts vivo and others as part of Android.

### Gaps
- No quantitative data was found on how many mainstream film apps (Dazz, Huji, FIMO, etc.) support long video with live LUTs in 2026. The "underserved" judgement for opportunity 1 rests on the feature lists of the apps reviewed, not a systematic audit.
- No Vietnam-specific data was found on demand for event disposable cameras, or on presence of POV/Lense/Scene in Vietnam.
- Effort estimates are engineering judgement, not benchmarked. Validate with a 2-week spike on the device matrix before committing.
