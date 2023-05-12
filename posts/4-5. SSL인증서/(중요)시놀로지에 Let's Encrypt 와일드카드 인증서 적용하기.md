---
page-title: "시놀로지에 Let's Encrypt 와일드카드 인증서 적용하기 :: www.uname.in"
url: https://www.uname.in/78
date: "2023-04-26 16:49:12"
---
시놀로지의 제어판에서 발급 받을 수 있는 Let's Encrypt 인증서는 90일 짜리 SSL 인증서 입니다.

시놀로지에서 SSL 인증서는 버튼 몇 번이면 발급이 가능하고, 자동으로 갱신까지 해줘서 매우 편리하게 SSL을 사용할 수 있다는 장점이 있으나,

하위 도메인에 대해서 매번 정의해줘야만 적용이 되는 번거로움이 있습니다.

Wildcard(와일드카드)는 하위 도메인에 대한 문제점을 해결합니다.

예를 들어, yourdomain.com과 its.yourdomain.com이라는 도메인이 있다고 가정합니다.

its.yourdomain.com은 yourdomain.com의 하위 도메인 입니다.

SSL 인증서에서는 하위 도메인이 많으면 많을 수록 abc.yourdomain.com. its.yourdomain.com. test.yourdomain.com, ... 와 같이 정의한 후 인증서를 갱신해주어야 하위 도메인까지 SSL이 적용 되지만 와일드카드는 단 두개만 정의하면 하위도메인까지 완벽하게 SSL을 적용 시킬 수 있습니다.

yourdomain.com과 \*.yourdomain.com 만 정의하면 됩니다. (\*은 모든 단어가 들어갈 수 있음을 의미합니다.)

만약 it.is.yourdomain.com과 같이 하위 도메인이 여러 수준으로 나뉘어 있다면, \*.\*.yourdomain.com으로 정의하기만 하면 4차 도메인까지 모두 SSL이 적용됩니다.

거기다 와일드카드는 하위 도메인에 대해 개수 제한이 없습니다.

하위 도메인이 100개든 1000개든 1만개든 상관이 없다는 거지요.

장점 하나하나가 모두 크게 작용합니다.

다만 시놀로지에서는 기본적으로 발급을 지원해주지 않기 때문에 초기 설정이 약간 번거롭습니다.

(물론 한번 설정해두면 알아서 스크립트가 돌면서 갱신하기 때문에 사실 걱정은 없습니다.)

시놀로지에 와일드카드 인증서 발급 후 적용까지, 시작해 보겠습니다.

작업 환경

\- Synology DS918+ (DSM 6.2.2-24922 Update 5)

시놀로지에서 SSH 기능 활성화

우선, 작업을 위해서는 ssh를 사용해야 합니다.

'제어판 -> 터미널 및 SNMP'에서 'SSH 서비스 활성화'에 체크한 후 \[ 적용 \]을 누릅니다.

acme.sh 스크립트 설정

Let's Encrypt에 와일드카드 발급을 요청하기 위해서는 acme.sh 라는 스크립트를 사용해야 합니다.

무려 와일드카드 발급을 위해 간단해진 자동화 스크립트입니다.

각자 사용하실 ssh 프로그램을 열고, 시놀로지에 접속한 뒤 아래 명령어를 입력합니다.

