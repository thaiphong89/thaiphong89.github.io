---
title: "Java OOP Phần 2: Đừng Lặp Lại Chính Mình (Inheritance)"
date: 2025-12-02T08:00:00+07:00
draft: false
summary: "Lập trình viên giỏi là người biết 'lười' đúng cách. Tại sao phải viết lại những đoạn code giống hệt nhau? Hãy để tính Kế thừa giúp bạn."
tags: ["Java", "OOP", "Inheritance", "DRY"]
categories: ["Lập trình"]
cover:
    image: "https://images.unsplash.com/photo-1511895426328-dc8714191300?q=80&w=2070&auto=format&fit=crop"
    alt: "Generations walking together"
    caption: "Kế thừa những gì tốt đẹp nhất từ thế hệ đi trước."
---

Một trong những nguyên tắc vàng trong lập trình là **DRY (Don't Repeat Yourself)** - Đừng lặp lại chính mình. Nhưng thực tế, khi mô tả các đối tượng, chúng ta thường gặp rất nhiều đặc điểm chung.

Ví dụ, khi bạn tạo một game có Chó (`Dog`) và Mèo (`Cat`). Cả hai đều có tên, đều có tuổi, và đều biết kêu. Nếu tạo hai class riêng biệt và viết lại từng dòng code khai báo tên, tuổi cho cả hai thì thật lãng phí công sức. Chưa kể sau này nếu muốn thêm thuộc tính "Cân nặng", bạn phải đi sửa ở cả hai nơi.

Java giải quyết vấn đề này bằng **Tính Kế Thừa (Inheritance)**. Tư duy ở đây là: Hãy tạo ra một class cha chung nhất (ví dụ `Animal` như trong file mẫu của chúng ta), chứa tất cả những gì chung nhất. Sau đó, Chó và Mèo chỉ cần "kế thừa" lại những thứ đó và phát triển thêm nét riêng của mình.

Hãy xem sức mạnh của từ khóa `extends` và `super`:

```java
// Class Cha: Chứa những đặc điểm chung của muôn loài
class Animal {
    protected String name; // protected giúp con cháu có thể truy cập được

    public Animal(String name) {
        this.name = name;
    }

    public void speak() {
        System.out.println(this.name + " đang phát ra âm thanh...");
    }
}

// Class Con: Kế thừa từ Animal
// Dog tự động có biến 'name' và hàm 'speak' mà không cần khai báo lại
class Dog extends Animal {
    private String breed; // Thuộc tính riêng chỉ chó mới có

    public Dog(String name, String breed) {
        // Từ khóa super: Gọi lên constructor của cha để nhờ cha khởi tạo dùm cái tên
        super(name); 
        this.breed = breed;
    }

    // Ghi đè (Override): Sửa lại hành động speak cho đúng chất của chó
    @Override
    public void speak() {
        // Bạn thậm chí có thể gọi lại hành động gốc của cha nếu muốn
        // super.speak(); 
        System.out.println(this.name + " sủa: Gâu gâu! 🐕");
    }
}
```


Bạn thấy đấy, nhờ kế thừa, code của chúng ta trở nên có tổ chức hơn hẳn. Nó giống như việc tiến hóa trong tự nhiên vậy, thế hệ sau thừa hưởng gen của thế hệ trước và phát triển thêm những đặc tính ưu việt hơn.