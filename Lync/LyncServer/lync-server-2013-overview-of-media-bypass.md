---
title: 'Lync Server 2013: 媒体绕过概述'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of media bypass
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412740(v=OCS.15)
ms:contentKeyID: 48184924
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a04bc9dfa250bc399f10a56ef58f78462044f5cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-media-bypass-in-lync-server-2013"></a><span data-ttu-id="14fbd-102">Lync Server 2013 中绕过媒体的概述</span><span class="sxs-lookup"><span data-stu-id="14fbd-102">Overview of media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14fbd-103">_**主题上次修改时间:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="14fbd-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="14fbd-104">当您想要最大程度地减少已部署中介服务器的数量时, 媒体绕过非常有用。</span><span class="sxs-lookup"><span data-stu-id="14fbd-104">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="14fbd-105">通常, 将在中心网站上部署中介服务器池, 并且它将控制分支站点上的网关。</span><span class="sxs-lookup"><span data-stu-id="14fbd-105">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="14fbd-106">启用媒体旁路后，来自分支站点中客户端的公用电话交换网 (PSTN) 呼叫的媒体可直接通过这些站点中的网关流动。</span><span class="sxs-lookup"><span data-stu-id="14fbd-106">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="14fbd-107">必须正确配置 Lync Server 2013 出站呼叫路由和企业语音策略, 以便将来自分支站点的客户端的 PSTN 呼叫路由到相应的网关。</span><span class="sxs-lookup"><span data-stu-id="14fbd-107">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="14fbd-p102">Wi-Fi 网络通常会比有线网络丢失更多的数据包。通常网关无法恢复这些丢失的数据包。因此，我们建议，在决定是否对无线子网启用绕过功能之前，先评估 Wi-Fi 网络的质量。同时，还需要在降低延迟和恢复丢失的数据包之间取得平衡。RTAudio 是一种可用于未绕过中介服务器的呼叫的编解码器，它更适合处理数据包丢失。</span><span class="sxs-lookup"><span data-stu-id="14fbd-p102">Wi-Fi networks typically experience more packet loss than wired networks. Recovery from this packet loss is not typically something that can be accommodated by gateways. Therefore, we recommend that you evaluate the quality of a Wi-Fi network before determining whether bypass should be enabled for a wireless subnet. There is a tradeoff in latency reduction versus recovery from packet loss to consider, as well. RTAudio, a codec which is available for calls that do not bypass the Mediation Server, is better suited for handling packet loss.</span></span>

<span data-ttu-id="14fbd-113">在您的企业语音结构到位后, 规划媒体绕过非常简单。</span><span class="sxs-lookup"><span data-stu-id="14fbd-113">After your Enterprise Voice structure is in place, planning for media bypass is straightforward.</span></span>

  - <span data-ttu-id="14fbd-114">如果您的拓扑属于集中式拓扑，但没有指向分支站点的 WAN 链路，则可以启用全局媒体旁路，因为没有必要进行细化的控制。</span><span class="sxs-lookup"><span data-stu-id="14fbd-114">If you have a centralized topology without WAN links to branch sites, you can enable global media bypass, because fine-tuned control is unnecessary.</span></span>

  - <span data-ttu-id="14fbd-115">如果您的拓扑属于分布式拓扑，其中包含一个或多个网络区域以及附属的分支站点，请确定以下信息：</span><span class="sxs-lookup"><span data-stu-id="14fbd-115">If you have a distributed topology that consists of one or more network regions and their affiliated branch sites, determine the following:</span></span>
    
      - <span data-ttu-id="14fbd-116">您的中介服务器对等方是否支持媒体旁路所需的功能。</span><span class="sxs-lookup"><span data-stu-id="14fbd-116">Whether your Mediation Server peers are able to support the capabilities required for media bypass.</span></span>
    
      - <span data-ttu-id="14fbd-117">每个网络区域中的哪些站点是正确连接的。</span><span class="sxs-lookup"><span data-stu-id="14fbd-117">Which sites in each network region are well-connected.</span></span>
    
      - <span data-ttu-id="14fbd-118">哪种媒体旁路与呼叫允许控制的组合适合您的网络。</span><span class="sxs-lookup"><span data-stu-id="14fbd-118">Which combination of media bypass and call admission control is appropriate for your network.</span></span>

