---
title: "Java OOP Phần 4: Tư Duy Của Kiến Trúc Sư (Abstraction)"
date: 2025-01-14T08:00:00+07:00
draft: false
summary: "Để lái xe hơi, bạn có cần biết động cơ đốt trong hoạt động ra sao không? Không. Bạn chỉ cần biết Vô-lăng và Chân ga. Đó chính là sự Trừu tượng hóa."
tags: ["Java", "OOP", "Abstraction", "Interface"]
categories: ["Lập trình"]
cover:
    image: "https://images.unsplash.com/photo-1506784983877-45594efa4cbe?q=80&w=2068&auto=format&fit=crop"
    alt: "Abstract Building Plan"
    caption: "Tập trung vào bản thiết kế tổng thể thay vì chi tiết từng viên gạch."
---

Chúng ta đã đi đến trụ cột cuối cùng của OOP: **Tính Trừu Tượng (Abstraction)**. Nếu 3 tính chất trước tập trung vào việc viết code (implementation), thì Trừu tượng tập trung vào tư duy thiết kế (design).

Trong thực tế, khi sếp giao cho bạn nhiệm vụ: "Hãy viết phần mềm quản lý các hình học". Bạn biết chắc chắn mọi hình học đều phải tính được diện tích. Nhưng tính thế nào? Hình tròn công thức khác, hình chữ nhật công thức khác. Lúc này, bạn chưa thể viết code chi tiết ngay được.

Thay vào đó, bạn tạo ra một khái niệm trừu tượng: "Tôi quy định rằng, bất cứ cái gì muốn được gọi là `HinhHoc` thì bắt buộc phải có chức năng `tinhDienTich`". Còn tính như thế nào thì để các class con tự lo.

Java cung cấp 2 công cụ tuyệt vời cho việc này: **Abstract Class** và **Interface**.

Ví dụ về Interface - Bản hợp đồng giữa các lập trình viên:

```java
// Đây là một "Bản hợp đồng" (Interface)
// Nó không chứa code xử lý, chỉ chứa các quy định
interface IThanhToan {
    void thanhToan(double soTien);
    void hoanTien();
}

// Class Ví Điện Tử ký hợp đồng này, nên BẮT BUỘC phải thực hiện các điều khoản
class ViMomo implements IThanhToan {
    @Override
    public void thanhToan(double soTien) {
        System.out.println("Đang kết nối server Momo... Trừ " + soTien + "đ");
    }

    @Override
    public void hoanTien() {
        System.out.println("Momo đang xử lý hoàn tiền...");
    }
}

// Class Thẻ Tín Dụng cũng ký hợp đồng, nhưng cách làm việc thì khác
class TheVisa implements IThanhToan {
    @Override
    public void thanhToan(double soTien) {
        System.out.println("Quẹt thẻ Visa... Trừ " + soTien + "đ");
    }
    // ... phải viết tiếp hàm hoanTien() nếu không sẽ báo lỗi
    public void hoanTien() { /*...*/ }
}

```
Nhờ tính trừu tượng, người quản lý dự án có thể thiết kế toàn bộ hệ thống bằng các Interface mà không cần quan tâm chi tiết bên trong. Điều này giúp tách biệt giữa "Việc cần làm" (What) và "Cách làm việc đó" (How), giúp code trở nên lỏng lẻo (loose coupling) và dễ bảo trì hơn rất nhiều.



Hy vọng qua series 4 bài viết này, các bạn đã có cái nhìn thấu đáo hơn về OOP trong Java. Nó không chỉ là những dòng code, mà là cả một tư duy để mô hình hóa thế giới thực vào máy tính. Hẹn gặp lại các bạn trong những bài chia sẻ nâng cao hơn nhé!