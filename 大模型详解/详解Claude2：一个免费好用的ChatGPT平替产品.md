还记得上星期OpenAI终于公布了GPT4 API接口和Code Interpreter插件，这一波的开放让大量用户体会到AI最新模型的强大能力。详情可以回看我之前写的文章：
[GPT4开放API和Code Interpreter！如何利用它们来提升你的工作效率](https://www.yuque.com/yuqueyonghumaryyq/fmvho1/mtcbnqzzwkbcbmd2?view=doc_embed)

看到AI大模型大有OpenAI统一天下的趋势，各大厂商终于还是坐不住了。这不，**Anthropic推出了ChatGPT的最强平替产品——Claude2。**而且最重要的是该软件免费申请，只要有账号就可以直接在国内使用。
![20230715002122.gif](https://cdn.nlark.com/yuque/0/2023/gif/29330410/1689351743788-07cc88e1-4410-4a6f-b36d-b494faff66fc.gif#averageHue=%23776a59&clientId=u84674817-1053-4&from=paste&height=178&id=ucc6ad671&originHeight=200&originWidth=218&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=505191&status=done&style=none&taskId=ufd0f9f43-2acf-4280-9718-b58eb1df747&title=&width=193.77777777777777)

Claude2和ChatGPT一样，也是一个大语言模型，对比于ChatGPT来说，有以下几个主要的优点：

- **免费注册使用（这里需要魔法上网）**
- Claude2支持100K 上下文，从价格上来看**比GPT4-4K便宜了4-5倍**
- 可以直接导入文档进行总结。目前ChatGPT只能解析网页内容，使用插件应用才能支持文档导入总结。**而Claude2本身就已经支持多个文档的导入，并可以概括文档之间的关系**
- 知识库对比ChatGPT更新，**知识截止时间是2023年初**
- 支持更长的上下文输入，**目前开放了10万tokens进行输入。**

当然也可以利用API接口调用其服务，从官网价格来看Claude2每1百万tokens仅需要花费$11：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1689350604456-ab6b23cb-4625-411f-9762-44209c845b90.png#averageHue=%23f3f0e9&clientId=u84674817-1053-4&from=paste&height=532&id=u77ccdfca&originHeight=599&originWidth=1167&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=88496&status=done&style=none&taskId=u56d7bf41-5571-4bb6-a649-bcc5d044ab1&title=&width=1037.3333333333333)

# 申请注册
目前要用到Claude2，可以登陆官网直接注册。最好用到美国IP进行注册就可以了，我这里用了谷歌浏览器的插件FreeVPN进行申请就可以了。
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1689410714677-542142d7-77b8-4b6d-95ff-408c87023452.png#averageHue=%23fdfcfb&clientId=u84674817-1053-4&from=paste&height=250&id=ua8a8b495&originHeight=281&originWidth=514&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=32348&status=done&style=none&taskId=u63472945-7976-46df-8620-09ff43f32a3&title=&width=456.8888888888889)
# 1.Claude2优化了哪些方面的能力
## 1.1 多语言和实用性能力提升

对比于1代Claude模型来说，Claude2主要提升在：

- 提升了模型的有用性和诚实度
- 对于无害性上，与1.3版本的效果类似

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1689406501992-217a8f6e-f538-403d-9573-9f243a57e56e.png#averageHue=%23faf7f4&clientId=u84674817-1053-4&from=paste&height=448&id=u72238645&originHeight=504&originWidth=837&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=46667&status=done&style=none&taskId=u62b43722-64be-42c5-9262-5c79043c6d1&title=&width=744)

- 同时，在多语言能力的处理上，使用Claude2将每个Flores 200数据集中的句子从英语翻译成目标语言，然后进行评估。实验中发现最新模型针对小语种Kannada、Lao等语言上有大幅度提升。

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1689407009616-a643559c-10bb-4e0f-bdeb-b3d52ebf6c12.png#averageHue=%23faf8f6&clientId=u84674817-1053-4&from=paste&height=513&id=u9f24688c&originHeight=577&originWidth=594&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=51166&status=done&style=none&taskId=u385cfbe0-722d-441d-8d45-2b8ee38694f&title=&width=528)

- 对于**GRE考试**来说，不同部分得分也有相应能力提升：

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1689407489449-2c1514b3-4d05-4092-99fe-e51019de2b5f.png#averageHue=%23f7f3f2&clientId=u84674817-1053-4&from=paste&height=158&id=u8af5bb30&originHeight=178&originWidth=660&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=32391&status=done&style=none&taskId=u9fbb9b96-abd5-4f5b-878e-9d3935e9531&title=&width=586.6666666666666)

## 1.2 更长的上下文处理
Claude在一代的时候，处理上下文已经达到了9K，而2代更是扩展到了200K个tokens，也就是相当于可以一次性处理15万个词语。目前在开放的对话中，暂时支持100K的tokens，以后会逐步开放
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1689407297432-9cbd4094-a451-459b-9e2c-92469616e940.png#averageHue=%23f8f5f3&clientId=u84674817-1053-4&from=paste&height=430&id=ude0db57b&originHeight=484&originWidth=808&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=54861&status=done&style=none&taskId=u6621e1e8-c222-4597-8768-b58e5812202&title=&width=718.2222222222222)

# 2.有趣的使用技巧
## 2.1 文档对话能力
我们知道，目前有一众收费的ChatPDF等文档问答网站，这些网站或者插件都是基于ChatGPT的功能去做的。

而Claude2直接可以说秒杀这些大部分的网站插件。它本身就支持文档对话，而且原生就支持100K的上下文进行输入。

可以看到官网的上就可以直接上传文档进行对话了：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1689411175490-a9d33267-14f8-4772-8faf-a3d8203a4ffa.png#averageHue=%23dedad3&clientId=u84674817-1053-4&from=paste&height=509&id=u95b2ed73&originHeight=573&originWidth=787&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=64125&status=done&style=none&taskId=u2439e04a-d1f3-4c7a-9e49-2312272c1d7&title=&width=699.5555555555555)

而且最大可以上传5个文件，每个文件最大可以10MB.

比如我这里把Claude2的技术文档上传上去，让它进行总结。它能够在几秒内把PDF进行总结：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1689411823845-3751f17f-c312-49b0-baec-b9815fea43c6.png#averageHue=%23ecebe8&clientId=u84674817-1053-4&from=paste&height=666&id=ueb44494c&originHeight=749&originWidth=1012&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=136960&status=done&style=none&taskId=u72e3654e-6cad-4449-b931-2f5d8060bd3&title=&width=899.5555555555555)

同时也可以不断询问文档中的细节，这个能力和ChatPDF相当：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1689411946632-186b9598-0adb-44ae-833b-421e9b00ecaf.png#averageHue=%23ededeb&clientId=u84674817-1053-4&from=paste&height=571&id=uc3af6a27&originHeight=642&originWidth=939&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=123647&status=done&style=none&taskId=ud703aed6-815b-4dac-b852-17e2c08afc4&title=&width=834.6666666666666)

当然，我们也能够利用它的能力，进行excel数据分析：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1689413792586-ace7b7c6-33c8-452c-8b65-9cb1685d6d27.png#averageHue=%23edeceb&clientId=u84674817-1053-4&from=paste&height=390&id=u2085e6ed&originHeight=439&originWidth=1000&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=260845&status=done&style=none&taskId=u68ac820c-1024-4320-9763-3386eaa3552&title=&width=888.8888888888889)

## 2.2 文档联系功能
而且，只要我们上传更多的文档，就可以让它总结其中之间的联系，省去了我们看多个文档写总结的时间：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1689413850247-a5c81876-4879-4f03-bcdb-280b281f89dd.png#averageHue=%23eeedeb&clientId=u84674817-1053-4&from=paste&height=645&id=u3c85a29e&originHeight=726&originWidth=942&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=103214&status=done&style=none&taskId=ub0b179e7-4b98-43ca-bfde-c1dd55e063b&title=&width=837.3333333333334)

# 3.Anthropic公司趣闻
说起这家Anthropic公司，其目标是成为一家研究人工智能安全和有益发展的公司，且由Dario Amodei和Daniela Amodei兄妹两于2021年创立。而且Dario Amodei曾在Open AI担任研究副总裁，领导了GPT-2和GPT-3等重要项目的开发。
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1689414227985-b8df3be0-9a9b-4200-bdcf-b52cfac6e304.png#averageHue=%23e2e1dd&clientId=u84674817-1053-4&from=paste&height=740&id=u5abb9a4d&originHeight=832&originWidth=1790&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=223686&status=done&style=none&taskId=u26bd9ce7-7a00-4f2f-8ba1-1ded3b3d1cc&title=&width=1591.111111111111)

所有说这家公司和OpenAI还是有一定的渊源的。只是因为后来，由于微软对OpenAI的投资，使其变成了专属于微软的CloseAI，Dario对其心存不满，因此就自立门户，创建了这家公司。

后续谷歌也对Anthropic公司进行了投资，因此这两家公司的竞争，也成为AI界的一大亮点。

好了，以上就是本期的所有内容了，我是leo，我们下期再见~
![qrcode_for_gh_f4f620aeff8d_258.jpg](https://cdn.nlark.com/yuque/0/2023/jpeg/29330410/1689414264722-0c503cd8-c54c-438c-a0e6-8599cafdcbdc.jpeg#averageHue=%23a6a4a3&clientId=u84674817-1053-4&from=paste&height=229&id=u4f6d96df&originHeight=258&originWidth=258&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=27597&status=done&style=none&taskId=u4b766f4a-1af9-4325-b374-ad068122d44&title=&width=229.33333333333334)

**

