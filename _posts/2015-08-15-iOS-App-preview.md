---
layout: post
keywords: 技术
description: iOS审核注意
title: "iOS审核注意"
categories: [Technology]
tags: [Technology]
group: archive
icon: file-alt
disqus: y
---

---
1，不能出现更新字样

---
2，不能有外部网页

---
3，不能有 CDkey

---
4，BuildVersion 必须用数字

---
5，用 dis 的 mobileprovision

---
6，archieve 出来的 xxx.app 文件可以直接拖到 iTunes 中，然后就会自动生成 xxx.ipa 文件

---
7，IPV6 真实环境测试

---
8, 补全 AppIcon 分辨率正确

---
9, iPad 选择 fullscreen

---
10, 提供两个账号，一个是小号，一个是能玩多有功能的大号

---
11, 测试 iOS 老的版本是否有闪退情况，因为API用的新的，可能苹果有改动

---
12, 保留一个审核的过的版本，以后出问题就改代码，修改版本号，继续用这个去提审

---
13, 尽量避免强更

---
14, mobileprovision 一定要配置正确，是否内购，是否允许通知

---
15, 商品类型一定要注意，和描述一致，月卡终身卡，非续订订阅。

---
16, 可以用变相方式来实现非商品内购，充值xxx钻可以有购买资格，购买需要xxx钻，相当于商品了

---
```cpp
struct addrinfo *answer, hint, *curr;
ZeroMemory(&hint, sizeof(hint));
hint.ai_family = AF_UNSPEC;
hint.ai_socktype = SOCK_STREAM;
char ipstr4[128] = {0};
char ipstr6[128] = {0};

struct sockaddr_in  *sockaddr_ipv4 = NULL;
struct sockaddr_in6 *sockaddr_ipv6 = NULL;

int ret = getaddrinfo(szHostName, NULL,&hint, &answer);
if (ret != 0) {
	return IPNone;
}

for (curr = answer; curr != NULL; curr = curr->ai_next) {
	switch (curr->ai_family){
	case AF_UNSPEC:
		//do something here
		break;
	case AF_INET:
		sockaddr_ipv4 = reinterpret_cast<struct sockaddr_in *>( curr->ai_addr);
	case AF_INET6:
		sockaddr_ipv6 = reinterpret_cast<struct sockaddr_in6 *>( curr->ai_addr);
		inet_ntop(AF_INET6, &sockaddr_ipv6->sin6_addr, ipstr6,sizeof(ipstr6));
		break;
	default:
		break;
	}
}
```


---