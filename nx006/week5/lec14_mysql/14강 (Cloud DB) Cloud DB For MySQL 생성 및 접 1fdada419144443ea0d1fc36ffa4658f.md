# 14강. (Cloud DB) Cloud DB For MySQL 생성 및 접속 데모@

강의시간: 10:35

[****10강. (데모) 데이터베이스 생성 및 연결****](https://www.notion.so/10-b7da476abbaf45ee89505529c4920f6b?pvs=21) 해당 Essential 실습에서 이미 해봤던 것이라서 생략하겠습니다. 다만 몇 가지 사항들만 추가 정리합니다.

![Untitled](14%E1%84%80%E1%85%A1%E1%86%BC%20(Cloud%20DB)%20Cloud%20DB%20For%20MySQL%20%E1%84%89%E1%85%A2%E1%86%BC%E1%84%89%E1%85%A5%E1%86%BC%20%E1%84%86%E1%85%B5%E1%86%BE%20%E1%84%8C%E1%85%A5%E1%86%B8%201fdada419144443ea0d1fc36ffa4658f/Untitled.png)

MySQL의 엔진 버전은 5.x.x 대 4개, 8.x.x 대 2개를 지원합니다. 기존에 사용하던 DB가 있다면 최대한 유사한 버전을 선택할 수 있습니다.

![Untitled](14%E1%84%80%E1%85%A1%E1%86%BC%20(Cloud%20DB)%20Cloud%20DB%20For%20MySQL%20%E1%84%89%E1%85%A2%E1%86%BC%E1%84%89%E1%85%A5%E1%86%BC%20%E1%84%86%E1%85%B5%E1%86%BE%20%E1%84%8C%E1%85%A5%E1%86%B8%201fdada419144443ea0d1fc36ffa4658f/Untitled%201.png)

고가용성 지원 체크란이 잇는데, 이를 풀면 마스터 서버 하나만 생성됩니다.

![Untitled](14%E1%84%80%E1%85%A1%E1%86%BC%20(Cloud%20DB)%20Cloud%20DB%20For%20MySQL%20%E1%84%89%E1%85%A2%E1%86%BC%E1%84%89%E1%85%A5%E1%86%BC%20%E1%84%86%E1%85%B5%E1%86%BE%20%E1%84%8C%E1%85%A5%E1%86%B8%201fdada419144443ea0d1fc36ffa4658f/Untitled%202.png)

강의에서는 Private Subnet에 설치하였기에, Public Subnet에 있는 웹 서버를 통해서 MySQL에 접속해야 합니다.

```bash
yum install mysql
```

위 명령어를 통해서 MySQL 클라이언트를 설치합니다.

```bash
mysql -u student -p -h <:private domain>
```

이때 IP가 아닌, Private Domain을 사용하게 되는데, 이 이유는 IP를 사용하게 되면 DB Crash가 발생했을 때 슬레이브로 옮기기 위해서입니다. 만약 IP를 그대로 사용할 경우 크래시가 발생한 마스터 서버를 가리키기에, 그대로 서비스가 종료되고 맙니다. 이를 유동적으로 변화하기 위해 도메인을 사용합니다.

![Untitled](14%E1%84%80%E1%85%A1%E1%86%BC%20(Cloud%20DB)%20Cloud%20DB%20For%20MySQL%20%E1%84%89%E1%85%A2%E1%86%BC%E1%84%89%E1%85%A5%E1%86%BC%20%E1%84%86%E1%85%B5%E1%86%BE%20%E1%84%8C%E1%85%A5%E1%86%B8%201fdada419144443ea0d1fc36ffa4658f/Untitled%203.png)

디비 서버에 접속할 수 있도록 ACG 설정에서 3306 포트를 열어줍니다(MySQL의 기본 포트가 3306)