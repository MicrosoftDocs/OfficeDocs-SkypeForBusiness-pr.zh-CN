---
title: Lync Server 2013：基于位置的路由的部署过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 108dd35c7f184c974a317f68901c94bc81e9e403
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="4bee1-102">Lync Server 2013 中基于位置的路由的部署过程</span><span class="sxs-lookup"><span data-stu-id="4bee1-102">Deployment process for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bee1-103">_**主题上次修改时间:** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="4bee1-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="4bee1-104">本主题概述了配置基于位置的路由所涉及的过程。</span><span class="sxs-lookup"><span data-stu-id="4bee1-104">This topic provides an overview of the process involved in configuring Location-Based Routing.</span></span> <span data-ttu-id="4bee1-105">在配置基于位置的路由之前, 必须部署 Lync Server Enterprise Edition 或标准版和企业版语音。</span><span class="sxs-lookup"><span data-stu-id="4bee1-105">You must deploy Lync Server Enterprise Edition or Standard Edition with Enterprise Voice before you configure Location-Based Routing.</span></span> <span data-ttu-id="4bee1-106">部署企业语音时, 已安装并启用基于位置的路由所需的组件。</span><span class="sxs-lookup"><span data-stu-id="4bee1-106">The components required by Location-Based Routing are already installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="location-based-routing-deployment-process"></a><span data-ttu-id="4bee1-107">基于位置的路由部署过程</span><span class="sxs-lookup"><span data-stu-id="4bee1-107">Location-Based Routing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4bee1-108">阶段</span><span class="sxs-lookup"><span data-stu-id="4bee1-108">Phase</span></span></th>
<th><span data-ttu-id="4bee1-109">步骤</span><span class="sxs-lookup"><span data-stu-id="4bee1-109">Steps</span></span></th>
<th><span data-ttu-id="4bee1-110">所需的组和角色</span><span class="sxs-lookup"><span data-stu-id="4bee1-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="4bee1-111">部署文档</span><span class="sxs-lookup"><span data-stu-id="4bee1-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4bee1-112">部署企业语音</span><span class="sxs-lookup"><span data-stu-id="4bee1-112">Deploy Enterprise Voice</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="4bee1-113">配置中继</span><span class="sxs-lookup"><span data-stu-id="4bee1-113">Configure Trunks</span></span></p></li>
<li><p><span data-ttu-id="4bee1-114">创建语音策略</span><span class="sxs-lookup"><span data-stu-id="4bee1-114">Create Voice Policies</span></span></p></li>
<li><p><span data-ttu-id="4bee1-115">定义语音路由</span><span class="sxs-lookup"><span data-stu-id="4bee1-115">Define Voice Routes</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4bee1-116">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="4bee1-116">CSVoiceAdmins</span></span><br />
<span data-ttu-id="4bee1-117">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4bee1-117">CsAdministrator</span></span><br />
<span data-ttu-id="4bee1-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="4bee1-118">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4bee1-119">部署企业语音</span><span class="sxs-lookup"><span data-stu-id="4bee1-119">Deploying Enterprise Voice</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bee1-120">验证您的企业语音部署</span><span class="sxs-lookup"><span data-stu-id="4bee1-120">Verify your Enterprise Voice deployment</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4bee1-121">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="4bee1-121">CSVoiceAdmins</span></span><br />
<span data-ttu-id="4bee1-122">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4bee1-122">CsAdministrator</span></span><br />
<span data-ttu-id="4bee1-123">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="4bee1-123">CsServerAdministrator</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bee1-124">配置网络区域、网站和子网</span><span class="sxs-lookup"><span data-stu-id="4bee1-124">Configure network regions, sites, and subnets</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="4bee1-125">创建网络区域</span><span class="sxs-lookup"><span data-stu-id="4bee1-125">Create network regions</span></span></p></li>
<li><p><span data-ttu-id="4bee1-126">创建网络网站</span><span class="sxs-lookup"><span data-stu-id="4bee1-126">Create network sites</span></span></p></li>
<li><p><span data-ttu-id="4bee1-127">将子网与网络站点关联</span><span class="sxs-lookup"><span data-stu-id="4bee1-127">Associates subnets with network sites</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4bee1-128">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="4bee1-128">CSVoiceAdmins</span></span><br />
<span data-ttu-id="4bee1-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4bee1-129">CsAdministrator</span></span><br />
<span data-ttu-id="4bee1-130">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="4bee1-130">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4bee1-131">关于网络区域、站点和子网</span><span class="sxs-lookup"><span data-stu-id="4bee1-131">About Network Regions, Sites, and Subnets</span></span><br />
<span data-ttu-id="4bee1-132">创建或修改网络区域</span><span class="sxs-lookup"><span data-stu-id="4bee1-132">Create or Modify a Network Region</span></span><br />
<span data-ttu-id="4bee1-133">创建或修改网络网站</span><span class="sxs-lookup"><span data-stu-id="4bee1-133">Create or Modify a Network Site</span></span><br />
<span data-ttu-id="4bee1-134">将子网与网络站点关联</span><span class="sxs-lookup"><span data-stu-id="4bee1-134">Associate a Subnet with a Network Site</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bee1-135">配置基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="4bee1-135">Configure Location-Based Routing</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="4bee1-136">创建语音路由策略</span><span class="sxs-lookup"><span data-stu-id="4bee1-136">Create voice routing policies</span></span></p></li>
<li><p><span data-ttu-id="4bee1-137">为每个主干定义单独的中继配置</span><span class="sxs-lookup"><span data-stu-id="4bee1-137">Define separate trunk configuration per trunk</span></span></p></li>
<li><p><span data-ttu-id="4bee1-138">修改语音策略</span><span class="sxs-lookup"><span data-stu-id="4bee1-138">Modify voice policies</span></span></p></li>
<li><p><span data-ttu-id="4bee1-139">启用基于位置的路由配置</span><span class="sxs-lookup"><span data-stu-id="4bee1-139">Enable Location-Based Routing configuration</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4bee1-140">CSVoiceAdmins</span><span class="sxs-lookup"><span data-stu-id="4bee1-140">CSVoiceAdmins</span></span><br />
<span data-ttu-id="4bee1-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4bee1-141">CsAdministrator</span></span><br />
<span data-ttu-id="4bee1-142">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="4bee1-142">CsServerAdministrator</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a><span data-ttu-id="4bee1-143">示例部署</span><span class="sxs-lookup"><span data-stu-id="4bee1-143">Sample Deployment</span></span>

