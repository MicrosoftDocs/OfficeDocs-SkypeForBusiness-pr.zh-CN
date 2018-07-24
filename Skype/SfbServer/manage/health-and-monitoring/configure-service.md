---
title: 配置 Mobility Service 以实现高性能 Skype 中的业务服务器
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 摘要： 了解业务服务器的 Skype 中 Mobility Service。
ms.openlocfilehash: 5031d34a2fdcb1610325afbf58c5524a0ee28ca8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21026804"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>配置 Mobility Service 以实现高性能 Skype 中的业务服务器
 
**摘要：** 了解业务服务器中 Skype Mobility Service。
  
> [!IMPORTANT]
> 本主题仅适用于 Skype 的业务服务器 Mobility Service (Mcx)，而不适用于对统一通信 Web API (UCWA)，如 Lync Server 2013 累积更新中提供： 2013 年 2 月。 
  
在 Internet 信息服务 (IIS) 7.5 安装 Mobility Service (Mcx) 时，Mobility Service 安装程序在前端服务器上配置某些性能设置。 建议您使用 IIS 7.5 以实现移动功能。 这些设置会影响 Mobility Service 允许的最大并发用户请求数和最大线程数。
  
以下是性能设置：
  
### <a name="settings-for-mcx-on-iis-75"></a>IIS 7.5 上的 Mcx 设置

1. **将 maxConcurrentThreadsPerCPU**设置为零 (0)。
    
2. **将 maxConcurrentRequestsPerCPU**设置为零 (0)。
    
3. 将 ASP.NET 进程模型设置为 AutoConfig（仅针对 IIS 7.5）。
    
4. 将 HTTP.sys 队列限制设置为 1,000（默认值）。
    

