1.Tiến hành phân tích tất cả các ca sử dụng còn lại trong hệ thống Payroll System
1. Login
Mô tả ngắn gọn: Ca sử dụng này mô tả cách mà một người dùng đăng nhập vào hệ thống Payroll.
Luồng sự kiện
Luồng cơ bản:
Người dùng nhập tên và mật khẩu.
Hệ thống xác thực tên và mật khẩu và đăng nhập người dùng vào hệ thống.
Luồng thay thế:
Tên/mật khẩu không hợp lệ: Nếu tên/mật khẩu không hợp lệ, hệ thống hiển thị thông báo lỗi và người dùng có thể quay lại hoặc hủy đăng nhập.
Yêu cầu đặc biệt: Không có.
Điều kiện trước: Hệ thống ở trạng thái đăng nhập và hiển thị màn hình đăng nhập.
Điều kiện sau: Người dùng đã đăng nhập vào hệ thống nếu thành công.
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
