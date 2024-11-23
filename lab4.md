## Bài thực hành Lab4.md  
### Thiết kế các ca sử dụng cho hệ thống "Payroll System" và giải thích lý do  
### **1. Use case Login**    
- Mục đích: Cho phép người dùng (nhân viên/quản trị viên) truy cập hệ thống payroll thông qua quy trình đăng nhập an toàn.
- Tác nhân: Người dùng và Hệ thống.
- Quy trình:
    + Người dùng nhập tên đăng nhập và mật khẩu.
    + Hệ thống xác thực thông tin:
    + Thành công: Cấp quyền truy cập.
    + Thất bại: Thông báo lỗi, yêu cầu thử lại.
    + Tiền điều kiện: Người dùng có tài khoản hợp lệ.
- Hậu điều kiện:
    + Thành công: Người dùng truy cập hệ thống.
    + Thất bại: Giới hạn truy cập nếu vượt quá số lần thử sai.
- Lý do thiết kế: Đảm bảo an toàn với mã hóa mật khẩu, giao diện đơn giản, và thông báo rõ ràng để hỗ trợ người dùng.

**Sơ đồ Use case** 

  ![Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bTYSab-aK9eSMgHGcAnWf9V-h4D3tVFpLH8ERmpBrq9AXrSMLoIcWjMuF5mTxj2ISR3tHD1qbobnQd9YSMf2af79XnfpajNoCjuk6jjWKBPuGNv2Xd8Ia6QGvtZVVBJC_EukC3swUhQmOKKh1Jy85fBCWvl0HfK0XGxCX79J2wuKf0-g8ki528EBqm6Mx8n6Kah5rGUpGhlXxlsboWKbZxSjLYX0g4HrMYmswmKF38VxcxE0wleLiX6QEHoICrB0OKS0000__y30000)
  
---
  
### **2. Use case Maintain Timecard**  
- Mục đích: Ghi nhận, chỉnh sửa, và quản lý giờ làm việc của nhân viên, hỗ trợ tính lương chính xác.
- Tác nhân:
    + Nhân viên: Cập nhật hoặc xem thẻ chấm công của mình.
    + Quản trị viên: Quản lý và chỉnh sửa thẻ chấm công cho nhân viên.
- Quy trình chính:
    + Người dùng nhập hoặc chỉnh sửa thông tin giờ làm, giờ nghỉ, làm thêm giờ.
    + Hệ thống lưu trữ và tính tổng số giờ làm việc.
- Luồng thay thế:
    + Thông tin không hợp lệ → Thông báo lỗi và yêu cầu sửa.
    + Quản trị viên chỉnh sửa → Lưu lại lịch sử chỉnh sửa.
    + Tiền điều kiện: Nhân viên có tài khoản và thẻ chấm công hợp lệ.
- Hậu điều kiện: Dữ liệu chấm công được lưu chính xác để sử dụng tính lương và báo cáo.
- Lý do thiết kế: Đảm bảo quản lý giờ làm việc minh bạch, hỗ trợ tính lương và tuân thủ chính sách lao động.

**Sơ đồ Use case**  
      ![Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bTYSab-aOAIQsv1JdvbQggIGcAn0em3ammeoizAJIvHy4tCIqnFBGAhWRAvIejJanEBKnMKV1Cpyqg0M24aCnSeL9G2LXRgRCG5Cqv1LzSE9A1W1TKDLye5DGr9HLXgKMPQ9KA5GsfU2j2z00000F__0m00)  

- Giải thích:
    + Employee: Nhân viên, tác nhân chịu trách nhiệm ghi nhận hoặc kiểm tra giờ làm việc của mình.
    + Admin: Quản trị viên, người có quyền chỉnh sửa hoặc quản lý thẻ chấm công của nhân viên.
    + UC_MaintainTimecard: Ca sử dụng chính "Quản lý thẻ chấm công".
    + Các đường kết nối mô tả mối quan hệ giữa tác nhân và ca sử dụng:
    + Nhân viên cập nhật giờ làm việc.
    + Quản trị viên chỉnh sửa thẻ chấm công và lưu lịch sử thay đổi.
    +Hệ thống hiển thị kết quả sau khi thực hiện các thao tác.
  
---
  
### **3. Usse case Run Payroll**  
- Mục đích: Tự động tính lương chính xác, tạo báo cáo và phiếu lương minh bạch.
- Tác nhân:
    + Quản trị viên: Khởi tạo và giám sát.
    + Hệ thống: Xử lý dữ liệu và tính toán lương.
- Quy trình chính:
    + Quản trị viên khởi tạo tính lương.
    + Hệ thống thu thập dữ liệu, áp dụng công thức tính lương, và xuất báo cáo/phiếu lương.
    + Kết quả được hiển thị để quản trị viên kiểm tra.
- Luồng thay thế:
    + Dữ liệu không hợp lệ → Thông báo lỗi, yêu cầu sửa.
    + Chỉnh sửa thủ công → Lưu lịch sử thay đổi.
- Tiền điều kiện: Dữ liệu chấm công và thông tin lương đã sẵn sàng.
- Hậu điều kiện: Lưu trữ chính xác, báo cáo và phiếu lương được tạo.
- Lý do thiết kế: Đảm bảo tính minh bạch, chính xác và tuân thủ quy định lao động.

