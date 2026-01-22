---
url: https://spring.academy/courses/building-a-rest-api-with-spring-boot/lessons/implementing-get
title: Implementing GET - Spring Academy
created: 2026-01-22T01:47:06.711Z
updated: 2026-01-22T01:49:39.089Z
tags: []
---

# Notes
# BÀI 1: TRIỂN KHAI PHƯƠNG THỨC GET (Implementing GET)

## 🎯 MỤC TIÊU BÀI HỌC
Trong bài học này, bạn sẽ học REST là gì và cách sử dụng Spring Boot để triển khai một RESTful endpoint đơn giản.

---

## 📚 PHẦN 1: REST, CRUD VÀ HTTP

### REST là gì?

**REST** (Representational State Transfer) - Chuyển Giao Trạng Thái Đại Diện

Trong hệ thống RESTful:
- **Đối tượng dữ liệu** được gọi là **Resource Representations** (Biểu Diễn Tài Nguyên)
- **Mục đích của RESTful API**: Quản lý trạng thái (state) của các Resources này

💡 **Hiểu đơn giản:**
- "State" (trạng thái) = "Value" (giá trị)
- "Resource Representation" = "Object" (đối tượng) hoặc "Thing" (thứ gì đó)
- **REST = Cách thức quản lý giá trị của các đối tượng**

Các đối tượng này có thể:
- Được truy cập qua API
- Thường được lưu trữ trong persistent data store (kho dữ liệu lâu dài) như database

### CRUD Operations (Các Thao Tác CRUD)

**CRUD** là viết tắt của:
- **C**reate - Tạo mới
- **R**ead - Đọc/Truy vấn
- **U**pdate - Cập nhật
- **D**elete - Xóa

👉 Đây là **4 thao tác cơ bản** có thể thực hiện trên objects trong data store.

REST có hướng dẫn cụ thể để triển khai từng thao tác này.

### HTTP Protocol (Giao Thức HTTP)

**Hypertext Transfer Protocol (HTTP)** - Giao thức truyền tải siêu văn bản

**Luồng hoạt động:**
1. Caller (người gọi) gửi **Request** đến một **URI**
2. Web server nhận request và chuyển (route) đến request handler
3. Handler tạo **Response** và gửi lại cho caller

**Cấu trúc Request:**
- **Method** (còn gọi là Verb - động từ)
- **URI** (còn gọi là Endpoint - điểm cuối)
- **Body** (nội dung)

**Cấu trúc Response:**
- **Status Code** (mã trạng thái)
- **Body** (nội dung)

---

## 🔄 PHẦN 2: MAPPING CRUD VỚI HTTP METHODS

### Bảng Ánh Xạ CRUD Operations

Khi hoàn thành khóa học, API của chúng ta sẽ trông như sau:

| CRUD Operation | HTTP Method | Endpoint URI Pattern |
|----------------|-------------|---------------------|
| **CREATE** (Tạo) | POST | `/cashcards` |
| **READ** (Đọc) | GET | `/cashcards/{id}` |
| **UPDATE** (Cập nhật) | PUT | `/cashcards/{id}` |
| **DELETE** (Xóa) | DELETE | `/cashcards/{id}` |

### Chi Tiết Về Endpoints

**Endpoint URI** cho Cash Card objects bắt đầu bằng `/cashcards`

**Lưu ý quan trọng:**
- ✅ **READ, UPDATE, DELETE**: Cần cung cấp **unique identifier** (định danh duy nhất) của resource
  - Ví dụ: Để đọc Cash Card có ID "42" → endpoint: `/cashcards/42`
  
- ❌ **CREATE**: **KHÔNG** cần cung cấp identifier
  - Lý do: Thao tác CREATE sẽ tự động tạo Cash Card mới với ID duy nhất
  - Application sẽ tự tạo unique identifier cho chúng ta

### Bảng Chi Tiết RESTful CRUD Operations

| Operation | API Endpoint | HTTP Method | Response Status |
|-----------|--------------|-------------|-----------------|
| Create | `/cashcards` | POST | 201 (CREATED) |
| Read | `/cashcards/{id}` | GET | 200 (OK) |
| Update | `/cashcards/{id}` | PUT | 204 (NO CONTENT) |
| Delete | `/cashcards/{id}` | DELETE | 204 (NO CONTENT) |

