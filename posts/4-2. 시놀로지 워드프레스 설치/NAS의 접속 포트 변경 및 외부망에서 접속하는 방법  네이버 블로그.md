---
page-title: "NAS의 접속 포트 변경 및 외부망에서 접속하는 방법 : 네이버 블로그"
url: https://m.blog.naver.com/kangyh5/222560719374
date: "2023-04-12 22:57:45"
---
NAS의 접속 포트를 변경하는 방법과 외부망에서 접속하는 방법에 대해 알아 본다.
NAS(Network Attached Storyage)를 사용하는 목적은 네트워크를 통해 별도의 저장 장치에 접근하기 위함이다. 사용자가 외부망에 있던지, 내부망에 있던지 네트워크에 연결되어 있다면, 언제 어디서든지 나스에 접근할 수 있어야 한다.
​
유저가 나스를 구축했다면, 집이나 사무실에 있든 여행을 가서든 출장을 가서든, 내부는 물론 외부에서도 나스에 접근할 수 있어야 그 효용 가치를 극대화할 수 있다.
![](https://mblogthumb-phinf.pstatic.net/MjAyMTExMDdfMjI0/MDAxNjM2MjUyNDIxNDgz.I4aeckQwNsfdEimIKwxvGiH7r3hIIxjHeffBJXqmjTgg.M5ypVwxWU2H-ptiDyLa8eDHgXnuOz6d3rYHUwBB1Kjwg.PNG.kangyh5/nas_1-0-1.PNG?type=w800)
그럼 시놀로지 나스나 헤놀로지 나스를 외부망에서 접속하는 방법에 대해 알아 보자.
​
먼저 NAS의 보안을 강화하기 위해 나스의 DSM http 포트(5000)를 변경하는 방법에 대해 알아 본다.
​
Synology 나스나 XPEnology 나스의 DSM http 포트는 5000번이다. 이것은 누구나 알고 있는 사실이다.
​
모두에게 알려진 사실은 보안에 취약하므로, 나스의 DSM http 포트를 변경하여 취약한 보안을 강화해 보자.
​
1) 나스에 접속하기
​
• 나스가 있는 내부망에서 내 PC의 웹 브라우저를 통해 나스에 접근을 시도한다. ( 나스의 내부 IP = 172.30.1.58일 때 )
​
• 내 PC에서 웹 브라우저의 주소창에 나스의 접속 주소( 나스의 내부 IP : DSM http 포트 )를 입력한다. DSM에서 기본적으로 설정되어 있는 HTTP 포트는 5000번이다.
![](https://mblogthumb-phinf.pstatic.net/MjAyMTExMDdfNTUg/MDAxNjM2MjM5NjA4NTE1.Yvy6suT6iMjXtKgAl7Ja8NrVVgdkWUmUBi4osDWV-m4g.KvI3b9BmDl9w9J45dyou1oGSWlHrg72vIkPqBOHjfUsg.PNG.kangyh5/nas_1-1-1.png?type=w800)
( 내 PC의 엣지 브라우저 주소창 = 172.30.1.58:5000 )
​
• 나스의 로그인 화면이 나타나면, 사용자 ID와 비밀번호를 입력하고, DSM 화면으로 진입한다.
![](https://mblogthumb-phinf.pstatic.net/MjAyMTExMDdfMTU2/MDAxNjM2MjM5Nzk5NDM1.FVxx5wpjNuCnPfyPM9YzaU3dD9U0hn8xkJimcYX2AK8g.HB_ILnMxeP7hTPL0WgAo4oxVhhcjEF2e53AUITTsj8Ag.PNG.kangyh5/nas_1-2.PNG?type=w800)
​
2) 나스의 포트 번호 변경하기
​
• 내 PC의 DSM 바탕화면에서 \[제어판\]을 선택하여 클릭한다.
![](https://mblogthumb-phinf.pstatic.net/MjAyMTExMDdfMTY2/MDAxNjM2MjM5OTgwMDYy.Us78J-O4omyXv7kB_Z1SOE8eVup4OcNQRBaFZidZlyIg.Gds13QYPfU6MRRKdPbdDTLBiym30DLeI1_FNKainjskg.PNG.kangyh5/nas_1-3-1.PNG?type=w800)
( 내 PC의 엣지 브라우저 화면 )
​
• '연결성' 항목에서 \[네트워크\]를 선택하여 클릭한다.
![](https://mblogthumb-phinf.pstatic.net/MjAyMTExMDdfMTE5/MDAxNjM2MjQwMjEwMzI3.PTxSRNdf5IRfe1BY4s9jD4dJSfrvpJZHXEVmtYFYe5cg.idfZGPmAgvnkAdII16cy8TmX7lzYelF_Y3JMWGhvih8g.PNG.kangyh5/nas_1-4-1.PNG?type=w800)
​
• '네트워크'에서 \[DSM 설정\] 항목을 선택하면, 기본 포트 번호가 HTTP는 5000번, HTTPS는 5001번으로 설정되어 있다.
![](https://mblogthumb-phinf.pstatic.net/MjAyMTExMDdfMTUy/MDAxNjM2MjQwNDk0NjQ5.pV8NBdlBMndRJ_9IJPUSboLdlKTIOBlcYWuCLuN2qYIg.w3yDMReZbteRssgRjPR5EgCKXiYMDoXFnOzQQzmP0R8g.PNG.kangyh5/nas_1-5-1.PNG?type=w800)
​
• HTTP를 3000번으로 변경하고, HTTPS는 3001번으로 변경한다. HTTPS는 'HTTPS 연결 활성화'가 체크되어야 변경할 수 있다.
![](https://mblogthumb-phinf.pstatic.net/MjAyMTExMDdfMTg2/MDAxNjM2MjQwNzQwODUx.1BqTudEMeVEoQ90j3PfVcL-fHayHxTxnh8vnm_m63KAg.j8ocN0Qo7cbvsxJlgf7x3SvGdQzetwWwIMe1Qpr3g6Yg.PNG.kangyh5/nas_1-7-1.PNG?type=w800)
하단에 \[적용\]을 클릭하면,
​
• 내 PC의 웹 브라우저에 아래와 같은 화면이 나타나고,
​
'작업 실패' 메세지 창에서 \[확인\]을 클릭한다.
![](https://mblogthumb-phinf.pstatic.net/MjAyMTExMDdfMjUw/MDAxNjM2MjQwODY4Mzc2.W0MrlAYuR0njq2Uzu0qEw_92BtYRiMUuFnO70qyspO8g.D9srHVtGwrdnqsXPg8EnVx7nud_OdQZfICzkiUWnKOAg.PNG.kangyh5/nas_1-9.PNG?type=w800)
​
• 잠시 기다리면, 아래와 같이 내 PC에 나스의 로그인 화면이 다시 나타난다. 웹 브라우저의 주소창을 보면, 나스 접속 IP 주소의 포트 번호가 5000번에서 3000번으로 변경된 것을 확인할 수 있다.
![](https://mblogthumb-phinf.pstatic.net/MjAyMTExMDdfMjQw/MDAxNjM2MjQxMTgwNzMx.sftDDWStDk6j-PcBklrwCh5GkM6yCRjipMFv6vIQi8sg._Lmvvw2ULBro9Y3P8zU0m_kcgUS4c0BRugTTm2uog_Mg.PNG.kangyh5/nas_1-10-1.PNG?type=w800)
다시 사용자 ID과 패스워드를 입력하고 로그인하면, 변경된 DSM http 포트(3000번)를 통해 나스에 접속하게 된다.
​
​
보통은 나스가 유무선 공유기에 연결되어 있을 것이며, 나스가 없는 외부망에서 나스를 접속하려면 포트포워딩 작업이 필요하다. 여기서는 나스가 KT의 유무선 공유기에 연결되어 있는 경우를 예로 진행한다.
​
1) KT 유무선 공유기에 접속하기
​
• 나스가 있는 내부망에서 내 PC를 KT 유무선 공유기의 관리자 페이지에 접속을 시도한다.
​
[http://172.30.1.254](http://172.30.1.254/) (바로가기)
또는
[http://homehub.kt.com](http://homehub.kt.com/) (바로가기)
​
• 내 PC의 웹 브라우저 주소창에 KT 유무선 공유기의 관리자 페이지 접속 주소를 직접 입력한다.
![](https://mblogthumb-phinf.pstatic.net/MjAyMTExMDdfNDQg/MDAxNjM2MjQzNDY0NDU1.9jxh-D3BXvLEJa3gXD8jLZFDPotWxy45al5X2jsApKog.MTETQZRTu2ZC7kVY-nJATnyt3qKK9fvFSL-0zpUpVNgg.PNG.kangyh5/nas_2-1-1.PNG?type=w800)
( 내부망에 있는 내 PC의 엣지 브라우저 화면 = DSM 진입 화면 )
​
​
• KT 유무선 공유기의 관리자 로그인 화면이 나타나면, 사용자 아이디와 비밀번호를 입력하고, 보안 문자까지 입력하여 로그인을 시도한다.
![](https://mblogthumb-phinf.pstatic.net/MjAyMTExMDdfMjU4/MDAxNjM2MjQzNTgwNDgz.IKHoNPR_xfiybzPCVOJwyTzpA29hUraYw06bV12-SqEg.gErwNQUq0k4gMxmfzP7Lx5g8fY5UMXZGsXXBExT7hQ0g.PNG.kangyh5/nas_2-2.PNG?type=w800)
​
• 관리자 설정 화면에 진입하면, 아래와 같은 화면이 나타난다.
![](https://mblogthumb-phinf.pstatic.net/MjAyMTExMDdfMTA4/MDAxNjM2MjQ0ODk5NTU0.SrHfchlHZFlyq4n0VecNtRY_3v6qT9zGYzfxjBWwIhYg.WP3uNcRwDiqUjKUWYy34dEfkm219HYv8wTeugU9Dgmcg.PNG.kangyh5/nas_2-3-1.PNG?type=w800)
여기의 \[인터넷 연결정보\]에서 IP 주소(123.123.45.45)를 잘 외워 두어야 한다. 이것은 KT 유무선 공유기의 외부 IP 주소이며, 나중에 나스의 외부망 접속 주소의 일부가 된다.
​
> 내부망에서 나스의 접속 주소와 외부망에서 나스의 접속 주소는 다르다.
2) 포트포워딩 설정하기
​
• 이제 포트 포워딩 설정 화면으로 이동한다.
​
• 장치설정 -> 트래릭 관리 -> 포트 포워딩 설정
![](https://mblogthumb-phinf.pstatic.net/MjAyMTExMDdfMTYx/MDAxNjM2MjQ1MTcyNjkz.NiTxDab8IGc2H0Gni7f_FrPv07hcvNhj8bJTrgB2es0g.GEox7Wx5n4bO7f4wQ1x2-e8eQnlsFS-t8EMWU35WBJkg.PNG.kangyh5/nas_2-4.PNG?type=w800)
​
• 포트 포워딩 설정 항목에서 아래와 같이 데이터를 입력한다.
​
\-. 외부 포트 : KT 유무선 공유기의 임의의 포트.
ex) 3000~3001 (내부 포트와 동일한 포트 번호 입력)
\-. 내부IP 주소 : 172.30.1.58 (NAS의 내부 IP 입력)
\-. 내부 포트 : 나스 DSM의 http 포트.
ex) 3000~3001 ( 변경한 DSM의 HTTP 포트 번호)
\-. 프로토콜 : ALL
\-. 설명 : nas
![](https://mblogthumb-phinf.pstatic.net/MjAyMTExMDdfMjEz/MDAxNjM2MjQ1MjA4Mzcz.rlvCSwcqn_IM_PlmYk_YBfM-su4wTk-PjkHYGWcvHUQg.vGP3LUnyKzCvMmf71afO3D4St7bKmrP6KpW7BpFid_Ug.PNG.kangyh5/nas_2-5.PNG?type=w800)
​
\* 포트 번호는 어플리케이션이 지나다닐 수 있도록 할당된 논리적 통로의 번호이다.
​
• 여기서 \[추가\]를 클릭하면, 하단 리스트에 nas 포트포워딩 설정 데이터가 나타난다.
![](https://mblogthumb-phinf.pstatic.net/MjAyMTExMDdfMTU3/MDAxNjM2MjQ1MzM5OTIz.PLuyIOkyhfIaEegqjz5AdMcpnWL19agOAJOo5WUe5LMg.IbzqV7yQexZvTzv7qLXG_EBZcE_VCJVBtgQdc85NTXUg.PNG.kangyh5/nas_2-6.PNG?type=w800)
​
여기까지 진행하면, 나스가 있는 KT 유무선 공유기의 포트포워딩 작업이 완료된 것이다.
​
​
3) 외부망에서 나스 접속하기
​
• 유무선 공유기의 포트포워딩 작업까지 완료되었으니, 이제 나스가 없는 외부망에서 나스에 접속을 시도해 보자.
​
• 외부망에 있는 PC의 웹 브라우저 주소창에 나스의 외부망 접속 주소를 입력한다.
​
> \[ 나스 외부망 접속 주소 \]
> 
> ​
> 
> 유무선 공유기의 외부 IP 주소 : 공유기의 외부 포트 (123.123.45.45:3000)
> 
> ​
> 
> \* 유무선 공유기의 포트포워딩에서 외부 포트 번호(3000)와 내부 포트 번호(3000)를 동일한 값으로 설정한 경우이다.
![](https://mblogthumb-phinf.pstatic.net/MjAyMTExMDdfNzIg/MDAxNjM2MjQ2NTQ5Mjc4.4lqk958eXYCN6FTthemcFaphzcTSDtXIg8S_FGzSt_Ug.dncijM4IiN2rNpIN1BvAvLD2HmSy2_MbgvAUVPWe31wg.PNG.kangyh5/nas_3-1-1.PNG?type=w800)
( 외부망 PC의 엣지 주소창 = 123.123.45.45:3000 )
​
• 나스에 접속하게 되면, 외부망 PC에 나스의 로그인 화면이 나타난다.
![](https://mblogthumb-phinf.pstatic.net/MjAyMTExMDdfMTc2/MDAxNjM2MjQ2ODg4NTk3.FfsQZS0KkRuzK2cSw4pX6A8ZLlEE9-9HueeggvdGvXsg.LxpIiSDw6P178UIMMOie8Ala0xkNo6Ef_yOKLtCQv_og.PNG.kangyh5/nas_3-2-1.PNG?type=w800)
​
• 사용자 ID와 패스워드를 입력하면, 아래와 같이 외부망에서 나스로 진입할 수 있게 된다.
![](https://mblogthumb-phinf.pstatic.net/MjAyMTExMDdfMTc1/MDAxNjM2MjQ3MjM0NjQ5.JjXXxAISF7FSF_kjHaCvgAbKEbcJ5pc2royTEGqOqYwg.N_4q9CI01J-ZPU-coaj4yct_saPfA6D9VNn-XzcXLJkg.PNG.kangyh5/nas_3-3-1.PNG?type=w800)
​
이제 인터넷에 접근할 수만 있다면, 언제 어디서든 내가 구축한 나스에 접속할 수 있다.
​
"이 포스팅은 쿠팡 파트너스 활동의 일환으로, 이에 따른 일정액의 수수료를 제공받습니다."
​
\[ 파일 탐색기에 NAS 연결하기 \]
#블로그 