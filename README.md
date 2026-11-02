# FoodGo — Bộ tài liệu ngữ cảnh cho Claude Code

Bộ file này giúp Claude Code hiểu dự án trước khi tạo hoặc sửa code. Đặt các file này ở thư mục gốc project Android `FoodGo/`.

## Cách dùng
1. Tạo project Android Studio mới: **Empty Views Activity**, Kotlin, XML.
2. Mở thư mục project đó trong VS Code hoặc Claude Code.
3. Sao chép các file trong bộ này vào thư mục gốc project.
4. Mở Claude Code tại thư mục gốc.
5. Gửi prompt khởi đầu ở `PROMPT_KHOI_DAU.md`.
6. Sau đó giao từng nhiệm vụ nhỏ theo `CURRENT_TASK.md`, không yêu cầu Claude tạo cả ứng dụng trong một lần.

## Lưu ý quan trọng
- Đây là tài liệu định hướng, không phải mã nguồn ứng dụng.
- Hãy để Claude kiểm tra cấu trúc project thực tế trước khi sửa Gradle hoặc tạo file.
- Dự án dùng **Kotlin + XML + ViewBinding**, không tự ý chuyển sang Jetpack Compose.
- Nhóm có 3 thành viên. Cách chia việc ở `TEAM_TASKS.md` được thiết kế để giảm xung đột khi merge code.
- Bốn bộ ZIP giao diện hiện có (Khách hàng, Chủ quán, Tài xế, Admin) là nguồn tham chiếu chính. Đặt các ảnh đã giải nén vào một thư mục tham khảo riêng hoặc mở chúng song song khi làm UI. Không tự ý bỏ qua thiết kế có sẵn.
- Nếu chi tiết nào trong thiết kế chưa rõ, Claude phải ghi câu hỏi/giả định thay vì tự bịa ra luồng nghiệp vụ.
