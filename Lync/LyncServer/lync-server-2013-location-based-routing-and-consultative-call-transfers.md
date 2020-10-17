---
title: Lync Server 2013： Location-Based 路由和咨询式呼叫转移
description: Lync Server 2013： Location-Based 路由和咨询式呼叫转移。
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
ms.openlocfilehash: 0d07cf6a33ff4d6ad57f8913a798fac3bc393a00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567668"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="06d7e-103">Lync Server 2013 中的 Location-Based 路由和咨询呼叫转移</span><span class="sxs-lookup"><span data-stu-id="06d7e-103">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06d7e-104">_**上次修改的主题：** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="06d7e-104">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="06d7e-105">除了强制 Location-Based 路由到 Lync 会议，Location-Based 路由会议应用程序还强制在向 PSTN 终结点传出的咨询呼叫转移上 Location-Based 路由限制。</span><span class="sxs-lookup"><span data-stu-id="06d7e-105">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="06d7e-106">咨询呼叫转接是在双方将呼叫转移到新用户之间建立的呼叫。</span><span class="sxs-lookup"><span data-stu-id="06d7e-106">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="06d7e-107">例如，PSTN 终结点将呼叫用户 A (Lync 被叫方) 。</span><span class="sxs-lookup"><span data-stu-id="06d7e-107">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="06d7e-108">用户 A 确定应将 PSTN 用户转接到用户 B (Lync 用户) 。</span><span class="sxs-lookup"><span data-stu-id="06d7e-108">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="06d7e-109">用户 A 将呼叫与 PSTN 用户置于保留状态，并呼叫用户 B。用户 B 同意与 PSTN 用户对话。</span><span class="sxs-lookup"><span data-stu-id="06d7e-109">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="06d7e-110">用户 A 将呼叫（保留）转移到用户 B。</span><span class="sxs-lookup"><span data-stu-id="06d7e-110">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="06d7e-111">**咨询呼叫转接呼叫流**</span><span class="sxs-lookup"><span data-stu-id="06d7e-111">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="06d7e-112">![会议图的基于位置的路由](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "会议图的基于位置的路由")</span><span class="sxs-lookup"><span data-stu-id="06d7e-112">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="06d7e-113">当启用 Location-Based 路由的用户启动 PSTN 终结点的咨询呼叫转移时 (如前面的图所示) 中，这将创建两个活动呼叫、PSTN 用户和 Lync 用户 A 之间的一次呼叫，以及 Lync 用户 A 和 Lync 用户 B 之间的另一个呼叫。 Location-Based 路由会议应用程序强制实施以下行为：</span><span class="sxs-lookup"><span data-stu-id="06d7e-113">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="06d7e-114">如果对 PSTN 呼叫的 SIP 中继路由有权将 PSTN 呼叫重新路由到网络站点（其中 Lync user B (即 "转移目标) 位于"，则将允许呼叫转移;否则，将阻止咨询呼叫转移。</span><span class="sxs-lookup"><span data-stu-id="06d7e-114">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="06d7e-115">此授权根据被转移方在与将活动呼叫路由到 PSTN 终结点的 SIP 中继位于同一网络站点中的位置进行。</span><span class="sxs-lookup"><span data-stu-id="06d7e-115">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="06d7e-116">如果 SIP 中继路由未授权入站 PSTN 呼叫将呼叫路由到 (Lync user B) 的传输方，或者转移方位于未知网络站点中，则咨询呼叫转移到 PSTN 终结点 (例如，将阻止呼叫转移目标) 。</span><span class="sxs-lookup"><span data-stu-id="06d7e-116">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="06d7e-117">下表介绍了 Location-Based 路由会议应用程序如何为咨询呼叫转移应用 Location-Based 路由限制。</span><span class="sxs-lookup"><span data-stu-id="06d7e-117">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="06d7e-118">虽然 PBX 终结点不与网络站点直接关联，但 PBX 的 SIP 中继可分配给网络站点。</span><span class="sxs-lookup"><span data-stu-id="06d7e-118">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="06d7e-119">因此，PBX 终结点可以与网络站点间接关联。</span><span class="sxs-lookup"><span data-stu-id="06d7e-119">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06d7e-120">呼叫转移方的网络站点</span><span class="sxs-lookup"><span data-stu-id="06d7e-120">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="06d7e-121">呼叫转接目标的网络站点</span><span class="sxs-lookup"><span data-stu-id="06d7e-121">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="06d7e-122">行为</span><span class="sxs-lookup"><span data-stu-id="06d7e-122">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06d7e-123">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="06d7e-123">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="06d7e-124">同一网络站点中的 Lync 用户 (即站点 1) </span><span class="sxs-lookup"><span data-stu-id="06d7e-124">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="06d7e-125">将允许咨询转移</span><span class="sxs-lookup"><span data-stu-id="06d7e-125">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06d7e-126">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="06d7e-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="06d7e-127">不同网络站点中的 Lync 用户 (即站点 2) </span><span class="sxs-lookup"><span data-stu-id="06d7e-127">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="06d7e-128">将不允许咨询转移</span><span class="sxs-lookup"><span data-stu-id="06d7e-128">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06d7e-129">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="06d7e-129">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="06d7e-130">未知网络站点中的 Lync 用户</span><span class="sxs-lookup"><span data-stu-id="06d7e-130">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="06d7e-131">将不允许咨询转移</span><span class="sxs-lookup"><span data-stu-id="06d7e-131">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06d7e-132">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="06d7e-132">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="06d7e-133">联合 Lync 用户</span><span class="sxs-lookup"><span data-stu-id="06d7e-133">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="06d7e-134">将不允许咨询转移</span><span class="sxs-lookup"><span data-stu-id="06d7e-134">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06d7e-135">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="06d7e-135">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="06d7e-136">同一站点中的 PBX 终结点 (即站点 1) </span><span class="sxs-lookup"><span data-stu-id="06d7e-136">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="06d7e-137">将允许咨询转移</span><span class="sxs-lookup"><span data-stu-id="06d7e-137">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06d7e-138">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="06d7e-138">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="06d7e-139">不同站点 (的 PBX 终结点，即 site 2) </span><span class="sxs-lookup"><span data-stu-id="06d7e-139">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="06d7e-140">将不允许咨询转移</span><span class="sxs-lookup"><span data-stu-id="06d7e-140">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06d7e-141">同一站点中的 PBX 终结点 (即站点 1) </span><span class="sxs-lookup"><span data-stu-id="06d7e-141">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="06d7e-142">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="06d7e-142">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="06d7e-143">将允许咨询转移</span><span class="sxs-lookup"><span data-stu-id="06d7e-143">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06d7e-144">不同网站中的 PBX 终结点 (即 site 2) </span><span class="sxs-lookup"><span data-stu-id="06d7e-144">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="06d7e-145">PSTN 终结点</span><span class="sxs-lookup"><span data-stu-id="06d7e-145">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="06d7e-146">将不允许咨询转移</span><span class="sxs-lookup"><span data-stu-id="06d7e-146">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06d7e-147">任何站点中的 PBX 终结点</span><span class="sxs-lookup"><span data-stu-id="06d7e-147">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="06d7e-148">同一网络站点中的 Lync 用户 (即站点 1) </span><span class="sxs-lookup"><span data-stu-id="06d7e-148">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="06d7e-149">将允许咨询转移</span><span class="sxs-lookup"><span data-stu-id="06d7e-149">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06d7e-150">任何站点中的 PBX 终结点</span><span class="sxs-lookup"><span data-stu-id="06d7e-150">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="06d7e-151">不同网络站点中的 Lync 用户 (即站点 2) </span><span class="sxs-lookup"><span data-stu-id="06d7e-151">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="06d7e-152">将允许咨询转移</span><span class="sxs-lookup"><span data-stu-id="06d7e-152">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06d7e-153">任何站点中的 PBX 终结点</span><span class="sxs-lookup"><span data-stu-id="06d7e-153">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="06d7e-154">未知网络站点中的 Lync 用户</span><span class="sxs-lookup"><span data-stu-id="06d7e-154">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="06d7e-155">将允许咨询转移</span><span class="sxs-lookup"><span data-stu-id="06d7e-155">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06d7e-156">任何站点中的 PBX 终结点</span><span class="sxs-lookup"><span data-stu-id="06d7e-156">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="06d7e-157">联合 Lync 用户</span><span class="sxs-lookup"><span data-stu-id="06d7e-157">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="06d7e-158">将允许咨询转移</span><span class="sxs-lookup"><span data-stu-id="06d7e-158">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

