OpenAI刚刚开放了ChatGPT的API，该模型被称为**“gpt-3.5-turbo”**，“turbo”意味着更快更强大。

使用gpt-3.5-turbo构建自己的应用程序，可以为你扩展更多的操作：

- 起草电子邮件或其他写作 
- 编写Python代码 
- 回答有关一组文档的问题 
- 创建对话代理 
- 为您的软件提供自然语言界面 
- 在多个学科中进行教学 
- 翻译语言 
- 模拟视频游戏角色等等 

它比原有的“gpt-2”模型更加灵活、快速和便宜。

仅需要几行代码，就可以快速构建你自己的对话机器人。
```python
import openai

openai.api_key = "your apk key"

messages = [
    {"role": "system", "content": "You are a kind helpful assistant."},
]

while True:
    message = input("User : ")
    if message:
        messages.append(
            {"role": "user", "content": message},
        )
        chat = openai.ChatCompletion.create(
            model="gpt-3.5-turbo", messages=messages
        )
    
    reply = chat.choices[0].message.content
    print(f"ChatGPT: {reply}")
    messages.append({"role": "assistant", "content": reply})
```

目前已经有很多国外的软件基于ChatGPT，构建了自己的AI。

**Yabble**是一家利用人工智能技术为客户提供业务战略建议的公司。他们创建了一个平台，让用户可以轻松地分析通过调查或客户反馈表格分享的数千个客户数据点，并提供清晰的数据支持的见解。

![yabble-cover.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1677902913536-e3d6dd11-a442-4b32-9e05-d99888e0dbb6.png#clientId=u24bb8bae-ee75-4&from=paste&height=420&id=udfd7b715&originHeight=840&originWidth=840&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=9681&status=done&style=none&taskId=u372eaf4a-2d04-4fa7-ba57-45ff452c443&title=&width=420)

**Inworld AI **使用 GPT-3 创建下一代人工智能角色：

![InworldAI.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1677902906983-37c8260c-2889-4eca-895c-c0beaeb84257.png#clientId=u24bb8bae-ee75-4&from=paste&height=825&id=u9ad532c1&originHeight=1650&originWidth=1650&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=56277&status=done&style=none&taskId=u6f3b678b-d37e-4c3b-9f46-e710be4d075&title=&width=825)

目前的定价为每1千个tokens收费0.002美元，大约相当于700个单词。我们需要注意的是，输入和输出文本都将消耗tokens。可以做简单计算一下，如果您有18美元的免费额度，则可以输入和输出总计6300000个英文单词。对于个人用户而言，免费账户可以使用很长一段时间。

如果需要日常使用，则可以进行充值。

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1677902520085-83672652-650e-4317-9dd7-bf3156c7a5ed.png#averageHue=%23fbfbfb&clientId=u24bb8bae-ee75-4&from=paste&height=587&id=u41b2ccc2&originHeight=1174&originWidth=3721&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=107009&status=done&style=none&taskId=u137865a9-f663-4981-8eee-686c8bd12aa&title=&width=1860.5)

当然，为了方便，我们也可以基于这个API构建自己的网站。下面我们来具体介绍一下怎么构建。

# 定制你的私人聊天网站
构建你的聊天机器人，首先需要拿到Openai的API key。当然你还是需要科学上网，申请到Openai的行号

然后在个人页面上找到自己的API key：

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1677901530035-4e07f42c-e937-4fde-a78b-a3ba9ddc10fc.png#averageHue=%23fefdfd&clientId=u24bb8bae-ee75-4&from=paste&height=530&id=uccdbdd86&originHeight=1060&originWidth=3777&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=206129&status=done&style=none&taskId=ubcc1ff67-d536-4f91-97e4-72b1b7d4e4f&title=&width=1888.5)

接下来，我已经把对应的代码放到GitHub仓库上：
> [https://github.com/llq20133100095/ChatGPTDemoAPI](https://github.com/llq20133100095/ChatGPTDemoAPI)


然后把代码克隆下来后，需要安装对应的包：
```bash
pip install openai
pip install gradio
```

最后运行代码就可以了：
```python
python app_v2.py
```

打开对应的网站，就可以进行愉快的对话拉

[![](https://github.com/llq20133100095/ChatGPTDemoAPI/raw/main/pictures/QQ%E6%88%AA%E5%9B%BE20230304110600.png#from=url&id=NJBzJ&originHeight=179&originWidth=2183&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&status=done&style=none&title=)](https://github.com/llq20133100095/ChatGPTDemoAPI/blob/main/pictures/QQ%E6%88%AA%E5%9B%BE20230304110600.png)

[![](https://github.com/llq20133100095/ChatGPTDemoAPI/raw/main/pictures/%E4%BC%81%E4%B8%9A%E5%BE%AE%E4%BF%A1%E6%88%AA%E5%9B%BE_16778992443380.png#from=url&id=SgP7h&originHeight=1723&originWidth=1688&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&status=done&style=none&title=)](https://github.com/llq20133100095/ChatGPTDemoAPI/blob/main/pictures/%E4%BC%81%E4%B8%9A%E5%BE%AE%E4%BF%A1%E6%88%AA%E5%9B%BE_16778992443380.png)

以上就是本期内容了，我是leo，欢迎关注我的公众号“算法一只狗”，我们下期再见~

![qrcode_for_gh_f4f620aeff8d_258.jpg](https://cdn.nlark.com/yuque/0/2023/jpeg/29330410/1677903247245-ba312e2c-42c3-4105-b558-386f0349e6f1.jpeg#averageHue=%23a6a4a3&clientId=u24bb8bae-ee75-4&from=paste&height=297&id=u5e05f21f&originHeight=258&originWidth=258&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=27597&status=done&style=none&taskId=uce0140d5-e617-4c2d-92d3-2b9da0da986&title=&width=297)
