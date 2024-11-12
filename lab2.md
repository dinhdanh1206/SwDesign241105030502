# Lab 2
---
## I.Phân Tích Các Ca Sử Dụng Trong Hệ Thống Payroll System
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
## 8. Biểu đồ Sequence giản lược cho ca sử dụng Duy trì Thẻ Chấm Công (Maintain Timecard)
 ![Diagram](https://www.planttext.com/api/plantuml/png/b94nQiCm541tdUAJgO7a0XvAG1c5m2He5sgn3B4S4XdI4tJk0KhjXYo5q0wTB4e7bTn39-WLgc-tWzikMRJyzvw-qATxdssjtDYgM16fRBa1hlsZ4Rb_CY2tm0LPnt6kyhKq5aPf5TgzOVvjgKFhQ3mE1VMl9XiXdR8X_I-qf7H8qLEp2EvX7jmpouExhJgCBkQC42vWUXcx2MJ17VFVmOj2SZ61B6htpDU5G5zDm6I-lXcJbA4TBqp0XhOfpzIZY3vkai3gz5BzySS4Xp3zkMNd6mKc0aVJ2M2rhuq6XNJV-twEnHIehjMFuUFEx_izkyKZoCKmgSjOG-HWoUpQNE6lVG400F__0m00)
- Giải Thích các Thành Phần Chính:
  - Nhân Viên (NV): Gửi yêu cầu chấm công, bao gồm mã nhân viên, giờ làm việc và ngày.
  - Quản Lý Thẻ Chấm Công (QL): Nhận yêu cầu từ nhân viên và thực hiện tạo mới thẻ chấm công.
  - Thẻ Chấm Công (TCC): Đối tượng thẻ chấm công được tạo và lưu trữ.
  - Cơ Sở Dữ Liệu (CSDL): Lưu lại thẻ chấm công mới và gửi thông báo thành công.
## II.Viết code Java mô phỏng ca sử dụng Maintain Timecard.
- Code Java mô phỏng ca sử dụng Maintain Timecard
  
        // Lớp Employee đại diện cho một nhân viên với thông tin cơ bản như id và tên
      class Employee {
          private String id;
          private String name;
          public Employee(String id, String name) {
              this.id = id;
              this.name = name;
          }
          public String getId() {
              return id;
          }
          public String getName() {
              return name;
          }
      }
      
      // Lớp Timecard đại diện cho thẻ chấm công với các thuộc tính cơ bản như giờ làm việc và ngày
      class Timecard {
          private String employeeId;
          private int hoursWorked;
          private String date;
          public Timecard(String employeeId, int hoursWorked, String date) {
              this.employeeId = employeeId;
              this.hoursWorked = hoursWorked;
              this.date = date;
          }
          public String getEmployeeId() {
              return employeeId;
          }
          public int getHoursWorked() {
              return hoursWorked;
          }
          public String getDate() {
              return date;
          }
          @Override
          public String toString() {
              return "Timecard{" +
                      "Employee ID='" + employeeId + '\'' +
                      ", Hours Worked=" + hoursWorked +
                      ", Date='" + date + '\'' +
                      '}';
          }
      }
      
      // Lớp TimecardManager chịu trách nhiệm tạo và quản lý các bản ghi thẻ chấm công
      import java.util.ArrayList;
      import java.util.List;
      class TimecardManager {
          private List<Timecard> timecards;
          public TimecardManager() {
              timecards = new ArrayList<>();
          }
          // Phương thức thêm thẻ chấm công mới
          public void addTimecard(Timecard timecard) {
              timecards.add(timecard);
              System.out.println("Added: " + timecard);
          }
          // Phương thức xem tất cả các thẻ chấm công
          public void viewTimecards() {
              for (Timecard tc : timecards) {
                  System.out.println(tc);
              }
          }
      }
      
      // Lớp Main mô phỏng quá trình tạo nhân viên và ghi nhận thời gian làm việc
      public class Main {
          public static void main(String[] args) {
              // Tạo nhân viên mới
              Employee employee = new Employee("E001", "Nguyen Van A");
              // Tạo TimecardManager để quản lý thẻ chấm công
              TimecardManager timecardManager = new TimecardManager();
              // Ghi nhận các thẻ chấm công cho nhân viên
              Timecard timecard1 = new Timecard(employee.getId(), 8, "2024-10-25");
              Timecard timecard2 = new Timecard(employee.getId(), 7, "2024-10-26");
              // Thêm thẻ chấm công vào hệ thống
              timecardManager.addTimecard(timecard1);
              timecardManager.addTimecard(timecard2);
              // Xem các thẻ chấm công đã ghi nhận
              System.out.println("\nDanh sách thẻ chấm công:");
              timecardManager.viewTimecards();
          }
      }
- Giải Thích Mã:
  - Lớp Employee: Lưu trữ thông tin cơ bản của nhân viên.
  - Lớp Timecard: Đại diện cho thẻ chấm công, chứa các thông tin như ID nhân viên, số giờ làm việc và ngày.
  - Lớp TimecardManager: Quản lý việc thêm và xem các thẻ chấm công.
  - Lớp Main: Mô phỏng quá trình thêm thẻ chấm công cho một nhân viên và hiển thị danh sách thẻ chấm công.
