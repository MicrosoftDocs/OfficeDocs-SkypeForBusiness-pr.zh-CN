---
title: 监视移动服务和 UCWA 在Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
description: 摘要：管理 Mobility Service (Mcx) 和统一通信 Web API (UCWA) 中Skype for Business Server。
ms.openlocfilehash: a9cc79e523c3ba6671df302d844dc5e05d3bae28
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608159"
---
# <a name="monitor-mobility-service-and-ucwa-usage-in-skype-for-business-server"></a>监视移动服务和 UCWA 在Skype for Business Server
 
**摘要：** 管理 Mobility Service (Mcx) 和统一通信 Web API (UCWA) 中Skype for Business Server。

> [!NOTE]
> MCX (Mobility Service) 2019 年不再提供对旧版移动客户端Skype for Business Server支持。 所有当前Skype for Business客户端已使用统一通信 Web API (UCWA) 支持即时消息 (IM) 、状态和联系人。 使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
您应持续监视 Skype for Business Server Mobility Service (Mcx) 和 UCWA (使用的 CPU 和) 。 若要监视使用情况，可以使用以下内容：
  
 **对于统一通信 Web API (UCWA) ：**
  
- **IIS 管理器中的 LyncUcwa** Internet Information Services () 进程。 在“工作进程”窗格中，查看“CPU 百分比”和“专用字节(KB)”（内存）列。
    
- **CPU** 和 **Processor** 性能计数器。
    
对于大多数部署，UCWA CPU 平均使用率应低于 15%。 内存使用率应位于监视中服务器内存容量限制中所述的限制[Skype for Business Server。](server-memory-capacity-limits.md)
  
除了 CPU 和内存使用率计数器之外，您还可以使用以下性能计数器来帮助确定服务器何时因请求而过载：
  
- **LS：WEB - 限制和身份验证\WEB -** 处理中的请求总数，指示服务器上挂起的 Web 请求数。 当此计数器达到 10，000 时，后续请求将失败，并出现错误消息"503 - 服务不可用"。
    
- **ASP.NET\Requests Queued**（应始终为零）。
    
> [!NOTE]
> 如果满足或超过这些值，应重新访问和重新计算容量规划，以正确调整 CPU 大小、内核数和承载 Web 服务的计算机的内存。 
  
 **对于 Mobility Service (Mcx) ：**
  
- IIS 管理器中的 **CSIntMcxAppPool** 和 **CSExtMcxAppPool** Internet Information Services () 进程。 在“工作进程”窗格中，查看“CPU 百分比”和“专用字节(KB)”（内存）列。
    
- **CPU** 和 **Processor** 性能计数器。
    
对于大多数部署，Mobility Service CPU 平均使用率应低于 15%。 内存使用率应位于监视中服务器内存容量限制中所述的限制[Skype for Business Server。](server-memory-capacity-limits.md)
  
除 CPU 和内存使用率计数器之外，您可以使用以下 ASP.NET 性能计数器来帮助确定服务器上的请求何时过载：
  
- **ASP.NET v2.0.50727\Requests Current**，指示服务器上挂起的 Web 请求的数目。 当此计数器达到 5，000 时，后续请求将失败，并返回错误消息"503 - 服务不可用"。
    
- **ASP.NET\Requests Queued**（应始终为零）。
    
> [!NOTE]
> 如果满足或超过这些值，应重新访问和重新编译容量规划，以正确调整 CPU 大小、内核数和托管 Web 服务的计算机的内存大小。 

> [!NOTE]
> MCX (Mobility Service) 2019 年不再提供对旧版移动客户端Skype for Business Server支持。 所有当前Skype for Business客户端已使用统一通信 Web API (UCWA) 支持即时消息 (IM) 、状态和联系人。 使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
## <a name="see-also"></a>另请参阅

[Monitor for server memory capacity limits in Skype for Business Server](server-memory-capacity-limits.md)
