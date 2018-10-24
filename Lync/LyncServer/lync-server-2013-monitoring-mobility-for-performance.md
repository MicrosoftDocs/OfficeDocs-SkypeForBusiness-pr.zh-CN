---
title: Lync Server 2013 中的监视移动性能
TOCTitle: Lync Server 2013 中的监视移动性能
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690033(v=OCS.15)
ms:contentKeyID: 49313739
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的监视移动性能

 

_**上一次修改主题：** 2013-02-14_

Lync Server Mobility Service 会增加前端服务器和前端池上的负载。与在最小化移动应用程序的情况下终止应用程序与服务器的连接的设备相比，在最小化移动应用程序的情况下保留应用程序与服务器的连接的移动设备（例如，Android 和 Nokia 设备）会产生更大的负载。随着您的移动使用率的增加，您需要监视移动性能以确定何时需要增加您的容量。

有几项限制会影响移动性能：

  - 可用内存

  - 请求队列限制

  - 并发连接

  - IIS 队列长度

可影响移动性能的服务器上的其他限制为 12 个并发登录、身份验证和会话续订和终止的最大值。对于大多数部署，无需修改这些最大值。

## 本部分内容

  - [针对服务器内存容量限制进行监视](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [监视 Mobility Service 和 UCWA 的使用情况](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [配置 Mobility Service 以实现高性能](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [监视 IIS 请求跟踪日志文件](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [移动性能计数器](lync-server-2013-mobility-performance-counters.md)

