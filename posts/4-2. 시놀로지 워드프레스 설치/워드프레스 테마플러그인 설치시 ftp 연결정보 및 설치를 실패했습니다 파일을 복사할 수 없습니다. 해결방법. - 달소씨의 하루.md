---
page-title: "워드프레스 테마/플러그인 설치시 ftp 연결정보 및 설치를 실패했습니다: 파일을 복사할 수 없습니다. 해결방법. - 달소씨의 하루"
url: https://blog.dalso.org/article/%EC%9B%8C%EB%93%9C%ED%94%84%EB%A0%88%EC%8A%A4-%ED%85%8C%EB%A7%88-%ED%94%8C%EB%9F%AC%EA%B7%B8%EC%9D%B8-%EC%84%A4%EC%B9%98%EC%8B%9C-ftp-%EC%97%B0%EA%B2%B0%EC%A0%95%EB%B3%B4-%EB%B0%8F-%EC%84%A4%EC%B9%98
date: "2023-04-27 19:52:07"
---
안녕하세요. 달소입니다.

오랜만에 워드프레스를 만들어서 이것저것 하려다보니 초기셋팅이 필요한게 한두가지가 아니네요…

초반에 바짝 셋팅해놓으면 추후에는 손댈일이 없기때문에 한번만 고생하시면됩니다!.

먼저 테마/플러그인 설치시에 바로 팝업창으로 뜨는 FTP 관련 이슈 해결방법입니다.

워드프레스는 기본적으로 테마/플러그인 설치시 FTP의 인증정보를 물어보는데요.  
FTP 셋팅이 꽤나 번거로운편이기때문에 보통 인증창을 스킵하고 디렉터리 권한변경으로 문제를 해결합니다.

![image.png.jpg](https://svrforum.com/files/attach/images/2021/06/18/2f1ba5fae562dacf564b26beeacde681.jpg)

간단하게 wp-conpig.php 파일에 아래내용을 추가해주면됩니다.

- define(‘FS_METHOD’, ‘direct’);

![image.png.jpg](https://svrforum.com/files/attach/images/2021/06/18/90a3e5217781fd6f16b4f8a3b663d2e8.jpg)

![image.png.jpg](https://svrforum.com/files/attach/images/2021/06/18/d3caafc906977f608418e653d7ed4457.jpg)

이제 다음 문제가 바로 또 발생합니다. 

![image.png.jpg](https://svrforum.com/files/attach/images/2021/06/18/df72f7469e0ecf60d520fb62f409edc7.jpg)

설치를 실패했습니다: 파일을 복사할 수 없습니다.

바로 권한문제인데요.

이부분도 wp-content 디렉터리에 대해 권한을 777로 주면 해결됩니다.

**cd /var/www/html 웹루트 폴더로 이동후**

**chmod -R 777 wp-content/**

![image.png.jpg](https://svrforum.com/files/attach/images/2021/06/18/9a8726601b8499805a0b2a77bb39e702.jpg)

그다음 다시 설치버튼을 누르면 설치가 완료됩니다.

![image.png.jpg](https://svrforum.com/files/attach/images/2021/06/18/e61b3761df32986f70d813fb80148fd3.jpg)

이것으로 

**FTP 이슈 –** 요청한 작업을 수행하려면, 워드프레스는 웹 서버에 접속해야 합니다. 계속하려면 FTP 자격증명을 입력해주세요. 자격증명을 기억하고 있지 않다면, 웹 호스트에 연락해야 합니다.

**설치 이슈** – 연결정보 및 설치를 실패했습니다: 파일을 복사할 수 없습니다.

해결방법이였습니다.

**————————————————–**

사이트 리뉴얼중입니다~

서버(Linux, ESXi), NAS(헤놀로지, ESXi 및 IT관련 정보, 기타 등등을 공유하는 커뮤니티 [SVRFORUM](https://svrforum.com/)을 새로 만들었습니다.  
많은 가입(?) 부탁드립니다~  
[**https://svrforum.com**](https://svrforum.com/)

이전글들은 모두 상단 메뉴의 Blog 글 모음에있습니다!