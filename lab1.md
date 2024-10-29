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

---
## 3. Phân Tích Ca Sử Dụng "Maintain Timecard"

   1 . Xác định các lớp phân tích:
   
   -  TimecardController: Điều khiển yêu cầu từ người dùng.
   - TimecardService: Xử lý logic liên quan đến chấm công.
   - Timecard: Thông tin về giờ làm việc.
   - Employee: Thông tin nhân viên cần chấm công.
   
   2 . Biểu Đồ Sequence Ca Sử Dụng Maintain Timecard.
 ![Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3fThRa5EVcLggeAkdK98PcvgSc9HYdD-NabHVavEQf62bKBwmzrhCnKg3wygLKX-k6ivc5nRe92N0QHA59A1rD9SXUJ3M_BIDJIvi9Y0P6vmQb5PPd8gqD0AeA4AEOVtuj8FKuca6QWBnUQI390UXPBCF8Nqp8UxvmADMv2BQG0kRvKKFTorMA7iuUv6C7CXoAYCmmipKIp1wX-WYV10iu8v8-dmmdo5x8UxzfSe59O2JUPoICrB0OKl0000__y30000)
  - Nhiệm vụ của từng lớp:
    - TimecardController: Nhận yêu cầu và điều khiển luồng xử lý.
    - TimecardService: Xử lý logic cập nhật và lưu trữ thông tin chấm công.
    - Timecard: Lưu thông tin giờ làm việc của nhân viên.
    - Employee: Gửi yêu cầu và nhận kết quả.
      
   3 . Biểu Đồ Lớp Cho Maintain Timecard.
   
   ![Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bToJc9niO9VHc9UM6Pgda8rbuA2GcuYZ6-b45nIb9cN3X8jISt39fnUckcKc9Vkd96OwvoVbwwXoLNB1JNL9JErr3i3g1uc2J4-ER40Q509Rbt96M6bg5egIdqgSQb75eUv7raCsR75-UwP-Jw9kLOAcNab82FW7jVLjSFYNYk5z8UxrsOgL1vULQgG_73Nyb8kJ4KGhIYE1klhpLH8URYxEpb3eUpXxgLSQ4f0kb2SRWMoO6s1Gbu6a2fHICzyk7kkGixX1RbS3gbvAQ2u0W000F__0m00)
   
   Giải Thích Biểu Đồ Lớp Maintain Timecard
- NhanVien (Nhân Viên)

  - Đại diện cho người dùng là nhân viên.
  - Thuộc tính:
    - maNhanVien: Mã định danh của nhân viên.
    - tenNhanVien: Tên của nhân viên.
    - Phương thức:
    - guiBangChamCong(): Nhân viên gửi bảng chấm công sau khi làm việc.
    - DieuKhienChamCong (Điều Khiển Chấm Công)

Lớp này điều khiển luồng xử lý khi có yêu cầu cập nhật bảng chấm công từ nhân viên.
- Phương thức:
    - capNhatBangChamCong(): Nhận yêu cầu và chuyển nó cho lớp dịch vụ xử lý.
    - DichVuChamCong (Dịch Vụ Chấm Công)

Thực hiện các logic nghiệp vụ liên quan đến chấm công, như kiểm tra giờ làm và lưu trữ dữ liệu.
- Phương thức:
    - xuLyBangChamCong(): Xử lý và cập nhật thông tin chấm công của nhân viên.
    - BangChamCong (Bảng Chấm Công)

Lưu trữ thông tin về số giờ làm việc của nhân viên.
- Thuộc tính:
    - maBangChamCong: Mã định danh của bảng chấm công.
    - soGioLam: Số giờ làm việc được ghi nhận.

Luồng Hoạt Động Của Ca Sử Dụng Maintain Timecard

   - NhanVien (Nhân Viên) gửi yêu cầu chấm công (qua phương thức guiBangChamCong()).
  - DieuKhienChamCong (Điều Khiển Chấm Công) nhận yêu cầu từ nhân viên và chuyển đến lớp DichVuChamCong (Dịch Vụ Chấm Công).
  - DichVuChamCong xử lý bảng chấm công và cập nhật dữ liệu vào BangChamCong (Bảng Chấm Công).

---
## 4. Hợp Nhất Kết Quả Phân Tích.
  1 . Biểu Đồ Lớp Cho Maintain Timecard.
  
  ![Diagram](https://www.planttext.com/api/plantuml/png/T9CnJiCm58RtdEADCFG26L15Ar69YeMe4gDnBTiYiQl6HbI8cG4nS00a62eaf0u8fcPW2E8UFW5Nm6xQ94xIqI_l__xVxpb_sNS_LMYkT187E4Pf2cTKIpxKWi9j0009AWiXdAiv5zIL5H7j-bsmOp0a9fo84h4zDmaTPQhvCH9qm50oa88U75RK8IVwbDd-oEfO9D6MVwF7YmkY1qYN7pfbEsQXmcXc_TL-Cymckk5qnKaIpL7Tnjs4QJognsfpV6iNU9_lIAAXB0TNdEhpIMMqcTXKwikOL3h7QQHLNNdglZkNUittEk5oZ98Gk50EKRsDNk-eQnyXK9EjE2poTmtOhDzqaGAKp5z5KBuBJrx6wL1ZPjRB173-PIDr61OWVrKRp2E7gSaUC8Dhaosz56tZYk9dQK0QONnNnzWkBuJODYwigUi4nGMm_1F1pzFlnhujzBSNMgN9FZ0mRh9xqGZlnNHYRwMX6zng1i9cNIcWbl0CSVwI17qYfkut_mS00F__0m00)
  
  Giải Thích Biểu Đồ Lớp Payment:
  - NguoiDung: Đại diện cho người dùng của hệ thống, có các thuộc tính như mã người dùng và tên người dùng. Người dùng sẽ gửi yêu cầu thanh toán.
  - DieuKhienThanhToan: Điều khiển việc xử lý yêu cầu thanh toán từ người dùng và gọi dịch vụ thanh toán.
  - DichVuThanhToan: Xử lý logic thanh toán, bao gồm kiểm tra và thực hiện giao dịch.
  - HoaDon: Lưu trữ thông tin hóa đơn, bao gồm mã hóa đơn và số tiền cần thanh toán.
  - CongThanhToan: Tương tác với các cổng thanh toán bên ngoài như PayPal hoặc Stripe.

 2 . Luồng Hoạt Động Hợp Nhất.
   - Người dùng gửi yêu cầu thanh toán → DieuKhienThanhToan xử lý và gọi DichVuThanhToan → thông tin từ HoaDon được lấy và gửi qua CongThanhToan.
   - Nhân viên gửi yêu cầu chấm công → DieuKhienChamCong gọi DichVuChamCong để cập nhật giờ làm vào BangChamCong.
