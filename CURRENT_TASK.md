# FoodGo — Nhiệm vụ hiện tại

## Trạng thái
- [x] Thiết kế gốc nằm trong `design/` (Admin_Actor, ChuQuan_Actor, KhachHang_Actor, TaiXe_Actor).
- [x] Công nghệ: Android Studio + Kotlin + XML + ViewBinding.
- [x] Project Android Studio (Empty Views Activity), package `com.foodgo.app`.
- [x] Gradle Sync thành công; app mẫu chạy được trên emulator.
- [x] ViewBinding đã bật.
- [x] Đã đẩy lên GitHub: https://github.com/duin333/Nhom9_AppDatXeGiaoDoAn.git (nhánh `main`).
- [x] **Chốt phạm vi: chỉ actor Khách hàng.** Bỏ Admin, Chủ quán, Tài xế.
- [x] Chốt điểm nhấn: Group Ordering (P1), Eco Rewards (P2), Scheduled Delivery (P3), Allergy Guard (P4, nếu còn thời gian). Smart Batch chỉ là lựa chọn phí ship mô phỏng.
- [ ] Chưa có mã nguồn tính năng.
- [ ] Chưa có brand kit, cây package, model dùng chung.
- [ ] Chưa có thiết kế cho Group Ordering, Eco, Hẹn giờ, Allergy Guard.

## Quyết định đã chốt
- JDK 17 (`C:\Program Files\Java\jdk-17`), ghi trong `gradle/gradle-daemon-jvm.properties`. Mọi thành viên cần JDK 17.
- AGP 9.4.1 (Kotlin tích hợp sẵn, KHÔNG thêm plugin Kotlin riêng).
- compileSdk 37, targetSdk 37, minSdk 24, Java target 11.
- Phiên bản Gradle: chưa xác nhận (xem `gradle/wrapper/gradle-wrapper.properties`).
- `.idea/` và `local.properties` nằm trong `.gitignore`.
- Không có `UserRole`. BC3 dùng dữ liệu mẫu; realtime thật để dành báo cáo cuối.
- Thư viện đề xuất (chờ nhóm đồng ý): Glide, Lottie.

## Nhiệm vụ tiếp theo duy nhất
**Giai đoạn 0, bước 1: Brand kit + cây package + model dùng chung (chưa code màn hình).**
1. Đề xuất bảng màu xanh nhiều tầng + màu nhấn ấm, font, style nút/thẻ/ô nhập → `colors.xml`, `themes.xml`, `dimens.xml`.
2. Chốt cây package: `ui/`, `data/model/`, `data/repository/`, `data/sample/`, `viewmodel/`, `utils/`.
3. Chốt model: FoodItem (có thành phần), Restaurant, CartItem, Order, OrderStatus, GroupOrder, GroupMember, GroupCartItem, Voucher.
4. Cả nhóm 3 người duyệt trước khi chia code.

Sau đó (từng nhiệm vụ riêng): dữ liệu mẫu → khung điều hướng → chia code A/B/C theo `TEAM_TASKS.md`.

## Việc nhóm cần làm ngoài code
- Cập nhật `UI_GUIDELINES.md` cho khớp brand kit khi được chốt.
- Chọn ảnh món (Unsplash/Pexels), cùng tỉ lệ và tông màu.
- Quyết định có thêm Glide/Lottie không.
- 2 thành viên còn lại clone repo, cài JDK 17, kiểm tra build.

## File đã thêm/sửa
- Toàn bộ project Android khởi tạo, 8 file `.md`, thư mục `design/`, `.gitignore`.
- Lần cập nhật này: `CLAUDE.md`, `PROJECT_PLAN.md`, `TEAM_TASKS.md`, `CURRENT_TASK.md`.

## Lỗi/giả định còn tồn tại
- `UI_GUIDELINES.md`, `README.md`, `PROMPT_*.md` còn nhắc 4 vai trò; ưu tiên `CLAUDE.md` khi mâu thuẫn.
- Gradle version chưa xác nhận.
- Chưa có thiết kế các màn hình mới; không được bịa luồng, cần ghi giả định và hỏi nhóm.
