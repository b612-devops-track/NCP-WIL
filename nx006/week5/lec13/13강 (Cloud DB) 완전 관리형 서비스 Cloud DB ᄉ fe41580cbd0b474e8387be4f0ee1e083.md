# 13강. (Cloud DB) 완전 관리형 서비스 Cloud DB 소개

강의시간: 16:44

## Cloud DB for MySQL

![Untitled](13%E1%84%80%E1%85%A1%E1%86%BC%20(Cloud%20DB)%20%E1%84%8B%E1%85%AA%E1%86%AB%E1%84%8C%E1%85%A5%E1%86%AB%20%E1%84%80%E1%85%AA%E1%86%AB%E1%84%85%E1%85%B5%E1%84%92%E1%85%A7%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20Cloud%20DB%20%E1%84%89%20fe41580cbd0b474e8387be4f0ee1e083/Untitled.png)

- DB의 부하는 Read Query가 많이 차지, 이를 분산시키는 것이 중요함
- Read Query를 분산 가능(Replication, 혹은 NCP에서 Slave Server라고 부름)
- 분단위 복원 및 시점 복원이 가능함

- MySQL의 데이터 볼륨은 자동으로 10GB 단위로 확장됨, 최대 6TB까지 확장 가능함
- 자동 Fail Over를 지원하고 있음
    - 1번이 마스터, 2번이 슬레이브일 때 1번이 죽으면 2번이 자동으로 마스터로 승격
- Private LB로 슬레이브 서버를 하나로 묶을 수 있음
- 단, 마스터가 여러 개일 때는 마스터에 대해서 묶는 건 안 됨(데이터 정합성 문제)

![Untitled](13%E1%84%80%E1%85%A1%E1%86%BC%20(Cloud%20DB)%20%E1%84%8B%E1%85%AA%E1%86%AB%E1%84%8C%E1%85%A5%E1%86%AB%20%E1%84%80%E1%85%AA%E1%86%AB%E1%84%85%E1%85%B5%E1%84%92%E1%85%A7%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20Cloud%20DB%20%E1%84%89%20fe41580cbd0b474e8387be4f0ee1e083/Untitled%201.png)

백업 시에 새로운 DB 서버를 만들고 거기에 복제해서 사용함

![Untitled](13%E1%84%80%E1%85%A1%E1%86%BC%20(Cloud%20DB)%20%E1%84%8B%E1%85%AA%E1%86%AB%E1%84%8C%E1%85%A5%E1%86%AB%20%E1%84%80%E1%85%AA%E1%86%AB%E1%84%85%E1%85%B5%E1%84%92%E1%85%A7%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20Cloud%20DB%20%E1%84%89%20fe41580cbd0b474e8387be4f0ee1e083/Untitled%202.png)

NCP Zone은 하나의 IDC이므로, Multi zone을 이용하는 것도 가능함

Master DB 2대를 서로 다른 존에 생성해서 가용성을 높이기

Zone이 다르므로 서브넷도 달라야 함, sub1, sub2로 서로 다른 디비 서브넷을 만들고 다른 서브넷에서 마스터 디비 서버를 운영해야 함

![Untitled](13%E1%84%80%E1%85%A1%E1%86%BC%20(Cloud%20DB)%20%E1%84%8B%E1%85%AA%E1%86%AB%E1%84%8C%E1%85%A5%E1%86%AB%20%E1%84%80%E1%85%AA%E1%86%AB%E1%84%85%E1%85%B5%E1%84%92%E1%85%A7%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20Cloud%20DB%20%E1%84%89%20fe41580cbd0b474e8387be4f0ee1e083/Untitled%203.png)

- Public Subnet은 Public IP 부여 가능, 외부에서 해당 DB 서버에 직접 접근 가능
- Private subnet은 Public IP 부여 불가, 오직 서브넷 내의 서버에서만 DB 서버에 접근 가능하다

## Cloud DB for Redis

