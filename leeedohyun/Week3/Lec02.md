# Compute 상품군 소개
## Compute 상품
- 기본적인 서버를 생성하고 관리하는 상품(서버의 집합)
    - 서비스 규모와 사용목적에 적합한 성능의 서버를 선택할 수 있도록 다양한 서버 타입 제공
    - 일반적인 2vCPU~16vCPU 상품부터 Higj Memory 서버, VDS, HPC, GPU 등 다양한 상품 라인업이 준비
    - G1과 G2로 구분하여 제공(성능상의 차이 및 스펙의 차이)
- 요금 구성
    - 컴퓨팅(CPU, 메모리), 네트워크(outbound), 스토리지 요금이 발생
    - 서버 정지 시 컴퓨팅 네트웍 요금은 발생하지 않으나 스토리지 비용 발생(Micro, Compact, Standard)
    - 서버 정지 시 표준 요금이 적용되는 서버(High Meomory 서버, VDS, GPU 서버)
- SSD, HDD 디스크 타입 제공
    - IO 퍼포먼스 차별화
    - SSD 사용 시 최대 IOPS 보장

## Bare Metal Server
- 단독으로 사용할 수 있는 고성능 물리 서버를 클라우드 형태로 제공
    - 물리 서버에 하이퍼 바이저 없이 바로 운영 체제를 설치하여 제공
    - 적합한 RAID 구성 방식을 선택할 수 있습니다.
    - 단독 서버를 사용하는 것이기 때문에 성능에 민감한 서비스도 안정적으로 운영 가능
    - CentOS, ORACLE, Linux와 Window 제공
    - 네이버 클라우드 플랫폼의 다양한 서비스와 연계 가능
    - 서버 장애 시 Live Migration 불가

VPC에서 제공하는 Bare Metal은 조금 다르다. VPC와 Subnet을 선택하여 구성하는 것이 추가 되어야 한다.

## GPU 서버
- 병렬 처리에 최적화된 GPU 서버의 고성능 컴퓨팅 파워를 제공
    - 딥러닝을 위한 GPU 서버 팜
        - NVDIA P40, V100 장착
        - NVDIA GRID 기술이 아닌 Pass Through를 적용하여 제공
        - 서버 당 최대 4장의 GPU 제공 (T4는 2장)
    - GPU 제공 사양
        - T4: 8vCPU, 40GB Memory 당 GPU 1개, 16GB GPU 메모리 제공
        - V100: 8vCPU, 90GB Memory 당 GPU 1개 32GB GPU 메모리 제공
    - 제공 OS
        - CentOS, Ubuntu 16.04

## Compute 상품
- 기본적인 서버를 생성하고 관리하는 상품
    - 서비스 규모와 사용목적에 적합한 성능의 서버를 선택할 수 있도록 다양한 서버 타입 제공
    - 강의 날짜 기준 어플리케이션 이미지는 제공하지 않음
    - 네트웍 인터페이스는 서버당 최대 3개까지 구성 가능
- SSD, HDD 디스크 타입 제공
    - IO 퍼포먼스 차별화
    - SSD 사용 시 최대 IOPS 보장
- GPU 상품은 VM 1대 당 최대 8개까지 장착 가능하게 업데이트 될 예정