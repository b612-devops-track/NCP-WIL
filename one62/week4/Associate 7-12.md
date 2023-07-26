
## 7강 : 로드밸런서, CDN 서비스 소개

### Load Balancer

Target Group : 로드밸런서 사용 시 요청을 처리할 대상에 대한 집합을 생성해야 함

TCP : 네트워크 로드 밸런서

고성능의 분산처리

클라이언트 IP가 그대로 로깅

TCP 레벨 고성능 분산처리

Proxy_TCP : 네트워크 프록시 로드 밸런서

TCP 세션 관리

HTTP, HTTPS : 애플리케이션 로드 밸런서

웹 애플리케이션에 사용

고정 IP

URL 기반 분기

L7 기능

### Global DNS

다양한 레코드 타입 지원

Alias 기능 제공

설정 반영 단계 추가

### CDN+, Global CDN

국내에서 더 빠르게 → CDN+

국외 → 글로벌 CDN

원본은 NCP 오브젝트 스토리지도 가능하고, 커스텀 오리진 서버도 가능함

## 8강 : 로드밸런서, DNS, CDN 서비스 생성 및 활용 데모 시연

### 로드밸런서

1. 타겟 그룹 생성
2. 로드밸런서 생성
    1. 애플리케이션 로드밸런서

### DNS

1. DNS 추가
2. 도메인에 공인 IP(서버의 공인 IP, 로드밸런서의 공인 IP) 추가
3. 배포

### CDN

CDN 신청

## 9강 : IPSEC-VPN, NAP Gateway, GRM 서비스 소개

### IPSEC VPN

고객의 사내망과 NCP 간 사설 통신

### NAT Gateway

방화벽에 접속할 때 outbound 트래픽에 대해 공인 IP를 고정시키기 위함

### Global Route Manager

글로벌 서비스 제공할 때 DNS 기반으로 로드밸런싱 서비스 제공

## 10강 : Auto-scaling 활용법 데모 시연

1. Launch Configuration 설정
    1. 서버 이미지 선택(or 설정 생성)
2. 오토 스케일링 그룹 생성
3. 이벤트 룰 생성

## 11강 : Storage 서비스 소개

- 오브젝트 스토리지
    - 객체 단위로 저장할 수 있는 스토리지 ⇒ 비정형 데이터에 적합
        - 정형 데이터 : 데이터베이스
        - 반정형 데이터 : 워드, 파워포인트 등
    - 정적 웹 사이트 호스팅 가능
    - S3 API 호환
    - Data Lifecycle 지원
- 아카이브 스토리지
    - 콜드 스토리지 - 데이터 접근 비용이 낮은 경우에 최적화
    - 데이터 저장 비용은 저렴, 데이터 처리 API 비용은 비쌈
- NAS
    - 다수의 서버에서 공유하여 사용
    - 스냅샷 이미지 이용 가능
    - 사설 IP 이용한 ACL 오픈으로 타 계정 서버에도 마운트 가능
- Data Teleporter
    - 대용량 데이터 이전 서비스
- 백업
    - 백업과 복구 서비스 제공, 책임

## 12강 : Object Storage 및 NAS Storage 생성 및 활용 데모

### Object Storage

1. 버킷 생성
2. S3 브라우저 실행
    1. REST Endpoint
    2. Access key, Secret key : 마이페이지 → API 인증키 관리

### NAS

1. NAS 볼륨 생성
2. 스냅샷 설정