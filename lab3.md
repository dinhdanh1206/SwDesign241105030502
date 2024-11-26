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
  - Ánh xạ các lớp phân tích (analysis classes) đến các phần tử thiết kế (design elements) là một bước quan trọng trong quá trình phát triển phần mềm, giúp chuyển đổi các khái niệm từ giai đoạn phân tích sang giai đoạn thiết kế chi tiết. Dưới đây là một cách tiếp cận để thực hiện ánh xạ này.

### a. Lớp Phân Tích (Analysis Classes)

Lớp phân tích thường được xác định trong giai đoạn phân tích yêu cầu và phản ánh các khái niệm hoặc đối tượng từ yêu cầu nghiệp vụ. Các lớp này chỉ ra các tính năng, các đối tượng trong hệ thống mà không quan tâm đến cách thức triển khai chi tiết.

Ví dụ về các lớp phân tích trong một **Bank System**:
- **Account**: Đại diện cho tài khoản ngân hàng của khách hàng.
- **Transaction**: Đại diện cho một giao dịch tài chính (chuyển tiền, rút tiền, v.v.).
- **Customer**: Đại diện cho khách hàng của ngân hàng.
- **Payment**: Đại diện cho các giao dịch thanh toán giữa các hệ thống.
- **BankSystem**: Hệ thống ngân hàng, quản lý các tài khoản, giao dịch và kết nối với các dịch vụ khác.

## b. Phần Tử Thiết Kế (Design Elements)

Các phần tử thiết kế chi tiết hóa các lớp phân tích thành các thành phần thực thi trong hệ thống, bao gồm các lớp, mô-đun, giao diện, và các lớp hỗ trợ.

## c. Ánh Xạ Các Lớp Phân Tích Đến Các Phần Tử Thiết Kế

### . **Account → Account Class**
- **Lớp phân tích**: `Account`
  - Các thuộc tính và phương thức trong lớp phân tích thường sẽ được chuyển thành các lớp thiết kế cụ thể.
- **Phần tử thiết kế**: `Account Class`
  - Các thuộc tính của tài khoản như `accountNumber`, `balance`, và `accountHolder` sẽ được triển khai trong lớp thiết kế.
  - Các phương thức như `deposit()`, `withdraw()`, `getBalance()` có thể được thiết kế như các phương thức trong lớp này.

### . **Transaction → Transaction Class**
- **Lớp phân tích**: `Transaction`
  - Mô tả các giao dịch như chuyển tiền, rút tiền.
- **Phần tử thiết kế**: `Transaction Class`
  - `Transaction` có thể có các thuộc tính như `transactionId`, `amount`, `date`. <br> Phương thức: `processTransaction()`, `validateTransaction()`.

### . **Customer → Customer Class**
- **Lớp phân tích**: `Customer`
  - Các thuộc tính và phương thức mô tả thông tin khách hàng.
- **Phần tử thiết kế**: `Customer Class`
  - `Customer` có thể có các thuộc tính như `customerId`, `name`, `email`, `phoneNumber`.
  - Các phương thức liên quan đến khách hàng như `updateInfo()`, `getAccountInfo()`.

### . **Payment → Payment System Integration**
- **Lớp phân tích**: `Payment`
  - Mô tả các giao dịch thanh toán, đặc biệt khi hệ thống cần tích hợp với các hệ thống thanh toán bên ngoài.
- **Phần tử thiết kế**: `Payment Service Class` hoặc `PaymentGateway`
  - Lớp thiết kế này có thể gọi các API từ bên ngoài, ví dụ như `sendPayment()`, `verifyPayment()`, và tích hợp với các hệ thống thanh toán qua giao diện (API) thiết kế.

### . **BankSystem → BankSystem Class**
- **Lớp phân tích**: `BankSystem`
  - Mô tả các chức năng chính của hệ thống ngân hàng.
- **Phần tử thiết kế**: `BankSystem Class`
  - Lớp thiết kế này sẽ chứa các phương thức như `manageAccount()`, `processTransaction()`, và `integratePayment()` để kết nối với các phần tử khác trong hệ thống.

## . Ví Dụ Minh Họa: Ánh Xạ Lớp Phân Tích Đến Các Phần Tử Thiết Kế trong Bank System

