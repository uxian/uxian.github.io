---
title: "OpenAI 2023 DevDay 总结"
date: 2023-11-07
layout: post
---

11月6日星期一[Open AI DevDay](https://openai.com/blog/new-models-and-developer-products-announced-at-devday)，ChatGPT迎来重大更新，知识库终于更新到今年4月份，诚意满满。并且宣布GPT Store，向Creator伸出了橄榄枝，诚邀一起赚钱。下面是我对这次发布会的梳理。

<meta property="og:image" content="/assets/2023-11-07-openai-dev-day/gpts.png">

<div style="margin-bottom: 20px">
  <img src="/assets/2023-11-07-openai-dev-day/gpts.png" class="centered-image" />
</div>

### 发布了GPT-4 Turbo
- 知识库从之前的2021年9月，更新到2023年4月，并且以后会加快同步速度。终于！
- 上下文 Context Token 从8K/32K 升级到 128K，差不多是300页的书长，甚至了超过Claude 2的100K。
- 输出速度提升了一倍。
- 用户不用去选择激活哪个插件了，模型自己会选择在合适的时候用插件，DALL-E，访问网络，数据分析，问就行了。
- ChatGPT Plus会立即切换为GPT-4 Turbo。
- 提了一嘴多模态(Multimodal)，肯定是很牛的，但GPT-4V两个月前就发布了，所以不算新信息。
- API的价格降到： 输Token价格下降3倍到$0.01/1K，输出 Token价格下降2倍到$0.03/1K。所以真的用使用128K的最长上下文的话，价格是$1.28。让它写一本300页的书的价格会是$3.84。
- Function calling可以同时call多个function了。
- 可以设置参数，增加相同输入时结果的确定性。
- 年底会开放GPT-4 Turbo的多模态功能(Multimodal)
- GPT-3.5也顺手更新了一下，降了个价，输入Token价格降低了75%到$0.003/1K，输出Token价格下降了62%到$0.006/1K。
- 大企业还可以做Fine-tuning。

### 定制GPT和GPT Store
- 这绝对是AI界的一个大事件！比GPT-4 Turbo的增量更新肯定影响更深远。
- 普通用户可以很方便的创建定制的GPT，最快几分钟就搞定。可以设定它的名称，功能，上传数据文件作为专属知识库，还可以集成一些API。
- 把定制GPT放到GPT Store还可以分成。也许这是真的App Store Moment。好焦虑啊，不想错过这个千载难逢的好机会，但是还没啥好想法。
- 发布会上演示了几个公司的GPT，有Code.org用来做编程教学的，有CanvaGPT用来做平面设计的，用的都是ChatGPT的聊天窗口，但和这些公司的服务做了深度的集成。
- 还演示了如何通过Zapier AI Actions来操作自己的日历，短信等。这意味着什么呢？将来你可以让ChatGPT访问你的邮箱、Notion啊什么的，就对着ChatGPT说话就能把事都办了，还能查自己记录下来的信息。
- Sam Altman还亲自演示了怎么做一个简单的GPT，不需要写代码就可以搞定。

### Assistants API
- 这个主要是面向应用开发者的，用来简化App和OpenAI的集成。
- 上面说的定制GPT，界面都是在ChatGPT的网站上的。而这个Assistants API主要是帮助其他产品或者App来集成ChatGPT的，界面是App自己的。
- 以前要集成ChatGPT，就是简单地调用API，API本身是Stateless的，每次都需要输入所有的context，如果是聊天功能，那么每次API调用都要传输整个会话内容，不仅慢，而且贵。开发者要自己做State management，Prompt and context management，extend capabilities，Retrieval。现在有了Threading的功能，是Stateful API，同一个会话，就只用传最新的信息。还提供了Retrieval和Code interpreter。
