---
page-title: "워드프레스 Elementor 플러그인 사용방법: 페이지 제작 시작하기 | 스위프트코딩"
url: https://swiftcoding.org/getting-started-with-elementor
date: "2023-04-15 21:41:06"
---
#워드프레스

워드프레스에는 ‘페이지(page)’라는 포스트 타입이 있고, [Elementor 페이지빌더 플러그인](https://swiftcoding.org/elementor)은 그 페이지를 코딩없이 마우스 클릭, 드래그 드랍으로 쉽게 디자인할 수 있도록 해주는 일종의 디자인 프로그램입니다. 

> Elementor 작업흐름
> 	 워드프레스 페이지를 만들어놓고, 
> 	 Elementor로 편집

Elementor 플러그인 사용방법 강좌글의 시작으로 이번 포스팅에서는 전체적인 흐름을 살펴보기위해 페이지를 만들고, Elementor 편집화면에서 간단히 엘리먼트 위젯을 추가한뒤 저장, 페이지를 발행하는 방법을 알아보겠습니다.

-   [워드프레스 페이지 생성하기](https://swiftcoding.org/getting-started-with-elementor#creating-a-page)
    -   페이지 템플릿 선택하기
    -   페이지 임시 저장 
-   [Elementor 편집화면의 구성](https://swiftcoding.org/getting-started-with-elementor#editing-screen)
-   [Elementor 디자인 구성요소 위젯 추가하기](https://swiftcoding.org/getting-started-with-elementor#adding-widgets)
-   [페이지 저장 & 공개하기](https://swiftcoding.org/getting-started-with-elementor#save)
    -   페이지 미리보기
-   [Elementor 종료하기](https://swiftcoding.org/getting-started-with-elementor#exit)

더 상세한 Elementor 매뉴얼은 차차 추가 작성할 예정인데 무료버전인 Elementor와 유료버전인 Elementor Pro에 대한 사용법 강좌를 모두 작성할 예정입니다. 다운로드 방법은 아래 링크를 참고하시기 바랍니다.

-   [Elementor Pro (무료,유료 버전) 구매 방법 및 라이센스 정보](https://swiftcoding.org/elementor)

## 워드프레스 페이지 생성하기

워드프레스에서 새로운 페이지를 곧바로 만들기 위해서는 사이트 어디서든지 화면 위에 위치한 **관리자 메뉴바** > **\+ 새로 추가** > **페이지**를 클릭하거나:

[![로그인 후 화면 위에 나타나는 관리자 메뉴바](https://swiftcoding.org/wp-content/uploads/2018/11/creating-a-wordpress-page-with-elementor-on-admin-bar.png)](https://swiftcoding.org/wp-content/uploads/2018/11/creating-a-wordpress-page-with-elementor-on-admin-bar.png)

워프드레스 **관리자 화면**\> **페이지** > **모든 페이지 > 새 페이지 추가** 메뉴로 곧바로 페이지 생성을 시작할 수 있긴 하지만, 저는 **모든 페이지** 목록에서 설명을 시작하려고 합니다.

[![모든 페이지 목록 화면](https://swiftcoding.org/wp-content/uploads/2018/11/creating-wp-page-on-all-page-menu.png)](https://swiftcoding.org/wp-content/uploads/2018/11/creating-wp-page-on-all-page-menu.png)

> 이곳에 보면 자신이 만든 페이지와 유료테마등이 만들어둔 페이지라거나 모든 페이지 목록을 볼 수 있습니다. 
> 이곳에서 설명을 시작하는 이유는 
> 	이 글을 쓰는 현시점 워드프레스에서 사용할 수 있는 ==두 개의 워드프레스 편집기 때문==입니다.

-   고전 편집기
-   [구텐베르크 편집기](https://swiftcoding.org/new-wp-editor-revew)

워드프레스 4.9.8 버전 이후 부터는 새로운 글쓰기 에디터인 [**구텐베르크**](https://swiftcoding.org/new-wp-editor-revew)가 나왔고 플러그인 형태로 고전 편집기와 구텐 베르크 둘 다 동시에 활성화 해서 바꿔 가며 쓸 수 있는데요. 그런 경우 페이지를 만들 때도 그때 그때 편집기를 선택해서 페이지를 만들 수 있습니다.

**모든 페이지** 화면 위에 있는 ‘**새 페이지 추가**‘ 옆에 [![](https://swiftcoding.org/wp-content/uploads/2018/11/reversed-triangle.png)](https://swiftcoding.org/wp-content/uploads/2018/11/reversed-triangle.png)역삼각형 버튼을 눌러 보면 아래처럼 나오게 됩니다. 

[![3가지 선택사항: Elementor, Gutenberg, 구버전 편집기 ](https://swiftcoding.org/wp-content/uploads/2018/11/choices-for-editors-to-create-a-page.png)](https://swiftcoding.org/wp-content/uploads/2018/11/choices-for-editors-to-create-a-page.png)

참고로 고전 편집기만 사용한다면 역삼각형 버튼이 나오지 않습니다. 그냥 곧바로 ‘새 페이지 추가’를 눌러 페이지를 생성하면 됩니다.

-   **Elementor** : 엘리멘터 페이지 빌더로 곧바로 시작
-   **Gutenberg**: 구텐베르크 편집기로 페이지 만들기
-   **구 버전 편집기**: 구 버전(클래식) 편집기로 페이지 만들기

이 중에 **Elementor** 로 곧바로 시작하면 페이지 템플릿이 기본 템플릿으로(아래에 설명) 시작되고, 페이지 주소인 URL 슬러그(slug)끝이 https://example.com/**elementor-2849** 처럼 랜덤으로 시작된다는 걸 유의해야합니다. 물론 둘 모두 나중에 바꿀 수는 있습니다.

새 페이지 추가로 페이지를 추가하게 되면 아래처럼 워드프레스 글쓰기 편집기가 시작됩니다.

[![tinyMCE 에디터의 모습](https://swiftcoding.org/wp-content/uploads/2018/11/page-editing-screen-with-classic-editor.png)](https://swiftcoding.org/wp-content/uploads/2018/11/page-editing-screen-with-classic-editor.png)

고전 편집기의 페이지 편집화면

[![Gutenberg 에디터의 모습](https://swiftcoding.org/wp-content/uploads/2018/11/page-editing-screen-with-gutenberg-editor.png)](https://swiftcoding.org/wp-content/uploads/2018/11/page-editing-screen-with-gutenberg-editor.png)

구텐베르크에서의 페이지 편집화면

위 화면에서 [![edit with elementor button](https://swiftcoding.org/wp-content/uploads/2018/11/edit-with-elementor-button.png)](https://swiftcoding.org/wp-content/uploads/2018/11/edit-with-elementor-button.png)Edit with Elementor 버튼을 클릭하면 Elementor 페이지빌더를 시작하게 되는데요. 이 때 본문 내용은 페이지빌더로 디자인할 내용이니 비워둬야합니다.

> 페이지빌더로 페이지를 디자인하게 되면 
> 	1) 워드프레스 코어기능인 **단축코드**(숏코드)로 페이지의 본문을 채우고, 
> 	2) 보여줄땐 Elementor 페이지빌더가 단축코드들을 각각의 요소로 렌더링하게 됩니다. 
> 다른 페이지빌더도 방법은 같습니다.

### 페이지 템플릿 선택하기

그리고 페이지 편집화면 오른쪽 ‘**페이지 속성**‘  메타박스에서 페이지의 레이아웃을 결정하는 ‘**템플릿**‘을 선택 할 수 있는데요.

[![기본 템플릿이 선택되어있음](https://swiftcoding.org/wp-content/uploads/2018/11/choosing-wordpress-page-template.png)](https://swiftcoding.org/wp-content/uploads/2018/11/choosing-wordpress-page-template.png)

이것은 Elementor 안에서도 페이지 설정을 통해 바꿀 수 있습니다. 처음엔 **기본 템플릿**이 선택되어있을 텐데 이것은 워드프레스 테마가 제공하는 기본 페이지 템플릿으로 보통은 헤더, 푸터, 사이드바가 있는 유형일겁니다.  

템플릿을 펼쳐보면 **자신이 사용중이 테마가 지원하는 페이지 템플릿**과 **Elementor가 제공하는 페이지 템플릿**이 나옵니다. 제 경우 테마가 제공하는 **또 다른 페이지 빌더가 제공하는 템플릿** 목록도 나오네요.

[![자신의 워드프레스 페이지 템플릿 목록](https://swiftcoding.org/wp-content/uploads/2018/11/all-page-templates-in-my-wordpress.png)](https://swiftcoding.org/wp-content/uploads/2018/11/all-page-templates-in-my-wordpress.png)

이 중에서 Elementor 가 제공하는 템플릿은 2가지 입니다.

-   Elementor Canvas(캔버스)
-   Elementor Full Width(전체너비)

 **Elementor Canvas**는 헤더, 푸터, 사이드바 모두 없고 페이지 본문만 나타나는 페이지 템플릿으로 빈화면으로 시작하게되는데요. 보통은, 랜딩페이지같은 정적인 페이지를 만들 때 이런 빈 화면의 페이지 템플릿을 사용하게 됩니다.

**Elementor Full Width**는 헤더, 페이지 본문, 푸터가 존재하게 되며 사이드바는 나타나지 않습니다. 자신의 블로그 스타일(제목, 로고 이미지등)을 유지하면서 페이지를 만들고 싶을 때 사용하면 될겁니다.

[![헤더, 사이드바, 푸터가 모두 존재](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-the-look-of-default-template.png)](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-the-look-of-default-template.png)

기본템플릿 선택시 Elementor 디자인 편집화면

[![헤더, 푸터, 사이드바 모두 없는 빈화면](https://swiftcoding.org/wp-content/uploads/2018/11/the-look-of-elementor-canvas-template.png)](https://swiftcoding.org/wp-content/uploads/2018/11/the-look-of-elementor-canvas-template.png)

elementor canvas 선택시 편집화면

[![헤더와 푸터가 존재하는 템플릿](https://swiftcoding.org/wp-content/uploads/2018/11/the-look-of-elementor-full-width-template.png)](https://swiftcoding.org/wp-content/uploads/2018/11/the-look-of-elementor-full-width-template.png)

elementor full width 선택시 편집화면

 헤더, 푸터, 사이드바등은 자신이 사용하는 테마의 그 것이므로 사전에 자신이 사용하는 테마에서 설정이 되어있어야 제대로 나타나겠습니다.

### 페이지 임시 저장 

페이지 템플릿까지 선택했다면 해당 페이지를 바로 공개하기보다는 임시로 저장하거나 비공개로 먼저 저장하도록 합시다. 페이지 디자인 편집은 손이 많이 가는 일이기 때문에 이르게 공개할 필요 없습니다.

페이지 제목, 고유주소, 페이지 속성, 특성이미지등을 설정하고 ‘**임시 글로 저장**‘ 해준뒤, [![edit with elementor button](https://swiftcoding.org/wp-content/uploads/2018/11/edit-with-elementor-button.png)](https://swiftcoding.org/wp-content/uploads/2018/11/edit-with-elementor-button.png)Edit with Elementor 버튼을 클릭해 Elementor 페이지빌더 화면을 시작할 수 있습니다.

  
  

## Elementor 편집화면의 구성

보통 페이지빌더를 사용해 페이지를 만들고 싶은 때는 기존 블로그,웹사이트의 디자인과는 동떨어진 랜딩페이지 같은 전체 화면 페이지를 원할 것이므로 **Elementor Canvas 템플릿**을 사용할테고, 그러면 처음으로 마주치는 화면 구성이 아래와 같을 것입니다.

[![왼쪽 사이드브아네느 엘리먼트 위젯 패널이 있고 가운데에는 페이지 본문 편집영역](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-panels-overview-on-canvas-template.png)](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-panels-overview-on-canvas-template.png)

elementor 화면 구성

편집영역에서 볼 수 있는 Drag widget here 영역에는 엘리먼트 위젯을 끌어다 놓을 수 있는데요. 이 영역은 섹션이 될 영역으르써,  + 아이콘과 폴더모양 아이콘을 볼 수 있습니다.

[![더하기 모양 아이콘과 폴더모양 아이콘. ](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-drag-widget-here-area.png)](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-drag-widget-here-area.png)

위 화면처럼 Add New Section 버튼[![빨간색 큰원에 가운데 십자가모양 아이콘](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-button-add-new-section.png)](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-button-add-new-section.png)을 누르면 칼럼의 갯수와 형태를 지정해 해당 구조의 칼럼을 가진 섹션을 추가하는 것으로 시작할 수도 있습니다.

## Elementor 디자인 구성요소 위젯 추가하기

Elemmentor 에서 사용하면서 가장 큰 개념은 레이아웃요소인 **섹션**(row, 가로 행)과 **칼럼**(세로 열) 그리고 **위젯**으로 나눌 수 있습니다. 위젯을 추가하면 항상 이 3가지가 모두 함께 있는데요. 이에 대한 자세한 사항은 다음에 알아보도록 하고 이번엔 간단히 원하는 위젯을 추가해 페이지를 꾸며봅시다.

참고로 Elementor에서 얘기하는 **위젯**은 일반적으로 워드프레스에서 얘기하는 (사이드바에 넣는)위젯이 아닌 디자인 구성요소들을 말합니다. 위의 편집화면 구성에서 볼 수 있는 왼쪽에 엘리먼트 위젯 패널에 보이는 것들말이죠.

화면 왼쪽 패널위에 위치한[![네모난 점 9개가 큰 네모를 이루는 블락형태의 버튼](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-show-widgets.png)](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-show-widgets.png)모든 위젯 보기 버튼을 누른 뒤 원하는 위젯을 끌어다 Drag widget here 영역에 끌어다 놓으면 곧바로 해당 위젯이 추가됩니다.

[![텍스트 위젯을 편집화면에 끌어다 놓는 모습](https://swiftcoding.org/wp-content/uploads/2018/11/dragging-a-widget-in-Elementor.png)](https://swiftcoding.org/wp-content/uploads/2018/11/dragging-a-widget-in-Elementor.png)

위처럼  Add New Section 버튼[![빨간색 큰원에 가운데 십자가모양 아이콘](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-button-add-new-section.png)](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-button-add-new-section.png)을 사용하지 않고 Drag widget here 영역에 곧바로 위젯을 끌어다 놓으면 섹션안에 1 컬럼의 레이아웃을 가진 엘리먼트가 생성됩니다.

그러면 아래처럼 해당 위젯을 클릭해서 왼쪽 패널에 나타나는 속성값을 작성하면 오른쪽 편집화면에 곧바로 반영되어 나타나는 것을 볼 수 있습니다.

[![Title 위젯의 속성을 세팅하는 모습 ](https://swiftcoding.org/wp-content/uploads/2018/11/setting-the-attribues-of-title-widget-in-Elementor.png)](https://swiftcoding.org/wp-content/uploads/2018/11/setting-the-attribues-of-title-widget-in-Elementor.png)

위젯의 속성값은 왼쪽 패널 위쪽에 자리잡은 각각의 content [![Content 연필모양 아이콘](https://swiftcoding.org/wp-content/uploads/2018/11/Elementor-button-Content-attributes.png)](https://swiftcoding.org/wp-content/uploads/2018/11/Elementor-button-Content-attributes.png), style[![Style 반원 두개가 합쳐진 동그라미 아이콘](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-button-style-attributes.png)](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-button-style-attributes.png), advanced[![Advanced 기어모양 아이콘](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-button-Advanced-attributes.png)](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-button-Advanced-attributes.png)속성 편집용 탭버튼을 클릭해서 조정할 수 있습니다.

이런 엘리먼트 위젯별 속성편집을 통한 세세한 디자인은 별도의 글로 알아보기로 하고, 대략적인 모습을 파악하는 이번글에서는 대충 지정해보도록 합시다. 섹션을 하나 더 추가하기위해서 아래그림처럼 [![빨간색 큰원에 가운데 십자가모양 아이콘](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-button-add-new-section.png)](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-button-add-new-section.png)버튼을 눌러 나오는 칼럼구조에서 두번째 것을 선택해봅시다.

[![더하기 모양 아이콘과 폴더모양 아이콘. ](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-drag-widget-here-area.png)](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-drag-widget-here-area.png)

그러면 앞서 추가했던 Titel (제목)이 있는 섹션 바로 아래 아래그림처럼 2개의 칼럼으로 이루어진 섹션이 추가됩니다. 현재 비어있는[![6개 점으로 된 편집핸들 이미지](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-section-edit-handle.png)](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-section-edit-handle.png)**섹션**이 선택되어있기 때문에 파란테두리로 섹션 레이아웃이 표시되고 있고, 왼쪽 패널위에 **Edit Section** 이라는 엘리멘트 이름을 알 수 있습니다.

[![섹션 선택박스(파란 테두리))](https://swiftcoding.org/wp-content/uploads/2018/11/added-section-with-2-columns-in-elementor.png)](https://swiftcoding.org/wp-content/uploads/2018/11/added-section-with-2-columns-in-elementor.png)

아래처럼 파란 테두리가 나타나는 것은 현재 선택된 엘리먼트의 레이아웃을 표시하는 것일 뿐입니다. 현재는 어느 엘리먼트 위젯도 추가되어있지 않으므로 2개의 칼럼모두 비어있습니다.

[![2개의 칼럼을 감싸고있는 섹션을 표시하기위한 테두리와 그 가운데 위쪽에 섹션 편집 핸들이 나타남](https://swiftcoding.org/wp-content/uploads/2018/11/the-layout-of-section-with-2-columns-in-elementor.png)](https://swiftcoding.org/wp-content/uploads/2018/11/the-layout-of-section-with-2-columns-in-elementor.png)

+ 표시 위치에 위젯이 들어가지 않는 이상 위 상태에서는 최종 페이지에 아무것도 나오지 않고 공간만 차지하고 있는 모습으로 하얗게 렌더링될 뿐입니다. 이제 + 와 회색테두리로 표현되는 칼럼에 위젯을 끌어다 놓을 차례입니다.

칼럼 안의 + 버튼을 누르거나 왼쪽 패널의 [![네모난 점 9개가 큰 네모를 이루는 블락형태의 버튼](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-show-widgets.png)](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-show-widgets.png) 모든 위젯보기 버튼을 눌러 모든 위젯을 표시한뒤 [![풍경 사진 아이콘](https://swiftcoding.org/wp-content/uploads/2018/11/icon-for-image-widget-of-elementor.png)](https://swiftcoding.org/wp-content/uploads/2018/11/icon-for-image-widget-of-elementor.png) image 위젯과 [![여러줄의 문장을 표현한 아이콘](https://swiftcoding.org/wp-content/uploads/2018/11/icon-for-text-editor-widget-of-elementor.png)](https://swiftcoding.org/wp-content/uploads/2018/11/icon-for-text-editor-widget-of-elementor.png)Text Editor 위젯을 각각의 칼럼에 끌어다 놓아주세요. 그리고 각각의 Content와 Style 속성값을 지정해 아래처럼 만들어 봅시다.

[![제목 아래로 사진과 글자가 들어가있는 섹션이 디자인된 모습](https://swiftcoding.org/wp-content/uploads/2018/11/roughly-designed-elementor-page-with-2-sections.png)](https://swiftcoding.org/wp-content/uploads/2018/11/roughly-designed-elementor-page-with-2-sections.png)

## 페이지 저장 & 공개하기

이번에는 Elementor로 페이지를 디자인하는 중간에 [임시 저장하거나 완료시 공개하는 방법](https://swiftcoding.org/elementor-save-history)을 알아봅시다. 

화면 왼쪽 패널 아래에 보면 아래 그림처럼 PUBLISH 또는 UPDATE 버튼이 있는 하단 툴바가 보일 겁니다.

[![PUBLISH 또는 UPDATE 버튼이 있는 툴바](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-tool-bar-on-bottom.png)](https://swiftcoding.org/wp-content/uploads/2018/11/elementor-tool-bar-on-bottom.png)

현재 페이지가 공개되지 않은 임시글이라면 PUBLISH로 표시되고, 공개된 글이라면 UPDATE로 나올 겁니다. 우리는 임시글로 시작했기때문에 PUBLISH가 나오게 되어있습니다.

  

편집한 내용을 공개하려면 PUBLISH 또는 UPDATE 버튼을 누르면 됩니다만, 그에 앞서 임시저장 하는 방법도 알아야겠죠?

[![Save Draft 와 Save as Template 메뉴가 나타났다](https://swiftcoding.org/wp-content/uploads/2018/11/save-draft-menu-of-bottom-toolbar-in-elementor.png)](https://swiftcoding.org/wp-content/uploads/2018/11/save-draft-menu-of-bottom-toolbar-in-elementor.png)

  

 PUBLISH 또는 UPDATE 오른쪽에 삼각형을 클릭하면 위 그림처럼 추가 메뉴가 나타납니다. 여기에서 **Save Draft**를 클릭하게 되면 Elementor의 Revision History에 저장됩니다. 리비전 히스토리는 하단 툴바의 [![시계와 되돌림 화살표로 형상화된 History 아이콘](https://swiftcoding.org/wp-content/uploads/2018/11/history-button-on-bottom-toolbar-in-elementor.png)](https://swiftcoding.org/wp-content/uploads/2018/11/history-button-on-bottom-toolbar-in-elementor.png)History 아이콘을 클릭해서 찾아볼 수 있습니다.

[Elementor의 Revision History](https://swiftcoding.org/elementor-save-history#history-panel)는  워드프레스 기본 페이지를 저장하는 Revision과는 별도입니다. 디자인한 페이지를 공개하거나 업데이트할 때는 워드프레스 페이지 기능에 저장된 리비전 버전과는 다를 수 있으므로 반드시 Elementor 편집화면에 들어와서 PUBLISH 또는 UPDATE 버튼을 눌러 공개하도록 해줍시다.

#### 페이지 미리보기

현재까지 디자인한 페이지를 미리보려면 하단 툴바의 [![사람 눈 모양 아이콘](https://swiftcoding.org/wp-content/uploads/2018/11/preview-changes-button-in-elementor.png)](https://swiftcoding.org/wp-content/uploads/2018/11/preview-changes-button-in-elementor.png)Preview changes 버튼을 클릭하면 새창이 열리면서 어떻게 디자인되었는지 확인할 수 있습니다.

[![방문자에게 보여지게될 페이지 모습](https://swiftcoding.org/wp-content/uploads/2018/11/page-preview-that-is-designed-with-elementor.png)](https://swiftcoding.org/wp-content/uploads/2018/11/page-preview-that-is-designed-with-elementor.png)

## Elementor 종료하기

Elementor로 페이지디자인을 끝냈다면 이제 다시 워드프레스 관리자 페이지로 화면을 바꿔야겠죠.

[![Exit to dashboard 버튼이 보인다](https://swiftcoding.org/wp-content/uploads/2018/11/Exit-to-dashboard-to-quit-elementor.png)](https://swiftcoding.org/wp-content/uploads/2018/11/Exit-to-dashboard-to-quit-elementor.png)

위 그림처럼 왼쪽 사이드바 패널에 [![햄버거 모양](https://swiftcoding.org/wp-content/uploads/2018/11/show-page-document-menu-button-in-elementor.png)](https://swiftcoding.org/wp-content/uploads/2018/11/show-page-document-menu-button-in-elementor.png)페이지 설정 메뉴보기 버튼을 클릭하고 나타나는 EXIT TO DASHBOARD 버튼을 누르면 아래그림처럼 해당 페이지의 기본 편집화면으로 넘어갑니다.

[![페이지 본문 영역에 텍스트 영역 대신 Edit with Elementor 버튼이 자리잡고 있다](https://swiftcoding.org/wp-content/uploads/2018/11/the-page-editing-screen-that-edited-by-elememtor-.png)](https://swiftcoding.org/wp-content/uploads/2018/11/the-page-editing-screen-that-edited-by-elememtor-.png)

이제 워드프레스 코어의 페이지 편집화면에서 본 해당페이지에는 본문 영역의 텍스트 에디터 대신 Edit with Elementor 버튼이 자리잡고 있는 모습을 볼 수 있습니다. 다시 Elementor로 편집하려면 이 버튼을 누르면 됩니다.

## 디자인방식의 한계: HTML 과 CSS 사전지식

 위젯등이나 상세 옵션에대한 설명은 앞으로 Elementor 사용법 강좌를 메뉴얼 설명 방식으로 풀어가면서 설명하겠지만, 아무래도 옵션이름같은 많은 용어들이 HTML, CSS의 그것과 같습니다.

Elementor 뿐만아니라 워드프레스 페이지빌더 플러그인들이 대부분 그러한데, 아무리 마우스 드래그 앤 드랍만으로도 디자인할 수 있다고 해도 HTML 과 CSS 스타일에대한 기초지식이 없다면 이것저것 해보면서 경험으로 익힐 수 밖에 없습니다.

그리고 깊이 생각해보면 사실 페이지빌더의 디자인 방식은 HTML, CSS의 방식을 **전혀** 벗어나지 못합니다.아무래도 좀 더 구시대의 나모웹에디터나 드림위버 같은 디자인툴 쪽에 가까울 뿐,  파워포인트나 키노트, 포토샵처럼 오브젝트를 내가원하는 위치에 넣을 수 있는 자유로운 디자인방식과는 약간 다릅니다.

CSS에서는 특히 디자인의 기초기반이되는 레이아웃이 다른곳에서는 쓰이지도 않는 relative, absolute, fixed, float 같은 듣도 보도 못 한 개념을 사용하는 것부터가 지옥같습니다. 그것이 CSS 스타일의 원죄이며 한계이고 오랜시간 웹디자이너들을 괴롭혀온 틀이라고 할 수 있습니다.

웹화면은 글자크기, 화면너비, 높이, 사용 디바이스등이 고정되어있지 않기 때문이기도 하며 수십년간 빠르게 변화해온 웹환경에 대응하며 계속 변화해왔기 때문이기도 한데요. 최근에는 좀더 직관적인 CSS 속성이 많이 생겼지만 오늘날까지 IE 6, 8같은 구시대 웹브라우저를 지원해야하는 현실을 마주하고 있다면 새로운 CSS 속성을 사용할 수 없기도하죠.

그래도 어쨌건 HTML과 CSS가 Elementor를 사용하기위해 필수는 아니지만 알면 큰 도움이 된다고 말하고 싶네요. 그리고 워드프레스 테마등을 조금씩 수정하고 싶을때도 커스텀으로 CSS를 사용할 줄 알면 도움이 많이 되기도 합니다.

워드프레스를 사용하는 우리가 페이지빌더를 사용해서 웹페이이지를 디자인하는 이유가 HTML, CSS, PHP 코딩없이 디자인하기위한 것이므로 Elementor사용에 도움이될 정도의 기초지식정도만 익히는걸 추천합니다. CSS도 깊이 들어가면 매우 복잡하고 학습시간이 꽤 기니까요.

#### 다음단계

다음글에서는 Elementor 에서 자주 사용할 [우클릭 메뉴와 단축키](https://swiftcoding.org/elementor-copy-and-paste)에대해서 알아보고 계속해서 강좌글을 이어가겠습니다.

#### 참고

-   [Elementor 및 Elementor Pro 구매방법](https://swiftcoding.org/elementor)
-   [Elementor 프로 구매 페이지](https://elementor.com/pro/?ref=2836&campaign=pro-purchase)