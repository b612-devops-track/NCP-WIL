# Associated Course 3주차

## ****13강. (Cloud DB) 완전 관리형 서비스 Cloud DB 소개****

### Cloud DB for MySQL

- 최대 32VCPU에 256GB 메모리 지원, 6TB 자동 디스크 확장 (Standard, High Memory)
- 자동 Fail-Over를 지원하며 최대 5대까지 복제 Slave ( Read Only ) 확장 가능
→ Slave DB에 한해 Private Load Balancer를 이용해서 Read 부하 분산 가능
- 자동 백업 주기를 설정할 수 있으며, 최대 30일 백업 파일 보관
- Master DB Failover : Master DB 장애로 Failover가 발생하는 상황을 재현하여 Application에 영향이 없는지 사전에 점검 가능
- DB Process 모니터링 : 특정 시점에 어떤 Query가 수행 중인지 확인할 수 있어 DB 상태를 점검하는데 도움을 받을 수 있음
- Stand Alone 백업 : Stand Alone 백업으로 설정 시 Stand By 서버 없이 Master 서버만 존재
데이터가 삭제되어도 백업 보관일 설정 내에서 백업으로 데이터를 복구 가능
- 멀티존 지원 : Master DB 서버 2대를 서로 다른 Zone에 생성하여 높은 가용성 제공
- Public Subnet에도 Private Subnet에도 구성할 수 있으나, Public에서만 도메인 구성(외부와의 소통) 가능

### Cloud DB for Redis

- 자동 복구를 통해 안정적으로 운영되는 완전 관리형 **클라우드 인메모리 캐시 서비스**
- Redis가 제공하지 않는 자동 Fail-over 기능을 독자적으로 개발하여 제공함으로써 장애발생 시에도 안정적인 서비스 제공
- 설치 후 Redis와 OS모니터링을 이용 가능
- 기본 포트 : TCP 6379
- Redis Cluster 제공
    - VPC 내 Private Subnet에 구성 ← 캐시이기 때문
    - 샤드 최소 3개
    - HA 구성 지원
    - Config Group을 통해 설정 적용

### Cloud DB for MS-SQL

- Classic은 2016 버전, VPC는 2019 버전 제공
- MySQL과 마찬가지로 Public, Private Subnet에 둘 다 위치 가능
- 네이버 서비스에서 검증된 최적화된 설정을 통해 안정적으로 운영되며, 장애가 발생하면 자동으로 복구
- 안정적인 서비스 제공을 위해 장애 발생 시 자동 Fail-over 기능 제공 ( Principal DB와 Mirror DB 총 2대 생성)
- 1분 단위의 쿼리 레벨 성능 분석을 지원하여 서비스 성능과 안정성을 향상

## ****15강.(AI/Application) 네이버클라우드플랫폼 AI/Application 서비스 소개****

### Geo Location

- 고객서버에서 질의한 IP 주소에 따른 지역정보 DB를 검색해 국가, 시/군/구, 동, 인근 지역의 좌표 정보 전달
- 접속 IP를 기반으로 동까지 확인 가능 (국내), 해외의 경우 주까지 확인 가능

### SENS

- Simple & Easy Notification Service : 웹을 통해서 혹은 API를 이용하여 다수의 사용자에게 SMS, Push 한 번에 발송

### Outbound Mailer

- 광고메일 발송을 위한 템플릿 기능, 법적인 기능 (제목에 광고 문구 삽입 및 수신 거부 기능) 제공

### 챗봇

- 학습을 통해 적절한 답변을 자동화, CSR, CSS와 연동을 통해 메신저 뿐만 아니라 음성 채팅까지 확장 가능
- 라인, 카카오톡, 페이스북 메신저와 연동

### Clova Speech Recognition (CSR)

- 음성을 텍스트로 변환
- 한국어, 영어, 일어, 중국어(간체) 제공, 국내에서 가장 높은 한국어 인식률
- Android 및 iOS SDK 제공
- Rest API 제공

### Clova Speech

- 긴 음성(음성 파일, 영상 파일)을 인식하고 텍스트 추출
    - 높은 성능의 한국어 장문 딕테이션
    - 미디어 인식에 강한 모델, 전화망 음성 인식을 강화한 모델

### Clova Voice

- CSS와 Clova Premium Voice가 통합된 버전
- 텍스트를 음성으로 변환, 총 29가지 음성과 감정 파라미터 제공
- 최대 1000글자 변환 가능 (한 문장에서 사용할 수 있는 최대 글자수는 200자)
- Wav 포맷의 경우 샘플링 Rate 지원

### Clova Dubbing

- 컨텐츠에 나레이션 추가 → 나레이션 음성 추가하는 기능
- 최대 500MB, 20분 이내 영상에 대해 더빙
- 더빙 편집기 제공
- 음성과 다양한 효과음 추가 기능 지원

### Clova Face Recognition

- 입력된 비전 데이터를 통해 얼굴을 인식하고 관련된 다양한 정보를 제공
- 두 가지 서비스를 제공: 1) 유명인 얼굴 인식, 2) 얼굴 감지
- 네이버가 보유한 대량의 이미지 DB 사용/ AI 기술인 머신 러닝을 사용하여 지속적으로 학습
- RESTful 형태로 API 제공, 고객의 서비스에 얼굴 인식 및 얼굴 감지 기능을 간단히 적용 가능

### Clova OCR

- 진보된 템플릿 기능, 지정된 템플릿에 맞추어 데이터를 추출하고 데이터베이스화, 관공서에서 사용

### Papago NMT (Neural Machine Translation)

- 영어, 일어, 중국어 통계 기반 번역,  RESTful API 제공

### Pose Estimation

- 이미지내의 주요 신체 영역을 인식하고 해당 영역을 좌표로 변환, RESTful API 제공

### Obiect Detection

- 이미지내의 객체를 탐지하고 객체를 분석/ 객체를 탐지하여 객체의 이름, 바운딩 박스, 탐지 정확률을 제공

### Search Trend

- 네이버 통합검색 서비스 조회 결과에 대한 통계 API
- 특정 키워드의 검색량을 기간별로 확인 가능
- 연령별, 성별, 검색 시 사용한 디바이스별 세분화 조회 가능
- 키워드 및 세분화 조회를 선택하여 RESTful API로 전달하면, 통계 결과를 리턴
- 직관성을 위해 요청된 기간 중 검색 횟수가 가장 높은 시점을 100으로 두고 상대적 비율로 제공
- Application 당 매일 1,000 건의 서비스 제공 (1,000건 이상은 고객지원 문의)

### nShortURL

- 길고 복잡한 URL을 간단하고 짧게 변경하는 API
- 긴 URL을 단축하여 글자 수 제한이 있는 SMS를 전송하거나 SNS를 이용 시 용이
- Application 당 매일 25,000 건의 서비스 제공 (25,000건 이상은 고객지원 문의)