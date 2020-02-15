---
title: Lync Server 2013： UserAgent 表
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
ms.openlocfilehash: 0ba13a18436c7a55ca68931ff2794fd584be84f9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a><span data-ttu-id="7a53a-102">Lync Server 2013 中的 UserAgent 表</span><span class="sxs-lookup"><span data-stu-id="7a53a-102">UserAgent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a53a-103">_**上次修改的主题：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="7a53a-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="7a53a-104">UserAgent 表是一个支持表，它存储参与数据库中记录的会话的各种用户代理的列表。</span><span class="sxs-lookup"><span data-stu-id="7a53a-104">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="7a53a-105">表中的每条记录代表一个用户代理</span><span class="sxs-lookup"><span data-stu-id="7a53a-105">Each record in the table represents one user agent</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7a53a-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="7a53a-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7a53a-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="7a53a-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7a53a-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="7a53a-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7a53a-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="7a53a-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a53a-110"><strong>UserAgentKey</strong></span><span class="sxs-lookup"><span data-stu-id="7a53a-110"><strong>UserAgentKey</strong></span></span></p></td>
<td><p><span data-ttu-id="7a53a-111">int</span><span class="sxs-lookup"><span data-stu-id="7a53a-111">int</span></span></p></td>
<td><p><span data-ttu-id="7a53a-112">主</span><span class="sxs-lookup"><span data-stu-id="7a53a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="7a53a-113">标识此用户代理的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="7a53a-113">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a53a-114"><strong>UserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="7a53a-114"><strong>UserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="7a53a-115">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="7a53a-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7a53a-116">独特</span><span class="sxs-lookup"><span data-stu-id="7a53a-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="7a53a-117">用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="7a53a-117">User Agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a53a-118"><strong>UAType</strong></span><span class="sxs-lookup"><span data-stu-id="7a53a-118"><strong>UAType</strong></span></span></p></td>
<td><p><span data-ttu-id="7a53a-119">smallint</span><span class="sxs-lookup"><span data-stu-id="7a53a-119">smallint</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a53a-120">1是中介服务器。</span><span class="sxs-lookup"><span data-stu-id="7a53a-120">1 is Mediation Server.</span></span></p>
<p><span data-ttu-id="7a53a-121">2是 A/V 会议服务器。</span><span class="sxs-lookup"><span data-stu-id="7a53a-121">2 is A/V Conferencing Server.</span></span></p>
<p><span data-ttu-id="7a53a-122">4为 Lync。</span><span class="sxs-lookup"><span data-stu-id="7a53a-122">4 is Lync.</span></span></p>
<p><span data-ttu-id="7a53a-123">8是 IP 电话。</span><span class="sxs-lookup"><span data-stu-id="7a53a-123">8 is IP Phone.</span></span></p>
<p><span data-ttu-id="7a53a-124">16为 Live Meeting 控制台。</span><span class="sxs-lookup"><span data-stu-id="7a53a-124">16 is Live Meeting Console.</span></span></p>
<p><span data-ttu-id="7a53a-125">32是部署验证工具（DVT）。</span><span class="sxs-lookup"><span data-stu-id="7a53a-125">32 is Deployment Validation Tool (DVT).</span></span></p>
<p><span data-ttu-id="7a53a-126">64是 Macintosh 计算机上的 Lync。</span><span class="sxs-lookup"><span data-stu-id="7a53a-126">64 is Lync on Macintosh computers.</span></span></p>
<p><span data-ttu-id="7a53a-127">128是 Office 通信服务器 2007 R2 助理。</span><span class="sxs-lookup"><span data-stu-id="7a53a-127">128 is Office Communications Server 2007 R2 Attendant.</span></span></p>
<p><span data-ttu-id="7a53a-128">256是会议通知服务。</span><span class="sxs-lookup"><span data-stu-id="7a53a-128">256 is Conferencing Announcement service.</span></span></p>
<p><span data-ttu-id="7a53a-129">512是会议自动助理。</span><span class="sxs-lookup"><span data-stu-id="7a53a-129">512 is Conferencing Auto Attendant.</span></span></p>
<p><span data-ttu-id="7a53a-130">1024是响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="7a53a-130">1024 is Response Group application.</span></span></p>
<p><span data-ttu-id="7a53a-131">2048处于语音控制之外。</span><span class="sxs-lookup"><span data-stu-id="7a53a-131">2048 is Outside Voice Control.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

