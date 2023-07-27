# (Network) IPSEC-VPN, NAT Gateway, GRM 서비스 소개
## IPSEC VPN
- 고객의 사내망과 NCP 간 사설 통신을 위한IPSEC VPN
    - 고객의 VPN 장비와 NCP VPN 장비 간 터널링 연결 제공
    - NCP 서버들은 Private Subnet 대역으로 통신 필요
    - BW 최대 30Mbps 제공

## NAT Gateway
- 비공인 IP를 가진 다수의 서버에게 대표 공인 IP를 이용한 외부 접속을 제공
    - NAT Gateway를 통해 외부로 접속할 때 사용되는 대표 공인 IP는 해당 NAT Gateway만 독점적으로 사용하는 IP
    - Auto Scaling과 연계된 자동 설정 제공
    - 보안상 다수의 공인 IP에 대한 ACL을 오픈할 수 없는 경우 혹은 공인 IP 생성 비용 절약 가능

## Global Route Manager
- DNS 기반의 다양한 방법을 통해 네트워크 트래픽을 안정적으로 로드밸런싱하는 GSLB 상품
    - DNS 기반의 로드밸런싱 서비스 제공을 통해서 지역별 트래픽 기반 부하 분산, DR 구축 등에 사용할 수 있는 상품
    - 로드밸런싱 타입은 4가지 제공
    - IP에 대한 Health Check만 제공