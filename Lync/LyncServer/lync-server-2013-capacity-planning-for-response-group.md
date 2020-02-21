---
title: Lync Server 2013：响应组的容量规划
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
ms.openlocfilehash: 9c9d43f6424a8d960ad5d0eee911b2f48455a39d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="e2bea-102">Lync Server 2013 中的响应组的容量规划</span><span class="sxs-lookup"><span data-stu-id="e2bea-102">Capacity planning for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2bea-103">_**上次修改的主题：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="e2bea-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="e2bea-104">下表介绍了可以用作容量规划要求基础的响应组用户模型。</span><span class="sxs-lookup"><span data-stu-id="e2bea-104">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e2bea-p101">下表中的数值假定所有响应组音频文件使用的是 16 kHz、单声道、16 位的 Wave (.wav) 文件。如果使用其他文件格式（如 Windows Media 音频 (.wma)），则数值可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="e2bea-p101">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files. If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e2bea-107">请记住，对于灾难恢复容量规划，一对池中的每一个池都应能处理这两个池中的所有响应组的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="e2bea-107">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="e2bea-108">响应组用户模型</span><span class="sxs-lookup"><span data-stu-id="e2bea-108">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e2bea-109">多重</span><span class="sxs-lookup"><span data-stu-id="e2bea-109">Metric</span></span></th>
<th><span data-ttu-id="e2bea-110">每个企业版池（包含8台前端服务器）</span><span class="sxs-lookup"><span data-stu-id="e2bea-110">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="e2bea-111">每台 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="e2bea-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e2bea-112">每秒传入的呼叫数</span><span class="sxs-lookup"><span data-stu-id="e2bea-112">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="e2bea-113">16 </span><span class="sxs-lookup"><span data-stu-id="e2bea-113">16</span></span></p></td>
<td><p><span data-ttu-id="e2bea-114">双面</span><span class="sxs-lookup"><span data-stu-id="e2bea-114">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2bea-115">连接到 IVR 或 MoH 的并发呼叫数</span><span class="sxs-lookup"><span data-stu-id="e2bea-115">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="e2bea-116">480</span><span class="sxs-lookup"><span data-stu-id="e2bea-116">480</span></span></p></td>
<td><p><span data-ttu-id="e2bea-117">60</span><span class="sxs-lookup"><span data-stu-id="e2bea-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2bea-118">并发的匿名会话数（无 IM）</span><span class="sxs-lookup"><span data-stu-id="e2bea-118">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="e2bea-119">224</span><span class="sxs-lookup"><span data-stu-id="e2bea-119">224</span></span></p></td>
<td><p><span data-ttu-id="e2bea-120">28</span><span class="sxs-lookup"><span data-stu-id="e2bea-120">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2bea-121">并发的匿名会话数（具有 IM）</span><span class="sxs-lookup"><span data-stu-id="e2bea-121">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="e2bea-122">64</span><span class="sxs-lookup"><span data-stu-id="e2bea-122">64</span></span></p></td>
<td><p><span data-ttu-id="e2bea-123">8 </span><span class="sxs-lookup"><span data-stu-id="e2bea-123">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2bea-124">活动代理数（正式和非正式）</span><span class="sxs-lookup"><span data-stu-id="e2bea-124">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="e2bea-125">1200</span><span class="sxs-lookup"><span data-stu-id="e2bea-125">1200</span></span></p></td>
<td><p><span data-ttu-id="e2bea-126">1200</span><span class="sxs-lookup"><span data-stu-id="e2bea-126">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e2bea-127">智能寻线数</span><span class="sxs-lookup"><span data-stu-id="e2bea-127">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="e2bea-128">400</span><span class="sxs-lookup"><span data-stu-id="e2bea-128">400</span></span></p></td>
<td><p><span data-ttu-id="e2bea-129">400</span><span class="sxs-lookup"><span data-stu-id="e2bea-129">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e2bea-130">IVR 组数（使用语音识别）</span><span class="sxs-lookup"><span data-stu-id="e2bea-130">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="e2bea-131">200</span><span class="sxs-lookup"><span data-stu-id="e2bea-131">200</span></span></p></td>
<td><p><span data-ttu-id="e2bea-132">200</span><span class="sxs-lookup"><span data-stu-id="e2bea-132">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

