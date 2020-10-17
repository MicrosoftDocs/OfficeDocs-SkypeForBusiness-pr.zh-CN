---
title: Lync Server 2013：直接 SIP 部署选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aaecb9bd7b5fc4f144236f83f85f9e1e192784f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529109"
---
# <a name="direct-sip-deployment-options-in-lync-server-2013"></a><span data-ttu-id="c322e-102">Lync Server 2013 中的直接 SIP 部署选项</span><span class="sxs-lookup"><span data-stu-id="c322e-102">Direct SIP deployment options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c322e-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c322e-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c322e-104">本主题提供了部署直接 SIP 连接的示例拓扑。</span><span class="sxs-lookup"><span data-stu-id="c322e-104">This topic provides example topologies for deploying direct SIP connections.</span></span>

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a><span data-ttu-id="c322e-105">Lync Server Stand-Alone</span><span class="sxs-lookup"><span data-stu-id="c322e-105">Lync Server Stand-Alone</span></span>

<span data-ttu-id="c322e-106">如果您的组织使用本节中介绍的某个部署，则可以使用 Lync Server 2013 作为组织的部分或全部的唯一电话解决方案。</span><span class="sxs-lookup"><span data-stu-id="c322e-106">If your organization uses one of the deployments described in this section, you can use Lync Server 2013 as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="c322e-107">本部分详细介绍了以下部署：</span><span class="sxs-lookup"><span data-stu-id="c322e-107">This section describes the following deployments in detail:</span></span>

  - <span data-ttu-id="c322e-108">**增量部署：** 此选项假设您有一个现有的专用分支 exchange (PBX) 基础结构，您打算将企业语音增量引入组织内较小的组或团队。</span><span class="sxs-lookup"><span data-stu-id="c322e-108">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

  - <span data-ttu-id="c322e-109">**Lync Server 仅限 VoIP 部署：** 此选项假定您正在考虑在没有传统电话基础结构的站点上部署企业语音。</span><span class="sxs-lookup"><span data-stu-id="c322e-109">**Lync Server VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

<div>

## <a name="incremental-deployment"></a><span data-ttu-id="c322e-110">增量部署</span><span class="sxs-lookup"><span data-stu-id="c322e-110">Incremental Deployment</span></span>

<span data-ttu-id="c322e-111">在增量部署中，Lync Server 2013 是单个团队或部门的唯一电话解决方案，而组织中的其他用户仍在使用 PBX。</span><span class="sxs-lookup"><span data-stu-id="c322e-111">In incremental deployment, Lync Server 2013 is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="c322e-112">此增量部署策略提供了一种通过受控制的试点计划将 IP 电话引入到企业中的方法。</span><span class="sxs-lookup"><span data-stu-id="c322e-112">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="c322e-113">Microsoft 统一通信最能满足其通信需求的工作组将移动到企业语音，而其他用户则仍保留在现有的 PBX 中。</span><span class="sxs-lookup"><span data-stu-id="c322e-113">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="c322e-114">根据需要，可以将其他工作组迁移到企业语音。</span><span class="sxs-lookup"><span data-stu-id="c322e-114">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="c322e-115">如果您明确定义了具有共同的通信要求并借给集中管理的用户组，则建议使用 "增量" 选项。</span><span class="sxs-lookup"><span data-stu-id="c322e-115">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="c322e-116">如果您的团队或部门分布在多个地理区域上，并且在长途费用中节省的成本很高，则此选项也很有效。</span><span class="sxs-lookup"><span data-stu-id="c322e-116">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="c322e-117">实际上，此选项对于创建可能分散在全球各地的成员的虚拟团队非常有用。</span><span class="sxs-lookup"><span data-stu-id="c322e-117">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="c322e-118">您可以创建、修改或 disband 此类团队，以快速响应移动的业务需求。</span><span class="sxs-lookup"><span data-stu-id="c322e-118">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="c322e-119">下图显示了用于在 PBX 背后部署企业语音的通用拓扑。</span><span class="sxs-lookup"><span data-stu-id="c322e-119">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="c322e-120">这是增量部署的推荐拓扑。</span><span class="sxs-lookup"><span data-stu-id="c322e-120">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="c322e-121">**增量部署选项**</span><span class="sxs-lookup"><span data-stu-id="c322e-121">**Incremental deployment option**</span></span>

