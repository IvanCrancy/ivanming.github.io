---
layout: post
title: UI设计练手：TrashGo--一个垃圾分类app设计分享
date: 2019-08-10
excerpt: "练手作品：TrashGo，使用XD制作，附带动画效果"
tags: [产品, DESIGN]
feature: https://ivancrancy.github.io/ivanming.github.io/assets/img/post_image/190810/feature@2x.png
comments: false
---

### 这是个啥？

最近垃圾分类这个话题貌似挺火的，所以就打算画一个设计稿。刚好最近想学一下Adobe XD， 就拿来练一下了。

![](https://ivancrancy.github.io/ivanming.github.io/assets/img/post_image/190810/poster.png)

### 全部大图

![app首页，支持搜索和查看历史的分类记录](https://ivancrancy.github.io/ivanming.github.io/assets/img/post_image/190810/home@3x.png)
![查看历史的分类记录](https://ivancrancy.github.io/ivanming.github.io/assets/img/post_image/190810/history@3x.png)

点击可以将历史记录滑出来
![](https://ivancrancy.github.io/ivanming.github.io/assets/img/post_image/190810/home_history.GIF)


![动画效果](https://ivancrancy.github.io/ivanming.github.io/assets/img/post_image/190810/home_category.GIF)

要分类垃圾可以拍照并自动识别
![点击按钮可以拍照识别](https://ivancrancy.github.io/ivanming.github.io/assets/img/post_image/190810/category@3x.png)

![识别到结果后会自动显示垃圾类别](https://ivancrancy.github.io/ivanming.github.io/assets/img/post_image/190810/result@3x.png)
![识别结果有误的话可以手动输入文字并识别](https://ivancrancy.github.io/ivanming.github.io/assets/img/post_image/190810/tellus@3x.png)

![动画效果](https://ivancrancy.github.io/ivanming.github.io/assets/img/post_image/190810/2.GIF)

### 实现思路？
现在只画了UI···不过已经有了大概的方法来实现这个app

首先就是使用百度AI的识图SDK，这个SDK可以输入图片然后会返回string，再接着用这个string去调GitHub某大佬的python库，整套流程下来连数据库都用不上，搜索历史的话···就存在用户的本地缓存上好了哈哈哈哈哈。