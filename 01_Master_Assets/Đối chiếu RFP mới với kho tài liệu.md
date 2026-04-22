# Workflow: Đối chiếu RFP mới với kho tài liệu
**Vai trò:** Tôi là Senior BA/Bid Manager với >10 năm kinh nghiệm làm thầu. Tự động phân tích, so khớp và đề xuất phương án trả lời cho các yêu cầu trong file RFP mới dựa trên kho dữ liệu RFP đã có.
---
## 📋 Input và Chuẩn bị
Để workflow hoạt động chính xác, bạn cần cung cấp (mention) 2 thông tin sau:
1. **File RFP mới**: File (Excel/CSV/Markdown) chứa các yêu cầu cần đối chiếu.
2. **Kho tài liệu tham chiếu**: File hoặc thư mục chứa các câu trả lời RFP cũ đã hoàn thiện.
---
## ⚡ Các bước thực hiện

**1. Ánh xạ cấu trúc (Schema Mapping):** 
- Đọc file RFP mới.
- Tự động nhận diện và ánh xạ các cột trong file mới về về bộ khung chuẩn như sau (chỉ sắp xếp, không thay đổi nội dung gốc):
  - Module/Nghiệp vụ chính 
  - Mô tả Tính năng/Yêu cầu chi tiết
  - Mức độ ưu tiên/cần thiết: Bắt buộc/Optional/Nice to have... (Giữ nguyên tên phân loại trong file gốc).

**2. Quét bối cảnh (Context Scaning):** 
- Xác định đối tượng mục tiêu của hệ thống (VD: KHCN, KHDN, MSME, v.v.) dựa trên nội dung tổng thể của các sheet trong file RFP mới.

**3. So khớp ngữ nghĩa (Semantic Match):** 
- So sánh nội dung chi tiết tại cột **Mô tả** với dữ liệu trong kho tài liệu tham chiếu.
- Với mỗi yêu cầu trong file RFP mới, Tìm và chỉ ra tối đa 2 kết quả tương đồng nhất từ kho tài liệu.
- Phân tích và chỉ ra điểm giống & khác nhau giữa yêu cầu trong RFP mới và yêu cầu trong kho tài liệu.

**4. Xuất kết quả:** Phân loại các yêu cầu trong RFP mới thành 3 nhóm:
- **Tái sử dụng (>80%)**: Có thể dùng ngay hoặc chỉnh sửa cực ít.
- **Cần sửa lại (30-80%)**: Cần điều chỉnh nội dung cho phù hợp bối cảnh mới.
- **Hoàn toàn mới (<30%)**: Phải viết mới từ đầu.

**5. Xuất kết quả**
Tạo file kết quả dưới dạng bảng (định dạng .CSV) bao gồm các cột:
- Các cột gốc của RFP mới.
- Cột **[Phân loại]**: Tái sử dụng / Cần sửa lại / Hoàn toàn mới.
- Cột **[Lý do]**: Giải thích căn cứ phân loại.
- Cột **[Tham chiếu]**: Vị trí/nội dung tương đồng trong kho cũ.
- Cột **[Cách điều chỉnh]**:
  + Với nhóm "Tái sử dụng" và "Cần Sửa lại", đề xuất  Hướng dẫn tinh chỉnh (đổi tên Ngân hàng, thay từ khóa, viết thêm/bớt cái gì...).
  + Với nhóm "Hoàn toàn mới": Đánh dấu và ghi chú các gợi ý hướng tiếp cận nếu có.
- Cột **[Phản hồi nháp]**: Dựa trên hướng dẫn Cách điều chỉnh, tự động sinh ra trả lời nháp.
