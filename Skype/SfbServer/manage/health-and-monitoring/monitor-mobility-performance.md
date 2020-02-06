---
title: 监视移动版 Skype for business 服务器的性能
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
ms.assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
description: 摘要：了解 Skype for Business 服务器中的移动服务（Mcx）和统一通信 Web API （UCWA）。
ms.openlocfilehash: 4d604c46704881a055385336f8b1ff32862d929a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817831"
---
# <a name="monitor-mobility-for-performance-in-skype-for-business-server"></a><span data-ttu-id="7e10e-103">监视移动版 Skype for business 服务器的性能</span><span class="sxs-lookup"><span data-stu-id="7e10e-103">Monitor mobility for performance in Skype for Business Server</span></span>
 
<span data-ttu-id="7e10e-104">**摘要：** 了解 Skype for Business 服务器中的移动服务（Mcx）和统一通信 Web API （UCWA）。</span><span class="sxs-lookup"><span data-stu-id="7e10e-104">**Summary:** Learn about the Mobility Service (Mcx) and the Unified Communications Web API (UCWA) in Skype for Business Server.</span></span>
  
<span data-ttu-id="7e10e-105">Skype for Business Server 移动服务（Mcx）和统一通信 Web API （UCWA）增加前端服务器和前端池的负载。</span><span class="sxs-lookup"><span data-stu-id="7e10e-105">The Skype for Business Server Mobility Service (Mcx) and the Unified Communications Web API (UCWA) increase the load on Front End Servers and Front End pools.</span></span> <span data-ttu-id="7e10e-106">即使在移动应用程序被最小化的情况下也保持与服务器的连接的移动设备（如运行 Lync 2010 Mobile 的 Android 和 Nokia 设备）以及运行 Lync 2013 移动设备的 Android 和 Apple 设备的负载比当移动应用程序最小化时，终止与服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="7e10e-106">Mobile devices that maintain a connection to the server even when the mobile application is minimized, such as Android and Nokia devices running Lync 2010 Mobile, as well as Android and Apple devices running Lync 2013 Mobile, impose a greater load than devices that terminate their connection to the server when the mobile application is minimized.</span></span> <span data-ttu-id="7e10e-107">随着移动性用途的增加，您必须监视移动性性能以确定何时需要增加容量。</span><span class="sxs-lookup"><span data-stu-id="7e10e-107">As your mobility usage increases, you must monitor mobility performance to determine when you need to increase your capacity.</span></span>

> [!NOTE]
> <span data-ttu-id="7e10e-108">在 Skype for Business Server 2019 中，MCX （移动服务）对旧式移动客户端的支持不再可用。</span><span class="sxs-lookup"><span data-stu-id="7e10e-108">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="7e10e-109">所有当前 Skype for business 移动客户端都已使用统一通信 Web API （UCWA）来支持即时消息（IM）、状态和联系人。</span><span class="sxs-lookup"><span data-stu-id="7e10e-109">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="7e10e-110">具有使用 MCX 的旧客户端的用户将需要升级到当前客户端。</span><span class="sxs-lookup"><span data-stu-id="7e10e-110">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
<span data-ttu-id="7e10e-111">有几项限制会影响移动性能：</span><span class="sxs-lookup"><span data-stu-id="7e10e-111">Several limits influence mobility performance:</span></span> 
  
- <span data-ttu-id="7e10e-112">可用内存</span><span class="sxs-lookup"><span data-stu-id="7e10e-112">Available memory</span></span>
    
- <span data-ttu-id="7e10e-113">请求队列限制</span><span class="sxs-lookup"><span data-stu-id="7e10e-113">Request queue limit</span></span>
    
- <span data-ttu-id="7e10e-114">并发连接</span><span class="sxs-lookup"><span data-stu-id="7e10e-114">Concurrent connections</span></span>
    
- <span data-ttu-id="7e10e-115">IIS 队列长度</span><span class="sxs-lookup"><span data-stu-id="7e10e-115">IIS queue length</span></span>
    
<span data-ttu-id="7e10e-p103">可影响移动性能的服务器上的其他限制包括最多 12 个并发登录、身份验证、会话续订和终止。对于大多数部署，无需修改这些最大值。</span><span class="sxs-lookup"><span data-stu-id="7e10e-p103">Other limits on servers that can influence mobility performance are a maximum of 12 concurrent sign-ins, authentications, session renewals, and terminations. These maximums do not need to be modified for most deployments.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="7e10e-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="7e10e-118">In this section</span></span>

- [<span data-ttu-id="7e10e-119">监视 Skype for Business 服务器中的服务器内存容量限制</span><span class="sxs-lookup"><span data-stu-id="7e10e-119">Monitor for server memory capacity limits in Skype for Business Server</span></span>](server-memory-capacity-limits.md)
    
- [<span data-ttu-id="7e10e-120">在 Skype for Business 服务器中监视移动服务和 UCWA 使用情况</span><span class="sxs-lookup"><span data-stu-id="7e10e-120">Monitor Mobility Service and UCWA usage in Skype for Business Server</span></span>](service-and-ucwa-usage.md)
    
- [<span data-ttu-id="7e10e-121">在 Skype for business Server 中配置高性能的移动服务</span><span class="sxs-lookup"><span data-stu-id="7e10e-121">Configure Mobility Service for high performance in Skype for Business Server</span></span>](configure-service.md)
    
- [<span data-ttu-id="7e10e-122">在 Skype for Business 服务器中监视 IIS 请求跟踪日志文件</span><span class="sxs-lookup"><span data-stu-id="7e10e-122">Monitoring IIS request tracing log files in Skype for Business Server</span></span>](iis-request-tracing-log-files.md)
    
- [<span data-ttu-id="7e10e-123">Skype for Business 服务器中的移动性能计数器</span><span class="sxs-lookup"><span data-stu-id="7e10e-123">Mobility performance counters in Skype for Business Server</span></span>](performance-counters.md)
    

