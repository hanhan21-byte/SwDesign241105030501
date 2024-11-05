1.Tiến hành phân tích tất cả các ca sử dụng còn lại trong hệ thống Payroll System
1. Login
-Mô tả ngắn gọn: Ca sử dụng này mô tả cách mà một người dùng đăng nhập vào hệ thống Payroll.
Luồng sự kiện
-Luồng cơ bản:
Người dùng nhập tên và mật khẩu.
Hệ thống xác thực tên và mật khẩu và đăng nhập người dùng vào hệ thống.
Luồng thay thế:
Tên/mật khẩu không hợp lệ: Nếu tên/mật khẩu không hợp lệ, hệ thống hiển thị thông báo lỗi và người dùng có thể quay lại hoặc hủy đăng nhập.
Yêu cầu đặc biệt: Không có.
Điều kiện trước: Hệ thống ở trạng thái đăng nhập và hiển thị màn hình đăng nhập.
Điều kiện sau: Người dùng đã đăng nhập vào hệ thống nếu thành công.

![Diagram](https://www.planttext.com/api/plantuml/png/L8yz2i9044RxFSMmbHQvG0e9_XI2NKumxeuni9cLcLqjn9DPU2IlO682ngzyF7Xyx-UhqeIISXUC2wWAXzYq37S3_Gh8IiBOKGbrafQR2LzwynR5_s60AuRMOwADa2TEBGPTB4jOnnW8sJpCrDYYdeyHnHipvefYzODGWXrndPqZrLCETYRQdKWKg9qGiHtiFN_BCEjQKn7xuTO7003__mC0)
2. Select Payment Method
Mô tả ngắn gọn: Cho phép nhân viên chọn phương thức thanh toán (nhận trực tiếp, gửi qua bưu điện, hoặc chuyển khoản trực tiếp).
Luồng sự kiện
Luồng cơ bản:
Nhân viên chọn phương thức thanh toán.
Hệ thống yêu cầu thông tin bổ sung nếu cần (địa chỉ hoặc thông tin ngân hàng).
Nhân viên cung cấp thông tin.
Hệ thống cập nhật thông tin.
Luồng thay thế:
Nhân viên không tìm thấy: Hệ thống hiển thị thông báo lỗi và kết thúc.
Yêu cầu đặc biệt: Không có.
Điều kiện trước: Nhân viên đã đăng nhập vào hệ thống.
Điều kiện sau: Phương thức thanh toán được cập nhật nếu thành công.

![Diagram](https://www.planttext.com/api/plantuml/png/R90z2i9048NxFSLW5S5S88MaqC924SG3J7O7NR9_x4wK89xCmYDv1ID6CS4ft_juytYFsxrCZ94RQuGqc18iRJ2-9OABWEvoe5vOgG9s7BKxz4R0rfBZDV7H3ps09YXasluIcQFpa9qMSF9QYQleVm_ulW10qBBUX-n3lqMBscIeLAIKndblGkb8aXSKVDASLUZg3Lhwi3D0ANtZUDFOYkAVIjyXydm-QbR0997fqjD4bEJKQxqd0000__y30000)
3. Maintain Employee Information
Mô tả ngắn gọn: Cho phép Quản trị viên Payroll duy trì thông tin nhân viên (thêm, sửa, xóa).
Luồng sự kiện
Luồng cơ bản:
Quản trị viên chọn chức năng (Thêm, Cập nhật, Xóa nhân viên).
Thực hiện theo các luồng con tương ứng.
Luồng thay thế:
Nhân viên không tìm thấy: Hệ thống hiển thị thông báo lỗi.
Xóa bị hủy: Hủy bỏ thao tác xóa và quay lại luồng chính.
Yêu cầu đặc biệt: Không có.
Điều kiện trước: Quản trị viên đã đăng nhập vào hệ thống.
Điều kiện sau: Thông tin nhân viên được cập nhật nếu thành công.

![Diagram](https://www.planttext.com/api/plantuml/png/T951IWH134NtVOemArtq1NeX8wWm6n6S2yH9d2ceIZL9MgOHJ-R28ta5kw5Qcs8igCr_lvBwoVVdrzOSrOSKcqD4CxXFVSmZCxmtC9qMk0Wxwk3PDSYn0C74bRHuzsDV8oHIDgjKCwaKn_CTqt3ma6LoFyICNb3s4-j_i3zbuSSXlR3MFJ2YZcitpBzPWbvTTx-X2nrwGkUruIq7Af0uyWNuqPG1Fk6eESPRIa62kQ9dBSC4I1Z4fxiytybhreHpddMbYpNQzkPlEnri4WeUsJRDbeNc1Vu0003__mC0)
4. Maintain Purchase Order
Mô tả ngắn gọn: Cho phép nhân viên hoa hồng ghi lại và duy trì đơn đặt hàng.
Luồng sự kiện
Luồng cơ bản:
Nhân viên chọn chức năng (Tạo, Cập nhật, Xóa đơn đặt hàng).
Hệ thống yêu cầu thông tin cần thiết.
Cung cấp thông tin và cập nhật hệ thống.
Luồng thay thế:
Đơn đặt hàng không tìm thấy: Hiển thị thông báo lỗi.
Truy cập không hợp lệ: Hiển thị thông báo lỗi nếu nhân viên cố gắng truy cập đơn hàng không phải của mình.
Đơn đặt hàng đã đóng: Hiển thị thông báo lỗi.
Yêu cầu đặc biệt: Không có.
Điều kiện trước: Nhân viên đã đăng nhập vào hệ thống.
Điều kiện sau: Thông tin đơn đặt hàng được cập nhật nếu thành công.
![Diagram](https://www.planttext.com/api/plantuml/png/R55B2W8n3DtFAO8hNSm5PY4ZwiALWYUeJT12FqFI2YAUp8L7yWgEOn6jTb5uxwN9U-dzUcibAex9sKfR9GARnFgWXDQCn72ke3yrX2TQOGFRoCRlCwkJnE28vy57fMEXxeorFPeXCeaKOiS1qyyJL94QMFJtG01efXuCNiQJvjjSBaaTVfOSWy6i85agbKkLSyw3SqR414-uT9qD9w9tNCf4aHZ0AQ_sz6LZNEpcOzBV6NKzBPRSmEZLLqPLInwVd_40003__mC0)

5. Run Payroll
Mô tả ngắn gọn: Mô tả cách thức chạy payroll vào thứ Sáu hàng tuần và ngày làm việc cuối cùng của tháng.
Luồng sự kiện
Luồng cơ bản:
Hệ thống tự động chạy payroll vào thời điểm định sẵn.
Lấy thông tin nhân viên đủ điều kiện.
Tính toán lương và khấu trừ.
In phiếu lương hoặc xử lý giao dịch ngân hàng.
Luồng thay thế:
Hệ thống ngân hàng không khả dụng: Hệ thống sẽ cố gắng gửi lại giao dịch sau một khoảng thời gian.
Yêu cầu đặc biệt: Không có.
Điều kiện trước: Không có.
Điều kiện sau: Thanh toán cho từng nhân viên đã được xử lý nếu thành công.
![Diagram](https://www.planttext.com/api/plantuml/png/R911IWH134NtTOhGgt7H5-Y538A22q4OBn2gCjgOgZILr40nU38N7iahs3rJEDDYbZ__9o_v_lpQgc6s4jbvHbLunfg5ULVLACBHmQboIQsnkHdW86Dm7wubxkF4KecQkGTgmcCOO6TvJA-jeSYOwm0FB6XD2nIAjr6IhlK9QwHaJsHlifu3u95zOJIQcHQUS-uNw0xJ-n_-AOidrPUCIV6qReDHIh8MlZfg_O2-lxqSE43N1f4kW8iFzfAxVq9N47DCAGK5kwm7ayvjPtNv_0y0003__mC0)


2.Mô phỏng ca sử dụng Maintain Timecard bằng Java
// Lớp đại diện cho thông tin nhân viên
class Employee {
    private int employeeId;
    private String name;
    private Timecard currentTimecard;

    public Employee(int id, String name) {
        this.employeeId = id;
        this.name = name;
    }

    public Timecard getCurrentTimecard() {
        return currentTimecard;
    }

    public void createNewTimecard() {
        this.currentTimecard = new Timecard();
    }

    public void submitTimecard() {
        if (currentTimecard != null) {
            currentTimecard.submit();
        }
    }
}

// Lớp đại diện cho bảng thời gian làm việc
class Timecard {
    private boolean isSubmitted = false;
    private Map<String, Integer> hoursWorked; // Ngày làm việc và giờ làm

    public Timecard() {
        hoursWorked = new HashMap<>();
    }

    public void addHours(String date, int hours) {
        if (!isSubmitted && hours <= 24) {
            hoursWorked.put(date, hours);
        } else {
            System.out.println("Error: Cannot add hours, timecard is submitted or hours exceed limit.");
        }
    }

    public void submit() {
        if (!isSubmitted) {
            isSubmitted = true;
            System.out.println("Timecard submitted successfully.");
        }
    }

    public boolean isSubmitted() {
        return isSubmitted;
    }
}

// Lớp mô phỏng việc chạy chương trình chính
public class PayrollSystem {
    public static void main(String[] args) {
        Employee employee = new Employee(1, "John Doe");

        // Tạo một timecard mới
        employee.createNewTimecard();

        // Thêm giờ làm việc vào bảng
        employee.getCurrentTimecard().addHours("2024-11-04", 8);
        employee.getCurrentTimecard().addHours("2024-11-05", 7);

        // Gửi timecard
        employee.submitTimecard();
    }
}
