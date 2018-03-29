---
title: 在 Skype for Business Server 2015 中规划企业语音
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: 企业语音业务服务器规划在 Skype 的基础知识，包括站点、 区域、 站点之间的网络链接和估计语音使用通信。
ms.openlocfilehash: a04c379e3a616a511306db62fd908af26e325418
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server-2015"></a><span data-ttu-id="88f15-103">在 Skype for Business Server 2015 中规划企业语音</span><span class="sxs-lookup"><span data-stu-id="88f15-103">Plan for Enterprise Voice in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="88f15-104">企业语音业务服务器规划在 Skype 的基础知识，包括站点、 区域、 站点之间的网络链接和估计语音使用通信。</span><span class="sxs-lookup"><span data-stu-id="88f15-104">Enterprise Voice planning basics in Skype for Business Server, including sites, regions, network links between sites, and estimating voice usage traffic.</span></span>
  
<span data-ttu-id="88f15-105">企业语音的部署过程取决于您现有的拓扑结构、 基础架构和您想要支持的企业语音功能。</span><span class="sxs-lookup"><span data-stu-id="88f15-105">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="88f15-106">所需过程将取决于您选择的功能，但还有另一些规划注意事项需要您重点关注。</span><span class="sxs-lookup"><span data-stu-id="88f15-106">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>
  
<span data-ttu-id="88f15-107">一般情况下，考虑的类型和数量要部署的站点和其地理位置、 每个站点的话务量、 连接站点的网络链接的类型是否为每个提供语音功能的冗余和故障切换站点，以及是否希望使用现有的 PBX 设备。</span><span class="sxs-lookup"><span data-stu-id="88f15-107">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="88f15-108">有一些特定的事项，例如高可用性、 业务服务器作为一个整体的规划为 Skype 时应考虑的。</span><span class="sxs-lookup"><span data-stu-id="88f15-108">There are certain considerations, such as high availability, that you should consider when you plan for Skype for Business Server as a whole.</span></span> <span data-ttu-id="88f15-109">根据需要在本部分中，整个主题讨论这些事项。</span><span class="sxs-lookup"><span data-stu-id="88f15-109">These considerations are discussed in topics throughout this section, as needed.</span></span>
  
## <a name="sites-and-regions"></a><span data-ttu-id="88f15-110">站点和区域</span><span class="sxs-lookup"><span data-stu-id="88f15-110">Sites and regions</span></span>

<span data-ttu-id="88f15-111">首先，要确定拓扑结构将部署企业语音和这些站点属于网络区域中的站点。</span><span class="sxs-lookup"><span data-stu-id="88f15-111">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="88f15-112">特别是，考虑如何将公用电话交换网 (PSTN) 连接到每个站点。</span><span class="sxs-lookup"><span data-stu-id="88f15-112">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="88f15-113">由于可管理性和物流方面的原因，这些站点所属的区域可能是一个决定性因素。</span><span class="sxs-lookup"><span data-stu-id="88f15-113">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="88f15-114">决定将本地部署网关的位置，将部署高存活力的分支装置 (Sba) 的位置，在其中您可以配置 SIP 中继 （本地或从中心站点） 到互联网电话服务提供程序 (ITSP)。</span><span class="sxs-lookup"><span data-stu-id="88f15-114">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>
  
## <a name="network-links-between-sites"></a><span data-ttu-id="88f15-115">站点之间的网络链路</span><span class="sxs-lookup"><span data-stu-id="88f15-115">Network links between sites</span></span>

<span data-ttu-id="88f15-116">您还需要考虑您希望网络链路中央网站和它的分支站点之间的带宽使用率。</span><span class="sxs-lookup"><span data-stu-id="88f15-116">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="88f15-117">如果有，或准备部署时，站点间的弹性 WAN 链接我们建议您部署网关，每个分支站点提供对这些站点的用户的本地向内直拨 (DID) 终止。</span><span class="sxs-lookup"><span data-stu-id="88f15-117">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="88f15-118">如果具有可恢复 WAN 链路，但 WAN 链路上的带宽可能被限定，则需要为该链路配置呼叫允许控制。</span><span class="sxs-lookup"><span data-stu-id="88f15-118">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="88f15-119">如果没有可恢复的 WAN 链接，承载分支站点，少于 1000 个用户，而且没有本地培训的 Skype 业务服务器管理员可用，我们建议您部署分支站点高存活力的分支装置。</span><span class="sxs-lookup"><span data-stu-id="88f15-119">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="88f15-120">如果要承载网站分支在 1000年和 5000 用户之间，缺乏弹性的 WAN 连接，并为业务服务器管理员可用，我们建议您部署自动恢复的分支服务器在分部地点的小型网关具有经过培训的 Skype。</span><span class="sxs-lookup"><span data-stu-id="88f15-120">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="88f15-121">如果具有支持媒体旁路功能的对等网关，则也可以考虑在限定链路上启用媒体旁路功能。</span><span class="sxs-lookup"><span data-stu-id="88f15-121">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>
  
## <a name="estimating-voice-usage-and-traffic"></a><span data-ttu-id="88f15-122">估计语音使用和流量</span><span class="sxs-lookup"><span data-stu-id="88f15-122">Estimating voice usage and traffic</span></span>

