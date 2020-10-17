---
title: Lync Server 2013：会议表
description: Lync Server 2013：会议表。
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
ms.openlocfilehash: 1e0d8c61e795dc0c8f9843b871d7e4efd1bec571
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561598"
---
# <a name="conferences-table-in-lync-server-2013"></a><span data-ttu-id="9adc6-103">Lync Server 2013 中的 "会议" 表</span><span class="sxs-lookup"><span data-stu-id="9adc6-103">Conferences table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9adc6-104">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9adc6-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9adc6-105">此表中的每条记录都包含有关一个会议的呼叫详细信息。</span><span class="sxs-lookup"><span data-stu-id="9adc6-105">Each record in this table contains call details about one conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9adc6-106">列</span><span class="sxs-lookup"><span data-stu-id="9adc6-106">Column</span></span></th>
<th><span data-ttu-id="9adc6-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="9adc6-107">Data Type</span></span></th>
<th><span data-ttu-id="9adc6-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="9adc6-108">Key/Index</span></span></th>
<th><span data-ttu-id="9adc6-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="9adc6-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9adc6-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9adc6-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9adc6-111">datetime</span><span class="sxs-lookup"><span data-stu-id="9adc6-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="9adc6-112">主</span><span class="sxs-lookup"><span data-stu-id="9adc6-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="9adc6-113">由 CDR 代理捕获会议请求的时间。</span><span class="sxs-lookup"><span data-stu-id="9adc6-113">Time that the conference request was captured by the CDR agent.</span></span> <span data-ttu-id="9adc6-114">仅用作用于唯一标识会议实例的主键。</span><span class="sxs-lookup"><span data-stu-id="9adc6-114">Used only as a primary key to uniquely identify a conference instance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9adc6-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9adc6-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9adc6-116">int</span><span class="sxs-lookup"><span data-stu-id="9adc6-116">int</span></span></p></td>
<td><p><span data-ttu-id="9adc6-117">主</span><span class="sxs-lookup"><span data-stu-id="9adc6-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="9adc6-118">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="9adc6-118">ID number to identify the session.</span></span> <span data-ttu-id="9adc6-119">与 <strong>SessionIdTime</strong> 结合使用，以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="9adc6-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9adc6-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="9adc6-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="9adc6-121">int</span><span class="sxs-lookup"><span data-stu-id="9adc6-121">int</span></span></p></td>
<td><p><span data-ttu-id="9adc6-122">对外</span><span class="sxs-lookup"><span data-stu-id="9adc6-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9adc6-123">会议 URI。</span><span class="sxs-lookup"><span data-stu-id="9adc6-123">Conference URI.</span></span> <span data-ttu-id="9adc6-124">有关详细信息，请参阅 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="9adc6-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9adc6-125"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="9adc6-125"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="9adc6-126">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="9adc6-126">uniqueidentifier</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9adc6-127">对定期会议有用;每个定期会议实例都具有相同的 <strong>ConferenceUri</strong>，但将具有不同的 <strong>ConfInstance</strong>。</span><span class="sxs-lookup"><span data-stu-id="9adc6-127">Useful for recurring conferences; each instance of a recurring conference has the same <strong>ConferenceUri</strong>, but will have a different <strong>ConfInstance</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9adc6-128"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="9adc6-128"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9adc6-129">datetime</span><span class="sxs-lookup"><span data-stu-id="9adc6-129">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9adc6-130">会议开始时间。</span><span class="sxs-lookup"><span data-stu-id="9adc6-130">Conference start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9adc6-131"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="9adc6-131"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9adc6-132">datetime</span><span class="sxs-lookup"><span data-stu-id="9adc6-132">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="9adc6-133">会议开始时间。</span><span class="sxs-lookup"><span data-stu-id="9adc6-133">Conference start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9adc6-134"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="9adc6-134"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="9adc6-135">int</span><span class="sxs-lookup"><span data-stu-id="9adc6-135">int</span></span></p></td>
<td><p><span data-ttu-id="9adc6-136">对外</span><span class="sxs-lookup"><span data-stu-id="9adc6-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9adc6-137">标识在其中捕获会议的池的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="9adc6-137">ID number to identify the pool in which the conference was captured.</span></span> <span data-ttu-id="9adc6-138">有关详细信息，请参阅 <a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="9adc6-138">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9adc6-139"><strong>OrganizerId</strong></span><span class="sxs-lookup"><span data-stu-id="9adc6-139"><strong>OrganizerId</strong></span></span></p></td>
<td><p><span data-ttu-id="9adc6-140">Int</span><span class="sxs-lookup"><span data-stu-id="9adc6-140">Int</span></span></p></td>
<td><p><span data-ttu-id="9adc6-141">对外</span><span class="sxs-lookup"><span data-stu-id="9adc6-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9adc6-142">标识此会议的组织者 URI 的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="9adc6-142">ID number to identify the organizer URI of this conference.</span></span> <span data-ttu-id="9adc6-143">有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="9adc6-143">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9adc6-144"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="9adc6-144"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="9adc6-145">smallint</span><span class="sxs-lookup"><span data-stu-id="9adc6-145">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9adc6-146">包含会议属性的位掩码。</span><span class="sxs-lookup"><span data-stu-id="9adc6-146">A bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="9adc6-147">可能的值是：</span><span class="sxs-lookup"><span data-stu-id="9adc6-147">Possible values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="9adc6-148">0X01</span><span class="sxs-lookup"><span data-stu-id="9adc6-148">0X01</span></span></p></li>
<li><p><span data-ttu-id="9adc6-149">合成</span><span class="sxs-lookup"><span data-stu-id="9adc6-149">Synthetic</span></span></p></li>
<li><p><span data-ttu-id="9adc6-150">事务</span><span class="sxs-lookup"><span data-stu-id="9adc6-150">Transaction</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9adc6-151"><strong>处理</strong></span><span class="sxs-lookup"><span data-stu-id="9adc6-151"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="9adc6-152">位</span><span class="sxs-lookup"><span data-stu-id="9adc6-152">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9adc6-153">监视服务使用的内部字段。</span><span class="sxs-lookup"><span data-stu-id="9adc6-153">Internal field used by the Monitoring service.</span></span></p>
<p><span data-ttu-id="9adc6-154">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="9adc6-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9adc6-155">\* 对于大多数会话，SessionIdSeq 的值将为1。</span><span class="sxs-lookup"><span data-stu-id="9adc6-155">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="9adc6-156">如果两个会话完全启动，则一个会话的 SessionIdSeq 将为1，而另一个会话将为2，依此类推。</span><span class="sxs-lookup"><span data-stu-id="9adc6-156">If two sessions start at exactly the same time, the SessionIdSeq for one will be 1, and for the other will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

