GPT4是一个大型的多模态模型，虽然在许多现实世界场景中的能力不如人类，但在各种专业和学术基准上表现出人类水平的表现。

例如，它通过模拟律师考试，分数在应试者的前 10% 左右；相比之下，GPT-3.5 的得分在倒数 10% 左右。OpenAI花了 6 个月的时间，使用对抗性测试程序和 ChatGPT 的经验教训迭代调整 GPT-4，从而在真实性、可控性和拒绝超出回答边界方面取得了有史以来最好的结果（尽管远非完美）。

在过去的两年里，我们重建了整个深度学习堆栈。一年前，我们训练 GPT-3.5 作为系统的第一次“试运行”。我们发现并修复了一些错误并改进了我们的理论基础。结果，OpenaAI发现GPT-4 训练运行（至少对我们而言！）**前所未有地稳定，成为能够提前准确预测其训练性能的第一个大型模型。随着我们继续专注于可靠的扩展，我们的目标是完善我们的方法，以帮助我们越来越多地提前预测和准备未来的能力。（能够首先预测）**

目前OpenAI开放了对应的GPT-4接口，同时也可以加入waitlist进行等待体验。

# 1.GPT优化了哪些方面的能力
## 1.1 Capabilities能力
GPT-3.5和GPT-4对比来看，有以下几个区别：

- 在处理复杂任务上，GPT-4更可靠、更有创意，并且能够处理更细微的指令。
- 各种奥林匹克竞赛、GRE考试、代码考试、统一律师考试等测试上，GPT-4都基本完虐GPT-3.5

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1679215239747-15cc6957-832e-43a3-8e42-603e8ce17f16.png#averageHue=%23eddcb5&clientId=ud20041de-2300-4&from=paste&height=351&id=u85f4917b&originHeight=351&originWidth=451&originalType=binary&ratio=1&rotation=0&showTitle=false&size=26823&status=done&style=none&taskId=u3f54ebf1-06b5-495f-b8cf-bcd7d5b94b4&title=&width=451)

- 在机器学习的一些基准测试集上，也表现更加突出，达到了SOTA的水准，比大部分的语言模型效果要好：

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1679215281043-a9caf9cc-9c33-40d4-bf64-b5adbe78f484.png#averageHue=%23f8f7f6&clientId=ud20041de-2300-4&from=paste&height=237&id=uaf09d73e&originHeight=237&originWidth=930&originalType=binary&ratio=1&rotation=0&showTitle=false&size=29917&status=done&style=none&taskId=u5d85369e-6e57-425d-b88e-184bd52f81e&title=&width=930)

## 1.2 视觉输入能力Visual Inputs
对比与GPT-3来说，GPT-4主要新增在可以处理图像输入信息。但目前图像输入功能还在预览阶段，目前不能够体验到该功能。

官网上给了很多具体的例子，像它能够理解图片的笑话：**用一个VGA连接器去给手机充电**
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1679297523217-04174c7d-8280-4f83-8cfb-d8800191e61e.png#averageHue=%23a69880&clientId=ud20041de-2300-4&from=paste&height=811&id=ufacd2b2f&originHeight=973&originWidth=981&originalType=binary&ratio=1&rotation=0&showTitle=false&size=644703&status=done&style=none&taskId=ue93c2a61-b898-44ba-966f-7734ca39797&title=&width=817.4999675154698)

或者能知道整幅图的不寻常地方：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1679297762812-116f6a00-8035-4731-ae60-5187c54f576b.png#averageHue=%236c6749&clientId=ud20041de-2300-4&from=paste&height=563&id=ufe4aee0b&originHeight=676&originWidth=931&originalType=binary&ratio=1&rotation=0&showTitle=false&size=650458&status=done&style=none&taskId=u5cc35837-a900-4674-898b-3653c463a55&title=&width=775.8333025044877)

另外，GPT-4在解答数学问题的时候，也会给出一个比较详细的步骤：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1679298031000-dc53da4c-5db2-42e1-b145-93a9e37a3a53.png#averageHue=%23f0f0ef&clientId=ud20041de-2300-4&from=paste&height=1182&id=u7cf254cb&originHeight=1419&originWidth=1189&originalType=binary&ratio=1&rotation=0&showTitle=false&size=462892&status=done&style=none&taskId=ua5dfa53b-13c5-47e2-88f5-df099a75acd&title=&width=990.8332939611556)
## 1.3 可操纵性
GPT-4在不同风格和角色上，完成度相当高。给定了一个角色给它，它能够有效的执行下去。

比如在官方放出的例子上，它扮演一个**“苏格拉底式导师”，**在一开始设定好系统所扮演的角色之后，用户不断逼问它公式的答案，但是它仍然能够不卑不亢的引导用户进行学习。这样的角色定位，相当于一名小学教师了：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1679300553738-3b6c1d02-c5fb-4c42-803b-1c28d8d8b79a.png#averageHue=%23e7e6e5&clientId=ud20041de-2300-4&from=paste&height=1204&id=u53544349&originHeight=1445&originWidth=1338&originalType=binary&ratio=1&rotation=0&showTitle=false&size=185358&status=done&style=none&taskId=ub08fe09b-0f84-4b44-9e8a-5d5177f8e3b&title=&width=1114.9999556938824)