<span data-ttu-id="88f15-123">Microsoft Lync Server 2013、 规划工具使用以下指标来估计用户通信： 每个站点支持该通讯所需的端口数。</span><span class="sxs-lookup"><span data-stu-id="88f15-123">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="88f15-124">对于**低流量**（每个用户每小时一个 PSTN 呼叫），每个端口对应 15 个用户。</span><span class="sxs-lookup"><span data-stu-id="88f15-124">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
    
> <span data-ttu-id="88f15-125">对于**中等流量**（每个用户每小时 2 个 PSTN 呼叫），每个端口对应 10 个用户。</span><span class="sxs-lookup"><span data-stu-id="88f15-125">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
    
> <span data-ttu-id="88f15-126">对于**高流量**（每个用户每小时 3 个或更多 PSTN 呼叫），每个端口对应 5 个用户。</span><span class="sxs-lookup"><span data-stu-id="88f15-126">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="88f15-127">端口数又确定中介服务器和网关所需的数目。</span><span class="sxs-lookup"><span data-stu-id="88f15-127">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="88f15-128">大多数组织考虑部署范围的大小从 2 个端口到端口多达 960 公用交换的电话网络 (PSTN) 网关。</span><span class="sxs-lookup"><span data-stu-id="88f15-128">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="88f15-129">（有更大的网关，但这些都主要由电话服务提供程序）。</span><span class="sxs-lookup"><span data-stu-id="88f15-129">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="88f15-p106">例如，具有 10,000 个用户和中等流量的组织将需要 1000 个端口。所需的网关数等于所需的端口总数，由网关的总容量决定。</span><span class="sxs-lookup"><span data-stu-id="88f15-p106">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  
## <a name="components-features-and-options-of-enterprise-voice"></a><span data-ttu-id="88f15-132">组件、 功能和企业语音的选项</span><span class="sxs-lookup"><span data-stu-id="88f15-132">Components, features, and options of Enterprise Voice</span></span>

<span data-ttu-id="88f15-133">有关规划企业语音部署，请参阅以下各部分的详细信息。</span><span class="sxs-lookup"><span data-stu-id="88f15-133">See the following sections for more information on planning your Enterprise Voice deployment.</span></span>
  
- [<span data-ttu-id="88f15-134">企业语音在 Skype 的业务服务器 2015年所需的组件</span><span class="sxs-lookup"><span data-stu-id="88f15-134">Components required for Enterprise Voice in Skype for Business Server 2015</span></span>](components-required-for-enterprise-voice.md)
    
- [<span data-ttu-id="88f15-135">在 Skype 的 PSTN 连接的业务服务器 2015年计划</span><span class="sxs-lookup"><span data-stu-id="88f15-135">Plan for PSTN connectivity in Skype for Business Server 2015</span></span>](pstn-connectivity-0.md)
    
- [<span data-ttu-id="88f15-136">Skype 在高级的企业语音功能的业务服务器 2015年的网络设置</span><span class="sxs-lookup"><span data-stu-id="88f15-136">Network settings for the advanced Enterprise Voice features in Skype for Business Server 2015</span></span>](network-settings-for-advanced-features.md)
    
- [<span data-ttu-id="88f15-137">在 Skype 呼叫许可控制业务服务器 2015年计划</span><span class="sxs-lookup"><span data-stu-id="88f15-137">Plan for call admission control in Skype for Business Server 2015</span></span>](call-admission-control.md)
    
- [<span data-ttu-id="88f15-138">紧急服务 Skype 业务服务器 2015年计划</span><span class="sxs-lookup"><span data-stu-id="88f15-138">Plan for emergency services in Skype for Business Server 2015</span></span>](emergency-services.md)
    
- [<span data-ttu-id="88f15-139">在业务 2015年的 Skype 的媒体跳过计划</span><span class="sxs-lookup"><span data-stu-id="88f15-139">Plan for media bypass in Skype for Business 2015</span></span>](media-bypass.md)
    
- [<span data-ttu-id="88f15-140">规划业务 2015年的 Skype 使用专用电话线路</span><span class="sxs-lookup"><span data-stu-id="88f15-140">Plan for private telephone lines with Skype for Business 2015</span></span>](private-telephone-lines.md)
    
- [<span data-ttu-id="88f15-141">基于位置的路由在 Skype 的业务 2015年计划</span><span class="sxs-lookup"><span data-stu-id="88f15-141">Plan for Location-Based Routing in Skype for Business 2015</span></span>](location-based-routing.md)
    
- [<span data-ttu-id="88f15-142">规划业务 2015年的 Skype 通话管理功能</span><span class="sxs-lookup"><span data-stu-id="88f15-142">Plan for call management features in Skype for Business 2015</span></span>](call-management-features.md)
    
- [<span data-ttu-id="88f15-143">企业语音在 Skype 的恢复能力的业务服务器 2015年计划</span><span class="sxs-lookup"><span data-stu-id="88f15-143">Plan for Enterprise Voice resiliency in Skype for Business Server 2015</span></span>](enterprise-voice-resiliency.md)
    

