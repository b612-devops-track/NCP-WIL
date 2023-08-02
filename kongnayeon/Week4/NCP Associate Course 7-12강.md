## Load balancer

: 서버에 가해지는 부하를 분산해 주는 장치

**Target Group**

요청을 처리할 대상에 대한 집합

**로드밸런싱 알고리즘**

Round Robin: 클라이언트에서 요청 오면 서버에 1개 분배하는 방식

Least Connection: 클라이언트 연결이 제일 적은 서버에게 새로운 커넥션을 분배하는 방식

Source IP Hash: 클라이언트 IP에 대한 해시테이블을 가지고 클라이언트 IP에 매핑되는 서버에 새로운 커넥션을 분배하는 방식

**종류**

애플리케이션 로드밸런서

네트워크 로드밸런서

네트워크 프록시 로드밸런서

TCP 레벨 고성능 분산 처리 - 네트워크 로드밸런서

TCP 세션 관리 - 네트워크 프록시 로드밸런서

SSL 인증 및 암호화 설정 - 애플리케이션 로드밸런서, 네트워크 프록시 로드밸런서

다양한 서버 부하 분산 방식 - 애플리케이션 로드밸런서, 네트워크 프록시 로드밸런서

L7(Application Layer) 기능 제공 - 애플리케이션 로드밸런서

Load Balancer 모니터링

Load Balancer 포트 설정: 여러 개의 로드밸런서 규칙을 동시에 설정할 수 있지만 서로서로 포트를 다르게 설정해야 함

## DNS(Deprecated)

도메인 등록 서비스

## Global DNS

## CDN+, Global CDN

컨텐츠를 Caching하여 보다 빠르고 안정적으로 사용자에게 전송하는 서비스

CDN이 필요한 경우

-   대규모 파일 배포나 이미지 서비스, 동영상 서비스 등 대규모로 트래픽이 발생하는 경우
-   웹서버를 토해 배포하게 되면 웹서버의 용량이 기하 급수적으로 커져야 함
-   이러한 대규모로 트래픽에 효과적으로 대응하기 위한 서비스

## IPSEC VPN

고객의 사내망과 NCP 간 사설 통신을 위한 IPSEC VPN

## NAP Gateway

비공인 IP를 가진 다수의 서버에게 대표 공인 IP를 이용한 외부 접속을 제공

## Global Route Manager

DNS 기반의 다양한 방법을 통해 네트워크 트래픽을 안정적으로 로드밸런싱하는 GSLB 상품

-   DNS 기반의 로드밸런싱 서비스 제공을 통해서 지역별 트래픽 기반 부하 분산, DR 구축 등에 사용할 수 있는 상품
-   로드밸런싱 타입은 4가지 제공(Round Robin, Weighted, GeoLocation, Failover)
-   IP에 대한 Health Checheck만 제공

## Object Storage

인터넷상에 원하는 데이터를 저장하고 사용할 수 있도록 구축된 오브젝트 스토리지

객체 기반의 무제한 파일 저장 스토리지

콘솔, RESTful API, SDK 등의 다양한 방법으로 오브젝트들을 관리하고, 저장된 파일은 각 파일마다 고유한 접근 URL이 부여되어 인터넷상에서 여러 사용자가 쉽게 접근 가능

정적 웹 사이트 호스팅 기능

## NAS

다수의 서버에서 공유하여 사용할 수 있는 스토리지

## Data Teleporter

대용량 데이터 이전을 위한 효과적인 솔루션

## Backup

서버 내 파일 및 Preinstall DB에 대한 백업 설정

## Cloud DB for MySQL

자동 Fail-Over 지원 및 사용자 환경에 맞는 구성 기능

-   Master DB Failover
-   DB Process 모니터링
-   Stand Alone 백업

## Cloud DB for Redis

자동 복구를 통해 안정적으로 운영되는 완전 관리형 클라우드 인메모리 캐시 서비스
