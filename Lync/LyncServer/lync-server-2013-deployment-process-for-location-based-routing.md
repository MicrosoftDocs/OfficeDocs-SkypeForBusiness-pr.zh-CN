---
title: Lync Server 2013：基于位置的路由的部署过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46da1be1d18477d56fa4b3046557102e8771ef68
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="576ac-102">Lync Server 2013 中基于位置的路由的部署过程</span><span class="sxs-lookup"><span data-stu-id="576ac-102">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="576ac-103">_**上次修改的主题：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="576ac-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="576ac-104">本主题概述了配置基于位置的路由过程中涉及的过程。</span><span class="sxs-lookup"><span data-stu-id="576ac-104">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="576ac-105">在配置基于位置的路由之前，必须部署 Lync Server Enterprise Edition 或 Standard Edition 和 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="576ac-105">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="576ac-106">在部署企业语音时，已安装并启用基于位置的路由所需的组件。</span><span class="sxs-lookup"><span data-stu-id="576ac-106">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="576ac-107">基于位置的路由部署过程</span><span class="sxs-lookup"><span data-stu-id="576ac-107">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="576ac-108">阶段</span><span class="sxs-lookup"><span data-stu-id="576ac-108">Phase</span></span></th>
<th><span data-ttu-id="576ac-109">步骤</span><span class="sxs-lookup"><span data-stu-id="576ac-109">Steps</span></span></th>
<th><span data-ttu-id="576ac-110">所需的组和角色</span><span class="sxs-lookup"><span data-stu-id="576ac-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="576ac-111">部署文档</span><span class="sxs-lookup"><span data-stu-id="576ac-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="576ac-112">部署企业语音</span><span class="sxs-lookup"><span data-stu-id="576ac-112">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="576ac-113">配置中继</span><span class="sxs-lookup"><span data-stu-id="576ac-113">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="576ac-114">创建语音策略</span><span class="sxs-lookup"><span data-stu-id="576ac-114">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="576ac-115">定义语音路由</span><span class="sxs-lookup"><span data-stu-id="576ac-115">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="576ac-116">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="576ac-116">CSVoiceAdmins</span></span><br />
<span data-ttu-id="576ac-117">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="576ac-117">CsAdministrator</span></span><br />
<span data-ttu-id="576ac-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="576ac-118">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="576ac-119">部署企业语音</span><span class="sxs-lookup"><span data-stu-id="576ac-119">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ac-120">验证您的企业语音部署</span><span class="sxs-lookup"><span data-stu-id="576ac-120">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="576ac-121">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="576ac-121">CSVoiceAdmins</span></span><br />
<span data-ttu-id="576ac-122">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="576ac-122">CsAdministrator</span></span><br />
<span data-ttu-id="576ac-123">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="576ac-123">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="576ac-124">配置网络区域、站点和子网</span><span class="sxs-lookup"><span data-stu-id="576ac-124">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="576ac-125">创建网络区域</span><span class="sxs-lookup"><span data-stu-id="576ac-125">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="576ac-126">创建网络站点</span><span class="sxs-lookup"><span data-stu-id="576ac-126">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="576ac-127">将子网与网络站点关联</span><span class="sxs-lookup"><span data-stu-id="576ac-127">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="576ac-128">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="576ac-128">CSVoiceAdmins</span></span><br />
<span data-ttu-id="576ac-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="576ac-129">CsAdministrator</span></span><br />
<span data-ttu-id="576ac-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="576ac-130">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="576ac-131">关于网络区域、站点和子网</span><span class="sxs-lookup"><span data-stu-id="576ac-131">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="576ac-132">创建或修改网络区域</span><span class="sxs-lookup"><span data-stu-id="576ac-132">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="576ac-133">创建或修改网络站点</span><span class="sxs-lookup"><span data-stu-id="576ac-133">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="576ac-134">将子网与网络站点相关联</span><span class="sxs-lookup"><span data-stu-id="576ac-134">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ac-135">配置基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="576ac-135">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="576ac-136">创建语音路由策略</span><span class="sxs-lookup"><span data-stu-id="576ac-136">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="576ac-137">为每个中继定义单独的中继配置</span><span class="sxs-lookup"><span data-stu-id="576ac-137">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="576ac-138">修改语音策略</span><span class="sxs-lookup"><span data-stu-id="576ac-138">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="576ac-139">启用基于位置的路由配置</span><span class="sxs-lookup"><span data-stu-id="576ac-139">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="576ac-140">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="576ac-140">CSVoiceAdmins</span></span><br />
<span data-ttu-id="576ac-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="576ac-141">CsAdministrator</span></span><br />
<span data-ttu-id="576ac-142">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="576ac-142">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="576ac-143">示例部署</span><span class="sxs-lookup"><span data-stu-id="576ac-143">Sample Deployment</span></span>

