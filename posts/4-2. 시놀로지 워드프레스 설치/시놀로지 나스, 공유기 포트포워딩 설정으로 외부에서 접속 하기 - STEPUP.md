---
page-title: "시놀로지 나스, 공유기 포트포워딩 설정으로 외부에서 접속 하기 - STEPUP %"
url: https://blog.laribbongs.net/%ec%8b%9c%eb%86%80%eb%a1%9c%ec%a7%80-%eb%82%98%ec%8a%a4-%ea%b3%b5%ec%9c%a0%ea%b8%b0-%ed%8f%ac%ed%8a%b8%ed%8f%ac%ec%9b%8c%eb%94%a9-%ec%84%a4%ec%a0%95%ec%9c%bc%eb%a1%9c-%ec%99%b8%eb%b6%80%ec%97%90/
date: "2023-04-11 15:40:31"
---
시놀로지 나스를 100% 활용하기 위해서는 외부 네트워크에서도 접속이 가능해야합니다. 시놀로지 나스를 같은 공유기를 사용하는 내부 네트워크에서만 사용하기에는 너무 아까운 장비입니다. 외부에서 나스에서 운영중인 웹사이트 또는 워드프레스 블로그 등에 접속하기 위해서는 공유기 설정에서 포트포워딩이라는 조치를 해주셔야합니다.

## 포트포워딩이란?

포트포워딩에 대한 개념은 구글링이나 아래 유튜브 영상을 통해서 공부해보실 것을 추천드립니다. 포트포워딩을 조금 더 깊게 이해하기 위해서는 웹 환경, IP주소 등 조금 더 폭넓은 개념에 대한 학습이 필요합니다. 그래서 아래 유튜브 채널을 통해서 공부를 해보시면 큰 도움이 되실 것입니다. 저도 이것을 보면서 웹 환경에 대한 이해도가 많이 올라갔습니다.

## 넷기어 RAX10 포트포워딩 방법

위에서 이야기한 포트포워딩에 대한 개념을 학습 하셨다면, 실제로 공유기 관리자 설정화면에서 어떻게 포트포워딩을 할 수 있는지 알려드리겠습니다. 사실 위 영상을 보시지 않고 지금부터 순서대로 따라만하셔도 설정은 가능합니다.

제가 사용 중인 공유기는 넷기어의 RAX10이라는 모델입니다. 일반적으로 집에서 IPTime제품을 많이 사용하실텐데, 설정 화면은 달라도 큰 흐름은 거의 동일하기 때문에 아래 내용을 보면서 따라하시면 됩니다.

우선 공유기 관리자 설정 창으로 이동하도록 하겠습니다. 일반적으로 집에서 사용하는 공유기의 관리자 설정 화면은 웹브라우저에 192.168.1.1을 입력하시면됩니다.

넷기어 RAX10 모델의 관리자 설정 화면은 아래와 같습니다. 포트포워딩을 하기 위해서는 고급 설정 메뉴로 이동하셔야합니다.

