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
ms.openlocfilehash: e94771b1dab86bdad627e2634c84001749a4ad0c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="47171-102">Lync Server 2013 中的会议视图</span><span class="sxs-lookup"><span data-stu-id="47171-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47171-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="47171-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="47171-104">“会议”视图会存储有关会议的信息。</span><span class="sxs-lookup"><span data-stu-id="47171-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="47171-105">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="47171-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47171-106">列</span><span class="sxs-lookup"><span data-stu-id="47171-106">Column</span></span></th>
<th><span data-ttu-id="47171-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="47171-107">Data Type</span></span></th>
<th><span data-ttu-id="47171-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="47171-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47171-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="47171-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="47171-110">datetime</span><span class="sxs-lookup"><span data-stu-id="47171-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="47171-111">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="47171-111">Time of session request.</span></span> <span data-ttu-id="47171-112">与 SessionIdSeq 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="47171-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="47171-113">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="47171-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47171-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="47171-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="47171-115">int</span><span class="sxs-lookup"><span data-stu-id="47171-115">int</span></span></p></td>
<td><p><span data-ttu-id="47171-116">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="47171-116">ID number to identify the session.</span></span> <span data-ttu-id="47171-117">与 SessionIdTime 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="47171-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="47171-118">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="47171-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47171-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="47171-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="47171-120">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="47171-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="47171-121">会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="47171-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47171-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="47171-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="47171-123">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="47171-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="47171-124">会议 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="47171-124">Type of the conference URI.</span></span> <span data-ttu-id="47171-125">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="47171-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47171-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="47171-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="47171-127">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="47171-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="47171-p105">用于定期会议。定期会议的每个实例都具有相同的 ConferenceUri，但 ConfInstance 不同。</span><span class="sxs-lookup"><span data-stu-id="47171-p105">Used for recurring conferences. Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47171-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="47171-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="47171-131">datetime</span><span class="sxs-lookup"><span data-stu-id="47171-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="47171-132">会议的开始时间。</span><span class="sxs-lookup"><span data-stu-id="47171-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47171-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="47171-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="47171-134">datetime</span><span class="sxs-lookup"><span data-stu-id="47171-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="47171-135">会议的结束时间。</span><span class="sxs-lookup"><span data-stu-id="47171-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47171-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="47171-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="47171-137">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="47171-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="47171-138">组织会议的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="47171-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47171-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="47171-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="47171-140">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="47171-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="47171-141">组织会议的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="47171-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="47171-142">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="47171-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47171-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="47171-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="47171-144">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="47171-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="47171-145">组织会议的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="47171-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="47171-146">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="47171-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47171-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="47171-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="47171-148">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="47171-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="47171-149">承载会议的池的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="47171-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47171-150"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="47171-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="47171-151">smallint</span><span class="sxs-lookup"><span data-stu-id="47171-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="47171-p108">包含会议属性的位掩码。可能的值包括：</span><span class="sxs-lookup"><span data-stu-id="47171-p108">Bit mask that contains Conference Attributes. Possible values are:</span></span></p>
<p><span data-ttu-id="47171-154">0X01 – 综合事务</span><span class="sxs-lookup"><span data-stu-id="47171-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

