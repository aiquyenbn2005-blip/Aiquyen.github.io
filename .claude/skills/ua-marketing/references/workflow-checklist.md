# Quy trình Vận hành Chiến dịch UA (End-to-End)

Mục lục: [1. Nghiên cứu & Lập kế hoạch](#1-nghiên-cứu--lập-kế-hoạch) ·
[2. Thiết lập đo lường](#2-thiết-lập-đo-lường-trước-khi-launch) ·
[3. Dựng chiến dịch](#3-dựng-chiến-dịch) · [4. Launch & Learning Phase](#4-launch--learning-phase) ·
[5. Giám sát hàng ngày](#5-giám-sát-hàng-ngày) · [6. Tối ưu định kỳ](#6-tối-ưu-định-kỳ-hàng-tuần) ·
[7. Scale](#7-scale) · [8. Báo cáo & Retrospective](#8-báo-cáo--retrospective) ·
[Checklist nhanh](#checklist-nhanh-copy-được)

Dùng quy trình này làm khung tổng thể; mỗi bước tham chiếu tới file chuyên sâu tương ứng.

## 1. Nghiên cứu & Lập kế hoạch

- Xác định mục tiêu kinh doanh cụ thể: volume, chất lượng (ROAS/LTV), hay validate kênh/thị
  trường mới. Mục tiêu mơ hồ ("tăng trưởng người dùng") cần được cụ thể hoá thành số liệu đo
  được (vd: "1000 install/ngày với CPI ≤ X và ROAS D30 ≥ Y%").
- Xác định ràng buộc: ngân sách, thị trường/hệ điều hành mục tiêu, benchmark ngành tham khảo
  (CPI, retention theo `references/metrics.md`).
- Phân tích dữ liệu lịch sử nếu có (chiến dịch trước, đối thủ, sản phẩm tương tự) để đặt kỳ
  vọng thực tế thay vì mục tiêu áp đặt từ trên xuống không dựa trên dữ liệu.
- Chọn kênh phù hợp giai đoạn sản phẩm — xem `references/channels.md`.

## 2. Thiết lập đo lường (trước khi launch)

- Xác nhận MMP đã tích hợp và gửi đúng các sự kiện quan trọng (install, sự kiện engagement
  chính, sự kiện doanh thu/purchase).
- Cấu hình cửa sổ attribution và mô hình attribution nhất quán trên mọi kênh sẽ so sánh.
- Với iOS: thiết kế/xác nhận schema SKAdNetwork conversion value đã phản ánh đúng các hành vi
  quan trọng nhất cần theo dõi (xem `references/attribution-measurement.md`).
- Thống nhất quy ước đặt tên campaign/ad set/creative để dễ phân tích chéo về sau (nguồn, mục
  tiêu, ngày launch, biến thể creative).
- **Không launch chiến dịch thật khi bước này chưa hoàn tất** — dữ liệu bị lỗi ngay từ đầu
  không thể "sửa lại" hồi tố sau khi đã chi tiêu.

## 3. Dựng chiến dịch

- Chọn loại chiến dịch/mục tiêu tối ưu phù hợp (install-optimized vs event-optimized) theo
  hướng dẫn từng kênh trong `references/channels.md`.
- Chuẩn bị creative đa dạng đủ để thuật toán có lựa chọn (xem `references/creative-testing.md`)
  — không launch với chỉ 1 creative duy nhất trừ khi đang test rất hẹp một giả thuyết cụ thể.
- Đặt ngân sách khởi điểm đủ để đạt ngưỡng dữ liệu tối thiểu cho thuật toán học (tham khảo mức
  khuyến nghị của từng nền tảng), không đặt quá thấp khiến campaign "chết yểu" trước khi có
  đủ dữ liệu đánh giá.

## 4. Launch & Learning Phase

- Không sửa targeting/creative/ngân sách liên tục trong learning phase — mỗi thay đổi lớn có
  thể reset quá trình học của thuật toán.
- Theo dõi để phát hiện lỗi kỹ thuật sớm (tracking không nhận event, creative bị từ chối/policy
  reject, ngân sách không tiêu hết do bid quá thấp) — đây là kiểm tra vận hành, không phải đánh
  giá hiệu suất.

## 5. Giám sát hàng ngày

- Theo dõi chỉ số leading: CTR, CVR, CPI, tốc độ tiêu ngân sách (spend pacing).
- Kiểm tra dấu hiệu bất thường sớm — xem red flags trong `references/fraud-prevention.md`.
- Không đưa ra kết luận tối ưu lớn chỉ dựa trên 1 ngày dữ liệu.

## 6. Tối ưu định kỳ (hàng tuần)

- Đánh giá theo cohort: retention D1/D7, ROAS theo mốc ngày đã định — xem
  `references/metrics.md` để tránh bẫy vanity metrics.
- Cắt ad set/creative dưới ngưỡng đã định trước (không cảm tính).
- Refresh creative theo tín hiệu fatigue — xem `references/creative-testing.md`.
- Điều chỉnh phân bổ ngân sách theo hiệu suất biên — xem `references/scaling-budget.md`.

## 7. Scale

- Chỉ scale khi đã có đủ dữ liệu ổn định qua nhiều chu kỳ đánh giá, không scale dựa trên một
  giai đoạn ngắn hiệu suất tốt bất thường.
- Áp dụng nguyên tắc scale dọc/scale ngang có kiểm soát — xem `references/scaling-budget.md`.
- Với mở rộng sang thị trường/kênh mới, coi như một chu kỳ mới bắt đầu lại từ bước 1-2 (không
  giả định benchmark từ thị trường/kênh cũ áp dụng nguyên vẹn).

## 8. Báo cáo & Retrospective

- Dùng mẫu trong `references/reporting-templates.md`.
- Với chiến dịch/thử nghiệm đã kết thúc, viết retrospective ngắn: giả thuyết ban đầu là gì, kết
  quả thực tế, bài học rút ra, và khuyến nghị cụ thể cho chu kỳ tiếp theo — tránh lặp lại thử
  nghiệm đã biết kết quả hoặc mất insight vì không ghi lại.

## Checklist nhanh (copy được)

```
[ ] Mục tiêu kinh doanh cụ thể, đo lường được đã được xác nhận
[ ] Ngân sách, benchmark CPI/ROAS mục tiêu đã thống nhất
[ ] MMP tích hợp đúng, sự kiện quan trọng đã gửi đúng
[ ] Cửa sổ + mô hình attribution đã cấu hình nhất quán
[ ] (iOS) Schema SKAdNetwork conversion value đã thiết kế
[ ] Quy ước đặt tên campaign/creative đã thống nhất
[ ] Creative đa dạng đủ, đã qua review nội dung/chính sách
[ ] Ngân sách khởi điểm đủ ngưỡng học của thuật toán
[ ] Không sửa campaign trong learning phase
[ ] Theo dõi hàng ngày: CTR/CVR/CPI/spend pacing + red flags gian lận
[ ] Đánh giá tuần theo cohort: retention D1/D7, ROAS theo mốc ngày
[ ] Quyết định cắt/giữ/scale dựa trên ngưỡng đã định trước, không cảm tính
[ ] Refresh creative theo tín hiệu fatigue, không đợi hiệu suất sập hẳn
[ ] Báo cáo trung thực, có insight và khuyến nghị hành động cụ thể
```
