# 13강. Global 및 Security 서비스 소개

## NCP Global 서비스

![Untitled](13%E1%84%80%E1%85%A1%E1%86%BC%20Global%20%E1%84%86%E1%85%B5%E1%86%BE%20Security%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%207ee94ec3b5cb4e5d8c48f7f824895810/Untitled.png)

사실 한국에서만 서비스할 거라면 NCP가 속도 측면에서 유리할 수는 있으나, 해외 서비스까지 노린다면, AWS, GCP, Azure 등 메이저 클라우드 3사 업체 대비 글로벌 리전의 수가 한참 모자란 것은 사실이긴 합니다.

## NCP Security 서비스

NCP Security 서비스는 크게 Safer 시리즈, Checker 시리즈로 제공됩니다.

- Safer 시리즈는 NCP 인프라 담당자로서, 제공하는 서비스가 엔드 유저들에게 보안상의 위험은 없는 지를 사전에 점검할 수 있는 서비스입니다.
    - Site Safer, App Safer, File Safer 등이 있습니다.
- Checker 시리즈는 인프라 담당자로서 체크해야 할 보안적 위험들을 리포트 형태로 체크할 수 있게 해주는 서비스입니다.

### Safer 시리즈

![Untitled](13%E1%84%80%E1%85%A1%E1%86%BC%20Global%20%E1%84%86%E1%85%B5%E1%86%BE%20Security%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%207ee94ec3b5cb4e5d8c48f7f824895810/Untitled%201.png)

![Untitled](13%E1%84%80%E1%85%A1%E1%86%BC%20Global%20%E1%84%86%E1%85%B5%E1%86%BE%20Security%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%207ee94ec3b5cb4e5d8c48f7f824895810/Untitled%202.png)

### Checker 시리즈

![Untitled](13%E1%84%80%E1%85%A1%E1%86%BC%20Global%20%E1%84%86%E1%85%B5%E1%86%BE%20Security%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%207ee94ec3b5cb4e5d8c48f7f824895810/Untitled%203.png)

Web Security Checker 서비스의 경우에는, 우리의 웹페이지에 NCP가 직접 모의 해킹을 시도하여 제공하는 웹 서비스에 보안상 취약점은 없는지 체크를 해줍니다.

![Untitled](13%E1%84%80%E1%85%A1%E1%86%BC%20Global%20%E1%84%86%E1%85%B5%E1%86%BE%20Security%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%207ee94ec3b5cb4e5d8c48f7f824895810/Untitled%204.png)

System Security Checker는 OS, WAS(Apache, Nginx) 설정에 취약점은 없는지 점검하고, 이를 리포트 형태로, 어떤 취약점이 있고 어떻게 보완할 수 있는지 등을 제공한다.

![Untitled](13%E1%84%80%E1%85%A1%E1%86%BC%20Global%20%E1%84%86%E1%85%B5%E1%86%BE%20Security%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%207ee94ec3b5cb4e5d8c48f7f824895810/Untitled%205.png)

App Security Checker는 모바일 앱에 대한 체크입니다.

모바일 앱을 개발하고 이를 마켓에 올리기 전에 미리 누락된 보안 사항은 없는지 체크할 때 이용하면 좋다고 합니다.

![Untitled](13%E1%84%80%E1%85%A1%E1%86%BC%20Global%20%E1%84%86%E1%85%B5%E1%86%BE%20Security%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%207ee94ec3b5cb4e5d8c48f7f824895810/Untitled%206.png)

보유한 SSL 인증서를 통합적으로 관리할 수 있는 서비스입니다. SSL 인증서는 https 통신에서, 우리의 웹사이트가 가짜가 아닌 진짜 웹사이트임을 증명하기 위해 제 3자 기관에서 발급한 인증서를 의미하는데, 이를 관리할 수 있게 해줍니다.

![Untitled](13%E1%84%80%E1%85%A1%E1%86%BC%20Global%20%E1%84%86%E1%85%B5%E1%86%BE%20Security%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%207ee94ec3b5cb4e5d8c48f7f824895810/Untitled%207.png)

Basic 서비스는 NCP 유저 누구나 무료로 이용할 수 있는 보안적인 서비스입니다.

Managed 서비스는 유료로 받을 수 있는 서비스입니다. DDoS 탐지, WAF 등의 서비스를 제공합니다.

Managed 서비스는 콘솔에서 신청하는 것이 아닌, 자료 → Security Monitoring Service 신청서를 서면으로 작성하여 고객 센터로 제출해야 합니다.

![Untitled](13%E1%84%80%E1%85%A1%E1%86%BC%20Global%20%E1%84%86%E1%85%B5%E1%86%BE%20Security%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%207ee94ec3b5cb4e5d8c48f7f824895810/Untitled%208.png)