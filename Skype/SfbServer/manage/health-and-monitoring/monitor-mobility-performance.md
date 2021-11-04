---
title: 监视移动性能以Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 摘要：了解 Mobility Service (Mcx) 和 Skype for Business Server 中的 UCWA (统一) API Skype for Business Server。
ms.openlocfilehash: 5f8adbbdc653d8cdf2e19ce3f82fc4fdb0383505
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746918"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a>监视移动性能以Skype for Business Server
 
**摘要：** 了解 Mobility Service (Mcx) 和统一通信 Web API (UCWA) Skype for Business Server。
  
Skype for Business Server Mobility Service (Mcx) 和统一通信 Web API (UCWA) 会增加前端服务器和前端池上的负载。 即使移动应用程序已最小化，也保持与服务器连接的移动设备（如运行 Lync 2010 Mobile 的 Android 和 Nokia 设备，以及运行 Lync 2013 Mobile 的 Android 和 Apple 设备）比在最小化移动应用程序时终止与服务器连接的设备造成更大的负载。 随着移动使用率的增加，您必须监视移动性能以确定何时需要增加容量。

> [!NOTE]
> MCX (Mobility Service) 2019 年不再提供对旧版移动客户端Skype for Business Server支持。 所有当前Skype for Business客户端已使用统一通信 Web API (UCWA) 支持即时消息 (IM) 、状态和联系人。 使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
有几项限制会影响移动性能： 
  
- 可用内存
    
- 请求队列限制
    
- 并发连接
    
- IIS 队列长度
    
可影响移动性能的服务器上的其他限制最多为 12 个并发登录、身份验证、会话续订和终止。 对于大多数部署，无需修改这些最大值。
  
## <a name="in-this-section"></a>本节内容

- [监视服务器内存容量限制Skype for Business Server](server-memory-capacity-limits.md)
    
- [监视移动服务和 UCWA 在Skype for Business Server](service-and-ucwa-usage.md)
    
- [配置 Mobility Service 以在 Skype for Business Server](configure-service.md)
    
- [监视 IIS 请求跟踪日志文件Skype for Business Server](iis-request-tracing-log-files.md)
    
- [移动性能计数器Skype for Business Server](performance-counters.md)
    