<span data-ttu-id="576ac-144">以下部署用于进一步说明基于位置的路由启用的机制。</span><span class="sxs-lookup"><span data-stu-id="576ac-144">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="576ac-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="576ac-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="576ac-146">传入 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="576ac-146">Incoming PSTN calls</span></span>

<span data-ttu-id="576ac-147">管理员可以使已定义的中继将呼叫路由到 "Site 1 Gateway" 以进行基于位置的路由，并将 "Site 1 Gateway" 与 Site 1 相关联。</span><span class="sxs-lookup"><span data-stu-id="576ac-147">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="576ac-148">启用后，通过 "Site 1 Gateway" 路由的呼叫将仅路由到位于站点1中的用户。</span><span class="sxs-lookup"><span data-stu-id="576ac-148">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="576ac-149">通过 "Site 1 Gateway" 中继路由到其他站点中的用户的所有呼叫，如 Site 2 将受到阻止，以防止 PSTN 收费旁路。</span><span class="sxs-lookup"><span data-stu-id="576ac-149">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="576ac-150">通过 "Site 1 Gateway" 进行的所有传入 PSTN 呼叫仅允许路由到站点1中的终结点。</span><span class="sxs-lookup"><span data-stu-id="576ac-150">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="576ac-151">例如，当 "Lync user 1" 向站点2传播时，通过 "Site 1 Gateway" 进行的所有传入 PSTN 呼叫将不会路由到站点2中的 "Lync 用户 1" 终结点。</span><span class="sxs-lookup"><span data-stu-id="576ac-151">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="576ac-152">如果 "Lync user 1" 传播到无法确定用户位置的未知网络站点，则应用相同的路由规则。</span><span class="sxs-lookup"><span data-stu-id="576ac-152">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="576ac-153">下表概述了此上下文中的 "Lync 用户 1" 的用户体验。</span><span class="sxs-lookup"><span data-stu-id="576ac-153">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="576ac-154">位于网络站点1的 Lync 用户1终结点</span><span class="sxs-lookup"><span data-stu-id="576ac-154">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="576ac-155">位于网络站点2中的 Lync 用户1终结点</span><span class="sxs-lookup"><span data-stu-id="576ac-155">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="576ac-156">位于未知网络站点中的 Lync 用户1终结点</span><span class="sxs-lookup"><span data-stu-id="576ac-156">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="576ac-157">对 Lync 用户1的入站 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="576ac-157">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="576ac-158">将呼叫路由到此位置中的终结点</span><span class="sxs-lookup"><span data-stu-id="576ac-158">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="576ac-159">呼叫不会路由到此位置中的终结点</span><span class="sxs-lookup"><span data-stu-id="576ac-159">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="576ac-160">呼叫不会路由到此位置中的终结点</span><span class="sxs-lookup"><span data-stu-id="576ac-160">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="576ac-161">传出 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="576ac-161">Outgoing PSTN calls</span></span>

