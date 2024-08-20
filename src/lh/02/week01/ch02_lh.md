2장: 객체 객체는 상태 행동 식별자를 지닌 실체인거다

2.1상태:
상태를 이용하면 과거에 얽매이지 않고 현재를 기반으로 객체의 행동 방식을 이해할 수 있다.

상태는 특정 시점에 객체가 가지고 있는 정보의 집합

객체의 상태는 객체에 존재하는 정적인 프로퍼티와 동적인 프로퍼티 값으로 구성 ex public class SimpleCalculator { private int result; // 계산기의 현재 결과를 나타내는 필드

// 생성자: 계산기의 초기 결과를 0으로 설정
public SimpleCalculator() {
result = 0;
}

// 숫자를 더하는 메서드
public void add(int number) {
result += number;  // 현재 결과에 숫자를 더함
System.out.println("결과: " + result);
}

// 현재 결과를 출력하는 메서드
public void printResult() {
System.out.println("현재 결과는: " + result);
}

public static void main(String[] args) {
SimpleCalculator calculator = new SimpleCalculator();  // 계산기 객체 생성

    calculator.printResult();  // 현재 결과는: 0

    calculator.add(5);         // 결과: 5
    calculator.add(10);        // 결과: 15
    calculator.add(-3);        // 결과: 12

    calculator.printResult();  // 현재 결과는: 12
}
} 여기서 result가 상태인거고 add 메서드에 의해 변경될 수 있는거다

2-2.행동 : 외부의 요청 또는 수신된 메시지에 응답하기 위해 동작하고 반응하는 활동 행동의 결과로 객체는 자신의 상태를 변경하거나 다른 객체에게 메세지 전달

구체적으로, 이 클래스에서의 행동은

1.add(int number) 메서드:

행동: 주어진 숫자를 계산기의 현재 결과(result)에 더함.
설명: 이 메서드는 result라는 상태를 변경 메서드를 호출할 때마다 계산기의 결과가 업데이트됩니다.

2.printResult() 메서드:

행동: 현재 result 값을 출력합니다.
설명: 이 메서드는 계산기의 현재 상태를 보여준다.

2-3.식별자: 어떤 객체를 다른 객체와 구분하는데 사용하는 객체의 프로퍼티

클래스 식별자: SimpleCalculator
필드 식별자: result
메서드 식별자: add, printResult
생성자 식별자: SimpleCalculator() (생성자의 경우 클래스 이름과 동일)
매개변수 식별자: number
이 식별자들은 코드에서 특정 요소를 식별하고 참조하는 데 사용