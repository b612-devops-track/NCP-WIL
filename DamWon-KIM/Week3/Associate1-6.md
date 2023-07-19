## 1강
네이버 클라우드 플랫폼 인증 제도

NCE : NCP에 대한 전문적인 지식이 있고 트러블 슈팅과 커스터마이징이 가능한 수준</br>
NCP : NCP에 대한 전문적인 지식이 있고 NCP를 활용하여 인프라를 독자적으로 구축할 뿐만 아니라 다양한 기능을 구현할 수 있는 수준</br>
NCA : NCP에 대한 기본적인 이해가 있고 NCP를 이용한 인프라 구성이 가능한 수준</br>
기업용 Cloud → 2017 Naver: Public Cloud 시작함

금융클라우드
국내 최초의 전문 금융 퍼블릭 클라우드
(ex.금감원)
 - 금융 및 핀테크 기업들이 법적인 규제에 대해 안심하고 사용할 수 있는 국내 최초의 전문 금융 퍼블릭 클라우드
 - 금융과 핀테크 기업만을 위한 전용 클라우드 데이터 센터
 - 국내 금융 컴플라이언스를 완벽하게 충족하는 클라우드 서비스 제공
 - 금융 분야에 특화된 체계적인 업무 지원 체계

Why Cloud?

비용 절감
- 데브옵스, 사용한 만큼 지불하는 등 기회 비용 최적화 등을 통한 비용 절감
- 다양한 부가 상품 이용을 통한 개발 비용 절감

빠른 Deploy
- 기존 Legacy 인프라에 비해 빠른 인프라 구성 시간
 
글로벌 진출시 용이
- 글로벌 리전 활용을 통해 글로벌 진출시보다 빠르고 손쉬운 인프라 구성

보안
- 인프라에 대한 보안은 클라우드 공급 업체에 위임
- 다양한 보안 상품을 이용하여 보안을 강화

[상품 의존성]

존 의존 상품
 - 서버, Subnet과 같이 존에 의존적인 상품

VPC 의존 상품
 - ACG(VPC)

리전 의존 상품
 - LB, Object Storage 등 네트워크 및 스토리지와 같이 서비스 지원 상품이 리전에 의존적인 상품

리전 통합 상품
 - DNS, PaaS, ACG(Classic) 등과 같은 어플리케이션 상품

## 2강

[네이버클라우드 서버에 대해 살펴볼 것]

Compute 상품

### 기본적인 서버를 생성하고 관리하는 상품
서비스 규모와 사용목적에 적합한 성능의 서버를 선택할 수 있도록 다양한 서버 타입 제공
일반적인 2vCPU~16vCPU 상품부터 High Memory 서버, VDS, HPC, GPU 등 다양한 상품 라이업이 준비
네이버 클라우드 플랫폼 체험용 서버인 마으크로 서버 제공
G1과 G2로 구분하여 제공(성능상의 차이 및 스펙의 차이) : vpc의 경우 G2만 제공하고 있음

SSD, HDD 디스크 타입 제공 : SaaS 방식으로 제공한다
IO 퍼포먼스 차별화
SSD 사용 시 최대 IOPS 보장

* SSD 외장하드가 비교적 최근에 출시되었고 HDD는 오래전부터 내장 하드 디스크로 많은 사랑을 받은 저장 장치입니다. 두 저장 장치 모두 노트북과 컴퓨터 모두 사용되고 있습니다.

* SSD : 반도체 메모리에 데이터를 기록하는 저장 장치
  반도체 기반의 저장 장치인 셈

* HDD : 자성 물질로 덮인 플래터라는 판을 모터를 통해 회전시키고 그 위에 헤드를 접근시켜 플래터가 회전하면서 플래터 위에 입력되어 있는 자기 배열을 변경하는 방식으로 데이터를 읽고 쓰는 장치입니다. 즉 SSD와 다르게 물리적으로 자성을 띈 물체에 데이터를 입력시키고 필요하면 회전시켜 데이터를 읽는 방식

* IOPS : Input/Output Operations Per Second

일반적으로 SSD가 빠를 수 있으나 100G당 4000IOPS 

Gen2
서버타입   CPU : Memory비율

하이퍼바이저

AutoScaling 이용 가능 : Compact , Standard

Micro, High Memory, VDS ,GPU는 autoscaling 불가함

## 3강

[서버를 control하는 것]
CLI Operation -> 서버 control 하는 방식
API Operation -> 서버 control 하는 방식

서버 생성 시 실행되는 스크립트를 지정
서버에 설치하여야 하는 패키지나 초기 설정 내용을 스크립트로 선언하여 서버 초기화를 최대한 빠르고 편리하게 구성

Linux는 Python, Perl, Shell, Windows는 Visaul Basic 스크립트로 작성
서버 생성 시 최초 1회에 한하여 실행

Init Script를 언제 사용하나요?
 - 같은 용도 서버를 여러 대 일괄로 생성하는 경우
 - 동일한 환경의 서버를 주기적으로 생성하는 경우
 - 용도별로 서버 초기 환경 관리가 필요한 경우

Classic vc VPC

