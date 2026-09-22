# Kênh Quảng Cáo UA

Mục lục: [Meta (Facebook/Instagram)](#meta-facebookinstagram-ads) · [Google UAC](#google-app-campaigns-uac) ·
[TikTok Ads](#tiktok-ads) · [Apple Search Ads](#apple-search-ads-asa) ·
[Mạng DSP/Mediation](#mạng-dsp--ad-mediation-ưu-tiên-cho-game) · [Influencer & Affiliate](#influencer--affiliate--cpi-network) ·
[Chọn kênh theo giai đoạn](#chọn-kênh-theo-giai-đoạn-sản-phẩm)

Nguyên tắc chung: mỗi nền tảng đều dùng thuật toán tối ưu dựa trên machine learning theo tín
hiệu chuyển đổi (event) được gửi về qua SDK/API/MMP. Chất lượng và tốc độ của tín hiệu này
quyết định thuật toán học nhanh hay chậm — luôn ưu tiên thiết lập tracking đúng trước khi đổ
ngân sách lớn vào bất kỳ kênh nào.

## Meta (Facebook/Instagram) Ads

- **Loại chiến dịch chính**: App Promotion campaign (App Install hoặc App Event Optimization -
  AEO). Với AEO, chọn tối ưu theo sự kiện giá trị (vd: purchase, mua trong app) thay vì chỉ
  install thô để thuật toán tìm đúng người dùng chất lượng.
- **Cấu trúc**: Campaign (mục tiêu + ngân sách CBO - Campaign Budget Optimization thường được
  khuyến nghị) → Ad Set (targeting, placement, tối ưu event) → Ads (creative).
- **AEM (Aggregated Event Measurement)**: cơ chế đo lường tổng hợp của Meta cho iOS sau ATT,
  giới hạn 8 sự kiện được ưu tiên đo per app per domain. Phải xếp hạng (prioritize) đúng sự
  kiện quan trọng nhất lên đầu vì Meta chỉ báo cáo sự kiện ưu tiên cao nhất xảy ra trong phiên.
- **Học máy (learning phase)**: ad set cần khoảng 50 sự kiện tối ưu/tuần để thoát learning
  phase ổn định. Sửa targeting/creative/ngân sách liên tục trong giai đoạn này sẽ reset học.
- **Lưu ý**: hiệu suất rất nhạy với chất lượng creative (đặc biệt video ngắn, UGC). Audience
  Network và Advantage+ (tự động hoá targeting/placement) ngày càng chiếm vai trò lớn — ít
  kiểm soát thủ công hơn nhưng thường hiệu quả hơn tự chọn targeting hẹp trong hầu hết trường hợp.

## Google App Campaigns (UAC)

- Chiến dịch tự động hoàn toàn: chỉ cần cung cấp creative (text, hình ảnh, video), ngân sách,
  và giá thầu mục tiêu (**tCPA** - target cost per action, hoặc **tROAS** - target ROAS). Google
  tự phân phối qua Search, Display, YouTube, Discover, Google Play.
- **Không có kiểm soát placement/targeting thủ công** — tối ưu chủ yếu qua chất lượng creative
  asset và tín hiệu chuyển đổi (conversion) gửi về qua Google Ads API / Firebase / MMP.
- **tROAS đòi hỏi khối lượng dữ liệu giá trị (purchase value) đủ lớn** để thuật toán học chính
  xác — nếu app còn ít dữ liệu doanh thu, nên bắt đầu bằng tCPA hoặc tối ưu theo in-app action
  trước khi chuyển sang tROAS.
- Cung cấp đa dạng asset (nhiều tỷ lệ khung hình, nhiều video ngắn/dài) giúp thuật toán có nhiều
  lựa chọn để tối ưu qua các placement khác nhau.

## TikTok Ads

- **App Install / App Event Optimization campaign** trong TikTok Ads Manager, tương tự cấu trúc
  Meta (Campaign → Ad Group → Ad).
- Nền tảng ưu tiên **nội dung native, dạng UGC** hơn creative "quảng cáo" rõ ràng — quảng cáo
  trông giống video tự nhiên trên feed thường có CTR/CVR tốt hơn.
- **Spark Ads** (boost nội dung tổ chức/influencer có sẵn) là định dạng mạnh vì tận dụng
  engagement tự nhiên đã có, thường hiệu quả hơn tạo quảng cáo mới hoàn toàn với cùng nội dung.
- Vòng đời creative ngắn hơn Meta rõ rệt — cần nhịp độ sản xuất creative mới nhanh hơn để tránh
  creative fatigue.

## Apple Search Ads (ASA)

- Quảng cáo xuất hiện khi người dùng tìm kiếm trên App Store — traffic có **ý định cao** (đã
  chủ động tìm kiếm), thường có CVR và retention tốt hơn traffic display/social.
- **Basic**: đơn giản, tự động, đặt ngân sách và CPA mục tiêu, phù hợp cho app nhỏ mới bắt đầu.
- **Advanced**: kiểm soát chi tiết — chọn từ khoá (bao gồm brand keyword của mình để bảo vệ
  traffic organic, và competitor keyword nếu chiến lược cho phép), đặt giá thầu theo từ khoá,
  loại chiến dịch Search/Search Tab/Today Tab/Product Pages.
- **Custom Product Pages**: có thể liên kết creative set khác nhau theo từng nhóm từ khoá/nguồn
  traffic, tăng độ liên quan (relevance) giữa quảng cáo và store page.
- Nên kết hợp chặt với đội ASO vì ASA và organic search chia sẻ cùng "sân chơi" trên trang kết
  quả tìm kiếm App Store.

## Mạng DSP / Ad Mediation (ưu tiên cho game)

- **AppLovin (AXON/MAX)**, **Unity Ads / ironSource (LevelPlay)**, **Liftoff**, **Digital
  Turbine**, **Moloco**, **Vungle (Liftoff Monetize)**: các nền tảng chuyên UA cho game/app,
  thường tích hợp cả mediation (hiển thị ads trong app khác để kiếm doanh thu) lẫn UA (mua
  traffic), tạo vòng lặp "traffic đến từ ecosystem quảng cáo trong app khác".
- Thuật toán các nền tảng này tối ưu rất mạnh dựa trên tín hiệu ROAS/LTV thực tế — cần đảm bảo
  gửi đủ sự kiện doanh thu (không chỉ install) để thuật toán học đúng đối tượng giá trị cao.
- Thường yêu cầu ngân sách tối thiểu tương đối cao mỗi ngày để thuật toán học hiệu quả — không
  phù hợp để test với ngân sách quá nhỏ giọt.
- Là kênh quan trọng bậc nhất với game hyper-casual/casual/mid-core vì lưu lượng lớn và có sẵn
  cơ chế reward-based/playable ads phù hợp với game.

## Influencer & Affiliate / CPI Network

- **Influencer marketing**: hợp tác người có ảnh hưởng để tạo nội dung/review app, đo lường qua
  mã khuyến mãi, link tracking riêng, hoặc bộ MMP gán nguồn traffic.
- **Affiliate/CPI network**: trả tiền theo install hoặc theo hành động qua network trung gian.
  **Rủi ro gian lận rất cao** ở kênh này (traffic không rõ nguồn gốc, motivated install/incent
  traffic) — xem `references/fraud-prevention.md` trước khi hợp tác, và luôn có cơ chế
  post-attribution QA (kiểm tra retention/behavior của traffic từ network này trước khi trả
  toàn bộ hoa hồng hoặc tăng ngân sách).
- Giá trị chính của kênh này thường không phải volume lớn mà là **độ tin cậy/bằng chứng xã hội**
  (social proof) và tiếp cận ngách (niche audience) mà quảng cáo trả phí thông thường khó chạm tới.

## Chọn kênh theo giai đoạn sản phẩm

- **Giai đoạn validate (ít dữ liệu, ngân sách nhỏ)**: ưu tiên kênh cho phép test nhanh, chi phí
  thấp để lấy tín hiệu sớm — Meta/TikTok với ngân sách nhỏ, hoặc ASA Basic. Tránh kênh cần
  ngân sách tối thiểu cao (một số DSP) khi chưa có đủ dữ liệu để nuôi thuật toán.
- **Giai đoạn scale (đã có product-market fit, LTV model ổn định)**: đa dạng hoá sang UAC,
  DSP/mediation networks, và tăng dần ASA Advanced — mỗi kênh đóng góp một phần ngân sách theo
  đúng hiệu suất thực đo được (marginal ROAS), không dồn hết vào một kênh dù đang tốt.
- **Giai đoạn tối ưu dài hạn**: bổ sung MMM và incrementality testing (xem
  `references/attribution-measurement.md`) để hiểu đóng góp thật của từng kênh khi attribution
  theo click/view không còn đủ tin cậy do các giới hạn privacy.
