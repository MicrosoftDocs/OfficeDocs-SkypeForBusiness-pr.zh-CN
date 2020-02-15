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
ms.openlocfilehash: 56f292a35f5e4f24ba5226e06a308e780ce5c687
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="05ebf-102">Lync Server 2013 中的会议视图</span><span class="sxs-lookup"><span data-stu-id="05ebf-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05ebf-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="05ebf-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="05ebf-104">“会议”视图会存储有关会议的信息。</span><span class="sxs-lookup"><span data-stu-id="05ebf-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="05ebf-105">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="05ebf-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05ebf-106">列</span><span class="sxs-lookup"><span data-stu-id="05ebf-106">Column</span></span></th>
<th><span data-ttu-id="05ebf-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="05ebf-107">Data Type</span></span></th>
<th><span data-ttu-id="05ebf-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="05ebf-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05ebf-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="05ebf-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="05ebf-110">datetime</span><span class="sxs-lookup"><span data-stu-id="05ebf-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="05ebf-111">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="05ebf-111">Time of session request.</span></span> <span data-ttu-id="05ebf-112">与 SessionIdSeq 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="05ebf-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="05ebf-113">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="05ebf-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ebf-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="05ebf-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="05ebf-115">int</span><span class="sxs-lookup"><span data-stu-id="05ebf-115">int</span></span></p></td>
<td><p><span data-ttu-id="05ebf-116">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="05ebf-116">ID number to identify the session.</span></span> <span data-ttu-id="05ebf-117">与 SessionIdTime 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="05ebf-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="05ebf-118">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="05ebf-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ebf-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="05ebf-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="05ebf-120">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="05ebf-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="05ebf-121">会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="05ebf-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ebf-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="05ebf-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="05ebf-123">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="05ebf-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="05ebf-124">会议 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="05ebf-124">Type of the conference URI.</span></span> <span data-ttu-id="05ebf-125">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="05ebf-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ebf-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="05ebf-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="05ebf-127">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="05ebf-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="05ebf-p105">用于定期会议。定期会议的每个实例都具有相同的 ConferenceUri，但 ConfInstance 不同。</span><span class="sxs-lookup"><span data-stu-id="05ebf-p105">Used for recurring conferences. Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ebf-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="05ebf-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="05ebf-131">datetime</span><span class="sxs-lookup"><span data-stu-id="05ebf-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="05ebf-132">会议的开始时间。</span><span class="sxs-lookup"><span data-stu-id="05ebf-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ebf-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="05ebf-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="05ebf-134">datetime</span><span class="sxs-lookup"><span data-stu-id="05ebf-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="05ebf-135">会议的结束时间。</span><span class="sxs-lookup"><span data-stu-id="05ebf-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ebf-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="05ebf-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="05ebf-137">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="05ebf-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="05ebf-138">组织会议的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="05ebf-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ebf-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="05ebf-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="05ebf-140">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="05ebf-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="05ebf-141">组织会议的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="05ebf-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="05ebf-142">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="05ebf-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ebf-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="05ebf-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="05ebf-144">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="05ebf-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="05ebf-145">组织会议的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="05ebf-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="05ebf-146">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="05ebf-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ebf-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="05ebf-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="05ebf-148">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="05ebf-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="05ebf-149">承载会议的池的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="05ebf-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ebf-150"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="05ebf-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="05ebf-151">smallint</span><span class="sxs-lookup"><span data-stu-id="05ebf-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="05ebf-p108">包含会议属性的位掩码。可能的值包括：</span><span class="sxs-lookup"><span data-stu-id="05ebf-p108">Bit mask that contains Conference Attributes. Possible values are:</span></span></p>
<p><span data-ttu-id="05ebf-154">0X01 – 综合事务</span><span class="sxs-lookup"><span data-stu-id="05ebf-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

