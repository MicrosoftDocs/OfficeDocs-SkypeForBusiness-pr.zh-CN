---
title: Lync Server 2013：配置故障转移路由
description: Lync Server 2013：配置故障转移路由。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a failover route
ms:assetid: 76e48df4-3b78-4fb7-b1f7-c1e604b81bad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398581(v=OCS.15)
ms:contentKeyID: 48184542
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7cfc45276931685a2d42103b1b7f1d5015dcd7e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560488"
---
# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="4c46d-103">在 Lync Server 2013 中配置故障转移路由</span><span class="sxs-lookup"><span data-stu-id="4c46d-103">Configuring a failover route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c46d-104">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4c46d-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="4c46d-p101">以下示例显示在 Dallas-GW1 因维护而关闭或因其他原因不可用时，管理员如何定义故障转移路由以供使用。下面的表显示了所需的配置更改。</span><span class="sxs-lookup"><span data-stu-id="4c46d-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="4c46d-p102">表 1. 用户策略</span><span class="sxs-lookup"><span data-stu-id="4c46d-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c46d-109">用户策略</span><span class="sxs-lookup"><span data-stu-id="4c46d-109">User policy</span></span></th>
<th><span data-ttu-id="4c46d-110">电话用法</span><span class="sxs-lookup"><span data-stu-id="4c46d-110">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c46d-111">Default Calling Policy</span><span class="sxs-lookup"><span data-stu-id="4c46d-111">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="4c46d-112">本地</span><span class="sxs-lookup"><span data-stu-id="4c46d-112">Local</span></span></p>
<p><span data-ttu-id="4c46d-113">名</span><span class="sxs-lookup"><span data-stu-id="4c46d-113">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c46d-114">Redmond Local Policy</span><span class="sxs-lookup"><span data-stu-id="4c46d-114">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="4c46d-115">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="4c46d-115">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c46d-116">Dallas Calling Policy</span><span class="sxs-lookup"><span data-stu-id="4c46d-116">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="4c46d-117">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="4c46d-117">DallasUsers</span></span></p>
<p><span data-ttu-id="4c46d-118">名</span><span class="sxs-lookup"><span data-stu-id="4c46d-118">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="4c46d-p103">表 2. 路由</span><span class="sxs-lookup"><span data-stu-id="4c46d-p103">Table 2. Routes</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c46d-121">路由名称</span><span class="sxs-lookup"><span data-stu-id="4c46d-121">Route name</span></span></th>
<th><span data-ttu-id="4c46d-122">号码模式</span><span class="sxs-lookup"><span data-stu-id="4c46d-122">Number pattern</span></span></th>
<th><span data-ttu-id="4c46d-123">电话用法</span><span class="sxs-lookup"><span data-stu-id="4c46d-123">Phone usage</span></span></th>
<th><span data-ttu-id="4c46d-124">干线</span><span class="sxs-lookup"><span data-stu-id="4c46d-124">Trunk</span></span></th>
<th><span data-ttu-id="4c46d-125">网关</span><span class="sxs-lookup"><span data-stu-id="4c46d-125">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c46d-126">Redmond Local Route</span><span class="sxs-lookup"><span data-stu-id="4c46d-126">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="4c46d-127">^\+1 (425 | 206 | 253) # A2\d {7}) $</span><span class="sxs-lookup"><span data-stu-id="4c46d-127">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="4c46d-128">本地</span><span class="sxs-lookup"><span data-stu-id="4c46d-128">Local</span></span></p>
<p><span data-ttu-id="4c46d-129">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="4c46d-129">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="4c46d-130">Trunk1</span><span class="sxs-lookup"><span data-stu-id="4c46d-130">Trunk1</span></span></p>
<p><span data-ttu-id="4c46d-131">Trunk2</span><span class="sxs-lookup"><span data-stu-id="4c46d-131">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="4c46d-132">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="4c46d-132">Red-GW1</span></span></p>
<p><span data-ttu-id="4c46d-133">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="4c46d-133">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c46d-134">Dallas Local Route</span><span class="sxs-lookup"><span data-stu-id="4c46d-134">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="4c46d-135">^\+1 (972 | 214 | 469) # A2\d {7}) $</span><span class="sxs-lookup"><span data-stu-id="4c46d-135">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="4c46d-136">本地</span><span class="sxs-lookup"><span data-stu-id="4c46d-136">Local</span></span></p></td>
<td><p><span data-ttu-id="4c46d-137">Trunk3</span><span class="sxs-lookup"><span data-stu-id="4c46d-137">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="4c46d-138">达拉斯-GW1</span><span class="sxs-lookup"><span data-stu-id="4c46d-138">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c46d-139">Universal Route</span><span class="sxs-lookup"><span data-stu-id="4c46d-139">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="4c46d-140">^\+ ( \d \* ) $</span><span class="sxs-lookup"><span data-stu-id="4c46d-140">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="4c46d-141">名</span><span class="sxs-lookup"><span data-stu-id="4c46d-141">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="4c46d-142">Trunk1</span><span class="sxs-lookup"><span data-stu-id="4c46d-142">Trunk1</span></span></p>
<p><span data-ttu-id="4c46d-143">Trunk2</span><span class="sxs-lookup"><span data-stu-id="4c46d-143">Trunk2</span></span></p>
<p><span data-ttu-id="4c46d-144">Trunk3</span><span class="sxs-lookup"><span data-stu-id="4c46d-144">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="4c46d-145">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="4c46d-145">Red-GW1</span></span></p>
<p><span data-ttu-id="4c46d-146">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="4c46d-146">Red-GW2</span></span></p>
<p><span data-ttu-id="4c46d-147">达拉斯-GW1</span><span class="sxs-lookup"><span data-stu-id="4c46d-147">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c46d-148">Dallas Users Route</span><span class="sxs-lookup"><span data-stu-id="4c46d-148">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="4c46d-149">^\+ ( \d \* ) $</span><span class="sxs-lookup"><span data-stu-id="4c46d-149">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="4c46d-150">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="4c46d-150">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="4c46d-151">Trunk3</span><span class="sxs-lookup"><span data-stu-id="4c46d-151">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="4c46d-152">达拉斯-GW1</span><span class="sxs-lookup"><span data-stu-id="4c46d-152">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4c46d-p104">在表 1 中，名为 GlobalPSTNHopoff 的电话用法添加到 Dallas Calling Policy 中的 DallasUsers 电话用法的后面。这样，当 DallasUsers 电话用法的路由不可用时，具有 Dallas Calling Policy 的呼叫就可以使用针对 GlobalPSTNHopoff 电话用法配置的路由。</span><span class="sxs-lookup"><span data-stu-id="4c46d-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

