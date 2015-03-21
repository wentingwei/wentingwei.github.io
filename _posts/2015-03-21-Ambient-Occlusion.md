---
layout: post
keywords: 技术
description: 静态渲染之Ambient Occlusion
title: "静态渲染之Ambient Occlusion"
categories: [技术]
tags: [技术]
group: archive
icon: file-alt
disqus: n
share: n
---

-----
[Ambient Occlusion Wikipedia][1]

-----

描述：对于3D游戏，AO作为全局光照的一部分已经成为很多3D引擎的标配，不管是静态还是SSAO，本文描述了，在游戏开发后期为了提高整体效果而弥补的静态渲染的AO。

-----
流程：

*	按文件划分UV（正常应该按场景的区域还划分？）
*	渲染生成AO贴图
*	运行期使用AO贴图


-----

一些要点：

*	分UV，合并单个文件的Mesh为一个Mesh，然后转换为DX的标准Mesh，然后利用DX自带的UVAtlas来进行UV划分（UVAtlas分的UV并不是很好），UVAtlas中有很多参数需要注意.分好UV的Mesh，根据文件把第二套UV数据插入进去，保存Mesh以及文件.
*	渲染生成AO部分参考[这篇文章][2],对于非封闭的模型，美术又没有补面的，要做一些特殊处理.
*	运行期AO贴图直接影响光照运算或者模拟乘上去（GameBryo的话直接放DarkMap通道来用了）


-----
[1]: http://en.wikipedia.org/wiki/Ambient_occlusion
[2]: http://www.gamasutra.com/view/feature/130455/hardware_accelerating_art_.php?page=2