---
title: 配置 Mobility Service 以实现高性能 Skype 中的业务服务器
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 摘要： 了解业务服务器的 Skype 中 Mobility Service。
ms.openlocfilehash: 3e3f0df7550a64236335108453f0c35d902a1713
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197490"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="59737-103">配置 Mobility Service 以实现高性能 Skype 中的业务服务器</span><span class="sxs-lookup"><span data-stu-id="59737-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="59737-104">**摘要：** 了解业务服务器中 Skype Mobility Service。</span><span class="sxs-lookup"><span data-stu-id="59737-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="59737-105">本主题仅适用于 Skype 的业务服务器 Mobility Service (Mcx)，而不适用于对统一通信 Web API (UCWA)，如 Lync Server 2013 累积更新中提供： 2013 年 2 月。</span><span class="sxs-lookup"><span data-stu-id="59737-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="59737-106">在 Internet 信息服务 (IIS) 7.5 安装 Mobility Service (Mcx) 时，Mobility Service 安装程序在前端服务器上配置某些性能设置。</span><span class="sxs-lookup"><span data-stu-id="59737-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="59737-107">建议您使用 IIS 7.5 以实现移动功能。</span><span class="sxs-lookup"><span data-stu-id="59737-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="59737-108">这些设置会影响 Mobility Service 允许的最大并发用户请求数和最大线程数。</span><span class="sxs-lookup"><span data-stu-id="59737-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="59737-109">以下是性能设置：</span><span class="sxs-lookup"><span data-stu-id="59737-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="59737-110">IIS 7.5 上的 Mcx 设置</span><span class="sxs-lookup"><span data-stu-id="59737-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="59737-111">将 **maxConcurrentThreadsPerCPU** 设置为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="59737-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="59737-112">将 **maxConcurrentRequestsPerCPU** 设置为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="59737-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="59737-113">将 ASP.NET 进程模型设置为 AutoConfig（仅针对 IIS 7.5）。</span><span class="sxs-lookup"><span data-stu-id="59737-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="59737-114">将 HTTP.sys 队列限制设置为 1,000（默认值）。</span><span class="sxs-lookup"><span data-stu-id="59737-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

