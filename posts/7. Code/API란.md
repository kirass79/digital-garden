# 1. 개념
- **API**(application programming interface 애플리케이션 프로그래밍 인터페이스\[\*\], 응용 프로그램 프로그래밍 인터페이스)는 
	- ==컴퓨터나 컴퓨터 프로그램 사이의 연결==이다. 
	- 컴퓨터와 인간을 연결시키는 사용자 인터페이스와 반대로, API는 컴퓨터나 소프트웨어를 서로 연결한다. 
	- 직접 사람(최종 사용자)에 의해 사용되도록 고안된 것이 아니며, 대신 소프트웨어에 이를 통합하고자 하는 컴퓨터 프로그래머가 사용하도록 고안되었다.
	- 일종의 소프트웨어 인터페이스 "인터페이스 (컴퓨팅)")이며 다른 종류의 소프트웨어에 서비스를 제공한다. 
	- ==이 연결이나 인터페이스를 빌드하거나 사용하는 방법의 표준==은 ==API 사양==으로 부른다. 
- API라는 용어는 ==사양이나 구현체를 의미할 수 있다.== 
	- 이 표준을 충족하는 컴퓨터 시스템은 ==API가 구현(implement)되었다거나 노출(expose)되었다==고 말한다. 
# 2. 용어정의
- API는 각기 다른 부분으로 구성되기도 하며 프로그래머가 사용할 수 있는 도구나 서비스의 역할을 한다. 
	- 이러한 부분들 중 하나를 사용하는 프로그램이나 프로그래머는 API의 해당 부분을 호출(call)한다고 말한다. 
	- API를 구성하는 호출들은 서브루틴, 메소드(method), 요청, 통신 엔드포인트")라고도 부른다. 
- API 사양은 이 호출들을 정의하며, 다시 말해 이들을 어떻게 사용하거나 구현하는지를 설명한다는 것을 의미한다. API의 한 가지 목적은 시스템이 동작하는 방식에 관한 내부의 세세한 부분을 숨기는") 것으로, 내부의 세세한 부분이 나중에 변경되더라도 프로그래머가 유용하게 사용할 수 있고 일정하게 관리할 수 있는 부분들만 노출시킨다. API는 특정 시스템용으로 커스텀하게 빌드될 수도 있고, 아니면 수많은 시스템 간 상호운용성을 허용하는, 공유가 되는 표준일 수도 있다. API라는 용어는 웹 API")를 의미하기도 하며,\[2\ 이는 인터넷에 의해 병합된 컴퓨터들 간 통신을 허용한다. 프로그래밍 언어, 소프트웨어 라이브러리 "라이브러리 (컴퓨팅)"), 컴퓨터 운영 체제, 컴퓨터 하드웨어를 위한 API도 존재한다. API는 1940년대에 기원하였으나 이 용어는 1960년대, 70년대 들어서야 모습을 드러냈다. ## 이용\[편집\] API는 응용 프로그램 이진 인터페이스(ABI)와는 구별한다. API는 소스 코드 기반인 반면 ABI는 이진 인터페이스이다. 이를테면 POSIX는 API인 반면, 리눅스 기본 규격은 ABI를 제공한다.\[3\ 
- ### 절차적 언어에서의 API
- 대부분의 절차적 언어에서 API는 특정한 작업을 수행할 함수들의 집합을 규정하며, 특정 소프트웨어 구성 요소와 상호 작용할 수 있게 한다. 유닉스 명령어 `man 3 sqrt`는 `sqrt` 함수의 시그너처")를 대표한다. SYNOPSIS #include <math.h> double sqrt(double X); float sqrtf(float X); DESCRIPTION sqrt computes the positive square root of the argument. ... RETURNS On success, the square root is returned. If X is real and positive... 이와 비슷하게, 다른 언어들은 절차적 라이브러리를 갖고 있다. 이를테면 펄에는 내부 문서화 기능을 이용할 수 있는 동일한 수식 작업을 위한 전용 API들이 있으며, perldoc 유틸리티를 이용하여 접근할 수 있다. $ perldoc \-f sqrt sqrt EXPR sqrt #Return the square root of EXPR. If EXPR is omitted, returns #square root of $\_. Only works on non-negative operands, unless #you've loaded the standard Math::Complex module. 
# 3. API의 예
- 윈도우 API - 마이크로소프트 윈도우의 다이렉트엑스 - 단일 유닉스 규격 - 자바 API - 스칼라 API "스칼라 (프로그래밍 언어)") - OpenGL - OpenAL - OpenCL ## 웹 API\[편집\] 웹 API는 웹 애플리케이션 개발에서 다른 서비스에 요청을 보내고 응답을 받기 위해 정의된 명세를 일컫는다. 예를 들어 블로그 API를 이용하면 블로그에 접속하지 않고도 다른 방법으로 글을 올릴 수 있다. 그 외에 우체국의 우편번호 API, 구글과 네이버의 지도 API등 유용한 API들이 많으므로, 요즘은 홈페이지 구축이나 추가개편 시 따로 추가로 개발하지 않고 이런 오픈 API를 가져와 사용하는 추세다. ## 같이 보기\[편집\] - 플러그인 - 소프트웨어 개발 키트 - 웹 서비스 - 매시업 ## 각주\[편집\] 1. ↑ Reddy, Martin (2011). 《API Design for C++》. Elsevier Science. 1쪽. ISBN (https://ko.wikipedia.org/wiki/%ED%8A%B9%EC%88%98:%EC%B1%85%EC%B0%BE%EA%B8%B0/9780123850041 "특수:책찾기/9780123850041"). 2. ↑ Lane, Kin (2019년 10월 10일). “Intro to APIs: History of APIs”. 《Postman》. 2020년 9월 18일에 확인함. When you hear the acronym “API” or its expanded version “Application Programming Interface,” it is almost always in reference to our modern approach, in that we use HTTP to provide access to machine readable data in a JSON or XML format, often simply referred to as “web APIs.” APIs have been around almost as long as computing, but modern web APIs began taking shape in the early 2000s. 3. ↑ “LSB Introduction”. Linux Foundation. 2012년 6월 21일. 2015년 4월 2일에 원본 문서에서 보존된 문서. 2015년 3월 27일에 확인함. 4. ↑ Stoughton, Nick (April 2005). “Update on Standards” (PDF). USENIX. 2009년 6월 4일에 확인함.
#코딩 