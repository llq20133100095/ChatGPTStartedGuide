
# 挑战不写一行代码！基于ChatGPT搭建自己的AI新闻总结工具

ChatGPT在生活中应用得最多的能力，当然要数其总结文章的能力。因此我们也不妨可以直接利用ChatGPT来实现一个自动AI新闻总结工具，把自己感兴趣的文章让它直接帮你总结。让ChatGPT快速帮你提炼要点，总结不同文章内容。

# 前期准备

1. 首先你当然需要有一个具体的ChatGPT账号，怎么申请可以看这篇文章：

[ChatGPT它还能玩出什么花来？](./账号申请和充值/ChatGPT它还能玩出什么花来？.md)

如果实在申请不了，也可以去某宝买一个账号，几十块就有了。

2. 然后要准备一个可以用的chatgpt 的api key，怎么申请信用卡和绑定教程可以看这里：

[账号申请和充值/ChatGPT账号申请+充值API和Plus账号](./账号申请和充值/ChatGPT账号申请+充值API和Plus账号.md)

本质上其实是在软件上申请一个虚拟的信用卡，信用卡充值需要用到USDT货币，就在殴易平台上充值就可以了。

3. 在官网上绑定信用卡后，就可以开始调用chatgpt的api key了

在个人页面上找到自己的API key：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1677901530035-4e07f42c-e937-4fde-a78b-a3ba9ddc10fc.png#averageHue=%23fefdfd&clientId=u24bb8bae-ee75-4&from=paste&height=530&id=uccdbdd86&originHeight=1060&originWidth=3777&originalType=binary&ratio=1.2000000476837158&rotation=0&showTitle=false&size=206129&status=done&style=none&taskId=ubcc1ff67-d536-4f91-97e4-72b1b7d4e4f&title=&width=1888.5)


# AI新闻爬虫
## 1.安装Selenium进行网页内容爬取
#### 安装selenium
```powershell
pip install selenium
```
#### 配置环境
（1）查看对应Chrome版本：
打开谷歌浏览器：浏览器输入地址

