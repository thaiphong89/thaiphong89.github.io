---
title: "Làm quen với Java: Hướng dẫn cho người mới bắt đầu"
date: 2025-12-02T08:00:00+07:00
draft: false
summary: "Khám phá ngôn ngữ lập trình Java - 'Viết một lần, chạy mọi nơi'. Bài viết này sẽ giúp bạn hiểu cú pháp cơ bản và viết chương trình đầu tiên."
tags: ["Java", "Programming", "Tutorial"]
categories: ["Lập trình"]
cover:
    image: "https://images.unsplash.com/photo-1517694712202-14dd9538aa97?q=80&w=2070&auto=format&fit=crop"
    alt: "Laptop displaying code"
    caption: "Java là nền tảng của hàng tỷ thiết bị trên toàn thế giới."
---

Chào mừng các bạn! Nếu bạn đang muốn bước chân vào thế giới lập trình Backend mạnh mẽ hay phát triển ứng dụng Android, **Java** chính là cánh cửa đầu tiên bạn cần mở khóa.

Trong bài viết này, chúng ta sẽ cùng nhau tìm hiểu những khái niệm cơ bản nhất của Java nhé.

## 1. Tại sao lại là Java? ☕

Java là một ngôn ngữ lập trình hướng đối tượng (OOP), nổi tiếng với triết lý: **"Write Once, Run Anywhere"** (Viết một lần, chạy mọi nơi). Điều này có nghĩa là code bạn viết trên Windows có thể chạy mượt mà trên MacOS hay Linux mà không cần sửa đổi gì.

* **Phổ biến:** Được sử dụng bởi Google, Amazon, Netflix...
* **Mạnh mẽ:** Quản lý bộ nhớ tự động, đa luồng.
* **Cộng đồng lớn:** Dễ dàng tìm kiếm tài liệu và hỗ trợ.

## 2. Chương trình "Hello World" đầu tiên

Mọi hành trình lập trình đều bắt đầu từ việc in ra dòng chữ "Hello World". Hãy xem cấu trúc của một file Java cơ bản:

```java
public class HelloWorld {
    public static void main(String[] args) {
        // Đây là nơi chương trình bắt đầu chạy
        System.out.println("Xin chào, Hồ Thái Phong!");
    }
}