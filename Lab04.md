# Các Ca Sử Dụng trong Hệ Thống Quản Lý Tiền Lương

## 1. Ca Sử Dụng cho Nhân Viên

### 1.1 Xem Thông Tin Cá Nhân
- **Diễn viên**: Nhân viên  
- **Tiền điều kiện**: Nhân viên đã đăng nhập vào hệ thống.  
- **Các bước**:  
  1. Nhân viên chọn mục "Thông tin cá nhân" trên menu chính.  
  2. Hệ thống hiển thị đầy đủ thông tin cá nhân của nhân viên (họ tên, ngày sinh, địa chỉ, số điện thoại, email, phòng ban, chức vụ, ...).  
- **Hậu điều kiện**: Nhân viên đã xem được thông tin cá nhân của mình.  

### 1.2 Cập Nhật Thông Tin Cá Nhân
- **Diễn viên**: Nhân viên  
- **Tiền điều kiện**: Nhân viên đã đăng nhập vào hệ thống.  
- **Các bước**:  
  1. Nhân viên chọn mục "Cập nhật thông tin cá nhân".  
  2. Hệ thống hiển thị form để nhân viên nhập thông tin cần cập nhật.  
  3. Nhân viên nhập thông tin mới và nhấn "Lưu".  
  4. Hệ thống cập nhật thông tin và hiển thị thông báo xác nhận.  
- **Hậu điều kiện**: Thông tin cá nhân của nhân viên đã được cập nhật.  

### 1.3 Xem Lịch Sử Bảng Lương
- **Diễn viên**: Nhân viên  
- **Tiền điều kiện**: Nhân viên đã đăng nhập vào hệ thống và hệ thống đã tính toán lương cho các kỳ trước.  
- **Các bước**:  
  1. Nhân viên chọn mục "Lịch sử bảng lương".  
  2. Hệ thống hiển thị danh sách các bảng lương đã được tính toán cho nhân viên.  
  3. Nhân viên chọn một bảng lương cụ thể để xem chi tiết.  
- **Hậu điều kiện**: Nhân viên đã xem được chi tiết bảng lương của kỳ đã chọn.  

---

## 2. Ca Sử Dụng cho Quản Lý

### 2.1 Thêm Mới Nhân Viên
- **Diễn viên**: Quản lý  
- **Tiền điều kiện**: Quản lý đã đăng nhập vào hệ thống.  
- **Các bước**:  
  1. Quản lý chọn mục "Quản lý nhân viên" và chọn "Thêm mới".  
  2. Hệ thống hiển thị form để nhập thông tin nhân viên mới.  
  3. Quản lý nhập đầy đủ thông tin và nhấn "Lưu".  
- **Hậu điều kiện**: Nhân viên mới đã được thêm vào hệ thống.  

### 2.2 Sửa Thông Tin Nhân Viên
- **Diễn viên**: Quản lý  
- **Tiền điều kiện**: Quản lý đã đăng nhập vào hệ thống.  
- **Các bước**:  
  1. Quản lý chọn mục "Quản lý nhân viên" và chọn nhân viên cần sửa.  
  2. Hệ thống hiển thị thông tin hiện tại của nhân viên.  
  3. Quản lý sửa các thông tin cần thiết và nhấn "Lưu".  
- **Hậu điều kiện**: Thông tin nhân viên đã được cập nhật.  

### 2.3 Phê Duyệt Bảng Lương
- **Diễn viên**: Quản lý  
- **Tiền điều kiện**: Bảng lương đã được tính toán và chờ phê duyệt.  
- **Các bước**:  
  1. Quản lý chọn mục "Phê duyệt bảng lương".  
  2. Hệ thống hiển thị danh sách các bảng lương chờ phê duyệt.  
  3. Quản lý xem chi tiết từng bảng lương và chọn "Phê duyệt" hoặc "Từ chối".  
- **Hậu điều kiện**: Bảng lương đã được phê duyệt hoặc từ chối.  