$ wget [https://raw.githubusercontent.com/acmesh-official/acme.sh/master/acme.sh](https://raw.githubusercontent.com/acmesh-official/acme.sh/master/acme.sh)

그 후 스크립트 파일을 실행하기 위해, 실행 권한을 부여합니다.

$ sudo chmod a+x acme.sh

와일드카드 인증서 발급

인증서 발급 과정입니다.

아래 명령어를 자신에게 맞게 몇가지 수정 후 실행해야 합니다.

$ /var/services/homes/사용자 이름/acme.sh --issue --dns --force -d 내 도메인 -d \*.내 도메인 --yes-I-know-dns-manual-mode-enough-go-ahead-please

사용자 이름

시놀로지의 homes 폴더 내의 내용물과 같은 위치입니다. 자신의 계정 이름을 적어주시면 됩니다.

내 도메인

와일드카드 인증서를 실제로 사용할 2차 도메인을 입력합니다. (예: yourdomain.com)

명령어를 치고 엔터를 누르면 뭔가 주르륵 뜨고 끝납니다.

당황하지 마시고, 딱 두 개만 보면 됩니다.

Domain: '\_acme-challenge.내 도메인'

TXT value: "키 값"

여러개가 있으면 있는 것 모두 다 보셔야 합니다.

도메인 관리 사이트(가비아, DNSZi 등)를 통해 DNS 레코드를 관리하고 계신다면, 사이트에서 TXT 레코드를 추가한 뒤 저장합니다.

시놀로지에서 DNS 서버 패키지를 운영하고 계신다면, TXT 레코드를 추가해서 입력 후 적용하시면 됩니다.

TXT 레코드가 잘 적용이 되었는지 확인하기 위해, nslookup을 통해 테스트 해 봅니다.

nslookup > set type=txt > \_acme-challenge.내 도메인

입력한 TXT 레코드의 내용이 잘 나타나면 DNS 서버 설정은 끝입니다.

인증서 갱신 명령어를 입력해서 최종적으로 인증서 발급을 완료합니다.

$ /var/services/homes/사용자 이름/acme.sh --renew --dns --force -d 내 도메인 -d \*.내 도메인 --yes-I-know-dns-manual-mode-enough-go-ahead-please

인증서는 /var/services/homes/사용자 이름/.acme.sh/내 도메인 폴더에 저장됩니다.

다만 갱신이 지속적으로 되는 과정에서는 /root/.acme.sh/내 도메인에 저장이 되고 갱신이 되는 것을 반복하기 때문에, 사실상 저 폴더는 필요가 없습니다.

스크립트만 잘 보관해주시면 됩니다.

이제 인증서 최초 발급 절차는 끝났습니다.

작업 스케줄러 등록으로 인증서 자동 갱신하면 됩니다.

인증서는 3개월 동안 유효합니다.

제어판에서 설정한 Let's Encrypt SSL 인증서는 한번 설정해두면 시놀로지에서 알아서 갱신했지만, 수동으로 발급한 Let's Encrypt 와일드카드는 그렇지 않습니다.

그렇다고 매번 ssh 쉘을 열어서 저 명령어를 써 넣고 인증서를 빼내서 갱신할 수는 없겠지요..ㅎㅎ

작업 스케줄러를 이용하면 아주 편하게 자동 갱신이 가능합니다.

작업 스케줄러에 작업을 추가하기 전, 선행되어야 하는 작업이 두 가지 있습니다.

1\. 발급한 와일드카드 인증서를 시놀로지에 추가

2\. 추가한 인증서의 경로 확인

1\. 발급한 와일드카드 인증서를 시놀로지에 추가

먼저, 조금전에 발급한 인증서를 PC로 받아와야 합니다.

파일 스테이션을 열고, home 폴더로 간 뒤, '.acme.sh' 폴더 안에 있는 본인 도메인 이름으로 된 폴더를 우클릭 하고

\[ 다운로드 \]를 누릅니다.

압축 파일 하나가 다운로드 됩니다.

다운로드 하고 열어서 압축까지 풀어줍니다.

압축 푼 후  필요한 것은 3개 입니다.

\- 내 도메인.key

\- 내 도메인.cer

\- ca.cer

​

파일은 준비되었으니, 이제 시놀로지에 인증서를 추가합니다.

'제어판 -> 보안 -> 인증서'에 들어간 뒤, \[ 추가 \]를 누릅니다.

'새 인증서 추가'를 클릭하고 \[ 다음 \]을 누릅니다.

'인증서 가져오기'를 선택하고 '기본 인증서로 설정'에 체크합니다.

조금 전에 받았던 파일들을 넣어줘야 합니다.

​

개인키 - 내 도메인.key

인증서 - 내 도메인.cer

중간 인증서 - ca.cer

넣고 \[ 확인 \]을 눌러주면 인증서가 추가된 것을 확인할 수 있습니다.

\[ 구성 \]을 눌러서 원하는 패키지의 인증서를 방금 추가한 인증서로 변경해줍니다.

이제 인증서의 경로를 알아내야 합니다.

2\. 추가한 인증서의 경로 확인

아래 명령을 입력해서 root 권한을 취득합니다.

암호는 시놀로지 계정 암호 입니다.

$ sudo -i

'/usr/syno/etc/certificate/\_archive' 경로의 DEFAULT 파일을 읽어서 기본 인증서의 폴더가 어느 것인지 알아냅니다.

\# cat /usr/syno/etc/certificate/\_archive/DEFAULT M5DH8Q

저는 M5DH8Q 라는 폴더에 있다고 가정해 보겠습니다.

제어판에서 추가한 인증서들은 '/usr/syno/etc/certificate/\_archive'에 각각 랜덤한 이름을 가진 폴더별로 저장되고

이 인증서 중 기본 인증서가 '/usr/syno/etc/certificate/system/default'에 복사되는 구조입니다.

그러면 '/usr/syno/etc/certificate/system/default'로 인증서를 바로 복사하면 되는 것 아니냐 라고 하실 수 있는데

이렇게 하면 DSM 6.2.2-24922 Update 5 기준으로, 제어판의 인증서 탭에도 뜨지 않고 사이트에 반영도 되지 않을 뿐더러 시놀로지를 재시작 해도 그대로였습니다.

자, 이제 인증서의 경로까지 파악을 했습니다.

이 경로는 인증서를 제거하기 전까지는 유효합니다.

이제 인증서 갱신을 위해, 최종적으로 작업 생성을 해야 합니다.

'제어판 -> 작업 스케줄러'에 들어갑니다.

생성 -> 예약된 작업 -> 사용자 정의 스크립트 순으로 클릭합니다.

작업 이름은 보기 편한 이름으로 해주시면 되고

사용자는 반드시 'root' 여야 합니다.

작업 주기를 설정합니다.

저는 매주 금요일마다 돌게끔 설정했습니다.

'실행 명령'의 '사용자 정의 스크립트' 부분에 내용을 모두 지우고, 아래 명령줄을 추가합니다.

\# 인증서 갱신

/var/services/homes/사용자 이름/acme.sh --renew --dns --force -d 내 도메인 -d \*.내 도메인 --yes-I-know-dns-manual-mode-enough-go-ahead-please

\# 갱신된 인증서를 시놀로지에 등록

/bin/cp /root/.acme.sh/내 도메인/내 도메인.cer /usr/syno/etc/certificate/\_archive/폴더 이름/cert.pem 

/bin/cp /root/.acme.sh/내 도메인/ca.cer /usr/syno/etc/certificate/\_archive/폴더 이름/chain.pem 

/bin/cp /root/.acme.sh/내 도메인/fullchain.cer /usr/syno/etc/certificate/\_archive/폴더 이름/fullchain.pem 

/bin/cp /root/.acme.sh/내 도메인/내 도메인.key /usr/syno/etc/certificate/\_archive/폴더 이름/privkey.pem

\# nginx 서비스 재시작 

/usr/syno/sbin/synoservicectl --reload nginx

폴더 이름에는 조금전에 DEFAULT 파일을 읽어서 나온 폴더 이름을 넣어주시면 됩니다.

명령줄이 문제가 없는지 잘 확인하고 \[ 확인 \]을 눌러 작업을 저장합니다.

결과를 메일이나 로그로 받아보시는 분들은 \`date\`나 echo 등을 이용해서 가독성을 향상시킬 수 있습니다.

이로써 시놀로지에 Let's Encrypt 와일드카드 인증서 등록을 완료했습니다.

자체 DNS 서버를 운영하고 있는 데다가, 레코드가 수시로 변동되다 보니까 매번 인증서 갱신하는게 일이었는데

와일드카드를 접하고 나서는 초기 발급만 해주면 레코드를 아무리 많이 추가하고 바꿔도 따로 갱신을 해주지 않아도 되서 너무 편하게 사용하고 있습니다.