---
page-title: "[CSS] Margin, Padding 차이점과 사용법 정리"
url: https://velog.io/@hyejin4169/CSS-margin-padding-%EC%B0%A8%EC%9D%B4%EC%A0%90%EA%B3%BC-%EC%82%AC%EC%9A%A9%EB%B2%95-%EC%A0%95%EB%A6%AC
date: "2023-04-25 15:43:14"
---
CSS를 익히기 시작할 때 가장 먼저 배우는게 Margin(마진)과 Padding(패딩) 같은데, 마진과 패딩의 차이점 및 사용방법을 정리해보겠다.

## Margin과 Padding 차이

> **Margin**: Object와 화면과의 여백(외부여백)  
> **Padding**: Object 내의 내부여백

![](https://velog.velcdn.com/images/hyejin4169/post/5a49d3d5-5fb4-48a9-ac2d-f660d14bbdcf/image.png)  
이 HTML 박스모델을 보면 더욱 이해가 쉽다. (다들 개발자 도구에서 많이 보셨죠..)

자세히 다시 설명하자면,

-   **Margin**은 Border 바깥쪽을 차지한다. 주변 요소와 거리를 두기 위한 영역이다.
    
-   **Padding**은 Content와 Border 사이의 여백을 나타낸는 영역이다. Content 영역이 배경색이나 배경 이미지를 가질 때, 이 Padding 영역까지도 영향을 미친다. 즉, Padding 영역도 Content의 연장으로 볼 수 있다.
    

#### 그 외의 차이점?

-   음수값: Margin만 적용 가능
-   auto: Margin만 적용 가능

## Margin과 Padding의 사용법

(마진 중심으로 설명합니다.)

#### 1\. 속성 4개 사용

-   시계방향(위, 오른쪽, 아래, 왼쪽) 순서로 값을 주면 된다.
    -   예: margin: 10px 5px 10px 5px

#### 2\. 속성 2개 사용

-   2개의 속성만 사용할 경우, 첫번째 값은 위와 아래 / 두번째 값은 오른쪽과 왼쪽 여백을 의미한다.
    -   예: margin: 10px 5px

#### 3\. 속성 1개 사용

-   1개의 속성만 사용할 경우, 위, 오른쪽, 아래, 왼쪽 모두 같은 값을 사용하게 된다.

#### 4\. padding 속성 1개 사용

-   패딩의 1개 속성만 사용할 경우, 안쪽여백이 변경된다.
    -   예: padding: 20px

#### 5\. 단일 속성 부여

-   위, 오른쪽, 아래, 왼쪽 중 하나에만 값을 부여하고 싶은 경우, 하단과 같이 방향을 지정해주면 된다.
    -   예: margin-right: 20px, padding-top: 10px

#### 6\. 가운데 정렬

-   auto를 이용한다. **padding은 auto값 선언 불가.**
    -   예: margin: auto

출처: [https://bebeya.tistory.com/entry/CSS-margin-padding-개념-사용법-정리](https://bebeya.tistory.com/entry/CSS-margin-padding-%EA%B0%9C%EB%85%90-%EC%82%AC%EC%9A%A9%EB%B2%95-%EC%A0%95%EB%A6%AC)  
[https://coding-factory.tistory.com/187](https://coding-factory.tistory.com/187)  
[https://enai.tistory.com/49](https://enai.tistory.com/49)