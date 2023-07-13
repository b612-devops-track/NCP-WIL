# Storage 서비스 소개
클라우드 상에서 데이터를 안전하게 저장하고 활용할 수 있는 서비스들이 집합되어 있다.

## Object Storage
- 인터넷 상에 데이터를 저장하고 사용할 수 있도록 구축된 오브젝트 스토리지
  - 객체 기반의 무제한 파일 저장 스토리지
  - 콘솔, RESTful API, SDK 등의 다양한 방법으로 오브젝트들을 관리하고, 저장된 파일은 각 파일마다 고유한 접근 URL이 부여되어 인터넷 상에서 여러 사용자가 쉽게 접근 가능
  - 정적 웹 사이트 호스팅 가능
- Object Storage 특징
  - S3 Compatibility API 지원
  - Data Lifecycle 지원
  - Sub Account와의 연동으로 접근 제어 가능
  - CDN, VOD Transcoder, Image Optimizer, Cloud Hadoop, Cloud Log Analytics와 같은 네이버 클라우드 플랫폼 내 다양한 상품과 통합/연계 지원

## Archive Storage
접근성이 떨어지는 데이터를 장기 백업이나 장기 보관 용도로 사용한다. 그렇기에 자주 사용되지 않는 데이터를 저장하기에 적합하다.

- 데이터 이카이빙 및 장기 백업에 최적화된 스토리지 서비스
  - AWS glacier에 대응되는 제품
  - Infrequent Data 백업 및 Archiving Data 보관을 주 목적으로 하는 스토리지
  - Object Storage보다 데이터 저장 비용은 저렴. 데이터 처리 API 비용은 비쌈
- Archive Storage 특징
  - 콘솔, API, CLI, SDK를 이용해 데이터 관리 가능
  - 데이터 최소 보관 기간없이 사용할 수 있음
  - 오브젝트 생명 주기 관리
  - Sub Account 연동을 통한 권한 관리 기능 제공

## NAS
- 다수의 서버에서 공유하여 사용할 수 있는 스토리지
  - 최소 500GB에서 10TB까지 구성 가능, 추가능 100GB 단위로 추가 가능
  - NAS 가용량 안에서 생성된 스냅샷 이미지 이용해서 데이터에 대한 복구 기능 제공
  - 프로토콜은 NFS/CIFS 제공
  - 서버 사설 IP 이용한 ACL 오픈으로 타 계정 서버에도 마운트하여 사용 가능
- Block Storage vs NAS

||추가 스토리지|NAS|
|---|:----:|:-----:|
|장점| 적은 용량 추가 가능(최소 10GB)| 공유 가능 </br> 동적 볼륨 사이즈 조정 가능 </br> 자동 스냅샷 기능 제공 </br> 이벤트 알람 기능 제공|
|단점| 공유 불가능| 최초 큰 용량 제공(초기 500GB 생성, 100GB 단위 증가)

## Data Teleporter
대용량의 데이터를 네이버 클라우드 플랫폼으로 이관할 때 사용하는 서비스이다.

- 대용량 데이터(최대 100T) 이전을 위한 전용 어플라이언스 대여 서비스
- 네트워크 비용 절감, 안전하고 빠른 데이터 이관이 가능한 서비스
- 이관 데이터를 Object Storage/Archive Storage/NAS에 Import

## Backup
서버 내 파일 및 Preinstall DB에 대한 백업 설정

- 백업 요청서 작성하여 서버 Agent를 설치하면 끝
- 백업 수행 주기로 8가지 옵션 제공
- 최대 24주까지 백업 파일 보관 가능