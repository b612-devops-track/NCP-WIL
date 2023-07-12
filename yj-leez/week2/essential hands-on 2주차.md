# essential hands-on 2주차

## 7강 Storage 서비스 소개

### Object Storage

- 객체 기반의 계층 없는 무제한 파일 저장 스토리지
- 콘솔, RESTful API, SDK 등의 다양한 방법으로 오브젝트들을 관리하고, 저장된 파일은 각 파일마다 고유한 접근 URL이 부여되어 인터넷상에서 여러 사용자가 쉽게 접근 가능
- NCP - Object Storage 특징
    - S3 Compatibility API 지원 → 이미 S3 Storage를 사용하고 있는 사람들도 Object Storage를 관리할 수 있음
    - Sub Account와의 연동으로 접근 제어 가능
    - NCP 내 다양한 상품과 통합/연계 지원

### Archive Storage

- AWS glacier에 대응되는 제품
- Infrequent Data 백업 및 Archiving Data 보관을 주 목적으로 하는 스토리지 → 오래 사용하지 않는 데이터를 저장하는데 주 목적
- Object Storage 보다 데이터 저장 비용은 저렴, 데이터 처리 API 비용은 비쌈
- 오브젝트 생명주기 관리가 가능함

### NAS

- 다수의 서버에서 공유하여 사용할 수 있는 스토리지
- 공유가 불가능한 스토리지와 다르게 공유 가능 but 최초 용량이 큼
- 가용량 내 자동 스냅샷 기능 제공 → 데이터에 대한 복구 기능 제공
- 프로토콜 : NFS/ CIFS

### Data Teleporter

- 대용량 데이터 이전을 위한 전용 어플라이언스 대여 서비스

## 8강

### Cloud DB for MySQL

- 완전관리형 데이터베이스 서버로서, 자동 Fail-over서비스(→ 최대 5대까지 확장 가능)와 자동 백업 서비스 제공
    
    ![Untitled](essential%20hands-on%202%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20420bf6acdba8479590cb62e34fc49a72/Untitled.png)
    
- Private Load Balancer를 통해 Read 분산 가능
- 제공하는 부가적인 기능
    - Master DB Failover: Failover가 잘 작동되는지 콘솔에서 확인 가능
    - DB Processing 모니터링: DB server 연결하여 수행중인 query 확인 가능
    - Stand alone 서버 생성: 단일 서버 생성 가능
    - 액티브 마스터 DB와 스탠바이 마스터 DB를 다른 존에 생성가능하게끔 → Zone 장애 발생 시에도 데이터베이스 가용성 유지
    - 로그로테이션 기능: 로그 로테이션 기능은 Error Log, Slow Log, General Log를 일별 또는 사이즈로 설정 가능

### Cloud DB for Redis

- 완전 관리형 클라우드 인메모리 캐시 서비스
- Redis가 제공하지 않는 자동 Fail-over 기능을 지원하여 장애발생 시에도 안정적인 서비스 제공
- MySQL 서버와 마찬가지로 모니터링 기능 제공
- VPC 환경 하에서 Redis Cluster 제공
    - Cluster 형태로 생성하고 관리 가능 → 데이터를 여러 Redis 노드에서 자동 분할
        - 데이터를 여러 대의 장비에서 처리함으로써 특정데이터에 집중되는 트래픽을 서버가 나누어 처리
        - 서버를 하나로 묶어 하나의 시스템처럼 동작하게 함으로써 클라이언트에게 고가용성을 제공

### Cloud DB for MySQL

- 완전관리형 데이터베이스 서버로서, 자동 Fail-over서비스와 자동 백업 서비스 제공
- 모니터링 기능 제공

## 11강 ****Management 서비스 소개****

### Monitoring 기능

- 클라우드 리소스 상태 모니터링 서비스 제공, Monitoring API 제공
- 통합화된 대시보드 → Cloud Insight

### Cloud Insight

- 통합 관리 모니터링 서비스
- 네이버 클라우드 플랫폼에서 만든 Basic Metric 뿐만 아니라, 사용자 설정에 따른 Custom Metric 설정도 가능
- Event Rule 설정 가능 → Event 발생 시 알람 제공

### Sub Account

- 동일한 인프라를 여러 명이서 관리할 때, 해당 관리자가 맡고 있는 역할에 맞게 권한을 부여하는 서비스 → 역할별로 권한 분리
- 2차 인증 기능 제공

### Web service Monitoring System (WMS)

- 시나리오 기반 모니터링을 제공하여, 사용자 이용 패턴에 따른 각 기능별 모니터링 수행 가능

### Cloud Activity Tracer

- root 계정 뿐만 아니라 sub 계정들이 어떤 서비스를 어떤 액션을 취했는지 로그 형태로 수집, 제공하는 서비스

### Resource Manager

- NCP 내 생성한 모든 리소스들을 한 눈에 볼 수 있는 통합관리 서비스 (= 기준이 리소스인 Cloud Activity Tracer)

## 13강 ****Global 및 Security 서비스 소개****

### Global

- Global Latency Status : NCP 국가 간 전용선 응답시간을 실시간으로 제공

### Security - Safer

- 보안 상 위협될 수 있는 사항들을 사전에 점검해 볼 수 있도록 제공되는 서비스
- Site Safer: 고객의 웹페이지에 악성코드가 있는지 주기적으로 검사
- App Safer: 고객의 App 실행 모바일 환경에 대한 보안 위협 여부를 실시간으로 탐지
- File Safer: 고객의 웹페이지에 업/ 다운로드 되는 파일에 대한 체크

### Security - Checker

- 보안적으로 체크해봐야할 사항에 대해 리포팅 형태로 제공되는 서비스
- Web Security Checker: 웹페이지에 모의해킹 진행 후 취약점이 없는지 체크
- System Security Checker: OS 및 WAS 설정에 대한 취약점 점검
- App Security Checker: 고객의 모바일 App을 분석하여 자동으로 보안 취약점을 점검할 수 있는 서비스로 리포트 형태로 제공
- Certificate Manager: SSL 인증서 등록 및 관리 통합
- Security Monitoring