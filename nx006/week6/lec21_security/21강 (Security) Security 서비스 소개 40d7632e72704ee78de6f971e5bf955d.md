# 21강.(Security) Security 서비스 소개

강의시간: 15:55

**👉** 'Anti-Virus - 윈도우 OS에 한해 오피스 스캔 백신 지원' 부분은 Classic 플랫폼만 해당됩니다. 참고 부탁드립니다. 🙇

# Safer 시리즈

사용자의 어플리케이션, 서비스를 안전하게 지키는 서비스

## Site Safer, App Safer

![Untitled](21%E1%84%80%E1%85%A1%E1%86%BC%20(Security)%20Security%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%2040d7632e72704ee78de6f971e5bf955d/Untitled.png)

## File Safer

![Untitled](21%E1%84%80%E1%85%A1%E1%86%BC%20(Security)%20Security%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%2040d7632e72704ee78de6f971e5bf955d/Untitled%201.png)

유저가 게시판에 파일을 올린다고 할 때, 이 파일을 중간에 가로채서 파일이 안전한 지 File Safer에 보내고 해당 파일을 검사한 후에 문제가 있다면 차단을 하는 로직

# Checker

웹 서비스가 안전한 지를 체크하는 서비스

![Untitled](21%E1%84%80%E1%85%A1%E1%86%BC%20(Security)%20Security%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%2040d7632e72704ee78de6f971e5bf955d/Untitled%202.png)

Naver Cloud Platform 안에 있는 자신의 서버에만 WSC를 돌릴 수 있다. WSC는 서버에 상당한 부하를 주는 작업이기에 NCP 안에 있는 자신의 서버에 대해서만 취약점을 점검할 수 있다. 해당 IP, 해당 서버가 내 소유여야만 WSC 가능

- 이거 근데 요금이 1건 당 40만 원이라서, 보안이 정말 중요한 사이트에서만 사용하는 것이 좋아보임.

![Untitled](21%E1%84%80%E1%85%A1%E1%86%BC%20(Security)%20Security%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%2040d7632e72704ee78de6f971e5bf955d/Untitled%203.png)

WSC는 모의 해킹 방식이지만, SSC는 설정 파일을 보고서 시스템 설정에 대해서 정적 분석을 진행함

- OS Security Checker
- WAS Security Checker 두 버전이 있음
    - WAS Checker의 경우 Apache, Tomcat, NginX 등을 제공하는데, 건 당 2만 원의 비용이 추가됨

![Untitled](21%E1%84%80%E1%85%A1%E1%86%BC%20(Security)%20Security%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%2040d7632e72704ee78de6f971e5bf955d/Untitled%204.png)

구글이나 애플에 앱 스토어에 앱을 등록할 때 보안 심사를 하게 되는데, 이때 App Security Checker로 먼저 보안 항목들에 대해 점검을 할 수 있음.

![Untitled](21%E1%84%80%E1%85%A1%E1%86%BC%20(Security)%20Security%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%2040d7632e72704ee78de6f971e5bf955d/Untitled%205.png)

![Untitled](21%E1%84%80%E1%85%A1%E1%86%BC%20(Security)%20Security%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%2040d7632e72704ee78de6f971e5bf955d/Untitled%206.png)

기본적으로 Basic Security Monitoring을 제공하고 있고, 원한다면 Managed로 변경 가능함.

이때 Anti Virus의 경우 원하는 별도의 백신으로 변경할 수도 있는데, 이때는 충돌을 방지하기 위해 반드시 기존의 안티 바이러스를 끄고서 원하는 별도의 백신을 설치해야 함.

## SSL VPN

- SSL VPN 을 통한 서버 접속
    - 10 대역의 28bit VPN IP 대역 제공 (Classic)
    - VPC 내의 Subnet에 생성 (VPC)
    - SSH, RDP와 같은 포트는 외부에서 접근할 수 없도록 ACG에서 차단하고
    - ACG에 VPN IP 대역에 대해서 접근 가능하도록 설정하여 서버를 안전하게 관리 가능

사실, 실습에서 Web001에는 Public IP를 부여를 했지만, NCP 안에 있는 서버에 접근할 때는 SSL VPN을 이용하는 게 훨씬 보안적으로 안정적이다. 또한 ACG, NACL에서는 서비스에서 필요로 하는 포트만 열어주는 게 가장 좋음. 즉 웹 서비스를 운영하는 경우 외부에는 80(http), 443(https) 포트만 여는 게 가장 안전함.

만약에 어플리케이션 취약점을 이용해 침투하는 경우는 IDS, WAF 등을 이용해 막아주는 것이 안전하다.

서버에 접근할 필요가 있을 시 SSL VPN을 이용하는 게 가장 안전하다.

- 최대 10개 ID 생성 가능 및 전용 VPN 프로그램 설치하여 VPN 사용
    - 3개, 5개, 10개 ID 생성 가능
    - 사용자 가이드를 통해 프로그램 다운로드 가능
- 1차 인증과 2차 인증 지원
    - ID / PW로 로그인 가능한 1차 인증
    - ID / PW 뿐만 아니라 SMS / Mail 의 OTP 를 입력해야 하는 2차 인증

## WebShell Behavior Detector

PHP MyAdmin 등의 툴에서 루트 패스워드를 변경하지 않거나 디폴트로 설정 시, 해커들이 Web Shell 공격 등을 수행할 수가 있음.

- 외부로부터의 웹 쉘 공격을 실시간 탐지
    - Agent 기반 탐지 시스템
    - 행위 기반 실시간 웹쉘 탐지를 비롯하여 알려지지 않은 의심스러운 패턴까지 탐지
    - 웹셀 의심 파일을 격리하거나 복구 가능
- 지원 환경
    - OS: Linux
    - WebServer: Apache, Tomcat, Nginx