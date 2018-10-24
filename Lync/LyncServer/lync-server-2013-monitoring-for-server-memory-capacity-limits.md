---
title: 针对服务器内存容量限制进行监视
TOCTitle: 针对服务器内存容量限制进行监视
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh689982(v=OCS.15)
ms:contentKeyID: 49312125
ms.date: 12/29/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 针对服务器内存容量限制进行监视

 

_**上一次修改主题：** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

> [!WARNING]
> 本主题中涉及容量规划的信息仅与 Lync 2010 Mobile 客户端和 Mobility Service (Mcx) 相关。Lync 2013 Mobile 客户端使用的统一通信 Web API (UCWA) 的容量规划由 Lync Server 2013 规划工具提供。


有两个移动性能计数器可帮助您确定当前使用率，并帮助您针对 Lync Server 2013 Mobility Service (Mcx) 规划容量，以及监控 UCWA 的内存使用情况。对于 UCWA，计数器类别为“LS:WEB – UCWA”。对于 Mobility Service (Mcx)，计数器类别为“LS:WEB - 移动通信服务”。要监控的计数器包括：

  - **Currently Active Session Count with Active Presence Subscriptions**，它是当前通过 UCWA 或 Mobility Service (Mcx) 注册的终结点的数目，这些终结点具有活动状态订阅（始终连接的移动用户的数目）

  - **Currently Active Session Count**，它是当前通过 UCWA 或 Mobility Service 注册的终结点的数目

如果 **Currently Active Session Count with Active Presence Subscriptions** 和 **Currently Active Session Count** 之间的差异随时间变小，则表示大多数移动设备用户具有始终连接的设备（如 Android 或 Nokia 移动设备（仅限 Mcx））。始终连接 UCWA 的设备包括运行 Lync 2013 Mobile 客户端的 Apple 和 Android 设备。如果 **Currently Active Session Count** 大大高于 **Currently Active Session Count with Active Presence Subscriptions**，则表示使用后台终结点设备（如 Apple iOS 设备或 Mcx 下的 Windows Phone）的用户更多。（Windows Phone 是唯一将按照此方式注册的 Lync 2013 Mobile 客户端。）

您应根据预计的使用率、容量规划结果和正在对 Mobility Service 和其他前端服务器计数器进行监控的情况为 **Currently Active Session Count with Active Presence Subscriptions** 和**Currently Active Session Count** 性能计数器设置限制。您设置的限制应允许您计算服务器容量并在超出容量时发出警报。

若要确定适当的限制，您需要先确定前端服务器上可用于 Mobility Service 的内存量。请监控计数器以根据以下公式确定您需要何时规划额外的容量：

Mcx Mobility Service 使用的内存总量 (MB) = 164 + (400 + 134) / 1024 \* **Currently Active Session Count with Active Presence Subscriptions** + 400 / 1024 \* (**Currently Active Session Count** – **Currently Active Session Count with Active Presence Subscriptions**)

> [!IMPORTANT]
> Microsoft Lync Server 2010 容量计算器是一种预填充所有公式的电子表格，计划者可以用其来确定服务器的要求，包括 CPU、内存和硬盘。您可以在以下地址下载电子表格和关联文档：<a href="http://go.microsoft.com/fwlink/?linkid=212657" class="uri">http://go.microsoft.com/fwlink/?linkid=212657</a>


前端服务器需要足够的可用内存以在发生故障转移时支持 Mobility Service。您可以使用 **Memory\\Available Mbytes** 计数器监视前端服务器上的当前可用内存，也可以使用前面所述的公式规划您预计 Mobility Service 将使用的内存量。

当您规划预计的移动用户数时，如果前端服务器上的可用内存量少于 1,500 MB，则您需要添加更多硬件以支持 Mobility Service。有关更多详细信息，请参阅操作文档中的[Lync Server 2013 中的监视移动性能](lync-server-2013-monitoring-mobility-for-performance.md)。

## 另请参阅

#### 其他资源

[Lync Server 2013 中的监视移动性能](lync-server-2013-monitoring-mobility-for-performance.md)

