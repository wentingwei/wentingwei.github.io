---
layout: post
keywords: 技术
description: iOS审核注意
title: "iOS审核注意"
categories: [Technology]
tags: [Technology]
group: archive
icon: file-alt
duoshuo: y
---

- 1，不能出现更新字样
- 2，不能有网页
- 3，不能有CDkey
- 4，build version 必须用数字
- 5，用dis的mobileprovision
- 6，achieve出来的.app文件，可以直接拖到iTunes 中，然后就会自动生成ipa
- 7，IPV6真实环境测试

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