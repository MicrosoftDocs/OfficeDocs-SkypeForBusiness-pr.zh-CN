---
title: 监视 Mobility Service 和 UCWA 的使用情况
TOCTitle: 监视 Mobility Service 和 UCWA 的使用情况
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690025(v=OCS.15)
ms:contentKeyID: 49313455
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 监视 Mobility Service 和 UCWA 的使用情况

 

_**上一次修改主题：** 2013-02-14_

您应持续监视 Lync Server Mobility Service (Mcx) 和统一通信 Web API (UCWA) 所使用的 CPU 和内存。若要监视使用率，您可以使用以下任一方法：

**对于统一通信 Web API (UCWA)：**

  - Internet Information Services (IIS) 管理器中的 **LyncUcwa** 工作进程。在“工作进程”窗格中，查看“CPU 百分比”和“专用字节(KB)”（内存）列。

  - **CPU** 和 **Processor** 性能计数器。

对于大多数部署，UCWA CPU 平均使用率应低于 15%。内存使用率应不超过[针对服务器内存容量限制进行监视](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)中所述的限制。

除 CPU 和内存使用率计数器之外，您可以使用以下性能计数器来帮助确定服务器上的请求何时过载：

  - **LS:WEB – Throttling and Authentication\\WEB – Total Requests in Processing**，指示服务器上挂起的 Web 请求的数目。当此计数器达到 10,000 时，后续请求将失败，错误消息为“503 - 服务不可用”。

  - **ASP.NET\\Requests Queued**（应始终为零）。

> [!NOTE]  
> 如果满足或超出这些值，则应重新审视并重新计算您的容量规划，以确定承载 Web 服务的计算机的正确 CPU 大小、内核数和内存。



**对于 Mobility Service (Mcx)：**

  - Internet Information Services (IIS) 管理器中的 **CSIntMcxAppPool** 和 **CSExtMcxAppPool** 工作进程。在“工作进程”窗格中，查看“CPU 百分比”和“专用字节(KB)”（内存）列。

  - **CPU** 和 **Processor** 性能计数器。

对于大多数部署，Mobility Service CPU 平均使用率应低于 15%。内存使用率应不超过[针对服务器内存容量限制进行监视](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)中所述的限制。

除 CPU 和内存使用率计数器之外，您可以使用以下 ASP.NET 性能计数器来帮助确定服务器上的请求何时过载：

  - **ASP.NET v2.0.50727\\Requests Current**，指示服务器上挂起的 Web 请求的数目。当此计数器达到 5,000 时，后续请求将失败，错误消息为“503 - 服务不可用”。

  - **ASP.NET\\Requests Queued**（应始终为零）。

> [!NOTE]  
> 如果满足或超出这些值，则应重新审视并重新计算您的容量规划，以确定承载 Web 服务的计算机的正确 CPU 大小、内核数和内存。



## 另请参阅

#### 概念

[针对服务器内存容量限制进行监视](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

