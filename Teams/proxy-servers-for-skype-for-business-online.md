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
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: 本文提供有关将代理服务器与 Microsoft Teams 或 Skype for Business 一起使用的信息。
ms.openlocfilehash: 0e2089cfa327a610c3ee98f1f20862a28939fd0c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117720"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="9a36c-103">Teams 或 Skype for Business Online 的代理服务器</span><span class="sxs-lookup"><span data-stu-id="9a36c-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="9a36c-104">本文提供有关将代理服务器与 Teams 或 Skype for Business 一同使用的指导。</span><span class="sxs-lookup"><span data-stu-id="9a36c-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="9a36c-105">建议不使用代理服务器</span><span class="sxs-lookup"><span data-stu-id="9a36c-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="9a36c-106">对于通过代理的 Teams 或 Skype for Business 流量，Microsoft 建议绕过代理。</span><span class="sxs-lookup"><span data-stu-id="9a36c-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="9a36c-107">代理不会使 Teams 或 Skype for Business 更安全，因为流量已加密。</span><span class="sxs-lookup"><span data-stu-id="9a36c-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="9a36c-108">另外，使用代理会产生问题。</span><span class="sxs-lookup"><span data-stu-id="9a36c-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="9a36c-109">环境中可能会出现由于延迟和数据包丢失而引起的与性能相关的问题。</span><span class="sxs-lookup"><span data-stu-id="9a36c-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="9a36c-110">此类问题会导致在音频和视频等 Teams 或 Skype for Business 方案中遇到负面体验，实时流至关重要。</span><span class="sxs-lookup"><span data-stu-id="9a36c-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="9a36c-111">如果需要使用代理服务器</span><span class="sxs-lookup"><span data-stu-id="9a36c-111">If you need to use a proxy server</span></span>

<span data-ttu-id="9a36c-112">某些组织无法绕过 Teams 或 Skype for Business 流量的代理。</span><span class="sxs-lookup"><span data-stu-id="9a36c-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="9a36c-113">如果你是这种情况，需要留意上面提到的问题。</span><span class="sxs-lookup"><span data-stu-id="9a36c-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="9a36c-114">Microsoft 还强烈建议：</span><span class="sxs-lookup"><span data-stu-id="9a36c-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="9a36c-115">使用外部 DNS 解析</span><span class="sxs-lookup"><span data-stu-id="9a36c-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="9a36c-116">使用基于直接 UDP 的路由</span><span class="sxs-lookup"><span data-stu-id="9a36c-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="9a36c-117">允许 UDP 流量</span><span class="sxs-lookup"><span data-stu-id="9a36c-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="9a36c-118">遵循网络指南中的其他建议： [为 Teams 准备组织的网络](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="9a36c-118">Following the other recommendations in our networking guidelines: [Prepare your organization's network for Teams](prepare-network.md)</span></span>
  
    
<span data-ttu-id="9a36c-119">遵循本指南应尽可能减少潜在问题。</span><span class="sxs-lookup"><span data-stu-id="9a36c-119">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9a36c-120">相关主题</span><span class="sxs-lookup"><span data-stu-id="9a36c-120">Related topics</span></span>

[<span data-ttu-id="9a36c-121">Microsoft 365 和 Office 365 网络连接原则</span><span class="sxs-lookup"><span data-stu-id="9a36c-121">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="9a36c-122">为 Teams 准备贵组织的网络</span><span class="sxs-lookup"><span data-stu-id="9a36c-122">Prepare your organization's network for Teams</span></span>](prepare-network.md)