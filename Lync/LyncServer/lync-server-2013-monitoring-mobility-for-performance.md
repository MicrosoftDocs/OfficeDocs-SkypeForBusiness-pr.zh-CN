---
title: 'Lync Server 2013: 监视性能移动性'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3b6cbdefcb7c78f68fe8838109dea3be5b8203d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a>在 Lync Server 2013 中监视移动性能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-14_

Lync Server 移动服务 (Mcx) 和统一通信 Web API (UCWA) 增加前端服务器和前端池的负载。 即使在移动应用程序被最小化的情况下也保持与服务器的连接的移动设备 (如运行 Lync 2010 Mobile 的 Android 和 Nokia 设备) 以及运行 Lync 2013 移动设备的 Android 和 Apple 设备的负载比当移动应用程序最小化时, 终止与服务器的连接。 随着移动性用途的增加, 您必须监视移动性性能以确定何时需要增加容量。

有几项限制会影响移动性能：

  - 可用内存

  - 请求队列限制

  - 并发连接

  - IIS 队列长度

对可能影响移动性能的服务器的其他限制是最多12个并发登录、身份验证、会话续订和终止。 对于大多数部署，无需修改这些最大值。

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中监视服务器内存容量限制](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [在 Lync Server 2013 中监视移动服务和 UCWA 使用情况](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [在 Lync Server 2013 中配置高性能的移动服务](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [在 Lync Server 2013 中监视 IIS 请求跟踪日志文件](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Lync Server 2013 中的移动性能计数器](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

