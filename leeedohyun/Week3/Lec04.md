# (Compute) 오토 스케일링과 쿠버네티스 서비스 소개
## 오토 스케일링
- 클라우드의 장점 중 하나는 유연한 인프라 확장
    - 인프라 확장의 높은 자유도를 이용하여 인프라 비용을 최적화하고 이벤트에 대응
    - 사용자가 정의한 주기(스케줄링), 사용자가 설정한 매트릭(모니터링), 사용자 요청(온디멘드)에 따라 서버를 자동 생성, 삭제 진행
- 오토 스케일링 설정
    - Launch Configuration
    - Auto Scaling Server Group
    - Event Rule

## Kubernates Service
- 완전 관리형 Kubernates Cluster 제공
    - Container의 배포(scheduling), 운영(HA Failover), 확장(Scaling)을 자동화하기 위한 플랫폼
    - Control Plane 설치, 운영에 대한 고민없이, 사용자는 Container가 구동되는 Worker Node에 대한 관리만 하면 된다.
    - Container Registry, Load Balancer 등 네이버 클라우드 플랫폼 다른 서비스와 통합하여 사용 가능