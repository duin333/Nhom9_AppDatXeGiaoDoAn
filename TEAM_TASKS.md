# FoodGo — Phân chia công việc cho nhóm 3 người

## Nguyên tắc phối hợp
- Chia theo **module/feature**, không chia mỗi người vài màn hình bất kỳ trong cùng một file.
- Mỗi thành viên làm trên branch riêng; không code trực tiếp lên `main`.
- Chốt giao diện contract và model chung trước khi chia code.
- Một người chịu trách nhiệm tích hợp, nhưng không có nghĩa người đó làm hết phần khó.
- Mỗi PR/commit nên nhỏ, có mô tả và cách kiểm tra.
- Không để hai thành viên cùng sửa `MainActivity`, file điều hướng, theme hoặc cùng một layout trong cùng thời điểm nếu chưa thống nhất.

## Phân công đề xuất
Có thể đổi tên thành viên sau khi nhóm thống nhất.

### Thành viên A — Khách hàng & tích hợp điều hướng
**Chịu trách nhiệm chính**
- Khung ứng dụng và điều hướng chính.
- Trang chủ khách hàng, danh sách quán/món, tìm kiếm/lọc theo thiết kế.
- Chi tiết món ăn.
- Tích hợp các màn hình khách hàng với giỏ hàng.
- Quản lý quy tắc chung: package, navigation, theme, cách đặt tên.

**Không tự ý làm**
- Không tự thay đổi model dùng chung mà không báo nhóm.
- Không sửa sâu module Chủ quán/Tài xế/Admin ngoài phần tích hợp.

### Thành viên B — Giỏ hàng, đặt đơn & Group Ordering
**Chịu trách nhiệm chính**
- Giỏ hàng cá nhân, cập nhật số lượng và tổng tiền.
- Tạo đơn mẫu và màn hình trạng thái đơn phía khách hàng.
- Group Ordering: tạo phòng, tham gia bằng mã, giỏ chung, hiển thị người thêm món và tổng tiền.
- Thiết kế Repository/model liên quan đến Order và GroupOrder cùng thành viên A trước khi triển khai.
- Viết test/checklist cho các trường hợp tổng tiền, thêm/xóa món và thành viên.

**Ưu tiên**
- BC3 làm local/sample data chạy được.
- Báo cáo cuối mới nối backend/sync nếu khả thi.

### Thành viên C — Chủ quán, Tài xế, Admin & tính năng hỗ trợ
**Chịu trách nhiệm chính**
- Màn hình danh sách đơn và cập nhật trạng thái phía Chủ quán.
- Màn hình đơn được giao và cập nhật trạng thái phía Tài xế.
- Các màn hình quản trị cơ bản của Admin theo thiết kế.
- Allergy Guard và Eco Rewards sau khi luồng cốt lõi đã ổn định.
- Kiểm tra tính nhất quán trạng thái đơn giữa các vai trò.

**Lưu ý**
- BC3 ưu tiên một luồng demo gọn cho từng vai trò, chưa cần chức năng quản trị sâu.
- Scheduled Delivery và Smart Batch Delivery là phần mở rộng, không làm trước các luồng cốt lõi.

## Quy tắc chung về code
- Một file/feature có một người chịu trách nhiệm chính.
- Model dùng chung cần được thống nhất sớm: FoodItem, Restaurant, CartItem, Order, OrderStatus, UserRole; bổ sung GroupOrder khi bắt đầu tính năng đặt nhóm.
- Không tạo các class trùng tên ở nhiều package.
- Trước khi đổi chữ ký hàm/model dùng chung, báo cho các thành viên khác.
- Không commit file local secret, API key, mật khẩu, `local.properties` chứa đường dẫn máy cá nhân nếu repository không được cấu hình phù hợp.
- Mỗi thành viên cần hiểu và giải thích được phần mình code khi bảo vệ.

## Git workflow đề xuất
- `main`: bản ổn định có thể demo.
- `dev`: nhánh tích hợp (chỉ dùng nếu nhóm đã quen workflow này).
- `feature/customer-home`, `feature/cart-order`, `feature/owner-driver-admin` hoặc tên tương tự.
- Trước khi merge: đồng bộ code mới, kiểm tra conflict, chạy build nếu có thể.
- Commit message rõ nghĩa, ví dụ: `feat: add customer food detail screen`, `fix: recalculate group cart total`.

## Nhịp phối hợp
- Đầu buổi: thống nhất việc mỗi người sẽ hoàn thành và file nào sẽ đụng tới.
- Cuối buổi: mỗi người báo 3 ý: đã làm gì, còn vướng gì, việc tiếp theo.
- Tích hợp sớm và thường xuyên; không đợi sát hạn mới ghép code.
- Chọn một người điều phối tích hợp, nhưng phân công review chéo để cả nhóm đều hiểu tổng thể.
