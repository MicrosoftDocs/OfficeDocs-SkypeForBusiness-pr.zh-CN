---
title: Skype for Business Server 中的直接 SIP 连接
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
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: Skype for Business Server 与 PSTN 网关和 IP-PBX 之间的直接 SIP 连接在 企业语音。
ms.openlocfilehash: 7a70a6f3afd303ef5847993240b26b47d1b4ceac
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096412"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a><span data-ttu-id="cc957-103">Skype for Business Server 中的直接 SIP 连接</span><span class="sxs-lookup"><span data-stu-id="cc957-103">Direct SIP connections in Skype for Business Server</span></span>

<span data-ttu-id="cc957-104">Skype for Business Server 与 PSTN 网关和 IP-PBX 之间的直接 SIP 连接在 企业语音。</span><span class="sxs-lookup"><span data-stu-id="cc957-104">Direct SIP connections are supported between Skype for Business Server and both PSTN gateways and IP-PBX in Enterprise Voice.</span></span>

<span data-ttu-id="cc957-105">可以使用直接 SIP 连接将 Skype for Business Server 连接到以下任一项：</span><span class="sxs-lookup"><span data-stu-id="cc957-105">You can use direct SIP connections to connect Skype for Business Server to either of the following:</span></span>

- <span data-ttu-id="cc957-106">IP-PBX</span><span class="sxs-lookup"><span data-stu-id="cc957-106">An IP-PBX</span></span>

- <span data-ttu-id="cc957-107">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="cc957-107">A PSTN gateway</span></span>

<span data-ttu-id="cc957-108">要实现直接 SIP 连接，必须按照与实现 SIP 中继基本相同的部署步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="cc957-108">To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk.</span></span> <span data-ttu-id="cc957-109">在这两种情况下，都使用中介服务器的外部接口实现连接。</span><span class="sxs-lookup"><span data-stu-id="cc957-109">In both cases, you implement the connection by using the external interface of a Mediation Server.</span></span> <span data-ttu-id="cc957-110">唯一的区别是，应将 SIP 中继连接到外部实体，如 ITSP 网关，而将直接 SIP 连接连接到本地网络中的内部实体，如 IP-PBX 或公用电话交换网 (PSTN) 网关。</span><span class="sxs-lookup"><span data-stu-id="cc957-110">The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.</span></span>

## <a name="direct-sip-deployment-options"></a><span data-ttu-id="cc957-111">直接 SIP 部署选项</span><span class="sxs-lookup"><span data-stu-id="cc957-111">Direct SIP deployment options</span></span>

### <a name="skype-for-business-server-stand-alone"></a><span data-ttu-id="cc957-112">Skype for Business Server Stand-Alone</span><span class="sxs-lookup"><span data-stu-id="cc957-112">Skype for Business Server Stand-Alone</span></span>
<span data-ttu-id="cc957-113"><a name="BKMK_CommunicationsServerStand-Alone"> </a></span><span class="sxs-lookup"><span data-stu-id="cc957-113"><a name="BKMK_CommunicationsServerStand-Alone"> </a></span></span>

<span data-ttu-id="cc957-114">如果你的组织使用本节中所述的部署之一，可以使用 Skype for Business Server 作为部分或整个组织的唯一电话解决方案。</span><span class="sxs-lookup"><span data-stu-id="cc957-114">If your organization uses one of the deployments described in this section, you can use Skype for Business Server as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="cc957-115">本节详细介绍以下部署：</span><span class="sxs-lookup"><span data-stu-id="cc957-115">This section describes the following deployments in detail:</span></span>

- <span data-ttu-id="cc957-116">**增量部署：** 此选项假定您具有现有的专用交换机 (PBX) ，并且您打算将 企业语音逐步引入到组织中较小的组或团队。</span><span class="sxs-lookup"><span data-stu-id="cc957-116">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

- <span data-ttu-id="cc957-117">**仅 VoIP 部署** ：此选项假定您考虑企业语音电话基础结构的站点上部署网络。</span><span class="sxs-lookup"><span data-stu-id="cc957-117">**VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

#### <a name="incremental-deployment"></a><span data-ttu-id="cc957-118">增量部署</span><span class="sxs-lookup"><span data-stu-id="cc957-118">Incremental Deployment</span></span>

