---
title: 监视 Skype for Business Server 中的移动性能
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
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 摘要：了解 Skype for Business Server 中的 Mobility Service (Mcx) 和统一通信 Web API (UCWA) 。
ms.openlocfilehash: d7473d22f2de0576bf6214ae43719c8bfc70d49a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816832"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="6da6f-103">监视 Skype for Business Server 中的移动性能</span><span class="sxs-lookup"><span data-stu-id="6da6f-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="6da6f-104">**摘要：** 了解 Skype for Business Server 中的 Mobility Service (Mcx) 和统一通信 Web API (UCWA) 。</span><span class="sxs-lookup"><span data-stu-id="6da6f-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="6da6f-105">Skype for Business Server Mobility Service (Mcx) 和统一通信 Web API (UCWA) 会增加前端服务器和前端池的负载。</span><span class="sxs-lookup"><span data-stu-id="6da6f-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="6da6f-106">即使最小化了移动应用程序（如运行 Lync 2010 Mobile 的 Android 和 Nokia 设备）也保持与服务器的连接的移动设备，以及运行 Lync 2013 Mobile 的 Android 和 Apple 设备，其负载大于在最小化移动应用程序时终止与服务器连接的设备。</span><span class="sxs-lookup"><span data-stu-id="6da6f-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="6da6f-107">随着移动使用率的增加，必须监视移动性能以确定何时需要增加容量。</span><span class="sxs-lookup"><span data-stu-id="6da6f-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="6da6f-108">SKYPE (Server 2019 中不再提供对) 移动客户端的 MCX 移动服务支持。</span><span class="sxs-lookup"><span data-stu-id="6da6f-108">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="6da6f-109">所有当前的 Skype for Business 移动客户端已使用统一通信 Web API (UCWA) 来支持即时消息 (IM) 、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="6da6f-109">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="6da6f-110">使用 MCX 的旧客户端的用户将需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="6da6f-110">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="6da6f-111">有几项限制会影响移动性能：</span><span class="sxs-lookup"><span data-stu-id="6da6f-111">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="6da6f-112">可用内存</span><span class="sxs-lookup"><span data-stu-id="6da6f-112">Available memory</span></span>
    
- <span data-ttu-id="6da6f-113">请求队列限制</span><span class="sxs-lookup"><span data-stu-id="6da6f-113">Request queue limit</span></span>
    
- <span data-ttu-id="6da6f-114">并发连接</span><span class="sxs-lookup"><span data-stu-id="6da6f-114">Concurrent connections</span></span>
    
- <span data-ttu-id="6da6f-115">IIS 队列长度</span><span class="sxs-lookup"><span data-stu-id="6da6f-115">IIS queue length</span></span>
    
<span data-ttu-id="6da6f-116">影响移动性能的服务器上的其他限制最多为 12 个并发登录、身份验证、会话续订和终止。</span><span class="sxs-lookup"><span data-stu-id="6da6f-116">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations.</span></span> <span data-ttu-id="6da6f-117">对于大多数部署，无需修改这些最大值。</span><span class="sxs-lookup"><span data-stu-id="6da6f-117">These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="6da6f-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="6da6f-118">In this section</span></span>

- [<span data-ttu-id="6da6f-119">监视 Skype for Business Server 中的服务器内存容量限制</span><span class="sxs-lookup"><span data-stu-id="6da6f-119">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="6da6f-120">监视 Skype for Business Server 中的 Mobility Service 和 UCWA 使用情况</span><span class="sxs-lookup"><span data-stu-id="6da6f-120">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="6da6f-121">配置 Mobility Service 以在 Skype for Business Server 中实现高性能</span><span class="sxs-lookup"><span data-stu-id="6da6f-121">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="6da6f-122">在 Skype for Business Server 中监视 IIS 请求跟踪日志文件</span><span class="sxs-lookup"><span data-stu-id="6da6f-122">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="6da6f-123">Skype for Business Server 中的移动性能计数器</span><span class="sxs-lookup"><span data-stu-id="6da6f-123">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

