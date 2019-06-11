---
title: 'Lync Server 2013: 监视群组聊天'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74897191cac7559237e961b7600a3ed478d11e58
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="e48e6-102">在 Lync Server 2013 中监视群组聊天</span><span class="sxs-lookup"><span data-stu-id="e48e6-102">Monitoring group chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e48e6-103">_**主题上次修改时间:** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="e48e6-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="e48e6-104">强烈建议运行 Microsoft 下载中心提供的最新[累积服务器更新安装程序](http://support.microsoft.com/kb/968802), 以提高性能。</span><span class="sxs-lookup"><span data-stu-id="e48e6-104">We highly recommend running the most recent [Cumulative Server Update Installer](http://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="e48e6-105">假设你正在运行最新的累积更新, 请使用以下压力测试表来了解你的群组聊天服务器是否在最佳运行状况下运行。</span><span class="sxs-lookup"><span data-stu-id="e48e6-105">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="e48e6-106">测试环境和用户模型</span><span class="sxs-lookup"><span data-stu-id="e48e6-106">Test environment and user model</span></span>

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
<td><p><span data-ttu-id="e48e6-107">群组聊天池中的三个群组聊天服务器, 每个服务器都有 8 GB 内存和8个处理器。</span><span class="sxs-lookup"><span data-stu-id="e48e6-107">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48e6-108">企业版中的两个 Lync Server 2013 前端。</span><span class="sxs-lookup"><span data-stu-id="e48e6-108">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48e6-109">60000多个群组聊天服务器上的并行用户。</span><span class="sxs-lookup"><span data-stu-id="e48e6-109">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48e6-110">25000通道由群组聊天池托管。</span><span class="sxs-lookup"><span data-stu-id="e48e6-110">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48e6-111">频道大小:</span><span class="sxs-lookup"><span data-stu-id="e48e6-111">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="e48e6-112">小频道大小:30</span><span class="sxs-lookup"><span data-stu-id="e48e6-112">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="e48e6-113">中等频道大小: 150</span><span class="sxs-lookup"><span data-stu-id="e48e6-113">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="e48e6-114">大频道大小: 2500</span><span class="sxs-lookup"><span data-stu-id="e48e6-114">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48e6-115">频道计数:</span><span class="sxs-lookup"><span data-stu-id="e48e6-115">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="e48e6-116">数字小型频道: 24000</span><span class="sxs-lookup"><span data-stu-id="e48e6-116">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="e48e6-117">数字中等通道800</span><span class="sxs-lookup"><span data-stu-id="e48e6-117">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="e48e6-118">大量频道24</span><span class="sxs-lookup"><span data-stu-id="e48e6-118">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="e48e6-119">通道24824总数</span><span class="sxs-lookup"><span data-stu-id="e48e6-119">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48e6-120">邀请频道:</span><span class="sxs-lookup"><span data-stu-id="e48e6-120">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="e48e6-121">频道的一半邀请频道</span><span class="sxs-lookup"><span data-stu-id="e48e6-121">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48e6-122">用户加入的频道数:</span><span class="sxs-lookup"><span data-stu-id="e48e6-122">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="e48e6-123">小:12</span><span class="sxs-lookup"><span data-stu-id="e48e6-123">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="e48e6-124">中等: 2</span><span class="sxs-lookup"><span data-stu-id="e48e6-124">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="e48e6-125">大: 1</span><span class="sxs-lookup"><span data-stu-id="e48e6-125">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48e6-126">联接费率:</span><span class="sxs-lookup"><span data-stu-id="e48e6-126">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="e48e6-127">每台服务器10个总/秒、3.33/秒</span><span class="sxs-lookup"><span data-stu-id="e48e6-127">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e48e6-128">注销费率:</span><span class="sxs-lookup"><span data-stu-id="e48e6-128">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="e48e6-129">每台服务器10个总/秒、3.33/秒</span><span class="sxs-lookup"><span data-stu-id="e48e6-129">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e48e6-130">聊天费率:</span><span class="sxs-lookup"><span data-stu-id="e48e6-130">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="e48e6-131">每个服务器20总/秒、每个服务器 6.66/秒</span><span class="sxs-lookup"><span data-stu-id="e48e6-131">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="e48e6-132">当使用不同的硬件规范或用户配置文件时, 以下性能计数器数值可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="e48e6-132">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="e48e6-133">要监视的性能计数器</span><span class="sxs-lookup"><span data-stu-id="e48e6-133">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e48e6-134">性能计数器</span><span class="sxs-lookup"><span data-stu-id="e48e6-134">Performance Counter</span></span></th>
<th><span data-ttu-id="e48e6-135">01b</span><span class="sxs-lookup"><span data-stu-id="e48e6-135">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e48e6-136">Process (ChannelService)-&gt;处理器时间百分比</span><span class="sxs-lookup"><span data-stu-id="e48e6-136">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="e48e6-137">分钟: 0</span><span class="sxs-lookup"><span data-stu-id="e48e6-137">Min: 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

