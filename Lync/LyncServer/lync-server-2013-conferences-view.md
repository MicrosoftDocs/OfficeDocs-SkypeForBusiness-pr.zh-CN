---
title: Lync Server 2013：会议视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences view
ms:assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721871(v=OCS.15)
ms:contentKeyID: 49733803
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f01d7fb0a2cb0526d4d6954b303a7cf78bb9333
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="e6a64-102">Lync Server 2013 中的会议视图</span><span class="sxs-lookup"><span data-stu-id="e6a64-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6a64-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e6a64-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e6a64-104">“会议”视图会存储有关会议的信息。</span><span class="sxs-lookup"><span data-stu-id="e6a64-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="e6a64-105">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="e6a64-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e6a64-106">列</span><span class="sxs-lookup"><span data-stu-id="e6a64-106">Column</span></span></th>
<th><span data-ttu-id="e6a64-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="e6a64-107">Data Type</span></span></th>
<th><span data-ttu-id="e6a64-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6a64-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e6a64-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e6a64-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e6a64-110">datetime</span><span class="sxs-lookup"><span data-stu-id="e6a64-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="e6a64-111">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="e6a64-111">Time of session request.</span></span> <span data-ttu-id="e6a64-112">与 SessionIdSeq 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="e6a64-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="e6a64-113">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="e6a64-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6a64-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e6a64-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e6a64-115">int</span><span class="sxs-lookup"><span data-stu-id="e6a64-115">int</span></span></p></td>
<td><p><span data-ttu-id="e6a64-116">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="e6a64-116">ID number to identify the session.</span></span> <span data-ttu-id="e6a64-117">与 SessionIdTime 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="e6a64-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="e6a64-118">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="e6a64-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6a64-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="e6a64-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e6a64-120">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="e6a64-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e6a64-121">会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="e6a64-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6a64-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e6a64-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e6a64-123">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e6a64-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6a64-124">会议 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="e6a64-124">Type of the conference URI.</span></span> <span data-ttu-id="e6a64-125">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e6a64-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6a64-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="e6a64-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e6a64-127">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="e6a64-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e6a64-p105">用于定期会议。定期会议的每个实例都具有相同的 ConferenceUri，但 ConfInstance 不同。</span><span class="sxs-lookup"><span data-stu-id="e6a64-p105">Used for recurring conferences. Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6a64-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="e6a64-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e6a64-131">datetime</span><span class="sxs-lookup"><span data-stu-id="e6a64-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="e6a64-132">会议的开始时间。</span><span class="sxs-lookup"><span data-stu-id="e6a64-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6a64-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="e6a64-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e6a64-134">datetime</span><span class="sxs-lookup"><span data-stu-id="e6a64-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="e6a64-135">会议的结束时间。</span><span class="sxs-lookup"><span data-stu-id="e6a64-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6a64-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="e6a64-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e6a64-137">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="e6a64-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e6a64-138">组织会议的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="e6a64-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6a64-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="e6a64-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="e6a64-140">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e6a64-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6a64-141">组织会议的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="e6a64-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="e6a64-142">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e6a64-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6a64-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e6a64-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e6a64-144">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e6a64-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6a64-145">组织会议的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="e6a64-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="e6a64-146">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="e6a64-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e6a64-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="e6a64-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e6a64-148">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="e6a64-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e6a64-149">承载会议的池的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="e6a64-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e6a64-150"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="e6a64-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="e6a64-151">smallint</span><span class="sxs-lookup"><span data-stu-id="e6a64-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="e6a64-p108">包含会议属性的位掩码。可能的值包括：</span><span class="sxs-lookup"><span data-stu-id="e6a64-p108">Bit mask that contains Conference Attributes. Possible values are:</span></span></p>
<p><span data-ttu-id="e6a64-154">0X01 – 综合事务</span><span class="sxs-lookup"><span data-stu-id="e6a64-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

