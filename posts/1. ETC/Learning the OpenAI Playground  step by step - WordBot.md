---
page-title: "Learning the OpenAI Playground | step by step - WordBot"
url: https://blog.wordbot.io/ai-artificial-intelligence/learning-the-openai-playground-step-by-step/
date: "2023-05-08 00:40:23"
---
The OpenAI playground was released to the public with no waitlist in November 2021. If you have been looking to test out building an AI generated application, now is the time.

In this short tutorial I will talk about some of the different characteristics the Openai gpt-3 playground provides. With a multitude of capabilities finding what’s best for you can start right here.

## What is OpenAi?

OpenAi is an Artificial Intelligence company most notably founded by Elon Musk and a team of other investors in 2015. Over the years they have done research in developing AI that would help humanity in many different ways.

Over the years they have developed and trained models that have learned from trillions of words on the internet. The latest model that has the internet buzzing from OpenAI is their GPT-3 model.

They have built a user friendly Playground around their GPT-3 model which allows you to build AI applications using their API.

So now lets talk a little about how you can get access and what the Open AI playground does.

## How to get access to the OpenAI Playground?

Visit the OpenAI playground on [OpenAi’s](https://openai.com/) Website and signup. You will have the option to signup using either your email, gmail or Microsoft account.

Once you get signed up you will have the option to choose if this account will be used for personal or business use. After you get logged in there will be a multitude of documentation to help assist you in figuring ouw how you want to use their playground.

## Making sense of the OpenAI Documentation

OpenAI provides a lot of documentation to read. Testing out some of the examples helps give you a good idea of the AI’s capabilities. The examples are predefined applications built using the playground that allow you to test without having to change settings

![openai example applications](https://blog.wordbot.io/wp-content/uploads/2022/01/open-ai-examples-1024x545.jpg)

openai example applications

Once you select one of the examples, you will see the predefined Application settings. Then you can select “Open in Playground”

![openai playground test application](https://blog.wordbot.io/wp-content/uploads/2022/01/example-settings-1024x518.jpg)

openai playground test application

Then you can proceed to test out the application. Visit the documentation page for more info on in depth terminology. Using the playground before hand gives a great hands on approach to learning.

## How the Openai Playground works

Now lets talk a little about how the openai playground really works. Currently as of this writing OpenAI gives all accounts $18 in free credits. Pricing will depend on a couple differernt factors such as:

-   Type of AI Engine being used
-   The amount of Input sent through the playground
-   The amount of output recieved from the

All of these can be adjusted by various settings. When you initially start working inside of the playground you will be presented with a screen like below.

![openai playground settings](https://blog.wordbot.io/wp-content/uploads/2022/01/openai-playground-1024x411.png)

openai playground settings

In the middle you have the playground you work in. On the top right you have the ability to save, share and view your api code. And finally off to the right you have the playground settings you may have to adjust as you learn.

## How to work the openai playground

So the first thing you may ask yourself is what do you type inside of this editor. This all depends on what you want to accomplish with the AI. To keep things simple lets talk about the Question and Answer Example we are using.

Think of the Playground as an empty brain and you have to teach it what you want to do. At the very top you will see the words *“I am a highly intelligent question answering bot. If you ask me a question that is rooted in truth, I will give you the answer. If you ask me a question that is nonsense, trickery, or has no clear answer, I will respond with “Unknown”*.

What this is doing is telling the playground instructions on how you want it to behave. Then underneath that you have what are called prompts.

Prompts are examples of the input and output your ai will generate. So since this is a question and answering bot we have some examples of how we want the questions asked and answered.

You will need to learn prompt engineering to make sure you get correct output generated.

Now that the examples are setup, at the very end you will see that there is a “Q:” with nothing in it. This is a open input that you can type a question into and press the generate button.

![](https://blog.wordbot.io/wp-content/uploads/2022/01/openai-playground-questions.png)

openai playground questions

As you can see I was able to ask it truthful questions and get real responses back. This shows the power of AI. We can get split second responses back in seconds.

## The openai playground settings

Openai has a multitude of settings you can change to make your outputs generate better text responses, control your cost and more.

One of the biggest settings which can effect not only affect cost but the quality of the output is the Engine

### Openai playground engines

There are 4 types of engines across 3 different series:

-   **Base Series**: which is a set of gpt-3 models that can understand and generate natural language
-   **Instruct Series**: This series is like the base series but better at following instructions that you give it.
-   **Codex Series**: Understands code and able to translate natural language to code.

Within those series you have the following engines:

-   ==**Openai Davinci Engine**: this engine is the most powerful and most expensive to use. This engine has the ability to understand complex intent and usually requires less instructions.==
-   **Openai Curie Engine**: the curie engine is very fast and cheaper to use. Best used for simple text questions and answers, summarization vs using Davinci which is better at more complicated text
-   **Openai Babbage Engine:** great at performing straightforward task such as classifying text.
-   **Openai Ada Engine:** Is great at performing simple classification, getting keywords from text etc. Typically the fastest engine but cheap.

![openai playground prices](https://blog.wordbot.io/wp-content/uploads/2022/01/openai-playground-prices-1024x324.png)

openai playground prices

### Openai request body settings

You can improve the openai playground by adjusting the various sliders and numbers.

-   **Temperature:** adjust the temperature from 0-1 to improve the accuracy of the results. Stay closer to 0 for more accurate specific answers. The closer you get to 1 the AI will become more creative with answers.
-   **Response Length:** The max amount of tokens to generate between prompt and output
-   **Stop Sequence:** This tells the output when to stop generating tokens. In the case of our Q/A Example the enter key between each set tells it when to stop
-   **Top P**: Controls the diversity of the output. Use either Top P or Temperature but not both
-   **Frequency Penalty:** Use this to decrease how often the output repeats the text verbatim
-   **Presence Penalty:** Adjust if you need the text to talk more or less about new topics
-   **Best Of:** Use to allow openai to generate a multiple of outputs and choose between the best one. This can eat up more tokens and cost more money
-   **Inject Start Text & Inject Restart Text:** set specific words to be inputted at the beginning and end of the output.

다양한 슬라이더와 숫자를 조정하여 openai 놀이터를 개선할 수 있습니다.

- **온도:** 온도를 0-1로 조정하여 결과의 정확도를 높입니다. 보다 정확한 특정 답을 얻으려면 0에 가깝게 유지하십시오. 1에 가까워질수록 AI는 더 창의적으로 대답할 것입니다.
- **응답 길이:** 프롬프트와 출력 사이에 생성할 최대 토큰 양
- **Stop Sequence:** 토큰 생성을 중지할 시기를 출력에 알려줍니다. Q/A 예제의 경우 각 세트 사이의 Enter 키는 중지할 때를 알려줍니다.
- **Top P**: 출력의 다양성을 제어합니다. Top P 또는 Temperature 중 하나를 사용하되 둘 다 사용하지 않음
- **빈도 페널티:** 출력에서 텍스트를 그대로 반복하는 빈도를 줄이기 위해 사용합니다.
- **Presence Penalty:** 새로운 주제에 대해 더 많이 또는 더 적게 이야기하기 위해 텍스트가 필요한 경우 조정합니다.
- **Best Of:** openai가 여러 출력을 생성하고 최상의 출력 중에서 선택할 수 있도록 사용합니다. 이것은 더 많은 토큰을 먹고 더 많은 비용이 들 수 있습니다.
- **Inject Start Text & Inject Restart Text:** 출력의 처음과 끝에 입력할 특정 단어를 설정합니다.

## Saving openai playground prompts

As you start creating prompts you will start to create different versions. Save these versions to be able to go back and test various settings. This prevents having to always edit settings and rewrite your prompts.

![save prompt](https://blog.wordbot.io/wp-content/uploads/2022/01/openai-playground-preset.png)

## Integrating the openai playground api into your application

Using the openai playground can only take you so far. Its just a testing ground before you start to build your applications. The prompts you create should be treated as proprietary information to your businesses.

Validate your business idea and then apply the api to your application to finish the rest. Click the view code button at the top of your playground.

![api settings](https://blog.wordbot.io/wp-content/uploads/2022/01/openai-playground-api.png)

openai playground api

Use that code to integrate into your application of choice. You can obtain your api key by going into the settings and click view api keys.

## Conclusion

Openai has given many ai businesses the ability to jumpstart their applications faster. [Wordbot](https://wordbot.io/) was built using GPT-3 provided by Openai. Learning how to use the openai playground is the single most important task to improving your application.

The opportunities are endless what GPT-3 will be able to do for businesses and applications.