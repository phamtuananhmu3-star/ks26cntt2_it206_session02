# Báo cáo Prompting: Tự động hóa xử lý dữ liệu đơn hàng

## 1. Thiết kế giải pháp (Prompt Chaining)
- **Bước 1:** Trích xuất thông tin thô từ email khách hàng thành JSON.
- **Bước 2:** Kiểm tra và làm sạch dữ liệu dị biệt (thiếu trường, sai định dạng).
- **Bước 3:** Xuất báo cáo dạng bảng Markdown chuẩn hóa.

## 2. Hệ thống Prompt thực thi
```
### Role: Data Processing Assistant
### Context: Chuẩn hóa dữ liệu đơn hàng e-commerce.
### Request: Đọc đoạn văn bản sau, trích xuất thông tin và trả về định dạng bảng Markdown.
### Constraints: 
- Chỉ lấy thông tin có trong văn bản, nếu thiếu ghi "N/A".
- Không thêm lời dẫn hoặc giải thích ngoài bảng.
### Input Data:
<customer_order>
Khách mua 2 áo thun đen size L, giao đến 12 Chùa Bộc, sđt 0901234567.
</customer_order>
```
### Output Format:
| Sản Phẩm | Số Lượng | Địa Chỉ | SĐT |
|---|---|---|---|
| Áo thun đen (Size L) | 2 | 12 Chùa Bộc | 0901234567 |
