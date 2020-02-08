---
title: 团队或 Skype for business Online 的代理服务器
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: 本文提供有关将代理服务器与 Skype for Business 配合使用的信息。
ms.openlocfilehash: a154b36fc03dc84916d5cb4bd383ff80bef901cd
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863744"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="939b4-103">Skype for business Online 的代理服务器</span><span class="sxs-lookup"><span data-stu-id="939b4-103">Proxy servers for Skype for Business Online</span></span>

<span data-ttu-id="939b4-104">本文提供有关将代理服务器与 Skype for Business 配合使用的指南。</span><span class="sxs-lookup"><span data-stu-id="939b4-104">This article provides guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="939b4-105">建议不使用代理服务器</span><span class="sxs-lookup"><span data-stu-id="939b4-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="939b4-p101">当需要通过代理的 Skype for business 通信时，Microsoft 建议绕过代理。由于流量已加密，因此代理不会使 Skype for business 更安全。</span><span class="sxs-lookup"><span data-stu-id="939b4-p101">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="939b4-p102">并且拥有代理可能会导致问题。与性能相关的问题可通过延迟和数据包丢失引入环境。此类问题将在此类团队或 Skype for Business 方案中产生消极的体验，因为实时流非常重要。</span><span class="sxs-lookup"><span data-stu-id="939b4-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="939b4-111">如果需要使用代理服务器</span><span class="sxs-lookup"><span data-stu-id="939b4-111">If you need to use a proxy server</span></span>

<span data-ttu-id="939b4-p103">有些组织无法为 Skype for Business 流量绕过代理。如果你是这种情况，需要留意上面提到的问题。</span><span class="sxs-lookup"><span data-stu-id="939b4-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="939b4-114">Microsoft 还强烈建议：</span><span class="sxs-lookup"><span data-stu-id="939b4-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="939b4-115">使用外部 DNS 解析</span><span class="sxs-lookup"><span data-stu-id="939b4-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="939b4-116">使用基于直接 UDP 的路由</span><span class="sxs-lookup"><span data-stu-id="939b4-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="939b4-117">允许 UDP 流量</span><span class="sxs-lookup"><span data-stu-id="939b4-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="939b4-118">按照我们的网络指南中的其他建议操作：</span><span class="sxs-lookup"><span data-stu-id="939b4-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="939b4-119">Skype for Business Online 中的媒体质量和网络连接性能</span><span class="sxs-lookup"><span data-stu-id="939b4-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](media-quality-and-network-connectivity-performance.md)
    
  - [<span data-ttu-id="939b4-120">为 Skype for Business Online 优化网络</span><span class="sxs-lookup"><span data-stu-id="939b4-120">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
    
<span data-ttu-id="939b4-121">遵循本指南应尽可能减少潜在问题。</span><span class="sxs-lookup"><span data-stu-id="939b4-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="939b4-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="939b4-122">Related topics</span></span>

[<span data-ttu-id="939b4-123">为 Skype for Business Online 优化网络</span><span class="sxs-lookup"><span data-stu-id="939b4-123">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
 