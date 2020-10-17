---
title: Lync Server 2013：会议视图
description: Lync Server 2013：会议视图。
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
ms.openlocfilehash: dee7fbb7c839c351fc9c81716a5800a678980549
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561578"
---
# <a name="conferences-view-in-lync-server-2013"></a><span data-ttu-id="1c90a-103">Lync Server 2013 中的会议视图</span><span class="sxs-lookup"><span data-stu-id="1c90a-103">Conferences view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c90a-104">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="1c90a-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="1c90a-105">“会议”视图会存储有关会议的信息。</span><span class="sxs-lookup"><span data-stu-id="1c90a-105">The Conferences View stores information about the conferences.</span></span> <span data-ttu-id="1c90a-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1c90a-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c90a-107">列</span><span class="sxs-lookup"><span data-stu-id="1c90a-107">Column</span></span></th>
<th><span data-ttu-id="1c90a-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="1c90a-108">Data Type</span></span></th>
<th><span data-ttu-id="1c90a-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="1c90a-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c90a-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="1c90a-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1c90a-111">datetime</span><span class="sxs-lookup"><span data-stu-id="1c90a-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="1c90a-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="1c90a-112">Time of session request.</span></span> <span data-ttu-id="1c90a-113">与 SessionIdSeq 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="1c90a-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="1c90a-114">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="1c90a-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c90a-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1c90a-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1c90a-116">int</span><span class="sxs-lookup"><span data-stu-id="1c90a-116">int</span></span></p></td>
<td><p><span data-ttu-id="1c90a-117">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="1c90a-117">ID number to identify the session.</span></span> <span data-ttu-id="1c90a-118">与 SessionIdTime 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="1c90a-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="1c90a-119">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="1c90a-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c90a-120"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="1c90a-120"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1c90a-121">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="1c90a-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1c90a-122">会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="1c90a-122">URI for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c90a-123"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="1c90a-123"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1c90a-124">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="1c90a-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1c90a-125">会议 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="1c90a-125">Type of the conference URI.</span></span> <span data-ttu-id="1c90a-126">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="1c90a-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c90a-127"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="1c90a-127"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="1c90a-128">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="1c90a-128">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="1c90a-p105">用于定期会议。定期会议的每个实例都具有相同的 ConferenceUri，但 ConfInstance 不同。</span><span class="sxs-lookup"><span data-stu-id="1c90a-p105">Used for recurring conferences. Each instance of a recurring conference has the same ConferenceUri but a different ConfInstance.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c90a-131"><strong>ConferenceStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="1c90a-131"><strong>ConferenceStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1c90a-132">datetime</span><span class="sxs-lookup"><span data-stu-id="1c90a-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="1c90a-133">会议的开始时间。</span><span class="sxs-lookup"><span data-stu-id="1c90a-133">Starting time for the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c90a-134"><strong>ConferenceEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="1c90a-134"><strong>ConferenceEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1c90a-135">datetime</span><span class="sxs-lookup"><span data-stu-id="1c90a-135">datetime</span></span></p></td>
<td><p><span data-ttu-id="1c90a-136">会议的结束时间。</span><span class="sxs-lookup"><span data-stu-id="1c90a-136">Ending time for the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c90a-137"><strong>OrganizerUri</strong></span><span class="sxs-lookup"><span data-stu-id="1c90a-137"><strong>OrganizerUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1c90a-138">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="1c90a-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1c90a-139">组织会议的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="1c90a-139">URI of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c90a-140"><strong>OrganizerType</strong></span><span class="sxs-lookup"><span data-stu-id="1c90a-140"><strong>OrganizerType</strong></span></span></p></td>
<td><p><span data-ttu-id="1c90a-141">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="1c90a-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1c90a-142">组织会议的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="1c90a-142">Type of URI of the user who organized the conference.</span></span> <span data-ttu-id="1c90a-143">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="1c90a-143">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c90a-144"><strong>OrganizerTenant</strong></span><span class="sxs-lookup"><span data-stu-id="1c90a-144"><strong>OrganizerTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="1c90a-145">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="1c90a-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1c90a-146">组织会议的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="1c90a-146">Tenant of the user who organized the conference.</span></span> <span data-ttu-id="1c90a-147">有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</span><span class="sxs-lookup"><span data-stu-id="1c90a-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c90a-148"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="1c90a-148"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="1c90a-149">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="1c90a-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1c90a-150">承载会议的池的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="1c90a-150">Fully qualified domain name of the pool that hosted the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c90a-151"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="1c90a-151"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="1c90a-152">smallint</span><span class="sxs-lookup"><span data-stu-id="1c90a-152">smallint</span></span></p></td>
<td><p><span data-ttu-id="1c90a-p108">包含会议属性的位掩码。可能的值包括：</span><span class="sxs-lookup"><span data-stu-id="1c90a-p108">Bit mask that contains Conference Attributes. Possible values are:</span></span></p>
<p><span data-ttu-id="1c90a-155">0X01 – 综合事务</span><span class="sxs-lookup"><span data-stu-id="1c90a-155">0X01 – Synthetic Transaction</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

