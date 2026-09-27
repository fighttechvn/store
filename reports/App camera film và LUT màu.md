# Lõi LUT của Filmode đủ nuôi ba app

Người dùng đang bỏ "filter VSCO" và "preset Lightroom" để tìm ba thứ mới: **máy ảnh digicam/CCD kiểu Y2K**, **công thức màu kiểu Fujifilm** và **LUT màu cho video**. Trên Google, trong ba năm trước giai đoạn dữ liệu bị nhiễu, "digicam" tăng 5,96 lần toàn cầu (19 lần ở Mỹ, 13,7 lần ở Indonesia), "fujifilm recipes" tăng 5,4 lần và "cube lut" tăng 2 lần. Cùng lúc, "lightroom presets" chỉ còn 0,66 lần và "vsco" 0,51 lần so với năm 2022. Ngách app chụp film rất lớn về lượt cài: khoảng **343 triệu lượt cài Google Play** trên 38 app được kiểm tra. Tiền lại dồn về iOS. **Dazz Cam** không có bản Android chính chủ nhưng ước thu khoảng **$900k/tháng** chỉ từ iOS. Các app Android trên 10 triệu lượt cài như ProCCD, Kapi Cam và OldRoll chỉ thu $8–20k/tháng (ước tính Sensor Tower). Gần như app nào cũng freemium: cho miễn phí một bộ look nhỏ, rồi thu tiền để mở toàn bộ máy ảnh hoặc look, hoặc thu lúc lưu và xuất ảnh. Giá phổ biến ở Mỹ là $0.99–2.99 cho mỗi máy, $9.99–29.99/năm, trọn đời $13.99–39.99. Nguyên nhân số một của đánh giá 1★ là **paywall hồi tố**, tức thu tiền thứ từng miễn phí, chứ không phải mức giá. Filmode và FilCam của đội đã có phần kỹ thuật khó nhất: LUT 64³ chạy GPU ngay trên kính ngắm, điều khiển thủ công qua Camera2, RAW DNG và nhập file .cube. Nhưng hai app mới có **69 và 327 lượt cài** và chưa vào top 30 của từ khóa chung nào. Báo cáo đề xuất ba app dùng chung một định dạng look: **(1) tái định vị Filmode thành máy ảnh digicam/film có chế độ sự kiện**, **(2) một app mới tên Filmode Studio cho công thức màu và LUT ảnh**, **(3) nâng FilCam thành máy quay LUT và RAW**. Về nền tảng, nên ra Google Play trước để lấp các khoảng trống trên Android và lấy lượt cài. Tuy vậy, app nào cũng phải có bản iOS trong vòng một đến hai quý, vì iOS biến người tải thành người trả tiền với tỷ lệ cao gấp khoảng 2,9 lần và giữ phần lớn doanh thu của ngách.

## Người dùng tìm digicam, công thức màu và LUT, bỏ dần VSCO

### Google Trends bị nhiễu từ tháng 8/2025, nên chỉ tin mức tăng trước đó

