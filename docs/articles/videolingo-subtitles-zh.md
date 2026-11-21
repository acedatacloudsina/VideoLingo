# 给英文录屏配中文字幕，最费劲的往往是按暂停

一段三分钟的软件演示，讲的人已经点开了下一个菜单，你还停在上一帧：刚才那句话怎么翻？该从哪个词断开？等字幕读完，画面里的按钮还在不在？

VideoLingo 就是做这份活儿的。给它一段视频，它能把对白听写出来，拆成适合上屏的短句，翻成中文，再把字幕对回原片。想保留讲解者的原声，到字幕这里就可以收工；想做中文版旁白，再往下走配音。两件事不用绑在一起。

![VideoLingo 项目演示图](https://raw.githubusercontent.com/Huanshere/VideoLingo/main/docs/public/images/demo.png)

*图源：VideoLingo 项目文档。*

字幕和译稿的区别，拿一句话就能说明白。比如录屏里的人说：“Drag the clip to the timeline, then trim the bit at the start.” 写进说明书，可以译成“将片段拖到时间线上，然后裁掉开头多余的部分”。放进视频，倒不如在鼠标拖动时只显示“把片段拖到时间线上”，等剪刀落下，再出一句“剪掉开头那一小段”。词没难到哪儿去，难的是让观众有空看鼠标。

这也是 VideoLingo 比“把听写稿丢进翻译框”多做的那部分：每句字幕都有自己的出场时间。拿它做软件教程，值得把省下来的听打时间花在校对上。尤其是菜单名：界面里写着 `Trim`，字幕里顺手留个英文，观众反而更容易找到。

### 翻译这一步，可以交给 Ace Data Cloud

VideoLingo 支持 OpenAI 兼容的对话接口，不用动源码。在侧栏的语言模型设置里，把 **Base URL** 填成 `https://api.acedata.cloud/v1`，**API Key** 填自己的 Ace Data Cloud 应用密钥，**Model** 填账户已开通、能按要求返回 JSON 的对话模型 ID，再把目标语言设为「简体中文」。这里用的是 **Chat Completions**：它处理听写出来的文字，不负责听视频，也不用为做字幕另配语音合成服务。密钥只放在自己的运行环境里，别随配置文件提交到 GitHub。

![VideoLingo 中文使用界面](https://raw.githubusercontent.com/Huanshere/VideoLingo/main/docs/pages/docs/zh_page.png)

*项目文档里的中文界面。接 Ace Data Cloud 时，地址和模型名换成自己的配置，不照抄截图。*

刚开始不妨只截半分钟，挑一段既有说话、又有鼠标操作的地方。回放的时候别光盯着有没有错别字：看到“点右上角”时，右上角那个按钮还在吗？再关掉声音看一遍。如果不用倒回去也能跟着做，这段字幕就算帮上忙了。

### 相关链接

[VideoLingo 原项目](https://github.com/Huanshere/VideoLingo) · [本文对应的 Fork](https://github.com/acedatacloudsina/VideoLingo) · [项目上手指南](https://github.com/Huanshere/VideoLingo/blob/main/docs/pages/docs/start.en-US.md)

[Ace Data Cloud 平台](https://platform.acedata.cloud/) · [Chat Completions 接口说明](https://platform.acedata.cloud/documents/openai-chat-completions)