## 1.4 增强模型限制性
尽管功能强大，但 GPT-4 与早期的 GPT 模型具有相似的局限性。最重要的是，它仍然不完全可靠。这里OpenAI把它定义为幻觉：给出的事实式错误的，也就是一本正经胡说八道。

从实际的效果来看，GPT-4模型比以前的GPT-3.5模型能够显著减少幻觉性。并且准确得分比GPT-3.5高40%：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1679301644979-34be2858-0e26-45e8-9528-c8603e8747e8.png#averageHue=%23242623&clientId=ud20041de-2300-4&from=paste&height=368&id=uad28d7fd&originHeight=442&originWidth=706&originalType=binary&ratio=1&rotation=0&showTitle=false&size=27389&status=done&style=none&taskId=uc66cbfc3-17a6-4efa-bd1d-c22b71a1d5b&title=&width=588.333309955068)

在基础模型上，GPT-3.5和GPT-4模型的效果还相差不多，但是GPT-4模型在经过RLHF后训练，效果比GPT-3.5要好很多。
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1679302061690-9e805e00-7f59-4adf-8a86-0b2fa0b768cc.png#averageHue=%23f6f6f6&clientId=ud20041de-2300-4&from=paste&height=324&id=u0ded0f8c&originHeight=389&originWidth=689&originalType=binary&ratio=1&rotation=0&showTitle=false&size=17954&status=done&style=none&taskId=u0ac06113-eee5-495e-91d1-3f17fc90c8c&title=&width=574.1666438513341)


# 2.有趣的问题
## 2.1 校准能力在RLHF训练过后下降
GPT-4由于用到的数据是2021年9月之前的，因此如果你问他未来的事情的时候，往往会犯简单的推理错误。

或者，它也会在生成代码的时候，引入一个安全漏洞。

但其实，在基础预训练模型过后，OpenAI发现它的校准能力还是不错的。但是经过之后的训练步骤之后，发现整体模型的准则减少了。

比如左图是预训练过程之后，对答案的预测置信度通常与正确概率相匹配。**右图是经过RLHF流程之后，模型的校准能力大幅下降。**
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1679372229260-cb86d41d-3668-4b11-aea2-efa4a16a5774.png#averageHue=%23e9e9e6&clientId=ud20041de-2300-4&from=paste&height=388&id=u9218084d&originHeight=466&originWidth=980&originalType=binary&ratio=1&rotation=0&showTitle=false&size=131698&status=done&style=none&taskId=u49c1ee9b-af7d-40df-a60d-2c725f67e35&title=&width=816.6666342152503)

## 2.2 风险和缓解措施
GPT-4在奖励模型上，新增了一个安全奖励信号，用来减少有害信息的输出。这里面，OpenAI制定了对应的很对不安全的规则来提示模型：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1679401918360-2fef89e1-d547-4bf2-9d08-b7fae09a0d63.png#averageHue=%23f2f2f2&clientId=ud20041de-2300-4&from=paste&height=817&id=udb3db525&originHeight=980&originWidth=698&originalType=binary&ratio=1&rotation=0&showTitle=false&size=96228&status=done&style=none&taskId=u6a0875c7-609f-447f-a294-25c67175947&title=&width=581.6666435533109)

在结果上，GPT-4比GPT-3.5模型在有害信息的输出上少15%：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1679401809910-360a5efb-6827-478f-94ea-14b3e619109e.png#averageHue=%23ebecf6&clientId=ud20041de-2300-4&from=paste&height=335&id=u0ece39b5&originHeight=402&originWidth=717&originalType=binary&ratio=1&rotation=0&showTitle=false&size=15334&status=done&style=none&taskId=uc596cb98-ad89-40e4-a7f5-00afdc3c517&title=&width=597.4999762574841)

# 3.GPT-4训练过程
GPT-4模型过于强大，以致于广大读者一直都希望OpenAI能够公布实现细节。但是遗憾的是，OpenAI发布的GPT-4，不是**“Open的AI模型。”**
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1679402136372-14d952a8-70e1-48cf-95ee-a52007555dd2.png#averageHue=%23b8e2a8&clientId=ud20041de-2300-4&from=paste&height=520&id=u0ca9bcc4&originHeight=624&originWidth=665&originalType=binary&ratio=1&rotation=0&showTitle=false&size=216320&status=done&style=none&taskId=uead558f8-253e-417e-b92f-6c4f5b54c1f&title=&width=554.1666446460627)
大部分的人工智能专家认为，这不仅破坏了OpenAI作为研究机构的创始精神，而且让其他人难以制定保障措施来应对威胁。

