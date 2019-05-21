---
title: 在 Skype for business Server 中配置高性能的移动服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: '摘要: 了解 Skype for Business 服务器中的移动服务。'
ms.openlocfilehash: 35e04fa080964495ccd9abed28c0688dd7be45a9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305841"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a>在 Skype for business Server 中配置高性能的移动服务
 
**摘要:** 了解 Skype for Business 服务器中的移动服务。
  
> [!IMPORTANT]
> 本主题仅适用于 Skype for Business Server 移动服务 (Mcx), 不适用于在 Lync Server 2013 的累积更新中提供的统一通信 Web API (UCWA): 2 月2013。 
  
在 Internet Information Services (IIS) 7.5 上安装移动服务 (Mcx) 时, 移动服务安装程序将在前端服务器上配置某些性能设置。 建议您使用 IIS 7.5 以实现移动功能。 这些设置会影响 Mobility Service 允许的最大并发用户请求数和最大线程数。
  
以下是性能设置：
  
### <a name="settings-for-mcx-on-iis-75"></a>IIS 7.5 上的 Mcx 设置

1. 将 **maxConcurrentThreadsPerCPU** 设置为零 (0)。
    
2. 将 **maxConcurrentRequestsPerCPU** 设置为零 (0)。
    
3. 将 ASP.NET 进程模型设置为 AutoConfig（仅针对 IIS 7.5）。
    
4. 将 HTTP.sys 队列限制设置为 1,000（默认值）。
    

