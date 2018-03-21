---
title: "Skype for Business Online 的代理服务器"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: "本文将提供相关指南，帮助你为 Skype for Business 使用代理服务器。"
ms.openlocfilehash: 29438474524c7c1e518fb3130fdaf436e562d76e
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2018
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="5a8f9-103">Skype for Business Online 的代理服务器</span><span class="sxs-lookup"><span data-stu-id="5a8f9-103">Proxy Servers for Skype for Business Online</span></span>

<span data-ttu-id="5a8f9-104">本文将提供相关指南，帮助你为 Skype for Business 使用代理服务器。</span><span class="sxs-lookup"><span data-stu-id="5a8f9-104">This article will help you with guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="5a8f9-105">建议不使用代理服务器</span><span class="sxs-lookup"><span data-stu-id="5a8f9-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="5a8f9-p101">考虑到通过代理的 Skype for Business 流量，Microsoft 建议绕过代理。代理并不会使 Skype for Business 更加安全，因为 Skype for Business 的流量已经过加密。</span><span class="sxs-lookup"><span data-stu-id="5a8f9-p101">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Skype for Business more secure because its traffic is already encrypted.</span></span>
  
<span data-ttu-id="5a8f9-p102">另外，使用代理会产生问题。环境中可能会出现由于延迟和数据包丢失而引起的与性能相关的问题。此类问题会对音频和视频等 Skype for Business 场景中的体验带来负面影响，因为在这些场景中，实时流至关重要。</span><span class="sxs-lookup"><span data-stu-id="5a8f9-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="5a8f9-111">如果需要使用代理服务器</span><span class="sxs-lookup"><span data-stu-id="5a8f9-111">If you need to use a proxy server</span></span>

<span data-ttu-id="5a8f9-p103">有些组织无法为 Skype for Business 流量绕过代理。如果你是这种情况，需要留意上面提到的问题。</span><span class="sxs-lookup"><span data-stu-id="5a8f9-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="5a8f9-114">Microsoft 还强烈建议：</span><span class="sxs-lookup"><span data-stu-id="5a8f9-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="5a8f9-115">使用外部 DNS 解析</span><span class="sxs-lookup"><span data-stu-id="5a8f9-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="5a8f9-116">使用基于直接 UDP 的路由</span><span class="sxs-lookup"><span data-stu-id="5a8f9-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="5a8f9-117">允许 UDP 流量</span><span class="sxs-lookup"><span data-stu-id="5a8f9-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="5a8f9-118">请遵循我们的网络指南中提供的其他建议：</span><span class="sxs-lookup"><span data-stu-id="5a8f9-118">Following the other recommendations in our Networking guidelines:</span></span>
    
  - [<span data-ttu-id="5a8f9-119">Skype for Business Online 中的媒体质量和网络连接性能</span><span class="sxs-lookup"><span data-stu-id="5a8f9-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="5a8f9-120">为 Skype for Business Online 优化网络</span><span class="sxs-lookup"><span data-stu-id="5a8f9-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="5a8f9-121">遵循本指南应尽可能减少潜在问题。</span><span class="sxs-lookup"><span data-stu-id="5a8f9-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="proxy-vendors-with-built-in-skype-for-business-support-or-configuration-options"></a><span data-ttu-id="5a8f9-122">具有内置 Skype for Business 支持或配置选项的代理供应商</span><span class="sxs-lookup"><span data-stu-id="5a8f9-122">Proxy vendors with built-in Skype for Business support or configuration options</span></span>

<span data-ttu-id="5a8f9-123">本部分包含提供的产品或服务已证明可以成功用于 Skype for Business 流量的代理供应商的信息。</span><span class="sxs-lookup"><span data-stu-id="5a8f9-123">This section will contain information about proxy vendors who provide products or services that are proven to work successfully with Skype for Business traffic.</span></span>
  
<span data-ttu-id="5a8f9-124">对于使用 **Bluecoat 代理解决方案** 的组织，新固件已发布，可以解决关于以下方面的若干个问题：</span><span class="sxs-lookup"><span data-stu-id="5a8f9-124">For organizations using **Bluecoat Proxy solutions**, a new firmware has been released which addresses several issues with:</span></span>
    
  - <span data-ttu-id="5a8f9-125">SSL 拦截</span><span class="sxs-lookup"><span data-stu-id="5a8f9-125">SSL interception</span></span>
    
  - <span data-ttu-id="5a8f9-126">OCSP/SRL 检查</span><span class="sxs-lookup"><span data-stu-id="5a8f9-126">OCSP/SRL checks</span></span>
    
  - <span data-ttu-id="5a8f9-127">基于 TLS 的 SIP</span><span class="sxs-lookup"><span data-stu-id="5a8f9-127">SIP over TLS</span></span>
    
  - <span data-ttu-id="5a8f9-128">对 TURN 的支持</span><span class="sxs-lookup"><span data-stu-id="5a8f9-128">support for TURN</span></span>
    
<span data-ttu-id="5a8f9-p104">Bluecoat 对 Skype for Business 的本地支持很容易启用，以便识别相关流量并相应地加以管理。这样可确保实现最佳的身份验证、信号传输和媒体流量流，以提供非凡的用户体验，且不会产生安全问题。</span><span class="sxs-lookup"><span data-stu-id="5a8f9-p104">Bluecoat's native support for Skype for Business can easily be enabled, allowing for the identification of relevant traffic, and managing it appropriately. This ensures optimal authentication, signaling, and media traffic flow, to provide a great user experience without security concerns.</span></span>
    
<span data-ttu-id="5a8f9-131">Bluecoat 代理是否属于您的网络拓扑，请参阅以下链接： https://support.symantec.com/en_US/article.DOC9757.html</span><span class="sxs-lookup"><span data-stu-id="5a8f9-131">Please refer to the following link if Bluecoat Proxy is a part of your network topology: https://support.symantec.com/en_US/article.DOC9757.html</span></span>

## <a name="related-topics"></a><span data-ttu-id="5a8f9-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="5a8f9-132">Related topics</span></span>

[<span data-ttu-id="5a8f9-133">为 Skype for Business Online 优化网络</span><span class="sxs-lookup"><span data-stu-id="5a8f9-133">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

## <a name="feedback"></a><span data-ttu-id="5a8f9-134">反馈意见？</span><span class="sxs-lookup"><span data-stu-id="5a8f9-134">Feedback?</span></span>
<span data-ttu-id="5a8f9-135">提供产品反馈意见或让我们知道我们所执行的信息，请参阅[Skype 业务反馈](https://www.skypefeedback.com)。</span><span class="sxs-lookup"><span data-stu-id="5a8f9-135">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>