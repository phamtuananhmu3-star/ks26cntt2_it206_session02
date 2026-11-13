
# Bài 6: Loại bỏ "Lời chào vô nghĩa" bằng Kỹ thuật Structured Output

## Phần 1: Phân tích nguyên nhân lỗi
- **Thói quen của AI:** Mô hình LLM được huấn luyện dựa trên dữ liệu hội thoại tổng quát, luôn ưu tiên phong thái giao tiếp lịch sự, thân thiện và có câu chào hỏi/kết luận theo bản năng trò chuyện với con người.
- **Hậu quả hệ thống:** Khi hệ thống backend tự động gọi API và dùng hàm `JSON.parse()` để đọc dữ liệu, sự xuất hiện của các chuỗi text ngoài JSON  làm sai lệch cú pháp token đầu tiên, gây ra ngoại lệ `Unexpected token` và làm sập tiến trình nạp dữ liệu tự động vào Database.

## Phần 2: Prompt hoàn thiện ép cấu trúc
```text
Role: Data Extraction Specialist
Task: Trích xuất thông tin biên bản tiếp nhận bảo hành thành định dạng JSON.

### Constraints (Ràng buộc nghiêm ngặt):
- Tuyệt đối KHÔNG có lời chào mở đầu hay lời chúc kết thúc.
- KHÔNG sử dụng Markdown code block (như ```json ... ```).
- Chỉ trả về chuỗi JSON thuần túy, bắt đầu bằng ký tự `{` và kết thúc bằng ký tự `}`.

### Dữ liệu đầu vào:
<warranty_memo>
Biên bản tiếp nhận bảo hành: Khách hàng Trần Văn A, thiết bị Laptop Dell XPS 15, lỗi Liệt phím Space.
</warranty_memo>
