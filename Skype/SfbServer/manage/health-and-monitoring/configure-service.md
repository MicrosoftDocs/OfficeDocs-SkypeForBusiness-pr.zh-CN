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
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="f8cb8-103">配置 Mobility Service 以在 Skype for Business Server 中实现高性能</span><span class="sxs-lookup"><span data-stu-id="f8cb8-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="f8cb8-104">**摘要：** 了解 Skype for Business Server 中的 Mobility Service。</span><span class="sxs-lookup"><span data-stu-id="f8cb8-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f8cb8-105">本主题仅适用于 Skype for Business Server Mobility Service (Mcx) ，不适用于 2013 年 2 月 Lync Server 2013 累积更新中提供的统一通信 Web API (UCWA) 。</span><span class="sxs-lookup"><span data-stu-id="f8cb8-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="f8cb8-106">在 Internet Information Services (IIS) 7.5 (Mcx) 安装 Mobility Service 时，Mobility Service 安装程序在前端服务器上配置一些性能设置。</span><span class="sxs-lookup"><span data-stu-id="f8cb8-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="f8cb8-107">建议您使用 IIS 7.5 以实现移动功能。</span><span class="sxs-lookup"><span data-stu-id="f8cb8-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="f8cb8-108">这些设置影响 Mobility Service 允许的最大并发用户请求数和最大线程数。</span><span class="sxs-lookup"><span data-stu-id="f8cb8-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="f8cb8-109">以下是性能设置：</span><span class="sxs-lookup"><span data-stu-id="f8cb8-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="f8cb8-110">IIS 7.5 上 Mcx 的设置</span><span class="sxs-lookup"><span data-stu-id="f8cb8-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="f8cb8-111">**maxConcurrentThreadsPerCPU** 设置为零 (0) 。</span><span class="sxs-lookup"><span data-stu-id="f8cb8-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="f8cb8-112">**maxConcurrentRequestsPerCPU** 设置为零 (0) 。</span><span class="sxs-lookup"><span data-stu-id="f8cb8-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="f8cb8-113">ASP.NET IIS 7.5 (设置为自动配置) 。</span><span class="sxs-lookup"><span data-stu-id="f8cb8-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="f8cb8-114">HTTP.sys默认队列限制设置为 1，000 (队列) 。</span><span class="sxs-lookup"><span data-stu-id="f8cb8-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

