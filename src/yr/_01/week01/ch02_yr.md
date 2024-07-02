# Chapter 02. 컴퓨터의 구조와 성능 향상

<aside>
💡 학습목표
- 컴퓨터를 구성하는 하드웨어의 특성을 이해한다.
- CPU와 메모리의 구성 및 동작 방식을 이해한다.
- 컴퓨터의 성능을 향상하는 기술을 알아본다.
- 멀티 프로세싱의 개념을 이해하고 관련 기법을 알아본다.

</aside>

## 하드웨어의 특성

- 하드웨어의 구성
  - 필수장치: CPU(중앙처리장치), 메인메모리
  - 주변장치: 입력장치, 출력장치, 저장장치
- 폰노이만 구조
  - 모든 프로그램은 메모리에 올라와야 실행할 수 있다.
- 자료 구조
  - 큐, 스택
  - 배열, 연결 리스트

## CPU와 메모리의 구성 및 동작 방식

- CPU 구성
  - 산술논리 연산장치
  - 제어장치
  - 레지스터: 작업에 필요한 데이터를 CPU 내부에 보관하는 곳
- 동작 방식

## 컴퓨터의 성능을 향상시키는 기술

- 버퍼
  - 두 장치 사이의 속도 차이를 완화하는 역할
  - 일정량의 데이터를 모아서 옮겨 속도 차이 완화
- (스풀)
- 저장장치의 계층 구조
  : 속도가 빠르고 값이 비싼 저장장치를 CPU 가까운 쪽에 두고, 값이 싸고 용량이 큰 저장장치를 반대쪽에 배치
- 인터럽트 방식: CPU의 작업과 저장장치의 데이터 이동을 독립적으로 운영(주방보조)
- 직접 메모리 접근
- 메모리 앱 입출력
- 사이클 훔치기

### 느낀점

레지스터 종류 왜이렇게 많은건지

저장장치의 계층구조 헷갈림