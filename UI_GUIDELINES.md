# FoodGo — Quy chuẩn giao diện

## 1. Nguồn thiết kế
- Ưu tiên các màn hình PNG trong 4 bộ ZIP đã có: Khách hàng, Chủ quán, Tài xế, Admin.
- Trước khi code một màn hình, đối chiếu ảnh tham khảo và xác định: bố cục, nội dung, hành động chính, trạng thái và điều hướng.
- Không tự ý thay đổi toàn bộ phong cách chỉ vì Claude có mẫu UI mặc định.
- Nếu ảnh không đủ rõ, ghi giả định và hỏi lại thay vì bịa chi tiết.

## 2. Định hướng thương hiệu
Định hướng sơ bộ: **Fresh & Modern**, xanh lá + trắng, cảm giác giao đồ ăn sạch sẽ, thân thiện, hiện đại. Hãy ưu tiên màu đã có trong thiết kế gốc nếu khác với đề xuất bên dưới.

Palette đề xuất ban đầu (chỉ dùng nếu chưa có màu chuẩn từ thiết kế):
- Primary: `#247A4B`
- Primary light: `#E7F4E9`
- Background: `#F7F9F7`
- Surface: `#FFFFFF`
- Text primary: `#25352B`
- Text secondary: `#6B756E`
- Border: `#E2E8E3`
- Error: `#B42318`

Không dùng màu hard-code rải rác trong layout; tập trung vào `colors.xml` và theme.

## 3. Bố cục và khả năng dùng
- Có phân cấp thị giác rõ: tiêu đề, thông tin phụ, giá, CTA.
- Khoảng cách, bo góc, icon và kích thước nút nhất quán.
- Nội dung có thể cuộn khi màn hình nhỏ.
- Kiểm tra tràn chữ tiếng Việt và font scale.
- Không đặt nút quan trọng sát mép màn hình.
- Có trạng thái empty/loading/error khi phù hợp.
- Nút phải thực hiện hành động thật trong phạm vi hiện tại, không chỉ trang trí.

## 4. Hình ảnh món ăn
- Ưu tiên ảnh món ăn đúng nội dung, crop thống nhất, chất lượng đồng đều.
- Không dùng emoji thay ảnh món ăn chính.
- Không dùng ảnh placeholder hoặc ảnh không liên quan trong bản demo cuối.
- Đặt tên tài nguyên rõ ràng, viết thường và dùng dấu gạch dưới.
- Tránh tải quá nhiều ảnh lớn vào một màn hình.

## 5. Component dùng chung
Xem xét tái sử dụng:
- Primary/secondary button
- Input/search field
- Food card / restaurant card
- Price row
- Toolbar/top app bar
- Bottom navigation theo từng vai trò nếu thiết kế có
- Loading/empty/error state
- Badge trạng thái đơn

Không tạo component chung quá phức tạp nếu chỉ dùng một lần.

## 6. XML và ViewBinding
- Layout XML dễ đọc, tránh lồng quá nhiều cấp không cần thiết.
- Dùng ViewBinding thay cho `findViewById()` trong code Kotlin mới.
- Tách strings, colors, dimens và styles khi hợp lý.
- Dùng `dp` cho kích thước và `sp` cho chữ.
- Hạn chế đặt toàn bộ giao diện bằng code Kotlin.
