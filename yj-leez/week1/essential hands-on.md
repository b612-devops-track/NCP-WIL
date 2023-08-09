# Essential hands-on 1주차

## 2강 ****VPC 서비스 및 Compute 서비스 소개****

### VPC란?

- 퍼블릭 클라우드 상에서 제공되는 고객 전용 사설 네트워크
- 각각의 VPC는 논리적으로 완벽하게 분리되어 있어 VPC별로 네트워크를 구성할 수 있고 각각의 VPC에따라 다르게 네트워크 설정을 줄 수 있음
- RFC1918에 명시된 사설 IP 주소 대역 제공 → 이 대역에 맞추어 VPC의 아이피범위를 구축해야함
    - 10.0.0.0/16 (10.0.0.0 ~ 10.0.255.255)
    - 172.16.0.0/16 (172.16.0.0 ~ 172.16.255.255)
    - 192.168.0.0/16 (192.168.0.0 ~ 192.168.255.255)
- VPC를 만들었다면 VPC 내 네트워크 공간을 세분화하여 Subnet을  VPC 내 네트워크 공간을 세분화 하여 사용
- VPC 구성요소: VPC, Subnet, NAT Gateway, Route Table, ACG, NACL, Virtual Private Gateway, VPC Peering
    - Subnet: 서브넷 안에 RDS, EC2와같은 리소스들을 위치시키며 인터넷과 연결되어 있는 public subnet, 연결되어있지 않는 public subnet으로 나뉨

<img width="493" alt="1" src="https://github.com/yj-leez/NCP-WIL/assets/77960090/df73fbbe-3c9b-4f56-bb13-be91c0cb89e6">


## 3강 ****Compute Operation(Server image, snapshot, init script 등) 소개****

### Server image/ Snap shot/ 유사서버

- 이미지, 스냅샷 또는 Cloud Storage에 저장된 이미지에서 커스텀 이미지를 만들고 이 이미지를 사용하여 가상 머신(VM) 인스턴스를 만들 수 있음 네이버 클라우드 플랫폼에서는 커스텀 이미지로 서버 이미지, 스냅샷 제공
- Server image: 서버 OS와 추가 볼륨을 대상으로 하며 디스크 타입이나 사이즈 변경 가능
- Snap shot: 볼륨을 대상으로 하며 디스크 타입이나 사이즈 변경 불가
- 유사 서버: 서버 OS를 대상으로 하여 userdata는 동일하게 적용되지 않으므로 소스 VM과 동일 OS, 사양, 키패어를 가진 VM 생성

### init script

- 서버에 설치하여야 하는 패키지나 초기 설정 내용을 스크립트로 선언하여 서버 초기화를 최대한 빠르고 편리하게 구성
- 같은 환경의 서버를 주기적으로 생성하거나 용도별로 서버 초기 환경 관리가 필요한 경우 등에 활용

### ACG

- NACL이 Subnet단계의 접근을 제어한 것과는 달리, ACG는 서버 단계의 접근을 제어하는 서버 방화벽 역할
- 프로토콜은 TCP, UDP, ICMP 중 선택, 접근 소스는 IP (CIDR), ACG Group 설정 가능

### Autoscaling

- 클라우드의 유연성을 돋보이게 하는 핵심기술로 사용자가 정의한 주기(스케줄링), 사용자가 설정한 메트릭(모니터링), 사용자 요청(온디멘드)에 따라 서버 사이즈를 자동으로 조절

## 4강 ****(데모) 서버 생성 및 내 서버 이미지로 서버 추가****

<img width="1552" alt="2" src="https://github.com/yj-leez/NCP-WIL/assets/77960090/0d0786c9-a856-402b-95c9-4c3123c89857">


VPC - VPC Management에서 VPC 생성 완료

<img width="1552" alt="3" src="https://github.com/yj-leez/NCP-WIL/assets/77960090/06f8815d-bbba-472e-aafd-b8f09a891e71">


<img width="1552" alt="4" src="https://github.com/yj-leez/NCP-WIL/assets/77960090/00e37cda-10d5-439e-8036-841fa57b62e7">


VPC - Network ACL에서 Inbound, Outbound 규칙 생성 완료

<img width="1552" alt="5" src="https://github.com/yj-leez/NCP-WIL/assets/77960090/bf6874e7-60b6-4668-ab11-f8db9db65fdb">


Server - ACG에서 Inbound, Outbound 규칙 생성 완료

