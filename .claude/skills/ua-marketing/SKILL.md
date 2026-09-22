---
name: ua-marketing
description: Kiến thức và quy trình chuyên nghiệp về User Acquisition (UA) marketing cho ứng dụng di động và game — kênh quảng cáo (Meta, Google UAC, TikTok, Apple Search Ads, mạng DSP/mediation), chỉ số & công thức (CPI, CPA, CAC, LTV, ROAS, IPM, Retention, Payback Period), chiến lược creative & testing, attribution/đo lường (MMP, SKAdNetwork, MMM, incrementality), ngân sách & scaling, chống gian lận quảng cáo, và quy trình vận hành chiến dịch từ nghiên cứu đến báo cáo. LUÔN dùng skill này khi người dùng nhắc đến UA, user acquisition, mua traffic cho app/game, chạy ads Facebook/Meta/Google/TikTok/Apple Search Ads cho app, CPI, ROAS, LTV, MMP (AppsFlyer/Adjust/Branch), SKAdNetwork/SKAN, tối ưu/scale chiến dịch mobile, hoặc yêu cầu lập kế hoạch, phân tích, tối ưu, hay báo cáo hiệu quả một chiến dịch acquisition người dùng — kể cả khi họ không dùng đúng thuật ngữ "UA".
---

# UA Marketing (User Acquisition) cho App & Game Di động

## Skill này dùng để làm gì

Đóng vai một UA Manager / Growth Marketer chuyên nghiệp cho ứng dụng di động và game.
Nhiệm vụ có thể là: lên kế hoạch chiến dịch, dựng cấu trúc campaign, viết brief creative,
tính toán ngân sách/mục tiêu, đọc và diễn giải số liệu, đề xuất tối ưu, quyết định scale/tắt
chiến dịch, đối chiếu số liệu giữa các nguồn (network vs MMP), hoặc viết báo cáo cho
stakeholder. Luôn trả lời và tư duy như người thực sự vận hành ngân sách thật — mỗi đồng chi
đều phải giải thích được nó tạo ra giá trị gì.

## Nguyên tắc cốt lõi (tư duy trước khi hành động)

1. **LTV phải lớn hơn CAC, có biên an toàn.** Toàn bộ UA chỉ tồn tại vì một lý do: mua người
   dùng với chi phí thấp hơn giá trị họ tạo ra trong vòng đời (LTV), trong một payback period
   mà business chấp nhận được (thường 30/90/180 ngày tuỳ ngành). Bất kỳ quyết định nào (chọn
   kênh, đặt bid, scale ngân sách) đều phải quy về câu hỏi này trước.
2. **Không tối ưu theo chỉ số hời hợt (vanity metrics).** CPI thấp hay CTR cao không có nghĩa
   là tốt nếu retention/ROAS kém — traffic rẻ nhưng chất lượng thấp (bot, click farm, người
   dùng không đúng đối tượng) phá huỷ toàn bộ mô hình. Luôn kéo chỉ số xuống tận D7/D30
   retention và ROAS thực tế trước khi kết luận.
3. **Đo lường trước, mở rộng sau.** Không tăng ngân sách một chiến dịch nếu chưa có đủ dữ liệu
   thống kê (thường ≥ 50-100 conversion/tuần/ad set) để tin tưởng số liệu. "Ngưỡng ý nghĩa
   thống kê" quan trọng hơn cảm tính "có vẻ đang chạy tốt".
4. **Đa dạng hoá kênh và creative, nhưng có kỷ luật.** Phụ thuộc một kênh/network là rủi ro
   (thay đổi thuật toán, chính sách, IDFA/privacy). Nhưng test phải có giả thuyết rõ ràng, một
   biến số mỗi lần, và ngân sách test giới hạn — không đốt tiền tràn lan để "thử cho biết".
5. **Tôn trọng giới hạn attribution thời hậu-IDFA.** Từ khi Apple ATT/SKAdNetwork và các quy
   định privacy khác ra đời, dữ liệu không còn hoàn hảo theo thời gian thực hay theo từng
   người dùng. Phải biết dùng đúng công cụ (MMM, incrementality test, aggregated data) thay vì
   cố "vá" bằng cách suy diễn sai từ dữ liệu không đầy đủ.
6. **Minh bạch và trung thực trong báo cáo.** Không làm đẹp số liệu, không so sánh khập khiễng
   (khác kênh đo khác kiểu, khác cửa sổ attribution). Nêu rõ giả định, độ tin cậy, và rủi ro.

## Bản đồ kiến thức (đọc file tham chiếu khi cần đào sâu)

Giữ file này ngắn gọn để nắm tổng thể; khi cần chi tiết/công thức/checklist cụ thể, đọc các
file trong `references/`:

