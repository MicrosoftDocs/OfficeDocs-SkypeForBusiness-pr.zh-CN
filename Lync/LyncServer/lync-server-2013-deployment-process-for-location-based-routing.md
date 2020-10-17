---
title: Lync Server 2013： Location-Based 路由的部署过程
description: Lync Server 2013： Location-Based 路由的部署过程。
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
ms.openlocfilehash: 2c321d9b0eada6e9501b2ded69120feae36be171
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551058"
---
# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="7eda8-103">Lync Server 2013 中 Location-Based 路由的部署过程</span><span class="sxs-lookup"><span data-stu-id="7eda8-103">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7eda8-104">_**上次修改的主题：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="7eda8-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="7eda8-105">本主题概述了配置 Location-Based 路由所涉及的过程。</span><span class="sxs-lookup"><span data-stu-id="7eda8-105">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="7eda8-106">在配置 Location-Based 路由之前，必须部署 Lync Server Enterprise Edition 或 Standard Edition 和 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="7eda8-106">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="7eda8-107">在部署企业语音时，已安装并启用 Location-Based 路由所需的组件。</span><span class="sxs-lookup"><span data-stu-id="7eda8-107">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="7eda8-108">Location-Based 路由部署过程</span><span class="sxs-lookup"><span data-stu-id="7eda8-108">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7eda8-109">阶段</span><span class="sxs-lookup"><span data-stu-id="7eda8-109">Phase</span></span></th>
<th><span data-ttu-id="7eda8-110">步骤</span><span class="sxs-lookup"><span data-stu-id="7eda8-110">Steps</span></span></th>
<th><span data-ttu-id="7eda8-111">所需的组和角色</span><span class="sxs-lookup"><span data-stu-id="7eda8-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="7eda8-112">部署文档</span><span class="sxs-lookup"><span data-stu-id="7eda8-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7eda8-113">部署企业语音</span><span class="sxs-lookup"><span data-stu-id="7eda8-113">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7eda8-114">配置中继</span><span class="sxs-lookup"><span data-stu-id="7eda8-114">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="7eda8-115">创建语音策略</span><span class="sxs-lookup"><span data-stu-id="7eda8-115">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="7eda8-116">定义语音路由</span><span class="sxs-lookup"><span data-stu-id="7eda8-116">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7eda8-117">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="7eda8-117">CSVoiceAdmins</span></span><br />
<span data-ttu-id="7eda8-118">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="7eda8-118">CsAdministrator</span></span><br />
<span data-ttu-id="7eda8-119">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="7eda8-119">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="7eda8-120">部署企业语音</span><span class="sxs-lookup"><span data-stu-id="7eda8-120">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eda8-121">验证您的企业语音部署</span><span class="sxs-lookup"><span data-stu-id="7eda8-121">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eda8-122">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="7eda8-122">CSVoiceAdmins</span></span><br />
<span data-ttu-id="7eda8-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="7eda8-123">CsAdministrator</span></span><br />
<span data-ttu-id="7eda8-124">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="7eda8-124">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eda8-125">配置网络区域、站点和子网</span><span class="sxs-lookup"><span data-stu-id="7eda8-125">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7eda8-126">创建网络区域</span><span class="sxs-lookup"><span data-stu-id="7eda8-126">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="7eda8-127">创建网络站点</span><span class="sxs-lookup"><span data-stu-id="7eda8-127">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="7eda8-128">将子网与网络站点关联</span><span class="sxs-lookup"><span data-stu-id="7eda8-128">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7eda8-129">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="7eda8-129">CSVoiceAdmins</span></span><br />
<span data-ttu-id="7eda8-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="7eda8-130">CsAdministrator</span></span><br />
<span data-ttu-id="7eda8-131">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="7eda8-131">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="7eda8-132">关于网络区域、站点和子网</span><span class="sxs-lookup"><span data-stu-id="7eda8-132">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="7eda8-133">创建或修改网络区域</span><span class="sxs-lookup"><span data-stu-id="7eda8-133">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="7eda8-134">创建或修改网络站点</span><span class="sxs-lookup"><span data-stu-id="7eda8-134">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="7eda8-135">将子网与网络站点相关联</span><span class="sxs-lookup"><span data-stu-id="7eda8-135">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eda8-136">配置 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="7eda8-136">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="7eda8-137">创建语音路由策略</span><span class="sxs-lookup"><span data-stu-id="7eda8-137">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="7eda8-138">为每个中继定义单独的中继配置</span><span class="sxs-lookup"><span data-stu-id="7eda8-138">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="7eda8-139">修改语音策略</span><span class="sxs-lookup"><span data-stu-id="7eda8-139">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="7eda8-140">启用 Location-Based 路由配置</span><span class="sxs-lookup"><span data-stu-id="7eda8-140">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="7eda8-141">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="7eda8-141">CSVoiceAdmins</span></span><br />
<span data-ttu-id="7eda8-142">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="7eda8-142">CsAdministrator</span></span><br />
<span data-ttu-id="7eda8-143">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="7eda8-143">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="7eda8-144">示例部署</span><span class="sxs-lookup"><span data-stu-id="7eda8-144">Sample Deployment</span></span>

