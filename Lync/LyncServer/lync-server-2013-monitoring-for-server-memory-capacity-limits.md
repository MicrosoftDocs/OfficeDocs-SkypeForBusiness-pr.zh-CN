---
title: Lync Server 2013：监视服务器内存容量限制
description: Lync Server 2013：监视服务器内存容量限制。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6561908af2c8f2f7b5fb9e347cc6247f7ca6642e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562048"
---
# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a>在 Lync Server 2013 中监视服务器内存容量限制

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> 本主题中涉及容量规划的信息仅适用于 Lync 2010 移动客户端和移动服务 (Mcx) 。 Lync 2013 移动客户端使用的统一通信 Web API (UCWA) 的容量规划由 Lync Server 2013、规划工具提供。



</div>

两个移动性能计数器可帮助您确定当前的使用情况，并帮助您规划 Lync Server 2013 移动服务 (Mcx) 的容量，并监视 UCWA 的内存使用率。 对于 UCWA，计数器类别为 **LS： WEB – UCWA**。 对于移动服务 (Mcx) ，计数器位于类别 **LS： WEB 移动通信服务**中。 要监视的计数器包括：

  - **当前处于活动状态订阅的活动会话计数**，这是通过 UCWA 或移动服务 () Mcx 的当前注册的终结点的数目，这些终结点具有活动状态订阅 (始终连接的移动用户数) 

  - **当前处于活动状态的会话计数**，是通过 UCWA 或移动服务注册的当前终结点的数目

如果 **当前活动会话计数与活动状态订阅** 和 **当前活动会话计数** 之间的差异较小，则意味着大多数移动设备用户都有一个始终连接的设备，例如 Android 或 Nokia 移动设备 (仅) 的 Mcx。 UCWA 始终连接的设备包括运行 Lync 2013 移动客户端) 的 Apple 和 Android 设备。 如果 **当前处于活动状态的会话计数** 比 **活动状态订阅当前活动会话计数**高得多，则表示在 Mcx 下的用户使用的是更多的后台终结点设备（如 Apple IOS 设备或 Windows Phone）。  (Windows Phone 是唯一将注册为此) 的 Lync 2013 移动客户端。

您应根据预期的使用情况、容量规划结果和对移动服务和其他前端服务器计数器的持续监控，对 **当前处于活动状态的会话计数** 和 **当前活动会话计数** 性能计数器设置限制。 你设置的限制应允许你评估服务器容量并在超出容量时发出警报。

若要确定适当的限制，需要先确定可在移动服务的前端服务器上使用的内存量。 根据以下公式监视计数器，以确定何时需要规划额外的容量：

Mcx 移动服务 (MB 使用的内存总量) = 164 + (400 + 134) /1024 \* **当前活动会话计数与活动状态订阅** + 400/1024 \* (**当前活动会话计数** – **当前处于活动状态订阅的活动会话计数**) 

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2010 容量计算器是预填充了所有公式的电子表格，以使规划器能够确定服务器（包括 CPU、内存和硬盘驱动器）的要求。 您可以从以下位置下载电子表格和关联文档： <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A>



</div>

前端服务器需要足够的可用内存来支持故障转移情况下的移动服务。 您可以通过使用 **内存 \\ 可用的 mb** 计数器，或使用前面提到的公式来规划预期移动服务要使用的内存量来监视前端服务器上当前可用的内存。

如果在规划预期的移动用户数时前端服务器上可用的内存量低于 1500 MB，则需要添加更多硬件以支持移动服务。 有关更多详细信息，请参阅操作文档中的 [监视 Lync Server 2013 中的性能移动性](lync-server-2013-monitoring-mobility-for-performance.md) 。

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中监视移动性以提高性能](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