<span data-ttu-id="576ac-162">在直接分配给用户的语音策略和分配给网络站点的语音路由策略中引用语音路由。</span><span class="sxs-lookup"><span data-stu-id="576ac-162">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="576ac-163">这两个策略都包含对路由的引用，可用于以不同的方式路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="576ac-163">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="576ac-164">例如，管理员可以为位于网络站点1中的所有用户定义一个语音路由策略，以便通过 "Site 1 Gateway" 路由所有出站呼叫，而某些用户的语音策略为所有出站呼叫通过 "Site 2 Gateway" 定义路由。</span><span class="sxs-lookup"><span data-stu-id="576ac-164">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="576ac-165">虽然这些用户位于网络站点1中，但其出站呼叫将通过 "Site 1 Gateway" 路由。</span><span class="sxs-lookup"><span data-stu-id="576ac-165">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="576ac-166">当用户位于配置为基于位置的路由的网络站点中时，网络站点的语音路由策略路由将覆盖用户的语音策略路由。</span><span class="sxs-lookup"><span data-stu-id="576ac-166">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="576ac-167">此规则对于临时移到不同网站的用户尤其有用。</span><span class="sxs-lookup"><span data-stu-id="576ac-167">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="576ac-168">在此特定情况下，用户将始终使用本地到其位置的网关;如果 "Lync user 3" 位于 "Site 2"，则所有出站呼叫都将通过 "Site 2 Gateway 路由"，但如果他转到站点1，则其在站点1处发出的所有出站呼叫将通过 "Site 1 Gateway" 路由。</span><span class="sxs-lookup"><span data-stu-id="576ac-168">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="576ac-169">下表说明了 Lync 用户1发出来自以下网络站点的出站呼叫的用户体验。</span><span class="sxs-lookup"><span data-stu-id="576ac-169">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="576ac-170">网络站点1</span><span class="sxs-lookup"><span data-stu-id="576ac-170">Network site 1</span></span></th>
<th><span data-ttu-id="576ac-171">网络站点2</span><span class="sxs-lookup"><span data-stu-id="576ac-171">Network site 2</span></span></th>
<th><span data-ttu-id="576ac-172">未知网络站点或未启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="576ac-172">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="576ac-173">出站呼叫的授权</span><span class="sxs-lookup"><span data-stu-id="576ac-173">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="576ac-174">Lync 用户1语音策略</span><span class="sxs-lookup"><span data-stu-id="576ac-174">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="576ac-175">Lync 用户1语音策略</span><span class="sxs-lookup"><span data-stu-id="576ac-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="576ac-176">Lync 用户1语音策略</span><span class="sxs-lookup"><span data-stu-id="576ac-176">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="576ac-177">出站呼叫的路由</span><span class="sxs-lookup"><span data-stu-id="576ac-177">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="576ac-178">站点1语音路由策略</span><span class="sxs-lookup"><span data-stu-id="576ac-178">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="576ac-179">站点2语音路由策略</span><span class="sxs-lookup"><span data-stu-id="576ac-179">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="576ac-180">用户的语音策略，并且仅对未启用基于位置的路由的系统</span><span class="sxs-lookup"><span data-stu-id="576ac-180">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="576ac-181">呼叫转移和转发</span><span class="sxs-lookup"><span data-stu-id="576ac-181">Call transfers and forwards</span></span>

<span data-ttu-id="576ac-182">当转接或转接呼叫时，呼叫的路由受基于位置的路由的影响。</span><span class="sxs-lookup"><span data-stu-id="576ac-182">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="576ac-183">下表描述了 Lync 用户1将 PSTN 呼叫转移或转发给另一个 Lync 用户的情况。</span><span class="sxs-lookup"><span data-stu-id="576ac-183">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="576ac-184">用户启动呼叫转移或转发</span><span class="sxs-lookup"><span data-stu-id="576ac-184">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="576ac-185">Lync 用户2</span><span class="sxs-lookup"><span data-stu-id="576ac-185">Lync user 2</span></span></th>
<th><span data-ttu-id="576ac-186">Lync 用户4</span><span class="sxs-lookup"><span data-stu-id="576ac-186">Lync user 4</span></span></th>
<th><span data-ttu-id="576ac-187">未对网络站点中的 Lync 用户启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="576ac-187">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="576ac-188">Lync 用户1</span><span class="sxs-lookup"><span data-stu-id="576ac-188">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="576ac-189">允许呼叫转接或转接</span><span class="sxs-lookup"><span data-stu-id="576ac-189">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="576ac-190">不允许呼叫转接或转接</span><span class="sxs-lookup"><span data-stu-id="576ac-190">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="576ac-191">不允许呼叫转接或转接</span><span class="sxs-lookup"><span data-stu-id="576ac-191">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="576ac-192">下表说明了基于位置的路由如何根据要转移的 Lync 用户的位置（Lync user 2、Lync user 4 等）将呼叫路由到 PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="576ac-192">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="576ac-193">呼叫转接到或转发到的终结点</span><span class="sxs-lookup"><span data-stu-id="576ac-193">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="576ac-194">Lync 用户2</span><span class="sxs-lookup"><span data-stu-id="576ac-194">Lync user 2</span></span></th>
<th><span data-ttu-id="576ac-195">Lync 用户4</span><span class="sxs-lookup"><span data-stu-id="576ac-195">Lync user 4</span></span></th>
<th><span data-ttu-id="576ac-196">未对网络站点中的 Lync 用户启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="576ac-196">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="576ac-197">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="576ac-197">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="576ac-198">呼叫转接或转接通过站点1语音路由策略和通过站点1网关的传出进行路由</span><span class="sxs-lookup"><span data-stu-id="576ac-198">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="576ac-199">呼叫转接或转接通过站点2语音路由策略和通过站点2网关的传出进行路由</span><span class="sxs-lookup"><span data-stu-id="576ac-199">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="576ac-200">通过 Lync 用户语音策略和通过未启用基于位置的路由的网关（如果可用）传递传出的呼叫转接或转移</span><span class="sxs-lookup"><span data-stu-id="576ac-200">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="576ac-201">同时响铃</span><span class="sxs-lookup"><span data-stu-id="576ac-201">Simultaneous ringing</span></span>

