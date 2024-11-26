# Phân Tích Kiến Trúc Hệ Thống Payroll System

## 1. Kiến trúc đề xuất

### Layered Architecture (Kiến trúc phân tầng)

#### **Thành phần chính**:
1. **User Interface Layer (Giao diện người dùng)**:
   - Tương tác qua giao diện Windows-based.
   - Chức năng: Nhập thông tin thời gian làm việc, lựa chọn phương thức thanh toán, xem báo cáo.

2. **Application Layer (Tầng nghiệp vụ)**:
   - Xử lý logic nghiệp vụ: tính toán lương, kiểm tra dữ liệu, xử lý overtime và hoa hồng.

3. **Data Access Layer (Tầng truy cập dữ liệu)**:
   - Thực hiện các truy vấn tới cơ sở dữ liệu như Payroll Database và Project Management Database.
   - Đảm bảo thông tin lấy từ DB2 không bị thay đổi.

4. **Database Layer (Cơ sở dữ liệu)**:
   - Lưu trữ thông tin về nhân viên, timecards, thông tin dự án, và bảng lương.

#### Biểu đồ kiến trúc:
![Diagram](https://www.planttext.com/api/plantuml/png/R55RJiCm4FptALO-G0_01sgg8bG990Jq0DlDqfhw4QqtGX7YP7nm9Aw0qwObKUi_pundPyU_tp_ph2ZQ1czCthi8aZ8RTUePdh2Jv3syT5avG2MqSygahR0n3T8UjmnsdLbW5PNb3OajO8RMmQU1SiXZpd0N6fywvlLg10xcLHrSBCJNo77HPXUvQ1xIrj71SNE2nhwlBZ2Xr8yOopkPcWUEUacSebmopzmaqNkEBAX99e6MgBZ1V5ok7YvNLrmkhkIRW4EqAIRflVHw33MmPNwfSJQx_T_z1koXPoI53wSxQyvKhpi7AxgAg8Txo1epvrZtF_m7003__mC0)

---

## 2. Cơ chế phân tích

### **Danh sách cơ chế chính**:
1. **Quản lý bảng thời gian (Timecard Management)**:
   - Nhập và ghi lại thời gian làm việc, bao gồm tự động ghi nhận overtime.

2. **Tính toán lương (Payroll Calculation)**:
   - Tự động tính toán lương dựa trên giờ làm, overtime, và hoa hồng.

3. **Xử lý phương thức thanh toán (Payment Method Processing)**:
   - Cho phép chọn phương thức thanh toán và nhập thông tin ngân hàng.

4. **Truy vấn từ cơ sở dữ liệu dự án (Project Management DB Access)**:
   - Tích hợp và truy xuất dữ liệu từ DB2.

5. **Báo cáo (Reporting Mechanism)**:
   - Tạo báo cáo giờ làm, lương, và thông tin liên quan.

6. **Bảo mật (Security Mechanism)**:
   - Bảo vệ thông tin nhân viên, giới hạn quyền truy cập.

7. **Tự động trả lương (Payroll Scheduling)**:
   - Tự động xử lý trả lương vào thứ Sáu hàng tuần và ngày cuối tháng.

---

## 3. Phân tích ca sử dụng: **Select Payment**

### **Lớp phân tích**:
- **Employee**: Đại diện cho nhân viên chọn phương thức thanh toán.
- **PaymentMethod**: Lưu thông tin phương thức thanh toán.
- **PaymentProcessor**: Xử lý và lưu thay đổi phương thức thanh toán.

### **Nhiệm vụ và thuộc tính của các lớp**:
- **Employee**: Chứa thông tin cá nhân và phương thức thanh toán.
- **PaymentMethod**: Lưu các lựa chọn thanh toán như "pick-up", "mail", và "direct deposit".
- **PaymentProcessor**: Xử lý nghiệp vụ thay đổi phương thức thanh toán.

#### Biểu đồ:
![Diagram](https://www.planttext.com/api/plantuml/png/b59BJiCm4Dtx5AEkoY8NYAAeYB10eXLIkS346HKhyKVs11419sF1aRW2IPmYfOqAU3VpdjvxC-ElZyzDOFJSwaQ4MXdmDf1WnGt1dXgI30_OQJ8CM-8dMq42Dms608N2WqSjX1pBM-qQsn71gu3XqLJV5Iaemx5fK5CAU_RA7687gyfJ2FEcYuxHC3q6Y6LaX37Q35Zh9VfL2izMLUBzc7E6Jc6p3Cl07YNdUTIFMe-TEubBBoHRfabaVQwkPDswdiPagcKpS2FdtafaPSt_zBUecilgkcVqSjTBU_rDlL2-tsf1pWR5bsrADFNk_9fIsjRmhjKb-Rzw__oS9CbFp59OnKk7bPWZsLkIJDjUGeOzBVLd4mgnwGSSVlut0000__y30000)

---

## 4. Phân tích ca sử dụng: **Maintain Timecard**

### **Lớp phân tích**:
- **Employee**: Đại diện cho nhân viên nhập và chỉnh sửa bảng thời gian.
- **Timecard**: Lưu trữ số giờ làm việc cho mỗi dự án.
- **TimecardProcessor**: Xử lý việc cập nhật và lưu bảng thời gian.

### **Nhiệm vụ và thuộc tính của các lớp**:
- **Employee**: Lưu thông tin về giờ làm và dự án tương ứng.
- **Timecard**: Lưu số giờ làm việc và dự án mà nhân viên nhập.
- **TimecardProcessor**: Kiểm tra và lưu trữ bảng thời gian.

#### Biểu đồ:
![Diagram](https://www.planttext.com/api/plantuml/png/X5BRIWCn47tFLmnzgc3x0Q6KGbTGi59Gy7cw6RUncqsPp1QA-6K--4d-WjbRsYfeO0DpaZddpCb-VNmkWY1BxKeLThO2ze6KM2a9LcWhYHyyMKSvie49B4iC0JAB1QDJAc_B6xSl_P48tXGqY_hwBjCGAJgmGaSQ7eLjLNH8NZDJ9MiyhecjDpe9TUUXtZWh0pQ-qd3mjZ-BVSItlkRmx7b7PcnG8dqMzslODhY6bzAZ35tlWzaqJ6zM-lh2R9j9bYW7JVCJsfuSw9ZNVjOPQ9NdYKhgS3av6jDw_zVrMGxZNvEisRzIBYkii20N4uaykC6GtY7V8XVqKBiDDSptDiYiiz5xAqYMvtSQZOjRKIizxcGoFuMdOUHQtJ1I2PnEvt-OYYrCaPSE57fhK7Mw8wKMCTtc9_m6003__mC0)

---

## 5. Hợp nhất kết quả phân tích

- **Lớp dùng chung**: Cả hai ca sử dụng đều có lớp **Employee** là trung tâm, chứa thông tin nhân viên.
- **Xử lý nghiệp vụ**:
  - **Select Payment**: PaymentProcessor.
  - **Maintain Timecard**: TimecardProcessor.
- **Chức năng chính**: Xử lý dữ liệu từ nhân viên và cập nhật hệ thống.

