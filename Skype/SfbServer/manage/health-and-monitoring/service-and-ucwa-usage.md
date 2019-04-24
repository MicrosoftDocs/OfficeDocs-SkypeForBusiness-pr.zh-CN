---
title: 监视 Mobility Service 和 UCWA 使用量 Skype 的业务服务器
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 摘要： 管理业务服务器 Mobility Service (Mcx) 和 Skype 中的统一的通信 Web API (UCWA)。
ms.openlocfilehash: 79516ec6cf5371061a0287e70e6ed81f8b2a5395
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197497"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>监视 Mobility Service 和 UCWA 使用量 Skype 的业务服务器
 
**摘要：** 管理业务服务器 Mobility Service (Mcx) 和 Skype 中的统一的通信 Web API (UCWA)。

> [!NOTE]
> MCX (Mobility Service) 支持旧的移动客户端的不再可用的业务服务器 2019 Skype 中。 业务移动客户端的所有当前 Skype 已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、 状态和联系人。 与使用 MCX 的旧客户端的用户需要升级到当前客户端。
  
持续，您应监视的 CPU 和内存 Skype 用于业务服务器 Mobility Service (Mcx) 和统一通信 Web API (UCWA)。 若要监视使用率，您可以使用以下任一方法：
  
 **对于统一通信 Web API (UCWA)：**
  
- 在 Internet 信息服务 (IIS) 管理器**LyncUcwa**工作进程。 在“**工作进程**”窗格中，查看“**CPU 百分比**”和“**专用字节 (KB)**”（内存）列。
    
- **CPU** 和**处理器**性能计数器。
    
对于大多数部署，UCWA CPU 平均使用率应低于 15%。 内存使用情况应范围内[的 Skype 业务服务器中的服务器内存容量限制监视器](server-memory-capacity-limits.md)中所述的限制。
  
除 CPU 和内存使用率计数器之外，您可以使用以下性能计数器来帮助确定服务器上的请求何时过载：
  
- **LS:WEB-限制和 Authentication\WEB-正在处理的请求总数**，表示挂起的服务器上的 web 请求的次数。 当此计数器达到 10,000 时，后续请求将失败，错误消息为“503 - 服务不可用”。
    
- **ASP.NET\Requests Queued**（应始终为零）。
    
> [!NOTE]
> 如果满足或超出这些值，则应重新审视并重新计算你的容量规划，以确定承载 Web 服务的计算机的正确 CPU 大小、内核数和内存。 
  
 **对于 Mobility Service (Mcx)：**
  
- **CSIntMcxAppPool**和**CSExtMcxAppPool**中的工作进程 Internet 信息服务 (IIS) 管理器。 在“**工作进程**”窗格中，查看“**CPU 百分比**”和“**专用字节 (KB)**”（内存）列。
    
- **CPU** 和**处理器**性能计数器。
    
对于大多数部署，Mobility Service CPU 平均使用率应低于 15%。 内存使用情况应范围内[的 Skype 业务服务器中的服务器内存容量限制监视器](server-memory-capacity-limits.md)中所述的限制。
  
除 CPU 和内存使用率计数器之外，您可以使用以下 ASP.NET 性能计数器来帮助确定服务器上的请求何时过载：
  
- **ASP.NET v2.0.50727\Requests Current**，指示服务器上挂起的 Web 请求的数目。 当此计数器达到 5,000 时，后续请求将失败，错误消息为“503 - 服务不可用”。
    
- **ASP.NET\Requests Queued**（应始终为零）。
    
> [!NOTE]
> 如果满足或超出这些值，则应重新审视并重新计算你的容量规划，以确定承载 Web 服务的计算机的正确 CPU 大小、内核数和内存。 

> [!NOTE]
> MCX (Mobility Service) 支持旧的移动客户端的不再可用的业务服务器 2019 Skype 中。 业务移动客户端的所有当前 Skype 已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、 状态和联系人。 与使用 MCX 的旧客户端的用户需要升级到当前客户端。
  
## <a name="see-also"></a>另请参阅

[监控服务器内存容量限制 Skype 业务服务器](server-memory-capacity-limits.md)
