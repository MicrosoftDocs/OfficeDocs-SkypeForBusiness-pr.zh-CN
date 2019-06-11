---
title: Lync Server 2013：直接 SIP 部署选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 277b64346dc17815438f2ac34da58f36d2b150f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a><span data-ttu-id="9b906-102">Lync Server 2013 中的直接 SIP 部署选项</span><span class="sxs-lookup"><span data-stu-id="9b906-102">Direct SIP deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b906-103">_**主题上次修改时间:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9b906-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="9b906-104">本主题提供了部署直接 SIP 连接的示例拓扑。</span><span class="sxs-lookup"><span data-stu-id="9b906-104">This topic provides example topologies for deploying direct SIP connections.</span></span>

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a><span data-ttu-id="9b906-105">Lync Server 独立版</span><span class="sxs-lookup"><span data-stu-id="9b906-105">Lync Server Stand-Alone</span></span>

<span data-ttu-id="9b906-106">如果你的组织使用本部分中介绍的部署之一, 则可以使用 Lync Server 2013 作为组织的部分或全部的唯一电话服务解决方案。</span><span class="sxs-lookup"><span data-stu-id="9b906-106">If your organization uses one of the deployments described in this section, you can use Lync Server 2013 as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="9b906-107">本部分详细介绍以下部署:</span><span class="sxs-lookup"><span data-stu-id="9b906-107">This section describes the following deployments in detail:</span></span>

  - <span data-ttu-id="9b906-108">**增量部署:** 此选项假设你有现有的专用分支 exchange (PBX) 基础结构, 并且想要将企业语音增量引入组织内较小的组或团队。</span><span class="sxs-lookup"><span data-stu-id="9b906-108">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

  - <span data-ttu-id="9b906-109">**Lync Server VoIP-仅限 VoIP 部署:** 此选项假设你正在考虑在没有传统的电话基础结构的网站上部署企业语音。</span><span class="sxs-lookup"><span data-stu-id="9b906-109">**Lync Server VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

<div>

## <a name="incremental-deployment"></a><span data-ttu-id="9b906-110">增量部署</span><span class="sxs-lookup"><span data-stu-id="9b906-110">Incremental Deployment</span></span>

<span data-ttu-id="9b906-111">在增量部署中, Lync Server 2013 是单个团队或部门的唯一电话服务解决方案, 而组织中的其他用户仍在使用 PBX。</span><span class="sxs-lookup"><span data-stu-id="9b906-111">In incremental deployment, Lync Server 2013 is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="9b906-112">此增量部署策略提供了一种通过受控试点计划在企业中引入 IP 电话的方法。</span><span class="sxs-lookup"><span data-stu-id="9b906-112">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="9b906-113">Microsoft 统一通信最适合使用其通信需求的工作组被移动到企业语音, 而其他用户则保留在现有 PBX 上。</span><span class="sxs-lookup"><span data-stu-id="9b906-113">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="9b906-114">可根据需要将其他工作组迁移到企业语音。</span><span class="sxs-lookup"><span data-stu-id="9b906-114">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="9b906-115">如果明确定义的用户组具有共同的通信要求, 并且该用户组适用于集中管理, 则建议使用 "增量" 选项。</span><span class="sxs-lookup"><span data-stu-id="9b906-115">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="9b906-116">如果你有团队或部门分布在地理区域上方, 而您的长途费用成本可能很大, 此选项也很有效。</span><span class="sxs-lookup"><span data-stu-id="9b906-116">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="9b906-117">实际上, 此选项对于创建其成员可能分散在全球各地的虚拟团队非常有用。</span><span class="sxs-lookup"><span data-stu-id="9b906-117">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="9b906-118">你可以创建、修改或解散此类团队, 以便快速响应对业务需求的变化。</span><span class="sxs-lookup"><span data-stu-id="9b906-118">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="9b906-119">下图显示了用于在 PBX 背后部署企业语音的一般拓扑。</span><span class="sxs-lookup"><span data-stu-id="9b906-119">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="9b906-120">这是增量部署的推荐拓扑。</span><span class="sxs-lookup"><span data-stu-id="9b906-120">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="9b906-121">**增量部署选项**</span><span class="sxs-lookup"><span data-stu-id="9b906-121">**Incremental deployment option**</span></span>

