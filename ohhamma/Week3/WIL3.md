# ****1강. 과정 소개 및 네이버클라우드플랫폼 서비스 개요****

## 클라우드의 역사
- 가상화 용어 사용
- 다양한 하이퍼바이저의 출현

## Why Cloud?
- 비용 절감 : efficiency
- 빠른 Deploy
- 글로벌 진출시 용이
- 보안

## 상품 의존성
- 존 의존 상품 : 서버, Subnet에 의존적
- VPC 의존 상품 : ACG(VPC)
- 리전 의존 상품 : LB
- 리전 통합 상품 : DNS


# ****2강. (Compute) Compute 상품군 소개****

## Compute 상품
- 서버의 집합
- 기본적인 서버를 생성하고 관리하는 상품
    - 사용 목적에 적합한 서버 선택
- 두 가지 디스크 타입 제공 : SSD, HDD
    - IO 퍼포먼스 차별화

## 서버 타입 (Classic)
- 다양한 서버 타입 제공
    - Micro : Windows 제공 x
    - Compact/Standard
    - High Memory : DB 구성시 사용
    - VDS(Virtual Dedicated Server) : 하나의 VM이 올라감
        - 하나의 리소스를 사용
        - 안정적인 시스템
    - CPU Intensive : 고성능
    - GPU

## 일반 서버 Gen2
- CPU:Memory 비율 고정
- Standard 1:4
- High CPU 1:2
- High Memory 1:8

## Bare Metal Server (Classic)
- 하이퍼바이저 존재 x
- 서버의 물리적인 리소스 이용
- 고성능의 서버, 게임서버에서 많이 이용
- CentOS, ORACLE Linux(8core), Windows 제공
- 내서버 이미지 , 스냅샷, 추가스토리지 기능 사용 x
- 마이그레이션 불가

## Bare Metal Server (VPC)
- Subnet 안에 위치
- CentOS, ORACLE Linux, RHEL 제공

## GPU 서버 (Classic)
- Pass Through 방식 제공
- GPU 제공 사양 : P40, V100

## GPU 서버 (VPC)
- GPU 제공 사양 : T4(가성비), V100
- Windows 제공 x (향휴 제공 예정)

## 국가별 지원 서버 타입 (Classic)
- 한국(KR) : GPU 서버 유일하게 제공
- 싱가폴(SG)
- 일본(JP)
- 미국(USW)
- 독일(DE)
- 홍콩(HK)

## Compute 상품 (VPC)
- 서버 타입 G2만 제공
- 어플리케이션 이미지 제공 x (향후 제공 예정)


# ****3강. (Compute) 서버 Operation 방안 소개****

## 서버 Operation 방법
- 웹 콘솔을 이용한 Operation
- CLI Operation : 명령어 이용
- API Operation : Operation 명령어 개발

## 서버 Operation

### Server Image
- 백업 : 복구가 필요한 경우
    - 그 시점 이후의 변화부분은 복구 x
- 마스터본 생성 : 서버 대량 복제
- `서버`가 대상
- 데이터는 있지만 설정은 없음

### Snapshot
- `볼륨`이 대상
- 백업, 복구 용도
- 서버의 추가 디스크로 붙임

### 유사 서버
- 서버의 설정만으로 깡통 서버 생성
- 데이터 없음

### Server Image Builder
- Packer를 활용한 서버이미지 생성
    - 클라우드 툴

### Init Script
- 서버 만들어진 이후 한 번 실행
- 설치해야하는 패키지나 초기 설정 내용
- 같은 용도 서버 여러 대 생성하는 경우
- 서버이미지보다 더 많은 시간이 걸림
    - 서버이미지와 섞어 사용
    - 기본 환경 → 서버이미지
    - 원본소스 배포 → init script

### ACG
- Access Control Group
- 서버 방화벽 역할
- 프로토콜 : TCP UDP ICMP
- VPC : NIC당 3개, VPC에 의존, In/Out Bound