<span data-ttu-id="14fbd-p103">启用媒体旁路后，会自动为某个网络区域和该区域中没有带宽限制的所有网络站点生成唯一的绕过 ID。在该区域内具有带宽限制的站点和通过具有带宽限制的 WAN 链路连接到该区域的站点都分配有其自己的唯一绕过 ID。</span><span class="sxs-lookup"><span data-stu-id="14fbd-p103">When you enable media bypass, a unique bypass ID is automatically generated for a network region, and for all network sites without bandwidth constraints within that region. Sites with bandwidth constraints within the region and sites connected to the region over WAN links with bandwidth constraints are each assigned their own unique bypass IDs.</span></span>

<span data-ttu-id="14fbd-121">当用户对 PSTN 进行调用时, 中介服务器会将客户端子网的旁路 ID 与网关子网的旁路 ID 进行比较。</span><span class="sxs-lookup"><span data-stu-id="14fbd-121">When a user makes a call to the PSTN, the Mediation Server compares the bypass ID of the client subnet with the bypass ID of the gateway subnet.</span></span> <span data-ttu-id="14fbd-122">如果这两个绕过 ID 匹配，则对该呼叫使用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="14fbd-122">If the two bypass IDs match, media bypass is used for the call.</span></span> <span data-ttu-id="14fbd-123">如果绕过 Id 不匹配, 则通话的媒体必须流过中介服务器。</span><span class="sxs-lookup"><span data-stu-id="14fbd-123">If the bypass IDs do not match, media for the call must flow through the Mediation Server.</span></span>

<span data-ttu-id="14fbd-124">用户收到来自 PSTN 的呼叫时，用户的客户端会将其绕过 ID 与 PSTN 网关的绕过 ID 进行比较。</span><span class="sxs-lookup"><span data-stu-id="14fbd-124">When a user receives a call from the PSTN, the user’s client compares its bypass ID to that of the PSTN gateway.</span></span> <span data-ttu-id="14fbd-125">如果两个旁路 Id 匹配, 则媒体直接从网关流向客户端, 而不是中介服务器。</span><span class="sxs-lookup"><span data-stu-id="14fbd-125">If the two bypass IDs match, media flows directly from the gateway to the client, bypassing the Mediation Server.</span></span>

<span data-ttu-id="14fbd-126">只有 Lync 2010 或更高版本的客户端和设备支持与中介服务器的媒体绕过交互。</span><span class="sxs-lookup"><span data-stu-id="14fbd-126">Only Lync 2010 or above clients and devices support media bypass interactions with a Mediation Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="14fbd-p106">除了全局启用媒体旁路之外，还必须在每个 PSTN 中继中分别启用媒体旁路。如果已全局启用绕过，但没有为特定的 PSTN 中继启用，则不会为涉及该 PSTN 中继的任何呼叫调用媒体旁路。此外，当媒体旁路设置为“<STRONG>使用站点和区域信息</STRONG>”时，必须将所有可路由的子网与它们所在的站点关联起来。如果不需要绕过的站点内有可路由的子网，则在启用媒体旁路之前，应该将这些子网分组到一个新的站点内。执行该操作可确保为不可路由的子网分配不同的绕过 ID。</span><span class="sxs-lookup"><span data-stu-id="14fbd-p106">In addition to enabling media bypass globally, you must enable media bypass individually on each PSTN trunk. If bypass is enabled globally, but is not enabled for a particular PSTN trunk, media bypass will not be invoked for any calls involving that PSTN trunk. In addition, when media bypass is set to <STRONG>Use Site and Region Information</STRONG>, you must associate all routable subnets with the sites in which they are located. If there are routable subnets within a site for which bypass is not wanted, these subnets should be grouped within a new site before you enable media bypass. Doing so will assure that the unroutable subnets are assigned a different bypass ID.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="14fbd-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14fbd-132">See Also</span></span>


[<span data-ttu-id="14fbd-133">Lync Server 2013 中的媒体绕过模式</span><span class="sxs-lookup"><span data-stu-id="14fbd-133">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="14fbd-134">Lync Server 2013 中的媒体绕过和呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="14fbd-134">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="14fbd-135">Lync Server 2013 中媒体旁路的技术要求</span><span class="sxs-lookup"><span data-stu-id="14fbd-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

