---
title: Lync Server 2013：Conferences 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17cbadaf18fa36ca55f7755b5e679e564163a207
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="8475a-102">Lync Server 2013 中的 Conferences 表</span><span class="sxs-lookup"><span data-stu-id="8475a-102">Conferences table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8475a-103">_**主题上次修改时间:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="8475a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="8475a-104">此表中的每条记录包含有关一次会议的通话详细信息。</span><span class="sxs-lookup"><span data-stu-id="8475a-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8475a-105">列</span><span class="sxs-lookup"><span data-stu-id="8475a-105">Column</span></span></th>
<th><span data-ttu-id="8475a-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="8475a-106">Data Type</span></span></th>
<th><span data-ttu-id="8475a-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="8475a-107">Key/Index</span></span></th>
<th><span data-ttu-id="8475a-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="8475a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8475a-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="8475a-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8475a-110">datetime</span><span class="sxs-lookup"><span data-stu-id="8475a-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="8475a-111">Primary</span><span class="sxs-lookup"><span data-stu-id="8475a-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="8475a-112">由 CDR 代理捕获会议请求的时间。</span><span class="sxs-lookup"><span data-stu-id="8475a-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="8475a-113">仅用作主键以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="8475a-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8475a-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8475a-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8475a-115">int</span><span class="sxs-lookup"><span data-stu-id="8475a-115">int</span></span></p></td>
<td><p><span data-ttu-id="8475a-116">Primary</span><span class="sxs-lookup"><span data-stu-id="8475a-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="8475a-117">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="8475a-117">ID number to identify the session.</span></span> <span data-ttu-id="8475a-118">与<strong>SessionIdTime</strong>结合使用以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="8475a-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8475a-119"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="8475a-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="8475a-120">int</span><span class="sxs-lookup"><span data-stu-id="8475a-120">int</span></span></p></td>
<td><p><span data-ttu-id="8475a-121">外表</span><span class="sxs-lookup"><span data-stu-id="8475a-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8475a-122">会议 URI。</span><span class="sxs-lookup"><span data-stu-id="8475a-122">Conference URI.</span></span> <span data-ttu-id="8475a-123">有关详细信息, 请参阅<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a>。</span><span class="sxs-lookup"><span data-stu-id="8475a-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8475a-124"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="8475a-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="8475a-125">标识符</span><span class="sxs-lookup"><span data-stu-id="8475a-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8475a-126">适用于定期会议;定期会议的每个实例都具有相同的<strong>ConferenceUri</strong>, 但将具有不同的<strong>ConfInstance</strong>。</span><span class="sxs-lookup"><span data-stu-id="8475a-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8475a-127"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="8475a-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8475a-128">datetime</span><span class="sxs-lookup"><span data-stu-id="8475a-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8475a-129">会议开始时间。</span><span class="sxs-lookup"><span data-stu-id="8475a-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8475a-130"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="8475a-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8475a-131">datetime</span><span class="sxs-lookup"><span data-stu-id="8475a-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8475a-132">会议开始时间。</span><span class="sxs-lookup"><span data-stu-id="8475a-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8475a-133"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="8475a-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="8475a-134">int</span><span class="sxs-lookup"><span data-stu-id="8475a-134">int</span></span></p></td>
<td><p><span data-ttu-id="8475a-135">外表</span><span class="sxs-lookup"><span data-stu-id="8475a-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8475a-136">标识在其中捕获会议的池的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="8475a-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="8475a-137">有关详细信息, 请参阅<a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表</a>。</span><span class="sxs-lookup"><span data-stu-id="8475a-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8475a-138"><strong>OrganizerId</strong></span><span class="sxs-lookup"><span data-stu-id="8475a-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="8475a-139">整形</span><span class="sxs-lookup"><span data-stu-id="8475a-139">Int</span></span></p></td>
<td><p><span data-ttu-id="8475a-140">外表</span><span class="sxs-lookup"><span data-stu-id="8475a-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8475a-141">标识此会议的组织者 URI 的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="8475a-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="8475a-142">有关详细信息, 请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 "用户" 表。</span><span class="sxs-lookup"><span data-stu-id="8475a-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8475a-143"><strong>旗</strong></span><span class="sxs-lookup"><span data-stu-id="8475a-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="8475a-144">smallint</span><span class="sxs-lookup"><span data-stu-id="8475a-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8475a-145">包含会议属性的位掩码。</span><span class="sxs-lookup"><span data-stu-id="8475a-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="8475a-146">可能的值：</span><span class="sxs-lookup"><span data-stu-id="8475a-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="8475a-147">0X01</span><span class="sxs-lookup"><span data-stu-id="8475a-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="8475a-148">合成</span><span class="sxs-lookup"><span data-stu-id="8475a-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="8475a-149">事务</span><span class="sxs-lookup"><span data-stu-id="8475a-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8475a-150"><strong>过</strong></span><span class="sxs-lookup"><span data-stu-id="8475a-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="8475a-151">bit</span><span class="sxs-lookup"><span data-stu-id="8475a-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8475a-152">监视服务使用的内部字段。</span><span class="sxs-lookup"><span data-stu-id="8475a-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="8475a-153">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="8475a-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8475a-154">\*对于大多数会话, SessionIdSeq 将具有值1。</span><span class="sxs-lookup"><span data-stu-id="8475a-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="8475a-155">如果两个会话的开始时间完全相同, 则一个会话的 SessionIdSeq 将为 1, 而另一个会话将为 2, 依此类推。</span><span class="sxs-lookup"><span data-stu-id="8475a-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

