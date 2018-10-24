---
title: Lync Server 2013：配置自动客户端登录以使用控制器
TOCTitle: 配置自动客户端登录以使用控制器
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398678(v=OCS.15)
ms:contentKeyID: 49313464
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置自动客户端登录以使用控制器

 

_**上一次修改主题：** 2012-09-08_

在部署 Lync Server 2013、控制器或控制器池时，建议的最佳实践是使用自动客户端登录。有关如何为自动客户端登录配置 DNS 服务器的详细信息，请参阅规划文档中的 [自动客户端登录的 DNS 要求](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)。

如果已部署自动客户端登录，请参阅以下几节以在一台或多台控制器上配置自动客户端登录。

## 单个控制器实例

如果已部署自动客户端登录，且指向 前端服务器或 前端池，则您需要更改 DNS SRV 记录以指向控制器。

## 控制器池

如果已部署自动客户端登录，且指向 前端服务器或 前端池，则您需要更改 DNS SRV 记录以指向控制器池。

