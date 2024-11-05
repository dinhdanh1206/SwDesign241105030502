# Lab 2
---
## Phân Tích Các Ca Sử Dụng Trong Hệ Thống Payroll System
## 1. Quản lý Nhân Viên (Manage Employees)
### Mô tả:
  Quản trị viên thêm, sửa, xóa, và xem thông tin nhân viên.
### Lớp phân tích:
  - **Employee**: Chứa thông tin nhân viên (id, name, position).
  - **EmployeeManager**: Quản lý hành động thêm, sửa, xóa, xem nhân viên.
---
## 2. Chấm Công (Record Timecard)
### Mô tả:
  Nhân viên ghi lại số giờ làm việc trong kỳ trả lương.
### Lớp phân tích:
  - **Timecard**: Lưu trữ số giờ làm việc (hoursWorked, date).
  - **TimecardManager**: Quản lý ghi nhận và lưu trữ thời gian làm việc.
---
## 3. Xử Lý Bảng Lương (Process Payroll)
### Mô tả:
  Tính lương dựa trên thời gian làm việc và loại hình lương.
### Lớp phân tích:
  - **Payroll**: Chứa thông tin bảng lương (grossPay, netPay).
  - **PayrollProcessor**: Xử lý tính lương và tạo phiếu lương.
---
## 4. Quản lý Phương Thức Thanh Toán (Manage Payment Methods)
### Mô tả:
  Cập nhật phương thức thanh toán của nhân viên.
### Lớp phân tích:
  - **PaymentMethod**: Chứa thông tin phương thức thanh toán (type, details).
  - **PaymentManager**: Quản lý cập nhật phương thức thanh toán.
---
## 5. Tạo Báo Cáo (Generate Reports)
### Mô tả:
  Quản trị viên tạo các báo cáo về nhân viên, chấm công, và bảng lương.
### Lớp phân tích:
  - **Report**: Chứa thông tin báo cáo (type, content).
  - **ReportGenerator**: Xử lý tạo báo cáo.
---
## 6. Quản lý Thông Tin Ngân Hàng (Manage Bank Information)
### Mô tả:
  Giao tiếp với ngân hàng để thực hiện giao dịch trả lương.
### Lớp phân tích:
  - **BankTransaction**: Chứa thông tin giao dịch ngân hàng (amount, status).
  - **BankInterface**: Giao tiếp với ngân hàng thực hiện giao dịch.
---
## 7. Đăng Nhập/Đăng Xuất (Login/Logout)
### Mô tả:
  Người dùng đăng nhập và đăng xuất khỏi hệ thống.
### Lớp phân tích:
  - **User**: Thông tin người dùng (username, password).
  - **AuthenticationService**: Xác thực người dùng.
  - **UserSession**: Quản lý phiên làm việc của người dùng.
##
