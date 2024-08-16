# 11. 파일 시스템

## 파일 시스템의 개요

### 1. **파일 시스템이란?**

컴퓨터에 존재하는 다양한 종류의 파일은 사용자가 직접 관리하면 문제가 생길 수 있으니, 운영체제가 알아서 관리한다. 이 관리를 파일 시스템이라 칭한다.
구성, 관리, 접근 방법 제공, 접근 권한 관리, 무결성 보장, 백업/복구, 암호화 등의 기능이 있다.
또한 관리 시 파일 테이블을 사용하여 파일과 파일의 집합체인 디렉터리를 관리하는데, 저장장치에서는 파일을 일정 크기로 묶어서 관리하는데 이를 블록이라고 부른다.

- 파일 디스크립터 : 파일 접근 권한

### 2. **파일 구조**

1. 순차 파일 구조 : 가장 기본적인 파일구조. 순차 파일 구조는 파일 내용이 하나의 긴 줄로 늘어선 형태이다.

2. 인덱스 파일 구조 : 순차 파일 구조의 단점을 해결한 파일 구조다. 순차 파일 구조에 인덱스 테이블을 추가하여 순차 접근과 직접 접근이 가능하다. 현대의 파일 시스템은 인덱스 파일 구조로, 파일을 저장할 때는 순차 파일 구조로 저장하고 파일에 접근할 때는 인덱스(블록 번호) 를 보고 원하는 파일에 직접 접근한다.

3. 직접 파일 구조: 저장하려는 데이터의 특정 값에 어떤 관계를 정의하여 물리적인 주소로 바로 변환하는 파일 구조다.

- 경로: 경로는 전체 디렉터리 중 파일이 어디에 있는지를 나타내는 정보다. 루트 디렉터리를 기준으로 파일의 위치를 나타내는 방식이 절대 경로, 현재 위치를 기준으로 파일의 위치를 표시하는 것을 상대 경로라고 한다.

### 3. **할당 방식**

1. 연결 할당 : 파일에 속한 데이터를 연결 리스트로 관리하는 방식이다. 파일 테이블에는 시작 블록에 대한 정보만 저장하고, ㄷ나머지 데이터는 시작 블록부터 연결하여 저장한다. 이 파일에 맨 끝에 해당ㅎ는 블록에는 링크 대신 널(null) 을 사용한다.

2. 인덱스 할당: 이 할당 방식에서 파일 제어 테이블은 인덱스 블록을 연결한다. 인덱스 블록 안에는 실제 데이터의 위치 정보(블록 정보) 가 순서대로 보관되어 있다.

- 파일 시스템은 빈 블록의 정보만 모아놓은 빈 공간 리스트를 사용하여 빈 공간을 효율적으로 관리한다.