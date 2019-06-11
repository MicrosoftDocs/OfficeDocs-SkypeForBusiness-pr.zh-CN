---
title: 'Lync Server 2013: 为高性能配置移动服务'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54a1c9b901e9a861b40a5cfa8c2642e3e3e41ffe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a>在 Lync Server 2013 中配置高性能的移动服务

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-17_

<div>


> [!IMPORTANT]  
> 本主题仅适用于 Lync Server 2013 移动服务 (Mcx), 不适用于在 Lync Server 2013 的累积更新中提供的统一通信 Web API (UCWA): 2 月2013。



</div>

在 Internet Information Services (IIS) 7.5 上安装移动服务 (Mcx) 时, 移动服务安装程序将在前端服务器上配置某些性能设置。 建议您使用 IIS 7.5 以实现移动功能。 这些设置会影响 Mobility Service 允许的最大并发用户请求数和最大线程数。

以下是性能设置：

<div>

## <a name="settings-for-mcx-on-iis-75"></a>IIS 7.5 上的 Mcx 设置

1.  将 **maxConcurrentThreadsPerCPU** 设置为零 (0)。

2.  将 **maxConcurrentRequestsPerCPU** 设置为零 (0)。

3.  将 ASP.NET 进程模型设置为 AutoConfig（仅针对 IIS 7.5）。

4.  将 HTTP.sys 队列限制设置为 1,000（默认值）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

