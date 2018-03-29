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
# <a name="monitor-mobility-for-performance-in-skype-for-business-server-2015"></a><span data-ttu-id="ae910-103">在 Skype for Business Server 2015 中监视移动性能</span><span class="sxs-lookup"><span data-stu-id="ae910-103">Monitor mobility for performance in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ae910-104">**摘要：**了解有关移动服务 (Mcx) 和统一的通信 Web API (UCWA) 在 Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="ae910-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ae910-105">Skype 业务服务器移动服务 (Mcx) 和统一通信 Web API (UCWA) 增加前端服务器和前端池上的负载。</span><span class="sxs-lookup"><span data-stu-id="ae910-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="ae910-106">即使在移动应用程序最小化，如 Android 和诺基亚设备运行 Lync 2010 移动，以及运行 Lync 2013 移动，Android 和苹果的设备时保持与服务器的连接的移动设备施加比设备的负荷越大，移动应用程序已最小化时终止与服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="ae910-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="ae910-107">随着移动使用率不断增加，必须监视移动性能，以确定何时需要增加容量。</span><span class="sxs-lookup"><span data-stu-id="ae910-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>
  
<span data-ttu-id="ae910-108">有几项限制会影响移动性能：</span><span class="sxs-lookup"><span data-stu-id="ae910-108">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="ae910-109">可用内存</span><span class="sxs-lookup"><span data-stu-id="ae910-109">Available memory</span></span>
    
- <span data-ttu-id="ae910-110">请求队列限制</span><span class="sxs-lookup"><span data-stu-id="ae910-110">Request queue limit</span></span>
    
- <span data-ttu-id="ae910-111">并发连接</span><span class="sxs-lookup"><span data-stu-id="ae910-111">Concurrent connections</span></span>
    
- <span data-ttu-id="ae910-112">IIS 队列长度</span><span class="sxs-lookup"><span data-stu-id="ae910-112">IIS queue length</span></span>
    
<span data-ttu-id="ae910-p102">可影响移动性能的服务器上的其他限制包括最多 12 个并发登录、身份验证、会话续订和终止。对于大多数部署，无需修改这些最大值。</span><span class="sxs-lookup"><span data-stu-id="ae910-p102">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="ae910-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="ae910-115">In this section</span></span>

- [<span data-ttu-id="ae910-116">服务器内存容量限制在商业服务器 2015年的 Skype 的监视器</span><span class="sxs-lookup"><span data-stu-id="ae910-116">Monitor for server memory capacity limits in Skype for Business Server 2015</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="ae910-117">在 Skype 的移动服务和 UCWA 使用情况监视业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="ae910-117">Monitor Mobility Service and UCWA usage in Skype for Business Server 2015</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="ae910-118">在 Skype 的业务服务器 2015年的高性能配置移动服务</span><span class="sxs-lookup"><span data-stu-id="ae910-118">Configure Mobility Service for high performance in Skype for Business Server 2015</span></span>](configure-service.md)
    
- [<span data-ttu-id="ae910-119">监视 IIS 请求跟踪的日志文件在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="ae910-119">Monitoring IIS request tracing log files in Skype for Business Server 2015</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="ae910-120">在业务服务器 2015年的 Skype 的移动性能计数器</span><span class="sxs-lookup"><span data-stu-id="ae910-120">Mobility performance counters in Skype for Business Server 2015</span></span>](performance-counters.md)
    

