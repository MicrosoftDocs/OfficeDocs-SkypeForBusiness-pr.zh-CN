---
title: Teams 或 Skype for Business Online 的代理服务器
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: 本文提供有关将代理服务器与团队或 Skype for Business 配合使用的信息。
ms.openlocfilehash: b06e7aa43dcbcf5aeab9011af72d94460f69cc63
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573202"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="588db-103">Teams 或 Skype for Business Online 的代理服务器</span><span class="sxs-lookup"><span data-stu-id="588db-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="588db-104">本文提供有关将代理服务器与团队或 Skype for Business 配合使用的指南。</span><span class="sxs-lookup"><span data-stu-id="588db-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="588db-105">建议不使用代理服务器</span><span class="sxs-lookup"><span data-stu-id="588db-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="588db-p101">当来自代理的团队或 Skype for business 通信流时，Microsoft 建议绕过代理。代理不会使团队或 Skype for business 更加安全，因为通信已加密。</span><span class="sxs-lookup"><span data-stu-id="588db-p101">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="588db-p102">并且拥有代理可能会导致问题。与性能相关的问题可通过延迟和数据包丢失引入环境。此类问题将在此类团队或 Skype for Business 方案中产生消极的体验，因为实时流非常重要。</span><span class="sxs-lookup"><span data-stu-id="588db-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="588db-111">如果需要使用代理服务器</span><span class="sxs-lookup"><span data-stu-id="588db-111">If you need to use a proxy server</span></span>

<span data-ttu-id="588db-p103">某些组织没有为团队或 Skype for business 流量绕过代理的选项。如果这是你所说的情况，上述问题需要牢记。</span><span class="sxs-lookup"><span data-stu-id="588db-p103">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="588db-114">Microsoft 还强烈建议：</span><span class="sxs-lookup"><span data-stu-id="588db-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="588db-115">使用外部 DNS 解析</span><span class="sxs-lookup"><span data-stu-id="588db-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="588db-116">使用基于直接 UDP 的路由</span><span class="sxs-lookup"><span data-stu-id="588db-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="588db-117">允许 UDP 流量</span><span class="sxs-lookup"><span data-stu-id="588db-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="588db-118">按照我们的网络指南中的其他建议操作：</span><span class="sxs-lookup"><span data-stu-id="588db-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="588db-119">Skype for Business Online 中的媒体质量和网络连接性能</span><span class="sxs-lookup"><span data-stu-id="588db-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="588db-120">为 Skype for Business Online 优化网络</span><span class="sxs-lookup"><span data-stu-id="588db-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="588db-121">遵循本指南应尽可能减少潜在问题。</span><span class="sxs-lookup"><span data-stu-id="588db-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="588db-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="588db-122">Related topics</span></span>

[<span data-ttu-id="588db-123">为 Skype for Business Online 优化网络</span><span class="sxs-lookup"><span data-stu-id="588db-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 