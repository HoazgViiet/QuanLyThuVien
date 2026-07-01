# 📚 Hệ thống Quản lý Thư Viện

Đây là ứng dụng dòng lệnh (CLI) bằng C++ hỗ trợ thư viện quản lý kho sách, thông tin độc giả và toàn bộ quy trình mượn/trả sách một cách tối ưu.

---

## 🛠 Cấu trúc dữ liệu sử dụng

| Cấu trúc | Vai trò | Lý do áp dụng |
| :--- | :--- | :--- |
| **BST (Cây nhị phân tìm kiếm)** | Quản lý kho sách | Tìm kiếm, thêm, xóa theo mã sách đạt hiệu suất cao với độ phức tạp $O(\log n)$. |
| **Queue (Hàng đợi)** | Danh sách chờ mượn sách | Đảm bảo tính công bằng theo nguyên tắc "Vào trước - Ra trước" (FIFO) khi sách hết. |
| **Stack (Ngăn xếp)** | Lịch sử thao tác mượn/trả | Hỗ trợ tính năng Hoàn tác (Undo) nhanh chóng theo nguyên tắc "Vào sau - Ra trước" (LIFO). |
| **Linked List (Danh sách liên kết)** | Quản lý danh sách độc giả | Cấp phát bộ nhớ động linh hoạt, thêm/xóa nhanh chóng mà không cần dịch chuyển dữ liệu. |

---

## 🚀 Hướng dẫn cài đặt và chạy

Mở Terminal/Command Prompt tại thư mục gốc của dự án và chạy lệnh biên dịch sau:

```bash
g++ -std=c++17 src/main.cpp src/functions.cpp -o app && ./app
Lưu ý: Nếu bạn chạy trên hệ điều hành Windows, hãy đổi ./app ở cuối câu lệnh thành app.exe.⭐ Chức năng chínhThêm, xóa, sửa thông tin sách.Tìm kiếm sách theo mã hoặc tên.Mượn sách (Tự động chuyển vào Queue chờ nếu sách đang được mượn hết).Trả sách (Cập nhật trạng thái và tự động thông báo/cấp sách cho người chờ tiếp theo).Xem lịch sử mượn/trả và Undo thao tác cuối cùng.Thống kê sách được mượn nhiều nhất và độc giả tích cực nhất.Lưu và đọc dữ liệu từ file .txt.🧪 Kịch bản kiểm thử (Test Cases)Kịch bảnThao tác thực hiệnKết quả mong đợi1. Thêm & Tìm kiếmThêm 3 cuốn sách vào hệ thống, tìm cuốn có mã "B002".Hệ thống hiển thị đúng và đầy đủ thông tin sách "B002".2. Mượn sáchĐộc giả mượn sách khi số lượng tồn kho > 0.Số lượng sách giảm 1 và ghi nhận vào lịch sử Stack.3. Hàng đợi (Queue)Độc giả mượn sách khi số lượng tồn kho = 0.Độc giả được tự động đưa vào danh sách chờ của cuốn sách đó.4. Trả sách tự độngĐộc giả trả sách đang có người xếp hàng chờ.Hệ thống lấy người đầu tiên trong Queue ra và cấp sách cho người đó.5. Hoàn tác (Undo)Thực hiện mượn sách, sau đó chọn chức năng Undo.Trạng thái sách và lịch sử quay trở lại chính xác như trước khi mượn.📂 Cấu trúc thư mục gốcPlaintextsrc/
|-- main.cpp       # Menu giao diện console và điều khiển luồng chương trình
|-- structures.h   # Khai báo các struct (Book, Reader) và nguyên mẫu hàm
|-- functions.cpp  # Cài đặt chi tiết logic của các cấu trúc dữ liệu và chức năng
