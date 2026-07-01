# 📚 Hệ thống Quản lý Thư Viện

Ứng dụng CLI (C++17) tối ưu hóa quy trình mượn/trả sách, quản lý độc giả và xử lý hàng đợi thư viện bằng các cấu trúc dữ liệu kinh điển.

**🚀 Cài đặt & Chạy:** `g++ -std=c++17 src/main.cpp src/functions.cpp -o app && ./app` *(Windows: đổi `./app` thành `app.exe`)*

---

### 🛠 Cấu trúc dữ liệu & Chức năng cốt lõi

* **BST ($O(\log n)$):** Quản lý kho sách. Hỗ trợ Thêm, Xóa, Sửa và Tìm kiếm (theo mã/tên) tốc độ cao.
* **Queue (FIFO):** Xử lý hàng đợi. Tự động đưa độc giả vào danh sách chờ khi sách hết và lập tức cấp phát sách khi có người trả.
* **Stack (LIFO):** Lưu lịch sử thao tác mượn/trả, hỗ trợ tính năng **Hoàn tác (Undo)** trạng thái tức thì.
* **Linked List:** Quản lý danh sách độc giả linh hoạt, cấp phát bộ nhớ động không gây lãng phí.
* **Tính năng phụ:** Thống kê sách hot/độc giả tích cực; Lưu & khôi phục dữ liệu từ file `.txt`.

---

### 🧪 5 Kịch bản kiểm thử (Test Cases)

1.  **Thêm & Tìm kiếm:** Nhập 3 sách mới $\rightarrow$ Tìm mã "B002" $\rightarrow$ Hiển thị chính xác thông tin.
2.  **Mượn sách (Kho > 0):** Độc giả mượn $\rightarrow$ Số lượng giảm 1, thao tác được ghi vào Stack.
3.  **Vào hàng đợi (Kho = 0):** Độc giả mượn sách đã hết $\rightarrow$ Tự động đẩy vào Queue của sách đó.
4.  **Trả & Cấp phát:** Khách trả sách $\rightarrow$ Hệ thống tự động pop người đầu Queue ra và cho mượn tiếp.
5.  **Hoàn tác (Undo):** Chọn Undo $\rightarrow$ Hủy thao tác mượn/trả cuối cùng, khôi phục nguyên vẹn trạng thái.

---

### 📂 Cấu trúc File (`src/`)

* `main.cpp` : Menu UI Console và điều khiển luồng chương trình.
* `structures.h` : Khai báo các struct (Book, Reader) và nguyên mẫu hàm.
* `functions.cpp`: Cài đặt chi tiết logic giải thuật của hệ thống.
