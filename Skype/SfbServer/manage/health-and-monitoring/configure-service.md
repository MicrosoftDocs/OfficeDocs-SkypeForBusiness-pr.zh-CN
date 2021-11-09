---
title: 配置 Mobility Service 以在 Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 摘要：了解 Skype for Business Server 中的 Mobility Service。
ms.openlocfilehash: 4c07c1e487875a41da0d1ba3c0d8872d96a5ac70
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828785"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>配置 Mobility Service 以在 Skype for Business Server
 
**摘要：** 了解移动服务在Skype for Business Server。
  
> [!IMPORTANT]
> 本主题仅适用于 Skype for Business Server Mobility Service (Mcx) ，不适用于 2013 年 2 月 Lync Server 2013 累积更新中提供的统一通信 Web API (UCWA) 。 
  
在 Internet Information Services (IIS () 7.5 Internet Information Services (安装 Mobility Service) 时，Mobility Service 安装程序会配置前端服务器上一些性能设置。 建议您使用 IIS 7.5 以实现移动功能。 这些设置会影响 Mobility Service 允许的最大并发用户请求数和最大线程数。
  
以下是性能设置：
  
### <a name="settings-for-mcx-on-iis-75"></a>设置 IIS 7.5 上的 Mcx

1. **maxConcurrentThreadsPerCPU** 设置为零 (0) 。
    
2. **maxConcurrentRequestsPerCPU** 设置为零 (0) 。
    
3. ASP.NET 仅在 IIS 7.5 (设置为自动配置) 。
    
4. HTTP.sys，默认队列限制设置为 1，000 (1，000) 。
    

