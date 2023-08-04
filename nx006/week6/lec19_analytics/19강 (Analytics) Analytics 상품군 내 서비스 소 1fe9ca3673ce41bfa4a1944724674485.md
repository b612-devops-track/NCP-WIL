# 19강.(Analytics) Analytics 상품군 내 서비스 소개

URL: https://www.edwith.org/associate-vpc/lecture/465872
강의시간: 9:43

## Data Analytics Service

![Untitled](19%E1%84%80%E1%85%A1%E1%86%BC%20(Analytics)%20Analytics%20%E1%84%89%E1%85%A1%E1%86%BC%E1%84%91%E1%85%AE%E1%86%B7%E1%84%80%E1%85%AE%E1%86%AB%20%E1%84%82%E1%85%A2%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%201fe9ca3673ce41bfa4a1944724674485/Untitled.png)

## ELSA(Effective Log Search & Analytics

![Untitled](19%E1%84%80%E1%85%A1%E1%86%BC%20(Analytics)%20Analytics%20%E1%84%89%E1%85%A1%E1%86%BC%E1%84%91%E1%85%AE%E1%86%B7%E1%84%80%E1%85%AE%E1%86%AB%20%E1%84%82%E1%85%A2%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%201fe9ca3673ce41bfa4a1944724674485/Untitled%201.png)

## CLA

![Untitled](19%E1%84%80%E1%85%A1%E1%86%BC%20(Analytics)%20Analytics%20%E1%84%89%E1%85%A1%E1%86%BC%E1%84%91%E1%85%AE%E1%86%B7%E1%84%80%E1%85%AE%E1%86%AB%20%E1%84%82%E1%85%A2%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%201fe9ca3673ce41bfa4a1944724674485/Untitled%202.png)

- 텍스트로 떨어지는 모든 로그에 대해서 분석이 가능함
- 예를 들어 직접 커스텀한 텍스트 데이터로 어플리케이션에서 로그를 빼낼 때, 해당 로그를 분석 가능함
- 100GB까지 수집 가능, 이후부터는 Object Storage로 로그를 익스포트 가능
    - 로그 용량을 늘릴 수는 없고, 이전 30%의 데이터를 삭제하게 됨

## RUA

![Untitled](19%E1%84%80%E1%85%A1%E1%86%BC%20(Analytics)%20Analytics%20%E1%84%89%E1%85%A1%E1%86%BC%E1%84%91%E1%85%AE%E1%86%B7%E1%84%80%E1%85%AE%E1%86%AB%20%E1%84%82%E1%85%A2%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%201fe9ca3673ce41bfa4a1944724674485/Untitled%203.png)

## Cloud Hadoop

![Untitled](19%E1%84%80%E1%85%A1%E1%86%BC%20(Analytics)%20Analytics%20%E1%84%89%E1%85%A1%E1%86%BC%E1%84%91%E1%85%AE%E1%86%B7%E1%84%80%E1%85%AE%E1%86%AB%20%E1%84%82%E1%85%A2%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%201fe9ca3673ce41bfa4a1944724674485/Untitled%204.png)

- Hadoop Cluster를 구성하는 건 매우 힘든 일
- 이를 편리하게 생성하도록 지원하는 게 Cloud Hadoop
- 기본적으로는 오브젝트 스토리지를 기본으로 제공
- 해당 오브젝트 스토리지에 원본 데이터를 넣어놓고, 이를 분석해서 해당 output을 다시 object storage에 저장이 가능함

## Cloud Search

![Untitled](19%E1%84%80%E1%85%A1%E1%86%BC%20(Analytics)%20Analytics%20%E1%84%89%E1%85%A1%E1%86%BC%E1%84%91%E1%85%AE%E1%86%B7%E1%84%80%E1%85%AE%E1%86%AB%20%E1%84%82%E1%85%A2%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%201fe9ca3673ce41bfa4a1944724674485/Untitled%205.png)

네이버 검색 엔진을 이용해서 우리의 사이트, 문서 내부의 결과를 검색을 하고 그 결과를 리턴함

## Elastic Search Service

![Untitled](19%E1%84%80%E1%85%A1%E1%86%BC%20(Analytics)%20Analytics%20%E1%84%89%E1%85%A1%E1%86%BC%E1%84%91%E1%85%AE%E1%86%B7%E1%84%80%E1%85%AE%E1%86%AB%20%E1%84%82%E1%85%A2%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%201fe9ca3673ce41bfa4a1944724674485/Untitled%206.png)

사용자에게 보다 편리한 엘라스틱 서치 검색 엔진을 구축하고 이용할 수 있게 함

## Cloud Data Streaming Service(Kafka)

![Untitled](19%E1%84%80%E1%85%A1%E1%86%BC%20(Analytics)%20Analytics%20%E1%84%89%E1%85%A1%E1%86%BC%E1%84%91%E1%85%AE%E1%86%B7%E1%84%80%E1%85%AE%E1%86%AB%20%E1%84%82%E1%85%A2%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%B5%E1%84%89%E1%85%B3%20%E1%84%89%E1%85%A9%201fe9ca3673ce41bfa4a1944724674485/Untitled%207.png)

- Apache Kafka는 LinkedIn에서 개발된 메시징 시스템