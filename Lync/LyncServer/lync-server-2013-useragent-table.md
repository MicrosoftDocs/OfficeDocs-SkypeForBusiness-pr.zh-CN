---
title: Lync Server 2013：UserAgent 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09bb2e3a71f81014bcb08952c03b59c93ac6a62f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845478"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a><span data-ttu-id="395e0-102">Lync Server 2013 中的 UserAgent 表</span><span class="sxs-lookup"><span data-stu-id="395e0-102">UserAgent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="395e0-103">_**主题上次修改时间:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="395e0-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="395e0-104">UserAgent 表是一个支持表, 用于存储参与数据库中记录的会话的各种用户代理的列表。</span><span class="sxs-lookup"><span data-stu-id="395e0-104">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="395e0-105">表中的每条记录表示一个用户代理</span><span class="sxs-lookup"><span data-stu-id="395e0-105">Each record in the table represents one user agent</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="395e0-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="395e0-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="395e0-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="395e0-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="395e0-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="395e0-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="395e0-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="395e0-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="395e0-110"><strong>UserAgentKey</strong></span><span class="sxs-lookup"><span data-stu-id="395e0-110"><strong>UserAgentKey</strong></span></span></p></td>
<td><p><span data-ttu-id="395e0-111">int</span><span class="sxs-lookup"><span data-stu-id="395e0-111">int</span></span></p></td>
<td><p><span data-ttu-id="395e0-112">Primary</span><span class="sxs-lookup"><span data-stu-id="395e0-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="395e0-113">标识此用户代理的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="395e0-113">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="395e0-114"><strong>UserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="395e0-114"><strong>UserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="395e0-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="395e0-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="395e0-116">唯一</span><span class="sxs-lookup"><span data-stu-id="395e0-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="395e0-117">用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="395e0-117">User Agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="395e0-118"><strong>UAType</strong></span><span class="sxs-lookup"><span data-stu-id="395e0-118"><strong>UAType</strong></span></span></p></td>
<td><p><span data-ttu-id="395e0-119">smallint</span><span class="sxs-lookup"><span data-stu-id="395e0-119">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="395e0-120">1是中介服务器。</span><span class="sxs-lookup"><span data-stu-id="395e0-120">1 is Mediation Server.</span></span></p>
<p><span data-ttu-id="395e0-121">2是 A/V 会议服务器。</span><span class="sxs-lookup"><span data-stu-id="395e0-121">2 is A/V Conferencing Server.</span></span></p>
<p><span data-ttu-id="395e0-122">4是 Lync。</span><span class="sxs-lookup"><span data-stu-id="395e0-122">4 is Lync.</span></span></p>
<p><span data-ttu-id="395e0-123">8是 IP 电话。</span><span class="sxs-lookup"><span data-stu-id="395e0-123">8 is IP Phone.</span></span></p>
<p><span data-ttu-id="395e0-124">16是 Live Meeting 控制台。</span><span class="sxs-lookup"><span data-stu-id="395e0-124">16 is Live Meeting Console.</span></span></p>
<p><span data-ttu-id="395e0-125">32是部署验证工具 (DVT)。</span><span class="sxs-lookup"><span data-stu-id="395e0-125">32 is Deployment Validation Tool (DVT).</span></span></p>
<p><span data-ttu-id="395e0-126">64是 Macintosh 计算机上的 Lync。</span><span class="sxs-lookup"><span data-stu-id="395e0-126">64 is Lync on Macintosh computers.</span></span></p>
<p><span data-ttu-id="395e0-127">128是 Office 通信服务器 2007 R2 助理。</span><span class="sxs-lookup"><span data-stu-id="395e0-127">128 is Office Communications Server 2007 R2 Attendant.</span></span></p>
<p><span data-ttu-id="395e0-128">256是会议公告服务。</span><span class="sxs-lookup"><span data-stu-id="395e0-128">256 is Conferencing Announcement service.</span></span></p>
<p><span data-ttu-id="395e0-129">512是会议自动助理。</span><span class="sxs-lookup"><span data-stu-id="395e0-129">512 is Conferencing Auto Attendant.</span></span></p>
<p><span data-ttu-id="395e0-130">1024是响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="395e0-130">1024 is Response Group application.</span></span></p>
<p><span data-ttu-id="395e0-131">2048不在语音控制范围内。</span><span class="sxs-lookup"><span data-stu-id="395e0-131">2048 is Outside Voice Control.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

