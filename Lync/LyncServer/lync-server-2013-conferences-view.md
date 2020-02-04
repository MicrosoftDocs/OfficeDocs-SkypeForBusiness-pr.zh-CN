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
ms.openlocfilehash: 36278c1053c2b5737e0de6caf914c050db93ea4b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="2d607-102">Lync Server 2013 中的 "会议" 视图</span><span class="sxs-lookup"><span data-stu-id="2d607-102">Conferences view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d607-103">_**主题上次修改时间：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2d607-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2d607-104">"会议" 视图存储有关会议的信息。</span><span class="sxs-lookup"><span data-stu-id="2d607-104">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="2d607-105">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="2d607-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2d607-106">列</span><span class="sxs-lookup"><span data-stu-id="2d607-106">Column</span></span></th>
<th><span data-ttu-id="2d607-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="2d607-107">Data Type</span></span></th>
<th><span data-ttu-id="2d607-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="2d607-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2d607-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="2d607-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2d607-110">datetime</span><span class="sxs-lookup"><span data-stu-id="2d607-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="2d607-111">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="2d607-111">Time of session request.</span></span> <span data-ttu-id="2d607-112">与 SessionIdSeq 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="2d607-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="2d607-113">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="2d607-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d607-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2d607-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2d607-115">int</span><span class="sxs-lookup"><span data-stu-id="2d607-115">int</span></span></p></td>
<td><p><span data-ttu-id="2d607-116">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="2d607-116">ID number to identify the session.</span></span> <span data-ttu-id="2d607-117">与 SessionIdTime 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="2d607-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="2d607-118">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="2d607-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d607-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="2d607-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2d607-120">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="2d607-120">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2d607-121">会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="2d607-121">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d607-122"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="2d607-122"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="2d607-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2d607-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2d607-124">会议 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="2d607-124">Type of the conference URI.</span></span> <span data-ttu-id="2d607-125">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="2d607-125">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d607-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="2d607-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="2d607-127">标识符</span><span class="sxs-lookup"><span data-stu-id="2d607-127">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="2d607-128">用于定期会议。</span><span class="sxs-lookup"><span data-stu-id="2d607-128">Used for recurring conferences.</span></span> <span data-ttu-id="2d607-129">定期会议的每个实例都具有相同的 ConferenceUri，但具有不同的 ConfInstance。</span><span class="sxs-lookup"><span data-stu-id="2d607-129">Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d607-130"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="2d607-130"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2d607-131">datetime</span><span class="sxs-lookup"><span data-stu-id="2d607-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="2d607-132">会议的开始时间。</span><span class="sxs-lookup"><span data-stu-id="2d607-132">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d607-133"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="2d607-133"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2d607-134">datetime</span><span class="sxs-lookup"><span data-stu-id="2d607-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="2d607-135">会议的结束时间。</span><span class="sxs-lookup"><span data-stu-id="2d607-135">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d607-136"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="2d607-136"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2d607-137">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="2d607-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2d607-138">组织会议的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="2d607-138">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d607-139"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="2d607-139"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="2d607-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2d607-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2d607-141">组织会议的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="2d607-141">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="2d607-142">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="2d607-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d607-143"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="2d607-143"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="2d607-144">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2d607-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2d607-145">组织会议的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="2d607-145">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="2d607-146">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="2d607-146">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2d607-147"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="2d607-147"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="2d607-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2d607-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2d607-149">托管会议的池的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="2d607-149">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2d607-150"><strong>旗</strong></span><span class="sxs-lookup"><span data-stu-id="2d607-150"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="2d607-151">smallint</span><span class="sxs-lookup"><span data-stu-id="2d607-151">smallint</span></span></p></td>
<td><p><span data-ttu-id="2d607-152">包含会议属性的位掩码。</span><span class="sxs-lookup"><span data-stu-id="2d607-152">Bit mask that contains Conference Attributes.</span></span> <span data-ttu-id="2d607-153">可能的值：</span><span class="sxs-lookup"><span data-stu-id="2d607-153">Possible values are:</span></span></p>
<p><span data-ttu-id="2d607-154">0X01-合成事务</span><span class="sxs-lookup"><span data-stu-id="2d607-154">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

