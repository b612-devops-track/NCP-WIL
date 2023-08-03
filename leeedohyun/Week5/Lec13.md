# (Cloud DB) 완전 관리형 서비스 Cloud DB 소개
## 완전 관리형으로 제공하는 것과 기존의 데이터베이스와의 차이점
1. 이중화, fail-over 기능 지원
2. Slave DB를 구성할 수 있게 된다.
데이터 베이스에 가장 큰 부하는 Read 쿼리가 절대적으로 많이 차지하는데, 한 서버에서 Read와 Write가 이루어진다면 데이터베이스에 부하가 올라가고 그로 인해 장애가 발생할 수 있다. 그래서 Read 쿼리를 분산시키는 것이 중요하다. 이를 위해 Slave 서버 제공한다.
3. 데이터베이스 백업

## Cloud DB for MySQL
- 자동 Fail-Over 지원 및 사용자 환경에 맞는 구성 가능
    - 최대 32vCPU에 256GB 메모리 지원, 6TB 자동 디스크 확장
    - 자동 Fail-Over를 지원하며 최대 5대까지 복제 Slave(Read Only) 확장 가능
    - Private Load Balancer를 이용해서 Read 부하 분산 가능
    - 자동 백업 주기를 설정할 수 있으며, 최대 30일 백업 파일 보관
- Master DB Failover
    - 콘솔에서 수동으로 Failover를 실행할 수 있다.
    - 서비스 오픈 전에 Master DB 장애로 Failover가 발생하는 상황을 재현하여 애플리케이션에 영향이 없는지 사전에 점검할 수 있다.
- DB Process 모니터링
    - DB Server를 연결하여 수행 중인 Query를 확인할 수 있다.
    - Slow Query 로그 외에도 특정 시점에 어떤 쿼리가 수행 중인지 확인할 수 있어 디비 상태를 점검하는데 도움을 받을 수 있다.
- Stand Alone 백업
    - Stand Alone 서버도 디비 백업을 사용할 수 있다.
    - 데이터가 삭제되어도 백업 보관일 설정 내에서 백업으로 데이터를 복구할 수 있다.
- 멀티존 지원
    - Master DB 서버 2대를 서로 다른 Zone에 생성하여 높은 가용성 제공
    - Master DB 서버는 같은 속성의 Subnet에 위치
- Public Subnet과 Private Subnet에 구성하는 것의 차이
    - Public Subnet에 구성하는 경우 Public 도메인을 구성할 수 있으나 Private Subnet은 구성 불가

## Cloud DB for Redis
- 자동 복구를 통해 안정적으로 운영되는 완전 관리형 클라우드 인메모리 캐시 서비스
    - Redis가 제공하지 않는 자동 Fail-Over 기능을 독자적으로 개발하여 제공함으로써 장애 발생 시에도 안정적인 서비스 제공
    - 설치 후 Redis와 OS 모니터링을 이용할 수 있으며 장애 또는 이벤트 발생 시 사용자의 메일, SMS로 장애 알람
    - 네이버 서비스에서 오랜 시간 검증된 Redis 설정을 기본으로 지원
    - Redis Cluster 미지원
    - 기본 포트: Tcp 6379
- Redis Cluster 제공
    - VPC 내 Private Subnet에 구성
    - 샤드 최소 3개
    - Config Group을 통해 설정 적용
    - HA 구성 지원

## Cloud DB for MS-SQL
- 네이버 서비스에서 검증된 최적화된 설정을 통해서 안정적으로 운영되며, 장애가 발생하면 자동으로 복구
    - 안정적인 서비스 제공을 위해 장애 발생 시 자동 Fail-over 기능 제공
    - 설치 후 즉시 MSSQL과 OS 모니터링을 이용할 수 있으며, MSSQL의 동작 상황을 그래프를 통해 손쉽게 확인 가능
    - 1분 단위의 쿼리 레벨 성능 분석을 지원하여 서비스 성능과 안정성을 향상