目前在开源大模型中，比较有名的是Meta的LLAMA模型系列和清华的ChatGLM模型。其中特别是在中文领域上，ChatGLM模型经过中文问答和对话的优化，更加符合中文使用者的偏好回答。

经过一段时间的迭代，ChatGLM模型引来了重大更新。新推出的2代版本叫ChatGLM2模型。它保留了初代模型的优秀特性，并引入了新的优点。

**首先其表现出更加强大的性能：**全面超越第一代模型，在多个数据集上有大幅度的提升，比初代模型在MMLU（+23%）、CEval（+33%）、GSM8K（+571%）、BBH（+60%）等方面具有更强的竞争力。
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1688213508228-88edb61e-7e8c-48c3-85ea-f25b3d9e4503.png#averageHue=%23fefdfc&clientId=ufedaf2c9-cc65-4&from=paste&height=507&id=u59139a91&originHeight=570&originWidth=1072&originalType=binary&ratio=1.125&rotation=0&showTitle=false&size=69236&status=done&style=none&taskId=u88cd9cf5-2f69-4d54-a3c3-0e10de9831c&title=&width=952.8888888888889)

**同时可以处理更长的文本**：第一代模型只能处理2K，到第二代模型扩展到了32K，同时还可以进行多轮次对话

**另一个优点可以节省推理空间：**利用Multi-Query Attention技术，ChatGLM2-6B具有更高效的推理速度和更低的显存占用。

在2048长度的文本输入下，其推理速度比ChaGLM第一代模型快13秒
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1688213736045-6c207ce6-b6a6-414e-849e-3f26852e8de8.png#averageHue=%23e0be8d&clientId=ufedaf2c9-cc65-4&from=paste&height=145&id=u8692ae06&originHeight=163&originWidth=388&originalType=binary&ratio=1.125&rotation=0&showTitle=false&size=13047&status=done&style=none&taskId=u2adfd31f-cb44-45c8-bbd5-29e1a3e5443&title=&width=344.8888888888889)

该项目目前已经有6.6K星：[https://github.com/THUDM](https://github.com/THUDM)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1688213462551-37524260-db1b-4d05-9fec-9f546c87ec88.png#averageHue=%230f141b&clientId=ufedaf2c9-cc65-4&from=paste&height=165&id=ua709e504&originHeight=186&originWidth=584&originalType=binary&ratio=1.125&rotation=0&showTitle=false&size=12578&status=done&style=none&taskId=u9b643d0d-d60a-44a8-8c8d-b9cf8aeef88&title=&width=519.1111111111111)

# 使用方法
如果要使用该模型，可以先下载github的仓库代码，然后安装对应的依赖包
```python
git clone https://github.com/THUDM/ChatGLM2-6B
cd ChatGLM2-6B
pip install -r requirements.txt
```

然后运行代码就可以了：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1688217491301-e095cc61-e4d3-4737-98e6-1a6be3722deb.png#averageHue=%23e7eaed&clientId=ufedaf2c9-cc65-4&from=paste&height=429&id=uf20c62f5&originHeight=483&originWidth=1031&originalType=binary&ratio=1.125&rotation=0&showTitle=false&size=59889&status=done&style=none&taskId=u0c34aa72-d5b3-4bb9-a663-f5ef3a0790a&title=&width=916.4444444444445)

# 对比GPT4（必应）
## Q1：什么工作钱多事少离家近？


**ChatGLM2：技术岗位、销售岗位、管理岗位、创意岗位**
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1688217805316-80c9032f-f485-4857-b736-c1b98b7a6c24.png#averageHue=%23f6f1cb&clientId=ufedaf2c9-cc65-4&from=paste&height=530&id=u47fff549&originHeight=596&originWidth=1529&originalType=binary&ratio=1.125&rotation=0&showTitle=false&size=109077&status=done&style=none&taskId=uf0f12987-93bb-48a2-a5e0-c762b8185a1&title=&width=1359.111111111111)


**Bing：保险代理人、程序员、翻译、市场营销**
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1684815395807-f1014338-c766-4e74-82e8-4b6941686886.png#averageHue=%23e2e8f7&clientId=u2e2fdfcf-8dd3-4&from=paste&height=626&id=u9c880d3d&originHeight=751&originWidth=893&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=234660&status=done&style=none&taskId=u28bd7cee-b785-46f8-8cfa-345a6514b59&title=&width=744.1666370961412)

## Q2：一个三角形,如果一条边长为4cm,另一条边长为7cm,则第三条边最长可能是多少厘米?
## 
**ChatGLM2：10cm（答案正确）**
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1688217874306-171ead3d-aa46-4fbf-9231-72e26785307d.png#averageHue=%23f6f9dc&clientId=ufedaf2c9-cc65-4&from=paste&height=516&id=u22429bb0&originHeight=581&originWidth=1547&originalType=binary&ratio=1.125&rotation=0&showTitle=false&size=71234&status=done&style=none&taskId=u16f27b28-0467-47f5-9d2e-7264a1faa6b&title=&width=1375.111111111111)

**Bing：10cm（答案正确）**
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1684835707107-e069c690-c754-43e8-9696-f14cf1ebbc0e.png#averageHue=%23c9d3f5&clientId=ubdcac386-b027-4&from=paste&height=364&id=uc5ca19cb&originHeight=437&originWidth=913&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=131168&status=done&style=none&taskId=u63d036b6-4de2-4ebc-9013-1a41b22d7c1&title=&width=760.8333031005342)

## Q3：用python写一个斐波拉契函数
**ChatGLM2：**
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1688217961925-e1efddbb-5bd3-48e0-acc1-6af460e7d34e.png#averageHue=%23ccdc9e&clientId=ufedaf2c9-cc65-4&from=paste&height=516&id=ua16490ed&originHeight=581&originWidth=1552&originalType=binary&ratio=1.125&rotation=0&showTitle=false&size=68033&status=done&style=none&taskId=ub69d0dc4-f973-44fb-9acf-29241f40585&title=&width=1379.5555555555557)


**Bing：**
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1684843215756-2f58bd66-f1b3-4650-853d-c70925ca898e.png#averageHue=%23e6eaf7&clientId=ubdcac386-b027-4&from=paste&height=739&id=u2c211346&originHeight=887&originWidth=914&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=194218&status=done&style=none&taskId=ua65ee0fb-dc51-4e00-9989-a053868de4b&title=&width=761.6666364007538)

从结果上看，ChatGLM2和GPT4的结果答案很相似，说明整体的模型效果确实能够不断接近GPT4了。

好了，以上就是本期的内容了，我是leo，我们下期再见~
![qrcode_for_gh_f4f620aeff8d_258.jpg](https://cdn.nlark.com/yuque/0/2023/jpeg/29330410/1684843258048-f02f7c43-fa7b-45e9-b5f5-407e2dc19f09.jpeg#averageHue=%23a6a4a3&clientId=ubdcac386-b027-4&from=paste&height=215&id=u42b2ea6f&originHeight=258&originWidth=258&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=27597&status=done&style=none&taskId=ue570be85-7a93-44fe-aeea-c09ace4442e&title=&width=214.9999914566679)

