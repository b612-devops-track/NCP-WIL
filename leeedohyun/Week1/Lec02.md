# VPC 란?
처음 클라우드를 이용할 때 가장 중요한 기능 중 하나
Virtual Primite Cloud의 약자, 고객 전용 사설 네트워크를 구축할 수 있도록 도와주는 서비스이다.
네트워크 환경을 이용할 때 다른 고객과 같은 네트워크를 이용한다면 보안적으로 문제가 될 수 있다. 하지만 각각의 VPC는 논리적으로 완벽하게 분리되어 있어 다른 사용자의 네트워크와 상호 간섭이 발생하는 영역없이 사용 가능

- RFC1918에 명시된 사설 IP 주소 대역 제공
  - 10.0.0.0/16(10.0.0.0~10.0.255.255)
  - 172.16.0.0/16(172.16.0.0~172.16.255.255)
  - 192.168.0.0/16(192.168.0.0~192.168.255.255)
- Subnet을 이용하여 VPC 내 네트워크 공간을 세분화하여 사용
- NACL을 이용하여 inbound/outbound 네트워크 트래픽을 Subnet 단위로 제어 가능
- VPC Flowlog 기능을 통해 네트워크 트래픽 정보를 수집, Object Storage에 저장

# 구성 요소
## Subnet
- VPC 네트워크 대역 공간을 세분화하여 사용
- 인터넷 게이트웨이, NAT 게이트웨이용 서브넷을 별도로 생성하여 외부 인터넷과의 통신을 조절할 수 있음
- NACL을 이용하여 inbound/outbound 네트워크 트래픽을 Subnet 단위로 제어 가능

## NACL
- Network Access Control List의 약자로 VPC의 보안을 강화시키는 요소
- Allow/Deny 모두 설정 가능. 상태 비저장 방식
- ACG vs NACL

| ACG | Network ACL |
| --- | --- |
| 서버 NIC 단위로 사용 | Subnet 단위로 적용 |
| Allow 규칙에 한하여 지원 | Allow, Deny 규칙 모두 지원
| 기본 All Deny | 기본 All Permit
| 모든 규칙을 확인하여 판단 | 우선순위에 따라 규칙을 반영

## Virtual Private Gateway
- VPC와 IPsec VPN 또는 Cloud Connect를 연결하기 위한 접점
- 보안이 확보된 통신 경로를 통해 네이버 클라우드 플랫폼과 온프레미스 네트워크를 잇는 하이브리드 클라우드 구축

## Route Table
- VPC 내에서 동작하는 고유의 라이팅 기능 제공
- 외부 연계 네트워크 및 내부 사설 통신 간 흐름을 제어