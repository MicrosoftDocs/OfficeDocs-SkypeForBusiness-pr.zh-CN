---
title: 监视移动版 Skype for business 服务器的性能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 摘要：了解 Skype for Business 服务器中的移动服务（Mcx）和统一通信 Web API （UCWA）。
ms.openlocfilehash: 4d604c46704881a055385336f8b1ff32862d929a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817831"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>监视移动版 Skype for business 服务器的性能
 
**摘要：** 了解 Skype for Business 服务器中的移动服务（Mcx）和统一通信 Web API （UCWA）。
  
Skype for Business Server 移动服务（Mcx）和统一通信 Web API （UCWA）增加前端服务器和前端池的负载。 即使在移动应用程序被最小化的情况下也保持与服务器的连接的移动设备（如运行 Lync 2010 Mobile 的 Android 和 Nokia 设备）以及运行 Lync 2013 移动设备的 Android 和 Apple 设备的负载比当移动应用程序最小化时，终止与服务器的连接。 随着移动性用途的增加，您必须监视移动性性能以确定何时需要增加容量。

> [!NOTE]
> 在 Skype for Business Server 2019 中，MCX （移动服务）对旧式移动客户端的支持不再可用。 所有当前 Skype for business 移动客户端都已使用统一通信 Web API （UCWA）来支持即时消息（IM）、状态和联系人。 具有使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
有几项限制会影响移动性能： 
  
- 可用内存
    
- 请求队列限制
    
- 并发连接
    
- IIS 队列长度
    
可影响移动性能的服务器上的其他限制包括最多 12 个并发登录、身份验证、会话续订和终止。对于大多数部署，无需修改这些最大值。
  
## <a name="in-this-section"></a>本节内容

- [监视 Skype for Business 服务器中的服务器内存容量限制](server-memory-capacity-limits.md)
    
- [在 Skype for Business 服务器中监视移动服务和 UCWA 使用情况](service-and-ucwa-usage.md)
    
- [在 Skype for business Server 中配置高性能的移动服务](configure-service.md)
    
- [在 Skype for Business 服务器中监视 IIS 请求跟踪日志文件](iis-request-tracing-log-files.md)
    
- [Skype for Business 服务器中的移动性能计数器](performance-counters.md)
    

