# ****7강. (Network) 로드밸런서, CDN 서비스 소개****

## Load Balancer

- Target Group : 서버에 대한 집합
- 프로토콜 : TCP, Proxy_TCP, HTTP, HTTPS
- 로드밸런서 알고리즘
    - Round Robin
    - Least Connection
    - Source IP Hash
- 종류 : 애플리케이션, 네트워크, 네트워크 프록시
- 타입별 기능 비교
    - Network : TCP, 고성능
    - Network Proxy : TCP, TLS, 로깅 제공
    - Application : HTTP/HTTPS, 로깅 제공

## Global DNS

- 도메인 등록 서비스
- 설정 반영 단계 추가
- 모니터링 기능 추가

## CDN+, Global CDN

- CDN+ : 국내 전용
- GCDN : 국외 전용
- 정적인 컨텐츠 대규모로 발생하는 경우 사용

# ****8강. (Network) 로드밸런서, DNS, CDN 서비스 생성 및 활용 데모 시연****

## 로드밸런서 생성

1. 타겟 그룹 생성
2. 로드밸런서 생성

## DNS 생성

1. 도메인 추가
2. 레코드 추가
    1. public IP (A)
    2. load balancer (CNAME)

## CDN 설정

1. CDN 신청

# ****9강. (Network) IPSEC-VPN, NAT Gateway, GRM 서비스 소개****

## IPSEC VPN

- 고객의 사내망과 NCP 간 사설 통신을 위한 IPSEC VPN
- Virtual Private Network

## NAT Gateway

- 다수의 비공인 IP 서버에게 대표 공인 IP를 이용한 외부 접속
- 나가는 IP 고정

## Global Route Manager

- 네트워크 트래픽 안정적으로 로드밸런싱
- GSLB : 어떤 서버를 사용하지 못하는 경우 다른 서버로 가는 경로로 안내
    - 로드밸런싱, 헬스체크 기능

# ****10강.(Compute) Auto-scaling 활용법 데모 시연****

1. Launch Configuration 생성
2. Auto Scaling Group 설정
    1. 최대/최소 용량, 기대 용량 (start)
    2. 쿨다운, 헬스체크 기간
    3. 정책 설정
3. Cloud Insight(Monitoring)
    1. event rule 생성 : VPC Auto Scaling
    2. 그룹 생성
    3. 템플릿 생성

# ****11강.(Storage) Storage 서비스 소개****

## Object Storage

- object 단위로 저장 및 관리
- 비정형 데이터에 적합 : 데이터 사이즈를 가늠하기 어려움
- data lifecycle 지원

## Archive Storage

- 장기 백업 및 데이터 아카이빙에 적합
- 성능↓ 비용↓

## NAS

- 다수의 서버에서 공유하며 사용 가능
- 자동 스냅샷 기능 제공
- 프로토콜
    - NFS : 리눅스, IP로 접근
    - CIFS : 윈도우, ID&PW로 접근스

## Data Teleporter

- 대용량 데이터 이전할 때
- 네트워크 비용 절감

## Backup

- 서버 내 파일 및 Preinstall DB에 대한 백업 설정

# ****12강.(Storage) Object Storage 및 NAS Storage 생성 및 활용 데모****

## Object Storage

1. 이용 신청
2. 버킷 신청
3. S3 browser로 접속
4. 마이페이지 → API 인증키, Secret key → 입력

## NAS

1. NAS 볼륨 생성 : 마운트 포인트 생성
2. 스냅샷 생성 설정
3. 이벤트 설정 : 디스크 용량이 임계치에 도달했을때 알람