---
page-title: "webui openpose로 원하는 자세로 이미지를 생성해보기 DesignerAllan"
url: https://ai-designer-allan.tistory.com/entry/webui-openpose%EB%A1%9C-%EC%9B%90%ED%95%98%EB%8A%94-%EC%9E%90%EC%84%B8%EB%A1%9C-%EC%9D%B4%EB%AF%B8%EC%A7%80%EB%A5%BC-%EC%83%9D%EC%84%B1%ED%95%B4%EB%B3%B4%EA%B8%B0
date: "2023-04-18 14:30:53"
---
**이미지를 생성할 때 자세를 고정시키고 싶다면 Controlnet의 openpose를 사용해 보세요**

안녕하세요 Allan입니다.

이번 포스팅에서는 Controlnet의 기능 중 하나인 openpose를 이용해서  
원하는 자세로 이미지를 생성하는 방법을 알아보겠습니다.

Controlnet에는 opnepose 말고도 유용한 기능도 많지만 추후에 포스팅해 보도록 하겠습니다.

## [Ⅰ. ControlNet 익스텐션 설치하기](https://ai-designer-allan.tistory.com/entry/webui-openpose%EB%A1%9C-%EC%9B%90%ED%95%98%EB%8A%94-%EC%9E%90%EC%84%B8%EB%A1%9C-%EC%9D%B4%EB%AF%B8%EC%A7%80%EB%A5%BC-%EC%83%9D%EC%84%B1%ED%95%B4%EB%B3%B4%EA%B8%B0#%E2%85%A0.%20ControlNet%20%EC%9D%B5%EC%8A%A4%ED%85%90%EC%85%98%20%EC%84%A4%EC%B9%98%ED%95%98%EA%B8%B0-1)

먼저 webui를 켜주도록 하겠습니다.

Extensions > install from URL로 들어가서 아래링크를 빨간 네모박스 안에 복붙 해주고 Install버튼을 눌러 줍니다.

- https://github.com/Mikubill/sd-webui-controlnet

![Extensions &gt; install from URL](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcpMGO8%2Fbtr4igYvi6a%2F4TtfIDjogwbqqVHYAMLVHk%2Fimg.png)

install버튼 아래에 설치가 완료되었다는 문구가 뜨면 성공입니다.

되셨으면 intall from URL 옆의 installed으로 들어가 Apply and restart UI 버튼을 눌러  
webui를 새로고침 해줍니다.

## [Ⅱ. openpose 다운로드하기](https://ai-designer-allan.tistory.com/entry/webui-openpose%EB%A1%9C-%EC%9B%90%ED%95%98%EB%8A%94-%EC%9E%90%EC%84%B8%EB%A1%9C-%EC%9D%B4%EB%AF%B8%EC%A7%80%EB%A5%BC-%EC%83%9D%EC%84%B1%ED%95%B4%EB%B3%B4%EA%B8%B0#%E2%85%A1.%20openpose%20%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%ED%95%98%EA%B8%B0-1)

먼저, 아래 사이트로 들어가 줍니다.