```javascript
chrome://version/
```
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1691813087622-f4f0d869-7fff-4ff3-93be-095d55e139c5.png#averageHue=%23f2f0f0&clientId=u1db345b5-f434-4&from=paste&height=365&id=ua9067b13&originHeight=411&originWidth=886&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=249209&status=done&style=none&taskId=u798c226b-6211-419a-b650-7453d4a9181&title=&width=787.5555555555555)
可以看到，版本号未99.0.4844.51
（2）下载Chrome谷歌浏览器对应版本的驱动: Chrome Drive
chromedriver下载网址： [http://chromedriver.storage.googleapis.com/index.html](http://chromedriver.storage.googleapis.com/index.html)
选择版本为99.0.4844.51:
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1691813100371-3a9d0c75-0310-4520-9879-fccf3b206309.png#averageHue=%23f5f0e9&clientId=u1db345b5-f434-4&from=paste&height=446&id=ubc2c917f&originHeight=502&originWidth=566&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=215973&status=done&style=none&taskId=uf58be244-26e8-4a66-adad-2ab5be668ad&title=&width=503.1111111111111)
解压后得到文件：chromedriver.exe，并把该文件放到python3中的Scripts中：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1691813112063-9749c2df-2167-4d00-bc8c-f13b1d6fb6dc.png#averageHue=%23fbf9f8&clientId=u1db345b5-f434-4&from=paste&height=487&id=u24e95b91&originHeight=548&originWidth=937&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=349022&status=done&style=none&taskId=ud4393782-f3d1-4fac-8741-e6f20f1f10c&title=&width=832.8888888888889)

#### 启动Selenium命令
利用chrome浏览器内核，就可以不启动窗口也可以登陆网站
```python
import time
from selenium import webdriver
 
# 1、创建Chrome实例 。
driver = webdriver.Chrome()
# 配置Chrome WebDriver的选项
options = Options()
options.add_argument("--headless")  # 以无头模式运行，即不显示浏览器窗口
# 添加不加载图片设置，提升速度
# options.add_argument('blink-settings=imagesEnabled=false')
# options.add_argument("interactive")
driver = webdriver.Chrome(options=options)
```

## 2.分析网站内容
这里主要爬取：[https://dataconomy.com/category/topics/data-science/artificial-intelligence/](https://dataconomy.com/category/topics/data-science/artificial-intelligence/)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1691813443090-945e0fa0-c6e5-4644-906b-92149331be95.png#averageHue=%238a8179&clientId=u1db345b5-f434-4&from=paste&height=553&id=u5fa861ab&originHeight=622&originWidth=1242&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=652992&status=done&style=none&taskId=udb99bcf5-6d42-4dfd-9243-2a80a62ca88&title=&width=1104)

比如我们点击上面网页的《tiktok wants to know》这篇文章的内容，然后F12打开开发者工具，发现需要爬取的内容包裹在了：div.content-inner
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1691813599767-38e3b689-a512-4e45-aa61-141794248fea.png#averageHue=%23d4dd99&clientId=u1db345b5-f434-4&from=paste&height=775&id=u8ebb8b66&originHeight=872&originWidth=1807&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=524737&status=done&style=none&taskId=u0fcb43f9-0009-416b-b3ac-cea6152bbe8&title=&width=1606.2222222222222)

因此我们可以询问ChatGPT，怎么基于这个网页进行爬取：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1691813966686-faa85e6a-3369-44e8-9110-f8a710436822.png#averageHue=%23b2caa6&clientId=u1db345b5-f434-4&from=paste&height=547&id=u9b3a12cd&originHeight=615&originWidth=671&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=49393&status=done&style=none&taskId=u2b465984-47a1-498b-9480-442b96c2653&title=&width=596.4444444444445)

然后ChatGPT就能给出相应的代码获取网页内容。

接着就可以调用ChatGPT的api_key，让他把刚刚那些内容进行总结：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1691828120616-e926ce19-abc2-47b6-9c3d-55334c9d6a8b.png#averageHue=%236dad85&clientId=u1db345b5-f434-4&from=paste&height=538&id=u39b52f73&originHeight=605&originWidth=545&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=40344&status=done&style=none&taskId=u0db5ac08-76fb-43f1-9372-06a895ed45b&title=&width=484.44444444444446)

得到ChatGPT总结的内容：

![image.png](https://cdn.nlark.com/yuque/0/2023/png/29330410/1691828360259-b0a22bb6-cf7d-46ca-8a41-2e777a79f091.png#averageHue=%233e3e37&clientId=u1db345b5-f434-4&from=paste&height=229&id=u3f454267&originHeight=258&originWidth=747&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=41130&status=done&style=none&taskId=ub9c8db8b-4260-4c19-99c2-f7efc2c1db9&title=&width=664)

# 总结
整体来看，利用ChatGPT就可以做到很好的闭环，不需要自己写大量的代码，就可以轻松实现一个爬虫+总结的工具。这个工具能够帮你一下子总结很多的内容文章，极大提高工作效率。所有代码存放在这里：，感兴趣的可以去下载来手动实现一下。

好了，以上就是本期的内容了，我是leo，我们下期再见~
![qrcode_for_gh_f4f620aeff8d_258.jpg](https://cdn.nlark.com/yuque/0/2023/jpeg/29330410/1691828548656-5ca04fb7-a311-4e71-97a5-9ac1b8bf4efd.jpeg#averageHue=%23a6a4a3&clientId=u1db345b5-f434-4&from=paste&height=229&id=u13bc0260&originHeight=258&originWidth=258&originalType=binary&ratio=1.3499999046325684&rotation=0&showTitle=false&size=27597&status=done&style=none&taskId=u9ca12fd2-c728-4652-a4ae-b5a3981ecf4&title=&width=229.33333333333334)

