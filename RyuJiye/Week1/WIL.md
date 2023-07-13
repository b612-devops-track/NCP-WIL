## VPC
* 퍼블릭 클라우드 상에서 제공되는 고객 전용 사설 네트워크   
* 서브넷을 이용하여 VPC 내 네트워크 공간을 세분화 하여 사용   
* 구성 요소: Subnet, NAT Gateway, Route Table, ACG, NACL, Virtual Private Gateway, VPC Peering

## Load Balancer
* 서버에 가해지는 부하를 분산해주는 장치 또는 기술
* 클라이언트와 서버풀 사이에 위치
* 한 대의 서버로 부하가 집중되지 않도록 관리해 각각의 서버가 최적의 퍼포먼스를 보일 수 있도록 함

       
![image](https://github.com/RyuJiye/NCP-WIL/assets/90456695/80c3c3fc-87b4-408d-b8ca-2332e9c4777b)


    
* 종류: 애플리케이션 로드밸런서, 네트워크 로드밸런서, 네트워크 프록시 로드밸런서   
* 알고리즘
      
  Round Robin:  
  서버에 들어온 요청을 순서대로 돌아가며 배정하는 방식  
  여러대의 서버가 동일한 스펙을 가짐  
  서버와의 연결이 오래 지속되지 않는 경우 적합
        
  Least Connection:  
  요청이 들어온 시점에 가장 적은 연결상태를 보이는 서버에 우선적으로 트래픽 분배  
  세션이 길어지거나 서버에 분배된 트래픽들이 일정하지 않은 경우 적합
    
  source IP Hash:  
  클라이언트의 IP 주소를 특정 서버로 매핑  
  사용자의 IP를 해싱하여 로드를 분배  
  사용자가 항상 동일한 서버로 연결되는 것을 보장  
  

  
## CDN(Content distribution network)  

  
![image](https://github.com/RyuJiye/NCP-WIL/assets/90456695/323cbdc1-39df-44cd-bca8-827c37e81672)  
  

* 동시에 여러 사용자가 content를 요구 -> 트래픽에 대응하기 위한 서비스 필요
* 대규모 단일 서버, 분산 서버  
* 대규모 단일 서버의 문제점: 단일 실패점, 혼잡점, 클라이언트와 물리적 거리    
* 여러 지역에 캐시 서버를 두어 클라이언트가 데이터를 요청하는 경우 origin server에서 원본을 캐시에 저장  
* OTT(over the top):  
  셋톱박스를 거치지 않고 인터넷망을 통해 영상 콘텐츠를 제공하는 온라인 동영상 서비스  
  폐쇄적인 영상 유통 인프라를 거치지 않고 공공 인터넷망을 동해 동영상 전송
