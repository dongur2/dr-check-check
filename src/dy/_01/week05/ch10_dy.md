# 10 입출력 시스템과 저장장치

- 메인버스: CPU + 메모리
- 그래픽 버스: CPU + 그래픽카드
- 고속 입출력 버스: 고속 주변장치
- 저속 입출력 버스: 저속 주변장치

하드 디스크에서 데이터를 가져오는 데 걸리는 총 시간 중 가장 오래 걸리는 것은 **탐색 시간**으로, 이 탐색 시간을 줄이기 위해 사용하는 것이 
**디스크 스케줄링 알고리즘**

### 디스크 스케줄링 알고리즘
- FCFS: 요청이 들어온 트랙 순서대로 서비스
- SSTF: 현재 헤드가 있는 위치에서 가장 가까운 트랙부터 서비스 - 아사 현상 발생 가능
- 블록 SSTF: 큐에 있는 트랙 요청을 일정 블록으로 붂은 후 그 안에서 순서를 변경
- SCAN: 맨 마지막 트랙에 도착할 때까지 앞으로만 전진하면서 트랙 서비스
- C-SCAN: 한쪽 방향으로 움직일 때 요청받은 트랙을 서비스하고 반대로 돌아올 때는 서비스 X
- LOOK: 더 이상 서비스할 트랙이 없으면 헤드가 끝까지 가지 않고 중간에서 방향 전환

### RAID

자동으로 백업하고 장애가 발생할 경우 이를 복구하는 시스템
