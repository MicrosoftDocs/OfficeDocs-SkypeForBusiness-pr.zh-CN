---
title: Lync Server 2013：监视移动服务和 UCWA 使用情况
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2248bbd2eea4bb9204a98b5c5805ef196cbf2015
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531789"
---
# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a>在 Lync Server 2013 中监视移动服务和 UCWA 使用情况

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-14_

在持续的基础上，应监视 Lync Server 移动服务 (Mcx) 和统一通信 Web API (UCWA) 所使用的 CPU 和内存。 若要监视使用情况，可以使用以下命令：

**对于统一通信 Web API (UCWA) ：**

  - Internet 信息服务 (IIS) 管理器中的 **LyncUcwa** 工作进程。 在“工作进程”**** 窗格中，查看“CPU 百分比”**** 和“专用字节(KB)”****（内存）列。

  - **CPU** 和 **Processor** 性能计数器。

对于大多数部署，UCWA CPU 使用率平均应低于15%。 内存使用率应处于在 [Lync server 2013 中监视服务器内存容量限制](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)中所描述的限制范围内。

除了 CPU 和内存使用率计数器之外，您还可以使用以下性能计数器来帮助确定服务器何时因请求而过载：

  - **LS： WEB –限制和身份验证 \\WEB –处理中的总请求**数，指示服务器上的挂起的 web 请求数。 当此计数器达到10000时，后续请求将失败，错误消息为 "503-服务不可用"。

  - **ASP.NET \\排队** (的请求应始终为零) 。

<div>


> [!NOTE]  
> 如果达到或超过这些值，则应重新访问并重新计算容量规划，以确保承载 Web 服务的计算机的 CPU、内核数和内存的正确大小。



</div>

**对于移动服务 (Mcx) ：**

  - Internet 信息服务中的 **CSIntMcxAppPool** 和 **CSExtMcxAppPool** 工作进程 (IIS) 管理器。 在“工作进程”**** 窗格中，查看“CPU 百分比”**** 和“专用字节(KB)”****（内存）列。

  - **CPU** 和 **Processor** 性能计数器。

对于大多数部署，移动服务 CPU 使用率平均应低于15%。 内存使用率应处于在 [Lync server 2013 中监视服务器内存容量限制](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)中所描述的限制范围内。

除 CPU 和内存使用率计数器之外，您可以使用以下 ASP.NET 性能计数器来帮助确定服务器上的请求何时过载：

  - **ASP.NET v 2.0.50727 \\请求 "Current**"，指示服务器上的挂起的 web 请求数。 当此计数器达到5000时，后续请求将失败，并出现错误消息 "503-服务不可用"。

  - **ASP.NET \\排队** (的请求应始终为零) 。

<div>


> [!NOTE]  
> 如果达到或超过这些值，则应重新访问并重新计算容量规划，以确保承载 Web 服务的计算机的 CPU、核心数量和内存的正确大小。



</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中监视服务器内存容量限制](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