![RAX10-공유기-관리자-설정-화면](https://blog.laribbongs.net/wp-content/uploads/2022/01/rax10-%E1%84%80%E1%85%AA%E1%86%AB%E1%84%85%E1%85%B5%E1%84%8C%E1%85%A1-%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8C%E1%85%A5%E1%86%BC.png)

RAX10 공유기 관리자 설정

고급 설정 메뉴에서는 공유기 관련된 다양한 세부설정을 할 수 있는데, 여기에 포트포워딩을 설정할 수 있는 메뉴가 있습니다.

![RAX10-공유기-관리자-고급-설정-포트포워딩](https://blog.laribbongs.net/wp-content/uploads/2022/01/rax10-%E1%84%80%E1%85%A9%E1%84%80%E1%85%B3%E1%86%B8%E1%84%89%E1%85%A5%E1%86%AF%E1%84%8C%E1%85%A5%E1%86%BC-1024x772.png)

RAX10 공유기 관리자 고급 설정

RAX10 공유기의 포트포워딩 메뉴에 들어가서 서비스는 ‘HTTP’를 선택하고 서버 IP주소에는 내 시놀로지 나스의 내부 IP 정보를 입력한 후 추가를 해줍니다.

![HTTP-서비스-포트포워딩](https://blog.laribbongs.net/wp-content/uploads/2022/01/rax10-%E1%84%91%E1%85%A9%E1%84%90%E1%85%B3%E1%84%91%E1%85%A9%E1%84%8B%E1%85%AF%E1%84%83%E1%85%B5%E1%86%BC-1024x538.png)

HTTP 서비스 포트포워딩

추가를 하면 아래와 같이 HTTP서비스가 추가가 되면서 외부, 내부 포트 번호가 ’80’으로 설정된 것을 확인할 수 있습니다. 참고로 HTTP 서비스는 포트번호 80, HTTPS 서비스는 포트번호 443입니다. 보안 연결을 위해서 HTTPS 서비스도 이용해야하기 때문에 443번 포트도 포트포워딩을 해주도록 하겠습니다.

![포트포워딩-80번포트](https://blog.laribbongs.net/wp-content/uploads/2022/01/%E1%84%91%E1%85%A9%E1%84%90%E1%85%B3%E1%84%91%E1%85%A9%E1%84%8B%E1%85%AF%E1%84%83%E1%85%B5%E1%86%BC-http%E1%84%8E%E1%85%AE%E1%84%80%E1%85%A1-1024x140.png)

80번포트 포트포워딩 등록

HTTP 서비스 앞에 있는 체크박스에 체크를 하고 아래에 있는 ‘서비스 편집’을 눌러서 아래와 같이 외부 포트 범위에 443을 추가해주도록 합니다.

![포트포워딩-443번-포트-추가](https://blog.laribbongs.net/wp-content/uploads/2022/01/%E1%84%91%E1%85%A9%E1%84%90%E1%85%B3%E1%84%91%E1%85%A9%E1%84%8B%E1%85%AF%E1%84%83%E1%85%B5%E1%86%BC-443%E1%84%91%E1%85%A9%E1%84%90%E1%85%B3-%E1%84%8E%E1%85%AE%E1%84%80%E1%85%A1-1024x753.png)

443번 포트 추가

443번 포트를 추가하고 나면 아래와 같이 HTTP서비스에 80번 포트와 443번 포트가 설정되어 있는 것을 확인할 수 있습니다. 이제 포트포워딩이 완료되었습니다.

![HTTP-HTTPS-서비스-포트포워딩](https://blog.laribbongs.net/wp-content/uploads/2022/01/%E1%84%91%E1%85%A9%E1%84%90%E1%85%B3%E1%84%91%E1%85%A9%E1%84%8B%E1%85%AF%E1%84%83%E1%85%B5%E1%86%BC-https-%E1%84%8E%E1%85%AE%E1%84%80%E1%85%A1-1024x143.png)

80번포트, 443번포트 포트포워딩

시놀로지 나스를 외부에서도 접속하기 위해서 공유기 넷기어 RAX10에 포트포워딩을 하는 방법을 알려드렸습니다. 개인도메인을 구입해서 나스와 연결하고 워드프레스를 운영하는 방법은 아래 글을 참고하시기 바랍니다.

***함께보면 좋은 글.***

-   [시놀로지 NAS 개인 도메인 연결 방법](https://blog.laribbongs.net/%ec%8b%9c%eb%86%80%eb%a1%9c%ec%a7%80-nas-%ea%b0%9c%ec%9d%b8-%eb%8f%84%eb%a9%94%ec%9d%b8-%ec%97%b0%ea%b2%b0/)
-   [시놀로지 나스 워드프레스 설치 이대로만 하세요 1탄.](https://blog.laribbongs.net/%ec%8b%9c%eb%86%80%eb%a1%9c%ec%a7%80-%eb%82%98%ec%8a%a4-%ec%9b%8c%eb%93%9c%ed%94%84%eb%a0%88%ec%8a%a4-%ec%84%a4%ec%b9%98-1%ed%83%84/)
-   [시놀로지 나스 워드프레스 설치 이대로만 하세요 2탄.](https://blog.laribbongs.net/%ec%8b%9c%eb%86%80%eb%a1%9c%ec%a7%80-%eb%82%98%ec%8a%a4-%ec%9b%8c%eb%93%9c%ed%94%84%eb%a0%88%ec%8a%a4-%ec%84%a4%ec%b9%98-2%ed%83%84/)
#블로그 