从GPT-4放出的技术报告来看，OpenAI主要是出于竞争以及安全等方面的考虑，未公布模型规模等技术细节。这种趋势感觉会越演越烈，以至于有网友开始调抗GPT-4应该去掉**“Open“**两个字
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1679402392822-f4d70fc6-d395-4089-8427-103e40941809.png#averageHue=%23d9e1ec&clientId=ud20041de-2300-4&from=paste&height=571&id=u62d8504a&originHeight=685&originWidth=663&originalType=binary&ratio=1&rotation=0&showTitle=false&size=305214&status=done&style=none&taskId=u2d4ac552-d8d2-44ce-baad-8cf9c34796b&title=&width=552.4999780456234)

从GPT 2.0的开源，到GPT 3.0的只有论文，再到ChatGPT连论文也没有，直到GPT 4.0的技术报告更像效果评测报告。一个很明显的趋势是，OpenAI做实了CloseAI的名号，之后OpenAI的最前沿研究不会再放出论文。

但是我们也可以从技术报告中，看到一些技术细节。

## 3.1 大模型能力预测
与以前的GPT模型一样，在做预训练的时候，GPT模型在公开的数据集上，预测文档中的下一个单词。这些数据是一个网络规模的数据语料库，包括数学问题的正确和不正确的解决方案，弱和强推理，自相矛盾和一致的陈述，并代表各种各样的意识形态和思想。

同时也和GPT以前的模型一样，都使用了RLHF方法（基于人类进行反馈），用来尽量拟合用户的意图。**但是从上面来看，使用了RLHF方法之后，其实准确率反而会有所下降。**

另一个新的创新方法是：**OpenAI在大模型训练之前，做了一个预测大模型的任务。**

我们知道，GPT-3参数量在1750亿左右，那么保守估计，GPT-4模型参数量可能已经上万了。对于这种大模型，每次训练都要花费大量的时间和算力。万一在训练好之后，发现模型效果不行，那么就需要重新调整超参数。这样就又需要耗费大量的成本。

因此，OpenAI为了能够预估待训练的模型的能力，用小模型来预测某些参数组合下对应大模型的某种能力，如果预测足够精准，能够极大缩短炼丹周期，同时极大减少试错成本，所以无论理论价值还是实际价值巨大，这个绝对是非常值得认真研究具体技术方法的。

从下图可以看到：x轴是计算量，OpenAI利用了多个小型模型，来很好的预测出GPT-4的模型能力。
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1679453771237-fc07d77e-7e05-429a-ba92-16771c173c90.png#averageHue=%23fcfcfc&clientId=ud20041de-2300-4&from=paste&height=395&id=u31e5b4c2&originHeight=406&originWidth=708&originalType=binary&ratio=1&rotation=0&showTitle=false&size=16920&status=done&style=none&taskId=ua2c70ebe-5b37-400c-9922-601190b3c96&title=&width=689)
特别是在数据集[HumanEval](https://github.com/openai/human-eval)中，计算量可以有效减少1000倍。

## 3.2 整体模型流程
通过OpenAI放出的技术报告，有理由怀疑GPT-4的模型训练过程如下所示：
![](https://cdn.nlark.com/yuque/0/2023/jpeg/29330410/1679456608767-550348c9-81b2-4f5f-91a9-884bf0aafe0e.jpeg)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1679456620547-2f801c1a-b7c9-4ffe-8eba-eb7cb14883ba.png#averageHue=%23fdfcfc&clientId=ud20041de-2300-4&from=paste&height=858&id=u811c1cce&originHeight=1030&originWidth=1651&originalType=binary&ratio=1&rotation=0&showTitle=false&size=248111&status=done&style=none&taskId=u87744047-2dd4-497a-ad3f-0a81365c75b&title=&width=1375.8332786626308)
步骤如下：

- 准备预训练数据集
- 利用小模型，来确定要训练的GPT模型的参数
- 利用RLHF方法，从预训练开始到强化学习阶段，这部分为主要阶段
- 安全性评估
- RBRMs（基于规则奖励）方法：在GPT-4训练过程中，额外提供一个奖励信号，当模型输出有害信息时，则拒绝这些请求。

# 4.总结
整体看下来，GPT-4模型可能不是创新力度最大的模型，但确实在与人交互上达到了目前AI的最高水平。其在理解人类语言上，是一个里程碑式的工作。

但GPT-4也存在一些挑战和局限性，比如数据质量、安全性、可解释性等。更多人希望看到更多开放、创新、合作的研究成果，推动整体AI领域的发展。我也期望着这一天的到来。

以上就是本期的全部内容了。我是leo，我们下期再见~
![qrcode_for_gh_f4f620aeff8d_258.jpg](https://cdn.nlark.com/yuque/0/2023/jpeg/29330410/1679456968279-abd0b0e7-0854-426f-90b7-6b46b55a8c2d.jpeg#averageHue=%23a6a4a3&clientId=ud20041de-2300-4&from=paste&height=215&id=ubdcbfe17&originHeight=258&originWidth=258&originalType=binary&ratio=1&rotation=0&showTitle=false&size=27597&status=done&style=none&taskId=u83e4c991-b84c-4f33-b59a-fd74e27d12b&title=&width=214.9999914566679)


