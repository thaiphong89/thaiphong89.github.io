---
title: "Java Bài 2: Biến và Các Kiểu Dữ Liệu Cơ Bản"
date: 2025-01-03T08:00:00+07:00
draft: false
summary: "Tìm hiểu về các hộp chứa dữ liệu trong Java: Biến là gì? Có những kiểu dữ liệu nào quan trọng?"
tags: ["Java", "Basics", "Variables"]
categories: ["Lập trình"]
cover:
    image: "https://images.unsplash.com/photo-1555066931-4365d14bab8c?q=80&w=2070&auto=format&fit=crop"
    alt: "Code variables on screen"
    caption: "Dữ liệu là nguyên liệu của mọi chương trình."
---

Sau khi đã chạy thành công "Hello World", bước tiếp theo là học cách lưu trữ thông tin. Trong Java, chúng ta dùng **Biến (Variables)**.

## 1. Biến là gì?

Hãy tưởng tượng biến giống như một cái hộp. Bạn đặt tên cho cái hộp đó và bỏ đồ vật (dữ liệu) vào bên trong.

Cú pháp khai báo: `Kiểu_dữ_liệu tên_biến = giá_trị;`

## 2. Các kiểu dữ liệu nguyên thủy (Primitive Types)

Java có 8 kiểu nguyên thủy, nhưng bạn chỉ cần nhớ kỹ 4 kiểu thường dùng nhất này khi mới bắt đầu:

* **int:** Số nguyên (Ví dụ: 1, 100, -5).
* **double:** Số thực/Số thập phân (Ví dụ: 3.14, 9.5).
* **boolean:** Giá trị đúng/sai (true/false).
* **char:** Một ký tự đơn lẻ (Ví dụ: 'A', 'z').

Ngoài ra, **String** (Chuỗi ký tự) là một kiểu dữ liệu đối tượng rất quan trọng dùng để lưu văn bản.

## 3. Ví dụ thực tế

```java
public class BienVaDuLieu {
    public static void main(String[] args) {
        int tuoi = 25;
        double diemTB = 8.5;
        boolean laSinhVien = true;
        String ten = "Hồ Thái Phong";

        System.out.println("Tên: " + ten);
        System.out.println("Tuổi: " + tuoi);
    }
}