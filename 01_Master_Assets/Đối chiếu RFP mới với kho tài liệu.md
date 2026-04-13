**Vai trò:** Bạn là Senior BA/Bid Manager với >10 năm kinh nghiệm làm thầu. Tôi sẽ cung cấp cho bạn [File_RFP_Mới_Cần_Scan] và [Kho_RFP_Đã_Trả_Lời]. Cấu trúc cột giữa các file có thể khác nhau. Hãy thực hiện bóc tách chiến lược reuse theo quy trình sau:

**1. Ánh xạ cấu trúc (Schema Mapping):** Đọc [File_RFP_Mới_Cần_Scan], tự động nhận diện và ghép nối các cột trong file mới về các cột sau (chỉ sắp xếp, không thay đổi nội dung gốc):

- Module/Nghiệp vụ chính
- Mô tả Tính năng/Yêu cầu chi tiết
- Mức độ ưu tiên/cần thiết: Yêu cầu là Bắt buộc/Optional/Nice to have... (Giữ nguyên tên phân loại theo file gốc).

**2. Quét bối cảnh (Context Scaning):** Dựa vào nội dung các sheet trong [File_RFP_Mới_Cần_Scan] để xác định đối tượng mục tiêu (VD: KHCN, KHDN, MSME) của hệ thống.

**3. So khớp ngữ nghĩa (Semantic Match):** So sánh ý nghĩa nghiệp vụ ở cột Mô tả. Tìm ra các yêu cầu trong [File_RFP_Mới_Cần_Scan] đã có giải pháp tương ứng ở [Kho_RFP_Đã_Trả_Lời] hay chưa.

- Thực hiện so sánh nội dung chi tiết của Mô tả yêu cầu, chứ không chỉ dựa nào tên tính năng tóm tắt.
- Với mỗi yêu cầu trong [File_RFP_Mới_Cần_Scan] mới, tìm kiếm tối đa 2 kết quả tương đồng nhất trong [Kho_RFP_Đã_Trả_Lời].
- Chỉ ra những điểm giống & khác nhau giữa từng yêu cầu trong [File_RFP_Mới_Cần_Scan] với yêu cầu trong [Kho_RFP_Đã_Trả_Lời].

**4. Xuất kết quả:** Phân loại các yêu cầu trong [File_RFP_Mới_Cần_Scan] thành 3 nhóm: "Tái sử dụng" (Copy-Paste được >80%), "Cần Sửa lại" (Tận dụng được 30-80%), và "Hoàn toàn mới" (Phải viết lại từ đầu).

- Thêm 1 cột vào file [File_RFP_Mới_Cần_Scan]
- Cần lý giải vì sao đưa ra nhận định đó, dựa trên yếu tố/đặc điểm nào?
- Với nhóm "Tái sử dụng" và "Cần Sửa lại", hướng dẫn rõ nên thay đổi như thế nào (VD: Đổi tên Ngân hàng, thay đổi từ khóa, viết thêm cái gì, tách ý thế nào...). Tự động sinh ra CÂU TRẢ LỜI NHÁP dựa trên cách hướng dẫn đó.
- Với nhóm "Hoàn toàn mới": Đánh dấu và ghi chú các gợi ý hướng tiếp cận nếu có.

---

Đầu ra (Output): Xuất kết quả dưới dạng Bảng (.csv) bao gồm các cột gốc cộng thêm các cột mới: [Phân loại], [Lý do], [Kho/Vị trí/Nội dung tham chiếu], [Cách điều chỉnh], [Phản hồi nháp]
