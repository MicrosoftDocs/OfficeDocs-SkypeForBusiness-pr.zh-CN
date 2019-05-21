---
title: Skype for business Server 中的 "规划企业语音"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Skype for business 服务器中的企业语音规划基础知识, 包括网站、区域、网站之间的网络链接和估计语音使用流量。
ms.openlocfilehash: fdc653404f6b7182086af00e6e788a1d3bd421eb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276864"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="00291-103">Skype for business Server 中的 "规划企业语音"</span><span class="sxs-lookup"><span data-stu-id="00291-103">Plan for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="00291-104">Skype for business 服务器中的企业语音规划基础知识, 包括网站、区域、网站之间的网络链接和估计语音使用流量。</span><span class="sxs-lookup"><span data-stu-id="00291-104">Enterprise Voice planning basics in Skype for Business Server, including sites, regions, network links between sites, and estimating voice usage traffic.</span></span>
  
<span data-ttu-id="00291-105">企业语音的部署过程取决于你的现有拓扑、基础结构和你希望支持的企业语音功能。</span><span class="sxs-lookup"><span data-stu-id="00291-105">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="00291-106">所需过程将取决于您选择的功能，但还有另一些规划注意事项需要您重点关注。</span><span class="sxs-lookup"><span data-stu-id="00291-106">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>
  
<span data-ttu-id="00291-107">通常, 请考虑要部署的网站的类型和数量以及它们的地理位置、每个网站的调用卷、连接网站的网络链接的类型, 无论你是否希望为每个网站提供语音功能的冗余和故障转移网站, 以及是否希望使用现有的 PBX 设备。</span><span class="sxs-lookup"><span data-stu-id="00291-107">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="00291-108">将 Skype for business 服务器规划为整体时, 应考虑一些事项 (如高可用性)。</span><span class="sxs-lookup"><span data-stu-id="00291-108">There are certain considerations, such as high availability, that you should consider when you plan for Skype for Business Server as a whole.</span></span> <span data-ttu-id="00291-109">这些注意事项将根据需要在本部分中的主题中进行讨论。</span><span class="sxs-lookup"><span data-stu-id="00291-109">These considerations are discussed in topics throughout this section, as needed.</span></span>
  
## <a name="sites-and-regions"></a><span data-ttu-id="00291-110">站点和区域</span><span class="sxs-lookup"><span data-stu-id="00291-110">Sites and regions</span></span>

<span data-ttu-id="00291-111">首先, 确定你的拓扑中的网站, 你将在这些网站中部署企业语音和这些网站所属的网络区域。</span><span class="sxs-lookup"><span data-stu-id="00291-111">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="00291-112">特别是，考虑如何将公用电话交换网 (PSTN) 连接到每个站点。</span><span class="sxs-lookup"><span data-stu-id="00291-112">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="00291-113">由于可管理性和物流方面的原因，这些站点所属的区域可能是一个决定性因素。</span><span class="sxs-lookup"><span data-stu-id="00291-113">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="00291-114">确定本地部署网关的位置 (将部署 Survivable 分支装置 (SBAs)), 以及你可以在哪里将 SIP 中继 (本地或中央网站) 配置为 Internet 电话服务提供商 (ITSP)。</span><span class="sxs-lookup"><span data-stu-id="00291-114">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>
  
## <a name="network-links-between-sites"></a><span data-ttu-id="00291-115">站点之间的网络链路</span><span class="sxs-lookup"><span data-stu-id="00291-115">Network links between sites</span></span>

<span data-ttu-id="00291-116">您还需要考虑您的中心站点与其分支站点之间网络链接所期望的带宽使用情况。</span><span class="sxs-lookup"><span data-stu-id="00291-116">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="00291-117">如果你拥有或计划在网站之间部署弹性 WAN 链接, 我们建议你在每个分支站点上部署网关, 以便为用户在这些网站上提供本地直接向内拨号 (已) 终止。</span><span class="sxs-lookup"><span data-stu-id="00291-117">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="00291-118">如果具有可恢复 WAN 链路，但 WAN 链路上的带宽可能被限定，则需要为该链路配置呼叫允许控制。</span><span class="sxs-lookup"><span data-stu-id="00291-118">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="00291-119">如果您没有弹性 WAN 链接, 在您的分支站点上托管的用户少于1000个用户, 并且没有本地训练有素的 Skype for business 服务器管理员可用, 我们建议您在分支站点部署 Survivable 分支装置。</span><span class="sxs-lookup"><span data-stu-id="00291-119">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="00291-120">如果你在分支站点上的1000和5000用户之间托管, 缺少弹性 WAN 连接, 并且有训练有素的 Skype for business 服务器管理员可用, 我们建议你在分支站点上使用小型网关部署 Survivable 分支服务器。</span><span class="sxs-lookup"><span data-stu-id="00291-120">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="00291-121">如果具有支持媒体旁路功能的对等网关，则也可以考虑在限定链路上启用媒体旁路功能。</span><span class="sxs-lookup"><span data-stu-id="00291-121">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>
  
