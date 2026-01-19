---
url: https://spring.academy/courses/building-a-rest-api-with-spring-boot/lessons/data-contracts
title: API Contracts & JSON - Spring Academy
created: 2026-01-19T03:18:47.384Z
updated: 2026-01-19T03:20:22.451Z
tags: []
---

# Notes

## API CONTRACTS & JSON (HỢP ĐỒNG API & JSON)

Chúng ta đang phát triển một API. Điều này đặt ra rất nhiều câu hỏi về cách API nên hoạt động:

### Những Câu Hỏi Chính

- Làm thế nào người tiêu dùng API nên tương tác với API?
- Người tiêu dùng cần gửi dữ liệu gì trong các kịch bản khác nhau?
- API nên trả về dữ liệu gì cho người tiêu dùng và khi nào?
- API giao tiếp như thế nào khi nó bị sử dụng không chính xác (hoặc có lỗi xảy ra)?

### Giải Pháp: Hợp Đồng API

Bất cứ khi nào có thể, nhà cung cấp API và người tiêu dùng nên thảo luận các kịch bản này và đi đến thỏa thuận. Tốt hơn nữa, họ nên ghi chép những thỏa thuận này không chỉ trong một hệ thống tài liệu chung, mà còn theo cách hỗ trợ **các bài kiểm tra tự động** (passed hoặc failed) dựa trên các quyết định này.

**Đây là nơi khái niệm "contracts" (hợp đồng) xuất hiện.**

---

## HỢP ĐỒNG API (API CONTRACTS)

### Định Nghĩa

**API Contract** là một **thỏa thuận chính thức giữa nhà cung cấp phần mềm và người tiêu dùng** mà trừu tượng giao tiếp cách tương tác với nhau.

**Hợp đồng này xác định:**
- Cách nhà cung cấp API và người tiêu dùng tương tác
- Dữ liệu được trao đổi trông như thế nào
- Cách giao tiếp các trường hợp thành công và thất bại

### Ưu Điểm Quan Trọng

- Nhà cung cấp và người tiêu dùng **không cần phải dùng cùng ngôn ngữ lập trình**, chỉ cần dùng **cùng một API contract**
- Cho phép sự tương tác giữa các hệ thống khác nhau

### Ví Dụ: Family Cash Card API Contract

Đối với miền (domain) Family Cash Card, giả sử hiện tại có một hợp đồng giữa dịch vụ Cash Card và tất cả các dịch vụ sử dụng nó.

#### Đặc Tả Request
```
Request URI: /cashcards/{id}
HTTP Verb: GET
Body: None
```

#### Đặc Tả Response

**Status Codes:**
- `200 OK` - Nếu người dùng được phép truy cập và Cash Card được lấy thành công
- `401 UNAUTHORIZED` - Nếu người dùng chưa xác thực (unauthenticated) hoặc không được phép (unauthorized)
- `404 NOT FOUND` - Nếu người dùng xác thực và được phép, nhưng không tìm thấy Cash Card

**Response Body Type:** JSON

**Ví Dụ Response Body:**
```json
{
  "id": 99,
  "amount": 123.45
}
```

---

## TẠI SAO API CONTRACTS QUAN TRỌNG?

### Tác Dụng

**API Contracts** quan trọng vì chúng **giao tiếp hành vi của REST API**. Chúng cung cấp chi tiết cụ thể về:
- Dữ liệu được tuần tự hóa (serialized) hoặc giải tuần tự hóa (deserialized) cho mỗi lệnh
- Tham số (parameters) được trao đổi

### Lợi Ích

- API contracts được viết theo cách có thể dễ dàng dịch thành **chức năng nhà cung cấp và người tiêu dùng**
- Có thể được dịch thành **các bài kiểm tra tự động tương ứng** (automated tests)
- Chúng ta sẽ triển khai cả **chức năng nhà cung cấp API** và **bài kiểm tra tự động** trong các lab

---

## JSON LÀ GÌ? (WHAT IS JSON?)

### Định Nghĩa

**JSON** = **Javascript Object Notation** (Ký Hiệu Đối Tượng Javascript)

JSON cung cấp một **định dạng trao đổi dữ liệu** đại diện cho thông tin cụ thể của một đối tượng theo cách **dễ đọc và dễ hiểu**.

### Ví Dụ JSON
```json
{
  "id": 99,
  "amount": 123.45
}
```

### Các Định Dạng Khác