**Sơ đồ Use case**  
      ![Diagram](https://www.planttext.com/api/plantuml/png/b96zJiCm58LtFyLHzhv01bJ4Kec5dpAZu4IDXUEKsAxeY1WOEl44KA4E84KmCCL27IprFVm4l09s4W6LAYIME_X-vzvphZ_DUYXLKYbTS99GLLROJmica4X4nzerJmAgScQ16RCl8kgPqxbKMT528sVke79dxiKa8aJBZ2OoGpIsjSZ1Ds-RfMy4zEpW_4IBesHUbPmJqkqP3FQs6uXnwASzC2ZNB4kettF8DXh4lPKOurm77qqzHUhCApZppZIeVreLeFRzRxczQNKhCUdODjCp_SV-rkw5zOM6ChEFcERCDMlzBU_XdQ4zg70LJevhPsfm-x5ZNNUr62EVxbQq9XUu_D6IOIRIy9bV0000__y30000)
  
- Giải thích:
  + Admin: Quản trị viên, tác nhân chính khởi tạo và giám sát quy trình tính lương.
  + System: Tác nhân phụ, chịu trách nhiệm xử lý và tạo kết quả.
  + UC_RunPayroll: Ca sử dụng "Tính lương", thể hiện toàn bộ quy trình từ khởi tạo, xử lý đến hiển thị kết quả.
  
---
  
### **4. Phân tích Lớp - Đến Cơ chế Phân tích**
- Hệ thống **Payroll** được chia thành các lớp chính như sau:

1. **Lớp Nhân viên (Employee)**  
   - **Mục đích**: Quản lý thông tin cá nhân và lương cơ bản.  
   - **Thuộc tính**: `employeeID`, `name`, `address`, `baseSalary`.  
   - **Hành vi**: Thêm, sửa, xóa thông tin nhân viên.  

2. **Lớp Thẻ chấm công (Timecard)**  
   - **Mục đích**: Ghi nhận giờ làm, thời gian nghỉ và làm thêm giờ.  
   - **Thuộc tính**: `date`, `hoursWorked`, `overtimeHours`.  
   - **Hành vi**: Tạo, cập nhật thẻ chấm công.  

3. **Lớp Quản trị viên (Admin)**  
   - **Mục đích**: Quản lý hệ thống, xác minh giờ làm, phân quyền.  
   - **Thuộc tính**: `adminID`, `name`, `role`.  
   - **Hành vi**: Xác thực đăng nhập, quản lý phân quyền.  

4. **Lớp Tính lương (Payroll)**  
   - **Mục đích**: Tính toán thu nhập, khấu trừ, tạo phiếu lương.  
   - **Thuộc tính**: `grossIncome`, `deductions`, `netIncome`.  
   - **Hành vi**: Tính toán lương, xuất phiếu lương.


 **Liên kết Phân tích-Lớp đến Cơ chế**
Các lớp phân tích được hiện thực hóa qua cơ chế cụ thể:

- **Cơ chế quản lý dữ liệu**:  
  - `Employee`, `Timecard` sử dụng cơ sở dữ liệu (SQL/MongoDB) hoặc ORM để lưu trữ.  

- **Cơ chế xác thực**:  
  - `Admin` sử dụng Authentication và Role-Based Access Control.  

- **Cơ chế xử lý nghiệp vụ**:  
  - `Payroll` sử dụng tầng logic xử lý (Service Layer) hoặc công cụ tính toán (Rules Engine).  

- **Cơ chế báo cáo**:  
  - `Payroll` tạo báo cáo và phiếu lương dưới dạng PDF, CSV.

**Sơ đồ Hệ thống Payroll System**

  ![Diagram](https://www.planttext.com/api/plantuml/png/X5GnRjj04EpvYeMA82a4zoe2GnJY8aGWHuIHTaqIkaF8Mvgy5Km4ALBb7GgG9arSfB8A5mJq3xuWNyZIEj4KBJbi2CxkpimEZ_oxUJWlBHQMizIBKYnB-A3GNEd4m1SFv1f3Xdje0jfOXzhsSM4BRPOEYJNwIW_0bCaiVPgYTCV4rscoAup7ZtS0gv9ip__wpGHMf6DNAXbFL6xfUUMhvnO8LU8hp7mHxdOmIwmcC4FhvA6a2qq1PeUkTd28OXbF-KNg2GnyHPYBBtkieRDtoMZ2GWyYxg4lfxn27HPq27RcOd4k1l9MzPeeJT2uoetm1zLSGhlawcXgsgY0-vbPnItN1UM3a3uhGlDU8OS53qfkvgFmdCflhpE8JdATAvrmLtCBTWPzMj2C0sbn3a4ELsjX1mxeKgm6U4SqHVAHEf9RHhk3vhDtmtFMrVp5LP-f-qZ6uxTzPnCO1TixXbUGDlS_AycZ_YEHoj9WLFt3m4hNlyp8wv_H_r34pUOtfBhPV6U8b40PH2tfoEkVf9RawHKAnwTw7K4cY13bZz8tN3MRRqV43-PybdiaClaBoayJxRmBj1LbwRAYfvlx1uPqUxTTc-NPj5wJZAvfv9qd9cx_DVy0003__mC0)
 
 - Giải thích
 - Lớp (class):
    + NhanVien: Quản lý thông tin nhân viên.
    + TheChamCong: Quản lý thông tin thẻ chấm công.
    + QuanTriVien: Quản lý quyền và xác thực.
    + TinhLuong: Thực hiện tính toán lương và tạo phiếu lương.
    + CoSoDuLieu: Lưu trữ thông tin nhân viên, thẻ chấm công.
    + BaoCao: Xuất báo cáo lương dưới dạng PDF/CSV.
- Quan hệ:
    + NhanVien và TheChamCong kết nối với CoSoDuLieu để lưu trữ dữ liệu.
    + QuanTriVien kiểm soát quyền và xác minh qua TinhLuong.
    + TinhLuong nhận dữ liệu từ TheChamCong và tạo báo cáo qua BaoCao.