<img width="1552" alt="6" src="https://github.com/yj-leez/NCP-WIL/assets/77960090/a393e71c-2933-4e32-bbce-6ad84335e17d">


Server - subnet 생성 완료

<img width="1552" alt="7" src="https://github.com/yj-leez/NCP-WIL/assets/77960090/5c35c5b9-e196-402a-b2ed-f37c70b132b2">


Server - Init Script 생성 완료

<img width="1552" alt="8" src="https://github.com/yj-leez/NCP-WIL/assets/77960090/3e5ef1d0-d3d1-45a2-b0f8-6e13de72da2e">


Server - Server - Server 생성 완료

<img width="1552" alt="9" src="https://github.com/yj-leez/NCP-WIL/assets/77960090/d99ad869-3bbb-45f3-9696-1e2658562560">


Server - Public IP 생성 완료

<img width="1552" alt="10" src="https://github.com/yj-leez/NCP-WIL/assets/77960090/bd440403-3132-4646-ba0b-91923cc1d79f">


Server - Server Image 생성 완료

<img width="1552" alt="11" src="https://github.com/yj-leez/NCP-WIL/assets/77960090/393087c1-bad6-4bfc-9d7f-ca96e80234d3">


브라우저로 공인 ip 접속시 80포트로 연결되어 apache 웹 서버의 기본 화면 표시

## 5강 Network 서비스 소개

### Load Balancer

- 부하 분산을 위해 서버 앞단에서 트래픽을 분산
- 종류: 애플리케이션 로드밸런서, 네트워크 로드밸런서, 네트워크 프록시 로드밸런서
- 알고리즘: Round Robin, Least Connection(클라이언트 연결이 제일 적은 서버에게 새로운 커넥션을 분배하는 방식), Source IP Hash(클라이언트 IP에 대한 해시테이블을 가지고 클라이언트 IP에 매핑되는 서버에 새로운 커넥션을 분배하는 방식)

<img width="306" alt="12" src="https://github.com/yj-leez/NCP-WIL/assets/77960090/63235656-6150-4182-9661-ee32b34b2e02">


### DNS

- 도메인을 판매하지는 않지만, 도메인을 네이버 클라우드 플랫폼에 잇는 리소스와 매핑할 수 있는 기능을 제공

### CDN

- 대규모 파일 배포나 이미지 서비스, 동영상 서비스 등 대규모로 트래픽이 발생하는 경우 효과적으로 대응하기 위한 서비스
- 국내, 국외 주 서비스 지역에 따른 CDN 상품 분리 제공

### IPSEC VPN

- 고객의 사내망과 네이버 클라우드 플랫폼 망을 망대망으로 연결 가능하게끔 하는 기능
- NCP 서버들은 Private Subnet 대역(192.168.x.x) 으로 통신 필요

### NAT Gateway

- 프라이빗 서브넷의 인스턴스가 VPC 외부의 서비스(인터넷)에 연결할 수 있도록하고 외부 서비스에서는 프라이빗 서브넷 내의 인스턴스와의 연결 할 수 없도록 하기 위해 NAT 게이트웨이를 사용

### Global Route Manager

- 로드밸런싱은 하나의 리전에 여러 vm으로 분배했다면 Global Route Manager은 DNS을 기반으로 여러 리전으로 로드밸런싱을 도와줌
- 종류: Round Robin, Weighted, GeoLocation, Failover

## 6강 ****(데모) 로드밸런서 및 Auto-scaling 서비스 구성****

### 로드밸런서 서비스 구성

1. VPC - Subnet Management - subnet 생성
2. Load Balancer - target group - target group 생성
3. Load Balancer - Load Balancer - Application Load Balancer 생성
✅ 접속정보로 접속하여 서버로 들어가지는지 확인

### Auto-scaling 서비스 구성

1. Launch Configuration을 통해서 오토 스케일링으로 생성될 서버의 이미지 생성
Compute - Auto Scaling - Launch Configuration - Launch Configuration 생성
2. Launch Configuration을 바탕으로 만들어진 VM들을 하나의 그룹으로 만들어서 관리할 수 있도록 하는 Scaling group 생성
Compute - Auto Scaling - Auto Scaling group - Auto Scaling group 생성 (정책 설정)
3. Event Rule을 통해 언제 증가, 감소할지 모니터링 매트릭 설정
Cloud insight - Configuration - Event Rule - VPC Auto Scaling Event Rule 생성