<span data-ttu-id="4bee1-144">以下部署用于进一步演示基于位置的路由启用的机制。</span><span class="sxs-lookup"><span data-stu-id="4bee1-144">The following deployment is used to illustrate further the mechanisms enabled by Location-Based Routing.</span></span>

<span data-ttu-id="4bee1-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span><span class="sxs-lookup"><span data-stu-id="4bee1-145">![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")</span></span>

<div>

## <a name="incoming-pstn-calls"></a><span data-ttu-id="4bee1-146">拨入 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="4bee1-146">Incoming PSTN calls</span></span>

<span data-ttu-id="4bee1-147">管理员可以启用定义以将呼叫路由到 "Site 1 网关" 以查找基于位置的路由, 并将 "站点1网关" 与站点1相关联。</span><span class="sxs-lookup"><span data-stu-id="4bee1-147">An administrator can enable the trunk defined to route calls to “Site 1 Gateway” for Location-Based Routing and associate the “Site 1 Gateway” to site 1.</span></span> <span data-ttu-id="4bee1-148">一旦启用, 通过 "站点1网关" 路由的呼叫将仅路由到位于站点1中的用户。</span><span class="sxs-lookup"><span data-stu-id="4bee1-148">Once enabled, calls that are routed through “Site 1 Gateway“ will only be routed to users that are located in site 1.</span></span> <span data-ttu-id="4bee1-149">所有呼叫均通过 "站点1网关" 主干发送到其他网站中的用户, 例如 "网站 2" 将被阻止以防止 PSTN 免绕过。</span><span class="sxs-lookup"><span data-stu-id="4bee1-149">All calls routed through the “Site 1 Gateway” trunk destined to users in a different site, such as site 2 will be blocked to prevent PSTN toll bypass.</span></span>

