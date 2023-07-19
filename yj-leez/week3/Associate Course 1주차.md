# Associate Course 1주차

## 1강. ****과정 소개 및 네이버클라우드플랫폼 서비스 개요****

### 네이버 클라우드 플랫폼 역사

![Untitled](Associate%20Course%201%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20cd47a92217ef4afbb04b615166540e28/Untitled.png)

- 공공 Cloud
    - 국내의 공공기관은 공공 클라우드 인증을 받은 클라우드만 이용 가능 → 들어가는 경로, 제공하는 상품들이 다름
    - 공공기관의 엄격한 심의 요건을 충족하고, 다수의 보안 인증을 취득하여 그 안정성을 검증 받음
- 금융 Cloud
    - 금감원, 금보원의 인증을 받은 국내 최초의 전문 금융 퍼블릭 클라우드
    - 금융과 핀테크 기업만을 위한 전용 클라우드 데이터 센터

### Why Cloud?

- 비용 절감
    - 데브옵스, 사용한 만큼 지불하는 등 기회 비용 최적화 등을 통한 비용 절감
    - PaaS,SaaS 상품들을 활용하면서 개발 시간 절감, 컴퓨팅 파워도 효과적으로 쓸 수 있음
- 빠른 Deploy
    - 기존 Legacy 인프라에 비해 빠른 인프라 구성 시간
- 글로벌 진출시 용이
    - 글로벌 리전 활용을 통해 글로벌 진출시 보다 빠르고 손쉬운 인프라 구성
- 보안
    - 인프라에 대한 보안은 클라우드 공급 업체에 위임
    - 다양한 보안 상품을 이용하여 보안을 강화

### 네이버 클라우드 플랫폼 전체 상품 라인업

![스크린샷 2023-07-19 오전 12.43.44.png](Associate%20Course%201%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20cd47a92217ef4afbb04b615166540e28/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-07-19_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%258C%25E1%2585%25A5%25E1%2586%25AB_12.43.44.png)

- IaaS 상품군: Compute, Storage, Networking
    - IaaS: CPU나 하드웨어 등의 컴퓨팅 리소스를 네트워크를 통해 이용하는 형태
- PaaS 상품군: Database, Analytics, Media, Game
    - PaaS: 기업의 애플리케이션 실행 환경 및 애플리케이션 개발 환경을 네트워크를 통해 이용하는 형태
- SaaS 상품군: AI Service, Dev Tools, Application Service
    - Saas: 소프트웨어의 기능을 네트워크를 통해 이용하는 형태

## 2강. ****(Compute) Compute 상품군 소개****

### Compute 상품

- 여러 템플릿 종류를 가지고 있는 서버들의 집합

| Classic | VPC |
| --- | --- |
| 2VCPU~16VCPU 상품부터 High Memory 서버, VDS, HPC, GPU 등 다양한 상품 라인업 | 서비스 규모와 사용목적에 적합한 성능의 서버를 선택할 수 있도록 다양한 서버 타입 제공
* GPU 상품은 VM 1대 당 최대 8개까지 장착 가능하게 업데이트 될 예정 |
| 체험용 서버인 마이크로 서버 제공 | 어플리케이션 이미지는 현재 제공하지 않음
네트웍 인터페이스는 서버당 최대 3개까지 구성 가능 |
| G1과 G2로 구분하여 제공 | G2만 제공 |
| SSD, HDD 디스크(SaaS 방식) 타입 제공
• IO 퍼포먼스 차별화
• SSD 사용 시 최대IOPS 보장 (4천 ~ 2만 IOPS) | Classic과 동일 |
| • 컴퓨팅(CPU. 메모리), 네트워크(outbound), 스토리지 요금이 발생
• 서버 정지 시 컴퓨팅, 네트웍 요금은 발생하지 않으나 스토리지 비용 발생 ( Micro, Compact, Standard)
• 서버 정지 시 표준 요금이 적용되는 서버 ( High Memory서버, VDS,GPU 서버) |  |

### Classic 서버 타입

1. Micro (1vCPU, 1G RAM, 50G HDD)
    - 한국에서만 제공되는 서비스
    - 서비스 체험용(테스트 용도)
2. Compact ( 2~16vCPU. 4G~ 32G RAM)
    - 저사양 서버
    - 개발 테스트 서버, 개인 홈페이지 운영, 소규모 웹사이트 운영
3. Standard ( 2~16vCPU. 4G~ 32G RAM)
    - IT비즈니스에 활용할 수 있는 네이버 클라우드 플랫폼 서비스 범용 서버
    - 중/대규모 모바일 및 웹 서비스 운영
    - 게임/미디어/금융 서비스 운영
