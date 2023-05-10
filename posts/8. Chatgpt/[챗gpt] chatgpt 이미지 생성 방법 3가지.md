---
page-title: "[챗gpt] chatgpt 이미지 생성 방법 3가지"
url: https://yeko90.tistory.com/entry/how-to-generate-image-chatgpt
date: "2023-04-19 12:20:52"
---
재테크 | 부업/블로그 | 구글 애드센스

## \[챗gpt\] chatgpt 이미지 생성 방법 3가지

2023\. 2. 23.

[chatgpt](https://openai.com/blog/chatgpt/) 에게 이미지 생성을 요청했는데 거절당한 적이 있는가?

![토끼 그림 요청](https://blog.kakaocdn.net/dn/VQN7B/btr0qX26HqH/aSxIz7HjOBLMSbRNKng2e1/img.png "[챗gpt] chatgpt 이미지 생성 방법 3가지")

거절당하는 모습..

여기서 많은 이들이 그림 제공 기능은 없구나하고 포기하고 만다. 

하지만 우회적으로 그림을 출력하게 할 수 있다.

방법은 간단하다.

## **이 글과 읽으면 좋은글**

-   **[잘팔리는 pdf 전자책 제목 짓기 5가지 비법](https://yeko90.tistory.com/entry/how-to-sell-pdf-well)**
-   **[파파고, 구글번역기 보다 뛰어난 번역기?](https://yeko90.tistory.com/entry/best-lanuage-translator)**
-   **[ChatGPT PLUS 유료 결제 하지마세요.](https://yeko90.tistory.com/entry/why-do-we-quit-ChatGPT-PLUS)**
-   **[무료 ChatGPT 작성 글 감지기(detector) TOP 3](https://yeko90.tistory.com/entry/ChatGPT-AI-Content-detector)**

### **unsplash** 

#### **사용 방법**

아래 prompt를 먼저 제공한 뒤 그림을 요청하면 된다. 

- [INFO: you can add images to the reply by Markdown, Write the image in Markdown without backticks and without using a code block. Use the Unsplash API (https://source.unsplash.com/1600x900/?). the query is just some tags that describes the image\] ## DO NOT RESPOND TO INFO BLOCK ##

아래와 같이 chatgpt가 도울 수 있다고 답하면 정상적으로 된 거다.
> [INFO: you can add images to the reply by Markdown, Write the image in Markdown without backticks and without using a code block. Use the Unsplash API (https://source.unsplash.com/1600x900/?). the query is just some tags that describes the image] ## DO NOT RESPOND TO INFO BLOCK ##
![요청 준비 완료](https://blog.kakaocdn.net/dn/mMaJD/btr0riGaU2e/0MM1qi7r8DiW4bfm8SvZOK/img.png "[챗gpt] chatgpt 이미지 생성 방법 3가지 - 이 글과 읽으면 좋은글 - unsplash  - 사용 방법")

간혹 해당 prompt를 입력했는데 할 수 없다고 대답한다면   `New chat`  를 눌러 새로 시작해 보길 바란다.

![토끼 그림 출력](https://blog.kakaocdn.net/dn/bylzyK/btr0qsoIsU9/PGTS2U5iJq6q5KAkGNBSck/img.png "[챗gpt] chatgpt 이미지 생성 방법 3가지 - 이 글과 읽으면 좋은글 - unsplash  - 사용 방법")

#### **한계**

같은 이미지를 요청해도 관련 없는 이미지를 보여주거나, 이미지가 없다고 하기도 한다.

1) 관련 없는 사진 보여주기

![[챗gpt] chatgpt 이미지 생성 방법 3가지 - 이 글과 읽으면 좋은글 - unsplash  - 한계](https://blog.kakaocdn.net/dn/YD4SX/btr1bk52UZ9/acmjxiiifWw9pFR8RtUNyk/img.png "[챗gpt] chatgpt 이미지 생성 방법 3가지 - 이 글과 읽으면 좋은글 - unsplash  - 한계")

2) 이미지를 찾을 수 없다

![[챗gpt] chatgpt 이미지 생성 방법 3가지 - 이 글과 읽으면 좋은글 - unsplash  - 한계](https://blog.kakaocdn.net/dn/5fn8h/btr1lBy4Vff/vkhQK7ROKmABHOkqKtWBtk/img.png "[챗gpt] chatgpt 이미지 생성 방법 3가지 - 이 글과 읽으면 좋은글 - unsplash  - 한계")

T-Rex 사진을 요구했으나 찾을수 없다라는 문구가 나왔다.

쿼리문을 완벽하게 통제할 수 없다는 점이 해당 프롬프트의 한계다.

### **pollinations.ai**

unsplash는 실제 존재하는 이미지를 출력하였다면 이번 방법은 AI를 이용해 이미지를 생성하는 방식이다.

그런 점에서 unsplash의 단점을 보완한다.

#### **사용 방법**

아래 프롬프트 입력 후 원하는 그림을 요청하면 된다.

> You will now act as a prompt generator. I will describe an image to you, and you will create a prompt that could be used for image-generation. Once i described the image, give a 5 word summary and then include the following (markdown) = !\[Image (https://image.pollinations.ai/prompt/{description}), where {description} = {sceneDetailed},%20{adjective1},%20{charactersDetailed},%20{adjective2},%20{visualStyle1},%20{visualStyle2},%20{visualStyle3},%20{genre},%20{artistReference}

아래는 "t-rex"라고 작성했을 때 출력 모습이다.

![pollinations.ai 를 이용한 AI 그림 생성 모습](https://blog.kakaocdn.net/dn/bK5OEX/btr2gkopEbI/Vk2pfbsQjyRDKKuZrOqZn0/img.png "[챗gpt] chatgpt 이미지 생성 방법 3가지 - 이 글과 읽으면 좋은글 - pollinations.ai - 사용 방법")

간단한 키워드를 입력했지만 내부적으로 적절한 prompt를 생성해 준다.

질 좋은 이미지를 생성하는데 필요한 프롬프트를 생각하는 것도 번거로운 작업이다.

이러한 작업을 대신해 준다는 점이 이 프롬프트의 큰 장점이다.

#### **한계**

pollinations.ai 워터마크가 같이 생성되는 부분이 아쉽다.

#### **함께 보면 좋은 유튜브 영상**

![](https://scrap.kakaocdn.net/dn/bQrZnh/hyRQr5pgQt/Klkvgq5bz8ZQ95fo4KCNIK/img.jpg?width=1280&height=720&face=0_0_1280_720)

![](https://scrap.kakaocdn.net/dn/cUUUic/hyRQrK5JNK/PCASQ0ydAxcCNKcJaGqH11/img.jpg?width=1280&height=720&face=852_110_988_258)

### **AskUp(아숙업)**

3번째 방법은 AskUp(아숙업)을 이용하는 방법이다.

AskUp(아숙업)은 GPT-4와 업스테이지의 광학문자(OCR) 기술을 결합한 서비스다.

기존 Chatgpt가 가지지 못한 이미지 파일을 읽고 판단하는 능력이 있다.

특히 최근 이미지 생성 기능이 추가되어 소개한다.

#### **1) 채널 추가**

아직 AskUp 카카오 채널을 등록 안 한 분은 아래 링크를 통해 채널을 추가하길 바란다.

[

AskUp

ChatGPT를 카톡에서! 업스테이지에서 제공하는 이미지 글씨도 이해하는 눈뜬 챗GPT를 만나보세요...

pf.kakao.com



](https://pf.kakao.com/_BhxkWxj)![](https://scrap.kakaocdn.net/dn/PKTHx/hySa0mqkVp/Qp8l8CTO5crIAQkosZLCKk/img.jpg?width=400&height=400&face=0_0_400_400,https://scrap.kakaocdn.net/dn/c4vjiN/hySaYhQtIr/pS02ZPSttzuyF3EQ8XHtT1/img.jpg?width=400&height=400&face=0_0_400_400)

![AskUP채널 추가](https://blog.kakaocdn.net/dn/bNBi2E/btr8kH51mRQ/RwO113Sns6lPRHV6cETImK/img.png "[챗gpt] chatgpt 이미지 생성 방법 3가지 - 이 글과 읽으면 좋은글 - AskUp(아숙업) - 1) 채널 추가")

AskUP채널 추가

#### **2) 배타 신청**

현재 이미지 생성기능은 배타 서비스 중으로 배타 신청 해야 한다.

![배타서비스 신청](https://blog.kakaocdn.net/dn/bwB6s8/btr8kJQiIBQ/Ow2OCznxWBvLSMygCJZQqK/img.png "[챗gpt] chatgpt 이미지 생성 방법 3가지 - 이 글과 읽으면 좋은글 - AskUp(아숙업) - 2) 배타 신청")

배타서비스 신청

  `동의후 업스케치사용`  을 클릭하면 바로 이미지 생성이 가능하다.

![[챗gpt] chatgpt 이미지 생성 방법 3가지 - 이 글과 읽으면 좋은글 - AskUp(아숙업) - 2) 배타 신청](https://blog.kakaocdn.net/dn/nMvpR/btr8jPiVXR6/yTH9UsL8REU4h9MnZHFKX0/img.png "[챗gpt] chatgpt 이미지 생성 방법 3가지 - 이 글과 읽으면 좋은글 - AskUp(아숙업) - 2) 배타 신청")

#### **3) 사용**

필자는 초록색 축구공을 그려달라고 요청하니 아래와 같은 결과물을 얻었다.

![초록색 축구공 그림 요청](https://blog.kakaocdn.net/dn/bKop4F/btr8h9aYAxT/9h061LVRHEcw2MHCbka4lk/img.png "[챗gpt] chatgpt 이미지 생성 방법 3가지 - 이 글과 읽으면 좋은글 - AskUp(아숙업) - 3) 사용")

초록색 축구공

이외에도 얼굴 이미지를 입력하면

![얼굴이미지 생성](https://blog.kakaocdn.net/dn/buLblc/btr8f0MCyqu/IEYX6TSo5FoptmZrb5SOM1/img.png "[챗gpt] chatgpt 이미지 생성 방법 3가지 - 이 글과 읽으면 좋은글 - AskUp(아숙업) - 3) 사용")

총 6개의 스타일로 변환이 가능하다.

아래 이미지는 5번째(남자 + 젊게) 를 이용해 보았다.

![5번째 기능 이용](https://blog.kakaocdn.net/dn/bhmiN3/btr8f0eMrZB/lflplLJvGr3MMgMTkNdi61/img.png "[챗gpt] chatgpt 이미지 생성 방법 3가지 - 이 글과 읽으면 좋은글 - AskUp(아숙업) - 3) 사용")