# Lab1 - Kết quả bài thực hành
----

## 1. Nội dung thực hành
Mục đích - Phân tích kiến trúc và ca sử dụng hệ thống "Payroll System" trong file tài liệu yêu cầu đính kèm.

----
## 2. Phân tích ca sử dụng Payment :
1. Xác định các lớp phân tích :
- Các lớp chính cho ca sử dụng Payment có thể gồm:
  - PaymentController: Quản lý luồng xử lý thanh toán.
  - PaymentService: Xử lý logic nghiệp vụ thanh toán.
  - Invoice: Thông tin hóa đơn cần thanh toán.
  - PaymentGateway: Tương tác với cổng thanh toán (như PayPal, Stripe).
  - User: Thông tin người dùng thực hiện thanh toán.


2. Biểu Đồ Sequence Ca Sử Dụng Payment :

  ![Diagram](https://www.planttext.com/api/plantuml/png/T54nQiD04EprYYtZmXzm4GmkWhj0o0FEyk4xSjuZvvLibQbIkF8JX361G8hWL3g2YmlvnxuWNyWfiR30ShSCCxEpip_-C5oGS9JDJNA_a0xwrt0hYhb46baaPus9u02Ay9f1ojLB1gG4AY0RIhpg9UVaayETTBbEPPIlsB-12P_TueONbMFCxR_4SBKh8Zzyu0n88wYm5_2r-RwWF28tWkHI5D605Flt59Hc_upTYnjoloipEQwsaBD_WWUk3WIFMGsqZCvIN2YlvLIFPNsG2gM6cHOMfkpNgUegCjhz_MJGr309fMs7IOOIf_5rlm000F__0m00)
- Nhiệm vụ của từng lớp:
  - PaymentController: Nhận yêu cầu từ người dùng và điều hướng luồng xử lý.
  - PaymentService: Thực hiện logic thanh toán, kiểm tra tính hợp lệ.
  - Invoice: Lưu trữ thông tin hóa đơn cần thanh toán.
  - PaymentGateway: Tương tác với các bên cung cấp dịch vụ thanh toán.
  - User: Người gửi yêu cầu và nhận kết quả giao dịch.
    
3. Biểu Đồ Lớp Cho Payment:

    ![Diagram](https://www.planttext.com/api/plantuml/png/X9A_IiH04CRxVOefjRWNI2475_10iJ4SMAwRPNSncOLavpI8jONu41Q785W8LhU5HPvady1NC6VkJn8YbZFx_MQ-RzXl_pKj7IySvHaJ6IzBk51aJKoeu9u1GCxtZGWkNM5GRTfEudXVavWRYOdcg1FByUYOFR3jwDX8EjFTrtR77PrNLv9cdFx0X5xGWBanCayAtWN-Mp-tFBQuYzLMNU-bJHeqWjJITIOFtCoY6cnt_Vc7cqqc9sCn8r31lnkewZS24TQln4PKBTmF-qi-6qY3Vn8Qbi6ls52puRRX8iZ2UbKr1klFneupEAhkHueQUV0V0hG9_X7RTE1i_O9iAZ5jFiSfT_AMLxlo1m00__y30000)
         
**Giải Thích Biểu Đồ Lớp Payment :**
- NguoiDung: Đại diện cho người dùng của hệ thống, có các thuộc tính như mã người dùng và tên người dùng. Người dùng sẽ gửi yêu cầu thanh toán.
- DieuKhienThanhToan: Điều khiển việc xử lý yêu cầu thanh toán từ người dùng và gọi dịch vụ thanh toán.
- DichVuThanhToan: Xử lý logic thanh toán, bao gồm kiểm tra và thực hiện giao dịch.
- HoaDon: Lưu trữ thông tin hóa đơn, bao gồm mã hóa đơn và số tiền cần thanh toán.
- CongThanhToan: Tương tác với các cổng thanh toán bên ngoài như PayPal hoặc Stripe.

