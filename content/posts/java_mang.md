---
title: "Java Bài 5: Mảng (Arrays) - Quản Lý Danh Sách"
date: 2025-01-06T08:00:00+07:00
draft: false
summary: "Làm thế nào để lưu điểm số của 100 sinh viên mà không cần khai báo 100 biến? Mảng chính là câu trả lời."
tags: ["Java", "Arrays", "Data Structure"]
categories: ["Lập trình"]
cover:
    image: "https://images.unsplash.com/photo-1544383835-bda2bc66a55d?q=80&w=2021&auto=format&fit=crop"
    alt: "Lockers in a row"
    caption: "Mảng giống như một dãy tủ locker được đánh số."
---

Đến lúc này, nếu muốn lưu tên của 3 người bạn, chúng ta phải khai báo 3 biến String. Nhưng nếu là 100 người thì sao? **Mảng (Array)** cho phép bạn lưu nhiều giá trị cùng kiểu trong một biến duy nhất.

## 1. Khai báo và Khởi tạo Mảng

```java
// Cách 1: Khai báo rồi gán giá trị sau
int[] diemSo = new int[5]; // Mảng chứa được 5 số nguyên

// Cách 2: Khai báo và gán giá trị luôn
String[] cars = {"Honda", "Toyota", "Ford", "BMW"};
Lưu ý quan trọng: Trong Java, chỉ số (index) bắt đầu từ 0.
public class MangCoBan {
    public static void main(String[] args) {
        String[] cars = {"Honda", "Toyota", "Ford"};
        
        // Lấy phần tử đầu tiên
        System.out.println(cars[0]); // In ra: Honda
        
        // Thay đổi giá trị
        cars[0] = "VinFast";
        System.out.println(cars[0]); // In ra: VinFast
    }
}