# Management 서비스 소개
네이버 클라우드 플랫폼상에서 인프라를 관리할 때 편리한 서비스를 모아서 제공해준다.

## Monitoring
네이버 클라우드 플랫폼에서 운영하는 서버에 대한 다양한 매트릭에 대한 정보를 대시보드 형태로 제공하는 서비스(클라우드 리소스 상태 모니터링 수행)

- 모든 상품에 대해 모니터링 서비스 제공
  - 기본: 상품 별 모니터링 그래프 확인 가능
  - 상세: 매트릭에 대한 임계치 설정과 이벤트 발생 시 알람 기능 제공
- 83개 세부 항목에 대한 모니터링 성능 정보를 수집하며, 그 중 약 60여개의 세부 항목에 대한 이벤트 경보 설정 가능
- Monitoring API 제공

## Cloud Insight
통합 관리 모니터링 서비스

- 네이버 클라우드 플랫폼 상품 및 사용자 애플리케이션 성능/운영 지표를 One Page로 통합
- 네이버 클라우드 플랫폼에서 만든 Basic Metric 뿐만 아니라, 사용자 설정에 따른 Custom Meric 설정도 가능
- 단계 별 Event Rule 생성과 Event 담당자 지정 가능
- Event 발생 시 담당자에게 SMS, Email을 통해 알람 제공
- 유지 보수 설정 기능을 통해 실제 장애로 인한 알람과 구분 가능

## Sub Account
동일한 인프라를 여러 명에서 관리할 때 해당 관리자가 맡고 있는 역할에 맞게 권한을 부여하는 서비스이다. 예를 들어, 서버 관리 담당자에게는 서버에 대한 접속만 가능하게 허용해주고, 오브젝트 스토리지 관리자인 경우 오브젝트 스토리지에 대해서만 매니징할 수 있도록 권한을 부여한다.

- 다수의 사용자가 동일한 자원을 이용하고 관리할 수 있도록 역할을 부여한 서브 계정을 제공하는 서비스
- 2차 인증(2-Factor Authentication) 설정
- 서브 계정이 작업한 모든 내역은 Cloud Activity Tracer 상품에서 확인 가능

## Web service Monitoring System(WMS)
관리하는 웹 페이지가 정상 동작하는지 모니터링할 수 있는 서비스이다. URL만 입력하면 주기적으로 모니터링 가능하다.

- 웹 서비스 유알엘을 입력하여 실시간으로 테스트를 진행할 수 있고, 스케줄을 등록하여 반복적인 모니터링 수행도 가능
- 경보 설정을 통해 모니터링 등록된 URL에서 오류가 감지되면 알람 발송 가능
- 시나리오 기반 모니터링을 제공하여, 사용자 이용 패턴에 따른 각 기능별 모니터링 수행 가능

## Cloud Activity Tracer
루트 계정 뿐만 아니라 서브 계정들이 다양한 액션에 대해서 로그 형태로 남겨 놓은 것을 의미한다.

- 약 155 종류의 네이버 클라우드 플랫폼 액션 로그를 수집
- Management 콘솔, API, SDK, CLI를 통한 계정 별 액션 로그와 비계정 활동에 대한 로깅 기능 제공
- Cloud Log Analytics와의 연동(필수)으로 로그 분석 및 로그를 엑셀로 다운로드 받거나 Object Storage로 Export 가능

## Resource Manger
계정이 아니라 각 개별 서비스가 기준이 된다.

- 네이버 클라우드 플랫폼 서비스 내 생성한 모든 리소스를 한 눈에 볼 수 있는 통합 관리 서비스
- 목적에 따라 자원들을 그룹화하거나 태그를 지정하여 다양하게 활용
- 리소스 별 생성 및 변경 이력을 확인