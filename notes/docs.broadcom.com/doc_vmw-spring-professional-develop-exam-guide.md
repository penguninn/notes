---
url: https://docs.broadcom.com/doc/vmw-spring-professional-develop-exam-guide
title: VMware Spring Professional Develop - Exam Guide
created: 2026-01-27T16:56:56.934Z
updated: 2026-01-27T16:57:07.578Z
tags: []
---

# Notes

# DATASHEET | 1

## HƯỚNG DẪN KỲ THI
**Spring Professional Develop**

### Chi tiết Kỳ thi (Cập nhật lần cuối: 26/01/2024)

Kỳ thi Spring Professional Develop (2V0-72.22), dẫn đến chứng chỉ Spring Certified Professional 2024, là kỳ thi gồm 60 câu hỏi, với điểm đạt là 300 theo phương pháp thang điểm chuẩn hóa. Thí sinh có 130 phút để hoàn thành kỳ thi, bao gồm thời gian phù hợp cho những người không phải là người bản ngữ tiếng Anh.

### Hình thức Thi

Đây là kỳ thi có giám sát được thực hiện thông qua Pearson VUE. Để biết thêm thông tin, vui lòng truy cập trang web Pearson VUE.

### Thông tin Chứng chỉ

Để biết chi tiết và danh sách đầy đủ các yêu cầu và khuyến nghị để đạt được chứng chỉ, vui lòng tham khảo trang web VMware Education Services – Certification.

### Thí sinh Đạt Chuẩn Tối thiểu

Thí sinh Đạt Chuẩn Tối thiểu (MQC - Minimally Qualified Candidate) được khuyến nghị có ít nhất 6 đến 12 tháng kinh nghiệm. MQC có cả hiểu biết khái niệm vững chắc và kinh nghiệm lập trình sử dụng Spring framework. MQC hiểu các tính năng chính của Spring và Spring Boot, bao gồm cấu hình (configuration), truy cập dữ liệu (data access), REST, AOP, auto-configuration, actuator, bảo mật (security), và Spring testing framework để xây dựng các ứng dụng doanh nghiệp và microservices.

---

## Các Phần của Kỳ thi

### Các Phần Bao gồm trong Kỳ thi này

#### Phần 1 – Spring Core

##### Mục tiêu 1.1 Giới thiệu Spring Framework

##### Mục tiêu 1.2 Java Configuration
- 1.2.1 Định nghĩa Spring Beans sử dụng mã Java
- 1.2.2 Truy cập Beans trong Application Context
- 1.2.3 Xử lý nhiều tệp Configuration
- 1.2.4 Xử lý Dependencies (phụ thuộc) giữa các Beans
- 1.2.5 Giải thích và định nghĩa Bean Scopes (phạm vi Bean)

##### Mục tiêu 1.3 Properties và Profiles
- 1.3.1 Sử dụng External Properties (thuộc tính bên ngoài) để kiểm soát Configuration
- 1.3.2 Trình bày mục đích của Profiles
- 1.3.3 Sử dụng Spring Expression Language (SpEL)

##### Mục tiêu 1.4 Annotation-Based Configuration và Component Scanning
- 1.4.1 Giải thích và sử dụng Annotation-based Configuration (cấu hình dựa trên annotation)
- 1.4.2 Thảo luận về Best Practices (thực hành tốt nhất) cho các lựa chọn Configuration
- 1.4.3 Sử dụng @PostConstruct và @PreDestroy
- 1.4.4 Giải thích và sử dụng "Stereotype" Annotations

##### Mục tiêu 1.5 Spring Bean Lifecycle (Vòng đời Spring Bean)
- 1.5.1 Giải thích Spring Bean Lifecycle
- 1.5.2 Sử dụng BeanFactoryPostProcessor và BeanPostProcessor
- 1.5.3 Giải thích cách Spring proxies thêm hành vi tại runtime
- 1.5.4 Mô tả cách Spring xác định thứ tự tạo bean
- 1.5.5 Tránh các vấn đề khi Inject beans theo kiểu (by type)

##### Mục tiêu 1.6 Aspect Oriented Programming (AOP - Lập trình hướng khía cạnh)
- 1.6.1 Giải thích các khái niệm đằng sau AOP và các vấn đề mà nó giải quyết
- 1.6.2 Triển khai và deploy Advices sử dụng Spring AOP
- 1.6.3 Sử dụng AOP Pointcut Expressions
- 1.6.4 Giải thích các loại Advice khác nhau và khi nào sử dụng chúng

---

#### Phần 2 – Data Management (Quản lý Dữ liệu)

