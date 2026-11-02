# FoodGo — Hướng dẫn làm việc cho Claude Code

## 1. Bối cảnh
FoodGo là ứng dụng Android giao đồ ăn phục vụ đồ án môn học. Nhóm có 3 thành viên. Thiết kế đã có cho 4 vai trò: Khách hàng, Chủ quán, Tài xế và Admin. Ưu tiên tận dụng các màn hình/luồng trong bộ ZIP thiết kế đã cung cấp, không thay bằng template giao đồ ăn chung chung.

## 2. Công nghệ bắt buộc
- Android Studio
- Kotlin
- XML layouts
- ViewBinding bật trong module app
- Không dùng Jetpack Compose trừ khi người dùng yêu cầu rõ ràng.
- Không tự ý thêm framework hoặc thư viện lớn.
- Ưu tiên các API Android và thư viện ổn định, tương thích cấu hình project thực tế.
- JDK hiện có của người dùng: JDK 17. Hãy kiểm tra Gradle/JDK thực tế trước khi đề xuất đổi phiên bản.

## 3. Cách tổ chức code
- Dùng MVVM đơn giản, có Repository khi cần; tránh Clean Architecture phức tạp quá mức.
- Tổ chức theo feature/package, ví dụ: `ui/`, `data/model/`, `data/repository/`, `viewmodel/`, `utils/`.
- Mỗi Activity/Fragment dùng ViewBinding và phải giải phóng binding đúng cách nếu dùng Fragment.
- Không viết toàn bộ ứng dụng vào một Activity.
- Tách dữ liệu mẫu khỏi code giao diện để sau này thay bằng dữ liệu thật.
- Không lặp lại màu sắc, kích thước, style ở nhiều nơi; dùng `colors.xml`, `dimens.xml`, `themes.xml`, drawable và các component tái sử dụng phù hợp.

## 4. Quy tắc làm việc an toàn
Trước mỗi nhiệm vụ:
1. Đọc `CLAUDE.md`, `PROJECT_PLAN.md`, `UI_GUIDELINES.md`, `TEAM_TASKS.md`, `CURRENT_TASK.md`.
2. Kiểm tra các file hiện có trước khi tạo/sửa.
3. Nêu ngắn gọn kế hoạch và danh sách file dự kiến bị ảnh hưởng.
4. Chỉ làm đúng phạm vi nhiệm vụ hiện tại.
5. Không ghi đè file hoặc xóa code đang có nếu chưa giải thích lý do.
6. Không tự ý thay đổi Gradle, package name, minSdk hoặc kiến trúc nếu không cần thiết.
7. Sau khi làm, liệt kê file đã tạo/sửa, cách chạy/kiểm tra và lỗi còn lại.
8. Không tuyên bố đã chạy build/test nếu chưa thực sự chạy.

## 5. Chất lượng UI
- Bám sát bộ thiết kế có sẵn trong 4 ZIP.
- Tránh giao diện generic, sơ sài, quá nhiều khoảng trắng vô lý hoặc chỉ dùng placeholder.
- Món ăn nên dùng hình ảnh phù hợp, chất lượng đồng đều và crop nhất quán. Không dùng ảnh vỡ, ảnh sai món hoặc emoji làm ảnh món ăn chính.
- Có trạng thái loading/empty/error khi phù hợp.
- Kiểm tra chữ tiếng Việt, tràn chữ, kích thước nút và khả năng cuộn.
- Tạo component dùng chung cho button, food card, input, toolbar và bottom navigation khi hợp lý.
- Không làm đẹp bằng cách phá vỡ khả năng sử dụng hoặc luồng nghiệp vụ.

## 6. Phạm vi tính năng
Tính năng cốt lõi: xem món ăn, chi tiết món, giỏ hàng, đặt đơn, quản lý đơn theo vai trò.
Tính năng khác biệt ưu tiên: **Group Ordering** — tạo/join phòng đặt món nhóm và thêm món vào giỏ chung.
Tính năng hỗ trợ theo mức độ ổn định:
- Allergy Guard: cảnh báo thông tin dị ứng dựa trên dữ liệu thành phần đã khai báo; không khẳng định món ăn chắc chắn an toàn.
- Eco Rewards: tùy chọn không lấy dụng cụ nhựa và điểm thưởng xanh.
- Scheduled Delivery: đặt lịch giao hàng, nếu thời gian cho phép.
- Smart Batch Delivery: chỉ mô phỏng/hiển thị đề xuất gom đơn nếu chưa có backend và thuật toán thật; không tuyên bố đã tối ưu tuyến giao hàng thật.

## 7. Dữ liệu và backend
- BC3: dùng dữ liệu mẫu/local state để hoàn thiện UI và luồng demo trước.
- Báo cáo cuối: đề xuất Firebase/giải pháp đồng bộ sau khi mô hình dữ liệu và luồng chính đã ổn định.
- Không trộn dữ liệu giả với dữ liệu thật mà không đánh dấu rõ.
- Không nhúng API key, mật khẩu hoặc thông tin bí mật vào source code.
- Không khẳng định đồng bộ realtime nếu chưa tích hợp và kiểm thử backend thật.

## 8. Tiêu chí hoàn thành một nhiệm vụ
Một nhiệm vụ chỉ được xem là hoàn thành khi:
- Code nằm đúng package và không tạo file trùng.
- Giao diện/luồng hoạt động trong phạm vi yêu cầu.
- Không có lỗi compile rõ ràng; nếu có công cụ build thì chạy build phù hợp.
- Có hướng dẫn kiểm tra thủ công.
- Nêu các giới hạn còn lại, không giấu lỗi.
