---
title: "Hành Trình Chinh Phục Java: Những Điều Năm 4 Mới 'Ngộ' Ra"
date: 2025-12-13
draft: false
description: "Tổng hợp những kinh nghiệm xương máu, các lỗi sai kinh điển và tư duy quan trọng khi học Java Core mà sinh viên thường bỏ qua."
# DÒNG NÀY ĐỂ HIỂN THỊ NGẮN GỌN BÊN NGOÀI:
summary: "Nếu ví Python là xe ga thì Java là xe côn tay. Bài viết này chia sẻ những kinh nghiệm 'xương máu' và tư duy quan trọng khi học Java mà mình ước được biết sớm hơn."
tags: ["Java", "Sharing", "Programming", "Sinh Viên"]
categories: ["Chia Sẻ", "Lập Trình"]
author: "Hồ Thái Phong"
---

Nếu ví Python là một chiếc xe ga êm ái, dễ đi, thì **Java** đối với mình giống như một chiếc xe côn tay phân khối lớn. Ban đầu làm quen thì cực kỳ vất vả, dễ "chết máy" (lỗi cú pháp), cồng kềnh, nhưng khi đã làm chủ được nó rồi thì bạn sẽ cảm thấy cực kỳ đầm chắc và an toàn trên những chặng đường dài.

Là một sinh viên năm 4 chuyên ngành CNTT, nhìn lại quãng đường từ lúc viết dòng `System.out.println("Hello World");` đầu tiên cho đến khi làm các dự án Spring Boot, mình muốn chia sẻ lại những "điểm chạm" kiến thức mà mình nghĩ bất cứ ai học Java cũng nên nắm chắc.

## 1. OOP không chỉ là lý thuyết đi thi

Hồi năm nhất, năm hai, mình học 4 tính chất OOP (Đóng gói, Kế thừa, Đa hình, Trừu tượng) chủ yếu để... qua môn. Mình học thuộc lòng định nghĩa nhưng không thực sự hiểu **tại sao** phải dùng nó.

Đến khi làm dự án thực tế, mình mới "thấm":
* **Encapsulation (Đóng gói):** Không phải cứ `private` biến rồi `get/set` cho vui. Nó là để bảo vệ dữ liệu, không cho bên ngoài sửa bậy bạ.
* **Polymorphism (Đa hình) & Interface:** Đây là "chân ái". Nhờ Interface, code của mình lỏng lẻo hơn (loose coupling). Ví dụ, hôm nay sếp bảo dùng Database MySQL, mai sếp thích chuyển sang PostgreSQL, nếu code chuẩn theo Interface thì việc sửa đổi cực kỳ nhẹ nhàng.

> **Lời khuyên:** Đừng chỉ code Class. Hãy tập tư duy theo Interface. "Program to an interface, not an implementation".

## 2. "Cú lừa" mang tên String

Đây là lỗi sai kinh điển mà 99% sinh viên (bao gồm cả mình ngày xưa) đều mắc phải.

### So sánh chuỗi
Trong C++, bạn có thể dùng `==` để so sánh chuỗi. Nhưng trong Java:
```java
String s1 = "Hello";
String s2 = new String("Hello");

// SAI: Kết quả là false vì nó so sánh địa chỉ ô nhớ
if (s1 == s2) { ... } 

// ĐÚNG: Kết quả là true vì nó so sánh nội dung
if (s1.equals(s2)) { ... }