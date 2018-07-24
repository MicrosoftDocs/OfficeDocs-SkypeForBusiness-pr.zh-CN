---
title: 监视移动性的 Skype 业务服务器的性能
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 摘要： 了解 Mobility Service (Mcx) 和统一的通信 Web API (UCWA) 中 Skype 业务服务器。
ms.openlocfilehash: 4affcb532697f24c87d62e18fc26552639dc00e1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20990635"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="0511d-103">监视移动性的 Skype 业务服务器的性能</span><span class="sxs-lookup"><span data-stu-id="0511d-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="0511d-104">**摘要：** 了解有关 Mobility Service (Mcx) 和统一的通信 Web API (UCWA) Skype 中的业务服务器。</span><span class="sxs-lookup"><span data-stu-id="0511d-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="0511d-105">针对业务服务器 Mobility Service (Mcx) 和统一通信 Web API (UCWA) Skype 增加前端服务器和前端池的负载。</span><span class="sxs-lookup"><span data-stu-id="0511d-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="0511d-106">移动应用程序最小化，例如 Android 和 Nokia 设备运行 Lync 2010 移动，以及 Android 和 Apple 设备运行 Lync 2013 Mobile，即使维护与服务器的连接的移动设备施加更多负载比设备的移动应用程序最小化时终止其连接到服务器。</span><span class="sxs-lookup"><span data-stu-id="0511d-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="0511d-107">随着增加移动使用情况，您必须监视移动性能，以确定当您需要增加容量。</span><span class="sxs-lookup"><span data-stu-id="0511d-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="0511d-108">MCX 旧的移动客户端支持不再可用的业务服务器 2019 Skype 中。</span><span class="sxs-lookup"><span data-stu-id="0511d-108">MCX support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="0511d-109">您的用户需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="0511d-109">Your users will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="0511d-110">有几项限制会影响移动性能：</span><span class="sxs-lookup"><span data-stu-id="0511d-110">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="0511d-111">可用内存</span><span class="sxs-lookup"><span data-stu-id="0511d-111">Available memory</span></span>
    
- <span data-ttu-id="0511d-112">请求队列限制</span><span class="sxs-lookup"><span data-stu-id="0511d-112">Request queue limit</span></span>
    
- <span data-ttu-id="0511d-113">并发连接</span><span class="sxs-lookup"><span data-stu-id="0511d-113">Concurrent connections</span></span>
    
- <span data-ttu-id="0511d-114">IIS 队列长度</span><span class="sxs-lookup"><span data-stu-id="0511d-114">IIS queue length</span></span>
    
<span data-ttu-id="0511d-p103">可影响移动性能的服务器上的其他限制包括最多 12 个并发登录、身份验证、会话续订和终止。对于大多数部署，无需修改这些最大值。</span><span class="sxs-lookup"><span data-stu-id="0511d-p103">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="0511d-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="0511d-117">In this section</span></span>

- [<span data-ttu-id="0511d-118">监控服务器内存容量限制 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="0511d-118">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="0511d-119">监视 Mobility Service 和 UCWA 使用量 Skype 的业务服务器</span><span class="sxs-lookup"><span data-stu-id="0511d-119">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="0511d-120">配置 Mobility Service 以实现高性能 Skype 中的业务服务器</span><span class="sxs-lookup"><span data-stu-id="0511d-120">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="0511d-121">监视 IIS 请求跟踪日志文件中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="0511d-121">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="0511d-122">Skype 业务服务器中的移动性能计数器</span><span class="sxs-lookup"><span data-stu-id="0511d-122">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

