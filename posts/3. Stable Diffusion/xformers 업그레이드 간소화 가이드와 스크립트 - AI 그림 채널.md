---
page-title: "xformers 업그레이드 간소화 가이드와 스크립트 - AI 그림 채널"
url: https://arca.live/b/aiart/71885593
date: "2023-04-25 19:30:33"
---
트러블슈팅 차 남김.

이미지는 참고자료에서 돋거해옴

참고자료 :

[https://arca.live/b/aiartreal/71609267](https://arca.live/b/aiartreal/71609267)

[https://arca.live/b/aiart/71559091](https://arca.live/b/aiart/71559091)

[https://arca.live/b/aiart/71319713](https://arca.live/b/aiart/71319713)

**\*주의\***

드림부스 익스텐션이 torch 버전을 강제로 돌리는 이슈를 확인 함.

해당 익스텐션을 쓰지 않는다면, 삭제 할 것.  
설치폴더\\extensions\\sd\_dreambooth\_extension

빼고도 계속 롤백이 된다면 파워쉘로 가상 환경 진입 후,

requirements 처리 될 때마다

pip list | select-string -pattern torch

로 버전 확인하고, 어떤 익스텐션이 영향을 줬는지 체크 할 것.

1\. 사전준비

1.  설치폴더에 가상 환경 폴더가 있다면 지운다.  
    보통 venv로 시작하는 폴더다.
2.  설치폴더\\webui-user.bat를 다음 내용으로 덮어쓴 뒤 실행 후 종료  
    이렇게 하야 나중에 torch를 다시 설치 할 일이 없긴 하다.  
    [@echo](https://arca.live/u/@echo) off  
    set PYTHON=  
    set GIT=  
    set VENV\_DIR=  
    set COMMANDLINE\_ARGS=**\--xformers**  
    set TORCH\_COMMAND=**pip install --pre torch torchvision torchaudio --index-url** [**https://download.pytorch.org/whl/nightly/cu118**](https://oo.pe/https://download.pytorch.org/whl/nightly/cu118 "download.pytorch.org/whl/nightly/cu118 (외부 사이트)")
    
    call webui.bat
    

4.  [CUDA Toolkit 11.8](https://oo.pe/https://developer.nvidia.com/cuda-11-8-0-download-archive "developer.nvidia.com/cuda-11-8-0-download-archive (외부 사이트)")  
    [![](https://ac-p1.namu.la/20230315sac/c2e23ca6f3fc29aff0846371855f6619ebad35da9895186cfe9e7f6abb32180e.png?expires=1682420913&key=kIS3FYtAn6vBAj2ZbWRk9Q)](https://ac-p1.namu.la/20230315sac/c2e23ca6f3fc29aff0846371855f6619ebad35da9895186cfe9e7f6abb32180e.png?expires=1682420913&key=kIS3FYtAn6vBAj2ZbWRk9Q&type=orig)
5.  C++ 빌드 도구
    1.  VS가 설치되어있지 않다면  
        [MSVC v143 - VS 2022 C++ x64/x86 build tools](https://oo.pe/https://visualstudio.microsoft.com/ko/vs/ "visualstudio.microsoft.com/ko/vs/ (외부 사이트)")  
        [![](https://ac-p1.namu.la/20230315sac/33d21c2600411e0653c09c41b6fa78be62f826d3af86c19a38bca0952f6e2880.png?expires=1682420913&key=jPQ963bmKCWCfVtVRTmqqg)](https://ac-p1.namu.la/20230315sac/33d21c2600411e0653c09c41b6fa78be62f826d3af86c19a38bca0952f6e2880.png?expires=1682420913&key=jPQ963bmKCWCfVtVRTmqqg&type=orig)  
        
    2.  VS가 설치되어있다면[![](https://ac-p1.namu.la/20230315sac/eb9ba306adce072cca5f922b7d38147d62227486a4a7c461bfcd3d14e9ee542e.png?expires=1682420913&key=IzkFolmxCEQBB6dOXMSK5g)](https://ac-p1.namu.la/20230315sac/eb9ba306adce072cca5f922b7d38147d62227486a4a7c461bfcd3d14e9ee542e.png?expires=1682420913&key=IzkFolmxCEQBB6dOXMSK5g&type=orig)
6.  [cuDNN 최신 버전](https://oo.pe/https://developer.nvidia.com/rdp/cudnn-download "developer.nvidia.com/rdp/cudnn-download (외부 사이트)")  
    (cuda11. cudnn-windows-x86\_64-x.x.x.x\_**cuda11**\-archive)을 받아 bin 폴더의 dll을 (webui 설치폴더)\\venv\\Lib\\site-packages\\torch\\lib 에 덮어씌우기

설치  
1\. **powershell**을 관리자 권한으로 실행

2\. sd 설치 폴더로 이동

3\. venv\\Scripts\\activate 입력하여 가상 환경 진입
- ==D:\stable-diffusion-webui\venv\Scripts\activate.bat==
	- D:\stable-diffusion-webui\venv\Scripts\activate.bat

4\. 진입했으면 아래 명령어를 그대로 복사 하여 붙여넣는다.  
CMD 아니고 **powershell**이다.

그리고 그래픽카드에 따라 TORCH\_CUDA\_ARCH\_LIST을 다르게 줘야 한다고 하길래 추가했다.

자신의 그래픽카드가 4천번대라면 4번째 줄의 첫번째 #을 지우면 된다.

> write-host "xformers comfiler"
> 
> & set NVCC\_FLAGS="-allow-unsupported-compiler"
> 
> & set TORCH\_CUDA\_ARCH\_LIST=8.6  #3000번대#
> 
> #& set TORCH\_CUDA\_ARCH\_LIST=8.9  #4000번대#
> 
> & pip uninstall xformers --yes
> 
> & pip install ninja setuptools wheel
> 
> & pip install torch torchvision torchaudio --extra-index-url [https://download.pytorch.org/whl/cu118](https://oo.pe/https://download.pytorch.org/whl/cu118 "download.pytorch.org/whl/cu118 (외부 사이트)")
> 
> & cd .\\repositories\\
> 
> & rd .\\xformers -force -recurse
> 
> & git clone [https://github.com/facebookresearch/xformers.git](https://oo.pe/https://github.com/facebookresearch/xformers.git "github.com/facebookresearch/xformers.git (외부 사이트)") --recurse-submodules
> 
> & cd .\\xformers\\
> 
> & pip list | select-string -pattern torch
> 
> & python [setup.py](https://oo.pe/http://setup.py "setup.py/ (외부 사이트)") build
> 
> & python [setup.py](https://oo.pe/http://setup.py "setup.py/ (외부 사이트)") bdist\_wheel
> 
> & cd .\\dist\\
> 
> & pip install

[![](https://ac-p1.namu.la/20230315sac/91496536e5612f0506bd61d5643e790f137d4af21eb00e345d8c88fadf2b29ec.png?expires=1682420913&key=1hFO3jgmlo-7qwSDIfNMOQ)](https://ac-p1.namu.la/20230315sac/91496536e5612f0506bd61d5643e790f137d4af21eb00e345d8c88fadf2b29ec.png?expires=1682420913&key=1hFO3jgmlo-7qwSDIfNMOQ&type=orig)

pip install까지 정상적으로 실행이 되었다면 탭키 누르고 엔터

중간에 멈췄다면 에러 확인 할 것.

ps. 파워쉘을 관리자로 실행 하는 이유 : 앱체크가 빌드를 방해해서

ps2. 나만 빌드 30분 넘게 걸리나..? 7950x인데..?

ps3. 나만 토치가 1.13.1로 계속 롤백 되는건가.. 왜지..

\>> 설치한 익스텐션의 requirements.txt에서 torch의 특정 버전을 요구하는지 확인. 필요 없는 익스텐션이라면 비활성화