---
title: Lync Server 2013：VoipDetails 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f13087202b15cf9b25f0c32741c396c48f628908
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="b9574-102">Lync Server 2013 中的 VoipDetails 表</span><span class="sxs-lookup"><span data-stu-id="b9574-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9574-103">_**主题上次修改时间：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b9574-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b9574-104">每条记录表示至少有一位用户是 VoIP 用户的 1 2 方呼叫。</span><span class="sxs-lookup"><span data-stu-id="b9574-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9574-105">列</span><span class="sxs-lookup"><span data-stu-id="b9574-105">Column</span></span></th>
<th><span data-ttu-id="b9574-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="b9574-106">Data Type</span></span></th>
<th><span data-ttu-id="b9574-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="b9574-107">Key/Index</span></span></th>
<th><span data-ttu-id="b9574-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="b9574-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9574-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b9574-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b9574-110">datetime</span><span class="sxs-lookup"><span data-stu-id="b9574-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="b9574-111">Primary</span><span class="sxs-lookup"><span data-stu-id="b9574-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="b9574-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="b9574-112">Time of session request.</span></span> <span data-ttu-id="b9574-113">与<strong>SessionIdSeq</strong>结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="b9574-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b9574-114">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="b9574-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9574-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b9574-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b9574-116">int</span><span class="sxs-lookup"><span data-stu-id="b9574-116">int</span></span></p></td>
<td><p><span data-ttu-id="b9574-117">Primary</span><span class="sxs-lookup"><span data-stu-id="b9574-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="b9574-118">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="b9574-118">ID number to identify the session.</span></span> <span data-ttu-id="b9574-119">与<strong>SessionIdTime</strong>结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="b9574-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b9574-120">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="b9574-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9574-121"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="b9574-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="b9574-122">int</span><span class="sxs-lookup"><span data-stu-id="b9574-122">int</span></span></p></td>
<td><p><span data-ttu-id="b9574-123">外表</span><span class="sxs-lookup"><span data-stu-id="b9574-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b9574-124">呼叫方的<strong>PhoneId</strong> 。</span><span class="sxs-lookup"><span data-stu-id="b9574-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="b9574-125">有关详细信息，请参阅<a href="lync-server-2013-phones-table.md">Lync Server 2013 中</a>的 "电话" 表。</span><span class="sxs-lookup"><span data-stu-id="b9574-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="b9574-126">如果 not NULL 且<strong>FromGatewayId</strong>不为 null，则呼叫方是 PSTN 用户。</span><span class="sxs-lookup"><span data-stu-id="b9574-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9574-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="b9574-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="b9574-128">int</span><span class="sxs-lookup"><span data-stu-id="b9574-128">int</span></span></p></td>
<td><p><span data-ttu-id="b9574-129">外表</span><span class="sxs-lookup"><span data-stu-id="b9574-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b9574-130">呼叫接收器的<strong>PhoneId</strong> 。</span><span class="sxs-lookup"><span data-stu-id="b9574-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="b9574-131">有关详细信息，请参阅<a href="lync-server-2013-phones-table.md">Lync Server 2013 中</a>的 "电话" 表。</span><span class="sxs-lookup"><span data-stu-id="b9574-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="b9574-132">如果 not NULL 且<strong>ToGatewayId</strong>不为 null，则呼叫接收器是 PSTN 用户。</span><span class="sxs-lookup"><span data-stu-id="b9574-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9574-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="b9574-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b9574-134">int</span><span class="sxs-lookup"><span data-stu-id="b9574-134">int</span></span></p></td>
<td><p><span data-ttu-id="b9574-135">外表</span><span class="sxs-lookup"><span data-stu-id="b9574-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b9574-136">呼叫来自的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="b9574-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="b9574-137">有关详细信息，请参阅<a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表</a>。</span><span class="sxs-lookup"><span data-stu-id="b9574-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9574-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="b9574-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="b9574-139">int</span><span class="sxs-lookup"><span data-stu-id="b9574-139">int</span></span></p></td>
<td><p><span data-ttu-id="b9574-140">外表</span><span class="sxs-lookup"><span data-stu-id="b9574-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b9574-141">将调用的中介服务器将转到。</span><span class="sxs-lookup"><span data-stu-id="b9574-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="b9574-142">有关详细信息，请参阅<a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表</a>。</span><span class="sxs-lookup"><span data-stu-id="b9574-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9574-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="b9574-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="b9574-144">int</span><span class="sxs-lookup"><span data-stu-id="b9574-144">int</span></span></p></td>
<td><p><span data-ttu-id="b9574-145">外表</span><span class="sxs-lookup"><span data-stu-id="b9574-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b9574-146">呼叫的网关来自。</span><span class="sxs-lookup"><span data-stu-id="b9574-146">Gateway the call is coming from.</span></span> <span data-ttu-id="b9574-147">有关详细信息，请参阅<a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的网关表</a>。</span><span class="sxs-lookup"><span data-stu-id="b9574-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9574-148"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="b9574-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="b9574-149">int</span><span class="sxs-lookup"><span data-stu-id="b9574-149">int</span></span></p></td>
<td><p><span data-ttu-id="b9574-150">外表</span><span class="sxs-lookup"><span data-stu-id="b9574-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b9574-151">呼叫将转网网关。</span><span class="sxs-lookup"><span data-stu-id="b9574-151">Gateway the call is going to.</span></span> <span data-ttu-id="b9574-152">有关详细信息，请参阅<a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的网关表</a>。</span><span class="sxs-lookup"><span data-stu-id="b9574-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9574-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="b9574-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="b9574-154">int</span><span class="sxs-lookup"><span data-stu-id="b9574-154">int</span></span></p></td>
<td><p><span data-ttu-id="b9574-155">外表</span><span class="sxs-lookup"><span data-stu-id="b9574-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b9574-156">断开呼叫的用户的 URI （如果用户具有 URI）。</span><span class="sxs-lookup"><span data-stu-id="b9574-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="b9574-157">有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 "用户" 表。</span><span class="sxs-lookup"><span data-stu-id="b9574-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9574-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="b9574-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="b9574-159">int</span><span class="sxs-lookup"><span data-stu-id="b9574-159">int</span></span></p></td>
<td><p><span data-ttu-id="b9574-160">外表</span><span class="sxs-lookup"><span data-stu-id="b9574-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b9574-161">断开通话的电话的 ID 已断开与电话的连接。</span><span class="sxs-lookup"><span data-stu-id="b9574-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="b9574-162">有关详细信息，请参阅<a href="lync-server-2013-phones-table.md">Lync Server 2013 中</a>的 "电话" 表。</span><span class="sxs-lookup"><span data-stu-id="b9574-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

