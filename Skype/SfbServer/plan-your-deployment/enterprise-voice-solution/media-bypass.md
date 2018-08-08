---
title: 规划媒体绕过 Skype for Business 中
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
description: 决策所必需的规划媒体旁路中 Skype 业务 Server 企业语音。 包括与呼叫允许控制 (CAC) 的互操作性。
ms.openlocfilehash: a6e7cd2a37af67415962a4f0a2e0c390160f66f3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21020855"
---
# <a name="plan-for-media-bypass-in-skype-for-business"></a><span data-ttu-id="39e1f-104">规划媒体绕过 Skype for Business 中</span><span class="sxs-lookup"><span data-stu-id="39e1f-104">Plan for media bypass in Skype for Business</span></span>
 
<span data-ttu-id="39e1f-105">决策所必需的规划媒体旁路中 Skype 业务 Server 企业语音。</span><span class="sxs-lookup"><span data-stu-id="39e1f-105">Decisions necessary for planning for media bypass in Skype for Business Server Enterprise Voice.</span></span> <span data-ttu-id="39e1f-106">包括与呼叫允许控制 (CAC) 的互操作性。</span><span class="sxs-lookup"><span data-stu-id="39e1f-106">Includes interoperation with call admission control (CAC).</span></span>
  
<span data-ttu-id="39e1f-107">媒体旁路功能是指从尽可能信号遍历中介服务器的呼叫的媒体路径中删除中介服务器。</span><span class="sxs-lookup"><span data-stu-id="39e1f-107">Media bypass refers to removing the Mediation Server from the media path whenever possible for calls whose signaling traverses the Mediation Server.</span></span>
  
<span data-ttu-id="39e1f-108">媒体旁路功能可通过减少延迟、不必要的转换、可能的数据包丢失和潜在的故障点数来提高语音质量。</span><span class="sxs-lookup"><span data-stu-id="39e1f-108">Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure.</span></span> <span data-ttu-id="39e1f-109">可以提高可伸缩性，由于消除了媒体绕过呼叫处理减少了中介服务器上的负载。</span><span class="sxs-lookup"><span data-stu-id="39e1f-109">Scalability can be improved, because elimination of media processing for bypassed calls reduces the load on the Mediation Server.</span></span> <span data-ttu-id="39e1f-110">在负载减少补充中介服务器的控制多个网关的能力。</span><span class="sxs-lookup"><span data-stu-id="39e1f-110">This reduction in load complements the ability of the Mediation Server to control multiple gateways.</span></span> 
  
 <span data-ttu-id="39e1f-111">媒体绕过中介服务器没有分支站点由一个或多个具有带宽限制的 WAN 链接连接到中心网站，其中通过允许从流动直接到不带其本地网关在分支站点客户端的媒体降低对带宽的要求首先不必流经 WAN 链接到中央站点中介服务器和备份。</span><span class="sxs-lookup"><span data-stu-id="39e1f-111">Where a branch site without a Mediation Server is connected to a central site by one or more WAN links with constrained bandwidth, media bypass lowers the bandwidth requirement by allowing media from a client at a branch site to flow directly to its local gateway without first having to flow across the WAN link to a Mediation Server at the central site and back.</span></span>
  
<span data-ttu-id="39e1f-112">由于无需中介服务器处理媒体，媒体绕过功能还可以减少企业语音基础结构所需要的中介服务器数。</span><span class="sxs-lookup"><span data-stu-id="39e1f-112">By relieving the Mediation Server from media processing, media bypass may also reduce the number of Mediation Servers that an Enterprise Voice infrastructure requires.</span></span> <span data-ttu-id="39e1f-113">一般而言，应尽可能启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="39e1f-113">As a general rule, enable media bypass wherever possible.</span></span>
  
<span data-ttu-id="39e1f-114">下图显示了具有和没有媒体旁路功能的拓扑中的基本媒体和信号路径。</span><span class="sxs-lookup"><span data-stu-id="39e1f-114">The following figure shows basic media and signaling pathways in topologies with and without media bypass.</span></span>
  
<span data-ttu-id="39e1f-115">**具有和没有媒体旁路功能的媒体和信号路径**</span><span class="sxs-lookup"><span data-stu-id="39e1f-115">**Media and signaling pathways with and without media bypass**</span></span>

![语音 CAC 媒体绕过连接强制实施](../../media/Plan_CS_VoiceCAC_enforcementofconnectionstoPSTN.jpg)
  
