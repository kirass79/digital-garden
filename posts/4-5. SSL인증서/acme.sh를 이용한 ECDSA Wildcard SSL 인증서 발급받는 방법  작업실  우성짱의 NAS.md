---
page-title: "acme.sh를 이용한 ECDSA Wildcard SSL 인증서 발급받는 방법 > 작업실 | 우성짱의 NAS"
url: https://www.wsgvet.com/bbs/board.php?bo_table=home&wr_id=591
date: "2023-04-23 07:16:10"
---
[![](https://cdn.wsgvet.com/data/file/home/3232235777_i5yGI3Fu_6a1b55874a58f4242be048aa414b66a4905840fd.png)](https://www.wsgvet.com/bbs/view_image.php?bo_table=home&fn=3232235777_i5yGI3Fu_6a1b55874a58f4242be048aa414b66a4905840fd.png)

0\. 들어가며

certbot을 이용하면 RSA기반 와일드카드 SSL 인증서는 쉽게 발급하고, 갱신이 됩니다.

그런데 ECDSA기반 와일드카드 SSL 인증서는 발급이 되지만 자동갱신이 안되는데요.

제가 2년 동안 RSA 인증서와 ECDSA 인증서를 수동으로 3개월마다 새로 생성했었는데 못할 짓이더라구요 ㅎㅎ

[https://www.wsgvet.com/bbs/board.php?bo\_table=home&wr\_id=492](https://www.wsgvet.com/bbs/board.php?bo_table=home&wr_id=492)

윗글이 4년 전에 썼던 글입니다. ㅎㅎ

RSA 인증서가 이미 설치되어있다고 치고... ECDSA 인증서도 발급받으면서 갱신이 되는 방법에 대해 알아보겠습니다.

사실 이 방법을 알면 그냥 RSA 인증서도 바로 발급됩니다. ㅎㅎ

1\. acme.sh 설치하기

위 명령어로 root 계정으로 들어갑니다.

root 계정이 아니면 권한 문제가 생길 수 있습니다. 공식 매뉴얼에는 sudo 명령어를 추천하지 않습니다.

위 명령어로 설치할 수 있습니다. 만약에 안된다면

위 명령어로도 설치할 수 있습니다.

> ~# curl [https://get.acme.sh](https://get.acme.sh/) | sh  
> 
>   % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
> 
>                                  Dload  Upload   Total   Spent    Left  Speed
> 
> 100   775    0   775    0     0   2516      0 --:--:-- --:--:-- --:--:--  2516
> 
>   % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
> 
>                                  Dload  Upload   Total   Spent    Left  Speed
> 
> 100  192k  100  192k    0     0  2320k      0 --:--:-- --:--:-- --:--:-- 2348k
> 
> \[Tue 02 Jun 2020 06:28:31 PM KST\] Installing from online archive.
> 
> \[Tue 02 Jun 2020 06:28:31 PM KST\] Downloading [https://github.com/acmesh-official/acme.sh/archive/master.tar.gz](https://github.com/acmesh-official/acme.sh/archive/master.tar.gz)
> 
> \[Tue 02 Jun 2020 06:28:32 PM KST\] Extracting master.tar.gz
> 
> \[Tue 02 Jun 2020 06:28:32 PM KST\] Installing to /root/.acme.sh
> 
> \[Tue 02 Jun 2020 06:28:32 PM KST\] Installed to /root/.acme.sh/acme.sh
> 
> \[Tue 02 Jun 2020 06:28:32 PM KST\] Installing alias to '/root/.bashrc'
> 
> \[Tue 02 Jun 2020 06:28:32 PM KST\] OK, Close and reopen your terminal to start using acme.sh
> 
> \[Tue 02 Jun 2020 06:28:32 PM KST\] Installing cron job
> 
> \[Tue 02 Jun 2020 06:28:32 PM KST\] Good, bash is found, so change the shebang to use bash as preferred.
> 
> \[Tue 02 Jun 2020 06:28:33 PM KST\] OK
> 
> \[Tue 02 Jun 2020 06:28:33 PM KST\] Install success!
> 
> ~#

위와 같이 설치가 됩니다.

SSH 터미널(Putty 등)을 끄고, 다시 접속합니다.

SSH에 다시 접속하면 별다른 작업을 하지 않아도 root 계정으로 acme.sh 명령어를 바로 쓸 수 있습니다.

2\. 클라우드플레어 API key 찾고 입력하기

클라우드플레어의 DNS 기능이 정말 간편하고 좋다고 생각합니다.

하지만 아쉽게도 .cf, .ga, .gq, .ml .tk와 같은 무료 도메인에 대해서는 클라우드플레어에서는 DNS 인증을 지원하지 않습니다.

이는 무료 도메인의 경우 대부분이 스팸 또는 테스트 용도로 쓰고 있기 때문에 서비스를 하지 않는 것 같습니다.

letsencrypt의 경우 와일드카드 SSL 인증서를 받으려면 DNS 인증을 받아야 되는데, 클라우드플레어에서는 불가능합니다.

따라서  [LuaDNS API를 이용한 무료도메인 와일드카드 SSL 인증서 발급 받기(링크)](https://www.wsgvet.com/bbs/board.php?bo_table=home&wr_id=640) 를 추천합니다.

또는 DNS 인증없이 4번의 멀티도메인으로 발급 받기로 가면 됩니다!

.cf, .ga, .gq, .ml .tk 도메인이 아니라면 클라우드플레어 API 인증 받는 것이 추후에도 훨씬 편하기 때문에 추천드립니다.  

[https://dash.cloudflare.com/profile/api-tokens](https://dash.cloudflare.com/profile/api-tokens)

위 링크로 들어가서 로그인 후 API keys를 찾습니다.

[![](https://cdn.wsgvet.com/data/file/home/3232235777_pawlAE6i_74e23a7afc0bcbf01e06a62ac4f6de69ef2cb732.png)](https://www.wsgvet.com/bbs/view_image.php?bo_table=home&fn=3232235777_pawlAE6i_74e23a7afc0bcbf01e06a62ac4f6de69ef2cb732.png)

**Keys used to access Cloudflare APIs.  
**

**Global API Key**에서 View를 누릅니다.

비번 인증하고 사람 체크하면 키가 보입니다.

123891273487129384123asdfajsdfa   

위와 같은 형식으로 나올텐데요.

SSH에서 

위와 같이 넣어줍니다.

위와 같은 형식으로 이메일 주소도 넣습니다.

3\. 인증서 발급받기

위 명령어로 인증서 발급 받을 폴더를 생성합니다.

이제 인증서를 발급 받을 차례입니다.

와일드카드 인증서를 발급받을 것이며, ec-384 옵션을 통해 ECDSA 인증서를 발급 받을 것입니다.

참고로 ec 옵션은 총 3가지가 가능합니다.

ec-256 (prime256v1, "ECDSA P-256")

ec-384 (secp384r1, "ECDSA P-384")

ec-521 (secp521r1, "ECDSA P-521", which is not supported by Let's Encrypt yet.)

아직 Let's encrypt에서는 ECDSA P-521을 지원하지 않으므로 쓰면 안되겠죠? ^^;;

그리고 숫자가 높을수록 보안이 높아지는데, 속도와 타협하기 위하여 ec-256을 선택하는 것이 현실적으로는 가장 좋다고 생각합니다.

ECDSA P-256으로 해도 RSA 2048 bit보다 암호화 강도가 높습니다.

발급은 제 홈페이지 주소로 해보았습니다.

실제 결과

> \# acme.sh --issue --dns dns\_cf -d wsgvet.com -d '\*.wsgvet.com' --keylength ec-384 \\  
> 
> \> --key-file       /etc/nginx/ssl/privkey.pem  \\
> 
> \> --fullchain-file /etc/nginx/ssl/fullchain.pem \\
> 
> \> --cert-file /etc/nginx/ssl/chain.pem \\
> 
> \> --reloadcmd     "systemctl reload nginx.service"
> 
> \[Tue 02 Jun 2020 07:20:39 PM KST\] Creating domain key
> 
> \[Tue 02 Jun 2020 07:20:39 PM KST\] The domain key is here: /etc/letsencrypt/wsgvet.com\_ecc/wsgvet.com.key
> 
> \[Tue 02 Jun 2020 07:21:26 PM KST\] Multi domain='DNS:wsgvet.com,DNS:\*.wsgvet.com'
> 
> \[Tue 02 Jun 2020 07:21:26 PM KST\] Getting domain auth token for each domain
> 
> \[Tue 02 Jun 2020 07:21:33 PM KST\] Getting webroot for domain='wsgvet.com'
> 
> \[Tue 02 Jun 2020 07:21:33 PM KST\] Getting webroot for domain='\*.wsgvet.com'
> 
> \[Tue 02 Jun 2020 07:21:33 PM KST\] Adding txt value: k for domain:  \_acme-challenge.wsgvet.com
> 
> \[Tue 02 Jun 2020 07:21:35 PM KST\] Adding record
> 
> \[Tue 02 Jun 2020 07:21:35 PM KST\] Added, OK
> 
> \[Tue 02 Jun 2020 07:21:35 PM KST\] The txt record is added: Success.
> 
> \[Tue 02 Jun 2020 07:21:35 PM KST\] Adding txt value: 7iL0 for domain:  \_acme-challenge.wsgvet.com
> 
> \[Tue 02 Jun 2020 07:21:37 PM KST\] Adding record
> 
> \[Tue 02 Jun 2020 07:21:38 PM KST\] Added, OK
> 
> \[Tue 02 Jun 2020 07:21:38 PM KST\] The txt record is added: Success.
> 
> \[Tue 02 Jun 2020 07:21:38 PM KST\] Let's check each dns records now. Sleep 20 seconds first.
> 
> \[Tue 02 Jun 2020 07:21:59 PM KST\] Checking wsgvet.com for \_acme-challenge.wsgvet.com
> 
> \[Tue 02 Jun 2020 07:21:59 PM KST\] Domain wsgvet.com '\_acme-challenge.wsgvet.com' success.
> 
> \[Tue 02 Jun 2020 07:21:59 PM KST\] Checking wsgvet.com for \_acme-challenge.wsgvet.com
> 
> \[Tue 02 Jun 2020 07:22:00 PM KST\] Domain wsgvet.com '\_acme-challenge.wsgvet.com' success.
> 
> \[Tue 02 Jun 2020 07:22:00 PM KST\] All success, let's return
> 
> \[Tue 02 Jun 2020 07:22:00 PM KST\] Verifying: wsgvet.com
> 
> \[Tue 02 Jun 2020 07:22:05 PM KST\] Success
> 
> \[Tue 02 Jun 2020 07:22:05 PM KST\] Verifying: \*.wsgvet.com
> 
> \[Tue 02 Jun 2020 07:22:09 PM KST\] Success
> 
> \[Tue 02 Jun 2020 07:22:09 PM KST\] Removing DNS records.
> 
> \[Tue 02 Jun 2020 07:22:09 PM KST\] Removing txt: qehk for domain: \_acme-challenge.wsgvet.com
> 
> \[Tue 02 Jun 2020 07:22:11 PM KST\] Removed: Success
> 
> \[Tue 02 Jun 2020 07:22:11 PM KST\] Removing txt: Vc4a9s7iL0 for domain: \_acme-challenge.wsgvet.com
> 
> \[Tue 02 Jun 2020 07:22:14 PM KST\] Removed: Success
> 
> \[Tue 02 Jun 2020 07:22:14 PM KST\] Verify finished, start to sign.
> 
> \[Tue 02 Jun 2020 07:22:14 PM KST\] Lets finalize the order, Le\_OrderFinalize:
> 
> \[Tue 02 Jun 2020 07:22:16 PM KST\] Download cert, Le\_LinkCert: 
> 
> \[Tue 02 Jun 2020 07:22:18 PM KST\] Cert success.
> 
> \-----BEGIN CERTIFICATE-----
> 
> xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
> 
> \-----END CERTIFICATE-----
> 
> \[Tue 02 Jun 2020 07:22:18 PM KST\] Your cert is in  /etc/letsencrypt/wsgvet.com\_ecc/wsgvet.com.cer
> 
> \[Tue 02 Jun 2020 07:22:18 PM KST\] Your cert key is in  /etc/letsencrypt/wsgvet.com\_ecc/wsgvet.com.key
> 
> \[Tue 02 Jun 2020 07:22:18 PM KST\] The intermediate CA cert is in  /etc/letsencrypt/wsgvet.com\_ecc/ca.cer
> 
> \[Tue 02 Jun 2020 07:22:18 PM KST\] And the full chain certs is there:  /etc/letsencrypt/wsgvet.com\_ecc/fullchain.cer
> 
> \[Tue 02 Jun 2020 07:22:18 PM KST\] Installing cert to:/etc/nginx/ssl/chain.pem
> 
> \[Tue 02 Jun 2020 07:22:18 PM KST\] Installing key to:/etc/nginx/ssl/privkey.pem
> 
> \[Tue 02 Jun 2020 07:22:18 PM KST\] Installing full chain to:/etc/nginx/ssl/fullchain.pem
> 
> \[Tue 02 Jun 2020 07:22:18 PM KST\] Run reload cmd: systemctl reload nginx.service
> 
> \[Tue 02 Jun 2020 07:22:18 PM KST\] Reload success
> 
> ~#

잘 발급되고, 인증서도 원하는 위치로 이동된 것을 알 수 있습니다.

참고로 RSA 인증서 발급도 가능합니다.

위와 같이 keylength부분을 그냥 빼면 됩니다..

명령어 단 2개로 와일드카드 인증서가 2개가 생깁니다. ㅎㅎ 신세계죠.

4. .cf, .ga, .gq, .ml .tk 무료 인증서에서 ECDSA SSL 인증서 발급 받고 자동 갱신하기

위와 같은 도메인을 사용한다면 와일드카드 SSL 인증서 받기는 어렵습니다.

무료 도메인을 사용하지만 와일드카드 인증서가 꼭 필요하다면

클라우드플레어 말고 다른 DNS 서비스 [https://asia.cloudns.net/](https://asia.cloudns.net/)  같은 곳을 이용하는 것이 낫습니다.

그래도 클라우드플레어의 장점이 많으니 이용하는 것이 낫겠죠? ^^;;

현재 사용하거나, 사용하고 싶은 도메인을 모두 등록하면 됩니다.

우선 위와 같이 SSL 인증서가 저장될 폴더를 지정합니다.

위와 같이 webroot 방식으로 발급받으면 멀티도메인 거의 무제한으로 발급 받을 수 있습니다.  

와일드카드 도메인이 아니라도 아쉬움없이 사용할 수 있을 것입니다.

대신에 /var/www/wordpress 와 같은 현재 웹서버의 root 폴더를 지정해줘야 합니다. 

그러면 현재 제 구글 클라우드 무료 플랜의 서버에서 직접 실행한 결과를 보여드리겠습니다.

> acme.sh --issue -w /var/www/gnuboard -d aced.ga -d [www.aced.ga](http://www.aced.ga/) -d blog.aced.ga -d home.aced.ga -d nas.aced.ga --keylength ec-384 \\
> 
> \> --key-file /etc/nginx/ssl/privkey.pem  \\
> 
> \> --fullchain-file /etc/nginx/ssl/fullchain.pem \\
> 
> \> --cert-file /etc/nginx/ssl/chain.pem \\
> 
> \> --reloadcmd "systemctl reload nginx.service"
> 
> \[Tue 02 Jun 2020 10:35:31 PM KST\] Multi domain='DNS:aced.ga,DNS:www.aced.ga,DNS:blog.aced.ga,DNS:home.aced.ga,DNS:nas.aced.ga'
> 
> \[Tue 02 Jun 2020 10:35:31 PM KST\] Getting domain auth token for each domain
> 
> \[Tue 02 Jun 2020 10:35:35 PM KST\] Getting webroot for domain='aced.ga'
> 
> \[Tue 02 Jun 2020 10:35:35 PM KST\] Getting webroot for domain='[www.aced.ga](http://www.aced.ga/)'
> 
> \[Tue 02 Jun 2020 10:35:35 PM KST\] Getting webroot for domain='blog.aced.ga'
> 
> \[Tue 02 Jun 2020 10:35:35 PM KST\] Getting webroot for domain='home.aced.ga'
> 
> \[Tue 02 Jun 2020 10:35:35 PM KST\] Getting webroot for domain='nas.aced.ga'
> 
> \[Tue 02 Jun 2020 10:35:36 PM KST\] aced.ga is already verified, skip http-01.
> 
> \[Tue 02 Jun 2020 10:35:36 PM KST\] Verifying: [www.aced.ga](http://www.aced.ga/)
> 
> \[Tue 02 Jun 2020 10:35:39 PM KST\] Success
> 
> \[Tue 02 Jun 2020 10:35:39 PM KST\] Verifying: blog.aced.ga
> 
> \[Tue 02 Jun 2020 10:35:42 PM KST\] Success
> 
> \[Tue 02 Jun 2020 10:35:42 PM KST\] Verifying: home.aced.ga
> 
> \[Tue 02 Jun 2020 10:35:44 PM KST\] Success
> 
> \[Tue 02 Jun 2020 10:35:44 PM KST\] Verifying: nas.aced.ga
> 
> \[Tue 02 Jun 2020 10:35:47 PM KST\] Success
> 
> \[Tue 02 Jun 2020 10:35:47 PM KST\] Verify finished, start to sign.
> 
> \[Tue 02 Jun 2020 10:35:47 PM KST\] Lets finalize the order, Le\_OrderFinalize: [https://acme-v02.api.letsencrypt.org/acme/finalize/87746931/3604088807](https://acme-v02.api.letsencrypt.org/acme/finalize/87746931/3604088807)
> 
> \[Tue 02 Jun 2020 10:35:48 PM KST\] Download cert, Le\_LinkCert: [https://acme-v02.api.letsencrypt.org/acme/cert/89876](https://acme-v02.api.letsencrypt.org/acme/cert/89876)
> 
> \[Tue 02 Jun 2020 10:35:49 PM KST\] Cert success.
> 
> \-----BEGIN CERTIFICATE-----
> 
> xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
> 
> \-----END CERTIFICATE-----
> 
> \[Tue 02 Jun 2020 10:35:49 PM KST\] Your cert is in  /root/.acme.sh/aced.ga\_ecc/aced.ga.cer
> 
> \[Tue 02 Jun 2020 10:35:49 PM KST\] Your cert key is in  /root/.acme.sh/aced.ga\_ecc/aced.ga.key
> 
> \[Tue 02 Jun 2020 10:35:49 PM KST\] The intermediate CA cert is in  /root/.acme.sh/aced.ga\_ecc/ca.cer
> 
> \[Tue 02 Jun 2020 10:35:49 PM KST\] And the full chain certs is there:  /root/.acme.sh/aced.ga\_ecc/fullchain.cer
> 
> \[Tue 02 Jun 2020 10:35:49 PM KST\] Installing cert to:/etc/nginx/ssl/chain.pem
> 
> \[Tue 02 Jun 2020 10:35:49 PM KST\] Installing key to:/etc/nginx/ssl/privkey.pem
> 
> \[Tue 02 Jun 2020 10:35:49 PM KST\] Installing full chain to:/etc/nginx/ssl/fullchain.pem
> 
> \[Tue 02 Jun 2020 10:35:49 PM KST\] Run reload cmd: systemctl reload nginx.service
> 
> \[Tue 02 Jun 2020 10:35:49 PM KST\] Reload success

위와 같이 잘 발급되고, 원하는 위치에 인증서가 이동된 것을 확인할 수 있습니다.

5\. 발급 리스트 확인하기

위 명령어를 넣으면

> Main\_Domain  KeyLength  SAN\_Domains                             Created                          Renew  
> 
> wsgvet.com   "ec-384"   \*.wsgvet.com,pogovet.com,\*.pogovet.com  Tue 02 Jun 2020 10:34:07 AM UTC  Sat 01 Aug 2020 10:34:06 AM UTC

위와 같이 발급 정보가 나옵니다.  

무료 도메인 멀티도메인의 경우

> acme.sh list
> 
> Main\_Domain  KeyLength  SAN\_Domains                                        Created                          Renew
> 
> aced.ga      "ec-384"   www.aced.ga,blog.aced.ga,home.aced.ga,nas.aced.ga  Tue 02 Jun 2020 01:35:49 PM UTC  Sat 01 Aug 2020 01:35:49 PM UTC

위와 같이 도메인이 모두 들어있고, 자동갱신도 되는 것을 확인할 수 있습니다.  

6\. 자동갱신 삭제하기

잘못 발급받았거나, 필요없을땐 삭제해야겠죠.

위 명령으로 자동갱신이 삭제됩니다. 아까 위에 있던 Main\_Domain에 있는 것 1개만 넣으면 됩니다.

> \[Tue 02 Jun 2020 07:29:05 PM KST\] wsgvet.com is removed, the key and cert files are in /etc/letsencrypt/wsgvet.com\_ecc  
> 
> \[Tue 02 Jun 2020 07:29:05 PM KST\] You can remove them by yourself.

위와 같이 자동갱신이 삭제되었고, 해당 폴더는 삭제가 안되니, 스스로 삭제하라고 합니다. ㅎㅎ

7\. acme.sh 자동 업그레이드 하기

위 명령어를 넣으면 됩니다.

> \[Tue 02 Jun 2020 06:42:39 PM KST\] Already uptodate!
> 
> \[Tue 02 Jun 2020 06:42:39 PM KST\] Upgrade success!

위와 같이 나오면 성공입니다.

8\. 자동갱신

acme.sh로 인증서를 발급받았다면 자동으로 발급 후 60일 뒤에 갱신하게 됩니다.

별다른 작업이 필요없는 것이 큰 장점입니다.

위 명령어를 넣으면 

> 9 0 \* \* \* "/etc/letsencrypt"/acme.sh --cron --home "/etc/letsencrypt" > /dev/null

위와 같이 매일 한번씩 시도하는 것을 알 수 있습니다.

9\. Nginx에 적용하기

443포트를 받는 server{ } 에 넣어주시면 됩니다.

기존 인증서 경로 바로 밑에 넣어주셔도 되구요.

위와 같이 인증서키와 풀체인 인증서를 넣어주시면 됩니다.

OSCP 인증을 하려면 trusted가 필요한데, RSA인증서 발급시 지정했다면 추가로 지정할 필요가 없습니다. ^^