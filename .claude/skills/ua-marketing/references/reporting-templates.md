# Mẫu Báo cáo & Phân tích

Mục lục: [Nguyên tắc viết báo cáo UA](#nguyên-tắc-viết-báo-cáo-ua) ·
[Mẫu báo cáo tuần](#mẫu-báo-cáo-tuần) · [Mẫu báo cáo tháng/chiến lược](#mẫu-báo-cáo-thángchiến-lược) ·
[Mẫu retrospective chiến dịch/thử nghiệm](#mẫu-retrospective-chiến-dịchthử-nghiệm) ·
[Mẫu đề xuất ngân sách](#mẫu-đề-xuất-ngân-sách)

## Nguyên tắc viết báo cáo UA

- **Số liệu đi kèm bối cảnh**: mọi con số phải nêu rõ khung thời gian, cửa sổ attribution, và
  so sánh với mốc nào (tuần trước, mục tiêu, benchmark ngành) — số liệu đơn lẻ không nói lên
  điều gì nếu thiếu điểm tham chiếu.
- **"Vì sao" quan trọng hơn "cái gì"**: đừng chỉ liệt kê CPI tăng/giảm bao nhiêu %, giải thích
  nguyên nhân (creative fatigue, thay đổi thuật toán nền tảng, mùa vụ, cạnh tranh đấu giá tăng...)
  và đưa ra căn cứ cho lời giải thích đó.
- **Luôn có phần khuyến nghị hành động cụ thể**, không chỉ mô tả tình hình. Người đọc báo cáo
  cần biết "vậy giờ làm gì tiếp theo".
- **Trung thực về rủi ro/độ không chắc chắn**: nếu dữ liệu chưa đủ để kết luận chắc chắn, nói rõ
  điều đó thay vì đưa ra kết luận nghe có vẻ chắc chắn nhưng dựa trên mẫu nhỏ.

## Mẫu báo cáo tuần

```markdown
# Báo cáo UA tuần [ngày bắt đầu] – [ngày kết thúc]

## Tóm tắt điều hành (2-3 câu)
[Kết quả nổi bật nhất tuần này và hành động chính đang/sẽ thực hiện]

## Số liệu tổng quan
| Chỉ số | Tuần này | Tuần trước | Mục tiêu | Ghi chú |
|---|---|---|---|---|
| Tổng chi phí | | | | |
| Installs | | | | |
| CPI blended | | | | |
| CTR trung bình | | | | |
| Retention D1 (cohort tuần trước) | | | | |
| ROAS D7 (cohort phù hợp) | | | | |

## Theo kênh
[Bảng breakdown chi phí/CPI/CVR/ROAS theo từng kênh, kèm nhận xét ngắn mỗi kênh]

## Điểm nổi bật / bất thường
- [Điều gì thay đổi đáng chú ý và giả thuyết nguyên nhân]

## Hành động tuần tới
- [Hành động cụ thể, ai chịu trách nhiệm, kỳ vọng kết quả]
```

## Mẫu báo cáo tháng/chiến lược

```markdown
# Báo cáo UA tháng [tháng/năm]

## Kết quả so với mục tiêu
[Bảng KPI tháng vs mục tiêu đã đặt đầu tháng, % hoàn thành]

## Hiệu suất theo kênh (xu hướng, không chỉ điểm số một tháng)
[Biểu đồ/bảng xu hướng CPI, ROAS D30, tỷ trọng ngân sách theo kênh qua các tháng gần đây]

## Phân tích LTV & Payback
[Đường cong LTV cập nhật theo cohort, so sánh payback period thực tế vs mục tiêu]

## Rủi ro & vấn đề cần chú ý
[Ví dụ: phụ thuộc quá nhiều vào một kênh, dấu hiệu fraud, thay đổi chính sách nền tảng ảnh
hưởng tracking]

## Đề xuất chiến lược tháng tới
[Thay đổi phân bổ ngân sách, kênh/thị trường mới cần test, thay đổi hướng creative]
```

## Mẫu retrospective chiến dịch/thử nghiệm

```markdown
# Retrospective: [Tên chiến dịch/thử nghiệm]

**Giả thuyết ban đầu**: [Điều gì được kỳ vọng và vì sao]
**Thiết lập test**: [Ngân sách, thời gian, biến số kiểm soát]
**Kết quả thực tế**: [Số liệu cụ thể, so với kỳ vọng]
**Kết luận**: [Giả thuyết đúng/sai/chưa đủ dữ liệu kết luận — nói rõ mức độ tin cậy]
**Bài học**: [Điều rút ra áp dụng được cho các chiến dịch khác]
**Khuyến nghị tiếp theo**: [Nhân rộng / dừng / cần test thêm biến gì]
```

## Mẫu đề xuất ngân sách

```markdown
# Đề xuất ngân sách UA: [kỳ đề xuất]

## Bối cảnh
[Tình hình hiện tại, lý do cần thay đổi ngân sách]

## Đề xuất phân bổ
| Kênh | Ngân sách hiện tại | Ngân sách đề xuất | Lý do thay đổi |
|---|---|---|---|

## Kỳ vọng kết quả
[Ước tính installs/CPI/ROAS dự kiến dựa trên hiệu suất biên quan sát được]

## Rủi ro & điều kiện đảo ngược
[Ví dụ: "Nếu ROAS D7 < X% sau 2 tuần, giảm ngân sách về mức cũ"]
```