<span data-ttu-id="c322e-122">![部门迁移选项关系图](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "部门迁移选项关系图")</span><span class="sxs-lookup"><span data-stu-id="c322e-122">![Departmental Migration Option diagram](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Departmental Migration Option diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c322e-123">如果要将 Lync Server 部署连接到认证的直接 SIP 合作伙伴，则不需要在中介服务器和 PBX 之间建立公用电话交换电话网络 (PSTN) 网关。</span><span class="sxs-lookup"><span data-stu-id="c322e-123">If you are connecting your Lync Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="c322e-124">有关认证的直接 SIP 合作伙伴的列表，请参阅 Microsoft 统一通信开放式互操作性计划网站，网址为 <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A> 。</span><span class="sxs-lookup"><span data-stu-id="c322e-124">For a list of certified Direct SIP partners, see the Microsoft Unified Communications Open Interoperability Program website at <A href="https://go.microsoft.com/fwlink/p/?linkid=203309">https://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c322e-125">此图中所示的媒体路径启用了媒体旁路 (建议的配置) 。</span><span class="sxs-lookup"><span data-stu-id="c322e-125">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="c322e-126">如果您选择禁用媒体旁路，媒体路径将通过中介服务器进行路由。</span><span class="sxs-lookup"><span data-stu-id="c322e-126">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

<span data-ttu-id="c322e-127">在此拓扑中，已为企业语音启用所选部门或工作组。</span><span class="sxs-lookup"><span data-stu-id="c322e-127">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="c322e-128">PSTN 网关将 (VoIP) 的工作组中的语音 over Internet 协议链接到 PBX。</span><span class="sxs-lookup"><span data-stu-id="c322e-128">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="c322e-129">启用企业语音的用户（包括远程工作人员）在 IP 网络中进行通信。</span><span class="sxs-lookup"><span data-stu-id="c322e-129">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="c322e-130">由企业语音用户对 PSTN 和未启用企业语音的合作者的呼叫将路由到相应的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="c322e-130">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="c322e-131">来自位于 PBX 系统或来自 PSTN 上的呼叫者的同事的呼叫将路由到 PSTN 网关，PSTN 网关会将呼叫转发到 Lync Server 进行路由。</span><span class="sxs-lookup"><span data-stu-id="c322e-131">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Lync Server for routing.</span></span>

<span data-ttu-id="c322e-132">有两种建议的配置，用于将企业语音连接到现有的 PBX 基础结构以实现互操作性： pbx 和 Enterprise voice in PBX 前端的企业语音。</span><span class="sxs-lookup"><span data-stu-id="c322e-132">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

<div>

## <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="c322e-133">PBX 背后的企业语音</span><span class="sxs-lookup"><span data-stu-id="c322e-133">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="c322e-134">在 PBX 后面部署企业语音时，PSTN 中的所有呼叫都将到达 PBX，后者将呼叫企业语音用户的所有呼叫路由到 PSTN 网关，并向 PBX 呼叫 PBX 用户。</span><span class="sxs-lookup"><span data-stu-id="c322e-134">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="c322e-135">PBX 前端的企业语音</span><span class="sxs-lookup"><span data-stu-id="c322e-135">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="c322e-136">在 PBX 前端部署企业语音时，所有呼叫都将到达 PSTN 网关，这会将企业语音用户的呼叫路由到 Lync Server，并呼叫 PBX 用户到 PBX。</span><span class="sxs-lookup"><span data-stu-id="c322e-136">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Lync Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="c322e-137">从企业语音和 PBX 用户对 PSTN 的调用通过 IP 网络路由到最经济高效的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="c322e-137">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="c322e-138">下表显示了此配置的优点和缺点。</span><span class="sxs-lookup"><span data-stu-id="c322e-138">The following table shows the advantages and disadvantages of this configuration.</span></span>

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a><span data-ttu-id="c322e-139">在 PBX 前端部署企业语音的优点和缺点</span><span class="sxs-lookup"><span data-stu-id="c322e-139">Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c322e-140">优点</span><span class="sxs-lookup"><span data-stu-id="c322e-140">Advantages</span></span></th>
<th><span data-ttu-id="c322e-141">缺点</span><span class="sxs-lookup"><span data-stu-id="c322e-141">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c322e-142">PBX 仍可为未启用企业语音的用户提供服务。</span><span class="sxs-lookup"><span data-stu-id="c322e-142">PBX still serves users not enabled for Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="c322e-143">现有网关可能不支持所需的功能或容量。</span><span class="sxs-lookup"><span data-stu-id="c322e-143">Existing gateways may not support the features or capacity that you want.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c322e-144">PBX 处理所有早期的设备。</span><span class="sxs-lookup"><span data-stu-id="c322e-144">PBX handles all earlier devices.</span></span></p></td>
<td><p><span data-ttu-id="c322e-145">需要从网关到 PBX 以及从网关到中介服务器的中继。</span><span class="sxs-lookup"><span data-stu-id="c322e-145">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="c322e-146">您可能需要来自服务提供商的更多中继。</span><span class="sxs-lookup"><span data-stu-id="c322e-146">You may need more trunks from the service provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c322e-147">企业语音用户保留相同的电话号码。</span><span class="sxs-lookup"><span data-stu-id="c322e-147">Enterprise Voice users keep the same phone numbers.</span></span></p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a><span data-ttu-id="c322e-148">Lync Server VoIP-Only 部署</span><span class="sxs-lookup"><span data-stu-id="c322e-148">Lync Server VoIP-Only Deployment</span></span>

<span data-ttu-id="c322e-149">企业语音为现有企业提供新的企业以及新的 office 网站，并有机会实施功能齐全的 VoIP 解决方案，而无需担心 PBX 集成或导致 IP PBX 基础结构的实际部署和维护成本。</span><span class="sxs-lookup"><span data-stu-id="c322e-149">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="c322e-150">此解决方案支持现场和远程工作人员。</span><span class="sxs-lookup"><span data-stu-id="c322e-150">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="c322e-151">在此部署中，所有呼叫都通过 IP 网络进行路由。</span><span class="sxs-lookup"><span data-stu-id="c322e-151">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="c322e-152">将对 PSTN 的呼叫路由到相应的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="c322e-152">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="c322e-153">Lync 2013 或 Lync Phone Edition 充当 softphone。</span><span class="sxs-lookup"><span data-stu-id="c322e-153">Lync 2013 or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="c322e-154">远程呼叫控制不可用且不必要，因为没有可供用户控制的 PBX 电话。</span><span class="sxs-lookup"><span data-stu-id="c322e-154">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="c322e-155">通过 Exchange 统一消息 (UM) 的可选部署，可以使用语音邮件和自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="c322e-155">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c322e-156">除了支持 Lync Server 2013 所需的网络基础结构之外，仅 VoIP 部署还可以使用小型的合格网关来支持传真机和模拟设备。</span><span class="sxs-lookup"><span data-stu-id="c322e-156">In addition to the network infrastructure that is required to support Lync Server 2013, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>



</div>

<span data-ttu-id="c322e-157">下图显示了仅限 VoIP 部署的典型拓扑。</span><span class="sxs-lookup"><span data-stu-id="c322e-157">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="c322e-158">**仅限 VoIP 的部署选项**</span><span class="sxs-lookup"><span data-stu-id="c322e-158">**VoIP-only deployment option**</span></span>

<span data-ttu-id="c322e-159">![Greenfidle 部署选项](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle 部署选项")</span><span class="sxs-lookup"><span data-stu-id="c322e-159">![Greenfidle deployment option](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle deployment option")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c322e-160">此图中所示的媒体路径启用了媒体旁路 (建议的配置) 。</span><span class="sxs-lookup"><span data-stu-id="c322e-160">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="c322e-161">如果您选择禁用媒体旁路，媒体路径将通过中介服务器进行路由。</span><span class="sxs-lookup"><span data-stu-id="c322e-161">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

