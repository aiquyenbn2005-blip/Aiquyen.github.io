# Ngân sách & Chiến lược Scale

Mục lục: [Nguyên tắc phân bổ ngân sách](#nguyên-tắc-phân-bổ-ngân-sách) ·
[Scale dọc vs Scale ngang](#scale-dọc-vertical-vs-scale-ngang-horizontal) ·
[Quy tắc tăng/giảm ngân sách an toàn](#quy-tắc-tănggiảm-ngân-sách-an-toàn) ·
[Day-parting & phân bổ theo thời gian](#day-parting--phân-bổ-theo-thời-gian) ·
[Phân bổ đa kênh](#phân-bổ-đa-kênh) · [Khi nào tắt một chiến dịch/ad set](#khi-nào-tắt-một-chiến-dịchad-set)

## Nguyên tắc phân bổ ngân sách

- Ngân sách nên phân bổ theo **hiệu suất biên (marginal ROAS/CPA)**, không phải hiệu suất trung
  bình. Một kênh có ROAS trung bình cao nhưng đã gần chạm trần quy mô khả dụng (audience đã
  bão hoà) sẽ cho ROAS biên thấp dần nếu đổ thêm tiền — lúc đó nên chuyển ngân sách tăng thêm
  sang kênh/ad set khác còn dư địa, dù ROAS trung bình của nó thấp hơn.
- Luôn dành một phần ngân sách cố định cho **thử nghiệm** (kênh mới, định dạng mới, thị trường
  mới) — thường 5-15% tổng ngân sách UA — để tránh phụ thuộc hoàn toàn vào các kênh đã biết và
  bị động khi các kênh đó thay đổi thuật toán/chính sách/hiệu suất.
- Ngân sách kiểm thử (test) phải đủ lớn để đạt ý nghĩa thống kê nhưng đủ nhỏ để giới hạn rủi ro
  — xác định trước "ngân sách rủi ro chấp nhận được" (vd: không quá X% ngân sách tuần cho một
  thử nghiệm chưa chứng minh) thay vì quyết định ngẫu hứng giữa chừng.

## Scale dọc (Vertical) vs Scale ngang (Horizontal)

- **Scale dọc**: tăng ngân sách của ad set/campaign đang chạy tốt. Rủi ro: tăng quá nhanh (kinh
  nghiệm ngành thường khuyến nghị không tăng quá ~20-30%/lần trong vòng 24-48 giờ) sẽ khiến
  thuật toán quay lại learning phase, tạm thời làm giảm hiệu suất và tăng CPA/CPI.
- **Scale ngang**: nhân bản chiến lược đang thắng sang audience mới, thị trường mới, hoặc
  campaign mới cùng cấu hình — giữ nguyên ad set đang thắng không bị xáo trộn, đồng thời mở
  rộng quy mô tổng thể. Thường an toàn hơn scale dọc quá nhanh vì không phá vỡ learning phase
  của ad set đang hoạt động tốt.
- Kết hợp cả hai theo nhịp độ: scale ngang để mở rộng nhanh, xen kẽ scale dọc từng bước nhỏ có
  kiểm soát cho các ad set đã chứng minh hiệu suất ổn định qua thời gian.

## Quy tắc tăng/giảm ngân sách an toàn

- Tăng ngân sách theo bước nhỏ, có khoảng nghỉ để quan sát trước khi tăng tiếp (không tăng dồn
  dập nhiều lần trong thời gian ngắn).
- Trước khi tăng ngân sách, xác nhận hiệu suất hiện tại đã ổn định qua đủ thời gian/khối lượng
  dữ liệu (không tăng ngân sách dựa trên vài ngày dữ liệu biến động mạnh).
- Khi giảm ngân sách hoặc tạm dừng, ưu tiên giảm dần thay vì tắt đột ngột toàn bộ nếu có thể,
  trừ khi có dấu hiệu gian lận hoặc lỗi tracking nghiêm trọng cần dừng ngay lập tức.
- Theo dõi sát chỉ số ngay sau mỗi lần thay đổi ngân sách lớn — biến động hiệu suất trong 24-72
  giờ đầu sau thay đổi thường phản ánh việc học lại của thuật toán, không nhất thiết là tín hiệu
  thật về chất lượng audience.

## Day-parting & phân bổ theo thời gian

- Với một số ngành (app thương mại điện tử, dịch vụ theo giờ hành chính), hiệu suất chuyển đổi
  có thể khác nhau rõ rệt theo giờ trong ngày/ngày trong tuần — phân tích dữ liệu lịch sử để
  cân nhắc phân bổ ngân sách nhiều hơn vào khung giờ hiệu suất cao, nếu nền tảng hỗ trợ kiểm
  soát này (lưu ý: nhiều nền tảng tự động hoá cao như UAC không hỗ trợ day-parting thủ công).
- Cẩn trọng không suy diễn day-parting từ dữ liệu quá ít — biến động ngẫu nhiên theo giờ dễ bị
  nhầm là pattern thật nếu mẫu nhỏ.

## Phân bổ đa kênh

- Xây **mô hình phân bổ mục tiêu** (target allocation) dựa trên hiệu suất lịch sử + dung lượng
  ước tính (khả năng chi tiêu thêm mà không giảm hiệu suất biên) của từng kênh, cập nhật định kỳ
  (vd: hàng tuần/hàng tháng) thay vì cố định vĩnh viễn.
- Không nên đặt "trứng vào một giỏ" dù một kênh đang vượt trội — thay đổi thuật toán, chính
  sách, hoặc chi phí đấu giá (do đối thủ tăng chi tiêu) có thể khiến hiệu suất kênh đó xấu đi
  đột ngột; đa dạng hoá là một hình thức quản trị rủi ro, không chỉ là tối ưu hiệu suất.
- Với ngân sách hạn chế, ưu tiên tập trung đủ sâu vào 1-2 kênh để đạt ngưỡng dữ liệu tối thiểu
  giúp thuật toán học hiệu quả, thay vì dàn trải quá mỏng qua nhiều kênh khiến không kênh nào
  đủ dữ liệu để tối ưu tốt.

## Khi nào tắt một chiến dịch/ad set

Đặt ngưỡng rõ ràng **trước khi launch**, tránh quyết định cảm tính giữa chừng:

- Không đạt CPI/CPA mục tiêu sau khi đã đủ ngân sách/thời gian để thoát learning phase (thường
  vài ngày đến một tuần tuỳ nền tảng và khối lượng chi tiêu).
- Retention D1/D7 thấp hơn đáng kể so với benchmark của các kênh khác đang chạy — dấu hiệu chất
  lượng traffic kém dù CPI có thể vẫn đẹp.
- ROAS ở mốc ngày đã định (D7/D30) thấp hơn ngưỡng tối thiểu đã thống nhất với business, và
  không có xu hướng cải thiện qua các thử nghiệm tối ưu đã thực hiện.
- Có dấu hiệu gian lận rõ ràng (xem `references/fraud-prevention.md`) — dừng ngay, không chờ
  đủ dữ liệu thống kê trong trường hợp này.