<span data-ttu-id="39e1f-117">您想要尽可能减少的部署中介服务器时，媒体绕过非常有用。</span><span class="sxs-lookup"><span data-stu-id="39e1f-117">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="39e1f-118">通常，将在中央站点部署中介服务器池，它将控制网关在分支站点。</span><span class="sxs-lookup"><span data-stu-id="39e1f-118">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="39e1f-119">启用媒体旁路后，来自分支站点中客户端的公用电话交换网 (PSTN) 呼叫的媒体可直接通过这些站点中的网关流动。</span><span class="sxs-lookup"><span data-stu-id="39e1f-119">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="39e1f-120">必须正确配置 Skype 业务服务器出站呼叫路由和企业语音策略，以便在分支站点的客户端的 PSTN 呼叫将路由至相应的网关。</span><span class="sxs-lookup"><span data-stu-id="39e1f-120">Skype for Business Server outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>
  
<span data-ttu-id="39e1f-p106">Wi-Fi 网络通常会比有线网络丢失更多的数据包。通常网关无法恢复这些丢失的数据包。因此，我们建议，在决定是否对无线子网启用绕过功能之前，先评估 Wi-Fi 网络的质量。同时，还需要在降低延迟和恢复丢失的数据包之间取得平衡。RTAudio 是一种可用于未绕过中介服务器的呼叫的编解码器，它更适合处理数据包丢失。</span><span class="sxs-lookup"><span data-stu-id="39e1f-p106">Wi-Fi networks typically experience more packet loss than wired networks. Recovery from this packet loss is not typically something that can be accommodated by gateways. Therefore, we recommend that you evaluate the quality of a Wi-Fi network before determining whether bypass should be enabled for a wireless subnet. There is a tradeoff in latency reduction versus recovery from packet loss to consider, as well. RTAudio, a codec which is available for calls that do not bypass the Mediation Server, is better suited for handling packet loss.</span></span>
  
## <a name="planning-your-media-bypass-deployment"></a><span data-ttu-id="39e1f-126">规划媒体绕过部署</span><span class="sxs-lookup"><span data-stu-id="39e1f-126">Planning your media bypass deployment</span></span>

<span data-ttu-id="39e1f-127">企业语音结构后，规划媒体绕过将变得非常简单。</span><span class="sxs-lookup"><span data-stu-id="39e1f-127">After your Enterprise Voice structure is in place, planning for media bypass is straightforward.</span></span>
  
- <span data-ttu-id="39e1f-128">如果您的拓扑属于集中式拓扑，但没有指向分支站点的 WAN 链路，则可以启用全局媒体旁路，因为没有必要进行细化的控制。</span><span class="sxs-lookup"><span data-stu-id="39e1f-128">If you have a centralized topology without WAN links to branch sites, you can enable global media bypass, because fine-tuned control is unnecessary.</span></span>
    
- <span data-ttu-id="39e1f-129">如果您的拓扑属于分布式拓扑，其中包含一个或多个网络区域以及附属的分支站点，请确定以下信息：</span><span class="sxs-lookup"><span data-stu-id="39e1f-129">If you have a distributed topology that consists of one or more network regions and their affiliated branch sites, determine the following:</span></span>
    
  - <span data-ttu-id="39e1f-130">您的中介服务器对等方是否支持媒体旁路所需的功能。</span><span class="sxs-lookup"><span data-stu-id="39e1f-130">Whether your Mediation Server peers are able to support the capabilities required for media bypass.</span></span>
    
  - <span data-ttu-id="39e1f-131">每个网络区域中的哪些站点是正确连接的。</span><span class="sxs-lookup"><span data-stu-id="39e1f-131">Which sites in each network region are well-connected.</span></span>
    
  - <span data-ttu-id="39e1f-132">哪种媒体旁路与呼叫允许控制的组合适合您的网络。</span><span class="sxs-lookup"><span data-stu-id="39e1f-132">Which combination of media bypass and call admission control is appropriate for your network.</span></span>
    
<span data-ttu-id="39e1f-p107">启用媒体旁路后，会自动为某个网络区域和该区域中没有带宽限制的所有网络站点生成唯一的绕过 ID。在该区域内具有带宽限制的站点和通过具有带宽限制的 WAN 链路连接到该区域的站点都分配有其自己的唯一绕过 ID。</span><span class="sxs-lookup"><span data-stu-id="39e1f-p107">When you enable media bypass, a unique bypass ID is automatically generated for a network region, and for all network sites without bandwidth constraints within that region. Sites with bandwidth constraints within the region and sites connected to the region over WAN links with bandwidth constraints are each assigned their own unique bypass IDs.</span></span>
  
