# [실습 2] Object Storage로 자기소개 포트폴리오 제작

### **Object Storage로 자기소개 포트폴리오 제작이란?**

Object Storage의 웹 퍼블리싱 기능으로 개인 온라인 포트폴리오나 알림 페이지 같은 간단한 정적 페이지를 쉽게 만들고 웹을 통해 서비스할 수 있습니다. 웹 서버를 설치하고 복잡한 웹 호스팅 과정을 거치는 것보다 편리합니다.

<img alt="실습2-1" src="https://github.com/b612-devops-track/NCP-WIL/assets/103591752/f9fe2d85-05fc-4e01-9a48-0da262080a4d">

페이지가 없다고 떠서 예전에 공부할 때 만들어 둔 html, css, js 파일을 배포해 봐야겠다.

<img  alt="실습2-2" src="https://github.com/b612-devops-track/NCP-WIL/assets/103591752/865010e8-eb13-4fea-b02d-3a9eba5dfc24">

API 키는 지난 실습에서 받은 키를 다시 쓴다.

<div>
<img width="48%" alt="실습2-3" src="https://github.com/b612-devops-track/NCP-WIL/assets/103591752/6b3fd068-8183-44aa-8624-d89ca75d8207">
<img width="48%" alt="실습2-4" src="https://github.com/b612-devops-track/NCP-WIL/assets/103591752/713f572d-0ac8-4181-8b07-637e1f413d3a">
</div>

오브젝트 스토리지의 버킷을 만들어 준다.

<img  alt="실습2-5" src="https://github.com/b612-devops-track/NCP-WIL/assets/103591752/d2b97ec4-1f43-48cc-bac1-a8c1ccffff2f">

배포할 파일을 업로드 해 준다

<div>
<img width="48%" alt="실습2-6" src="https://github.com/b612-devops-track/NCP-WIL/assets/103591752/e33422a1-370a-4488-b3fd-83ab11ed12a8">
<img width="48%" alt="실습2-7" src="https://github.com/b612-devops-track/NCP-WIL/assets/103591752/e1409492-dcce-4dee-b0d1-d25cfb263adf">
</div>

모든 파일의 권한을 공개로 바꿔 줬다.

<img alt="실습2-8" src="https://github.com/b612-devops-track/NCP-WIL/assets/103591752/934e7a8b-047f-4dc2-8117-e351915ddb4a">

저렇게 생성된 링크로 들어가면

<div>
<img width="48%" alt="실습2-9" src="https://github.com/b612-devops-track/NCP-WIL/assets/103591752/91d225e3-ad7a-4225-8c97-3285254a46e0">
<img width="48%" alt="실습2-10" src="https://github.com/b612-devops-track/NCP-WIL/assets/103591752/63587484-9c44-424b-88ce-2b77acd117a0">
</div>

이미지, html, css, js가 모두 정상적으로 동작하는 페이지가 배포되었다
