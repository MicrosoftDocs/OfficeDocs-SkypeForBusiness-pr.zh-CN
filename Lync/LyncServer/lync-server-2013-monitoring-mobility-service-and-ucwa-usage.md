---
title: 'Lync Server 2013: 监视移动服务和 UCWA 使用情况'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 758fef9e3f2c31bec88927c75b271808d5bbc43c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a>在 Lync Server 2013 中监视移动服务和 UCWA 使用情况

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-14_

在持续的基础上, 你应该监视 Lync Server 移动服务 (Mcx) 和统一通信 Web API (UCWA) 使用的 CPU 和内存。 若要监视使用率，您可以使用以下任一方法：

**对于统一通信 Web API (UCWA)：**

  - Internet Information Services (IIS) 管理器中的**LyncUcwa**工作进程。 在“**工作进程**”窗格中，查看“**CPU 百分比**”和“**专用字节 (KB)**”（内存）列。

  - **CPU** 和**处理器**性能计数器。

对于大多数部署，UCWA CPU 平均使用率应低于 15%。 内存使用率应在 "在[Lync server 2013 中监视服务器内存容量限制](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)" 中介绍的限制范围内。

除 CPU 和内存使用率计数器之外，您可以使用以下性能计数器来帮助确定服务器上的请求何时过载：

  - **LS: web-限制和身份\\验证 web –处理中的总请求**数, 指示服务器上的挂起 WEB 请求数。 当此计数器达到 10,000 时，后续请求将失败，错误消息为“503 - 服务不可用”。

  - **排队\\的 ASP.NET 请求**(应始终为零)。

<div>


> [!NOTE]  
> 如果您达到或超过这些值, 则应该重新访问和重新计算您的容量规划, 以便对托管 Web 服务的计算机进行正确的 CPU、内核数和内存的调整。



</div>

**对于 Mobility Service (Mcx)：**

  - Internet Information Services (IIS) 管理器中的**CSIntMcxAppPool**和**CSExtMcxAppPool**工作进程。 在“**工作进程**”窗格中，查看“**CPU 百分比**”和“**专用字节 (KB)**”（内存）列。

  - **CPU** 和**处理器**性能计数器。

对于大多数部署，Mobility Service CPU 平均使用率应低于 15%。 内存使用率应在 "在[Lync server 2013 中监视服务器内存容量限制](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)" 中介绍的限制范围内。

除 CPU 和内存使用率计数器之外，您可以使用以下 ASP.NET 性能计数器来帮助确定服务器上的请求何时过载：

  - **ASP.NET v 2.0.50727\\请求 "当前**", 这表示服务器上已挂起的 web 请求数。 当此计数器达到 5,000 时，后续请求将失败，错误消息为“503 - 服务不可用”。

  - **排队\\的 ASP.NET 请求**(应始终为零)。

<div>


> [!NOTE]  
> 如果您达到或超过这些值, 则应该重新访问和重新计算您的容量规划, 以便正确调整托管 Web 服务的计算机的 CPU、内核数和内存的大小。



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

