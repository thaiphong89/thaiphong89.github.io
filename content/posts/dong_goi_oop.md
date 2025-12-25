---
title: "Java OOP Phần 1: Tại Sao Phải 'Giấu' Dữ Liệu? (Encapsulation)"
date: 2025-01-11T08:00:00+07:00
draft: false
summary: "Bạn có dám để ví tiền của mình giữa đường cho ai cũng có thể lấy? Nếu câu trả lời là không, thì bạn đã hiểu về tính Đóng gói trong lập trình rồi đấy."
tags: ["Java", "OOP", "Encapsulation", "Security"]
categories: ["Lập trình"]
cover:
    image: "https://images.unsplash.com/photo-1563013544-824ae1b704d3?q=80&w=2070&auto=format&fit=crop"
    alt: "Secure Vault"
    caption: "Dữ liệu quan trọng cần được bảo vệ sau những lớp khóa an toàn."
---

Chào các bạn,

Khi mới bắt đầu học lập trình, mình thường có thói quen khai báo mọi biến là `public`. Lý do rất đơn giản: "Để public cho tiện, muốn gọi ở đâu cũng được, đỡ phải viết hàm lấy dữ liệu rườm rà". Nhưng khi dự án lớn lên, mình mới nhận ra đó là một "thảm họa".

Hãy tưởng tượng bạn đang xây dựng một ứng dụng ngân hàng giống như ví dụ `TaiKhoanNganHang` mà chúng ta từng thấy. Nếu bạn để số dư tài khoản là `public`, bất kỳ đoạn code nào, hay bất kỳ lập trình viên nào trong team cũng có thể vô tình gán: `taiKhoan.soDu = -1000000;`. Điều này thật vô lý và nguy hiểm!

Đây chính là lúc **Tính Đóng Gói (Encapsulation)** xuất hiện như một vị cứu tinh.

Trong Java, chúng ta sử dụng từ khóa `private` để giấu dữ liệu đi. Nó giống như việc bạn cất tiền vào két sắt vậy. Người ngoài không thể thò tay vào lấy tiền (truy cập biến trực tiếp). Nếu muốn rút tiền hay nạp tiền, họ phải thông qua giao dịch viên (các hàm `method` công khai). Nhờ đó, giao dịch viên có thể kiểm tra xem số tiền nạp vào có hợp lệ hay không trước khi đồng ý cập nhật số dư.

Dưới đây là cách mình chuyển đổi tư duy từ JavaScript sang Java để bảo vệ tài khoản của bạn:

```java
public class TaiKhoanNganHang {
    // 1. Dữ liệu được giấu kín (Private)
    // Người ngoài không thể thấy hay sửa trực tiếp biến này
    private String chuTaiKhoan;
    private double soDu;

    public TaiKhoanNganHang(String chuTaiKhoan, double soDuBanDau) {
        this.chuTaiKhoan = chuTaiKhoan;
        this.soDu = soDuBanDau;
    }

    // 2. Cung cấp "cửa chính" để thao tác dữ liệu
    // Hàm nạp tiền đóng vai trò như giao dịch viên, kiểm tra tính hợp lệ
    public void napTien(double soTien) {
        if (soTien > 0) {
            this.soDu += soTien;
            System.out.println("Đã nạp thành công: " + soTien);
        } else {
            System.out.println("Lỗi: Số tiền nạp phải lớn hơn 0!");
        }
    }

    // 3. Getter: Chỉ cho phép xem số dư, không cho phép sửa
    public double getSoDu() {
        return this.soDu;
    }
}
```

Nhờ cách viết này, đối tượng của bạn trở nên an toàn và đáng tin cậy hơn rất nhiều. Code gọn gàng, logic chặt chẽ, và quan trọng nhất là ngủ ngon vì không sợ ai đó vô tình làm hỏng dữ liệu của mình!