<span data-ttu-id="4bee1-150">所有通过 "站点1网关" 拨入的 PSTN 呼叫仅允许路由到位于站点1中的终结点。</span><span class="sxs-lookup"><span data-stu-id="4bee1-150">All incoming PSTN calls through “Site 1 Gateway” will only be allowed to route to endpoints located in site 1.</span></span> <span data-ttu-id="4bee1-151">例如, 当 "Lync 用户 1" 传播到站点2时, 所有通过 "站点1网关" 传入的 PSTN 呼叫将不会被路由到位于站点2中的 "Lync 用户 1" 终结点。</span><span class="sxs-lookup"><span data-stu-id="4bee1-151">For example, when “Lync user 1” travels to site 2, all incoming PSTN calls through “Site 1 Gateway” will not be routed to “Lync user 1” endpoints located in site 2.</span></span> <span data-ttu-id="4bee1-152">如果 "Lync 用户 1" 传播到无法确定用户位置的未知网络网站, 则会应用相同的路由规则。</span><span class="sxs-lookup"><span data-stu-id="4bee1-152">The same routing rule applies if “Lync user 1” travels to an unknown network site where the user’s location can’t be determined.</span></span>

<span data-ttu-id="4bee1-153">下表概述了在此上下文中 "Lync 用户 1" 的用户体验。</span><span class="sxs-lookup"><span data-stu-id="4bee1-153">The following table outlines the user experience of “Lync user 1” in this context.</span></span>


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
<th><span data-ttu-id="4bee1-154">Lync 用户1位于网络站点1中的终结点</span><span class="sxs-lookup"><span data-stu-id="4bee1-154">Lync user 1 endpoints located in network site 1</span></span></th>
<th><span data-ttu-id="4bee1-155">Lync 用户1位于网络站点2中的终结点</span><span class="sxs-lookup"><span data-stu-id="4bee1-155">Lync user 1 endpoints located in network site 2</span></span></th>
<th><span data-ttu-id="4bee1-156">位于未知网络网站中的 Lync 用户1终结点</span><span class="sxs-lookup"><span data-stu-id="4bee1-156">Lync user 1 endpoints located in unknown network site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4bee1-157">对 Lync 用户1的入站 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="4bee1-157">Inbound PSTN calls to Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="4bee1-158">呼叫将路由到此位置中的终结点</span><span class="sxs-lookup"><span data-stu-id="4bee1-158">Calls are routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="4bee1-159">调用未路由到此位置中的终结点</span><span class="sxs-lookup"><span data-stu-id="4bee1-159">Calls are not routed to endpoints in this location</span></span></p></td>
<td><p><span data-ttu-id="4bee1-160">调用未路由到此位置中的终结点</span><span class="sxs-lookup"><span data-stu-id="4bee1-160">Calls are not routed to endpoints in this location</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a><span data-ttu-id="4bee1-161">出局 PSTN 呼叫</span><span class="sxs-lookup"><span data-stu-id="4bee1-161">Outgoing PSTN calls</span></span>

<span data-ttu-id="4bee1-162">语音路由以直接分配给用户的语音策略以及分配给网络站点的语音路由策略引用。</span><span class="sxs-lookup"><span data-stu-id="4bee1-162">Voice routes are referenced in both Voice Policies assigned directly to users, and Voice Routing Policies assigned to network sites.</span></span> <span data-ttu-id="4bee1-163">这两个策略都包含对路由的引用, 可用于以不同的方式路由通话。</span><span class="sxs-lookup"><span data-stu-id="4bee1-163">Both policies contain references to routes, which can be used to route a call differently.</span></span> <span data-ttu-id="4bee1-164">例如, 管理员可以为位于 network 1 中的所有用户定义一个语音路由策略, 以便通过 "Site 1 网关" 路由所有出站呼叫, 而某些用户的语音策略定义了通过 "Site 2 网关" 进行的所有出站呼叫的路由。</span><span class="sxs-lookup"><span data-stu-id="4bee1-164">For example, an administrator can define a Voice Routing Policy for all users located in network site 1 to route all outbound calls through the “Site 1 Gateway” while the Voice Policy of some users define a route for all outbound calls through the “Site 2 Gateway”.</span></span> <span data-ttu-id="4bee1-165">虽然这些用户位于网络站点1中, 但其出站呼叫将通过 "站点1网关" 传送。</span><span class="sxs-lookup"><span data-stu-id="4bee1-165">While these users are located in network site 1, their outbound calls will be routed through the “Site 1 Gateway”.</span></span>

