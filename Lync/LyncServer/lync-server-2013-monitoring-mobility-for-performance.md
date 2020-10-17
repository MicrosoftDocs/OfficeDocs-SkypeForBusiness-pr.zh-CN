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
ms.openlocfilehash: 0e217e28545eea15a61bf4b4470472cc9944e9b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531819"
---
# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a>在 Lync Server 2013 中监视移动性以提高性能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-14_

Lync Server 移动服务 (Mcx) 和统一通信 Web API (UCWA) 提高前端服务器和前端池的负载。 即使在移动应用程序已最小化（如运行 Lync 2010 Mobile 的 Android 和 Nokia 设备，以及运行 Lync 2013 移动的 Android 和 Apple 设备）中，仍可保持与服务器的连接的移动设备会比在最小化移动应用程序时终止与服务器的连接的设备所施加的负载更大。 随着移动性使用的增加，您必须监视移动性性能，以确定何时需要增加容量。

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

