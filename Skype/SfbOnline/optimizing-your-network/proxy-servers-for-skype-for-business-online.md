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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: 本文提供有关将代理服务器与 Skype for Business。
ms.openlocfilehash: 09ed98c5f69d6e244a5f87125e4ad607e4d16226
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240411"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="43eb7-103">Skype for Business Online 的代理服务器</span><span class="sxs-lookup"><span data-stu-id="43eb7-103">Proxy servers for Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="43eb7-104">本文提供有关将代理服务器与 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="43eb7-104">This article provides guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="43eb7-105">建议不使用代理服务器</span><span class="sxs-lookup"><span data-stu-id="43eb7-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="43eb7-106">考虑到通过代理的 Skype for Business 流量，Microsoft 建议绕过代理。</span><span class="sxs-lookup"><span data-stu-id="43eb7-106">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="43eb7-107">代理不会使Skype for Business更安全，因为流量已加密。</span><span class="sxs-lookup"><span data-stu-id="43eb7-107">Proxies don't make Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="43eb7-108">另外，使用代理会产生问题。</span><span class="sxs-lookup"><span data-stu-id="43eb7-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="43eb7-109">环境中可能会出现由于延迟和数据包丢失而引起的与性能相关的问题。</span><span class="sxs-lookup"><span data-stu-id="43eb7-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="43eb7-110">此类问题将导致音频和视频等Teams或Skype for Business场景中的负面体验，实时流至关重要。</span><span class="sxs-lookup"><span data-stu-id="43eb7-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="43eb7-111">如果需要使用代理服务器</span><span class="sxs-lookup"><span data-stu-id="43eb7-111">If you need to use a proxy server</span></span>

<span data-ttu-id="43eb7-p103">有些组织无法为 Skype for Business 流量绕过代理。如果你是这种情况，需要留意上面提到的问题。</span><span class="sxs-lookup"><span data-stu-id="43eb7-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="43eb7-114">Microsoft 还强烈建议：</span><span class="sxs-lookup"><span data-stu-id="43eb7-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="43eb7-115">使用外部 DNS 解析</span><span class="sxs-lookup"><span data-stu-id="43eb7-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="43eb7-116">使用基于直接 UDP 的路由</span><span class="sxs-lookup"><span data-stu-id="43eb7-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="43eb7-117">允许 UDP 流量</span><span class="sxs-lookup"><span data-stu-id="43eb7-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="43eb7-118">遵循网络指南中的其他建议：</span><span class="sxs-lookup"><span data-stu-id="43eb7-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="43eb7-119">Skype for Business Online 中的媒体质量和网络连接性能</span><span class="sxs-lookup"><span data-stu-id="43eb7-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](media-quality-and-network-connectivity-performance.md)
    
  - [<span data-ttu-id="43eb7-120">为 Skype for Business Online 优化网络</span><span class="sxs-lookup"><span data-stu-id="43eb7-120">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
    
<span data-ttu-id="43eb7-121">遵循本指南应尽可能减少潜在问题。</span><span class="sxs-lookup"><span data-stu-id="43eb7-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="43eb7-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="43eb7-122">Related topics</span></span>

[<span data-ttu-id="43eb7-123">为 Skype for Business Online 优化网络</span><span class="sxs-lookup"><span data-stu-id="43eb7-123">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
 
