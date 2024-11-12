---
title: "Summary of OpenAI 2023 DevDay"
date: 2023-11-07
layout: post
lang: en
---

On Monday, November 6th, during the [Open AI DevDay](https://openai.com/blog/new-models-and-developer-products-announced-at-devday), ChatGPT received a major update, with its knowledge base finally updated to April of this year, showing great sincerity. Additionally, the GPT Store was announced, extending an olive branch to creators, inviting them to earn together. Here is my summary of the conference.

<meta property="og:image" content="https://junbo.li/assets/2023-11-07-openai-dev-day/gpts.png">

<div style="margin-bottom: 20px">
  <img src="/assets/2023-11-07-openai-dev-day/gpts.png" class="centered-image" />
</div>

### GPT-4 Turbo Released
- The knowledge base has been updated from September 2021 to April 2023, and future updates will be faster. Finally!
- The context token limit has been upgraded from 8K/32K to 128K, roughly the length of a 300-page book, even surpassing Claude 2's 100K.
- Output speed has doubled.
- Users no longer need to choose which plugin to activate; the model will automatically select the appropriate plugin, such as DALL-E, web browsing, or data analysis, when needed.
- ChatGPT Plus will immediately switch to GPT-4 Turbo.
- Multimodal capabilities were briefly mentioned, which are certainly impressive, but since GPT-4V was released two months ago, it's not new information.
- API prices have dropped: input token prices decreased threefold to $0.01/1K, and output token prices halved to $0.03/1K. So, using the maximum 128K context would cost $1.28. Writing a 300-page book would cost $3.84.
- Function calling can now handle multiple functions simultaneously.
- Parameters can be set to increase the determinism of results with the same input.
- By the end of the year, GPT-4 Turbo's multimodal capabilities will be available.
- GPT-3.5 also received a price cut, with input token prices reduced by 75% to $0.003/1K and output token prices decreased by 62% to $0.006/1K.
- Large enterprises can also perform fine-tuning.

### Custom GPTs and GPT Store
- This is definitely a major event in the AI world! It will have a more profound impact than the incremental update of GPT-4 Turbo.
- Ordinary users can easily create custom GPTs, which can be done in just a few minutes. You can set its name, functions, upload data files as a dedicated knowledge base, and even integrate some APIs.
- Placing custom GPTs in the GPT Store allows for revenue sharing. This might truly be the App Store Moment. I'm anxious, not wanting to miss this once-in-a-lifetime opportunity, but I don't have any good ideas yet.
- The conference showcased GPTs from several companies, such as Code.org for programming education and CanvaGPT for graphic design, all using ChatGPT's chat interface but deeply integrated with these companies' services.
- It also demonstrated how to use Zapier AI Actions to manage your calendar, texts, etc. What does this mean? In the future, you can let ChatGPT access your email, Notion, and more, just by talking to ChatGPT to get things done and check your recorded information.
- Sam Altman personally demonstrated how to create a simple GPT without needing to write code.

### Assistants API
- This is mainly aimed at application developers to simplify the integration of apps with OpenAI.
- The custom GPTs mentioned above have interfaces on the ChatGPT website. The Assistants API, however, is designed to help other products or apps integrate ChatGPT, with the interface being the app's own.
- Previously, integrating ChatGPT involved simply calling an API, which was stateless, requiring all context to be input each time. For chat functions, this meant transmitting the entire conversation content with each API call, which was not only slow but also expensive. Developers had to manage state, prompt and context management, extend capabilities, and retrieval themselves. Now, with the threading feature, it is a stateful API, where only the latest information needs to be sent in the same session. It also provides retrieval and a code interpreter.
