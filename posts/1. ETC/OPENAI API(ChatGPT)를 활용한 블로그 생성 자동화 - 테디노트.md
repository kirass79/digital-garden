---
page-title: "OPENAI API(ChatGPT)를 활용한 블로그 생성 자동화 - 테디노트"
url: https://teddylee777.github.io/python/chatgpt-blog-automation/
date: "2023-05-08 22:40:20"
---
**🔔 신규 오픈 🔔**  
\[인프런\] **스트림릿(Streamlit)을 활용한 파이썬 웹앱 제작하기** - [구경하러 가기!](http://bit.ly/3JVkczg)

2023년 01월 29일 11 분 소요

이번 포스팅에서는 `OPENAI`의 API를 활용하여 `ChatGPT` 의 텍스트 생성 모델인 `text-davinci-003`로 **주제**와 **세부요구사항**에 맞게 자동으로 블로그를 생성하고 이를 GitHub Pages에 블로그로 포스팅으로 자동 배포하는 튜토리얼을 진행해 보도록 하겠습니다.

## 실습파일[Permalink](https://teddylee777.github.io/python/chatgpt-blog-automation/#%EC%8B%A4%EC%8A%B5%ED%8C%8C%EC%9D%BC "Permalink")

[![](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/teddylee777/machine-learning/blob/master/13-ChatGPT/01-chatgpt.ipynb)  

## openai 관련 설정[Permalink](https://teddylee777.github.io/python/chatgpt-blog-automation/#openai-%EA%B4%80%EB%A0%A8-%EC%84%A4%EC%A0%95 "Permalink")

**API KEY 발급 방법**

-   [https://beta.openai.com/](https://beta.openai.com/) 접속하여 회원가입 후
    
-   [https://beta.openai.com/account/api-keys](https://beta.openai.com/account/api-keys) 에서 API KEY 발급
    
-   `create new key` 클릭 후 생성된 API KEY **복사**
    

```
# openai 설치 코드
# !pip install openai
```

```
import openai

openai.api_key = "OPENAI API 키 입력"
```

## 주제와 지시사항을 선정[Permalink](https://teddylee777.github.io/python/chatgpt-blog-automation/#%EC%A3%BC%EC%A0%9C%EC%99%80-%EC%A7%80%EC%8B%9C%EC%82%AC%ED%95%AD%EC%9D%84-%EC%84%A0%EC%A0%95 "Permalink")

`주제`를 선정합니다.

```
city = "New York"
topic = f"Top 10 Restaurants you must visit when traveling to {city}"
category = "travel"
print(topic)
```

Top 10 Restaurants you must visit when traveling to New York

세부 `지시사항`을 입력합니다.

-   [https://translate.google.com/](https://translate.google.com/)

```
# 프롬프트 (내용 수정 가능)
prompt = f'''
Write blog posts in markdown format.
Write the theme of your blog as "{topic}".
Highlight, bold, or italicize important words or sentences.
Please include the restaurant's address, menu recommendations and other helpful information(opening and closing hours) as a list style.
Please make the entire blog less than 10 minutes long.
The audience of this article is 20-40 years old.
Create several hashtags and add them only at the end of the line.
Add a summary of the entire article at the beginning of the blog post.
'''
```

## chatgpt api로 블로그 주제와 지시문을 전달하여 글을 생성[Permalink](https://teddylee777.github.io/python/chatgpt-blog-automation/#chatgpt-api%EB%A1%9C-%EB%B8%94%EB%A1%9C%EA%B7%B8-%EC%A3%BC%EC%A0%9C%EC%99%80-%EC%A7%80%EC%8B%9C%EB%AC%B8%EC%9D%84-%EC%A0%84%EB%8B%AC%ED%95%98%EC%97%AC-%EA%B8%80%EC%9D%84-%EC%83%9D%EC%84%B1 "Permalink")

```
def generate_blog(topic, prompt):
    # 모델 엔진 선택
    model_engine = "text-davinci-003"

    # 맥스 토큰
    max_tokens = 2048

    # 블로그 생성
    completion = openai.Completion.create(
        engine=model_engine,
        prompt=prompt,
        max_tokens=max_tokens,
        temperature=0.3,      # creativity
        top_p=1,
        frequency_penalty=0,
        presence_penalty=0
    )
    return completion
```

결과를 전달 받아 출력합니다.

```
response = generate_blog(topic, prompt)
# 생성된 글 출력
print(response.choices[0].text)
```

#Top10NYC #NYCrestaurants #TravelFood

Are you planning a trip to New York and looking for the best restaurants to visit? Look no further! Here is a list of the top 10 restaurants you must visit when traveling to New York. From classic Italian to modern American, these restaurants are sure to satisfy your taste buds. Each restaurant is listed with its address, menu recommendations, and other helpful information such as opening and closing hours. So, let’s get started!

##1. Carbone

Address: 181 Thompson St, New York, NY 10012

Carbone is an Italian-American restaurant that serves classic Italian dishes with a modern twist. The menu features dishes such as veal parmesan, spaghetti carbonara, and lasagna. The restaurant also offers a variety of wines and cocktails. Carbone is open from 5:30pm to 11pm Monday through Saturday, and 5pm to 10pm on Sunday.

##2. The Smith

Address: 956 2nd Ave, New York, NY 10022

The Smith is a modern American restaurant that serves classic American dishes with a contemporary twist. The menu features dishes such as mac and cheese, burgers, and steak. The restaurant also offers a variety of craft beers and cocktails. The Smith is open from 11:30am to 11pm Monday through Thursday, 11:30am to 12am Friday and Saturday, and 11am to 10pm on Sunday.

##3. Momofuku Noodle Bar

Address: 171 1st Ave, New York, NY 10003

Momofuku Noodle Bar is a Japanese-American restaurant that serves classic Japanese dishes with an American twist. The menu features dishes such as ramen, dumplings, and bao buns. The restaurant also offers a variety of sake and cocktails. Momofuku Noodle Bar is open from 11:30am to 11pm Monday through Thursday, 11:30am to 12am Friday and Saturday, and 11am to 10pm on Sunday.

##4. The Spotted Pig

Address: 314 W 11th St, New York, NY 10014

The Spotted Pig is a British-American restaurant that serves classic British dishes with an American twist. The menu features dishes such as fish and chips, shepherd’s pie, and bangers and mash. The restaurant also offers a variety of beers and cocktails. The Spotted Pig is open from 11:30am to 11pm Monday through Thursday, 11:30am to 12am Friday and Saturday, and 11am to 10pm on Sunday.

##5. Del Posto

Address: 85 10th Ave, New York, NY 10011

Del Posto is an Italian-American restaurant that serves classic Italian dishes with a modern twist. The menu features dishes such as risotto, gnocchi, and osso buco. The restaurant also offers a variety of wines and cocktails. Del Posto is open from 5:30pm to 11pm Monday through Saturday, and 5pm to 10pm on Sunday.

##6. Balthazar

Address: 80 Spring St, New York, NY 10012

Balthazar is a French-American restaurant that serves classic French dishes with an American twist. The menu features dishes such as steak frites, coq au vin, and bouillabaisse. The restaurant also offers a variety of wines and cocktails. Balthazar is open from 11:30am to 11pm Monday through Thursday, 11:30am to 12am Friday and Saturday, and 11am to 10pm on Sunday.

##7. Katz’s Delicatessen

Address: 205 E Houston St, New York, NY 10002

Katz’s Delicatessen is a classic New York deli that serves classic Jewish dishes with an American twist. The menu features dishes such as pastrami sandwiches, matzo ball soup, and knishes. The restaurant also offers a variety of beers and cocktails. Katz’s Delicatessen is open from 8am to 10pm Monday through Saturday, and 8am to 9pm on Sunday.

##8. The NoMad

Address: 1170 Broadway, New York, NY 10001

The NoMad is a modern American restaurant that serves classic American dishes with a contemporary twist. The menu features dishes such as roasted chicken, steak tartare, and pork chops. The restaurant also offers a variety of craft beers and cocktails. The NoMad is open from 11:30am to 11pm Monday through Thursday, 11:30am to 12am Friday and Saturday, and 11am to 10pm on Sunday.

##9. Eleven Madison Park

Address: 11 Madison Ave, New York, NY 10010

Eleven Madison Park is a French-American restaurant that serves classic French dishes with an American twist. The menu features dishes such as foie gras, duck confit, and beef tartare. The restaurant also offers a variety of wines and cocktails. Eleven Madison Park is open from 5:30pm to 11pm Monday through Saturday, and 5pm to 10pm on Sunday.

##10. The Breslin

Address: 16 W 29th St, New York, NY 10001

The Breslin is a British-American restaurant that serves classic British dishes with an American twist. The menu features dishes such as fish and chips, shepherd’s pie, and bangers and mash. The restaurant also offers a variety of beers and cocktails. The Breslin is open from 11:30am to 11pm Monday through Thursday, 11:30am to 12am Friday and Saturday, and 11am to 10pm on Sunday.

So, there you have it! The top 10 restaurants you must visit when traveling to New York. From classic Italian to modern American, these restaurants are sure to satisfy your taste buds. Bon Appétit! #NYCrestaurants #TravelFood #Top10NYC

## 해시태그 추출[Permalink](https://teddylee777.github.io/python/chatgpt-blog-automation/#%ED%95%B4%EC%8B%9C%ED%83%9C%EA%B7%B8-%EC%B6%94%EC%B6%9C "Permalink")

```
import re

hashtag_pattern = r'(#+[a-zA-Z0-9(_)]{1,})'

re.findall(hashtag_pattern, response['choices'][0]['text'])
```

\['#Top10NYC',
 '#NYCrestaurants',
 '#TravelFood',
 '##1',
 '##2',
 '##3',
 '##4',
 '##5',
 '##6',
 '##7',
 '##8',
 '##9',
 '##10',
 '#NYCrestaurants',
 '#TravelFood',
 '#Top10NYC'\]

해시태그를 `태그화` 하기 위하여 다음과 같이 문자열 형태로 변경합니다.

```
hashtags = [w[1:] for w in re.findall(hashtag_pattern, response['choices'][0]['text'])]
tag_string = ""
for w in hashtags:
    # 3글자 이상 추출
    if len(w) > 3:
        tag_string += f'{w}, '
tag_string
```

'Top10NYC, NYCrestaurants, TravelFood, NYCrestaurants, TravelFood, Top10NYC, '

```
tag_string = re.sub(r'[^a-zA-Z, ]', '', tag_string)
tag_string = tag_string.strip()[:-1]
tag_string
```

'TopNYC, NYCrestaurants, TravelFood, NYCrestaurants, TravelFood, TopNYC'

## 마크다운 형식의 블로그 글 생성[Permalink](https://teddylee777.github.io/python/chatgpt-blog-automation/#%EB%A7%88%ED%81%AC%EB%8B%A4%EC%9A%B4-%ED%98%95%EC%8B%9D%EC%9D%98-%EB%B8%94%EB%A1%9C%EA%B7%B8-%EA%B8%80-%EC%83%9D%EC%84%B1 "Permalink")

아래는 블로그의 `헤더` 입니다. 블로그 발행시 적용할 옵션을 지정합니다.

```
page_head = f'''---
layout: single
title:  "{topic}"
categories: {category}
tag: [{tag_string}]
toc: false
author_profile: false
sidebar:
    nav: "counts"
---
'''
print(page_head)
```

\---
layout: single
title:  "Top 10 Restaurants you must visit when traveling to New York"
categories: travel
tag: \[TopNYC, NYCrestaurants, TravelFood, NYCrestaurants, TravelFood, TopNYC\]
toc: false
author\_profile: false
sidebar:
    nav: "counts"
---

```
# 첫 줄은 타이틀(제목)과 겹치기 때문에 제거하도록 합니다.
body = '\n'.join(response['choices'][0]['text'].strip().split('\n')[1:])
```

`헤더` + `블로그 본문` 을 결합하여 최종 블로그 글을 완성합니다.

```
output = page_head + body
print(output)
```

\---
layout: single
title:  "Top 10 Restaurants you must visit when traveling to New York"
categories: travel
tag: \[TopNYC, NYCrestaurants, TravelFood, NYCrestaurants, TravelFood, TopNYC\]
toc: false
author\_profile: false
sidebar:
    nav: "counts"
---

Are you planning a trip to New York and looking for the best restaurants to visit? Look no further! Here is a list of the top 10 restaurants you must visit when traveling to New York. From classic Italian to modern American, these restaurants are sure to satisfy your taste buds. Each restaurant is listed with its address, menu recommendations, and other helpful information such as opening and closing hours. So, let’s get started!

##1. Carbone

Address: 181 Thompson St, New York, NY 10012

Carbone is an Italian-American restaurant that serves classic Italian dishes with a modern twist. The menu features dishes such as veal parmesan, spaghetti carbonara, and lasagna. The restaurant also offers a variety of wines and cocktails. Carbone is open from 5:30pm to 11pm Monday through Saturday, and 5pm to 10pm on Sunday.

##2. The Smith

Address: 956 2nd Ave, New York, NY 10022

The Smith is a modern American restaurant that serves classic American dishes with a contemporary twist. The menu features dishes such as mac and cheese, burgers, and steak. The restaurant also offers a variety of craft beers and cocktails. The Smith is open from 11:30am to 11pm Monday through Thursday, 11:30am to 12am Friday and Saturday, and 11am to 10pm on Sunday.

##3. Momofuku Noodle Bar

Address: 171 1st Ave, New York, NY 10003

Momofuku Noodle Bar is a Japanese-American restaurant that serves classic Japanese dishes with an American twist. The menu features dishes such as ramen, dumplings, and bao buns. The restaurant also offers a variety of sake and cocktails. Momofuku Noodle Bar is open from 11:30am to 11pm Monday through Thursday, 11:30am to 12am Friday and Saturday, and 11am to 10pm on Sunday.

##4. The Spotted Pig

Address: 314 W 11th St, New York, NY 10014

The Spotted Pig is a British-American restaurant that serves classic British dishes with an American twist. The menu features dishes such as fish and chips, shepherd’s pie, and bangers and mash. The restaurant also offers a variety of beers and cocktails. The Spotted Pig is open from 11:30am to 11pm Monday through Thursday, 11:30am to 12am Friday and Saturday, and 11am to 10pm on Sunday.

##5. Del Posto

Address: 85 10th Ave, New York, NY 10011

Del Posto is an Italian-American restaurant that serves classic Italian dishes with a modern twist. The menu features dishes such as risotto, gnocchi, and osso buco. The restaurant also offers a variety of wines and cocktails. Del Posto is open from 5:30pm to 11pm Monday through Saturday, and 5pm to 10pm on Sunday.

##6. Balthazar

Address: 80 Spring St, New York, NY 10012

Balthazar is a French-American restaurant that serves classic French dishes with an American twist. The menu features dishes such as steak frites, coq au vin, and bouillabaisse. The restaurant also offers a variety of wines and cocktails. Balthazar is open from 11:30am to 11pm Monday through Thursday, 11:30am to 12am Friday and Saturday, and 11am to 10pm on Sunday.

##7. Katz’s Delicatessen

Address: 205 E Houston St, New York, NY 10002

Katz’s Delicatessen is a classic New York deli that serves classic Jewish dishes with an American twist. The menu features dishes such as pastrami sandwiches, matzo ball soup, and knishes. The restaurant also offers a variety of beers and cocktails. Katz’s Delicatessen is open from 8am to 10pm Monday through Saturday, and 8am to 9pm on Sunday.

##8. The NoMad

Address: 1170 Broadway, New York, NY 10001

The NoMad is a modern American restaurant that serves classic American dishes with a contemporary twist. The menu features dishes such as roasted chicken, steak tartare, and pork chops. The restaurant also offers a variety of craft beers and cocktails. The NoMad is open from 11:30am to 11pm Monday through Thursday, 11:30am to 12am Friday and Saturday, and 11am to 10pm on Sunday.

##9. Eleven Madison Park

Address: 11 Madison Ave, New York, NY 10010

Eleven Madison Park is a French-American restaurant that serves classic French dishes with an American twist. The menu features dishes such as foie gras, duck confit, and beef tartare. The restaurant also offers a variety of wines and cocktails. Eleven Madison Park is open from 5:30pm to 11pm Monday through Saturday, and 5pm to 10pm on Sunday.

##10. The Breslin

Address: 16 W 29th St, New York, NY 10001

The Breslin is a British-American restaurant that serves classic British dishes with an American twist. The menu features dishes such as fish and chips, shepherd’s pie, and bangers and mash. The restaurant also offers a variety of beers and cocktails. The Breslin is open from 11:30am to 11pm Monday through Thursday, 11:30am to 12am Friday and Saturday, and 11am to 10pm on Sunday.

So, there you have it! The top 10 restaurants you must visit when traveling to New York. From classic Italian to modern American, these restaurants are sure to satisfy your taste buds. Bon Appétit! #NYCrestaurants #TravelFood #Top10NYC

## 블로그 `.md` 파일명에 기입할 날짜 형식을 생성[Permalink](https://teddylee777.github.io/python/chatgpt-blog-automation/#%EB%B8%94%EB%A1%9C%EA%B7%B8-md-%ED%8C%8C%EC%9D%BC%EB%AA%85%EC%97%90-%EA%B8%B0%EC%9E%85%ED%95%A0-%EB%82%A0%EC%A7%9C-%ED%98%95%EC%8B%9D%EC%9D%84-%EC%83%9D%EC%84%B1 "Permalink")

```
import os
from datetime import datetime, timedelta

# 어제 일자 생성
yesterday = datetime.now() - timedelta(days=1)
yesterday
```

datetime.datetime(2023, 1, 29, 3, 12, 17, 631524)

블로그 파일명에 입력할 `날짜 형식`을 위한 처리를 수행합니다.

```
timestring = yesterday.strftime('%Y-%m-%d')
timestring
```

'2023-01-29'

파일명을 생성합니다.

-   여기서 `날짜` + `블로그제목` 형식으로 공백 없이 파일명을 생성합니다.

```
filename = f"{timestring}-{'-'.join(topic.lower().split())}.md"
filename
```

'2023-01-29-top-10-restaurants-you-must-visit-when-traveling-to-new-york.md'

## 생성한 블로그를 github pages 경로에 생성[Permalink](https://teddylee777.github.io/python/chatgpt-blog-automation/#%EC%83%9D%EC%84%B1%ED%95%9C-%EB%B8%94%EB%A1%9C%EA%B7%B8%EB%A5%BC-github-pages-%EA%B2%BD%EB%A1%9C%EC%97%90-%EC%83%9D%EC%84%B1 "Permalink")

블로그의 `_posts`가 위치한 절대 경로를 지정합니다.

```
# github pages 주소의 _posts 절대 경로 지정
blog_directory = r"블로그ROOT폴더경로/_posts"
```

`블로그 경로` + `파일 이름` 으로 마크다운 파일을 저장할 전체 경로를 생성합니다.

```
# 파일 이름 생성
filepath = os.path.join(blog_directory, filename)
filepath
```

'/Users/teddy/Dev/github/teddynote.github.io/\_posts/2023-01-29-top-10-restaurants-you-must-visit-when-traveling-to-new-york.md'

마지막으로 파일에 마크다운으로 작성된 블로그 글을 쓰고 **저장**합니다.

```
with open(filepath, 'w') as f:
    f.write(output)
    f.close()
```