page-title: "Stable Diffusion Web UI(SD) 초 간단 윈도우 설치방법 속도 높이는법 소개."
url: https://loodyrunning.tistory.com/2718
date: "2023-04-17 14:35:42"
---
## Stable Diffusion Web UI(SD) 초 간단 윈도우 설치방법 속도 높이는법 소개.

SD 윈도우 설치

윈도우상에서 로컬로 설치하는 Stable Diffusion Web UI(이하 SD) 이미지 AI의 초 간단 인스톨 방법을 소개합니다.

이 글을 읽으시는 분은 「윈도우에서 소프트를 사용할 수 있는 사람」정도로, 프로그래밍등을 몰라도 괜찮습니다. 그럼 SD 윈도우 설치법과 기본적인 조작법 업데이트까지 살펴보겠습니다.

## Stable DIffusion Web UI는?

![](https://blog.kakaocdn.net/dn/o96Ib/btr3efmPGJd/WlMftKlG1Rv8Ek4ekKJr31/img.png)

브라우저 상에서 Stable Diffusion을 컨트롤 할 수 있도록 한 것입니다. 슬라이더 등이 추가되어 세세한 설정이 직관적으로 용이합니다.

그 중에서도 AUTOMATIC1111가 제작한 버전이 설치도 간단하고 다기능이기 때문에 소개합니다. 많은 사람들이 주로 이 버전으로 제작하고 있습니다. 모 커뮤에서 사용하는 통합패치도 이 버전을 사용한것으로 알려져 있습니다.


## NVIDIA제 그래픽 보드를 탑재한 PC가 필요합니다.

윈도우 상에서 Stable Diffusion을 작동시키기 위해서는 NVIDIA GeForce 시리즈나 NVIDIA RTX A 시리즈 등의 NVIDIA 그래픽 보드를 탑재한 PC가 필요합니다.

4GB VRAM에서도 움직이도록 튠되어 있는 것 같으니 지포스 등을 이용하시는 분들은 일단 시도해 보는 것은 어떨까요?

하지만 저사양 그래픽 카드는 AI 이미지를 만드는데, 압박이 심할것입니다.

## 윈도우 상에서 「로컬」의 전제 환경을 구축하다

Stable Diffusion Web UI 를 윈도우 상에서 움직이는 경우는, 이하의 소프트웨어류를 인스톨 할 필요가 있습니다.

・Python 3.10.6 or Python 3.10.8  
・Git

이것만 있으면 됩니다.

## Python 설치

![](https://blog.kakaocdn.net/dn/czVQmA/btr3pqHxo4Q/W5xeWYGLGq0MKaeQ5bD3YK/img.png)

Python은 Stable Diffusion을 움직이기 위한 프로그래밍 언어입니다.

Pasted-180

Python 3.10.6 의 윈도우 installer (64-bit) 를 다운로드 합니다.

**※최신 3.11 이후에는 실행 시 오류가 발생합니다. 반드시 3.10.6 또는 Python 3.10.8을 넣어주세요.**  
위 두 버전은 작성자가 실행 테스트를 한것들입니다.

### Add Python 3.10 to PATH에 체크

![](https://blog.kakaocdn.net/dn/bxpsw9/btr3cKgPnsP/kJ1mdwE3NoKPd9hYUcwKZ0/img.png)

Python 설치 첫 화면에서는 왼쪽 하단에 Add Python 3.10 to PATH라는 체크 버튼이 있어서 체크를 하겠습니다.

그런 다음 Install Now를 눌러 설치를 시작합니다.

### 경로 최대 260자 제한 해제

![](https://blog.kakaocdn.net/dn/dPCtd8/btr3bpEdu7i/dq50qHj8Ho46kHSwmngd3k/img.png)

설치가 완료된 후에 "Disable path length limit" 버튼이 보이므로 이를 누릅니다.

이를 누르면 260자까지의 경로 길이(폴더 이름 등의 길이) 제한을 해제하기 위한 레지스트리 변경 처리가 이루어집니다. 윈도우 10 버전 1607 이후에 대응한 기능이 됩니다.

하는 이유는 Stable Diffusion 등의 처리에서 긴 경로명을 실행하거나 할 때 260자 이상이 되는 경우가 있어 에러가 날 수 있기 때문입니다.

자세한 내용을 알고 싶으신 분은 Microsoft 자료 등을 참조해 봅시다.

### Python 동작확인

설치 후 명령 프롬프트를 실행하여 "python-V"를 실행하고 Python 버전이 나타나면 정상적으로 설치되어 있습니다.

![](https://blog.kakaocdn.net/dn/dOcHvf/btr3bpc863j/Ad5TW3k2Ie2dclSPk5521K/img.png)

```
python -V

Python 3.10.6
```

## Git 설치

![](https://blog.kakaocdn.net/dn/sVvBf/btr3ezet1OT/v66kcGjrrtBndM4Ty45Xwk/img.png)

이어서 'GitHub'에서 데이터를 가져오기 위한 'Git'이라는 툴을 설치합니다.

[공식 사이트](https://gitforwindows.org/)에서 64-bit의 Git for 윈도우 최신 버전을 다운로드합니다.

![](https://blog.kakaocdn.net/dn/bWIhrJ/btr3gMLfQbH/CAfEus0or5gu1cuWwkkYq0/img.png)

설치 시에는 다양한 옵션이 있는데 Select Components의 Git Bash Here에 체크를 해두도록 하겠습니다. 이를 통해 Stable Diffusion WebUI 업데이트가 편해집니다.

그 외에는 특별히 변경할 점은 없습니다. Next 눌러가면 됩니다.

### Git 동작 확인

설치 후 명령 프롬프트를 실행하고 git-v를 실행하여 Git 버전이 나타나면 정상적으로 설치되어 있습니다.

![](https://blog.kakaocdn.net/dn/cnnOfI/btr3oe1tV9r/ObhCSsevz7oZ4au58lqrJK/img.png)

```
git -v

git version 2.37.3.Windows.1
```

## Stable Diffusion Web UI 설치 및 부팅

### Stable Diffusion Web UI 다운로드 및 압축 해제

Stable Diffusion Web UI 설치 장소는 어디든 괜찮은데 이번에는 C:\\stable-diffusion-webui에 설치하는 형태로 소개하겠습니다.

ZIP 파일을 DL하여 압축 해제하거나 Git 명령으로 설치하는 두 가지 방법이 있습니다.

#### 명령 프롬프트에서 Git를 실행하는 방법 \[추천\] 초 간단

명령 프롬프트 상에서 Git 명령을 사용하여 설치할 수도 있습니다.Stable Diffusion Web UI 업데이트가 편해서 추천드립니다.

git clone 명령어를 사용하면 커런트 디렉토리에 stable-diffusion-webui 폴더가 전개됩니다.

예를 들어 아래와 같이 "cd C:"(C드라이브 바로 아래로 이동)을 한 후 git clone 명령을 실행하면 C:\\stable-diffusion-webui 폴더에 필요한 파일이 전개됩니다.

![](https://blog.kakaocdn.net/dn/I6bVl/btr3c22F3RC/AqkioXNQJGNljqQTCm2DG1/img.png)

```
cd C:\

git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui.git
```

![](https://blog.kakaocdn.net/dn/c3iwe7/btr3bdw5WQ3/kEOno19VYoA0vGy9PLUftk/img.png)

SD 윈도우 설치

#### ZIP 파일을 해동하는 방법【업데이트가 귀찮음】

Git을 도저히 사용할 수 없다면 이 방법입니다. Stable Diffusion Web UI 업데이트를 검토하고 있는 경우 적합하지 않습니다.

![](https://blog.kakaocdn.net/dn/12fq3/btr3cckktqn/fK4aikaHSqKTMACQTpmTp1/img.png)

[깃허브 페이지](https://github.com/AUTOMATIC1111/stable-diffusion-webui)에서 녹색 Code 버튼 > Download ZIP 에서 stable-diffusion-webui.zip 를 다운로드 합니다.

Zip 폴더 내의 stable-diffusion-webui 폴더를 복사하여 C드라이브 바로 아래에 붙입니다.

### 모델 파일(ckpt 파일) 다운로드 및 설치(2023/2/5 업데이트)

Stable Diffusion에서 이용할 수 있는 모델 파일(ckpt 파일)을 준비해야 합니다.

다양한 모델이 있으니 한 예를 소개해 드릴게요.

-   Stable Diffusion(3.97GB) ([Hugging Face](https://huggingface.co/CompVis/stable-diffusion-v-1-4-original)、sd-v1-4.ckpt DL)
-   Waifu Diffusion의 애니메이션 일러스트 특화 모델(7.2GB) ([Hugging Face](https://huggingface.co/hakurei/waifu-diffusion-v1-3)에서 Waifu Diffusion v1.3의 Float 32 Full Weights (wd-v1-3-full.ckpt)을 DL)
-   AI봇 모델 개량판([Hugging Face](https://huggingface.co/naclbit/trinart_stable_diffusion_v2)에서 하나의 ckpt를 DL)
-   Anything V4.0(7.7GB) ([Hugging Face](https://huggingface.co/andite/anything-v4.0/tree/main) anything-v4.0.ckpt、anything-v4.0.vae.pt DL)

애니메이션 일러스트를 주로 내고 싶은 사람은 2~4일까요? 어느 쪽을 이용하는 경우든 다운로드한 ckpt 파일이나 vae.pt 파일은 C:\\stable-diffusion-webui\\models\\Stable-diffusion에 넣습니다.

#### 다중 모델 설치 가능

여러 모델 파일을 넣을 수 있으며 WebUI 왼쪽 상단에서 전환 가능합니다.

.ckpt파일을 폴더안에 넣으면 부팅이 없어도 전활할 수 있습니다. 예를 들어 sd-v1-4.ckpt와 wd-v1-3-full.ckpt를 C:\\stable-diffusion-webui\\models\\Stable-diffusion에 넣으면 부팅 후 화면 상단 "Stable Diffusion checkpoint"에서 전환이 가능합니다.

### webui-user.bat 실행

C:\\stable-diffusion-webui 폴더의 webui-user.bat 파일을 실행합니다.

「윈도우에 의해서 PC가 보호되었습니다」가 나올 수 있습니다. 이것은 마이너한 파일의 실행시에 위험성이 없는지의 확인을 하는 것으로, 바이러스등이 검지된 것은 아닙니다.

실행하고 싶기 때문에 「상세 정보」를 누른 후 「실행」을 누릅니다.

![](https://blog.kakaocdn.net/dn/BTFz5/btr3lDHb8ZN/k7AaIgHvsYSkyLGpwlARh0/img.png)

명령 프롬프트가 실행되고 Stable Diffusion 본체 등 필요한 파일이 다운로드되므로 끝날 때까지 방치하고 기다립니다.

### WEB UI의 기동과 종료

![](https://blog.kakaocdn.net/dn/cJv25O/btr3cIDgSM2/fK1aZxkkK8j810KJ7OvObk/img.png)

webui-user.bat 처리가 정상적으로 끝나면 웹서버 기능이 실행되고 명령 프롬프트에 "Running on local URL http:/127.0.0.1:7860"이라고 표시됩니다.

http:/127.0.0.1:7860에 접속하면 Stable Diffusion Web UI가 실행됩니다.

이때 명령 프롬프트는 닫지 마십시오.닫으면 서버도 종료되어 처리가 되지 않습니다.

Stable Diffusion Web UI를 종료할 때 브라우저와 명령 프롬프트를 닫습니다.

### 언인스톨

stable-diffusion-webui 폴더를 삭제하면 됩니다.

## Git에서 설치한 경우 업데이트 방법

![](https://blog.kakaocdn.net/dn/diQ8DL/btr3eX7nZoZ/NbIgi43ibGOlFcjE3K7WzK/img.png)

stable-diffusion-webui 폴더를 우클릭한 후 "Git Bash Here"를 클릭합니다.

![](https://blog.kakaocdn.net/dn/ma0OG/btr3bZSU8eG/pHbqtdmXU1M3CnyGFaLfG0/img.png)

이런 화면이 나오기 때문에 '**git pull'** 이라고 쳐서 실행을 합니다.

**Git Bash Here가 없는 경우**

Git Bash Here 명령이 없을 경우 Git 설치를 다시 실행하고 화면 하단의 Only show newoptions 체크를 제거하고 Git Bash Here를 추가 설치하십시오.

## Stable Diffusion Web UI 동작 테스트

기본적인 Stable Diffusion 사용법을 통해 동작을 확인해 보세요.

![](https://blog.kakaocdn.net/dn/0v3ET/btr3iJAUVnm/E4wgBPgbv95Jg3hxUw5wg1/img.png)

### txt2img (텍스트에서 이미지 생성)

버전에 따라 기능 위치가 다를 수 있습니다. 일단 위 8개 항목을 입력하면 될 것 같습니다.

#### ① Stable Diffusion checkpoint를 지정

DL한 모델 파일(ckpt)을 선택합니다.

#### ② Prompt (지시문)

어떤 이미지를 내고 싶은지 영어로 지정합니다. 특별히 강조하고 싶다면 괄호로 묶으시면 됩니다.

예： (((masterpiece)))

Stable Diffusion에서 생성된 이미지와 Prompt를 볼 수 있는 [Lexica](https://lexica.art/)라는 사이트에서는 출력 이미지의 prompt를 볼 수 있으므로 마음에 드는 것을 복사하여 시도해 보면 재미있습니다.

[

Lexica

The Stable Diffusion search engine

lexica.art



](https://lexica.art/)![](https://scrap.kakaocdn.net/dn/3Cewu/hyRTO7gLv8/UiMUXov1THK5GY1hAUK960/img.png?width=1200&height=627&face=0_0_1200_627,https://scrap.kakaocdn.net/dn/g0RJJ/hyRTKcLsjB/X5EwN1nSD6YoSdPQnpIxxk/img.png?width=1200&height=627&face=0_0_1200_627)

#### ③ Nevative Prompt(부정적 지시문) ※입력 임의

출력 이미지에서 제거하고 싶은 것, 나오면 싫은 요소를 영어로 지정합니다. 예를 들어 성 - 적인 요소가 나오지 않았으면 하는 경우 등은 n - s - f - w 와 같은 텍스트를 넣습니다. 이것은 대시를 제거하고 붙여서 넣어야 합니다.

#### ④ Sampling Steps

정밀도입니다. 높은 편이 예쁘지만 출력이 느려집니다.

#### ⑤ Sampling method

이미지 샘플링 방식입니다.여러가지 시도해보세요.

#### ⑥ Width, Height (출력하는 폭, 높이의 px)

출력할 이미지의 폭과 높이입니다.이것은 이용하는 모델에 따라 적절한 값이 다릅니다.기본은 512x512px이고 폭이나 높이를 바꾸면 같은 요소가 반복적으로 나올 수 있습니다.

#### ⑦ Batch Count(몇 번 낼지), Batch Size(한 번에 몇 장 낼지)

출력할 이미지 수는 Batch Count와 Batch Size로 결정됩니다.

총 출력 매수 = Batch Size (한 번에 몇 장 낼지) x Batch Count (몇 번 낼지)

Batch Count는 한 번의 Generate로 몇 연속으로 이미지를 내느냐입니다. 연속으로 찍어내는 듯한 이미지로 VRAM에 영향을 주지 않습니다. 많이 내고 싶을 때는 기본적으로 이쪽을 늘립시다.

Batch Size는 1회 처리에서 동시에 내는 매수로, 많이 하면 그래픽 보드의 VRAM을 넘어 오류가 날 수 있습니다. 출력하는 해상도와 수행하는 처리, VRAM의 여유 공간 등에 따라 어디까지 갈 수 있는지는 다릅니다. 잘 모르는 사람은 1로 두세요.대용량 VRAM을 탑재하고 있는 분은 늘려 여러 장을 동시에 출력할 수 있어 시간이 짧아집니다.

#### ⑧ CFG Scale

값을 올릴수록 Prompt에 대해 충실한 그림을 출력하려고 하지만 '원래 그림의 감촉'은 손실됩니다. 올릴 경우에는 Sampling Steps도 같이 올리는 것이 파탄이 잘 나지 않습니다.

#### ⑨ Generate 버튼

설정을 바탕으로 이미지를 출력합니다.

그 외 다양한 기능이 있습니다만, 본 글은 초보자를 위한 것으로 할애합니다.

## RTX 40시리즈 이용 시에는 cuDNN을 '교체'하는 편이 빨라질 수도

Table Diffusion Web UI에서는 webui.bat의 처리 중 Python의 가상 환경 구축을 자동으로 수행해 주는데, 그 중 PyTorch나 cuDN의 설치도 이루어지고 있다고 생각됩니다.

단, RTX 4090/4080 등 RTX 40시리즈 그래픽 보드를 이용하고 있는 경우, Stable Diffusion Web UI에서 설치되는 cuDNN이 오래되어 성능을 살리지 못하는 경우가 있는 것 같습니다.

cuDN을 교체할 경우 [NVIDIA 사이트](https://developer.nvidia.com/rdp/cudnn-download)에서 cuDN을 DL합니다.다운로드에는 NVIDIA 계정이 필요합니다.

![](https://blog.kakaocdn.net/dn/drjyY3/btr3iIWjmIh/Fp8x1gBGqELg5Bj8xLyK3k/img.png)

최신 cuDN11.x를 DL합니다.

치환 파일  
DL한 cuDN의 zip 파일을 압축 해제하고 bin 폴더 내에 있는 아래 파일을 C:\\stable-diffusion-web-ui\\venv\\Lib\\site-packages\\torch\\lib에 덮어씁니다.

-   cudnn\_adv\_infer64\_8.dll
-   cudnn\_adv\_train64\_8.dll
-   cudnn\_cnn\_infer64\_8.dll
-   cudnn\_cnn\_infer64\_8.dll
-   cudnn\_cnn\_train64\_8.dll
-   cudnn\_ops\_infer64\_8.dll
-   cudnn64\_8.dll

만약을 위해 덮어쓰기 전의 상기 파일을 백업해 두는 것이 좋습니다.

### cuDN 교체의 효과 예

i7-13700F와 RTX 4070 Ti로 16장의 512x512px 파일을 상당히 무거운 설정으로 출력했을 때 소요 시간입니다.  압도적으로 빨라지고 있네요.

prompt : photograph, forest, morning, canon

DDIM,150steps,512x512, Batch count 16, CFG 30, seed 2398368750

-   RTX407012GB(WebUI+cuDN교체) / **247초**
-   RTX 4070 12GB(WebUI 넣은 직후) / **392초**

## Stable Diffusion 동작에 추천하는 PC

Stable Diffusion을 위해 PC를 구매하려는 분들을 위한 세 가지 포인트가 있습니다.

-   NVIDIA 그래픽 보드(GeForce 등)가 장착되어 있어야 합니다.
-   VRAM의 양이 많을수록 출력할 수 있는 해상도 한계가 높아집니다(12GB 이상이 바람직함).
-   그래픽 보드의 사양이 높을수록 출력이 빨라집니다.

이런 점에서 '게이밍 PC', '크리에이터용 PC'라고 불리는 PC는 호환이 됩니다. 이상 초 간단 SD 윈도우 설치방법 속도 높이는법 소개였습니다.