##### Mục tiêu 2.1 Giới thiệu Spring JDBC
- 2.1.1 Sử dụng và cấu hình JdbcTemplate của Spring
- 2.1.2 Thực thi queries (truy vấn) sử dụng callbacks để xử lý result sets
- 2.1.3 Xử lý data access exceptions (ngoại lệ truy cập dữ liệu)

##### Mục tiêu 2.2 Transaction Management (Quản lý Giao dịch) với Spring
- 2.2.1 Mô tả và sử dụng Spring Transaction Management
- 2.2.2 Cấu hình Transaction Propagation (lan truyền giao dịch)
- 2.2.3 Thiết lập Rollback rules (quy tắc hoàn tác)
- 2.2.4 Sử dụng Transactions trong Tests

##### Mục tiêu 2.3 Spring Boot và Spring Data cho Backing Stores
- 2.3.1 Triển khai ứng dụng Spring JPA sử dụng Spring Boot
- 2.3.2 Tạo Spring Data Repositories cho JPA

---

#### Phần 3 – Spring MVC

##### Mục tiêu 3.1 Web Applications với Spring Boot
- 3.1.1 Giải thích cách tạo ứng dụng Spring MVC sử dụng Spring Boot
- 3.1.2 Mô tả vòng đời xử lý request cơ bản cho REST requests
- 3.1.3 Tạo RESTful controller đơn giản để xử lý GET requests
- 3.1.4 Cấu hình cho deployment (triển khai)

##### Mục tiêu 3.2 REST Applications
- 3.2.1 Tạo controllers để hỗ trợ các REST endpoints cho nhiều verbs (phương thức HTTP)
- 3.2.2 Sử dụng RestTemplate để gọi RESTful services

---

#### Phần 4 – Testing (Kiểm thử)

##### Mục tiêu 4.1 Testing Spring Applications
- 4.1.1 Viết tests sử dụng JUnit 5
- 4.1.2 Viết Integration Tests (kiểm thử tích hợp) sử dụng Spring
- 4.1.3 Cấu hình Tests sử dụng Spring Profiles
- 4.1.4 Mở rộng Spring Tests để làm việc với Databases

##### Mục tiêu 4.2 Advanced Testing với Spring Boot và MockMVC
- 4.2.1 Bật Spring Boot testing
- 4.2.2 Thực hiện integration testing
- 4.2.3 Thực hiện MockMVC testing
- 4.2.4 Thực hiện slice testing (kiểm thử từng lớp)

---

#### Phần 5 – Security (Bảo mật)

- **Mục tiêu 5.1** Giải thích các khái niệm bảo mật cơ bản
- **Mục tiêu 5.2** Sử dụng Spring Security để cấu hình Authentication (xác thực) và Authorization (phân quyền)
- **Mục tiêu 5.3** Định nghĩa Method-level Security (bảo mật cấp phương thức)

---

#### Phần 6 – Spring Boot

##### Mục tiêu 6.1 Giới thiệu Tính năng Spring Boot
- 6.1.1 Giải thích và sử dụng các tính năng Spring Boot
- 6.1.2 Mô tả quản lý dependencies của Spring Boot

##### Mục tiêu 6.2 Spring Boot Properties và Autoconfiguration
- 6.2.1 Mô tả các tùy chọn để định nghĩa và tải properties
- 6.2.2 Sử dụng auto-configuration (tự động cấu hình)
- 6.2.3 Ghi đè cấu hình mặc định

##### Mục tiêu 6.3 Spring Boot Actuator
- 6.3.1 Cấu hình Actuator endpoints
- 6.3.2 Bảo mật Actuator HTTP endpoints
- 6.3.3 Định nghĩa custom metrics (số liệu tùy chỉnh)
- 6.3.4 Định nghĩa custom health indicators (chỉ báo sức khỏe tùy chỉnh)

---

## Khóa học/Tài liệu Đào tạo Được Khuyến nghị

### Các khóa học được VMware sử dụng để phát triển kỳ thi này và được khuyến nghị mạnh mẽ cho bạn để chuẩn bị thi:

- Spring Framework Essentials
- Spring Boot
- Learning Path: Spring Certified Professional
- Spring: Core Training (Đã ngừng)

### Các khóa học mà VMware chấp nhận đáp ứng yêu cầu khóa đào tạo (Danh sách bao gồm các khóa học được sử dụng để phát triển kỳ thi này):

- Learning Path: Spring Certified Professional
- Spring: Core Training (Đã ngừng nhưng vẫn đủ điều kiện)

---

## Chứng chỉ Liên quan

**Spring Certified Professional 2024**

---

