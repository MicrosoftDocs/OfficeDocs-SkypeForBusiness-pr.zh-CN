---
title: 规划企业语音 Skype for Business Server 中的服务
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: 企业语音 Skype for Business Server 中的规划基础知识，包括站点、区域、站点之间的网络链接以及估计语音使用流量。
ms.openlocfilehash: 8f10eed8dfcfa7a8878b673ab76fd4d1fd40cc29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825672"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="f2eef-103">规划企业语音 Skype for Business Server 中的服务</span><span class="sxs-lookup"><span data-stu-id="f2eef-103">Plan for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="f2eef-104">企业语音 Skype for Business Server 中的规划基础知识，包括站点、区域、站点之间的网络链接以及估计语音使用流量。</span><span class="sxs-lookup"><span data-stu-id="f2eef-104">Enterprise Voice planning basics in Skype for Business Server, including sites, regions, network links between sites, and estimating voice usage traffic.</span></span>
  
<span data-ttu-id="f2eef-105">部署的部署企业语音取决于现有拓扑、基础结构和企业语音支持的功能。</span><span class="sxs-lookup"><span data-stu-id="f2eef-105">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="f2eef-106">所需过程将取决于您选择的功能，但还有另一些规划注意事项需要您重点关注。</span><span class="sxs-lookup"><span data-stu-id="f2eef-106">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>
  
<span data-ttu-id="f2eef-107">通常，请考虑要部署的站点的类型和数量及其地理位置、每个站点的呼叫量、连接站点的网络链接类型、是否要为每个站点的语音功能提供冗余和故障转移，以及是否要使用现有 PBX 设备。</span><span class="sxs-lookup"><span data-stu-id="f2eef-107">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="f2eef-108">规划整个 Skype for Business Server 时应考虑某些注意事项，例如高可用性。</span><span class="sxs-lookup"><span data-stu-id="f2eef-108">There are certain considerations, such as high availability, that you should consider when you plan for Skype for Business Server as a whole.</span></span> <span data-ttu-id="f2eef-109">根据需要，本节中的主题将讨论这些注意事项。</span><span class="sxs-lookup"><span data-stu-id="f2eef-109">These considerations are discussed in topics throughout this section, as needed.</span></span>
  
## <a name="sites-and-regions"></a><span data-ttu-id="f2eef-110">站点和地区</span><span class="sxs-lookup"><span data-stu-id="f2eef-110">Sites and regions</span></span>

<span data-ttu-id="f2eef-111">首先，在拓扑中标识要部署企业语音的站点以及这些站点所属的网络区域。</span><span class="sxs-lookup"><span data-stu-id="f2eef-111">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="f2eef-112">特别是，考虑如何将公用电话交换网 (PSTN) 连接到每个站点。</span><span class="sxs-lookup"><span data-stu-id="f2eef-112">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="f2eef-113">由于可管理性和物流方面的原因，这些站点所属的区域可能是一个决定性因素。</span><span class="sxs-lookup"><span data-stu-id="f2eef-113">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="f2eef-114">确定将在本地部署网关、部署 Survivable Branch Appliances (SBA) 以及在本地或中央站点 (配置 SIP 中继) 到 Internet 电话服务提供商 (ITSP) 。</span><span class="sxs-lookup"><span data-stu-id="f2eef-114">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>
  
## <a name="network-links-between-sites"></a><span data-ttu-id="f2eef-115">站点之间的网络链接</span><span class="sxs-lookup"><span data-stu-id="f2eef-115">Network links between sites</span></span>

<span data-ttu-id="f2eef-116">您还需要考虑中央站点及其分支站点之间的网络链路上预计的带宽使用量。</span><span class="sxs-lookup"><span data-stu-id="f2eef-116">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="f2eef-117">如果您有或计划部署站点之间的可恢复 WAN 链路，我们建议您在每个分支站点部署网关，为这些站点中的用户提供本地外线直拨 (DID) 终止。</span><span class="sxs-lookup"><span data-stu-id="f2eef-117">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="f2eef-118">如果具有可恢复 WAN 链路，但 WAN 链路上的带宽可能被限定，则需要为该链路配置呼叫允许控制。</span><span class="sxs-lookup"><span data-stu-id="f2eef-118">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="f2eef-119">如果没有可恢复的 WAN 链路，分支站点上承载的用户少于 1000，并且没有本地经过培训的 Skype for Business Server 管理员，我们建议您在分支站点部署 Survivable Branch Appliance。</span><span class="sxs-lookup"><span data-stu-id="f2eef-119">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="f2eef-120">如果你在分支站点托管 1000 到 5000 个用户，缺少可恢复的 WAN 连接，并且有经过培训的 Skype for Business Server 管理员可用，我们建议您在分支站点部署具有小网关的 Survivable Branch Server。</span><span class="sxs-lookup"><span data-stu-id="f2eef-120">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="f2eef-121">如果具有支持媒体旁路功能的对等网关，则也可以考虑在限定链路上启用媒体旁路功能。</span><span class="sxs-lookup"><span data-stu-id="f2eef-121">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>
  
