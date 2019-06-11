---
title: 'Lync Server 2013: 会议视图'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 710aadb2770e9389d9e4becf206d68b8e8d815ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="26838-102">Lync Server 2013 中的 "会议" 视图</span><span class="sxs-lookup"><span data-stu-id="26838-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26838-103">_**主题上次修改时间:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="26838-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="26838-104">"会议" 视图存储有关会议的信息。</span><span class="sxs-lookup"><span data-stu-id="26838-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="26838-105">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="26838-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="26838-106">列</span><span class="sxs-lookup"><span data-stu-id="26838-106">Column</span></span></th>
<th><span data-ttu-id="26838-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="26838-107">Data Type</span></span></th>
<th><span data-ttu-id="26838-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="26838-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26838-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="26838-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="26838-110">datetime</span><span class="sxs-lookup"><span data-stu-id="26838-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="26838-111">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="26838-111">Time of session request.</span></span> <span data-ttu-id="26838-112">与 SessionIdSeq 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="26838-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="26838-113">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="26838-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26838-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="26838-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="26838-115">int</span><span class="sxs-lookup"><span data-stu-id="26838-115">int</span></span></p></td>
<td><p><span data-ttu-id="26838-116">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="26838-116">ID number to identify the session.</span></span> <span data-ttu-id="26838-117">与 SessionIdTime 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="26838-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="26838-118">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="26838-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26838-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="26838-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="26838-120">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="26838-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="26838-121">会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="26838-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26838-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="26838-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="26838-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="26838-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26838-124">会议 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="26838-124">Type of the conference URI.</span></span> <span data-ttu-id="26838-125">有关详细信息, 请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="26838-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26838-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="26838-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="26838-127">标识符</span><span class="sxs-lookup"><span data-stu-id="26838-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="26838-128">用于定期会议。</span><span class="sxs-lookup"><span data-stu-id="26838-128">Used for recurring conferences.</span></span> <span data-ttu-id="26838-129">定期会议的每个实例都具有相同的 ConferenceUri, 但具有不同的 ConfInstance。</span><span class="sxs-lookup"><span data-stu-id="26838-129">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26838-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="26838-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="26838-131">datetime</span><span class="sxs-lookup"><span data-stu-id="26838-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="26838-132">会议的开始时间。</span><span class="sxs-lookup"><span data-stu-id="26838-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26838-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="26838-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="26838-134">datetime</span><span class="sxs-lookup"><span data-stu-id="26838-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="26838-135">会议的结束时间。</span><span class="sxs-lookup"><span data-stu-id="26838-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26838-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="26838-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="26838-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="26838-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="26838-138">组织会议的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="26838-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26838-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="26838-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="26838-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="26838-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26838-141">组织会议的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="26838-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="26838-142">有关详细信息, 请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="26838-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26838-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="26838-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="26838-144">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="26838-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26838-145">组织会议的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="26838-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="26838-146">有关详细信息, 请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="26838-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26838-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="26838-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="26838-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="26838-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="26838-149">托管会议的池的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="26838-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26838-150"><strong>旗</strong></span><span class="sxs-lookup"><span data-stu-id="26838-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="26838-151">smallint</span><span class="sxs-lookup"><span data-stu-id="26838-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="26838-152">包含会议属性的位掩码。</span><span class="sxs-lookup"><span data-stu-id="26838-152">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="26838-153">可能的值：</span><span class="sxs-lookup"><span data-stu-id="26838-153">Possible values are:</span></span></p>
<p><span data-ttu-id="26838-154">0X01-合成事务</span><span class="sxs-lookup"><span data-stu-id="26838-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