<span data-ttu-id="39e1f-135">当用户对 PSTN 呼叫，中介服务器进行比较的网关子网的绕过 id 客户的子网的绕过 ID。</span><span class="sxs-lookup"><span data-stu-id="39e1f-135">When a user makes a call to the PSTN, the Mediation Server compares the bypass ID of the client subnet with the bypass ID of the gateway subnet.</span></span> <span data-ttu-id="39e1f-136">如果这两个绕过 ID 匹配，则对该呼叫使用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="39e1f-136">If the two bypass IDs match, media bypass is used for the call.</span></span> <span data-ttu-id="39e1f-137">如果绕过 Id 不匹配，用于呼叫的媒体必须流动中介服务器。</span><span class="sxs-lookup"><span data-stu-id="39e1f-137">If the bypass IDs do not match, media for the call must flow through the Mediation Server.</span></span>
  
<span data-ttu-id="39e1f-138">当用户收到来自 PSTN 的呼叫时，用户的客户端会将其与 PSTN 网关的绕过 ID 进行比较。</span><span class="sxs-lookup"><span data-stu-id="39e1f-138">When a user receives a call from the PSTN, the user's client compares its bypass ID to that of the PSTN gateway.</span></span> <span data-ttu-id="39e1f-139">如果两个绕过 Id 匹配，媒体流直接从客户端，绕过中介服务器的网关。</span><span class="sxs-lookup"><span data-stu-id="39e1f-139">If the two bypass IDs match, media flows directly from the gateway to the client, bypassing the Mediation Server.</span></span>
  
<span data-ttu-id="39e1f-140">仅限 Lync 2010 或更高版本客户端和设备支持媒体绕过与中介服务器的交互。</span><span class="sxs-lookup"><span data-stu-id="39e1f-140">Only Lync 2010 or newer clients and devices support media bypass interactions with a Mediation Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="39e1f-p110">除了全局启用媒体旁路之外，还必须在每个 PSTN 中继中分别启用媒体旁路。如果已全局启用绕过，但没有为特定的 PSTN 中继启用，则不会为涉及该 PSTN 中继的任何呼叫调用媒体旁路。此外，当媒体旁路设置为“**使用站点和区域信息**”时，必须将所有可路由的子网与它们所在的站点关联起来。如果不需要绕过的站点内有可路由的子网，则在启用媒体旁路之前，应该将这些子网分组到一个新的站点内。执行该操作可确保为不可路由的子网分配不同的绕过 ID。</span><span class="sxs-lookup"><span data-stu-id="39e1f-p110">In addition to enabling media bypass globally, you must enable media bypass individually on each PSTN trunk. If bypass is enabled globally, but is not enabled for a particular PSTN trunk, media bypass will not be invoked for any calls involving that PSTN trunk. In addition, when media bypass is set to **Use Site and Region Information**, you must associate all routable subnets with the sites in which they are located. If there are routable subnets within a site for which bypass is not wanted, these subnets should be grouped within a new site before you enable media bypass. Doing so will assure that the unroutable subnets are assigned a different bypass ID.</span></span> 
  
## <a name="media-bypass-modes"></a><span data-ttu-id="39e1f-146">媒体绕过模式</span><span class="sxs-lookup"><span data-stu-id="39e1f-146">Media bypass modes</span></span>

<span data-ttu-id="39e1f-p111">必须配置全局和每个单个 PSTN 中继的媒体旁路。在全局范围内启用媒体旁路时，有两种选择：“**始终绕过**”和“**使用站点和区域信息**”。</span><span class="sxs-lookup"><span data-stu-id="39e1f-p111">You must configure media bypass both globally and for each individual PSTN trunk. When enabling media bypass globally, you have two choices: **Always Bypass** and **Use Site and Region Information**.</span></span> 
  
<span data-ttu-id="39e1f-p112">顾名思义，“**始终绕过**”表示将试图绕过所有 PSTN 呼叫。“**始终绕过**”用于既不需要启用呼叫允许控制也不需要指定与何时尝试媒体旁路相关的详细配置信息的部署。此外，在客户端和 PSTN 网关之间有完全连接时需使用“**始终绕过**”。在此配置中，所有子网将映射至唯一的绕过 ID，该 ID 由系统计算得出。</span><span class="sxs-lookup"><span data-stu-id="39e1f-p112">As the name suggests, **Always Bypass** means that bypass will be attempted for all PSTN calls. **Always Bypass** is used for deployments where there is no need to enable call admission control, nor is there a need to specify detailed configuration information regarding when to attempt media bypass. Furthermore, **Always Bypass** is used when there is full connectivity between clients and PSTN gateways. In this configuration, all subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>
  
