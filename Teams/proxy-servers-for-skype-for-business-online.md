---
title: 工作组或业务 online Skype 的代理服务器
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
description: 本文提供了有关与团队或 Skype 的代理服务器使用的业务信息。
ms.openlocfilehash: 1b25d0554ec8c5dca113be0842149dae11850b7e
ms.sourcegitcommit: 327fe807b461aff18b06449f06b9e51ce393c4bc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2019
ms.locfileid: "29972204"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="37247-103">工作组或业务 online Skype 的代理服务器</span><span class="sxs-lookup"><span data-stu-id="37247-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="37247-104">本文提供有关使用代理服务器团队或 Skype for Business 的指导。</span><span class="sxs-lookup"><span data-stu-id="37247-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="37247-105">建议不使用代理服务器</span><span class="sxs-lookup"><span data-stu-id="37247-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="37247-106">当谈到团队或 Skype 的业务流量通过代理时，Microsoft 建议绕过代理服务器。</span><span class="sxs-lookup"><span data-stu-id="37247-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="37247-107">代理不使团队或 for Business 的 Skype 更加安全因为已加密流量。</span><span class="sxs-lookup"><span data-stu-id="37247-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="37247-108">另外，使用代理会产生问题。</span><span class="sxs-lookup"><span data-stu-id="37247-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="37247-109">环境中可能会出现由于延迟和数据包丢失而引起的与性能相关的问题。</span><span class="sxs-lookup"><span data-stu-id="37247-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="37247-110">例如，这些问题将导致这样的团队或 Skype 业务方案音频和视频，为负体验实时流至关重要。</span><span class="sxs-lookup"><span data-stu-id="37247-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="37247-111">如果需要使用代理服务器</span><span class="sxs-lookup"><span data-stu-id="37247-111">If you need to use a proxy server</span></span>

<span data-ttu-id="37247-112">某些组织具有用于工作组或 Skype 的业务通信不使用代理服务器的选项。</span><span class="sxs-lookup"><span data-stu-id="37247-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="37247-113">如果你是这种情况，需要留意上面提到的问题。</span><span class="sxs-lookup"><span data-stu-id="37247-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="37247-114">Microsoft 还强烈建议：</span><span class="sxs-lookup"><span data-stu-id="37247-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="37247-115">使用外部 DNS 解析</span><span class="sxs-lookup"><span data-stu-id="37247-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="37247-116">使用基于直接 UDP 的路由</span><span class="sxs-lookup"><span data-stu-id="37247-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="37247-117">允许 UDP 流量</span><span class="sxs-lookup"><span data-stu-id="37247-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="37247-118">关注我们网络指南中的其他建议：</span><span class="sxs-lookup"><span data-stu-id="37247-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="37247-119">Skype for Business Online 中的媒体质量和网络连接性能</span><span class="sxs-lookup"><span data-stu-id="37247-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="37247-120">为 Skype for Business Online 优化网络</span><span class="sxs-lookup"><span data-stu-id="37247-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="37247-121">遵循本指南应尽可能减少潜在问题。</span><span class="sxs-lookup"><span data-stu-id="37247-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="37247-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="37247-122">Related topics</span></span>

[<span data-ttu-id="37247-123">为 Skype for Business Online 优化网络</span><span class="sxs-lookup"><span data-stu-id="37247-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 