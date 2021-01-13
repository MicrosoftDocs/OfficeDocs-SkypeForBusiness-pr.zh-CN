---
title: 配置 Mobility Service 以在 Skype for Business Server 中实现高性能
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
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 摘要：了解 Skype for Business Server 中的 Mobility Service。
ms.openlocfilehash: 83d8d6dc7a32b05a58c738deddc8c92e43bd5557
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817032"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>配置 Mobility Service 以在 Skype for Business Server 中实现高性能
 
**摘要：** 了解 Skype for Business Server 中的 Mobility Service。
  
> [!IMPORTANT]
> 本主题仅适用于 Skype for Business Server Mobility Service (Mcx) ，不适用于 2013 年 2 月 Lync Server 2013 累积更新中提供的统一通信 Web API (UCWA) 。 
  
在 Internet Information Services (IIS) 7.5 (Mcx) 安装 Mobility Service 时，Mobility Service 安装程序在前端服务器上配置一些性能设置。 建议您使用 IIS 7.5 以实现移动功能。 这些设置影响 Mobility Service 允许的最大并发用户请求数和最大线程数。
  
以下是性能设置：
  
### <a name="settings-for-mcx-on-iis-75"></a>IIS 7.5 上 Mcx 的设置

1. **maxConcurrentThreadsPerCPU** 设置为零 (0) 。
    
2. **maxConcurrentRequestsPerCPU** 设置为零 (0) 。
    
3. ASP.NET IIS 7.5 (设置为自动配置) 。
    
4. HTTP.sys默认队列限制设置为 1，000 (队列) 。
    

