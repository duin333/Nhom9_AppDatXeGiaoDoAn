# FoodGo — Kế hoạch sản phẩm và phạm vi

## 1. Mục tiêu
Xây dựng ứng dụng Android giao đồ ăn có UI chỉn chu, các luồng chức năng dễ demo và có điểm nhấn riêng. Ứng dụng phục vụ đồ án học phần, vì vậy ưu tiên tính ổn định, giải thích được khi bảo vệ và triển khai theo từng giai đoạn.

## 2. Vai trò người dùng
1. **Khách hàng**: duyệt món/quán, tìm kiếm, xem chi tiết, thêm giỏ, đặt hàng, theo dõi đơn, tham gia đặt nhóm.
2. **Chủ quán**: xem đơn đến, chấp nhận/từ chối theo luồng được thiết kế, cập nhật trạng thái chuẩn bị.
3. **Tài xế**: xem đơn được giao, cập nhật trạng thái nhận/giao đơn theo luồng thiết kế.
4. **Admin**: màn hình quản trị/tổng quan và quản lý cơ bản theo bộ thiết kế.

Không cần xây toàn bộ backend quản trị thực tế ngay ở BC3. Mỗi vai trò phải có luồng demo rõ ràng và nhất quán.

## 3. Tính năng cốt lõi
- Chọn vai trò/đăng nhập demo phù hợp thiết kế.
- Trang chủ, danh sách quán/món, tìm kiếm/lọc nếu có trong thiết kế.
- Chi tiết món ăn.
- Giỏ hàng và thay đổi số lượng.
- Tạo đơn/đặt hàng.
- Màn hình lịch sử hoặc trạng thái đơn theo thiết kế.
- Luồng xử lý đơn cho Chủ quán.
- Luồng nhận/cập nhật đơn cho Tài xế.
- Các màn hình Admin ở mức phù hợp với đồ án.

## 4. Tính năng tạo khác biệt — ưu tiên
### P1: Group Ordering (tính năng chủ lực)
- Người tạo tạo phòng đặt món nhóm.
- Cho phép chia sẻ mã phòng/QR/link nếu phù hợp phạm vi; ở giai đoạn đầu ưu tiên mã phòng.
- Người khác tham gia phòng.
- Thành viên thêm món vào giỏ nhóm.
- Hiển thị rõ món nào do thành viên nào thêm.
- Có tổng tiền và cách chia tiền đơn giản, minh bạch.
- BC3: mô phỏng bằng dữ liệu mẫu/local state; cần demo được luồng tạo phòng → tham gia → thêm món.
- Báo cáo cuối: tích hợp lưu trữ/đồng bộ nếu khả thi; chỉ gọi là realtime sau khi kiểm thử trên ít nhất hai phiên chạy/thiết bị.

### P2: Allergy Guard
- Hồ sơ khách hàng có thể khai báo thành phần cần tránh.
- Món ăn có metadata thành phần/dị ứng mẫu.
- Hiển thị cảnh báo rõ ràng khi món có thành phần trùng với hồ sơ.
- Luôn ghi rõ đây là cảnh báo dựa trên dữ liệu được cung cấp; người dùng cần xác nhận với nhà hàng. Không bảo đảm món ăn an toàn tuyệt đối.

### P3: Eco Rewards
- Tùy chọn “Không lấy dụng cụ nhựa”.
- Cộng điểm xanh theo quy tắc minh bạch khi đặt đơn thành công (hoặc mô phỏng ở BC3).
- Hiển thị điểm và lịch sử/đổi voucher nếu đủ thời gian.
- Tránh cộng điểm nhiều lần khi trạng thái đơn thay đổi lặp lại.

### P4: Scheduled Delivery
- Chọn ngày/khung giờ giao hàng.
- Kiểm tra dữ liệu đầu vào và hiển thị lại lịch đã chọn.
- Có thể làm ở giai đoạn cuối nếu luồng cốt lõi ổn định.

### P5: Smart Batch Delivery
- Giai đoạn đầu chỉ là ý tưởng mở rộng hoặc demo đề xuất gom đơn.
- Không tuyên bố tối ưu tuyến đường/giảm chi phí thật khi chưa có dữ liệu, thuật toán và kiểm thử thực tế.

## 5. Mục tiêu theo đợt báo cáo
### BC3 — giao diện + chức năng mức trung bình
Mục tiêu: có ứng dụng chạy được, giao diện tương đối hoàn chỉnh và luồng chức năng cốt lõi demo được.
- Tạo project sạch và cấu trúc nhất quán.
- Dùng dữ liệu mẫu có tổ chức.
- Hoàn thiện các màn hình quan trọng theo thiết kế.
- Điều hướng giữa các màn hình chính.
- Demo được luồng khách hàng xem món → thêm giỏ → tạo đơn mẫu.
- Có luồng cơ bản cho Chủ quán, Tài xế, Admin.
- Có bản demo Group Ordering ở mức local/sample data nếu đủ thời gian.
- Chưa bắt buộc backend realtime hoàn chỉnh; không giả vờ rằng dữ liệu đã đồng bộ thật.

### Báo cáo cuối — hoàn thiện chi tiết
- Hoàn thiện các luồng nghiệp vụ và kiểm tra lỗi.
- Tích hợp backend/lưu trữ đồng bộ nếu phù hợp với thời gian và cấu hình.
- Hoàn thiện Group Ordering trước các tính năng phụ.
- Bổ sung Allergy Guard và Eco Rewards.
- Scheduled Delivery chỉ triển khai nếu chức năng chính ổn định.
- Kiểm thử, sửa UI, chuẩn bị kịch bản demo, báo cáo và giải thích code.

## 6. Quy tắc ưu tiên
1. App build được và mở được.
2. Luồng khách hàng cốt lõi hoạt động.
3. Các vai trò khác có luồng demo nhất quán.
4. Group Ordering.
5. Chất lượng UI và xử lý trạng thái/lỗi.
6. Allergy Guard và Eco Rewards.
7. Scheduled Delivery.
8. Smart Batch Delivery chỉ làm khi có thời gian.

## 7. Điều chưa được tự suy đoán
- Chi tiết màn hình phải đối chiếu bộ ZIP/Figma của nhóm.
- Chưa có xác nhận backend/database cuối cùng.
- Chưa xác nhận cách đăng nhập/xác thực thực tế.
- Chưa xác nhận thanh toán thật; mặc định không tích hợp cổng thanh toán thật.
- Chưa xác nhận bản đồ/GPS thật; không tự thêm nếu không cần.
