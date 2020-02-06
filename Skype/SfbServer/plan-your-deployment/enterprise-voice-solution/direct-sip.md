---
title: Skype for Business 服务器中的直接 SIP 连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 在企业语音版 Skype for Business 服务器以及 PSTN 网关和 IP PBX 之间支持直接 SIP 连接。
ms.openlocfilehash: 1948e08d63aed9d49c70443a386adce6dc65f78e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803052"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a><span data-ttu-id="f63a1-103">Skype for Business 服务器中的直接 SIP 连接</span><span class="sxs-lookup"><span data-stu-id="f63a1-103">Direct SIP connections in Skype for Business Server</span></span>

<span data-ttu-id="f63a1-104">在企业语音版 Skype for Business 服务器以及 PSTN 网关和 IP PBX 之间支持直接 SIP 连接。</span><span class="sxs-lookup"><span data-stu-id="f63a1-104">Direct SIP connections are supported between Skype for Business Server and both PSTN gateways and IP-PBX in Enterprise Voice.</span></span>

<span data-ttu-id="f63a1-105">您可以使用直接 SIP 连接将 Skype for Business 服务器连接到以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="f63a1-105">You can use direct SIP connections to connect Skype for Business Server to either of the following:</span></span>

- <span data-ttu-id="f63a1-106">IP PBX</span><span class="sxs-lookup"><span data-stu-id="f63a1-106">An IP-PBX</span></span>

- <span data-ttu-id="f63a1-107">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="f63a1-107">A PSTN gateway</span></span>

<span data-ttu-id="f63a1-108">若要实现直接 SIP 连接，请遵循与实现 SIP 主干基本相同的部署步骤。</span><span class="sxs-lookup"><span data-stu-id="f63a1-108">To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk.</span></span> <span data-ttu-id="f63a1-109">在这两种情况下，通过使用中介服务器的外部接口实现连接。</span><span class="sxs-lookup"><span data-stu-id="f63a1-109">In both cases, you implement the connection by using the external interface of a Mediation Server.</span></span> <span data-ttu-id="f63a1-110">唯一的区别是，你可以将 SIP 中继连接到外部实体（如 ITSP 网关），并将直接 SIP 连接连接到本地网络内的内部实体，如 IP PBX 或公共交换电话网络（PSTN）网关。</span><span class="sxs-lookup"><span data-stu-id="f63a1-110">The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.</span></span>

## <a name="direct-sip-deployment-options"></a><span data-ttu-id="f63a1-111">直接 SIP 部署选项</span><span class="sxs-lookup"><span data-stu-id="f63a1-111">Direct SIP deployment options</span></span>

### <a name="skype-for-business-server-stand-alone"></a><span data-ttu-id="f63a1-112">Skype for business Server 独立版</span><span class="sxs-lookup"><span data-stu-id="f63a1-112">Skype for Business Server Stand-Alone</span></span>
<span data-ttu-id="f63a1-113"><a name="BKMK_CommunicationsServerStand-Alone"> </a></span><span class="sxs-lookup"><span data-stu-id="f63a1-113"><a name="BKMK_CommunicationsServerStand-Alone"> </a></span></span>

<span data-ttu-id="f63a1-114">如果你的组织使用本部分中介绍的部署之一，则可以使用 Skype for Business 服务器作为组织的部分或全部服务的唯一电话服务解决方案。</span><span class="sxs-lookup"><span data-stu-id="f63a1-114">If your organization uses one of the deployments described in this section, you can use Skype for Business Server as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="f63a1-115">本部分详细介绍以下部署：</span><span class="sxs-lookup"><span data-stu-id="f63a1-115">This section describes the following deployments in detail:</span></span>

- <span data-ttu-id="f63a1-116">**增量部署：** 此选项假设你有现有的专用分支 exchange （PBX）基础结构，并且想要将企业语音增量引入组织内较小的组或团队。</span><span class="sxs-lookup"><span data-stu-id="f63a1-116">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

