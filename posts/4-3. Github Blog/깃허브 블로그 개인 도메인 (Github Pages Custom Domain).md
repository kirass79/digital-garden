---
page-title: "깃허브 블로그 개인 도메인 (Github Pages Custom Domain)"
url: https://wonderbout.tistory.com/120
date: "2023-04-20 04:52:31"
---
1.  [HOME](https://wonderbout.tistory.com/)
2.  [블로그 운영](https://wonderbout.tistory.com/category/%EB%B8%94%EB%A1%9C%EA%B7%B8%20%EC%9A%B4%EC%98%81)
3.  [블로그CMS](https://wonderbout.tistory.com/category/%EB%B8%94%EB%A1%9C%EA%B7%B8%20%EC%9A%B4%EC%98%81/%EB%B8%94%EB%A1%9C%EA%B7%B8CMS)

![thumbnail](https://blog.kakaocdn.net/dn/Q0RuO/btqGJvdRKzU/OhFsa5Oz2JJwBCvi6yUapK/img.png)

[깃허브 페이지](https://pages.github.com/)에 개인 도메인 등록 과정을 설명하기 위해 작성되었습니다. 이미 깃허브 페이지를 이용한 사이트 또는 블로그가 구성되어 있다면 앞부분들은 생략하고 [**깃허브 페이지 커스텀 도메인 등록**](https://wonderbout.tistory.com/120#customDomain) 부분만 살펴보시면 되겠습니다.

**깃허브(Github)**에 가입하고 간단한 index.html 파일을 업로드해 깃허브 페이지를 만들고 **Custom Domain**(개인 도메인)을 등록하는 과정입니다.

---

## 깃허브 가입하기

우선 [깃허브(Github)](https://github.com/) 가입부터 하도록 하겠습니다.

![github](https://blog.kakaocdn.net/dn/d96W1q/btqGK562686/grVjmxYWenKA9QM21YRoLk/img.png)

깃허브 첫 페이지로 접속하면 가입 양식이 보입니다.

1.  **User name**에 영문으로 사용자 명을 입력합니다. 여기서 입력한 이름이 차후 깃허브 페이지에서 사용될 주소가 됩니다. 예) `사용자명. github.io`
2.  회신받을 수 있는 이메일을 입력합니다.
3.  비밀번호를 입력합니다.
4.  **Sign up** 버튼을 클릭합니다.

![계정생성](https://blog.kakaocdn.net/dn/cub8WJ/btqGIJwEH5P/WucPZxG5bGE2t5dNgaJcv1/img.png)

로봇 검증을 마치고 하단에 **Join a free plan** 버튼을 클릭합니다.

![계정생성](https://blog.kakaocdn.net/dn/dRko5X/btqGHw5SwmV/x7947MVUqZniIo0QKMIEv0/img.png)

해당 항목 선택 과정이 나타나면 선택하셔도 되고 하지 않아도 됩니다. 하단에 설정 완료 버튼을 클릭합니다.

---

![계정생성 메일확인](https://blog.kakaocdn.net/dn/H8Hrk/btqGGG8KE0q/DHkzvuwpEoUkLdrTDvFpsk/img.png)

가입 시 입력한 이메일로 이동해 확인하라는 알림이 나타납니다. 각자 메일의 받은 편지함을 확인하고 확인 버튼을 클릭합니다.

---

## 깃허브 리포지토리 생성 하기

![리포지토리 생성 버튼](https://blog.kakaocdn.net/dn/1dNhx/btqGC5OWI0v/8UpOu9Dp4Y2h66lJGuDjmK/img.png)

**Create a reposltory** 버튼을 클릭합니다.

만약 위와 같은 이미지가 나타나지 않았다면 상단 메뉴 중 플러스 표시를 클릭해 **New reposltory**를 선택합니다.

![리포지토리 생성 메뉴](https://blog.kakaocdn.net/dn/bNb3EI/btqGH15ocgw/zfYiPZ7g3s4a4TkUiDaEW1/img.png)

---

![리포지토리 생성](https://blog.kakaocdn.net/dn/b7vRcu/btqGH1j1LRv/XSW6Wts2JcF2UJrC8bmPzk/img.png)

1.  입력창에 회원가입 시 등록한 **Username**(사용자명)을 입력하고 `.github.io`를 붙여 줍니다. 예) `username.github.io`
2.  **Public** 선택
3.  **Create reposltory** 버튼을 클릭합니다.

### 리포지토리에 파일 업로드 하기

리포지토리가 생성되었습니다. 여기서는 **Git Bash**를 사용하지 않고 깃허브에서 바로 간단하게 HTML 파일 한 장만 업로드하고 접속이 되는지만 알아보겠습니다.

![리포지토리 파일 업로드](https://blog.kakaocdn.net/dn/clbMkZ/btqGK23yUYt/ZmWALQa9ICeLqDRPtsA3Rk/img.png)

**uploading an existing** 링크를 클릭합니다.

---

아래 **index.html** 파일을 다운로드해 마우스로 드래그해서 박스 안에 넣어 줍니다.

[

index.html

0.00MB



](https://blog.kakaocdn.net/dn/HFoVA/btqGFbgQfT2/CxgZvmswWXMwFirHt89EA0/index.html?attach=1&knm=tfile.html)

![인덱스 파일 업로드](https://blog.kakaocdn.net/dn/b4i1YV/btqGG0FRCq5/izKPvEInjIlB9TqOAqhCPK/img.png)

파일이 업로드가 되었으면 아래 **Commit changes** 버튼을 클릭합니다.

---

![리포지토리 업로드 확인](https://blog.kakaocdn.net/dn/bk34CO/btqGGZ1hbAW/BkZmjgQctkBoMGSSPPWUN1/img.png)

1.  파일이 잘 업로드되었는지 확인합니다.
2.  상단 메뉴 중 **Settings**를 클릭합니다.

## 깃허브 페이지 접속 확인

설정 페이지에서 아래로 스크롤하면 **GitHub Pages** 항목이 보입니다.

![깃허브 페이지 접속 확인](https://blog.kakaocdn.net/dn/1ulLB/btqGDRizd6T/yJHgxdecy8tS9dRNNAkCI0/img.png)

위 이미지와 같이 초록색으로 체크가 되어 있으면 연결 가능 상태입니다. 각자 클릭해 접속이 되는지 확인해 봅니다.

여기까지 `index.html` 파일만 업로드해 간단한 페이지를 구성해 보았습니다. 차후 정적 사이트 생성기 등을 이용해 멋진 웹 사이드 또는 블로그를 만드는 것도 괜찮을 것입니다.

[StaticGen](https://www.staticgen.com/)에 방문하시면 **휴고, 개츠비, 지킬** 등 다양한 정적 페이지 생성기들을 보실 수 있으니 참고해 보시길 바랍니다.

## 깃허브 페이지 커스텀 도메인 등록

현재까지는 깃허브에서 제공된 서브 도메인으로만 연결이 가능하지만 개인이 소유한 도메인을 연결해 사용할 수도 있습니다.

### 도메인 DNS 설정

도메인 관리 업체로 이동해 도메인 관리(DNS 설정 또는 CNAME 관리 등 업체마다 명칭이 다름) 설정의 갑니다.

![DNS 설정](https://blog.kakaocdn.net/dn/XN83p/btqGHavcGEN/D0KsAVEXhrKMu5TvgOFioK/img.png)

타입을 CNAME으로 하고 네임에 @표시 위치 값에 자신의 깃허브 페이지 주소를 넣어 줍니다.

-   예) `username.github.io`

루트 도메인에 CNAME(별칭)을 사용할 수 없는 경우(호스팅 케이 알)에는 아래 IP 주소들을 A 레드에 입력합니다. IP 주소 중 하나만 등록해도 되지만 전체를 다 등록해 주는 것이 안전합니다.

-   185.199.108.153
-   185.199.109.153
-   185.199.110.153
-   185.199.111.153

![DNS 설정](https://blog.kakaocdn.net/dn/bd9B19/btqGHriWqYw/6GnVSZkTwE6owfZR3bKLV1/img.png)

도메인 관리 업체에 따라 Name 부분에 @골뱅이 표시를 하지 않고 빈란으로 해야 하는 경우도 있습니다.(**호스팅케이알**)

[깃허브 페이지 도움말](https://help.github.com/en/github/working-with-github-pages/managing-a-custom-domain-for-your-github-pages-site) 참조

### 커스텀 도메인 등록

다시 깃허브 설정 페이지에서 **Custom Domain**에 자신의 루트 도메인 주소를 입력하고 **Save** 버튼을 클릭합니다. 서브 도메인을 이용할 경우에는 서브 도메인을 입력합니다.

![custom_domain](https://blog.kakaocdn.net/dn/6sntF/btqGIguHPJD/QTS5QeUXkv2kNH2gPLeEV0/img.png)

잠시 기다리면 또는 잠시 후 새로 고침을 하면 상단에 등록한 도메인 주소가 나타납니다.

![custom_domain_https](https://blog.kakaocdn.net/dn/DI6pB/btqGK3OV8jm/lkTunamkrOldQi6FLKbrRK/img.png)

위 이미지처럼 변경된 도메인 주소가 나타나면 하단에 **Enforce HTTPS**에 체크 표시를 해 HTTPS를 적용합니다.

보안 인증서(https)가 적용되기까지 5~10분 정도 소요됩니다.

보안 인증서가 적용이 되면 아래와 같이 https로 시작하는 도메인 주소가 표시됩니다.

![custom_domain_https](https://blog.kakaocdn.net/dn/bu3QNb/btqGIpLIrq3/0TtDrADUJMoklVZACDPTz1/img.png)

**깃허브**에 가입하고 간단한 **깃허브 페이지**를 만들고 개인 도메인 등록까지 마쳤습니다. **깃허브 페이지**를 이용하면 무료로 **블로그**뿐만 아니라 랜딩 페이지 등으로도 활용할 수 있습니다.

**<함께 보면 좋은 글>  
**

-   [도메인 가격 비교(후이즈, 가비아, 호스팅케이알)](https://wonderbout.tistory.com/117)
-   [무료로 사용할 수 있는 최상위 국가 도메인](https://wonderbout.tistory.com/118)
-   [클라우드플레어로 네임서버 변경 하기](https://wonderbout.tistory.com/119)