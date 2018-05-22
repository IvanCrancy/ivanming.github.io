---
layout: post
title: Python爬虫--根据关键词筛选豆瓣租房小组的帖子
date: 2018-05-23
excerpt: "租房好难啊····"
tags: [Python, 技术向]
feature: https://ivancrancy.github.io/ivanming.github.io/assets/img/post_image/features/10.png
comments: false
---
### 背景
最近租的房子到期了，然而没找到合适的是有一起合租，所以只能退租。
心水的话，是想找到一个一房一厅的户型，在豆瓣上找了很久，然而豆瓣的帖子太乱太杂了，筛选起来太麻烦了，所以萌生了做一个爬虫的想法，根据关键词来爬取合适自己需求的帖子。

### 思路
我先将我想住的地址附近的关键字，如地铁站名，公路名，小区名等存起来【不知道去百度地图搜--附近的小区】，然后我去爬信息的标题，标题里一旦出现关键字，我就将这个url存下来，然后我自己可以一个个点进去看，看房子信息如何。

我的代码非常简单，也没有做任何的伪装，更没有开线程，所以···豆瓣很快就把我的IP封了···

不过没关系，这个爬虫足足跑了5分多钟，豆瓣的反爬虫才有反应，然而我已经拿到了600多条数据了，足够我去筛选了。


### 以下是代码

````        
<span style="font-size:14px;"># -*- coding: utf-8 -*-  
import urllib2  
from bs4 import BeautifulSoup  
  
start=0  
end=100  
page_size=25  
key_words=["客村","赤岗","鹭江","厦滘","大石"]  
key_words.extend(["新鸿花园","华景园","海天花苑","御景雅苑","丽庭雅苑","珠影","御景阁","中大北门","滨江东路","新港中路"])  
key_words.extend(["地铁八号线","8号线","地铁三号线","3号线","5分钟路程"])  
key_words.extend(["一房一厅","长租","男女不限"])  
  
href_start=18  
href_end=63  
title_start=72  
  
out_file=open("/Users/Ivan/Codes/douban_room/result.csv","w+")  
# 将爬虫结果保存为CSV文件，方便日后慢慢点击和添加备注信息
  
def crawl_douban_room():  
    for i in range(end):  
        url="https://www.douban.com/group/haizhuzufang/discussion?start=0"+str(i*25)
        # 这里是我要爬取的小组的地址，从第一页开始爬；

        req=urllib2.Request(url)  
        response=urllib2.urlopen(req).read()  
        soup=BeautifulSoup(response,"html5lib")  
        info=soup.select("table.olt tbody tr")  
        for child in info[1:]:  
            content=child.select("td.title a")[0].prettify().encode('utf-8')  
            href=content[href_start:href_end]  
            title_end=content.find('">')  
            title=content[title_start:title_end]  
            for key_word in key_words:  
                if title.find(key_word)!=-1:  
                    print >> out_file, href,title  
                    break  
          
if __name__=="__main__":  
    crawl_douban_room()  
      
</span>  
````


现在仍然在疯狂刷帖ing····

### 找房子好难啊！！！！！！