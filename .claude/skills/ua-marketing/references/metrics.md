# Chỉ số & Công thức UA

Mục lục: [Chỉ số chi phí](#chỉ-số-chi-phí) · [Chỉ số hiệu suất phễu](#chỉ-số-hiệu-suất-phễu) ·
[Chỉ số giá trị người dùng](#chỉ-số-giá-trị-người-dùng) · [Retention](#retention) ·
[ROAS & Payback](#roas--payback-period) · [Bảng tổng hợp công thức](#bảng-tổng-hợp-công-thức) ·
[Cách diễn giải đúng](#cách-diễn-giải-đúng-tránh-bẫy-vanity-metrics)

## Chỉ số chi phí

- **CPI (Cost Per Install)** = Tổng chi phí quảng cáo / Số lượt cài đặt.
  Chỉ số cơ bản nhất nhưng dễ gây hiểu nhầm nhất — CPI thấp không đồng nghĩa traffic tốt.
- **CPC (Cost Per Click)** = Tổng chi phí / Số click.
- **CPM (Cost Per Mille)** = Chi phí cho 1.000 lượt hiển thị = (Chi phí / Impressions) × 1000.
- **CPA (Cost Per Action/Acquisition)** = Chi phí / Số hành động mục tiêu (vd: đăng ký, mua
  hàng đầu tiên, đạt level X). Cụ thể hơn CPI vì gắn với hành vi có giá trị thật.
- **CAC (Customer Acquisition Cost)** = Tổng chi phí (bao gồm cả ads, hoa hồng, đôi khi cả
  lương team UA) / Số khách hàng trả phí mới có được. CAC khác CPA ở chỗ CAC thường tính đầy đủ
  chi phí vận hành, không chỉ chi phí media.

## Chỉ số hiệu suất phễu

- **CTR (Click-Through Rate)** = Số click / Số impression × 100%. Đo sức hấp dẫn của creative.
- **CVR / IPM liên quan đến store**:
  - **CVR (Conversion Rate)** = Số install / Số click × 100% (store listing → install), hoặc
    tổng quát hơn: số hành động mục tiêu / số người vào phễu ở bước trước.
  - **IPM (Installs Per Mille)** = Số install / Số impression × 1000. Phổ biến trong UA game vì
    kết hợp cả CTR lẫn CVR store page thành một con số duy nhất để so sánh creative.
- **Store Conversion Rate (store page CVR)** = Số install / Số lượt xem trang store
  (App Store/Google Play). Bị ảnh hưởng bởi ASO (icon, screenshot, rating, mô tả) — UA và ASO
  luôn phải phối hợp vì creative ads đưa traffic đến, nhưng store page mới "chốt" install.

## Chỉ số giá trị người dùng

- **ARPU (Average Revenue Per User)** = Tổng doanh thu / Tổng số người dùng (gồm cả người
  không trả phí).
- **ARPPU (Average Revenue Per Paying User)** = Tổng doanh thu / Số người dùng trả phí.
- **LTV (Lifetime Value)** = Tổng giá trị (thường là doanh thu, đôi khi gồm cả giá trị quảng
  cáo trong app) mà một người dùng tạo ra trong suốt "vòng đời" sử dụng app.
  - Công thức đơn giản theo cohort: `LTV(n ngày) = ARPU tích lũy của cohort đó tính đến ngày n`.
  - Công thức dự phóng (khi chưa đủ dữ liệu dài hạn), ví dụ theo đường cong retention:
    `LTV dự phóng ≈ ARPU/ngày × Tổng số ngày hoạt động dự kiến (ước tính từ đường cong retention)`.
  - Luôn nêu rõ LTV đang tính ở mốc ngày nào (LTV D7, LTV D30, LTV D180...) — so sánh LTV khác
    mốc ngày là sai lầm phổ biến nhất khi đọc báo cáo.

## Retention

- **Retention D1/D7/D30** = % người dùng cài đặt vào ngày 0 còn quay lại mở app vào đúng ngày
  1/7/30 sau đó (classic retention), hoặc mở app *vào ngày đó hoặc sau đó* tuỳ định nghĩa
  (rolling retention) — phải luôn nói rõ định nghĩa đang dùng vì hai cách tính cho kết quả khác
  nhau đáng kể.
- **Benchmark tham khảo (thay đổi theo ngành/thị trường, chỉ để định hướng, không phải chuẩn
  tuyệt đối)**: game casual D1 ~30-40%, D7 ~10-15%, D30 ~3-6%; app non-game (utility/finance)
  thường có đường cong khác, ít "rơi" nhanh ở D1 nhưng D30 cũng thấp nếu không có habit loop.
- Retention là chỉ số dự báo LTV sớm nhất và đáng tin nhất trước khi có đủ dữ liệu doanh thu —
  dùng retention D1/D7 để đánh giá chất lượng traffic sớm, không cần đợi đến ROAS D30.

## ROAS & Payback Period

- **ROAS (Return on Ad Spend)** = Doanh thu quy về từ chiến dịch / Chi phí quảng cáo × 100%.
  Luôn gắn với mốc ngày: ROAS D7, ROAS D30, ROAS D90... ROAS D7 = 20% nghĩa là sau 7 ngày, cứ
  100 đồng chi ads thì thu lại 20 đồng doanh thu (chưa hoà vốn, nhưng có thể vẫn đang trên đà
  đạt ROAS 100% ở mốc xa hơn).
- **Payback Period** = Số ngày (hoặc tháng) cần để tổng doanh thu tích luỹ từ một cohort bằng
  chi phí đã bỏ ra để có được cohort đó (ROAS đạt 100%). Doanh nghiệp thường đặt ngưỡng chấp
  nhận được (vd: payback ≤ 6 tháng) dựa trên dòng tiền và khẩu vị rủi ro.
- **Break-even ROAS** = 100%. Nhưng mục tiêu kinh doanh thực tế thường cao hơn 100% ở payback
  period đã định, vì còn chi phí vận hành khác ngoài media.
- **MER (Marketing Efficiency Ratio) / Blended ROAS** = Tổng doanh thu toàn bộ (mọi nguồn,
  organic lẫn paid) / Tổng chi phí marketing. Dùng để nhìn hiệu quả tổng thể khi attribution
  theo từng kênh không còn chính xác (đặc biệt sau các thay đổi về privacy).

## Bảng tổng hợp công thức

| Chỉ số | Công thức | Dùng để |
|---|---|---|
| CPI | Chi phí / Installs | Đánh giá chi phí thu hút thô |
| CPC | Chi phí / Clicks | Đánh giá chi phí ở tầng click |
| CPM | Chi phí / Impressions × 1000 | So sánh chi phí hiển thị giữa kênh |
| CPA/CAC | Chi phí / Số hành động (hoặc khách hàng) | Gắn chi phí với giá trị thật |
| CTR | Clicks / Impressions | Đo sức hút creative |
| CVR | Installs (hoặc actions) / Clicks | Đo hiệu quả phễu sau click |
| IPM | Installs / Impressions × 1000 | Chỉ số tổng hợp CTR+CVR cho ranking creative |
| ARPU | Doanh thu / Tổng users | Giá trị trung bình mỗi user |
| ARPPU | Doanh thu / Users trả phí | Giá trị trung bình mỗi user trả phí |
| LTV(n) | ARPU tích luỹ đến ngày n | So với CAC để quyết định đầu tư |
| Retention Dn | Users hoạt động ngày n / Users ngày 0 | Dự báo sớm chất lượng traffic |
| ROAS(n) | Doanh thu đến ngày n / Chi phí | Đo hiệu quả tài chính theo mốc |
| Payback Period | Ngày mà ROAS tích luỹ đạt 100% | Đo tốc độ hoàn vốn |
| MER/Blended ROAS | Tổng doanh thu / Tổng chi phí marketing | Đánh giá hiệu quả tổng thể |

## Cách diễn giải đúng (tránh bẫy vanity metrics)

- **CPI thấp + Retention D1 thấp** → traffic rẻ nhưng kém chất lượng (thường do targeting quá
  rộng hoặc creative "câu view" gây hiểu nhầm về nội dung app). Đừng mừng vội vì CPI đẹp.
- **CTR cao nhưng CVR thấp** → creative hấp dẫn nhưng gây kỳ vọng sai (mismatch giữa quảng cáo
  và trải nghiệm thật), hoặc store page yếu. Cần xem lại thông điệp creative có khớp app không.
- **ROAS D7 thấp không có nghĩa là chiến dịch thất bại** nếu đường cong LTV của app vốn dài hạn
  (vd: app dựa vào subscription năm) — phải so với benchmark payback period của chính app đó,
  không so chéo giữa các app có mô hình kiếm tiền khác nhau.
- **So sánh chỉ công bằng khi cùng điều kiện**: cùng cửa sổ attribution, cùng định nghĩa
  retention (classic vs rolling), cùng thị trường/hệ điều hành. Khi so sánh hai chiến dịch,
  luôn kiểm tra các điều kiện này trước khi kết luận "kênh A tốt hơn kênh B".
- **Mẫu nhỏ = kết luận không đáng tin.** Một ad set có 5 install chưa nói lên điều gì về CPI hay
  retention thật. Cần khối lượng đủ lớn (thường hàng chục đến hàng trăm conversion) trước khi
  ra quyết định tối ưu dựa trên chỉ số đó.
