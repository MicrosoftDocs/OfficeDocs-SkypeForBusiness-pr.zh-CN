---
title: Lync Server 2013：配置移动服务以实现高性能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d587444dfd1fbe4fae8898438a51bc9cfb2b5ff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526949"
---
# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a>在 Lync Server 2013 中配置移动服务以实现高性能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-17_

<div>


> [!IMPORTANT]  
> 本主题仅适用于 Lync Server 2013 移动服务 (Mcx) ，不适用于 Lync Server 2013 的累积更新：二月2013中提供的统一通信 Web API (UCWA) 。



</div>

当您在 Internet Information Services (IIS) 7.5 上安装移动服务 (Mcx) 时，移动服务安装程序将在前端服务器上配置一些性能设置。 建议您使用 IIS 7.5 以实现移动功能。 这些设置会影响移动服务允许的最大并发用户请求数和最大线程数。

以下是性能设置：

<div>

## <a name="settings-for-mcx-on-iis-75"></a>IIS 7.5 上的 Mcx 设置

1.  **maxConcurrentThreadsPerCPU** 设置为零 (0) 。

2.  **maxConcurrentRequestsPerCPU** 设置为零 (0) 。

3.  ASP.NET 进程模型设置为仅) IIS 7.5 的自动配置 (。

4.  默认情况下，HTTP.sys 队列限制设置为 1000 () 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

