---
title: 监视移动性的 Skype 业务服务器的性能
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 摘要： 了解 Mobility Service (Mcx) 和统一的通信 Web API (UCWA) 中 Skype 业务服务器。
ms.openlocfilehash: f4932a9ff14500aa16d2e183a3b665e7106302ee
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "21226915"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>监视移动性的 Skype 业务服务器的性能
 
**摘要：** 了解有关 Mobility Service (Mcx) 和统一的通信 Web API (UCWA) Skype 中的业务服务器。
  
针对业务服务器 Mobility Service (Mcx) 和统一通信 Web API (UCWA) Skype 增加前端服务器和前端池的负载。 移动应用程序最小化，例如 Android 和 Nokia 设备运行 Lync 2010 移动，以及 Android 和 Apple 设备运行 Lync 2013 Mobile，即使维护与服务器的连接的移动设备施加更多负载比设备的移动应用程序最小化时终止其连接到服务器。 随着增加移动使用情况，您必须监视移动性能，以确定当您需要增加容量。

> [!NOTE]
> MCX (Mobility Service) 支持旧的移动客户端的不再可用的业务服务器 2019 Skype 中。 业务移动客户端的所有当前 Skype 已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、 状态和联系人。 与使用 MCX 的旧客户端的用户需要升级到当前客户端。
  
有几项限制会影响移动性能： 
  
- 可用内存
    
- 请求队列限制
    
- 并发连接
    
- IIS 队列长度
    
可影响移动性能的服务器上的其他限制包括最多 12 个并发登录、身份验证、会话续订和终止。对于大多数部署，无需修改这些最大值。
  
## <a name="in-this-section"></a>本节内容

- [监控服务器内存容量限制 Skype 业务服务器](server-memory-capacity-limits.md)
    
- [监视 Mobility Service 和 UCWA 使用量 Skype 的业务服务器](service-and-ucwa-usage.md)
    
- [配置 Mobility Service 以实现高性能 Skype 中的业务服务器](configure-service.md)
    
- [监视 IIS 请求跟踪日志文件中 Skype 业务服务器](iis-request-tracing-log-files.md)
    
- [Skype 业务服务器中的移动性能计数器](performance-counters.md)
    

