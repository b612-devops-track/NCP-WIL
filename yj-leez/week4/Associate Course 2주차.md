# Associate Course 2주차

## ****7강. (Network) 로드밸런서, CDN 서비스 소개****

### Target Group

- 동일 VPC내에 있는 서버들에 대해 타겟 그룹 생성 가능
- 타겟 그룹 안에 있는 서버를 다른 타겟 그룹에 속하게 할 수 있지만 타겟 그룹을 다수의 로드밸런서에 연결할 수는 없음
- 서비스를 수행하는 대상의 프로토콜에 따라 L4와 L7으로 구분
- 프로토콜
    - TCP : Network Load Balancer
    - Proxy_TCP : Network Proxy Load Balancer
    - HTTP: Application Load Balancer
    - HTTPS: Application Load Balancer

### Load Balancer

- 알고리즘
    - Round Robin : 클라이언트에서 요청이 오면 서버에 1개씩 분배하는 방식
    - Least Connection : 클라이언트 연결이 제일 적은 서버에게 새로운 커넥션을 분배하는 방식
    - Source IP Hash : 클라이언트 IP에 대한 해시테이블을 가지고 클라이언트 IP에 매핑되는 서버에 새로운 커넥션을 분배하는 방식  → 한 번 특정 서버에 접속하게 되면 그 이후부터 계속 특정 서버에 접속하게 됨, 로드 밸런싱은 무너질 수도 있음
- 애플리케이션 로드밸런서
    - HTTP, HTTPS 를 사용하는 웹 애플리케이션에 보다 유연한 구성이 가능
    - 고정 IP 제공
    - URL 기반 분기 가능 ex [https://www.edwith.org/study](https://www.edwith.org/study) 와 [https://www.edwith.org/](https://www.edwith.org/study)00 다른 서버로 접속
- 네트워크 로드밸런서
    - 고성능의 분산처리 가능
    - Client IP가 그대로 로깅
    - 알고리즘은 Hash, RR만 제공
    - 로깅 제공은 하지 않지만 아웃바운드에 대해 로드밸런서가 중계하지 않아 더 나은 성능 제공
- 네트워크 프록시 로드밸런서
    - Classic과 유사한 Proxy 로드밸런서
- TCP 레벨 고성능 분산처리 → 네트워크 로드밸런서
TCP 세션 관리 → 네트워크 프록시 로드밸런서 
SSL 인증 및 암호화 설정 → 애플리케이션 로드밸런서, 네트워크 프록시 로드밸런서 
다양한 서버 부하 분산 방식 → 애플리케이션 로드밸런서, 네트워크 프록시 로드밸런서
L7(Application Layer) 기능 제공 → 애플리케이션 로드밸런서 ( HTTP/HTTPS 트래픽에 대해서 패킷 헤더를 확인하여 Application 레벨에서의 분기처리를 제공 )

### DNS

- 다양한 레코드 타입 지원 ( A, NS, PTR, AAAA, MX, CNAME, SPF, TXT, SRV, CAA)
- Alias 기능 제공 및 설정 반영 단계 추가

### CDN+, Global CDN

- 컨텐츠를 Caching 하여 보다 빠르고 안정적으로 사용자에게 전송하는 서비스
    - 국내, 국외 주 서비스 지역에 따른 CDN 상품 분리 제공 (CDN+ : 국내 전용, GCDN : 국외 전용)
    - 원본은 NCP 오브젝트 스토리지 혹은 커스텀 오리진 서버를 둘 수 있음
    - 도메인은 랜덤 CON 도메인 (*.ntruss.com ) 혹은 보유하고 있는 도메인 사용 가능
    - 지원 프로토콜은 HTTP, HTTPS / 아직은 정적인 콘텐츠만 가능

## ****9강. (Network) IPSEC-VPN, NAT Gateway, GRM 서비스 소개****

### IPsec VPN

- 고객의 사내망과 NCP 간 사설 통신을 위한 IPSEC VPN
    - IPsec VPN터널을 통해 이동하는 패킷은 아래처럼 패킷이 가진 헤더, IP주소, 데이터 부분이 모두 암호화 처리되어 전달
    
    ![Untitled](Associate%20Course%202%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%200dbbfc9e936048e79583d0369b1b35b2/Untitled.png)
    
- 고객의 VPN 장비와 NCP VPN 장비 간 터널링 연결 제공 (통신 방식 호환이 되어야 함)
- NCP 서버들은 Private Subnet 대역(192.168.x.x) 으로 통신 필요

### NAT Gateway

- 비공인 IP를 가진 다수의 서버에게 대표 공인 IP를 이용한 외부 접속을 제공
- NAT Gateway를 통해 외부로 접속할 때 사용되는 대표 공인 IP는 해당 NAT Gateway만 독점적으로 사용하는 IP
- Auto Scaling과 연계된 자동 설정 제공

### Global Route Manager

- DNS 기반의 다양한 방법을 통해 네트워크 트래픽을 안정적으로 로드밸런싱하는 GSLB 상품
    - DNS 기반의 로드밸런싱 서비스 제공을 통해서 지역별 트래픽 기반 부하 분산, DR 구축 등에 사용할 수 있는 상품
    - IP에 대한 Health Check 만 제공 → Health Check에 실패한 경우 해당 IP 주소가 DNS 응답 풀에서 제외

## ****11강.(Storage) Storage 서비스 소개****

### Object Storage

- 인터넷상에 원하는 데이터를 저장하고 사용할 수 있도록 구축된 오브젝트 스토리지
    - 객체 기반의(비정형의) 무제한 파일 저장 스토리지
- Object Storage 특징
    - AWS S3 Compatibility API 지원
    - Data Lifecycle 지원 → 백업 시 오래된 파일 Archive Storage로 자동 연계

### Archive Storage

- 데이터 아카이빙 및 장기 백업에 최적화된 스토리지 서비스
    - Infrequent Data 백업 및 Archiving Data 보관을 주 목적으로 하는 스토리지
    - Object Storage 보다 데이터 저장 비용은 저렴, 데이터 처리 API 비용은 비쌈
- Archive Storage 특징
    - 데이터 최소 보관 기간없이 사용할 수 있음
    - 콘솔, API(swift, 53), CLI, SDK를 이용해 데이터 관리 가능

### NAS

- 직원들이 네트워크를 통해 효과적으로 협업할 수 있도록 데이터를 지속적으로 사용할 수 있게 하는 파일 전용 스토리지 디바이스
    - 최소 500GB에서 10TB까지 구성 가능, 추가는 100GB 단위로 추가 가능
    - NAS 가용량 안에서 생성된 스냅샷 이미지 이용해서 데이터에 대한 복구 기능 제공
    - 프로토콜은 NFS( → 리눅스에서 사용, IP 접근 제어 ) / CIFS ( → 윈도우에서 사용, Id, password 접근 제어 ) 제공
    - 서버 사설IP 이용한 ACL 오픈으로 타 계정 서버에도 마운트하여 사용 가능
    - 추가 스토리지와 비교했을 때 최초 용량이 크다는 단점이 있지만, 공유가 가능하다는 장점 있음

### Data Teleporter

- 대용량 데이터 ( 최대 100T ) 이전을 위한 전용 어플라이언스 대여 서비스
- 네트워크 비용 절감, 안전하고 빠른 데이터 이관이 가능한 서비스
- 이관 데이터를 NCP Object storage / NAS에 Import