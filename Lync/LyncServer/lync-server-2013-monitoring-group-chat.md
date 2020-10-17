---
title: Lync Server 2013：监视组聊天
description: Lync Server 2013：监视组聊天。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 625e45f455e8dba50a5fa64240b62cb010623d16
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562028"
---
# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="877bb-103">在 Lync Server 2013 中监视组聊天</span><span class="sxs-lookup"><span data-stu-id="877bb-103">Monitoring group chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="877bb-104">_**上次修改的主题：** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="877bb-104">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="877bb-105">强烈建议运行 Microsoft 下载中心提供的最新 [累积服务器更新安装程序](https://support.microsoft.com/kb/968802) ，以提高性能。</span><span class="sxs-lookup"><span data-stu-id="877bb-105">We highly recommend running the most recent [Cumulative Server Update Installer](https://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="877bb-106">如果你正在运行最新的累积更新，请使用以下压力测试表来了解你的组聊天服务器是否以最佳运行状况运行的指标。</span><span class="sxs-lookup"><span data-stu-id="877bb-106">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="877bb-107">测试环境和用户模型</span><span class="sxs-lookup"><span data-stu-id="877bb-107">Test environment and user model</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="877bb-108">组聊天池中的三组聊天服务器，每个服务器具有 8 GB 内存和8个处理器。</span><span class="sxs-lookup"><span data-stu-id="877bb-108">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="877bb-109">企业版中的两个 Lync Server 2013 前端。</span><span class="sxs-lookup"><span data-stu-id="877bb-109">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="877bb-110">在三个组聊天服务器上为60000个并发用户。</span><span class="sxs-lookup"><span data-stu-id="877bb-110">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="877bb-111">25000通道由组聊天池承载。</span><span class="sxs-lookup"><span data-stu-id="877bb-111">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="877bb-112">频道大小：</span><span class="sxs-lookup"><span data-stu-id="877bb-112">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="877bb-113">小频道大小：30</span><span class="sxs-lookup"><span data-stu-id="877bb-113">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="877bb-114">中等频道大小：150</span><span class="sxs-lookup"><span data-stu-id="877bb-114">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="877bb-115">大型频道大小：2500</span><span class="sxs-lookup"><span data-stu-id="877bb-115">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="877bb-116">频道计数：</span><span class="sxs-lookup"><span data-stu-id="877bb-116">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="877bb-117">数字小通道：24000</span><span class="sxs-lookup"><span data-stu-id="877bb-117">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="877bb-118">数字中等通道800</span><span class="sxs-lookup"><span data-stu-id="877bb-118">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="877bb-119">大型频道数24</span><span class="sxs-lookup"><span data-stu-id="877bb-119">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="877bb-120">通道24824总数</span><span class="sxs-lookup"><span data-stu-id="877bb-120">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="877bb-121">邀请频道：</span><span class="sxs-lookup"><span data-stu-id="877bb-121">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="877bb-122">频道的一半邀请频道</span><span class="sxs-lookup"><span data-stu-id="877bb-122">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="877bb-123">用户加入的通道数：</span><span class="sxs-lookup"><span data-stu-id="877bb-123">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="877bb-124">小：12</span><span class="sxs-lookup"><span data-stu-id="877bb-124">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="877bb-125">中：2</span><span class="sxs-lookup"><span data-stu-id="877bb-125">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="877bb-126">大型：1</span><span class="sxs-lookup"><span data-stu-id="877bb-126">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="877bb-127">联接率：</span><span class="sxs-lookup"><span data-stu-id="877bb-127">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="877bb-128">每台服务器总共10次，每个服务器 3.33/秒</span><span class="sxs-lookup"><span data-stu-id="877bb-128">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="877bb-129">注销率：</span><span class="sxs-lookup"><span data-stu-id="877bb-129">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="877bb-130">每台服务器总共10次，每个服务器 3.33/秒</span><span class="sxs-lookup"><span data-stu-id="877bb-130">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="877bb-131">聊天速度：</span><span class="sxs-lookup"><span data-stu-id="877bb-131">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="877bb-132">每个服务器总共20个，每秒 6.66/秒</span><span class="sxs-lookup"><span data-stu-id="877bb-132">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="877bb-133">使用不同的硬件规范或用户配置文件时，以下性能计数器数可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="877bb-133">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="877bb-134">要监视的性能计数器</span><span class="sxs-lookup"><span data-stu-id="877bb-134">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="877bb-135">性能计数器</span><span class="sxs-lookup"><span data-stu-id="877bb-135">Performance Counter</span></span></th>
<th><span data-ttu-id="877bb-136">阙</span><span class="sxs-lookup"><span data-stu-id="877bb-136">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="877bb-137">处理 (ChannelService) - &gt; 处理器时间</span><span class="sxs-lookup"><span data-stu-id="877bb-137">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="877bb-138">最小值：0</span><span class="sxs-lookup"><span data-stu-id="877bb-138">Min: 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

