# ****13강. (Cloud DB) 완전 관리형 서비스 Cloud DB 소개****

## 완전관리형 DB

- 이중화
- slave db 구성 가능 : read query 분산
- 백업

## Cloud DB for MySQL

- 자동 fail-over 지원
- 서버 어드민 접근 x
- 최소 10GB 최대 6TB (10GB 단위 증가)
- 최대 5대 slave 확장 가능
- 기본 포트 3306

### Master DB Failover

- manual하게 강제로 master db failover
- master db 장애 상황 재현 및 사전 점검

### DB Process 모니터링

- 특정 시점에 수행중인 쿼리 모니터링 가능

### Stand Alone 백업

- (default) master stand by
- stand alone : 오로지 master
    - 새로운 백업파일도 master만

### VPC 추가 지원

- 멀티존 지원 : master db 서버를 서로 다른 zone에
    - 각각 kr1 zone, kr2 zone subnet
- public/private subnet 차이
    - public → public 도메인 부여

## Cloud DB for Redis

- redundancy : 서버 이중화, 서비스 연속성 유지
- cluster 미지원
    - cluster의 장점 : 메모리 증산 가능
- 기본 포트 6379

### VPC 추가 지원

- cluster 지원
- 샤드 최소 3개
- HA 구성
- 반드시 private subnet에 구성
    - cache db이기 때문 : 외부에서 접근 x

## Cloud DB for MS-SQL

- 기본 포트 1433
- principal / mirror db
- 이중화 & 백업 지원
- 쿼리 성능 분석 가능

### VPC 추가 지원

- MSSQL 2019 지원
- private / public subnet 둘 다 위치 가능

# ****14강. (Cloud DB) Cloud DB For MySQL 생성 및 접속 데모****

1. DB server 생성 (private)
2. ACG 설정 수정 : 3306 포트 open
3. private 도메인으로 접속
4. Monitoring query timeline으로 쿼리 확인 가능

# ****15강.(AI/Application) 네이버클라우드플랫폼 AI/Application 서비스 소개****

# AI & Application

- NCP AI
    - 플랫폼 Clova
    - 번역 서비스 Papago
- NCP Application
    - Geolocation
    - Maps
    - nShortURL
    - SENS
    - Search Trend

### Geo Location

- 사용자 IP를 통해 위치 정보 제공
- 동까지 확인 가능

### SENS

- Simple & Easy Notification Service
- SMS나 APP Push 쉽게 전송

### Outbound Mailer

- 대량 메일 발송
- 광고메일 발송 템플릿 & 법적기능
- 치환 태그 기능 : `${name}`
    - csv 파일 사용

### 챗봇

- CS, 주문시스템 같은 고객 대응을 로봇으로 대체
- 학습을 통해 적절한 답변 자동화

### Clova Speech Recognition (CSR)

- 음성 → 텍스트 변환
- 긴 음성 인식 → 텍스트 추출

### Clova Voice

- 텍스트 → 자연스러운 음성으로 변환
- 감정 파라미터 제공

### Clova Dubbing

- 컨텐츠에 나레이션 추가 기능
- 더빙 편집기 제공

### Clova Face Recognition

- 입력된 데이터 → 얼굴 인식 및 관련 정보 제공
- 유명인 얼굴 인식
- 얼굴 감지

### Clova OCR

- 문서 스캔
- 지정된 템플릿에 맞추어 데이터 추출 및 db화

### Papago NMT (Neural Machine Translation)

- 통계 기반 번역
- Rest API 제공

### Pose Estimation

- 이미지내 주요 신체 영역 인식 및 좌표로 변환

### Object Detection

- 이미지내 객체 탐지 및 분석

### Search Trend

- 네이버 통합검색 서비스 조회 결과에 대한 통계 API

### nShortURL

- 단축 URL
- QR코드 이미지 무료로 제공

# ****16강.(AI/Application) Cloud Outbound Mailer 활용 데모****

1. 템플릿 등록
    1. 치환태그 사용 가능
    2. 광고 메일인 경우, 수신거부 안내문도 있음
2. 파일 업로드를 통한 대량 메일발송
    1. 치환태그에 들어갈 내용 채워넣기
3. 발송하기
    1. 예약발송 가능