<span data-ttu-id="cc957-119">在增量部署中，Skype for Business Server 是单个团队或部门的唯一电话解决方案，而组织中其他用户继续使用 PBX。</span><span class="sxs-lookup"><span data-stu-id="cc957-119">In incremental deployment, Skype for Business Server is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="cc957-120">此增量部署策略提供了一种方法，通过受控试点计划将 IP 电话引入企业。</span><span class="sxs-lookup"><span data-stu-id="cc957-120">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="cc957-121">其通信需求由 Microsoft 统一通信最满足的工作组将移动到 企业语音，而其他用户仍保留在现有 PBX 上。</span><span class="sxs-lookup"><span data-stu-id="cc957-121">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="cc957-122">根据需要，可以将其他工作组企业语音迁移至其他工作组。</span><span class="sxs-lookup"><span data-stu-id="cc957-122">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="cc957-123">如果您明确定义了具有共同通信要求且适合集中管理的用户组，则建议使用增量选项。</span><span class="sxs-lookup"><span data-stu-id="cc957-123">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="cc957-124">如果你的团队或部门分布在广泛的地理区域，其中节省的长途费用可能很大，则此选项也有效。</span><span class="sxs-lookup"><span data-stu-id="cc957-124">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="cc957-125">事实上，此选项可用于创建其成员可能分散在全球的虚拟团队。</span><span class="sxs-lookup"><span data-stu-id="cc957-125">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="cc957-126">可以创建、修改或取消此类团队，以快速响应变化中的业务需求。</span><span class="sxs-lookup"><span data-stu-id="cc957-126">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="cc957-127">下图显示了在 PBX 后面部署 企业语音的常规拓扑。</span><span class="sxs-lookup"><span data-stu-id="cc957-127">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="cc957-128">这是建议用于增量部署的拓扑。</span><span class="sxs-lookup"><span data-stu-id="cc957-128">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="cc957-129">**增量部署选项**</span><span class="sxs-lookup"><span data-stu-id="cc957-129">**Incremental deployment option**</span></span>

