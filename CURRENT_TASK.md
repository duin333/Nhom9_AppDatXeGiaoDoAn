# FoodGo — Nhiệm vụ hiện tại

## Trạng thái
- [x] Đã có thiết kế giao diện cho 4 vai trò dưới dạng ZIP/ảnh.
- [x] Đã chốt công nghệ: Android Studio + Kotlin + XML + ViewBinding.
- [x] JDK người dùng cho biết: JDK 17.
- [ ] Chưa tạo project Android Studio.
- [ ] Chưa có mã nguồn ứng dụng.
- [ ] Chưa xác nhận phiên bản Android Studio, Gradle, AGP và minSdk thực tế.

## Nhiệm vụ hiện tại của Claude Code
**Chưa code tính năng. Trước tiên hãy kiểm tra môi trường và lập kế hoạch tạo project.**

1. Xem thư mục hiện tại có phải project Android Studio hay chưa.
2. Nếu chưa có project, giải thích ngắn gọn cấu hình tạo project phù hợp:
   - Empty Views Activity
   - Kotlin
   - XML
   - ViewBinding
   - package dự kiến `com.foodgo.app` (chỉ dùng nếu người dùng chưa tạo package khác)
   - JDK 17 nếu tương thích với Gradle/Android Gradle Plugin của project; không tự ép phiên bản không tương thích.
3. Không tự ý tạo lại toàn bộ Gradle project nếu người dùng định tạo project bằng Android Studio. Có thể hướng dẫn tạo project trong Android Studio trước, sau đó kiểm tra file.
4. Khi project đã tồn tại, kiểm tra cấu trúc và đề xuất danh sách file/folder ban đầu.
5. Đọc thiết kế hiện có trước khi đề xuất code từng màn hình. Không giả định đã xem được ZIP/Figma nếu chúng chưa có trong workspace Claude Code.
6. Trả về checklist ngắn cho người dùng thực hiện, từng bước một.

## Định nghĩa hoàn thành
- Project được tạo trong Android Studio.
- Gradle Sync thành công.
- Ứng dụng mẫu chạy được trên emulator/thiết bị.
- ViewBinding đã bật.
- Chưa bắt đầu nhiều feature trước khi nền tảng được kiểm tra.

## Sau khi hoàn thành nhiệm vụ này
Cập nhật file này với:
- trạng thái hiện tại;
- các quyết định đã chốt;
- nhiệm vụ tiếp theo duy nhất;
- file được thêm/sửa;
- lỗi hoặc giả định còn tồn tại.
