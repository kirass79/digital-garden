안녕하세요 Allan입니다. 이번 포스팅에서는  보정을 해주는 역할인 vae 적용하는 방법에 대해서 알아보겠습니다. 
## Ⅰ. vae 적용하기 
### 1. vae 다운받기 
- 먼저 vae를 다운 받아 주도록 하겠습니다. > 
	- 실사용 vae [https://huggingface.co/stabilityai/sd-vae-ft-mse-original/blob/main/vae-ft-mse-840000-ema-pruned.ckpt](https://huggingface.co/stabilityai/sd-vae-ft-mse-original/blob/main/vae-ft-mse-840000-ema-pruned.ckpt) > 
	- 2D용 vae [https://huggingface.co/hakurei/waifu-diffusion-v1-4/blob/main/vae/kl-f8-anime2.ckpt](https://huggingface.co/hakurei/waifu-diffusion-v1-4/blob/main/vae/kl-f8-anime2.ckpt) 
- 이 외에도 많은 종류의 vae가 있지만  목적별로 가장 많이 사용되는 vae를 가져와 봤습니다. 
### 2. vae 올바른 경로에 넣어주기 
- vae는 다음과 같은 경로에 넣어 주시면 됩니다. > 
	- sd/stable-diffusion-webui/models/VAE 
### 3. webui에서 vae 적용하기 
1) vae를 적용하기 위해 webui로 들어가 줍니다. [[내PC에 적용하기]]
2) 상단에 여러 탭 중 Settings 탭으로 들어가 줍니다. 
![settings](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2F61UAU%2Fbtr3dTR0zMW%2FcJgW6QmQM4ZbQwlBW2JCy0%2Fimg.png) 3) 다음 그림과 같이 좌측의 Stable Diffusion에 들어가 줍니다. ![](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FqgkVR%2Fbtr3dcjWIIX%2Fz9sj6he3SSsVbihDPT3QU1%2Fimg.png) 4) SD VAE 탭을 클릭해 주면 VAE폴더에 있는 파일들이 보이게 되는데 목적에 맞게 선택해 주시면 됩니다.