### 추가 스토리지 구성
- OS 영역 50GB에 추가 스토리지 용량 필요한 경우
- 스토리지 Detach / Attach 기능 제공
- 디스크 크기 변경 기능 적용


# ****4강. (Compute) 오토스케일링과 쿠버네티스 서비스 소개****

## 오토 스케일링
- 스케일링을 자동으로
- IAS에서 제공
- 유연한 인프라 확장
    - `스케줄링` : 사용자가 정의한 주기
    - `모니터링` : 사용자가 설정한 메트릭
    - `온디멘드` : 사용자 요청
- 오토스케일링 설정
    - Launch Configuration
    - Autoscaling Server Group
    - Event Rule
- Scale Out / In : 서버 대수 늘이고 줄이기
    - cf) Scale Up : 서버 성능↑ 비용↑

## Kubernetes Service
- 컨테이너 서비스
- 완전 관리형 Kubernetes Cluster 제공
    - LB 자동 연결 가능
- 보다 효과적인 MSA 구성 가능


# ****5강. (Network) Network 상품군 및 VPC 소개****

## 네이버 클라우드 플랫폼 Networking
- DNS, CDN과 같은 다양한 서비스 제공
- VPC 제공 : 가상의 사설망 구성
    - Virtual Private Cloud
    - Classic과 구분 : 사설 통신 불가
    - 네트워크의 확장성

## VPC (Virtual Private Cloud)
- 논리적으로 격리된 고객 전용 네트워크 공간
- 계정당 최대 3개의 VPC 생성 가능 (한국 기준)
- IP 주소 범위 : `10.0.0.0/8` `172.16.16.0.0/12` `192.168.0.0/16`
    - Subnet을 이용하여 VPC 내 Segment 생성 및 관리 가능
- Peering : VPC간 연결을 위한 네트워크 구성
    - 다른 계정과의 VPC 연결 가능

### ACG & NACL
- 방화벽 기능
- Network Access Control List : VPC의 보안 강화
    - Subnet 단위 ACL
- ACG : VPC 종속적, whitelist 방식 (Allow 규칙만), 모든 규칙 확인
- NACL : Subnet 단위 할당, 비저장 방식(Stateless), 우선순위로 규칙 반영
    - 룰 검사 먼저 진행
- 매핑 정보 변경 가능

### Subnet
- 특정 대역 선언 및 사용
- CIDR 형태로 범위 지정
- Zone 지정 가능
- public / private subnet 구분
    - public : 서버만 위치, 공인IP 부여
    - private : 서버 or LB 위치


# ****6강. (Network) VPC 환경 및 서버 생성 데모 시연****

## 서버 생성
1. VPC 생성 : `10.0.0.0/16`
2. NACL 생성 및 rule 설정 (보안)
    1. public
    2. private(db)
    3. private(lb) : UDP 지원 x
3. Subnet 생성
    1. public : `10.0.1.0/24`
    2. private(db) : `10.0.2.0/24`
    3. private(lb) : `10.0.255.0/24`
4. ACG 생성 (NIC에 대한 ACG)
    1. public
    2. private(db)
5. Init Script 생성
6. 서버 생성 (web-subnet)
7. 공인IP 할당

## 서버 Operation 작업
1. 유사서버로 서버 생성 : 서버 설정 그대로 복사
2. 서버이미지 생성 : 서버 끄지 않아도 됨
3. 서버이미지로 서버 생성 : 데이터 그대로, 설정은 따로

## 스토리지 추가
1. 스토리지 생성
2. 디스크 물리적으로 연결
3. 이용 전 디스크 인식 : fdisk → format → mount

## Snapshot 생성
1. 스토리지 스냅샷 생성 (web001-disk1)
2. 스냅샷으로 스토리지 생성 (web003-disk1)
3. web003에 disk1이 추가된 것을 확인할 수 있음