<span data-ttu-id="576ac-202">在示例拓扑中配置基于位置的路由后，将强制执行以下交互操作。</span><span class="sxs-lookup"><span data-stu-id="576ac-202">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="576ac-203">下表说明了基于位置的路由是否允许不同 Lync 用户同时响铃（例如，Lync 用户2、Lync 用户4等）。</span><span class="sxs-lookup"><span data-stu-id="576ac-203">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="576ac-204">传入 PSTN 呼叫目标</span><span class="sxs-lookup"><span data-stu-id="576ac-204">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="576ac-205">Lync 用户2</span><span class="sxs-lookup"><span data-stu-id="576ac-205">Lync user 2</span></span></th>
<th><span data-ttu-id="576ac-206">Lync 用户4</span><span class="sxs-lookup"><span data-stu-id="576ac-206">Lync user 4</span></span></th>
<th><span data-ttu-id="576ac-207">未对网络站点中的 Lync 用户启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="576ac-207">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="576ac-208">Lync 用户1</span><span class="sxs-lookup"><span data-stu-id="576ac-208">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="576ac-209">允许同时振铃</span><span class="sxs-lookup"><span data-stu-id="576ac-209">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="576ac-210">不允许同时响铃</span><span class="sxs-lookup"><span data-stu-id="576ac-210">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="576ac-211">不允许同时响铃</span><span class="sxs-lookup"><span data-stu-id="576ac-211">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="576ac-212">下表说明了基于位置的路由是否允许从不同 Lync 用户同时响铃到 PSTN 终结点（例如，Lync user 2、Lync user 4 等）。</span><span class="sxs-lookup"><span data-stu-id="576ac-212">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="576ac-213">同时振铃目标</span><span class="sxs-lookup"><span data-stu-id="576ac-213">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="576ac-214">Lync 用户2</span><span class="sxs-lookup"><span data-stu-id="576ac-214">Lync user 2</span></span></th>
<th><span data-ttu-id="576ac-215">Lync 用户4</span><span class="sxs-lookup"><span data-stu-id="576ac-215">Lync user 4</span></span></th>
<th><span data-ttu-id="576ac-216">未对网络站点中的 Lync 用户启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="576ac-216">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="576ac-217">Lync 用户1移动电话（PSTN 终结点）</span><span class="sxs-lookup"><span data-stu-id="576ac-217">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="576ac-218">通过网络站点1的语音路由策略进行的呼叫路由，通过站点1网关进行的传出</span><span class="sxs-lookup"><span data-stu-id="576ac-218">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="576ac-219">通过网络站点2的语音路由策略和通过站点2网关进行的传出路由的呼叫</span><span class="sxs-lookup"><span data-stu-id="576ac-219">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="576ac-220">呼叫通过呼叫者语音策略路由，并将通过未启用基于位置的路由的 PSTN 网关进行出口</span><span class="sxs-lookup"><span data-stu-id="576ac-220">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="576ac-221">另请参阅</span><span class="sxs-lookup"><span data-stu-id="576ac-221">See Also</span></span>


[<span data-ttu-id="576ac-222">在 Lync Server 2013 中规划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="576ac-222">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

