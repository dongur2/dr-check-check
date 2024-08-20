객체지향의 사실과 오해
-1장: 객체 객체가 무엇인가 예로 들자면

1.객체 : 강아지

2.속성: 이름 ,나이

3.메소드: 짖기, 꼬리 흔들기

이걸 이제 프로그래밍 언어로 설명해보자

1-1.클래스: 객체를 만들기 위한 템플릿, 쉽게 말해 설계도

이 안에 객체가 가져야할 변수와 메소드가 정의 되어 있다.

class Dog {
// 속성: 이름, 나이, 종
String name;
int age;
String breed;

    // 생성자
    Dog(String name, int age, String breed) {
        this.name = name;   
        this.age = age;
        this.breed = breed;
    }

    // 메소드: 짖기
    void bark() {
        System.out.println(this.name + " is barking");
    }
}

1-2.객체(object): 이 클래스를 실제로 만들어내는 과정

public class Main {
public static void main(String[] args) {
Dog myDog = new Dog("Buddy", 3, "Golden Retriever");  // 객체 생성
myDog.bark();  // "Buddy is barking" 출력
}
}
여기서 my_dog은 Dog 클래스의 객체

즉 이 객체는 name: Buddy

             age:3 

            breed: Golden Retriever
즉 클래스는 객체를 정의하기 위한 설계도

객체는 클래스를 바탕으로 만들어지는 실제 인스턴스

객체는 협력적,자율적

그래서 객체 지향이란 무엇인가 대부분의 사람이 객체 지향을 클래스 구조가 있는거라 생각하지만 x 자바 스크립트를 생각하면 클래스가 존재하지 않는데 객체 지향 언어임 즉 객체 지향의 핵심은 데이터를 객체로 만들어 이를 중심으로 프로그램을 구현하는거