Các định dạng dữ liệu phổ biến khác bao gồm:
- **YAML** (Yet Another Markup Language) - Một ngôn ngữ đánh dấu khác
- **XML** (Extensible Markup Language) - Ngôn ngữ đánh dấu mở rộng

### Tại Sao JSON Tốt Hơn XML?

So với XML, JSON:
- Đọc và ghi **nhanh hơn**
- **Dễ sử dụng hơn**
- Chiếm **ít dung lượng hơn**
- Hoạt động **liền mạch với các ứng dụng dựa trên Javascript**

### Ưu Điểm của JSON

- Có thể sử dụng với **hầu hết các ngôn ngữ lập trình hiện đại**
- Hoạt động trên **tất cả các nền tảng chính**
- **JSON đã thay thế XML** làm định dạng được sử dụng rộng rãi nhất cho các API được sử dụng bởi các ứng dụng Web, bao gồm REST APIs

---

## BẢNG THUẬT NGỮ QUAN TRỌNG

| Thuật Ngữ | Tiếng Anh | Giải Thích |
|-----------|-----------|-----------|
| Hợp Đồng | Contract | Thỏa thuận, quy ước |
| API Contract | API Contract | Thỏa thuận về hành vi API |
| Nhà Cung Cấp | Provider | Bên cung cấp dịch vụ/API |
| Người Tiêu Dùng | Consumer | Bên sử dụng dịch vụ/API |
| Trao Đổi Dữ Liệu | Data Interchange | Sự trao đổi thông tin giữa các bên |
| Tuần Tự Hóa | Serialized | Chuyển đổi dữ liệu thành dạng có thể truyền tải |
| Giải Tuần Tự Hóa | Deserialized | Chuyển đổi dữ liệu nhận được trở lại dạng ban đầu |
| Kiểm Tra Tự Động | Automated Tests | Các bài kiểm tra chạy tự động |
| JSON | JSON | Javascript Object Notation - Ký hiệu đối tượng Javascript |
| YAML | YAML | Yet Another Markup Language - Một ngôn ngữ đánh dấu khác |
| XML | XML | Extensible Markup Language - Ngôn ngữ đánh dấu mở rộng |
| Request URI | Request URI | Địa chỉ của yêu cầu API |
| HTTP Verb | HTTP Verb | Phương thức HTTP (GET, POST, PUT, DELETE...) |
| Status Code | Status Code | Mã trạng thái HTTP |
| 200 OK | 200 OK | Thành công - Yêu cầu được xử lý thành công |
| 401 UNAUTHORIZED | 401 UNAUTHORIZED | Không được phép - Người dùng chưa xác thực hoặc không có quyền |
| 404 NOT FOUND | 404 NOT FOUND | Không tìm thấy - Tài nguyên không tồn tại |
| Authenticated | Xác thực | Đã xác nhận danh tính người dùng |
| Authorized | Được phép | Người dùng có quyền truy cập tài nguyên |
| Response Body | Phần thân phản hồi | Dữ liệu được trả về trong phản hồi |

---

## GHI CHÚ ÔN LẠI - ĐIỂM CHÍNH

✅ **API Contract** = Thỏa thuận giữa nhà cung cấp API và người tiêu dùng  
✅ **Importance** = Giúp giao tiếp rõ ràng, hỗ trợ automated tests  
✅ **JSON** = Định dạng trao đổi dữ liệu phổ biến nhất cho REST APIs  
✅ **HTTP Methods** = GET, POST, PUT, DELETE để thao tác tài nguyên  
✅ **Status Codes** = 200 OK, 401 UNAUTHORIZED, 404 NOT FOUND, v.v.  
✅ **No Language Requirement** = Provider và Consumer không cần cùng ngôn ngữ lập trình

---

## FAMILY CASH CARD API - QUICK REFERENCE
```
GET /cashcards/{id}

Responses:
- 200 OK: Lấy Cash Card thành công
- 401 UNAUTHORIZED: Không xác thực hoặc không được phép
- 404 NOT FOUND: Cash Card không tồn tại

Response Body:
{
  "id": 99,
  "amount": 123.45
}
```

---

## BƯỚC TIẾP THEO

🚀 Làm bài **Lab: Testing First** để bắt đầu viết các bài kiểm tra cho API!

---

## LIÊN HỆ & TÀI LIỆU

- **JSON:** https://www.json.org/
- **YAML:** https://yaml.org/
- **XML:** https://www.w3.org/XML/
- **Consumer-Driven Contracts:** Xem tài liệu chính thức Spring