---
title: 在 Skype for Business 服务器中监视移动服务和 UCWA 使用情况
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: '摘要: 在 Skype for Business 服务器中管理移动服务 (Mcx) 和统一通信 Web API (UCWA)。'
ms.openlocfilehash: 5447eb0ac8ffe468fd52c7011824cc1f2f2f7b55
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279793"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>在 Skype for Business 服务器中监视移动服务和 UCWA 使用情况
 
**摘要:** 在 Skype for Business 服务器中管理移动服务 (Mcx) 和统一通信 Web API (UCWA)。

> [!NOTE]
> 在 Skype for Business Server 2019 中, MCX (移动服务) 对旧式移动客户端的支持不再可用。 所有当前 Skype for business 移动客户端都已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、状态和联系人。 具有使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
在持续的基础上, 你应该监视 Skype for Business Server 移动服务 (Mcx) 和统一通信 Web API (UCWA) 使用的 CPU 和内存。 若要监视使用率，您可以使用以下任一方法：
  
 **对于统一通信 Web API (UCWA)：**
  
- Internet Information Services (IIS) 管理器中的**LyncUcwa**工作进程。 在“**工作进程**”窗格中，查看“**CPU 百分比**”和“**专用字节 (KB)**”（内存）列。
    
- **CPU** 和**处理器**性能计数器。
    
对于大多数部署，UCWA CPU 平均使用率应低于 15%。 内存使用率应在[监视器的 "Skype for business" 服务器的 "服务器内存容量限制](server-memory-capacity-limits.md)" 中介绍的限制范围内。
  
除 CPU 和内存使用率计数器之外，您可以使用以下性能计数器来帮助确定服务器上的请求何时过载：
  
- **LS: WEB 阻止和 Authentication\WEB-正在处理的请求总数**, 指示服务器上的挂起 WEB 请求的数量。 当此计数器达到 10,000 时，后续请求将失败，错误消息为“503 - 服务不可用”。
    
- **ASP.NET\Requests Queued**（应始终为零）。
    
> [!NOTE]
> 如果满足或超出这些值，则应重新审视并重新计算你的容量规划，以确定承载 Web 服务的计算机的正确 CPU 大小、内核数和内存。 
  
 **对于 Mobility Service (Mcx)：**
  
- Internet Information Services (IIS) 管理器中的**CSIntMcxAppPool**和**CSExtMcxAppPool**工作进程。 在“**工作进程**”窗格中，查看“**CPU 百分比**”和“**专用字节 (KB)**”（内存）列。
    
- **CPU** 和**处理器**性能计数器。
    
对于大多数部署，Mobility Service CPU 平均使用率应低于 15%。 内存使用率应在[监视器的 "Skype for business" 服务器的 "服务器内存容量限制](server-memory-capacity-limits.md)" 中介绍的限制范围内。
  
除 CPU 和内存使用率计数器之外，您可以使用以下 ASP.NET 性能计数器来帮助确定服务器上的请求何时过载：
  
- **ASP.NET v2.0.50727\Requests Current**，指示服务器上挂起的 Web 请求的数目。 当此计数器达到 5,000 时，后续请求将失败，错误消息为“503 - 服务不可用”。
    
- **ASP.NET\Requests Queued**（应始终为零）。
    
> [!NOTE]
> 如果满足或超出这些值，则应重新审视并重新计算你的容量规划，以确定承载 Web 服务的计算机的正确 CPU 大小、内核数和内存。 

> [!NOTE]
> 在 Skype for Business Server 2019 中, MCX (移动服务) 对旧式移动客户端的支持不再可用。 所有当前 Skype for business 移动客户端都已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、状态和联系人。 具有使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
## <a name="see-also"></a>另请参阅

[监视 Skype for Business 服务器中的服务器内存容量限制](server-memory-capacity-limits.md)
