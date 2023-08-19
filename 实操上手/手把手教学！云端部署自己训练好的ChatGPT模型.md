自从上一年出现的ChatGPT爆火之后，越来越多人开始期待能够训练一个自己的模型。但是由于OpenAI没有开源ChatGPT模型的代码，只能够调用其提供的API接口，因此想要训练自己的聊天机器人困难重重。

幸好，针对LLM的开源社区贡献了很多可以供我们自己训练的模型。比如Meta开源了对标GPT3模型的LLaMA模型，而斯坦福在其基础上，利用7B LLaMA模型和52K指令数据上进行微调，得到了[Alpaca](https://github.com/tatsu-lab/stanford_alpaca)模型。并在评估中，其效果和ChatGPT模型类似。

但是Alpaca对于普通的用户而言，还是难以进行训练。因此又出现了Alpaca-Lora，让我们能够在**消费级显卡中**，几小时内就可以完成Alpaca的微调工作。
> [https://github.com/tloen/alpaca-lora](https://github.com/tloen/alpaca-lora)


# 训练自己的模型
## 1.准备数据集
要训练自己的模型，首先要准备好数据集。这里面我们可以使用类似于instruct的方法，构造指令数据集结构：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1683033192361-60dc7108-f307-4efd-a60b-07539b10835b.png#averageHue=%23f8f8f8&clientId=u5eb482e8-9793-4&from=paste&height=248&id=r1dKg&originHeight=310&originWidth=1531&originalType=binary&ratio=1.25&rotation=0&showTitle=false&size=13269&status=done&style=none&taskId=uacdfd6a5-f4fe-4beb-8e43-d547248612d&title=&width=1224.8)
比如我们可以直接使用开源的中文数据集：Chinese-alpaca-lora
> [https://github.com/LC1332/Chinese-alpaca-lora/blob/main/data/trans_chinese_alpaca_data.json](https://github.com/LC1332/Chinese-alpaca-lora/blob/main/data/trans_chinese_alpaca_data.json)



## 2.下载开源代码
我们可以直接使用Alpaca-LoRA 的代码
```
git clone https://github.com/tloen/alpaca-lora.git
```

把刚刚的数据集放到文件夹alpaca-lora目录下。

构造对应的python环境，同时安装依赖库：
```
conda create -n alpaca python=3.9
conda activate alpaca
cd alpaca-lora
pip install -r requirements.txt
```

保证pytorch版本可用，如果下面命令如果输出是**True**，则说明pytorch安装成功：
```
import torch
torch.cuda.is_available()
```

## 3.开启训练
在训练开启之前，我们需要先下载LLaMA基础模型，可以去到huggingface上进行下载：
> [https://huggingface.co/decapoda-research/llama-7b-hf/tree/main](https://huggingface.co/decapoda-research/llama-7b-hf/tree/main)

由于国内有限制，只能一个一个把所有的文件进行下载，然后放到目录llama-7b-hf下：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1683033966434-77878295-cc23-466f-b95d-ef5363c0bd29.png#averageHue=%23e6c79d&clientId=u5eb482e8-9793-4&from=paste&height=645&id=u4e4a875d&originHeight=806&originWidth=1498&originalType=binary&ratio=1.25&rotation=0&showTitle=false&size=135791&status=done&style=none&taskId=u977945aa-bbb0-43a0-835d-a2bf6a58d9e&title=&width=1198.4)

开启训练模型，执行下面命令：
```
python finetune.py \
    --base_model 'llama-7b-hf' \
    --data_path './trans_chinese_alpaca_data.json' \
    --output_dir './lora-alpaca-zh'
```

- base_model：在huggingface中下载的模型
- data_path：数据集
- output_dir：微调过后，模型的输出目录

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1683036923653-1caabb47-08e1-4993-bf5c-4842bdbe5405.png#averageHue=%23403f3d&clientId=u5eb482e8-9793-4&from=paste&height=174&id=uc2f74e44&originHeight=218&originWidth=1399&originalType=binary&ratio=1.25&rotation=0&showTitle=false&size=28016&status=done&style=none&taskId=u6bbc815a-4130-48c4-bb15-9b7667b35e4&title=&width=1119.2)
模型训练后，就可以看到 lora-alpaca-zh 有模型生成了
# 云端模型部署
在这里，可以直接利用kaggle部署模型。

首先把对应的模型、数据集和代码放到kaggle notebook中：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1683035801128-2a3e3255-8e1e-4184-80a9-c81a5ec1ee0a.png#averageHue=%23d5ba8c&clientId=u5eb482e8-9793-4&from=paste&height=688&id=u7b0cdf9a&originHeight=860&originWidth=1839&originalType=binary&ratio=1.25&rotation=0&showTitle=false&size=172731&status=done&style=none&taskId=u54daab2a-6d9a-4cc1-8f70-fbf9b3cd5cc&title=&width=1471.2)

可以像我上面的部署一样，或者可以直接复制我的kaggle代码：
> [https://www.kaggle.com/code/llqdata/alpaca-lora](https://www.kaggle.com/code/llqdata/alpaca-lora)


同时需要设置GPU，打开网络：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1683035860994-0c2818d9-4028-4c7f-812c-aa5c872178dd.png#averageHue=%23fefbfb&clientId=u5eb482e8-9793-4&from=paste&height=513&id=u49c2451a&originHeight=641&originWidth=507&originalType=binary&ratio=1.25&rotation=0&showTitle=false&size=45743&status=done&style=none&taskId=u6a8c5274-d258-4644-9b44-2c2c7519168&title=&width=405.6)

保存代码后，点击 Open logs in Viewer，等待一定时间：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1683035665866-13e99498-ac32-4706-ae25-208920929963.png#averageHue=%23dbbc8d&clientId=u5eb482e8-9793-4&from=paste&height=698&id=uddaf5585&originHeight=873&originWidth=1008&originalType=binary&ratio=1.25&rotation=0&showTitle=false&size=131164&status=done&style=none&taskId=ua2a0ee66-8728-45e4-a90f-904b0c3536f&title=&width=806.4)

打开日志中生成的网页，就可以得到对话网页了：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1683036039305-2ec1a80d-5e92-4a2d-a2de-3df432b5c23b.png#averageHue=%23fefdfd&clientId=u5eb482e8-9793-4&from=paste&height=634&id=ud9fc8cce&originHeight=793&originWidth=1519&originalType=binary&ratio=1.25&rotation=0&showTitle=false&size=147592&status=done&style=none&taskId=u3da49adc-368a-48cb-8570-84a925d104b&title=&width=1215.2)

比如可以让它找出下面文章的主旨：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1683036385149-c9430662-d503-417f-8bc7-0556f1f1d862.png#averageHue=%23fefdfc&clientId=u5eb482e8-9793-4&from=paste&height=652&id=u8b33b388&originHeight=815&originWidth=1547&originalType=binary&ratio=1.25&rotation=0&showTitle=false&size=85354&status=done&style=none&taskId=u20deb417-54c1-4878-8bad-0ce41b6c4ca&title=&width=1237.6)

当然，这个网页可以在手机上运行的，这样就可以随时随地的和它进行对话了。

好了，以上就是所有教程的内容了，我是leo，我们下期再见~

