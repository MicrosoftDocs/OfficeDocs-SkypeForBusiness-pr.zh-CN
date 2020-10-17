---
title: Lync Server 2013： UserAgent 表
description: Lync Server 2013： UserAgent 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b701d8384313d0267dd566e0c32242f6cc077472
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558888"
---
# <a name="useragent-table-in-lync-server-2013"></a><span data-ttu-id="e5942-103">Lync Server 2013 中的 UserAgent 表</span><span class="sxs-lookup"><span data-stu-id="e5942-103">UserAgent table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5942-104">_**上次修改的主题：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="e5942-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="e5942-105">UserAgent 表是一个支持表，它存储参与数据库中记录的会话的各种用户代理的列表。</span><span class="sxs-lookup"><span data-stu-id="e5942-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="e5942-106">表中的每条记录代表一个用户代理</span><span class="sxs-lookup"><span data-stu-id="e5942-106">Each record in the table represents one user agent</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5942-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="e5942-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e5942-108"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="e5942-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e5942-109"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="e5942-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e5942-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="e5942-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5942-111"><strong>UserAgentKey</strong></span><span class="sxs-lookup"><span data-stu-id="e5942-111"><strong>UserAgentKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e5942-112">int</span><span class="sxs-lookup"><span data-stu-id="e5942-112">int</span></span></p></td>
<td><p><span data-ttu-id="e5942-113">主</span><span class="sxs-lookup"><span data-stu-id="e5942-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="e5942-114">标识此用户代理的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="e5942-114">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5942-115"><strong>UserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="e5942-115"><strong>UserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="e5942-116">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5942-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5942-117">独特</span><span class="sxs-lookup"><span data-stu-id="e5942-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="e5942-118">用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="e5942-118">User Agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5942-119"><strong>UAType</strong></span><span class="sxs-lookup"><span data-stu-id="e5942-119"><strong>UAType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5942-120">smallint</span><span class="sxs-lookup"><span data-stu-id="e5942-120">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e5942-121">1是中介服务器。</span><span class="sxs-lookup"><span data-stu-id="e5942-121">1 is Mediation Server.</span></span></p>
<p><span data-ttu-id="e5942-122">2是 A/V 会议服务器。</span><span class="sxs-lookup"><span data-stu-id="e5942-122">2 is A/V Conferencing Server.</span></span></p>
<p><span data-ttu-id="e5942-123">4为 Lync。</span><span class="sxs-lookup"><span data-stu-id="e5942-123">4 is Lync.</span></span></p>
<p><span data-ttu-id="e5942-124">8是 IP 电话。</span><span class="sxs-lookup"><span data-stu-id="e5942-124">8 is IP Phone.</span></span></p>
<p><span data-ttu-id="e5942-125">16为 Live Meeting 控制台。</span><span class="sxs-lookup"><span data-stu-id="e5942-125">16 is Live Meeting Console.</span></span></p>
<p><span data-ttu-id="e5942-126">32是部署验证工具 (DVT) 。</span><span class="sxs-lookup"><span data-stu-id="e5942-126">32 is Deployment Validation Tool (DVT).</span></span></p>
<p><span data-ttu-id="e5942-127">64是 Macintosh 计算机上的 Lync。</span><span class="sxs-lookup"><span data-stu-id="e5942-127">64 is Lync on Macintosh computers.</span></span></p>
<p><span data-ttu-id="e5942-128">128是 Office 通信服务器 2007 R2 助理。</span><span class="sxs-lookup"><span data-stu-id="e5942-128">128 is Office Communications Server 2007 R2 Attendant.</span></span></p>
<p><span data-ttu-id="e5942-129">256是会议通知服务。</span><span class="sxs-lookup"><span data-stu-id="e5942-129">256 is Conferencing Announcement service.</span></span></p>
<p><span data-ttu-id="e5942-130">512是会议自动助理。</span><span class="sxs-lookup"><span data-stu-id="e5942-130">512 is Conferencing Auto Attendant.</span></span></p>
<p><span data-ttu-id="e5942-131">1024是响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="e5942-131">1024 is Response Group application.</span></span></p>
<p><span data-ttu-id="e5942-132">2048处于语音控制之外。</span><span class="sxs-lookup"><span data-stu-id="e5942-132">2048 is Outside Voice Control.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