- <span data-ttu-id="f63a1-117">**仅限 VoIP 的部署：** 此选项假定你考虑在没有传统的电话基础结构的网站上部署企业语音。</span><span class="sxs-lookup"><span data-stu-id="f63a1-117">**VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

#### <a name="incremental-deployment"></a><span data-ttu-id="f63a1-118">增量部署</span><span class="sxs-lookup"><span data-stu-id="f63a1-118">Incremental Deployment</span></span>

<span data-ttu-id="f63a1-119">在增量部署中，Skype for business 服务器是单个团队或部门的唯一电话服务解决方案，而组织中的其他用户仍在使用 PBX。</span><span class="sxs-lookup"><span data-stu-id="f63a1-119">In incremental deployment, Skype for Business Server is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="f63a1-120">此增量部署策略提供了一种通过受控试点计划在企业中引入 IP 电话的方法。</span><span class="sxs-lookup"><span data-stu-id="f63a1-120">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="f63a1-121">Microsoft 统一通信最适合使用其通信需求的工作组被移动到企业语音，而其他用户则保留在现有 PBX 上。</span><span class="sxs-lookup"><span data-stu-id="f63a1-121">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="f63a1-122">可根据需要将其他工作组迁移到企业语音。</span><span class="sxs-lookup"><span data-stu-id="f63a1-122">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="f63a1-123">如果明确定义的用户组具有共同的通信要求，并且该用户组适用于集中管理，则建议使用 "增量" 选项。</span><span class="sxs-lookup"><span data-stu-id="f63a1-123">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="f63a1-124">如果你有团队或部门分布在地理区域上方，而您的长途费用成本可能很大，此选项也很有效。</span><span class="sxs-lookup"><span data-stu-id="f63a1-124">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="f63a1-125">实际上，此选项对于创建其成员可能分散在全球各地的虚拟团队非常有用。</span><span class="sxs-lookup"><span data-stu-id="f63a1-125">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="f63a1-126">你可以创建、修改或解散此类团队，以便快速响应对业务需求的变化。</span><span class="sxs-lookup"><span data-stu-id="f63a1-126">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="f63a1-127">下图显示了用于在 PBX 背后部署企业语音的一般拓扑。</span><span class="sxs-lookup"><span data-stu-id="f63a1-127">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="f63a1-128">这是增量部署的推荐拓扑。</span><span class="sxs-lookup"><span data-stu-id="f63a1-128">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="f63a1-129">**增量部署选项**</span><span class="sxs-lookup"><span data-stu-id="f63a1-129">**Incremental deployment option**</span></span>