### 2.4 Xem Báo Cáo Tổng Hợp
- **Diễn viên**: Quản lý  
- **Tiền điều kiện**: Quản lý đã đăng nhập vào hệ thống.  
- **Các bước**:  
  1. Quản lý chọn mục "Báo cáo".  
  2. Hệ thống hiển thị danh sách các loại báo cáo (ví dụ: báo cáo lương theo phòng ban, báo cáo thuế TNCN).  
  3. Quản lý chọn loại báo cáo cần xem và chọn khoảng thời gian.  
  4. Hệ thống hiển thị báo cáo theo yêu cầu.  
- **Hậu điều kiện**: Quản lý đã xem được báo cáo.  

---

## 3. Ca Sử Dụng cho Kế Toán

### 3.1 Xuất Hóa Đơn Lương
- **Diễn viên**: Kế toán  
- **Tiền điều kiện**: Bảng lương đã được phê duyệt.  
- **Các bước**:  
  1. Kế toán chọn mục "Xuất hóa đơn lương".  
  2. Hệ thống hiển thị danh sách các bảng lương đã được phê duyệt.  
  3. Kế toán chọn bảng lương cần xuất hóa đơn và nhấn "Xuất".  
  4. Hệ thống tạo và xuất file hóa đơn lương.  
- **Hậu điều kiện**: Hóa đơn lương đã được xuất thành công.  

### 3.2 Nộp Thuế
- **Diễn viên**: Kế toán  
- **Tiền điều kiện**: Bảng lương đã được phê duyệt và đã xuất hóa đơn.  
- **Các bước**:  
  1. Kế toán chọn mục "Nộp thuế".  
  2. Hệ thống tính toán số thuế phải nộp và tạo file khai thuế.  
  3. Kế toán kiểm tra và nộp file khai thuế.  
- **Hậu điều kiện**: Thuế đã được nộp.  

### 3.3 Đối Chiếu Số Liệu với Ngân Hàng
- **Diễn viên**: Kế toán  
- **Tiền điều kiện**: Bảng lương đã được thanh toán.  
- **Các bước**:  
  1. Kế toán chọn mục "Đối chiếu số liệu".  
  2. Hệ thống so sánh số liệu thanh toán trên hệ thống với số liệu từ ngân hàng.  
  3. Kế toán kiểm tra và đối chiếu các khoản chênh lệch.  
- **Hậu điều kiện**: Số liệu đã được đối chiếu.  

---

## 4. Ca Sử Dụng cho Hệ Thống

### 4.1 Tự Động Tính Lương Hàng Tháng
- **Diễn viên**: Hệ thống  
- **Tiền điều kiện**: Đến ngày cuối tháng hoặc ngày được cấu hình.  
- **Các bước**:  
  1. Hệ thống tự động thu thập dữ liệu chấm công, thông tin nhân viên.  
  2. Hệ thống tính toán lương theo công thức đã được cài đặt.  
  3. Hệ thống tạo bảng lương và gửi thông báo cho quản lý để phê duyệt.  
- **Hậu điều kiện**: Bảng lương đã được tính toán và sẵn sàng để phê duyệt.  

### 4.2 Gửi Email Thông Báo Bảng Lương
- **Diễn viên**: Hệ thống  
- **Tiền điều kiện**: Bảng lương đã được phê duyệt.  
- **Các bước**:  
  1. Hệ thống gửi email thông báo đến từng nhân viên về bảng lương của họ.  
- **Hậu điều kiện**: Nhân viên đã nhận được email thông báo.  

### 4.3 Lưu Trữ Lịch Sử Bảng Lương
- **Diễn viên**: Hệ thống  
- **Tiền điều kiện**: Bảng lương đã được tính toán và lưu trữ.  
- **Các bước**:  
  1. Hệ thống lưu trữ bảng lương vào cơ sở dữ liệu.  
- **Hậu điều kiện**: Bảng lương đã được lưu trữ để tra cứu sau này.  
