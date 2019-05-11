---
title: Skype 中的业务服务器的直接 SIP 连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: Skype 的业务服务器，并同时 PSTN 网关和企业语音中的 IP PBX 之间支持直接 SIP 连接。
ms.openlocfilehash: 8d7533b77612f21ed36e7ee3334c484fc4edd04c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924988"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a><span data-ttu-id="939e1-103">Skype 中的业务服务器的直接 SIP 连接</span><span class="sxs-lookup"><span data-stu-id="939e1-103">Direct SIP connections in Skype for Business Server</span></span>

<span data-ttu-id="939e1-104">Skype 的业务服务器，并同时 PSTN 网关和企业语音中的 IP PBX 之间支持直接 SIP 连接。</span><span class="sxs-lookup"><span data-stu-id="939e1-104">Direct SIP connections are supported between Skype for Business Server and both PSTN gateways and IP-PBX in Enterprise Voice.</span></span>

<span data-ttu-id="939e1-105">可以使用直接 SIP 连接的业务服务器的 Skype 连接到以下任一项：</span><span class="sxs-lookup"><span data-stu-id="939e1-105">You can use direct SIP connections to connect Skype for Business Server to either of the following:</span></span>

- <span data-ttu-id="939e1-106">IP-PBX</span><span class="sxs-lookup"><span data-stu-id="939e1-106">An IP-PBX</span></span>

- <span data-ttu-id="939e1-107">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="939e1-107">A PSTN gateway</span></span>

<span data-ttu-id="939e1-108">若要实现的直接 SIP 连接，您按照本质上是相同的部署步骤即可实现 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="939e1-108">To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk.</span></span> <span data-ttu-id="939e1-109">在这两种情况下，您可以使用中介服务器的外部接口实现连接。</span><span class="sxs-lookup"><span data-stu-id="939e1-109">In both cases, you implement the connection by using the external interface of a Mediation Server.</span></span> <span data-ttu-id="939e1-110">SIP 中继连接到外部实体，如 ITSP 网关，并在您的本地网络，如 IP PBX 或公用电话交换网 (pstn) 网关的直接 SIP 连接连接到内部的实体，唯一的区别。</span><span class="sxs-lookup"><span data-stu-id="939e1-110">The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.</span></span>

## <a name="direct-sip-deployment-options"></a><span data-ttu-id="939e1-111">直接 SIP 部署选项</span><span class="sxs-lookup"><span data-stu-id="939e1-111">Direct SIP deployment options</span></span>

### <a name="skype-for-business-server-stand-alone"></a><span data-ttu-id="939e1-112">Skype 业务 server 独立</span><span class="sxs-lookup"><span data-stu-id="939e1-112">Skype for Business Server Stand-Alone</span></span>
<span data-ttu-id="939e1-113"><a name="BKMK_CommunicationsServerStand-Alone"> </a></span><span class="sxs-lookup"><span data-stu-id="939e1-113"></span></span>

<span data-ttu-id="939e1-114">如果您的组织使用本节中所述的部署之一，您可以用于 Skype 业务服务器作为部分或整个组织的唯一电话解决方案。</span><span class="sxs-lookup"><span data-stu-id="939e1-114">If your organization uses one of the deployments described in this section, you can use Skype for Business Server as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="939e1-115">本节介绍了以下部署详细信息：</span><span class="sxs-lookup"><span data-stu-id="939e1-115">This section describes the following deployments in detail:</span></span>

- <span data-ttu-id="939e1-116">**增量部署：** 此选项假定您具有现有的专用交换机 (pbx) 基础结构，并且您打算企业语音逐步引入贵组织中的团队或较小的组。</span><span class="sxs-lookup"><span data-stu-id="939e1-116">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

- <span data-ttu-id="939e1-117">**仅 VoIP 部署：** 此选项假定您正考虑在没有传统电话基础结构的站点的企业语音部署。</span><span class="sxs-lookup"><span data-stu-id="939e1-117">**VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

#### <a name="incremental-deployment"></a><span data-ttu-id="939e1-118">增量部署</span><span class="sxs-lookup"><span data-stu-id="939e1-118">Incremental Deployment</span></span>

