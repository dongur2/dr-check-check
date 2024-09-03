# 04 역할, 책임, 협력

**조화**를 이루며 적극적으로 **상호작용하는 협력적인 객체**를 창조

###  **협력**
다수의 <u>연쇄적인 요청과 응답</u>의 흐름으로 구성
- 요청과 응답은 협력에 참여하는 객체가 수행할 책임을 정의

###  **책임**
어떤 객체가 <u>어떤 요청에 대해 응답할 수 있거나 응답할 의무</u>가 있는 경우 해당 객체가 책임을 가짐

: 객체에 의해 정의되는 응집도 있는 행위의 집합

1.  무엇을 할 수 있는가(doing)

        1. 스스로 하는 것
        2. 다른 객체의 행동을 시작시키는 것
        3. 다른 객체의 활동을 제어/조절하는 것
2.  무엇을 알고 있는가(knowing)

        1. 개인적인 정보에 관해 아는 것
        2. 관련된 객체에 관해 아는 것
        3. 자신이 유도/계산할 수 있는 것에 관해 아는 것

- 객체의 책임은 일반적으로 **외부에서 접근 가능한 공용 서비스 관점**에서
  - 객체의 *외부에 제공*해 줄 수 있는 정보(아는 것)
  - *외부에 제공*해 줄 수 있는 서비스(하는 것)

  ⇒ **객체의 공용 인터페이스**를 구성

### 역할
어떤 객체가 수행하는 책임의 집합은 객체가 협력 안에서 수행하는 역할을 암시

: 협력 내에서 **동일한 메세지를 동일한 방식으로 이해할 수 있는 다른 객체로 대체**할 수 있음을 나타내는 일종의 표식

⇒ <u>하나의 협력 안에 여러 종류 객체가 참여</u>할 수 있게 함으로써 **협력을 추상화**

<br>

### 객체지향 설계 기법
> 역할의 개념을 사용하면 <u>유사한 협력을 추상화</u>하여 **다양한 객체들이 협력에 참여할 수 있기 때문에 협력이 좀 더 유연해지며 재사용성**이 높아진다. 역할은 객체지향 설계의 **단순성, 유연성, 재사용성**을 뒷받침하는 핵심 개념이다.

    1. 책임—주도 설계(Responsibility—Driven Design; RDD)
        
        협력에 필요한 책임들을 식별하고 적합한 객체에게 책임을 할당
        
    2. 디자인 패턴(Design Pattern)
        
        전문가들이 반복적으로 사용하는 해결 방법을 정의해 놓은 설계 템플릿 모음
        
    3. 테스트—주도 개발(Test—Driven Development;TDD)
        
        테스트를 먼저 작성하고 테스트를 통과하는 구체적인 코드를 추가하면서 애플리케이션을 완성
        
        책임을 수행할 객체/클라이언트가 기대하는 객체의 역할이 메세지를 수신할 때 어떤 결과를 반환하고 그 과정에서 어떤 객체와 협력할 것인지에 대한 기대를 코드의 형태로 작성


### 객체지향 시스템
목적: 사용자의 요구를 만족시킬 수 있는 기능 제공 & 이해 용이, 단순, 유연한 상호작용을 제공하는 객체 공동체 구축

[Why Object-Oriented Programming? ](https://www.codecademy.com/article/cpp-object-oriented-programming)
> Object-oriented programming (OOP) is a programming paradigm that allows you to **package together data states and functionality** to modify those data states, while **keeping the details hidden away** (like with the lightbulb). As a result, code with OOP design is **flexible, modular, and abstract.** This makes it <u>particularly useful when you create larger programs</u>.