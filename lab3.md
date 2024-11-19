# Lab 3
---
## I. Subsystem context diagrams.
  ![Diagram](https://www.planttext.com/api/plantuml/png/h911JiGm34NtEOLt31AzG8KG0h7e3j4JU3AUcT3KYM8NJJLmCXOSYIlGb1OwmvOi8ilEy__vd-yVjwAOj6kzaSPnn8GjHBGDxgZMtXCaiegyysJC1Tm7rXGyXFNpq3RMemWyOZ_q_3JpbE1e89_KyJHRNPgtp5UibBPeoRYvWkeEkQbxKMfdS4CnYDCL3hZTasrAcAih6CYGaHBoNV4sf1RL1PuqwcujtzjY2eT-CldF8W-iJXt9RmGZk11RC1bu8Z_MidTHpD_8YkBc98aIDYv7FziK60K4NXoQvSFhrw9O_EvabfV-M3iVd9ly0W00__y30000)
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
