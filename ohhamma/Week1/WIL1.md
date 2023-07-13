# 1강. 네이버클라우드플랫폼 소개 및 상품구성

## 클라우드를 도입해야 하는 이유
- 비용절감 효과
- 빠른 Deploy 및 글로벌 시장 진출 용이
- 보안

## 네이버클라우드플랫폼 상품구성

### 인프라 상품군
- Compute
- Containers
- Glocal Infrastructure
- Storage
- Migration
- Networking
- Hybrid & Private Cloud
- Content Delivery

### 플랫폼 상품군
- Database
- Gaming
- Blockchain
- Analytics
- Media
- IoT

### 어플리케이션 상품군
- AI NAVER API
- AI Service
- Developers Tools
- Application Service
- Biz Application

### 관리/보안 상품군
- Management & Governance Services
- Security


# 2강. ****VPC 서비스 및 Compute 서비스 소개****

## VPC
- Virtual Private Cloud
- 논리적으로 완벽하게 분리, 상호간섭 x
- VPC Flowlog : 트래픽 정보 수집 및 저장

### Subnet
- VPC 내 공간 세분화

### NACL
- Network Access Control List
- VPC 보안 강화
- 트래픽 Subnet 단위 제어
- 우선순위에 따른 규칙 반영

### Virtual Private Gateway
- 온프레미스 네트워크과 네이버 클라우드 플랫폼 연결
- 
#### 💡 `IPsec VPN` vs `Cloud Connect`
- IPsec VPN : 망-to-망 연결
- Cloud Connect : 전용선 연결

### Route Table
- NAT 게이트로 나가는 규칙 추가
- 외부로 나가는 흐름 제어

## 네이버 플랫폼 Compute 상품

### 일반 서버의 서버 타입
- 마이크로 서버

### Bare Metal Server
- 고성능 물리 서버 단독 사용, 하이퍼바이저 x
- 서버 장애 시 Migration x

### GPU Server
- 병렬 처리에 최적화


# 3강. Compute Operation 소개

## Server Image
- 서버가 갖고 있는 전체 데이터를 하나의 이미지로 생성한 것

## Snapshot
- 특정 볼륨에 대한 복사본을 만드는 작업

## 유사서버
- 특정 서버가 갖고 있는 스펙, 탬플릿을 떠오는 것
- 데이터를 가져오지 x

## Init Script
- 서버 생성 시 실행되는 스크립트 작성

## ACG
- Access Control Group
- 서버 방화벽 역할
- 우선순위 x
- 단일 네트워크 카드 최대 3개의 ACG

## Anti-Virus
- Windows OS에 한하여 백신 기본 제공

## 추가 스토리지 구성
- 블록 스토리지
- 스터리지 Detach / Attach 기능 제공
- 디스크 크기 변경 적용

## Autoscaling
- 유연한 인프라 확장
- 설정
    - Launch Configuration : 템플릿 생성
    - Autoscaling Server Group : 하나의 그룹으로 묶어 관리
    - Event Rule :  모니토링 매트릭 설정

## Kubernetes Service
- 완전 관리형 Kubernetes Cluster 제공


# 4강. (데모) 서버 생성 및 내 서버 이미지로 서버 추가

## 서버 생성 및 접근
1. VPC 생성
2. Network ACL 생성 (우선순위o)
    - Inbound/Outbound 규칙 설정
3. Subnet 생성
4. ACG 생성
    - Inbound/Outbound 규칙 설정
5. Init Script 생성
6. 서버 생성
    1. 서버 이미지 선택
    2. 서버 설정
    3. 인증키 설정
    4. 네트워크 접근 설정
7. 공인IP 생성
8. 인증키로 서버pw 확인

## 서버 이미지로 서버 추가
1. 서버 이미지 생성
2. 생성한 서버 이미지로 서버 추가
    - 스펙 변경 가능
    - script 선택 x
- 서버 이미지 이름으로 복사본 여부 확인 가능


# 5강. Network 서비스 소개

## Load Balancer
- 부화 분산 처리
- 종류 : 애플리케이션, 네트워크, 네트워크 프록시
- DSR 방식 : Direct Server Return
    - 요청에 대한 response load balancer 거치지 않고 client에게 전달
- 분산 알고리즘
    - Round Robin
    - Least Connection
    - Source IP Hash

## DNS
- 도메인 등록 서비스
- 보유하고 있는 도메인을 네이버 클라우드 플랫폼 서비스와 매핑

## CDN
- 정적 데이터 빠르게 전달
- 컨텐츠 caching

## IPSEC VPN
- 고객의 사내망와 NCP 간 망대망 통신
- private subnet으로 통신 필요 (192.168.x.x)

## NAT Gateway
- 비공인 IP를 가진 많은 VM들이 하나의 공인 IP를 공유해서 사용
- routing table 설정

## Global Route Manager
- 여러 region으로 load balancing 도와줌
- DNS 기반으로 사용
- 분배 알고리즘
    - Round Robin
    - Weighted
    - GeoLocation
    - Failover


# 6강. (데모) 로드밸런서 및 Auto-scaling 서비스 구성

## 로드밸런서 생성
1. 로드밸런서 전용 subnet 생성
2. 로드밸런서 target group 생성
3. 애플리케이션 로드밸런서 생성
4. 주어진 접속정보로 접속하기

## Auto-scaling으로 서버 생성
1. launch configuration으로 서버의 이미지 템플릿 생성
2. 생선된 VM들을 하나의 그룹으로 묶어주는 auto scaling group 생성
    1. launch configuration 선택
    2. 그룹 설정
    3. 네트워크 접근 설정
    4. 일정(정책) 설정
    5. 통보 설정

## Event rule으로 모니터링 메트릭 설정
- 클라우드 인사이트 → 이벤트 룰에서 설정 가능
1. Cloud Insight 상품 이용 신청 (처음에만)
2. Event Rule 생성
    1. VPC Auto Scaling
    2. 감시 대상 설정 (그룹 생성)
    3. 감시 항목 및 조건 설정 (템플릿 생성)
    4. 액션 설정 (Auto Scaling 정책)
    5. 규칙 이름 설정
