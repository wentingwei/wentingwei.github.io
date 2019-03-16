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
3. TOOLBOX 预览模型表现
4. 引擎和TOOLBOX对接，让表现一致（技术）
5. 皮肤散射材质支持（技术）
6. 毛发材质支持（技术）
7. 制作天空球还表现环境，增加细节
8. 布料制作（Marvelous Designer)

---
## 散射和投射的简单实现
---

1. 散射通过与积分曲率采样取色方式
2. 投射通过模型视野厚度或本身厚度来计算，叠加到光照运算之后

Ref:
https://www.alanzucconi.com/2017/08/30/fast-subsurface-scattering-1/
https://www.alanzucconi.com/2017/08/30/fast-subsurface-scattering-2/
https://zhuanlan.zhihu.com/p/35628106
[GPU PRO2]pre integrated skin shading