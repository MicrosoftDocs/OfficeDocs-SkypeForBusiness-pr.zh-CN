---
title: Lync Server 2013： ConferenceMessageCount 视图
description: Lync Server 2013： ConferenceMessageCount 视图。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount view
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49733727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 212d6e1a346253809fb70806424350cc7fc0dfe2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561608"
---
# <a name="conferencemessagecount-view-in-lync-server-2013"></a><span data-ttu-id="66f3a-103">Lync Server 2013 中的 ConferenceMessageCount 视图</span><span class="sxs-lookup"><span data-stu-id="66f3a-103">ConferenceMessageCount view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66f3a-104">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="66f3a-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="66f3a-105">ConferenceMessageCount 视图存储有关用户已向会议中发送的消息数的信息。</span><span class="sxs-lookup"><span data-stu-id="66f3a-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="66f3a-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="66f3a-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="66f3a-107">ConferenceMessageCount 视图包含在 <A href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013 的 ConferenceSessionDetails 视图</A> 中的所有列，此外还列出了下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="66f3a-107">The ConferenceMessageCount view contains all of the columns in the <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66f3a-108">列</span><span class="sxs-lookup"><span data-stu-id="66f3a-108">Column</span></span></th>
<th><span data-ttu-id="66f3a-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="66f3a-109">Data Type</span></span></th>
<th><span data-ttu-id="66f3a-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="66f3a-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66f3a-111"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="66f3a-111"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="66f3a-112">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="66f3a-112">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="66f3a-113">发送消息的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="66f3a-113">URI of the user who sent the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66f3a-114"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="66f3a-114"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="66f3a-115">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="66f3a-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="66f3a-116">发送消息的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="66f3a-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="66f3a-117">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="66f3a-117">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66f3a-118"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="66f3a-118"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="66f3a-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="66f3a-119">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="66f3a-120">发送消息的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="66f3a-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="66f3a-121">有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</span><span class="sxs-lookup"><span data-stu-id="66f3a-121">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66f3a-122"><strong>UserMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="66f3a-122"><strong>UserMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="66f3a-123">smallint</span><span class="sxs-lookup"><span data-stu-id="66f3a-123">smallint</span></span></p></td>
<td><p><span data-ttu-id="66f3a-124">用户在会议会话期间发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="66f3a-124">Number of messages sent by the user during the conference session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