<span data-ttu-id="939e1-119">在增量部署中，Skype 业务 server 是个别团队的唯一电话解决方案或部门，组织中的用户的其余部分时继续使用 PBX。</span><span class="sxs-lookup"><span data-stu-id="939e1-119">In incremental deployment, Skype for Business Server is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="939e1-120">此增量部署策略提供一种方法 IP 电话引入企业通过受控的试点计划。</span><span class="sxs-lookup"><span data-stu-id="939e1-120">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="939e1-121">其通信需求最构成由 Microsoft 统一通信的工作组移至企业语音，而其他用户保留在现有 PBX 上。</span><span class="sxs-lookup"><span data-stu-id="939e1-121">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="939e1-122">根据需要可将其他工作组迁移至企业语音。</span><span class="sxs-lookup"><span data-stu-id="939e1-122">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="939e1-123">增量同步选项被建议如果您清楚地定义了用户组，已在公用和的通信要求适合于集中式管理。</span><span class="sxs-lookup"><span data-stu-id="939e1-123">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="939e1-124">此选项也是有效的如果您有团队或部门，广泛地理区域，节省长途话费会产生重大影响。</span><span class="sxs-lookup"><span data-stu-id="939e1-124">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="939e1-125">实际上，此选项可用于创建其成员可能会分散在世界各地的虚拟团队。</span><span class="sxs-lookup"><span data-stu-id="939e1-125">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="939e1-126">您可以创建、 修改或解散这样的团队中快速响应业务要求。</span><span class="sxs-lookup"><span data-stu-id="939e1-126">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="939e1-127">下图显示了部署企业语音位于 PBX 后面的通用拓扑。</span><span class="sxs-lookup"><span data-stu-id="939e1-127">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="939e1-128">这是建议的拓扑增量部署。</span><span class="sxs-lookup"><span data-stu-id="939e1-128">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="939e1-129">**增量部署选项**</span><span class="sxs-lookup"><span data-stu-id="939e1-129">**Incremental deployment option**</span></span>

