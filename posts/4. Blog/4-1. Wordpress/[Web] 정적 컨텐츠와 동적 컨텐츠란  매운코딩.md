---
page-title: "[Web] 정적 컨텐츠와 동적 컨텐츠란? :: 매운코딩"
url: https://cceeun.tistory.com/68
date: "2023-04-27 22:27:09"
---
Web의 동작 원리에 대한 공부를 했었다. (참고 - [https://cceeun.tistory.com/67](https://cceeun.tistory.com/67) )

[

\[Web\] 웹 서비스 동작 원리

브라우저를 통하여 웹사이트에 접속하였을때 내부적으로 서버에서는 어떤 동작이 일어나고, 웹 데이터의 흐름은 어떻게 흘러가는 것일까?에 대한 궁금증이 생겨 웹의 동작 원리에 대하여 알아�

cceeun.tistory.com



](https://cceeun.tistory.com/67)![](https://scrap.kakaocdn.net/dn/DbShY/hyGeM7OZ3G/JtKmAkTYuJRp448yxf2tV0/img.png?width=800&height=135&face=0_0_800_135,https://scrap.kakaocdn.net/dn/eqYz4u/hyGePQ1Ghq/HkiBfK1Kj38f8e5Sc2TM4k/img.png?width=800&height=135&face=0_0_800_135,https://scrap.kakaocdn.net/dn/HtM0z/hyGeJQMvZL/3fEYCqSGeiJwxRorPvK8p0/img.png?width=750&height=698&face=0_0_750_698)

그렇다면 Web server에서 WAS로 요청할지 말지를 결정하는 요인인 정적 컨텐츠와 동적 컨텐츠는 어떤것을 의미할까?

**<정적 컨텐츠와 동적 컨텐츠>**

**(1) 정적 컨텐츠**

\- 실시간으로 변경할 필요가 없는 데이터. 변화가 없는 데이터.

\- 어떤 접속자에게든 동일한 모습을 반환한다.

\- 그렇기 때문에 웹서버의 디스크에 저장을 해두고 요청이 있으면 웹서버에서 client에게 반환해준다.

(ex. 회사 로고)

**(2) 동적 컨텐츠**

\- 자주 변경되는 데이터. 

\- 접속자의 요청에 따라 각각 다른 형태의 데이터를 반환한다.

\- 이런 데이터는 WAS에서 동적으로 생성하여 웹서버에게 결과를 반환해준다.

(ex. client의 은행 잔고, 인터넷 쇼핑몰 장바구니)