# 《Web应用基础》课程结业报告

- 做的什么
- 开发过程
- 遇到的问题
- 如何解决
- 未解决的问题
- 总结

-------------------


## 做的什么


 - 本项目建造的是一个静态页面网站，目的是介绍世界各地端午节的习俗，由gitpage托管。


## 开发过程


- 网站的内容策划
> 首先确定自己的网页主题，本项目目的是展示端午节的节日习俗，要实现在几个页面内介绍世界各地端午节的习俗，包括中国内地，日本，韩国，越南等地。
- 网站的整体结构
> 网页由五个页面组成，包含主页，端午节介绍，端午节习俗，赛龙舟以及联系回访页。
> 其中主页主要由文字组成。端午介绍页包含一张图片和几段关于端午来历的文字。习俗页则主要包含世界各地端午的图片，结合一个筛选显示的js控件，可以将各地的端午习俗图片筛选出来加以展示。赛龙舟页由一段视频和一幅幻灯片组成，展示的是赛龙舟的节日赛事。
- 页面设计
> 因为是介绍节日的网页，所以网页整体气氛要活跃，在这里可以采用幻灯片和活动图片的方式实现。而端午节与屈原这一爱国诗人的故事有关，也要用上厚重，大气的设计，这里可以用背景图片的方式实现，背景图显示深色，展示厚重。



## 遇到的问题
- 如何选择自己网页的主题风格
- 使用css实现图片轮播问题
- 在线视频播放
- div垂直居中问题

## 如何解决
##### 如何确定网页风格
`决定网页的主题风格对于一个个人前端开发者而言是十分重要的。一般来说，如果要面向市场的需要，这个网页应该与社会上人们的关注点有关，故应该根据人们的喜好决定主题。但是作为一个学生开发的个人网页，并不需要十分注重市场的需求，而可以根据自己的需求决定网页的主题。
开始我百度个人风格的网页设计，但是不符合我的审美观。后来想到了端午节将至，决定要开发一个与端午节有关主题的网页。主题以此决定下来。`

##### 如何实现图片轮播
`使用css实现图片轮播，通过css animation控制图片轮换`
```
#stage{
	margin: lem auto;
	width: 382px;
	height: 292px;
}

#stage a{
	position: absolute;
}

#stage a img{
	padding: 10px;
	border: 1px solid #ccc;
	background: #fff;
}

#stage a:nth-of-type(1){
	animation-name: fader;
	animation-delay: 4s;
	animation-duration: 1s;
	z-index: 20;
}

#stage a:nth-of-type(2){
	z-index: 10;
}

#stage a:nth-of-type(n+3){
	display: none;
}

@keyframes fader{
	from {opacity: 1.0;}
	to{opacity: 0.0;}
}

```
---
##### 如何实现在线视频播放居中问题
`使用iframe实现在线视频引用，通过手动调节引用的链接实现视频居中`
```
//调节前的链接
<iframe src="//player.bilibili.com/player.html?aid=55371415&bvid=BV1La4y177fA&cid=228083768&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>
//手动调节后的链接
<iframe id="mcvideo" src="//player.bilibili.com/player.html?aid=55371415&page=1&high_quality=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true" width=60%> </iframe>
```
---
##### 如何实现图片垂直居中问题
`兼容性较好垂直居中（不限宽高）`
<!-- ``` -->
<div class="parent">
    <div class="child"></div>
</div>
```
```
<style>
.parent{
    position: relative;
    width: 100%;
    height: 300px;
    background: #F1F1F1;
}
.child {
    position: absolute;
    top:0;
    left:0;
    right:0;
    bottom: 0;
    width: 150px;
    height: 150px;
    margin: auto;
    background: #0c7cb5;
}
</style>
<!-- ``` -->
```
<div class="parent">
    <div class="child"></div>
</div>
```
```
<style>
.parent{
    position: relative;
    width: 100%;
    height: 300px;
    background: #F1F1F1;
}
.child {
    position: absolute;
    top:0;
    left:0;
    right:0;
    bottom: 0;
    width: 150px;
    height: 150px;
    margin: auto;
    background: #0c7cb5;
}
</style>
```
` css3 实现垂直居中`
`语法：display:flex,justify-content:center, align-items: center`
1. display:flex,设置弹性布局显示；
2. justify-content: center, 设置子元素水平居中；
3. align-items: center, 设置子元素垂直居中；
```
div {
    display: flex;  
    justify-content: center;  
    align-items: center;
}
```

## 未解决的问题
##### 图片和视频引用页加载过慢问题
因为是引用链接，也决定了加载的速度由视频源网站的速度决定。
##### 背景图片颜色过暗妨碍图片上文字显示问题
尝试过多背景图片进行调色处理，比起一开始的完全看不出文章要好一点，但是还是不太能看清文字。
## 总结
> 通过这次实验，我学会了基本的静态网页的开发方式，css的使用和js与网页结合产生动画效果。在这次实验过程中，我遇到了许多问题，这些问题部分得到了解决，部分未解决。这是个人能力实践过程中会遇到的问题之一：能力不足问题，但是通过网络的发达，人们纷纷在网络中分享自己类似问题的解决方案。在参考他人的开发经验过程中，我学习到了许多，也解决了自己的问题。
> 这次的实验终于结束，在这段时间内的制作经验我会好好利用，在未来的时间内不断地学习，提高自己的开发能力以及解决问题的能力，从而为下一次开发做好更好的铺垫。这是一次重要的经历，我在知识，技能方面都有了不少收获，我的综合素质也提高了。