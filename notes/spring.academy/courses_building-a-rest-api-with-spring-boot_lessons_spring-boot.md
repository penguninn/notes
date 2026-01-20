---
url: https://spring.academy/courses/building-a-rest-api-with-spring-boot/lessons/spring-boot
title: API Contracts & JSON - Spring Academy
created: 2026-01-20T05:26:46.509Z
updated: 2026-01-20T07:33:23.853Z
tags: []
---

# Notes

# SPRING VÀ SPRING BOOT

## Spring và Spring Boot

Spring và Spring Boot đều là các framework Java được sử dụng để xây dựng ứng dụng. Hãy coi chúng như những bộ công cụ giúp các nhà phát triển xây dựng và tổ chức code của họ một cách hiệu quả và có thể mở rộng.

---

## Spring (Framework Spring)

Spring là một framework toàn diện cung cấp nhiều module khác nhau để xây dựng các loại ứng dụng khác nhau. Nó giống như một hộp công cụ khổng lồ với mọi công cụ bạn có thể cần để xây dựng bất cứ thứ gì.

### Các Module Chính của Spring

- **Spring MVC** - Để xây dựng ứng dụng web
- **Spring Data** - Để truy cập dữ liệu (database)
- **Spring Security** - Để xác thực (authentication) và phân quyền (authorization)

### Nhược Điểm

Khó khăn trong thiết lập. Bạn phải cấu hình (configuration) rất nhiều, chỉnh sửa các thành phần khác nhau của framework để có thể chạy được một ứng dụng.

---

## Spring Boot

May mắn thay, Spring Boot làm cho việc làm việc với Spring đơn giản hơn nhiều. Spring Boot giống như một phiên bản "có ý kiến" hơn của Spring.

### Đặc Điểm của Spring Boot

- Đã có nhiều thiết lập sẵn (pre-configured settings) và thư viện phụ thuộc (dependencies) được sử dụng phổ biến trong các ứng dụng Spring
- Rất dễ để bắt đầu nhanh chóng mà không phải lo lắng về việc thiết lập mọi thứ từ đầu
- Đi kèm với một **máy chủ web tích hợp (embedded web server)**, vì vậy bạn có thể dễ dàng tạo và triển khai các ứng dụng web mà không cần máy chủ bên ngoài

### Tóm Tắt

- **Spring** = Framework mạnh, linh hoạt, nhưng phức tạp khi thiết lập
- **Spring Boot** = Phiên bản streamlined (tối ưu) của Spring, dễ bắt đầu, có nhiều tính năng tích hợp sẵn

---

## Bộ Chứa IoC (Inversion of Control) của Spring

Spring Boot tận dụng **Bộ chứa Inversion of Control (IoC)** của Spring Core. Bạn sẽ sử dụng tính năng này rất nhiều khi xây dựng ứng dụng Family Cash Card.

### IoC là Gì?

IoC cho phép bạn **cấu hình cách và thời điểm các thư viện phụ thuộc (dependencies) được cung cấp cho ứng dụng của bạn tại thời gian chạy (runtime)**.

### Ví Dụ Thực Tế

Giả sử bạn muốn sử dụng một **cơ sở dữ liệu khác nhau**:
- Cơ sở dữ liệu này cho **phát triển cục bộ (local development)**
- Cơ sở dữ liệu khác cho **ứng dụng trực tiếp (live, public-facing application)**

**Vấn đề nếu không có IoC:** Bạn phải viết code cứng (hard-code) mọi trường hợp có thể vào logic ứng dụng của mình.

**Giải pháp với IoC:** Spring Boot cho phép bạn cung cấp một **cấu hình bên ngoài (external configuration)** mà chỉ định cách và thời điểm các thư viện phụ thuộc như vậy được sử dụng. Code ứng dụng của bạn không cần biết sự khác biệt này.

### Dependency Injection (DI) vs Inversion of Control (IoC)

- **Inversion of Control** thường được gọi là **Dependency Injection (DI)**, nhưng về mặt kỹ thuật, không hoàn toàn chính xác
- **Dependency Injection** và các framework đi kèm chỉ là **một cách để đạt được Inversion of Control**
- Các nhà phát triển Spring thường nói rằng các dependencies được "tiêm vào (injected)" ứng dụng của họ tại runtime

**Ghi chú quan trọng:** Nhiều ngôn ngữ lập trình và framework khác cũng có IoC, nhưng chúng không nhất thiết gọi nó là "Dependency Injection". Tuy nhiên, trong cộng đồng Spring, bạn sẽ thường nghe hai thuật ngữ này được sử dụng thay thế cho nhau.

---

## Spring Initializr

### Spring Initializr là Gì?

Khi bắt đầu một ứng dụng Spring Boot mới, **Spring Initializr** là bước được khuyến nghị đầu tiên.

Bạn có thể coi **Spring Initializr** giống như một **giỏ hàng mua sắm (shopping cart)** cho tất cả các thư viện phụ thuộc mà ứng dụng của bạn có thể cần.

### Tác Dụng

- Nhanh chóng và dễ dàng **tạo ra một ứng dụng Spring Boot hoàn chỉnh, sẵn sàng chạy**

### Quy Trình Chung của Spring Initializr

1. Điền thông tin siêu dữ liệu (metadata)
2. Thêm các thư viện phụ thuộc (dependencies) phù hợp
3. Tạo dự án (generate project) của bạn

### Lưu Ý

Trong khóa học này, chúng tôi sẽ cung cấp tất cả các hướng dẫn này cho bạn. Trong phần còn lại của khóa học, chúng ta sẽ thêm vào ứng dụng Spring Boot được tạo bởi Initializr.

---

## BẢNG THUẬT NGỮ QUAN TRỌNG

| Thuật Ngữ | Tiếng Anh | Giải Thích |
|-----------|-----------|-----------|
| Framework | Framework | Bộ framework - bộ công cụ/thư viện tích hợp |
| Toolkit | Toolkit | Bộ công cụ |
| Module | Module | Thành phần, mô-đun |
| Configuration | Cấu hình | Thiết lập, tùy chỉnh |
| Dependency | Thư viện phụ thuộc | Các thư viện mà code bạn cần dùng |
| IoC Container | Bộ chứa IoC | Hệ thống quản lý dependencies |
| Inversion of Control | Đảo ngược điều khiển | Cách quản lý dependencies |
| Dependency Injection | Tiêm thư viện phụ thuộc | Cách cung cấp dependencies |
| Runtime | Thời gian chạy | Khi ứng dụng đang chạy |
| Embedded Web Server | Máy chủ web tích hợp | Web server nằm trong ứng dụng |
| Pre-configured | Đã cấu hình sẵn | Thiết lập trước đó |
| Metadata | Siêu dữ liệu | Dữ liệu về dữ liệu |
| Hard-code | Code cứng | Viết giá trị trực tiếp vào code |
| External Configuration | Cấu hình bên ngoài | Tệp config riêng biệt |

---

## GHI CHÚ ÔN LẠI - ĐIỂM CHÍNH

✅ **Spring** = Flexible nhưng cần config nhiều  
✅ **Spring Boot** = Đã config sẵn, dễ dùng  
✅ **IoC Container** = Quản lý dependencies tự động  
✅ **Dependency Injection** = Cung cấp dependencies tự động khi chạy  
✅ **Spring Initializr** = Tool tạo project Spring Boot nhanh chóng  
✅ **Embedded Web Server** = Không cần máy chủ riêng biệt

---
