---
title: 在 Skype for Business Server 2015 中监视 Mobility Service 和 UCWA 的使用情况
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 摘要： 管理 (Mcx) 的移动服务和统一的通信 Web API (UCWA) 在 Skype 业务服务器 2015年。
ms.openlocfilehash: e71d18fe90eb9a7f2fd7b6563e6d6930f2473e74
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中监视 Mobility Service 和 UCWA 的使用情况
 
**摘要：**管理 (Mcx) 的移动服务和统一的通信 Web API (UCWA) 在 Skype 业务服务器 2015年。
  
不断地，应该监视 CPU 和内存，可通过 Skype 业务服务器移动服务 (Mcx) 和统一通信 Web API (UCWA)。 若要监视使用率，您可以使用以下任一方法：
  
 **对于统一通信 Web API (UCWA)：**
  
- **LyncUcwa**工作在 Internet Information Services (IIS) 管理器进程。 在“**工作进程**”窗格中，查看“**CPU 百分比**”和“**专用字节 (KB)**”（内存）列。
    
- **CPU** 和**处理器**性能计数器。
    
对于大多数部署，UCWA CPU 平均使用率应低于 15%。 内存使用情况应属于所述[显示器中业务服务器 2015年的 Skype 的服务器内存容量限制](server-memory-capacity-limits.md)的范围之内。
  
除 CPU 和内存使用率计数器之外，您可以使用以下性能计数器来帮助确定服务器上的请求何时过载：
  
- **LS:WEB-调节和 Authentication\WEB-正在处理的请求总数**，它指示挂起的 web 服务器上的请求的次数。 当此计数器达到 10,000 时，后续请求将失败，错误消息为“503 - 服务不可用”。
    
- **ASP.NET\Requests 排队**（应始终为零）。
    
> [!NOTE]
> 如果满足或超出这些值，则应重新审视并重新计算你的容量规划，以确定承载 Web 服务的计算机的正确 CPU 大小、内核数和内存。 
  
 **对于 Mobility Service (Mcx)：**
  
- **CSIntMcxAppPool**和**CSExtMcxAppPool**中的工作进程 Internet Information Services (IIS) 管理器。 在“**工作进程**”窗格中，查看“**CPU 百分比**”和“**专用字节 (KB)**”（内存）列。
    
- **CPU** 和**处理器**性能计数器。
    
对于大多数部署，Mobility Service CPU 平均使用率应低于 15%。 内存使用情况应属于所述[显示器中业务服务器 2015年的 Skype 的服务器内存容量限制](server-memory-capacity-limits.md)的范围之内。
  
除 CPU 和内存使用率计数器之外，您可以使用以下 ASP.NET 性能计数器来帮助确定服务器上的请求何时过载：
  
- **当前的 ASP.NET v2.0.50727\Requests**，它指示挂起的 web 服务器上的请求的次数。 当此计数器达到 5,000 时，后续请求将失败，错误消息为“503 - 服务不可用”。
    
- **ASP.NET\Requests 排队**（应始终为零）。
    
> [!NOTE]
> 如果满足或超出这些值，则应重新审视并重新计算你的容量规划，以确定承载 Web 服务的计算机的正确 CPU 大小、内核数和内存。 
  
## <a name="see-also"></a>另请参阅

#### 

[服务器内存容量限制在商业服务器 2015年的 Skype 的监视器](server-memory-capacity-limits.md)

