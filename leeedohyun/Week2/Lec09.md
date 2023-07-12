# 데이터베이스 소개
2가지 형태로 제공한다. 하나는 서버 이미지 형태로 제공하고 다른 하나는 완전 관리형 데이터베이스 서버 형태로 제공한다. 둘의 차이점은 완전 관리형 데이터베이스는 자동 Fail-over, 백업이 데이터베이스 서버를 만들 때 손쉽게 만들 수 있도록 제공한다. 지금은 완전 관리형 데이터베이스에 대해서만 알아보자.

## CloudDB for MySQL
자동 Fail-Over를 지원하고 사용자 환경에 맞는 구성이 가능하다.

- 최대 32vCPU에 256GB 메모리 지원. 6TB 자동 디스크 확장(Standard, High Memory)
- 자동 Fail-Over를 지원하며 최대 5대까지 복제 Slave(Read Only) 확장 가능
- Private Load Balancer를 이용해서 Read 부하 분산 가능
- 자동 백업 주기를 설정할 수 있으며, 최대 30일 백업 파일 보관

<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/e985878b-1de2-41c0-b0e1-697e4bcb77c3">

위의 그림을 보면 알 수 있듯이 고가용성을 유지하기 위해서는 마스터 db와 스탠바이 마스터 db를 생성해야 한다. 만약 마스터 db가 장애 발생하면 스탠바이 마스터 db가 마스터 db로 롤을 변경한다. 스탠바이 마스터 db가 마스터 db로 오면서 스탠바이 마스터 db를 생성해서 고가용성을 유지할 수 있도록 설정을 유지하고 진행한다.

### 부가적인 기능
1. Master DB Failover
- 콘솔에서 수동으로 Failover를 실행할 수 있다.
- 서비스 오픈 전에 Master DB 장애로 Failover가 발생하는 상황을 재현하여 애플리케이션에 영향이 없는지 사전에 점검 가능

2. DB Process 모니터링
- DB Server를 연결하여 수행 중인 Query를 확인할 수 있다.
- Slow Query 로그 외에도 특정 시점에 어떤 Query가 수행 중인지 확인할 수 있어 DB 상태를 점검하는데 도움을 받을 수 있다.

3. Standard Alone 서버 생성
- 단일 서버 생성도 가능
- 데이터가 삭제되어도 백업 보관일 설정 내에서 1분 단위로 데이터를 시점 복원할 수 있다.

4. Multi zone 구성 제공
- 액티브 마스터 DB와 스탠바이 마스터 DB를 다른 Zone에 생성하여 Zone 장애 발생 시 데이터베이스 가용성을 유지

5. 로그 로테이션 기능 개선
- 로그 로테이션 기능은 Error Log, Slow Log, General Log를 일별 또는 사이즈로 설정할 수 있다.

## Cloud DB for Redis
완전관리형 / 인메모리 캐시 서비스, 

- Redis가 제공하지 않는 자동 Fail-over 기능을 독자적으로 개발하여 제공함으로써 장애 발생 시에도 안정적인 서비스 제공
- 설치 후 Redis와 OS 모니터링을 이용할 수 있으며 장애 또는 이벤트 발생 시 사용자의 메일, SMS로 장애 알람
- 네이버 서비스에서 오랜 시간 검증된 Redis 설정을 기본으로 지원
- VPC 환경 하에 Redis Cluster 지원
- Redis Cluster는 Redis 설치를 실행하는 방법을 제공하며 데이터는 여러 Redis 노드에서 자동으로 분할
  - 데이터를 여러 대의 장비에서 처리함으로써 특정 데이터에 집중되는 트래픽을 서버가 나누어 처리
  - 서버를 하나로 묶어 하나의 시스템처럼 동작하게 함으로써 클라이언트에게 고가용성을 제공

## Cloud DB for MS-SQL
- 안정적인 서비스 제공을 위해 장애 발생 시 자동 Fail-over 기능 제공(Principle DB와 Mirror DB 총 2대 생성)
- 설치 후 즉시 MSSQL과 OS 모니터링을 이용할 수 있으며, MSSQL의 동작 상황을 그래프를 통해 손쉽게 확인 가능
- 1분 단위의 쿼리 레벨 성능 분석 지원하여 서비스 성능과 안정성을 향상

<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/875094ea-8571-452f-89ab-d161043fc172">