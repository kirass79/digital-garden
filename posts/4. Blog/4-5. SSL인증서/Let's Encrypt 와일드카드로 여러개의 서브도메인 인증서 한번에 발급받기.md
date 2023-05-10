---
page-title: "Let's Encrypt 와일드카드로 여러개의 서브도메인 인증서 한번에 발급받기"
url: https://oasisfores.com/letsencrypt-wildcard-ssl-certificate/
date: "2023-04-26 17:37:28"
---
이번 글에서는 무료 SSL 인증서 발급 서비스인 Let’s Encrypt를 이용하여 여러개의 서브도메인을 하나의 인증서로 관리할 수 있는 방법에 대해서 알아보겠습니다.
어렵게 말해서 그렇지 oasisfores.com 앞에 aaa.oasisfores.com이나 bbb.oasisfores.com같이 무슨 서브도메인이 오던지 간에 발급받은 하나의 인증서만으로 다 자물쇠를 걸어버릴 수 있다는 겁니다.
![https-example](https://oasisfores.com/wp-content/uploads/2020/06/123-280x300.png)
굳이 이게 필요한걸까 라는 생각이 드실 수도 있겠지만 Webroot, Standalone 방식으로 인증서를 발급 받을 경우 지정한 몇개의 도메인 이외에는 SSL이 적용되지 않으며, 새로운 서비스 제공을 위해 서브도메인을 추가할 경우 그때마다 기존 인증서를 추가 설정해주어야 하는 번거로움이 있습니다.
우선 Let’s Encrypt의 인증서 발급 방식에 대해 알아볼까요?
## 1\. Standalone
가장 비효율적인 방식이라고도 할 수 있으며, certbot 에서 80 포트의 standalone webserver 를 따로 띄워서 인증서를 발급받는 방식입니다.
80, 443 포트를 이미 열고 있다면 발급시마다 구동중인 웹서버를 내려야 한다는 단점이 존재합니다.
당연히 와일드카드 인증 방식은 제공하지 않습니다.
와일드카드라는 용어에 익숙하지 않으신 분들도 계실텐데, 와일드카드라는 것은 어떠한 규칙을 표현하는 하나의 방식입니다.
단순하게 생각하시면 됩니다. aaa.oasisfores.com / bbb.oasisfores.com / ccc.oasisfores.com … 모두 .oasisfores.com은 똑같고 앞에 문자열만 다르죠?
귀찮으니까 이런 경우들을 싸그리 다 합쳐서 **\*.oasisfores.com**으로 표현한 다음 컴퓨터한테 ***‘야 앞에 별표 표시한 부분에는 뭐가 올지는 모르겠는데 암튼 뭐가 오든 인증서 적용시켜놔라? 나 바쁘거든?’***  이라고 떠넘겨버리는 겁니다. 이때 이 \* 같은 표현을 바로 와일드카드라고 합니다.
아래 사진을 보면 실제로 \*.oasisfores.com이 적혀있죠?^^
![wildcard-cert-example](https://oasisfores.com/wp-content/uploads/2020/06/413-300x127.png)
## 2\. Webroot
실제 돌아가고 있는 웹 서버에 특정 파일 쓰기 작업을 통해 인증하는 방식입니다. 이 방식을 이용하면 웹서버를 내렸다가 다시 띄울 필요가 없다는 장점이 있지만 한번에 하나의 폴더를 공유하는 도메인에 대해서만 발급 가능하다는 단점이 존재합니다.
예를 들어 www.oasisfores.com과 oasisfores.com이 같은 결과를 띄운다고 해봅시다. 두 주소 모두 /home/user123/www 디렉토리 내부의 웹 문서를 사용자에게 보여준다고 했을 때, Let’s Encrypt는 웹 문서 파일이 위치한 /home/user123/www 디렉토리에 접근이 가능한지를 시험해봄으로써 해당 도메인의 유효성을 인증하는 것입니다.
이 경우 사용자에게 서비스할 웹 문서가 다르다면(디렉토리가 다를 경우) www.oasisfores.com에 대한 인증서와 oasisfores.com에 대한 인증서를 따로따로 발급받아야 합니다.
한번의 명령으로 지정할 수 있는 webroot 경로는 단 하나 뿐이기 때문입니다.
결국 이 방식또한 와일드카드를 이용한 인증은 받을 수 없습니다.
## 3\. DNS
세 방식 중 유일하게 와일드카드를 이용하여 모든 서브도메인에 대한 인증서를 발급받을 수가 있습니다.
Let’s Encrypt에서 요구하는 특정값을 DNS TXT 레코드에 입력함으로써 인증을 받는 방식입니다.
이것도 말만 어렵지 사실 별거 아닌 내용입니다.
Let’s Encrypt는 인증기관으로서 질서를 지키기 위해 인증서를 요청하는 도메인이 실제로 안전하고 유효한 도메인인지 확인할 의무가 있습니다.
간단히 예를 들어보죠
***서버 개발자 : 야 나 주소 옆에 자물쇠좀 걸고싶은데 인증서 하나만 떼줘라. 정말 공짜로 해주는거 맞지?***
***Let’s Encrypt :  ㅇㅇ 공짜 맞긴 한데 그 도메인 진짜 니가 갖고있는거 맞아? 내가 지금 당장 랜덤 문자열 두개 줄테니까 그거 니 도메인에 표시좀 해볼래?***
***서버 개발자 : 아 어차피 줄거 되게 깐깐하게 구네… 니가 준 문자열 두개 DNS 레코드에 TXT 형식으로 표시해놨으니까 와서 확인해봐라 내거 맞는지 아닌지 ㅡㅡ***
***Let’s Encrypt : ㅇㅋ 확인했음 니 서버 맞네. 인증서 줄게.***
정말 가볍게 표현하긴 했지만 실제로 이런 방식을 통해 이루어집니다.
이제 자세한 방법을 알아볼까요?
## 4. 본론 – DNS 인증방식을 이용하여 와일드카드 도메인 인증서 발급받기
준비물은 간단합니다. 본인 소유의 서버와 도메인만 있으면 됩니다.
이때 도메인을 그냥 소유만 하고 있으면 안되고 반드시 레코드 관리가 가능해야합니다.
과정은 Ubuntu + Apache2를 기준으로 진행되니 참고바랍니다.
우선 Letsencrypt와 certbot부터 설치합니다. 간단한 명령어 두줄이면 끝납니다.
- apt install letsencrypt
- apt install certbot
문제는 인증서를 발급받는 아래의 명령어인데, 이게 인터넷에 나와있는게 다 다르고 오류도 앵간히 떠서 애 좀 먹었습니다.
- certbot certonly \--manual \-d \*.example.com \-d example.com \--preferred\-challenges dns
	- certbot certonly \--manual \-d \*.lifesproutz.com \-d lifesproutz.com \--preferred\-challenges dns

뭐 dns 뒤에 01을 붙이는 사람도 있고 –server https://acme-v02.api.letsencrypt.org/directory를 붙이는 사람도 있는데 파이썬 접속 오류가 계속 떠서 그냥 다 쳐내버리고 위와 같이 입력했습니다.
어차피 기능은 완전히 동일하기 때문에 큰 문제는 되지 않습니다.
이때 위 명령어에서 -d \*.example.com -d example.com는 오타로 두번 입력된 것이 아니니 반드시 위와 같이 입력해주셔야 합니다.
앞의 -d \*.example.com은 example.com 앞에 . 이 붙은 상태에서 뭐가 더 적혀져있는 걸 와일드카드로 나타낸거고 뒤의 -d example.com은 example.com 앞에 . 조차도 붙지 않은 순수한 상태를 의미합니다.
그럴일은 보통 없겠지만 앞에 서브도메인이 오지 않는 example.com을 아예 이용하지 않을 생각이라면 굳이 입력하지 않아도 괜찮기는 합니다.
아무튼 위 명령어를 입력하면 뭐 동의해야하는데 동의하느냐, 문제 생기면 너 이메일로 보내줄건데 이메일 주소 좀 알려줘라 그런 것들이 주욱주욱 나오는데 다 입력해주시면 됩니다.
신나게 입력하다보면 아래 사진과 같은 내용이 나오는데 이때도 계속 엔터 누르시면 안되고 여기서부터는 집중하셔야됩니다.
![acme-challenge-shell](https://oasisfores.com/wp-content/uploads/2020/06/41-e1593224411824-300x189.png)
여기가 위에서 예시로 들었던 Let’s Encrypt가 문자열 두개를 던져주는 단계입니다.
저는 DNS TTL 때문에 계속 실패해서 삽질 좀 했었는데… 제가 성공한 방법을 그대로 알려드리겠습니다.
우선 첫번째 문자열 던져줬을 때 그걸 바로 DNS TXT 레코드에 옮겨적지 마시고 그냥 차분하게 엔터 한번 더 눌러줍니다.
여기서 실수로 엔터를 한번 더 누르시면 DNS 레코드를 입력하기도 전에 Let’s Encrypt가 도메인으로 찾아오기 때문에 인증에 실패하니 조심하셔야 합니다.
아무튼 두번째 문자열까지 나와서 최종적으로 문자열 두개가 나오는데, 이때 이 두개의 문자열을 본인의 도메인 관리 페이지의 DNS 레코드 입력칸에 입력해줍니다.
개인 DNS서버를 가지고 계신 분들은 알아서 잘 하실 것이라고 믿습니다… 저는 안해봐서 모르겠네요
![acme-challenge-dns-setting](https://oasisfores.com/wp-content/uploads/2020/06/516513-300x72.png)
입력 방식은 호스팅 회사마다 다르기 때문에 뭐가 정답이라고는 딱히 말씀드릴 수는 없지만 대충 \_acme-challenge를 서브도메인 자리에 입력하고 Let’s Encrypt가 제시한 문자열을 TXT 레코드 내용에 입력하면 됩니다.
- _acme-challenge
- TXT
- h4CtvRUM9XjSWy38X5c3Yxe4Qv0T2i_FLM-DxnXpL5Q
- HK28ZbksWMgxsl4EVdZ2ZodZOs60Pd_QfRboYcVBQfk

#**이때 중요한게 있습니다. 레코드 입력이 끝났다고 해서 바로 엔터를 누르시면 안됩니다.**
DNS에는 TTL이라는게 있기 때문에 방금 입력한 정보가 전세계로 퍼지는데에는 시간이 좀 걸립니다.
이것도 호스팅 회사마다 다른데 보통 그렇게 오래 걸리지는 않습니다.
그럼 저희는 입력한 정보가 제대로 적용됐는지 안됐는지도 모른채로 그냥 멀뚱멀뚱 기다리고만 있어야 할까요?
당연히 아닙니다. 다 방법이 있죠.
쉘의 dig 명령어를 사용하면 쉽게 TXT 레코드 적용 여부를 알 수 있지만 안타깝게도 지금은 인증서 발급 진행중이라 이용할 수가 없습니다.
다행히도 구글에서 온라인 dig 명령어 실행기 서비스를 제공중이네요. 이것을 이용합시다.
[https://toolbox.googleapps.com/apps/dig/](https://toolbox.googleapps.com/apps/dig/)
![google-dig-example](https://oasisfores.com/wp-content/uploads/2020/06/ewag-300x152.png)
이용법은 정말 간단합니다. \_acme-challenge.도메인 앞부분.도메인 뒷부분을 입력하고 텍스트 버튼을 누르면 현재 도메인에 적용되어있는 DNS TXT 레코드가 출력됩니다.
이때 입력한 두개가 정상적으로 표시되고 있다면 재빨리 엔터를 눌러주세요. 저는 시간이 좀 지나니까 TXT 레코드가 덮어쓰기 되어서 하나로 인식되더라구요…
엔터를 눌렀을 때 congratulations 어쩌구가 뜨면 인증서 발급이 제대로 완료된 것입니다.
인증서 파일은 기본적으로 아래 디렉토리에 위치하게 되고, 몇 가지 간단한 설정을 통해 사이트에 자물쇠를 걸어줄 수 있습니다.
/etc/letsencrypt/live/example.com/
SSL 사이트 설정 방법은 다른 사이트에도 잘 나와있고 그리 어렵지 않으니 여기선 굳이 서술하지 않겠습니다.
아래 사이트를 이용하면 10초도 안걸려서 대부분의 설정을 끝마칠 수 있으니 참고하시면 좋을 겁니다.
[https://webmaster.cafe/tools/apache-conf-generator/](https://webmaster.cafe/tools/apache-conf-generator/)
아무튼 이렇게 해서 모든 서브도메인을 커버하는 와일드카드 인증서 발급 방법을 알아보았습니다.
이제 무슨 서브 도메인을 추가하든 뒷부분 example.com이 변하지 않는 이상 모두 SSL 인증서가 보장될 겁니다.
도움이 되었으면 좋겠네요. 끝까지 읽어주셔서 감사합니다.^^

