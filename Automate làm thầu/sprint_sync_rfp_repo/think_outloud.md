# Think Outloud

- Yêu cầu của người dùng là "Đồng bộ repo này: https://github.com/chanhnequyzi/RFP.git".
- Workspace hiện tại là `c:\Users\linhn\Khoa_Hoc_Antigravity\Automate làm thầu`. Tuy nhiên đây là một thư mục con trong repo git lớn `Khoa_Hoc_Antigravity`.
- Đã thêm remote `rfp` cho Git repo chung của toàn workspace và fetch nhánh `main`. Repo `RFP.git` có các file như `01_Master_Assets/Style_Guide.md`, `Bidding Playbook.docx`, v.v.
- Để đồng bộ, một cách hợp lý là pull mã nguồn từ `rfp/main` và trộn (merge) vào git repo hiện tại. Các lịch sử git của repo local và RFP repo là độc lập (unrelated histories) nên cần cờ `--allow-unrelated-histories`. Hoặc phương án khác là git đẩy mã nguồn hiện tại lên repo mới. Thường đồng bộ có nghĩa là kéo về.
- Sẽ thực hiện lệnh pull từ repo RFP về local để đồng bộ file mới xuống.
- User hỏi cách đẩy file (push) lên GitHub. Tôi sẽ hướng dẫn các bước git add, git commit, git push và đưa ra lựa chọn thực hiện dùm user. Chú ý hướng dẫn họ đẩy lên nhánh `main` của repo `rfp` (`git push rfp master:main`).
- Khách hàng lại hỏi: "Làm thế nào để tôi thêm file trực tiếp lên repo này?". Có khả năng khách hàng muốn hỏi cách thao tác trực tiếp trên giao diện web của Github, hoặc cách để code trên máy tính tự động nhảy vào đúng kho đó mà không cần dùng lệnh lằng nhằng. Tôi sẽ hướng dẫn cả 2 cách trực quan: Thao tác trên Web (kéo thả) và Thao tác trên VS Code (dùng giao diện Source Control hoặc tạo file để tôi tự chạy lệnh cho họ).
- Khách hàng yêu cầu: "Tạo một folder ghi là INPUT". Tôi đã tạo folder `INPUT` trong thư mục `Automate làm thầu`. 
- Cần lưu ý là Git không tự động theo dõi các thư mục rỗng. Vì vậy, tôi đã tạo thêm một file nháp có tên `.gitkeep` (`INPUT/.gitkeep`) để Github có thể nhận diện và cập nhật thư mục này sau khi push. Đã ghi lại hoạt động vào nhật ký.
- Khách hàng yêu cầu đẩy file `skill_prompt_rule.md` nằm trong `INPUT` lên repo RFP. Tôi sẽ thực hiện `git add` trỏ đích danh tới file này (và sẵn tiện add luôn `.gitkeep`), sau đó `git commit` và `git push rfp master:main`. Việc này hoàn thành chu trình đồng bộ đầy đủ lên Repo Github.
- [SỰ CỐ PUSH THẤT BẠI] Quá trình Push lên Github trả về lỗi `403 Permission denied`. Lỗi này là do cấu hình tài khoản sinh viên/cá nhân hiện tại (`linhnmk58fyu-crypto`) chưa được cấp quyền (collaborator) để đẩy mã nguồn lên repo `chanhnequyzi/RFP.git`. Sẽ thông báo cho khách hàng cách khắc phục.
- Khách hàng đã cấp quyền và yêu cầu thử lại. Tôi đã chạy lại lệnh `git push rfp master:main` và thành công. Mã nguồn đã được đồng bộ lên repo RFP trên tài khoản của khách. Hoàn thành task.
