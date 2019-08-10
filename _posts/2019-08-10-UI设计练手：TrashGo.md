---
layout: post
title: UI设计练手：TrashGo--一个垃圾分类app设计分享
date: 2019-08-10
excerpt: "练手作品：TrashGo，使用XD制作，附带动画效果"
tags: [产品, DESIGN]
feature: https://upload-images.jianshu.io/upload_images/7434288-d5e56b6a4286ba3d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240
comments: false
---

### 这是个啥？

最近垃圾分类这个话题貌似挺火的，所以就打算画一个设计稿。刚好最近想学一下Adobe XD， 就拿来练一下了。

![](https://upload-images.jianshu.io/upload_images/7434288-3e3572c026e4f19b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 全部大图

![app首页，支持搜索和查看历史的分类记录](https://upload-images.jianshu.io/upload_images/7434288-db3bc0c9ff9171dd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![查看历史的分类记录](https://upload-images.jianshu.io/upload_images/7434288-d83e38eb97dad08c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

点击可以将历史记录滑出来
![home_history.GIF](https://upload-images.jianshu.io/upload_images/7434288-f98631955f90236e.GIF?imageMogr2/auto-orient/strip)


![查看分类详情](https://upload-images.jianshu.io/upload_images/7434288-f1c87714ed902382.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![home_category.GIF](https://upload-images.jianshu.io/upload_images/7434288-a3a7bf00d082f8a5.GIF?imageMogr2/auto-orient/strip)



要分类垃圾可以拍照并自动识别
![点击按钮可以拍照识别](https://upload-images.jianshu.io/upload_images/7434288-80b1fbb4f87ef57f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![识别到结果后会自动显示垃圾类别](https://upload-images.jianshu.io/upload_images/7434288-8a57f36125bd2345.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![识别结果有误的话可以手动输入文字并识别](https://upload-images.jianshu.io/upload_images/7434288-f9ea649b29d8adc4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![动画效果](https://upload-images.jianshu.io/upload_images/7434288-ede0aba393880939.GIF?imageMogr2/auto-orient/strip)


### 实现思路？
现在只画了UI···不过已经有了大概的方法来实现这个app

首先就是使用百度AI的识图SDK，这个SDK可以输入图片然后会返回string，再接着用这个string去调GitHub某大佬的python库，整套流程下来连数据库都用不上，搜索历史的话···就存在用户的本地缓存上好了哈哈哈哈哈。