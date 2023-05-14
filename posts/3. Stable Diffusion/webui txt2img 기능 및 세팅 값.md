web ui 화면 상단에 보면 txt2img, img2img, Extras, PNG info 등등이 있는데 이번 포스팅에서는 txt2img 안에 있는 기능들에 대해 알아보고 각각 적절한 세팅값에 대해서도 알려드리도록 하겠습니다. (참고로 필자가 코랩 유저이기 때문에 코랩 기준으로 설명합니다.) 코랩 설치하는 방법을 모르시는 분들은 아래링크 참고해 주세요. [\[Stable Diffusion\] 스테이블 디퓨전 web ui 코랩 초간단 설치 방법](https://ai-designer-allan.tistory.com/entry/Stable-Diffusion-%EC%8A%A4%ED%85%8C%EC%9D%B4%EB%B8%94-%EB%94%94%ED%93%A8%EC%A0%84-web-ui-%EC%BD%94%EB%9E%A9-%EC%B4%88%EA%B0%84%EB%8B%A8-%EC%84%A4%EC%B9%98-%EB%B0%A9%EB%B2%95) 먼저, Stable Diffusion webui 사용법 총정리 가이드를 참고하여 순서대로 배워 보시는 것을 추천드립니다. [스테이블디퓨전 webui 사용 방법 총 정리](https://ai-designer-allan.tistory.com/entry/%EC%8A%A4%ED%85%8C%EC%9D%B4%EB%B8%94%EB%94%94%ED%93%A8%EC%A0%84-webui-%EC%82%AC%EC%9A%A9-%EB%B0%A9%EB%B2%95-%EC%B4%9D-%EC%A0%95%EB%A6%AC) [ 스테이블디퓨전 webui 사용 방법 총 정리 Stable Diffusion webui 사용방법 코랩 설치부터 여러 익스텐션 적용까지 한 번에 총정리 안녕하세요 Allan입니다. 이번 포스팅에서는 지금까지 스테이블 디퓨전 webui를 사용하는 방법에 대해서 다뤘던 ai-designer-allan.tistory.com ](https://ai-designer-allan.tistory.com/entry/%EC%8A%A4%ED%85%8C%EC%9D%B4%EB%B8%94%EB%94%94%ED%93%A8%EC%A0%84-webui-%EC%82%AC%EC%9A%A9-%EB%B0%A9%EB%B2%95-%EC%B4%9D-%EC%A0%95%EB%A6%AC)
## Ⅰ. Stable Diffusion checkpoint checkpoint는 model이라고도 불리는 부분인데 닌텐도 칩처럼 생각하시면 됩니다. 
닌텐도도 칩 갈아 끼울 때마다 다른 게임들을 플레이할 수 있는 것처럼 Stable Diffsion에서도 체크포인트 혹은 모델을 갈아 끼울 때마다 완전히 다른 스타일의 그림을 그릴 수 있게 됩니다. 아래 이미지에서 빨간 박스 친 부분에서 체크포인트를 바꿔 줄 수 있습니다. ![Stable Diffusion checkpoint](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbzJGRN%2Fbtr2Iw26YTR%2FW5zYusotQaoQeLelKju7bk%2Fimg.png) 아무런 모델을 적용하지 않고 기본 모델을 사용하여 나온 그림들은 퀄리티가 매우 낮으니 모델 꼭 적용하고 이용하시는 것을 추천드립니다. (모델 다운/적용하는 방법은 나중에) 
## Ⅱ. Prompt / Negative Prompt 다른 Gen AI 사용해 보신 분들은 Prompt에 대해 익숙하실 것입니다. 
간단하게 설명하자면 prompt는 우리가 만들고 싶은 그림을 설명하는 부분입니다. Negative prompt는 말 그대로 그림에서 제외하고 싶은 키워드를 넣어 주시면 됩니다. 미드저니의  '--no' 파라미터와 비슷한 기능입니다. 
## Ⅲ. 각 종 옵션 prompt 입력란 밑에 보면 각 종 옵션들을 조정할 수 있는 칸이 있습니다. 하나하나 알아보도록 하겠습니다. 
![각 종 옵션](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FoJBBA%2Fbtr2FiqQLVy%2F0an1K2xFsKX9mGgxVKFo61%2Fimg.png) 
### 1. Sampling method 
- 샘플링 메서드는 말 그대로 샘플링하는 방법을 선택하는 것입니다. 
- 어떤 과정을 통해 그림을 그릴지 정하는 것이라고 생각하시면 됩니다. 
- 현재 글을 쓰고 있는 기준으로 가장 많이 사용되는 Sampling method로는 아래 3가지가 있음
	- Euler a 
	- DPM++2M Karras 
	- DPM++SDE Karras 
- 이 셋 중에 선택하셔서 적용해 보시고  마음에 드시는 Sampling method 선택하는 것을 추천드립니다. 
### 2. Sampling steps 
- 몇 번의 단계로 그림을 생성할지 결정하는 부분입니다. 
- 0부터 150까지 설정할 수 있으며 숫자가 높아질수록  더 많은 단계를 통해 그림을 생성합니다. 
- Sampling steps가 높아질수록 더 정교한 그림을 뽑아낼 것 같지만 그건 또 그렇지 않습니다. 
- 어느 정도 이상 높아지면 별다른 차이가 없을뿐더러 오히려 너무 높아지게 되면 그림이 이상해기도 합니다. 
- 보통 ==20~30사이의 값==으로 설정합니다. 
- 모델 별로 추천하는 Sampling steps가 있는데 모델을 다운 받을 때 확인하고 설정하시는 것을 추천드립니다. 
- 또한 Sampling method에 따라서 권장되는 Sampling steps가 있는데 
	- DPM++ 2M Karras, DPM++ SDE Karras는 보통 30, 
	- Euler a는 20으로 설정합니다. 
- 참고해서 설정해 주세요. 
### 3. Restore faces, Tiling
- 말 그대로 얼굴 보정이고 Tiling은 타일패턴으로 그림이 나오는데 사실 쓸 일이 별로 없습니다. 
### 4. Hires.fix 
- Hires는 고해상도를 의미하고 HIres.fix는 고해상도로 그림을 보정해 주는 역할을 합니다. 
- Hires는 먼저 그림이 생성된 이후 한 번 더 고해상도 보정을 하는 방법으로 진행됩니다. 즉, 기본이미지 생성 -> Hires.fix적용해서 다시 생성 이런 과정으로 그림을 생성해 줍니다. 
- Hires.fix에 체크해 주시면 다음과 같은 창이 새로 생깁니다. 
![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FQjgq0%2Fbtr2DF74xJq%2Fo4Dr0cNJZKc2phLUOtRWrk%2Fimg.png) 
- Upscaler** 어떤 방법으로 업스케일을 할지 정해 줍니다. 보통 애니메 스타일은 위 그림과 같이 R-ESRGAN 4x+ Anime6B 혹은 Latent를 실사 이미지는  R-ESRGAN를 사용합니다. **\- 
- Hires steps** 마찬가지로 Sampling step과 유사합니다. Hires.fix 과정을 거칠 때 몇 번의 단계를 거칠지 정해줍니다. Sampling step과 유사하거나 동일하게 설정해 주시는 것을 추천드립니다. (이론적으로 step을 늘릴수록 퀄리티 좋은 그림이 나오겠지만 시간만 무진장 걸릴 뿐 별 차이 없습니다.) **\- 
- Denoising strength** Denoising strength이 높을수록 기존그림에서 많은 변화가 생기고 Denoising strength이 낮을수록 기존 그림과 유사합니다. 0.4~0.6으로 설정해 주시는 것을 추천드립니다. **\- 
- Upscale by** 몇 배 업스케일 할지 설정해 줍니다. 512x512 그림에서 Upscale by를 2로 설정해 주시면  1024x1024 그림으로 나옵니다. 
### 5. Width/Height 
- 가로세로 픽셀 조정 기능입니다. 
- 이 기능으로 설정하시는 것보단 hires.fix나  Extras에서 조절하시는 것을 추천드립니다. 
### 6. CFG Scale 
- 프롬프트의 영향력을 설정해 줍니다. 
- 수치가 낮을수록 프롬프트에 강하게 의존하고 수치가 높을수록 자유도가 증가합니다. 
- 7~9정도로 설정해주시는 것을 추천드립니다. 
### 7. Batch count / Batch size 
- **한 번에 그림을 여러 장 그릴 때 사용합니다.** 
- **Batch count는 생성할 배치 수를 설정해 주고** **Batch size는 하나의 배치에 들어갈 그림의 수를 설정해 줍니다.** 
- **큰 차이는 없으니 그림 여러 장 뽑고 싶으실 때는** **Batch count나 Batch size 둘 중 하나면** **변경하셔서 사용하시는 것을 추천드립니다.** 
### 8. Seed 
- 그림의 고유 번호라고 생각하시면 됩니다. 
- 같은 프롬프트를 입력하더라도 Seed값에 따라 다른 그림이 나오게 됩니다. 동일한 그림을 뽑고 싶으시다면 Seed값을 동일하게 설정해 주시면 됩니다. 
- 기본값은 -1로 되어있는데 \-1로 설정하면 랜덤으로 Seed가 설정됩니다. 
### 9. ControlNet 
- 피사체의 자세나 구도 등을 설정해 주는 기능입니다. ControlNet에 대한 자세한 내용이 궁금하시다면 아래 포스팅을 참고해 주세요. [[webui ControlNet(컨트롤넷) 사용방법]]
![](https://scrap.kakaocdn.net/dn/g4XGl/hyR31FMdkX/C0alYHzzG7cDbW4YX53Uvk/img.png?width=800&height=619&face=493_57_717_476,https://scrap.kakaocdn.net/dn/Bbdmi/hyR37lFGBW/gIoTNsokLeNZOCHz8x0Us1/img.png?width=800&height=619&face=493_57_717_476,https://scrap.kakaocdn.net/dn/enZYgK/hyR385XsG2/0CBwLdBLhSBDnqBxwP17GK/img.png?width=1280&height=997&face=0_0_1280_997) 