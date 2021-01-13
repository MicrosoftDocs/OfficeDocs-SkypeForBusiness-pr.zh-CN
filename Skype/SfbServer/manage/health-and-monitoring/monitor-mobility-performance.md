---
title: 监视 Skype for Business Server 中的移动性能
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 摘要：了解 Skype for Business Server 中的 Mobility Service (Mcx) 和统一通信 Web API (UCWA) 。
ms.openlocfilehash: d7473d22f2de0576bf6214ae43719c8bfc70d49a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816832"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>监视 Skype for Business Server 中的移动性能
 
**摘要：** 了解 Skype for Business Server 中的 Mobility Service (Mcx) 和统一通信 Web API (UCWA) 。
  
Skype for Business Server Mobility Service (Mcx) 和统一通信 Web API (UCWA) 会增加前端服务器和前端池的负载。 即使最小化了移动应用程序（如运行 Lync 2010 Mobile 的 Android 和 Nokia 设备）也保持与服务器的连接的移动设备，以及运行 Lync 2013 Mobile 的 Android 和 Apple 设备，其负载大于在最小化移动应用程序时终止与服务器连接的设备。 随着移动使用率的增加，必须监视移动性能以确定何时需要增加容量。

> [!NOTE]
> SKYPE (Server 2019 中不再提供对) 移动客户端的 MCX 移动服务支持。 所有当前的 Skype for Business 移动客户端已使用统一通信 Web API (UCWA) 来支持即时消息 (IM) 、状态和联系人。 使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
有几项限制会影响移动性能： 
  
- 可用内存
    
- 请求队列限制
    
- 并发连接
    
- IIS 队列长度
    
影响移动性能的服务器上的其他限制最多为 12 个并发登录、身份验证、会话续订和终止。 对于大多数部署，无需修改这些最大值。
  
## <a name="in-this-section"></a>本节内容

- [监视 Skype for Business Server 中的服务器内存容量限制](server-memory-capacity-limits.md)
    
- [监视 Skype for Business Server 中的 Mobility Service 和 UCWA 使用情况](service-and-ucwa-usage.md)
    
- [配置 Mobility Service 以在 Skype for Business Server 中实现高性能](configure-service.md)
    
- [在 Skype for Business Server 中监视 IIS 请求跟踪日志文件](iis-request-tracing-log-files.md)
    
- [Skype for Business Server 中的移动性能计数器](performance-counters.md)
    

