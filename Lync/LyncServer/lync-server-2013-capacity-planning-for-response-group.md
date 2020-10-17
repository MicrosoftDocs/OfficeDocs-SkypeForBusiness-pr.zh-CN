---
title: Lync Server 2013：响应组的容量规划
description: Lync Server 2013：响应组的容量规划。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78c543f558f67deaaeb781b308aa5f68d39cd785
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544428"
---
# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="1e9d7-103">Lync Server 2013 中的响应组的容量规划</span><span class="sxs-lookup"><span data-stu-id="1e9d7-103">Capacity planning for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e9d7-104">_**上次修改的主题：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="1e9d7-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="1e9d7-105">下表介绍了可以用作容量规划要求基础的响应组用户模型。</span><span class="sxs-lookup"><span data-stu-id="1e9d7-105">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1e9d7-p101">下表中的数值假定所有响应组音频文件使用的是 16 kHz、单声道、16 位的 Wave (.wav) 文件。如果使用其他文件格式（如 Windows Media 音频 (.wma)），则数值可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="1e9d7-p101">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files. If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1e9d7-108">请记住，对于灾难恢复容量规划，一对池中的每一个池都应能处理这两个池中的所有响应组的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="1e9d7-108">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="1e9d7-109">响应组用户模型</span><span class="sxs-lookup"><span data-stu-id="1e9d7-109">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1e9d7-110">跃点数</span><span class="sxs-lookup"><span data-stu-id="1e9d7-110">Metric</span></span></th>
<th><span data-ttu-id="1e9d7-111">每个 Enterprise Edition 池 (与8台前端服务器) </span><span class="sxs-lookup"><span data-stu-id="1e9d7-111">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="1e9d7-112">每台 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="1e9d7-112">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e9d7-113">每秒传入的呼叫数</span><span class="sxs-lookup"><span data-stu-id="1e9d7-113">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="1e9d7-114">16 </span><span class="sxs-lookup"><span data-stu-id="1e9d7-114">16</span></span></p></td>
<td><p><span data-ttu-id="1e9d7-115">双面</span><span class="sxs-lookup"><span data-stu-id="1e9d7-115">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e9d7-116">连接到 IVR 或 MoH 的并发呼叫数</span><span class="sxs-lookup"><span data-stu-id="1e9d7-116">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="1e9d7-117">480</span><span class="sxs-lookup"><span data-stu-id="1e9d7-117">480</span></span></p></td>
<td><p><span data-ttu-id="1e9d7-118">60</span><span class="sxs-lookup"><span data-stu-id="1e9d7-118">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e9d7-119">并发的匿名会话数（无 IM）</span><span class="sxs-lookup"><span data-stu-id="1e9d7-119">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="1e9d7-120">224</span><span class="sxs-lookup"><span data-stu-id="1e9d7-120">224</span></span></p></td>
<td><p><span data-ttu-id="1e9d7-121">28</span><span class="sxs-lookup"><span data-stu-id="1e9d7-121">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e9d7-122">并发的匿名会话数（具有 IM）</span><span class="sxs-lookup"><span data-stu-id="1e9d7-122">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="1e9d7-123">64</span><span class="sxs-lookup"><span data-stu-id="1e9d7-123">64</span></span></p></td>
<td><p><span data-ttu-id="1e9d7-124">8 </span><span class="sxs-lookup"><span data-stu-id="1e9d7-124">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e9d7-125">活动代理数（正式和非正式）</span><span class="sxs-lookup"><span data-stu-id="1e9d7-125">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="1e9d7-126">1200</span><span class="sxs-lookup"><span data-stu-id="1e9d7-126">1200</span></span></p></td>
<td><p><span data-ttu-id="1e9d7-127">1200</span><span class="sxs-lookup"><span data-stu-id="1e9d7-127">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e9d7-128">智能寻线数</span><span class="sxs-lookup"><span data-stu-id="1e9d7-128">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="1e9d7-129">400</span><span class="sxs-lookup"><span data-stu-id="1e9d7-129">400</span></span></p></td>
<td><p><span data-ttu-id="1e9d7-130">400</span><span class="sxs-lookup"><span data-stu-id="1e9d7-130">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e9d7-131">IVR 组数（使用语音识别）</span><span class="sxs-lookup"><span data-stu-id="1e9d7-131">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="1e9d7-132">200</span><span class="sxs-lookup"><span data-stu-id="1e9d7-132">200</span></span></p></td>
<td><p><span data-ttu-id="1e9d7-133">200</span><span class="sxs-lookup"><span data-stu-id="1e9d7-133">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

