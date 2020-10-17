---
title: Lync Server 2013 可伸缩性
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
ms.openlocfilehash: d2b26f8f7b7b254a8576a08e9b24fdeb2da633b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510955"
---
# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="649b0-102">Lync Server 2013 的可伸缩性</span><span class="sxs-lookup"><span data-stu-id="649b0-102">Scalability with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="649b0-103">_**上次修改的主题：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="649b0-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="649b0-104">在两个版本的 Enterprise Edition 和 Standard Edition 中提供了 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="649b0-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="649b0-105">不同的版本主要面向不同规模的组织。</span><span class="sxs-lookup"><span data-stu-id="649b0-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="649b0-106">如下表所示，两个版本均支持所有工作负荷的所有功能，高可用性和灾难恢复除外。</span><span class="sxs-lookup"><span data-stu-id="649b0-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="649b0-107">功能</span><span class="sxs-lookup"><span data-stu-id="649b0-107">Feature</span></span></th>
<th><span data-ttu-id="649b0-108">Enterprise Edition 是否支持？</span><span class="sxs-lookup"><span data-stu-id="649b0-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="649b0-109">Standard Edition 是否支持？</span><span class="sxs-lookup"><span data-stu-id="649b0-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="649b0-110">即时消息 (IM) 和状态</span><span class="sxs-lookup"><span data-stu-id="649b0-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="649b0-111">是</span><span class="sxs-lookup"><span data-stu-id="649b0-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="649b0-112">是</span><span class="sxs-lookup"><span data-stu-id="649b0-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="649b0-113">会议</span><span class="sxs-lookup"><span data-stu-id="649b0-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="649b0-114">是</span><span class="sxs-lookup"><span data-stu-id="649b0-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="649b0-115">是</span><span class="sxs-lookup"><span data-stu-id="649b0-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="649b0-116">A/V 会议</span><span class="sxs-lookup"><span data-stu-id="649b0-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="649b0-117">是</span><span class="sxs-lookup"><span data-stu-id="649b0-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="649b0-118">是</span><span class="sxs-lookup"><span data-stu-id="649b0-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="649b0-119">电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="649b0-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="649b0-120">是</span><span class="sxs-lookup"><span data-stu-id="649b0-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="649b0-121">是</span><span class="sxs-lookup"><span data-stu-id="649b0-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="649b0-122">企业语音</span><span class="sxs-lookup"><span data-stu-id="649b0-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="649b0-123">是</span><span class="sxs-lookup"><span data-stu-id="649b0-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="649b0-124">是</span><span class="sxs-lookup"><span data-stu-id="649b0-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="649b0-125">虚拟化</span><span class="sxs-lookup"><span data-stu-id="649b0-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="649b0-126">是</span><span class="sxs-lookup"><span data-stu-id="649b0-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="649b0-127">是</span><span class="sxs-lookup"><span data-stu-id="649b0-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="649b0-128">高可用性、故障转移和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="649b0-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="649b0-129">是</span><span class="sxs-lookup"><span data-stu-id="649b0-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="649b0-130">否</span><span class="sxs-lookup"><span data-stu-id="649b0-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

