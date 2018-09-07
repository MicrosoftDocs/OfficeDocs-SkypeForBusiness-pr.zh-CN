---
title: Skype for Business Online 的代理服务器
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: 本文将提供相关指南，帮助你为 Skype for Business 使用代理服务器。
ms.openlocfilehash: 3d83e2f6d4eb2b88a52eb949217ac2f00c72acff
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850010"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="9859e-103">Skype for Business Online 的代理服务器</span><span class="sxs-lookup"><span data-stu-id="9859e-103">Proxy Servers for Skype for Business Online</span></span>

<span data-ttu-id="9859e-104">本文将提供相关指南，帮助你为 Skype for Business 使用代理服务器。</span><span class="sxs-lookup"><span data-stu-id="9859e-104">This article will help you with guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="9859e-105">建议不使用代理服务器</span><span class="sxs-lookup"><span data-stu-id="9859e-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="9859e-p101">考虑到通过代理的 Skype for Business 流量，Microsoft 建议绕过代理。代理并不会使 Skype for Business 更加安全，因为 Skype for Business 的流量已经过加密。</span><span class="sxs-lookup"><span data-stu-id="9859e-p101">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Skype for Business more secure because its traffic is already encrypted.</span></span>
  
<span data-ttu-id="9859e-p102">另外，使用代理会产生问题。环境中可能会出现由于延迟和数据包丢失而引起的与性能相关的问题。此类问题会对音频和视频等 Skype for Business 场景中的体验带来负面影响，因为在这些场景中，实时流至关重要。</span><span class="sxs-lookup"><span data-stu-id="9859e-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="9859e-111">如果需要使用代理服务器</span><span class="sxs-lookup"><span data-stu-id="9859e-111">If you need to use a proxy server</span></span>

<span data-ttu-id="9859e-p103">有些组织无法为 Skype for Business 流量绕过代理。如果你是这种情况，需要留意上面提到的问题。</span><span class="sxs-lookup"><span data-stu-id="9859e-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="9859e-114">Microsoft 还强烈建议：</span><span class="sxs-lookup"><span data-stu-id="9859e-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="9859e-115">使用外部 DNS 解析</span><span class="sxs-lookup"><span data-stu-id="9859e-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="9859e-116">使用基于直接 UDP 的路由</span><span class="sxs-lookup"><span data-stu-id="9859e-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="9859e-117">允许 UDP 流量</span><span class="sxs-lookup"><span data-stu-id="9859e-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="9859e-118">请遵循我们的网络指南中提供的其他建议：</span><span class="sxs-lookup"><span data-stu-id="9859e-118">Following the other recommendations in our Networking guidelines:</span></span>
    
  - [<span data-ttu-id="9859e-119">Skype for Business Online 中的媒体质量和网络连接性能</span><span class="sxs-lookup"><span data-stu-id="9859e-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="9859e-120">为 Skype for Business Online 优化网络</span><span class="sxs-lookup"><span data-stu-id="9859e-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="9859e-121">遵循本指南应尽可能减少潜在问题。</span><span class="sxs-lookup"><span data-stu-id="9859e-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9859e-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="9859e-122">Related topics</span></span>

[<span data-ttu-id="9859e-123">为 Skype for Business Online 优化网络</span><span class="sxs-lookup"><span data-stu-id="9859e-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 