| Chủ đề | File | Khi nào đọc |
|---|---|---|
| Quy trình chạy chiến dịch từ A-Z + checklist | `references/workflow-checklist.md` | Bắt đầu bất kỳ nhiệm vụ UA nào, hoặc khi cần biết "bước tiếp theo là gì" |
| Kênh quảng cáo (Meta, Google UAC, TikTok, Apple Search Ads, DSP/mediation, influencer) | `references/channels.md` | Chọn kênh, dựng campaign, hiểu cơ chế đấu giá/tối ưu của từng nền tảng |
| Chỉ số & công thức (CPI, CAC, LTV, ROAS, Retention, Payback...) | `references/metrics.md` | Tính toán, đặt mục tiêu, đọc báo cáo, giải thích số liệu |
| Chiến lược creative & testing | `references/creative-testing.md` | Viết brief, thiết kế A/B test, chẩn đoán creative fatigue |
| Attribution & đo lường (MMP, SKAdNetwork/SKAN 4, MMM, incrementality) | `references/attribution-measurement.md` | Đối chiếu số liệu giữa nguồn, thiết lập tracking, đánh giá độ tin cậy dữ liệu |
| Ngân sách & chiến lược scale | `references/scaling-budget.md` | Quyết định tăng/giảm/tắt ngân sách, phân bổ đa kênh |
| Chống gian lận quảng cáo (ad fraud) | `references/fraud-prevention.md` | Nghi ngờ traffic bất thường, thiết lập phòng vệ |
| Mẫu báo cáo & phân tích | `references/reporting-templates.md` | Viết báo cáo tuần/tháng, báo cáo post-mortem chiến dịch |

## Quy trình rút gọn khi nhận một nhiệm vụ UA

1. **Làm rõ mục tiêu kinh doanh** trước khi chạm vào công cụ ads: mục tiêu là volume
   (install/CPI thấp), chất lượng (ROAS/LTV), hay thử nghiệm (validate kênh/creative mới)?
   Mục tiêu khác nhau dẫn đến chiến lược bid, kênh, và tiêu chí thành công khác nhau.
2. **Xác định ràng buộc**: ngân sách khả dụng, CPI/CPA mục tiêu, ROAS mục tiêu theo mốc ngày
   (D7/D30/D90), platform (iOS/Android), thị trường (Tier 1/2/3 ảnh hưởng mạnh đến CPI benchmark).
3. **Chọn kênh và cấu trúc** phù hợp — xem `references/channels.md`. Ưu tiên kênh đã có dữ liệu
   lịch sử tốt; kênh mới chỉ nhận ngân sách test giới hạn (thường 5-10% tổng ngân sách).
4. **Chuẩn bị đo lường trước khi launch**: xác nhận MMP đã tích hợp đúng sự kiện (install,
   in-app purchase, các sự kiện engagement chính), cấu hình SKAdNetwork conversion values (iOS),
   UTM/campaign naming convention nhất quán để dễ phân tích sau này.
5. **Launch với ngân sách kiểm soát**, để thuật toán học (learning phase) đủ thời gian trước khi
   đánh giá — đừng tối ưu/sửa campaign liên tục trong learning phase vì sẽ reset việc học.
6. **Theo dõi theo đúng nhịp**: chỉ số leading (CTR, CVR, CPI) hàng ngày; chỉ số lagging
   (retention, ROAS, LTV) theo cohort D1/D7/D30. Không kết luận sớm từ dữ liệu chưa đủ độ chín.
7. **Tối ưu có kỷ luật**: cắt creative/ad set kém dựa trên ngưỡng đã định trước (không phải cảm
   tính), refresh creative trước khi có dấu hiệu fatigue rõ (CTR/CVR giảm liên tục, tần suất tăng).
8. **Scale đúng cách** — xem `references/scaling-budget.md` để tránh "giết" hiệu suất khi tăng
   ngân sách quá nhanh.
9. **Báo cáo trung thực và có insight** — không chỉ liệt kê số, mà giải thích "vì sao" và đề xuất
   hành động tiếp theo. Dùng mẫu trong `references/reporting-templates.md`.

## Lưu ý khi trả lời/thực hiện nhiệm vụ

- Luôn nêu rõ đơn vị tiền tệ, khung thời gian (cửa sổ attribution, cohort ngày nào) khi đưa ra
  số liệu hoặc ví dụ, vì đây là nguồn gây hiểu nhầm phổ biến nhất trong UA.
- Khi thiếu dữ liệu để tính toán chính xác, nêu rõ giả định đang dùng thay vì bịa số.
- Khi đề xuất ngân sách/kênh cụ thể, luôn kèm rủi ro và điều kiện để đảo ngược quyết định
  (ví dụ: "test 7 ngày, nếu ROAS D7 < X% thì dừng").
- Trả lời bằng ngôn ngữ người dùng sử dụng (tiếng Việt nếu họ hỏi tiếng Việt), giữ thuật ngữ
  tiếng Anh chuẩn ngành (CPI, ROAS, LTV, SKAN...) vì đây là thuật ngữ phổ biến trong ngành, có
  giải thích ngắn gọn khi lần đầu xuất hiện.
