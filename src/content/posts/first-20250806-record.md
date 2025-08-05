---
title: first-20250806-record
published: 2025-08-06
description: '第一篇文章，简单介绍一下建站过程与这一天的record'
image: './first-20250806-record/lunacover.png'
tags: [record,first,luna,aigc,fuwari,2xnz,建站]
category: 'RECORDs'
draft: false 
lang: 'zh-CN'
---

# 建站过程
我是跟着

::github{repo="saicaca/fuwari"}

这个项目的教程一步步走完的，基本上是按照教程一步步来，没有什么问题。再加上之前已经用github pages建过站，然后是看了[二叉树树](https://2x.nz/)的主页介绍的[Fuwari](https://github.com/saicaca/fuwari)的前端模板，同时还从这个视频

<iframe width="100%" height="468" src="//player.bilibili.com/player.html?bvid=BV1V7uYzpE1w&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

里了解到Netlify这个平台，感觉我最终的博客选型大概就是这个模板了，太好看了，太舒服了这个扁平化设计，响应式好而且是基于Astro框架的东西，确实不赖。

## 一些排障

每次处理资源路径我都比较蒙古，看着文档半天还不知道怎么写，开着pnpm dev写了半天，结果打开网站就报错，谔谔了。最后盯着[官方文档](https://docs.astro.build/en/guides/images/#images-in-markdown-files)

```
# My Markdown Page

<!-- Local image stored in src/assets/ -->
<!-- Use a relative file path or import alias -->
![A starry night sky.](../assets/stars.png)

<!-- Image stored in public/images/ -->
<!-- Use the file path relative to public/ -->
![A starry night sky.](/images/stars.png)

<!-- Remote image on another server -->
<!-- Use the full URL of the image -->
![Astro](https://example.com/images/remote-image.png)
```
看半天后选择第二种写法，然后本地终于是过检查了，虽然图片依旧不显示，avatar不显示，cover也不显示，感觉神必。但是推到netlify就是正常的。我还是根本不懂前端到底怎么运作的，唉唉。

然后就是这个table语法，我以为是我自己问题，结果看官方demo也是那样子，那没事了，确实是官方的问题，换成标准md语法就好了。

由于自带的教程文档太多了，索性丢给AI写了个多合一文章，方便对比着看写。

# 这一天的record

## 早上
没有早上，暑假至今，这个东西已经消失了，不过我觉得最近还是有必要改善下作息，妈的这文本补全还是有点恐怖，写个record也要送进ai搞续写的话还是有点膈应。

## 中午
起床了，然后赶紧把那个阿里云欠费的事给解决了，把要用的模型都开启免费额度，我看到这个账单心都凉了，我操。

| 用量  | 用量单位 | 目录价  | 目录价定价类型 | 价格单位   | 目录总价   |
| :------- | :------- | :------ | :------------- | :--------- | :--------- |
| 814.659  | 千tokens | ¥ 0.006 | -              | 元/千tokens | ¥ 4.887954 |
| 6.708    | 千tokens | ¥ 0.024 | -              | 元/千tokens | ¥ 0.160992 |
| 1826.363 | 千tokens | ¥ 0.009 | -              | 元/千tokens | ¥ 16.437267 |

我尼玛，昨天用哈基米用的超免费额度了retry半天于是想着用qwen顶一下，然后就注册阿里云账号搞了下qwen3-coder-480B-instruct模型，有一说一用这玩意的时候让我感觉到第一次用哈基米的时候的体验——快的飞起，爽麻了，美美白嫖，结果晚上上床了一封欠费短信发过来让我心凉了一半，赶紧充钱，捏吗的。

然后吃拼好饭，打了会cs2。

## 下午

吃拼好饭，然后开始部署网站。
然后wjw突然走进来，打扰我排bug，然后点进了这个视频

<iframe width="100%" height="468" src="//player.bilibili.com/player.html?bvid=BV1zQhjz6EsR&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

我看了一遍，只能说确实不错，后边动画确实又唐又帅，闹斯特麻麻这一块。

![塔爹启动](./first-20250806-record/tadieqidong.png)

确实不赖吧
![塔爹登场](./first-20250806-record/tadiedengchang.png)

啊啊啊啊啊啊啊谁懂看到塔爹出场的救赎感 >=<

之后看有没有时间，有的话可以练个塔爹lora，然后美美~~。
大概就是这样了，说实话要不是写这个东西，我每天的record其实很少的。

最后再放一下刚跑好的lunasama,封面也是AI图，嗯。

![luna好看捏，虽然跑的不咋地](./first-20250806-record/lunasama.png)

# 音乐推荐

哦对了，这曲子我从期末周听到现在，确实爽。

<iframe width="100%" height="468" src="//player.bilibili.com/player.html?bvid=BV1CnKLz1Ez2&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

无内鬼，速听😎。

# 后记
我终于发现了，不知道是什么原因，本地dev开发的时候需要把astro.config.mjs里的

```
adapter: netlify(), //本地dev的时候得注释
```
注释掉，然后就能正常显示图片了。要push的时候再取消注释就行了。
谔谔。神必bug。