4. High Memory ( 8~32vCPU, 64 ~ 256G RAM)
    - 64GB이상의 고 메모리 서버, 데이터 애플리케이션 운영
    - 고성능 데이터베이스 서버, 대규모 게임 서비스
5. VDS ( 20~32vCPU, 80~232G RAM, 1~2TB HDD)
    - VM 1개만 제공 → 하드웨어 점유를 한 개가 함 → 안정적인 시스템
6. CPU Intensive ( 20~32vCPU, 80~232G RAM, 1~2TB HDD)
    - 대규모 연산 시 빠른 처리가 필요한 업무에 적함
    - 머신/딥 러닝용 처리서버, 고성능 웹서버, HPC/배치 처리, 비디오 인코딩
7. GPU( 4 or 8vCPU, 30 or 60G RAM, 50G HDD)
    - 병렬 처리에 최적화된 GPU서버의 고성능 컴퓨팅 파워 제공
    - NVIDIA GRID 기술이 아닌 Pass Through를 적용해 제공,  서버당 최대 2장의 GPU제공

### VPC 서버 타입

![Untitled](Associate%20Course%201%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20cd47a92217ef4afbb04b615166540e28/Untitled%201.png)

### Classic Bare Metal Server

- 단독으로 사용할 수 있는 고성능 물리 서버를 클라우드 형태로 제공
- 물리서버에 하이퍼바이저 없이 바로 운영 체제를 설치하여 제공 → CPU, Memory 등 서버의 물리적인 리소스 그대로 사용 가능
- 적합한 RAID 구성 방식 선택 가능
- CentOS, ORACLE Linux와 windows 제공
- 하이퍼바이저 존재 x →  내서버 이미지, 스냅샷, 추가스토리지 기능 사용 불가, 서버 장애 시 Live Migration 불가

### VPC Bare Metal Server

- Classic과 거의 유사하나, 스펙이 약간 다름
- VPC와 Subnet을 선택하여 구성(Bare Metal 전용 Subnet에 구성 가능, VPC내 서브넷 제공)
- CentOS, ORACLE Linux와 RHEL 제공(Windows 미제공)

### 국가별 지원 서버 타입

![스크린샷 2023-07-19 오후 12.02.46.png](Associate%20Course%201%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20cd47a92217ef4afbb04b615166540e28/%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-07-19_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_12.02.46.png)

## 3강. ****(Compute) 서버 Operation 방안 소개****

### 서버 Operation 방법

1. 웹 콘솔을 이용한 Operation
    - Ncloud.com 콘솔을 이용하여 다양한 오퍼레이션 진행
2. CLI Operation
    - 별도의 C니 툴을 설치하여 명령 프롬프트에서 명령어를 이용하여 Operation
    - Obiect Storage의 경우 AWS CLI를 이용하여 Operation
3. API Operation
    - 네이버 클라우드 플랫폼에서 제공하는 API를 이용하여 Operation 명령어 개발하여 사용
    - S3의 경우 AWS API를 이용하여 Operation

### 서버 Operation 기능

1. Server Image/ Snapshot/ 유사서버
    - Server Image : 백업 , 혹은 Auto-scaling이나 복제를 위한 마스터 이미지로 사용 가능
    - Snapshot : 서버 OS 영역에 스냅샷 떠서 기존 서버의 추가 볼륨으로 붙이는데 사용 가능
    - 유사 서버: 기존 서버의 설정 부분만 이용하여 깡통 서버를 만들 때 사용 가능
    
    |  | 서버 이미지 | 스냅샷 | 유사 서버 |
    | --- | --- | --- | --- |
    | 대상 | 서버 OS + 추가 볼륨 | 볼륨 | 서버 OS |
    | 서버 상태 | OFF(Classic)/ ON(VPC) | - | - |
    |  | 부팅 디스크 타입 변경 | 디스크 타입 변경 |  |
    | 이미지 사용 | 서버 타입 변경(사양) | 디스크 사이즈 변경 불가 |  |
    |  | 리전 간 이미지 공유 | 리전 간 이미지 공유 |  |
2. Init Script
    - 서버에 설치하여야 하는 패키지나 초기 설정 내용을 스크립트로 선언하여 서버 초기화를 최대한 빠르고 편리하게 구성
    - Linux는 Python, Perl, Shell, Windows는 Visual Basic 스크립트로 작성
    - 서버 생성 시 최초 1회에 한하여 실행
    - Init Script를 언제 사용하나요?
        - 같은 용도 서버를 여러 대 일괄로 생성하는 경우, 동일한 환경의 서버를 주기적으로 생성하는 경우
        → Server Image로도 가능한 기능, 하지만 Init Script로 만들면 어플리케이션을 직접 생성하므로 더 시간이 오래걸림
        → 기본 환경은 이미지로 구축을 하고, 업데이트 된 내용이나 원본 소스를 가져와서 배포하는 건 Init Script로 하는 것을 추천
