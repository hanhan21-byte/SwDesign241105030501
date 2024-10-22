1. Phân tích kiến trúc
Kiến trúc đề xuất
Dựa trên yêu cầu của hệ thống "Payroll System", kiến trúc đề xuất cho bài toán sẽ theo mô hình Layered Architecture (kiến trúc phân tầng) với các thành phần chính sau:
-User Interface Layer (Giao diện người dùng): Cho phép người dùng tương tác với hệ thống qua giao diện Windows-based. Người dùng nhập thông tin thời gian làm việc, lựa chọn phương thức thanh toán, xem báo cáo.
-Application Layer (Tầng nghiệp vụ): Chịu trách nhiệm xử lý logic nghiệp vụ như tính toán lương, kiểm tra dữ liệu nhập vào, xử lý overtime và hoa hồng.
-Data Access Layer (Tầng truy cập dữ liệu): Thực hiện các truy vấn tới cơ sở dữ liệu, bao gồm cả Payroll Database và Project Management Database. Đảm bảo thông tin từ DB2 được lấy chính xác nhưng không bị thay đổi.
-Database Layer (Cơ sở dữ liệu): Lưu trữ thông tin về nhân viên, bảng thời gian (timecards), thông tin về dự án và bảng lương (payroll).
 ![Diagram](https://www.planttext.com/api/plantuml/png/R55RJiCm4FptALO-G0_01sgg8bG990Jq0DlDqfhw4QqtGX7YP7nm9Aw0qwObKUi_pundPyU_tp_ph2ZQ1czCthi8aZ8RTUePdh2Jv3syT5avG2MqSygahR0n3T8UjmnsdLbW5PNb3OajO8RMmQU1SiXZpd0N6fywvlLg10xcLHrSBCJNo77HPXUvQ1xIrj71SNE2nhwlBZ2Xr8yOopkPcWUEUacSebmopzmaqNkEBAX99e6MgBZ1V5ok7YvNLrmkhkIRW4EqAIRflVHw33MmPNwfSJQx_T_z1koXPoI53wSxQyvKhpi7AxgAg8Txo1epvrZtF_m7003__mC0)

2. Cơ chế phân tích
Danh sách cơ chế cần giải quyết
Dựa vào yêu cầu bài toán, các cơ chế chính mà hệ thống cần giải quyết bao gồm:
-Cơ chế quản lý bảng thời gian (Timecard Management): Nhập và ghi lại thời gian làm việc của nhân viên, bao gồm cơ chế tự động ghi nhận overtime.
-Cơ chế tính toán lương (Payroll Calculation): Tự động tính toán lương dựa trên giờ làm việc, overtime, và hoa hồng.
-Cơ chế xử lý phương thức thanh toán (Payment Method Processing): Cho phép nhân viên chọn phương thức thanh toán và nhập thông tin tài khoản ngân hàng nếu chọn phương thức chuyển khoản.
-Cơ chế truy vấn từ cơ sở dữ liệu dự án (Project Management DB Access): Tích hợp và truy xuất dữ liệu từ DB2 mà không làm thay đổi nội dung.
-Cơ chế báo cáo (Reporting Mechanism): Tạo báo cáo về số giờ làm việc, lương nhận được, và các thông tin khác cho từng nhân viên.
-Cơ chế bảo mật (Security Mechanism): Bảo mật thông tin nhân viên và giới hạn quyền truy cập chỉ cho phép nhân viên chỉnh sửa thông tin của chính họ.
-Cơ chế tự động chạy trả lương (Payroll Scheduling): Tự động chạy trả lương vào thứ Sáu hàng tuần và ngày cuối tháng.
3. Phân tích ca sử dụng: Select Payment
Lớp phân tích
Dựa trên ca sử dụng Select Payment, các lớp phân tích chính bao gồm:
-Employee: Đại diện cho nhân viên chọn phương thức thanh toán.
-PaymentMethod: Lớp này lưu trữ thông tin về phương thức thanh toán mà nhân viên chọn.
-PaymentProcessor: Lớp xử lý nghiệp vụ thay đổi và lưu phương thức thanh toán vào hệ thống.
Nhiệm vụ và thuộc tính của các lớp
-Employee: Chứa thông tin cá nhân và thông tin về phương thức thanh toán của nhân viên.
-PaymentMethod: Chứa các thông tin về phương thức thanh toán như "pick-up", "mail", và "direct deposit"
-PaymentProcessor: Xử lý và lưu thay đổi phương thức thanh toán
![Diagram](https://www.planttext.com/api/plantuml/png/b59BJiCm4Dtx5AEkoY8NYAAeYB10eXLIkS346HKhyKVs11419sF1aRW2IPmYfOqAU3VpdjvxC-ElZyzDOFJSwaQ4MXdmDf1WnGt1dXgI30_OQJ8CM-8dMq42Dms608N2WqSjX1pBM-qQsn71gu3XqLJV5Iaemx5fK5CAU_RA7687gyfJ2FEcYuxHC3q6Y6LaX37Q35Zh9VfL2izMLUBzc7E6Jc6p3Cl07YNdUTIFMe-TEubBBoHRfabaVQwkPDswdiPagcKpS2FdtafaPSt_zBUecilgkcVqSjTBU_rDlL2-tsf1pWR5bsrADFNk_9fIsjRmhjKb-Rzw__oS9CbFp59OnKk7bPWZsLkIJDjUGeOzBVLd4mgnwGSSVlut0000__y30000)
![Diagram](https://www.planttext.com/api/plantuml/png/X99BRi8m48RtFiM8LIkH2x2eK9KkaP1G3p34Ksh5BppE8cVheaVg5JhE0udGWfVs___VFFppzRtbZ2btpYfkZOSKc5GssH8So5AJOO-z8v-XaejpHxuXg0sU4ZgbiCaXmPkBDlH4AagIQKn4aQzctuxoPz1JcWb-1SYmtntkgclCU4IcILo_AZLJe7efTjX0AlLmXZXvtUZbcQIAJDGNvmQquMYnXn2BWE4fcgQjkhW6XyQkvJsLdZN5m2O__m4TqnTCXLO6LQBUem8vj-Gc-0-J74p0sKYM2NR27cotE65G6eep_WIeTIBc1uYbUc3KOsVrsDbTsX5zAoF84lC8TIKbh-UHbvM9h8iQCos7DJnM5-XYVQDdIhgc_hVekHnngQrKKNxpBm000F__0m00)
4. Phân tích ca sử dụng: Maintain Timecard
Lớp phân tích
Dựa trên ca sử dụng Maintain Timecard, các lớp phân tích chính bao gồm:
-Employee: Đại diện cho nhân viên nhập và chỉnh sửa bảng thời gian.
-Timecard: Lớp lưu trữ thời gian làm việc của nhân viên cho mỗi dự án.
-TimecardProcessor: Xử lý việc cập nhật và lưu bảng thời gian.
Nhiệm vụ và thuộc tính của các lớp
-Employee: Chứa thông tin về số giờ làm việc và các dự án tương ứng.
-Timecard: Lưu thông tin về số giờ làm việc và dự án mà nhân viên đã nhập.
-TimecardProcessor: Xử lý nghiệp vụ kiểm tra và lưu trữ bảng thời gian.
![Diagram](https://www.planttext.com/api/plantuml/png/X5BRIWCn47tFLmnzgc3x0Q6KGbTGi59Gy7cw6RUncqsPp1QA-6K--4d-WjbRsYfeO0DpaZddpCb-VNmkWY1BxKeLThO2ze6KM2a9LcWhYHyyMKSvie49B4iC0JAB1QDJAc_B6xSl_P48tXGqY_hwBjCGAJgmGaSQ7eLjLNH8NZDJ9MiyhecjDpe9TUUXtZWh0pQ-qd3mjZ-BVSItlkRmx7b7PcnG8dqMzslODhY6bzAZ35tlWzaqJ6zM-lh2R9j9bYW7JVCJsfuSw9ZNVjOPQ9NdYKhgS3av6jDw_zVrMGxZNvEisRzIBYkii20N4uaykC6GtY7V8XVqKBiDDSptDiYiiz5xAqYMvtSQZOjRKIizxcGoFuMdOUHQtJ1I2PnEvt-OYYrCaPSE57fhK7Mw8wKMCTtc9_m6003__mC0)
![Diagram](https://www.planttext.com/api/plantuml/png/P94zRiCm38LtdeB8xWjaA8BM6Gq4Q2v0ouIZn99SYchHitN8aNA5qCvFqNhGzBxtFG6y_9mtMKcqX07ooKUKb1dKwy3Oa8zg3_S-i2FfiC9t_YWS7MFjgHSA0EGq2Mx3EAHlPXXDvfqVAIgk7iKLKiRzszzm9-d8JXkAr7FWg3KfjPHvfdTD_Ghmq6BrOdrSeqpxMT4L4QkWtXV0KcEcbb4z6t4WwHbZ2IrBXZcfVZLQ9Fvd5cksm8A7L2JZLv8JTqicbpRunKVcw9C6tv7opJ0d5ZqDwsVfBb7pmuPZDrtZ2W00__y30000)
5. Hợp nhất kết quả phân tích
Các lớp dùng chung: Cả hai ca sử dụng đều có lớp Employee là lớp trung tâm chứa thông tin về nhân viên.
Xử lý nghiệp vụ: Mỗi ca sử dụng có lớp xử lý nghiệp vụ riêng (PaymentProcessor và TimecardProcessor), nhưng cùng thực hiện nhiệm vụ xử lý dữ liệu nhập từ nhân viên và cập nhật hệ thống.
