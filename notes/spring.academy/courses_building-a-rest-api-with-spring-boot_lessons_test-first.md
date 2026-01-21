---
url: https://spring.academy/courses/building-a-rest-api-with-spring-boot/lessons/test-first
title: Testing First - Spring Academy
created: 2026-01-21T08:21:20.892Z
updated: 2026-01-21T08:38:42.792Z
tags: []
---

# Notes

# Testing First

## KIỂM THỬ THEO HƯỚNG PHÁT TRIỂN (Test Driven Development - TDD)

### Khái Niệm Cơ Bản
Các đội phát triển phần mềm thường viết **test suite** (bộ kiểm thử) để phòng chống **regressions** (lỗi phát sinh). Tuy nhiên, chúng ta sẽ làm khác đi:

**Chúng ta viết test trước khi viết code ứng dụng.**

Phương pháp này gọi là **Test Driven Development (TDD)** hay **Kiểm thử hướng dẫn phát triển**.

### Tại Sao Sử Dụng TDD?

✅ **Thiết kế hệ thống dựa trên mong muốn** - Bằng cách xác định hành vi mong đợi trước, chúng ta thiết kế dựa trên "hệ thống nên làm gì" chứ không phải "hệ thống hiện tại làm gì"

✅ **Hướng dẫn viết code tối thiểu** - Test hướng dẫn bạn viết đúng lượng code cần thiết để thỏa mãn yêu cầu

✅ **Bảo vệ chống lỗi** - Khi test vượt qua, bạn có:
- Code ứng dụng hoạt động (implementation)
- Khoan tránh lỗi trong tương lai (guard against errors)

---

## THÁP KIỂM THỬ (Testing Pyramid)

Các loại test có thể được viết ở các cấp độ khác nhau của hệ thống. Ở mỗi cấp độ, có sự cân bằng giữa:
- Tốc độ thực hiện (**speed**)
- Chi phí bảo trì (**maintenance cost**)
- Độ tin cậy (**confidence**)

### 1. Unit Tests (Kiểm Thử Đơn Vị)
- **Định nghĩa**: Kiểm thử một "unit" nhỏ của hệ thống, cách ly với phần còn lại
- **Đặc điểm**: Đơn giản, nhanh chóng
- **Tỉ lệ**: Phải có tỉ lệ cao trong tháp kiểm thử
- **Lợi ích**: Giúp thiết kế code **highly cohesive, loosely coupled** (gắn kết cao, lỏng lẻo)

### 2. Integration Tests (Kiểm Thử Tích Hợp)
- **Định nghĩa**: Kiểm thử một tập con của hệ thống, có thể kiểm thử nhiều units cùng lúc
- **Đặc điểm**: Phức tạp hơn, bảo trì khó hơn, chạy chậm hơn unit tests
- **Tỉ lệ**: Ít hơn unit tests

### 3. End-to-End Tests (Kiểm Thử Toàn Luồng)
- **Định nghĩa**: Kiểm thử hệ thống qua giao diện người dùng (ví dụ: web browser)
- **Đặc điểm**: Rất kỹ lưỡng nhưng chạy **rất chậm** và **dễ bị lỗi** (fragile)
- **Tỉ lệ**: Nên có số lượng nhỏ nhất

---

## VÒ XANH, XANH LÁ CÂY, TỰA LẠI (Red, Green, Refactor Loop)

**Vòng lặp TDD**: Cách duy nhất để phát triển **nhanh chóng** một cách bền vững là liên tục cải thiện code.

### 3 Giai Đoạn Của Vòng Lặp:

**1. VÒ XANH (Red) - Viết Test Thất Bại**
- Viết một test thất bại cho chức năng mong muốn
- Lý do: Chưa có implementation nên test chắc chắn thất bại

**2. XANH LÁ CÂY (Green) - Làm Test Vượt Qua**
- Thực hiện điều đơn giản nhất để làm test vượt qua
- Lý do: Không cần viết thêm code không cần thiết

**3. TỰA LẠI (Refactor) - Cải Thiện Code**
- Tìm cơ hội để:
  - Đơn giản hóa code
  - Giảm sự lặp lại (**duplication**)
  - Cải thiện code mà không thay đổi hành vi (**behavior**)
- Lý do: Test bảo vệ bạn không làm hỏng gì

**4. LẶP LẠI (Repeat)**
- Quay lại bước 1 với chức năng tiếp theo

---

## BẢNG THUẬT NGỮ QUAN TRỌNG

| Thuật Ngữ Tiếng Việt | Tiếng Anh | Giải Thích |
|-----------|-----------|-----------|
| Kiểm thử | Test | Quá trình xác minh hành vi của code |
| Bộ kiểm thử | Test Suite | Tập hợp các test |
| Lỗi phát sinh | Regression | Lỗi mới phát sinh do thay đổi code |
| Cô lập | Isolated | Tách biệt với các phần khác của hệ thống |
| Gắn kết cao | Highly Cohesive | Các phần liên quan chặt chẽ với nhau |
| Lỏng lẻo | Loosely Coupled | Các phần ít phụ thuộc lẫn nhau |
| Kỳ dị/dễ vỡ | Fragile | Code dễ bị hỏng với những thay đổi nhỏ |
| Hành vi | Behavior | Cách code hoạt động |
| Trừu tượng | Abstraction | Ẩn chi tiết phức tạp |

---

## GHI CHÚ ÔN LẠI - ĐIỂM CHÍNH

✅ **TDD** = Viết test trước, code sau

✅ **3 lợi ích chính của TDD**:
  1. Thiết kế dựa trên mong muốn, không phải hiện tại
  2. Hướng dẫn viết code tối thiểu cần thiết
  3. Bảo vệ chống lỗi trong tương lai

✅ **Tháp kiểm thử** (từ nhiều nhất đến ít nhất):
  1. Unit Tests (nhiều nhất, nhanh nhất)
  2. Integration Tests (trung bình)
  3. End-to-End Tests (ít nhất, chậm nhất)

✅ **Vòng Red-Green-Refactor**:
  - Red: Test thất bại
  - Green: Code để test vượt qua
  - Refactor: Cải thiện code
  - Repeat: Lặp lại

✅ **Lợi ích refactor**: Chỉ có thể refactor an toàn khi có test bảo vệ

---

## BỨC TIẾP THEO

📌 **Lesson tiếp theo**: Bạn sẽ thực hành viết **unit tests** dùng TDD cho **JSON contracts** mà chúng ta sẽ dùng khi phát triển **Family Cash Card REST API**

💡 **Chuẩn bị**: Sẵn sàng thực hành vòng Red-Green-Refactor throughout the course!

---

**Trang:** 1/20 lessons (5%)  
**Tiến độ khóa học:** Building a REST API with Spring Boot (Spring Academy)
