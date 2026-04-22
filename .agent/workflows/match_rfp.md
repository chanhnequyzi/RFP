# Workflow: Đối chiếu RFP mới với kho tài liệu

Tự động phân tích, so khớp và đề xuất phương án trả lời cho các yêu cầu trong file RFP mới dựa trên kho dữ liệu RFP đã có.

## 📋 Input và Chuẩn bị
Để workflow hoạt động chính xác, bạn cần cung cấp (mention) 2 thông tin sau:
1. **File RFP mới**: File (Excel/CSV/Markdown) chứa các yêu cầu cần đối chiếu.
2. **Kho tài liệu tham chiếu**: File hoặc thư mục chứa các câu trả lời RFP cũ đã hoàn thiện.

---

## ⚡ Các bước thực hiện

### 1. Ánh xạ cấu trúc (Schema Mapping)
- Đọc file RFP mới.
- Tự động nhận diện và ánh xạ các cột về bộ khung chuẩn:
    - `Module/Nghiệp vụ chính`
    - `Mô tả Tính năng/Yêu cầu chi tiết`
    - `Mức độ ưu tiên` (Bắt buộc/Optional/...)

### 2. Quét bối cảnh (Context Scanning)
- Xác định đối tượng mục tiêu của hệ thống (VD: KHCN, KHDN, MSME, v.v.) dựa trên nội dung tổng thể của các sheet.

### 3. So khớp ngữ nghĩa (Semantic Match)
- So sánh nội dung chi tiết tại cột **Mô tả** với dữ liệu trong kho tài liệu tham chiếu.
- Tìm tối đa 2 kết quả tương đồng nhất cho mỗi yêu cầu.
- Phân tích điểm giống và khác nhau về mặt nghiệp vụ.

### 4. Phân loại và Đề xuất
Phân loại yêu cầu thành 3 nhóm:
- **Tái sử dụng (>80%)**: Có thể dùng ngay hoặc chỉnh sửa cực ít.
- **Cần sửa lại (30-80%)**: Cần điều chỉnh nội dung cho phù hợp bối cảnh mới.
- **Hoàn toàn mới (<30%)**: Phải viết mới từ đầu.

### 5. Xuất kết quả
Tạo file kết quả tại thư mục `Output/` dưới dạng bảng (CSV hoặc Markdown) bao gồm:
- Các cột gốc của RFP mới.
- Cột **[Phân loại]**: Tái sử dụng / Cần sửa lại / Hoàn toàn mới.
- Cột **[Lý do]**: Giải thích căn cứ phân loại.
- Cột **[Tham chiếu]**: Vị trí/nội dung tương đồng trong kho cũ.
- Cột **[Cách điều chỉnh]**: Hướng dẫn tinh chỉnh (đổi tên NH, thay từ khóa...).
- Cột **[Phản hồi nháp]**: Nội dung câu trả lời dự kiến.

---

## 🚀 Prompt mẫu để chạy Workflow

Sử dụng lệnh sau để bắt đầu:

> **/match_rfp** đối chiếu file @[Tên_File_RFP_Mới] với kho dữ liệu tại @[Thư_Mục_Hoặc_File_Kho_Cũ]

*Ví dụ:*
> **/match_rfp** @[Input/RFP_Vietbank_2026.xlsx] @[Online_Workspace/01_Master_Assets/Kho_RFP_Mau.csv]
