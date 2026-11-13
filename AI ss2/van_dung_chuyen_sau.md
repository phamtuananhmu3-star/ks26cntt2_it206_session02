 # Bước 1: Thiết kế giải pháp (I/O)
**Input (Đầu vào)**: Dữ liệu thô từ phiếu bảo hành hoặc tin nhắn phản hồi của khách hàng 
**Output (Đầu ra)**: Định dạng bảng Markdown chuẩn hóa gồm 3 cột: Mã Khách Hàng, Sản Phẩm, Trạng Thái Xử Lý.
## Bước 2: Viết Prompt chuẩn 
Tải mã xuống
Sao chép mã
### Role: Bạn là trợ lý AI tự động hóa dữ liệu cho cửa hàng.
### Context: Cần chuẩn hóa dữ liệu bảo hành từ tin nhắn lộn xộn của khách hàng thành bảng báo cáo.
### Request: Trích xuất thông tin từ đoạn văn bản bên dưới thành bảng Markdown.
### Constraints:
- Nếu dữ liệu bị trống, điền "Chưa rõ".
- Tuyệt đối không tự bịa thêm thông tin ngoài văn bản.
### Input Data:
<customer_feedback>
Khách hàng Nguyễn Văn A gửi bảo hành máy tính Dell Inspiron, tình trạng lỗi bàn phím.
</customer_feedback>
### Output Format:
| Mã Khách Hàng | Sản Phẩm | Trạng Thái Xử Lý |
|---|---|---|
| KH_01 | Dell Inspiron | Chờ tiếp nhận |
