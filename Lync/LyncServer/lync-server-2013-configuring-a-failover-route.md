---
title: Lync Server 2013：配置故障转移路由
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
ms.openlocfilehash: 22ebdf359a8cdf5f20ada8740a589b0181c3cc93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="7903f-102">在 Lync Server 2013 中配置故障转移路由</span><span class="sxs-lookup"><span data-stu-id="7903f-102">Configuring a failover route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7903f-103">_**主题上次修改时间：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="7903f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="7903f-p101">以下示例显示在 Dallas-GW1 因维护而关闭或因其他原因不可用时，管理员如何定义故障转移路由以供使用。下面的表显示了所需的配置更改。</span><span class="sxs-lookup"><span data-stu-id="7903f-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="7903f-p102">表 1. 用户策略</span><span class="sxs-lookup"><span data-stu-id="7903f-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7903f-108">用户策略</span><span class="sxs-lookup"><span data-stu-id="7903f-108">User policy</span></span></th>
<th><span data-ttu-id="7903f-109">电话用法</span><span class="sxs-lookup"><span data-stu-id="7903f-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7903f-110">默认呼叫策略</span><span class="sxs-lookup"><span data-stu-id="7903f-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="7903f-111">Local</span><span class="sxs-lookup"><span data-stu-id="7903f-111">Local</span></span></p>
<p><span data-ttu-id="7903f-112">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="7903f-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7903f-113">Redmond 本地策略</span><span class="sxs-lookup"><span data-stu-id="7903f-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="7903f-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="7903f-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7903f-115">Dallas 呼叫策略</span><span class="sxs-lookup"><span data-stu-id="7903f-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="7903f-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="7903f-116">DallasUsers</span></span></p>
<p><span data-ttu-id="7903f-117">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="7903f-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="7903f-p103">表 2. 路由</span><span class="sxs-lookup"><span data-stu-id="7903f-p103">Table 2. Routes</span></span>

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
<th><span data-ttu-id="7903f-120">路由名称</span><span class="sxs-lookup"><span data-stu-id="7903f-120">Route name</span></span></th>
<th><span data-ttu-id="7903f-121">号码模式</span><span class="sxs-lookup"><span data-stu-id="7903f-121">Number pattern</span></span></th>
<th><span data-ttu-id="7903f-122">电话用法</span><span class="sxs-lookup"><span data-stu-id="7903f-122">Phone usage</span></span></th>
<th><span data-ttu-id="7903f-123">中继</span><span class="sxs-lookup"><span data-stu-id="7903f-123">Trunk</span></span></th>
<th><span data-ttu-id="7903f-124">网关</span><span class="sxs-lookup"><span data-stu-id="7903f-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7903f-125">Redmond 本地路由</span><span class="sxs-lookup"><span data-stu-id="7903f-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="7903f-126">^\+1（425 | 206 | 253）（\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="7903f-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="7903f-127">Local</span><span class="sxs-lookup"><span data-stu-id="7903f-127">Local</span></span></p>
<p><span data-ttu-id="7903f-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="7903f-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="7903f-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="7903f-129">Trunk1</span></span></p>
<p><span data-ttu-id="7903f-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="7903f-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="7903f-131">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="7903f-131">Red-GW1</span></span></p>
<p><span data-ttu-id="7903f-132">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="7903f-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7903f-133">Dallas 本地路由</span><span class="sxs-lookup"><span data-stu-id="7903f-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="7903f-134">^\+1（972 | 214 | 469）（\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="7903f-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="7903f-135">Local</span><span class="sxs-lookup"><span data-stu-id="7903f-135">Local</span></span></p></td>
<td><p><span data-ttu-id="7903f-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="7903f-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="7903f-137">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="7903f-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7903f-138">通用路由</span><span class="sxs-lookup"><span data-stu-id="7903f-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="7903f-139">^\+?（\d \*） $</span><span class="sxs-lookup"><span data-stu-id="7903f-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="7903f-140">GlobalPSTNHopoff</span><span class="sxs-lookup"><span data-stu-id="7903f-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="7903f-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="7903f-141">Trunk1</span></span></p>
<p><span data-ttu-id="7903f-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="7903f-142">Trunk2</span></span></p>
<p><span data-ttu-id="7903f-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="7903f-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="7903f-144">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="7903f-144">Red-GW1</span></span></p>
<p><span data-ttu-id="7903f-145">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="7903f-145">Red-GW2</span></span></p>
<p><span data-ttu-id="7903f-146">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="7903f-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7903f-147">Dallas 用户路由</span><span class="sxs-lookup"><span data-stu-id="7903f-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="7903f-148">^\+?（\d \*） $</span><span class="sxs-lookup"><span data-stu-id="7903f-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="7903f-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="7903f-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="7903f-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="7903f-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="7903f-151">Dallas-GW1</span><span class="sxs-lookup"><span data-stu-id="7903f-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7903f-p104">在表 1 中，名为 GlobalPSTNHopoff 的电话用法添加到 Dallas Calling Policy 中的 DallasUsers 电话用法的后面。这样，当 DallasUsers 电话用法的路由不可用时，具有 Dallas Calling Policy 的呼叫就可以使用针对 GlobalPSTNHopoff 电话用法配置的路由。</span><span class="sxs-lookup"><span data-stu-id="7903f-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

