---
title: Lync Server 2013： VoipDetails 表
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
ms.openlocfilehash: 26feac5b9995aa1a8444029442adcb9c935083d3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535409"
---
# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="ebfd3-102">Lync Server 2013 中的 VoipDetails 表</span><span class="sxs-lookup"><span data-stu-id="ebfd3-102">VoipDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ebfd3-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ebfd3-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ebfd3-104">每条记录均表示一个其中至少有一个用户是 VoIP 用户的双方呼叫。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-104">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ebfd3-105">列</span><span class="sxs-lookup"><span data-stu-id="ebfd3-105">Column</span></span></th>
<th><span data-ttu-id="ebfd3-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="ebfd3-106">Data Type</span></span></th>
<th><span data-ttu-id="ebfd3-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="ebfd3-107">Key/Index</span></span></th>
<th><span data-ttu-id="ebfd3-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="ebfd3-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ebfd3-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ebfd3-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ebfd3-110">datetime</span><span class="sxs-lookup"><span data-stu-id="ebfd3-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="ebfd3-111">主</span><span class="sxs-lookup"><span data-stu-id="ebfd3-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="ebfd3-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-112">Time of session request.</span></span> <span data-ttu-id="ebfd3-113">与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ebfd3-114">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebfd3-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ebfd3-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ebfd3-116">int</span><span class="sxs-lookup"><span data-stu-id="ebfd3-116">int</span></span></p></td>
<td><p><span data-ttu-id="ebfd3-117">主</span><span class="sxs-lookup"><span data-stu-id="ebfd3-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="ebfd3-118">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-118">ID number to identify the session.</span></span> <span data-ttu-id="ebfd3-119">与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ebfd3-120">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebfd3-121"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="ebfd3-121"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="ebfd3-122">int</span><span class="sxs-lookup"><span data-stu-id="ebfd3-122">int</span></span></p></td>
<td><p><span data-ttu-id="ebfd3-123">对外</span><span class="sxs-lookup"><span data-stu-id="ebfd3-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ebfd3-124">呼叫者的 <strong>PhoneId</strong>。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-124"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="ebfd3-125">有关详细信息，请参阅 <a href="lync-server-2013-phones-table.md">Lync Server 2013 中的电话表</a> 。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-125">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="ebfd3-126">如果不为 null，并且 <strong>FromGatewayId</strong> 也为不为 null，则呼叫者是 PSTN 用户。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-126">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebfd3-127"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="ebfd3-127"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="ebfd3-128">int</span><span class="sxs-lookup"><span data-stu-id="ebfd3-128">int</span></span></p></td>
<td><p><span data-ttu-id="ebfd3-129">对外</span><span class="sxs-lookup"><span data-stu-id="ebfd3-129">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ebfd3-130">呼叫接收者的 <strong>PhoneId</strong>。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-130"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="ebfd3-131">有关详细信息，请参阅 <a href="lync-server-2013-phones-table.md">Lync Server 2013 中的电话表</a> 。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-131">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="ebfd3-132">如果不为 null，并且 <strong>ToGatewayId</strong> 也为不为 null，则呼叫接收者是 PSTN 用户。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-132">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebfd3-133"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="ebfd3-133"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ebfd3-134">int</span><span class="sxs-lookup"><span data-stu-id="ebfd3-134">int</span></span></p></td>
<td><p><span data-ttu-id="ebfd3-135">对外</span><span class="sxs-lookup"><span data-stu-id="ebfd3-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ebfd3-136">呼叫的源中介服务器。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-136">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="ebfd3-137">有关详细信息，请参阅 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-137">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebfd3-138"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="ebfd3-138"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="ebfd3-139">int</span><span class="sxs-lookup"><span data-stu-id="ebfd3-139">int</span></span></p></td>
<td><p><span data-ttu-id="ebfd3-140">对外</span><span class="sxs-lookup"><span data-stu-id="ebfd3-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ebfd3-141">呼叫的目标中介服务器。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-141">The Mediation Server called is going to.</span></span> <span data-ttu-id="ebfd3-142">有关详细信息，请参阅 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-142">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebfd3-143"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="ebfd3-143"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="ebfd3-144">int</span><span class="sxs-lookup"><span data-stu-id="ebfd3-144">int</span></span></p></td>
<td><p><span data-ttu-id="ebfd3-145">对外</span><span class="sxs-lookup"><span data-stu-id="ebfd3-145">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ebfd3-146">呼叫的源网关。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-146">Gateway the call is coming from.</span></span> <span data-ttu-id="ebfd3-147">有关详细信息，请参阅 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的网关表</a> 。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-147">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebfd3-148"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="ebfd3-148"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="ebfd3-149">int</span><span class="sxs-lookup"><span data-stu-id="ebfd3-149">int</span></span></p></td>
<td><p><span data-ttu-id="ebfd3-150">对外</span><span class="sxs-lookup"><span data-stu-id="ebfd3-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ebfd3-151">呼叫的目标网关。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-151">Gateway the call is going to.</span></span> <span data-ttu-id="ebfd3-152">有关详细信息，请参阅 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的网关表</a> 。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-152">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ebfd3-153"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="ebfd3-153"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="ebfd3-154">int</span><span class="sxs-lookup"><span data-stu-id="ebfd3-154">int</span></span></p></td>
<td><p><span data-ttu-id="ebfd3-155">对外</span><span class="sxs-lookup"><span data-stu-id="ebfd3-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ebfd3-156">断开呼叫的用户的 URI（如果用户具有 URI）。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-156">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="ebfd3-157">有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ebfd3-158"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="ebfd3-158"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="ebfd3-159">int</span><span class="sxs-lookup"><span data-stu-id="ebfd3-159">int</span></span></p></td>
<td><p><span data-ttu-id="ebfd3-160">对外</span><span class="sxs-lookup"><span data-stu-id="ebfd3-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ebfd3-161">断开呼叫的电话的 ID。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-161">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="ebfd3-162">有关详细信息，请参阅 <a href="lync-server-2013-phones-table.md">Lync Server 2013 中的电话表</a> 。</span><span class="sxs-lookup"><span data-stu-id="ebfd3-162">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

