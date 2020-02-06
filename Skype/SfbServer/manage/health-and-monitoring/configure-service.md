---
title: 在 Skype for business Server 中配置高性能的移动服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
description: 摘要：了解 Skype for Business 服务器中的移动服务。
ms.openlocfilehash: d50aab5ced14753a7665c6560220d1dfdca1061d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818052"
---
# <a name="configure-mobility-service-for-high-performance-in-skype-for-business-server"></a><span data-ttu-id="d556e-103">在 Skype for business Server 中配置高性能的移动服务</span><span class="sxs-lookup"><span data-stu-id="d556e-103">Configure Mobility Service for high performance in Skype for Business Server</span></span>
 
<span data-ttu-id="d556e-104">**摘要：** 了解 Skype for Business 服务器中的移动服务。</span><span class="sxs-lookup"><span data-stu-id="d556e-104">**Summary:** Learn about the Mobility Service in Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d556e-105">本主题仅适用于 Skype for Business Server 移动服务（Mcx），不适用于在 Lync Server 2013 的累积更新中提供的统一通信 Web API （UCWA）：2月2013。</span><span class="sxs-lookup"><span data-stu-id="d556e-105">This topic applies only to the Skype for Business Server Mobility Service (Mcx), and does not apply to Unified Communications Web API (UCWA), as delivered in the Cumulative Updates for Lync Server 2013: February 2013.</span></span> 
  
<span data-ttu-id="d556e-106">在 Internet Information Services （IIS）7.5 上安装移动服务（Mcx）时，移动服务安装程序将在前端服务器上配置某些性能设置。</span><span class="sxs-lookup"><span data-stu-id="d556e-106">When you install the Mobility Service (Mcx) on Internet Information Services (IIS) 7.5, the Mobility Service installer configures some performance settings on the Front End Server.</span></span> <span data-ttu-id="d556e-107">建议您使用 IIS 7.5 以实现移动功能。</span><span class="sxs-lookup"><span data-stu-id="d556e-107">We recommend that you use IIS 7.5 for mobility.</span></span> <span data-ttu-id="d556e-108">这些设置会影响 Mobility Service 允许的最大并发用户请求数和最大线程数。</span><span class="sxs-lookup"><span data-stu-id="d556e-108">The settings affect the maximum number of concurrent user requests and the maximum number of threads that are allowed for the Mobility Service.</span></span>
  
<span data-ttu-id="d556e-109">以下是性能设置：</span><span class="sxs-lookup"><span data-stu-id="d556e-109">Here are the performance settings:</span></span>
  
### <a name="settings-for-mcx-on-iis-75"></a><span data-ttu-id="d556e-110">IIS 7.5 上的 Mcx 设置</span><span class="sxs-lookup"><span data-stu-id="d556e-110">Settings for Mcx on IIS 7.5</span></span>

1. <span data-ttu-id="d556e-111">将 **maxConcurrentThreadsPerCPU** 设置为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="d556e-111">**maxConcurrentThreadsPerCPU** is set to zero (0).</span></span>
    
2. <span data-ttu-id="d556e-112">将 **maxConcurrentRequestsPerCPU** 设置为零 (0)。</span><span class="sxs-lookup"><span data-stu-id="d556e-112">**maxConcurrentRequestsPerCPU** is set to zero (0).</span></span>
    
3. <span data-ttu-id="d556e-113">将 ASP.NET 进程模型设置为 AutoConfig（仅针对 IIS 7.5）。</span><span class="sxs-lookup"><span data-stu-id="d556e-113">ASP.NET process model is set to AutoConfig (for IIS 7.5 only).</span></span>
    
4. <span data-ttu-id="d556e-114">将 HTTP.sys 队列限制设置为 1,000（默认值）。</span><span class="sxs-lookup"><span data-stu-id="d556e-114">HTTP.sys queue limit is set to 1,000 (by default).</span></span>
    

