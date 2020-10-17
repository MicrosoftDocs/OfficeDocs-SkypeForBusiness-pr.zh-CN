---
title: Lync Server 2013： VoIPDetails 视图
description: Lync Server 2013： VoIPDetails 视图。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ecd34be0c8568eef29d773f088e8503a8065743
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566198"
---
# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="66a24-103">Lync Server 2013 中的 VoIPDetails 视图</span><span class="sxs-lookup"><span data-stu-id="66a24-103">VoIPDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66a24-104">_**上次修改的主题：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="66a24-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="66a24-105">VoIPDetails 视图存储有关对等会话（其中至少有一个用户是 VoIP 用户）的信息。</span><span class="sxs-lookup"><span data-stu-id="66a24-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="66a24-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="66a24-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="66a24-107">VoIPDetails 视图包含在 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 的 SessionDetails 视图</A> 中的所有列，此外还列出了下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="66a24-107">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66a24-108">列</span><span class="sxs-lookup"><span data-stu-id="66a24-108">Column</span></span></th>
<th><span data-ttu-id="66a24-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="66a24-109">Data Type</span></span></th>
<th><span data-ttu-id="66a24-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="66a24-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66a24-111"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="66a24-111"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="66a24-112">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="66a24-112">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="66a24-113">启动会话的用户的电话 ID。</span><span class="sxs-lookup"><span data-stu-id="66a24-113">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66a24-114"><strong>ToPhone</strong></span><span class="sxs-lookup"><span data-stu-id="66a24-114"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="66a24-115">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="66a24-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="66a24-116">加入会话的用户的电话 URI。</span><span class="sxs-lookup"><span data-stu-id="66a24-116">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66a24-117"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="66a24-117"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="66a24-118">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="66a24-118">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="66a24-119">断开会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="66a24-119">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66a24-120"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="66a24-120"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="66a24-121">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="66a24-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="66a24-122">断开会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="66a24-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="66a24-123">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="66a24-123">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66a24-124"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="66a24-124"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="66a24-125">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="66a24-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="66a24-126">断开会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="66a24-126">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66a24-127"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="66a24-127"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="66a24-128">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="66a24-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="66a24-129">断开会话的用户的电话 URI。</span><span class="sxs-lookup"><span data-stu-id="66a24-129">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66a24-130"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="66a24-130"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="66a24-131">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="66a24-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="66a24-132">启动会话的用户使用的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="66a24-132">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66a24-133"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="66a24-133"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="66a24-134">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="66a24-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="66a24-135">加入会话的用户使用的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="66a24-135">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66a24-136"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="66a24-136"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="66a24-137">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="66a24-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="66a24-138">启动会话的用户使用的网关。</span><span class="sxs-lookup"><span data-stu-id="66a24-138">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66a24-139"><strong>ToGateway</strong></span><span class="sxs-lookup"><span data-stu-id="66a24-139"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="66a24-140">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="66a24-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="66a24-141">加入会话的用户使用的网关。</span><span class="sxs-lookup"><span data-stu-id="66a24-141">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

