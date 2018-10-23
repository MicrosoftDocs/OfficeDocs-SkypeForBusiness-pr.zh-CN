---
title: 验证对外部用户的联盟和远程访问
TOCTitle: 验证对外部用户的联盟和远程访问
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49888547
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 验证对外部用户的联盟和远程访问

 

_**上一次修改主题：** 2012-09-18_

将联盟路由迁移到 Lync Server 2013  边缘服务器后，应该执行一些功能测试，以确认联盟能够按预期方式执行。外部用户访问测试应包括贵组织支持的每种类型的外部用户，包括下列任意部分或全部用户。

## 测试外部用户和外部访问的连接

  - 来自至少一个联盟域的用户、 Lync Server 2013 上的内部用户和 Lync Server 2010 上的用户。测试即时消息 (IM)、状态、音频/视频 (A/V) 和桌面共享。

  - 组织支持的每个公共 IM 服务提供商的用户（其设置已完成）与 Lync Server 2013 上的用户和 Lync Server 2010 上的用户的通信。

  - 验证匿名用户是否能够加入会议。

  - 使用远程用户访问（从 Intranet 外部但不使用 VPN 登录到 Lync Server 2010 ）测试 Lync Server 2010 上承载的用户与 Lync Server 2013 上的用户和 Lync Server 2010 上的用户。测试 IM、状态、A/V 和桌面共享。

  - 使用远程用户访问（从 Intranet 外部但不使用 VPN 登录到 Lync Server 2013 ）测试 Lync Server 2013 上承载的用户与 Lync Server 2013 上的用户和 Lync Server 2010 上的用户。测试 IM、状态、A/V 和桌面共享。

