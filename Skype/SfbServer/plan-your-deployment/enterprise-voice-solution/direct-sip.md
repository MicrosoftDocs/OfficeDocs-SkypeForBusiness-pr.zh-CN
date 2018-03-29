---
title: Skype for Business Server 2015 中的直接 SIP 连接
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: Skype 的业务服务器并同时 PSTN 网关之间的 IP-PBX 中企业语音支持的 SIP 的直接连接。
ms.openlocfilehash: 36b549b20708f0f9b09b8aeadf6f4197b9de1371
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="direct-sip-connections-in-skype-for-business-server-2015"></a><span data-ttu-id="a38bc-103">Skype for Business Server 2015 中的直接 SIP 连接</span><span class="sxs-lookup"><span data-stu-id="a38bc-103">Direct SIP connections in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a38bc-104">Skype 的业务服务器并同时 PSTN 网关之间的 IP-PBX 中企业语音支持的 SIP 的直接连接。</span><span class="sxs-lookup"><span data-stu-id="a38bc-104">Direct SIP connections are supported between Skype for Business Server and both PSTN gateways and IP-PBX in Enterprise Voice.</span></span>
  
<span data-ttu-id="a38bc-105">直接的 SIP 连接可用于将 Skype 业务服务器连接到以下任一项：</span><span class="sxs-lookup"><span data-stu-id="a38bc-105">You can use direct SIP connections to connect Skype for Business Server to either of the following:</span></span>
  
- <span data-ttu-id="a38bc-106">IP PBX</span><span class="sxs-lookup"><span data-stu-id="a38bc-106">An IP-PBX</span></span> 
    
- <span data-ttu-id="a38bc-107">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="a38bc-107">A PSTN gateway</span></span>
    
<span data-ttu-id="a38bc-108">若要实现 SIP 直接连接，请那样实现 SIP 中继按照实质上相同的部署步骤。</span><span class="sxs-lookup"><span data-stu-id="a38bc-108">To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk.</span></span> <span data-ttu-id="a38bc-109">在这两种情况下，您将使用中介服务器的外部接口实现连接。</span><span class="sxs-lookup"><span data-stu-id="a38bc-109">In both cases, you implement the connection by using the external interface of a Mediation Server.</span></span> <span data-ttu-id="a38bc-110">唯一的区别是，将 SIP 中继连接到外部实体，例如 ITSP 网关，并在您的本地网络，如 IP PBX 或公用交换的电话网络 (PSTN) 网关连接到内部实体直接 SIP 连接。</span><span class="sxs-lookup"><span data-stu-id="a38bc-110">The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.</span></span>
  
## <a name="direct-sip-deployment-options"></a><span data-ttu-id="a38bc-111">直接 SIP 部署选项</span><span class="sxs-lookup"><span data-stu-id="a38bc-111">Direct SIP deployment options</span></span>

### <a name="skype-for-business-server-stand-alone"></a><span data-ttu-id="a38bc-112">Skype 业务服务器独立</span><span class="sxs-lookup"><span data-stu-id="a38bc-112">Skype for Business Server Stand-Alone</span></span>
<span data-ttu-id="a38bc-113"><a name="BKMK_CommunicationsServerStand-Alone"> </a></span><span class="sxs-lookup"><span data-stu-id="a38bc-113"></span></span>

<span data-ttu-id="a38bc-114">如果您的组织使用一种部署在这一节中所述，可以为业务服务器使用 Skype，作为部分或全部的组织的唯一电话服务解决方案。</span><span class="sxs-lookup"><span data-stu-id="a38bc-114">If your organization uses one of the deployments described in this section, you can use Skype for Business Server as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="a38bc-115">本部分介绍以下详细部署：</span><span class="sxs-lookup"><span data-stu-id="a38bc-115">This section describes the following deployments in detail:</span></span>
  
- <span data-ttu-id="a38bc-116">**增量部署：**此选项假定您拥有现有的专用分组交换机 (PBX) 基础结构，并打算向较小的团队或组织内的团队逐步引入企业语音。</span><span class="sxs-lookup"><span data-stu-id="a38bc-116">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>
    