<span data-ttu-id="9b906-122">![部门迁移选项图表](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "部门迁移选项图表")</span><span class="sxs-lookup"><span data-stu-id="9b906-122">![Departmental Migration Option diagram](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Departmental Migration Option diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9b906-123">如果您将 Lync Server 部署连接到认证的直接 SIP 合作伙伴, 则不需要在中介服务器和 PBX 之间使用公共交换式电话网络 (PSTN) 网关。</span><span class="sxs-lookup"><span data-stu-id="9b906-123">If you are connecting your Lync Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="9b906-124">有关认证直接 SIP 合作伙伴的列表, 请参阅 Microsoft 统一通信打开互操作性计划网站<A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>。</span><span class="sxs-lookup"><span data-stu-id="9b906-124">For a list of certified Direct SIP partners, see the Microsoft Unified Communications Open Interoperability Program website at <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="9b906-125">此图所示的媒体路径启用了媒体旁路 (推荐配置)。</span><span class="sxs-lookup"><span data-stu-id="9b906-125">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="9b906-126">如果选择禁用 "绕过媒体", 则媒体路径将通过中介服务器进行路由。</span><span class="sxs-lookup"><span data-stu-id="9b906-126">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

<span data-ttu-id="9b906-127">在此拓扑中, 将为企业语音启用选定的部门或工作组。</span><span class="sxs-lookup"><span data-stu-id="9b906-127">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="9b906-128">PSTN 网关将启用了 Internet 协议 (VoIP) 的工作组的语音链接到 PBX。</span><span class="sxs-lookup"><span data-stu-id="9b906-128">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="9b906-129">已启用企业语音的用户 (包括远程工作人员) 通过 IP 网络进行通信。</span><span class="sxs-lookup"><span data-stu-id="9b906-129">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="9b906-130">通过企业语音用户呼叫 PSTN 和未启用企业语音的同事将路由到相应的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="9b906-130">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="9b906-131">来自仍在 PBX 系统或来自 PSTN 的呼叫者的同事的呼叫将路由到 PSTN 网关, 该网关会将呼叫转发到 Lync 服务器进行路由。</span><span class="sxs-lookup"><span data-stu-id="9b906-131">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Lync Server for routing.</span></span>

<span data-ttu-id="9b906-132">有两种推荐配置, 可用于将企业语音连接到现有 PBX 基础结构以实现互操作: 在 PBX 前面的 PBX 和企业语音背后的企业语音。</span><span class="sxs-lookup"><span data-stu-id="9b906-132">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

<div>

## <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="9b906-133">PBX 背后的企业语音</span><span class="sxs-lookup"><span data-stu-id="9b906-133">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="9b906-134">当企业语音部署在 PBX 背后时, PSTN 的所有调用都将到达 PBX, 它将呼叫企业语音用户到 PSTN 网关, 并与 pbx 用户通话。</span><span class="sxs-lookup"><span data-stu-id="9b906-134">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="9b906-135">PBX 前面的企业语音</span><span class="sxs-lookup"><span data-stu-id="9b906-135">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="9b906-136">如果在 PBX 前面部署了企业语音, 所有通话都将进入 PSTN 网关, 该网关会将企业语音用户的呼叫路由到 Lync Server, 并将 PBX 用户与 PBX 通话。</span><span class="sxs-lookup"><span data-stu-id="9b906-136">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Lync Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="9b906-137">从企业语音和 PBX 用户到 PSTN 的通话均通过 IP 网络路由到最经济高效的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="9b906-137">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="9b906-138">下表显示了此配置的优点和缺点。</span><span class="sxs-lookup"><span data-stu-id="9b906-138">The following table shows the advantages and disadvantages of this configuration.</span></span>

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a><span data-ttu-id="9b906-139">在 PBX 前面部署企业语音的优点和缺点</span><span class="sxs-lookup"><span data-stu-id="9b906-139">Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b906-140">最终</span><span class="sxs-lookup"><span data-stu-id="9b906-140">Advantages</span></span></th>
<th><span data-ttu-id="9b906-141">一些</span><span class="sxs-lookup"><span data-stu-id="9b906-141">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b906-142">PBX 仍可为未启用企业语音的用户提供服务。</span><span class="sxs-lookup"><span data-stu-id="9b906-142">PBX still serves users not enabled for Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="9b906-143">现有网关可能不支持所需的功能或容量。</span><span class="sxs-lookup"><span data-stu-id="9b906-143">Existing gateways may not support the features or capacity that you want.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b906-144">PBX 处理所有较早的设备。</span><span class="sxs-lookup"><span data-stu-id="9b906-144">PBX handles all earlier devices.</span></span></p></td>
<td><p><span data-ttu-id="9b906-145">需要从 PBX 到 PBX 以及从网关到中介服务器的网关之间的主干。</span><span class="sxs-lookup"><span data-stu-id="9b906-145">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="9b906-146">您可能需要来自服务提供商的更多中继。</span><span class="sxs-lookup"><span data-stu-id="9b906-146">You may need more trunks from the service provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b906-147">企业语音用户保持相同的电话号码。</span><span class="sxs-lookup"><span data-stu-id="9b906-147">Enterprise Voice users keep the same phone numbers.</span></span></p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a><span data-ttu-id="9b906-148">Lync Server 仅 VoIP 部署</span><span class="sxs-lookup"><span data-stu-id="9b906-148">Lync Server VoIP-Only Deployment</span></span>

<span data-ttu-id="9b906-149">企业语音为现有企业提供新的企业和新的 office 网站, 从而实现了一个功能完备的 VoIP 解决方案, 而无需担心 PBX 集成或导致真正的部署和维护。IP PBX 基础结构的成本。</span><span class="sxs-lookup"><span data-stu-id="9b906-149">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="9b906-150">此解决方案支持现场和远程工作人员。</span><span class="sxs-lookup"><span data-stu-id="9b906-150">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="9b906-151">在此部署中, 所有通话都通过 IP 网络进行路由。</span><span class="sxs-lookup"><span data-stu-id="9b906-151">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="9b906-152">对 PSTN 的调用将路由到相应的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="9b906-152">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="9b906-153">Lync 2013 或 Lync Phone Edition 用作 softphone。</span><span class="sxs-lookup"><span data-stu-id="9b906-153">Lync 2013 or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="9b906-154">远程呼叫控制不可用, 因为没有可供用户控制的 PBX 手机。</span><span class="sxs-lookup"><span data-stu-id="9b906-154">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="9b906-155">通过 Exchange 统一消息 (UM) 的可选部署提供语音邮件和自动助理服务。</span><span class="sxs-lookup"><span data-stu-id="9b906-155">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9b906-156">除了支持 Lync Server 2013 所需的网络基础结构之外, 仅有 VoIP 的部署可以使用小型的合格网关来支持传真机和模拟设备。</span><span class="sxs-lookup"><span data-stu-id="9b906-156">In addition to the network infrastructure that is required to support Lync Server 2013, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>



</div>

<span data-ttu-id="9b906-157">下图显示了仅限 VoIP 的部署的典型拓扑。</span><span class="sxs-lookup"><span data-stu-id="9b906-157">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="9b906-158">**仅限 VoIP 的部署选项**</span><span class="sxs-lookup"><span data-stu-id="9b906-158">**VoIP-only deployment option**</span></span>

<span data-ttu-id="9b906-159">![Greenfidle 部署选项](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle 部署选项")</span><span class="sxs-lookup"><span data-stu-id="9b906-159">![Greenfidle deployment option](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle deployment option")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9b906-160">此图所示的媒体路径启用了媒体旁路 (推荐配置)。</span><span class="sxs-lookup"><span data-stu-id="9b906-160">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="9b906-161">如果选择禁用 "绕过媒体", 则媒体路径将通过中介服务器进行路由。</span><span class="sxs-lookup"><span data-stu-id="9b906-161">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

