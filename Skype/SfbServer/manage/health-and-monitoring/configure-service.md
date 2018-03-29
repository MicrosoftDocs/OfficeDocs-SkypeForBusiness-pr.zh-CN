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
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server-2015"></a><span data-ttu-id="805c3-103">在 Skype for Business Server 2015 中配置 Mobility Service 以实现高性能</span><span class="sxs-lookup"><span data-stu-id="805c3-103">Configure Mobility Service for high performance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="805c3-104">**摘要：**了解业务服务器 2015 Skype 的移动服务。</span><span class="sxs-lookup"><span data-stu-id="805c3-104">**Summary:** Learn about the Mobility Service in Skype for Business Server 2015.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="805c3-105">本主题仅适用于 Skype 业务服务器 2015年移动服务 (Mcx) 并不会应用到统一通信 Web API (UCWA)，Lync Server 2013 累积更新中提供： 2 月 2013年。</span><span class="sxs-lookup"><span data-stu-id="805c3-105">This topic applies only to the Skype for Business Server 2015 Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="805c3-106">在 Internet Information Services (IIS) 7.5 安装移动服务 (Mcx) 时，移动服务安装程序会在前端服务器上配置某些性能设置。</span><span class="sxs-lookup"><span data-stu-id="805c3-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="805c3-107">建议您使用 IIS 7.5 以实现移动功能。</span><span class="sxs-lookup"><span data-stu-id="805c3-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="805c3-108">这些设置会影响 Mobility Service 允许的最大并发用户请求数和最大线程数。</span><span class="sxs-lookup"><span data-stu-id="805c3-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="805c3-109">以下是性能设置：</span><span class="sxs-lookup"><span data-stu-id="805c3-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="805c3-110">IIS 7.5 上的 Mcx 设置</span><span class="sxs-lookup"><span data-stu-id="805c3-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="805c3-111">**maxConcurrentThreadsPerCPU**设置为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="805c3-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="805c3-112">**maxConcurrentRequestsPerCPU**设置为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="805c3-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="805c3-113">将 ASP.NET 进程模型设置为 AutoConfig（仅针对 IIS 7.5）。</span><span class="sxs-lookup"><span data-stu-id="805c3-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="805c3-114">将 HTTP.sys 队列限制设置为 1,000（默认值）。</span><span class="sxs-lookup"><span data-stu-id="805c3-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

