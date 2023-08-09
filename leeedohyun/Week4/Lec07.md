# (Network) 로드밸런서, CDN 서비스 소개
## Load Balancer
- Target Group
    - 요청을 처리할 대상에 대한 집합
    - 동일 VPC 내에 있는 서버들에 대해 타겟 그룹 생성 가능
    - 타겟 그룹 안에 있는 서버를 다른 타겟 그룹에 속하게 할 수 있지만 타겟 그룹을 다수의 로드밸런서에 연결할 수는 없다.
    - 헬스 체ㅋ 주기 (5~300초) 및 임계값 설정
    - 기본은 Round Robin 설정
        - 알고리즘 및 Sticky ProxyProtocol 설정 변경은 생성 이후에 진행

- 로드밸런서
    - 부하처리 성능에 따라 Small/Medium/Large 중 선택 가능

- 알고리즘
    - Round Robin
    - Least Connection
    - Source IP Hash

### 방식
- 애플리케이션 로드밸런서
    - HTTP, HTTPS를 사용하는 웹 애플리케이션에 보다 유연한 구성이 가능
    - 고정 IP 제공
    - URL 기반 분기 가능
    - 알고리즘은 3가지 제공
- 네트워크 로드밸런서
    - 고성능의 분산처리 가능
    - Client IP가 그대로 로깅
    - 알고리즘은 Hash, RR만 제공
- 네트워크 프록시 로드 밸런서
    - Classic과 유사한 Proxy 로드밸런서

### 특징
- TCP 레벨 고성능 분산처리 - 네트워크 로드밸런서
- TCP 세션 관리 - 네트워크 프록시 로드밸런서
- SSL 인증 및 암호화 설정 - 애플리케이션 로드밸런서, 네트워크 프록시 로드밸런서
- 다양한 서버 부하 분산 방식- 애플리케이션 로드밸런서 네트워크 프록시 로드밸런서
- L7(Application Layer) 기능 제공 - 애플리케이션 로드밸런서

## DNS
### Global DNS
- 도메인 등록 서비스
    - 다양한 레코드 타입 지원
    - Alias 기능 제공 및 설정 반영 단계 추가
    - 등록 도메인으로 인입되는 트래픽을 분기(Round Robin)
    - 모니터링 기능 제공

## CDN+
- 컨텐치츠를 Caching하여 보다 빠르고 안정적으로 사용자에게 전송하는 서비스
    - 국내, 국외 주 서비스 지역에 따른 CDN 상품 분리 제공
    - 원본은 NCP 오브젝트 스토리지 혹은 커스텀 오리진 서버를 둘 수 있음
    - 도메인은 랜덤 CDN 도메인 혹은 보유하고 있는 도메인 사용 가능
    - 지원 프로토콜은 HTTP/S
- CDN이 언제 필요할까?
    - 대규모 파일 배포나 이미지 서비스, 동영상 서비스 등 대규모로 트래픽이 발생하는 경우
    - 웹 서버를 통해 배포하게 되면 웹 서버의 용량이 기하 급수적으로 커져야 함
    - 이러한 대규모 트래픽에 효과적으로 대응하기 위한 서비스