ACG란? (Access Control Group)
  - 서버 방화벽 역할
  - Default ACG와 Custom ACG로 구분
  - 프로토콜은 TCP, UDP, ICMP 중 선택, 접근 소스는 IP (CIDR), ACG Group 설정 가능능


서버 Operation - 추가 스토리지 구성

서버 상품들 → Operation하는 기능들에 대해서 살펴보았다

## 4강

오토스케일링 & Kubernetes

오토스케일링 : 클라우드의 장점 중 하나는 유연한 인프라 확장

인프라 확장의 높은 자유도를 이용하여 인프라 비용을 최적화하고 이벤트에 대응
사용자가 정의한 주기(스케줄링), 사용자가 설정한 메트릭(모니터링), 사용자 요청(온디멘드)에 따라 서버를 자동 생성, 삭제 진행
오토스케일링 설정 : 서버를 한대 늘릴건지, 100%늘릴건지

Window Server, Linux → 어떤 로드밸런스에 속할지 이런것도 다 설정을 해줘야됨

Launch Configuration

1.1 이름으로 구분되므로 한 계정 내 유일
1.2 액션의 대상이 되는 서버의 기본 템플릿(이미지, 서버타입, ACG 등)
1.3 베이스 이미지는 퍼블릭 이미지, 커스텀 이미지인 내서버 이미지 사용 가

Scale up : 서버의 성능을 높이는 것 [단점 : 비용이 비효율적, scale에 대해서도 한계가 있음 : CPU, 메모리를 무한정 늘릴순 없다]
Scale out/in : autoscaling : 서버 댓수를 늘리는 것

Kubernetes : Container 서비스
완전 관리형 Kubernetes Cluster 제공

Container의 배포(scheduling), 운영(HA, Failover), 확장(Scaling)을 자동화하기 위한 플랫폼
Control Plane 설치, 운영에 대한 고민 없이, 사용자는 Container 가 구동되는 Worker Node 에 대한 관리만 하면 됨
Container Registry, Load Balancer 등 네이버 클라우드 플랫폼 다른 서비스와 통합하여 사용 가능

Kubernetes 란
  컨테이너화된 애플리케이션의 자동 디플로이, 스케일링 등을 제공하는 관리시스템, 오픈소스 기반
  클라우드화된 애플리케이션을 빠르게 자동적으로 배포하고, 컨테이너들의 오케스트레이션, 스케일링 등을 제공하는 컨테이너 관리 시스템


## 5강
네이버클라우드 플랫폼

네트워크 : vpc와 관련된 내용들, 다양한 상품들에 대해서
외부와의 통로, 내부와의 통로 뿐만 아니라 DNS, CDN과 같은 다양한 서비스를 제공

VPC- Subnet 속성[VPC라는 건 전체 큰 덩어리의 아이피 대역]

[Subnet은 그 안의 Segment]

VPC 주소 범위 내에서 CIDR 형태로 주소 범위 지정
Zone을 지정할 수 있으며 동일한 Zone 내에 여러 Subnet 생성 가능
인터넷과 연결되는 Public Subnet과 폐쇄적인 Private Subnet으로 구분
Public Subnet 내에 있는 서버만 Public IP 부여 가능
VPC당 최대 200개의 Subnet 생성 가능

Public Subnet
서버만 위치시킬 수 있으며 서버에 공인 IP를 부여할 수 있다

Private Subnet
서버 혹은 로드밸런서를 위치시킬 수 있다 (대표적 : redis)

나갈때의 방향성이 중요
나갈 때는 Public Subnet, Private Subnet 둘 다 나가는 건 나갈 수 있어
들어올 때는 Public Subnet에 있는 Subnet 중에서 공인 IP를 가지고 있는 서버들에 대해서 외부에서 들어 올 수 있는 것

vpc 환경 → vpc → subnet → server 만드는 작업


## 6강 📁
🪂🛩️
1. vpc 만들기
   
2. vpc - Network ACL lab2-vpc-web-nacl 생성, Rule 설정
    
3. [inbound 설정하고 나서도 outbound 설정하기]
    
inbound로 들어올 수 있어도 나갈 때 outbound룰에 accept allow가 없다면 막힌다
보안과 관련된 사항들, network를 설계하는 작업들을 처음부터 잘 고려를 해야한다
    
4. lb를 위한 lb subnet, lb subnet을 위한 nacl이 필요하다
   lb는 기본적으로 udp를 서비스하고 있지 않다
   lb로 들어오는 것들은 대부분 불특정 다수, ip를 특정짓기가 어렵다
    
5. ACG규칙 설정
    acg와 nacl의 차이점 중 하나 : acg는 whitelist 방식 때문에 열어야 하는 ip list만 관리하고 나머진 다 불러야 한다
    classic 은 서버에 대해서 acg를 구성한다면
    vpc에서는 nic에 대해서 acg를 구성하게 된다
    
6. [vpc에 대한 ip 설정]
    비공인 ip를 가지고 있어서 접근 불가하기 때문에 공인 ip를 할당 할것
    
7. 서버 설정
    
8. 서버이미지 설정
    
9. classic 같은 경우는 서버를 껐어야 이미지를 만들 수 있는데, vpc같은 경우는 서버를 끄지 않고도 이미지를 만들 수 있다
    
10. snapshot 만들고
11. 이걸 스토리지 생성
