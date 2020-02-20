---
title: Lync Server 2013：监视组聊天
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
ms.openlocfilehash: a42589db677132170e9456c998d96fd2eb1de5d2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a><span data-ttu-id="bb033-102">在 Lync Server 2013 中监视组聊天</span><span class="sxs-lookup"><span data-stu-id="bb033-102">Monitoring group chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb033-103">_**上次修改的主题：** 2014-08-04_</span><span class="sxs-lookup"><span data-stu-id="bb033-103">_**Topic Last Modified:** 2014-08-04_</span></span>

<span data-ttu-id="bb033-104">强烈建议运行 Microsoft 下载中心提供的最新[累积服务器更新安装程序](https://support.microsoft.com/kb/968802)，以提高性能。</span><span class="sxs-lookup"><span data-stu-id="bb033-104">We highly recommend running the most recent [Cumulative Server Update Installer](https://support.microsoft.com/kb/968802) available on the Microsoft Download Center for performance improvements.</span></span>

<span data-ttu-id="bb033-105">如果你正在运行最新的累积更新，请使用以下压力测试表来了解你的组聊天服务器是否以最佳运行状况运行的指标。</span><span class="sxs-lookup"><span data-stu-id="bb033-105">Assuming you are running latest cumulative update, use the following stress test table for metrics to understand if your Group Chat Servers are running at optimal health.</span></span>

### <a name="test-environment-and-user-model"></a><span data-ttu-id="bb033-106">测试环境和用户模型</span><span class="sxs-lookup"><span data-stu-id="bb033-106">Test environment and user model</span></span>

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
<td><p><span data-ttu-id="bb033-107">组聊天池中的三组聊天服务器，每个服务器具有 8 GB 内存和8个处理器。</span><span class="sxs-lookup"><span data-stu-id="bb033-107">Three Group Chat Servers in a Group Chat pool, each with 8 GB memory and 8 processors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb033-108">企业版中的两个 Lync Server 2013 前端。</span><span class="sxs-lookup"><span data-stu-id="bb033-108">Two Lync Server 2013 Front Ends in Enterprise Edition.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb033-109">在三个组聊天服务器上为60000个并发用户。</span><span class="sxs-lookup"><span data-stu-id="bb033-109">60,000 concurrent users across three Group Chat Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb033-110">25000通道由组聊天池承载。</span><span class="sxs-lookup"><span data-stu-id="bb033-110">25,000 channels hosted by Group Chat Pool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb033-111">频道大小：</span><span class="sxs-lookup"><span data-stu-id="bb033-111">Channel Size:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb033-112">小频道大小：30</span><span class="sxs-lookup"><span data-stu-id="bb033-112">Small Channel Size: 30</span></span></p></li>
<li><p><span data-ttu-id="bb033-113">中等频道大小：150</span><span class="sxs-lookup"><span data-stu-id="bb033-113">Medium Channel Size: 150</span></span></p></li>
<li><p><span data-ttu-id="bb033-114">大型频道大小：2500</span><span class="sxs-lookup"><span data-stu-id="bb033-114">Large Channel Size: 2500</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb033-115">频道计数：</span><span class="sxs-lookup"><span data-stu-id="bb033-115">Channel Count:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb033-116">数字小通道：24000</span><span class="sxs-lookup"><span data-stu-id="bb033-116">Number small channels: 24,000</span></span></p></li>
<li><p><span data-ttu-id="bb033-117">数字中等通道800</span><span class="sxs-lookup"><span data-stu-id="bb033-117">Number medium channels 800</span></span></p></li>
<li><p><span data-ttu-id="bb033-118">大型频道数24</span><span class="sxs-lookup"><span data-stu-id="bb033-118">Number large channels 24</span></span></p></li>
<li><p><span data-ttu-id="bb033-119">通道24824总数</span><span class="sxs-lookup"><span data-stu-id="bb033-119">Total Channels 24,824</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb033-120">邀请频道：</span><span class="sxs-lookup"><span data-stu-id="bb033-120">Invite channels:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb033-121">频道的一半邀请频道</span><span class="sxs-lookup"><span data-stu-id="bb033-121">Half the channels were invite channels</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb033-122">用户加入的通道数：</span><span class="sxs-lookup"><span data-stu-id="bb033-122">Number of channels a user joins:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb033-123">小：12</span><span class="sxs-lookup"><span data-stu-id="bb033-123">Small: 12</span></span></p></li>
<li><p><span data-ttu-id="bb033-124">中：2</span><span class="sxs-lookup"><span data-stu-id="bb033-124">Medium: 2</span></span></p></li>
<li><p><span data-ttu-id="bb033-125">大型：1</span><span class="sxs-lookup"><span data-stu-id="bb033-125">Large: 1</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb033-126">联接率：</span><span class="sxs-lookup"><span data-stu-id="bb033-126">Join rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb033-127">每台服务器总共10次，每个服务器 3.33/秒</span><span class="sxs-lookup"><span data-stu-id="bb033-127">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb033-128">注销率：</span><span class="sxs-lookup"><span data-stu-id="bb033-128">Logout rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb033-129">每台服务器总共10次，每个服务器 3.33/秒</span><span class="sxs-lookup"><span data-stu-id="bb033-129">10 total/second, 3.33/second per server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb033-130">聊天速度：</span><span class="sxs-lookup"><span data-stu-id="bb033-130">Chat rate:</span></span></p>
<ul>
<li><p><span data-ttu-id="bb033-131">每个服务器总共20个，每秒 6.66/秒</span><span class="sxs-lookup"><span data-stu-id="bb033-131">20 total/second, 6.66/second per server</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="bb033-132">使用不同的硬件规范或用户配置文件时，以下性能计数器数可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="bb033-132">The following performance counter numbers will likely vary when different hardware specifications or user profiles are used.</span></span>



</div>

### <a name="performance-counter-to-be-monitored"></a><span data-ttu-id="bb033-133">要监视的性能计数器</span><span class="sxs-lookup"><span data-stu-id="bb033-133">Performance counter to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bb033-134">性能计数器</span><span class="sxs-lookup"><span data-stu-id="bb033-134">Performance Counter</span></span></th>
<th><span data-ttu-id="bb033-135">阙</span><span class="sxs-lookup"><span data-stu-id="bb033-135">Thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb033-136">Process （ChannelService）-&gt;处理器时间百分比</span><span class="sxs-lookup"><span data-stu-id="bb033-136">Process(ChannelService)-&gt;%Processor Time</span></span></p></td>
<td><p><span data-ttu-id="bb033-137">最小值：0</span><span class="sxs-lookup"><span data-stu-id="bb033-137">Min: 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

