---
title: 'Lync Server 2013: VoIPDetails 视图'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9553be13dcd73f89ba8d6ab051602d378bf353da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="75186-102">Lync Server 2013 中的 VoIPDetails 视图</span><span class="sxs-lookup"><span data-stu-id="75186-102">VoIPDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75186-103">_**主题上次修改时间:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="75186-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="75186-104">VoIPDetails 视图存储有关对等会话的信息, 其中至少有一个用户是 VoIP 用户。</span><span class="sxs-lookup"><span data-stu-id="75186-104">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="75186-105">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="75186-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="75186-106">VoIPDetails 视图包含<A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 的 SessionDetails 视图</A>中的所有列以及下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="75186-106">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75186-107">列</span><span class="sxs-lookup"><span data-stu-id="75186-107">Column</span></span></th>
<th><span data-ttu-id="75186-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="75186-108">Data Type</span></span></th>
<th><span data-ttu-id="75186-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="75186-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75186-110"><strong>FromPhone</strong></span><span class="sxs-lookup"><span data-stu-id="75186-110"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="75186-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="75186-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="75186-112">启动会话的用户的电话 URI。</span><span class="sxs-lookup"><span data-stu-id="75186-112">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75186-113"><strong>ToPhone</strong></span><span class="sxs-lookup"><span data-stu-id="75186-113"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="75186-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="75186-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="75186-115">加入会话的用户的电话 URI。</span><span class="sxs-lookup"><span data-stu-id="75186-115">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75186-116"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="75186-116"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="75186-117">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="75186-117">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="75186-118">断开会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="75186-118">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75186-119"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="75186-119"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="75186-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="75186-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="75186-121">断开会话的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="75186-121">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="75186-122">有关详细信息, 请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="75186-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75186-123"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="75186-123"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="75186-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="75186-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="75186-125">断开会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="75186-125">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75186-126"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="75186-126"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="75186-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="75186-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="75186-128">断开会话的用户的电话 URI。</span><span class="sxs-lookup"><span data-stu-id="75186-128">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75186-129"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="75186-129"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="75186-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="75186-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="75186-131">启动会话的用户所使用的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="75186-131">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75186-132"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="75186-132"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="75186-133">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="75186-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="75186-134">加入会话的用户所使用的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="75186-134">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75186-135"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="75186-135"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="75186-136">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="75186-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="75186-137">启动会话的用户所使用的网关。</span><span class="sxs-lookup"><span data-stu-id="75186-137">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75186-138"><strong>ToGateway</strong></span><span class="sxs-lookup"><span data-stu-id="75186-138"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="75186-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="75186-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="75186-140">加入会话的用户所使用的网关。</span><span class="sxs-lookup"><span data-stu-id="75186-140">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

