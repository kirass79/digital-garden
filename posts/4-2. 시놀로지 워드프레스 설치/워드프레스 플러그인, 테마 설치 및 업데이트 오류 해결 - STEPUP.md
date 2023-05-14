---
page-title: "워드프레스 플러그인, 테마 설치 및 업데이트 오류 해결 - STEPUP"
url: https://blog.laribbongs.net/%EC%9B%8C%EB%93%9C%ED%94%84%EB%A0%88%EC%8A%A4-%ED%94%8C%EB%9F%AC%EA%B7%B8%EC%9D%B8-%ED%85%8C%EB%A7%88-%EC%84%A4%EC%B9%98-%EC%98%A4%EB%A5%98/
date: "2023-04-14 16:02:57"
---
시놀로지 나스에 워드프레스를 수동 설치 후 테마나 플러그인을 설치할 때 FTP 또는 SSH 자격증명을 입력하라는 화면이 뜰 경우 아래 방법대로 해결하시기 바랍니다.

## FTP 또는 SSH 자격증명 입력 문제 해결

워드프레스 설치 후 기쁜 마음으로 테마 쇼핑과 플러그인 설치를 하려고 하니 아래와 같은 화면이 뜨면서 진행이 되지 않습니다. 주요한 오류 메세지는 “~ FTP 또는 SSH 자격증명을 입력해주세요” 입니다.

![FTP-SSH-자격증명-입력-요청](https://blog.laribbongs.net/wp-content/uploads/2022/02/%ED%94%8C%EB%9F%AC%EA%B7%B8%EC%9D%B8-%EC%84%A4%EC%B9%98-%EC%98%A4%EB%A5%98.jpg)

FTP / SSH 자격증명 입력 요청

위 문제는 워드프레스 설치 폴더에 있는 wp-config.php 파일 내 명령어 한 줄만 추가해주면 깔끔하게 해결이 됩니다.

-   추가할 명령어 : 
	- define(‘FS_METHOD’, ‘direct’);

고수 분들은 터미널로 접속하여 VI편집기를 사용해서 바로 수정도 하지만 저는 그 정도 실력은 가지지 못해 아래와 같이 단순한 방법으로 수정했습니다.

먼저 File Station에서 워드프레스 설치 폴더에 있는 wp-config.php 파일을 다운로드 했습니다. 그리고 atom이라는 코딩 프로그램으로 wp-config.php파일을 열어서 아래와 같이 제일 마지막 줄에 위 명령어를 추가했습니다.

![wp-config.php-명령어-추가](https://blog.laribbongs.net/wp-content/uploads/2022/02/wp-config.php-%EB%AA%85%EB%A0%B9%EC%96%B4-%EC%B6%94%EA%B0%80.jpg)

wp-config.php 명령어 추가

저장을 한 후 wp-config.php파일을 다시 File Station을 사용하여 원래 있었던 워드프레스 설치 폴더에 업로드했습니다.

구글링을 해보면 위와 같은 방법으로 안내가 되어 있고 실제 적용 후 한달여간 사용하면서 테마/플러그인 설치 및 업데이트가 전혀 이상없이 진행됩니다. 같은 문제로 고생하고 계시는 분들이 계시다면 도움되시길 바랍니다.

# 사견
- define(‘FS_METHOD’, ‘direct’);를 붙여넣기 하면서 두가지 조심해야할 사항이 있고 문제시 에러가 발생함
	- 먼저 define(‘FS\_METHOD’, ‘direct’);와 같이 예견치 않게 \ 이 들어가는 경우가 있었고
	- 다음으로 define('FS_METHOD’, ‘direct’);에서 '따옴표'모양이 두꺼운 따옴표를 사용하는 것으로 변환되어 생기는 문제였음

***함께보면 좋은 글.***

-   [시놀로지 NAS 개인 도메인 연결 방법](https://blog.laribbongs.net/%ec%8b%9c%eb%86%80%eb%a1%9c%ec%a7%80-nas-%ea%b0%9c%ec%9d%b8-%eb%8f%84%eb%a9%94%ec%9d%b8-%ec%97%b0%ea%b2%b0/)
-   [시놀로지 나스, 공유기 포트포워딩 설정으로 외부에서 접속 하기](https://blog.laribbongs.net/%ec%8b%9c%eb%86%80%eb%a1%9c%ec%a7%80-%eb%82%98%ec%8a%a4-%ea%b3%b5%ec%9c%a0%ea%b8%b0-%ed%8f%ac%ed%8a%b8%ed%8f%ac%ec%9b%8c%eb%94%a9-%ec%84%a4%ec%a0%95%ec%9c%bc%eb%a1%9c-%ec%99%b8%eb%b6%80%ec%97%90/)
-   [시놀로지 나스 워드프레스 설치 이대로만 하세요 1탄.](https://blog.laribbongs.net/%ec%8b%9c%eb%86%80%eb%a1%9c%ec%a7%80-%eb%82%98%ec%8a%a4-%ec%9b%8c%eb%93%9c%ed%94%84%eb%a0%88%ec%8a%a4-%ec%84%a4%ec%b9%98-1%ed%83%84/)
-   [시놀로지 나스 워드프레스 설치 이대로만 하세요 2탄.](https://blog.laribbongs.net/%ec%8b%9c%eb%86%80%eb%a1%9c%ec%a7%80-%eb%82%98%ec%8a%a4-%ec%9b%8c%eb%93%9c%ed%94%84%eb%a0%88%ec%8a%a4-%ec%84%a4%ec%b9%98-2%ed%83%84/)
#블로그 