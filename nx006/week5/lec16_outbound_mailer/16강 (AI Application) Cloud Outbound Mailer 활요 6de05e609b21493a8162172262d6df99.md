# 16강.(AI/Application) Cloud Outbound Mailer 활용 데모

URL: https://www.edwith.org/associate-vpc/lecture/464269?isDesc=false
강의시간: 5:01

# NCP Cloud Outbound Mailer 사용하기

![Untitled](16%E1%84%80%E1%85%A1%E1%86%BC%20(AI%20Application)%20Cloud%20Outbound%20Mailer%20%E1%84%92%E1%85%AA%E1%86%AF%E1%84%8B%E1%85%AD%206de05e609b21493a8162172262d6df99/Untitled.png)

Cloud Outbound Mailer는 Services→Application Services→Cloud Outbound Mailer에 들어가보시면 있습니다.

## 템플릿 등록하기

![Untitled](16%E1%84%80%E1%85%A1%E1%86%BC%20(AI%20Application)%20Cloud%20Outbound%20Mailer%20%E1%84%92%E1%85%AA%E1%86%AF%E1%84%8B%E1%85%AD%206de05e609b21493a8162172262d6df99/Untitled%201.png)

먼저 템플릿을 생성합니다. 템플릿 등록 버튼을 누르고

![Untitled](16%E1%84%80%E1%85%A1%E1%86%BC%20(AI%20Application)%20Cloud%20Outbound%20Mailer%20%E1%84%92%E1%85%AA%E1%86%AF%E1%84%8B%E1%85%AD%206de05e609b21493a8162172262d6df99/Untitled%202.png)

이런 식으로 간단히 예시 템플릿을 생성해서 등록합니다.

## 메일 발송하기

![Untitled](16%E1%84%80%E1%85%A1%E1%86%BC%20(AI%20Application)%20Cloud%20Outbound%20Mailer%20%E1%84%92%E1%85%AA%E1%86%AF%E1%84%8B%E1%85%AD%206de05e609b21493a8162172262d6df99/Untitled%203.png)

방금 만든 템플릿을 이용해서 바로 발송이 가능합니다. 발송하기를 누릅니다.

![Untitled](16%E1%84%80%E1%85%A1%E1%86%BC%20(AI%20Application)%20Cloud%20Outbound%20Mailer%20%E1%84%92%E1%85%AA%E1%86%AF%E1%84%8B%E1%85%AD%206de05e609b21493a8162172262d6df99/Untitled%204.png)

광고 메일인지 여부, 템플릿, 내용을 수정할 수 있고, 파일도 넣을 수 있습니다.

- 일반 메일은 메일 그대로 보냅니다
- 광고 메일은 광고가 제목 앞에 붙고, 메일의 맨 끝에 수신 거부 내용이 붙게 됩니다(법적 사항임)

![Untitled](16%E1%84%80%E1%85%A1%E1%86%BC%20(AI%20Application)%20Cloud%20Outbound%20Mailer%20%E1%84%92%E1%85%AA%E1%86%AF%E1%84%8B%E1%85%AD%206de05e609b21493a8162172262d6df99/Untitled%205.png)

발송 방법을 구분할 수 있는데, 여기에서 템플릿에 치환태그를 넣었기 때문에, 파일 업로드를 통해서 메일을 보낼 수 있습니다. 이때 대량수신자 발송용 입력양식을 살펴보겠습니다.

![Untitled](16%E1%84%80%E1%85%A1%E1%86%BC%20(AI%20Application)%20Cloud%20Outbound%20Mailer%20%E1%84%92%E1%85%AA%E1%86%AF%E1%84%8B%E1%85%AD%206de05e609b21493a8162172262d6df99/Untitled%206.png)

이런 식으로 되어 있습니다. 참고로 만약에 다른 템플릿 안에 치환 태그를 사용한 경우, 컬럼에 이를 추가해주면 됩니다.

![Untitled](16%E1%84%80%E1%85%A1%E1%86%BC%20(AI%20Application)%20Cloud%20Outbound%20Mailer%20%E1%84%92%E1%85%AA%E1%86%AF%E1%84%8B%E1%85%AD%206de05e609b21493a8162172262d6df99/Untitled%207.png)

파일을 업로드해서 올리면 되고, 또한 예약 발송도 설정할 수 있습니다.

![Untitled](16%E1%84%80%E1%85%A1%E1%86%BC%20(AI%20Application)%20Cloud%20Outbound%20Mailer%20%E1%84%92%E1%85%AA%E1%86%AF%E1%84%8B%E1%85%AD%206de05e609b21493a8162172262d6df99/Untitled%208.png)

이렇게 설정을 해준 뒤에 파일 업로드를 하고 발송해보겠습니다.

![Untitled](16%E1%84%80%E1%85%A1%E1%86%BC%20(AI%20Application)%20Cloud%20Outbound%20Mailer%20%E1%84%92%E1%85%AA%E1%86%AF%E1%84%8B%E1%85%AD%206de05e609b21493a8162172262d6df99/Untitled%209.png)

확인 후 발송을 누릅니다.

![Untitled](16%E1%84%80%E1%85%A1%E1%86%BC%20(AI%20Application)%20Cloud%20Outbound%20Mailer%20%E1%84%92%E1%85%AA%E1%86%AF%E1%84%8B%E1%85%AD%206de05e609b21493a8162172262d6df99/Untitled%2010.png)

![Untitled](16%E1%84%80%E1%85%A1%E1%86%BC%20(AI%20Application)%20Cloud%20Outbound%20Mailer%20%E1%84%92%E1%85%AA%E1%86%AF%E1%84%8B%E1%85%AD%206de05e609b21493a8162172262d6df99/Untitled%2011.png)

발송 준비가 되었고, 즉시발송을 눌러보겠습니다.

![Untitled](16%E1%84%80%E1%85%A1%E1%86%BC%20(AI%20Application)%20Cloud%20Outbound%20Mailer%20%E1%84%92%E1%85%AA%E1%86%AF%E1%84%8B%E1%85%AD%206de05e609b21493a8162172262d6df99/Untitled%2012.png)

짠~ 왔습니다.

참고로 메일은 1,000건 이하의 경우 요금은 무료이며, 1,000건 초과부터는 건 당 0.45원이 청구됩니다.

또한 이렇게 직접 만지지 않고, RestAPI를 사용할 수도 있습니다. 어플리케이션에서 이메일을 사용해야 할 때 보다 편리하게 서비스를 제공할 수 있겠습니다.