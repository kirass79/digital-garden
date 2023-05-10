---
page-title: "ControlNet WEBUI 확장기능을 이용해서 쉽게 포즈 변경하기 - AI 그림 채널"
url: https://arca.live/b/aiart/69816884
date: "2023-04-24 17:23:15"
---
[![](https://ac-p1.namu.la/20230214sac2/d6f79d53a018894aeb41945e614deddab7c01b1fba6ef8d71b7a6e036269cd63.png?expires=1682327978&key=OkSr8J2mC01brUK4Ylstzw)](https://ac-p1.namu.la/20230214sac2/d6f79d53a018894aeb41945e614deddab7c01b1fba6ef8d71b7a6e036269cd63.png?expires=1682327978&key=OkSr8J2mC01brUK4Ylstzw&type=orig)

어제 오늘자로 컨트롤넷 WEBUI 확장에서

SEG, NORMAL MAP 기능이 추가됨에 따라 설치 및 사용 방법에 대해 알려주겠음

예전 pix2pix나 wd+sd뎁스보다 성능 ㄹㅇ 확실하니 찍먹 꼭 해라

미니콘다 방식으로 설치한 사람도 넘어가도 괜찮을 듯함

모든 기능이 작동하긴 하는데,

아직 WIP라 계속 개선해나갈테니 하루 한번쯤은 확장기능 업데이트 누르는걸 권장

[![](https://ac-p1.namu.la/20230214sac2/34070f46b6eec1b3849c581c2dd8165c93f9400e68a1b5da06092d87699e4173.png?expires=1682327978&key=uPKvIH44JrGyJb-VSrTSEw)](https://ac-p1.namu.la/20230214sac2/34070f46b6eec1b3849c581c2dd8165c93f9400e68a1b5da06092d87699e4173.png?expires=1682327978&key=uPKvIH44JrGyJb-VSrTSEw&type=orig)

1\. 확장기능 -> URL로부터 확장기능 설치로 가서 아래 링크를 입력하고 설치한다. 

[https://github.com/Mikubill/sd-webui-controlnet](https://oo.pe/https://github.com/Mikubill/sd-webui-controlnet "github.com/Mikubill/sd-webui-controlnet (외부 사이트)")

2번에서 Refresh model했을때 추가된 모델 안보일 수 있으니, 설치한 다음에 일단 WEBUI 완전 종료한다.

[![](https://ac-p1.namu.la/20230214sac2/70d75a45a061229f03b4361e9425b9ccf327767171cc6c596973858202c01bd3.png?expires=1682327978&key=ppmMSJv9IME1w6IzsO9wZg)](https://ac-p1.namu.la/20230214sac2/70d75a45a061229f03b4361e9425b9ccf327767171cc6c596973858202c01bd3.png?expires=1682327978&key=ppmMSJv9IME1w6IzsO9wZg&type=orig)

[![](https://ac-p1.namu.la/20230221sac2/eb36fb4d01ce1fdcd4373882fa10be62b5e8fa1e723c82c5bba048118b656a54.png?expires=1682327978&key=IZFtkSpoi4O376v15vM2Mg)](https://ac-p1.namu.la/20230221sac2/eb36fb4d01ce1fdcd4373882fa10be62b5e8fa1e723c82c5bba048118b656a54.png?expires=1682327978&key=IZFtkSpoi4O376v15vM2Mg&type=orig)

2\. [https://huggingface.co/lllyasviel/ControlNet/tree/main/models](https://oo.pe/https://huggingface.co/lllyasviel/ControlNet/tree/main/models "huggingface.co/lllyasviel/ControlNet/tree/main/models (외부 사이트)")

[https://civitai.com/models/9251/controlnet-pre-trained-models](https://oo.pe/https://civitai.com/models/9251/controlnet-pre-trained-models "civitai.com/models/9251/controlnet-pre-trained-models (외부 사이트)")

위 링크에 가서 모델을 다운 받는다. (huggingface는 원본, civitai는 용량 압축모델)

huggingface 원본 파일은 다 합쳐서 50기가 가까이 되니까 용량 부족한 사람은 civitai가서 압축 모델 받거나

찝찝하면 huggingface에서 필요한 원본 모델만 다운받으면 됨

**그리고 제발 모델 하나만 받아놓고 왜 안되냐고 그러지 마라.**

**openpose할거면 openpose 모델 받아야지 왜 canny 모델받아놓고 안된다 그럼?**

Civitai에서 무지성으로 다운로드 누르지말고 밑으로 스크롤해서 필요한 모델로 바꿔 받아라

그리고 혹시 이전에 미니콘다 방식으로 설치한 사람들은

**기존 애니띵 병합모델 삭제하고 이거로 새로 받아라.** 

그 이유는 간단함

[![](https://ac-p1.namu.la/20230214sac2/2c82767bc69a00c901b504d626396b461c29090cba5c86b770cd5ccdd5d10b4a.png?expires=1682327978&key=-3CMq_OLocLtKQJ3ZDMw_w)](https://ac-p1.namu.la/20230214sac2/2c82767bc69a00c901b504d626396b461c29090cba5c86b770cd5ccdd5d10b4a.png?expires=1682327978&key=-3CMq_OLocLtKQJ3ZDMw_w&type=orig)

[](https://arca.live/e/26900)

WEBUI 확장에선 모델 병합없이도 다른 모델이랑 쓰까쓰기 가능함

[![](https://ac-p1.namu.la/20230214sac2/8f2d24efc272f67802cdd56147c2f120666d8b462a4adc720f2e192f97732464.png?expires=1682327978&key=1FrLAbdzOpS12JRkmlHQkg)](https://ac-p1.namu.la/20230214sac2/8f2d24efc272f67802cdd56147c2f120666d8b462a4adc720f2e192f97732464.png?expires=1682327978&key=1FrLAbdzOpS12JRkmlHQkg&type=orig)

3\. stable-diffusion-webui\\extensions\\sd-webui-controlnet\\models

확장 기능이 설치된 폴더로 이동해보면 models 폴더가 있을텐데

여기에 2번에서 다운받은 모델을 집어넣으면 됨

[![](https://ac-p1.namu.la/20230214sac2/427df35275995cce2318583d2e606d8b92f30c1a11cf70c77c1fd6f2fbdd2d05.png?expires=1682327978&key=KBBsGkV70okuVXa_crlUoQ)](https://ac-p1.namu.la/20230214sac2/427df35275995cce2318583d2e606d8b92f30c1a11cf70c77c1fd6f2fbdd2d05.png?expires=1682327978&key=KBBsGkV70okuVXa_crlUoQ&type=orig)

[![](https://ac-p1.namu.la/20230214sac2/c01c5df28b8d07b3b92d5deceacb3aa6cd61b503062e791f47d2539801939bf2.png?expires=1682327978&key=i2ILzlQvd4Np421TZ9sXKg)](https://ac-p1.namu.la/20230214sac2/c01c5df28b8d07b3b92d5deceacb3aa6cd61b503062e791f47d2539801939bf2.png?expires=1682327978&key=i2ILzlQvd4Np421TZ9sXKg&type=orig)

4\. TXT2IMG 또는 IMG2IMG 탭에서 아래로 스크롤해보면 ControlNet 확장기능이 있을거임

Enable 체크하면 되고, 자기 VRAM이 8기가 이하다 싶으면 Low VRAM도 같이 체크하면 됨

preprocessor랑 model을 설정해야 사용 가능한데 이건 조금 뒤에 설명함

[![](https://ac-p1.namu.la/20230214sac2/91e766a546ef5c84dbf53d0b5ddc67549cf43f37c886e23c8ce7434a795fd367.png?expires=1682327978&key=B5X3_-3vLyMgL9qzfyOEow)](https://ac-p1.namu.la/20230214sac2/91e766a546ef5c84dbf53d0b5ddc67549cf43f37c886e23c8ce7434a795fd367.png?expires=1682327978&key=B5X3_-3vLyMgL9qzfyOEow&type=orig)

Weight는 컨트롤넷이 적용되는 강도라고 생각하면 됨

분석결과가 100% 동일한거 보면 알겠지만, 컨트롤넷 분석 결과를 얼마나 충실히 재현할지 고르는거라고 보면 될듯

[![](https://ac-p1.namu.la/20230214sac2/3175024928720c93c33abc33a96bca29ba6ca27ccf8f6a7f2e49263cf4a3d759.jpg?expires=1682327978&key=EhkRQ-8aFf3A0793K1Q7Ag)](https://ac-p1.namu.la/20230214sac2/3175024928720c93c33abc33a96bca29ba6ca27ccf8f6a7f2e49263cf4a3d759.jpg?expires=1682327978&key=EhkRQ-8aFf3A0793K1Q7Ag&type=orig)

리사이즈 모드는

뭘 골라도 애자같으니 애초에 그림 width, height 사이즈랑 일치시키는게 낫지만

일단 어떻게 작동하는지 보여주자면 아래와 같음

[![](https://ac-p1.namu.la/20230214sac2/ff4ee8ac1037b7a3bf1939f770b244eaed5fbeb2e3d122e7a9da25dd56a6a91b.jpg?expires=1682327978&key=OaGbh8UZbIxmQutDMo6gxg)](https://ac-p1.namu.la/20230214sac2/ff4ee8ac1037b7a3bf1939f770b244eaed5fbeb2e3d122e7a9da25dd56a6a91b.jpg?expires=1682327978&key=OaGbh8UZbIxmQutDMo6gxg&type=orig)

Outer Fit은 그림 사이즈랑 맞지 안될 경우 무조건 대가리깨져도 확대함. 걍 좌우를 쳐내는게 맞지 않노..

inner fit은 그림 사이즈랑 맞지 않을 경우 레터박스를 넣으면서 비율을 유지함

Just resize 고르는 흑우없제? 그림 찌그러진다 하지마라

img2img탭에서 오류 뜨는 경우는 ControlNet에만 이미지 넣고, img2img엔 이미지 안넣어서 그런거임

딱히 img2img 기능이 필요하지 않으면 txt2img탭으로 굴리면 된다. txt2img탭의 ControlNet에도 img 넣는 기능이 있음

[![](https://ac-p1.namu.la/20230214sac2/9e253cba86209af9a7b06abcaf52d0ce4ce2e33f51b8c56f750050b403061fed.png?expires=1682327978&key=eeAbf-wLGeq2vETpxGcK5w)](https://ac-p1.namu.la/20230214sac2/9e253cba86209af9a7b06abcaf52d0ce4ce2e33f51b8c56f750050b403061fed.png?expires=1682327978&key=eeAbf-wLGeq2vETpxGcK5w&type=orig)

[![](https://ac-p1.namu.la/20230214sac2/036ee992b1512cb61bc21cf4445374b0cccee815f07f4952b97cfab60046e8dc.png?expires=1682327978&key=QMc1DOMGiJDgr9EqaT0Bsw)](https://ac-p1.namu.la/20230214sac2/036ee992b1512cb61bc21cf4445374b0cccee815f07f4952b97cfab60046e8dc.png?expires=1682327978&key=QMc1DOMGiJDgr9EqaT0Bsw&type=orig) 

[https://arca.live/b/aiart/69724880](https://arca.live/b/aiart/69724880)

**컨트롤넷 처음이면 위 링크 일단 읽어봐라**

각 모델별 추가 설명은 위 링크에 가보면 있음. 

용량 넉넉하면 openpose 외에도 Depth, Normal, Canny, HED 등 다른거도 받아봐라. 쓸만함

**그리고 포즈 추출할거면 openpose 받아야지** 

**선 따주는 canny받아놓고 왜 안된다 그럼?**

모델별로 특징이 다르니 엉뚱한 모델 받아놓고 안된다고 하지마라

**Preprocessor None = 직접 생성한 뼈대, 뎁스맵 등의 이미지를 넣을 때**

**Preprocessor 설정 = 사진에서 뼈대, 뎁스맵 등을 추출할 때**

[![](https://ac-p1.namu.la/20230214sac2/095d9b1e601b028b8b3588e03e7ec486af85be7617651b738f2a6fff86b9303b.png?expires=1682327978&key=5mW4btoNYG4x-3pFvcAiBQ)](https://ac-p1.namu.la/20230214sac2/095d9b1e601b028b8b3588e03e7ec486af85be7617651b738f2a6fff86b9303b.png?expires=1682327978&key=5mW4btoNYG4x-3pFvcAiBQ&type=orig)

1-a. Pose 설정방법 (사진/그림에서 뼈대 추출할 때)

[![](https://ac-p1.namu.la/20230217sac2/92bb0152ea013cd48986f8218c8d5f320cf97ae31863a38f64c77cbd8707e12b.png?expires=1682327978&key=DNeV99dwp21wqE5HLzYPbQ)](https://ac-p1.namu.la/20230217sac2/92bb0152ea013cd48986f8218c8d5f320cf97ae31863a38f64c77cbd8707e12b.png?expires=1682327978&key=DNeV99dwp21wqE5HLzYPbQ&type=orig)

1-B. Pose 설정방법 (직접 만든 뼈대를 입력할 때)

[![](https://ac-p1.namu.la/20230215sac2/c3c70c5c3569d9ab2333e23fd0c6671ba9bb8a30a6b2f5a27b61e737e1585f96.png?expires=1682327978&key=hFb5ial2piEPfKFQ48VhUw)](https://ac-p1.namu.la/20230215sac2/c3c70c5c3569d9ab2333e23fd0c6671ba9bb8a30a6b2f5a27b61e737e1585f96.png?expires=1682327978&key=hFb5ial2piEPfKFQ48VhUw&type=orig)

2-A. Depth 설정방법 (사진, 그림에서 뎁스맵 추출할 때)

[![](https://ac-p1.namu.la/20230217sac2/ad1155a2bd02ba8b4749d54da23ae235db42af8e030abb6671daa0d6e4c89efa.png?expires=1682327978&key=t6Afj2TkqqTbvkFiW80n_w)](https://ac-p1.namu.la/20230217sac2/ad1155a2bd02ba8b4749d54da23ae235db42af8e030abb6671daa0d6e4c89efa.png?expires=1682327978&key=t6Afj2TkqqTbvkFiW80n_w&type=orig)

2-B. Depth 설정방법 (직접 제작한 뎁스맵 입력할 때)

[![](https://ac-p1.namu.la/20230214sac2/c31d38d923e3d80957165e4d5ff8102c392f735010eb107a7e9b0ce900dd0fd1.png?expires=1682327978&key=ea00Oc8cp12S4yGVOU23_A)](https://ac-p1.namu.la/20230214sac2/c31d38d923e3d80957165e4d5ff8102c392f735010eb107a7e9b0ce900dd0fd1.png?expires=1682327978&key=ea00Oc8cp12S4yGVOU23_A&type=orig)

3\. Normal 설정방법

[![](https://ac-p1.namu.la/20230214sac2/88393f3d09cac8bc689b038fb1b55ea0d41ab26014e4ad448b507a1a7c19a594.png?expires=1682327978&key=BeoV4BqMKLG0TwlTeD8CfA)](https://ac-p1.namu.la/20230214sac2/88393f3d09cac8bc689b038fb1b55ea0d41ab26014e4ad448b507a1a7c19a594.png?expires=1682327978&key=BeoV4BqMKLG0TwlTeD8CfA&type=orig)

4\. Seg 설정방법

\* SEG가 목록에 안나올경우 cmd창 열고 pip install prettytable 하고 WEBUI 껐다 켜봐라

[![](https://ac-p1.namu.la/20230214sac2/7ca30b1d2c60861282461d56fcd1dc173147290a51ac3255ad6a3a78e67e6c4e.png?expires=1682327978&key=pm8YpJmy_k1N84_2FIv9lw)](https://ac-p1.namu.la/20230214sac2/7ca30b1d2c60861282461d56fcd1dc173147290a51ac3255ad6a3a78e67e6c4e.png?expires=1682327978&key=pm8YpJmy_k1N84_2FIv9lw&type=orig)

5\. MLSD 설정방법

[![](https://ac-p1.namu.la/20230214sac2/f2ac63c276491057ab124090d0232cb42af4981fb927ab470d22b75c99893c4f.png?expires=1682327978&key=0f9PKOOk3i3wwjBn3lEb2Q)](https://ac-p1.namu.la/20230214sac2/f2ac63c276491057ab124090d0232cb42af4981fb927ab470d22b75c99893c4f.png?expires=1682327978&key=0f9PKOOk3i3wwjBn3lEb2Q&type=orig)

6\. CANNY 설정방법

[![](https://ac-p1.namu.la/20230214sac2/f1c5d8db49994241dd7cab92a2ffcdfdb37a83d34a45f2640c56df1cb08e62b9.png?expires=1682327978&key=096iko97NYW9sAHSITlTOg)](https://ac-p1.namu.la/20230214sac2/f1c5d8db49994241dd7cab92a2ffcdfdb37a83d34a45f2640c56df1cb08e62b9.png?expires=1682327978&key=096iko97NYW9sAHSITlTOg&type=orig)

7\. HED 설정방법

[![](https://ac-p1.namu.la/20230214sac2/05d65e637fff1e14c19918bfc2fb5d2a161cc18ba7f5f313c02ff4981bd70b5d.png?expires=1682327978&key=-KSHFhlpNUaG0JtOVE5iYQ)](https://ac-p1.namu.la/20230214sac2/05d65e637fff1e14c19918bfc2fb5d2a161cc18ba7f5f313c02ff4981bd70b5d.png?expires=1682327978&key=-KSHFhlpNUaG0JtOVE5iYQ&type=orig)

8\. SCRIBBLE 설정방법

preprocessor는 none으로 설정한 상태로 두고 모델만 변경하면 됨

손으로 그린 그림 밑에 넣으면 된다.

[![](https://ac-p1.namu.la/20230214sac2/5172a8b9ec0f0ab6416fdbf763cde2f0bc317796fbfa566ef0101d34d1697303.png?expires=1682327978&key=o9WTmVIBMblv3j0UpBLF9w)](https://ac-p1.namu.la/20230214sac2/5172a8b9ec0f0ab6416fdbf763cde2f0bc317796fbfa566ef0101d34d1697303.png?expires=1682327978&key=o9WTmVIBMblv3j0UpBLF9w&type=orig)

9\. SCRIBBLE INTERACTIVE 설정방법

preprocessor는 none으로 설정한 상태로 두고 모델만 변경하면 됨

opening draw canvas 클릭해서 그리는거 나오면 거기다 그리면 된다.

[![](https://ac-p1.namu.la/20230214sac2/f98bc5e578d94b6de43d166bf8bd7abd060450904f0b4a9bda779074706d4a7e.png?expires=1682327978&key=YShAtK9l_E26fkar-z5zpQ)](https://ac-p1.namu.la/20230214sac2/f98bc5e578d94b6de43d166bf8bd7abd060450904f0b4a9bda779074706d4a7e.png?expires=1682327978&key=YShAtK9l_E26fkar-z5zpQ&type=orig)

10\. SCRIBBLE fake 설정방법

딱히 포즈, 뎁스맵, scribble에서만

Preprocessor none으로 해놓고 직접 만든 데이터 넣는거 되는게 아니라 다른거도 다 됨. 

그냥 자주 찾는 것들만 예시로 해놓은거임