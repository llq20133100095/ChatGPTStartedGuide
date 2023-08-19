
看到这个标题，你肯定以为我在吹牛了。我们都知道，单单ChatGPT模型的参数量级就在1750亿左右，而GPT4预估在上万亿了。对于这种大模型，每次训练都要花费大量的时间和算力，而且在推理的时候，更是需要运行在GPU上进行结果输出。

而这个项目，就是致力于使用小模型不断的逼近大模型的效果。

但是由于目前GPT4模型没有开源代码，那为啥这个项目又称为GPT4呢？本质上，它利用了Meta开源的LLaMA模型，在基于GPT4使用的数据集的情况下。最后在评估的时候，与GPT4的结果进行对比评估。

该项目的代码地址如下：
> [https://github.com/nomic-ai/gpt4all](https://github.com/nomic-ai/gpt4all)


# 

在收集样本的过程当中，使用GPT-3.5-Turbo OpenAI API在2023年3月20日至26日之间收集了大概一百万个提示对。为了获取更多的多样化信息，利用三个公开数据集（unifiedchip2、Stackoverflow Questions、Big-science/P3），**不同的数据集有不一样的聚集性，因此很好的促进数据集的多样化。**

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1684757776199-9729f60f-894c-4877-9c72-34c63217dee4.png#averageHue=%23f5e9e5&clientId=u05a1425f-bc30-4&from=paste&height=323&id=u08f83616&originHeight=278&originWidth=324&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=106885&status=done&style=none&taskId=u2027ad7b-51f8-49ed-b9e5-15030874299&title=&width=376)

从该论文中介绍，它主要是基于LLaMA  7B模型去微调，使用LoRA在437,605个样本上进行训练。

最后在模型对比上，某些任务是接近于GPT3.5和GPT4。

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1684758100645-28be9826-62d7-4022-9ee6-70daee0ad5c2.png#averageHue=%23fefefe&clientId=u05a1425f-bc30-4&from=paste&height=1600&id=u40e9b93e&originHeight=1920&originWidth=1242&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=416597&status=done&style=none&taskId=u42e738c1-4ec0-4fd0-8dfc-e22c9df51a6&title=&width=1034.9999588727967)

在模型的困惑度上，它对比了Alpaca-lora模型，数值越低表明越真实：

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1684813327834-92915a7e-0595-4bcd-a211-c4785e745f68.png#averageHue=%23f4f0eb&clientId=u2e2fdfcf-8dd3-4&from=paste&height=305&id=u45148a53&originHeight=366&originWidth=506&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=16364&status=done&style=none&taskId=uc97423d6-e586-4cae-b087-fa895da7796&title=&width=421.6666499111394)

而且主要它有一个优势就是可以运行在个人的CPU上。
 
# 使用方法
我们可以直接去官网下载起客户端
> [https://gpt4all.io/index.html](https://gpt4all.io/index.html)


安装好后，可以看到，从界面上提供了多个模型供我们下载。对比于ChatGPT的1750亿大参数，该项目提供的gpt4all模型仅仅需要70亿，所以它确实可以运行在我们的cpu上。

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1684728418860-dc3090af-a202-4870-a3e5-33f277b4a57b.png#averageHue=%233c3e45&clientId=u05a1425f-bc30-4&from=paste&height=938&id=u6207e7ce&originHeight=1126&originWidth=1922&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=218815&status=done&style=none&taskId=uab2b8613-2bd7-4105-8d6a-1e35dc18707&title=&width=1601.666603022154)


或者也可以直接使用python调用其模型。

首先需要安装对应的python包：
```
pip install gpt4all
```

把项目代码下载下来：
```
git clone --recurse-submodules https://github.com/nomic-ai/gpt4all
cd gpt4all/gpt4all-backend/
mkdir build
cd build
cmake ..
cmake --build . --parallel
```

设置对应的python包：
```
cd ../../gpt4all-bindings/python
pip3 install -e .
```

接着就可以在代码中进行调用了：
```python
from gpt4all import GPT4All

gptj = GPT4All("ggml-gpt4all-j-v1.3-groovy")
messages = [{"role": "user", "content": "Name 3 colors"}]
gptj.chat_completion(messages)
```

# 对比GPT4（必应）

## Q1：什么工作钱多事少离家近？


**GPT4All：金融行业（只说了一个答案）**

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1684827922534-49ad7ef3-978f-42f4-87ff-f33fcb1b7994.png#averageHue=%23474a59&clientId=u2e2fdfcf-8dd3-4&from=paste&height=237&id=u206524c0&originHeight=285&originWidth=1054&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=132417&status=done&style=none&taskId=u13ae82f9-e256-4fd5-a104-a2f944de4bc&title=&width=878.3332984315039)


**Bing：保险代理人、程序员、翻译、市场营销**

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1684815395807-f1014338-c766-4e74-82e8-4b6941686886.png#averageHue=%23e2e8f7&clientId=u2e2fdfcf-8dd3-4&from=paste&height=626&id=u9c880d3d&originHeight=751&originWidth=893&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=234660&status=done&style=none&taskId=u28bd7cee-b785-46f8-8cfa-345a6514b59&title=&width=744.1666370961412)

## Q2：一个三角形,如果一条边长为4cm,另一条边长为7cm,则第三条边最长可能是多少厘米?
## 

**GPT4All：5cm（答案错误）**

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1684842479634-4b994b40-0aef-421a-abf1-9ba9b77f6b80.png#averageHue=%23434553&clientId=ubdcac386-b027-4&from=paste&height=170&id=u7012d6f6&originHeight=204&originWidth=1049&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=31172&status=done&style=none&taskId=ub831e4b1-e9f3-4967-9b39-f75ee09ebd5&title=&width=874.1666319304056)

**Bing：10cm（答案正确）**

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1684835707107-e069c690-c754-43e8-9696-f14cf1ebbc0e.png#averageHue=%23c9d3f5&clientId=ubdcac386-b027-4&from=paste&height=364&id=uc5ca19cb&originHeight=437&originWidth=913&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=131168&status=done&style=none&taskId=u63d036b6-4de2-4ebc-9013-1a41b22d7c1&title=&width=760.8333031005342)

## Q3：用python写一个斐波拉契函数

**GPT4All：**

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1684843105423-28636ecc-0b1e-402c-b970-d563567fc34f.png#averageHue=%23444655&clientId=ubdcac386-b027-4&from=paste&height=276&id=u2f1cd61d&originHeight=331&originWidth=676&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=39042&status=done&style=none&taskId=ue01774d3-e588-4069-ac9e-607522ddcde&title=&width=563.3333109484787)


**Bing：**

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1684843215756-2f58bd66-f1b3-4650-853d-c70925ca898e.png#averageHue=%23e6eaf7&clientId=ubdcac386-b027-4&from=paste&height=739&id=u2c211346&originHeight=887&originWidth=914&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=194218&status=done&style=none&taskId=ua65ee0fb-dc51-4e00-9989-a053868de4b&title=&width=761.6666364007538)

从结果上看，GPT4ALL在数学计算上还是比GPT4差一点，但是在日常问题回答上还是可以的。

好了，以上就是本期的内容了，我是leo，我们下期再见~

![qrcode_for_gh_f4f620aeff8d_258.jpg](https://cdn.nlark.com/yuque/0/2023/jpeg/29330410/1684843258048-f02f7c43-fa7b-45e9-b5f5-407e2dc19f09.jpeg#averageHue=%23a6a4a3&clientId=ubdcac386-b027-4&from=paste&height=215&id=u42b2ea6f&originHeight=258&originWidth=258&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=27597&status=done&style=none&taskId=ue570be85-7a93-44fe-aeea-c09ace4442e&title=&width=214.9999914566679)


