---
title: 'Lync Server 2013: 监视服务器内存容量限制'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68728c85b14231644b445569857896f34abe535f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a>在 Lync Server 2013 中监视服务器内存容量限制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> 本主题中涉及容量规划的信息仅适用于 Lync 2010 移动客户端和移动服务 (Mcx)。 Lync 2013 移动客户端使用的统一通信 Web API (UCWA) 的容量规划由 Lync Server 2013、计划工具提供。



</div>

两个移动性能计数器可帮助你确定当前使用情况并帮助你规划 Lync Server 2013 移动服务 (Mcx) 的容量, 以及监视 UCWA 的内存使用情况。 对于 UCWA，计数器类别为“**LS:WEB – UCWA**”。 对于 Mobility Service (Mcx)，计数器类别为“**LS:WEB - 移动通信服务**”。 要监控的计数器包括：

  - **Currently Active Session Count with Active Presence Subscriptions**，它是当前通过 UCWA 或 Mobility Service (Mcx) 注册的终结点的数目，这些终结点具有活动状态订阅（始终连接的移动用户的数目）

  - **Currently Active Session Count**，它是当前通过 UCWA 或 Mobility Service 注册的终结点的数目

如果**当前活动的会话计数与活动状态订阅**和**当前活动会话计数**之间的差异在一段时间内较小, 这意味着大多数移动设备用户拥有一个始终连接的设备, 例如 Android 或Nokia 移动设备 (仅限 Mcx)。 UCWA 始终连接的设备包括运行 Lync 2013 移动客户端的 Apple 和 Android 设备。 如果**当前处于活动状态的会话计数**比**当前处于活动状态订阅的当前活动会话计数**高得多, 这表示使用后台终结点设备 (如 Apple IOS 设备或 Windows Phone) 的用户Mcx. (Windows Phone 是唯一将注册为此的 Lync 2013 移动客户端)。

你应该针对**当前处于活动状态的订阅**和**当前活动会话计数**性能计数器 (基于你预期的使用情况、容量计划结果和持续监视) 设置当前活动会话计数的限制移动服务和其他前端服务器计数器。 您设置的限制应允许您计算服务器容量并在超出容量时发出警报。

若要确定相应的限制, 需要首先确定移动服务前端服务器上的可用内存量。 请监控计数器以根据以下公式确定您需要何时规划额外的容量：

Mcx 移动服务 (MB) 使用的总内存 = 164 + (400 + 134)/1024 \* **当前处于活动状态订阅的活动会话计数**+ 400/1024 \* (**当前处于活动**状态的会话计数-当前处于活动状态的会话计数**有活动的状态订阅**)

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2010 容量计算器是预填充了所有公式的电子表格, 它使 planner 能够确定服务器 (包括 CPU、内存和硬盘) 的要求。 您可以在以下位置下载电子表格和相关文档:<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A>



</div>

前端服务器需要足够的可用内存才能在故障转移情况下支持移动服务。 你可以使用**内存\\可用**的 "mb" 计数器来监视前端服务器上的当前可用内存, 或使用前面提到的公式来规划你希望移动服务使用的内存量。

如果在针对预期的移动用户数进行规划时前端服务器上可用的内存量小于 1500 MB, 则需要添加更多硬件来支持移动服务。 有关更多详细信息, 请参阅在操作文档中[监视 Lync Server 2013 中的性能移动性](lync-server-2013-monitoring-mobility-for-performance.md)。

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中监视移动性能](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