| **Lớp Phân Tích**    | **Phần Tử Thiết Kế**      | **Thuộc Tính và Phương Thức**                                                   |
|----------------------|---------------------------|--------------------------------------------------------------------------------|
| **Account**           | `Account Class`            | Thuộc tính: `accountNumber`, `balance`, `accountHolder`. <br> Phương thức: `deposit()`, `withdraw()`, `getBalance()`. |
| **Transaction**       | `Transaction Class`        | Thuộc tính: `transactionId`, `amount`, `date`. <br> Phương thức: `processTransaction()`, `validateTransaction()`. |
| **Customer**          | `Customer Class`           | Thuộc tính: `customerId`, `name`, `email`, `phoneNumber`. <br> Phương thức: `updateInfo()`, `getAccountInfo()`. |
| **Payment**           | `PaymentService Class`     | Phương thức: `sendPayment()`, `verifyPayment()`. <br> Tích hợp API thanh toán bên ngoài. |
| **BankSystem**        | `BankSystem Class`         | Phương thức: `manageAccount()`, `processTransaction()`, `integratePayment()`. |
## a. Ánh Xạ Các Lớp Phân Tích Sang Mô Hình Lớp UML
![Diagram](https://www.planttext.com/api/plantuml/png/V9DTJiCm3CVVUufeJvt4Bj07D0P2smj26Xp0Ixqj8XzLucwg42VZWIDn1HAQR4rLw4CZst_7lzZ9z-VNqX5OQfKik0Jds1tdfjN4tWiMFkZDfrRjq5PiIrReGn_QWGJDiMAFqW1byhMHzLXUOsESe19KKCIiUSLEHjIzuYpeM5iu_oCv8AtwikKy5Vue8lgB1Us0ap0wuTFLjQbpdgn8H0Jontdm_zvkhE7et63VK7LbZ4JGlUG4KeIqFpGNjllMaL5e4nYFzfXAWyBSWmg4p5tDqMYS6adR19QDtfjIupciAJxkOXpphzJ7eddbVOPEeQOjsfFWcAWTwZf6yY7TC8jSD0A3vr8nxnHQiUzIzkHWfXgt0lssxHoXIX0AD1mm4fVnnbsEa1rqOe23mjNmncHvGXCUh6zbmctwjHhr9GTEJsUnkCtkOiLcQt2pOkWBci7Hl6JZ4YxMRDVDYa4ug4SJyHcl3lskIpyJ_tn_0000__y30000)

### 3 Ánh xạ các phần tử thiết kế vào các gói

| Design Element       | "Owning" Package           |
|----------------------|----------------------------|
| **Account Class**       | AccountManagement         |
| **Transaction Class**   | TransactionProcessing     |
| **Customer Class**      | CustomerManagement        |
| **PaymentService Class**| PaymentIntegration        |
| **BankSystem Class**    | BankSystemCore            |

### 4 Biểu đồ mô tả các layers trong hệ thống và quan hệ giữa chúng
![Digital](https://www.planttext.com/api/plantuml/png/Z9I_IiH04CRxFCMGtXUm4C-_Y7Tmg9rOZ7lBPJ7P3RkpQX1h2ojBIn4H1B6mImgByqNs2Nm5BtSURh8vCKr89lFxzfjlo5VriMu8DTaiZN9aPpZc40yrDrmIab0I-bXm7SDL1DFhkA_6GkuedPtCdmSeP2_FKy5cNtkL7cFAIjhYX28rNk58epJ8VZ-_ZdwbDwmHaXi3jH1hYVyW3xa-5uo7k6PXqnfI6TVDjqCiCkunVF4j98Ifo4o_I_c0vye8Khe8nOFQGjyl-6hRbyIrn1Js9F6nxfhsps5taVW5BhZRakaY3_qUScQreA9dHu9cKbvQiBAo5WmGLY7UTTMhW6BoOe6vyjd6KMUcy_wEMIzXTAG_HxHJMTBVNf9vSokyxjueiEbxzzAesu-qBU3SbKyIHgvwWrIuwgPrW2QdE_8_MO7dnYJ-IOa2z_v85YjI4_PT-K4WNNKdQiGjIwQywWaeGPa0gSc3Z9VGmjsgWOF98oIJT_oNhUOQpY9A1AIkV12GgEcDuFFELVTo3AUkV5IGkVALucYTor7z5_e6003__mC0)