<span data-ttu-id="7eda8-145">以下部署用于进一步说明 Location-Based 路由启用的机制。</span><span class="sxs-lookup"><span data-stu-id="7eda8-145">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="7eda8-146">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="7eda8-146">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="7eda8-147">传入 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="7eda8-147">Incoming PSTN calls</span></span>

<span data-ttu-id="7eda8-148">管理员可以使已定义的中继将呼叫路由到 "Site 1 Gateway" 以进行 Location-Based 路由，并将 "Site 1 Gateway" 与 Site 1 相关联。</span><span class="sxs-lookup"><span data-stu-id="7eda8-148">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="7eda8-149">启用后，通过 "Site 1 Gateway" 路由的呼叫将仅路由到位于站点1中的用户。</span><span class="sxs-lookup"><span data-stu-id="7eda8-149">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="7eda8-150">通过 "Site 1 Gateway" 中继路由到其他站点中的用户的所有呼叫，如 Site 2 将受到阻止，以防止 PSTN 收费旁路。</span><span class="sxs-lookup"><span data-stu-id="7eda8-150">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="7eda8-151">通过 "Site 1 Gateway" 进行的所有传入 PSTN 呼叫仅允许路由到站点1中的终结点。</span><span class="sxs-lookup"><span data-stu-id="7eda8-151">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="7eda8-152">例如，当 "Lync user 1" 向站点2传播时，通过 "Site 1 Gateway" 进行的所有传入 PSTN 呼叫将不会路由到站点2中的 "Lync 用户 1" 终结点。</span><span class="sxs-lookup"><span data-stu-id="7eda8-152">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="7eda8-153">如果 "Lync user 1" 传播到无法确定用户位置的未知网络站点，则应用相同的路由规则。</span><span class="sxs-lookup"><span data-stu-id="7eda8-153">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="7eda8-154">下表概述了此上下文中的 "Lync 用户 1" 的用户体验。</span><span class="sxs-lookup"><span data-stu-id="7eda8-154">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


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
<th><span data-ttu-id="7eda8-155">位于网络站点1的 Lync 用户1终结点</span><span class="sxs-lookup"><span data-stu-id="7eda8-155">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="7eda8-156">位于网络站点2中的 Lync 用户1终结点</span><span class="sxs-lookup"><span data-stu-id="7eda8-156">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="7eda8-157">位于未知网络站点中的 Lync 用户1终结点</span><span class="sxs-lookup"><span data-stu-id="7eda8-157">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7eda8-158">对 Lync 用户1的入站 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="7eda8-158">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="7eda8-159">将呼叫路由到此位置中的终结点</span><span class="sxs-lookup"><span data-stu-id="7eda8-159">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="7eda8-160">呼叫不会路由到此位置中的终结点</span><span class="sxs-lookup"><span data-stu-id="7eda8-160">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="7eda8-161">呼叫不会路由到此位置中的终结点</span><span class="sxs-lookup"><span data-stu-id="7eda8-161">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="7eda8-162">传出 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="7eda8-162">Outgoing PSTN calls</span></span>