### Request Body (Nội Dung Yêu Cầu)

**Khi nào cần Request Body?**
- CREATE operation: Cần data để tạo resource mới
- UPDATE operation: Cần data để cập nhật resource

**Ví dụ:**
- Cash Card mới có thể có giá trị tiền ban đầu (beginning cash value amount)
- UPDATE operation có thể thay đổi số tiền đó

---

## 💳 PHẦN 3: VÍ DỤ VỚI CASH CARD

### Ví Dụ Read Endpoint

**Kịch bản:** Đọc thông tin Cash Card có ID = 123

**REQUEST:**
```
Method: GET
URL: http://cashcard.example.com/cashcards/123
Body: (empty - để trống vì GET request không có body)
```

**RESPONSE (Thành công):**
```
Status Code: 200 (OK)
Body:
{
  "id": 123,
  "amount": 25.00
}
```

**Giải thích:**
- Response body chứa JSON representation của Resource được yêu cầu
- Status Code 200 = Thành công

---

## 🌱 PHẦN 4: REST TRONG SPRING BOOT

### Spring's IoC Container

**IoC** (Inversion of Control) - Đảo Ngược Điều Khiển

Một trong những nhiệm vụ chính của Spring:
- Cấu hình (configure) và khởi tạo (instantiate) objects
- Các objects này gọi là **Spring Beans**
- Thường được tạo bởi Spring (không dùng từ khóa `new` của Java)

### Spring Annotations và Component Scan

**Cách tạo Spring Beans:**
1. Sử dụng **Spring Annotation** trên class
2. Spring sẽ tạo instance của class đó trong **Component Scan phase** (giai đoạn quét component)
3. Diễn ra khi **application startup** (khởi động ứng dụng)
4. Bean được lưu trong **Spring's IoC container**
5. Từ đó, bean có thể được **injected** (tiêm/chèn vào) bất kỳ code nào yêu cầu nó

### Spring Web Controllers

**Controller** là nơi xử lý Requests trong Spring Web.

**Tạo REST Controller:**
```java
@RestController
class CashCardController {
}
```

👉 Chỉ cần vậy để nói với Spring: **"Tạo một REST Controller"**

**Cách hoạt động:**
- Controller được inject vào Spring Web
- Spring Web sẽ route API requests đến đúng method

### Handler Method (Phương Thức Xử Lý)

**Handler method**: Method được chỉ định để xử lý request phù hợp

**Bước 1 - Tạo method cơ bản:**
```java
private CashCard findById(Long requestedId) {
}
```

**Bước 2 - Thêm @GetMapping annotation:**
```java
@GetMapping("/cashcards/{requestedId}")
private CashCard findById(Long requestedId) {
}
```
- REST quy định Read endpoint dùng HTTP GET method
- `@GetMapping` chỉ định URI Path

**Bước 3 - Thêm @PathVariable annotation:**
```java
@GetMapping("/cashcards/{requestedId}")
private CashCard findById(@PathVariable Long requestedId) {
}
```
- `@PathVariable` giúp Spring lấy giá trị từ URI
- Parameter name `requestedId` khớp với `{requestedId}` trong URI
- Spring tự động assign giá trị đúng vào biến

**Bước 4 - Sử dụng ResponseEntity:**
```java
@RestController
class CashCardController {
  @GetMapping("/cashcards/{requestedId}")
  private ResponseEntity<CashCard> findById(@PathVariable Long requestedId) {
     CashCard cashCard = /* Code để lấy CashCard */;
     return ResponseEntity.ok(cashCard);
  }
}
```

**ResponseEntity** - Class do Spring Web cung cấp:
- Tạo Response với status code 200 (OK)
- Body chứa CashCard object
- `ResponseEntity.ok(cashCard)` là utility method tiện lợi

---

## 📖 BẢNG THUẬT NGỮ QUAN TRỌNG

