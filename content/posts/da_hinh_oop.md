
---
title: "Java OOP Phần 3: Sự Linh Hoạt Của Đa Hình (Polymorphism)"
date: 2025-01-13T08:00:00+07:00
draft: false
summary: "Làm thế nào để quản lý một sở thú hỗn loạn với hàng trăm loài vật khác nhau chỉ bằng một dòng lệnh? Đa hình chính là câu trả lời."
tags: ["Java", "OOP", "Polymorphism"]
categories: ["Lập trình"]
cover:
    image: "https://images.unsplash.com/photo-1544365558-35aa4afcf11f?q=80&w=2070&auto=format&fit=crop"
    alt: "Shape shifting art"
    caption: "Cùng một hành động, nhưng mỗi đối tượng lại phản ứng theo cách riêng."
---

Nếu Kế thừa giúp chúng ta tái sử dụng code, thì **Đa hình (Polymorphism)** giúp code của chúng ta trở nên mềm dẻo và linh hoạt đến kinh ngạc. Đây thường là phần khó hiểu nhất với người mới, nhưng hãy để mình lấy một ví dụ đời thường nhé.

Hãy tưởng tượng nút "Phát" (Play) trên các thiết bị điện tử.
* Nếu bạn nhấn "Phát" trên máy nghe nhạc, nó phát ra âm thanh.
* Nếu bạn nhấn "Phát" trên đầu đĩa DVD, nó chiếu hình ảnh lên TV.
* Nếu bạn nhấn "Phát" trong game, nhân vật bắt đầu di chuyển.

Cùng là một hành động "Phát", nhưng tùy vào đối tượng nhận lệnh mà kết quả lại khác nhau. Trong lập trình Java, điều này cũng tương tự. Bạn có thể xem mọi đối tượng `Dog`, `Cat`, `Duck` đều là `Animal`. Khi bạn ra lệnh cho một `Animal` hãy `speak()`, con chó sẽ sủa, con mèo sẽ kêu meo meo, dù lệnh gọi hàm là y hệt nhau.

Điều này cực kỳ hữu ích khi bạn muốn xử lý một danh sách hỗn hợp các đối tượng:

```java
// Lớp cha Animal
class Animal {
    String name;
    public Animal(String name) {
        this.name = name;
    }
    public void speak() {
        System.out.println("Animal is making a sound");
    }
}

// Lớp con Dog kế thừa Animal
class Dog extends Animal {
    String breed;
    public Dog(String name, String breed) {
        super(name);
        this.breed = breed;
    }
    @Override
    public void speak() {
        System.out.println(name + " (chó " + breed + ") sủa: Gâu gâu!");
    }
}

// Lớp con Cat kế thừa Animal
class Cat extends Animal {
    public Cat(String name) {
        super(name);
    }
    @Override
    public void speak() {
        System.out.println(name + " (mèo) kêu: Meo meo!");
    }
}

public class SoThu {
    public static void main(String[] args) {
        Animal[] danhSachThu = new Animal[2];
        danhSachThu[0] = new Dog("Lulu", "Pug");
        danhSachThu[1] = new Cat("Mimi");

        for (Animal thu : danhSachThu) {
            thu.speak();
        }
    }
}
```

Kết quả:

Lulu sủa: Gâu gâu!

Mimi kêu: Meo meo!

Bạn thấy không? Chúng ta không cần dùng if-else để kiểm tra "Nếu là chó thì sủa, nếu là mèo thì kêu". Java tự động biết đối tượng đó thực sự là gì để thực hiện hành động tương ứng (nhờ cơ chế Overriding mà ta đã làm ở bài trước). Đây chính là sức mạnh giúp các hệ thống lớn dễ dàng mở rộng mà không cần sửa đổi code cũ.