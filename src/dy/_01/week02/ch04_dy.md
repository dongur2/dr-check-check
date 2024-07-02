# 04 CPU 스케줄링
여러 프로세스의 상황을 고려하여 <u>CPU와 시스템 자원을 어떻게 배정</u>할지 결정

1. 고수준 스케줄링(장기 스케줄링): 시스템 내 전체 작업 수를 조절
    - 작업 요청이 오면 시스템 상황을 고려하여 작업 승인/거부 결정 -> 시스템 내 동시 실행 가능한 프로세스 수(멀티 프로그래밍 정도) 결정

2. **저수준 스케줄링(단기 스케줄링)**: 어떤 프로세스에 CPU를 할당할지, 어떤 프로세스를 대기 상태로 보낼지 등을 결정
    - 오늘날의 CPU 스케줄러는 대부분 중간 스케줄링 + 저수준 스케줄링 구성
    - 시스템 성능에 영향

3. **중간 수준 스케줄링**: 고주준 스케줄링과 저수준 스케줄링 사이에서 저수준 스케줄링이 완만하게 이루어지도록 완충
    - 고수준 스케줄링의 결정으로 <u>프로세스가 활성화된 이후, 시스템에 과부하가 발생했을 경우에 부하를 조절</u>
    - 중지 & 활성화로 전체 시스템의 활성화된 프로세스 수 조절: 이미 활성화된 프로세스 중 일부를 보류 상태로 보내거나, 보류된 프로세스를 처리 능력에 여유가 생겼을 때 다시 활성화

## 스케줄링의 목적
**모든 프로세스가 자원을 공평하게 배정**받고, 시스템 자원이 **유휴 시간 없이 사용**되도록 하여 효율성을 높이며, 우선순위를 사용해 **중요 프로세스가 먼저 작동**되도록 하고 시스템 자원을 점유/파괴하려는 프로세스로부터 자원을 보호하여 안정성을 보장한다. 또한, **프로세스가 증가해도 시스템이 안정적으로 작동**하도록 조치하여 확장성도 보장하고, **적절한 시간 안에 프로세스 요구에 반응**하도록 보장해야 하며, **특정 프로세스 작업이 무한히 연기되지 않도록 방지**한다.

## 스케줄링 고려 사항
1. 선점형 스케줄링 & 비선점형 스케줄링
- 선점형: 어떤 프로세스가 CPU를 할당받아 실행 중이더라도, 운영체제가 CPU를 강제로 빼앗기 가능
    - *문맥 교환 같은 부가적인 작업 때문에 낭비*가 발생하지만, 빠른 응답 시간을 요구하는 <u>대화형 시스템/시분할 시스템에 적합</u>하다.
- 비선점형: 어떤 프로세스가 CPU를 점유하면, 다른 프로세스가 빼앗기 불가능
    - 선점형보다 스케줄러 작업량이 적고 문맥 교환에 의한 낭비가 적지만, *CPU 사용 시간이 짧은 여러 프로세스가 오랫동안 기다려야 하므로 전체 시스템 처리율이 감소*한다. 이전 일괄 작업 시스템에서 사용했던 방식이다.

2. 대부분의 CPU 스케줄러는 **우선순위**를 사용한다. 우선순위가 높다는 말은 **더 빨리 & 더 자주 실행된다**는 의미가 된다.

3. CPU 집중 프로세스와 입출력 집중 프로세스가 같이 있을 경우, 입출력 집중 프로세스를 먼저 실행 상태로 옮겨 대기 상태로 이동시킨 뒤 다음 프로세스를 실행 상태로 가져온다.

4. 전면 프로세스는 즉각 사용자와 상호작용에 반응해야 하므로 우선순위 > 후면 프로세스

## 다중 큐
**우선순위에 따른 여러 개의 큐**를 만들어 매번 모든 PCB의 우선순위를 검색하지 않도록 한다.

프로세스는 **<u>준비 상태</u>에 들어올 때마다 자신의 우선순위에 해당하는 큐의 마지막에 삽입**된다. 이 때 우선순위는 운영체제가 부여한 이후로 프로세스 종료까지 순위가 변하지 않는 고정 우선순위 방식과 프로세스 생성 시 부여받은 우선순위가 프로세스 작업 중에 변하는 변동 우선순위 방식에 따른다.

또한 <u>**대기 상태**</u>에서도 다중 큐를 사용하는데, 이 때는 **같은 입출력을 요구한 프로세스끼리 큐가 구성**된다.

둘의 차이점은 **준비 큐는 한 번에 프로세스 하나를 꺼내 CPU에 할당**하지만, **대기 큐는 여러 개의 PCB를 동시에 꺼내 준비 상태로 옮긴다**는 점이다. 많은 입출력장치에서 입출력이 동시에 끝날 경우 여러 개의 인터럽트가 한꺼번에 처리되기 때문이다.


## 스케줄링 알고리즘
#### 비선점형 알고리즘: CPU를 점유하고 있는 프로세스에게서 CPU를 빼앗기 불가능 (일괄 작업 시스템)
- FCFS: 동일한 우선순위로 취급하는 단일 큐로, 들어온 순서대로 프로세스를 처리 -> 콘보이 현상 발생
- SJF: 실행 시간이 짧은 프로세스를 우선 처리 -> 아사 현상 발생 & 실행 시간 예측 곤란
- HRN: 대기 시간을 고려하여 응답 비율이 높은 프로세스를 우선 처리 -> 완화됐지만 아사 현상 발생 & 실행 시간 예측 곤란

#### 선점형 알고리즘: CPU를 점유하고 있는 프로세스에게서 CPU 뺴앗기 가능 (시분할 시스템)
- 라운드 로빈: 기본적으로 FCFS와 비슷하지만, 각 프로세스는 주어진 타임 슬라이스만큼 작업한 뒤, 그 시간 내에 작업을 완료하지 못하면 큐 끝(tail)으로 삽입 -> 끝날 때까지 순환
- SRT: 라운드 로빈 + SJF; 남은 실행 시간이 짧은 프로세스 우선 처리 -> 아사 현상 & 실행 시간 예측 곤란
- 우선순위: 아사 현상 & 매번 우선순위 계산으로 인한 오버헤드
- 다단계 큐: 우선순위에 따른 다단계 큐(라운드 로빈) 운영 -> 각 상위 우선순위 큐가 완료되지 않으면 하위 큐 실행X
  -> 하위 프로세스 무기한 연기 문제
- **다단계 피드백 큐**: 기본적으로 다단계 큐와 같게 운영하지만, 각 프로세스는 CPU에서 한 번 실행된 후에 한단계 낮은 우선순위 큐 끝에 삽입 & 하위 큐로 갈 수록 타임 슬라이스 증가