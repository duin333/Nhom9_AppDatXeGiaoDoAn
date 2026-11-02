# FoodGo — Nhiệm vụ hiện tại

## Trạng thái
- [x] Đã có thiết kế giao diện 4 vai trò, nằm trong `design/` (Admin_Actor, ChuQuan_Actor, KhachHang_Actor, TaiXe_Actor).
- [x] Đã chốt công nghệ: Android Studio + Kotlin + XML + ViewBinding.
- [x] Đã tạo project Android Studio (Empty Views Activity), package `com.foodgo.app`.
- [x] Gradle Sync thành công, app mẫu chạy được trên emulator ("Hello World").
- [x] ViewBinding đã bật trong `app/build.gradle.kts`.
- [x] Đã đẩy lên GitHub: https://github.com/duin333/Nhom9_AppDatXeGiaoDoAn.git (nhánh `main`).
- [ ] Chưa có mã nguồn tính năng.
- [ ] Chưa chốt cấu trúc package và model dùng chung.

## Các quyết định đã chốt
- JDK 17 (`C:\Program Files\Java\jdk-17`), ghi trong `gradle/gradle-daemon-jvm.properties`. Mọi thành viên cần JDK 17.
- AGP 9.4.1 (Kotlin tích hợp sẵn, KHÔNG thêm plugin Kotlin riêng).
- compileSdk 37, targetSdk 37, minSdk 24.
- Java target: VERSION_11 (mặc định template, giữ nguyên).
- Gradle: chưa xác nhận (xem `gradle/wrapper/gradle-wrapper.properties`).
- `.idea/` và `local.properties` nằm trong `.gitignore`.

## Nhiệm vụ tiếp theo duy nhất
**Chốt cấu trúc package và model dùng chung (chưa code màn hình).**
1. Đề xuất cây package: `ui/`, `data/model/`, `data/repository/`, `viewmodel/`, `utils/`.
2. Chốt model: FoodItem, Restaurant, CartItem, Order, OrderStatus, UserRole (GroupOrder để sau).
3. Đối chiếu với trạng thái đơn trong thiết kế Chủ quán/Tài xế/Khách hàng để OrderStatus thống nhất.
4. Cả nhóm 3 người đồng ý trước khi chia code.

## File đã thêm/sửa
- Toàn bộ project Android khởi tạo, 8 file `.md`, thư mục `design/`.
- `.gitignore` thêm `.idea/`.

## Lỗi/giả định còn tồn tại
- Phiên bản Gradle chưa xác nhận.
- Bộ thiết kế chưa thấy màn hình Group Ordering (tính năng P1); cần nhóm quyết định thiết kế thêm hay làm theo mô tả.
- 2 thành viên còn lại chưa clone và kiểm tra build trên máy của họ.