<span data-ttu-id="39e1f-p113">通过“**使用站点和区域信息**”，与站点和区域配置关联的绕过 ID 将用于做出绕过决定。此配置可使您灵活地配置大部分常用拓扑的绕过，因为除了支持与呼叫允许控制 (CAC) 的交互之外，它还可以使您对何时发生绕过进行精确控制。系统会尝试通过自动分配绕过 ID 简化任务，如下所示。</span><span class="sxs-lookup"><span data-stu-id="39e1f-p113">With **Use Site and Region Information**, the bypass ID associated with site and region configuration is used to make the bypass decision. This configuration provides the flexibility to configure bypass for most common topologies, as it gives you fine-grained control over when bypass happens, in addition to supporting interactions with call admission control (CAC). The system tries to ease your task by automatically assigning bypass IDs as follows.</span></span>
  
- <span data-ttu-id="39e1f-156">系统会自动为每个区域分配单个唯一的绕过 ID。</span><span class="sxs-lookup"><span data-stu-id="39e1f-156">The system automatically assigns a single unique bypass ID to each region.</span></span>
    
- <span data-ttu-id="39e1f-157">任何通过 WAN 链路连接到区域的没有带宽限制的站点将继承与该区域相同的绕过 ID。</span><span class="sxs-lookup"><span data-stu-id="39e1f-157">Any site connected to a region over a WAN link without bandwidth constraints inherits the same bypass ID as the region.</span></span>
    
- <span data-ttu-id="39e1f-158">将为通过 WAN 链路与区域关联的具有带宽限制的站点分配与该区域不同的绕过 ID。</span><span class="sxs-lookup"><span data-stu-id="39e1f-158">A site associated with the region over a WAN link with constrained bandwidth is assigned a different bypass ID from that of the region.</span></span>
    
- <span data-ttu-id="39e1f-159">与每个站点关联的子网将继承该站点的绕过 ID。</span><span class="sxs-lookup"><span data-stu-id="39e1f-159">Subnets associated with each site inherit the bypass ID for that site.</span></span>
    
## <a name="media-bypass-and-call-admission-control"></a><span data-ttu-id="39e1f-160">媒体绕过和呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="39e1f-160">Media bypass and call admission control</span></span>

<span data-ttu-id="39e1f-p114">媒体旁路和呼叫允许控制 (CAC) 协同工作以管理呼叫媒体的带宽控制。媒体旁路可以改善连接良好的链接中的媒体流；CAC 管理具有带宽限制的链接上的流量。由于媒体旁路和 CAC 相互排斥，因此在规划其中一项时必须注意另一项。支持以下组合：</span><span class="sxs-lookup"><span data-stu-id="39e1f-p114">Media bypass and call admission control (CAC) work together to manage bandwidth control for call media. Media bypass facilitates media flow over well-connected links; CAC manages traffic on links with bandwidth constraints. Because Media Bypass and CAC are mutually exclusive, you must be mindful of one when planning for the other. The following combinations are supported:</span></span>
  
- <span data-ttu-id="39e1f-p115">同时启用 CAC 和媒体旁路。必须将媒体旁路设置为“**使用站点和区域信息**”。该站点和区域信息与用于 CAC 的信息相同。</span><span class="sxs-lookup"><span data-stu-id="39e1f-p115">CAC and Media Bypass are both enabled. Media Bypass must be set to **Use Site and Region Information**. This site and region information is the same as that used for CAC.</span></span>
    
    <span data-ttu-id="39e1f-168">如果启用 CAC，则不能选择“**始终绕过**”，反之亦然，因为两种配置相互排斥。</span><span class="sxs-lookup"><span data-stu-id="39e1f-168">If you enable CAC, you cannot select **Always Bypass**, and vice-versa, because the two configurations are mutually exclusive.</span></span> <span data-ttu-id="39e1f-169">即两者中只有一个可应用于任意给定的 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="39e1f-169">That is, only one of the two will apply to any given PSTN call.</span></span> <span data-ttu-id="39e1f-170">首先，将执行检查以确定是否对呼叫应用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="39e1f-170">First, a check is made to determine if media bypass applies to the call.</span></span> <span data-ttu-id="39e1f-171">如果是，则不使用 CAC。</span><span class="sxs-lookup"><span data-stu-id="39e1f-171">If it does, then CAC is not used.</span></span> <span data-ttu-id="39e1f-172">这样可行，因为如果可以对呼叫使用旁路，则根据定义将使用不需要 CAC 的连接。</span><span class="sxs-lookup"><span data-stu-id="39e1f-172">This makes sense, because if a call is eligible for bypass, it is by definition using a connection where CAC is not needed.</span></span> <span data-ttu-id="39e1f-173">如果不能应用于呼叫绕过，（即，如果客户端和网关的绕过 Id 不匹配），然后 CAC 应用于调用。</span><span class="sxs-lookup"><span data-stu-id="39e1f-173">If bypass cannot be applied to the call (that is, if the client's and gateway's bypass IDs do not match), then CAC is applied to the call.</span></span>
    
