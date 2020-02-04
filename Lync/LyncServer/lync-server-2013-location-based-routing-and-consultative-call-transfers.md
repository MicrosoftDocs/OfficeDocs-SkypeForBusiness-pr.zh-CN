---
title: Lync Server 2013：基于位置的路由和咨询式呼叫转移
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e433baf180b8e4abf50ec374848204bf6628eb0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="67fbc-102">Lync Server 2013 中基于位置的路由和咨询式呼叫转移</span><span class="sxs-lookup"><span data-stu-id="67fbc-102">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67fbc-103">_**主题上次修改时间：** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="67fbc-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="67fbc-104">除了强制执行基于位置的到 Lync 会议的路由，基于位置的路由会议应用程序在向 PSTN 终结点传出的咨询呼叫转移上强制实施基于位置的路由限制。</span><span class="sxs-lookup"><span data-stu-id="67fbc-104">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="67fbc-105">咨询式呼叫转移是在双方将呼叫转移到新用户之间建立的呼叫。</span><span class="sxs-lookup"><span data-stu-id="67fbc-105">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="67fbc-106">例如，PSTN 终结点呼叫用户 A （Lync 被呼叫者）。</span><span class="sxs-lookup"><span data-stu-id="67fbc-106">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="67fbc-107">用户 A 确定应将 PSTN 用户转发给用户 B （Lync 用户）。</span><span class="sxs-lookup"><span data-stu-id="67fbc-107">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="67fbc-108">用户 A 将呼叫与 PSTN 用户保持通话状态，然后呼叫用户 B。用户 B 同意与 PSTN 用户交谈。</span><span class="sxs-lookup"><span data-stu-id="67fbc-108">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="67fbc-109">用户 A 将呼叫转接至用户 B。</span><span class="sxs-lookup"><span data-stu-id="67fbc-109">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="67fbc-110">**咨询呼叫转接呼叫流**</span><span class="sxs-lookup"><span data-stu-id="67fbc-110">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="67fbc-111">![会议的基于位置的路由图示](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "会议的基于位置的路由图示")</span><span class="sxs-lookup"><span data-stu-id="67fbc-111">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="67fbc-112">如果启用了基于位置的路由的用户启动 PSTN 终结点的咨询呼叫转移（如上图所示），这将创建两个活动呼叫、PSTN 用户 A 和 Lync 用户 A 之间的一个通话以及 Lync 用户 A 和 Lync 用户 B 之间的另一个通话。以下行为由基于位置的路由会议应用程序强制执行：</span><span class="sxs-lookup"><span data-stu-id="67fbc-112">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="67fbc-113">如果 SIP 中继路由的 PSTN 呼叫有权将 PSTN 呼叫重新路由到 Lync 用户 B （即传输目标）所在的网络站点，则将允许呼叫转移;否则，将阻止咨询呼叫转接。</span><span class="sxs-lookup"><span data-stu-id="67fbc-113">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="67fbc-114">此授权的依据是转接方的位置与负责将活动呼叫路由到 PSTN 终结点的 SIP 中继位于相同网络站点。</span><span class="sxs-lookup"><span data-stu-id="67fbc-114">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="67fbc-115">如果 SIP 中继路由入站 PSTN 呼叫无权将呼叫路由到已传输方（Lync 用户 B）所在的网络站点，或者转移方位于未知的网络站点，则咨询呼叫将转移到 PSTN将阻止终结点（即呼叫转移目标）。</span><span class="sxs-lookup"><span data-stu-id="67fbc-115">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="67fbc-116">下表介绍了基于位置的路由选择限制如何应用基于位置的路由选择限制以进行咨询式呼叫转移。</span><span class="sxs-lookup"><span data-stu-id="67fbc-116">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="67fbc-117">尽管 PBX 终结点并非直接与某个网络站点关联，但可以为 PBX 连接到的 SIP 中继分配一个网络站点。</span><span class="sxs-lookup"><span data-stu-id="67fbc-117">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="67fbc-118">因此，PBX 终结点可以间接与网络站点关联。</span><span class="sxs-lookup"><span data-stu-id="67fbc-118">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67fbc-119">呼叫被转接方的网络站点</span><span class="sxs-lookup"><span data-stu-id="67fbc-119">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="67fbc-120">呼叫转接目标的网络站点</span><span class="sxs-lookup"><span data-stu-id="67fbc-120">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="67fbc-121">行为</span><span class="sxs-lookup"><span data-stu-id="67fbc-121">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67fbc-122">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="67fbc-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="67fbc-123">同一网络网站中的 Lync 用户（即站点1）</span><span class="sxs-lookup"><span data-stu-id="67fbc-123">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="67fbc-124">咨询转接将被允许</span><span class="sxs-lookup"><span data-stu-id="67fbc-124">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67fbc-125">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="67fbc-125">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="67fbc-126">不同网络站点中的 Lync 用户（即站点2）</span><span class="sxs-lookup"><span data-stu-id="67fbc-126">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="67fbc-127">咨询转接将被禁止</span><span class="sxs-lookup"><span data-stu-id="67fbc-127">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67fbc-128">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="67fbc-128">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="67fbc-129">未知网络网站中的 Lync 用户</span><span class="sxs-lookup"><span data-stu-id="67fbc-129">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="67fbc-130">咨询转接将被禁止</span><span class="sxs-lookup"><span data-stu-id="67fbc-130">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67fbc-131">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="67fbc-131">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="67fbc-132">联合 Lync 用户</span><span class="sxs-lookup"><span data-stu-id="67fbc-132">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="67fbc-133">咨询转接将被禁止</span><span class="sxs-lookup"><span data-stu-id="67fbc-133">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67fbc-134">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="67fbc-134">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="67fbc-135">PBX 终结点位于相同站点（即站点 1）</span><span class="sxs-lookup"><span data-stu-id="67fbc-135">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="67fbc-136">咨询转接将被允许</span><span class="sxs-lookup"><span data-stu-id="67fbc-136">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67fbc-137">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="67fbc-137">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="67fbc-138">PBX 终结点位于不同站点（即站点 2）</span><span class="sxs-lookup"><span data-stu-id="67fbc-138">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="67fbc-139">咨询转接将被禁止</span><span class="sxs-lookup"><span data-stu-id="67fbc-139">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67fbc-140">PBX 终结点位于相同站点（即站点 1）</span><span class="sxs-lookup"><span data-stu-id="67fbc-140">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="67fbc-141">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="67fbc-141">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="67fbc-142">咨询转接将被允许</span><span class="sxs-lookup"><span data-stu-id="67fbc-142">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67fbc-143">PBX 终结点位于不同站点（即站点 2）</span><span class="sxs-lookup"><span data-stu-id="67fbc-143">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="67fbc-144">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="67fbc-144">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="67fbc-145">咨询转接将被禁止</span><span class="sxs-lookup"><span data-stu-id="67fbc-145">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67fbc-146">PBX 终结点位于任意站点</span><span class="sxs-lookup"><span data-stu-id="67fbc-146">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="67fbc-147">同一网络网站中的 Lync 用户（即站点1）</span><span class="sxs-lookup"><span data-stu-id="67fbc-147">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="67fbc-148">咨询转接将被允许</span><span class="sxs-lookup"><span data-stu-id="67fbc-148">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67fbc-149">PBX 终结点位于任意站点</span><span class="sxs-lookup"><span data-stu-id="67fbc-149">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="67fbc-150">不同网络站点中的 Lync 用户（即站点2）</span><span class="sxs-lookup"><span data-stu-id="67fbc-150">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="67fbc-151">咨询转接将被允许</span><span class="sxs-lookup"><span data-stu-id="67fbc-151">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67fbc-152">PBX 终结点位于任意站点</span><span class="sxs-lookup"><span data-stu-id="67fbc-152">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="67fbc-153">未知网络网站中的 Lync 用户</span><span class="sxs-lookup"><span data-stu-id="67fbc-153">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="67fbc-154">咨询转接将被允许</span><span class="sxs-lookup"><span data-stu-id="67fbc-154">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67fbc-155">PBX 终结点位于任意站点</span><span class="sxs-lookup"><span data-stu-id="67fbc-155">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="67fbc-156">联合 Lync 用户</span><span class="sxs-lookup"><span data-stu-id="67fbc-156">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="67fbc-157">咨询转接将被允许</span><span class="sxs-lookup"><span data-stu-id="67fbc-157">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

