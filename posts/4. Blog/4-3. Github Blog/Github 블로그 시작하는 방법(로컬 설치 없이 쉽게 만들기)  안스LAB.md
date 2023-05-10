---
page-title: "Github 블로그 시작하는 방법(로컬 설치 없이 쉽게 만들기) | 안스LAB"
url: https://ahnslab.com/21-how-to-start-github-blog/
date: "2023-04-20 15:23:14"
---
카테고리: [Github블로그](https://ahnslab.com/category/github-page), 작성: 2021-12-02

github블로그를 가장 간단하게 시작하는 방법입니다. 로컬에 ruby, git 등 설치 없이도 github 블로그를 시작할 수 있습니다.

## Table of contents

-   [1\. Github이란?](https://ahnslab.com/21-how-to-start-github-blog/#1-github%EC%9D%B4%EB%9E%80)
-   [2\. Github 가입하기](https://ahnslab.com/21-how-to-start-github-blog/#2-github-%EA%B0%80%EC%9E%85%ED%95%98%EA%B8%B0)
-   [3\. 테마 선택하고 복사해오기](https://ahnslab.com/21-how-to-start-github-blog/#3-%ED%85%8C%EB%A7%88-%EC%84%A0%ED%83%9D%ED%95%98%EA%B3%A0-%EB%B3%B5%EC%82%AC%ED%95%B4%EC%98%A4%EA%B8%B0)
-   [4\. 블로그 배포하기, URL 정하기](https://ahnslab.com/21-how-to-start-github-blog/#4-%EB%B8%94%EB%A1%9C%EA%B7%B8-%EB%B0%B0%ED%8F%AC%ED%95%98%EA%B8%B0-url-%EC%A0%95%ED%95%98%EA%B8%B0)
-   [5\. 기본정보 수정하기 (config.yml)](https://ahnslab.com/21-how-to-start-github-blog/#5-%EA%B8%B0%EB%B3%B8%EC%A0%95%EB%B3%B4-%EC%88%98%EC%A0%95%ED%95%98%EA%B8%B0-configyml)
-   [6\. 포스팅 해보기](https://ahnslab.com/21-how-to-start-github-blog/#6-%ED%8F%AC%EC%8A%A4%ED%8C%85-%ED%95%B4%EB%B3%B4%EA%B8%B0)
-   [7\. 마무리](https://ahnslab.com/21-how-to-start-github-blog/#7-%EB%A7%88%EB%AC%B4%EB%A6%AC)

---

많은 분들이 블로그(또는 사이트)를 만들기 위해 Github 페이지를 사용합니다. 특히 개발자 분들이 많이 사용하곤 하는데요. Github 페이지는 원래는 소프트웨어의 프로그램 개발 코드를 저장하고 관리하기 위한 플랫폼이지만, 사이트를 만들고 운영할 수 있는 플랫폼으로도 제공됩니다.

개발자가 아닐 경우, Github, Git 이라는 용어 등이 낯설고 그 과정도 복잡하게 느껴지고, 어렵게 느껴지기 때문에 Github으로 블로그를 시작하기 어려울 수도 있지만, 최대한 쉬운 방법으로 한번 설명을 드려보려고 합니다. (※ 지금 보시는 블로그도 Github 페이지를 통해 만들어진 블로그입니다.)

## [](https://ahnslab.com/21-how-to-start-github-blog/#1-github%EC%9D%B4%EB%9E%80)1\. Github이란?

개발, 코딩을 하시는 분들은 github을 다 알고 계신데요. 아닌 분들을 위해 간단하게 설명을 해드려보면, Github 은 소프트웨어 개발에 사용되는 코드를 저장하고, 관리하는 온라인 상의 공간이라고 볼 수 있습니다. 프로그램 코드의 수정, 반영, 취소, 복구, 배포 등 여러가지 기능을 가지고 있습니다.

우리가 블로그 생성에 사용할 Github 페이지([Github Page](https://pages.github.com/))는, Github 플랫폼을 이용해, 웹사이트 또는 블로그 등을 만들고, 실제로 온라인상에서 서비스할 수도 있도록 도와줍니다.

## [](https://ahnslab.com/21-how-to-start-github-blog/#2-github-%EA%B0%80%EC%9E%85%ED%95%98%EA%B8%B0)2\. Github 가입하기

이 화면은 Github 에 접속하면 보이는 첫 화면입니다.

![github 홈](https://ahnslab.com/assets/images/posts/21/github_blog_new_000.jpg)

github 홈

먼저, github 사이트에 접속합니다.  
Username과 Email 을 입력하여 가입합니다. username은 추후 변경도 가능합니다.

![github 가입하기](https://ahnslab.com/assets/images/posts/21/github_blog_new_0001.jpg)

github 가입하기

과정을 마치면, 계정이 생성됩니다. 로그인 후, 본인의 프로필 홈 주소로 들어갑니다. github.com/{username}  
이 상태에서, repository 라는 프로그램 코드 저장소를 만들어, 코드를 업로드 하고, 관리할 수 있습니다.

![github 가입 후 홈](https://ahnslab.com/assets/images/posts/21/github_blog_new_0002.jpg)

github 가입 후 홈

위의 화면처럼 보이시나요?  
현재는, repository(저장소)가 하나도 없는 상태입니다.  
이제 블로그를 생성하면 됩니다. 아래에서 계속 보겠습니다.

## [](https://ahnslab.com/21-how-to-start-github-blog/#3-%ED%85%8C%EB%A7%88-%EC%84%A0%ED%83%9D%ED%95%98%EA%B3%A0-%EB%B3%B5%EC%82%AC%ED%95%B4%EC%98%A4%EA%B8%B0)3\. 테마 선택하고 복사해오기

※ 지금 사용하는 방식은 특정 테마에서 간혹 동작하지 않을 수도 있습니다. 아래의 확인된 테마를 사용하여 블로그 생성을 연습해보고, 추후 다른 테마들에도 적용해보시기 권해드립니다.

우리는 ‘jekyll’이라는 사이트 생성 엔진을 사용하게 됩니다. 그러기 위해 jekyll 테마를 먼저 선택을 해야 하는 거구요. 아래의 사이트들이 있는데, 한번 살펴보도록 하겠습니다.

-   [https://jekyllthemes.io](https://jekyllthemes.io/)
-   [http://jekyllthemes.org](http://jekyllthemes.org/)

여기서 사용해볼 테마는 ‘now jekyll theme’ 입니다.

-   [https://jekyllthemes.io/theme/jekyll-now](https://jekyllthemes.io/theme/jekyll-now)

무료이고, 가장 간단한 UI를 가지고 있어서, 선택을 해보았습니다.

테마가 어떤 모습인지는 아래의 데모 페이지를 확인하시면 됩니다.

-   [http://www.jekyllnow.com/](http://www.jekyllnow.com/)

다음으로는, (1) 공개된 테마의 코드를 나의 저장소(repository)로 복사해온 뒤, (2) 기본설정 파일을 나에게 맞도록 수정하여 사이트를 배포하는 과정이 있습니다.

먼저, 우리가 선택한 테마의 코드 저장소로 이동합니다.  
[https://github.com/barryclark/jekyll-now](https://github.com/barryclark/jekyll-now)

이동을 하면 아래와 같이 저장소 화면이 보이는데요. 여기서 우측 상단 ‘fork’ 버튼을 선택합니다.

![fork code](https://ahnslab.com/assets/images/posts/21/github_blog_new_001.jpg)

fork code

복사(fork)가 진행이되고 완료되면, 우리가 선택한 블로그 테마의 코드가 자신의 저장소로 복제가 됩니다. 다시 처음에 만든 Github의 홈화면으로 가보면, repositories 탭에 코드저장소가 하나 생성이 된 걸 볼 수 있습니다.

![fork code](https://ahnslab.com/assets/images/posts/21/github_blog_new_002.jpg)

fork code

## [](https://ahnslab.com/21-how-to-start-github-blog/#4-%EB%B8%94%EB%A1%9C%EA%B7%B8-%EB%B0%B0%ED%8F%AC%ED%95%98%EA%B8%B0-url-%EC%A0%95%ED%95%98%EA%B8%B0)4\. 블로그 배포하기, URL 정하기

이제 우리가 복사해 온 코드에 우리가 사용할 사이트의 정보 등을 입력해야 합니다. 먼저, 저장소의 이름을 변경해야 합니다.

![rename repository](https://ahnslab.com/assets/images/posts/21/github_blog_new_004.jpg)

rename repository

이 저장소의 이름은, 우리가 사용할 블로그의 주소와 관련이 있습니다. 보통 github 블로그를 운영하면 ~~~.github.io 처럼 블로그 주소를 가져가는 경우가 많은데, 이를 위해서는 저장소 이름을 맞게 세팅해주어야 합니다.

-   repository name 이 ‘abc’ 인 경우, 블로그 주소는  
    **https://계정아이디.github.io/abc**
-   repository name 이 ‘계정아이디.github.io’ 인 경우, 블로그 주소는  
    **https://계정아이디.github.io**

예제의 경우에서는, github에 가입한 아이디가 ‘ahnslog’입니다. 그리고 repository 이름은 ‘ahnslog.github.io’로 하였습니다. 이럴 경우, 최종 블로그 주소는 ‘https://ahnslog.github.io’가 됩니다. 하지만, repository 이름을 다르게 지정할 경우에는 https://ahnslog.github.io/{repository name} 이 되겠죠.

여기까지 완료하면, 블로그의 생성이 완료가 된 것입니다. 아래처럼 주소를 쳐서 들어가보면 블로그가 나와야 정상입니다.

![github blog 생성 모습](https://ahnslab.com/assets/images/posts/21/github_blog_new_005.jpg)

github blog 생성 모습

## [](https://ahnslab.com/21-how-to-start-github-blog/#5-%EA%B8%B0%EB%B3%B8%EC%A0%95%EB%B3%B4-%EC%88%98%EC%A0%95%ED%95%98%EA%B8%B0-configyml)5\. 기본정보 수정하기 (config.yml)

이제 블로그의 제목 등 기본정보를 수정합니다. 이미 블로그는 온라인상에 공개 배포가 되어 있는 상태이지만, 내용이 복사해온 테마의 내용 그대로이기 떄문에 설정값 등을 바꿔주어야 합니다.

설정을 바꾸기 위해서는, 우리 저장소에 올라가 있는 코드를 수정해줘야 하는데요. 코드의 수정은 보통 로컬 PC 상에서 코드를 내려받고 수정하는 작업이 일반적입니다.(프로그램 개발의 경우) 하지만, 이 과정이 처음 하는 분들에게 조금은 어려울 수 있기 때문에, 로컬이 아닌 github 사이트에서 직접 수정을 해보도록 하겠습니다.

내 github 홈의 repository 화면에서, Code 탭을 선택해보겠습니다. 아래의 화면처럼, 내 사이트를 이루는 여러 코드파일을 볼 수 있습니다. 파일을 하나 선택해보면, 그 파일을 실제로 수정할 수 있습니다.

![repository code](https://ahnslab.com/assets/images/posts/21/github_blog_new_006.jpg)

repository code

jekyll github 블로그의 세팅정보는 \_config.yml 이라는 파일에 기록됩니다. 아래는 \_config.yml 을 선택하여 수정모드로 진입한 상태입니다.

처음 수정해볼 부분은 사이트의 네임입니다. 코드의 name: 이라고 되어 있는 부분을 찾아서, 다른 이름으로 변경을 해봅니다.

![repository code](https://ahnslab.com/assets/images/posts/21/github_blog_new_010.jpg)

repository code

모두 수정한 뒤, 아래로 스크롤을 내리면, ‘Commit changes’라는 버튼을 볼 수 있는데, 이 버튼이 수정내용을 저장하는 버튼입니다. Commit 이라는 용어입니다.

![repository code](https://ahnslab.com/assets/images/posts/21/github_blog_new_011.jpg)

repository code

저장(커밋)을 완료 하고 잠시 후(몇분이 걸릴 수도 있습니다.), 실제 사이트에 다시 접속해보면, 블로그의 이름이 바뀐 것을 볼 수 있습니다.

![repository code](https://ahnslab.com/assets/images/posts/21/github_blog_new_012.jpg)

repository code

## [](https://ahnslab.com/21-how-to-start-github-blog/#6-%ED%8F%AC%EC%8A%A4%ED%8C%85-%ED%95%B4%EB%B3%B4%EA%B8%B0)6\. 포스팅 해보기

블로그의 기초설정은 위에서처럼 \_config.yml을 수정하는 것이고, 수정 방식은 github.com 사이트에서 직접 repository의 파일을 수정하는 것이었습니다. 그럼 포스팅도 한번 간단히 해보겠습니다.

포스팅은 \_posts 디렉토리에 파일을 만드는 것으로 진행이 됩니다. 아래처럼 \_posts 경로에 들어가보면, 현재 2014-3-3-Hello-World.md 라는 파일이 샘플로 이미 만들어져 있고, 파일을 선택하면 내용을 볼 수 있습니다.

![포스팅 파일](https://ahnslab.com/assets/images/posts/21/github_blog_new_017.jpg)

포스팅 파일

우측의 “<>” 모양을 선택하면, 파일의 실제 내용을 볼 수 있는데요. 이 파일이 작성된 형식을 마크다운이라고 합니다. 파일의 확장자도 md로 되어 있습니다. 이렇게 github page 에서는 \_posts 하위에 날짜-파일이름.md 라는 형식으로 파일을 생성하면, 포스팅으로 인식을 하게 됩니다.

![포스팅 파일](https://ahnslab.com/assets/images/posts/21/github_blog_new_018.jpg)

포스팅 파일

간단히 내용을 살펴보면, 아래와 같이 되어있는데요. 첫 부분의 —와 — 사이는 메타정보가 됩니다. 포스팅 페이지의 제목, 레이아웃, 날짜, 발행여부 등의 정보가 들어가게 됩니다.

메타정보 이후부터가 실제 포스팅의 내용이라고 보시면 되는데, 마크다운 양식에 맞게 작성을 하시면 됩니다. # 는 H1, ## 는 H2 는 a 링크, 처럼 특정 키워드와 내용을 함께 작성하게 됩니다. 마크다운의 자세한 양식은 다른 포스팅에서 정리를 해보도록 하겠습니다.

```
---
layout: post
title: You're up and running!
---

Next you can update your site name, avatar and other options using the _config.yml file in the root of your repository (shown below).

![_config.yml](/images/config.png)

The easiest way to make your first post is to edit this one. Go into /_posts/ and update the Hello World markdown file. For more instructions head over to the [Jekyll Now repository](https://github.com/barryclark/jekyll-now) on GitHub.
```

이렇게 작성된 파일은 최종적으로 블로그의 포스팅 하나로 등록이 되는 것입니다.

![포스팅 화면](https://ahnslab.com/assets/images/posts/21/github_blog_new_019.jpg)

포스팅 화면

## [](https://ahnslab.com/21-how-to-start-github-blog/#7-%EB%A7%88%EB%AC%B4%EB%A6%AC)7\. 마무리

위 과정을 통해, 처음으로 Github 에 가입을 하고, 저장소(repository)를 만들고 테마를 복사(fork)해 와서, 블로그를 웹 상에 배포, 공개하는 과정을 알아보았습니다.

앞으로 블로그에 글을 쓰고, 사이트의 모양을 수정하고, 꾸미는 방식도 위의 과정에서 크게 벗어나지 않습니다.

다만, 글을 쓰는 방식이 일반 네이버블로그나 티스토리 등과 조금 다르고, 사이트의 모양 등을 수정하기 위해서는 html, css, javascript 등의 이해와, jekyll 이라는 블로그 엔진이 돌아가는 방식 등을 이해하여야 합니다.

다음 포스팅에서는, 블로그 글을 작성하고, 지우고, 사이트를 꾸미는 등의 방법에 대해 계속하여 다뤄보도록 하겠습니다.

---