## <a name="estimating-voice-usage-and-traffic"></a><span data-ttu-id="00291-122">估计语音使用和流量</span><span class="sxs-lookup"><span data-stu-id="00291-122">Estimating voice usage and traffic</span></span>

<span data-ttu-id="00291-123">Microsoft Lync Server 2013、计划工具使用以下指标估计每个站点上的用户流量以及支持该流量所需的端口数。</span><span class="sxs-lookup"><span data-stu-id="00291-123">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="00291-124">对于**低流量**（每个用户每小时一个 PSTN 呼叫），每个端口对应 15 个用户。</span><span class="sxs-lookup"><span data-stu-id="00291-124">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="00291-125">对于**中等流量**（每个用户每小时 2 个 PSTN 呼叫），每个端口对应 10 个用户。</span><span class="sxs-lookup"><span data-stu-id="00291-125">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="00291-126">对于**高流量**（每个用户每小时 3 个或更多 PSTN 呼叫），每个端口对应 5 个用户。</span><span class="sxs-lookup"><span data-stu-id="00291-126">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="00291-127">端口数依次确定所需中介服务器和网关的数量。</span><span class="sxs-lookup"><span data-stu-id="00291-127">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="00291-128">大多数组织考虑将范围从2个端口部署到最多960端口的公共交换电话网络 (PSTN) 网关。</span><span class="sxs-lookup"><span data-stu-id="00291-128">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="00291-129">(甚至更大的网关, 但主要由电话服务提供商使用。)</span><span class="sxs-lookup"><span data-stu-id="00291-129">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="00291-p106">例如，具有 10,000 个用户和中等流量的组织将需要 1000 个端口。所需的网关数等于所需的端口总数，由网关的总容量决定。</span><span class="sxs-lookup"><span data-stu-id="00291-p106">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  
## <a name="components-features-and-options-of-enterprise-voice"></a><span data-ttu-id="00291-132">企业语音的组件、功能和选项</span><span class="sxs-lookup"><span data-stu-id="00291-132">Components, features, and options of Enterprise Voice</span></span>

<span data-ttu-id="00291-133">有关规划企业语音部署的详细信息, 请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="00291-133">See the following sections for more information on planning your Enterprise Voice deployment.</span></span>
  
- [<span data-ttu-id="00291-134">Skype for business Server 中的企业语音所需的组件</span><span class="sxs-lookup"><span data-stu-id="00291-134">Components required for Enterprise Voice in Skype for Business Server</span></span>](components-required-for-enterprise-voice.md)
    
- [<span data-ttu-id="00291-135">在 Skype for Business 服务器中规划 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="00291-135">Plan for PSTN connectivity in Skype for Business Server</span></span>](pstn-connectivity-0.md)
    
- [<span data-ttu-id="00291-136">Skype for Business Server 中的高级企业语音功能的网络设置</span><span class="sxs-lookup"><span data-stu-id="00291-136">Network settings for the advanced Enterprise Voice features in Skype for Business Server</span></span>](network-settings-for-advanced-features.md)
    
- [<span data-ttu-id="00291-137">在 Skype for Business 服务器中规划呼叫许可控制</span><span class="sxs-lookup"><span data-stu-id="00291-137">Plan for call admission control in Skype for Business Server</span></span>](call-admission-control.md)
    
- [<span data-ttu-id="00291-138">Skype for business Server 中的紧急服务计划</span><span class="sxs-lookup"><span data-stu-id="00291-138">Plan for emergency services in Skype for Business Server</span></span>](emergency-services.md)
    
- [<span data-ttu-id="00291-139">在 Skype for Business 中规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="00291-139">Plan for media bypass in Skype for Business</span></span>](media-bypass.md)
    
- [<span data-ttu-id="00291-140">通过 Skype for Business 规划私人电话线</span><span class="sxs-lookup"><span data-stu-id="00291-140">Plan for private telephone lines with Skype for Business</span></span>](private-telephone-lines.md)
    
- [<span data-ttu-id="00291-141">在 Skype for Business 中规划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="00291-141">Plan for Location-Based Routing in Skype for Business</span></span>](location-based-routing.md)
    
- [<span data-ttu-id="00291-142">在 Skype for Business 中规划通话管理功能</span><span class="sxs-lookup"><span data-stu-id="00291-142">Plan for call management features in Skype for Business</span></span>](call-management-features.md)
    
- [<span data-ttu-id="00291-143">Plan for Enterprise Voice resiliency in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="00291-143">Plan for Enterprise Voice resiliency in Skype for Business Server</span></span>](enterprise-voice-resiliency.md)
    

