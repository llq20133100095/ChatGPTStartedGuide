在上一年的时候，我曾经写过一篇关于《我的世界》的强化学习AI文章。感兴趣的读者可以看看这篇文章：

[让AI玩《我的世界》](https://zhuanlan.zhihu.com/p/536735680?utm_id=0)

在之前的强化学习AI中，**OpenAI利用《我的世界》的玩家视频来学习，训练出超大的预训练模型VPT。**
![](https://cdn.nlark.com/yuque/0/2023/png/29330410/1685179851039-8cc6b30f-5b0f-4f22-9b74-37253dff3271.png#averageHue=%23ebf2f6&clientId=ued902873-adab-4&from=paste&id=GCZdH&originHeight=494&originWidth=1080&originalType=url&ratio=1&rotation=0&showTitle=false&status=done&style=none&taskId=u5d945200-01f3-4992-a91c-7d4c3470d02&title=)

但是在之前的智能体中，往往需要训练一个模型，利用强化学习或者监督学习的方法来提升智能体的效果。

而英伟达这一次直接利用LLM大模型，构造出了Voyager，通过接入GPT4来让模型自我探索，实现真正的自我驱动学习。

模型中主要由三个关键组件构成：

- 自动教程：可以最大化智能体进行探索
- 存储和检索复杂行为：不断添加可执行代码技能库
- 程序改进：新的迭代提示机制，包含环境反馈、执行错误和自我验证

相比于以前的智能体，Voyager模型最大的优势在于，它不需要进行模型参数微调。它主要通过黑盒查询与GPT4进行交互，从而不断强化技能组合的开发，这能够有效避免旧有技能的灾难性遗忘。

在实际的表现中，Voyager能够进行上下文的终身学习能力，并且在《我的世界》这款游戏中表现出人类玩家的熟练程度。从下图可以看出，**它获得重要独特的物品量级比以前的模型要高3.3倍。整体旅行旅行时间延长了 2.3 倍 距离，并解锁关键科技树里程碑的速度比之前的 SOTA 快 15.3 倍**。
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1685320887738-d75e7d33-c53a-4c11-8b27-b2fc4af2fd65.png#averageHue=%23f2efed&clientId=ued902873-adab-4&from=paste&height=745&id=t7Kdz&originHeight=745&originWidth=1196&originalType=binary&ratio=1&rotation=0&showTitle=false&size=238488&status=done&style=none&taskId=ue534d552-80c2-4142-9695-3fe00546378&title=&width=1196)

最为重要的是，研究人员发现，Voyager能够在一个新的《我的世界》的环境中，利用学到的技能库从头开始解决新任务，这说明其具有一定的技能保存能力。

# 该智能体能做什么？
接入GPT4进行自我驱动，该模型能够学习到一些复杂的行为，比如在《我的世界》中：

> **与末影人战斗**

![](https://cdn.nlark.com/yuque/0/2023/gif/29330410/1685322739417-004b7a9b-6707-4fc6-b98f-e33b80f288f9.gif#averageHue=%230a0a00&clientId=ued902873-adab-4&from=paste&id=wEJd6&originHeight=360&originWidth=640&originalType=url&ratio=1&rotation=0&showTitle=false&status=done&style=none&taskId=ua6f56c70-2c57-46e8-b7ac-4c41b7dff2c&title=)

> **挖水晶**

![](https://cdn.nlark.com/yuque/0/2023/gif/29330410/1685322792325-a032ad43-19bb-47fc-8f76-079421e3e23d.gif#averageHue=%23244855&clientId=ued902873-adab-4&from=paste&id=KyyUG&originHeight=360&originWidth=640&originalType=url&ratio=1&rotation=0&showTitle=false&status=done&style=none&taskId=u04af446c-48c5-4254-a57b-b33b8a25e81&title=)

> **打猎**

![](https://cdn.nlark.com/yuque/0/2023/gif/29330410/1685322907487-40eee053-9975-4860-a54a-17d3f095a49b.gif#averageHue=%23385c42&clientId=ued902873-adab-4&from=paste&id=csUbq&originHeight=360&originWidth=640&originalType=url&ratio=1&rotation=0&showTitle=false&status=done&style=none&taskId=u0be2ea8d-4a19-45f0-9e61-0a5c2e61d58&title=)

实现的行为决策也可以更为复杂，比如

> **建造基地**

![](https://cdn.nlark.com/yuque/0/2023/gif/29330410/1685323358665-a69b9dee-019b-4676-9b8a-da8d7a404bd9.gif#averageHue=%232e3d33&clientId=ued902873-adab-4&from=paste&id=im1W9&originHeight=360&originWidth=640&originalType=url&ratio=1&rotation=0&showTitle=false&status=done&style=none&taskId=uc9d47dc8-2dad-42fa-a7dd-ac13bbaf0ae&title=)

整体来说，它能够学习到人类做出的正确行为决策，并进行自主学习和记忆相应的技能。
# 模型细节
前面也说到了，经典的AI智能体学习方法，一般来说包括强化学习（RL）和模仿学习，他们的目标是不断拟合真实玩家的操作，但是其往往缺乏广泛的系统探索、可解释性和泛化能力。

如果用现有的大语言模型（LLM），来预先封装好一系列行动知识和可执行策略的话，虽然他们可以适用于一些常用的行为决策中，但是并不能在较长时间内逐步获取、更新、积累和转移学习到的知识。

像《我的世界》这种开放世界来说，它本身并没有设定一个最终目标或者是一个固定情节，而是提供一个游戏世界，给玩家进行自我发挥。这就需要相应的智能体能够不断进行自我学习：
（1）根据其当前的技能水平和世界状态**提出合适的任务**，例如：**如果在AI知道自己深处在沙漠，则应该把目标偏向于挖掘仙人掌**
![Voyager - An Open-Ended Embodied Agent with Large Language Models[00_00_08--00_00_28].gif](https://cdn.nlark.com/yuque/0/2023/gif/29330410/1685324830761-6d265d97-6886-45b0-8277-60c92154a890.gif#averageHue=%23313c23&clientId=ued902873-adab-4&from=paste&height=226&id=IY3Is&originHeight=226&originWidth=400&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2644279&status=done&style=none&taskId=u5cd0b881-01a2-461b-83c8-9b2979568a9&title=&width=400)

（2）根据环境反馈完善技能，并将**掌握的技能提交到记忆中**以备将来重用（例如，与僵尸战斗类似于与蜘蛛战斗）

（3）**不断探索世界**，以自我驱动的方式寻找新的任务

Voyager的关键模块共有三个，从图上可以看出：**用于开放式探索的自动教程，用于日益复杂行为的技能库，以及使用代码作为操作空间的迭代提示机制。**
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1685331518018-d7cd867f-a76f-471f-831a-768517d612cf.png#averageHue=%23f3f2ea&clientId=ued902873-adab-4&from=paste&height=634&id=f9YvH&originHeight=634&originWidth=1441&originalType=binary&ratio=1&rotation=0&showTitle=false&size=317248&status=done&style=none&taskId=u35e93435-0016-48b8-a75f-3260f19d51f&title=&width=1441)

 
## 自动探索
作为一个自动探索教程，其主要嵌入了目前最强大的LLM模型GPT4，会考虑探索进度和智能体的状态，基于GPT4来尽可能探索多样的东西。
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1685335689178-a857daf8-8be7-4f77-9f64-1c271cbe171d.png#averageHue=%23cabfe7&clientId=ued902873-adab-4&from=paste&id=nd5nX&originHeight=1936&originWidth=5080&originalType=url&ratio=1&rotation=0&showTitle=false&size=2302405&status=done&style=none&taskId=u2375960c-1ec0-43ae-a50a-ec3dc45bd42&title=)

比如上面的例子可以知道：
当前智能体感知到环境有一把木镐和一些石头，那么GPT4会觉得你此时需要升级为石镐来提高效率。**因此它会安排智能体任务：制作 1 个石镐。**

## 技能库
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1685417365483-334fa3a5-7d97-40b6-8933-ca208c49e208.png#averageHue=%23f5f4ed&clientId=u8c7bb10c-0f51-4&from=paste&height=628&id=uf73bbf63&originHeight=706&originWidth=1470&originalType=binary&ratio=1.125&rotation=0&showTitle=false&size=241619&status=done&style=none&taskId=u8c58612e-8f74-4f29-973b-a7537e364a2&title=&width=1306.6666666666667)

每个技能都通过嵌入其描述来索引，可以在将来的类似情况下检索。

当面对新的提出的任务，模型执行查询来确定前 5 名相关技能。复杂的技能可以通过编写更简单的程序来合成，这能够增强智能体的旅行时间，迅速增强能力，减轻灾难性的遗忘。

## 迭代提示机制
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1685417633848-690fc7ab-4bb8-4692-9979-d5a9ea8c989c.png#averageHue=%23a7be8c&clientId=u8c7bb10c-0f51-4&from=paste&height=628&id=u96155124&originHeight=707&originWidth=1195&originalType=binary&ratio=1.125&rotation=0&showTitle=false&size=312607&status=done&style=none&taskId=u26f33e32-2718-47d6-9c1e-5590845de11&title=&width=1062.2222222222222)
**左：环境反馈。**GPT-4 意识到在制作棍子之前还需要 2 块木板。**右：执行错误。**GPT-4 意识到它应该制作一把木斧而不是金合欢斧，因为《我的世界》中没有金合欢斧。

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1685423831468-6cb78361-c316-4fbe-84a9-145782d439f2.png#averageHue=%23d7caf2&clientId=u8c7bb10c-0f51-4&from=paste&height=537&id=u55eaf82a&originHeight=604&originWidth=1498&originalType=binary&ratio=1.125&rotation=0&showTitle=false&size=268346&status=done&style=none&taskId=ub81954bb-a122-4c09-86f0-6b8a405aa2f&title=&width=1331.5555555555557)
**自我验证。**通过向 GPT-4 提供智能体的当前状态和任务，要求它充当批评者并通知研究人员程序是否完成了任务。此外，如果任务失败，它会提供 建议如何完成任务。

# 智能体整体效果

### 科技树精通
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1685423939818-bed7b801-5ae1-41f4-bf4a-c0fbe855f0fe.png#averageHue=%23ededed&clientId=u8c7bb10c-0f51-4&from=paste&id=u01e6d139&originHeight=352&originWidth=1828&originalType=url&ratio=1.125&rotation=0&showTitle=false&size=106074&status=done&style=none&taskId=u31f73e51-a9c2-448c-9794-ab471c0e533&title=)
在这个表里面，标记了《我的世界》中关键技能的掌握情况：**木制工具→石工具→铁工具→钻石工具，**其中“木制工具”最基础，而“钻石工具”则掌握难度较高。表中分数表示三次总运行中的成功试验数。**迭代次数越少，方法的效率就越高。**与Baseline模型相比较来说，Voyager解锁关键技能的速度提高15.3倍，并且**是唯一一个解锁科技树钻石工具的AI。**

### 地图旅行时间变长
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1685428945453-db7c6a7f-d5d8-4e36-81e4-318599b61c11.png#averageHue=%237fab3d&clientId=u8c7bb10c-0f51-4&from=paste&id=u2f7884af&originHeight=1532&originWidth=2855&originalType=url&ratio=1.125&rotation=0&showTitle=false&size=1077343&status=done&style=none&taskId=u0b675b94-6bc2-4297-aa85-befa44137fc&title=)

Voyager能够通过穿越各种地形来扩展旅行的距离，而Baseline智能体仅限于局部区域，这严重阻碍了他们发现新知识的能力。

### 智能体的泛化能力增强
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1685428944385-46f5271c-58c9-47b0-b49b-830ca2c1466d.png#averageHue=%23e8e8e8&clientId=u8c7bb10c-0f51-4&from=paste&id=uc7a11afe&originHeight=314&originWidth=1432&originalType=url&ratio=1.125&rotation=0&showTitle=false&size=93193&status=done&style=none&taskId=u6ff6e667-8264-4d5d-be94-f6e8e120387&title=)![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1685428945472-5497c22b-9eff-4ccd-9e99-c741c6fe8daa.png#averageHue=%23edeceb&clientId=u8c7bb10c-0f51-4&from=paste&id=u854c8cfe&originHeight=2878&originWidth=4132&originalType=url&ratio=1.125&rotation=0&showTitle=false&size=1018497&status=done&style=none&taskId=uaa381bae-907e-4659-83d0-87deb143adc&title=)

如果把游戏中的世界进行重置，Voyager也可以不断的解决大部分的任务，这是基于其技能库中存储的数据完成任务。

从整体的AI智能体效果来看，还是很令人经验的，并且这是第一个用LLM驱动来进行自主学习的游戏AI。它主要用到的就是GPT4来不断促进AI探索世界，丰富自己的技能，并且不需要认为干预。而且最大的优点在于不需要对模型参数进行调整，就可以得到通用型AI了。

好了，以上就是本期的全部内容了，我是leo，我们下期再见~
![qrcode_for_gh_f4f620aeff8d_258.jpg](https://cdn.nlark.com/yuque/0/2023/jpeg/29330410/1685431056074-38e6a5f3-cb1e-4333-a273-e9f9dcae8714.jpeg#averageHue=%23a6a4a3&clientId=u8c7bb10c-0f51-4&from=paste&height=229&id=u4681cbc8&originHeight=258&originWidth=258&originalType=binary&ratio=1.125&rotation=0&showTitle=false&size=27597&status=done&style=none&taskId=uf42706f9-cf28-4705-b69c-302f7051419&title=&width=229.33333333333334)

 