| Thuật Ngữ Tiếng Việt | English Term | Giải Thích |
|----------------------|--------------|------------|
| Chuyển Giao Trạng Thái Đại Diện | REST (Representational State Transfer) | Kiến trúc API để quản lý trạng thái tài nguyên |
| Biểu Diễn Tài Nguyên | Resource Representation | Đối tượng dữ liệu trong hệ thống RESTful |
| Giao Diện Lập Trình Ứng Dụng | API (Application Programming Interface) | Cách thức các ứng dụng giao tiếp với nhau |
| Tạo-Đọc-Cập nhật-Xóa | CRUD (Create, Read, Update, Delete) | 4 thao tác cơ bản trên dữ liệu |
| Giao Thức Truyền Tải Siêu Văn Bản | HTTP (Hypertext Transfer Protocol) | Giao thức giao tiếp web |
| Yêu Cầu | Request | Lời gọi từ client đến server |
| Phản Hồi | Response | Kết quả trả về từ server cho client |
| Phương Thức | Method/Verb | Loại hành động (GET, POST, PUT, DELETE) |
| Điểm Cuối | Endpoint/URI | Địa chỉ của resource trên server |
| Mã Trạng Thái | Status Code | Số chỉ kết quả của request (200, 201, 404...) |
| Nội Dung Yêu Cầu | Request Body | Dữ liệu gửi kèm trong request |
| Nội Dung Phản Hồi | Response Body | Dữ liệu trả về trong response |
| Đảo Ngược Điều Khiển | IoC (Inversion of Control) | Container quản lý objects trong Spring |
| Spring Bean | Spring Bean | Object được quản lý bởi Spring container |
| Chú Thích | Annotation | Metadata đánh dấu class/method (@RestController) |
| Quét Component | Component Scan | Quá trình Spring tìm và tạo beans |
| Tiêm Phụ Thuộc | Dependency Injection | Spring tự động cung cấp objects cần thiết |
| Bộ Điều Khiển | Controller | Class xử lý HTTP requests |
| Biến Đường Dẫn | Path Variable | Biến lấy từ URI path ({id}) |

---

## ✅ GHI CHÚ ÔN LẠI - ĐIỂM CHÍNH

### Về REST và HTTP
✅ REST sử dụng HTTP methods để định nghĩa CRUD operations
✅ GET = Read, POST = Create, PUT = Update, DELETE = Delete
✅ Endpoint pattern: `/cashcards` cho CREATE, `/cashcards/{id}` cho READ/UPDATE/DELETE
✅ Response codes quan trọng: 200 (OK), 201 (CREATED), 204 (NO CONTENT)
✅ GET request có body rỗng, POST/PUT request có body chứa data

### Về Spring Boot
✅ `@RestController` tạo REST controller
✅ `@GetMapping("/path/{variable}")` map HTTP GET request đến method
✅ `@PathVariable` lấy giá trị từ URI path
✅ `ResponseEntity` tạo HTTP response với status code và body
✅ `ResponseEntity.ok(object)` trả về response 200 với object trong body
✅ Spring tự động tạo và quản lý beans qua IoC container

### Code Pattern Cơ Bản
```java
@RestController
class CashCardController {
  @GetMapping("/cashcards/{requestedId}")
  private ResponseEntity<CashCard> findById(@PathVariable Long requestedId) {
     // Logic lấy dữ liệu
     return ResponseEntity.ok(cashCard);
  }
}
```

---

## 🎯 BƯỚC TIẾP THEO

**Trong Lab tiếp theo, bạn sẽ:**
1. ✍️ Tự tay triển khai REST endpoint đầu tiên
2. 🧪 Test endpoint với Spring Boot
3. 💻 Viết code trong IntelliJ IDEA

**Tips để học tốt:**
- 📝 Gõ lại code thay vì copy/paste
- 🔍 Chú ý cách Spring annotations hoạt động
- 🧩 Hiểu rõ luồng: Request → Controller → Response
- 📚 Tham khảo HTTP Standard để hiểu sâu hơn

---

## 📌 TÀI LIỆU THAM KHẢO

- [HTTP Standard](https://developer.mozilla.org/en-US/docs/Web/HTTP)
- [Spring Beans Documentation](https://docs.spring.io/spring-framework/reference/core/beans.html)

---

**Progress: Lesson 1/20 (5%) ✅**
**Next: Bắt đầu Lab - Triển khai GET endpoint thực tế!**