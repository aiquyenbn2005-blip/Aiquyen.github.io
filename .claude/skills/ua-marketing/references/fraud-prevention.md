# Chống Gian lận Quảng cáo (Ad Fraud)

Mục lục: [Vì sao fraud là rủi ro nghiêm trọng](#vì-sao-fraud-là-rủi-ro-nghiêm-trọng) ·
[Các dạng gian lận phổ biến](#các-dạng-gian-lận-phổ-biến) · [Dấu hiệu cảnh báo](#dấu-hiệu-cảnh-báo-red-flags) ·
[Cơ chế phòng vệ](#cơ-chế-phòng-vệ) · [Quy trình xử lý khi nghi ngờ](#quy-trình-xử-lý-khi-nghi-ngờ)

## Vì sao fraud là rủi ro nghiêm trọng

Gian lận quảng cáo không chỉ gây lãng phí ngân sách trực tiếp — nó còn **làm nhiễu dữ liệu**
dùng để huấn luyện thuật toán tối ưu (thuật toán sẽ học sai "chân dung người dùng chất lượng"
nếu bị nhiễm dữ liệu giả), làm sai lệch mọi phân tích LTV/ROAS dựa trên traffic đó, và trong
trường hợp incent/motivated traffic còn có thể vi phạm chính sách nền tảng dẫn đến khoá tài
khoản quảng cáo.

## Các dạng gian lận phổ biến

- **Click spamming/click flooding**: gửi lượng lớn click giả (không có impression thật tương
  ứng) hy vọng "trúng" install tự nhiên/organic để nhận công attribution (last-click).
- **Click injection**: phần mềm độc hại trên thiết bị Android phát hiện lúc app khác chuẩn bị
  được cài (qua broadcast receiver) và bắn một click giả ngay trước khi cài đặt hoàn tất để
  "cướp" attribution của install đó (kể cả install đến từ nguồn organic hoặc kênh khác).
- **SDK spoofing**: giả mạo dữ liệu gửi từ SDK đo lường (giả install, giả event) mà không có
  thiết bị/người dùng thật đứng sau — thường ở quy mô lớn, tự động hoá.
- **Device farm / Install farm**: dùng nhiều thiết bị thật (hoặc giả lập) vận hành thủ công/bán
  tự động để tạo install thật về mặt kỹ thuật nhưng không có ý định sử dụng app thật.
- **Bot traffic**: click/impression tạo bởi phần mềm tự động thay vì người dùng thật.
- **Incentivized/motivated install không khai báo**: traffic được trả thưởng để cài đặt (tiền,
  điểm thưởng trong app khác) nhưng network không minh bạch tiết lộ đây là traffic incent —
  loại traffic này có retention/LTV cực thấp vì người dùng không có nhu cầu thật.
- **Attribution hijacking**: các hình thức "cướp công" install vốn dĩ sẽ tự đến (organic) bằng
  các kỹ thuật click giả gắn ngay trước thời điểm install để giành attribution.

## Dấu hiệu cảnh báo (red flags)

- CTR bất thường cao nhưng CVR (install/click) bất thường thấp, hoặc ngược lại (install nhiều
  bất thường so với lượng click/impression ghi nhận được).
- Retention D1 gần như bằng 0 từ một nguồn traffic cụ thể, trong khi các nguồn khác bình thường.
- Thời gian giữa click và install (click-to-install time - CTIT) quá ngắn bất thường (gần như
  tức thời, thấp hơn cả thời gian tải app thực tế thường mất) — dấu hiệu điển hình của click
  injection/spamming.
- Phân bố địa lý/thiết bị bất thường: tập trung bất thường vào một dải IP, một model thiết bị
  hiếm, hoặc một hệ điều hành/phiên bản cụ thể không tương xứng với thị trường mục tiêu.
- Tỷ lệ uninstall ngay sau install cao bất thường từ một nguồn cụ thể.
- Chênh lệch lớn giữa số liệu network tự báo cáo và số liệu MMP mà không giải thích được bằng
  khác biệt cấu hình attribution.

## Cơ chế phòng vệ

- **Luôn dùng MMP làm lớp trung gian đo lường** thay vì để network tự báo cáo trực tiếp — hầu
  hết MMP lớn (AppsFlyer, Adjust, Singular...) có bộ máy phát hiện gian lận tích hợp sẵn, chặn
  hoặc gắn cờ install/click đáng ngờ trước khi tính vào báo cáo và trước khi trả tiền cho network.
- **Thiết lập ngưỡng CTIT hợp lý** trong cấu hình MMP để tự động loại click injection rõ ràng.
- **Theo dõi retention/behavior theo cohort nguồn traffic** định kỳ (không chỉ nhìn CPI/volume)
  — đây là "tuyến phòng thủ cuối" phát hiện gian lận tinh vi lọt qua các bộ lọc tự động.
- **Thận trọng đặc biệt với các network/affiliate không rõ nguồn traffic** (thường ở mô hình
  CPI network/incent network) — yêu cầu minh bạch về nguồn traffic, bắt đầu với ngân sách nhỏ
  và kiểm tra chất lượng kỹ trước khi tăng chi tiêu hoặc trả hoa hồng lớn.
- **Đối chiếu định kỳ** số liệu giữa các nguồn (network vs MMP vs analytics nội bộ) theo quy
  trình ở `references/attribution-measurement.md`.

## Quy trình xử lý khi nghi ngờ

1. **Cô lập nguồn nghi ngờ** — tạm dừng ngân sách/ad set/network đó ngay lập tức, không chờ
   phân tích đầy đủ xong mới hành động (chi phí dừng nhầm thấp hơn nhiều so với tiếp tục chi
   tiền cho traffic gian lận).
2. **Thu thập bằng chứng** từ báo cáo fraud detection của MMP, dữ liệu CTIT, phân bố thiết
   bị/địa lý, và so sánh retention với các nguồn khác trong cùng kỳ.
3. **Đối chất với network/affiliate** dựa trên bằng chứng cụ thể, yêu cầu giải trình hoặc hoàn
   tiền theo điều khoản hợp đồng/chính sách nền tảng nếu có.
4. **Cập nhật bộ lọc phòng vệ** (ngưỡng CTIT, danh sách chặn thiết bị/IP nếu nền tảng hỗ trợ)
   để ngăn tái diễn từ cùng nguồn.
5. **Ghi nhận vào hồ sơ đánh giá network** để tham chiếu khi quyết định phân bổ ngân sách trong
   tương lai — network/affiliate có lịch sử traffic gian lận nên bị giảm ưu tiên hoặc loại bỏ
   khỏi danh sách kênh sử dụng.