<span data-ttu-id="7eda8-163">在直接分配给用户的语音策略和分配给网络站点的语音路由策略中引用语音路由。</span><span class="sxs-lookup"><span data-stu-id="7eda8-163">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="7eda8-164">这两个策略都包含对路由的引用，可用于以不同的方式路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="7eda8-164">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="7eda8-165">例如，管理员可以为位于网络站点1中的所有用户定义一个语音路由策略，以便通过 "Site 1 Gateway" 路由所有出站呼叫，而某些用户的语音策略为所有出站呼叫通过 "Site 2 Gateway" 定义路由。</span><span class="sxs-lookup"><span data-stu-id="7eda8-165">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="7eda8-166">虽然这些用户位于网络站点1中，但其出站呼叫将通过 "Site 1 Gateway" 路由。</span><span class="sxs-lookup"><span data-stu-id="7eda8-166">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="7eda8-167">当用户位于为 Location-Based 路由配置的网络站点中时，网络站点的语音路由策略路由将覆盖用户的语音策略路由。</span><span class="sxs-lookup"><span data-stu-id="7eda8-167">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="7eda8-168">此规则对于临时移到不同网站的用户尤其有用。</span><span class="sxs-lookup"><span data-stu-id="7eda8-168">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="7eda8-169">在此特定情况下，用户将始终使用本地到其位置的网关;如果 "Lync user 3" 位于 "Site 2"，则所有出站呼叫都将通过 "Site 2 Gateway 路由"，但如果他转到站点1，则其在站点1处发出的所有出站呼叫将通过 "Site 1 Gateway" 路由。</span><span class="sxs-lookup"><span data-stu-id="7eda8-169">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="7eda8-170">下表说明了 Lync 用户1发出来自以下网络站点的出站呼叫的用户体验。</span><span class="sxs-lookup"><span data-stu-id="7eda8-170">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


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
<th><span data-ttu-id="7eda8-171">网络站点1</span><span class="sxs-lookup"><span data-stu-id="7eda8-171">Network site 1</span></span></th>
<th><span data-ttu-id="7eda8-172">网络站点2</span><span class="sxs-lookup"><span data-stu-id="7eda8-172">Network site 2</span></span></th>
<th><span data-ttu-id="7eda8-173">未知网络站点或未对 Location-Based 路由启用</span><span class="sxs-lookup"><span data-stu-id="7eda8-173">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7eda8-174">出站呼叫的授权</span><span class="sxs-lookup"><span data-stu-id="7eda8-174">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="7eda8-175">Lync 用户1语音策略</span><span class="sxs-lookup"><span data-stu-id="7eda8-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="7eda8-176">Lync 用户1语音策略</span><span class="sxs-lookup"><span data-stu-id="7eda8-176">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="7eda8-177">Lync 用户1语音策略</span><span class="sxs-lookup"><span data-stu-id="7eda8-177">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eda8-178">出站呼叫的路由</span><span class="sxs-lookup"><span data-stu-id="7eda8-178">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="7eda8-179">站点1语音路由策略</span><span class="sxs-lookup"><span data-stu-id="7eda8-179">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="7eda8-180">站点2语音路由策略</span><span class="sxs-lookup"><span data-stu-id="7eda8-180">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="7eda8-181">用户的语音策略，并且仅对未启用 Location-Based 路由的系统</span><span class="sxs-lookup"><span data-stu-id="7eda8-181">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="7eda8-182">呼叫转移和转发</span><span class="sxs-lookup"><span data-stu-id="7eda8-182">Call transfers and forwards</span></span>

<span data-ttu-id="7eda8-183">当转接或转接呼叫时，呼叫的路由将受到 Location-Based 路由的影响。</span><span class="sxs-lookup"><span data-stu-id="7eda8-183">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="7eda8-184">下表描述了 Lync 用户1将 PSTN 呼叫转移或转发给另一个 Lync 用户的情况。</span><span class="sxs-lookup"><span data-stu-id="7eda8-184">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7eda8-185">用户启动呼叫转移或转发</span><span class="sxs-lookup"><span data-stu-id="7eda8-185">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="7eda8-186">Lync 用户2</span><span class="sxs-lookup"><span data-stu-id="7eda8-186">Lync user 2</span></span></th>
<th><span data-ttu-id="7eda8-187">Lync 用户4</span><span class="sxs-lookup"><span data-stu-id="7eda8-187">Lync user 4</span></span></th>
<th><span data-ttu-id="7eda8-188">未对网络站点中的 Lync 用户启用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="7eda8-188">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7eda8-189">Lync 用户1</span><span class="sxs-lookup"><span data-stu-id="7eda8-189">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="7eda8-190">允许呼叫转接或转接</span><span class="sxs-lookup"><span data-stu-id="7eda8-190">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="7eda8-191">不允许呼叫转接或转接</span><span class="sxs-lookup"><span data-stu-id="7eda8-191">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="7eda8-192">不允许呼叫转接或转接</span><span class="sxs-lookup"><span data-stu-id="7eda8-192">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="7eda8-193">下表说明了 Location-Based 路由如何根据要转移的 Lync 用户的位置 (Lync 用户2、Lync user 4 （etc）) 到 PSTN 终结点来影响呼叫路由</span><span class="sxs-lookup"><span data-stu-id="7eda8-193">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7eda8-194">呼叫转接到或转发到的终结点</span><span class="sxs-lookup"><span data-stu-id="7eda8-194">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="7eda8-195">Lync 用户2</span><span class="sxs-lookup"><span data-stu-id="7eda8-195">Lync user 2</span></span></th>
<th><span data-ttu-id="7eda8-196">Lync 用户4</span><span class="sxs-lookup"><span data-stu-id="7eda8-196">Lync user 4</span></span></th>
<th><span data-ttu-id="7eda8-197">未对网络站点中的 Lync 用户启用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="7eda8-197">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7eda8-198">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="7eda8-198">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="7eda8-199">呼叫转接或转接通过站点1语音路由策略和通过站点1网关的传出进行路由</span><span class="sxs-lookup"><span data-stu-id="7eda8-199">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="7eda8-200">呼叫转接或转接通过站点2语音路由策略和通过站点2网关的传出进行路由</span><span class="sxs-lookup"><span data-stu-id="7eda8-200">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="7eda8-201">通过 Lync 用户语音策略或通过未启用基于位置的路由 (的网关路由传出的呼叫转接或转移（如果可用）) </span><span class="sxs-lookup"><span data-stu-id="7eda8-201">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="7eda8-202">同时响铃</span><span class="sxs-lookup"><span data-stu-id="7eda8-202">Simultaneous ringing</span></span>

