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
ms.openlocfilehash: e6ff4828bdfddbfca7734836fdfdbe24f0b90c4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-with-lync-server-2013"></a><span data-ttu-id="b111e-102">Lync Server 2013 可伸缩性</span><span class="sxs-lookup"><span data-stu-id="b111e-102">Scalability with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b111e-103">_**主题上次修改时间：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="b111e-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="b111e-104">Lync Server 在两个版本的企业版和标准版中提供。</span><span class="sxs-lookup"><span data-stu-id="b111e-104">Lync Server is offered in two editions, Enterprise Edition and Standard Edition.</span></span> <span data-ttu-id="b111e-105">不同版本主要适用于不同规模的组织。</span><span class="sxs-lookup"><span data-stu-id="b111e-105">The different editions are intended primarily for different sizes of organizations.</span></span> <span data-ttu-id="b111e-106">如下表所示，这两个版本都支持除高可用性和灾难恢复之外的所有工作负荷中的所有功能。</span><span class="sxs-lookup"><span data-stu-id="b111e-106">As shown in the following table, both editions support all functionality in all workloads, except for high availability and disaster recovery.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b111e-107">功能</span><span class="sxs-lookup"><span data-stu-id="b111e-107">Feature</span></span></th>
<th><span data-ttu-id="b111e-108">在企业版中受支持？</span><span class="sxs-lookup"><span data-stu-id="b111e-108">Supported in Enterprise Edition?</span></span></th>
<th><span data-ttu-id="b111e-109">在标准版中受支持？</span><span class="sxs-lookup"><span data-stu-id="b111e-109">Supported in Standard Edition?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b111e-110">即时消息（IM）和状态</span><span class="sxs-lookup"><span data-stu-id="b111e-110">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="b111e-111">必需</span><span class="sxs-lookup"><span data-stu-id="b111e-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="b111e-112">是</span><span class="sxs-lookup"><span data-stu-id="b111e-112">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b111e-113">网络会议</span><span class="sxs-lookup"><span data-stu-id="b111e-113">Conferencing</span></span></p></td>
<td><p><span data-ttu-id="b111e-114">必需</span><span class="sxs-lookup"><span data-stu-id="b111e-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="b111e-115">是</span><span class="sxs-lookup"><span data-stu-id="b111e-115">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b111e-116">A/V 会议</span><span class="sxs-lookup"><span data-stu-id="b111e-116">A/V conferencing</span></span></p></td>
<td><p><span data-ttu-id="b111e-117">必需</span><span class="sxs-lookup"><span data-stu-id="b111e-117">Yes</span></span></p></td>
<td><p><span data-ttu-id="b111e-118">是</span><span class="sxs-lookup"><span data-stu-id="b111e-118">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b111e-119">电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="b111e-119">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="b111e-120">必需</span><span class="sxs-lookup"><span data-stu-id="b111e-120">Yes</span></span></p></td>
<td><p><span data-ttu-id="b111e-121">是</span><span class="sxs-lookup"><span data-stu-id="b111e-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b111e-122">企业语音</span><span class="sxs-lookup"><span data-stu-id="b111e-122">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="b111e-123">必需</span><span class="sxs-lookup"><span data-stu-id="b111e-123">Yes</span></span></p></td>
<td><p><span data-ttu-id="b111e-124">是</span><span class="sxs-lookup"><span data-stu-id="b111e-124">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b111e-125">Virtualization</span><span class="sxs-lookup"><span data-stu-id="b111e-125">Virtualization</span></span></p></td>
<td><p><span data-ttu-id="b111e-126">必需</span><span class="sxs-lookup"><span data-stu-id="b111e-126">Yes</span></span></p></td>
<td><p><span data-ttu-id="b111e-127">是</span><span class="sxs-lookup"><span data-stu-id="b111e-127">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b111e-128">高可用性、故障切换和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="b111e-128">High availability, failover, and disaster recovery</span></span></p></td>
<td><p><span data-ttu-id="b111e-129">是</span><span class="sxs-lookup"><span data-stu-id="b111e-129">Yes</span></span></p></td>
<td><p><span data-ttu-id="b111e-130">否</span><span class="sxs-lookup"><span data-stu-id="b111e-130">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

