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
ms.collection: M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: 本文提供有关将代理服务器与团队或 Skype for Business 配合使用的信息。
ms.openlocfilehash: e0733393a40c2d2c2fd62d986a4b4d66d0c2c35f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304367"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="859ec-103">Teams 或 Skype for Business Online 的代理服务器</span><span class="sxs-lookup"><span data-stu-id="859ec-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="859ec-104">本文提供有关将代理服务器与团队或 Skype for Business 配合使用的指南。</span><span class="sxs-lookup"><span data-stu-id="859ec-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="859ec-105">建议不使用代理服务器</span><span class="sxs-lookup"><span data-stu-id="859ec-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="859ec-106">当来自代理的团队或 Skype for business 通信流时, Microsoft 建议绕过代理。</span><span class="sxs-lookup"><span data-stu-id="859ec-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="859ec-107">代理不会使团队或 Skype for business 更加安全, 因为通信已加密。</span><span class="sxs-lookup"><span data-stu-id="859ec-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="859ec-108">另外，使用代理会产生问题。</span><span class="sxs-lookup"><span data-stu-id="859ec-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="859ec-109">环境中可能会出现由于延迟和数据包丢失而引起的与性能相关的问题。</span><span class="sxs-lookup"><span data-stu-id="859ec-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="859ec-110">此类问题将在此类团队或 Skype for Business 方案中产生消极的体验, 因为实时流非常重要。</span><span class="sxs-lookup"><span data-stu-id="859ec-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="859ec-111">如果需要使用代理服务器</span><span class="sxs-lookup"><span data-stu-id="859ec-111">If you need to use a proxy server</span></span>

<span data-ttu-id="859ec-112">某些组织没有为团队或 Skype for business 流量绕过代理的选项。</span><span class="sxs-lookup"><span data-stu-id="859ec-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="859ec-113">如果你是这种情况，需要留意上面提到的问题。</span><span class="sxs-lookup"><span data-stu-id="859ec-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="859ec-114">Microsoft 还强烈建议：</span><span class="sxs-lookup"><span data-stu-id="859ec-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="859ec-115">使用外部 DNS 解析</span><span class="sxs-lookup"><span data-stu-id="859ec-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="859ec-116">使用基于直接 UDP 的路由</span><span class="sxs-lookup"><span data-stu-id="859ec-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="859ec-117">允许 UDP 流量</span><span class="sxs-lookup"><span data-stu-id="859ec-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="859ec-118">按照我们的网络指南中的其他建议操作:</span><span class="sxs-lookup"><span data-stu-id="859ec-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="859ec-119">Skype for Business Online 中的媒体质量和网络连接性能</span><span class="sxs-lookup"><span data-stu-id="859ec-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="859ec-120">为 Skype for Business Online 优化网络</span><span class="sxs-lookup"><span data-stu-id="859ec-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="859ec-121">遵循本指南应尽可能减少潜在问题。</span><span class="sxs-lookup"><span data-stu-id="859ec-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="859ec-122">相关主题</span><span class="sxs-lookup"><span data-stu-id="859ec-122">Related topics</span></span>

[<span data-ttu-id="859ec-123">为 Skype for Business Online 优化网络</span><span class="sxs-lookup"><span data-stu-id="859ec-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 