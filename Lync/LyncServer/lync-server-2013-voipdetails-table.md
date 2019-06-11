---
title: Lync Server 2013：VoipDetails 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7879f5dc7d5b884dfc2d3777ed4fa800978a3cff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="87698-102">Lync Server 2013 中的 VoipDetails 表</span><span class="sxs-lookup"><span data-stu-id="87698-102">VoipDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87698-103">_**主题上次修改时间:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="87698-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="87698-104">每条记录表示至少有一位用户是 VoIP 用户的 1 2 方呼叫。</span><span class="sxs-lookup"><span data-stu-id="87698-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87698-105">列</span><span class="sxs-lookup"><span data-stu-id="87698-105">Column</span></span></th>
<th><span data-ttu-id="87698-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="87698-106">Data Type</span></span></th>
<th><span data-ttu-id="87698-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="87698-107">Key/Index</span></span></th>
<th><span data-ttu-id="87698-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="87698-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87698-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="87698-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="87698-110">datetime</span><span class="sxs-lookup"><span data-stu-id="87698-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="87698-111">Primary</span><span class="sxs-lookup"><span data-stu-id="87698-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="87698-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="87698-112">Time of session request.</span></span> <span data-ttu-id="87698-113">与<strong>SessionIdSeq</strong>结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="87698-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="87698-114">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="87698-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87698-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="87698-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="87698-116">int</span><span class="sxs-lookup"><span data-stu-id="87698-116">int</span></span></p></td>
<td><p><span data-ttu-id="87698-117">Primary</span><span class="sxs-lookup"><span data-stu-id="87698-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="87698-118">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="87698-118">ID number to identify the session.</span></span> <span data-ttu-id="87698-119">与<strong>SessionIdTime</strong>结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="87698-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="87698-120">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="87698-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87698-121"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="87698-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="87698-122">int</span><span class="sxs-lookup"><span data-stu-id="87698-122">int</span></span></p></td>
<td><p><span data-ttu-id="87698-123">外表</span><span class="sxs-lookup"><span data-stu-id="87698-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="87698-124">呼叫方的<strong>PhoneId</strong> 。</span><span class="sxs-lookup"><span data-stu-id="87698-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="87698-125">有关详细信息, 请参阅<a href="lync-server-2013-phones-table.md">Lync Server 2013 中</a>的 "电话" 表。</span><span class="sxs-lookup"><span data-stu-id="87698-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="87698-126">如果 not NULL 且<strong>FromGatewayId</strong>不为 null, 则呼叫方是 PSTN 用户。</span><span class="sxs-lookup"><span data-stu-id="87698-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87698-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="87698-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="87698-128">int</span><span class="sxs-lookup"><span data-stu-id="87698-128">int</span></span></p></td>
<td><p><span data-ttu-id="87698-129">外表</span><span class="sxs-lookup"><span data-stu-id="87698-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="87698-130">呼叫接收器的<strong>PhoneId</strong> 。</span><span class="sxs-lookup"><span data-stu-id="87698-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="87698-131">有关详细信息, 请参阅<a href="lync-server-2013-phones-table.md">Lync Server 2013 中</a>的 "电话" 表。</span><span class="sxs-lookup"><span data-stu-id="87698-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="87698-132">如果 not NULL 且<strong>ToGatewayId</strong>不为 null, 则呼叫接收器是 PSTN 用户。</span><span class="sxs-lookup"><span data-stu-id="87698-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87698-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="87698-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="87698-134">int</span><span class="sxs-lookup"><span data-stu-id="87698-134">int</span></span></p></td>
<td><p><span data-ttu-id="87698-135">外表</span><span class="sxs-lookup"><span data-stu-id="87698-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="87698-136">呼叫来自的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="87698-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="87698-137">有关详细信息, 请参阅<a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表</a>。</span><span class="sxs-lookup"><span data-stu-id="87698-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87698-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="87698-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="87698-139">int</span><span class="sxs-lookup"><span data-stu-id="87698-139">int</span></span></p></td>
<td><p><span data-ttu-id="87698-140">外表</span><span class="sxs-lookup"><span data-stu-id="87698-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="87698-141">将调用的中介服务器将转到。</span><span class="sxs-lookup"><span data-stu-id="87698-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="87698-142">有关详细信息, 请参阅<a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表</a>。</span><span class="sxs-lookup"><span data-stu-id="87698-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87698-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="87698-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="87698-144">int</span><span class="sxs-lookup"><span data-stu-id="87698-144">int</span></span></p></td>
<td><p><span data-ttu-id="87698-145">外表</span><span class="sxs-lookup"><span data-stu-id="87698-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="87698-146">呼叫的网关来自。</span><span class="sxs-lookup"><span data-stu-id="87698-146">Gateway the call is coming from.</span></span> <span data-ttu-id="87698-147">有关详细信息, 请参阅<a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的网关表</a>。</span><span class="sxs-lookup"><span data-stu-id="87698-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87698-148"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="87698-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="87698-149">int</span><span class="sxs-lookup"><span data-stu-id="87698-149">int</span></span></p></td>
<td><p><span data-ttu-id="87698-150">外表</span><span class="sxs-lookup"><span data-stu-id="87698-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="87698-151">呼叫将转网网关。</span><span class="sxs-lookup"><span data-stu-id="87698-151">Gateway the call is going to.</span></span> <span data-ttu-id="87698-152">有关详细信息, 请参阅<a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的网关表</a>。</span><span class="sxs-lookup"><span data-stu-id="87698-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87698-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="87698-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="87698-154">int</span><span class="sxs-lookup"><span data-stu-id="87698-154">int</span></span></p></td>
<td><p><span data-ttu-id="87698-155">外表</span><span class="sxs-lookup"><span data-stu-id="87698-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="87698-156">断开呼叫的用户的 URI (如果用户具有 URI)。</span><span class="sxs-lookup"><span data-stu-id="87698-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="87698-157">有关详细信息, 请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 "用户" 表。</span><span class="sxs-lookup"><span data-stu-id="87698-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87698-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="87698-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="87698-159">int</span><span class="sxs-lookup"><span data-stu-id="87698-159">int</span></span></p></td>
<td><p><span data-ttu-id="87698-160">外表</span><span class="sxs-lookup"><span data-stu-id="87698-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="87698-161">断开通话的电话的 ID 已断开与电话的连接。</span><span class="sxs-lookup"><span data-stu-id="87698-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="87698-162">有关详细信息, 请参阅<a href="lync-server-2013-phones-table.md">Lync Server 2013 中</a>的 "电话" 表。</span><span class="sxs-lookup"><span data-stu-id="87698-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

