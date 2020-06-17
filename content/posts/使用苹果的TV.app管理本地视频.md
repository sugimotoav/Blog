---
title: "将苹果自带的TV应用变成本地AV媒体中心"
date: 2020-06-16T14:01:12+08:00
draft: true
---

资料

https://videoconverter.wondershare.com/edit-video/what-is-metadata.html

https://kdenlive.org/en/project/adding-meta-data-to-mp4-video/

https://ghost-timroesner.herokuapp.com/swift-accessing-metadata-from-avasset/

https://stackoverflow.com/questions/37584067/how-to-add-metadata-in-video-mov-in-ios

https://python-forum.io/Thread-Video-Metadata-Question


一些信息, 备用

```
keySpace=itsk, key class = __NSCFNumber, key=©nam, commonKey=title 标题
keySpace=itsk, key class = __NSCFNumber, key=©day, commonKey=(null) 日期
keySpace=itsk, key class = __NSCFNumber, key=tvsh, commonKey=(null) 显示, 可能和Apple TV有关
keySpace=itsk, key class = __NSCFNumber, key=desc, commonKey=(null) 标语, 大概是描述
keySpace=itsk, key class = __NSCFNumber, key=ldes, commonKey=(null) 描述, 应该是简介, long description
keySpace=itsk, key class = __NSCFNumber, key=©too, commonKey=software metadata编码工具名称
keySpace=itsk, key class = __NSCFNumber, key=©ART, commonKey=artist
```


iflicks

- 名称 == Tv的标题
- 标语 == TV的简短描述
- 流派 == TV的类型, 由于只能写一个值, 用来写Genre其实不太合适
- 发布日期(YYYY/MM/dd) == TV的年份, 只能显示出年, 月份和日期显示不出来
- 显示 == TV中显示不出来, 看metadata的key是Collection 暂时不知道干嘛用的
- 演员 == TV的表演者
- 导演 == TV的导演
- 副导演 == TV中显示不出来, metadata的key是Codirector
- 制作人 == TV的制作人
- 编剧家 == TV的编剧
- 描述 == 完整描述
- 季节描述没什么用
- 评论 == 注释, metadata的key是Comment



<img src="https://cdn.jsdelivr.net/gh/zhaoleihello/ImageStore@master/Images/iShot2020-06-1701.59.20.jpg" width=800px title="mediainfo信息">


## 测试

<img src="https://cdn.jsdelivr.net/gh/zhaoleihello/ImageStore@master/Images/iShot2020-06-1709.20.16.jpg" width=600px title="测试视频文件">
