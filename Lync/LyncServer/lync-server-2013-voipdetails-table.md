---
title: Lync Server 2013： VoipDetails 表
description: Lync Server 2013： VoipDetails 表。
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
ms.openlocfilehash: f23d991c1d577a15717de2572d744e1b65ba6bab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566278"
---
# <a name="voipdetails-table-in-lync-server-2013"></a><span data-ttu-id="40e7d-103">Lync Server 2013 中的 VoipDetails 表</span><span class="sxs-lookup"><span data-stu-id="40e7d-103">VoipDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40e7d-104">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="40e7d-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="40e7d-105">每条记录均表示一个其中至少有一个用户是 VoIP 用户的双方呼叫。</span><span class="sxs-lookup"><span data-stu-id="40e7d-105">Each record represents one two-party call in which at least one user is a VoIP user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="40e7d-106">列</span><span class="sxs-lookup"><span data-stu-id="40e7d-106">Column</span></span></th>
<th><span data-ttu-id="40e7d-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="40e7d-107">Data Type</span></span></th>
<th><span data-ttu-id="40e7d-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="40e7d-108">Key/Index</span></span></th>
<th><span data-ttu-id="40e7d-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="40e7d-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="40e7d-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="40e7d-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="40e7d-111">datetime</span><span class="sxs-lookup"><span data-stu-id="40e7d-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="40e7d-112">主</span><span class="sxs-lookup"><span data-stu-id="40e7d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="40e7d-113">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="40e7d-113">Time of session request.</span></span> <span data-ttu-id="40e7d-114">与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="40e7d-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="40e7d-115">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="40e7d-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40e7d-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="40e7d-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="40e7d-117">int</span><span class="sxs-lookup"><span data-stu-id="40e7d-117">int</span></span></p></td>
<td><p><span data-ttu-id="40e7d-118">主</span><span class="sxs-lookup"><span data-stu-id="40e7d-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="40e7d-119">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="40e7d-119">ID number to identify the session.</span></span> <span data-ttu-id="40e7d-120">与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="40e7d-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="40e7d-121">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="40e7d-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40e7d-122"><strong>FromNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="40e7d-122"><strong>FromNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="40e7d-123">int</span><span class="sxs-lookup"><span data-stu-id="40e7d-123">int</span></span></p></td>
<td><p><span data-ttu-id="40e7d-124">对外</span><span class="sxs-lookup"><span data-stu-id="40e7d-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="40e7d-125">呼叫者的 <strong>PhoneId</strong>。</span><span class="sxs-lookup"><span data-stu-id="40e7d-125"><strong>PhoneId</strong> of the caller.</span></span> <span data-ttu-id="40e7d-126">有关详细信息，请参阅 <a href="lync-server-2013-phones-table.md">Lync Server 2013 中的电话表</a> 。</span><span class="sxs-lookup"><span data-stu-id="40e7d-126">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="40e7d-127">如果不为 null，并且 <strong>FromGatewayId</strong> 也为不为 null，则呼叫者是 PSTN 用户。</span><span class="sxs-lookup"><span data-stu-id="40e7d-127">If not NULL and <strong>FromGatewayId</strong> is not NULL, then the caller was a PSTN user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40e7d-128"><strong>ConnectedNumberId</strong></span><span class="sxs-lookup"><span data-stu-id="40e7d-128"><strong>ConnectedNumberId</strong></span></span></p></td>
<td><p><span data-ttu-id="40e7d-129">int</span><span class="sxs-lookup"><span data-stu-id="40e7d-129">int</span></span></p></td>
<td><p><span data-ttu-id="40e7d-130">对外</span><span class="sxs-lookup"><span data-stu-id="40e7d-130">Foreign</span></span></p></td>
<td><p><span data-ttu-id="40e7d-131">呼叫接收者的 <strong>PhoneId</strong>。</span><span class="sxs-lookup"><span data-stu-id="40e7d-131"><strong>PhoneId</strong> of the call receiver.</span></span> <span data-ttu-id="40e7d-132">有关详细信息，请参阅 <a href="lync-server-2013-phones-table.md">Lync Server 2013 中的电话表</a> 。</span><span class="sxs-lookup"><span data-stu-id="40e7d-132">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="40e7d-133">如果不为 null，并且 <strong>ToGatewayId</strong> 也为不为 null，则呼叫接收者是 PSTN 用户。</span><span class="sxs-lookup"><span data-stu-id="40e7d-133">If not NULL and <strong>ToGatewayId</strong> is not NULL, then the call receiver was a PSTN user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40e7d-134"><strong>FromMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="40e7d-134"><strong>FromMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="40e7d-135">int</span><span class="sxs-lookup"><span data-stu-id="40e7d-135">int</span></span></p></td>
<td><p><span data-ttu-id="40e7d-136">对外</span><span class="sxs-lookup"><span data-stu-id="40e7d-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="40e7d-137">呼叫的源中介服务器。</span><span class="sxs-lookup"><span data-stu-id="40e7d-137">The Mediation Server the call is coming from.</span></span> <span data-ttu-id="40e7d-138">有关详细信息，请参阅 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="40e7d-138">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40e7d-139"><strong>ToMediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="40e7d-139"><strong>ToMediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="40e7d-140">int</span><span class="sxs-lookup"><span data-stu-id="40e7d-140">int</span></span></p></td>
<td><p><span data-ttu-id="40e7d-141">对外</span><span class="sxs-lookup"><span data-stu-id="40e7d-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="40e7d-142">呼叫的目标中介服务器。</span><span class="sxs-lookup"><span data-stu-id="40e7d-142">The Mediation Server called is going to.</span></span> <span data-ttu-id="40e7d-143">有关详细信息，请参阅 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="40e7d-143">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40e7d-144"><strong>FromGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="40e7d-144"><strong>FromGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="40e7d-145">int</span><span class="sxs-lookup"><span data-stu-id="40e7d-145">int</span></span></p></td>
<td><p><span data-ttu-id="40e7d-146">对外</span><span class="sxs-lookup"><span data-stu-id="40e7d-146">Foreign</span></span></p></td>
<td><p><span data-ttu-id="40e7d-147">呼叫的源网关。</span><span class="sxs-lookup"><span data-stu-id="40e7d-147">Gateway the call is coming from.</span></span> <span data-ttu-id="40e7d-148">有关详细信息，请参阅 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的网关表</a> 。</span><span class="sxs-lookup"><span data-stu-id="40e7d-148">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40e7d-149"><strong>ToGatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="40e7d-149"><strong>ToGatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="40e7d-150">int</span><span class="sxs-lookup"><span data-stu-id="40e7d-150">int</span></span></p></td>
<td><p><span data-ttu-id="40e7d-151">对外</span><span class="sxs-lookup"><span data-stu-id="40e7d-151">Foreign</span></span></p></td>
<td><p><span data-ttu-id="40e7d-152">呼叫的目标网关。</span><span class="sxs-lookup"><span data-stu-id="40e7d-152">Gateway the call is going to.</span></span> <span data-ttu-id="40e7d-153">有关详细信息，请参阅 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的网关表</a> 。</span><span class="sxs-lookup"><span data-stu-id="40e7d-153">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="40e7d-154"><strong>DisconnectedbyURIId</strong></span><span class="sxs-lookup"><span data-stu-id="40e7d-154"><strong>DisconnectedbyURIId</strong></span></span></p></td>
<td><p><span data-ttu-id="40e7d-155">int</span><span class="sxs-lookup"><span data-stu-id="40e7d-155">int</span></span></p></td>
<td><p><span data-ttu-id="40e7d-156">对外</span><span class="sxs-lookup"><span data-stu-id="40e7d-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="40e7d-157">断开呼叫的用户的 URI（如果用户具有 URI）。</span><span class="sxs-lookup"><span data-stu-id="40e7d-157">URI of the user who disconnected the call, if the user has a URI.</span></span> <span data-ttu-id="40e7d-158">有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="40e7d-158">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="40e7d-159"><strong>DisconnectedbyPhoneId</strong></span><span class="sxs-lookup"><span data-stu-id="40e7d-159"><strong>DisconnectedbyPhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="40e7d-160">int</span><span class="sxs-lookup"><span data-stu-id="40e7d-160">int</span></span></p></td>
<td><p><span data-ttu-id="40e7d-161">对外</span><span class="sxs-lookup"><span data-stu-id="40e7d-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="40e7d-162">断开呼叫的电话的 ID。</span><span class="sxs-lookup"><span data-stu-id="40e7d-162">ID of the phone that disconnected the call was disconnected from a phone.</span></span> <span data-ttu-id="40e7d-163">有关详细信息，请参阅 <a href="lync-server-2013-phones-table.md">Lync Server 2013 中的电话表</a> 。</span><span class="sxs-lookup"><span data-stu-id="40e7d-163">See the <a href="lync-server-2013-phones-table.md">Phones table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

