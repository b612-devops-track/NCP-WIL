# 3강. (Compute) 서버 Operation 방안 소개

URL: https://www.edwith.org/associate-vpc/lecture/441815
강의시간: 15:20

![Untitled](3%E1%84%80%E1%85%A1%E1%86%BC%20(Compute)%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%A5%20Operation%20%E1%84%87%E1%85%A1%E1%86%BC%E1%84%8B%E1%85%A1%E1%86%AB%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%20ead0e8ce1bbe4bbfb5403894d3645902/Untitled.png)

- 서버 이미지를 만들 땐 추가 볼륨을 detach 하고서 만드는 것이 좋다. 추가 볼륨까지 붙이고 이미지를 굽는 건 지양되어야 함
- Packer 등 Server Image Builder를 이용해서 서버 생성도 가능함

![Untitled](3%E1%84%80%E1%85%A1%E1%86%BC%20(Compute)%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%A5%20Operation%20%E1%84%87%E1%85%A1%E1%86%BC%E1%84%8B%E1%85%A1%E1%86%AB%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%20ead0e8ce1bbe4bbfb5403894d3645902/Untitled%201.png)

- Server Image로 서버를 만드는 게 더 빠르다. Auto Scailing 등으로 서버를 관리할 때는 서버 이미지를 이용하는 게 좋고, 최근 업데이트 사항들은 매번 이미지를 굽는 것보다는 Init Script 등으로 활용하는 게 더 좋을 수 있다.

![Untitled](3%E1%84%80%E1%85%A1%E1%86%BC%20(Compute)%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%A5%20Operation%20%E1%84%87%E1%85%A1%E1%86%BC%E1%84%8B%E1%85%A1%E1%86%AB%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%20ead0e8ce1bbe4bbfb5403894d3645902/Untitled%202.png)

![Untitled](3%E1%84%80%E1%85%A1%E1%86%BC%20(Compute)%20%E1%84%89%E1%85%A5%E1%84%87%E1%85%A5%20Operation%20%E1%84%87%E1%85%A1%E1%86%BC%E1%84%8B%E1%85%A1%E1%86%AB%20%E1%84%89%E1%85%A9%E1%84%80%E1%85%A2%20ead0e8ce1bbe4bbfb5403894d3645902/Untitled%203.png)