- <span data-ttu-id="a38bc-117">**仅 VoIP 部署：**此选项假定您正在考虑部署地点没有传统的电话服务基础结构的企业语音。</span><span class="sxs-lookup"><span data-stu-id="a38bc-117">**VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>
    
#### <a name="incremental-deployment"></a><span data-ttu-id="a38bc-118">增量部署</span><span class="sxs-lookup"><span data-stu-id="a38bc-118">Incremental Deployment</span></span>

<span data-ttu-id="a38bc-119">在增量部署中，Skype 业务服务器的唯一电话服务解决方案的各个小组或部门，而余下的组织中的用户继续使用 PBX。</span><span class="sxs-lookup"><span data-stu-id="a38bc-119">In incremental deployment, Skype for Business Server is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="a38bc-120">此增量部署策略提供 IP 电话服务中引入通过控制试点企业的一种方法。</span><span class="sxs-lookup"><span data-stu-id="a38bc-120">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="a38bc-121">在其他用户保持在现有的 PBX，其通信需求被最好地满足由 Microsoft 统一通信工作组被移动到企业语音。</span><span class="sxs-lookup"><span data-stu-id="a38bc-121">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="a38bc-122">根据需要可以到企业语音迁移其他工作组。</span><span class="sxs-lookup"><span data-stu-id="a38bc-122">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>
  
<span data-ttu-id="a38bc-123">增量同步选项建议如果您具备明确定义用户组，有常用和通信要求同样适用于集中式管理。</span><span class="sxs-lookup"><span data-stu-id="a38bc-123">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="a38bc-124">此选项也是有效的如果您有工作组或部门的分布过宽的地理区域，在长途费用节约非常显著。</span><span class="sxs-lookup"><span data-stu-id="a38bc-124">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="a38bc-125">事实上，此选项可用于创建虚拟团队，其成员可能分散在全球各地。</span><span class="sxs-lookup"><span data-stu-id="a38bc-125">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="a38bc-126">您可以创建、 修改或 disband 中对移动业务需求的快速响应这类小组。</span><span class="sxs-lookup"><span data-stu-id="a38bc-126">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>
  
<span data-ttu-id="a38bc-127">下图显示了部署的企业语音交换机的一般拓扑。</span><span class="sxs-lookup"><span data-stu-id="a38bc-127">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="a38bc-128">这是建议的拓扑结构进行增量部署。</span><span class="sxs-lookup"><span data-stu-id="a38bc-128">This is the recommended topology for incremental deployment.</span></span>
  
<span data-ttu-id="a38bc-129">**增量部署选项**</span><span class="sxs-lookup"><span data-stu-id="a38bc-129">**Incremental deployment option**</span></span>

![部门迁移选项图](../../media/Fig28_Departmental_migration_option.jpg)
  