<span data-ttu-id="4bee1-166">当用户位于为基于位置的路由配置的网络网站中时, 网络网站的语音路由策略路由将覆盖用户的语音策略路由。</span><span class="sxs-lookup"><span data-stu-id="4bee1-166">When a user is located in a network site configured for Location-Based Routing, the network site’s Voice Routing Policy route overrides the user’s Voice Policy route.</span></span> <span data-ttu-id="4bee1-167">此规则对于临时移动到其他网站的用户尤其有用。</span><span class="sxs-lookup"><span data-stu-id="4bee1-167">This rule is particularly useful for users that temporarily move to a different site.</span></span> <span data-ttu-id="4bee1-168">在此特定情况下, 用户将始终使用本地到其位置的网关;如果 "Lync 用户 3" 位于 "Site 2" 中, 则其所有出站呼叫将通过 "Site 2 网关" 路由, 但如果他向站点1传播, 则在站点1处发出的所有出站呼叫将通过 "站点1网关" 进行路由。</span><span class="sxs-lookup"><span data-stu-id="4bee1-168">In this particular case a user will always use a gateway that is local to his location; if “Lync user 3” is located at “Site 2”, all his outbound calls will be routed via “Site 2 Gateway”, but if he travels to site 1, all his outbound calls placed while he’s at site 1 will be routed through “Site 1 Gateway”.</span></span>

<span data-ttu-id="4bee1-169">下表说明了 Lync 用户1从以下网络站点发出出站呼叫的用户体验。</span><span class="sxs-lookup"><span data-stu-id="4bee1-169">The following table illustrates the user experience of Lync user 1 placing an outbound call from the following network sites.</span></span>


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
<th><span data-ttu-id="4bee1-170">网络站点1</span><span class="sxs-lookup"><span data-stu-id="4bee1-170">Network site 1</span></span></th>
<th><span data-ttu-id="4bee1-171">网络站点2</span><span class="sxs-lookup"><span data-stu-id="4bee1-171">Network site 2</span></span></th>
<th><span data-ttu-id="4bee1-172">未知网络网站或未启用基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="4bee1-172">Unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4bee1-173">出站呼叫授权</span><span class="sxs-lookup"><span data-stu-id="4bee1-173">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="4bee1-174">Lync 用户1语音策略</span><span class="sxs-lookup"><span data-stu-id="4bee1-174">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="4bee1-175">Lync 用户1语音策略</span><span class="sxs-lookup"><span data-stu-id="4bee1-175">Lync user 1 voice policy</span></span></p></td>
<td><p><span data-ttu-id="4bee1-176">Lync 用户1语音策略</span><span class="sxs-lookup"><span data-stu-id="4bee1-176">Lync user 1 voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bee1-177">传出呼叫的路由</span><span class="sxs-lookup"><span data-stu-id="4bee1-177">Routing of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="4bee1-178">站点1语音路由策略</span><span class="sxs-lookup"><span data-stu-id="4bee1-178">Site 1 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="4bee1-179">站点2语音路由策略</span><span class="sxs-lookup"><span data-stu-id="4bee1-179">Site 2 voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="4bee1-180">用户的语音策略, 并且仅适用于不支持基于位置的路由的系统</span><span class="sxs-lookup"><span data-stu-id="4bee1-180">User’s voice policy and only to systems not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a><span data-ttu-id="4bee1-181">呼叫转移和转发</span><span class="sxs-lookup"><span data-stu-id="4bee1-181">Call transfers and forwards</span></span>

<span data-ttu-id="4bee1-182">当转接或转发呼叫时, 呼叫的路由受基于位置的路由影响。</span><span class="sxs-lookup"><span data-stu-id="4bee1-182">When calls are transferred or forwarded, the routing of calls is affected by Location-Based Routing.</span></span>

