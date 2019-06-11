---
title: Lync Server 2013 可伸缩性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scalability
ms:assetid: 46fa0cb5-1507-4a12-ad3f-ba64585e2dc4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417160(v=OCS.15)
ms:contentKeyID: 48183995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dfdc96934871fd2e73af30507288c734e786cc0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="87bbf-102">Lync Server 2013 可伸缩性</span><span class="sxs-lookup"><span data-stu-id="87bbf-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="87bbf-103">_**主题上次修改时间:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="87bbf-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="87bbf-104">Lync Server 在两个版本的企业版和标准版中提供。</span><span class="sxs-lookup"><span data-stu-id="87bbf-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="87bbf-105">不同版本主要适用于不同规模的组织。</span><span class="sxs-lookup"><span data-stu-id="87bbf-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="87bbf-106">如下表所示, 这两个版本都支持除高可用性和灾难恢复之外的所有工作负荷中的所有功能。</span><span class="sxs-lookup"><span data-stu-id="87bbf-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="87bbf-107">功能</span><span class="sxs-lookup"><span data-stu-id="87bbf-107">Feature</span></span></th>
<th><span data-ttu-id="87bbf-108">在企业版中受支持？</span><span class="sxs-lookup"><span data-stu-id="87bbf-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="87bbf-109">在标准版中受支持？</span><span class="sxs-lookup"><span data-stu-id="87bbf-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="87bbf-110">即时消息 (IM) 和状态</span><span class="sxs-lookup"><span data-stu-id="87bbf-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="87bbf-111">是</span><span class="sxs-lookup"><span data-stu-id="87bbf-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="87bbf-112">是</span><span class="sxs-lookup"><span data-stu-id="87bbf-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87bbf-113">网络会议</span><span class="sxs-lookup"><span data-stu-id="87bbf-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="87bbf-114">是</span><span class="sxs-lookup"><span data-stu-id="87bbf-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="87bbf-115">是</span><span class="sxs-lookup"><span data-stu-id="87bbf-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87bbf-116">A/V 会议</span><span class="sxs-lookup"><span data-stu-id="87bbf-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="87bbf-117">是</span><span class="sxs-lookup"><span data-stu-id="87bbf-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="87bbf-118">是</span><span class="sxs-lookup"><span data-stu-id="87bbf-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87bbf-119">电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="87bbf-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="87bbf-120">是</span><span class="sxs-lookup"><span data-stu-id="87bbf-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="87bbf-121">是</span><span class="sxs-lookup"><span data-stu-id="87bbf-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87bbf-122">企业语音</span><span class="sxs-lookup"><span data-stu-id="87bbf-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="87bbf-123">是</span><span class="sxs-lookup"><span data-stu-id="87bbf-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="87bbf-124">是</span><span class="sxs-lookup"><span data-stu-id="87bbf-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="87bbf-125">Virtualization</span><span class="sxs-lookup"><span data-stu-id="87bbf-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="87bbf-126">是</span><span class="sxs-lookup"><span data-stu-id="87bbf-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="87bbf-127">是</span><span class="sxs-lookup"><span data-stu-id="87bbf-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="87bbf-128">高可用性、故障切换和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="87bbf-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="87bbf-129">是</span><span class="sxs-lookup"><span data-stu-id="87bbf-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="87bbf-130">否</span><span class="sxs-lookup"><span data-stu-id="87bbf-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

