# ****7강. Storage 서비스 소개****

## Object Storage
- 사용자 인터넷상에 원하는 데이터를 저장하고 활용 가능
- 무제한에 가까운 확장성
- Sub Account : 각 역할에 맞는 권한만 부여
    - 인프라를 안전하게 관리

## Archive Storage
- 데이터 아카이빙 및 장기 백업에 최적화
- AWS glacier에 대응
- 자주 사용되지 않는 데이터를 보관하기 위한 용도
- 오브젝트 생명주기 관리
    - object management

## NAS
- 여러 서버에서 공유 가능
- 500GB ~ 10TB
- 스냅샷 기능 내장 : 백업, 복구 용도
- NFS : 리눅스 서버끼리 공유할 때 사용
- CIFS : 윈도우 서버끼리 공유할 떄 사용
- 타 계정 서버에도 마운트하여 사용 가능
- 이벤트 알람 기능 제공

## Data Teleporter
- 대용량 데이터 이전을 위해 사용
- 안전하고 빠른 데이터 이관

## Backup
- 백업 요청서 작성하여 신청해야함 (고객센터)
- 최대 24주까지 백업 파일 보관


# ****8강. (데모) 오브젝트 스토리지 활용안****


# ****9강. 데이터베이스 소개****
- 완전 관리형 데이터베이스 서버 형태

## Cloud DB for MySQL
- 자동 Fail-Over 및 자동 백업 설정 지원
- Slave database 최대 5개
- private load balancer로 부하 분산 가능
- 최대 30일 백업 파일 보관
- 고가용성 유지 : 마스터DB & 스탠바이마스터DB

### 1. Master DB Failover
- Failover 테스트 가능
- 콘솔에서 테스트

### 2. DB Process 모니터링
- 수행중인 쿼리 확인 가능

### 3. Stand Alone 서버 생성
- 고가용성 유지 x
- 서버 1대만으로 운영

### 4. Multi zone 구성 제공
- 마스터DB & 스탠바이마스터DB 서로 다른 zone에 배치
- 지속적으로 서비스 제공 가능

### 5. 로그 로테이션 기능 개선
- error log 등 로그 설정 가능

## Cloud DB for Redis
- 완전 관리형 DB
- 인메모리 캐시 서비스
- Redis가 제공하지 않는 자동 Fail-over 기능 제공
- Cluster 형태로 생성 및 관리
    - 여러 Redis 노드에서 자동으로 분할
- client에게 고가용성 제공

## Cloud DV for MS-SQL
- 완전 관리형 DB
- 자동 Fail-over 기능 & 자동 백업 기능 제공
- 2대의 DB 서버로 고가용성 서버 : principal 서버 & mirror 서버
- 모니터링 기능 내장


# ****10강. (데모) 데이터베이스 생성 및 연결****


# ****11강. Management 서비스 소개****

## (구) Monitoring
- 서버에 대한 다양한 metric을 대시보드 형태로 제공
- 통합화된 대시보드 제공하기 위해 Cloud Insight 서비스 출시

## Cloud Insight
- 통합 관리 모니터링 시스템
- basic metric & custom metric
- event rule 설정
- event 담당자 지정 가능
    - event 발생 시 담당자에게 sms, email로 알람 제공

## Sub Account
- 동일한 인프라를 여러명이 관리
- 각 관리자 역할에 맞게 권한 부여
- 2차 인증 기능 제공
    - OTP number까지 기입
- 서브 계정의 작업을 Cloud Activity Tracer로 로그 형태로 확인 가능

## Web service Monitoring System (WMS)
- 관리중인 웹페이지가 잘 동작하는지 모니터링
- 시나리오 기반의 모니터링 가능
    - 사용자의 이동패턴에 대해서도 모니터링 가능

## Cloud Activity Tracer
- root 계정뿐만 아니라 서브 계정에서도 액션을 로그 형태로 남겨놓음
    - 계정별 액션을 살펴봄
- 약 155 종류의 액션 로그 수집
- Cloud Log Analytics와의 연동 : 로그를 한번에 관리 가능

## Resource Manager
- 각 서비스 별로 액션을 살펴봄
- 목적에 따라 자원 그룹화 가능
- 리소스별 생성 및 변경 내용 확인 가능


# ****12강. (데모) 상세모니터링 설정****


# ****13강. Global 및 Security 서비스 소개****

## Global Latency Status
- 일본 싱가폴 독일 홍콩 미국 등
- 글로벌 region끼리 전용선 구축
- 안정적인 네트워크 트래픽

## Site Safer
- 웹페이지에 악성 코드가 있는지 주기적으로 검사
- 뉴스 쇼핑 광고에 실제로 적용

## App Safer
- APP 환경에 대한 보압 위협 여부를 탐지

## File Safer
- 업로드 / 다운로드 되는 파일의 악성코드 여부 탐지

## Web Security Checker
- 모의해킹 시행
- 웹 취약점 점검 및 진단

## System Security Checker
- 고객의 OS, WAS 설정에 대한 취약점 점검
- 리포트 형태로 취약점과 보완법 제공

## App Security Checker
- 고객의 모바일 APP에 대한 보안 취약점 진단
- 리포트 형태로 결과 제공
- APP 출시 전에 확인할 때 유용

## Certificate Manager
- SSL 인증서 통합적으로 관리
- 인증서 만료 전에 알람 메일 전송

## Security Monitoring

### Basic
- NCP 인프라를 사용하는 누구나 무료로 사용 가능
- Anti-Virus : 윈도우OS에 한해 오피스 스캔 지원
- IDS 이벤트 탐지

### Managed
- 유료
- IDS 이벤트 탐지
- DDoS 이벤트 탐지
- IPS 이벤트 탐지
- 침해 사고 기술 지원
- WAF
- Anti-Virus

## SSL VPN
- 10 대역의 28bit VPN IP 대역 제공
- 3개, 5개, 10개 ID 생성 가능
- 1차 인증, 2차 인증 제공