## <a name="estimating-voice-usage-and-traffic"></a><span data-ttu-id="f2eef-122">估计语音使用和流量</span><span class="sxs-lookup"><span data-stu-id="f2eef-122">Estimating voice usage and traffic</span></span>

<span data-ttu-id="f2eef-123">Microsoft Lync Server 2013 规划工具使用下列指标来估计每个站点上的用户流量以及支持该流量所需的端口数。</span><span class="sxs-lookup"><span data-stu-id="f2eef-123">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="f2eef-124">对于 **低流量**（每个用户每小时一个 PSTN 呼叫），每个端口对应 15 个用户。</span><span class="sxs-lookup"><span data-stu-id="f2eef-124">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="f2eef-125">对于 **中等流量**（每个用户每小时 2 个 PSTN 呼叫），每个端口对应 10 个用户。</span><span class="sxs-lookup"><span data-stu-id="f2eef-125">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="f2eef-126">对于 **高流量**（每个用户每小时 3 个或更多 PSTN 呼叫），每个端口对应 5 个用户。</span><span class="sxs-lookup"><span data-stu-id="f2eef-126">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="f2eef-127">端口数反过来决定所需的中介服务器和网关的数量。</span><span class="sxs-lookup"><span data-stu-id="f2eef-127">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="f2eef-128">公用电话交换网 (PSTN) 网关，大多数组织都考虑部署大小范围从 2 个端口到最多 960 个端口。</span><span class="sxs-lookup"><span data-stu-id="f2eef-128">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="f2eef-129"> (还有更大的网关，但这些网关主要由电话服务提供商使用。) </span><span class="sxs-lookup"><span data-stu-id="f2eef-129">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="f2eef-p106">例如，具有 10,000 个用户和中等流量的组织将需要 1000 个端口。所需的网关数等于所需的端口总数，由网关的总容量决定。</span><span class="sxs-lookup"><span data-stu-id="f2eef-p106">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  
## <a name="components-features-and-options-of-enterprise-voice"></a><span data-ttu-id="f2eef-132">应用程序的组件、功能和企业语音</span><span class="sxs-lookup"><span data-stu-id="f2eef-132">Components, features, and options of Enterprise Voice</span></span>

<span data-ttu-id="f2eef-133">有关规划部署部署企业语音部分。</span><span class="sxs-lookup"><span data-stu-id="f2eef-133">See the following sections for more information on planning your Enterprise Voice deployment.</span></span>
  
- [<span data-ttu-id="f2eef-134">Skype for Business Server 企业语音所需的组件</span><span class="sxs-lookup"><span data-stu-id="f2eef-134">Components required for Enterprise Voice in Skype for Business Server</span></span>](components-required-for-enterprise-voice.md)
    
- [<span data-ttu-id="f2eef-135">在 Skype for Business Server 中规划 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="f2eef-135">Plan for PSTN connectivity in Skype for Business Server</span></span>](pstn-connectivity-0.md)
    
- [<span data-ttu-id="f2eef-136">Skype for Business Server 中高级企业语音功能的网络设置</span><span class="sxs-lookup"><span data-stu-id="f2eef-136">Network settings for the advanced Enterprise Voice features in Skype for Business Server</span></span>](network-settings-for-advanced-features.md)
    
- [<span data-ttu-id="f2eef-137">在 Skype for Business Server 中规划呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="f2eef-137">Plan for call admission control in Skype for Business Server</span></span>](call-admission-control.md)
    
- [<span data-ttu-id="f2eef-138">在 Skype for Business Server 中规划紧急服务</span><span class="sxs-lookup"><span data-stu-id="f2eef-138">Plan for emergency services in Skype for Business Server</span></span>](emergency-services.md)
    
- [<span data-ttu-id="f2eef-139">在 Skype for Business 中规划媒体旁路</span><span class="sxs-lookup"><span data-stu-id="f2eef-139">Plan for media bypass in Skype for Business</span></span>](media-bypass.md)
    
- [<span data-ttu-id="f2eef-140">使用 Skype for Business 规划专用电话线路</span><span class="sxs-lookup"><span data-stu-id="f2eef-140">Plan for private telephone lines with Skype for Business</span></span>](private-telephone-lines.md)
    
- [<span data-ttu-id="f2eef-141">在 Skype for Business Location-Based路由计划</span><span class="sxs-lookup"><span data-stu-id="f2eef-141">Plan for Location-Based Routing in Skype for Business</span></span>](location-based-routing.md)
    
- [<span data-ttu-id="f2eef-142">在 Skype for Business 中规划呼叫管理功能</span><span class="sxs-lookup"><span data-stu-id="f2eef-142">Plan for call management features in Skype for Business</span></span>](call-management-features.md)
    
- [<span data-ttu-id="f2eef-143">规划 skype for Business Server 企业语音恢复能力</span><span class="sxs-lookup"><span data-stu-id="f2eef-143">Plan for Enterprise Voice resiliency in Skype for Business Server</span></span>](enterprise-voice-resiliency.md)
    