3. ACG
    - 서버 방화벽 역할
    
    |  | Classic | VPC |
    | --- | --- | --- |
    | 최대 생성 개수 | 계정당 100개 | VPC 당 500개 |
    | 적용 대상 | 서버 | NIC |
    | 적용 ACG 개수 | 서버 당 5개 | NIC 당 3개 |
    | 속성 | 매핑 정보 변경 불가 | 매핑 정보 변경 가능 |
    | 의존성 | 의존성 없음 | VPC에 의존 |
    | Rule 속성 | Inbound | In/ OutBound |
4. 추가 스토리지 구성
    - OS 영역인 50GB에 추가로 더 큰 로컬 스토리지 용량이 필요할 경우 사용
    - 단일 서버에 최대 15개의 추가 스토리지를 추가할 수 있음
    - 스토리지 당 10GB에서 2TB까지 생성할 수 있음
    - 디스크 크기 변경 기능 적용 → 확장은 가능하나 축소는 불가
    - Linux는 LVM, Windows는 동적 디스크 할당을 통해 여러 개의 디스크를 하나의 볼륨으로 묶을 수 있음

## ****4강. (Compute) 오토스케일링과 쿠버네티스 서비스 소개****

### Auto-scaling

- 사용자가 정의한 주기(스케줄링), 사용자가 설정한 메트릭(모니터링), 사용자 요청(온디멘드)에 따라 서버를 자동 생성, 삭제 진행
- 오토스케일링 설정
    - Launch Configuration
    1.1 이름으로 구분되므로 한 계정 내 유일
    1.2 액션의 대상이 되는 서버의 이본 템플릿 (이미지, 서버 타입, ACG 등)
    1.3 베이스 이미지는 퍼블릭 이미지, 커스텀 이미지인 내서버 이미지 사용 가능
    - Autoscaling Server Group
    2.1 Scaling, Management 액션을 위한 논리적 그룹
    2.2 minSize <= desiredCapacity &= maxSize 대소 관계 유지
    - Event Rule (*Classic: Group Event Setting)
    3.1 액션의 기준이 되는 모니터링 매트릭 설정

### Kubernetes Services

- 완전 관리형 Kubernetes Cluster 제공
    - Container의 배포(scheduling), 운영(HA, Failover), 확장(Scaling)을 자동화하기 위한 플랫폼
    - Control Plane 설치, 운영에 대한 고민 없이, 사용자는 Container 가 구동되는 Worker Node에 대한 관리만 하면 됨

## ****5강. (Network) Network 상품군 및 VPC 소개****

### VPC

- 클라우드상에서 논리적으로 격리된 고객 전용 네트워크 공간
    - 현재 한국 리전 민간, 금융 클라우드에 적용
    - 계정당 최대 3개의 VPC 생성 가능
- IP 주소 범위
    - 10.0.0.0/8,172.16.0.0/12,192.168.0.0/16 중에서 선택
    - 최소 /28 에서 최대 /16까지 Netmask 생성 가능
    - Subnet을 이용하여 VPC 안에서 Segment 생성 관리 가능
- Peering
    - 내 VPC간 연결 뿐만 아니라 다른 계정과의 VPC 연결도 가능

![Untitled](Associate%20Course%201%E1%84%8C%E1%85%AE%E1%84%8E%E1%85%A1%20cd47a92217ef4afbb04b615166540e28/Untitled%202.png)

- AGC & NACL ; NACL 검사 후 → ACG 검사 진행
    
    
    | ACG | Network ACL |
    | --- | --- |
    | 서버(NIC) 단위로 적용 | Subnet 단위로 적용 |
    | Allow 규칙에 한하여 지원 | Allow, Deny 규칙 모두 지원 |
    | Stateful: Response 트래픽 자동 허용 | Stateless: Response 트래픽에 대한 Allow 규칙 추가적으로 필요 |
    | 모든 규칙을 확인하여 판단 | 우선순위에 따라 규칙을 반영 |
- Subnet
    - VPC 주소 범위 내에서 CIDR 형태로 주소 범위 지정
    - 인터넷과 연결되는 Public Subnet과 폐쇄적인 Private Subnet으로 구분
        - Public Subnet: 서버만 위치시킬 수 있으며 서버에 공인 IP를 부여
        - Private Subnet: 서버 혹은 로드밸런서를 위치
    - VPC당 최대 200개의 Subnet 생성 가능