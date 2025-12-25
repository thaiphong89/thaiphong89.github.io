---
title: "Java Bài 4: Vòng Lặp For và While"
date: 2025-01-05T08:00:00+07:00
draft: false
summary: "Đừng lặp lại code thủ công! Hãy để máy tính làm việc nặng nhọc với vòng lặp For và While."
tags: ["Java", "Loops", "Basics"]
categories: ["Lập trình"]
cover:
    image: "https://images.unsplash.com/photo-1550751827-4bd374c3f58b?q=80&w=2070&auto=format&fit=crop"
    alt: "Spiral staircase"
    caption: "Lặp lại cho đến khi hoàn thành nhiệm vụ."
---

Giả sử bạn cần in ra dòng chữ "Tôi yêu Java" 100 lần. Bạn sẽ không muốn copy-paste câu lệnh in 100 lần đâu đúng không? Đó là lúc **Vòng lặp** tỏa sáng.

## 1. Vòng lặp For

Dùng khi bạn biết trước số lần cần lặp.

```java
// In các số từ 1 đến 5
for (int i = 1; i <= 5; i++) {
    System.out.println("Số đếm: " + i);
}