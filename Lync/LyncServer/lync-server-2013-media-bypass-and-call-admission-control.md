---
title: Lync Server 2013：媒体绕过和呼叫允许控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4afa8f26e28fbb4261b0d8524c02efeb8d2a3132
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524629"
---
# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="eedba-102">Lync Server 2013 中的媒体旁路和呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="eedba-102">Media bypass and call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eedba-103">_**上次修改的主题：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="eedba-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="eedba-p101">媒体旁路和呼叫允许控制 (CAC) 协同工作以管理呼叫媒体的带宽控制。媒体旁路可以改善连接良好的链接中的媒体流；CAC 管理具有带宽限制的链接上的流量。由于媒体旁路和 CAC 相互排斥，因此在规划其中一项时必须注意另一项。支持以下组合：</span><span class="sxs-lookup"><span data-stu-id="eedba-p101">Media bypass and call admission control (CAC) work together to manage bandwidth control for call media. Media bypass facilitates media flow over well-connected links; CAC manages traffic on links with bandwidth constraints. Because Media Bypass and CAC are mutually exclusive, you must be mindful of one when planning for the other. The following combinations are supported:</span></span>

  - <span data-ttu-id="eedba-p102">同时启用 CAC 和媒体旁路。必须将媒体旁路设置为“使用站点和区域信息”\*\*\*\*。该站点和区域信息与用于 CAC 的信息相同。</span><span class="sxs-lookup"><span data-stu-id="eedba-p102">CAC and Media Bypass are both enabled. Media Bypass must be set to **Use Site and Region Information**. This site and region information is the same as that used for CAC.</span></span>
    
    <span data-ttu-id="eedba-p103">如果启用 CAC，则不能选择“始终绕过”\*\*\*\*，反之亦然，因为两种配置相互排斥。即两者中只有一个可应用于任意给定的 PSTN 呼叫。首先，将执行检查以确定是否对呼叫应用媒体旁路。如果是，则不使用 CAC。这样可行，因为如果可以对呼叫使用旁路，则根据定义将使用不需要 CAC 的连接。如果无法对呼叫应用旁路（即客户端的旁路 ID 和网关的旁路 ID 不匹配），将对呼叫应用 CAC。</span><span class="sxs-lookup"><span data-stu-id="eedba-p103">If you enable CAC, you cannot select **Always Bypass**, and vice-versa, because the two configurations are mutually exclusive. That is, only one of the two will apply to any given PSTN call. First, a check is made to determine if media bypass applies to the call. If it does, then CAC is not used. This makes sense, because if a call is eligible for bypass, it is by definition using a connection where CAC is not needed. If bypass cannot be applied to the call (that is, if the client’s and gateway’s bypass IDs do not match), then CAC is applied to the call.</span></span>

  - <span data-ttu-id="eedba-117">未启用 CAC 并且将媒体旁路设置为“始终绕过”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="eedba-117">CAC not enabled and Media Bypass set to **Always Bypass**.</span></span>
    
    <span data-ttu-id="eedba-118">在此配置中，客户端和中继子网将映射至唯一的旁路绕过 ID，该 ID 由系统计算得出。</span><span class="sxs-lookup"><span data-stu-id="eedba-118">In this configuration, both client and trunk subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

  - <span data-ttu-id="eedba-119">未启用 CAC 并且将媒体旁路设置为“使用站点和区域信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="eedba-119">CAC not enabled and Media Bypass set to **Use Site and Region Information**.</span></span>
    
    <span data-ttu-id="eedba-p104">在启用“使用站点和区域信息”\*\*\*\* 的配置中，绕过确定基本上以相同方式工作，不论是否启用 CAC。即对于任何给定的 PSTN 呼叫，客户端的子网将映射至特定站点，并且会提取该子网的绕过 ID。同样，网关的子网将映射至特定站点，并会提取该子网的绕过 ID。仅当两个绕过 ID 相同时，才会对呼叫执行绕过。如果不同，将不会发生媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="eedba-p104">Where **Use Site and Region Information** is enabled, bypass determination works essentially the same way, regardless of whether CAC is enabled or not. That is, for any given PSTN call, the client’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted. Similarly, the gateway’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted. Only if the two bypass IDs are identical will bypass happen for the call. If they are not identical, media bypass will not occur.</span></span>
    
    <span data-ttu-id="eedba-p105">如果要使用站点和区域配置控制绕过决定，那么即使在全局范围内禁用 CAC，也需要为每个站点和链接定义带宽策略。与带宽限制的实际值或其内容形式无关。最终目标是让系统自动计算不同的绕过 ID，以便与连接不佳的不同区域设置关联。根据定义，定义带宽限制是指链接连接不佳。</span><span class="sxs-lookup"><span data-stu-id="eedba-p105">Even though CAC is disabled globally, bandwidth policy needs to be defined for each site and link if you want to use site-and-region configuration to control the bypass decision. The actual value of the bandwidth constraint or its modality doesn’t matter. The ultimate goal is to have the system automatically calculate different bypass IDs to associate with different locales that are not well connected. Defining a bandwidth constraint by definition means a link is not well connected.</span></span>

  - <span data-ttu-id="eedba-129">启用 CAC，但未启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="eedba-129">CAC is enabled and media bypass is not enabled.</span></span> <span data-ttu-id="eedba-130">该配置仅适用于所有网关和 IP-PBX 均连接不佳，或不满足媒体旁路的其他要求的情况。</span><span class="sxs-lookup"><span data-stu-id="eedba-130">This would apply only where all gateways and IP-PBXs are not well connected or do not meet other requirements for media bypass.</span></span> <span data-ttu-id="eedba-131">有关媒体旁路要求的详细信息，请参阅 [Lync Server 2013 中媒体旁路的技术要求](lync-server-2013-technical-requirements-for-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="eedba-131">For details about requirements for media bypass, see [Technical requirements for media bypass in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="eedba-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eedba-132">See Also</span></span>


[<span data-ttu-id="eedba-133">Lync Server 2013 中的媒体旁路概述</span><span class="sxs-lookup"><span data-stu-id="eedba-133">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="eedba-134">Lync Server 2013 中的媒体旁路模式</span><span class="sxs-lookup"><span data-stu-id="eedba-134">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="eedba-135">Lync Server 2013 中媒体旁路的技术要求</span><span class="sxs-lookup"><span data-stu-id="eedba-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

