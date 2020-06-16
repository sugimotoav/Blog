---
title: "本地AV的终极管理方式"
date: 2020-06-16T01:05:43+08:00
toc: true
draft: false
---

<img src="https://cdn.jsdelivr.net/gh/zhaoleihello/ImageStore@master/Images/iShot2020-06-1602.14.03.jpg" width=600px title="更新中">

<!--more-->

我们来聊聊怎样的管理办法才是最终的解决方式(大言不惭, 哈哈哈).


像我这种懒人, 肯定最喜欢省事的办法, 新下的片儿找个固定文件夹移动过去就不管了, 就像我那外人看来凌乱的桌子一样, 什么都堆在那.

![0C76Tw](https://cdn.jsdelivr.net/gh/zhaoleihello/ImageStore@master/Images/0C76Tw.jpg)


我以前我的目录是这样的结构, emby那一套, 一看这个图片名字就知道是那套

![32Xs5f](https://cdn.jsdelivr.net/gh/zhaoleihello/ImageStore@master/Images/32Xs5f.png)

本来想借鉴一下他们的代码的, 结果发现个事, 读懂他们的代码还没自己写来的快.

他们写的肯定先对文件名正则匹配, 然后根据格式化过的字符串作为url的发送请求去从web上现找, 因为我有个数据库, 图片也早就下完了, 我根本不用去发送请求, 文件名也自己处理过了, 从本地数据库里查询一下就行了, 速度飞快.

emby这套, 我当时试了试图片后缀名不加"-fanart", nfo文件里准确的写入我自定义的图片名, 结果发现不行, emby识别不了, 最后只能改回来.

那时候免费的emby还不能硬件解码(现在我看倒是有白嫖方法开启硬件加速了), 我什么都弄完了一用才发现不能硬解, 电脑风扇转的厉害, 然后我就把它弃了, 直接不用了, 看片就去文件夹里点开看看.


去年觉得这么弄不行, 每次更新一批新片还得运行几次脚本, 找片也费劲, 我只想找某一部片, 得点半天鼠标去翻文件夹.

有人喜欢用系统自带的"标签", 用颜色标记那些特别喜欢的片子, 是个办法. 根据类型不同, 打不同颜色的标签, 也是个办法.

其实都是没有办法的办法, 但凡有更好的办法, 肯定不打标签, 五颜六色的怪乱的.

另外这种方式存放片子你一定会遇到一个尴尬的事:

![7nQRX5](https://cdn.jsdelivr.net/gh/zhaoleihello/ImageStore@master/Images/7nQRX5.png)

假如你喜欢的多名女优一起共演了一个片子, 如果是根据女优名进行分类, 这视频肯定不能复制一份去浪费硬盘, 那么有的人会使用
"制作替身", 等于Windows的快捷方式.

这个方法肯定是行的, 但是:

![toTggc](https://cdn.jsdelivr.net/gh/zhaoleihello/ImageStore@master/Images/toTggc.png)

这看起来是不是很囧.

见过喜欢给片子添加简介的坛友, 文件夹看起来更囧了.

![iShot2020-06-1202.48.13](https://cdn.jsdelivr.net/gh/zhaoleihello/ImageStore@master/Images/iShot2020-06-1202.48.13.jpg)

再看看没有替身的目录的样子:

![GWhrFu](https://cdn.jsdelivr.net/gh/zhaoleihello/ImageStore@master/Images/GWhrFu.png)

也没好到哪去, 看着也挺尴尬, 闲七杂八的有点多, emby这种必须放封面和nfo的条件约束很讨厌.

最后为了解决这一切, 让自己以后再也不用干这些整理来整理去的蠢事, 我开始着手自制一个应用.

这个应用界面参考了苹果自带的Music应用, 以前集成在iTunes里.

![2qCBIv](https://cdn.jsdelivr.net/gh/zhaoleihello/ImageStore@master/Images/2qCBIv.png)

Music应用长这样:

![iShot2020-06-1122.24.32](https://cdn.jsdelivr.net/gh/zhaoleihello/ImageStore@master/Images/iShot2020-06-1122.24.32.jpg)

需要实现哪些主要功能:

1. 更新资料, 收集新片的信息存入数据库
2. 可以进行复杂的查询, 网页端一般不提供这种查询, 咱们的javbus就没有, 这个自己没有数据库的话无法实现.
3. 脱离Finder(访达), 应用直接调用本地播放器打开视频.

写应用就不能用python了, 不擅长干这个.

语言用的Swift, UI用的苹果去年新出的UI框架SwiftUI(一堆坑), 数据库用的苹果的Core Data(一堆坑).

先粗略的看看它的样子

![iShot2020-06-1601.15.21](https://cdn.jsdelivr.net/gh/zhaoleihello/ImageStore@master/Images/iShot2020-06-1601.15.21.jpg)

...(未完待续)
