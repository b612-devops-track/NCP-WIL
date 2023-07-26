# NCP Associate Course 1-6강

### 클라우드의 역사

- 1960년대 가상화라는 용어 사용
    - 당시에는 전 가상화 기법을 사용하여 구현
    - 에뮬레이터도 존재

- 다양한 하이퍼바이저의 출현
    - IBM의 Logical Partition
        - IBM의 유닉스 머신에 사용되는 하이퍼 바이저
- VMWare
- Xen
- Hyper-V
- KVM

### 공공 클라우드

공공 클라우드 인증을 받은 클라우드

### 금융 클라우드

금융 분야에 특화된 체계적인 업무 지원 체계

### 클라우드를 사용해야 하는 이유

**비용 절감 효과**

- DevOps를 통한 인건비 절감
- 스케일링 기법들을 통한 인프라 비용 최적화
- SaaS, PaaS, 다양한 부가상품 활용을 통한 개발 비용 절감

**빠른 Deploy 및 글로벌 시장 진출 용이**

- 기존 Legacy 인프라에 비해 빠른 Deployment
- Global 리전을 활용한 손쉬운 글로벌 서비스 가능

**보안**

- 인프라에 대한 보안은 CSP(Cloud Service Provider)에 위임
- 서비스 level에 대한 보안만 신경 쓰면 됨

### Compute 상품

- 기본적인 서버를 생성하고 관리하는 상품
- 요금 구성
    - 컴퓨팅, 네트워크, 스토리지 요금이 발생
    - 서버 정지 시 컴퓨팅, 네트워크 요금은 발생하지 않으나 스토리지 비용 발생
    - 서버 정지 시 표준 요금이 적용되는 서버

### Bare Metal Server

단독으로 사용할 수 있는 고성능 물리 서버를 클라우드 형태로 제공

### GPU 서버

병렬 처리에 최적화된 GPU 서버의 고성능 컴퓨팅 파워를 제공

### 서버 Operation 방법

- 웹 콘솔을 이용한 Operation
- CLI Operation
- API Operation

### Init Script

서버 생성 시 실행되는 스크립트를 지정

같은 용도 서버를 여러 대 일괄로 생성하는 경우, 동일한 환경의 서버를 주기적으로 생성하는 경우, 용도별로 서버 초기 환경 관리가 필요한 경우 사용

### ACG(Access Control Group)

서버 방화벽 역할

### 오토 스케일링

클라우드의 장점 중 하나는 유연한 인프라 확장

오토스케일링 설정

- Launch Configuration
- Autoscaling Server Group
- Event Rule

### Kubernetes Service

Container의 배포, 운영, 확장을 자동화하기 위한 플랫폼

Control Plane 설치, 운영에 대한 고민 없이 사용자는 Container가 구동되는 Worker Node에 대한  관리만 하면 됨

### Load Balancer

유입되는 네트워크 트래픽을 백엔드 서버로 분기

### DNS

네임서버 제공

### CDN

요청 사용자에 가장 가까운 엣지(edge) 서버에서 캐싱된 파일을 제공하여 원본 부하를 낮추는 기능

### IPSEC VPN

Site-to-Site연결

### NAT Gateway

비공인 IP를 가진 다수의 서버에게 단일 공인 IP를 이용한 외부 접속 제공

### Global Route Manager

글로벌 네트워크 트래픽을 백엔드 서버로 분기

### VPC

가상의 사설망 구축

IP 대역 설정

- 클라우드상에서 논리적으로 격리된 고객 전용 네트워크 공간
- SUbnet을 이용하여 VPC 안에서 Segment 생성 관리 가능
- Peering: VPC 간 연결을 위한 네트워크 구성

### Subnet

네트워크 Segment 구성

- VPC 주소 범위 내에서 CIDR 형태로 주소 범위 지정
- Public Subnet: 서버만 위치시킬 수 있으며 서버에 공인 IP를 부여할 수 있다.
- Private Subnet: 서버 혹은 로드밸런서를 위치시킬 수 있다.

### Network ACL

Subnet 단위로 통신 제어

### VPC Peering

VPC간 사설 통신을 가능하게 함

### Route Table / Virtual Private Gateway

VPN/전용선 연결 시 통신을 가능하게 함