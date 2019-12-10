## PRD 价值主张设计
### 加值宣言
---
生物图鉴APP调用生物识别API，对用户上传的生物照片进行识别，以文字档案的样式展示生物信息，鼓励持用户在APP内和其他用户交流、分享生物信息，增强用户对大自然的兴趣，拓宽生物方面的见识。倡导用户了解各种生物的基本习性，并以此更有效地保护生物多样性。

### 目标
---
* 看见新奇生物，即刻拿起手机拍照“捕捉”，成为生物收录大师。
* 与其他用户交换图鉴信息，以点亮更多地图模块。

### 战略背景
---
我国是世界上生物多样性最为丰富的国家之一，但现今部分生态系统功能不断退化，内陆淡水生态系统受到威胁，部分重要湿地退化。物种濒危程度加剧，据估计，我国野生高等植物濒危比例达15%—20%。遗传资源不断丧失和流失，一些农作物野生近缘种的生存环境遭受破坏，栖息地丧失。

今年联合国旗下权威机构生物多样性和生态系统服务政府间科学政策平台（IPBES）发布的报告宣布，在未来的10年将有100万个物种灭绝。我们已经进入了生物大灭绝的不可逆进程，改变生活、生产方式是重中之重。而回归到日常生活中我们能做到的就是加以了解，小心保护。一份小小的生物档案也可以成为这场生态攻坚战的开始。

### 核心价值
---
为用户提供动植物识别介绍服务，满足用户收集兴趣以及微社交需求。

### 核心价值与用户痛点
---
* 用户看见一种新奇生物想要了解，却不知道怎么贴切地描述其特征去搜索。
* 用户看见有趣的生物信息想和朋友分享。
* 用户希望参与环保工作，但是对生物习性不太了解。

### 人工智能概率性与用户痛点
---
* 用户使用拍照识别的时候，照片模糊、光线不足，影响识别。
* 人工智能识别错误，导致用户获取到错误的生物信息。

### 需求列表与人工智能API加值 
---
| 人工智能 | 用户需求 | 重要程度 |
| --------- | ------- | ------- |
| 智能植物识别 | 帮助用户了解上传照片中的植物品类的基本信息 | 非常重要 |
| 智能动物识别 | 帮助用户了解上传照片中的动物品类的基本信息 | 非常重要 |
| 调用地图API生成中国生物地图 | 生成用户个人的“生物图鉴”，记录用户收录的生物地域信息 | 次重要 |

## API产品使用
### 使用水平
---
**植物识别**

* Request

        Params
        image="图片的Base64编码"
        
        Post
        https://aip.baidubce.com/rest/2.0/image-classify/v1/plant?access_token="您的access_token"
        
        Header
        Content-Type:application/x-www-form-urlencoded

* Response

        {"log_id": "2496432657638288476",
	        "result": [
		{"score": 0.79263657331467,
			"name": "美人梅"},
		{"score": 0.63683325052261,
			"name": "樱花"},
		{"score": 0.037346817553043,
			"name": "垂丝海棠"}
        	]
        }

**动物识别**

* Request

        Params
        image="图片的Base64编码"
        
        Post
        https://aip.baidubce.com/rest/2.0/image-classify/v2/animal?access_token="您的access_token"
        
        Header
        Content-Type:application/x-www-form-urlencoded

* Response

		{"log_id": "7324262042776161066",
			"result": [
		{"score": "0.972855",
			"name": "国宝大熊猫"},
		{"score": "0.0183829",
			"name": "秦岭四宝"},
		{"score": "0.00248046",
			"name": "团团圆圆"},
		{"score": "0.0019389",
			"name": "圆仔"},
		{"score": "0.00134386",
			"name": "棕色大熊猫"},
		{"score": "0.000270675",
			"name": "小熊猫"}
			]
		}


### 使用比较分析
---
**种类对比**
* 百度AI
![百度图像技术](https://images.gitee.com/uploads/images/2019/1211/010747_7bd4fea3_1831462.jpeg "百度图像技术.jpg")

* 腾讯云AI
![腾讯云图像技术]!(https://images.gitee.com/uploads/images/2019/1211/010747_7bd4fea3_1831462.jpeg "百度图像技术.jpg")

* 阿里云AI

阿里云AI图像技术方面暂时不能满足生物图鉴APP的使用需求。
![阿里云图像技术](https://images.gitee.com/uploads/images/2019/1211/010950_62cc666f_1831462.png "阿里云.png")

**价格对比**
* 百度AI
![百度动物识别价格](https://images.gitee.com/uploads/images/2019/1211/011115_eed6ad8d_1831462.jpeg "百度动物识别.jpg")
![百度植物识别价格](https://images.gitee.com/uploads/images/2019/1211/011143_d951cfd1_1831462.jpeg "百度植物识别.jpg")

* 腾讯云AI
![腾讯云识别价格](https://images.gitee.com/uploads/images/2019/1211/011206_42cf8c96_1831462.png "腾讯云价格.png")

**对比结果**
* 价格
百度AI平台是国内几个平台中最便宜的，而且每日享有500次免费调用额度，识别失败不扣费。

* 种类
百度AI平台图像技术类发展较为成熟，种类更多，专业性更强。相比于其他AI平台没有或者笼统的图像识别，百度AI平台细分出了动物、植物智能识别API，能在APP中有更好的表现力。

* 总结
综上所述，在生物图鉴APP里，将采用百度动物智能识别API以及百度植物智能识别API.

### 使用后风险报告
---
> ILSRVRC（ImageNet 图像分类大赛） 比赛设置如下：
1000类图像分类问题，训练数据集126万张图像，验证集5万张，测试集10万张（标注未公布）。
评价标准采用 top-5 错误率——即对一张图像预测5个类别，只要有一个和人工标注类别相同就算对，否则算错。

* 近几年ILSRVRC 比赛结果如下表所示：

机构 | top-5错误率(%)|方法
---|---|---
Google|6.66|http://arxiv.org/abs/1409.484
rMSRA|4.94|http://arxiv.org/abs/1502.01852
Baidu|5.98|http://arxiv.org/abs/1501.02876
Oxford|7.33|http://arxiv.org/abs/1409.1556
NYU|11.7 |http://arxiv.org/abs/1311.2901
U.Toronto|16.4|http://www.cs.toronto.edu/~fritz/absps/imagenet.pdf
 
**识别失败后办法**
* 在失败界面中设置输入框，供用户手动输入关键词，进而重新识别
* 在失败界面输入框下针对动物或植物提供一定标签供用户选择，例如动物提供：“颜色”、“毛发长度”、“体型大小”等标签；植物提供：“高度”、“形状”、“颜色”等标签，帮助机器学习，重新识别。

* 在失败界面提供的标签下方提供已有高相似生物图片供用户辨认，查看是否为图中生物。

* 在最下方提供信息反馈界面跳转按钮，记录该次识别失败记录。