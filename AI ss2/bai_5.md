# Bài 5: Cơ chế In-Context Learning trong Phân loại Review Khách hàng

## Phần 1: Phân tích cơ chế In-Context Learning
- **Bản chất:** In-Context Learning cho phép mô hình ngôn ngữ lớn (LLM) hiểu và thực hiện nhiệm vụ mới ngay trong lúc chạy (inference) thông qua các ví dụ đầu vào mà **không cần cập nhật trọng số (weights)** hay train lại model.
- **Cơ chế hoạt động:** Khi cung cấp các ví dụ mẫu (Few-shot), ngữ cảnh đó tạo ra điểm neo xác suất, kích hoạt các không gian tri thức tiềm ẩn sẵn có để AI nhận diện văn phong phức tạp (như mỉa mai, khen đểu, ẩn ý kỹ thuật) thay vì chỉ dịch nghĩa đen từ ngữ như ở Zero-shot.

## Phần 2: Thiết kế Prompt Few-shot nhận diện đánh giá mỉa mai
```text
Role: Chuyên gia phân tích cảm xúc khách hàng tại TechShop.
Task: Phân loại chính xác cảm xúc của đánh giá sản phẩm thành [TÍCH CỰC] hoặc [TIÊU CỰC], đặc biệt chú ý phát hiện các câu khen đểu, mỉa mai về nhiệt độ, pin và thời gian giao hàng.