- <span data-ttu-id="39e1f-174">未启用 CAC 并且将媒体旁路设置为“**始终绕过**”。</span><span class="sxs-lookup"><span data-stu-id="39e1f-174">CAC not enabled and Media Bypass set to **Always Bypass**.</span></span>
    
    <span data-ttu-id="39e1f-175">在此配置中，客户端和中继子网将映射至唯一的旁路绕过 ID，该 ID 由系统计算得出。</span><span class="sxs-lookup"><span data-stu-id="39e1f-175">In this configuration, both client and trunk subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>
    
- <span data-ttu-id="39e1f-176">未启用 CAC 并且将媒体旁路设置为“**使用站点和区域信息**”。</span><span class="sxs-lookup"><span data-stu-id="39e1f-176">CAC not enabled and Media Bypass set to **Use Site and Region Information**.</span></span>
    
    <span data-ttu-id="39e1f-177">在启用“**使用站点和区域信息**”的配置中，绕过确定基本上以相同方式工作，不论是否启用 CAC。</span><span class="sxs-lookup"><span data-stu-id="39e1f-177">Where **Use Site and Region Information** is enabled, bypass determination works essentially the same way, regardless of whether CAC is enabled or not.</span></span> <span data-ttu-id="39e1f-178">即，对于任何给定的 PSTN 呼叫，客户端的子网映射到特定站点，并提取该子网的绕过 ID。</span><span class="sxs-lookup"><span data-stu-id="39e1f-178">That is, for any given PSTN call, the client's subnet is mapped to a particular site, and the bypass ID for that subnet is extracted.</span></span> <span data-ttu-id="39e1f-179">同样，网关的子网映射到特定站点，并提取该子网的绕过 ID。</span><span class="sxs-lookup"><span data-stu-id="39e1f-179">Similarly, the gateway's subnet is mapped to a particular site, and the bypass ID for that subnet is extracted.</span></span> <span data-ttu-id="39e1f-180">仅当两个绕过 ID 相同时，才会对呼叫执行绕过。</span><span class="sxs-lookup"><span data-stu-id="39e1f-180">Only if the two bypass IDs are identical will bypass happen for the call.</span></span> <span data-ttu-id="39e1f-181">如果不同，将不会发生媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="39e1f-181">If they are not identical, media bypass will not occur.</span></span>
    
    <span data-ttu-id="39e1f-182">如果要使用站点和区域配置控制绕过决定，那么即使在全局范围内禁用 CAC，也需要为每个站点和链接定义带宽策略。</span><span class="sxs-lookup"><span data-stu-id="39e1f-182">Even though CAC is disabled globally, bandwidth policy needs to be defined for each site and link if you want to use site-and-region configuration to control the bypass decision.</span></span> <span data-ttu-id="39e1f-183">无关紧要的带宽约束或其形式的实际值。</span><span class="sxs-lookup"><span data-stu-id="39e1f-183">The actual value of the bandwidth constraint or its modality doesn't matter.</span></span> <span data-ttu-id="39e1f-184">最终目标是让系统自动计算不同的绕过 ID，以便与连接不佳的不同区域设置关联。</span><span class="sxs-lookup"><span data-stu-id="39e1f-184">The ultimate goal is to have the system automatically calculate different bypass IDs to associate with different locales that are not well connected.</span></span> <span data-ttu-id="39e1f-185">根据定义，定义带宽限制是指链接连接不佳。</span><span class="sxs-lookup"><span data-stu-id="39e1f-185">Defining a bandwidth constraint by definition means a link is not well connected.</span></span>
    