Trước khi đọc số liệu, cần biết một cái bẫy. Từ tháng 8/2025, Google Trends thổi phồng các truy vấn tiếng Anh ít người tìm. Ba từ khóa đối chứng trung tính là "weather app", "calculator app" và "flashlight app" tăng 2,2–3,0 lần sau tháng 8/2025 dù nhu cầu thật không đổi, trong khi từ phổ biến "calculator" gần như đứng yên (0,87 lần) ([Google Trends](https://trends.google.com/trends/explore?date=today%205-y&q=weather%20app)). Giới marketing cũng đã cảnh báo rằng giờ đây "từ khóa nào cũng đang trending" ([Marketing Experts Hub](https://b2b.marketingexpertshub.com/p/google-trends-is-broken-why-does)). Vì vậy, việc "film camera app" nhảy từ 5 lên 77 điểm trong đúng tháng 8/2025, tức tăng 8,3 lần, là nhiễu chứ không phải bùng nổ ([Google Trends](https://trends.google.com/trends/explore?date=today%205-y&q=film%20camera%20app)). Báo cáo này đo xu hướng thật bằng **tỷ lệ trước nhiễu**: lấy trung bình giai đoạn 10/2024–6/2025 chia cho trung bình 10/2021–6/2022. Kết quả được đối chiếu thêm với chỉ số YouTube Search, nơi không có bước nhảy tháng 8/2025.

Đo theo cách đó, có ba cụm nhu cầu tăng thật.

Cụm **digicam/CCD/Y2K** tăng mạnh nhất. "Digicam" tăng 5,96 lần toàn cầu, 19 lần ở Mỹ, 13,7 lần ở Indonesia và 6,9 lần ở Đức. Tháng 8–9/2026 nó vẫn ở đỉnh 5 năm, trong khi các từ đối chứng đã hạ nhiệt ([Google Trends](https://trends.google.com/trends/explore?date=today%205-y&q=digicam)). Trên YouTube Search, "digicam" tăng 9,6 lần rồi giữ mức cao suốt 2025–2026 ([Google Trends – YouTube](https://trends.google.com/trends/explore?date=today%205-y&gprop=youtube&q=digicam)). Riêng "y2k camera" đi lên từ một nền rất nhỏ, vọt đỉnh trong tháng 3–5/2026 rồi rơi lại. Đó là dấu hiệu của một mốt ngắn hạn ([Google Trends](https://trends.google.com/trends/explore?date=today%205-y&q=y2k%20camera)).

Cụm **công thức màu / film simulation** tăng đều. "Fujifilm recipes" tăng 5,44 lần, "fuji recipe" 2,34 lần, "film simulation" 2,35 lần ([Google Trends](https://trends.google.com/trends/explore?date=today%205-y&q=fujifilm%20recipes)). Trên YouTube, "fuji recipe" đạt đỉnh 5 năm vào tuần 14/6/2026 ([Google Trends – YouTube](https://trends.google.com/trends/explore?date=today%205-y&gprop=youtube&q=fuji%20recipe)). Ở Nhật, lượt tìm "フィルムシミュレーション" (film simulation) trong tháng 8–9/2026 cao gấp 2,57 lần cùng kỳ 2024 ([Google Trends JP](https://trends.google.com/trends/explore?date=today%205-y&q=%E3%83%95%E3%82%A3%E3%83%AB%E3%83%A0%E3%82%B7%E3%83%9F%E3%83%A5%E3%83%AC%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3&geo=JP)).

Cụm **LUT / color grading** tăng nhờ thói quen quay video Log trên điện thoại. "Luts" tăng 1,6 lần, "cube lut" 2,04 lần, "color grading" 1,88 lần ([Google Trends](https://trends.google.com/trends/explore?date=today%205-y&q=cube%20lut)). Hai truy vấn liên quan tăng nhanh nhất là "lut màu blackmagic camera" (+1.950%, một truy vấn tiếng Việt nổi lên ở cấp toàn cầu) và "apple log lut" ([Google Trends](https://trends.google.com/trends/explore?date=today%2012-m&q=lut)).

Ngoài ba cụm trên, "dazz cam" tăng 1,8 lần toàn cầu và 2,3 lần ở Brazil. Đi kèm là các truy vấn "dazz cam app for android" (+130%) và "apps like dazz cam" (+100%) ([Google Trends](https://trends.google.com/trends/explore?date=today%2012-m&q=dazz%20cam)). Người dùng Android đang đi tìm một Dazz cho máy của mình.

Chiều ngược lại, **VSCO** giảm còn 0,51 lần toàn cầu, 0,10 lần ở Việt Nam và 0,16 lần ở Indonesia ([Google Trends](https://trends.google.com/trends/explore?date=today%205-y&q=vsco)). "Lightroom presets" còn 0,66 lần toàn cầu, trên YouTube chỉ còn 0,41 lần. "Preset lightroom" còn 0,52 lần ở Việt Nam và 0,28 lần ở Indonesia ([Google Trends](https://trends.google.com/trends/explore?date=today%205-y&q=lightroom%20presets)). "Huji cam" còn 0,44 lần. Nhu cầu preset không biến mất mà đổi hình: các truy vấn liên quan tăng nhanh là "film presets for lightroom" (+90%) và "film lightroom presets" (+70%) ([Google Trends](https://trends.google.com/trends/explore?date=today%2012-m&q=lightroom%20presets)). Người dùng vẫn muốn "màu film", chỉ là họ không còn tìm theo tên VSCO hay Lightroom nữa.

**Bảng 1 — Từ khóa: xu hướng thật và cách dùng** (tỷ lệ trước nhiễu = trung bình 10/2024–6/2025 ÷ trung bình 10/2021–6/2022; TG = toàn cầu; dữ liệu kéo ngày 27/9/2026)

| Cụm từ khóa | Thị trường mạnh | Xu hướng thật | Kết luận | Dùng cho | Nguồn |
|---|---|---|---|---|---|
| digicam | PH, SG, ID, US, DE | TG 5,96×; US 19×; ID 13,7×; DE 6,9×; YouTube 9,6× | Tăng mạnh, đỉnh 5 năm vào T8–9/2026 | App 1 | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=digicam) |
| ccd camera / ccd cam | HK, SG, MY, VN, KR | TG 1,3× (lẫn nhu cầu mua máy thật) | Tăng nhẹ | App 1 | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=ccd%20camera) |
| y2k camera | US, JP, KR | Từ nền rất nhỏ; đỉnh T3–5/2026 rồi rơi | Mốt ngắn, dùng làm từ phụ | App 1 | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=y2k%20camera) |
| dazz cam, dazz cam android, apps like dazz cam | MM, PH, ID, VN, BR | TG 1,8×; BR 2,3×; VN tăng 3,3× đến 2024 rồi đi ngang | Khoảng trống trên Android; không dùng tên "Dazz" | App 1 | [GT](https://trends.google.com/trends/explore?date=today%2012-m&q=dazz%20cam) |
| disposable camera app | US | 2,8× (đỉnh 4/2025) | Tăng thật, nghiêng về app sự kiện | App 1 (sự kiện) | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=disposable%20camera%20app) |
| fujifilm recipes, fuji recipe, film simulation | SG, AU, US, JP | 5,44×; 2,34×; 2,35×; JP năm 2026 gấp 2,2–2,6× năm 2024 | Tăng thật, trên Play còn ít đối thủ | App 2 | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=fujifilm%20recipes) |
| luts, cube lut, lut app | US, JP, KR, DE | 1,6×; 2,04×; 3,4× | Tăng thật, nhờ video Log | App 3, App 2 | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=cube%20lut) |
| color grading | US, ID, BR, DE | TG 1,88×; BR 4,6× | Tăng thật | App 3 | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=color%20grading) |
| lut màu | VN | 4,15× từ nền nhỏ; "lut màu blackmagic camera" +1.950% | Tăng thật | App 3 | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lut%20m%C3%A0u&geo=VN) |
| màu film, ảnh film, máy ảnh film | VN | 0,88–1,02×; "máy ảnh film" đạt đỉnh 5 năm tuần 30/8/2026 | Ổn định, nhu cầu thẩm mỹ bền | App 1, App 2 | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=m%C3%A0u%20film&geo=VN) |
| film grain | US, VN | 1,33× (phần tăng sau 2025 bị thổi phồng) | Tăng nhẹ, ít đối thủ | App 1, App 2 | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=film%20grain) |
| lightroom presets / preset lightroom | BD, LK, PH, VN, ID, BR | TG 0,66×; VN 0,52×; ID 0,28×; YouTube 0,41× | Giảm, thị trường đã bão hòa | Chỉ dùng biến thể "film presets" | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=lightroom%20presets) |
| vsco, vsco filter | VN, ID, BR | TG 0,51×; VN 0,10×; ID 0,16× | Giảm mạnh | Tránh | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=vsco) |
| huji cam | TG | 0,44× | Giảm | Tránh | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=huji%20cam) |
| app chụp ảnh, app chỉnh màu, công thức màu | VN | 0,51×; 0,26×; 0,39× (lẫn nghĩa nhuộm tóc) | Giảm trên Google | Chỉ dùng "công thức màu fujifilm" | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=app%20ch%E1%BB%89nh%20m%C3%A0u&geo=VN) |
| film camera app, film filter | TG, US | Nhảy 8,3× và 7,3× sau T8/2025, vượt ngưỡng đối chứng 2,2–3× | Nhiễu, không phải tăng thật | Vẫn là từ khóa tốt trong store | [GT](https://trends.google.com/trends/explore?date=today%205-y&q=film%20camera%20app) |

### Người Việt tìm "màu film" trên Google, còn tìm app thì tìm thẳng trong store

Trên Google, các truy vấn chung về app ở Việt Nam đang giảm. "App chụp ảnh" còn 0,51 lần, "app chỉnh màu" 0,26 lần, "công thức màu" 0,39 lần; từ cuối cùng lại bị lẫn với công thức màu nhuộm tóc ([Google Trends](https://trends.google.com/trends/explore?date=today%205-y&q=app%20ch%E1%BB%A5p%20%E1%BA%A3nh&geo=VN)). Ngược lại, nhu cầu thẩm mỹ vẫn giữ được. "Màu film" và "ảnh film" đi ngang ở mức cao; riêng "ảnh film" trong tháng 8–9/2026 cao gấp 1,44 lần cùng kỳ 2024. "Máy ảnh film" đạt đỉnh 5 năm vào tuần 30/8/2026 ([Google Trends](https://trends.google.com/trends/explore?date=today%205-y&q=m%C3%A1y%20%E1%BA%A3nh%20film&geo=VN)). "Lut màu" tăng 4,15 lần, dù từ một nền nhỏ.

"Dazz cam" ở Việt Nam tăng 3,3 lần từ 2022 đến 2024 rồi đi ngang. Tuy vậy, câu hỏi "cách tải dazz cam cho android" vẫn tăng 150% ([Google Trends](https://trends.google.com/trends/explore?date=today%2012-m&q=dazz%20cam&geo=VN)), nghĩa là người dùng Android Việt Nam vẫn đang tìm cách có được trải nghiệm của Dazz.

Gợi ý tự động của Google cho thấy người Việt gõ gì. "App chụp ảnh film" được nối thành "miễn phí", "android", "có con thỏ", "lắc tay", "trung quốc" ([Google Suggest](https://suggestqueries.google.com/complete/search?client=firefox&hl=vi&gl=vn&q=app%20ch%E1%BB%A5p%20%E1%BA%A3nh%20film)). "Màu film" được nối thành "kodak gold 200", "fuji 400", "kodak ultramax 400" ([Google Suggest](https://suggestqueries.google.com/complete/search?client=firefox&hl=vi&gl=vn&q=m%C3%A0u%20film)). "Công thức màu" gợi ý "fujifilm" đầu tiên, sau đó toàn là màu nhuộm tóc ([Google Suggest](https://suggestqueries.google.com/complete/search?client=firefox&hl=vi&gl=vn&q=c%C3%B4ng%20th%E1%BB%A9c%20m%C3%A0u)).

Trong Google Play Việt Nam, gợi ý tự động lại phong phú hơn nhiều: "film cam", "dazz cam chụp ảnh", "ccd pro", "digicam y2k", "grainy", "polaroid dazz cam" ([Google Play VN](https://play.google.com/store/search?q=film%20camera&c=apps&gl=VN)). Hệ quả thực tế: khi chọn từ khóa tiếng Việt cho ASO, nên dựa vào gợi ý và thứ hạng trong store thay vì Google Trends.

### Store và mạng xã hội cho thấy cùng một bức tranh

Trong store, các từ khóa đầu (head term) đều là từ chung cộng phong cách: film camera, retro camera, vintage camera, film filter, ccd, digicam, y2k camera, disposable camera và dazz. Cùng ba app là OldRoll, ProCCD và "Vintage Film Camera – Digicam" của ZANKHANA chiếm top 3 cho hầu hết các từ này ở Mỹ, Việt Nam, Indonesia, Nhật và Hàn ([Google Play US](https://play.google.com/store/search?q=film%20camera&c=apps&gl=US)). Nhóm từ đầu vì thế rất khó cho app mới.

Ngược lại, một số trường kết quả mỏng, cũ hoặc chất lượng thấp, và đó là chỗ app mới có thể chen vào. Với từ khóa "lut", app #1 trên Play Mỹ chỉ có hơn 10 nghìn lượt cài, còn 3DLUT mobile dù có 17 triệu lượt cài đã ngừng cập nhật từ 7/2024 ([Google Play](https://play.google.com/store/search?q=lut&c=apps&gl=US)). Với "fuji film filter", FujiStyle chỉ có hơn 10 nghìn lượt cài ([Google Play](https://play.google.com/store/search?q=fuji%20film%20filter&c=apps&gl=US)). Với "film grain", app đứng #1 có hơn 50 nghìn lượt cài. Ở Việt Nam, từ "preset" đã có Fimii, một app mới hơn 5 nghìn lượt cài, lọt vào top. Theo thang độ phổ biến 5–100 của ASOTools (không ghi ngày), "dazz cam" được 52 điểm, "lightroom presets" 44, "disposable camera" 41 và "film camera" 37, trong khi độ khó của "film camera", "disposable camera" và "lightroom presets" chỉ 18–20 ([ASOTools](https://asotools.io/app-store-keywords/film-camera); [ASOTools](https://asotools.io/app-analytics/dazz-cam-keyword-monitoring)).

Mạng xã hội khuếch đại cùng xu hướng. Số liệu hashtag TikTok dưới đây là ảnh chụp không ghi ngày, nhiều khả năng từ trước 2024. #y2k có 26,6 tỷ lượt xem ([HashtagRadar](https://hashtagradar.com/hashtag/y2k/)). #digicam có 567 triệu lượt xem, trung bình khoảng 19,8 nghìn lượt mỗi bài ([HashtagRadar](https://hashtagradar.com/hashtag/digicam/)). Con số trung bình này cao gấp ba lần #vsco (6,4 nghìn) ([HashtagRadar](https://hashtagradar.com/hashtag/vsco/)), tức là nội dung digicam đang thiếu so với nhu cầu. #colorgrading có 902 triệu lượt xem ([HashtagRadar](https://hashtagradar.com/hashtag/colorgrading/)).

Thị trường phần cứng cũng đi cùng chiều. Theo số liệu CIPA, lượng máy ảnh ống kính liền (compact) xuất xưởng năm 2025 tăng khoảng 30% ([DPReview](https://www.dpreview.com/articles/2386206926/cipa-data-2025-camera-lens-shipments-fixed-lens-cameras-interchangable/)), và từ tháng 1 đến tháng 4/2026 lượng xuất xưởng hằng tháng vẫn bằng 117–148% cùng kỳ 2025 ([PetaPixel](https://petapixel.com/2026/06/11/compact-camera-sales-are-still-booming-amid-growing-photo-industry/)). Ở Việt Nam, báo chí mô tả Gen Z đang "hồi sinh" máy compact cũ giá 3–5 triệu đồng ([CafeBiz](https://cafebiz.vn/tung-bi-smartphone-khai-tu-dong-may-anh-20-nam-tuoi-bat-ngo-hoi-sinh-gen-z-dang-tao-nen-thi-truong-trieu-usd-176260619070655028.chn)). Apple vừa thêm điều chỉnh độ hạt (grain) vào Photographic Styles nhưng chỉ cho iPhone 18 Pro ([MacRumors](https://www.macrumors.com/2026/09/22/apple-backtracks-camera-feature-compatibility/)), nên toàn bộ máy Android và các iPhone đời cũ vẫn cần app bên thứ ba để có hiệu ứng film.

## Android giữ lượt cài, iOS giữ doanh thu

Cộng bộ đếm lượt cài trên trang Google Play của 38 app máy ảnh film được kiểm tra (xem Bảng 2) cho ra khoảng **343,1 triệu lượt cài**, trong đó 12 app lớn nhất chiếm khoảng 299 triệu và các app ra mắt từ 2020 trở đi chiếm khoảng 124 triệu. Tăng trưởng đã chuyển hẳn sang thế hệ digicam/CCD. Kapi Cam tăng từ 5 lên 10 triệu lượt cài chỉ trong khoảng 3/1–5/4/2026 ([AndroidRank](https://www.androidrank.org/application/x/com.sensemobile.action)), ProCCD tăng từ 1 lên 10 triệu trong khoảng 4/2023–5/2025 ([AndroidRank](https://www.androidrank.org/application/proccd_digital_film_camera/com.cerdillac.proccd)), và app của ZANKHANA đi từ 0 lên 4,6 triệu lượt cài trong khoảng 14 tháng ([AndroidRank](https://www.androidrank.org/application/x/filmcamera.vintagecamera.digitalcamera.retrocamera)). Trong khi đó, thế hệ 2018 (Huji, Kuji, Foodie) đã chững lại, mỗi app còn tối đa khoảng 30 nghìn lượt tải/tháng trên Android.

Về doanh thu, lưu ý rằng mọi con số tải và doanh thu dưới đây đều là **ước tính Sensor Tower** cho "tháng gần nhất", nhiều khả năng là tháng 8/2026. Số liệu không đổi khi thay tham số quốc gia, nên nhiều khả năng đây là số toàn cầu theo từng nền tảng. Nhóm app chụp film cốt lõi trên iOS ước thu khoảng **$1,44 triệu/tháng**, riêng Dazz chiếm khoảng $900k, tức khoảng 60% ([Sensor Tower – Dazz](https://app.sensortower.com/overview/1422471180?country=US)).

### Bảng thống kê app chụp film, retro và digicam

**Bảng 2 — App chụp film/retro/digicam** (lượt cài Play là bộ đếm chính xác mà Play nhúng trong trang, dữ liệu ngày 27/9/2026; ST = Sensor Tower, ước tính tháng gần nhất; iOS = số đánh giá ở store Mỹ)

| App (nhà phát triển) | Lượt cài Play | Điểm Play (số đánh giá) | ST Android/tháng: tải / doanh thu | iOS: số đánh giá (điểm) | ST iOS/tháng: tải / doanh thu | Xếp hạng, tăng trưởng nổi bật |
|---|---|---|---|---|---|---|
| [Dazz Cam](https://apps.apple.com/us/app/id1422471180) (DAZZ PTE. LTD., SG) | Không có bản chính chủ | — | — | 114.851 (4,75) | 2 triệu / **$900k** | iOS top free: BR #5, ID #9, TH #13, VN #14, US #24; top grossing BR #15, ID #15, VN #30 |
| [Huji Cam](https://play.google.com/store/apps/details?id=kr.co.manhole.hujicam&hl=en&gl=US) (Manhole, KR) | 46,16 triệu | 3,59 (190K) | 10k / <$5k | 11.960 (4,22) | 90k / <$5k | Làn sóng 2018, đã chững lại |
| [Foodie](https://play.google.com/store/apps/details?id=com.linecorp.foodcam.android&hl=en&gl=US) (SNOW, KR) | 42,27 triệu | 3,58 (132K) | 30k / $10k | 9.319 (4,74) | 30k / $100k | iOS grossing KR #26, VN #28 |
| [OldRoll](https://play.google.com/store/apps/details?id=com.accordion.analogcam&hl=en&gl=US) (accordion, CN) | 40,05 triệu | 4,27 (213K) | 400k / $20k | 5.589 (4,71) | 200k / $90k | Top 1–2 cho "film camera" trên Play US/VN |
| [Kuji Cam](https://play.google.com/store/apps/details?id=com.ginnypix.kujicam&hl=en&gl=US) (GinnyPix) | 32,83 triệu | 3,97 (180K) | <5k / <$5k | Chỉ có trên Android | — | Đã chững lại |
| [Fomz](https://play.google.com/store/apps/details?id=com.imendon.fomz&hl=en&gl=US) (CN) | 31,67 triệu | 4,51 (90K) | n/a | 1.215 (4,71) | 200k / $10k | 1 triệu → 10 triệu trong khoảng 6/2023–3/2025 |
| [ProCCD](https://play.google.com/store/apps/details?id=com.cerdillac.proccd&hl=en&gl=US) (CN) | 22,23 triệu | 4,83 (198K) | 600k / $8k | 2.134 (4,74) | 200k / $60k | #1 Play cho "ccd camera" và "digicam"; Play VN Photography top free #10 |
| [Dazzil Cam](https://play.google.com/store/apps/details?id=com.camerafilm.lofiretro&hl=en&gl=US) (bên thứ ba) | 20,35 triệu | 4,14 (86K) | 100k / n/a | — | — | Mượn tên Dazz trên Android |
| [Kapi Cam](https://play.google.com/store/apps/details?id=com.sensemobile.action&hl=en&gl=US) (TETRAS.AI, HK) | 16,33 triệu | 4,58 (66K) | **1 triệu** / $9k | 1.657 (4,70) | 300k / $7k | Play ID top free #13, BR #26; iOS ID top free #21 |
| [NOMO CAM](https://play.google.com/store/apps/details?id=com.blink.academy.nomopro&hl=en&gl=US) (CN) | 9,75 triệu | 3,73 (13,6K) | 20k / <$5k | 48.176 (4,66) | 20k / $30k | iOS VN top free #15; #1 trên Play VN cho "chụp ảnh film" |
| [Vintage Film Camera – Digicam](https://play.google.com/store/apps/details?id=filmcamera.vintagecamera.digitalcamera.retrocamera&hl=en&gl=US) (ZANKHANA, SG) | 4,63 triệu | 4,75 (109K) | 600k / $9k | 128 (4,79) | <5k / <$5k | Ra mắt 11/7/2025; #1 Play US cho "film camera" |
| [POV – Disposable Camera Events](https://play.google.com/store/apps/details?id=com.untitledshows.pov&hl=en&gl=US) | 1,28 triệu | 4,80 (6,5K) | 100k / **$80k** | — | — | App sự kiện; doanh thu trên mỗi lượt tải Android cao nhất trong nhóm |
| [y2k: 2000s photo editor](https://play.google.com/store/apps/details?id=com.abel.y2k&hl=en&gl=US) | 1,10 triệu | 4,85 (22K) | 80k / <$5k | — | — | Ra mắt 14/12/2025 |
| [1998 Cam](https://play.google.com/store/apps/details?id=com.aaai.cam1998&hl=en&gl=US) (AAAI Studio) | 136.898 (đăng lại năm 2026) | 4,44 (785) | 30k / <$5k | 40.249 (4,80) | 80k / $10k | Người đã mua trọn đời bị đòi trả tiền lại |
| [ism](https://apps.apple.com/us/app/id1580668065) (MWM) | — | — | — | 11.248 (4,73) | 100k / $200k | iOS US top free #50, top grossing #83 |
| [101cam](https://apps.apple.com/us/app/id6781998623) (SNOW) | — | — | — | 89 (4,65) | 60k / <$5k | Ra mắt 10/7/2026; iOS top free KR #1, BR #3, JP #14 |

Số ước tính tải và doanh thu lấy từ các trang tổng quan Sensor Tower của từng app, ví dụ [Kapi Android](https://app.sensortower.com/overview/com.sensemobile.action?country=US), [ProCCD Android](https://app.sensortower.com/overview/com.cerdillac.proccd?country=US), [OldRoll iOS](https://app.sensortower.com/overview/1570093460?country=US) và [POV](https://app.sensortower.com/overview/com.untitledshows.pov?country=US).

Bảng này cho thấy ba điều. **Thứ nhất, tên tuổi đắt nhất ngách lại vắng mặt trên Android.** Không tìm thấy bản Android nào của DAZZ PTE. LTD.; mọi kết quả "Dazz" trên Play đều của nhà phát triển khác ([Google Play](https://play.google.com/store/search?q=dazz+cam&c=apps&hl=en&gl=US)), và các app mượn tên đang hưởng lượng tìm kiếm đó. Dazzil có 20,3 triệu lượt cài. Một app tên "Dazz Cam" của MA CLO APPS ra mắt ngày 30/8/2026 đã vượt 100 nghìn lượt cài trong chưa đầy một tháng và đứng #42 top grossing mục Photography ở Brazil ([AppBrain](https://www.appbrain.com/stats/google-play-rankings/top_grossing/photography/br)).

**Thứ hai, Android kiếm tiền rất kém với app máy ảnh film.** Kapi thu khoảng $0,009 trên mỗi lượt tải Android, ProCCD khoảng $0,013. OldRoll thu khoảng $0,05/lượt tải trên Android, so với khoảng $0,45 trên iOS. Ngoại lệ là app sự kiện: POV chỉ có 100 nghìn lượt tải Android mỗi tháng nhưng ước thu $80k, gần gấp 9 lần Kapi dù Kapi có 1 triệu lượt tải.

**Thứ ba, cạnh tranh đang nóng lên.** SNOW tung 101cam vào tháng 7/2026 và app này lên #1 top free ở Hàn Quốc chỉ sau 11 tuần ([iTunes RSS KR](https://itunes.apple.com/kr/rss/topfreeapplications/limit=100/genre=6008/json)). Năm 2026 cũng có loạt app mới dường như của nhà phát triển Việt Nam: Fimii, Rollie, Eluvo, DiscCam. Quốc tịch của các nhà phát triển này suy ra từ tên, chưa xác minh.

### Bảng thống kê app preset, công thức màu và LUT

**Bảng 3 — App chỉnh ảnh preset/công thức và app LUT/video** (cùng nguồn và quy ước như Bảng 2)

| App | Loại | Lượt cài Play | Điểm Play (số đánh giá) | iOS: số đánh giá ở Mỹ | ST iOS/tháng | ST Android/tháng | Ghi chú |
|---|---|---|---|---|---|---|---|
| [Lightroom](https://play.google.com/store/apps/details?id=com.adobe.lrmobile&hl=en&gl=US) | Chỉnh ảnh | 470,9 triệu | 4,47 (3,66M) | 336.826 | 1M / $5M | 6M / $1M | Play Photography top grossing #2–11 ở cả 7 thị trường kiểm tra ([bảng Play VN](https://play.google.com/store/apps/category/PHOTOGRAPHY?hl=en&gl=VN)) |
| [VSCO](https://play.google.com/store/apps/details?id=com.vsco.cam&hl=en&gl=US) | Preset | 164,5 triệu | 3,62 (1,33M) | 277.508 | 400k / $2M | 300k / $60k | iOS US grossing #22; trên Play chỉ vào top 50 grossing ở BR và DE |
| [Hypic](https://play.google.com/store/apps/details?id=com.xt.retouchoversea&hl=en&gl=US) | AI + preset film | 122,7 triệu | 3,09 (262K) | 17.172 | 1M / $800k | 3M / $200k | iOS VN grossing #5 |
| [Prequel](https://play.google.com/store/apps/details?id=com.prequel.app&hl=en&gl=US) | Filter | 63,1 triệu | 4,52 (394K) | 343.946 | 700k / $2M | 300k / $200k | iOS US grossing #25 |
| [Tezza](https://play.google.com/store/apps/details?id=org.tezza&hl=en&gl=US) | Preset | 9,96 triệu | 3,66 (12,9K) | 47.293 | 300k / $2M | 30k / $10k | iOS US grossing #23; không vào top 50 nào trên Play |
| [Afterlight](https://play.google.com/store/apps/details?id=com.fueled.afterlight&hl=en&gl=US) | Preset film | 11,4 triệu | 2,71 (60,8K) | 20.664 | <5k / $20k | <5k / <$5k | Có gói trọn đời |
| [Darkroom](https://apps.apple.com/us/app/id953286746) | Chỉnh film chuyên sâu | Chỉ có trên iOS | — | 29.354 | <5k / $30k | — | Không có bản Android |
| [RNI Films](https://apps.apple.com/us/app/id1017098672) | Giả lập film | Chỉ có trên iOS | — | 9.062 | 8k / $20k | — | Không có bản Android |
| [Dehancer](https://apps.apple.com/us/app/id6443648413) | Giả lập film | Chỉ có trên iOS | — | 430 | <5k / $20k | — | Không có bản Android |
| [FLTR](https://play.google.com/store/apps/details?id=com.feelty&hl=en&gl=US) | Thư viện preset DNG | 30,0 triệu | 4,57 (419K) | 81.073 | n/a | n/a | Sống bằng quảng cáo; không vào top grossing nào |
| [Koloro](https://play.google.com/store/apps/details?id=com.cerdillac.persetforlightroom&hl=en&gl=US) | Preset | 40,2 triệu | 4,80 (431K) | 2.335 | n/a | n/a | Bản Play ngừng cập nhật từ 27/6/2024 |
| [Fimii](https://play.google.com/store/apps/details?id=com.ankii.fimii&hl=en&gl=VN) (indie VN) | Preset film | 8.736 | 4,89 ở VN (229) | 24 (VN: 865) | 10k / <$5k | n/a | iOS VN top free #11, grossing #49; Play VN Photography top free #14 |
| [Fuji X Weekly](https://play.google.com/store/apps/details?id=com.fujixweekly.FujiXWeekly&hl=en&gl=US) | Công thức Fujifilm | 407.926 | 4,44 (875) | — | — | <5k | Gói ủng hộ (Patron) $19.99/năm |
| [FujiStyle](https://play.google.com/store/apps/details?id=com.fujistylelead.global&hl=en&gl=US) | Công thức | 21.872 | 4,40 (632) | 363 | <5k / $10k | — | iOS VN grossing #85 |
| [3DLUT mobile](https://play.google.com/store/apps/details?id=com.lutmobile.lut&hl=en&gl=US) | LUT | 17,4 triệu | 3,88 (29,6K) | — | — | — | Cập nhật cuối ngày 29/7/2024 |
| [LUT Generator](https://play.google.com/store/apps/details?id=lut.generator.luts&hl=en&gl=US) | LUT | 13.685 | 4,20 (88) | — | — | — | #1 trên Play US cho "lut" |
| [Blackmagic Camera](https://play.google.com/store/apps/details?id=com.blackmagicdesign.android.blackmagiccam&hl=en&gl=US) | Quay chuyên nghiệp, miễn phí | 3,92 triệu | 4,59 (14,6K) | 23.056 | 1M tải | 300k tải | Nhập .cube; chỉ hỗ trợ một danh sách máy flagship |
| [mcpro24fps](https://play.google.com/store/apps/details?id=lv.mcprotector.mcpro24fps&hl=en&gl=US) | Quay chuyên nghiệp, $19.99 trả trước | 16.241 | 4,57 (4K) | — | — | <5k / <$5k | Tự làm Log bằng đường cong GPU |
| [Leica LUX](https://apps.apple.com/us/app/id6477182657) | Camera pro + look | — | — | 7.619 | 60k / $300k | — | iOS DE grossing #31 |
| [PeekLut](https://apps.apple.com/us/app/id6473661560) / [LUT Studio](https://apps.apple.com/us/app/id6479377583) | LUT (iOS) | — | — | 654 / 725 | n/a | — | $34.99/năm; $29.99–49.99/năm |
| [CapCut](https://play.google.com/store/apps/details?id=com.lemon.lvoverseas&hl=en&gl=US) | Chỉnh video | 2,01 tỷ | 3,56 (13M) | 1.122.051 | 11M / $58M | 22M / $15M | Top 1–4 ở mọi thị trường; theo các hướng dẫn bên thứ ba, bản mobile không nhập được LUT |
| [VN](https://play.google.com/store/apps/details?id=com.frontrow.vlog&hl=en&gl=US) (Ubiquiti) | Chỉnh video | 333,9 triệu | 4,71 (5,5M) | 317.787 | 1M / $200k | 5M / $70k | Nhập LUT miễn phí |

Bảng 3 cho thấy **ba khoảng trống trên Android**. Khoảng trống thứ nhất là app giả lập film cao cấp: Darkroom, RNI Films và Dehancer chỉ có trên iOS, dù mỗi app ước thu $20–30k/tháng mà không cần lượng cài lớn ([Sensor Tower – Darkroom](https://app.sensortower.com/overview/953286746?country=US)). Khoảng trống thứ hai là LUT: nhu cầu có thật vì 3DLUT mobile đạt 17,4 triệu lượt cài, nhưng app này đã bị bỏ bê, còn các app mới ra (CameLUT, ColorShaper, Modipix) đều dưới 10 nghìn lượt cài, trong khi trên iOS cùng loại công cụ bán được $35–60/năm. Khoảng trống thứ ba là công thức màu: Fuji X Weekly và FujiStyle cộng lại chưa tới nửa triệu lượt cài trên Play. Ngược lại, các app thư viện preset Lightroom như FLTR và Koloro có hàng chục triệu lượt cài nhưng sống bằng quảng cáo và không lọt top grossing nào, dấu hiệu rõ rằng preset đã thành hàng phổ thông, khó thu tiền.

Trường hợp đáng chú ý nhất với đội là **Fimii**. Đây là app preset film của lập trình viên độc lập Lê Nguyễn Khoa ([fimii.app](https://fimii.app/about)); trang của app không ghi quốc gia, nhưng tên tác giả và tên hiển thị "Fimii: Chỉnh Ảnh Film" trên Sensor Tower cho thấy app nhắm vào người Việt ([Sensor Tower – Fimii](https://app.sensortower.com/overview/6755296366?country=US)). App chỉ bán một gói trọn đời $9.99, không có gói thuê bao. Chỉ sau khoảng 7 tháng, Fimii đã lên #11 top free iOS Việt Nam và #14 top free Photography trên Play Việt Nam ([iTunes RSS VN](https://itunes.apple.com/vn/rss/topfreeapplications/limit=200/genre=6008/json)).

### Bảng xếp hạng cho thấy Việt Nam là thị trường màu film

**Bảng 4 — Thứ hạng app film/retro/công thức màu, iOS Photo & Video, ngày 27/9/2026**

| Thị trường | Top free | Top grossing | Nguồn |
|---|---|---|---|
| Việt Nam | Fimii #11, Dazz #14, NOMO #15, Foodie #49, OldRoll #52, Fomz #56, ProCCD #62, Rollie #73, Eluvo #78, DiscCam #86 | Foodie #28, Dazz #30, Fimii #49, OldRoll #80, Leica LUX #82, FujiStyle #85, Rollie #93, Eluvo #100 | [free](https://itunes.apple.com/vn/rss/topfreeapplications/limit=100/genre=6008/json), [grossing](https://itunes.apple.com/vn/rss/topgrossingapplications/limit=100/genre=6008/json) |
| Hàn Quốc | 101cam #1, Dazz #18, ProCCD #76, Foodie #85 | Foodie #26, Dazz #29, 101cam #53, BerryFilm #59, filmhwa #62 | [free](https://itunes.apple.com/kr/rss/topfreeapplications/limit=100/genre=6008/json), [grossing](https://itunes.apple.com/kr/rss/topgrossingapplications/limit=100/genre=6008/json) |
| Nhật | 101cam #14, Pixie+ #18, Dazz #35, OldRoll #73 | Foodie #40, Dazz #52, Leica LUX #68, OldRoll #82 | [free](https://itunes.apple.com/jp/rss/topfreeapplications/limit=100/genre=6008/json) |
| Indonesia | Dazz #9, Kapi #21, OldRoll #58, Fomz #59, ProCCD #68 | Dazz #15, Leica LUX #75, OldRoll #92 | [free](https://itunes.apple.com/id/rss/topfreeapplications/limit=100/genre=6008/json) |
| Thái Lan | Dazz #13, Fomz #34, ProCCD #65, Kapi #96 | Dazz #32, Foodie #42, Fomz #80 | [free](https://itunes.apple.com/th/rss/topfreeapplications/limit=100/genre=6008/json) |
| Brazil | 101cam #3, Dazz #5, OldRoll #85 | Dazz #15 | [free](https://itunes.apple.com/br/rss/topfreeapplications/limit=100/genre=6008/json) |
| Mỹ | Dazz #24, ism #50, 101cam #54, Huji #71 | ism #83 (Dazz ngoài top 100) | [free](https://itunes.apple.com/us/rss/topfreeapplications/limit=100/genre=6008/json) |
| Đức | Leica LUX #36, Dazz #39 | Leica LUX #31, Dazz #100 | [free](https://itunes.apple.com/de/rss/topfreeapplications/limit=100/genre=6008/json) |

Trên Google Play, bảng xếp hạng mục Photography của AppBrain cho thấy cùng các tên đó. Ở Brazil, Kapi đứng #26, ProCCD #38 và OldRoll #46 top free ([AppBrain BR](https://www.appbrain.com/stats/google-play-rankings/top_free/photography/br)). Ở Indonesia, Kapi đứng #13 và app của ZANKHANA #26 ([AppBrain ID](https://www.appbrain.com/stats/google-play-rankings/top_free/photography/id)). Ở Mỹ, không có app máy ảnh film thuần nào trong top 100 free vì danh sách bị app AI chiếm hết ([AppBrain US](https://www.appbrain.com/stats/google-play-rankings/top_free/photography/us)). AppBrain không cung cấp bảng xếp hạng cho Việt Nam và Thái Lan.

Gộp lại, Việt Nam, Indonesia, Thái Lan, Hàn Quốc và Brazil là năm thị trường mạnh nhất cho app film. Riêng ở Việt Nam, 8 app liên quan đến màu film nằm trong top 100 grossing iOS, cho thấy người dùng Việt không chỉ tải mà còn trả tiền cho màu film. Mỹ và Đức nghiêng về "camera chuyên nghiệp kèm look" (Leica LUX) hơn là máy ảnh film vui.

### Filmode và FilCam có đủ kỹ thuật nhưng gần như chưa có phân phối

**Bảng 5 — Hồ sơ ba listing hiện có của đội (27/9/2026)**

| | Filmode Vibe (Android, `app.filmode`) | Filmode (iOS, id 6791145420) | FilCam (Android, `app.filmode.filcam`) |
|---|---|---|---|
| Ra mắt | 22/7/2026 | 22/7/2026 | 4/9/2026 |
| Lượt cài / đánh giá | 69 lượt cài; chưa đủ đánh giá để hiện điểm | 0 đánh giá; Sensor Tower ước <5k lượt tải/tháng | 327 lượt cài; chưa đủ đánh giá để hiện điểm |
| Danh mục | **Productivity** (không phải Photography) | Photo & Video | Photography |
| Nội dung chính | 18 look miễn phí + 25 look Pro; 10 hiệu ứng thời gian thực; 3 kiểu máy (Toy, Instant, Pro); video tối đa 15 giây; photobooth tách nền; bảng ghim ảnh (board) trên cloud | Hơn 200 look trong 10 gói; cuộn phim 12/24/36 kiểu; Match Photo; nhập .cube và .xmp; video 4K; 20 ngôn ngữ | Chế độ P/S/I/M; RAW DNG miễn phí; 43 look; LUT 64³ in thẳng vào JPEG; phơi sáng dài, bracketing, focus stacking thuộc gói Pro |
| Giá | $2.99–29.99 mỗi mục (VN: 78.000–777.000đ) | $1.99/tháng; $4.99/3 tháng; $14.99/năm; $19.99 trọn đời; gói look lẻ $0.99–2.99; pass sự kiện Group/Party/Wedding $2.99/$9.99/$49.99 | $0.99–9.99 mỗi mục (VN: 26.000–260.000đ); dùng thử 7 ngày với gói năm |
| Hiển thị khi tìm kiếm | Chỉ đứng top khi tìm tên "filmode" | — | #24 cho "raw camera", #29 cho "manual camera" (Mỹ) |
| Vấn đề đã thấy | Người dùng báo lỗi không lưu được ảnh (8/9); tên khung "Polaroid" là nhãn hiệu; xếp sai danh mục | Nội dung khác xa bản Android | Người dùng báo lỗi không lưu được ảnh (8/9); chưa có bản iOS |

Nguồn: [Google Play – Filmode Vibe](https://play.google.com/store/apps/details?id=app.filmode&hl=en&gl=US), [App Store – Filmode](https://apps.apple.com/us/app/id6791145420), [Google Play – FilCam](https://play.google.com/store/apps/details?id=app.filmode.filcam&hl=en&gl=US), [Google Play search "filmode"](https://play.google.com/store/search?q=filmode&c=apps&gl=US).

Hai app đã có phần khó nhất: một pipeline LUT trên GPU dùng chung cho preview, ảnh và video; điều khiển thủ công qua Camera2; ghi DNG; và tách nền người ngay trên máy. Khoảng cách với đối thủ vì thế nằm ở **phân phối và định vị**, không nằm ở công nghệ.

Hiện tại "Filmode" chưa có lượng tìm kiếm đo được trên Google ([Google Trends](https://trends.google.com/trends/explore?date=today%205-y&q=filmode)), và Filmode Vibe không lọt top 30 cho bất kỳ từ khóa film nào ở Mỹ hay Việt Nam. Việc xếp app vào danh mục Productivity làm tình hình tệ thêm, vì mọi đối thủ đều nằm trong bảng xếp hạng Photography. Bản Android và bản iOS của Filmode cũng đã tách thành hai sản phẩm khác nhau: Android có 43 look, còn iOS có hơn 200 look, thêm cuộn phim và pass sự kiện. Cùng tài khoản nhà phát triển còn 10 app tiện ích ra mắt trong khoảng 18–26/9/2026, tất cả đều 0+ lượt cài ([Google Play](https://play.google.com/store/apps/dev?id=7730541199735528284&hl=en&gl=US)). Đó là dấu hiệu của chiến lược phát hành nhiều app; với nguồn lực nhỏ, dồn sức cho ba app film trong báo cáo này sẽ cho kết quả tốt hơn.

## Người dùng trả tiền để sở hữu, bỏ đi khi bị lấy lại thứ đã có

### Tính năng trả phí và mức giá của các app chính

Cách chặn trả phí phổ biến nhất trong ngách là giới hạn **kích thước kho máy ảnh/look** cộng với **thu tiền lúc lưu hoặc xuất**. Nhiều app cho xem trước look Pro trực tiếp rồi mới thu tiền khi lưu: Filmode Vibe ("chỉ khi giữ ảnh mới hỏi"), Darkroom ("xuất ảnh cần Darkroom+"), Dehancer (giới hạn số lần xuất). Ngoài kho look, các tính năng hay bị khóa là nhập ảnh có sẵn (Huji, NOMO PRO), tắt thời gian "tráng phim" (NOMO PRO), bỏ watermark và quảng cáo (FIMO), video 4K và video không watermark (Filmode iOS), chỉnh hàng loạt, RAW, masking và AI (Lightroom, VSCO Pro), tạo hoặc xuất LUT (tính năng biến Match thành LUT của Filmode, xuất 3D LUT của Mattebox Pro), và các chế độ chụp chuyên sâu (FilCam) ([App Store – Mattebox](https://apps.apple.com/us/app/id452438265); [App Store – NOMO](https://apps.apple.com/us/app/id1362548649)).

Ngược lại, **nhập .cube miễn phí ở mọi app có hỗ trợ** (Filmode, FilCam, VN, Blackmagic), và chụp RAW thường cũng miễn phí. Hai thứ này là mức tối thiểu của thị trường, không phải lý do để người dùng trả tiền ([App Store – Filmode](https://apps.apple.com/us/app/id6791145420); [darkroom.co](https://darkroom.co/darkroom+)).

**Bảng 6 — Tính năng trả phí và giá** (giá App Store lấy từ mục In-App Purchases ngày 27/9/2026; Play chỉ công bố khoảng giá mỗi mục; giá VN là giá App Store Việt Nam trừ khi ghi khác)

| App | Mô hình | Miễn phí gồm | Trả phí mở ra | Giá US | Giá VN |
|---|---|---|---|---|---|
| [Filmode iOS](https://apps.apple.com/us/app/id6791145420) (đội) | Thuê bao + trọn đời + gói lẻ + pass | Cuộn 12 kiểu; một số bộ look; nhập .cube/.xmp; xuất ảnh không watermark | Mọi look; chỉnh hàng loạt; quang học ống kính; cuộn 24/36; video 4K không watermark; biến Match thành LUT | $1.99/tháng; $14.99/năm; $19.99 trọn đời; gói $0.99–2.99; pass $2.99/$9.99/$49.99 | 59.000đ/tháng; 499.000đ/năm; 599.000đ trọn đời; Wedding Pass 1.499.000đ |
| [Filmode Vibe](https://play.google.com/store/apps/details?id=app.filmode&hl=en&gl=US) (đội) | Thuê bao + trọn đời | Mọi kiểu máy, hiệu ứng, trình sửa, photobooth; 18 look; nhập .cube | 25 look nữa; phơi sáng dài; vệt sáng; paywall hiện khi lưu | $2.99–29.99/mục | 78.000–777.000đ/mục (Play) |
| [FilCam](https://play.google.com/store/apps/details?id=app.filmode.filcam&hl=en&gl=US) (đội) | Thuê bao (gói năm dùng thử 7 ngày) + trọn đời | Chỉnh tay, RAW DNG, LUT film | Chụp đêm, bracketing, focus stacking, intervalometer, phơi sáng dài | $0.99–9.99/mục | 26.000–260.000đ/mục (Play) |
| [Dazz Cam](https://apps.apple.com/us/app/id1422471180) | Thuê bao + mua một lần + từng máy | Một số máy | Mọi máy và phụ kiện | Pro $6.99; mua một lần $19.99; mỗi máy $0.99–2.99 | Pro 99.000đ; mua một lần 299.000đ |
| [OldRoll](https://apps.apple.com/us/app/id1570093460) | VIP + trọn đời + từng máy; có quảng cáo trên Android | Vài máy | Mọi máy | $4.49–4.99/tháng; $12.99–19.99/năm; trọn đời $17.99–27.99 | 329.000–399.000đ/năm; 499.000đ trọn đời |
| [ProCCD](https://apps.apple.com/us/app/id1616113199) | VIP tuần/năm + trọn đời + từng máy; có quảng cáo trên Android | Một số máy | Mọi máy | $2.99/tuần; $5.99–8.99/năm; trọn đời $13.99–17.99 | 149.000–229.000đ/năm; 299.000–399.000đ trọn đời |
| [Kapi Cam](https://apps.apple.com/us/app/id6740760807) | Tuần/tháng/năm/trọn đời | Một số máy | Tất cả | $4.99/tuần; $9.99–12.99/tháng; $69.99–89.99/năm; $149 trọn đời | 19.000đ/tuần; 599.000–1.499.000đ/năm |
| [NOMO CAM](https://apps.apple.com/us/app/id1362548649) | Từng máy + PRO theo năm | Vài máy giá $0 | Mọi máy; nhập ảnh; tắt thời gian tráng | PRO $24.99/năm; mỗi máy $0.99–1.99 | 579.000đ/năm |
| [FIMO](https://apps.apple.com/us/app/id1454219307) | Từng cuộn film + Pro theo năm | Vài cuộn, kèm watermark và quảng cáo | Bỏ watermark và quảng cáo; mọi chất liệu | $0.99–1.99/cuộn; $29.99/năm | 29.000đ/cuộn |
| [1998 Cam](https://apps.apple.com/us/app/id1450480287) | Thuê bao + trọn đời | Vài filter | Toàn bộ | $1.99–5.99/tháng; $15.99–29.99/năm; $39.99 trọn đời | 369.000–999.000đ/năm; 1.199.000đ trọn đời |
| [Huji Cam](https://apps.apple.com/us/app/id781383622) | Mua một lần | Camera | Nhập ảnh; bỏ quảng cáo | $0.99 | 29.000đ |
| [VSCO](https://apps.apple.com/us/app/id588013838) | Plus/Pro | 15–16 preset | Hơn 200 preset; chỉnh video; AI | Plus $9.99/tháng, $39.99/năm; Pro $14.99/$69.99 (mua trên web rẻ hơn: $29.99/$59.99 mỗi năm) | Plus 799.000đ/năm |
| [Lightroom](https://apps.apple.com/us/app/id878783582) | Premium theo dung lượng | Chỉnh ảnh cơ bản | Masking; AI; RAW từ máy khác | $3.99/tuần đến $49.99/năm (100GB); $19.99/năm (40GB) | 469.000đ/năm (40GB) |
| [Darkroom](https://darkroom.co/darkroom+) | Thuê bao + trọn đời | Dùng mọi công cụ nhưng không xuất | Xuất ảnh | $9.99/tháng; $39.99/năm; $99.99 trọn đời | 499.000đ/năm; 2.999.000đ trọn đời |
| [RNI Films](https://apps.apple.com/us/app/id1017098672) | Thuê bao + gói film | Gói film nhập môn | Các gói film | $0.99–1.99/tháng; $9.99/năm; mỗi gói $3.99 | 229.000đ/năm; mỗi gói 119.000đ |
| [Dehancer](https://apps.apple.com/us/app/id6443648413) | Tính theo lượt xuất | Khoảng 10 lượt xuất (số liệu 2023) | Xuất không giới hạn | $4.99–9.99/tháng; $49.99–89.99/năm | 1.299.000–2.299.000đ/năm |
| [Afterlight](https://apps.apple.com/us/app/id1293122457) | Thuê bao + trọn đời | Vài preset | Hơn 300 preset | $1.99/tuần; $15.99–23.99/năm; $19.99–39.99 trọn đời | 419.000–599.000đ/năm |
| [Fimii](https://apps.apple.com/us/app/id6755296366) | Mua đứt | Trình sửa ảnh | Các phần premium | $9.99 trọn đời | 263.000đ (Play VN) |
| [FujiStyle](https://apps.apple.com/us/app/id6504739559) | Thuê bao | — | Công thức, khung | $3.99/tháng; $9.99/quý; $14.99/năm | — |
| [PeekLut](https://apps.apple.com/us/app/id6473661560) / [LUT Studio](https://apps.apple.com/us/app/id6479377583) | Thuê bao | — | Gói Peek+ / LUT Studio Pro (nhập .cube, xem trước LUT thời gian thực, xuất bản chỉnh thành LUT) | $2.99/tuần, $34.99/năm / $29.99–49.99/năm | — |
| [mcpro24fps](https://play.google.com/store/apps/details?id=lv.mcprotector.mcpro24fps&hl=en&gl=US) | Trả trước | Có app demo riêng | Toàn bộ | $19.99 | — |
| [POV](https://play.google.com/store/apps/details?id=com.untitledshows.pov&hl=en&gl=US) | Trả theo sự kiện | — | Gói theo quy mô sự kiện (số khách, số ảnh mỗi khách) | $4.99–119.99/mục | — |
| [Blackmagic Camera](https://apps.apple.com/us/app/blackmagic-camera/id6449580241) | Miễn phí hoàn toàn | Tất cả | — | $0 | $0 |

Từ bảng giá rút ra bốn mốc tham chiếu ở Mỹ. App máy ảnh retro bán từng máy $0.99–2.99, thuê bao $1.99–5.99/tháng hoặc $9.99–29.99/năm, và trọn đời $13.99–39.99. App chỉnh ảnh cao cấp như VSCO, Darkroom, Tezza thu $39.99–89.99/năm. Gói theo tuần chủ yếu xuất hiện ở app AI hoặc của nhà phát hành lớn (Kapi, Prequel, Picsart). Công cụ LUT chuyên nghiệp thu $35–60/năm.

Ở Việt Nam có một điểm quan trọng với đội. Filmode đang dùng thang giá quy đổi mặc định của Apple: 499.000đ/năm và 599.000đ trọn đời. Các đối thủ thì hạ giá riêng cho Việt Nam. Dazz Pro chỉ 99.000đ và gói mua một lần 299.000đ. ProCCD có gói năm 149.000đ và trọn đời 299.000–399.000đ. Kapi bán gói tuần 19.000đ ([App Store VN – Dazz](https://apps.apple.com/vn/app/id1422471180); [App Store VN – ProCCD](https://apps.apple.com/vn/app/id1616113199)). So ra, gói năm của Filmode ở Việt Nam đắt gấp 3–5 lần các app dẫn đầu.

### Điều khiến người dùng trả tiền hoặc bỏ app

Đợt quét khoảng 13.900 đánh giá Google Play từ 2024 đến 9/2026 cho thấy lý do bỏ app lớn nhất là **thay đổi cách thu tiền**, chứ không phải giá. Trong 4.825 đánh giá của nhóm app máy ảnh film (Kapi, OldRoll, ProCCD, Dazzil, Huji, Kuji, NOMO, FIMO), các lời phàn nàn ở mức 1–2★ chia ra như sau: paywall hoặc thuê bao 33%, quảng cáo 16%, crash 10% ([Google Play – Kapi](https://play.google.com/store/apps/details?id=com.sensemobile.action)). Ở nhóm app chỉnh ảnh, tỷ lệ phàn nàn về paywall lên tới 43%. Cụm "trước miễn phí, giờ phải trả" xuất hiện trong 156 đánh giá. Một đánh giá như vậy của CapCut có 12.240 lượt bấm "hữu ích" ([Google Play – CapCut](https://play.google.com/store/apps/details?id=com.lemon.lvoverseas)).

Người dùng đã mua rồi mà bị đòi trả lại là một nguồn giận dữ riêng. FIMO chuyển từ bán lẻ từng cuộn sang thuê bao, 1998 Cam gỡ app xuống rồi đăng lại khiến người đã mua trọn đời phải mua lần nữa ([Google Play – 1998 Cam](https://play.google.com/store/apps/details?id=com.aaai.cam1998&hl=en&gl=US)), và NOMO lấy lại quyền Pro của người đã mua. Ở chiều ngược lại, 110 đánh giá xin hoặc khen gói **trọn đời/mua một lần**; một người dùng Dazz iOS viết rằng app "đáng 5 sao chỉ vì bạn thực sự mua đứt được" ([App Store – Dazz](https://apps.apple.com/us/app/1422471180?see-all=reviews&platform=iphone)). Học sinh, sinh viên Việt Nam nói thẳng rằng họ chấp nhận xem quảng cáo chứ không trả phí ([Google Play – Polarr](https://play.google.com/store/apps/details?id=photo.editor.polarr)), nhưng ghét bị bắt "xem 3 quảng cáo để lấy một tấm ảnh" như ở Kapi. Mảng video chuyên nghiệp đau ở chỗ khác là **phân mảnh thiết bị**: 29% đánh giá 1–2★ của Blackmagic Camera và mcpro24fps nhắc tên một hãng máy cụ thể ([Google Play – Blackmagic](https://play.google.com/store/apps/details?id=com.blackmagicdesign.android.blackmagiccam)).

Đợt quét cũng cho thấy nhiều nỗi lo thường được nhắc tới lại ít khi là lý do gây 1★ ở thị trường đại chúng: gói theo tuần, watermark, độ phân giải thấp, look trông giả và màu da, mỗi thứ chỉ chiếm khoảng 3% lời phàn nàn trở xuống. Thứ người dùng thực sự đòi là những tính năng "như iPhone" và độ tin cậy. Ảnh động kiểu Live Photo trên Android được nhắc trong 102 đánh giá của ProCCD và 57 đánh giá của Kapi. Họ cần góc siêu rộng 0.5× và flash cho camera trước. Ảnh chụp ra phải giống kính ngắm; một đánh giá tiếng Việt của Kapi chê ảnh "lúc chưa chụp nhìn đẹp lắm mà chụp thì nó xấu quắc". Và họ không muốn bị bắt tạo tài khoản: lỗi đăng nhập chiếm 21% lời phàn nàn của VSCO, 26% của NOMO và 27% của POV ([Google Play – NOMO](https://play.google.com/store/apps/details?id=com.blink.academy.nomopro)).

### Chuẩn chuyển đổi, phí store và thuế ở Việt Nam

Photo & Video là danh mục nhiều lượt cài nhưng chuyển đổi thấp. Theo RevenueCat, tỷ lệ chuyển từ dùng thử sang trả tiền có trung vị 22,2%, thấp nhất trong mọi danh mục, và chỉ còn 17,1% trên Google Play; 68% đợt dùng thử của danh mục kéo dài từ 4 ngày trở xuống. Đổi lại, danh mục có đà doanh thu sớm tốt nhất: trung vị doanh thu một năm sau ra mắt là $124/tháng, so với khoảng $72 của mọi danh mục, và trong hai năm đầu 21,4% app mới đạt $1K/tháng, 7,3% đạt $10K/tháng. Photo & Video cũng là danh mục dùng kết hợp "thuê bao + trọn đời" nhiều nhất, ở 33,0% số app ([RevenueCat](https://www.revenuecat.com/state-of-subscription-apps)). Theo Adapty, thử nghiệm bản địa hóa (dịch cộng tiền tệ địa phương) làm tăng giá trị vòng đời khách hàng (LTV) nhiều nhất trong các loại thử nghiệm, tới 62,3%, trong khi Android chỉ chiếm 15,25% doanh thu thuê bao toàn cầu dù có khoảng 70% người dùng ([Adapty](https://adapty.io/blog/mobile-app-monetization-2026/)).

Quảng cáo không bù được khoảng chênh đó. Ở thị trường nhóm 3 như Việt Nam, quảng cáo có thưởng (rewarded) có eCPM $2–3 và quảng cáo xen kẽ (interstitial) $1–2 ([RevenueLab](https://www.revenuelab.fyi/blog/admob-ecpm-benchmarks-2026)); với 10.000 người dùng hoạt động mỗi ngày, mỗi người xem 1–2 quảng cáo có thưởng, doanh thu chỉ khoảng $20–60/ngày. Đó là lý do các app film châu Á chồng cả quảng cáo xen kẽ lẫn banner mà vẫn thu ít.

Về phí, cả hai store đều thu 15% với nhà phát triển nhỏ. Google Play áp mức 10% phí dịch vụ + 5% phí thanh toán cho $1 triệu đầu tiên ở Mỹ, EEA và Anh từ 30/6/2026 ([Google Play Console](https://support.google.com/googleplay/android-developer/answer/112622?hl=en)). Apple áp 15% qua Small Business Program ([Apple](https://developer.apple.com/app-store/small-business-program/)).

Với cá nhân đặt tại Việt Nam, Apple khấu trừ 2% thuế thu nhập cá nhân và 5% thuế nhà thầu tính trên phần hoa hồng ([Apple Developer](https://developer.apple.com/news/?id=yo2104n5)). Google thu và nộp hộ 5% VAT trên giao dịch của người mua Việt Nam, chi trả bằng USD/EUR với ngưỡng chuyển khoản tối thiểu $100 ([Google Play Console](https://support.google.com/googleplay/android-developer/answer/138000?hl=en)).

## Android để lấy người dùng, iOS để thu tiền

**Bảng 7 — So sánh Google Play và iOS theo bằng chứng**

| Chỉ số | Google Play | App Store | Nguồn |
|---|---|---|---|
| Tỷ lệ tải → trả tiền sau 35 ngày (mọi danh mục) | 0,9% | 2,6% | [RevenueCat](https://www.revenuecat.com/state-of-subscription-apps) |
| Doanh thu trên mỗi lượt cài sau 60 ngày | $0.16 (Ấn Độ/Đông Nam Á: $0.04) | $0.42 (Ấn Độ/Đông Nam Á: $0.15) | [RevenueCat](https://www.revenuecat.com/state-of-subscription-apps) |
| Tỷ lệ dùng thử → trả tiền, Photo & Video | 17,1%, thấp nhất trong bảng | Trung vị danh mục 22,2% (cả hai store) | [RevenueCat](https://www.revenuecat.com/state-of-subscription-apps) |
| Tỷ trọng doanh thu thuê bao toàn cầu | 15,25%, dù có khoảng 70% người dùng | Phần còn lại | [Adapty](https://adapty.io/blog/mobile-app-monetization-2026/) |
| Doanh thu/tháng của app film hàng đầu | OldRoll $20k; Kapi $9k; ProCCD $8k | Dazz $900k; ism $200k; Foodie $100k; OldRoll $90k | [Sensor Tower](https://app.sensortower.com/overview/1422471180?country=US) |
| Doanh thu trên mỗi lượt tải (tính từ số ST) | Kapi ~$0.009; ProCCD ~$0.013; OldRoll ~$0.05 | Dazz ~$0.45; OldRoll ~$0.45 | [Sensor Tower](https://app.sensortower.com/overview/com.accordion.analogcam?country=US) |
| Thị phần máy bán ra ở VN năm 2025 | Samsung 26%, OPPO 18%, Xiaomi 17% | Apple 20% (mức kỷ lục) | [TelecomLead](https://telecomlead.com/smart-phone/vietnam-smartphone-market-2025-samsung-leads-with-26-share-as-premium-ai-and-security-drive-industry-shift-124714) |
| Khoảng trống cạnh tranh | Không có Dazz chính chủ; Darkroom, RNI, Dehancer không có bản Android; app LUT cũ hoặc nhỏ | Đối thủ mạnh; khoảng 77% app thuê bao mới ra mắt trên iOS | [Google Play](https://play.google.com/store/search?q=dazz+cam&c=apps&hl=en&gl=US); [RevenueCat](https://www.revenuecat.com/state-of-subscription-apps) |
| Phí với nhà phát triển nhỏ | 15% | 15% | [Google](https://support.google.com/googleplay/android-developer/answer/112622?hl=en); [Apple](https://developer.apple.com/app-store/small-business-program/) |
| Rủi ro chính sách lớn nhất | Luật công bố thông tin thuê bao; bắt buộc dùng Photo Picker | Guideline 4.3 về app spam/biến thể, siết lại từ 9/6/2026 | [Google](https://support.google.com/googleplay/android-developer/answer/9900533?hl=en); [MacRumors](https://www.macrumors.com/2026/06/09/app-store-guidelines-low-quality-apps/) |

Khuyến nghị: **ra Google Play trước, nhưng đừng xây app chỉ cho Android.**

Có bốn lý do để đi trước bằng Android. Code của đội vốn viết cho Android trước. Các khoảng trống rõ nhất đều nằm trên Android: Dazz vắng mặt, app giả lập film cao cấp không có, app LUT đã cũ. Apple chỉ chiếm 20% máy bán ra ở Việt Nam năm 2025, nghĩa là khoảng 80% còn lại là Android. Và Android đem lại lượt cài nhanh: các app film Android hàng đầu nhận 400 nghìn đến 1 triệu lượt tải mỗi tháng. Nhưng doanh thu thì nằm ở iOS: doanh thu trên mỗi lượt tải trong ngách này trên iOS cao gấp 10–100 lần Android, và người dùng iOS Việt Nam đang trả tiền cho màu film, như vị trí của Dazz (#30) và Fimii (#49) trên bảng grossing cho thấy.

Áp vào từng app, thứ tự nền tảng khác nhau. **App 1 (Filmode)** đã có iOS, nên hai nền tảng làm song song và đồng bộ tính năng ngay. **App 2 (Studio)** ra Android trước để chiếm khoảng trống, rồi lên iOS sau khoảng một quý, vì Fimii cho thấy người dùng iOS Việt Nam trả tiền cho đúng loại app này. **App 3 (FilCam)** ra Android trước và có thể chỉ ở Android khá lâu, vì trên iOS đã có Blackmagic miễn phí, Apple Log gốc và nhiều app LUT nên khoảng trống hẹp hơn; lý do để lên iOS về sau là Leica LUX đã chứng minh "camera pro kèm look" thu được khoảng $300k/tháng ([Sensor Tower – Leica LUX](https://app.sensortower.com/overview/6477182657?country=US)).

Về thị trường, nên ưu tiên Việt Nam, Indonesia, Thái Lan, Philippines, Hàn Quốc và Brazil. Đây là nơi Dazz và các app film đứng hạng cao, và nơi lượng tìm "digicam" và "dazz cam" tập trung nhiều nhất.

## Ba app nên xây trên một lõi look chung

Bằng chứng ở các phần trên chỉ ra ba việc khác nhau mà người dùng cần làm: chụp ảnh "có vibe" digicam/film cùng bạn bè; biến ảnh đã có thành màu film theo một công thức; và quay video với LUT rồi chỉnh màu clip. Mỗi việc có bộ từ khóa, đối thủ và mức sẵn lòng trả tiền riêng, nên chúng nên là ba app tách biệt thay vì một app ôm tất cả. Tách rõ như vậy còn giúp tránh bị Apple coi là "biến thể" theo guideline 4.3 ([MacRumors](https://www.macrumors.com/2026/06/09/app-store-guidelines-low-quality-apps/)).

Điểm nối ba app là **một định dạng look chung**: file .cube đi kèm một công thức JSON mô tả grain, halation, vignette, khung và date stamp. Một công thức tạo trong Studio có thể quét QR để dùng trực tiếp trong kính ngắm Filmode, và cũng chính LUT đó dùng được cho video trong FilCam. Ở Việt Nam, người dùng khám phá app qua các bài "công thức màu" do creator đăng. Bài giới thiệu ProCCD của tài khoản @congthucmau đạt khoảng 50,5 nghìn lượt xem ([Threads](https://www.threads.com/@congthucmau/post/DT9WDPzidyR/)). Người dùng VSCO Việt Nam đã xin được "lưu công thức dưới dạng mã QR" ([App Store VN](https://itunes.apple.com/vn/rss/customerreviews/id=588013838/sortBy=mostRecent/json)). Vòng lặp chia sẻ công thức giữa ba app đi thẳng vào kênh khám phá này, và chưa có đối thủ Trung Quốc hay Hàn Quốc nào làm.

### Tổng quan ba app và quan hệ với app hiện có

**Bảng 8 — Tổng quan ba app đề xuất** (giá là đề xuất, cần thử A/B)

| | App 1 — Filmode | App 2 — Filmode Studio | App 3 — FilCam |
|---|---|---|---|
| Việc người dùng cần làm | Chụp ảnh digicam/film "có vibe", ảnh động, cuộn phim, album sự kiện | Biến ảnh có sẵn thành màu film theo công thức; tạo, nhập và chia sẻ công thức/LUT | Quay video và chụp ảnh với LUT trực tiếp; chỉnh màu clip; tạo và dùng LUT riêng |
| Xây từ | Filmode Vibe (Android) và Filmode iOS; giữ package `app.filmode` và bundle iOS | Trình sửa ảnh, Match Photo và bộ nhập .xmp của Filmode iOS, tách ra thành listing mới | FilCam (`app.filmode.filcam`): giữ chế độ thủ công và RAW, thêm video LUT và công cụ chỉnh màu |
| Từ khóa chính | digicam, ccd camera, retro/vintage/film camera, y2k camera, disposable camera; VN: máy ảnh film, app chụp ảnh film, máy ảnh ccd | film recipes, film simulation, film filter, film presets; VN: công thức màu fujifilm, preset màu film, chỉnh màu film, màu film | lut camera, 3d lut, cube lut, color grading, log camera, raw/manual camera; VN: lut màu, chỉnh màu video |
| Tiêu đề store gợi ý | "Filmode: Digicam & Film Camera" / "Filmode: Máy ảnh film, Digicam" | "Filmode Studio: Film Recipes" / "Filmode Studio: Công thức màu" | "FilCam: LUT Video & RAW Camera" / "FilCam: Quay LUT màu & RAW" |
| Đối thủ chính | Dazz (iOS), ProCCD, Kapi, OldRoll, ZANKHANA Digicam, 101cam, POV | Fimii, FujiStyle, Fuji X Weekly, VSCO, Afterlight, RNI/Dehancer (iOS) | Blackmagic Camera, mcpro24fps, 3DLUT mobile, PeekLut, LUT Studio |
| Nền tảng | Android và iOS song song (iOS đã có) | Android trước, iOS sau khoảng một quý | Android trước; iOS khi bản Android đã ổn định |
| Giá US | Giữ $1.99/tháng, $14.99/năm, $19.99 trọn đời; từng máy $0.99–1.99; pass sự kiện $2.99/$9.99/$49.99 | $19.99 trọn đời; $14.99/năm; gói lẻ $1.99–3.99 | $19.99–24.99/năm (dùng thử 7 ngày); $39.99 trọn đời; $2.99–3.99/tháng |
| Giá VN | Khoảng 149.000–199.000đ/năm; khoảng 299.000đ trọn đời | Khoảng 199.000–263.000đ trọn đời; khoảng 149.000đ/năm | Khoảng 249.000–299.000đ/năm; khoảng 499.000đ trọn đời |

Các mức giá neo theo bằng chứng đã nêu ở Bảng 6. App 1 giữ giá iOS hiện tại, vốn đã ở mức thấp của ngách và ngang Dazz ($19.99 mua một lần) cùng ProCCD ($13.99–17.99 trọn đời). App 2 neo vào Fimii ($9.99), Koloro ($21.99), Afterlight ($19.99–39.99) và FujiStyle ($14.99/năm). App 3 neo vào mcpro24fps ($19.99), Halide ($19.99/năm, $69.99 mua một lần) và PeekLut ($34.99/năm) ([App Store – Halide](https://apps.apple.com/us/app/id885697368)). Giá Việt Nam đặt khoảng 40–50% giá Mỹ, khớp với cách Dazz và ProCCD định giá ở Việt Nam và với dữ liệu RevenueCat rằng giá trung vị ở Ấn Độ/Đông Nam Á chỉ bằng 46–54% giá ở thị trường lớn. Trên Android, gói trọn đời nên được đặt nổi bật, vì người dùng xin gói này nhiều trong khi 32,2% lượt hủy thuê bao trên Google Play đến từ lỗi thanh toán ([RevenueCat](https://www.revenuecat.com/state-of-subscription-apps)).

### Nền tảng dùng chung: Filmode Core

Cả ba app dùng chung một bộ lõi, gọi tạm là Filmode Core, để mỗi app mới không phải viết lại pipeline màu, thanh toán hay bản địa hóa. Tính năng AI đặt ngay trên máy và chỉ dùng cho màu sắc (dự đoán LUT, bảo vệ tông da), không dùng để sinh ảnh: 61,4% app thuê bao Photo & Video đã gắn nhãn AI, nhưng app AI rời bỏ nhanh hơn và bị hoàn tiền nhiều hơn ([RevenueCat](https://www.revenuecat.com/state-of-subscription-apps)), và người dùng đang phàn nàn về "tính năng AI không cần thiết" ([Google Play – Kapi](https://play.google.com/store/apps/details?id=com.sensemobile.action)). Về kỹ thuật, CameraX 1.6 đã ổn định các API cần thiết là SessionConfig, các nhóm tính năng (HLG, UHD, chống rung) và CameraEffect ([CameraX](https://developer.android.com/jetpack/androidx/releases/camera)), còn Media3 có sẵn `SingleColorLut` nhận LUT dạng cube N³ hoặc HALD ([Media3](https://developer.android.com/reference/androidx/media3/effect/SingleColorLut)), nên không cần tới FFmpeg.

**Bảng 9 — Epic → module → feature của Filmode Core**

| Epic | Module | Tính năng | Giai đoạn |
|---|---|---|---|
| C1. Look Engine | C1.1 Định dạng look | Một file look gồm LUT .cube 33³/64³ cộng công thức JSON (grain, halation, bloom, vignette, CA, khung, date stamp, cường độ); có đánh số phiên bản; ghi tên tác giả; tương thích ngược | MVP |
| | C1.2 Bộ nhập | Đọc .cube 17/33/65, HALD (level 8/12), .3dl; chuyển .xmp và preset .dng thành LUT cộng tham số; báo rõ phần nào không chuyển được (grain, độ nét, khử nhiễu) | MVP |
| | C1.3 Pipeline GPU Android | SurfaceProcessor GLES 3.x của CameraX dùng texture 3D; nội suy trilinear khi xem trước, tetrahedral khi xuất; grain theo độ sáng với seed cố định để ảnh xem trước giống ảnh xuất; halation/bloom xử lý ở ¼ độ phân giải | MVP |
| | C1.4 Pipeline iOS | Metal/Core Image `CIColorCubeWithColorSpace` (tối đa 64³); chuyển shader từ GLSL sang Metal | V1 |
| | C1.5 Xuất LUT | Xuất .cube 33/65 và ảnh HALD từ bất kỳ look nào | V1 |
| C2. Tài khoản và khôi phục | C2.1 Không cần tài khoản | Dùng offline, look đóng gói sẵn trong app; ảnh lưu thẳng vào album có tên rõ ràng; khôi phục giao dịch mua qua biên nhận Play/App Store | MVP |
| | C2.2 Đăng nhập tùy chọn | Đăng nhập Google/Apple, không dùng OTP số điện thoại; đồng bộ thư viện look và công thức; xóa tài khoản ngay trong app | V1 |
| | C2.3 Liên kết ba app | Deep link "mở look này trong Filmode, Studio hoặc FilCam"; ba app dùng chung một thư viện look | V1 |
| C3. Thanh toán và paywall | C3.1 Billing | Play Billing và StoreKit 2; gói tháng, năm, trọn đời, gói lẻ, pass sự kiện; dùng thử 3–7 ngày với gói năm | MVP |
| | C3.2 Paywall tuân thủ | Hiện số tiền thực bị trừ, không quy ra giá theo tháng; ghi rõ điều khoản dùng thử và cách hủy bằng tiếng Việt và tiếng Anh; nút đóng dễ thấy | MVP |
| | C3.3 Giá theo vùng | Bảng giá riêng cho VN, ID, PH, BR, IN; thử A/B giá qua remote config | MVP |
| | C3.4 Cam kết không thu hồi | Không bao giờ chuyển tính năng miễn phí sang Pro; giữ nguyên quyền của người đã mua; mã quà tặng và mã khuyến mãi | MVP |
| C4. Bản địa hóa và tên an toàn | C4.1 Ngôn ngữ và văn hóa | Tiếng Việt, Anh, Hàn, Nhật, Indonesia, Thái, Bồ Đào Nha (Brazil); gọi đúng "Tết Nguyên đán / Lunar New Year" | MVP |
| | C4.2 Lọc tên thương hiệu | Kiểm tra tên look, công thức và khung để tránh Kodak, Portra, Fujifilm, Classic Chrome, Polaroid, Instax, Leica; dùng tên tự đặt | MVP |
| | C4.3 Listing store | Tiêu đề, mô tả ngắn và ảnh chụp màn hình theo cụm từ khóa của từng thị trường; thử nghiệm listing trên Play | MVP |
| C5. Chất lượng và thiết bị | C5.1 Ma trận thiết bị | Test trên Galaxy A/S, Redmi Note, OPPO A/Reno, Vivo, Pixel; dò khả năng từng máy (ống kính, fps, 10-bit, RAW, extensions) và ẩn thứ máy không hỗ trợ | MVP |
| | C5.2 Crash và hiệu năng | Báo crash và ANR; xử lý ảnh dưới 1,5 giây; xem trước 30 fps trên máy tầm trung | MVP |
| | C5.3 Phân tích | Phễu cài → chụp/sửa → lưu → paywall → mua; cờ tính năng; thử A/B | MVP |
| C6. Quyền riêng tư và lưu trữ | C6.1 Truy cập media | Dùng Photo Picker để mở ảnh và video (không xin READ_MEDIA_*); lưu ảnh tự chụp qua MediaStore | MVP |
| | C6.2 EXIF | Giữ EXIF và thêm thẻ Software; tùy chọn xóa vị trí khi chia sẻ | MVP |
| | C6.3 Minh bạch | Khai báo Data safety và nhãn quyền riêng tư; mọi xử lý ảnh diễn ra trên máy | MVP |

### App 1 — Filmode: máy ảnh digicam, film và sự kiện

Filmode nên trở thành "máy ảnh digicam và film" cho Gen Z. Trên Android, app cạnh tranh trực tiếp với ProCCD, Kapi và OldRoll; trên iOS, với Dazz. Ba bằng chứng đứng sau hướng đi này: lượng tìm "digicam" tăng thật và mạnh nhất ngách; mọi app tăng nhanh từ 2023 đều theo chủ đề CCD, digicam hoặc máy quay; và người dùng Android đang tìm "Dazz cho Android".

**Trải nghiệm cốt lõi.** Mở app là vào ngay kính ngắm với một chiếc máy "có tính cách": digicam CCD đầu những năm 2000, máy phim 35mm ngắm-chụp, máy dùng một lần, máy chụp lấy liền, máy đồ chơi, điện thoại đời đầu hoặc máy quay DV. Mỗi máy có một **hiệu ứng chữ ký** đủ lạ để khoe lên TikTok. Trong ngách này, độ lan truyền đến từ một mẹo chụp cụ thể, không đến từ số lượng filter. Mẹo "ảnh chuyển động" (flash + grain cao + rung máy lúc chụp) đã đưa Dazz trở lại mạng xã hội năm 2026, nhất là với nhóm 16–25 tuổi ([TechTudo](https://www.techtudo.com.br/guia/2026/06/dazz-cam-o-que-faz-e-como-usar-efeitos-nas-fotos-veja-se-apk-vale-a-pena-edapps.ghtml)). Trào lưu digicam cũng lan từ TikTok sang Instagram nhờ những look rất cụ thể như look Canon G7X ([Back Market](https://www.backmarket.com/en-us/c/photo-and-video/digicam-trend-nostalgia-social-media)).

**Kỹ thuật phải giải đúng những gì đánh giá đòi.** Ảnh chụp ra phải giống hệt kính ngắm, nên preview và ảnh cuối dùng chung một shader. App phải hỗ trợ góc siêu rộng 0.5×, thứ nhận lời khen được bấm "hữu ích" nhiều nhất của Kapi (519 lượt), có flash màn hình cho camera trước, và xoay ảnh đúng hướng trên mọi hãng máy. "Live Photo cho Android" phải xuất ra định dạng chia sẻ được; một đánh giá 2★ của ProCCD chê app chỉ lưu "một video và một ảnh, không phải live photo như quảng cáo" ([Google Play – ProCCD](https://play.google.com/store/apps/details?id=com.cerdillac.proccd)). Cuộn phim 12/24/36 kiểu với thời gian "tráng" trễ (đã có trên iOS) giữ lại cảm giác chờ đợi của máy film.

**Chế độ sự kiện** biến board trên cloud và web camera sẵn có của Filmode thành album cho đám cưới và bữa tiệc. Khách quét mã QR và chụp ngay trong trình duyệt, không cần cài app. Chủ tiệc duyệt ảnh và tải toàn bộ bằng một chạm. Điều này quan trọng ở Việt Nam, nơi phần lớn khách dùng Android. Người dùng POV từng phàn nàn rằng chế độ không cần tải app "chỉ chạy trên iPhone" và rằng họ phải trả "$70 để hơn 200 khách mỗi người chụp 25 tấm" ([Google Play – POV](https://play.google.com/store/apps/details?id=com.untitledshows.pov&hl=en&gl=US)). Đây là nguồn doanh thu B2C2B, tức bán cho chủ tiệc để phục vụ khách của họ. Mô hình này đã được kiểm chứng: POV ước thu $80k/tháng từ chỉ 100 nghìn lượt tải Android, mức doanh thu trên mỗi lượt tải cao nhất ngách ([Sensor Tower – POV](https://app.sensortower.com/overview/com.untitledshows.pov?country=US)), và Filmode iOS đã bán sẵn Wedding Pass $49.99. Vì chưa có dữ liệu về nhu cầu app sự kiện ở Việt Nam, chế độ này nên được thử với vài đám cưới, bữa tiệc thật trước khi đầu tư lớn.

**Kiếm tiền.** Giữ lời hứa "không quảng cáo, không watermark": với eCPM $2–3 của quảng cáo có thưởng ở Việt Nam, quảng cáo không đáng để phá lời hứa đó, trong khi quảng cáo chiếm 16% lời phàn nàn 1–2★ của nhóm app film. Giữ cơ chế xem trước look Pro trực tiếp và chỉ thu tiền khi lưu. Gói miễn phí phải rộng rãi và không bao giờ bị thu hẹp. Bán thêm từng máy và gói theo mùa (Tết, Trung thu, mùa cưới), và hạ giá Việt Nam về gần mức của Dazz và ProCCD. Ba việc nên làm ngay là chuyển danh mục Play từ Productivity sang Photography, đổi tên khung "Polaroid" thành "Instant", và đưa hơn 200 look, cuộn phim cùng pass sự kiện từ iOS sang Android.

**Bảng 10 — Epic → module → feature của App 1 (Filmode)**

| Epic | Module | Tính năng | Gói | Giai đoạn |
|---|---|---|---|---|
| A1. Thư viện máy ảnh | A1.1 Các dòng máy | Digicam CCD đầu 2000s (nhiều biến thể), máy phim 35mm ngắm-chụp, máy dùng một lần, máy lấy liền, máy đồ chơi, điện thoại đời đầu, máy quay DV; mỗi máy có một hiệu ứng chữ ký và tên tự đặt | Khoảng 8 máy miễn phí; còn lại Pro hoặc mua lẻ | MVP |
| | A1.2 Cửa hàng máy | Thử mọi máy ngay trong kính ngắm; ảnh mẫu; "thử trước, trả khi lưu"; mua lẻ $0.99–1.99; gói theo mùa | Free/IAP | MVP |
| | A1.3 Tùy biến máy | Cường độ look và grain; chế độ hiệu ứng ngẫu nhiên kiểu Huji; date stamp đổi được định dạng, lấy giờ thật từ EXIF; chọn khung | Free một phần/Pro | V1 |
| A2. Chụp thời gian thực | A2.1 Kính ngắm | Xem trước LUT và hiệu ứng ở 30 fps; ảnh chụp giống hệt kính ngắm; lưới, hẹn giờ, chụp liên tiếp | Free | MVP |
| | A2.2 Ống kính và flash | Góc siêu rộng 0.5×, tele, camera trước; flash trực tiếp, flash màn hình cho selfie, flash màu; xoay đúng hướng trên mọi hãng | Free | MVP |
| | A2.3 Hiệu ứng chữ ký | "Ảnh chuyển động" (flash + grain + rung máy); kira/star; halation; bụi; light leak; VHS; nén JPEG kiểu CCD | Free một phần/Pro | MVP |
| | A2.4 Chất lượng ảnh | Ultra HDR tùy máy; dùng Night/HDR extensions cho ảnh tĩnh nếu máy có; tăng sáng khi thiếu sáng | Free | V1 |
| A3. Ảnh động | A3.1 Chụp chuyển động | Ghi 1,5–3 giây quanh lúc bấm, áp cùng look | Free | MVP |
| | A3.2 Xuất ảnh động | Motion Photo trên Android, Live Photo trên iOS, MP4/GIF lặp, kèm ảnh tĩnh riêng | Free | MVP |
| | A3.3 Chia sẻ | Khung 9:16; chia sẻ thẳng lên TikTok, Instagram, Zalo, Messenger | Free | V1 |
| A4. Video ngắn và máy quay | A4.1 Quay có look | Nâng giới hạn 15 giây hiện nay lên 60 giây 1080p; timecode kiểu DV; thu âm | Free 30 giây / Pro 60 giây | V1 |
| | A4.2 Hiệu ứng video | Grain động, VHS, leak động, khung camcorder | Pro | V1 |
| A5. Cuộn phim và tráng phim | A5.1 Cuộn phim | Cuộn 12/24/36 kiểu, đếm số khung còn lại, không cho xem trước | 12 kiểu Free; 24/36 Pro | MVP |
| | A5.2 Tráng trễ | Hẹn giờ tráng (1 giờ hoặc 24 giờ), thông báo khi "tráng xong" | Free | V1 |
| | A5.3 Photo dump | Ghép cả cuộn thành collage hoặc carousel Instagram; xuất ZIP | Pro | V1 |
| A6. Nhập ảnh và chỉnh nhanh | A6.1 Áp máy cho ảnh có sẵn | Chọn ảnh qua Photo Picker; áp hàng loạt | Free có giới hạn/Pro | MVP |
| | A6.2 Chỉnh cơ bản | Phơi sáng, cân bằng trắng, tương phản, cường độ, cắt; nút "mở trong Filmode Studio" để chỉnh sâu | Free | MVP |
| | A6.3 Khung và photobooth | Khung Instant, Booth, Film strip; photobooth tách nền (đã có) | Free/Pro | MVP |
| A7. Sự kiện và album chung | A7.1 Tạo sự kiện | Chủ tiệc tạo album; chọn máy và look chung; đặt số ảnh mỗi khách, thời lượng, tráng trễ; sinh mã QR và link | Pass | V1 |
| | A7.2 Tham gia không cần cài app | Web camera (getUserMedia + LUT WebGL) chạy trên Android và iPhone; khách vẫn có thể dùng app nếu muốn; chụp offline rồi đồng bộ sau | Free cho khách | V1 |
| | A7.3 Quản lý album | Duyệt hoặc ẩn ảnh; tải toàn bộ một chạm; trình chiếu; xuất để in | Pass | V1 |
| | A7.4 Giá sự kiện | Pass trả trước rõ ràng theo quy mô (Group/Party/Wedding); giá bằng VND; giới hạn ảnh mỗi khách rộng rãi | IAP | V1 |
| A8. Board và chia sẻ | A8.1 Board | Bảng ghim ảnh và board trên cloud (đã có); mời bằng mã; xem trên web | Free | MVP |
| | A8.2 Thẻ công thức máy | Ảnh kèm thông số máy và look, có mã QR để bạn bè chụp cùng look | Free | V1 |
| A9. Kiếm tiền | A9.1 Gói miễn phí cố định | Khoảng 8 máy, 18 look và các hiệu ứng cơ bản; không quảng cáo; ảnh không watermark | Free | MVP |
| | A9.2 Filmode Pro | Gói tháng, năm (có dùng thử) và trọn đời; cùng SKU và giá trên Android và iOS | Pro | MVP |
| | A9.3 Mua lẻ | Từng máy; gói Tết và Noel; pass sự kiện | IAP | MVP |
| A10. Tăng trưởng và ASO | A10.1 Listing | Tiêu đề theo từ khóa digicam/film; danh mục Photography; ảnh chụp màn hình theo từng thị trường | — | MVP |
| | A10.2 Creator | Bộ hướng dẫn cho từng hiệu ứng chữ ký; hashtag riêng; chương trình creator ở VN, ID, PH | — | V1 |
| | A10.3 Giới thiệu bạn bè | Tặng một máy khi mời được bạn; mời bạn vào sự kiện | Free | V1 |
| A11. Đồng bộ Android–iOS | A11.1 Đưa tính năng iOS sang Android | Hơn 200 look, cuộn phim, Match Photo, pass | — | MVP |
| | A11.2 Giữ quyền lợi cũ | Người dùng iOS hiện có giữ mọi tính năng đã mua khi app được tái cấu trúc | — | MVP |

### App 2 — Filmode Studio: công thức màu và LUT cho ảnh

Filmode Studio phục vụ việc "làm ảnh đã chụp ra màu film theo một công thức". App được tách khỏi camera để có bộ từ khóa, đối thủ và tệp người dùng riêng: người sửa ảnh chụp từ máy ảnh thật hoặc từ điện thoại khác, và creator muốn bán công thức.

**Bằng chứng ủng hộ.** Lượng tìm "fujifilm recipes" tăng 5,4 lần và vẫn đang lên trên YouTube. Trên Play gần như chưa có ai: FujiStyle mới 21.872 lượt cài, Fuji X Weekly 407.926 lượt. Các app giả lập film cao cấp (Darkroom, RNI Films, Dehancer) chỉ có trên iOS. Fimii bán một gói trọn đời $9.99 mà lọt top 15 free trên cả hai store ở Việt Nam ([Google Play – Fimii](https://play.google.com/store/apps/details?id=com.ankii.fimii&hl=en&gl=VN)). Các công thức mang tên Kodak (Kodachrome, Portra, Gold, Tri-X) và Classic Chrome là nhóm được xem nhiều nhất trên Fuji X Weekly năm 2026 ([Fuji X Weekly](https://fujixweekly.com/2026/08/03/top-26-most-popular-fujifilm-recipes-of-2026-so-far-summer-edition/)); nhu cầu là có thật, nhưng tên gọi phải tránh nhãn hiệu.

**Trải nghiệm cốt lõi.** Người dùng chọn ảnh rồi chọn một công thức. Công thức được mô tả bằng tham số như công thức máy Fujifilm: màu nền, độ thô và kích thước grain, độ đậm màu, lệch cân bằng trắng, dải động, tone vùng sáng và vùng tối. Nhưng mọi công thức đều mang tên tự đặt. Người dùng tinh chỉnh bằng thanh trượt, lưu lại và chia sẻ công thức thành một thẻ ảnh có mã QR.

**Các tính năng đi kèm.** Người dùng nhập được preset và LUT đã mua ở dạng .cube, .xmp và .dng. Đây là tệp người dùng có sẵn: trên Gumroad có 2.474 sản phẩm preset Lightroom dạng DNG, so với 456 dạng XMP ([Gumroad](https://gumroad.com/products/search?query=lightroom%20presets)), còn người Việt rủ nhau "mua chung presets Lightroom 50k" trên Voz ([Voz](https://voz.vn/t/50k-mua-chung-presets-lightroom-cua-hpphotoshop.321187/)). Tính năng match từ ảnh mẫu có bản v1 dùng truyền màu thống kê và bản v2 dùng mô hình dự đoán LUT chạy trên máy kiểu Neural Preset hoặc Deep Analog ([arXiv](https://arxiv.org/abs/2608.14702)); kết quả xuất thành LUT .cube dùng được trong CapCut bản desktop, VN hoặc Blackmagic. App còn bảo vệ tông da nhờ tính năng tách nền người sẵn có, và chỉnh hàng loạt để cả một feed có chung một look.

**Kiếm tiền.** Nhập .cube và .xmp miễn phí, vì đây là mức tối thiểu của thị trường. Gói Pro mở toàn bộ thư viện công thức, RAW, chỉnh hàng loạt, lưu kết quả match thành look, xuất LUT và bảo vệ tông da. Gói trọn đời làm giá neo.

Về lâu dài, có thể mở chợ look cho creator theo mô hình Hàn Quốc. filmhwa (mua một lần $2.99) và Berryfilm ($1.99) là hai app filter mang thương hiệu influencer, đang đứng #62 và #59 top grossing iOS Hàn Quốc ([App Store – filmhwa](https://apps.apple.com/us/app/id6443723657); [App Store – Berryfilm](https://apps.apple.com/us/app/id6741474933)). Trên Etsy, các bộ preset bán chạy nhất bán được hàng nghìn đến hàng chục nghìn bản, mỗi bản khoảng $1–5 ([EtsyHunt](https://ehunt.ai/etsy-competitor-research/best-etsy-presets)).

**Bảng 11 — Epic → module → feature của App 2 (Filmode Studio)**

| Epic | Module | Tính năng | Gói | Giai đoạn |
|---|---|---|---|---|
| B1. Trình chỉnh sửa film | B1.1 Chỉnh không phá hủy ảnh gốc | Lịch sử thao tác; so sánh trước/sau; bản sao ảo | Free | MVP |
| | B1.2 Công cụ màu | Phơi sáng, cân bằng trắng/tint, đường cong tone, HSL, bánh xe màu 3 vùng, tách tông | Free một phần/Pro | MVP |
| | B1.3 Mô phỏng film | Grain theo độ sáng (kích thước, độ thô); halation; bloom; vignette; quang sai màu (CA); độ nét | Free một phần/Pro | MVP |
| | B1.4 RAW | Giải mã DNG, ProRAW và RAW của các hãng máy phổ biến; xử lý 16-bit | Pro | V1 |
| B2. Công thức màu | B2.1 Mô hình công thức | Tham số: màu nền, grain, độ đậm màu, lệch cân bằng trắng R/B, dải động, tone sáng/tối, độ nét, clarity; tên tự đặt, không dùng nhãn hiệu | Free | MVP |
| | B2.2 Thư viện công thức | Chia theo phong cách (máy phim, máy compact, điện ảnh, chân dung) và theo cảnh (nắng, đêm, trong nhà); bộ sưu tập theo mùa | Khoảng 20 công thức Free; còn lại Pro | MVP |
| | B2.3 Nhập công thức dạng chữ | Dán công thức từ blog hoặc Threads, app tự nhận ra tham số | Free | V1 |
| | B2.4 Thẻ công thức | Ảnh thẻ ghi thông số kèm mã QR để đăng Threads, TikTok, Instagram | Free | MVP |
| B3. Nhập preset/LUT đã có | B3.1 Bộ nhập | .cube, HALD, .3dl; chuyển .xmp và .dng thành look; giải nén file zip gói đã mua | Free | MVP |
| | B3.2 Thư viện | Thư mục, gắn thẻ, yêu thích; xem trước trên chính ảnh của người dùng | Free | MVP |
| B4. Sao chép màu từ ảnh mẫu | B4.1 Match v1 | Truyền màu thống kê (trung bình/độ lệch trong không gian Lab, khớp CDF) thành LUT 33³ | Xem trước Free; lưu thành look là Pro | MVP |
| | B4.2 Match v2 bằng AI | Mô hình dự đoán LUT chạy trên máy (kiểm tra giấy phép mã nguồn trước khi dùng) | Pro | V2 |
| | B4.3 Tinh chỉnh sau match | Cường độ; giữ tông da; khóa độ sáng | Pro | V1 |
| B5. Mặt nạ và tông da | B5.1 Bảo vệ tông da | Tách người để giữ nguyên màu da khi áp look | Pro | V1 |
| | B5.2 Chỉnh cục bộ | Mặt nạ bầu trời; cọ vẽ; vùng tròn | Pro | V2 |
| B6. Hàng loạt và feed | B6.1 Áp hàng loạt | Áp một công thức cho nhiều ảnh, tự cân lại phơi sáng từng ảnh | Pro | V1 |
| | B6.2 Đồng bộ feed | Sao chép/dán thiết lập; xem trước lưới feed 3×3 | Free một phần | V1 |
| B7. Xuất | B7.1 Xuất ảnh | JPEG, HEIF, PNG đủ độ phân giải; Ultra HDR; giữ EXIF; xóa vị trí GPS | Free | MVP |
| | B7.2 Xuất look | .cube (dùng cho CapCut desktop, VN, Resolve, Blackmagic), HALD, file look; mở thẳng trong Filmode hoặc FilCam | Pro | V1 |
| B8. Cộng đồng | B8.1 Chia sẻ công thức | Qua mã QR, link hoặc mã chữ; trang web công thức công khai để lên Google cho từ khóa "công thức màu …" | Free | V1 |
| | B8.2 Khám phá | Công thức thịnh hành; theo dõi creator; remix công thức và ghi tên tác giả | Free | V2 |
| | B8.3 Kiểm duyệt | Báo cáo vi phạm; lọc tên thương hiệu; gỡ nội dung khi có khiếu nại | — | V2 |
| B9. Chợ look của creator | B9.1 Gói creator | Bán qua IAP; hồ sơ creator; ảnh mẫu | IAP | V2 |
| | B9.2 Chia doanh thu | Bảng điều khiển cho creator (doanh số, lượt dùng); chi trả | — | V2 |
| | B9.3 Gói mang thương hiệu creator | Gói look riêng cho influencer kiểu filmhwa/Berryfilm | IAP | V3 |
| B10. Kiếm tiền | B10.1 Gói miễn phí | Trình sửa lõi, khoảng 20 công thức, nhập .cube/.xmp/.dng, chia sẻ bằng QR | Free | MVP |
| | B10.2 Studio Pro | Mọi công thức, RAW, hàng loạt, lưu match thành look, xuất LUT, bảo vệ tông da; gói trọn đời và gói năm | Pro | MVP |
| | B10.3 Gói lẻ | Gói công thức hoặc gói creator $1.99–3.99 | IAP | V1 |
| B11. Onboarding và hướng dẫn | B11.1 Gợi ý phong cách | Câu hỏi chọn phong cách khi mở app lần đầu; gợi ý công thức theo cảnh nhờ nhận diện cảnh trên máy | Free | V1 |
| | B11.2 Hướng dẫn | Bài hướng dẫn song ngữ "làm màu film X trên điện thoại" | Free | V1 |

### App 3 — FilCam: máy quay LUT và RAW cho Android

FilCam nên mở rộng từ "máy ảnh RAW thủ công" thành "máy quay LUT và RAW", tức một camera chuyên nghiệp cho cả ảnh lẫn video.

**Bằng chứng ủng hộ.** Lượng tìm LUT và color grading tăng thật; ở Việt Nam, "lut màu" tăng 4,15 lần. Mảng LUT trên Play vừa mỏng vừa cũ: 3DLUT mobile ngừng cập nhật từ 29/7/2024, còn app #1 cho từ khóa "lut" chỉ có 13.685 lượt cài ([Google Play – 3DLUT mobile](https://play.google.com/store/apps/details?id=com.lutmobile.lut&hl=en&gl=US)). Theo hướng dẫn của bên thứ ba, CapCut bản mobile không nhập được LUT tùy chỉnh ([cinem8](https://cinem8.co/blogs/blog/how-to-use-luts-in-capcut-for-color-grading)). Blackmagic Camera miễn phí nhưng chỉ hỗ trợ một danh sách máy flagship ([Blackmagic](https://www.blackmagicdesign.com/products/blackmagiccamera/techspecs/W-APP-02)), và người dùng vẫn xin được "chọn và xem trước LUT ngay trên màn hình quay" (297 lượt bấm hữu ích) cùng "thanh chỉnh cường độ" (105 lượt) ([Google Play – Blackmagic](https://play.google.com/store/apps/details?id=com.blackmagicdesign.android.blackmagiccam)). Filmic Pro đã sa sút, chỉ còn 2,34★ trên Play sau khi Bending Spoons cho cả đội phát triển nghỉ việc ([Videomaker](https://www.videomaker.com/news/uncertain-future-for-filmic-pro-as-entire-team-has-been-laid-off/)). Ngay cả người dùng máy ảnh film vui cũng muốn quay video với đúng filter mình thích ([Google Play – OldRoll](https://play.google.com/store/apps/details?id=com.accordion.analogcam)).

**Trải nghiệm cốt lõi.** Người dùng quay với LUT hiển thị trực tiếp, 1080p trên máy tầm trung và 4K trên máy hỗ trợ, đổi LUT và chỉnh cường độ ngay trong kính ngắm, rồi chọn "in" LUT thẳng vào file hoặc ghi video sạch để chỉnh sau. Hồ sơ pseudo-Log dùng đường cong GPU riêng như mcpro24fps, nên không phụ thuộc chế độ Log của hãng máy ([mcpro24fps](https://www.mcpro24fps.com/technical-luts/)); HLG 10-bit được bật khi máy hỗ trợ. Một trình chỉnh màu cho clip có sẵn chuyển file Samsung Log, Apple Log hoặc pseudo-Log về Rec.709 và xuất hàng loạt bằng Media3 Transformer. Rủi ro lớn nhất là phân mảnh thiết bị, nên app phải dò khả năng từng máy, ẩn tính năng máy không hỗ trợ (như FilCam đang làm với phần ảnh) và công bố danh sách máy được hỗ trợ.

**Kiếm tiền.** Giữ nguyên lời hứa hiện tại: chỉnh tay, RAW DNG và LUT film là miễn phí. Thêm video 1080p có LUT vào gói miễn phí. Gói Pro mở 4K, Log/HLG, chỉnh màu Log sang 709, xuất hàng loạt, tạo và xuất LUT, cùng các chế độ chụp chuyên sâu đã có.

**Bảng 12 — Epic → module → feature của App 3 (FilCam)**

| Epic | Module | Tính năng | Gói | Giai đoạn |
|---|---|---|---|---|
| F1. Máy ảnh thủ công và RAW (giữ nguyên) | F1.1 Điều khiển tay | Chế độ P/S/I/M; ISO, tốc độ, EV, cân bằng trắng theo Kelvin, lấy nét tay; khóa AE/AF/AWB; bấm chụp bằng phím âm lượng | Free | Đã có |
| | F1.2 Định dạng | RAW DNG cùng JPEG/HEIF có LUT; tùy tên file và thư mục; EXIF đầy đủ | Free | Đã có |
| | F1.3 Công cụ đo | Histogram, focus peaking, zebra, false color, waveform, thước cân bằng | Free | MVP |
| | F1.4 Chế độ chuyên sâu | Phơi sáng dài 30 giây; vệt sáng; bracketing 3/5/7; focus stacking; chụp đêm; intervalometer | Pro | Đã có |
| F2. Quay video có LUT | F2.1 Ghi hình | 1080p ở 24/25/30/60 fps; 4K30 trên máy hỗ trợ (qua feature groups); H.264/H.265; chọn bitrate | 1080p Free / 4K Pro | MVP |
| | F2.2 LUT trong kính ngắm | Đổi LUT ngay trên màn hình quay; thanh cường độ; so sánh A/B; chồng LUT kỹ thuật lên LUT sáng tạo | Free | MVP |
| | F2.3 Chế độ ghi | In LUT vào file, hoặc ghi sạch với LUT chỉ để xem (kèm file LUT để chỉnh sau) | In LUT Free / ghi sạch Pro | MVP |
| | F2.4 Điều khiển video | Shutter angle; khóa phơi sáng; đo mức âm thanh; mic ngoài/USB; chống rung; grain và halation động | Pro | V1 |
| F3. Log và HDR | F3.1 Pseudo-Log | Đường cong GPU cộng LUT kỹ thuật để đưa về Rec.709 | Pro | V1 |
| | F3.2 HLG 10-bit | Bật khi máy hỗ trợ; kiểm tra trước bằng `isSessionConfigSupported` | Pro | V1 |
| | F3.3 Apple Log (bản iOS) | Quay Apple Log trên iPhone Pro, áp chuỗi LUT Log→709 cộng LUT sáng tạo | Pro | V2 |
| F4. Quản lý LUT | F4.1 Thư viện LUT | Nhập .cube, .3dl, HALD; thư mục; yêu thích; ảnh thu nhỏ render trên khung hình hiện tại | Free | MVP |
| | F4.2 Bộ LUT khởi đầu | LUT tự làm cho phong cách điện ảnh, film, và bộ Log→709 chuẩn | Free một phần/Pro | MVP |
| | F4.3 Đồng bộ look | Nhận look từ Filmode Studio và Filmode | Free | V1 |
| F5. Chỉnh màu clip có sẵn | F5.1 Chỉnh cơ bản | Chọn clip qua Photo Picker; áp LUT cùng phơi sáng, cân bằng trắng, tương phản, bão hòa, đường cong | Free (giới hạn thời lượng)/Pro | MVP |
| | F5.2 Chuyển đổi Log | Samsung Log, Apple Log, pseudo-Log → Rec.709 | Pro | V1 |
| | F5.3 Scopes | Waveform, vectorscope, histogram | Pro | V1 |
| | F5.4 Xuất | Xuất hàng loạt bằng Media3 Transformer; tone-map HDR sang SDR; giữ âm thanh | Pro | V1 |
| F6. Tạo và xuất LUT | F6.1 Lưu bản chỉnh thành LUT | Xuất .cube 33/65 | Pro | V1 |
| | F6.2 LUT từ ảnh mẫu | Dùng chung module B4 của Studio | Pro | V1 |
| | F6.3 Xuất sang app khác | Đóng gói cho CapCut desktop, VN, Resolve, Blackmagic Camera; chia sẻ qua mã QR | Pro | V1 |
| F7. Tương thích thiết bị | F7.1 Dò khả năng máy | Ống kính, fps, 10-bit, chống rung, RAW; ẩn thứ máy không hỗ trợ | — | MVP |
| | F7.2 Danh sách máy hỗ trợ | Trang công khai; báo lỗi theo từng máy ngay trong app | — | V1 |
| | F7.3 Nhiệt độ và pin | Giảm tải khi máy nóng; cảnh báo cho người dùng | — | V1 |
| F8. Kiếm tiền | F8.1 Gói miễn phí | Chỉnh tay, RAW DNG, LUT ảnh, nhập .cube, video 1080p có LUT | Free | MVP |
| | F8.2 FilCam Pro | 4K, Log/HLG, chỉnh màu Log→709, hàng loạt, xuất LUT, chế độ chụp chuyên sâu; gói tháng, năm (dùng thử 7 ngày) và trọn đời | Pro | MVP |
| F9. Hướng dẫn | F9.1 Học quay Log | Hướng dẫn tiếng Việt "quay Log và dùng lut màu trên Android" | Free | V1 |

### Thứ tự triển khai, việc cần sửa ngay và rủi ro

Nên làm theo thứ tự App 1 → App 2 → App 3.

App 1 đi trước vì đã có sẵn, và vì lượng tìm digicam đang ở đỉnh. Nếu làm ngay, app còn kịp mùa Tết Nguyên đán 2027 và mùa cưới. App 2 đứng thứ hai vì dùng lại trình sửa ảnh đã chạy trên iOS, rủi ro thiết bị thấp, và Fimii đã chứng minh sức hút ở Việt Nam. App 3 đi sau cùng vì cần kiểm thử thiết bị nặng nhất.

**Bảng 13 — Lộ trình đề xuất.** Công sức tính bằng tuần-người, là ước tính kỹ thuật trong ghi chú nghiên cứu, chưa được đo thực tế. Nên chạy thử 2 tuần trên ma trận thiết bị trước khi cam kết, và dành 20–25% công sức cho kiểm thử thiết bị.

| Giai đoạn | Thời gian | Hạng mục | Công sức (Android) | Mốc đo |
|---|---|---|---|---|
| 0. Sửa nền | T10/2026 | Xác nhận hết lỗi lưu ảnh ở cả hai app; chuyển Filmode sang danh mục Photography; đổi tên khung "Polaroid"; tiêu đề store mới; bảng giá VN theo vùng | 2–3 tuần | Không còn báo lỗi lưu ảnh; bắt đầu có thứ hạng cho "máy ảnh film" hoặc "digicam" ở VN |
| 1. Filmode Core và App 1 | T10/2026–T1/2027 | Định dạng look chung; đưa tính năng iOS sang Android; máy digicam và hiệu ứng chữ ký; ảnh động; gói Tết; chế độ sự kiện chạy trên web | Định dạng look 3–5; sự kiện 6–10 | Tỷ lệ lưu ảnh mỗi phiên; tỷ lệ chuyển đổi ở paywall; số pass bán được |
| 2. App 2 Studio | Q1/2027 Android; Q2/2027 iOS | Trình sửa ảnh, công thức, bộ nhập preset, match v1, chia sẻ QR | Công thức 4–6; match v1 2–3; tông da 2–4; bản iOS 4–8 | Số công thức được chia sẻ; thứ hạng cho "công thức màu fujifilm" |
| 3. App 3 FilCam | Q2–Q3/2027 | Video LUT, pseudo-Log/HLG, trình chỉnh màu clip, xuất LUT | Camera video 8–12; chỉnh màu 6–10; bản iOS 6–8 và 5–8 | Tỷ lệ crash theo hãng máy; tỷ lệ chuyển sang Pro |
| 4. Chợ creator | Nửa cuối 2027 | Marketplace, chia doanh thu, kiểm duyệt | 10–16, thêm 4 cho iOS | Số creator; doanh thu từ gói creator |

Có bốn nhóm rủi ro chính.

**Pháp lý và nhãn hiệu.** Chính sách Play cấm dùng nhãn hiệu của người khác trong tiêu đề, icon, mô tả và nội dung app ([Google Play](https://support.google.com/googleplay/android-developer/answer/9888072?hl=en)). Riêng Kodak đã đổi tên Portra thành "Ektacolor Pro" vào tháng 3/2026 ([Fuji X Weekly](https://fujixweekly.com/2026/03/26/kodak-renames-portra-and-t-max/)). VSCO chỉ gọi thẳng tên phim khi kèm tuyên bố không liên kết với Kodak ([VSCO](https://www.vsco.co/features/film-filters/kodak-presets)). Vì vậy đội nên dùng tên tự đặt cho look, và không đóng gói các bộ LUT CC BY-SA như RawTherapee vào app ([Pat David](https://patdavid.net/2015/03/film-emulation-in-rawtherapee/)).

**Chính sách store.** Play cấm hiển thị giá quy ra theo tháng khi thực tế thu theo năm ([Google Play](https://support.google.com/googleplay/android-developer/answer/9900533?hl=en)). Apple yêu cầu không lấy đi tính năng mà người dùng đã trả tiền khi chuyển sang mô hình thuê bao ([Apple](https://developer.apple.com/app-store/review/guidelines/)), nên khi tái cấu trúc Filmode iOS phải giữ nguyên quyền của người đã mua. Photo Picker là bắt buộc với app chỉnh ảnh trên Android ([Google Play](https://support.google.com/googleplay/android-developer/answer/14115180?hl=en)).

**Cạnh tranh.** SNOW (với 101cam) và các nhà phát hành Trung Quốc có ngân sách lớn hơn nhiều, và số app film mới của nhà phát triển Việt Nam ra mắt trong năm 2026 cũng đang tăng. Lợi thế của đội phải đến từ bản địa hóa, giá hợp lý và vòng lặp chia sẻ công thức, không phải từ ngân sách quảng cáo.

**Dữ liệu.** Chưa có số lượt tìm kiếm tuyệt đối cho bất kỳ từ khóa nào, vì Keyword Planner và các công cụ ASO đều cần tài khoản trả phí. Mọi con số doanh thu đều là ước tính Sensor Tower, không ghi rõ tháng và không tính doanh thu quảng cáo. Bảng xếp hạng là ảnh chụp của một ngày. Chưa có dữ liệu về nhu cầu app sự kiện ở Việt Nam, nên chế độ sự kiện của App 1 cần được thử ở quy mô nhỏ trước khi đầu tư lớn.

## Kết luận

Ngách này không thưởng cho số lượng filter. Nó thưởng cho ba thứ khác. Một là một mẹo chụp đủ đặc biệt để lan trên TikTok. Hai là sự tin cậy: mua đứt được, không bị lấy lại thứ đã có, không bắt tạo tài khoản. Ba là look mang đi được giữa ảnh, video và các nền tảng. Đội đã có sẵn lời hứa "không quảng cáo, không watermark" và một lõi LUT hiếm app nhỏ nào có, nhưng gần như chưa có phân phối. Vì vậy, công sức tiếp theo nên dồn vào listing, từ khóa, giá bản địa hóa và định dạng look chung, thay vì thêm look mới. Chiến lược nền tảng hợp lý là dùng Android để có lượt cài và kiểm chứng sản phẩm, dùng iOS để thu tiền, và dùng Việt Nam cùng Đông Nam Á làm bàn đạp đầu tiên.

Kỳ vọng cũng cần thực tế. Một năm sau ra mắt, app Photo & Video trung vị thu $124/tháng, và chỉ khoảng một phần năm số app đạt $1K/tháng trong hai năm. Mốc thành công đầu tiên hợp lý cho mỗi app là $1K/tháng cộng với một vị trí trong top từ khóa ở Việt Nam, chứ chưa phải đuổi theo Dazz. Khoản chi đầu tiên đáng làm là thuê một công cụ ASO trả phí trong một tháng để lấy số lượt tìm thật cho Google Play Mỹ và Việt Nam. Đây là khoảng trống dữ liệu lớn nhất của nghiên cứu này, và nó quyết định tiêu đề của cả ba app.
