# 04. CPU 스케쥴링

## 스케쥴링

### 1. **스케쥴링이란?**

프로세스가 생성된 후 종료될 때까지 모든 상태 변화를 조정하는 관리 역할

-고수준부터 저수준까지의 스케쥴링이 존재
    1. 고수준 스케쥴링
    가장 큰 틀에서 이루어지는 CPU 스케쥴링
    시스템 내의 전체 작업 수를 조절하는 관리
    : 분기로 어떤 작업을 시스템이 받아들일지, 거부할지를 결정 -> **승인의 개념**

    2. 저수준 스케쥴링
    가장 작은 단위의 스케쥴링
    활성화된 프로세스들의 실제 진행을 관리

    3. 중간 수준 스케쥴링
    고수준 스케쥴링에 의해 실행이 결정된 프로세스의 수를 조절하여 시스템의 과부하를 막아주는 관리


    --> 이들의 목적은 모든 프로세스가 공평하게 작업하도록 하는 것 ( 공평성, 안정성, 효율성, 확장성, 반응시간 보장, 무한 연기 방지)


### 2. **프로세스의 운선순위**

![title](https://yansigit.github.io/posts/cpu-%ec%8a%a4%ec%bc%80%ec%a4%84%eb%a7%81/Untitled%205.png)

> 선점형 스케줄링 : 어떤 프로세스가 CPU 를 할당받아 실행 중이더라도 스케줄러가 CPU를 강제로 뺏을 수 있는 스케줄링 방식. 문맥 교환이 일어나야 하므로 낭비가 생긴다는 단점이 있나 하나의 프로세스가 CPU 를 독점할 수 없기 때문에 빠른 응답 시간을 요구하는 대화형 시스템이나 시분할 시스템에 적합하다.

> 비선점형 스케줄링 : 어떤 프로세스가 CPU 를 점유하면 작업을 완료할 때까지 다른 프로세스가 CPU 를 뺏을 수 없는 스케줄링 방식.

### 3. **스케쥴링 알고리즘**

그냥 종류를 설명하는 느낌이고 안중요해보임

- 비선점형 알고리즘
1. FCFS 스케쥴링: 큐
2. SJF 스케쥴링: 실행 시간이 가장 짧은 작업부터 CPU 할당
3. HRN 스케쥴링: CPU를 할당받기 위해 기다린 시간과 CPU 사용 시간을 고려해서 스케쥴링

- 선점형 알고리즘
1. 라운드 로빈 스케쥴링: 할당받은 타임 슬라이스 동안 작업을 하다가 완료하지 못하면 큐의 맨 뒤로 밀려남
2. SRT 스케쥴링: 남은 작업 시간이 적은 프로세스에 CPU 를 먼저 할당
3. 다단계 큐 스케쥴링: 우선순위 스케쥴링 병렬처리
4. 다단꼐 피드백 큐 스케쥴링: 우선순위 스케쥴링 라운드 로빈 처리

-둘 다 가능한 알고리즘

1. 우선순위 스케쥴링: 프로세스의 중요도에 따라 정해진 우선순위(**priority**)
에 따라 처리. 우선순위를 자체적으로 정해줘야 한다

### 4. **인터럽트 처리**
현대에는 입출력 장치가 많이 발전하여 
입출력 요청 -> 입출력 완료
과정이 일어나면 이벤트를 발생시켜 이 사실을 알리는 방식을 만들었는데, 이를 인터럽트라고 함

동기적 인터럽트 / 비동기적 인터럽트가 있음
