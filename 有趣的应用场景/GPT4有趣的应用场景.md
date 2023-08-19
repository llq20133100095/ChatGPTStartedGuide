GPT4模型已经公布了一堆时间，之间我也解构过它的一些技术细节。详情可以看我以前写过的这篇文章：

[GPT4详解~你感兴趣的点都在这里](https://www.yuque.com/yuqueyonghumaryyq/fmvho1/pl5ltlf3lvbi8xhu?view=doc_embed)

今天我们一起来看看，GPT4目前已经应用的一些有趣场景。

# GPT-4 Copilot X：AI 提升程序员的体验
[https://github.blog/2023-03-22-github-copilot-x-the-ai-powered-developer-experience/](https://github.blog/2023-03-22-github-copilot-x-the-ai-powered-developer-experience/)
还记得那个帮助你生成代码的GitHub Copilot项目吗？在敲代码的时候，它往往能够很神奇的预测自己下一行代码的写法。有了它之后，对于重复性的写代码工作可以很简单的就实现出来。

这不，为了赶上GPT-4的这股热潮，GitHub Copilot终于集成了GPT-4模型。

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1679574466594-5506ed18-0f70-4a17-8d6e-d3455433a53c.png#averageHue=%23526394&clientId=ubd104b62-55e3-4&from=paste&height=477&id=u315c8dbc&originHeight=572&originWidth=1072&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=1114372&status=done&style=none&taskId=u33637b1b-1ac6-4e94-8639-6fe004d8e72&title=&width=893.3332978354574)

其中Copilot X在官网上介绍共有4个不同的功能：

- **Copilot Chat：**直接在编辑器上，针对代码错误进行询问
- **Copilot for Pull Requests**：有效的帮你管理代码仓库
- **Copilot for documentation：**针对项目文档、常用代码等内容发起提问，即时获取答案。
- **Copilot for the command line interface (CLI)：**在命令行终端上，给出代码提示

> **Copilot Chat**

Github在一些代码编辑软件上，嵌入了GPT-4用来进行聊天。

![b6b45681-b5ac-4b08-ac38-5dbea2b53d9d.gif](https://cdn.nlark.com/yuque/0/2023/gif/29330410/1680268483184-065e9ba9-64e6-4f19-8ca7-cfc4fdb332fc.gif#averageHue=%23305d23&clientId=u40a5826e-91d7-4&from=paste&height=432&id=u8e73f9ec&originHeight=1080&originWidth=1920&originalType=binary&ratio=2.5&rotation=0&showTitle=false&size=3675638&status=done&style=none&taskId=u1867a28a-da12-4864-a339-0254f3dbb0a&title=&width=768)

它不仅仅是一个简单的聊天工具，也可以识别开发人员输入的代码、显示的错误等消息。帮助程序员能够深入分析代码块的作用，并解析代码的用途等。

> **Copilot for Pull Requests**


能够帮助开发人员生命周期中为您提供帮助，从编写代码的 IDE 到与团队共享代码的拉取请求。

在Github中，往往需要编写拉取请求描述，用来帮助程序员能够快速了解代码的功能等细节。

![c3faba2f-331b-4ded-9307-5afddbba3504.gif](https://cdn.nlark.com/yuque/0/2023/gif/29330410/1680268565460-f2d149dd-4d2a-4d0f-a693-acbec64fcf94.gif#averageHue=%23f3f5fe&clientId=u40a5826e-91d7-4&from=paste&height=636&id=uda045c5d&originHeight=1590&originWidth=1708&originalType=binary&ratio=2.5&rotation=0&showTitle=false&size=2305754&status=done&style=none&taskId=u42dcf7f8-3d38-46fc-aa7e-e0c928d61a9&title=&width=683.2)

或者，还能够利用AI解决代码仓库中别人提出的问题。比如，有人刚刚在你的仓库上提出了一个问题：“用PyTorch替换TensorFlow”。这时候，就可以直接利用AI帮助你解决这个问题

![057aba4a-69a6-44b7-900c-1e2c290e3859.gif](https://cdn.nlark.com/yuque/0/2023/gif/29330410/1680351031236-523ecb06-b883-4e1a-9202-c03c46fa0304.gif#averageHue=%23eaecf6&clientId=u31e2e474-b41f-4&from=paste&height=432&id=u9b12233d&originHeight=1080&originWidth=1920&originalType=binary&ratio=2.5&rotation=0&showTitle=false&size=4127781&status=done&style=none&taskId=u0e174bd3-ea75-4ca7-bb45-eeccfc5ef43&title=&width=768)

> **Copilot for documentation**


它也直接提供了一个聊天界面，让你可以随时随地的向他提出问题。

同时在文档中，直接给出每一个步骤的答案。针对项目文档、常用代码等内容发起提问，即时获取答案。

![06e057ef-1d39-4cce-823e-7429d7aff76e.gif](https://cdn.nlark.com/yuque/0/2023/gif/29330410/1680271590415-6c4baf44-61a8-4b28-ab16-936c2db2167e.gif#averageHue=%23e7edfe&clientId=u40a5826e-91d7-4&from=paste&height=432&id=uc924338f&originHeight=1080&originWidth=1920&originalType=binary&ratio=2.5&rotation=0&showTitle=false&size=2550782&status=done&style=none&taskId=u4fada7fe-9d0c-46e3-be1d-752225adef8&title=&width=768)

> **Copilot for the command line interface (CLI)**

一般来说，程序员面对最多的可能是命令行终端了。因此Github推出了针对终端的提示代码器。

它可以编写命令和循环，并给出查找标志以满足程序员的查询。

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1680271826786-b63e0068-186d-4b64-a541-1943ddf3d569.png#averageHue=%23090808&clientId=u40a5826e-91d7-4&from=paste&height=442&id=u02182f1a&originHeight=1104&originWidth=1757&originalType=binary&ratio=2.5&rotation=0&showTitle=false&size=203219&status=done&style=none&taskId=u0402b228-57ec-4347-a6c2-e10d69ed4ce&title=&width=702.8)

# Cursor：自动代码生成工具
Cursor 是一款专为 AI 编程而生的编辑器。它也接入了OpenAI的GPT4模型，用来提升程序员写代码的效率。主要有以下几个功能：

- 编写代码：使用比 Copilot 更智能的 AI 生成 10-100 行代码
- 查看代码 差异：让 AI 建议一段代码，让它进行对比
- 聊天：可以像和ChatGPT一样进行聊天，让它帮助你解决代码问题
- 解析代码：生成代码解析、评估代码错误等功能

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1680315670738-348150d6-7d05-4dd6-b90c-2ac9c7e88fe0.png#averageHue=%23121212&clientId=ubd6de653-7ba1-4&from=paste&height=721&id=u34977749&originHeight=1803&originWidth=3840&originalType=binary&ratio=2.5&rotation=0&showTitle=false&size=458133&status=done&style=none&taskId=uccacf4a4-2c91-4d12-9cd6-866a1fa8ebe&title=&width=1536)

目前Cursor界面比较简单，仅仅只能作为写代码工具。但在界面上，我们就可以直接利用快捷键“ctrl + k”快速生成所需要的代码。

> **比如，我想要从零开始生成一个LSTM神经网络**

![0ed24ed2-7a3c-4319-9c46-f827e26db574.gif](https://cdn.nlark.com/yuque/0/2023/gif/29330410/1680353570207-d68be9c5-fcaf-4990-83d5-ce0e245cc11d.gif#averageHue=%23385c34&clientId=u9b23128b-fe95-4&from=paste&height=360&id=ubf627e75&originHeight=720&originWidth=1280&originalType=binary&ratio=2&rotation=0&showTitle=false&size=326109&status=done&style=none&taskId=u6d734790-52a5-4543-89ef-4e55db02e1b&title=&width=640)

或者直接生成一个网页，用来判定图片是否喜欢：
> **生成一个可以本地部署的网页，页面上可以随机放一张图片，同时图片下方有两个按钮，一个是喜欢按钮，一个是不喜欢按钮**

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1680353361894-cf0e0658-9bdd-46e9-9a7a-1d20117a58c2.png#averageHue=%23c7bfb8&clientId=u9b23128b-fe95-4&from=paste&height=893&id=uff86c971&originHeight=1786&originWidth=3828&originalType=binary&ratio=2&rotation=0&showTitle=false&size=2211634&status=done&style=none&taskId=u840ffb93-32c0-4b09-b40a-9c0469e8f79&title=&width=1914)
最后，直接一键生成网页代码。

用了这么多天，其实最有用的还是可以直接解析代码，和它对话，就可以直接知道这个代码实现什么功能：

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1680353485504-90322452-2573-4ca5-8ef0-b7ad2509a8c5.png#averageHue=%239b725e&clientId=u9b23128b-fe95-4&from=paste&height=1030&id=u0c14ca69&originHeight=2060&originWidth=3840&originalType=binary&ratio=2&rotation=0&showTitle=false&size=805207&status=done&style=none&taskId=u3d7a1149-65de-4b36-9812-307d3ff0383&title=&width=1920)

那么，以后只需要简单的几句话，就可以了解到这些其他人实现的函数效果是什么了。简直是代码解析神器~
# 微软Office Copilot
在3月16日时，微软就宣布Office产品正式接入GPT4模型，被称为“Microsoft 365 Copilot“。

![](https://cdn.nlark.com/yuque/0/2023/png/29330410/1680662380101-f5a58bd0-757e-4717-9220-899f5d7bc81b.png#averageHue=%23dae5da&clientId=u10a79718-f979-4&from=paste&id=u78dcc6a9&originHeight=1081&originWidth=1921&originalType=url&ratio=1.25&rotation=0&showTitle=false&status=done&style=none&taskId=u40bed6a2-eedb-46e1-b2ca-1fd3fdc35fb&title=)

他在官方介绍到，如果未来人们都能够用上的话，可以大大提升生产力，并同时转换工作思维和方法：

> **释放创造力**


比如：可以直接利用**word**中的copilot进行文档撰写。在Copilot上输入想要生成的主题，则可以快速启动创作过程，从而节省写作时间。

![word[00_00_02--00_00_22].gif](https://cdn.nlark.com/yuque/0/2023/gif/29330410/1680665130973-4af5c9e8-cf1d-4de9-aaae-317dc0d96e18.gif#averageHue=%23f6f6fa&clientId=u10a79718-f979-4&from=paste&height=181&id=Lmoy2&originHeight=226&originWidth=400&originalType=binary&ratio=1.25&rotation=0&showTitle=false&size=3192391&status=done&style=none&taskId=ua53fae83-93a6-41b8-b6e9-e76b852b8fa&title=&width=320)

又或者，可以直在**PPT**上，通过提示在几秒内创建精美的演示文稿。

![ppt (1).gif](https://cdn.nlark.com/yuque/0/2023/gif/29330410/1680665532231-642304d0-b6ed-4e4f-bf96-18b8b09cbb98.gif#averageHue=%23e6f0fd&clientId=u10a79718-f979-4&from=paste&height=216&id=ud86bbeac&originHeight=270&originWidth=480&originalType=binary&ratio=1.25&rotation=0&showTitle=false&size=1834857&status=done&style=none&taskId=ue3ed8fab-4a8b-41b4-a2bd-8c79e4ae182&title=&width=384)

当然，它也可以直接在excel上，帮我们提取和整理想要的数据。

![excel[00_00_00--00_00_20].gif](https://cdn.nlark.com/yuque/0/2023/gif/29330410/1680666263537-c1e57e1a-43a7-4f49-ae71-92691aeac89c.gif#averageHue=%23d5dad4&clientId=u10a79718-f979-4&from=paste&height=181&id=u97f6e0e7&originHeight=226&originWidth=400&originalType=binary&ratio=1.25&rotation=0&showTitle=false&size=1522327&status=done&style=none&taskId=uba979b2b-b381-4e76-82c0-f33e9a13172&title=&width=320)

> **释放生产力**


在很多时候，我们在工作中70%以上都做的是重复繁杂的工作。比如在某次会议上，需要进行总结等等。

这些时候，Office Copilot可以快速的帮助我们进行有效总结

![team[00_00_04--00_00_24].gif](https://cdn.nlark.com/yuque/0/2023/gif/29330410/1680666379896-a2d3a3cc-0f70-41c9-9408-f312ef78e02b.gif#averageHue=%23ccd9ec&clientId=u10a79718-f979-4&from=paste&height=181&id=u029cf5af&originHeight=226&originWidth=400&originalType=binary&ratio=1.25&rotation=0&showTitle=false&size=2098093&status=done&style=none&taskId=u2e8e72af-3c01-452e-91cb-13388aefcbe&title=&width=320)

就想官网所说的一样：**人类天生就又梦想、创造和创新。**相信如果以后真的大规模推广之后，能够帮助我们进一步提高工作效率，解决大量重复枯燥的问题，让我们能够更好的集中在创造和创新工作上。

好了，以上就是本期的全部内容了。我是leo，欢迎关注我的公众号”算法一只狗“，我们下期再见~

![qrcode_for_gh_f4f620aeff8d_258.jpg](https://cdn.nlark.com/yuque/0/2023/jpeg/29330410/1680666110978-53bfb9e0-6161-4794-a0ef-b9d22cd65cbf.jpeg#averageHue=%23a6a4a3&clientId=u10a79718-f979-4&from=paste&height=206&id=u9bd8bc40&originHeight=258&originWidth=258&originalType=binary&ratio=1.25&rotation=0&showTitle=false&size=27604&status=done&style=none&taskId=uda4ae749-c3ab-4c21-ad89-f7985be471e&title=&width=206.4)