<span data-ttu-id="7eda8-203">在示例拓扑中配置基于位置的路由后，将强制执行以下交互操作。</span><span class="sxs-lookup"><span data-stu-id="7eda8-203">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="7eda8-204">下表说明了 Location-Based 路由是否允许不同 Lync 用户同时响铃 (例如 Lync 用户2、Lync user 4 等) 。</span><span class="sxs-lookup"><span data-stu-id="7eda8-204">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7eda8-205">传入 PSTN 呼叫目标</span><span class="sxs-lookup"><span data-stu-id="7eda8-205">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="7eda8-206">Lync 用户2</span><span class="sxs-lookup"><span data-stu-id="7eda8-206">Lync user 2</span></span></th>
<th><span data-ttu-id="7eda8-207">Lync 用户4</span><span class="sxs-lookup"><span data-stu-id="7eda8-207">Lync user 4</span></span></th>
<th><span data-ttu-id="7eda8-208">未对网络站点中的 Lync 用户启用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="7eda8-208">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7eda8-209">Lync 用户1</span><span class="sxs-lookup"><span data-stu-id="7eda8-209">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="7eda8-210">允许同时振铃</span><span class="sxs-lookup"><span data-stu-id="7eda8-210">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="7eda8-211">不允许同时响铃</span><span class="sxs-lookup"><span data-stu-id="7eda8-211">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="7eda8-212">不允许同时响铃</span><span class="sxs-lookup"><span data-stu-id="7eda8-212">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="7eda8-213">下表说明了 Location-Based 路由是否允许从不同 Lync 用户同时响铃到 PSTN 终结点 (例如 Lync user 2、Lync user 4 等) 。</span><span class="sxs-lookup"><span data-stu-id="7eda8-213">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7eda8-214">同时振铃目标</span><span class="sxs-lookup"><span data-stu-id="7eda8-214">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="7eda8-215">Lync 用户2</span><span class="sxs-lookup"><span data-stu-id="7eda8-215">Lync user 2</span></span></th>
<th><span data-ttu-id="7eda8-216">Lync 用户4</span><span class="sxs-lookup"><span data-stu-id="7eda8-216">Lync user 4</span></span></th>
<th><span data-ttu-id="7eda8-217">未对网络站点中的 Lync 用户启用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="7eda8-217">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7eda8-218">Lync 用户1移动电话 (PSTN 终结点) </span><span class="sxs-lookup"><span data-stu-id="7eda8-218">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="7eda8-219">通过网络站点1的语音路由策略进行的呼叫路由，通过站点1网关进行的传出</span><span class="sxs-lookup"><span data-stu-id="7eda8-219">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="7eda8-220">通过网络站点2的语音路由策略和通过站点2网关进行的传出路由的呼叫</span><span class="sxs-lookup"><span data-stu-id="7eda8-220">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="7eda8-221">呼叫通过呼叫者语音策略路由，并将通过未启用 Location-Based 路由的 PSTN 网关进行出口</span><span class="sxs-lookup"><span data-stu-id="7eda8-221">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7eda8-222">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7eda8-222">See Also</span></span>


[<span data-ttu-id="7eda8-223">在 Lync Server 2013 中规划 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="7eda8-223">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

