---
title: 在 Skype for Business Server 2015 中配置 Mobility Service 以实现高性能
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 摘要： 了解业务服务器 2015年的 Skype 的移动服务。
ms.openlocfilehash: 12f64ed75195bb94365686d76cdfca841e6c9c8e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中配置 Mobility Service 以实现高性能
 
**摘要：**了解业务服务器 2015 Skype 的移动服务。
  
> [!IMPORTANT]
> 本主题仅适用于 Skype 业务服务器 2015年移动服务 (Mcx) 并不会应用到统一通信 Web API (UCWA)，Lync Server 2013 累积更新中提供： 2 月 2013年。 
  
在 Internet Information Services (IIS) 7.5 安装移动服务 (Mcx) 时，移动服务安装程序会在前端服务器上配置某些性能设置。 建议您使用 IIS 7.5 以实现移动功能。 这些设置会影响 Mobility Service 允许的最大并发用户请求数和最大线程数。
  
以下是性能设置：
  
### <a name="settings-for-mcx-on-iis-75"></a>IIS 7.5 上的 Mcx 设置

1. **maxConcurrentThreadsPerCPU**设置为零 (0)。
    
2. **maxConcurrentRequestsPerCPU**设置为零 (0)。
    
3. 将 ASP.NET 进程模型设置为 AutoConfig（仅针对 IIS 7.5）。
    
4. 将 HTTP.sys 队列限制设置为 1,000（默认值）。
    

