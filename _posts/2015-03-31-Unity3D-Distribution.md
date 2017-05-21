---
layout: post
keywords: [Unity3D]
description: Unity3D之打包IPA和APK
title: "Unity3D之打包IPA和APK"
categories: [Unity3D]
tags: [Unity3D]
group: archive
icon: file-alt
disqus: y
---

---
用Unity3D开发App，最终会打包为ipa(iOS),apk(Android),**本质是zip文件**，下面我们来介绍这两个平台如何打包。

- 系统 : OSX10.10.2
- Unity : 4.6.3

---
##1. iOS平台ipa打包
---

####1. 注册Apple开发者账号,[注册链接][1]
####2. 打开Unity菜单 File -> Build Setting 选中IOS平台，添加场景，设置好对应的选项，参考下图： 
 ![](/images/post/unity3d_distribution_02.png)
####3. 上一步选好之后，点击Build And Run 会出现下面的界面，点击保存即可
 ![](/images/post/unity3d_distribution_03.png)
####4. 接下来会自动编译，过程中我们会看到XCode打开了
####5. 下一步分几个步骤如下图所示：
#####1.选择 Product -> Archive
![](/images/post/unity3d_distribution_04.png)
#####2. 选中项目，点击Export
![](/images/post/unity3d_distribution_05.png)
#####3. 勾选选项，点击下一步
![](/images/post/unity3d_distribution_06.png)
#####4. 这一步会自动选中证书，点击Export即可，接下来等待ipa出现吧
![](/images/post/unity3d_distribution_07.png)

---
##2. Android平台apk打包
---
####1.下载[Android SDK][2],[下载链接][3]
####2.通过Android SDK Manager 安装更新SDK，国内参考链接；[http://www.androiddevtools.cn/][4]
####3.设置Unity Preferences 设置SDK路径
![](/images/post/unity3d_distribution_01.png)
####4.打开Unity菜单 File -> Build Setting 选中Android平台，添加场景，设置好对应的选项，参考下图，接下来等待apk出现吧 
![](/images/post/unity3d_distribution_08.png)

[1]:https://developer.apple.com/enroll/selectEnrollmentType.php?t=cm
[2]:http://developer.android.com/sdk/index.html
[3]:http://dl.google.com/android/android-sdk_r24.1.2-macosx.zip
[4]:http://www.androiddevtools.cn/