![Untitled](13%E1%84%80%E1%85%A1%E1%86%BC%20(Cloud%20DB)%20%E1%84%8B%E1%85%AA%E1%86%AB%E1%84%8C%E1%85%A5%E1%86%AB%20%E1%84%80%E1%85%AA%E1%86%AB%E1%84%85%E1%85%B5%E1%84%92%E1%85%A7%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20Cloud%20DB%20%E1%84%89%20fe41580cbd0b474e8387be4f0ee1e083/Untitled%204.png)

- 레디스 서버의 경우는 캐시 디비(인메모리 서버)
    - 레디스 서버 생성 시 오직 메모리 양만 가능함
    - 이중화되어 있기 때문에 서버 두 대가 만들어짐
- 레디스 클러스터를 사용하게 되면, 4GB 서버 3대로 Total 12GB의 캐시 팜을 구성 가능함. 여기서 4GB를 추가하면 16GB, … 이런 식으로 쉽게 메모리 증설 가능함. 또한 가용성이 좋아짐
- Port 6379는 Redis 기본 Port
- Port 3306(MySQL), Port 1433(MSSQL)을 기본 포트로 제공, 기본 포트는 언제든 변경할 수 있음

![Untitled](13%E1%84%80%E1%85%A1%E1%86%BC%20(Cloud%20DB)%20%E1%84%8B%E1%85%AA%E1%86%AB%E1%84%8C%E1%85%A5%E1%86%AB%20%E1%84%80%E1%85%AA%E1%86%AB%E1%84%85%E1%85%B5%E1%84%92%E1%85%A7%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20Cloud%20DB%20%E1%84%89%20fe41580cbd0b474e8387be4f0ee1e083/Untitled%205.png)

- HA를 구성하게 되면 샤드 3개가 예비로 추가 구성되어 3개의 샤드가 추가 생성, 실제 서비스에는 3개의 샤드가 투입되나 총 6개의 샤드가 구성됨
- Redis는 오직 Private Subnet으로만 생성 가능
- 캐시를 외부에서 접근하는 건 일반적으로 잘 사용되는 방법은 아니기 때문에 Private subnet만 생성 가능

## Cloud DB for MS-SQL

![Untitled](13%E1%84%80%E1%85%A1%E1%86%BC%20(Cloud%20DB)%20%E1%84%8B%E1%85%AA%E1%86%AB%E1%84%8C%E1%85%A5%E1%86%AB%20%E1%84%80%E1%85%AA%E1%86%AB%E1%84%85%E1%85%B5%E1%84%92%E1%85%A7%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20Cloud%20DB%20%E1%84%89%20fe41580cbd0b474e8387be4f0ee1e083/Untitled%206.png)

- MySQL에서는 Master, Slave라고 부르는 것을 MS-SQL에서는 Principal, Mirror라고 부름

![Untitled](13%E1%84%80%E1%85%A1%E1%86%BC%20(Cloud%20DB)%20%E1%84%8B%E1%85%AA%E1%86%AB%E1%84%8C%E1%85%A5%E1%86%AB%20%E1%84%80%E1%85%AA%E1%86%AB%E1%84%85%E1%85%B5%E1%84%92%E1%85%A7%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20Cloud%20DB%20%E1%84%89%20fe41580cbd0b474e8387be4f0ee1e083/Untitled%207.png)

- 클래식은 MSSQL 2016을 지원하는데 비해 VPC는 MSSQL 2019를 지원함

## Cloud DB for MongoDB

![Untitled](13%E1%84%80%E1%85%A1%E1%86%BC%20(Cloud%20DB)%20%E1%84%8B%E1%85%AA%E1%86%AB%E1%84%8C%E1%85%A5%E1%86%AB%20%E1%84%80%E1%85%AA%E1%86%AB%E1%84%85%E1%85%B5%E1%84%92%E1%85%A7%E1%86%BC%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20Cloud%20DB%20%E1%84%89%20fe41580cbd0b474e8387be4f0ee1e083/Untitled%208.png)