<span data-ttu-id="4bee1-183">下表描述了 Lync 用户1将 PSTN 呼叫转移或转发给另一个 Lync 用户的情况。</span><span class="sxs-lookup"><span data-stu-id="4bee1-183">The following table depicts Lync user 1 transferring or forwarding a PSTN call to another Lync user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4bee1-184">用户启动呼叫转移或转发</span><span class="sxs-lookup"><span data-stu-id="4bee1-184">User initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="4bee1-185">Lync 用户2</span><span class="sxs-lookup"><span data-stu-id="4bee1-185">Lync user 2</span></span></th>
<th><span data-ttu-id="4bee1-186">Lync 用户4</span><span class="sxs-lookup"><span data-stu-id="4bee1-186">Lync user 4</span></span></th>
<th><span data-ttu-id="4bee1-187">没有为基于位置的路由启用网络站点中的 Lync 用户</span><span class="sxs-lookup"><span data-stu-id="4bee1-187">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4bee1-188">Lync 用户1</span><span class="sxs-lookup"><span data-stu-id="4bee1-188">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="4bee1-189">允许呼叫转接</span><span class="sxs-lookup"><span data-stu-id="4bee1-189">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="4bee1-190">不允许呼叫转接</span><span class="sxs-lookup"><span data-stu-id="4bee1-190">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="4bee1-191">不允许呼叫转接</span><span class="sxs-lookup"><span data-stu-id="4bee1-191">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="4bee1-192">下表说明了基于位置的路由如何根据正在传输到 PSTN 终结点的 Lync 用户的位置 (Lync 用户2、Lync 用户4等) 来影响呼叫的路由方式</span><span class="sxs-lookup"><span data-stu-id="4bee1-192">The following table illustrates how Location-Based Routing affects how the call is routed based on the location of the Lync user being transferred (Lync user 2, Lync user 4, etc) to a PSTN endpoint</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4bee1-193">呼叫转移或转发到的终结点</span><span class="sxs-lookup"><span data-stu-id="4bee1-193">Endpoint where call is transferred or forwarded to</span></span></th>
<th><span data-ttu-id="4bee1-194">Lync 用户2</span><span class="sxs-lookup"><span data-stu-id="4bee1-194">Lync user 2</span></span></th>
<th><span data-ttu-id="4bee1-195">Lync 用户4</span><span class="sxs-lookup"><span data-stu-id="4bee1-195">Lync user 4</span></span></th>
<th><span data-ttu-id="4bee1-196">没有为基于位置的路由启用网络站点中的 Lync 用户</span><span class="sxs-lookup"><span data-stu-id="4bee1-196">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4bee1-197">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="4bee1-197">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="4bee1-198">呼叫转移或转移通过站点1的 "语音路由策略" 和 "通过站点1网关的外出" 传送</span><span class="sxs-lookup"><span data-stu-id="4bee1-198">Call forward or transfer is routed through site 1 voice routing policy and egress via Site 1 Gateway</span></span></p></td>
<td><p><span data-ttu-id="4bee1-199">呼叫转移或转移通过站点2的 "语音路由策略" 和 "站点 2" 网关的外出进行路由</span><span class="sxs-lookup"><span data-stu-id="4bee1-199">Call forward or transfer is routed through site 2 voice routing policy and egress via Site 2 Gateway</span></span></p></td>
<td><p><span data-ttu-id="4bee1-200">呼叫转移或转移通过 Lync 用户语音策略进行路由, 并通过不支持基于位置的路由的网关进行传出 (如果可用)</span><span class="sxs-lookup"><span data-stu-id="4bee1-200">Call forward or transfer is routed through the Lync user voice policy and egress via a gateway not enabled for location-based routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a><span data-ttu-id="4bee1-201">同时响铃</span><span class="sxs-lookup"><span data-stu-id="4bee1-201">Simultaneous ringing</span></span>

<span data-ttu-id="4bee1-202">在示例拓扑中配置基于位置的路由后, 将强制执行以下交互。</span><span class="sxs-lookup"><span data-stu-id="4bee1-202">Once location-based routing is configured in the sample topology, the following interactions are enforced.</span></span>

