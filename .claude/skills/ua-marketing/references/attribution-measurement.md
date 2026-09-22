# Attribution & Đo lường

Mục lục: [Vì sao attribution khó hơn trước](#vì-sao-attribution-khó-hơn-trước) ·
[MMP](#mmp-mobile-measurement-partner) · [SKAdNetwork / SKAN 4](#skadnetwork--skan-4-ios) ·
[Mô hình attribution](#mô-hình-attribution) · [MMM](#mmm-marketing-mix-modeling) ·
[Incrementality Testing](#incrementality-testing) · [Đối chiếu số liệu giữa các nguồn](#đối-chiếu-số-liệu-giữa-các-nguồn)

## Vì sao attribution khó hơn trước

Trước đây, mỗi lượt cài đặt có thể gắn gần như chính xác với một click/impression cụ thể qua
device ID (IDFA trên iOS, GAID trên Android). Từ khi Apple giới thiệu App Tracking Transparency
(ATT — yêu cầu người dùng đồng ý mới được theo dõi liên-app) và các quy định privacy khác trên
toàn ngành, phần lớn traffic iOS không còn có device-level ID đáng tin cậy để attribution
chính xác 1-1. Kết quả: dữ liệu attribution ngày nay thường **tổng hợp (aggregated)**, **trễ**,
hoặc **có nhiễu**. Agent phải hiểu rõ giới hạn này để không suy diễn sai từ dữ liệu không đầy đủ.

## MMP (Mobile Measurement Partner)

Các nền tảng đo lường bên thứ ba độc lập, đóng vai trò "trọng tài" trung lập giữa nhà quảng cáo
và các network quảng cáo — vì mỗi network có động lực báo cáo có lợi cho mình nếu tự đo.

- **Các MMP phổ biến**: AppsFlyer, Adjust, Branch, Kochava, Singular.
- **Vai trò chính**:
  1. Gắn install/event với nguồn traffic (network, campaign, creative) qua SDK trong app.
  2. Hợp nhất dữ liệu từ nhiều network về một dashboard duy nhất để so sánh công bằng.
  3. Cung cấp lớp bảo vệ chống gian lận (fraud protection) — xem `references/fraud-prevention.md`.
  4. Chuyển tiếp dữ liệu về SKAdNetwork (iOS) và giải mã/mô hình hoá dữ liệu ẩn danh đó thành
     báo cáo campaign có thể đọc được (dùng mô hình xác suất do MMP xây dựng).
- **Nguyên tắc thiết lập**: định nghĩa rõ **cửa sổ attribution** (attribution window — thường
  7 ngày cho click, 1 ngày cho view/impression, có thể tuỳ chỉnh) và **mô hình attribution**
  trước khi launch, áp dụng nhất quán để so sánh công bằng giữa các kỳ báo cáo.

## SKAdNetwork / SKAN 4 (iOS)

Cơ chế attribution do chính Apple cung cấp, bảo toàn quyền riêng tư (không có device ID),
network tự báo cáo về Apple, Apple chuyển tiếp dữ liệu đã được làm nhiễu/trễ về nhà quảng cáo.

- **Conversion Value (CV)**: một số nguyên nhỏ (0-63 với fine-grained value) được app mã hoá để
  biểu diễn hành vi người dùng sau install (vd: đã hoàn tất tutorial, đã mua hàng, mức chi tiêu
  gần đúng) — phải thiết kế **schema mã hoá CV** cẩn thận vì không gian giá trị rất hạn chế,
  đánh đổi giữa việc bắt được nhiều tín hiệu hành vi vs. độ chi tiết mỗi tín hiệu.
- **Crowd anonymity**: Apple chỉ gửi CV về nhà quảng cáo khi đủ số lượng install trong nhóm đó
  (đảm bảo không thể suy ra danh tính cá nhân) — campaign/traffic nhỏ có thể không bao giờ nhận
  được CV (rơi vào "null"), khiến dữ liệu về các chiến dịch nhỏ/dài đuôi rất hạn chế.
- **SKAN 4 cải tiến so với SKAN 3**: nhiều cửa sổ báo cáo hơn (postback 0, 1, 2, tối đa ~35
  ngày thay vì chỉ 1 lần), **coarse-grained conversion value** (low/medium/high) dùng khi crowd
  anonymity chưa đủ để trả fine-grained value, và **hierarchical source identifier** (SKAN 4 mở
  rộng số ký tự source ID) giúp phân biệt campaign/creative chi tiết hơn (dù vẫn cần đủ crowd
  anonymity để nhận giá trị chi tiết nhất).
- **Hệ quả thực tế**: báo cáo iOS thường trễ vài ngày, không có dữ liệu ở cấp độ người dùng cá
  nhân, và các campaign/audience nhỏ có độ tin cậy dữ liệu thấp hơn nhiều so với Android
  (nơi vẫn còn nhiều tín hiệu device-level hơn, tuỳ thị trường và chính sách Google hiện hành).

## Mô hình attribution

- **Last-click / Last-touch**: gán toàn bộ công cho điểm chạm cuối cùng trước install/conversion.
  Đơn giản, phổ biến nhất, nhưng đánh giá thấp vai trò của các kênh "mở đường" (branding, video
  view không click).
- **Multi-touch attribution (MTA)**: phân bổ công trạng cho nhiều điểm chạm theo trọng số (linear,
  time-decay, position-based...). Chính xác hơn về lý thuyết nhưng ngày càng khó thực hiện đúng
  vì thiếu dữ liệu device-level xuyên kênh (đặc biệt trên iOS).
- **View-through attribution**: gán conversion cho người *thấy* quảng cáo dù không click. Dễ bị
  thổi phồng giá trị các kênh có impression khối lượng lớn (display, video) — nên đặt cửa sổ
  view-through ngắn hơn nhiều so với click-through và diễn giải thận trọng.

## MMM (Marketing Mix Modeling)

Mô hình thống kê dùng dữ liệu **tổng hợp theo thời gian** (chi tiêu theo kênh theo ngày/tuần,
doanh thu/KPI tổng thể, các yếu tố ngoại sinh như mùa vụ, giá, sự kiện) để ước tính đóng góp
của từng kênh vào kết quả kinh doanh — **không cần** dữ liệu attribution ở cấp độ người dùng.

- **Ưu điểm**: không bị ảnh hưởng bởi giới hạn privacy/IDFA, nhìn được cả tác động dài hạn và
  hiệu ứng "halo" (kênh này ảnh hưởng gián tiếp đến hiệu quả kênh khác, vd: brand ads thúc đẩy
  hiệu suất performance ads).
- **Nhược điểm**: cần lượng dữ liệu lịch sử đủ dài (thường hàng chục tuần trở lên) và đủ biến
  động chi tiêu giữa các kênh để mô hình có ý nghĩa thống kê; không phản hồi nhanh theo thời
  gian thực như MMP, phù hợp cho quyết định ngân sách chiến lược hơn là tối ưu chiến dịch hàng ngày.

## Incrementality Testing

Phương pháp thực nghiệm để trả lời câu hỏi quan trọng nhất mà attribution model không tự trả
lời được: "Nếu KHÔNG chạy quảng cáo này, người dùng đó có tự đến/tự mua hàng không?" (traffic
đó có thật sự **tăng thêm - incremental** hay chỉ "cướp công" từ organic/kênh khác).

- **Ghost bids / PSA (Public Service Ads) test**: một số network hỗ trợ chạy "quảng cáo giả"
  (không thực sự hiển thị) cho nhóm đối chứng để so sánh với nhóm thực sự nhận quảng cáo, giữ
  nguyên hành vi đấu giá của thuật toán.
- **Geo holdout test**: chia thị trường/khu vực địa lý thành nhóm chạy ads và nhóm không chạy
  (hoặc chạy mức chi tiêu khác nhau), so sánh chênh lệch kết quả giữa hai nhóm để ước tính tác
  động thật (incremental lift) của quảng cáo.
- **Khi nào cần incrementality test**: khi ROAS/CPI báo cáo trông rất tốt nhưng tăng trưởng
  tổng thể của app không tương xứng — dấu hiệu điển hình của việc kênh đang "ăn" traffic vốn dĩ
  sẽ đến tự nhiên (organic cannibalization) chứ không tạo ra người dùng mới thật sự.

## Đối chiếu số liệu giữa các nguồn

Khi số liệu network tự báo cáo và MMP lệch nhau (thường xảy ra), quy trình xử lý:

1. Xác nhận **cùng cửa sổ attribution và cùng mô hình attribution** — phần lớn chênh lệch đến
   từ khác biệt cấu hình, không phải lỗi hệ thống.
2. Coi **MMP là nguồn "sự thật" (source of truth)** để ra quyết định ngân sách/tối ưu, vì đây là
   bên trung lập; số liệu network dùng để tối ưu trong nền tảng đó (bidding) nhưng không dùng để
   so sánh cross-channel.
3. Nếu chênh lệch quá lớn (vượt ngưỡng thường thấy, ví dụ >20-30%) và không giải thích được bằng
   khác biệt cấu hình, nghi ngờ vấn đề tracking (SDK tích hợp sai, mất event) hoặc gian lận
   — xem `references/fraud-prevention.md`.
