# VPC

### VPC란?

- 고객 전용 사설 네트워크
- 각각의 vpc는 완벽하게 분리되어 있기에 다른 사용자의 네트워크와 상호 간섭이 발생x
- 서브넷을 이용하여 vpc내 네트워크 공간을 세분화하여 사용
- nacl 이용해 inbound/outbound 네트워크 트래픽을 서브넷 단위로 제어 가능
- 구성요소: vpc, subnet, route table, acg, nacl, virtual private gateway, vpc peering

# Subnet/NACL

### Subnet?

- VPC 네트워크 대역 공간을 세분화하여 사용
- 인터넷 게이트웨이, NAT 게이트웨이용 서브넷을 별도 생성해 외부 인터넷과의 통신 조절
- NACL을 이용해 inbound/outbound 네트워크 트래픽을 Subnet 단위로 제어 가능

### NACL?

- VPC의 보안을 강화
- Allow/Deny 모두 설정 가능, 상태 비저장 방식

| ACG | NACL |
| --- | --- |
| NIC단위 | 서브넷 단위 |
| Allow 규칙에 한해 지원 | Allow, Deny 규칙 모두 지원 |
| 응답 트래픽 자동 허용 | 응답 트래픽에 대한 allow 규칙이 추가로 필요 |
| 모든 규칙을 확인하여 판단 | 우선순위에 따라 규칙 반영 |

# Virtual Private Gateway / Route Table

### Virtual Private Gateway?

- vpc와 IPsec VPN 또는 Cloud Connect를 연결하기 위한 접점
- 보완이 확보된 통신 경로를 통해 네이버 클라우드 플래폼과 온프레미스 네트워크를 잇는 하이브리드 클라우드를 구축

### Route Table?

- vpc 내에서 동작하는 고유의 라이팅 기능 제공
- 외부 인계 네트워크 및 내부 사설 통신 간 흐름을 제어

# Server Image / Snapshot / 유사서버

|  | 서버 이미지 | 스냅샷 | 유사 서버 |
| --- | --- | --- | --- |
| 대상 | 서버 OS + 추가 볼륨 | 볼륨 | 서버 OS |
| 서버 상태 | ON | ON | ON |
| 이미지 | 부팅 디스크 타입 변경 | 디스크 타입 변경 |  |
| 사 | 서버 타입 변경(사양) | 디스크 사이즈 변경 불가 |  |
| 용 | 리전 간 이미지 공유 | 리전 간 이미지 공유 |  |

# Init Script

### 서버 생성 시 실행되는 스크립트를 지정

### When?

- 같은 용도 서버를 여러 대 일괄로 생성하는 경우
- 동일한 환경의 서버를 주기적으로 생성하는 경우
- 용도별로 서버 초기 환경 관리가 필요한 경우

# ACG, Anti-Virus

### ACG

- 서버 방화벽 역할
- default와 custom 구분
- 서버에 대한 acg 변경 / 추가 할당 상시 가능

### Anti-Virus

- Window OS에 한하여 백신 기본 제공
- 리눅스의 경우 별도 비용 발생ㅠ

# Autoscaling

### 1. Launch Configuration

- 이름으로 구분되므로 한 계정 내 유일
- 액션의 대상이 되는 서버의 기본 템플릿 존재
- 베이스 이미지는 퍼블릭 이미지, 커스텀 이미지 사용 가능

### 2. Autoscaling Server Group

- Scaling, Management 액션을 위한 논리적 그룹

### 3. Event Rule

- 액션의 기준이 되는 모니터링 매트릭 설정

## 완전 관리형 쿠버네티스 클러스터 제공

# Load Balancer

### Load Balancer?

- 서버 앞단에서 트래픽을 분산
- 로드밸랜서 하나를 생성하면 뒷단에 서버 2개가 생성되고, 도메인에 바인딩 되어 제공한다
- 종류: 애플리케이션 로드밸런서, 네트워크 로드밸런서, 네트워크 프록시 로드밸런서

### 연결방식

- 프록시, dsr 방식 모두 지원 (근데 프록시는 클라이언트 ip확인하려면 별도의 설정이 필요함)

### 로드밸런싱 알고리즘

- Round Robin: 클라이언트에서 요청이 오면 서버에 1개씩 분배하는 방식
- Least Connection: 클라이언트 연결이 제일 적은 서버에게 새로운 커넥션을 분배하는 방식
- Source IP Hash: 클라이언트 IP에 대한 해시테이블을 가지고 클라이언트 IP에 매핑되는 서버에 새로운 커넥션을 분배하는 방식

## DNS - 도메인 등록 서비스

# CDN+ / GCDN

### 컨텐츠를 Caching하여 보다 빠르고 안정적으로 사용자에게 전송하는 서비스

### When?

- 대규모 파일 배포나 이미지 서비스, 동영상 서비스 등 대규모로 트래픽이 발생하는 경우
- 웹서버를 통해 배포하게 되면 웹서버의 용량이 기하급수적으로 커져야 함
- 이러한 대규모 트래픽에 효과적으로 대응하기 위한 서비스

# IPSEC VPN

- 고객의 사내망과 ncp 간 사설 통신을 위함
- 고객이 직접 사설망을 생성해야 활용 가능

# NAT Gateway

- 비공인 IP를 가진 다수의 서버에게 대표 공인 IP를 이용한 외부 접속을 제공

# Global Route Manager

- DNS 기반의 다양한 방법을 통하여 네트워크 트래픽을 안정적으로 로드밸런싱