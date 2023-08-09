# (Network) Network 상품군 및 VPC 소개
## 네이버 클라우드 플랫폼 Networking
- 외부와의 통로, 내부와의 통로 뿐만 아니라 DNS, CDN과 같은 다양한 서비스를 제공
    - 유입되는 네트워크 트래픽을 백엔드 서버로 분기하기 위한 Load Balancer
    - 네임서버 제공하는 DNS
    - 요청 사용자에 가장 가까운 엣지 서버에서 캐싱된 파일을 제공하여 원본 부하를 낮출 수 있는 CDN 상품
    - Site-to-Site 연결을 위한 IPSEC VPN 상품
    - 비공인 IP를 가진 다수의 서버에게 단일 공인 IP를 이용한 외부 접속을 제공하는 NAT Gateway 제공
    - 글로벌 네트워크 트래픽을 백엔드 서버로 분기하기 위한 Global Route Manager
- 가상의 사설 망을 구성할 수 있는 VPC 제공
    - VPC의 경우 기존 Classic과 구분되어 VPC와 Classic 간의 사설 통신 및 상품 이용은 불가
    - IP 대역을 설정하는 VPC
    - 네트워크 Segment를 구성하는 Subnet
    - VPC간 사설 통신을 가능하게 하는 VPC Peering
    - VPN / 전용선 연결 시 통신을 가능하게 하는 Route / Virtual Private Gateway

## VPC(Virtual Private Cloud)
<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/0db763ce-152b-44e6-bdf5-7d9a53488bd1" width="500">

- 클라우드상에서 논리적인 격리된 고객 전용 네트워크 공간
    - 계정당 최대 3개의 VPC 생성 가능
- IP 주소 범위
    - 10.0.0.0 - 10.255.255.255 (10/8 접두사)
    - 172.16.0.0 - 172.31.255.255 (172.16/12 접두사)
    - 192.168.0.0 - 192.168.255.255 (192.168/16 접두사)
    - 최소 /28에서 최대 /16까지 Netmask 생성 가능
    - Subnet을 이용하여 VPC 안에서 Segment 생성 관리 가능
- Peering
    - VPC간 연결을 위한 네트웍 구성
    - 내 VPC간 연결 뿐만 아니라 다른 계정과의 VPC 연결도 가능
    - 타계정 VPC 연결 시 로그인 ID, VPC ID, VPC 명 입력 필요

### ACG & NACL
- ACG & NACL
    - Network Access Control List의 약자로 VPC의 보안을 강화시키는 요소
    - NACL이 Subnet에 적용되어 외부에서 접속 시 NACL 룰 검사가 먼저 진행
    - Allow / Deny 모두 설정 가능, 상태 비저장 방식
    - VPC 환경에서 서버, Subnet에 적용된 ACGdhk NACL을 다룬 ACG와 NACL로 변경 가능
- NACL 생성
    - VPC에 종속적인 Network ACL 생성 가능
    - Subnet 레벨에서 동작

## Subnet
- 속성
    - VPC 주소 범위 내에서 CIDR 형태로 주소 범위 지정
    - Zone을 지정할 수 있으며 동일한 Zone 내에 여러 Subnet 생성 가능
    - 인터넷과 연결되는 Public Subnet과 폐쇄적인 Private Subnet으로 구분
    - Public Subnet 내에 있는 서버만 Public IP 부여 가능
    - VPC당 최대 200개의 Subnet 생성 가능
- Public Subnet
    - 서버만 위치시킬 수 있으며 서버에 공인 IP를 부여할 수 있다.
- Private Subnet
    - 서버 혹은 로드밸런서를 위치시킬 수 있다.