![部门迁移选项图](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> <span data-ttu-id="939e1-131">如果要连接到认证的直接 SIP 合作伙伴您 Skype 业务服务器部署，则不需要中介服务器与 PBX 之间的公用电话交换网 (pstn) 网关。</span><span class="sxs-lookup"><span data-stu-id="939e1-131">If you are connecting your Skype for Business Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="939e1-132">有关直接 SIP 的认证合作伙伴的列表，请参阅[Microsoft 统一通信开放互操作性计划](https://go.microsoft.com/fwlink/p/?linkId=203309)。</span><span class="sxs-lookup"><span data-stu-id="939e1-132">For a list of certified Direct SIP partners, see the  [Microsoft Unified Communications Open Interoperability Program](https://go.microsoft.com/fwlink/p/?linkId=203309).</span></span>

> [!NOTE]
> <span data-ttu-id="939e1-133">此图中所示的媒体路径已启用媒体旁路 （推荐配置）。</span><span class="sxs-lookup"><span data-stu-id="939e1-133">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="939e1-134">如果您选择要禁用媒体旁路，通过中介服务器路由的媒体路径。</span><span class="sxs-lookup"><span data-stu-id="939e1-134">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>

<span data-ttu-id="939e1-135">在此拓扑中，所选的部门或工作组启用了企业语音。</span><span class="sxs-lookup"><span data-stu-id="939e1-135">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="939e1-136">PSTN 网关链接语音 (voip)-启用到 PBX 的工作组。</span><span class="sxs-lookup"><span data-stu-id="939e1-136">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="939e1-137">启用了企业语音，包括远程工作者的用户将通过 IP 网络进行通信。</span><span class="sxs-lookup"><span data-stu-id="939e1-137">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="939e1-138">由企业语音用户对 PSTN 和未启用企业语音的同事的呼叫路由至相应的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="939e1-138">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="939e1-139">从同事仍位于 PBX 系统，或在 PSTN 的呼叫者的呼叫将路由到 PSTN 网关，将 Skype 调用业务服务器转发的路由。</span><span class="sxs-lookup"><span data-stu-id="939e1-139">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Skype for Business Server for routing.</span></span>

<span data-ttu-id="939e1-140">有两种建议的配置为连接到现有 PBX 基础结构的互操作性的企业语音： 企业语音位于 PBX 和企业语音位于 PBX 前面后面。</span><span class="sxs-lookup"><span data-stu-id="939e1-140">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

#### <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="939e1-141">企业语音位于 PBX 后面</span><span class="sxs-lookup"><span data-stu-id="939e1-141">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="939e1-142">在 PBX 后面部署了企业语音，则所有来自 PSTN 的呼叫到达 PBX，这将向企业语音用户的呼叫路由到 PSTN 网关，并向到 PBX 的 PBX 用户调用。</span><span class="sxs-lookup"><span data-stu-id="939e1-142">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

#### <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="939e1-143">企业语音位于 PBX 前面</span><span class="sxs-lookup"><span data-stu-id="939e1-143">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="939e1-144">当位于 PBX 前面部署企业语音时，所有呼叫都到达 PSTN 网关，路由为企业语音用户移动到 Skype 调用业务服务器和 PBX 用户到 PBX 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="939e1-144">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Skype for Business Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="939e1-145">来自企业语音和 PBX 用户对 PSTN 的呼叫是通过 IP 网络路由到最经济高效的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="939e1-145">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="939e1-146">下表显示了此配置的优缺点。</span><span class="sxs-lookup"><span data-stu-id="939e1-146">The following table shows the advantages and disadvantages of this configuration.</span></span>

<span data-ttu-id="939e1-147">**部署企业语音位于 PBX 前面的优点和缺点**</span><span class="sxs-lookup"><span data-stu-id="939e1-147">**Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX**</span></span>

|<span data-ttu-id="939e1-148">**优点**</span><span class="sxs-lookup"><span data-stu-id="939e1-148">**Advantages**</span></span>|<span data-ttu-id="939e1-149">**缺点**</span><span class="sxs-lookup"><span data-stu-id="939e1-149">**Disadvantages**</span></span>|
|:-----|:-----|
|<span data-ttu-id="939e1-150">PBX 仍那些未启用企业语音用户提供服务。</span><span class="sxs-lookup"><span data-stu-id="939e1-150">PBX still serves users not enabled for Enterprise Voice.</span></span>  <br/> |<span data-ttu-id="939e1-151">现有的网关可能不支持的功能或所需的容量。</span><span class="sxs-lookup"><span data-stu-id="939e1-151">Existing gateways may not support the features or capacity that you want.</span></span>  <br/> |
|<span data-ttu-id="939e1-152">PBX 处理所有的早期设备。</span><span class="sxs-lookup"><span data-stu-id="939e1-152">PBX handles all earlier devices.</span></span>  <br/> |<span data-ttu-id="939e1-153">需要从 PBX 网关和中介服务器的网关的中继。</span><span class="sxs-lookup"><span data-stu-id="939e1-153">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="939e1-154">您可能需要从服务提供商的多个中继。</span><span class="sxs-lookup"><span data-stu-id="939e1-154">You may need more trunks from the service provider.</span></span>  <br/> |
|<span data-ttu-id="939e1-155">企业语音用户保留相同的电话号码。</span><span class="sxs-lookup"><span data-stu-id="939e1-155">Enterprise Voice users keep the same phone numbers.</span></span>  <br/> | <br/> |

#### <a name="voip-only-deployment"></a><span data-ttu-id="939e1-156">仅 VoIP 部署</span><span class="sxs-lookup"><span data-stu-id="939e1-156">VoIP-Only Deployment</span></span>

<span data-ttu-id="939e1-157">企业语音提供了新的企业，以及新 office 网站的现有企业，能够实现全功能的 VoIP 解决方案，而不必担心 PBX 集成，或导致的大量的部署和维护IP PBX 基础结构的成本。</span><span class="sxs-lookup"><span data-stu-id="939e1-157">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="939e1-158">此解决方案支持现场和远程工作者。</span><span class="sxs-lookup"><span data-stu-id="939e1-158">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="939e1-159">在此部署中，所有呼叫都通过 IP 网络都路由。</span><span class="sxs-lookup"><span data-stu-id="939e1-159">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="939e1-160">到 PSTN 的呼叫路由至相应的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="939e1-160">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="939e1-161">Skype 适用于商务或 Lync Phone Edition 充当软电话。</span><span class="sxs-lookup"><span data-stu-id="939e1-161">Skype for Business or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="939e1-162">远程呼叫控制是不可用的和不必要，因为有用户控件没有 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="939e1-162">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="939e1-163">通过可选的部署的 Exchange 统一消息 (UM) 提供了语音邮件和自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="939e1-163">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

> [!NOTE]
> <span data-ttu-id="939e1-164">除了支持 Skype 业务服务器所需的网络基础结构，仅 VoIP 部署还可以使用小型合格网关支持传真机和模拟设备。</span><span class="sxs-lookup"><span data-stu-id="939e1-164">In addition to the network infrastructure that is required to support Skype for Business Server, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>

<span data-ttu-id="939e1-165">下图显示了仅 VoIP 部署的典型拓扑。</span><span class="sxs-lookup"><span data-stu-id="939e1-165">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="939e1-166">**仅 VoIP 部署选项**</span><span class="sxs-lookup"><span data-stu-id="939e1-166">**VoIP-only deployment option**</span></span>

![绿场部署选项](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> <span data-ttu-id="939e1-168">此图中所示的媒体路径已启用媒体旁路 （推荐配置）。</span><span class="sxs-lookup"><span data-stu-id="939e1-168">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="939e1-169">如果您选择要禁用媒体旁路，通过中介服务器路由的媒体路径。</span><span class="sxs-lookup"><span data-stu-id="939e1-169">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>

## <a name="pstn-gateway-deployment-options"></a><span data-ttu-id="939e1-170">PSTN 网关部署选项</span><span class="sxs-lookup"><span data-stu-id="939e1-170">PSTN Gateway deployment options</span></span>

### <a name="pstn-gateways"></a><span data-ttu-id="939e1-171">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="939e1-171">PSTN Gateways</span></span>

<span data-ttu-id="939e1-172">公用电话交换网 (pstn) 网关是直接或通过 SIP 中继连接翻译企业语音基础结构与 PSTN 之间信号和媒体的第三方硬件组件。</span><span class="sxs-lookup"><span data-stu-id="939e1-172">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="939e1-173">在任一拓扑中，网关终止 PSTN。</span><span class="sxs-lookup"><span data-stu-id="939e1-173">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="939e1-174">网关在其自己的子网中隔离并连接到企业网络通过中介服务器。</span><span class="sxs-lookup"><span data-stu-id="939e1-174">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="939e1-175">具有多个站点企业通常会部署一个或多个网关在每个网站。</span><span class="sxs-lookup"><span data-stu-id="939e1-175">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="939e1-176">分支站点可以连接到 PSTN 通过网关，或通过 Survivable Branch Appliance，结合使用，网关和一个框中的服务器。</span><span class="sxs-lookup"><span data-stu-id="939e1-176">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="939e1-177">如果分支站点使用网关，注册器和中介服务器所需在网站上，除非 WAN 链接是弹性。</span><span class="sxs-lookup"><span data-stu-id="939e1-177">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="939e1-178">一个或多个中介服务器，都并置在前端服务器，可以将一个或多个网关的呼叫路由每个站点。</span><span class="sxs-lookup"><span data-stu-id="939e1-178">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="939e1-179">建议的注册器、 中介服务器和所需网站上的网关作为 Survivable Branch Appliance 部署。</span><span class="sxs-lookup"><span data-stu-id="939e1-179">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="939e1-180">确定数量、 大小和 PSTN 网关的位置可能是规划企业语音基础结构时必须做出的最重要且最昂贵的决策。</span><span class="sxs-lookup"><span data-stu-id="939e1-180">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="939e1-181">以下是要考虑的主要问题。</span><span class="sxs-lookup"><span data-stu-id="939e1-181">Here are the main questions to consider.</span></span> <span data-ttu-id="939e1-182">请记住这些问题的答案是所有相互依赖</span><span class="sxs-lookup"><span data-stu-id="939e1-182">Keep in mind that the answers to these questions are all interdependent</span></span>

- <span data-ttu-id="939e1-183">需要多少 PSTN 网关？</span><span class="sxs-lookup"><span data-stu-id="939e1-183">How many PSTN gateways are needed?</span></span> <span data-ttu-id="939e1-184">答案取决于用户数和的预期并发呼叫 （流量负载），数 （每个站点需要一个） 的网站的数目。</span><span class="sxs-lookup"><span data-stu-id="939e1-184">The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

- <span data-ttu-id="939e1-185">大小网关应当？</span><span class="sxs-lookup"><span data-stu-id="939e1-185">What size should the gateways be?</span></span> <span data-ttu-id="939e1-186">答案取决于该站点的用户数以及流量负载。</span><span class="sxs-lookup"><span data-stu-id="939e1-186">The answer depends on the number of users at the site and on the traffic load.</span></span>

- <span data-ttu-id="939e1-187">其中网关应当位于？</span><span class="sxs-lookup"><span data-stu-id="939e1-187">Where should the gateways be located?</span></span> <span data-ttu-id="939e1-188">答案部分取决于，在拓扑和您的组织的地理分布。</span><span class="sxs-lookup"><span data-stu-id="939e1-188">The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

  <span data-ttu-id="939e1-189">您还应该考虑网关拓扑选项 （有关详细信息，请参阅网关拓扑本主题后面）。</span><span class="sxs-lookup"><span data-stu-id="939e1-189">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

#### <a name="mn-trunk-support"></a><span data-ttu-id="939e1-190">M:N 中继支持</span><span class="sxs-lookup"><span data-stu-id="939e1-190">M:N Trunk Support</span></span>

<span data-ttu-id="939e1-191">中介服务器可以将路由呼叫通过多个网关，会话边界控制器 (Sbc) 提供 Internet 电话服务提供商或二者的组合。</span><span class="sxs-lookup"><span data-stu-id="939e1-191">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="939e1-192">此外，在池中的多个中介服务器可以与多个网关进行交互。</span><span class="sxs-lookup"><span data-stu-id="939e1-192">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="939e1-193">定义中介服务器和网关之间的逻辑路由称为中继。</span><span class="sxs-lookup"><span data-stu-id="939e1-193">The logical route defined between a Mediation Server and gateway is called a trunk.</span></span> <span data-ttu-id="939e1-194">时内部用户发起 PSTN 呼叫，前端池上的出站路由逻辑中选择的中继路由通过利用可能是适用于该特定的呼叫路由的所有可能的组合。</span><span class="sxs-lookup"><span data-stu-id="939e1-194">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="939e1-195">使用 DNS 负载平衡，如果呼叫无法到达由于中介服务器池中，特定问题的网关呼叫将重试池中备用的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="939e1-195">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="939e1-196">关于规划多个网关的详细信息，请参阅[中的业务服务器 Skype M:N 中继](m-n-trunk.md)。</span><span class="sxs-lookup"><span data-stu-id="939e1-196">For details about planning for multiple gateways, see [M:N trunk in Skype for Business Server](m-n-trunk.md).</span></span>

<span data-ttu-id="939e1-197">有关其他出站路由增强功能的详细信息，请参阅[Call Routes](https://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx)。</span><span class="sxs-lookup"><span data-stu-id="939e1-197">For details about other outbound routing enhancements, see [Call Routes](https://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx).</span></span>

#### <a name="gateway-topologies"></a><span data-ttu-id="939e1-198">网关拓扑</span><span class="sxs-lookup"><span data-stu-id="939e1-198">Gateway Topologies</span></span>

<span data-ttu-id="939e1-199">考虑网关部署的基本问题时，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="939e1-199">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1. <span data-ttu-id="939e1-200">计数您要使用企业语音提供 PSTN 连接的网站。</span><span class="sxs-lookup"><span data-stu-id="939e1-200">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2. <span data-ttu-id="939e1-201">估计每个站点 （用户数） 和每小时每个用户的呼叫的平均数目的流量。</span><span class="sxs-lookup"><span data-stu-id="939e1-201">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3. <span data-ttu-id="939e1-202">部署一个或多个网关在每个网站来处理预期的流量。</span><span class="sxs-lookup"><span data-stu-id="939e1-202">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="939e1-203">使用此拓扑，每个站点和站点间的工作者之间的呼叫将所有路由通过 intranet。</span><span class="sxs-lookup"><span data-stu-id="939e1-203">With this topology, calls among workers at each site and between sites are all routed over your intranet.</span></span> <span data-ttu-id="939e1-204">通过企业 IP 网络到目标号码的位置最接近的网关路由到 PSTN 的呼叫。但如果您的组织支持数十、 数百或数千个网站分布在一个或多个大洲，像许多财务机构和其他大型企业那样？</span><span class="sxs-lookup"><span data-stu-id="939e1-204">Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do?</span></span> <span data-ttu-id="939e1-205">在这种情况下，部署单独的网关，每个站点不可行。</span><span class="sxs-lookup"><span data-stu-id="939e1-205">In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="939e1-206">为了解决此问题，许多大型公司都喜欢部署一个或几个大型电话中央站点。</span><span class="sxs-lookup"><span data-stu-id="939e1-206">To address this issue, many large companies prefer to deploy one or a few large telephony central sites.</span></span>

<span data-ttu-id="939e1-207">在这种拓扑，每个中央站点上部署几个大型网关足以容纳预期的用户负载。</span><span class="sxs-lookup"><span data-stu-id="939e1-207">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="939e1-208">会向企业中的用户的所有呼叫都转接到中央站点的公司的电话服务提供商。</span><span class="sxs-lookup"><span data-stu-id="939e1-208">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="939e1-209">在中央站点的路由逻辑决定是否应将呼叫路由通过 intranet 或到 PSTN。</span><span class="sxs-lookup"><span data-stu-id="939e1-209">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

#### <a name="gateway-location"></a><span data-ttu-id="939e1-210">网关的位置</span><span class="sxs-lookup"><span data-stu-id="939e1-210">Gateway Location</span></span>

<span data-ttu-id="939e1-211">网关的位置还决定您选择的网关和及其配置方式的类型。</span><span class="sxs-lookup"><span data-stu-id="939e1-211">Gateway location may also determine the types of gateways that you choose and how they are configured.</span></span> <span data-ttu-id="939e1-212">有许多 PSTN 协议，都不是成为全球标准。</span><span class="sxs-lookup"><span data-stu-id="939e1-212">There are dozens of PSTN protocols, none of which is a worldwide standard.</span></span> <span data-ttu-id="939e1-213">如果您的所有网关都位于单个国家/地区，这不是问题，但如果在多个国家/地区找到网关，每个必须配置根据国家/地区的 PSTN 标准。</span><span class="sxs-lookup"><span data-stu-id="939e1-213">If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region.</span></span> <span data-ttu-id="939e1-214">此外，不可能在印度、 巴西或欧盟认证操作中，例如，加拿大，经过认证的网关。</span><span class="sxs-lookup"><span data-stu-id="939e1-214">Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

#### <a name="gateway-size-and-number"></a><span data-ttu-id="939e1-215">网关的大小和数量</span><span class="sxs-lookup"><span data-stu-id="939e1-215">Gateway Size and Number</span></span>

<span data-ttu-id="939e1-216">大多数组织都考虑部署大小在 2 到 960 端口 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="939e1-216">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports.</span></span> <span data-ttu-id="939e1-217">（有更大的网关，但这些主要由电话服务提供商）。在估计您的组织要求的端口数，使用以下准则：</span><span class="sxs-lookup"><span data-stu-id="939e1-217">(There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

- <span data-ttu-id="939e1-218">具有较少的电话用法 （每个用户每小时一个 PSTN 呼叫） 的组织应为每 15 个用户分配一个端口。</span><span class="sxs-lookup"><span data-stu-id="939e1-218">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users.</span></span> <span data-ttu-id="939e1-219">例如，如果您有 20 个用户，您将需要两个端口的网关。</span><span class="sxs-lookup"><span data-stu-id="939e1-219">For example, if you have 20 users, you will require a gateway with two ports.</span></span>

- <span data-ttu-id="939e1-220">具有数量中等的电话用法 （每个用户每小时两个 PSTN 呼叫） 的组织应为每 10 个用户分配一个端口。</span><span class="sxs-lookup"><span data-stu-id="939e1-220">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users.</span></span> <span data-ttu-id="939e1-221">例如，如果您有 100 个用户，您将需要 10 个端口分配一个或多个网关之间总共。</span><span class="sxs-lookup"><span data-stu-id="939e1-221">For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

- <span data-ttu-id="939e1-222">具有大量电话用法 （三个或多个 PSTN 呼叫每个用户每小时） 的组织应为每五个用户分配一个端口。</span><span class="sxs-lookup"><span data-stu-id="939e1-222">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users.</span></span> <span data-ttu-id="939e1-223">例如，如果您有 47,000 用户，您将需要至少 10 个大型网关之间分配 9,400 个端口的总数。</span><span class="sxs-lookup"><span data-stu-id="939e1-223">For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

- <span data-ttu-id="939e1-224">用户数量或流量组织增加量时，可以获取额外的端口。</span><span class="sxs-lookup"><span data-stu-id="939e1-224">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="939e1-225">对于任何给定必须支持的用户数，您必须部署更少的、 更大的网关或较小的选择。</span><span class="sxs-lookup"><span data-stu-id="939e1-225">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones.</span></span> <span data-ttu-id="939e1-226">通常，建议至少为组织的两个网关维护可用性，如果一个网关失败。</span><span class="sxs-lookup"><span data-stu-id="939e1-226">As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="939e1-227">您部署每个 PSTN 网关必须至少一个相应的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="939e1-227">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>


