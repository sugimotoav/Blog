---
title: "Hello World"
date: 2020-06-13T23:36:52+08:00
toc: true
draft: false
---

<img src="https://gitee.com/sugimoto/ImageStore/raw/master/Images/img_icon_5%20%281%29.png" width=400px title="我们无法一起学习">

<!--more-->

## 文本测试

Colorful World

オシャレな服装で 弾ける笑顔
穿着漂亮的衣服绽放笑容
すれ違うVivid同世代
擦肩而过的生动的同龄人
ビルに映る わたし さえないモノトーン
啤酒里倒映着我单调乏味的脸
ほんと 都会の夜って綺麗で残酷
真是都市夜晚美丽里的残酷
近づけば近づく程に
越来越靠近
それでも“いつか”を夢見て ここに居んの
就算这样 也总是梦到“不知何时”在这里住着
モノクロって諦めた世界も
放弃黑白的世界也是
枠からはみ出せない願いも
无法从框框里溢出的愿望也是
逃げてても“いつか”なんて来ないし
就算逃避 “不知何时”什么的也没来
Steppin' to the Colorful World
踏入彩色的世界吧
塗り替えよう 今夜 夢見たワンダーランド
就像重新粉刷一样 今晚梦到了仙境
涙には 温もりのオレンジ
眼泪就是温暖的橙色
曇り空にはパッションピンク
阴云密布的天空就是激情粉
Everybody Say！！ Yeah！！ 何度だって
大家说 yeah！ 好几次
好きな 色を重ねて
堆叠喜欢的颜色
この瞬間 思うまま 歩き出そう
那个瞬间 想就这么随心所欲的走出去
きっと 世界は変わる
世界一定会改变


いつまで経っても減らないままの
不知道过了多久都没有减少的
白色の色鉛筆
白色的彩铅
まるでわたしみたい みんなをうらやんで
简直就像羡慕大家的我
誰かの色眼鏡 気にして
介意某人的墨镜
目立たずに影にまぎれ込んで
有不引人注意的影子混入
嫌気がさす心うずくなら
假如不开心会让心痛
Steppin' to the Colorful World
踏入彩色的世界吧
塗り替えよう 今夜 夢見たワンダーガール
就像重新粉刷一样 今晚梦到了奇迹女孩
弱さには 幸せのイエロー
柔弱就是幸福的黄色
やるせなさにはベイビーブルー
令人厌烦的就是浅蓝色
Everybody Say！！ Yeah！！ 何度だって
大家说 yeah！ 好几次
好きな 色を重ねて
堆叠喜欢的颜色
この瞬間 思うまま 歩き出そう
那个瞬间 想就这么随心所欲的走出去
きっと 世界は変わる
世界一定会改变


たったひとりでも涙は流せるけれど
但是就算只有一个人也会流泪
笑うことだけは難しいの
然而只笑的话是很难的呀
君がそばに居なきゃ だから ふたり 一緒に
必须要住在你的身旁 所以 两个人一起
Steppin' to the Colorful World
踏入彩色的世界吧
塗り替えよう 今夜 僕らのワンダーランド
就像重新粉刷一样 今晚 我们的仙境
笑顔には 愛しさのローズレッド
笑容就是爱怜的玫瑰红
想い出にはエバーグリーン
回忆就是万年青
Everybody Say！！ Yeah！！ 何度だって
大家说 yeah！ 好几次
好きな 色を重ねて
堆叠喜欢的颜色
この瞬間 思うまま 走り出そう
那个瞬间 想就这么随心所欲的跑出去
きっと 世界は変わる
世界一定会改变


## meme独有格式测试

`..这是一个特别长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长长的段落..`


## 代码块

```swift
import AppKit

func copyContent(input: String) {

    let pasteBoard = NSPasteboard.general

    pasteBoard.clearContents()
    pasteBoard.setString(input, forType: .string)
}

func copyManyContent(input: [String]) {

    let mergeString = input.joined(separator: "\n")

    let pasteBoard = NSPasteboard.general

    pasteBoard.clearContents()
    pasteBoard.setString(mergeString, forType: .string)


}

func pasteContent() -> String {
    let pasteBoard = NSPasteboard.general
    return pasteBoard.string(forType: .string) ?? ""
}

```

## 图片测试

<img src="http://konachan.net/image/d8d99b016b18d039326580c8c97f2b84/Konachan.com%20-%20308723%20bibido%20brown_eyes%20brown_hair%20chinese_clothes%20clouds%20long_hair%20scenic%20signed%20sky%20sunset%20tears%20tree%20wristwear.jpg" width=400px title="From Konachan" />

![](http://konachan.net/image/d8d99b016b18d039326580c8c97f2b84/Konachan.com%20-%20308723%20bibido%20brown_eyes%20brown_hair%20chinese_clothes%20clouds%20long_hair%20scenic%20signed%20sky%20sunset%20tears%20tree%20wristwear.jpg "From Konachan")



## Youtube视频测试

{{< youtube wsl8HS_lVHE >}}
