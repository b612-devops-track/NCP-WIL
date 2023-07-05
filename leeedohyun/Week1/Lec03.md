# Server Image, Snapshot, 유사 서버
## Server Image
- 내가 만든 vm 서버의 이미지, 전체를 하나의 이미지로 뜬다고 이해하면 된다.
서버 이미지 자체를 하나로 다 뜬 것을 의미한다.
서버를 정지할 필요 없음
- 새로운 서버를 만들 때 원하는 디스크 타입으로 변경이 가능
- 한국뿐만 아니라 다른 리전으로 이미지 공유 가능

## Snapshot
특정 볼륨 하나에 대해서 카피본을 만드는 작업 
- 서버가 운영 중에서 쉽게 뜰 수 있다.
- 디스크 사이즈 변경 불가
- 리전 간 이미지 공유

## 유사 서버
- 어느 한 특정 서버가 가지고 있는 스펙, 템플릿을 떠오는 것을 의미한다.
- 데이터를 가지고 오는 것은 아님

## Server Image Builder
- Packer를 활용해서 내 서버 이미지를 생성해주는 서비스
- 이미지 디스크립션 파일을 이용해서 내 서버 이미지 생성 가능

# Init Script
- 서버를 생성할 때 최초의 1회만 서버가 부팅하고 난 후 동작하는 스크립트를 뜻한다.
- 운영하는 서버에 공통적으로 가져가야 할 설정이 있다면 이닛 스크립트 작성해서 서버를 만들 때 모두가 사용할 수 있도록 관리

- Linux는 Python, Perl, Bash Shell, Windows는 Visual Basic 스크립트로 작성

```shell
#!/bin/bash

yum -y install httpd php mysql -mysql
chkconfig httpd on
cd /var/www/html
wget http://211.249.50.207/lab-adv/lab-adv.tgz
tar xvfz lab-adv.tgz
cat phpadd>> /etc/httpd/conf/httpd.conf
/etc/rc.d/init.d/httpd start
chmod 777 /var/www/html -R
```

## 언제 사용하나요?
- 같은 용도 서버를 여러 대 일괄로 생성하는 경우
- 동일한 환경의 서버를 주기적으로 생성하는 경우
- 용도별로 서버 초기 환경 관리가 필요한 경우

# ACG, Anti-Virus
## ACG
- 서버 방화벽 역할을 도와주는 보안 구성 요소
- Inbound/Outbound 룰 설정 가능
- NACL의 경우는 우선순위가 있지만 ACG는 없다.
- 프로토콜은 TCP, UDP, ICMP 중 선택, 접근 소스는 IP(CIDR), ACG Group 설정 가능
- 단일 네트워크 카드는 최대 3개의 ACG를 적용할 수 있음. 단일 ACG는 최대 100개의 룰 설정 가능
- 서버에 대한 ACG 변경/추가 할당 상시 가능

## Anti-Virus
- Windows OS에 한하여 백신 기본 제공
- 리눅스의 경우, 별도 비용 발생

## 기타 보안/관리 사항
- Security Monitoring(IDS, IPS, WAF DDos) 이용 추가 보안 및 사용자가 설정한 임계치 기반 모니터링 시스템 구성 가능

# 추가 스토리지 구성
- 서버에 기본적으로 생성되는 OS 스토리지 이외에 추가 스토리지 연결할 수 있음(블록 스토리지에 해당)
- OS 영역인 50GB에 추가로 더 큰 로컬 스토리지 용량이 필요한 경우 사용
  - 스토리지 당 10GB에서 2TB까지 생성할 수 있음
- 스토리지 추가 개수 제한
  - 단일 서버에 최대 15개의 추가 스토리지를 추가할 수 있음(기본 OS 이미지 1개 + 추가 스토리지 15개)
- 스토리지 볼륨을 2TB 이상 사용하고자 하는 경우
  - Linux는 LVM, Windows는 동적 디스크 할당을 통해 여러 개의 디스크를 하나의 볼륨으로 묶을 수 있음
- 스토리지 Detach / Attach 기능 제공
  - 서버에 연결된 디스크를 다른 서버로 옮길 수 있다
- 디스크 크기 변경 기능 적용
  - 사용 중인 디스크의 크기가 부족할 경우 필요한 크기로 확장
  
# Autoscaling
- 유연하게 인프라를 확장하거나 축소할 수 있도록 도와주는 상품

네이버 클라우드 플랫폼에서 Autoscaling을 이용하기 위해서 3가지 서비스를 만들어줘야 한다.

1. Launch Configuration: Autoscaling으로 구성한 서버에 템플릿을 만들어 준다고 생각하면 된다.
- 이름으로 구분되므로 한 계정 내 유일
- 액션의 대상이 되는 서버의 기본 템플릿(이미지, 서버 타입, ACG 등)
- 베이스 이미지는 퍼블릭 이미지, 커스텀 이미지인 내 서버 이미지 사용 가능

2. Autoscaling Server Group: Launch Configuration을 기반으로 하는 서버가 만들어지는데 이 서버를 그룹으로 관리하면 더 편리하다.
- Scaling, Management 액션을 위한 논리적 그룹
- minSize <= desiredCapacity <= MaxSize 대소 관계 유지
- desiredCapacity: 최초의 서버가 생성될 때 최초 서버 대수

3. Event Rule: Autoscaling으로 서버를 증가시키거나 감소시킬 때, 언제 증가시킬 것인지 혹은 감소시킬 것인지 액션의 기준이 되는 모니터링 매트릭을 만들어줘야 한다.
- 액션의 기준이 되는 모니터링 매트릭 설정

# Kubernetes Service
- 완전 관리형 Kubernetes Cluster 제공
  - Container의 배포(scheduling), 운영(HA, Failover), 확장(Scaling)을 자동화하기 위한 플랫폼
  - Control Plane 설치. 운영에 대한 고민 없이, 사용자는 Container가 구동되는 Worker Node에 대한 관리만 하면 됨
  - Container Registry, Load Balancer 등 네이버 클라우드 플랫폼 다른 서비스와 통합하여 사용 가능