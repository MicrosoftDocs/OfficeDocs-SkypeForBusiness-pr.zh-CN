---
title: Lync Server 2013：会议表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3dbaf1a721433cc04aa681dad56d753de8bc9a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="46e74-102">Lync Server 2013 中的 "会议" 表</span><span class="sxs-lookup"><span data-stu-id="46e74-102">Conferences table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46e74-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="46e74-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="46e74-104">此表中的每条记录都包含有关一个会议的呼叫详细信息。</span><span class="sxs-lookup"><span data-stu-id="46e74-104">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46e74-105">列</span><span class="sxs-lookup"><span data-stu-id="46e74-105">Column</span></span></th>
<th><span data-ttu-id="46e74-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="46e74-106">Data Type</span></span></th>
<th><span data-ttu-id="46e74-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="46e74-107">Key/Index</span></span></th>
<th><span data-ttu-id="46e74-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="46e74-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46e74-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="46e74-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="46e74-110">datetime</span><span class="sxs-lookup"><span data-stu-id="46e74-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="46e74-111">主</span><span class="sxs-lookup"><span data-stu-id="46e74-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="46e74-112">由 CDR 代理捕获会议请求的时间。</span><span class="sxs-lookup"><span data-stu-id="46e74-112">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="46e74-113">仅用作用于唯一标识会议实例的主键。</span><span class="sxs-lookup"><span data-stu-id="46e74-113">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46e74-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="46e74-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="46e74-115">int</span><span class="sxs-lookup"><span data-stu-id="46e74-115">int</span></span></p></td>
<td><p><span data-ttu-id="46e74-116">主</span><span class="sxs-lookup"><span data-stu-id="46e74-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="46e74-117">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="46e74-117">ID number to identify the session.</span></span> <span data-ttu-id="46e74-118">与<strong>SessionIdTime</strong>结合使用，以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="46e74-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46e74-119"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="46e74-119"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="46e74-120">int</span><span class="sxs-lookup"><span data-stu-id="46e74-120">int</span></span></p></td>
<td><p><span data-ttu-id="46e74-121">对外</span><span class="sxs-lookup"><span data-stu-id="46e74-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="46e74-122">会议 URI。</span><span class="sxs-lookup"><span data-stu-id="46e74-122">Conference URI.</span></span> <span data-ttu-id="46e74-123">有关详细信息，请参阅<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a>。</span><span class="sxs-lookup"><span data-stu-id="46e74-123">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46e74-124"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="46e74-124"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="46e74-125">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="46e74-125">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="46e74-126">对定期会议有用;每个定期会议实例都具有相同的<strong>ConferenceUri</strong>，但将具有不同的<strong>ConfInstance</strong>。</span><span class="sxs-lookup"><span data-stu-id="46e74-126">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46e74-127"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="46e74-127"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="46e74-128">datetime</span><span class="sxs-lookup"><span data-stu-id="46e74-128">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="46e74-129">会议开始时间。</span><span class="sxs-lookup"><span data-stu-id="46e74-129">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46e74-130"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="46e74-130"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="46e74-131">datetime</span><span class="sxs-lookup"><span data-stu-id="46e74-131">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="46e74-132">会议开始时间。</span><span class="sxs-lookup"><span data-stu-id="46e74-132">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46e74-133"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="46e74-133"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="46e74-134">int</span><span class="sxs-lookup"><span data-stu-id="46e74-134">int</span></span></p></td>
<td><p><span data-ttu-id="46e74-135">对外</span><span class="sxs-lookup"><span data-stu-id="46e74-135">Foreign</span></span></p></td>
<td><p><span data-ttu-id="46e74-136">标识在其中捕获会议的池的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="46e74-136">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="46e74-137">有关详细信息，请参阅<a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表</a>。</span><span class="sxs-lookup"><span data-stu-id="46e74-137">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46e74-138"><strong>OrganizerId</strong></span><span class="sxs-lookup"><span data-stu-id="46e74-138"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="46e74-139">Int</span><span class="sxs-lookup"><span data-stu-id="46e74-139">Int</span></span></p></td>
<td><p><span data-ttu-id="46e74-140">对外</span><span class="sxs-lookup"><span data-stu-id="46e74-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="46e74-141">标识此会议的组织者 URI 的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="46e74-141">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="46e74-142">有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</span><span class="sxs-lookup"><span data-stu-id="46e74-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46e74-143"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="46e74-143"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="46e74-144">smallint</span><span class="sxs-lookup"><span data-stu-id="46e74-144">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="46e74-145">包含会议属性的位掩码。</span><span class="sxs-lookup"><span data-stu-id="46e74-145">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="46e74-146">可能的值是：</span><span class="sxs-lookup"><span data-stu-id="46e74-146">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="46e74-147">0X01</span><span class="sxs-lookup"><span data-stu-id="46e74-147">0X01</span></span></p></li>
<li><p><span data-ttu-id="46e74-148">合成</span><span class="sxs-lookup"><span data-stu-id="46e74-148">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="46e74-149">事务</span><span class="sxs-lookup"><span data-stu-id="46e74-149">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46e74-150"><strong>处理</strong></span><span class="sxs-lookup"><span data-stu-id="46e74-150"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="46e74-151">位</span><span class="sxs-lookup"><span data-stu-id="46e74-151">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="46e74-152">监视服务使用的内部字段。</span><span class="sxs-lookup"><span data-stu-id="46e74-152">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="46e74-153">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="46e74-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="46e74-154">\*对于大多数会话，SessionIdSeq 的值将为1。</span><span class="sxs-lookup"><span data-stu-id="46e74-154">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="46e74-155">如果两个会话完全启动，则一个会话的 SessionIdSeq 将为1，而另一个会话将为2，依此类推。</span><span class="sxs-lookup"><span data-stu-id="46e74-155">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

