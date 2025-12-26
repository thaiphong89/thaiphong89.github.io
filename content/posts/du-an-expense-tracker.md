---
title: "Project Diary: Tôi Đã Xây Dựng App Quản Lý Chi Tiêu Như Thế Nào?"
date: 2025-12-04
draft: false
description: "Hành trình xây dựng ứng dụng Expense Tracker từ ý tưởng đến thực tế, sử dụng Flutter, SQLite và tư duy phân tích dữ liệu."
# DÒNG NÀY ĐỂ HIỂN THỊ NGẮN GỌN BÊN NGOÀI:
summary: "Từ câu hỏi 'Tiền đi đâu hết rồi?', mình quyết định tự code ứng dụng quản lý chi tiêu với Flutter & SQLite. Cùng xem cách mình áp dụng tư duy Data Engineer vào dự án cá nhân này."
tags: ["Project", "Flutter", "Data Analysis", "Portfolio"]
categories: ["Dự Án", "Lập Trình"]
author: "Hồ Thái Phong"
---

Là sinh viên xa nhà, việc quản lý tài chính cá nhân luôn là một bài toán đau đầu. "Tiền đi đâu hết rồi?" là câu hỏi mình tự hỏi mỗi cuối tháng. Thay vì dùng Excel hay sổ tay, mình quyết định: **"Tại sao không tự code một cái App cho riêng mình?"**

Và thế là dự án **Expense Tracker** ra đời. Đây không chỉ là một ứng dụng ghi chép, mà là nơi mình áp dụng tư duy của một **Data Engineer** vào việc xử lý dữ liệu cá nhân.

## 1. Bài toán đặt ra

Mình cần một ứng dụng không chỉ để *nhập* số tiền, mà còn phải:
* Hoạt động Offline (không cần mạng vẫn ghi chép được).
* Trực quan hóa dữ liệu (nhìn biểu đồ là biết tháng này ăn hàng quá đà hay không).
* **Dự báo:** Cảnh báo nếu tốc độ tiêu tiền hiện tại sẽ khiến mình "viêm màng túi" trước ngày 30.

## 2. Tech Stack (Công nghệ sử dụng)

Để giải quyết bài toán trên, mình đã chọn các công nghệ sau:

* **Mobile App:** [Flutter](https://flutter.dev/) (Dart). Lý do: Code một lần chạy được cả Android lẫn iOS, UI mượt mà.
* **Database:** [SQLite](https://www.sqlite.org/). Lý do: Nhẹ, lưu trữ cục bộ (Local Storage), truy vấn SQL chuẩn chỉnh.
* **Visualization:** Chart.js & Flutter Charts.
* **Data Logic:** Python (cho phần xử lý logic dự báo và phân tích thói quen).

## 3. Những thách thức kỹ thuật

### Tối ưu luồng dữ liệu (Data Flow)
Ban đầu, mình nghĩ chỉ cần `INSERT` và `SELECT` là xong. Nhưng khi dữ liệu lên tới hàng trăm giao dịch, việc hiển thị báo cáo bị chậm.
**Giải pháp:** Mình đã học cách thực hiện **Aggregation** (tổng hợp dữ liệu) ngay trong câu truy vấn SQL thay vì lôi hết dữ liệu thô về rồi mới cộng trừ nhân chia trong code.

```sql
-- Ví dụ: Tính tổng chi tiêu theo danh mục trong tháng hiện tại
SELECT category, SUM(amount) 
FROM transactions 
WHERE strftime('%m', date) = '01' 
GROUP BY category;