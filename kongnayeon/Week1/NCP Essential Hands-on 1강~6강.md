# NCP Essential Hands-on 1강~6강

# 클라우드를 도입해야 하는 이유

**비용 절감 효과**

-   DevOps를 통한 인건비 절감
-   스케일링 기법들을 통한 인프라 비용 최적화
-   SaaS, PaaS, 다양한 부가상품 활용을 통한 개발 비용 절감

**빠른 Deploy 및 글로벌 시장 진출 용이**

-   기존 Legacy 인프라에 비해 빠른 Deployment
-   Global 리전을 활용한 손쉬운 글로벌 서비스 가능

**보안**

-   인프라에 대한 보안은 CSP(Cloud Service Provider)에 위임
-   서비스 level에 대한 보안만 신경 쓰면 됨

# VPC(Virtual Private Cloud)

-   가상의 사설 클라우드
-   다른 네트워크와 논리적으로 분리되어 있어 IT 인프라를 안전하게 구축하고 간편하게 관리할 수 있음

# Subnet

-   VPC 네트워크의 대역 공간을 세분화해서 사용
-   인터넷 게이트웨이, NAT 게이트웨이용 서브넷을 별도로 생성하여 외부 인터넷과의 통신을 조절할 수 있음
-   NACL을 이용햐여 inbound/outbound 네트워크 트래픽을 Subnet 단위로 제어 가능

# NACL(Network Access Control List)

-   VPC의 보안을 강화시키는 요소
-   Allow/Deny 모두 설정 가능, 상태 비저장 방식

![스크린샷 2023-07-05 오후 9.01.34.png](https://github.com/b612-devops-track/NCP-WIL/assets/103591752/d1f7ef5a-fa98-4f26-b4b7-6910627ace8a)

# Virtual Private Gateway

-   VPC와 IPsec VPN 또는 Cloud Connect를 연결하기 위한 접점
-   보안이 확보된 통신 경로를 통해 네이버 클라우드 플랫폼과 온프레미스 네트워크를 잇는 하이브리드 클라우드를 구축
    ![스크린샷 2023-07-05 오후 9.03.04.png](https://github.com/b612-devops-track/NCP-WIL/assets/103591752/1391de23-fb65-432e-868b-43594b4bc5f6)

# Route Table이란?

-   VPC 내에서 동작하는 고유의 라우팅 기능 제공
-   외부 연계 네트워크 및 내부 사설 통신 간 흐름을 제어

# Server Image / Snapshot / 유사 서버

![스크린샷 2023-07-05 오후 9.04.29.png](https://github.com/b612-devops-track/NCP-WIL/assets/103591752/bff753a0-b643-4252-b86f-c094eff95cba)

# Init Script

-   서버 실행 시 실행되는 스크립트를 지정
-   설치해야 하는 패키지나 초기 설정 내용을 스크립트로 선언 → 빠르고 편리한 서버 구성
-   서버 생성 시 최초 1회에 한하여 실행

-   같은 용도 서버를 여러 대 일괄로 생성하는 경우
-   동일한 환경의 서버를 주기적으로 생성하는 경우
-   용도별로 서버 초기 환경 관리가 필요한 경우

# ACG(Access Control Group), Anti-Virus

### ACG

-   서버 방화벽 역할, Inbound/Outbound 룰 설정 가능
-   Default ACG, Custom ACG,
-   프로토콜은 TCP, UDP, ICMP 중 선택 가능, 접근 소스는 IP, ACG Group 설정 가능
-   서버에 대한 ACG 변경/추가 할당 상시 가능

### Anti-Virus

-   Window OS에 한하여 백신 기본 제공, 리눅스는 별도 비용

# Autoscaling

-   인프라 확장의 높은 자유도 활용
-   스케줄링, 모니터링, 온디멘드에 따라 서버 자동 생성, 삭제 진행

# Kubernetes Service

-   Container의 배포, 운영, 확장을 자동화하기 위한 플랫폼
-   Control Plane 설치, 운영에 대한 고민 없이, 사용자는 Container가 구동되는 Worker Node에 대한 관리만 하면 됨
-   Container Registry, Load Balancer 등과 통합하여 사용 가능

# Load Balancer

-   부하 분산을 위해 서버 앞단에서 트래픽을 분산해 주는 것
-   기본적으로 로드밸런서 하나를 생성하면 뒷단에 Load Balancer 서버 2개가 생성되고, 도메인에 바인딩되어 제공

# 로드밸런싱 알고리즘

-   Round Robin: 클라이언트에서 요청이 오면 서버에 1개씩 분배하는 방식
-   Least Connection: 클라이언트에서 연결이 제일 적은 서버에게 새로운 커넥션을 분배하는 방식
-   Source IP Hash: 클라이언트 IP에 대한 해시테이블을 가지고 클라이언트 IP에 매핑되는 서버에 새로운 커넥션을 분배하는 방식

# DNS

-   도메인 등록 서비스

# CDN

-   컨텐츠를 Caching하여 보다 빠르고 안정적으로 사용자에게 전송하는 서비스

**CDN이 필요한 경우**

-   대규모 파일 배포나 이미지 서비스, 동영상 서비스 등 대규모로 트래픽이 발생하는 경우
-   웹서버를 통해 배포하게 되면 웹서버의 용량이 기하급수적으로 커져야 함
-   이러한 대규모 트래픽에 효과적으로 대응하기 위한 서비스

# NAT Gateway

-   비공인 IP를 가진 다수의 서버에게 대표 공인 IP를 이용한 외부 접속을 제공
