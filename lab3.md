# Lab 3
---
## I. Subsystem context diagrams.

**BankSystem (Hệ thống ngân hàng)**: Đây là hệ thống chính, thực hiện các chức năng ngân hàng như quản lý tài khoản, xử lý giao dịch và cung cấp các dịch vụ ngân hàng trực tuyến.

  ![Diagram](https://www.planttext.com/api/plantuml/png/f591JiCm4BplArOz5ObMS8sgg89JRqYym3WROTLPLzuD8a9z6GUUn1U86mmcLKzSxBLdPdSyykVxnrRKHEqx3s2z4S47CyJW_NrWJJj5t6piTAXhV0D4Z3r_ivPNS0Hmh1HROmbtTuRtZuCeTQFivpuB6pe4SReqezm-azrNcAjh7DaXoIjCwuxR43kZBd2QmK49FRLQOUCYMSsz14zomHTdyXF-c93-IQRw4CFhy7yhlpcTsEC8OdKwTJwM7WhX19rdkxXPhsyNk5hLPNPGvbXGBZ0IbEsS0JCZS467Ss2kWorna_x95m000F__0m00)
- Biểu đồ ngữ cảnh cho hệ thống con BankSystem sẽ bao gồm các tác nhân bên ngoài và các hệ thống mà hệ thống con này tương tác với:
- Thành phần chính:
  - PayrollController (Control Object): Đối tượng điều khiển, gọi giao diện để thực hiện việc gửi lương.
  - ankSystem (Interface): Giao diện trung gian định nghĩa chức năng deposit() để gửi lương vào tài khoản ngân hàng.
  - BankSystem (Subsystem Proxy): Hệ thống con thực thi giao diện IBankSystem, thực hiện logic gửi lương.
  - Paycheck (Entity): Thực thể lưu thông tin về số tiền lương.
  - BankInformation (Entity): Thực thể lưu thông tin tài khoản ngân hàng.
- Mối quan hệ :
  - PayrollController → IBankSystem:
      + PayrollController gọi phương thức deposit() của IBankSystem để xử lý gửi lương.
  - IBankSystem → BankSystem:
      + BankSystem kế thừa và thực thi giao diện IBankSystem.
  - IBankSystem → Paycheck & BankInformation:
      + Giao diện IBankSystem sử dụng dữ liệu từ Paycheck (số tiền lương) và BankInformation (thông tin ngân hàng).
## II. Analysis class to design element map.
