# Mẫu prompt giao nhiệm vụ nhỏ cho Claude Code

Hãy đọc các tài liệu dự án trước khi bắt đầu. Nhiệm vụ hiện tại:

**Mục tiêu:** [ghi một kết quả cụ thể, ví dụ: tạo màn hình chi tiết món ăn theo ảnh tham khảo]

**Phạm vi:**
- Chỉ làm [feature/màn hình cụ thể].
- Dùng Kotlin + XML + ViewBinding.
- Bám sát ảnh tham khảo đã có trong workspace.
- Dùng dữ liệu mẫu/repository hiện tại; không tự ý thêm backend hoặc thư viện mới.
- Không sửa module của thành viên khác.
- Không thay đổi model/API dùng chung nếu chưa nêu rõ lý do và ảnh hưởng.

**Tiêu chí chấp nhận:**
1. [UI/luồng phải có]
2. [nút nào phải hoạt động]
3. [trạng thái lỗi/empty/loading nếu có]
4. Project không có lỗi compile do thay đổi này.

Trước khi code, hãy nêu ngắn gọn file sẽ tạo/sửa. Sau khi code, liệt kê file đã thay đổi, cách kiểm tra thủ công và các giới hạn còn lại. Không tuyên bố đã build thành công nếu chưa chạy build.
