# 10. 입출력 시스템과 저장장치

## 입출력 시스템

### **1. 입출력 장치와 채널**

컴퓨터는 필수장치인 CPU, 메모리 / 주변장치인 입출력장치와 저장장치로 구성된다.
각 장치는 메인보드의 버스로 연결되며 데이터 전송 속도에 따라 저속 / 고속 주변장치로 나눌 수 있다.

> 저속 주변장치 : 메모리와 주변장치 사이에 오고 가는 데이터양이 적어 데이터 전송율이 낮은 장치를 말한다. 키보드의 경우 아무리 빨리 타이핑을 한다고 해도 초당 전송률이 1KB 를 넘지 않으므로 저속 주변장치에 해당한다.

> 고속 주변장치: 메모리와 주변장치 사이에 대용량의 데이터가 오고 가므로 데이터 전송률이 높은 장치를 말한다. 출력장치인 그래픽카드의 경우 모니터에 초당 십 장의 그래픽을 보여주여야 하므로 고속 주변장치에 해당하며, 하드디스크도 대용량의 데이터를 메모리에 올리거나 메모리에서 하드디스크로 옮겨야 하므로 고속 주변장치에 해당한다.

**입출력 버스**
컴퓨터를 사용하기 시작한 초기에는 주변장치가 많지 않았고 CPU 와 메모리의 속도도 빠르지 않아 모든 장치가 하나의 버스로 연결되었고, CPU 가 작업을 진행하다가 입출력 명령을 만나면 직접 입출력장치에서 데이터를 가져왔다.
-> 이를 폴링(polling) 방식이라고 한다.

고속 주변장치가 저속 주변장치와 입추력 버스를 공유하면 입출력 속도가 현저히 저하되므로, 고속 입출력 버스와 저속 입출력 버스로 분리하여 **입출력 제어기를 통해** 운영한다. 입출력장치에서 입출력 제어기까지 가는 데에 인터럽트 핸들링, 이중 버퍼 처리를 통해 유리하게 신호를 제어하게 된다.

### **2. 저장장치**

본 책에서는

1. 하드디스크
2. SSD
3. CD
   세 가지 종류로 저장장치를 설명한다. 셋의 기본 개념은 같으네, 섹터라는 가장 작은 물리적 저장 단위를 기반으로 '어떤 방식으로 데이터를 읽고,쓰고,고치는가'
   만을 나눈 것이다. 당연히 0/1 이진법으로 데이터를 저장하며 플래터라는 일종의 자석으로 이를 제어한다. 그 외에 디테일은 중요하지 않다는 생각이 들어 생략한다.

> 하드디스크 입출력 속도 : 탐색 시간 + 회전 징녀 시간 + 전송 시간. 주로 탐색 시간이 가장 오래 걸린다.

### **3. 디스크 스케쥴링**

스케쥴링의 종류가 많은데,

1. FCFS 디스크 스케쥴링

2. SSTF 디스크 스케쥴링

3. 블록 SSTF 디스크 스케쥴링

**4. SCAN 디스크 스케쥴링**
: 헤드가 움직이기 시작하면 맨 마지막 트랙에 도착할 때까지 되돌아가지 않고 계속 앞으로만 전진하면서 요청받은 트랙을 서비스한다.
가장 빠르다.

5. C-SCAN 디스크 스케쥴링