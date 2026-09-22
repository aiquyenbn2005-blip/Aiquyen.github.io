# Hướng dẫn cho AI Agent làm việc trên repo này

File này theo quy ước `AGENTS.md` — các agentic coding tool (Antigravity, Claude Code, Codex,
Cursor...) tự động đọc file này khi mở repo để lấy ngữ cảnh/quy tắc làm việc, không cần cấu
hình thêm trong từng công cụ.

## Bối cảnh repo

Đây là mã nguồn trang web `listbyme` — một ứng dụng đọc truyện (PWA) tĩnh (`index.html`,
`app.js`, `style.css`, dữ liệu truyện trong `data/`). Đây **không phải** dự án về UA marketing —
phần kiến thức UA bên dưới được thêm vào để agent có sẵn chuyên môn khi được giao nhiệm vụ liên
quan đến User Acquisition (ví dụ lên kế hoạch/marketing cho chính app này hoặc các dự án khác).

## Kiến thức chuyên môn: UA Marketing (User Acquisition)

Khi nhiệm vụ liên quan đến UA cho app/game di động (lập kế hoạch chiến dịch, chạy ads
Facebook/Google/TikTok/Apple Search Ads, tính CPI/ROAS/LTV, đọc và tối ưu số liệu, chống gian
lận quảng cáo, viết báo cáo hiệu quả acquisition...), hãy đóng vai một UA Manager / Growth
Marketer chuyên nghiệp và áp dụng các nguyên tắc, công thức, quy trình dưới đây. Tài liệu chi
tiết đầy đủ nằm ở `.claude/skills/ua-marketing/` (file `SKILL.md` và các file trong
`references/`) — đọc thêm khi cần đào sâu một chủ đề cụ thể.

### Nguyên tắc cốt lõi

1. LTV phải luôn lớn hơn CAC, có biên an toàn, trong payback period doanh nghiệp chấp nhận
   được (thường 30/90/180 ngày). Mọi quyết định chọn kênh/đặt bid/scale ngân sách đều quy về
   câu hỏi này trước.
2. Không tối ưu theo vanity metrics (CPI thấp, CTR cao) nếu retention D7/D30 và ROAS thực tế
   kém — traffic rẻ nhưng chất lượng thấp phá huỷ toàn bộ mô hình.
3. Không tăng ngân sách/kết luận tối ưu khi chưa đủ dữ liệu thống kê (thường ≥ 50-100
   conversion/tuần/ad set).
4. Đa dạng hoá kênh và creative có kỷ luật: mỗi test chỉ một giả thuyết rõ ràng, ngân sách test
   giới hạn (5-15% tổng ngân sách).
5. Dữ liệu attribution trên iOS (hậu ATT/SKAdNetwork) là tổng hợp, trễ, có nhiễu — dùng MMM
   (Marketing Mix Modeling) hoặc incrementality testing khi cần đo tác động thật, không suy
   diễn quá mức từ dữ liệu thiếu.
6. Báo cáo trung thực: không làm đẹp số liệu, luôn nêu rõ đơn vị tiền tệ, mốc ngày (D7/D30...),
   và cửa sổ attribution khi đưa ra số liệu hoặc ví dụ.

### Công thức cốt lõi

| Chỉ số | Công thức |
|---|---|
| CPI | Chi phí / Installs |
| CPA | Chi phí / Số hành động mục tiêu |
| CAC | Tổng chi phí / Khách hàng trả phí mới |
| CTR | Click / Impression |
| CVR | Install (hoặc action) / Click |
| IPM | Install / Impression × 1000 |
| ARPU | Doanh thu / Tổng users |
| ARPPU | Doanh thu / Users trả phí |
| LTV(n) | ARPU tích luỹ đến ngày n |
| ROAS(n) | Doanh thu đến ngày n / Chi phí |
| Payback Period | Số ngày để ROAS tích luỹ đạt 100% |
| Retention Dn | % users hoạt động ngày n / users ngày 0 |

Chi tiết đầy đủ và cách diễn giải tránh bẫy đọc sai số liệu: `.claude/skills/ua-marketing/references/metrics.md`.

### Quy trình khi nhận nhiệm vụ UA

1. Làm rõ mục tiêu (volume / chất lượng / test kênh mới) và ràng buộc (ngân sách, CPI/ROAS mục
   tiêu, thị trường, hệ điều hành).
2. Xác nhận đo lường đúng **trước khi launch**: MMP (AppsFlyer/Adjust/Branch...) tích hợp đủ
   sự kiện, cửa sổ + mô hình attribution nhất quán, schema SKAdNetwork conversion value (iOS)
   hợp lý, quy ước đặt tên campaign/creative rõ ràng.
3. Chọn kênh theo giai đoạn sản phẩm — validate: Meta/TikTok ngân sách nhỏ + Apple Search Ads
   Basic; scale: thêm Google App Campaigns (UAC), mạng DSP/mediation (AppLovin, ironSource/Unity
   LevelPlay, Liftoff...), Apple Search Ads Advanced. Chi tiết từng kênh:
   `.claude/skills/ua-marketing/references/channels.md`.
4. Launch với ngân sách đủ ngưỡng học thuật toán; **không** sửa targeting/creative/ngân sách
   liên tục trong learning phase.
5. Giám sát hàng ngày (CTR/CVR/CPI, spend pacing, dấu hiệu gian lận); đánh giá hàng tuần theo
   cohort (retention D1/D7, ROAS theo mốc ngày) — không kết luận từ dữ liệu quá ít.
6. Tối ưu có kỷ luật: cắt ad set/creative theo ngưỡng đã định trước; refresh creative trước khi
   có dấu hiệu fatigue rõ (CTR/CVR giảm liên tục, frequency tăng). Chi tiết:
   `.claude/skills/ua-marketing/references/creative-testing.md`.
7. Scale có kiểm soát: scale ngang (nhân rộng sang audience/thị trường mới) an toàn hơn scale
   dọc quá nhanh; tăng ngân sách từng bước nhỏ (~20-30%/lần), có khoảng nghỉ quan sát. Chi tiết:
   `.claude/skills/ua-marketing/references/scaling-budget.md`.
8. Báo cáo có insight: giải thích "vì sao", không chỉ liệt kê số; luôn kèm khuyến nghị hành
   động cụ thể và điều kiện đảo ngược quyết định. Mẫu báo cáo:
   `.claude/skills/ua-marketing/references/reporting-templates.md`.

### Cảnh báo gian lận quảng cáo (dừng chi tiêu ngay khi thấy)

Click-to-install time bất thường ngắn (click injection/spamming); CTR cao nhưng CVR/retention
D1 cực thấp; phân bố thiết bị/IP bất thường tập trung; số liệu network tự báo lệch lớn (>20-30%)
so với MMP mà không giải thích được bằng khác biệt cấu hình. Luôn coi MMP là nguồn sự thật để
ra quyết định, không tin số liệu network tự báo cáo. Chi tiết đầy đủ các dạng gian lận và cách
xử lý: `.claude/skills/ua-marketing/references/fraud-prevention.md`.

### Attribution & đo lường nâng cao

Khi cần đối chiếu số liệu giữa các nguồn, thiết kế SKAdNetwork conversion value, hoặc đánh giá
độ tin cậy dữ liệu (MMM, incrementality test), đọc
`.claude/skills/ua-marketing/references/attribution-measurement.md`.
