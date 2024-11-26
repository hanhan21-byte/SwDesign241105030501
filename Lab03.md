# Hệ Thống Payroll System - Phân Tích Và Thiết Kế

## 1. Biểu Đồ Ngữ Cảnh Subsystem

### BankSystem Subsystem
**Mô tả:**  
- **BankSystem**: Hệ thống xử lý giao dịch ngân hàng, gửi lệnh chuyển khoản để thanh toán lương nhân viên.  
- **IBankSystem**: Interface giao tiếp giữa Payroll System và BankSystem, cung cấp phương thức `deposit`.  
- **PayrollController**: Gọi phương thức `deposit` để xử lý lương cho nhân viên.

---

### PrintService Subsystem
**Mô tả:**  
- **PrintService**: Hệ thống in phiếu lương (checks) và gửi phiếu lương cho nhân viên.  
- **IPrintService**: Interface cho phép Payroll System gọi hàm `print`.  
- **PayrollController**: Gọi phương thức `print` thông qua `IPrintService` để in phiếu lương.

---

### ProjectManagementDatabase Subsystem
**Mô tả:**  
- **ProjectManagementDatabase**: Hệ thống lưu trữ dữ liệu dự án liên quan đến nhân viên, hỗ trợ tính toán lương dựa trên các dự án.  
- **PayrollController**: Giao tiếp với ProjectManagementDatabase thông qua các phương thức `addProjectData`, `updateProjectData`, `deleteProjectData` để quản lý dữ liệu dự án.

---

## 2. Phân Tích Lớp Sang Phần Tử Thiết Kế
| **Lớp Phân Tích**          | **Phần Tử Thiết Kế**                        |
|----------------------------|---------------------------------------------|
| LoginForm                  | LoginForm                                   |
| MaintainTimecardForm       | MainEmployeeForm, TimecardForm, MainApplicationForm |
| TimecardController         | TimecardController                          |
| SystemClockInterface       | SystemClockInterface                        |
| PayrollController          | PayrollController                           |
| Paycheck                   | Paycheck                                    |
| Employee                   | Employee, EmployeeForm, EmployeeController  |
| PurchaseOrder              | PurchaseOrder, PurchaseOrderForm, PurchaseOrderController |
| BankSystemInterface        | BankSystemInterface, BankSystemProxy        |
| PrintService               | PrintService, PrintController               |
| ProjectManagementDatabase  | ProjectManagementDatabase, DatabaseController |
| PaycheckCalculator         | PaycheckCalculator, SalaryCalculator        |
| CommissionedEmployee       | CommissionedEmployeeForm, CommissionedEmployeeController |
| EmployeeDatabase           | EmployeeDatabase, DatabaseService           |
| PayrollDatabase            | PayrollDatabase, DatabaseController         |
| PaymentMethod              | PaymentMethod, DirectDeposit, CheckPayment  |
| Timecard                   | Timecard, TimecardEntryForm                 |
| BankInformation            | BankInformation, BankService                |

---

## 3. Phần Tử Thiết Kế Và Gói Sở Hữu
| **Phần Tử Thiết Kế**       | **Gói Sở Hữu**                              |
|----------------------------|---------------------------------------------|
| LoginForm                  | Middleware::Security:GUI Framework          |
| MainEmployeeForm           | Applications::Employee Activities           |
| TimecardForm               | Applications::Employee Activities           |
| MainApplicationForm        | Middleware::Security:GUI Framework          |
| TimecardController         | Applications::Employee Activities           |
| SystemClockInterface       | Applications::Payroll                       |
| PayrollController          | Applications::Payroll                       |
| Paycheck                   | Business Services::Payroll Artifacts        |
| Employee                   | Applications::Employee Activities           |
| PurchaseOrder              | Business Services::Purchase Management      |
| BankSystemInterface        | Business Services::Bank Integration         |
| PrintService               | Business Services::Printing                 |
| ProjectManagementDatabase  | Infrastructure::Database Management         |
| PaycheckCalculator         | Business Services::Payroll Artifacts        |
| CommissionedEmployee       | Applications::Employee Activities           |
| EmployeeDatabase           | Infrastructure::Database Management         |
| PayrollDatabase            | Infrastructure::Database Management         |
| PaymentMethod              | Business Services::Payment Integration      |
| Timecard                   | Applications::Employee Activities           |
| BankInformation            | Business Services::Bank Integration         |

---

## 4. Tầng Kiến Trúc Và Phụ Thuộc Của Chúng
![Architectural Layers and Dependencies](https://www.planttext.com/api/plantuml/png/T5CnJiCm5Drz2giBKw-0gXQGa5eHgMoemyVz9AQE7TaEKeGu0GihOc9WOE806HZeHN82he13Y8eT9qkKzv_VU_hF-Qu_PyQ2jcKkI05i1odIIQBHeBHWkP9q2HNg2Rqdr3rNIvLoUQPqlg4TS9eNGbM8lrW7hO3B27p9SsIWjntqG0v-yz9mYSRGLfq5ZWbKMWcnKDAsRzGRttWmw7q60wV4CcIx1GXM2h1A-p4Ir8ORYv9XaA7tEW4Brs1muqKBKQrkaTaLIAUQkps6yrApp7rUw2q62NfcOD_3QzHtdFKwSv2xTUNovkVIehw1TkBKZkZ-gQaVPKPbcktVWRAlLqQBhAdVgCtAfdvcDELD_V4t4KtzKf3_pKwdnz6z3vljgB4g_BexNgmP4Zljonxs5mdbXVMPOTaZL38qwfY3jG_EZl96hy3e2UzIZB5YbOzmoGpbjlshVm000F__0m00)
