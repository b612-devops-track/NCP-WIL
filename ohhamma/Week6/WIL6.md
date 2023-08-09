# ****17강. (Management) Management 상품군 내 서비스 소개****

## Monitoring

- 클라우드 리소스 상태 모니터링 수행
- 기본 모니터링 : 기본 상품별 모니터링 그래프 확인
- 상세 모니터링 : 클라우드 인사이트, 과거 데이터, 알람 서비스
- 모니터링 API 제공

## Sub Account

- 특정 팀에 대해서 특정 권한 부여 (세분화)
- 다수의 사용자에게 역할 부여
- Cloud Activity Tracer에서 확인 가능

## Web service Monitoring System (WMS)

- 시나리오(이벤트) 기반 웹서버 품질 체크
- 글로벌 사이트에 대한 품질도 확인 가능
- 에러 이벤트에 대한 내용도 확인 가능

## Cloud Activity Tracer

- ncp 안에서 사용자의 활동 로그 수집
- 로그를 엑셀로 다운받거나 object storage로 export 가능

## Resource Manager

- 어떤 리소스를 사용하고 있는지 확인

## Cloud Insight

- 통합 관리 모니터링 서비스
- 임계치 설정 가능
- 대시보드 커스터마이징 기능
- event 발생시 알람 제공

# ****18강. (Management) Cloud Insight 서비스 신청 및 설정 데모****

- 각 상품마다 모니터링 항목 존재
    - 기본 모니터링 확인 가능
    - 상세 모니터링은 Cloud Insight 신청 필요
- Cloud Insight (Event Rule 생성)
    1. 감시 대상 설정
    2. 감시 항목 및 조건 설정
    3. 액션

# ****19강.(Analytics) Analytics 상품군 내 서비스 소개****

## Data Analytics Service (DAS)

- 웹사이트 데이터 분석 서비스
- 고객 행동 데이터 분석 환경 제공
- 행동패턴까지 분석 가능

## ELSA

- Effective Log Search & Analytics
- 앱이 죽는 이유를 분석해줌
- App Crash Report 제공

## CLA

- Cloud Load Analytics
- 서버에 남는 다양한 로그들을 통합 수집
- 커스텀 로그 기능 제공
- 30일동안 보관, 최대 100G 수집

## RUA

- 웹페이지 분석 도구
- 얼마나 많은 사용자들이 어디를 접속했는지

## Cloud Hadoop

- 하둡 클러스터 편리하게 생성 및 관리
- 사용자 목적에 맞게 사용 (총 4가지)

## Cloud Search

- 네이버 검색엔진 사용 가능
- 네이버 형태소 분석 처리기 기반으로 한국어 처리

## Elasticsearch Service

- Elasticsearch 클러스터 손쉽게 배포, 보로, 운영 및 확장 가능

## Cloud Data Streaming Service

- Apache Kafka Cluster 쉽고 간편하게 구축

# ****20강. (Analytics) Cloud Log Analytics 활용법 데모****

1. management → log 수집 설정
2. server에서 agent 설치
3. search → log 확인

# ****21강.(Security) Security 서비스 소개****

<aside>
💡 **safer** vs **checker**

- safer: 안전하게 지킨다
- checker: 안전한지 진단
</aside>

## Site Safer

- 고객 웹페이지에 악성 코드가 있는지 주기적으로 검사
- 있다고 판단되면 빠르게 notifier 보냄

## App Safer

- 고객의 app 실행 모바일 환경에 대한 보안 위협 여부 탐지
- 치팅 프로그램, 핵 검사 - 무결성 검사

## File Safer

- 업로드 / 다운로드 되는 파일의 악성코드 여부 탐지
- 중간에 존재하는 필터 서비스

## Web Security Checker

- 고객의 웹사이트 보안 취약점 진단
- 모의해킹으로 취약점 점검
- 내 소유여야만 실행 가능

## System Security Checker

- 실행파일로 시스템이 안전한지 확인
- 설정파일 내용 점검
- 점검에 필요한 Agent 설치 필요
- 수정 가이드 제공

## App Security Checker

- 앱이 보안에 문제가 없는지 확인
- 앱 등록 전 보안 심사할 때 사용

## Certificate Manager

- SSL 인증서 등록 및 관리 통합
- 인증서 한번 등록 이후 바로바로 이용 가능
- 인증서 만료 관련 메일 발송

## Security Monitoring

- basic : IDS 이벤트 감지, Anti-Virus
    - 문제가 생기면 고지
- managed : IDS, DDos, IPS, WAF, Anti-Virus
    - 주기적으로 리포트 제공)

## SSL VPN

- 서버 접속시 안전하게 접속 가능
- 1차 인증 & 2차 인증 제공

## WebShell Behavior Detector

- 외부로부터의 웹 쉘 공격을 실시간 탐지
- 행위 기반으로 탐지, 의심되면 파일들을 격리

# ****22강.(Media) 미디어 서비스 소개****

## Live Station

- 실시간 방송을 위한 플랫폼
- CDN을 통해 안정적인 송출 가능
- 스트림 정보 제공
- 타임머신 기능
- 두가지 프로토콜 제공

## VOD Station

- Object storage에 보관된 영상 파일을 이용하여 스트리밍 서비스 제공
- DRM 적용 기능 제공

## VOD Transcoder

- 영상 하나로 다양한 포맷 만들때 사용
- 디바이스에 맞는 해상도에 transcoding

## Image Optimizer

- 이미지 썸네일 만들어줌
- CDN으로 배포
- 보다 편리하게 URL 사이트 만들수있음
- 이미지 보정 기능 제공
- 이미지 아웃풋 접근 x
- 비즈니스에 사용

## Video Player

- 나만의 커스텀 비디오 플레이어 만들어줌
- ncp 플랫폼에 최적화
- 커스텀 플레이어 Object Storage에 저장