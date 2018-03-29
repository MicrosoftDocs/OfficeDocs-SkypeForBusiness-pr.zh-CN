---
title: 在 Skype for Business Server 2015 中监视移动性能
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 摘要： 了解移动服务 (Mcx) 和统一的通信 Web API (UCWA) 在 Skype 业务服务器 2015年。
ms.openlocfilehash: 1981bff8398f3fab9206f9dab748c545268f7edf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中监视移动性能
 
**摘要：**了解有关移动服务 (Mcx) 和统一的通信 Web API (UCWA) 在 Skype 业务服务器 2015年。
  
Skype 业务服务器移动服务 (Mcx) 和统一通信 Web API (UCWA) 增加前端服务器和前端池上的负载。 即使在移动应用程序最小化，如 Android 和诺基亚设备运行 Lync 2010 移动，以及运行 Lync 2013 移动，Android 和苹果的设备时保持与服务器的连接的移动设备施加比设备的负荷越大，移动应用程序已最小化时终止与服务器的连接。 随着移动使用率不断增加，必须监视移动性能，以确定何时需要增加容量。
  
有几项限制会影响移动性能： 
  
- 可用内存
    
- 请求队列限制
    
- 并发连接
    
- IIS 队列长度
    
可影响移动性能的服务器上的其他限制包括最多 12 个并发登录、身份验证、会话续订和终止。对于大多数部署，无需修改这些最大值。
  
## <a name="in-this-section"></a>本节内容

- [服务器内存容量限制在商业服务器 2015年的 Skype 的监视器](server-memory-capacity-limits.md)
    
- [在 Skype 的移动服务和 UCWA 使用情况监视业务服务器 2015](service-and-ucwa-usage.md)
    
- [在 Skype 的业务服务器 2015年的高性能配置移动服务](configure-service.md)
    
- [监视 IIS 请求跟踪的日志文件在 Skype 业务服务器 2015](iis-request-tracing-log-files.md)
    
- [在业务服务器 2015年的 Skype 的移动性能计数器](performance-counters.md)
    

