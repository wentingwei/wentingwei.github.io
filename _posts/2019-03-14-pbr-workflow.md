---
layout: post
keywords: [Think]
description: 美术PBR工作流
title: "美术PBR工作流"
categories: [Think]
tags: [Think]
group: archive
icon: file-alt
disqus: y
published: false
---

---
## 美术PBR工作流
---

1. 建模3DSMAX，MAYA，ZBRUSH
2. SUBSTANCE 制作材质贴图
3. 3DSMAX或者动捕 制作动画
4. 引擎和SUBSTANCE对接，让表现一致（技术）
5. 皮肤散射材质支持（技术）
6. 头发材质支持（技术）
7. 毛皮材质植萃（技术）
8. 制作天空球环境表现，增加细节
9. 布料制作（Marvelous Designer)
10. 注意Unity在Gamma空间，用SP最好用unityshader或者livelink(官方有提供)
11. 注意Unity的Shader尽量不用SurfaceShader
12. 存储GI信息参数到材质中，用来解决切换环境的问题

---
## 散射和透射的简单实现
---

1. 散射通过预积分曲率采样取色方式
2. 投射通过模型视野厚度或本身厚度来计算，叠加到光照运算之后

参考文档:
https://www.alanzucconi.com/2017/08/30/fast-subsurface-scattering-1/
https://www.alanzucconi.com/2017/08/30/fast-subsurface-scattering-2/
https://zhuanlan.zhihu.com/p/35628106
[GPU PRO2]pre integrated skin shading