> [!NOTE]
> <span data-ttu-id="a38bc-131">如果连接到直接 SIP 认证合作伙伴的您 Skype 业务服务器部署，则不需要中介服务器和 PBX 之间的公用交换的电话网络 (PSTN) 网关。</span><span class="sxs-lookup"><span data-stu-id="a38bc-131">If you are connecting your Skype for Business Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="a38bc-132">经认证的直接 SIP 的合作伙伴的列表，请参阅[Microsoft 统一通信开放互操作性计划](https://go.microsoft.com/fwlink/p/?linkId=203309)。</span><span class="sxs-lookup"><span data-stu-id="a38bc-132">For a list of certified Direct SIP partners, see the  [Microsoft Unified Communications Open Interoperability Program](https://go.microsoft.com/fwlink/p/?linkId=203309).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a38bc-133">此图中所示的媒体路径有媒体回避启用 （推荐配置）。</span><span class="sxs-lookup"><span data-stu-id="a38bc-133">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="a38bc-134">如果您选择禁用媒体回避，媒体路径被经过中介服务器。</span><span class="sxs-lookup"><span data-stu-id="a38bc-134">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span> 
  
<span data-ttu-id="a38bc-135">在此拓扑中，所选的部门或工作组启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="a38bc-135">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="a38bc-136">PSTN 网关链接语音 (voip)-启用到 PBX 的工作组。</span><span class="sxs-lookup"><span data-stu-id="a38bc-136">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="a38bc-137">为企业语音，包括远程工作人员，启用了用户通过 IP 网络进行通信。</span><span class="sxs-lookup"><span data-stu-id="a38bc-137">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="a38bc-138">到 PSTN 和同事不启用了企业语音企业语音用户呼叫被路由到相应的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="a38bc-138">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="a38bc-139">从同事仍在 PBX 系统，或 PSTN 上的调用方调用路由到路由业务服务器转发到 Skype 呼叫 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="a38bc-139">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Skype for Business Server for routing.</span></span>
  
<span data-ttu-id="a38bc-140">有两种推荐的配置为连接到现有的 PBX 基础结构的互操作性的企业语音： 企业语音背后的 PBX 和企业语音 PBX 的前面。</span><span class="sxs-lookup"><span data-stu-id="a38bc-140">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>
  
#### <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="a38bc-141">PBX 后面的企业语音</span><span class="sxs-lookup"><span data-stu-id="a38bc-141">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="a38bc-142">企业语音在部署时在 PBX 后面，所有从 PSTN 呼叫到达 PBX，这将对企业语音用户的呼叫路由到 PSTN 网关，并向到 PBX 的 PBX 用户呼叫。</span><span class="sxs-lookup"><span data-stu-id="a38bc-142">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span> 
  
#### <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="a38bc-143">在 PBX 企业语音</span><span class="sxs-lookup"><span data-stu-id="a38bc-143">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="a38bc-144">企业语音在部署时 PBX 的前面，所有调用将都到达 PSTN 网关的路由业务服务器和 PBX 的 PBX 用户调用调用企业语音 Skype 用户。</span><span class="sxs-lookup"><span data-stu-id="a38bc-144">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Skype for Business Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="a38bc-145">来自企业语音和 PBX 用户到 PSTN 呼叫被路由到最经济高效的 PSTN 网关在 IP 网络上。</span><span class="sxs-lookup"><span data-stu-id="a38bc-145">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="a38bc-146">下表显示了此配置的优缺点。</span><span class="sxs-lookup"><span data-stu-id="a38bc-146">The following table shows the advantages and disadvantages of this configuration.</span></span>
  
<span data-ttu-id="a38bc-147">**部署前 PBX 的企业语音的优点和缺点**</span><span class="sxs-lookup"><span data-stu-id="a38bc-147">**Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX**</span></span>

|<span data-ttu-id="a38bc-148">**优势**</span><span class="sxs-lookup"><span data-stu-id="a38bc-148">**Advantages**</span></span>|<span data-ttu-id="a38bc-149">**缺点**</span><span class="sxs-lookup"><span data-stu-id="a38bc-149">**Disadvantages**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a38bc-150">PBX 仍是用户不能启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="a38bc-150">PBX still serves users not enabled for Enterprise Voice.</span></span>  <br/> |<span data-ttu-id="a38bc-151">现有的网关可能不支持的功能或所需的容量。</span><span class="sxs-lookup"><span data-stu-id="a38bc-151">Existing gateways may not support the features or capacity that you want.</span></span>  <br/> |
|<span data-ttu-id="a38bc-152">PBX 处理所有早期的设备。</span><span class="sxs-lookup"><span data-stu-id="a38bc-152">PBX handles all earlier devices.</span></span>  <br/> |<span data-ttu-id="a38bc-153">要求从到 PBX 的网关和网关中介服务器的主干。</span><span class="sxs-lookup"><span data-stu-id="a38bc-153">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="a38bc-154">您可能需要多个中继服务供应商。</span><span class="sxs-lookup"><span data-stu-id="a38bc-154">You may need more trunks from the service provider.</span></span>  <br/> |
|<span data-ttu-id="a38bc-155">企业语音用户保留相同的电话号码。</span><span class="sxs-lookup"><span data-stu-id="a38bc-155">Enterprise Voice users keep the same phone numbers.</span></span>  <br/> | <br/> |
   
#### <a name="voip-only-deployment"></a><span data-ttu-id="a38bc-156">仅 VoIP 部署</span><span class="sxs-lookup"><span data-stu-id="a38bc-156">VoIP-Only Deployment</span></span>

<span data-ttu-id="a38bc-157">企业语音提供新创办的企业，以及新的办公地点，对于现有的企业来说，实施全面的 VoIP 解决方案，而无需担心 PBX 集成或招致的重大部署和维护的机会IP PBX 基础结构的成本。</span><span class="sxs-lookup"><span data-stu-id="a38bc-157">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="a38bc-158">此解决方案支持现场和远程工作人员。</span><span class="sxs-lookup"><span data-stu-id="a38bc-158">This solution supports both on-site and remote workers.</span></span>
  
<span data-ttu-id="a38bc-159">在该部署中，所有呼叫通过 IP 网络都路由。</span><span class="sxs-lookup"><span data-stu-id="a38bc-159">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="a38bc-160">到 PSTN 呼叫被路由到相应的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="a38bc-160">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="a38bc-161">Skype 业务或 Lync 电话版作为软电话。</span><span class="sxs-lookup"><span data-stu-id="a38bc-161">Skype for Business or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="a38bc-162">远程呼叫控制是不可用且不必要，因为有没有 PBX 电话用户控制。</span><span class="sxs-lookup"><span data-stu-id="a38bc-162">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="a38bc-163">语音邮件和自动助理服务都可以通过可选的部署的 Exchange 统一消息 (UM)。</span><span class="sxs-lookup"><span data-stu-id="a38bc-163">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a38bc-164">除了支持 Skype 业务服务器所需的网络基础结构，只有 VoIP 部署可以使用小的、 合格的网关支持传真机和模拟设备。</span><span class="sxs-lookup"><span data-stu-id="a38bc-164">In addition to the network infrastructure that is required to support Skype for Business Server, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span> 
  
<span data-ttu-id="a38bc-165">下图显示了典型仅 VoIP 的部署拓扑。</span><span class="sxs-lookup"><span data-stu-id="a38bc-165">The following figure shows a typical topology for a VoIP-only deployment.</span></span>
  
<span data-ttu-id="a38bc-166">**仅 VoIP 部署选项**</span><span class="sxs-lookup"><span data-stu-id="a38bc-166">**VoIP-only deployment option**</span></span>

![绿场部署选项](../../media/Fig29_Greenfield_deployment_option.jpg)
  
> [!NOTE]
> <span data-ttu-id="a38bc-168">此图中所示的媒体路径有媒体回避启用 （推荐配置）。</span><span class="sxs-lookup"><span data-stu-id="a38bc-168">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="a38bc-169">如果您选择禁用媒体回避，媒体路径被经过中介服务器。</span><span class="sxs-lookup"><span data-stu-id="a38bc-169">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span> 
  
## <a name="pstn-gateway-deployment-options"></a><span data-ttu-id="a38bc-170">PSTN 网关部署选项</span><span class="sxs-lookup"><span data-stu-id="a38bc-170">PSTN Gateway deployment options</span></span>

### <a name="pstn-gateways"></a><span data-ttu-id="a38bc-171">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="a38bc-171">PSTN Gateways</span></span>

<span data-ttu-id="a38bc-172">公用交换的电话网络 (PSTN) 网关是翻译信号和媒体之间的企业语音基础结构和 PSTN，直接或通过连接到 SIP 中继的第三方硬件组件。</span><span class="sxs-lookup"><span data-stu-id="a38bc-172">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="a38bc-173">在任何拓扑中，网关将终止 PSTN。</span><span class="sxs-lookup"><span data-stu-id="a38bc-173">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="a38bc-174">网关隔离在其自己的子网，并连接到企业网络，通过中介服务器。</span><span class="sxs-lookup"><span data-stu-id="a38bc-174">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>
  
<span data-ttu-id="a38bc-175">具有多个站点的企业通常会部署在每个站点的一个或多个网关。</span><span class="sxs-lookup"><span data-stu-id="a38bc-175">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="a38bc-176">分支站点可以连接到 PSTN 网关，通过或高存活力的分支装置，结合了网关和服务器在一台机器。</span><span class="sxs-lookup"><span data-stu-id="a38bc-176">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="a38bc-177">如果分支站点使用网关，一个注册商和中介服务器需要在网站上，除非在 WAN 链接发生弹性。</span><span class="sxs-lookup"><span data-stu-id="a38bc-177">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="a38bc-178">一个或多个中介服务器，搭配在前端服务器，可以将调用的一个或多个网关路由在每个站点。</span><span class="sxs-lookup"><span data-stu-id="a38bc-178">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="a38bc-179">我们建议，作为高存活力的分支应用装置部署注册、 中介服务器和站点上所需的网关。</span><span class="sxs-lookup"><span data-stu-id="a38bc-179">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>
  
<span data-ttu-id="a38bc-180">确定的数量、 大小和位置的 PSTN 网关可能是最重要和最高决策规划企业语音基础结构时必须执行的。</span><span class="sxs-lookup"><span data-stu-id="a38bc-180">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span> 
  
<span data-ttu-id="a38bc-181">以下是需要考虑的主要问题。</span><span class="sxs-lookup"><span data-stu-id="a38bc-181">Here are the main questions to consider.</span></span> <span data-ttu-id="a38bc-182">请记住，这些问题的答案是所有相互依赖</span><span class="sxs-lookup"><span data-stu-id="a38bc-182">Keep in mind that the answers to these questions are all interdependent</span></span>
  
- <span data-ttu-id="a38bc-183">需要多少 PSTN 网关？</span><span class="sxs-lookup"><span data-stu-id="a38bc-183">How many PSTN gateways are needed?</span></span> <span data-ttu-id="a38bc-184">答案取决于用户数、 预期的同时调用 （通信负载），数量和站点 （每个站点需要一个） 的数目。</span><span class="sxs-lookup"><span data-stu-id="a38bc-184">The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>
    
- <span data-ttu-id="a38bc-185">网关应为有多大？</span><span class="sxs-lookup"><span data-stu-id="a38bc-185">What size should the gateways be?</span></span> <span data-ttu-id="a38bc-186">答案取决于站点上的用户数和通信负载。</span><span class="sxs-lookup"><span data-stu-id="a38bc-186">The answer depends on the number of users at the site and on the traffic load.</span></span>
    
- <span data-ttu-id="a38bc-187">在网关应位于？</span><span class="sxs-lookup"><span data-stu-id="a38bc-187">Where should the gateways be located?</span></span> <span data-ttu-id="a38bc-188">答案取决于部分在拓扑结构上以及部分组织的地理分布。</span><span class="sxs-lookup"><span data-stu-id="a38bc-188">The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>
    
 <span data-ttu-id="a38bc-189">此外应考虑您的网关拓扑选项 （有关详细信息，请参阅网关拓扑在本主题后面）。</span><span class="sxs-lookup"><span data-stu-id="a38bc-189">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>
  
#### <a name="mn-trunk-support"></a><span data-ttu-id="a38bc-190">M:N 中继支持</span><span class="sxs-lookup"><span data-stu-id="a38bc-190">M:N Trunk Support</span></span>

<span data-ttu-id="a38bc-191">中介服务器可以发送多个网关，会话边框控制器 (SBCs) 通过调用提供的互联网电话服务提供程序或二者的组合。</span><span class="sxs-lookup"><span data-stu-id="a38bc-191">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="a38bc-192">此外，在池中的多个中介服务器可以与多个网关进行交互。</span><span class="sxs-lookup"><span data-stu-id="a38bc-192">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="a38bc-193">逻辑定义中介服务器和网关之间的路由称为主干。</span><span class="sxs-lookup"><span data-stu-id="a38bc-193">The logical route defined between a Mediation Server and gateway is called a trunk.</span></span> <span data-ttu-id="a38bc-194">当内部用户发出 PSTN 呼叫时，前端池上的出站路由逻辑选择通过传送出可能适用于该特定呼叫路由的所有可能组合的干线。</span><span class="sxs-lookup"><span data-stu-id="a38bc-194">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="a38bc-195">利用 DNS 负载平衡，如果调用未能到达网关是池中的特定的中介服务器问题呼叫将重试池中备用的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="a38bc-195">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span> 
  
<span data-ttu-id="a38bc-196">规划多个网关的详细信息，请参阅[在业务服务器 2015年的 Skype 的 M:N 干线](m-n-trunk.md)。</span><span class="sxs-lookup"><span data-stu-id="a38bc-196">For details about planning for multiple gateways, see [M:N trunk in Skype for Business Server 2015](m-n-trunk.md).</span></span>
  
<span data-ttu-id="a38bc-197">有关其他出站路由增强功能的详细信息，请参见[调用路由](http://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a38bc-197">For details about other outbound routing enhancements, see [Call Routes](http://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx).</span></span>
  
#### <a name="gateway-topologies"></a><span data-ttu-id="a38bc-198">网关拓扑</span><span class="sxs-lookup"><span data-stu-id="a38bc-198">Gateway Topologies</span></span>

<span data-ttu-id="a38bc-199">当考虑网关部署的基本问题时，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a38bc-199">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>
  
1. <span data-ttu-id="a38bc-200">您要通过使用企业语音提供的 PSTN 连接性的站点进行计数。</span><span class="sxs-lookup"><span data-stu-id="a38bc-200">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>
    
2. <span data-ttu-id="a38bc-201">估计在每个站点 （用户数） 和平均每用户每小时的调用次数的通信。</span><span class="sxs-lookup"><span data-stu-id="a38bc-201">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>
    
3. <span data-ttu-id="a38bc-202">部署在每个站点来处理预期的通信量的一个或多个网关。</span><span class="sxs-lookup"><span data-stu-id="a38bc-202">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>
    
<span data-ttu-id="a38bc-203">使用此拓扑中，工作人员在每个站点和站点间之间的调用所有经过在 intranet 上。</span><span class="sxs-lookup"><span data-stu-id="a38bc-203">With this topology, calls among workers at each site and between sites are all routed over your intranet.</span></span> <span data-ttu-id="a38bc-204">通过将目标数字的位置最接近的网关的企业 IP 网络路由到 PSTN 呼叫。但如果您的组织支持数十个或数百个或甚至数千个站点分布在一个或多个大洲，与许多金融机构和其它大型企业的？</span><span class="sxs-lookup"><span data-stu-id="a38bc-204">Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do?</span></span> <span data-ttu-id="a38bc-205">在这种情况下，部署在每个站点的单独的网关并不可行。</span><span class="sxs-lookup"><span data-stu-id="a38bc-205">In such cases, deploying a separate gateway at each site is not practical.</span></span>
  
<span data-ttu-id="a38bc-206">若要解决此问题，很多大公司想部署一个或几个大的电话中心站点。</span><span class="sxs-lookup"><span data-stu-id="a38bc-206">To address this issue, many large companies prefer to deploy one or a few large telephony central sites.</span></span>
  
<span data-ttu-id="a38bc-207">在此拓扑中，每一个中心站点部署不足以容纳预期的用户负载多大网关。</span><span class="sxs-lookup"><span data-stu-id="a38bc-207">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="a38bc-208">对企业中的用户的所有调用都转发到中央站点的公司的电话服务提供商。</span><span class="sxs-lookup"><span data-stu-id="a38bc-208">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="a38bc-209">中心站点的路由逻辑确定呼叫是否应通过内联网或 PSTN 路由。</span><span class="sxs-lookup"><span data-stu-id="a38bc-209">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>
  
#### <a name="gateway-location"></a><span data-ttu-id="a38bc-210">网关的位置</span><span class="sxs-lookup"><span data-stu-id="a38bc-210">Gateway Location</span></span>

<span data-ttu-id="a38bc-211">网关的位置也可能会确定网关选择和配置方式的类型。</span><span class="sxs-lookup"><span data-stu-id="a38bc-211">Gateway location may also determine the types of gateways that you choose and how they are configured.</span></span> <span data-ttu-id="a38bc-212">有许多的 PSTN 协议，都不是一种全球标准。</span><span class="sxs-lookup"><span data-stu-id="a38bc-212">There are dozens of PSTN protocols, none of which is a worldwide standard.</span></span> <span data-ttu-id="a38bc-213">如果所有的网关位于单个国家/地区中，这不是问题，但如果在多个国家/地区找到网关，必须将每个配置根据该国家/地区的 PSTN 标准。</span><span class="sxs-lookup"><span data-stu-id="a38bc-213">If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region.</span></span> <span data-ttu-id="a38bc-214">此外，网关的认证，例如加拿大的操作中，不可能在印度、 巴西或欧盟认证。</span><span class="sxs-lookup"><span data-stu-id="a38bc-214">Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>
  
#### <a name="gateway-size-and-number"></a><span data-ttu-id="a38bc-215">网关的大小和数量</span><span class="sxs-lookup"><span data-stu-id="a38bc-215">Gateway Size and Number</span></span>

<span data-ttu-id="a38bc-216">大多数组织将考虑部署范围的大小从 2 到多达 960 端口 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="a38bc-216">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports.</span></span> <span data-ttu-id="a38bc-217">（有更大的网关，但这些都主要由电话服务提供商）。在估计您组织所需的端口数，可使用以下准则：</span><span class="sxs-lookup"><span data-stu-id="a38bc-217">(There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>
  
- <span data-ttu-id="a38bc-218">光的电话使用率 （一个 PSTN 呼叫每个用户每小时） 的组织应为每个 15 个用户分配一个端口。</span><span class="sxs-lookup"><span data-stu-id="a38bc-218">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users.</span></span> <span data-ttu-id="a38bc-219">例如，如果您有 20 个用户，您将需要两个端口的网关。</span><span class="sxs-lookup"><span data-stu-id="a38bc-219">For example, if you have 20 users, you will require a gateway with two ports.</span></span>
    
- <span data-ttu-id="a38bc-220">具有中等电话使用情况 （两个 PSTN 呼叫每个用户每小时） 的组织应为每 10 个用户分配一个端口。</span><span class="sxs-lookup"><span data-stu-id="a38bc-220">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users.</span></span> <span data-ttu-id="a38bc-221">例如，如果您有 100 个用户，您将需要总共 10 个端口分配一个或多个网关之间。</span><span class="sxs-lookup"><span data-stu-id="a38bc-221">For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>
    
- <span data-ttu-id="a38bc-222">繁重的电话使用率 （三个或更多 PSTN 呼叫每个用户每小时） 的组织应为每次五个用户分配一个端口。</span><span class="sxs-lookup"><span data-stu-id="a38bc-222">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users.</span></span> <span data-ttu-id="a38bc-223">例如，如果您有 47000 个用户，您将需要总共至少 10 个大网关之间分配 9,400 端口。</span><span class="sxs-lookup"><span data-stu-id="a38bc-223">For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>
    
- <span data-ttu-id="a38bc-224">其他端口还可以获得为用户数或在您的组织增加的通讯量。</span><span class="sxs-lookup"><span data-stu-id="a38bc-224">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>
    
<span data-ttu-id="a38bc-225">对于任何给定必须支持的用户数，必须部署更少、 更大的网关或较小的选择。</span><span class="sxs-lookup"><span data-stu-id="a38bc-225">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones.</span></span> <span data-ttu-id="a38bc-226">一般来说，建议最少的为组织的两个网关一个网关失败时保持可用性。</span><span class="sxs-lookup"><span data-stu-id="a38bc-226">As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span> 
  
<span data-ttu-id="a38bc-227">在部署每个 PSTN 网关必须有至少一个相应的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="a38bc-227">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>
  

