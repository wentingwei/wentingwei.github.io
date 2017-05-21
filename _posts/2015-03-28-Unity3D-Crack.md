---
layout: post
keywords: [Unity3D]
description: Unity3D之破解与反破解
title: "Unity3D之破解与反破解"
categories: [Unity3D]
tags: [Unity3D]
group: archive
icon: file-alt
disqus: y
---

---
###1. Unity3D破解（MacOSX）

- 分别复制两个文件到相应目录即可
- /Library/Application Support/Unity/Unity_v4.x.ulf
- /Applications/Unity/Unity.app/Contents/MacOS/Unity

---
###2. Unity3D游戏资源导出

1. 下载.IPA或者.APK文件,修改后缀名为.zip，解压就得到打包的资源
2. 使用资源的提取工具[disunity][0]提取资源，具体参考其说明

---
###3. 代码反编译与防止

- 随便下载一个Unity做的游戏apk解压，找到Assembly-CSCarp.dll
- 拖拽到 MonoDevelop中打开（ 或者使用 .NET Reflector 8 反编译 ）
- 防止反编译插件：Codeguard

---
###4. 代码混淆与还原

- 代码混淆与还原工具[de4dot][1]

---
参考:

- [http://www.xuanyusong.com/][2]
- [https://github.com/ata4/disunity/releases][0]
- [https://github.com/0xd4d/de4dot][1]

[0]: https://github.com/ata4/disunity/releases
[1]: https://github.com/0xd4d/de4dot
[2]: http://www.xuanyusong.com/
