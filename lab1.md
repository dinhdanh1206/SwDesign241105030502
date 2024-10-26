# Lab1 - Kết quả bài thực hành
----

## 1. Nội dung thực hành
Mục đích - Phân tích kiến trúc và ca sử dụng hệ thống "Payroll System" trong file tài liệu yêu cầu đính kèm.

----
## 2. Phân tích ca sử dụng Payment
### 2.1. Xác định các lớp phân tích:
- Các lớp chính cho ca sử dụng Payment có thể gồm:
  - PaymentController: Quản lý luồng xử lý thanh toán.
  - PaymentService: Xử lý logic nghiệp vụ thanh toán.
  - Invoice: Thông tin hóa đơn cần thanh toán.
  - PaymentGateway: Tương tác với cổng thanh toán (như PayPal, Stripe).
  - User: Thông tin người dùng thực hiện thanh toán.
### 2.2. Biểu Đồ Sequence Ca Sử Dụng Payment:
  ![Diagram](https://www.planttext.com/api/plantuml/png/T54nQiD04EprYYtZmXzm4GmkWhj0o0FEyk4xSjuZvvLibQbIkF8JX361G8hWL3g2YmlvnxuWNyWfiR30ShSCCxEpip_-C5oGS9JDJNA_a0xwrt0hYhb46baaPus9u02Ay9f1ojLB1gG4AY0RIhpg9UVaayETTBbEPPIlsB-12P_TueONbMFCxR_4SBKh8Zzyu0n88wYm5_2r-RwWF28tWkHI5D605Flt59Hc_upTYnjoloipEQwsaBD_WWUk3WIFMGsqZCvIN2YlvLIFPNsG2gM6cHOMfkpNgUegCjhz_MJGr309fMs7IOOIf_5rlm000F__0m00)
- Nhiệm vụ của từng lớp
  - PaymentController: Nhận yêu cầu từ người dùng và điều hướng luồng xử lý.
  - PaymentService: Thực hiện logic thanh toán, kiểm tra tính hợp lệ.
  - Invoice: Lưu trữ thông tin hóa đơn cần thanh toán.
  - PaymentGateway: Tương tác với các bên cung cấp dịch vụ thanh toán.
  - User: Người gửi yêu cầu và nhận kết quả giao dịch.

 
