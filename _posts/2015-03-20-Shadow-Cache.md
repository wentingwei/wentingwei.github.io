---
layout: post
keywords: 技术
description: 阴影优化之shadow cache
title: "阴影优化之shadow cache"
categories: [Technology]
tags: [Technology]
group: archive
icon: file-alt
duoshuo: y
---

-----
**描述**：

对于3DMMO游戏，实时阴影一般使用shadowmap来实现，这样的话就存在一个问题，这张shadowmap需要画阴影摄像机下的所有物件一遍，对于DrawCall基本是没有阴影的2倍左右，虽然我们可以用ReadDepthAsTexture来对RT以及渲染稍作优化，但是DrawCall本质没有下降，那么有没有方法来减少DrawCall，或者在前期渲染好DepthTexture呢？

-----
针对这个问题，我做了一个思考：美术在场景做好之后，我们划分场景，预渲染整个场景静态物件的深度到贴图上，运行期，根据阴影摄像机的位置不同来拼接这些深度图，以此实现减少DrawCall和全局阴影的效果。

-----
**具体做法**：

-	在Shadow Camera的空间，划分整个场景，计算好每个阴影摄像机的位置以及远近才见面，这时候需要根据地形以及场景物件的摆放等
-	针对每个摆好的阴影摄像机，对场景拍照，保存深度图
-	运行期根据当前阴影摄像机所在的位置，拼出一张深度图，然后再画动态物件到shadowmap上
-	最终使用这张shadowmap来画场景物件，实现阴影效果

-----
**一些关键点**：

-	划分区间，阴影摄像机可见的所有模型的顶点位置，最终算出一个合适的阴影摄像机
-	保存深度图时，分解通道到rgba，然后压缩存储为png，减少存储空间
-	拼图时，使用了Pixel Shader写深度的点，shader中 { depth ：depth}这种写法
- 	最终的shadowmap使用[Read depth buffer as texture][0]技术


---
参考：

- http://aras-p.info/texts/D3D9GPUHacks.html

---
[0]:http://aras-p.info/texts/D3D9GPUHacks.html