![部门迁移选项图](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> <span data-ttu-id="f63a1-131">如果您将 Skype for Business 服务器部署连接到认证的直接 SIP 合作伙伴，则不需要在中介服务器和 PBX 之间使用公共交换式电话网络（PSTN）网关。</span><span class="sxs-lookup"><span data-stu-id="f63a1-131">If you are connecting your Skype for Business Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="f63a1-132">有关认证直接 SIP 合作伙伴的列表，请参阅[Microsoft 统一通信打开互操作性计划](https://go.microsoft.com/fwlink/p/?linkId=203309)。</span><span class="sxs-lookup"><span data-stu-id="f63a1-132">For a list of certified Direct SIP partners, see the  [Microsoft Unified Communications Open Interoperability Program](https://go.microsoft.com/fwlink/p/?linkId=203309).</span></span>

> [!NOTE]
> <span data-ttu-id="f63a1-133">此图所示的媒体路径启用了媒体旁路（推荐配置）。</span><span class="sxs-lookup"><span data-stu-id="f63a1-133">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="f63a1-134">如果选择禁用 "绕过媒体"，则媒体路径将通过中介服务器进行路由。</span><span class="sxs-lookup"><span data-stu-id="f63a1-134">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>

<span data-ttu-id="f63a1-135">在此拓扑中，将为企业语音启用选定的部门或工作组。</span><span class="sxs-lookup"><span data-stu-id="f63a1-135">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="f63a1-136">PSTN 网关将启用了 Internet 协议（VoIP）的工作组的语音链接到 PBX。</span><span class="sxs-lookup"><span data-stu-id="f63a1-136">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="f63a1-137">已启用企业语音的用户（包括远程工作人员）通过 IP 网络进行通信。</span><span class="sxs-lookup"><span data-stu-id="f63a1-137">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="f63a1-138">通过企业语音用户呼叫 PSTN 和未启用企业语音的同事将路由到相应的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="f63a1-138">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="f63a1-139">来自仍在 PBX 系统或来自 PSTN 的呼叫者的同事的呼叫将路由到 PSTN 网关，该网关会将呼叫转发到 Skype for Business 服务器进行路由。</span><span class="sxs-lookup"><span data-stu-id="f63a1-139">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Skype for Business Server for routing.</span></span>

<span data-ttu-id="f63a1-140">有两种推荐配置，可用于将企业语音连接到现有 PBX 基础结构以实现互操作：在 PBX 前面的 PBX 和企业语音背后的企业语音。</span><span class="sxs-lookup"><span data-stu-id="f63a1-140">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

#### <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="f63a1-141">PBX 背后的企业语音</span><span class="sxs-lookup"><span data-stu-id="f63a1-141">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="f63a1-142">当企业语音部署在 PBX 背后时，PSTN 的所有调用都将到达 PBX，它将呼叫企业语音用户到 PSTN 网关，并与 pbx 用户通话。</span><span class="sxs-lookup"><span data-stu-id="f63a1-142">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

#### <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="f63a1-143">PBX 前面的企业语音</span><span class="sxs-lookup"><span data-stu-id="f63a1-143">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="f63a1-144">如果在 PBX 前面部署了企业语音，所有通话都将进入 PSTN 网关，该网关将呼叫企业语音用户至 Skype for business 服务器，并与 PBX 用户通话。</span><span class="sxs-lookup"><span data-stu-id="f63a1-144">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Skype for Business Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="f63a1-145">从企业语音和 PBX 用户到 PSTN 的通话均通过 IP 网络路由到最经济高效的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="f63a1-145">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="f63a1-146">下表显示了此配置的优点和缺点。</span><span class="sxs-lookup"><span data-stu-id="f63a1-146">The following table shows the advantages and disadvantages of this configuration.</span></span>

<span data-ttu-id="f63a1-147">**在 PBX 前面部署企业语音的优点和缺点**</span><span class="sxs-lookup"><span data-stu-id="f63a1-147">**Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX**</span></span>

|<span data-ttu-id="f63a1-148">**最终**</span><span class="sxs-lookup"><span data-stu-id="f63a1-148">**Advantages**</span></span>|<span data-ttu-id="f63a1-149">**一些**</span><span class="sxs-lookup"><span data-stu-id="f63a1-149">**Disadvantages**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f63a1-150">PBX 仍可为未启用企业语音的用户提供服务。</span><span class="sxs-lookup"><span data-stu-id="f63a1-150">PBX still serves users not enabled for Enterprise Voice.</span></span>  <br/> |<span data-ttu-id="f63a1-151">现有网关可能不支持所需的功能或容量。</span><span class="sxs-lookup"><span data-stu-id="f63a1-151">Existing gateways may not support the features or capacity that you want.</span></span>  <br/> |
|<span data-ttu-id="f63a1-152">PBX 处理所有较早的设备。</span><span class="sxs-lookup"><span data-stu-id="f63a1-152">PBX handles all earlier devices.</span></span>  <br/> |<span data-ttu-id="f63a1-153">需要从 PBX 到 PBX 以及从网关到中介服务器的网关之间的主干。</span><span class="sxs-lookup"><span data-stu-id="f63a1-153">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="f63a1-154">您可能需要来自服务提供商的更多中继。</span><span class="sxs-lookup"><span data-stu-id="f63a1-154">You may need more trunks from the service provider.</span></span>  <br/> |
|<span data-ttu-id="f63a1-155">企业语音用户保持相同的电话号码。</span><span class="sxs-lookup"><span data-stu-id="f63a1-155">Enterprise Voice users keep the same phone numbers.</span></span>  <br/> | <br/> |

#### <a name="voip-only-deployment"></a><span data-ttu-id="f63a1-156">仅限 VoIP 的部署</span><span class="sxs-lookup"><span data-stu-id="f63a1-156">VoIP-Only Deployment</span></span>

<span data-ttu-id="f63a1-157">企业语音为现有企业提供新的企业和新的 office 网站，从而实现了一个功能完备的 VoIP 解决方案，而无需担心 PBX 集成或导致真正的部署和维护。IP PBX 基础结构的成本。</span><span class="sxs-lookup"><span data-stu-id="f63a1-157">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="f63a1-158">此解决方案支持现场和远程工作人员。</span><span class="sxs-lookup"><span data-stu-id="f63a1-158">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="f63a1-159">在此部署中，所有通话都通过 IP 网络进行路由。</span><span class="sxs-lookup"><span data-stu-id="f63a1-159">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="f63a1-160">对 PSTN 的调用将路由到相应的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="f63a1-160">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="f63a1-161">Skype for Business 或 Lync Phone Edition 用作 softphone。</span><span class="sxs-lookup"><span data-stu-id="f63a1-161">Skype for Business or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="f63a1-162">远程呼叫控制不可用，因为没有可供用户控制的 PBX 手机。</span><span class="sxs-lookup"><span data-stu-id="f63a1-162">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="f63a1-163">通过 Exchange 统一消息（UM）的可选部署提供语音邮件和自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="f63a1-163">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

> [!NOTE]
> <span data-ttu-id="f63a1-164">除了支持 Skype for Business 服务器所需的网络基础结构之外，仅有 VoIP 的部署可以使用小型的合格网关来支持传真机和模拟设备。</span><span class="sxs-lookup"><span data-stu-id="f63a1-164">In addition to the network infrastructure that is required to support Skype for Business Server, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>

<span data-ttu-id="f63a1-165">下图显示了仅限 VoIP 的部署的典型拓扑。</span><span class="sxs-lookup"><span data-stu-id="f63a1-165">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="f63a1-166">**仅限 VoIP 的部署选项**</span><span class="sxs-lookup"><span data-stu-id="f63a1-166">**VoIP-only deployment option**</span></span>

![绿场部署选项](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> <span data-ttu-id="f63a1-168">此图所示的媒体路径启用了媒体旁路（推荐配置）。</span><span class="sxs-lookup"><span data-stu-id="f63a1-168">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="f63a1-169">如果选择禁用 "绕过媒体"，则媒体路径将通过中介服务器进行路由。</span><span class="sxs-lookup"><span data-stu-id="f63a1-169">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>

## <a name="pstn-gateway-deployment-options"></a><span data-ttu-id="f63a1-170">PSTN 网关部署选项</span><span class="sxs-lookup"><span data-stu-id="f63a1-170">PSTN Gateway deployment options</span></span>

### <a name="pstn-gateways"></a><span data-ttu-id="f63a1-171">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="f63a1-171">PSTN Gateways</span></span>

<span data-ttu-id="f63a1-172">公共交换式电话网络（PSTN）网关是第三方硬件组件，可直接或通过连接到 SIP 中继在企业语音基础结构和 PSTN 之间转换信号和媒体。</span><span class="sxs-lookup"><span data-stu-id="f63a1-172">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="f63a1-173">在任一拓扑中，网关将终止 PSTN。</span><span class="sxs-lookup"><span data-stu-id="f63a1-173">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="f63a1-174">网关被隔离在其自己的子网中，并通过中介服务器连接到企业网络。</span><span class="sxs-lookup"><span data-stu-id="f63a1-174">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="f63a1-175">具有多个网站的企业通常会在每个网站上部署一个或多个网关。</span><span class="sxs-lookup"><span data-stu-id="f63a1-175">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="f63a1-176">分支站点可以通过网关或通过 Survivable 分支设备连接到 PSTN，该设备将网关和服务器结合到一个框中。</span><span class="sxs-lookup"><span data-stu-id="f63a1-176">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="f63a1-177">如果分支站点使用网关，则在网站上需要注册机构和中介服务器，除非 WAN 链接是复原的。</span><span class="sxs-lookup"><span data-stu-id="f63a1-177">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="f63a1-178">一个或多个中介服务器（在前端服务器上 collocated）可路由每个站点上的一个或多个网关的呼叫。</span><span class="sxs-lookup"><span data-stu-id="f63a1-178">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="f63a1-179">我们建议将网站上所需的注册机构、中介服务器和网关部署为 Survivable 分支装置。</span><span class="sxs-lookup"><span data-stu-id="f63a1-179">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="f63a1-180">确定 PSTN 网关的数量、大小和位置可能是规划企业语音基础结构时必须做出的最重要且昂贵的决策。</span><span class="sxs-lookup"><span data-stu-id="f63a1-180">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="f63a1-181">下面是要考虑的主要问题。</span><span class="sxs-lookup"><span data-stu-id="f63a1-181">Here are the main questions to consider.</span></span> <span data-ttu-id="f63a1-182">请记住，这些问题的答案都是相互依赖的</span><span class="sxs-lookup"><span data-stu-id="f63a1-182">Keep in mind that the answers to these questions are all interdependent</span></span>

- <span data-ttu-id="f63a1-183">需要多少个 PSTN 网关？</span><span class="sxs-lookup"><span data-stu-id="f63a1-183">How many PSTN gateways are needed?</span></span> <span data-ttu-id="f63a1-184">答案取决于用户数、预计的同时通话数（流量负载）和网站数（每个网站需要一个）。</span><span class="sxs-lookup"><span data-stu-id="f63a1-184">The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

- <span data-ttu-id="f63a1-185">网关应具有的大小是多少？</span><span class="sxs-lookup"><span data-stu-id="f63a1-185">What size should the gateways be?</span></span> <span data-ttu-id="f63a1-186">答案取决于网站上的用户数以及流量负载。</span><span class="sxs-lookup"><span data-stu-id="f63a1-186">The answer depends on the number of users at the site and on the traffic load.</span></span>

- <span data-ttu-id="f63a1-187">网关应位于何处？</span><span class="sxs-lookup"><span data-stu-id="f63a1-187">Where should the gateways be located?</span></span> <span data-ttu-id="f63a1-188">答案部分取决于拓扑和组织地理位置分布的部分。</span><span class="sxs-lookup"><span data-stu-id="f63a1-188">The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

  <span data-ttu-id="f63a1-189">你还应考虑网关拓扑选项（有关详细信息，请参阅本主题后面的网关拓扑）。</span><span class="sxs-lookup"><span data-stu-id="f63a1-189">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

#### <a name="mn-trunk-support"></a><span data-ttu-id="f63a1-190">M:N 中继支持</span><span class="sxs-lookup"><span data-stu-id="f63a1-190">M:N Trunk Support</span></span>

<span data-ttu-id="f63a1-191">中介服务器可通过多个网关、由 Internet 电话服务提供商提供的会话边界控制器（SBCs）或这两者的组合来路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="f63a1-191">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="f63a1-192">此外，池中的多个中介服务器可以与多个网关交互。</span><span class="sxs-lookup"><span data-stu-id="f63a1-192">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="f63a1-193">在中介服务器和网关之间定义的逻辑路由称为主干。</span><span class="sxs-lookup"><span data-stu-id="f63a1-193">The logical route defined between a Mediation Server and gateway is called a trunk.</span></span> <span data-ttu-id="f63a1-194">当内部用户置入 PSTN 呼叫时，前端池上的出站路由逻辑将选择哪些干线路由到可能可用于路由特定呼叫的所有可能的组合。</span><span class="sxs-lookup"><span data-stu-id="f63a1-194">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="f63a1-195">使用 DNS 负载平衡，如果由于池中的特定中介服务器出现问题而导致呼叫无法到达网关，则会将该呼叫重试到池中的备用中介服务器。</span><span class="sxs-lookup"><span data-stu-id="f63a1-195">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="f63a1-196">有关规划多个网关的详细信息，请参阅[Skype For Business 服务器中的 M:N 主干](m-n-trunk.md)。</span><span class="sxs-lookup"><span data-stu-id="f63a1-196">For details about planning for multiple gateways, see [M:N trunk in Skype for Business Server](m-n-trunk.md).</span></span>

<span data-ttu-id="f63a1-197">有关其他出站路由增强的详细信息，请参阅[呼叫路由](https://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f63a1-197">For details about other outbound routing enhancements, see [Call Routes](https://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx).</span></span>

#### <a name="gateway-topologies"></a><span data-ttu-id="f63a1-198">网关拓扑</span><span class="sxs-lookup"><span data-stu-id="f63a1-198">Gateway Topologies</span></span>

<span data-ttu-id="f63a1-199">考虑网关部署的基本问题时，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="f63a1-199">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1. <span data-ttu-id="f63a1-200">使用企业语音对要提供 PSTN 连接的站点进行计数。</span><span class="sxs-lookup"><span data-stu-id="f63a1-200">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2. <span data-ttu-id="f63a1-201">估计每个网站上的流量（用户数和每个用户每小时平均通话数）。</span><span class="sxs-lookup"><span data-stu-id="f63a1-201">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3. <span data-ttu-id="f63a1-202">在每个站点部署一个或多个网关以处理预期的流量。</span><span class="sxs-lookup"><span data-stu-id="f63a1-202">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="f63a1-203">在此拓扑中，每个站点和站点之间的工作人员之间的通话均通过 intranet 进行路由。</span><span class="sxs-lookup"><span data-stu-id="f63a1-203">With this topology, calls among workers at each site and between sites are all routed over your intranet.</span></span> <span data-ttu-id="f63a1-204">对 PSTN 的调用通过企业 IP 网络路由到最接近目标号码位置的网关。但是，如果您的组织支持数十个或成百上千个站点分布在一个或多个洲内，那么许多金融机构和其他大型企业都有这些功能？</span><span class="sxs-lookup"><span data-stu-id="f63a1-204">Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do?</span></span> <span data-ttu-id="f63a1-205">在这种情况下，在每个网站上部署单独的网关是不切实际的。</span><span class="sxs-lookup"><span data-stu-id="f63a1-205">In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="f63a1-206">为了解决此问题，许多大型公司更喜欢部署一个或几个大型电话中心站点。</span><span class="sxs-lookup"><span data-stu-id="f63a1-206">To address this issue, many large companies prefer to deploy one or a few large telephony central sites.</span></span>

<span data-ttu-id="f63a1-207">在此拓扑中，将在每个中心站点上部署几个大型网关，足以容纳预期的用户负载。</span><span class="sxs-lookup"><span data-stu-id="f63a1-207">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="f63a1-208">对企业中的用户的所有呼叫均由公司的电话服务提供商转发到中央站点。</span><span class="sxs-lookup"><span data-stu-id="f63a1-208">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="f63a1-209">中心网站上的路由逻辑确定是否应通过 intranet 或 PSTN 路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="f63a1-209">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

#### <a name="gateway-location"></a><span data-ttu-id="f63a1-210">网关位置</span><span class="sxs-lookup"><span data-stu-id="f63a1-210">Gateway Location</span></span>

<span data-ttu-id="f63a1-211">网关位置还可以确定你选择的网关类型以及它们的配置方式。</span><span class="sxs-lookup"><span data-stu-id="f63a1-211">Gateway location may also determine the types of gateways that you choose and how they are configured.</span></span> <span data-ttu-id="f63a1-212">有许多 PSTN 协议，它们都不是全球标准。</span><span class="sxs-lookup"><span data-stu-id="f63a1-212">There are dozens of PSTN protocols, none of which is a worldwide standard.</span></span> <span data-ttu-id="f63a1-213">如果你的所有网关均位于单个国家/地区，则不会出现问题，但如果你在多个国家/地区中找到网关，则每个国家/地区都必须根据该国家/地区的 PSTN 标准进行配置。</span><span class="sxs-lookup"><span data-stu-id="f63a1-213">If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region.</span></span> <span data-ttu-id="f63a1-214">此外，为在加拿大（例如加拿大）内操作认证的网关可能未在印度、巴西或欧盟进行认证。</span><span class="sxs-lookup"><span data-stu-id="f63a1-214">Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

#### <a name="gateway-size-and-number"></a><span data-ttu-id="f63a1-215">网关大小和号码</span><span class="sxs-lookup"><span data-stu-id="f63a1-215">Gateway Size and Number</span></span>

<span data-ttu-id="f63a1-216">大多数组织都将考虑从2到多达960端口部署范围内的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="f63a1-216">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports.</span></span> <span data-ttu-id="f63a1-217">（甚至更大的网关，但主要由电话服务提供商使用。）估计你的组织所需的端口数时，请使用以下指南：</span><span class="sxs-lookup"><span data-stu-id="f63a1-217">(There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

- <span data-ttu-id="f63a1-218">具有轻型电话使用的组织（每个用户每小时一个 PSTN 呼叫）应该为每15个用户分配一个端口。</span><span class="sxs-lookup"><span data-stu-id="f63a1-218">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users.</span></span> <span data-ttu-id="f63a1-219">例如，如果您有20个用户，将需要一个具有两个端口的网关。</span><span class="sxs-lookup"><span data-stu-id="f63a1-219">For example, if you have 20 users, you will require a gateway with two ports.</span></span>

- <span data-ttu-id="f63a1-220">具有中等电话服务使用率（每个用户每小时两个 PSTN 呼叫）的组织应为每10个用户分配一个端口。</span><span class="sxs-lookup"><span data-stu-id="f63a1-220">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users.</span></span> <span data-ttu-id="f63a1-221">例如，如果您有100用户，那么您将需要在一个或多个网关之间分配10个端口。</span><span class="sxs-lookup"><span data-stu-id="f63a1-221">For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

- <span data-ttu-id="f63a1-222">使用大量电话服务的组织（每个用户每小时的三个或更多 PSTN 呼叫）应为每五个用户分配一个端口。</span><span class="sxs-lookup"><span data-stu-id="f63a1-222">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users.</span></span> <span data-ttu-id="f63a1-223">例如，如果您有47000用户，则需要在至少10个大型网关之间分配的9400端口总数。</span><span class="sxs-lookup"><span data-stu-id="f63a1-223">For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

- <span data-ttu-id="f63a1-224">在您的组织中增加的用户数或您的组织中的流量量增加时，可以获得其他端口。</span><span class="sxs-lookup"><span data-stu-id="f63a1-224">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="f63a1-225">对于任何必须支持的用户数，您可以选择部署较少、更大的网关或较小的网关。</span><span class="sxs-lookup"><span data-stu-id="f63a1-225">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones.</span></span> <span data-ttu-id="f63a1-226">通常，建议组织至少两个网关，以便在一个网关出现故障时保持可用性。</span><span class="sxs-lookup"><span data-stu-id="f63a1-226">As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="f63a1-227">你部署的每个 PSTN 网关都必须至少有一个对应的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="f63a1-227">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>


