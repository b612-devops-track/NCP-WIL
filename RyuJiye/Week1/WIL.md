## VPC
퍼블릭 클라우드 상에서 제공되는 고객 전용 사설 네트워크   
서브넷을 이용하여 VPC 내 네트워크 공간을 세분화 하여 사용   
구성 요소: Subnet, NAT Gateway, Route Table, ACG, NACL, Virtual Private Gateway, VPC Peering

## Load Balancer
부하 분산을 위해 서버 앞단에서 트래픽을 분산하는 것   
종류: 애플리케이션 로드밸런서, 네트워크 로드밸런서, 네트워크 프록시 로드밸런서   
알고리즘: Round Robin, Least Connection, Source IP Hash

## CDN
웹서버를 통해 대규모 파일을 배포할 때 트래픽에 대응하기 위한 서비스
여러 지역에 캐시 서버를 두어 클라이언트가 데이터를 요청하는 경우 origin server에서 원본을 캐시에 저장
