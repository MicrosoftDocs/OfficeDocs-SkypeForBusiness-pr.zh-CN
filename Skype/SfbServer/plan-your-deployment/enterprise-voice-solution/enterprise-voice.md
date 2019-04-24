---
title: 规划业务服务器的 Skype 中的企业语音
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: 企业语音规划业务服务器中 Skype 的基础知识，包括网站、 区域、 网络站点间的链接和估计语音用法流量。
ms.openlocfilehash: 281dfefedb05cd60e1d050d708bacae4eec2baa2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206892"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="3eca1-103">规划业务服务器的 Skype 中的企业语音</span><span class="sxs-lookup"><span data-stu-id="3eca1-103">Plan for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="3eca1-104">企业语音规划业务服务器中 Skype 的基础知识，包括网站、 区域、 网络站点间的链接和估计语音用法流量。</span><span class="sxs-lookup"><span data-stu-id="3eca1-104">Enterprise Voice planning basics in Skype for Business Server, including sites, regions, network links between sites, and estimating voice usage traffic.</span></span>
  
<span data-ttu-id="3eca1-105">企业语音的部署过程取决于您现有的拓扑和基础结构，您想要支持的企业语音功能。</span><span class="sxs-lookup"><span data-stu-id="3eca1-105">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="3eca1-106">所需过程将取决于您选择的功能，但还有另一些规划注意事项需要您重点关注。</span><span class="sxs-lookup"><span data-stu-id="3eca1-106">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>
  
<span data-ttu-id="3eca1-107">一般情况下，应考虑的类型和数量您想要部署的网站和及其地理位置、 呼叫量在每个站点、 将网站，连接的网络链接的类型是否要为每个语音功能提供冗余和故障转移网站，并且是否想要使用现有的 PBX 设备。</span><span class="sxs-lookup"><span data-stu-id="3eca1-107">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="3eca1-108">有某些注意事项，例如业务服务器作为一个整体规划 Skype 时应考虑的高可用性。</span><span class="sxs-lookup"><span data-stu-id="3eca1-108">There are certain considerations, such as high availability, that you should consider when you plan for Skype for Business Server as a whole.</span></span> <span data-ttu-id="3eca1-109">根据需要在此部分中，整个主题讨论以下注意事项。</span><span class="sxs-lookup"><span data-stu-id="3eca1-109">These considerations are discussed in topics throughout this section, as needed.</span></span>
  
## <a name="sites-and-regions"></a><span data-ttu-id="3eca1-110">站点和区域</span><span class="sxs-lookup"><span data-stu-id="3eca1-110">Sites and regions</span></span>

<span data-ttu-id="3eca1-111">首先，确定您将在其中部署企业语音和这些网站所属的网络区域的拓扑中的网站。</span><span class="sxs-lookup"><span data-stu-id="3eca1-111">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="3eca1-112">特别是，考虑如何将公用电话交换网 (PSTN) 连接到每个站点。</span><span class="sxs-lookup"><span data-stu-id="3eca1-112">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="3eca1-113">由于可管理性和物流方面的原因，这些站点所属的区域可能是一个决定性因素。</span><span class="sxs-lookup"><span data-stu-id="3eca1-113">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="3eca1-114">确定将本地部署网关的位置，其中将部署 Survivable Branch Appliance (Sba)，以及可在其中配置 SIP 中继 （本地或中央站点） 到 Internet 电话服务提供商 (ITSP)。</span><span class="sxs-lookup"><span data-stu-id="3eca1-114">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>
  
## <a name="network-links-between-sites"></a><span data-ttu-id="3eca1-115">站点之间的网络链路</span><span class="sxs-lookup"><span data-stu-id="3eca1-115">Network links between sites</span></span>

<span data-ttu-id="3eca1-116">您还需要考虑您预期网络链路您中央站点和其分支站点之间的带宽使用率。</span><span class="sxs-lookup"><span data-stu-id="3eca1-116">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="3eca1-117">如果有，或计划部署，可恢复的 WAN 链接之间网站，我们建议您部署在每个分支站点提供这些网站的用户的本地外线直拨分机 (DID) 终止网关。</span><span class="sxs-lookup"><span data-stu-id="3eca1-117">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="3eca1-118">如果具有可恢复 WAN 链路，但 WAN 链路上的带宽可能被限定，则需要为该链路配置呼叫允许控制。</span><span class="sxs-lookup"><span data-stu-id="3eca1-118">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="3eca1-119">如果您没有可恢复的 WAN 链接，承载分支站点，少于 1000 位用户，且不具有本地培训的 Skype 业务服务器管理员可用，我们建议您部署 Survivable Branch Appliance 分支站点。</span><span class="sxs-lookup"><span data-stu-id="3eca1-119">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="3eca1-120">如果您承载 1000年到 5000 分支站点的用户，缺少可恢复的 WAN 连接，并且具有经过 Skype 培训为可用，我们建议您部署 Survivable Branch Server 与小型网关在分支站点的业务服务器管理员。</span><span class="sxs-lookup"><span data-stu-id="3eca1-120">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="3eca1-121">如果具有支持媒体旁路功能的对等网关，则也可以考虑在限定链路上启用媒体旁路功能。</span><span class="sxs-lookup"><span data-stu-id="3eca1-121">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>
  
