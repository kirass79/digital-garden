  먼저 Stable Diffsion 에서 사용되는 파일들을 다운 받을 수 있는 사이트 두 곳 링크를 올려드리도록 하겠습니다. 
	  Civitai : [https://civitai.com/](https://civitai.com/) 허깅 페이스 : [https://huggingface.co/](https://huggingface.co/) 
  
  먼저, Stable Diffusion webui 사용법 총정리 가이드를 참고하여 순서대로 배워 보시는 것을 추천드립니다. [스테이블디퓨전 webui 사용 방법 총 정리](https://ai-designer-allan.tistory.com/entry/%EC%8A%A4%ED%85%8C%EC%9D%B4%EB%B8%94%EB%94%94%ED%93%A8%EC%A0%84-webui-%EC%82%AC%EC%9A%A9-%EB%B0%A9%EB%B2%95-%EC%B4%9D-%EC%A0%95%EB%A6%AC) [ 스테이블디퓨전 webui 사용 방법 총 정리 Stable Diffusion webui 사용방법 코랩 설치부터 여러 익스텐션 적용까지 한 번에 총정리 안녕하세요 Allan입니다. 이번 포스팅에서는 지금까지 스테이블 디퓨전 webui를 사용하는 방법에 대해서 다뤘던 ai-designer-allan.tistory.com ](https://ai-designer-allan.tistory.com/entry/%EC%8A%A4%ED%85%8C%EC%9D%B4%EB%B8%94%EB%94%94%ED%93%A8%EC%A0%84-webui-%EC%82%AC%EC%9A%A9-%EB%B0%A9%EB%B2%95-%EC%B4%9D-%EC%A0%95%EB%A6%AC)! 
  
  ## Ⅰ. Checkpoint (model)
   --- checkpoint 혹은 model이라고도 불립니다. 
   - ==그림을 그리는 AI의 뇌== 즉, 그리는 사람을 선택하는 것이라고 생각하시면 됩니다. 
	   - Stable Diffusion 이라는 몸체에 Checkpoint라는 뇌를 장착시키고  그림을 그리게 만드는 것입니다. 
	   - 어떤 모델을 사용하느냐는  어떤 뇌를 사용하느냐와 같습니다. 
	   - 예를 들면, 피카소 모델을 장착했다면  생성한 그림은 전반적으로 피카소 스타일의 그림이 될 것입니다. 
	   - 하지만 피카소 모델을 장착했다 해서 피카소 스타일의 그림만을 그릴 수 있는 것은 아닙니다. ==반고흐의 그림 스타일을 학습==해서  피카소 모델로 반고흐처럼 그림을 그릴 수 있을 것입니다. 
	   - 여기서 ==학습이라는 것이 밑에서 배울 lora / embedding / hyper network 이 친구들== 입니다. 
	   - 하지만 그렇다고 해서 피카소 모델이 반고흐가 될 수는 없을 것입니다. 뇌는 피카소의 뇌를 장착했으니까요. 
   - 모델에 대해 더 자세하게 알아보고 싶다면 아래 포스팅을 참고해 주세요. [[스테이블 디퓨전 모델(checkpoint)이란  모델 집중 탐구 DesignerAllan]] 
   - Checkpoint(model) 적용하는 방법 [[Checkpoint(model) 적용하기]]
![](https://scrap.kakaocdn.net/dn/yO5LK/hyRSPM7ZLa/ubyLxUFCtNzabed7GZRL50/img.png?width=800&height=281&face=0_0_800_281,https://scrap.kakaocdn.net/dn/bkwVok/hyRSMbLJU3/OQWheloJ4CmLTl8zC7FZO1/img.png?width=800&height=281&face=0_0_800_281,https://scrap.kakaocdn.net/dn/byD5Ar/hyRTYhmTUz/lu8Q9h4QHDLkn8om6NxORk/img.png?width=1024&height=1024&face=432_262_720_575) 

## Ⅱ. lora / embedding / hyper network
- lora, embedding, hyper network 이 세가지는 이미지 생성을 위한 보조 모델입니다. 또한 학습된 데이터와 유사한 그림을 생성할 수 있게 됩니다. 
- 이 세가지 용어는 모두 webui에서 나온 단어가 아니라 AI에서 사용되는 전문용어이기 때문에 사실 정확한 이해는 필요하지 않습니다. 다만, 그 느낌의 차이를 이해하면 어떤 것을 선택해야 할지 도움이 될 수 있기 때문에 간단하게 알아보도록 하겠습니다. 
### 1. lora 로라는 드림부스 기반 학습입니다. 
- 드림부스는 가장 영향력이 큰 학습방법이라고 생각하시면 됩니다. 비유해 보자면 뇌 전체를 수술한다고 볼 수 있습니다. 
- 로라는 ==학습된 뇌의 일부를 추출하여서 우리가 쓰는 Model(뇌)에 이식 시키는 정도==로 생각하시면 되겠습니다. 로라는 대부분의 경우에 피사체를 위주로 학습을 하게 됩니다. 장점 - 원하는 스타일의 그림을 생성할 수 있을 만큼 영향력이 크다. 
- 드림부스 기반이지만 용량이나 GPU의 요구성능이 그렇게 크거나 높지 않다. 
- 동시에 여러 lora를 적용할 수 있다. (적용 가중치도 조절할 수 있음) 
### 2. embedding textual inversion이라고도 합니다. 
- 임베딩은 모델에 영향을 주지 않은 채 프롬프트를 추가 학습하는 방법입니다. 즉, 추가적인 특징 하나 정도를 만들어 준다고 생각하시면 될 것 같습니다. 예를 들자면 모델을 '공부'시키는 정도가 될 것 같습니다. 장점  - 여러 임베딩을 한번에 적용할 수 있다. - 여러 모델에서 자유롭게 사용할 수 있다. - 용량이 가볍다. 단점 - 용량이 작고, 영향력이 작은 만큼  원하는 특징이 나타나지 않는 경우가 있다. lora/embedding 적용방법은 아래 포스팅 참고 [스테이블 디퓨전 colab에서 lora와 embedding 적용하기](https://ai-designer-allan.tistory.com/entry/%EC%8A%A4%ED%85%8C%EC%9D%B4%EB%B8%94-%EB%94%94%ED%93%A8%EC%A0%84-colab%EC%97%90%EC%84%9C-lora%EC%99%80-embedding-%EC%A0%81%EC%9A%A9%ED%95%98%EA%B8%B0) [ 스테이블 디퓨전 colab에서 lora와 embedding 적용하기 안녕하세요 Allan 입니다. 이번 포스팅에서는 lora 와 embedding을 적용하는 방법에 대해서 알아보겠습니다. 로라를 적용할 때 입력해야 할 trigger words, 로라와 임베딩의 가중치 등등 처음시작하시는 ai-designer-allan.tistory.com ](https://ai-designer-allan.tistory.com/entry/%EC%8A%A4%ED%85%8C%EC%9D%B4%EB%B8%94-%EB%94%94%ED%93%A8%EC%A0%84-colab%EC%97%90%EC%84%9C-lora%EC%99%80-embedding-%EC%A0%81%EC%9A%A9%ED%95%98%EA%B8%B0)![](https://scrap.kakaocdn.net/dn/dWhNdC/hyRTSPKMou/uylqP6kMpBDMSwnj5OBnRK/img.png?width=800&height=800&face=337_205_562_450,https://scrap.kakaocdn.net/dn/cCc6ZQ/hyRTLb3vir/0l4NJ9HJxL9RGAGIyLr7A0/img.png?width=800&height=800&face=337_205_562_450,https://scrap.kakaocdn.net/dn/JzeJU/hyRTPS13r0/cxIM5nCaY1nKug1aBmH8M0/img.png?width=1491&height=831&face=265_246_474_474) 
### 3. hyper network 하이퍼 네트워크는 임베딩과 유사하다고 생각하시면 됩니다. 
- 로라가 뇌의 일부를 이식해서 뇌 자체를 변형시키는 것이라면 하이퍼 네트워크는 뇌를 바꾸는 것이 아니라 임베딩 처럼 '공부'를 시키는 것이라 볼 수 있습니다. 따라서 하이퍼 네트워크는 로라만큼의 영향력을 줄 수는 없습니다. 하지만 임베딩 보다는 더 큰 영향력을 행사할 수 있습니다. 임베딩이 학교에서 '공부'하는 것 정도라면 하이퍼 네트워크는 어렸을 때 부터 머리속에 '각인'시키는 것이라 볼 수 있겠습니다. 그렇기 때문에 하이퍼 네트워크는 임베딩보다는 훨씬 큰 용량을 가지고 있습니다. '뇌'를 바꾸는 로라와 비슷한 정도의 용량입니다. 그래서 저는 하이퍼 네트워크보다는 로라를 사용하는 것을 선호합니다. 물론 하이퍼 네트워크만의 장점도 분명 존재하겠지만 제 개인적인 생각은 로라가 더 좋은 것 같습니다. 
## Ⅲ. vae 
- vae는 ==그림을 보정해 주는 역할==이라고 생각하시면 됩니다. 
- 그림이 흐리게 나온다거나 남들이 뽑은 그림보다 퀄리티가 떨어지는 것 같다면 vae를 적용하지 않았을 가능성이 큽니다. vae도 마찬가지로 많은 종류가 있지만  용도별로 가장 많이 쓰이는 vae 두 가지를 소개해 드리도록 하겠습니다. 
- 그림 스타일에 맞게 사용하시는 것을 추천드립니다. 
	- > 반 실사용 vae [https://huggingface.co/stabilityai/sd-vae-ft-mse-original/blob/main/vae-ft-mse-840000-ema-pruned.ckpt](https://huggingface.co/stabilityai/sd-vae-ft-mse-original/blob/main/vae-ft-mse-840000-ema-pruned.ckpt) 
	- 2D용 vae [https://huggingface.co/hakurei/waifu-diffusion-v1-4/blob/main/vae/kl-f8-anime2.ckpt](https://huggingface.co/hakurei/waifu-diffusion-v1-4/blob/main/vae/kl-f8-anime2.ckpt) 
### 1. vae 적용 방법
[[vae적용 한번에 끝내기]]
![](https://scrap.kakaocdn.net/dn/QlB8t/hyRTMhHlB3/ycYAfKcfqGqDQzmotw9DR1/img.png?width=800&height=125&face=0_0_800_125,https://scrap.kakaocdn.net/dn/MNDC2/hyRTVeHeIm/5qKlOstD444ZRhxI13hGV1/img.png?width=800&height=125&face=0_0_800_125,https://scrap.kakaocdn.net/dn/OE241/hyRTLpAunJ/diSFmkkbtwgw7TAdL12wvk/img.png?width=983&height=725&face=0_0_983_725) 
