---
title: Lync Server 2013：组间呼叫应答的容量规划
description: Lync Server 2013：组间呼叫应答的容量规划。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12648c57d1036a0ed27c60ef6399bf570c5dcd3d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544528"
---
# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="d9bd1-103">Lync Server 2013 中组呼叫应答的容量规划</span><span class="sxs-lookup"><span data-stu-id="d9bd1-103">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9bd1-104">_**上次修改的主题：** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="d9bd1-104">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="d9bd1-105">下表介绍了可用作容量规划需求基础的组呼叫装货用户模型。</span><span class="sxs-lookup"><span data-stu-id="d9bd1-105">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d9bd1-106">组呼叫应答基于呼叫寄存应用程序。</span><span class="sxs-lookup"><span data-stu-id="d9bd1-106">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="d9bd1-107">请记住，对于灾难恢复容量规划，配对池的每个池应能够在两个池中处理呼叫寄存服务的工作负载，包括组内呼叫应答。</span><span class="sxs-lookup"><span data-stu-id="d9bd1-107">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="d9bd1-108">组呼叫应答用户模型</span><span class="sxs-lookup"><span data-stu-id="d9bd1-108">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9bd1-109">跃点数</span><span class="sxs-lookup"><span data-stu-id="d9bd1-109">Metric</span></span></th>
<th><span data-ttu-id="d9bd1-110">每个前端池 (8 台前端服务器) </span><span class="sxs-lookup"><span data-stu-id="d9bd1-110">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="d9bd1-111">每台 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="d9bd1-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9bd1-112">建议的每组用户数</span><span class="sxs-lookup"><span data-stu-id="d9bd1-112">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="d9bd1-113">50</span><span class="sxs-lookup"><span data-stu-id="d9bd1-113">50</span></span></p></td>
<td><p><span data-ttu-id="d9bd1-114">50</span><span class="sxs-lookup"><span data-stu-id="d9bd1-114">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9bd1-115">建议的组数</span><span class="sxs-lookup"><span data-stu-id="d9bd1-115">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="d9bd1-116">500</span><span class="sxs-lookup"><span data-stu-id="d9bd1-116">500</span></span></p></td>
<td><p><span data-ttu-id="d9bd1-117">60</span><span class="sxs-lookup"><span data-stu-id="d9bd1-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9bd1-118">为组中的呼叫应答启用的每个池的最大用户数</span><span class="sxs-lookup"><span data-stu-id="d9bd1-118">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="d9bd1-119">25,000</span><span class="sxs-lookup"><span data-stu-id="d9bd1-119">25,000</span></span></p></td>
<td><p><span data-ttu-id="d9bd1-120">3,000</span><span class="sxs-lookup"><span data-stu-id="d9bd1-120">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9bd1-121">每个池每分钟对每个池启用的组内呼叫的总传入呼叫的最大速率</span><span class="sxs-lookup"><span data-stu-id="d9bd1-121">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="d9bd1-122">500</span><span class="sxs-lookup"><span data-stu-id="d9bd1-122">500</span></span></p></td>
<td><p><span data-ttu-id="d9bd1-123">60</span><span class="sxs-lookup"><span data-stu-id="d9bd1-123">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d9bd1-124">用户每个池每分钟检索组中的呼叫的最大速率</span><span class="sxs-lookup"><span data-stu-id="d9bd1-124">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="d9bd1-125">200</span><span class="sxs-lookup"><span data-stu-id="d9bd1-125">200</span></span></p></td>
<td><p><span data-ttu-id="d9bd1-126">word</span><span class="sxs-lookup"><span data-stu-id="d9bd1-126">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="d9bd1-127">对于少于八台前端服务器的前端池，以线性方式计算指标。</span><span class="sxs-lookup"><span data-stu-id="d9bd1-127">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="d9bd1-128">例如，如果您的前端池有一个前端服务器，则计算表中显示的值的最大负载为1/8。</span><span class="sxs-lookup"><span data-stu-id="d9bd1-128">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="d9bd1-129">只要您不超过每个池的最大用户数，您就可以按组和组数增加或减少建议的用户数。</span><span class="sxs-lookup"><span data-stu-id="d9bd1-129">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="d9bd1-130">例如，您的 Standard Edition server 可以拥有每组25个用户的120组，因为为组内呼叫应答启用的用户数量仍在用户模型中的最大 (，120组数25个用户3000是为用户启用组内呼叫应答) 的用户。</span><span class="sxs-lookup"><span data-stu-id="d9bd1-130">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

