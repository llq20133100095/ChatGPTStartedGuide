
自从openai开放了ChatGPT接口之后，一些开发者开始利用这个接口进行私人订制。因此本文找了几个好玩的应用，帮助大家开发一下思路。

# 订制真人对话系统
近期我就在huggingface网站上看到了利用ChatGPT和Whisper语音识别，来制作真人对话系统的。
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1678525691798-2fb939d9-31c8-42c6-82b7-3c85546af02d.png#averageHue=%23f0f0f0&clientId=u768ff4bf-aa4f-4&from=paste&height=702&id=ubc5b3732&originHeight=1403&originWidth=3054&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=316824&status=done&style=none&taskId=u3111bbeb-b72f-4107-9281-22653c5455b&title=&width=1527)

各位如果感兴起可以上这个网站上体验一下：
> [https://huggingface.co/spaces/JavaFXpert/Chat-GPT-LangChain](https://huggingface.co/spaces/JavaFXpert/Chat-GPT-LangChain)


这个项目主要结合了ChatGPT的对话功能，和Whisper语音识别功能。

我自己搭建了一下，卡在了要给钱的那一步。哈哈哈哈，如果有哪位大佬有钱有闲的可以自己也搭建一个。

如果要从头到尾搭建这个项目的话，首先需要还是需要有OpenAI的账号，并且获取到**API KEY**。这个获取方法，在我之前的文章里面有提到：
[OpenAI开放ChatGPT的API，快来定制你的私人对话网站](https://mp.weixin.qq.com/s/c2qtKB5tnkcvPHIBvx_EEw)

然后还需要到谷歌搜索上申请serpapi key
> [https://serpapi.com/manage-api-key](https://serpapi.com/manage-api-key)

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1678526127714-4e66f3c7-1367-423f-96d9-1999125fa451.png#averageHue=%23a6b387&clientId=u768ff4bf-aa4f-4&from=paste&height=455&id=u810704be&originHeight=910&originWidth=3294&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=128329&status=done&style=none&taskId=ub1f4968d-9984-4d74-b276-546d5f8b36f&title=&width=1647)

最后，就是需要申请到一个EXHUMAN的**API KEY**了。这一步，可以做到自定义上传自己的头像。
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1678527134124-79fe8577-8e67-4346-8876-95a16eee3b5a.png#averageHue=%2385a5ae&clientId=u768ff4bf-aa4f-4&from=paste&height=640&id=u291c3571&originHeight=1280&originWidth=3111&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=725401&status=done&style=none&taskId=u330a3544-d51c-41db-b516-e3ae93a968f&title=&width=1555.5)
但要拿到API KEY，则需要49美元一个月。这个价格还不便宜的。😭
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1678527096039-fcc60863-6831-44e0-b00c-3a8fc37a55a7.png#averageHue=%23575b52&clientId=u768ff4bf-aa4f-4&from=paste&height=890&id=u593e1997&originHeight=1780&originWidth=2923&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=274663&status=done&style=none&taskId=u4f851661-7a82-4553-a208-47527589b0c&title=&width=1461.5)

把上述申请到的API KEY放到代码上就可以了。

# 利用ChatGPT提取B站视频要点
在知乎上，看到网友“[小段同学的杂记](https://www.zhihu.com/column/666666)”做了一个**“长视频自动化摘要笔记完整工作流”**
> [https://zhuanlan.zhihu.com/p/610250035](https://zhuanlan.zhihu.com/p/610250035)


这个工具，有以下几个流程：

1. 遇到一个视频，通过它的 BVID 获取基本信息；
2. 自动抓取视频的字幕并解析；
3. 将视频的文本内容发送给 OpenAI API，要求其进行内容摘要；
4. 将视频的基本信息和 GPT-3.5 返回的摘要内容，填入 Notion 的相应页面。

总结来说，相当于利用ChatGPT来总结B站的视频，然后生成对应的摘要文字：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1678528700274-c0f744af-5538-4fcf-92c1-06f1f4e1c9cd.png#averageHue=%23f0f0f0&clientId=u768ff4bf-aa4f-4&from=paste&height=429&id=u48fc70fb&originHeight=858&originWidth=1664&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=840793&status=done&style=none&taskId=u177e42db-e4e1-44d3-b138-9ae73e9e034&title=&width=832)

最后导出到Notion文字笔记：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1678528662724-cf1b347a-b45d-4adf-bd21-434ad163b8cd.png#averageHue=%23f5f5f4&clientId=u768ff4bf-aa4f-4&from=paste&height=318&id=WbE70&originHeight=636&originWidth=1703&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=628835&status=done&style=none&taskId=uc7c1c05a-ea3d-4537-a58b-1524abfe160&title=&width=851.5)

以后，只要利用ChatGPT就能够很方便的对任一一个视频进行有效总结了。

# 开发个人的微信接口
具体可以参看这个github项目：
> [https://github.com/zhayujie/chatgpt-on-wechat](https://github.com/zhayujie/chatgpt-on-wechat)


部署的方法比较简单，把项目代码克隆下来
```python
git clone https://github.com/zhayujie/chatgpt-on-wechat
cd chatgpt-on-wechat/
```

然后安装对应的依赖包：
```python
pip3 install itchat-uos==1.5.0.dev0
pip3 install --upgrade openai
```
## 配置
配置文件的模板在根目录的config-template.json中，需复制该模板创建最终生效的 config.json 文件：
```python
cp config-template.json config.json
```

然后在config.json中填入配置，以下是对默认配置的说明，可根据需要进行自定义修改：
```python
# config.json文件内容示例
{ 
  "open_ai_api_key": "YOUR API KEY",                          # 填入上面创建的 OpenAI API KEY
  "proxy": "127.0.0.1:7890",                                  # 代理客户端的ip和端口
  "single_chat_prefix": ["bot", "@bot"],                      # 私聊时文本需要包含该前缀才能触发机器人回复
  "single_chat_reply_prefix": "[bot] ",                       # 私聊时自动回复的前缀，用于区分真人
  "group_chat_prefix": ["@bot"],                              # 群聊时包含该前缀则会触发机器人回复
  "group_name_white_list": ["ChatGPT测试群", "ChatGPT测试群2"], # 开启自动回复的群名称列表
  "image_create_prefix": ["画", "看", "找"],                   # 开启图片回复的前缀
  "conversation_max_tokens": 1000,                            # 支持上下文记忆的最多字符数
  "character_desc": "你是ChatGPT, 一个由OpenAI训练的大型语言模型, 你旨在回答并解决人们的任何问题，并且可以使用多种语言与人交流。"  # 人格描述
}
```

## 代理
国内需要设置对应的代理, 使用方法可以参考这个项目：
>  [https://github.com/Ice-Hazymoon/openai-scf-proxy](https://github.com/Ice-Hazymoon/openai-scf-proxy)

得到类似于 : [https://service-aaaaa.hk.apigw.tencentcs.com/](https://service-aaaaa.hk.apigw.tencentcs.com/) 的地址后在 app.py中添加以下代码
```python
openai.api_base = "https://service-aaaaa.hk.apigw.tencentcs.com/v1"
```

最后就可以在微信上调用ChatGPT接口了

**例如可以在个人聊天中输入信息：**
![](https://github.com/zhayujie/chatgpt-on-wechat/raw/master/docs/images/single-chat-sample.jpg#from=url&id=S7J6I&originHeight=1114&originWidth=1750&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&status=done&style=none&title=)

**或者在群组进行聊天：**
![](https://github.com/zhayujie/chatgpt-on-wechat/raw/master/docs/images/group-chat-sample.jpg#from=url&id=skSgh&originHeight=1288&originWidth=1652&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&status=done&style=none&title=)

**还可以调用Dall-E模型，进行图像生成：**
![](https://github.com/zhayujie/chatgpt-on-wechat/raw/master/docs/images/image-create-sample.jpg#from=url&id=p8MXi&originHeight=525&originWidth=800&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&status=done&style=none&title=)

好了，以上就是本期的全部内容了，我是leo，欢迎关注我的公众号“算法一只狗”。
![qrcode_for_gh_f4f620aeff8d_258.jpg](https://cdn.nlark.com/yuque/0/2023/jpeg/29330410/1678684487029-cf4fae99-cc6b-4741-98bc-3d85f2740248.jpeg#averageHue=%23a6a4a3&clientId=u77716545-c2eb-4&from=paste&height=215&id=ubf9a4520&originHeight=258&originWidth=258&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=27597&status=done&style=none&taskId=u4b600bb6-16bd-4623-bcb4-5103fd8eb21&title=&width=214.9999914566679)