- <span data-ttu-id="39e1f-186">启用 CAC，但未启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="39e1f-186">CAC is enabled and media bypass is not enabled.</span></span> <span data-ttu-id="39e1f-187">该配置仅适用于所有网关和 IP-PBX 均连接不佳，或不满足媒体旁路的其他要求的情况。</span><span class="sxs-lookup"><span data-stu-id="39e1f-187">This would apply only where all gateways and IP-PBXs are not well connected or do not meet other requirements for media bypass.</span></span> <span data-ttu-id="39e1f-188">媒体绕过的要求的详细信息，请参阅[媒体绕过的要求](http://technet.microsoft.com/library/6162a204-0e7c-460a-8eb2-e592c6590a8a.aspx)。</span><span class="sxs-lookup"><span data-stu-id="39e1f-188">For details about requirements for media bypass, see [Requirements for Media Bypass](http://technet.microsoft.com/library/6162a204-0e7c-460a-8eb2-e592c6590a8a.aspx).</span></span>
    
## <a name="technical-requirements"></a><span data-ttu-id="39e1f-189">技术要求</span><span class="sxs-lookup"><span data-stu-id="39e1f-189">Technical requirements</span></span>

<span data-ttu-id="39e1f-190">对于每个 pstn 呼叫，中介服务器决定是否可以而不遍历中介服务器发送到的中介服务器对等方直接从业务终结点的原点而言的 Skype 的媒体。</span><span class="sxs-lookup"><span data-stu-id="39e1f-190">For each call to the PSTN, the Mediation Server determines whether media from the Skype for Business endpoint of origin can be sent directly to a Mediation Server peer without traversing the Mediation Server.</span></span> <span data-ttu-id="39e1f-191">对等方可以是与其中路由呼叫的中介服务器之间的中继关联的 Internet 电话服务提供商 (ITSP) 的 PSTN 网关、IP-PBX 或会话边界控制器 (SBC)。</span><span class="sxs-lookup"><span data-stu-id="39e1f-191">The peer can be a PSTN gateway, IP-PBX, or Session Border Controller (SBC) at an Internet telephony service provider (ITSP) that is associated with the trunk between the Mediation Server where the call is routed.</span></span>
  
<span data-ttu-id="39e1f-192">当满足以下要求时，可采用媒体旁路功能：</span><span class="sxs-lookup"><span data-stu-id="39e1f-192">Media bypass can be employed when the following requirements are met:</span></span>
  
- <span data-ttu-id="39e1f-193">中介服务器对等必须支持媒体旁路，最重要的是能够处理多个 （称为"早期对话数"） 的分叉的响应的所需的功能。</span><span class="sxs-lookup"><span data-stu-id="39e1f-193">A Mediation Server peer must support the necessary capabilities for media bypass, the most important being the ability to handle multiple forked responses (known as "early dialogs").</span></span> <span data-ttu-id="39e1f-194">与网关、PBX 制造商或 ITSP 联系，以获取网关、PBX 或 SBC 可接受的最大早期对话数的值。</span><span class="sxs-lookup"><span data-stu-id="39e1f-194">Contact the manufacturer of your gateway or PBX, or your ITSP, to obtain the value for the maximum number of early dialogs that the gateway, PBX, or SBC can accept.</span></span>
    
- <span data-ttu-id="39e1f-195">中介服务器对等方必须接受直接从业务终结点的 Skype 的媒体流量。</span><span class="sxs-lookup"><span data-stu-id="39e1f-195">The Mediation Server peer must accept media traffic directly from Skype for Business endpoints.</span></span> <span data-ttu-id="39e1f-196">许多 ITSPs 允许其 SBC 只能从中介服务器接收通信。</span><span class="sxs-lookup"><span data-stu-id="39e1f-196">Many ITSPs allow their SBC to receive traffic only from the Mediation Server.</span></span> <span data-ttu-id="39e1f-197">与 ITSP 以确定其 SBC 是否接受直接从业务终结点的 Skype 的媒体流量。</span><span class="sxs-lookup"><span data-stu-id="39e1f-197">Contact your ITSP to determine whether its SBC accepts media traffic directly from Skype for Business endpoints.</span></span>
    
- <span data-ttu-id="39e1f-198">Skype 业务客户端和对等方必须正确连接，这意味着也位于相同的网络区域，或在网络通过 WAN 连接到该区域的站点链接的中介服务器已没有带宽限制</span><span class="sxs-lookup"><span data-stu-id="39e1f-198">Skype for Business clients and a Mediation Server peer must be well connected, meaning that they are either located in the same network region or at network sites that connect to the region over WAN links that have no bandwidth constraints</span></span>
    

