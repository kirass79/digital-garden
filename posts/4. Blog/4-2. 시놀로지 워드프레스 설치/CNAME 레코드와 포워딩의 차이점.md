One simple difference between domain forwarding and adding a CNAME record is that domain forwarding can redirect a domain to a directory and CNAMEs cannot. For example, let's say you had a blog website, and on that website there was a page just for recipes. Let's say the domain for that was myblog.com and you have a domain myrecipeblog.com and you want everyone who types myrecipeblog.com to be redirected to the recipe page at myblog.com/recipes, you could accomplish this with domain forwarding but not with a CNAME.

- 특정 홈페이지의 일부 페이지만을 도메인에 연결하고 싶을 경우에는 오로지 포워딩 기능만으로 구현이 가능
	- CNAME은 일부페이지만을 도메인에 연결하는 것이 안됨
- 단점은 포워딩은 서버를 거쳐 가는 것이므로 딜레이 발생함
#네트웍 

