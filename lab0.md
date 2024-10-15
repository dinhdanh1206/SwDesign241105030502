# Lab0 - Kết quả bài thực hành

## 1. Nội dung thực hành
- Một số biểu đồ đơn giản (lớp, ca sử dụng, gói, ...) biểu diễn trong PlantText
- Hiểu cú pháp cơ bản của Markdown.

### 2. Biểu đồ lớp (Class Diagram) – Hệ thống Quản Lý Sinh Viên
- Biểu đồ lớp (Class Diagram) mô tả các đối tượng chính trong hệ thống và mối quan hệ giữa chúng.

  ![Diagram](https://www.planttext.com/api/plantuml/png/R90z2i9048NxFSMmLHHIs6uXWXQ2POBzaYpPmMGMp2g8M5bOvmnUGEiW5WRlaHDu1HFpWqNAUJFlcpVpoP-prCgjtIKn2sAPfk0XwJKgWYC3W4HwQm58jYwqyHK9yEmMAQe5bKYC_uLGKhGwhBIHInCu8m5xWo4xiPRTDZfqM_u3hA81DJK-qbnZawJ7BNxR1e8EeYcIXyOXAgTLDQS_bayukEuK-9XtM07SwZA_1w2np2_4MHT_UBZ8thSolmPGPCMP8jYy7fpD58NLRvtH5m00__y30000)

- Các lớp chính:
  - SinhVien: Quản lý thông tin sinh viên, cho phép đăng ký khóa học.
  - KhoaHoc: Lưu thông tin khóa học (mã, tên, số tín chỉ, học kỳ).
  - DangKy: Lưu thông tin đăng ký khóa học của sinh viên.

#### 2.1. Biểu đồ ca sử dụng (Use Case Diagram) – Hệ thống Quản Lý Sinh Viên
- Biểu đồ ca sử dụng (Use Case Diagram)

  ![Use Case Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bTYSab-aK9mPbv6M6Pg7fGRM9gO5rAK2HRXWiafwDefQ1oPSAGvBrqX-_1UXUoCmviJ5J8UxkvDraHL596Qgt1aOkR3tSsvcbn8PYdeWcG3In_kMfoda0CqeXYeIw4iy_2gFFpgKAnoICrB0RcS2m000F__0m00)
- Mô tả
  - Sinh viên:
     - Đăng ký tài khoản và đăng nhập.
     - Đăng ký khóa học và xem điểm.
     - Quản trị viên:
     - Đăng nhập.
     - Quản lý thông tin sinh viên và khóa học.
#### 2.2.Biểu đồ gói (Package Diagram) – Hệ thống Quản Lý Sinh Viên
- Biểu đồ gói (Package Diagram)

  ![Use Case Diagram](https://www.planttext.com/api/plantuml/png/b90n2i9G38RtdY9qxmKwYAA3u2Gjxg5zl1VQfjA-3Y9EpWuUmCaB24vQnA7YFNe2hs2nLYteO213FiZ_vyyjFtTJZOdEej2OeXUW562Ei_AuPGYB4x2yxifyG-0N1vOcp0q0ByGq1OTOJKZm0rKLeJEnWLZNeufTmJOuEY6MDH8HKlY15bM_vCOPifjGMx7dHyJ_YYwChqa2LUmHL9cllCyO8nNZCFRUda_GTj62l_8qTedxYfeRMv46o78q-_6V7qOiSLRlsTM-5asYrxSjgzC8ss1UrfSbImYAasdS0G00__y30000)
- Mô tả
    - Gói Quản lý người dùng: Quản lý sinh viên và quản trị viên.
    - Gói Quản lý khóa học: Chứa thông tin khóa học và đăng ký của sinh viên.
    - Các gói tương tác với nhau để đảm bảo quy trình quản lý đồng bộ và chính xác.