![部门迁移选项图](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> <span data-ttu-id="cc957-131">如果要将 Skype for Business Server 部署连接到认证的直接 SIP 合作伙伴，则不需要中介服务器与 PBX 之间的公用电话交换网 (PSTN) 网关。</span><span class="sxs-lookup"><span data-stu-id="cc957-131">If you are connecting your Skype for Business Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="cc957-132">有关经认证的直接 SIP 合作伙伴的列表，请参阅  [Microsoft 统一通信开放式互操作性计划](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)。</span><span class="sxs-lookup"><span data-stu-id="cc957-132">For a list of certified Direct SIP partners, see the  [Microsoft Unified Communications Open Interoperability Program](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="cc957-133">此图中显示的媒体路径已启用媒体旁路 (推荐配置) 。</span><span class="sxs-lookup"><span data-stu-id="cc957-133">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="cc957-134">如果选择禁用媒体旁路，则媒体路径将通过中介服务器进行路由。</span><span class="sxs-lookup"><span data-stu-id="cc957-134">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>

<span data-ttu-id="cc957-135">在此拓扑中，选定的部门或工作组已启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="cc957-135">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="cc957-136">PSTN 网关将启用了 VoIP (的 VoIP) 语音连接到 PBX。</span><span class="sxs-lookup"><span data-stu-id="cc957-136">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="cc957-137">启用了远程企业语音包括远程工作者）通过 IP 网络进行通信。</span><span class="sxs-lookup"><span data-stu-id="cc957-137">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="cc957-138">用户企业语音 PSTN 和未启用 PSTN 的企业语音呼叫将路由到相应的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="cc957-138">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="cc957-139">来自仍在 PBX 系统的同事或 PSTN 上的呼叫者的呼叫将路由到 PSTN 网关，PSTN 网关将呼叫转发到 Skype for Business Server 进行路由。</span><span class="sxs-lookup"><span data-stu-id="cc957-139">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Skype for Business Server for routing.</span></span>

<span data-ttu-id="cc957-140">有两种建议的配置用于将 企业语音 连接到现有 PBX 基础结构实现互操作性：企业语音 PBX 后面，企业语音 PBX 前面。</span><span class="sxs-lookup"><span data-stu-id="cc957-140">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

#### <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="cc957-141">企业语音 PBX 后面</span><span class="sxs-lookup"><span data-stu-id="cc957-141">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="cc957-142">在 PBX 企业语音时，来自 PSTN 的所有呼叫将到达 PBX，PBX 将呼叫路由至 企业语音 用户到 PSTN 网关，而将 PBX 用户的呼叫路由到 PBX。</span><span class="sxs-lookup"><span data-stu-id="cc957-142">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

#### <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="cc957-143">企业语音 PBX 前面</span><span class="sxs-lookup"><span data-stu-id="cc957-143">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="cc957-144">当企业语音 PBX 之前部署呼叫时，所有呼叫都到达 PSTN 网关，PSTN 网关将 企业语音 用户的呼叫路由到 Skype for Business Server，PBX 用户的呼叫路由到 PBX。</span><span class="sxs-lookup"><span data-stu-id="cc957-144">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Skype for Business Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="cc957-145">来自用户和 PBX 用户企业语音 PSTN 的呼叫通过 IP 网络路由到最经济高效的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="cc957-145">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="cc957-146">下表显示了此配置的优缺点。</span><span class="sxs-lookup"><span data-stu-id="cc957-146">The following table shows the advantages and disadvantages of this configuration.</span></span>

<span data-ttu-id="cc957-147">**在 PBX 企业语音部署的优缺点**</span><span class="sxs-lookup"><span data-stu-id="cc957-147">**Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX**</span></span>

|<span data-ttu-id="cc957-148">**优点**</span><span class="sxs-lookup"><span data-stu-id="cc957-148">**Advantages**</span></span>|<span data-ttu-id="cc957-149">**缺点**</span><span class="sxs-lookup"><span data-stu-id="cc957-149">**Disadvantages**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc957-150">PBX 仍为未启用此功能企业语音。</span><span class="sxs-lookup"><span data-stu-id="cc957-150">PBX still serves users not enabled for Enterprise Voice.</span></span>  <br/> |<span data-ttu-id="cc957-151">现有网关可能不支持您需要的功能或容量。</span><span class="sxs-lookup"><span data-stu-id="cc957-151">Existing gateways may not support the features or capacity that you want.</span></span>  <br/> |
|<span data-ttu-id="cc957-152">PBX 处理所有早期设备。</span><span class="sxs-lookup"><span data-stu-id="cc957-152">PBX handles all earlier devices.</span></span>  <br/> |<span data-ttu-id="cc957-153">需要从网关到 PBX 以及从网关到中介服务器的中继。</span><span class="sxs-lookup"><span data-stu-id="cc957-153">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="cc957-154">您可能需要来自服务提供商的更多中继。</span><span class="sxs-lookup"><span data-stu-id="cc957-154">You may need more trunks from the service provider.</span></span>  <br/> |
|<span data-ttu-id="cc957-155">企业语音用户保留相同的电话号码。</span><span class="sxs-lookup"><span data-stu-id="cc957-155">Enterprise Voice users keep the same phone numbers.</span></span>  <br/> | <br/> |

#### <a name="voip-only-deployment"></a><span data-ttu-id="cc957-156">VoIP-Only部署</span><span class="sxs-lookup"><span data-stu-id="cc957-156">VoIP-Only Deployment</span></span>

<span data-ttu-id="cc957-157">企业语音 提供了新业务以及现有企业的新办公网站，从而有机会实现功能齐全的 VoIP 解决方案，而无需担心 PBX 集成或导致 IP-PBX 基础结构的大量部署和维护成本。</span><span class="sxs-lookup"><span data-stu-id="cc957-157">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="cc957-158">此解决方案支持现场和远程工作者。</span><span class="sxs-lookup"><span data-stu-id="cc957-158">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="cc957-159">在此部署中，所有呼叫均通过 IP 网络路由。</span><span class="sxs-lookup"><span data-stu-id="cc957-159">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="cc957-160">对 PSTN 的呼叫将路由到相应的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="cc957-160">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="cc957-161">Skype for Business 或 Lync Phone Edition 充当软电话。</span><span class="sxs-lookup"><span data-stu-id="cc957-161">Skype for Business or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="cc957-162">由于没有 PBX 电话可让用户控制，因此远程呼叫控制不可用且不必要。</span><span class="sxs-lookup"><span data-stu-id="cc957-162">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="cc957-163">语音邮件和自动助理服务通过可选的 Exchange 统一消息和 UM (部署) 。</span><span class="sxs-lookup"><span data-stu-id="cc957-163">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

> [!NOTE]
> <span data-ttu-id="cc957-164">除了支持 Skype for Business Server 所需的网络基础结构之外，仅 VoIP 部署可以使用小型合格网关来支持传真机和模拟设备。</span><span class="sxs-lookup"><span data-stu-id="cc957-164">In addition to the network infrastructure that is required to support Skype for Business Server, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>

<span data-ttu-id="cc957-165">下图显示了仅 VoIP 部署的典型拓扑。</span><span class="sxs-lookup"><span data-stu-id="cc957-165">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="cc957-166">**仅 VoIP 部署选项**</span><span class="sxs-lookup"><span data-stu-id="cc957-166">**VoIP-only deployment option**</span></span>

![绿色部署选项](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> <span data-ttu-id="cc957-168">此图中显示的媒体路径已启用媒体旁路 (推荐配置) 。</span><span class="sxs-lookup"><span data-stu-id="cc957-168">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="cc957-169">如果选择禁用媒体旁路，则媒体路径将通过中介服务器进行路由。</span><span class="sxs-lookup"><span data-stu-id="cc957-169">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>

## <a name="pstn-gateway-deployment-options"></a><span data-ttu-id="cc957-170">PSTN 网关部署选项</span><span class="sxs-lookup"><span data-stu-id="cc957-170">PSTN Gateway deployment options</span></span>

### <a name="pstn-gateways"></a><span data-ttu-id="cc957-171">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="cc957-171">PSTN Gateways</span></span>

<span data-ttu-id="cc957-172">公用电话交换网 (PSTN) 网关是第三方硬件组件，可直接或通过到 SIP 中继的连接转换企业语音基础结构和 PSTN 之间的信号和媒体。</span><span class="sxs-lookup"><span data-stu-id="cc957-172">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="cc957-173">在任一拓扑中，网关都终止 PSTN。</span><span class="sxs-lookup"><span data-stu-id="cc957-173">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="cc957-174">网关隔离在其自己的子网中，并通过中介服务器连接到企业网络。</span><span class="sxs-lookup"><span data-stu-id="cc957-174">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="cc957-175">具有多个站点的企业通常在每个站点部署一个或多个网关。</span><span class="sxs-lookup"><span data-stu-id="cc957-175">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="cc957-176">分支站点可以通过网关或 Survivable Branch Appliance 连接到 PSTN，该分支设备将网关和服务器组合在一个框中。</span><span class="sxs-lookup"><span data-stu-id="cc957-176">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="cc957-177">如果分支站点使用网关，则站点上需要注册器服务器和中介服务器，除非 WAN 链路具有弹性。</span><span class="sxs-lookup"><span data-stu-id="cc957-177">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="cc957-178">一个或多个并位于前端服务器的中介服务器可以路由每个站点上一个或多个网关的呼叫。</span><span class="sxs-lookup"><span data-stu-id="cc957-178">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="cc957-179">我们建议将站点上所需的注册器、中介服务器和网关部署为 Survivable Branch Appliance。</span><span class="sxs-lookup"><span data-stu-id="cc957-179">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="cc957-180">确定 PSTN 网关的数量、大小和位置可能是在规划 PSTN 基础结构时必须做出的最重要且企业语音决定。</span><span class="sxs-lookup"><span data-stu-id="cc957-180">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="cc957-p116">以下是需要考虑的主要问题。请记住，这些问题的答案都是相互依存的</span><span class="sxs-lookup"><span data-stu-id="cc957-p116">Here are the main questions to consider. Keep in mind that the answers to these questions are all interdependent</span></span>

- <span data-ttu-id="cc957-p117">需要多少个 PSTN 网关？答案取决于用户数量、预期的同时呼叫数（流量负载）以及站点数（每个站点需要一个）。</span><span class="sxs-lookup"><span data-stu-id="cc957-p117">How many PSTN gateways are needed? The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

- <span data-ttu-id="cc957-p118">网关应当为多大？答案取决于站点中的用户数以及流量负载。</span><span class="sxs-lookup"><span data-stu-id="cc957-p118">What size should the gateways be? The answer depends on the number of users at the site and on the traffic load.</span></span>

- <span data-ttu-id="cc957-p119">网关应当位于何处？答案部分取决于贵组织的拓扑和地理分布。</span><span class="sxs-lookup"><span data-stu-id="cc957-p119">Where should the gateways be located? The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

  <span data-ttu-id="cc957-189">还应该考虑网关拓扑选项（有关详细信息，请参阅本主题后面的“网关拓扑”）。</span><span class="sxs-lookup"><span data-stu-id="cc957-189">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

#### <a name="mn-trunk-support"></a><span data-ttu-id="cc957-190">M:N 中继支持</span><span class="sxs-lookup"><span data-stu-id="cc957-190">M:N Trunk Support</span></span>

<span data-ttu-id="cc957-191">中介服务器可以通过多个网关、会话边界控制器 (Internet) 服务提供商提供的 SDC 或两者的组合来路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="cc957-191">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="cc957-192">此外，池中的多个中介服务器可以与多个网关交互。</span><span class="sxs-lookup"><span data-stu-id="cc957-192">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="cc957-193">中介服务器和网关之间定义的逻辑路由称为中继。</span><span class="sxs-lookup"><span data-stu-id="cc957-193">The logical route defined between a Mediation Server and gateway is called a trunk.</span></span> <span data-ttu-id="cc957-194">当内部用户拨打 PSTN 呼叫时，前端池上的出站路由逻辑会从可用于路由该特定呼叫的所有可能的组合中选择要路由的中继。</span><span class="sxs-lookup"><span data-stu-id="cc957-194">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="cc957-195">通过 DNS 负载平衡，如果呼叫因池中特定中介服务器的问题而无法到达网关，则呼叫将重试池中的备用中介服务器。</span><span class="sxs-lookup"><span data-stu-id="cc957-195">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="cc957-196">有关规划多个网关的详细信息，请参阅[M：N trunk in Skype for Business Server。](m-n-trunk.md)</span><span class="sxs-lookup"><span data-stu-id="cc957-196">For details about planning for multiple gateways, see [M:N trunk in Skype for Business Server](m-n-trunk.md).</span></span>

<span data-ttu-id="cc957-197">有关其他出站路由增强功能，请参阅[Call Routes](/previous-versions/office/lync-server-2013/lync-server-2013-voice-routes)。</span><span class="sxs-lookup"><span data-stu-id="cc957-197">For details about other outbound routing enhancements, see [Call Routes](/previous-versions/office/lync-server-2013/lync-server-2013-voice-routes).</span></span>

#### <a name="gateway-topologies"></a><span data-ttu-id="cc957-198">网关拓扑</span><span class="sxs-lookup"><span data-stu-id="cc957-198">Gateway Topologies</span></span>

<span data-ttu-id="cc957-199">考虑网关部署的基本问题时，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cc957-199">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1. <span data-ttu-id="cc957-200">使用 PSTN 连接计算要提供 PSTN 连接的企业语音。</span><span class="sxs-lookup"><span data-stu-id="cc957-200">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2. <span data-ttu-id="cc957-201">估计每个站点的流量（用户数和每小时每个用户的平均呼叫数）。</span><span class="sxs-lookup"><span data-stu-id="cc957-201">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3. <span data-ttu-id="cc957-202">在每个站点部署一个或多个网关来处理预期的流量。</span><span class="sxs-lookup"><span data-stu-id="cc957-202">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="cc957-p121">使用此拓扑，每个站点内工作者之间的呼叫以及站点之间的呼叫都将通过 Intranet 路由。对 PSTN 的呼叫将通过企业 IP 网络路由到与目标号码所在位置最接近的网关。但是，如果贵组织像许多财务机构和其他大型企业那样，支持数十、数百甚至数千个跨越一个或多个大陆的站点，该怎么办？在这种情况下，在每个站点都部署一个单独的网关是不切实际的。</span><span class="sxs-lookup"><span data-stu-id="cc957-p121">With this topology, calls among workers at each site and between sites are all routed over your intranet. Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do? In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="cc957-206">为了解决此问题，许多大型公司倾向于部署一个或几个大型电话中央站点。</span><span class="sxs-lookup"><span data-stu-id="cc957-206">To address this issue, many large companies prefer to deploy one or a few large telephony central sites.</span></span>

<span data-ttu-id="cc957-207">在此拓扑中，每个中央站点都部署了几个足以容纳预期用户负载的大型网关。</span><span class="sxs-lookup"><span data-stu-id="cc957-207">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="cc957-208">对于企业中各个用户的所有呼叫都将由公司的电话服务提供商转发到某个中央站点。</span><span class="sxs-lookup"><span data-stu-id="cc957-208">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="cc957-209">中央站点的路由逻辑确定呼叫是应该通过 Intranet 路由还是路由到 PSTN。</span><span class="sxs-lookup"><span data-stu-id="cc957-209">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

#### <a name="gateway-location"></a><span data-ttu-id="cc957-210">网关的位置</span><span class="sxs-lookup"><span data-stu-id="cc957-210">Gateway Location</span></span>

<span data-ttu-id="cc957-p123">网关的位置还可能决定所选网关的类型及其配置方式。目前有许多 PSTN 协议，但没有一种成为全球标准。如果您所有的网关都位于同一个国家/地区，这不会带来任何问题。但是，如果您在多个国家/地区设置了网关，则必须按照该国家/地区的 PSTN 标准来配置每个网关。而且，经过认证能够在某个国家/地区（例如加拿大）正常工作的网关可能未在印度、巴西或欧盟获得认证。</span><span class="sxs-lookup"><span data-stu-id="cc957-p123">Gateway location may also determine the types of gateways that you choose and how they are configured. There are dozens of PSTN protocols, none of which is a worldwide standard. If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region. Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

#### <a name="gateway-size-and-number"></a><span data-ttu-id="cc957-215">网关的大小和数量</span><span class="sxs-lookup"><span data-stu-id="cc957-215">Gateway Size and Number</span></span>

<span data-ttu-id="cc957-p124">大多数组织都考虑部署大小在 2 到 960 个端口之间的 PSTN 网关。（还有更大的网关，但是这些网关主要由电话服务提供商使用。）请按照下列准则来估计贵组织所需的端口数：</span><span class="sxs-lookup"><span data-stu-id="cc957-p124">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports. (There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

- <span data-ttu-id="cc957-p125">对于电话呼叫数量较少的组织（每个用户每小时一个 PSTN 呼叫），则应当为每 15 个用户分配一个端口。例如，如果有 20 个用户，则需要一个具有两个端口的网关。</span><span class="sxs-lookup"><span data-stu-id="cc957-p125">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users. For example, if you have 20 users, you will require a gateway with two ports.</span></span>

- <span data-ttu-id="cc957-p126">对于电话呼叫数量适中的组织（每个用户每小时两个 PSTN 呼叫），则应当为每 10 个用户分配一个端口。例如，如果您有 100 个用户，则将需要在一个或多个网关之间总共分配 10 个端口。</span><span class="sxs-lookup"><span data-stu-id="cc957-p126">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users. For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

- <span data-ttu-id="cc957-p127">对于电话呼叫数量较多的组织（每个用户每小时三个或更多个 PSTN 呼叫），则应当为每 5 个用户分配一个端口。例如，如果您有 47,000 个用户，则将至少在 10 个较大网关之间总共分配 9,400 个端口。</span><span class="sxs-lookup"><span data-stu-id="cc957-p127">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users. For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

- <span data-ttu-id="cc957-224">当贵组织中的用户数量或流量增加时，可以获取额外的端口。</span><span class="sxs-lookup"><span data-stu-id="cc957-224">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="cc957-p128">对于您必须支持的任何给定数量的用户，您可以选择部署少量大型网关，也可以选择部署小型网关。通常，建议在一个组织中至少部署两个网关，以便在其中一个网关出现故障时保持可用性。</span><span class="sxs-lookup"><span data-stu-id="cc957-p128">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones. As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="cc957-227">部署的每个 PSTN 网关都必须至少有一个对应的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="cc957-227">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>