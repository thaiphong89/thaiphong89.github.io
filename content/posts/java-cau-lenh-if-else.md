---
title: "Java Phần 3: Câu Lệnh Điều Kiện If-Else"
date: 2025-12-03T08:00:00+07:00
draft: false
summary: "Làm sao để chương trình thông minh hơn? Hãy dạy nó cách đưa ra quyết định dựa trên các điều kiện."
tags: ["Java", "Logic", "Control Flow"]
categories: ["Lập trình"]
cover:
    image: "https://images.unsplash.com/photo-1504868584819-f8e8b4b6d7e3?q=80&w=2076&auto=format&fit=crop"
    alt: "Fork in the road sign"
    caption: "Nếu đúng thì rẽ trái, nếu sai thì rẽ phải."
---

Cuộc sống luôn tràn ngập những lựa chọn: "Nếu trời mưa, tôi sẽ ở nhà. Ngược lại, tôi sẽ đi chơi". Trong Java, chúng ta thể hiện tư duy này qua câu lệnh **if-else**.

## 1. Cấu trúc If-Else

```java
if (điều_kiện) {
    // Thực hiện nếu điều kiện ĐÚNG (true)
} else {
    // Thực hiện nếu điều kiện SAI (false)
}
public class KiemTraDauRot {
    public static void main(String[] args) {
        double diemThi = 4.5;

        if (diemThi >= 5.0) {
            System.out.println("Chúc mừng! Bạn đã đậu.");
        } else {
            System.out.println("Rất tiếc, bạn cần thi lại.");
        }
    }
}