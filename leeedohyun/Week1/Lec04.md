# VPC 생성
먼저, VPC를 생성한다.  


<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/87b5b635-a192-4e0b-940d-9de134bff4fa" width="500"/>  

  
주소 범위는 위의 private 대역 내의 범위 내에서 선택하면 된다. 실습은 10.0.0/16으로 진행한다. 

   
# Network ACL 생성
<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/0ba5bb26-06ba-4f04-a236-afe37862c51b" width="700"/>

VPC를 생성할 때 디폴트로 생성된다. 하지만 잘 사용하지 않고 수동으로 생성해준다.   

<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/dd76700a-4ee6-432d-9357-1a11e4b25ff5" width="500"/>  

이렇게 Network ACL을 생성하면 껍데기 하나 생성된 것이다. 그렇기 때문에 Network ACL에 룰을 설정해주어야 한다. Inbound와 Outbound를 다음과 같이 설정해준다.

<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/9f429a47-616a-418e-865a-f25878b1dfd1" width="500"/>  

<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/a537d362-1aed-480e-9155-c073662b11de" width="500"/>  

# subnet 생성
VPC를 세분화해서 대역을 사용할 수 있게 도와주는 subnet을 만들어 보자.

<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/2f458420-7a1e-44c5-b652-d963d7d78706" width="500"/>  

# ACG 생성
보안을 책임지는 ACG를 만들어보자.

<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/68393198-f605-43f7-938a-cc32f6c90629" width="500"/>  

Network ACL와 마찬가지로 껍데기가 생성되기 때문에 룰을 설정해준다.

<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/0280cbdc-2699-42a1-951e-b24f88cfe3e6" width="500"/>  

<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/e0c18c47-ebcf-4732-9a61-5c89abe614be" width="500"/>  

# init script
<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/e9ac0325-fd54-4631-a3b8-ff116baf7353" width="500"/>  

# Server 생성
서버를 생성한 다음 공인 IP를 생성해준다. 그리고 서버에 접속을 하면 정상적으로 접근하는 것을 확인할 수 있다.

<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/43132e7f-338d-49a1-937c-33317e6ef407" width="500"/>

서버 이미지를 가지고 동일한 환경의 서버를 새로 만들 수 있는데, 어떻게 만들 수 있는지 알아보자. 원하는 서버 이미지를 선택해서 서버 생성을 하면 처음에 서버 생성할 때와 동일한 화면이라는 것을 확인할 수 있다.
Network Inteface의 비공인 IP만 10.0.1.102로 만들어주고 나머지는 동일하게 만들어준다.

<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/4eae8ff0-0a7d-48c3-8675-793507b301d5" width="700"/>

서버 이미지 이름을 통해 베이스 이미지인지 내 서버 이미지로 만들어진 것인지 확인할 수 있다.
