# NCP Essential Hands-on 7강~13강

# Object Storage

**인터넷상에 원하는 데이터를 저정하고 사용할 수 있도록 구축된 오브젝트 스토리지**

- 객체 기반의 무제한 파일 저장 스토리지
- 콘솔, RESTful API, SDK 등의 다양한 방법으로 오브젝트들을 관리하고, 저장된 파일은 각 파일마다 고유한 접근 URL이 부여되어 인터넷상에서 여러 사용자가 쉽게 접근 가능
- 정적 웹 사이트 호스팅 가능

Object Storage 특징

- S3 Compatibility API 지원
- Data Lifecycle 지원
- Sub Account와의 연동으로 접근 제어 가능
- CDN, VOD Transcoder, Image Optimizer, Cloud Hadoop, Cloud Log Analytics와 같은 네이버클라우드플랫폼 내 다양한 상품과 통합/연계 지원

# Archive Storage

**데이터 아카이빙 및 장기 백업에 최적화된 스토리지 서비스**

- AWS glacier에 대응되는 제품
- Infrequent Data 백업 및 Archiving Data 보관을 주 목적으로 하는 스토리지
- Object Storage보다 데이터 저장 비용은 저렴하고 데이터 처리 API 비용은 비쌈

**Archive Storage 특징**

- 콘솔, API(swift, s3), CLI, SDK클 이용해 데이터 관리 가능
- 데이터 최소 보관 기간 없이 사용할 수 있음
- 오브젝트 생명주기 관리
- Sub Account 연동을 통한 관리 기능 제공

# NAS

**다수의 서버에서 공유하여 사용할 수 있는 스토리지**

- 스토리지 내부에서 스냅샷 이미지를 이용해 데이터 복구 가능
- 프로토콜 NFS(리눅스), CIFS(window) 제공

# Data Teleporter

**대용량 데이터 이전을 위한 효과적인 솔루션**

- 대용량 데이터 이전을 위한 전용 어플라이언스 대여 서비스
- 이관 데이터를 Object Storage / Archive Storage / NAS에 Import

# Backup

**서버 내 파일 및 Preinstall DB에 대한 백업 설정**

# DataBase

MySQL: 완전관리형 데이터베이스 서버

Redis: 완전관리형 데이터베이스, 인메모리 캐시 서비스, Fail-over 기능을 제공하지 않는다

# 모니터링 서비스

**클라우드 리소스 상태 모니터링 수행**

# Sub Account

**서브 계정 별 역할 부여를 통한 리소스 관리**

# Web service Monitoring System(WMS)

**고객의 웹페이지 품질 측정 도구**

# Cloud Activity Tracer

**루트 계정, 서브 계정 등 다양한 계정의 활동 로그 수집**

# Resource Manager

**리소스별 활동 로그 수집**

- 리소스들을 통합적으로 관리할 수 있도록 제공하는 서비스

# Security Service

- Site Safer: 고객의 웹페이지에 악성 코드가 있는지 주기적으로 검사
- App Safer: 고객의 APP 실행 모바일 환경에 대한 보안 위협 여부를 실시간으로 탐지
- File Safer: 업로드/다운로드 되는 파일의 악성코드 여부 탐지

# Checker Service

- Web Security Cheker: 모의 해킹을 통한 고객의 웹사이트 보안 취약점 진단
- System Security Cheker: 고객의 시스템 보안 취약점 진단
- App Security Cheker: 고객의 모바일 앱 보안 취약점 진단
- Certificate Manager: SSL 인증서 등록 및 관리 통합
- Security Monitoring
- SSL VPN