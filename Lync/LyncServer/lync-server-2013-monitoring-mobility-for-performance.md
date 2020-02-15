---
title: Lync Server 2013：监视性能移动性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 131a6a4dd6fffb3081ff2b1dee58318afd525eaa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a>在 Lync Server 2013 中监视移动性以提高性能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-14_

Lync Server 移动服务（Mcx）和统一通信 Web API （UCWA）增加了前端服务器和前端池的负载。 即使在移动应用程序已最小化（如运行 Lync 2010 Mobile 的 Android 和 Nokia 设备，以及运行 Lync 2013 移动的 Android 和 Apple 设备）的情况下，仍会保持与服务器的连接的移动设备会带来更多负载，而不是设备在移动应用程序最小化时终止与服务器的连接。 随着移动性使用的增加，您必须监视移动性性能，以确定何时需要增加容量。

有几项限制会影响移动性能：

  - 可用内存

  - 请求队列限制

  - 并发连接

  - IIS 队列长度

对可能影响移动性能的服务器的其他限制是最多同时有12项登录、身份验证、会话续订和终止。 对于大多数部署，无需修改这些最大值。

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中监视服务器内存容量限制](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [在 Lync Server 2013 中监视移动服务和 UCWA 使用情况](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [在 Lync Server 2013 中配置移动服务以实现高性能](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [在 Lync Server 2013 中监视 IIS 请求跟踪日志文件](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Lync Server 2013 中的移动性能计数器](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

