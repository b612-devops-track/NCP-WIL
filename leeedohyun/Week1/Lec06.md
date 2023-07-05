# 로드 밸런서 생성
바로 생성할 수 없고 로드밸런서 전용 서버를 만들어야 한다. 이번에는 로드밸런서 전용 서버를 만들어보자.

<img src="https://github.com/leeedohyun/NCP-WIL/assets/116694226/315ff861-fe6c-4ef0-bef2-8e986b1111df" width="500"/>

subnet을 만들고 나서 Target Group을 생성하고 로드 밸런서를 생성하면 다음과 같은 3가지 로드 밸런서가 나온다. 그중에서 Application 로드 밸런서를 선택하여 생성해준다.
생성하면 접속 정보가 할당된다. 상태가 운영 중으로 변경되면 접속 정보로 들어가서 분기가 잘 되는지, 부하가 분산이 잘 되는지 확인해보자.

# Auto-Scaling 생성
가장 먼저 Lauch Configuration을 생성해준다. 그다음 Lauch Configuration을 바탕으로 만들어진 VM들을 하나의 그룹으로 관리하도록 Auto Scaling Group을 생성한다.
생성하고 나면 기대 용량만큼 자동으로 서버가 생성되는 것을 확인할 수 있다.

![image](https://github.com/leeedohyun/NCP-WIL/assets/116694226/24f4b558-af9d-4c66-b1d4-00f1942199a7)

마지막으로 이벤트 룰을 통해서 언제 서버를 증가시키거나 감소시킬 것인지 모니터링 매트릭을 설정해주어야 한다. Cloud Insight에서 처음 사용하면 상품 이용 신청을 하면 된다.
그리고 이벤트 룰을 생성해주면 된다. 그러면 다음과 같은 감시 상품이 나오는데, VPC Auto Scaling을 선택해준다.

![image](https://github.com/leeedohyun/NCP-WIL/assets/116694226/9dab9110-3c3a-4df4-9305-7ba9bfb4a394)

감시 항목을 위한 템플릿을 만들어준다. 만드는 방법은 생성 버튼을 누르고 감시할 항목을 선택하면 된다. 지금은 CPU 사용량에 대해서 감시 템플릿을 만들 것이기 때문에 avg_cpu_used_rto를 선택한다.
그리고 조건으로 CPU의 사용량이 30%가 넘어가면 알람 메일을 Warning으로 만들어준다. Auto scaling의 정책을 add 정책으로 생성해주면 이밴트 룰 생성이 완료된다.