## <a name="estimating-voice-usage-and-traffic"></a><span data-ttu-id="3eca1-122">估计语音使用和流量</span><span class="sxs-lookup"><span data-stu-id="3eca1-122">Estimating voice usage and traffic</span></span>

<span data-ttu-id="3eca1-123">Microsoft Lync Server 2013、 规划工具使用以下任一指标来估计每个站点和支持该流量所需的端口数的用户通信。</span><span class="sxs-lookup"><span data-stu-id="3eca1-123">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="3eca1-124">对于**低流量**（每个用户每小时一个 PSTN 呼叫），每个端口对应 15 个用户。</span><span class="sxs-lookup"><span data-stu-id="3eca1-124">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="3eca1-125">对于**中等流量**（每个用户每小时 2 个 PSTN 呼叫），每个端口对应 10 个用户。</span><span class="sxs-lookup"><span data-stu-id="3eca1-125">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="3eca1-126">对于**高流量**（每个用户每小时 3 个或更多 PSTN 呼叫），每个端口对应 5 个用户。</span><span class="sxs-lookup"><span data-stu-id="3eca1-126">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="3eca1-127">反过来的端口数确定的中介服务器和网关都需要的数目。</span><span class="sxs-lookup"><span data-stu-id="3eca1-127">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="3eca1-128">大多数组织考虑部署大小在 2 端口到 960 端口公用电话交换网 (pstn) 网关。</span><span class="sxs-lookup"><span data-stu-id="3eca1-128">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="3eca1-129">（有更大的网关，但是这些主要由电话服务提供程序。）</span><span class="sxs-lookup"><span data-stu-id="3eca1-129">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="3eca1-p106">例如，具有 10,000 个用户和中等流量的组织将需要 1000 个端口。所需的网关数等于所需的端口总数，由网关的总容量决定。</span><span class="sxs-lookup"><span data-stu-id="3eca1-p106">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  
## <a name="components-features-and-options-of-enterprise-voice"></a><span data-ttu-id="3eca1-132">组件、 功能和企业语音的选项</span><span class="sxs-lookup"><span data-stu-id="3eca1-132">Components, features, and options of Enterprise Voice</span></span>

<span data-ttu-id="3eca1-133">规划企业语音部署，请参阅以下各节的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3eca1-133">See the following sections for more information on planning your Enterprise Voice deployment.</span></span>
  
- [<span data-ttu-id="3eca1-134">所需的 Skype 中的企业语音的企业服务器组件</span><span class="sxs-lookup"><span data-stu-id="3eca1-134">Components required for Enterprise Voice in Skype for Business Server</span></span>](components-required-for-enterprise-voice.md)
    
- [<span data-ttu-id="3eca1-135">规划业务服务器中 Skype 的 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="3eca1-135">Plan for PSTN connectivity in Skype for Business Server</span></span>](pstn-connectivity-0.md)
    
- [<span data-ttu-id="3eca1-136">Skype 中的高级企业语音功能 Business server 网络设置</span><span class="sxs-lookup"><span data-stu-id="3eca1-136">Network settings for the advanced Enterprise Voice features in Skype for Business Server</span></span>](network-settings-for-advanced-features.md)
    
- [<span data-ttu-id="3eca1-137">规划呼叫允许控制 Skype 中的业务服务器</span><span class="sxs-lookup"><span data-stu-id="3eca1-137">Plan for call admission control in Skype for Business Server</span></span>](call-admission-control.md)
    
- [<span data-ttu-id="3eca1-138">规划业务服务器中 Skype 的紧急服务</span><span class="sxs-lookup"><span data-stu-id="3eca1-138">Plan for emergency services in Skype for Business Server</span></span>](emergency-services.md)
    
- [<span data-ttu-id="3eca1-139">规划媒体绕过 Skype for Business 中</span><span class="sxs-lookup"><span data-stu-id="3eca1-139">Plan for media bypass in Skype for Business</span></span>](media-bypass.md)
    
- [<span data-ttu-id="3eca1-140">规划与业务的 Skype 的专用电话线路</span><span class="sxs-lookup"><span data-stu-id="3eca1-140">Plan for private telephone lines with Skype for Business</span></span>](private-telephone-lines.md)
    
- [<span data-ttu-id="3eca1-141">Plan for Business 中 Skype 基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="3eca1-141">Plan for Location-Based Routing in Skype for Business</span></span>](location-based-routing.md)
    
- [<span data-ttu-id="3eca1-142">Plan for Business 的 Skype 中呼叫管理功能</span><span class="sxs-lookup"><span data-stu-id="3eca1-142">Plan for call management features in Skype for Business</span></span>](call-management-features.md)
    
- [<span data-ttu-id="3eca1-143">Plan for Enterprise Voice resiliency in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3eca1-143">Plan for Enterprise Voice resiliency in Skype for Business Server</span></span>](enterprise-voice-resiliency.md)
    

