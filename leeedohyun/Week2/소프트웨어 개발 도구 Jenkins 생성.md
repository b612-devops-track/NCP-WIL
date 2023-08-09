# Jekins란?
반복적인 소프트웨어 개발 프로세스를 자동화할 수 있습니다. 지속적 통합(Continuous Integration, CI)과 지속적 배포(Continuous Delivery, CD)를 위한 대표적인 개발자 도구로, 빌드, 테스트, 배포 프로세스를 자동화하여 소프트웨어 품질과 개발 생산성을 높입니다.

# 서버 생성
먼저 Jenkins 서버를 생성해준다.

![image](https://github.com/leeedohyun/NCP-WIL/assets/116694226/d582bd0a-b2c0-42c6-95e4-f7cc033d6f1e)

# 서버 접속 환경 설정
Jenkins 서버에 공인 IP를 부여해준다. 그리고 나서 포트 포워딩을 다음과 같이 설정한다.

<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/1e2e9943-424a-4920-ab43-170de91ba4b7" width="500">

<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/964f90f3-505b-4790-8796-50c2d2aea08b" width="500">

</br>

ACG 설정을 하고 나면 서버 접속 환경 설정은 끝이 난다.

# 서버 접속
성공적으로 서버에 접속할 수 있다는 것을 확인할 수 있다.

<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/a80d16dd-314c-4f9f-834a-c37acb1d4fab" width="500">

# Jenkins 프로세스 실행
<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/48cc3538-9d4f-4f11-9465-62194986d195" width="500">

Jenkins 프로세스를 실행하는 명령어
```bash
service jenkins start
```

Jenkins 프로세스를 중지하는 명령어
```bash
service jenkins stop
```

Jenkins 프로세스 상태를 확인하는 명령어
```bash
service jenkins status
```

# Jenkins 웹 서버 접속
공인IP:18080에 접속한다.

<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/38eeac97-e493-42eb-8900-7f1b38bc913b
" width="500">

초기 비밀번호로 로그인해서 Jenkins 플러그인을 설치한다. 그리고 나서 젠킨스 Admin 계정을 생성한다. 이제 젠킨스 웹을 사용할 수 있다!

<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/32461abd-f07f-4c54-ac39-6245d28f4677
" width="500">