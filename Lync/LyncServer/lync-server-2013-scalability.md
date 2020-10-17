---
title: Lync Server 2013 可伸缩性
description: Lync Server 2013 的可伸缩性。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability
ms:assetid: 46fa0cb5-1507-4a12-ad3f-ba64585e2dc4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417160(v=OCS.15)
ms:contentKeyID: 48183995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28cd5820755ffd1eb863ed6f2369b5756a7ae3f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543788"
---
# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="66911-103">Lync Server 2013 的可伸缩性</span><span class="sxs-lookup"><span data-stu-id="66911-103">Scalability with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66911-104">_**上次修改的主题：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="66911-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="66911-105">在两个版本的 Enterprise Edition 和 Standard Edition 中提供了 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="66911-105">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="66911-106">不同的版本主要面向不同规模的组织。</span><span class="sxs-lookup"><span data-stu-id="66911-106">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="66911-107">如下表所示，两个版本均支持所有工作负荷的所有功能，高可用性和灾难恢复除外。</span><span class="sxs-lookup"><span data-stu-id="66911-107">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66911-108">功能</span><span class="sxs-lookup"><span data-stu-id="66911-108">Feature</span></span></th>
<th><span data-ttu-id="66911-109">Enterprise Edition 是否支持？</span><span class="sxs-lookup"><span data-stu-id="66911-109">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="66911-110">Standard Edition 是否支持？</span><span class="sxs-lookup"><span data-stu-id="66911-110">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66911-111">即时消息 (IM) 和状态</span><span class="sxs-lookup"><span data-stu-id="66911-111">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="66911-112">是</span><span class="sxs-lookup"><span data-stu-id="66911-112">Yes</span></span></p></td>
<td><p><span data-ttu-id="66911-113">是</span><span class="sxs-lookup"><span data-stu-id="66911-113">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66911-114">会议</span><span class="sxs-lookup"><span data-stu-id="66911-114">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="66911-115">是</span><span class="sxs-lookup"><span data-stu-id="66911-115">Yes</span></span></p></td>
<td><p><span data-ttu-id="66911-116">是</span><span class="sxs-lookup"><span data-stu-id="66911-116">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66911-117">A/V 会议</span><span class="sxs-lookup"><span data-stu-id="66911-117">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="66911-118">是</span><span class="sxs-lookup"><span data-stu-id="66911-118">Yes</span></span></p></td>
<td><p><span data-ttu-id="66911-119">是</span><span class="sxs-lookup"><span data-stu-id="66911-119">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66911-120">电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="66911-120">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="66911-121">是</span><span class="sxs-lookup"><span data-stu-id="66911-121">Yes</span></span></p></td>
<td><p><span data-ttu-id="66911-122">是</span><span class="sxs-lookup"><span data-stu-id="66911-122">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66911-123">企业语音</span><span class="sxs-lookup"><span data-stu-id="66911-123">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="66911-124">是</span><span class="sxs-lookup"><span data-stu-id="66911-124">Yes</span></span></p></td>
<td><p><span data-ttu-id="66911-125">是</span><span class="sxs-lookup"><span data-stu-id="66911-125">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66911-126">虚拟化</span><span class="sxs-lookup"><span data-stu-id="66911-126">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="66911-127">是</span><span class="sxs-lookup"><span data-stu-id="66911-127">Yes</span></span></p></td>
<td><p><span data-ttu-id="66911-128">是</span><span class="sxs-lookup"><span data-stu-id="66911-128">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66911-129">高可用性、故障转移和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="66911-129">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="66911-130">是</span><span class="sxs-lookup"><span data-stu-id="66911-130">Yes</span></span></p></td>
<td><p><span data-ttu-id="66911-131">否</span><span class="sxs-lookup"><span data-stu-id="66911-131">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