## Tài liệu Tham khảo*

Ngoài các khóa học được khuyến nghị, những người ra đề sử dụng các tài liệu tham khảo sau đây khi viết câu hỏi thi. Bạn nên nghiên cứu nội dung tham khảo khi chuẩn bị làm bài thi, ngoài bất kỳ khóa đào tạo được khuyến nghị nào.

| Tên | Phiên bản |
|-----|-----------|
| Spring Framework Documentation | Spring Framework 5.3 |
| Spring Framework Core Technologies | Spring Framework 5.3 |
| Spring Framework Data Access | Spring Framework 5.3 |
| Spring Framework Testing | Spring Framework 5.3 |
| Spring Framework MVC | Spring Framework 5.3 |
| Spring Security | Spring Framework 5.3 |
| Spring Data JPA | Spring Data 2021.0 |
| Using Spring Boot | Spring Boot 2.5 |
| Spring Boot Features | Spring Boot 2.5 |
| Spring Boot Actuator | Spring Boot 2.5 |
| Spring Boot Build Tools Plugins | Spring Boot 2.5 |

---

## Người Đóng góp Nội dung Kỳ thi

- Art Fewell
- Sergi Almar
- Bill Kable
- Candice Estrada
- Jason Hoong Kit Lee
- Sam Sanders
- Patrick Baumgartner
- Chinmay Inamdar

---

## Thông tin Pháp lý

VMware, LLC. 3401 Hillview Avenue Palo Alto CA 94304 USA  
Tel: 877-486-9273 | Fax: 650-427-5001 | www.vmware.com

© 2024 VMware, LLC. Bảo lưu mọi quyền.

Sản phẩm hoặc tài liệu workshop được bảo vệ bởi luật bản quyền và sở hữu trí tuệ của Hoa Kỳ và quốc tế. Các sản phẩm VMware được bảo vệ bởi một hoặc nhiều bằng sáng chế được liệt kê tại http://www.vmware.com/download/patents.html. VMware là nhãn hiệu đã đăng ký hoặc nhãn hiệu của VMware, LLC. tại Hoa Kỳ và/hoặc các khu vực pháp lý khác. Tất cả các nhãn hiệu và tên khác được đề cập ở đây có thể là nhãn hiệu của các công ty tương ứng.

VMware đảm bảo rằng công ty sẽ thực hiện các dịch vụ workshop này một cách hợp lý sử dụng các tiêu chuẩn và thực hành được chấp nhận rộng rãi trong ngành. BẢO HÀNH RÕ RÀNG ĐÃ NÊU LÀ THAY THẾ CHO TẤT CẢ CÁC BẢO HÀNH KHÁC, RÕ RÀNG, NGỤ Ý, THEO LUẬT ĐỊNH HOẶC CÁCH KHÁC BAO GỒM BẢO HÀNH NGỤ Ý VỀ KHẢ NĂNG BÁN ĐƯỢC HOẶC TÍNH PHÙ HỢP CHO MỤC ĐÍCH CỤ THỂ ĐỐI VỚI CÁC DỊCH VỤ VÀ SẢN PHẨM GIAO HÀNG DO VMWARE CUNG CẤP, HOẶC KẾT QUẢ CÓ THỂ ĐẠT ĐƯỢC TỪ ĐÓ. VMWARE SẼ KHÔNG CHỊU TRÁCH NHIỆM ĐỐI VỚI BẤT KỲ DỊCH VỤ HOẶC SẢN PHẨM CỦA BÊN THỨ BA ĐƯỢC XÁC ĐỊNH HOẶC GIỚI THIỆU CHO KHÁCH HÀNG.

Tất cả tài liệu được cung cấp trong workshop này đều có bản quyền của VMware ("Tài liệu Workshop"). VMware cấp cho khách hàng của workshop này giấy phép sử dụng và tạo các bản sao hợp lý của bất kỳ Tài liệu Workshop nào chỉ cho mục đích tạo điều kiện thuận lợi cho việc hiểu biết, sử dụng và vận hành nội bộ của công ty đó đối với (các) sản phẩm VMware được cấp phép. Ngoại trừ được nêu rõ ràng trong câu trên, không có sự chuyển giao bất kỳ quyền sở hữu trí tuệ nào hoặc bất kỳ giấy phép nào khác được cấp theo các điều khoản của workshop này.

Nếu bạn ở Hoa Kỳ, đơn vị ký hợp đồng VMware cho dịch vụ sẽ là VMware, LLC., và nếu ở ngoài Hoa Kỳ, đơn vị ký hợp đồng VMware sẽ là VMware International Limited.

**REV. 1/24**