[https://civitai.com/models/9251/controlnet-pre-trained-models](https://civitai.com/models/9251/controlnet-pre-trained-models)

[

ControlNet Pre-Trained Models | Stable Diffusion Controlnet | Civitai

STOP! THESE MODELS ARE NOT FOR PROMPTING/IMAGE GENERATION These are the models required for the ControlNet extension , converted to Safetensor and ...

civitai.com



](https://civitai.com/models/9251/controlnet-pre-trained-models)![](https://scrap.kakaocdn.net/dn/AOeR1/hyRWBOjG1H/Ipnn1bCD1Kykop8AeKu33k/img.png?width=832&height=1280&face=0_0_832_1280,https://scrap.kakaocdn.net/dn/njMvF/hyRXxwIAGB/VqPibvlnrdMkqu8bXx5d50/img.png?width=832&height=1280&face=0_0_832_1280,https://scrap.kakaocdn.net/dn/bWDA3s/hyRXyvCY9K/1yUK1m6xhCrSTNOeaxutRk/img.jpg?width=400&height=615&face=0_0_400_615)

사이트에 들어가셔서 스크롤을 내려보면 다음과 같이 ControlNet모델을 선택할 수 있는 곳이 보입니다.

![오픈포즈 다운](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FCDjlG%2Fbtr37viY9J4%2Fkdf5TXKTZSgyBJjOuiw80K%2Fimg.png)

먼저 좌측에서 OpenPose V1.0을 선택해 주시고

우측의 다운로드 버튼을 눌러 다운 받아 주도록 하겠습니다.

다운 받은 파일은

구글 드라이브에서 SD/extensions/sd-webui-controlnet/models에 넣어 주시면 됩니다.

다운경로는 코랩 버전마다 다를 수도 있고 로컬도 다를 수도 있으니  
올바른 경로에 넣어 주시면 됩니다.

다른 모델을 사용하고 싶으신 분들은 원하시는 모델 다운 받은 후 같은 경로에 넣어주시면 됩니다.

## [Ⅲ. 레퍼런스 포즈 이미지 구하기](https://ai-designer-allan.tistory.com/entry/webui-openpose%EB%A1%9C-%EC%9B%90%ED%95%98%EB%8A%94-%EC%9E%90%EC%84%B8%EB%A1%9C-%EC%9D%B4%EB%AF%B8%EC%A7%80%EB%A5%BC-%EC%83%9D%EC%84%B1%ED%95%B4%EB%B3%B4%EA%B8%B0#%E2%85%A2.%20%EB%A0%88%ED%8D%BC%EB%9F%B0%EC%8A%A4%20%ED%8F%AC%EC%A6%88%20%EC%9D%B4%EB%AF%B8%EC%A7%80%20%EA%B5%AC%ED%95%98%EA%B8%B0-1)

먼저, 레퍼런스가 될 포즈 이미지를 구해야 합니다.

저는 다음 이미지를 레퍼런스로 잡도록 하겠습니다.

![레퍼런스 포즈](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FqprQl%2Fbtr37uEn9e3%2FRa7Y41qp3JNPkyghKB16y1%2Fimg.png)

## [Ⅳ. 포즈 추출하기](https://ai-designer-allan.tistory.com/entry/webui-openpose%EB%A1%9C-%EC%9B%90%ED%95%98%EB%8A%94-%EC%9E%90%EC%84%B8%EB%A1%9C-%EC%9D%B4%EB%AF%B8%EC%A7%80%EB%A5%BC-%EC%83%9D%EC%84%B1%ED%95%B4%EB%B3%B4%EA%B8%B0#%E2%85%A3.%20%ED%8F%AC%EC%A6%88%20%EC%B6%94%EC%B6%9C%ED%95%98%EA%B8%B0-1)

webui를 다시켜줍니다.

t2i의 가장 하단에 보면 ControlNet이 있는 것을 볼 수 있습니다.

이미지를 업로드하는 곳과 옵션 설정하는 곳이 있는데

먼저 레퍼런스 이미지를 업로드해 주시면 됩니다.

설정은 다음과 같이 해주시면 됩니다.

![ControlNet 옵션설정](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbRiwH1%2Fbtr38K09wi4%2Fk3Qd761Pgu7tMoyejB1eUk%2Fimg.png)

VRAM이 부족하다면 상단의 Low VRAM 체크해 주시면 됩니다.

preprocessor는 openpose를 선택해 주시고 Model은 다운 받은 모델을 선택해 주시면 됩니다.

나머지 값들은 그대로 두시고 하단의 네모박스 부분을 클릭해 주시면  
레퍼런스 이미지에서 모델의 포즈를 추출해 줍니다.
- 네모박스가 불꼿모양으로 바뀌었고, 위치는 프로세서와 모델 사이에 있음
	- Allow Preview를 체크해야 함

다음과 같이 업로드한 이미지 옆에 레퍼런스 이미지의 포즈가 추출된 것을 볼 수 있습니다.

![추출된 포즈 이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fchgzj4%2Fbtr4gv3iz82%2FLUvjgAoHK3rH6KU9w2ETlK%2Fimg.png)

## [Ⅴ. 이미지 생성하기](https://ai-designer-allan.tistory.com/entry/webui-openpose%EB%A1%9C-%EC%9B%90%ED%95%98%EB%8A%94-%EC%9E%90%EC%84%B8%EB%A1%9C-%EC%9D%B4%EB%AF%B8%EC%A7%80%EB%A5%BC-%EC%83%9D%EC%84%B1%ED%95%B4%EB%B3%B4%EA%B8%B0#%E2%85%A4.%20%EC%9D%B4%EB%AF%B8%EC%A7%80%20%EC%83%9D%EC%84%B1%ED%95%98%EA%B8%B0-1)

이제 정말 준비가 끝났습니다.

이 상태에서 평소와 똑같이 이미지를 생성하시면 됩니다.

다음과 같이 이미지를 생성해 보도록 하겠습니다.

> (masterpiece:1.2, best quality), (real picture, intricate details),1girl,cute  
> Negative prompt: (worst quality, low quality:1.4),easynegative,bad\_prompt\_version2,nsfw  
> Steps: 30, Sampler: DPM++ SDE Karras, CFG scale: 9, Seed: 3802968948, Size: 512x512,  
> Model: camelliamix25D\_v10, Clip skip: 2,

참고로 네거티브 프롬프트에 쓰여져 있는 easynegative,bad\_prompt\_version2는 임베딩을 적용한 것이니  
임베딩 없이 쓰시면 아무 효과 없습니다.

임베딩 적용하는 방법을 모르신다면 아래 포스팅을 참고해 주세요.

[스테이블 디퓨전 colab에서 lora와 embedding 적용하기](https://ai-designer-allan.tistory.com/entry/%EC%8A%A4%ED%85%8C%EC%9D%B4%EB%B8%94-%EB%94%94%ED%93%A8%EC%A0%84-colab%EC%97%90%EC%84%9C-lora%EC%99%80-embedding-%EC%A0%81%EC%9A%A9%ED%95%98%EA%B8%B0)

[

스테이블 디퓨전 colab에서 lora와 embedding 적용하기

안녕하세요 Allan 입니다. 이번 포스팅에서는 lora 와 embedding을 적용하는 방법에 대해서 알아보겠습니다. 로라를 적용할 때 입력해야 할 trigger words, 로라와 임베딩의 가중치 등등 처음시작하시는

ai-designer-allan.tistory.com



](https://ai-designer-allan.tistory.com/entry/%EC%8A%A4%ED%85%8C%EC%9D%B4%EB%B8%94-%EB%94%94%ED%93%A8%EC%A0%84-colab%EC%97%90%EC%84%9C-lora%EC%99%80-embedding-%EC%A0%81%EC%9A%A9%ED%95%98%EA%B8%B0)![](https://scrap.kakaocdn.net/dn/bs95oE/hyRXtVo6ss/1xG5eec4sxQw7FlsX24UGK/img.png?width=800&height=800&face=337_205_562_450,https://scrap.kakaocdn.net/dn/eI78P/hyRXrJ3hBL/pn3IU9XYp1MyxcVoNyHOT0/img.png?width=800&height=800&face=337_205_562_450,https://scrap.kakaocdn.net/dn/bwasbG/hyRWtCHlvw/V7fUM42Dmf6PcDPcDu7YQK/img.png?width=1491&height=831&face=265_246_474_474)

아무튼, 그림을 생성해 보았고  
레퍼런스 이미지와 생성한 이미지의 비교샷 보여드리도록 하겠습니다.

![생성된 이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FlaYPJ%2Fbtr4igKYgE5%2FtTBKzawVNK7HwdCnwbDJY1%2Fimg.png)![레퍼런스 이미지](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FqprQl%2Fbtr37uEn9e3%2FRa7Y41qp3JNPkyghKB16y1%2Fimg.png)

잘 보시면 몸의 각도, 얼굴 각도, 팔의 위치 모두 동일하게 이미지가 생성된 것을 볼 수 있습니다.

이런 방식으로 매우 유용하게 사용될 수 있는 기능이니 설치하는 게 조금 복잡하긴 해도  
별로 어렵지 않으니 꼭 시도해 보시는 것을 추천드립니다.

생성한 이미지를 고퀄리티의 이미지로 만들어 주고 싶다면 아래 포스팅을 참고해 주세요.

[webui Upscale : 나만 고화질 이미지 생성이 안된다면??](https://ai-designer-allan.tistory.com/entry/webui-Upscale-%EB%82%98%EB%A7%8C-%EA%B3%A0%ED%99%94%EC%A7%88-%EC%9D%B4%EB%AF%B8%EC%A7%80-%EC%83%9D%EC%84%B1%EC%9D%B4-%EC%95%88%EB%90%9C%EB%8B%A4%EB%A9%B4)

[

webui Upscale : 나만 고화질 이미지 생성이 안된다면??

안녕하세요 Allan입니다. 이번 포스팅에서는 webui에서 고화질 이미지를 생성하는 방법에 대해서 알아보겠습니다. 다른 사람들이 생성한 이미지를 보면 고화질에 엄청 디테일하지만 본인이 생성

ai-designer-allan.tistory.com



](https://ai-designer-allan.tistory.com/entry/webui-Upscale-%EB%82%98%EB%A7%8C-%EA%B3%A0%ED%99%94%EC%A7%88-%EC%9D%B4%EB%AF%B8%EC%A7%80-%EC%83%9D%EC%84%B1%EC%9D%B4-%EC%95%88%EB%90%9C%EB%8B%A4%EB%A9%B4)![](https://scrap.kakaocdn.net/dn/Gtd7B/hyRXxclBKx/OeaMneK49oz8oWvLN6hlJk/img.png?width=800&height=800&face=341_263_462_394,https://scrap.kakaocdn.net/dn/bxItm3/hyRWq0cwvA/DDRZrKcwrjLoXeRXT9vkbk/img.png?width=800&height=800&face=341_263_462_394,https://scrap.kakaocdn.net/dn/1KsiH/hyRXCrbhhP/mkMsGWKRSK32ohcUy3ZTl0/img.png?width=768&height=768&face=337_264_443_380)