<span data-ttu-id="4bee1-203">下表说明了基于位置的路由是否允许不同 Lync 用户同时拨打 (如 Lync 用户2、Lync 用户4等)。</span><span class="sxs-lookup"><span data-stu-id="4bee1-203">The following table illustrates whether Location-Based Routing allows simultaneous ringing for different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4bee1-204">打入的 PSTN 呼叫目标</span><span class="sxs-lookup"><span data-stu-id="4bee1-204">Incoming PSTN call target</span></span></th>
<th><span data-ttu-id="4bee1-205">Lync 用户2</span><span class="sxs-lookup"><span data-stu-id="4bee1-205">Lync user 2</span></span></th>
<th><span data-ttu-id="4bee1-206">Lync 用户4</span><span class="sxs-lookup"><span data-stu-id="4bee1-206">Lync user 4</span></span></th>
<th><span data-ttu-id="4bee1-207">没有为基于位置的路由启用网络站点中的 Lync 用户</span><span class="sxs-lookup"><span data-stu-id="4bee1-207">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4bee1-208">Lync 用户1</span><span class="sxs-lookup"><span data-stu-id="4bee1-208">Lync user 1</span></span></p></td>
<td><p><span data-ttu-id="4bee1-209">允许同时拨打</span><span class="sxs-lookup"><span data-stu-id="4bee1-209">Simultaneous ring is allowed</span></span></p></td>
<td><p><span data-ttu-id="4bee1-210">不允许同时拨打</span><span class="sxs-lookup"><span data-stu-id="4bee1-210">Simultaneous ring is not allowed</span></span></p></td>
<td><p><span data-ttu-id="4bee1-211">不允许同时拨打</span><span class="sxs-lookup"><span data-stu-id="4bee1-211">Simultaneous ring is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="4bee1-212">下表说明了基于位置的路由是否允许来自不同 Lync 用户 (即 Lync 用户2、Lync 用户4等) 的 PSTN 终结点同时拨打 PSTN 终结点。</span><span class="sxs-lookup"><span data-stu-id="4bee1-212">The following table illustrates whether Location-Based Routing allows simultaneous ringing to a PSTN endpoint from different Lync users (i.e. Lync user 2, Lync user 4, etc).</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4bee1-213">同时响铃目标</span><span class="sxs-lookup"><span data-stu-id="4bee1-213">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="4bee1-214">Lync 用户2</span><span class="sxs-lookup"><span data-stu-id="4bee1-214">Lync user 2</span></span></th>
<th><span data-ttu-id="4bee1-215">Lync 用户4</span><span class="sxs-lookup"><span data-stu-id="4bee1-215">Lync user 4</span></span></th>
<th><span data-ttu-id="4bee1-216">没有为基于位置的路由启用网络站点中的 Lync 用户</span><span class="sxs-lookup"><span data-stu-id="4bee1-216">Lync user in network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4bee1-217">Lync 用户1移动电话 (PSTN 终结点)</span><span class="sxs-lookup"><span data-stu-id="4bee1-217">Lync user 1 mobile phone (PSTN endpoint)</span></span></p></td>
<td><p><span data-ttu-id="4bee1-218">通过网络站点1的语音路由策略和通过站点1网关传出的呼叫进行路由</span><span class="sxs-lookup"><span data-stu-id="4bee1-218">Call routed through network site 1’s voice routing policy and egress via site 1 gateway</span></span></p></td>
<td><p><span data-ttu-id="4bee1-219">通过网络站点2的语音路由策略和通过站点2网关传出的呼叫进行路由</span><span class="sxs-lookup"><span data-stu-id="4bee1-219">Call routed through network site 2’s voice routing policy and egress via site 2 gateway</span></span></p></td>
<td><p><span data-ttu-id="4bee1-220">呼叫通过呼叫者语音政策路由, 并且将通过不支持基于位置的路由的 PSTN 网关外出</span><span class="sxs-lookup"><span data-stu-id="4bee1-220">Call routed through the caller voice policy and will egress via a PSTN gateway not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4bee1-221">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4bee1-221">See Also</span></span>


[<span data-ttu-id="4bee1-222">在 Lync Server 2013 中规划基于位置的路由</span><span class="sxs-lookup"><span data-stu-id="4bee1-222">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

