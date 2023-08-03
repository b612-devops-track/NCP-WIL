## 13강

Cloud DB for MySQL, Cloud DB for Redis, Cloud DB for MSSQL
  * 자동 Fail-Over 지원 및 사용자 환경에 맞는 구성 가능
  * 최대 32vCPU에 256GB 메모리 지원, 6TB 자동 디스크 확장(Standard, High Memory)
  * 자동 Fail-Over를 지원하며 최대 5대까지 복제 Slave 확장 가능
  * Private Load Balancer를 이용해서 Read 부하 분산 가능
  * 자동 백업 주기를 설정할 수 있으며, 최대 30일 백업 파일 보관

Master DB Failover
  * 콘솔에서 수동으로 Failover를 실행할 수 있다
  * 서비스 오픈 전에서 Master DB장애로 Failover가 발생하는 상황을 재현하여 Application에 영향이 없는지 사전에 점검을 할 수 있다

DB Process 모니터링
  * DB Server 연결하여 수행 중인 Query를 확인할 수 있다.
  * Slow Query로그 외에도 특정 시점에 어떤 Query가 수행 중인지 확인할 수 있어 DB 상태를 점검하는데 도움을 받을 수 있다

Stand Alone 백업
  * Stand Alone 서버도 DB 백업을 사용할 수 있다.
  * 데이터가 삭제되어도 백업 보관일 설정 내에서 백업으로 데이터를 복구 할 수 있다.

Subnet - public subnet, private subnet</br>
MySQL는 public subnet, private subnet에 둘 다 넣을 수 있다</br>
Public Subnet과 Private Subnet에 구성하는 것의 차이</br>
Public Subnet에 구성하는 경우 Public 도메인을 구성할 수 있으나 Private Subnet은 구성 불가</br>

Cloud DB for Redis</br>
자동 복구를 통해 안정적으로 운영되는 완전 관리형 클라우드 인메모리 캐시 서비스</br>
Redis가 제공하지 않는 자동 Fail-over 기능을 독자적으로 개발하여 제공함으로써 장애발생 시에도 안정적인 서비스 제공</br>
Redis는 캐시 : 캐시를 외부에서 접근하는 것은 일반적으로 제공되는 방식이 아니다</br>
Redis Cluster 제공</br>

VPC 내 Private Subnet에 구성</br>

샤드 최소 3개
Config Group을 통해 설정 적용
HA 구성 지원
Online Cluster 변경 미지원(향후 지원 예)

Cloud DB for MS-SQL
네이버 서비스에서 검증된 최적화된 설정을 통해 안정적으로 운영되며, 장애가 발생하면 자동을 복구

AI & Application
네이버클라우드 플랫폼 AI
AI플랫폼인 Clova, 번역 서비스인 Papago

딥러닝을 위한 Tensorflow가 탑재된 서버 이미지 제공(CentOS 7.3, Ubuntu 16.04)

네이버클라우드플랫폼 Application
네이버에서 사용하는 기술과 서비스를 API로 제공
Geolocation, Maps, nShortURL, SENS, Search Trend 등 제공

## 14강

Cloud DB For MySQL 생성 및 접속 데모

## 15강

Clova Face Recognition</br>
입력된 비전 데이터를 통해 얼굴을 인식하고 관련된 다양한 정보를 제공</br>
크게 두 가지 서비스를 제공 : 1) 유명인 얼굴인식, 2) 얼굴감지</br>
네이버가 보유한 대량의 이미지 DB를 통해 국내에서 가장 뛰어난 유명인 얼굴 인식과 정확한 얼굴 감지 기능 제공</br>
AI기술인 머신 러닝을 사용하여 지속적으로 학습</br>
RESTful형태로 API제공, 고객의 서비스에 얼굴 인식 및 얼굴 감지 기능을 간단히 적용 가능</br>

Pose Estimation</br>
이미지내의 주요 신체 영역을 이식하고 해당 영역을 좌표로 변환</br>
이미지를 분석하여 신체 영역 좌표를 결과값으로 제공</br>
RESTful API 방식으로 제공</br>
이미지는 2MB 이하로 제공</br>

nShortURL</br>
길고 복잡한 URL을 간단하고 짧게 변경하는 API</br>
긴 URL을 단축하여 글자 수 제한이 있는 SMS를 전송하거나 SNS를 이용 시 용이</br>
최근 유해 정보를 기반으로, 유해성이 필터링된 URL만 생성 가능</br>

REST API 제공</br>
QR코드 이미지를 무료로 함께 생성(단축URL.qr)</br>
Application 당 매일 25,000 건의 서비스 제공(25,000건 이상은 고객지원 문의)</br>

네이버 통합검색 서비스를 통해 수집되는 검색어 통계를 다양한 기준으로 조회하고 활용</br>
대량 메일 발송을 위한 Outbound Mailer</br>
고객 대응에 활용할 수 있는 챗봇</br>

## 16강
(AI/Application) Cloud Outbound Mailer 활용 데모
