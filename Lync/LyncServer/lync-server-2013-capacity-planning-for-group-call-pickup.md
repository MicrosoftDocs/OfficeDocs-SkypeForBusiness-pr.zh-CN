---
title: 'Lync Server 2013: 组呼叫装货的容量规划'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba588de723e7482039fdae4b97991080a1b92c47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="f8cee-102">Lync Server 2013 中组呼叫装货的容量规划</span><span class="sxs-lookup"><span data-stu-id="f8cee-102">Capacity planning for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8cee-103">_**主题上次修改时间:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="f8cee-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="f8cee-104">下表介绍了组呼叫装货用户模型, 您可以将其用作容量规划要求的基础。</span><span class="sxs-lookup"><span data-stu-id="f8cee-104">The following table describes the Group Call Pickup user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f8cee-105">组呼叫分拣基于呼叫寄存应用程序。</span><span class="sxs-lookup"><span data-stu-id="f8cee-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="f8cee-106">请记住, 对于灾难恢复容量规划, 配对池的每个池都应该能够处理呼叫驻留服务的工作负荷, 包括组呼叫在两个池中的呼叫。</span><span class="sxs-lookup"><span data-stu-id="f8cee-106">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services, including Group Call Pickup, in both pools.</span></span>



</div>

### <a name="group-call-pickup-user-model"></a><span data-ttu-id="f8cee-107">组呼叫装货用户模型</span><span class="sxs-lookup"><span data-stu-id="f8cee-107">Group Call Pickup User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f8cee-108">指标</span><span class="sxs-lookup"><span data-stu-id="f8cee-108">Metric</span></span></th>
<th><span data-ttu-id="f8cee-109">每个前端池 (具有8个前端服务器)</span><span class="sxs-lookup"><span data-stu-id="f8cee-109">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="f8cee-110">每台 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="f8cee-110">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8cee-111">建议的每组用户数</span><span class="sxs-lookup"><span data-stu-id="f8cee-111">Recommended number of users per group</span></span></p></td>
<td><p><span data-ttu-id="f8cee-112">50</span><span class="sxs-lookup"><span data-stu-id="f8cee-112">50</span></span></p></td>
<td><p><span data-ttu-id="f8cee-113">50</span><span class="sxs-lookup"><span data-stu-id="f8cee-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8cee-114">建议的组数</span><span class="sxs-lookup"><span data-stu-id="f8cee-114">Recommended number of groups</span></span></p></td>
<td><p><span data-ttu-id="f8cee-115">500</span><span class="sxs-lookup"><span data-stu-id="f8cee-115">500</span></span></p></td>
<td><p><span data-ttu-id="f8cee-116">60</span><span class="sxs-lookup"><span data-stu-id="f8cee-116">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8cee-117">针对组内呼叫应答启用的每个池的最大用户数</span><span class="sxs-lookup"><span data-stu-id="f8cee-117">Maximum number of users per pool enabled for Group Call Pickup</span></span></p></td>
<td><p><span data-ttu-id="f8cee-118">25,000</span><span class="sxs-lookup"><span data-stu-id="f8cee-118">25,000</span></span></p></td>
<td><p><span data-ttu-id="f8cee-119">3,000</span><span class="sxs-lookup"><span data-stu-id="f8cee-119">3,000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8cee-120">每个池每分钟针对组内呼叫应答启用的所有用户的最大传入呼叫速率</span><span class="sxs-lookup"><span data-stu-id="f8cee-120">Maximum rate of incoming calls to total users enabled for Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="f8cee-121">500</span><span class="sxs-lookup"><span data-stu-id="f8cee-121">500</span></span></p></td>
<td><p><span data-ttu-id="f8cee-122">60</span><span class="sxs-lookup"><span data-stu-id="f8cee-122">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8cee-123">每个池每分钟用户使用组内呼叫应答检索的最大呼叫速率</span><span class="sxs-lookup"><span data-stu-id="f8cee-123">Maximum rate of calls retrieved by users with Group Call Pickup per pool per minute</span></span></p></td>
<td><p><span data-ttu-id="f8cee-124">200</span><span class="sxs-lookup"><span data-stu-id="f8cee-124">200</span></span></p></td>
<td><p><span data-ttu-id="f8cee-125">二十五</span><span class="sxs-lookup"><span data-stu-id="f8cee-125">25</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="f8cee-126">对于少于八个前端服务器的前端池, 按线性计算指标。</span><span class="sxs-lookup"><span data-stu-id="f8cee-126">For Front End pools that have fewer than eight Front End Servers, calculate the metrics linearly.</span></span> <span data-ttu-id="f8cee-127">例如, 如果您的前端池有一个前端服务器, 请将最大负载计算为表中显示的值1/8。</span><span class="sxs-lookup"><span data-stu-id="f8cee-127">For example, if your Front End pool has one Front End Server, calculate the maximum load as 1/8 of the values shown in the table.</span></span></P>
> <LI>
> <P><span data-ttu-id="f8cee-128">只要不超过每个池的最大用户数，您就可以增加或减少建议的组数以及每组用户数。</span><span class="sxs-lookup"><span data-stu-id="f8cee-128">You can increase or decrease the recommended number of users per group and number of groups as long as you do not exceed the maximum number of users per pool.</span></span> <span data-ttu-id="f8cee-129">例如, 你的标准版服务器可以拥有每组25个用户的120组, 因为为组呼叫挑选启用的用户数仍在用户模型的最大范围内 (即, 120 组乘以25个3000用户为组呼叫装货启用的用户)。</span><span class="sxs-lookup"><span data-stu-id="f8cee-129">For example, your Standard Edition server can have 120 groups with 25 users per group because the number of users enabled for Group Call Pickup is still within the user model maximum (that is, 120 groups times 25 users is 3,000 users enabled for Group Call Pickup).</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

