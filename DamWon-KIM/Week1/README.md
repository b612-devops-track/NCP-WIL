[!접속.jpg](접속.jpg) </br></br>
[!apm 설치.jpg](apm설치.jpg)

# Load Balancer종류

애플리케이션 로드밸런서 HTTP/HTTPS</br></br>
네트워크 로드밸런서 TCP  DSR</br></br>
네트워크 프록시 로드밸런서 TCP,TLS</br></br>

네이버 클라우드 플랫폼 Networking - Load balancer</br></br>
로드밸런싱 알고리즘에서 가장 잘 쓰이는 거</br></br>
Round Robin : 클라이언트에서 요청이 오면 서버에 1개씩 분배하는 방식</br></br>

CDN+ 국내전용/GCDN 글로벌 전용

Networking = NAT Gateway
  - Autosacling과 관련된 자동 설정 제공

Global Route Manager
  - 여러 region으로 Load Balancing을 도와주는 서비스
  - DNS를 기반으로 사용할 수 있음
  - 분배 알고리즘을 가지고 있다(Round Robin, Weighted ,GeoLocation, Failover)



### 참고문헌
[레퍼런스1](https://mollangpiu.tistory.com/179)
[레퍼런스2](https://mollangpiu.tistory.com/180)
