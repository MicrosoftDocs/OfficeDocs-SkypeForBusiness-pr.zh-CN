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
ms.openlocfilehash: 17477c647d2e5dd5918225486c43b93a29509fb2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="a71b8-102">在 Lync Server 2013 中配置故障转移路由</span><span class="sxs-lookup"><span data-stu-id="a71b8-102">Configuring a failover route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a71b8-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a71b8-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a71b8-p101">以下示例显示在 Dallas-GW1 因维护而关闭或因其他原因不可用时，管理员如何定义故障转移路由以供使用。下面的表显示了所需的配置更改。</span><span class="sxs-lookup"><span data-stu-id="a71b8-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="a71b8-p102">表 1. 用户策略</span><span class="sxs-lookup"><span data-stu-id="a71b8-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a71b8-108">用户策略</span><span class="sxs-lookup"><span data-stu-id="a71b8-108">User policy</span></span></th>
<th><span data-ttu-id="a71b8-109">电话用法</span><span class="sxs-lookup"><span data-stu-id="a71b8-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a71b8-110">Default Calling Policy</span><span class="sxs-lookup"><span data-stu-id="a71b8-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="a71b8-111">Local</span><span class="sxs-lookup"><span data-stu-id="a71b8-111">Local</span></span></p>
<p><span data-ttu-id="a71b8-112">名</span><span class="sxs-lookup"><span data-stu-id="a71b8-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71b8-113">Redmond Local Policy</span><span class="sxs-lookup"><span data-stu-id="a71b8-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="a71b8-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="a71b8-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71b8-115">Dallas Calling Policy</span><span class="sxs-lookup"><span data-stu-id="a71b8-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="a71b8-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="a71b8-116">DallasUsers</span></span></p>
<p><span data-ttu-id="a71b8-117">名</span><span class="sxs-lookup"><span data-stu-id="a71b8-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="a71b8-p103">表 2. 路由</span><span class="sxs-lookup"><span data-stu-id="a71b8-p103">Table 2. Routes</span></span>

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
<th><span data-ttu-id="a71b8-120">路由名称</span><span class="sxs-lookup"><span data-stu-id="a71b8-120">Route name</span></span></th>
<th><span data-ttu-id="a71b8-121">号码模式</span><span class="sxs-lookup"><span data-stu-id="a71b8-121">Number pattern</span></span></th>
<th><span data-ttu-id="a71b8-122">电话用法</span><span class="sxs-lookup"><span data-stu-id="a71b8-122">Phone usage</span></span></th>
<th><span data-ttu-id="a71b8-123">干线</span><span class="sxs-lookup"><span data-stu-id="a71b8-123">Trunk</span></span></th>
<th><span data-ttu-id="a71b8-124">网关</span><span class="sxs-lookup"><span data-stu-id="a71b8-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a71b8-125">Redmond Local Route</span><span class="sxs-lookup"><span data-stu-id="a71b8-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="a71b8-126">^\+1（425 | 206 | 253）（\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="a71b8-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="a71b8-127">Local</span><span class="sxs-lookup"><span data-stu-id="a71b8-127">Local</span></span></p>
<p><span data-ttu-id="a71b8-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="a71b8-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="a71b8-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="a71b8-129">Trunk1</span></span></p>
<p><span data-ttu-id="a71b8-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="a71b8-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="a71b8-131">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="a71b8-131">Red-GW1</span></span></p>
<p><span data-ttu-id="a71b8-132">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="a71b8-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71b8-133">Dallas Local Route</span><span class="sxs-lookup"><span data-stu-id="a71b8-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="a71b8-134">^\+1（972 | 214 | 469）（\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="a71b8-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="a71b8-135">Local</span><span class="sxs-lookup"><span data-stu-id="a71b8-135">Local</span></span></p></td>
<td><p><span data-ttu-id="a71b8-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="a71b8-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="a71b8-137">达拉斯-GW1</span><span class="sxs-lookup"><span data-stu-id="a71b8-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a71b8-138">Universal Route</span><span class="sxs-lookup"><span data-stu-id="a71b8-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="a71b8-139">^\+?（\d \*） $</span><span class="sxs-lookup"><span data-stu-id="a71b8-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="a71b8-140">名</span><span class="sxs-lookup"><span data-stu-id="a71b8-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="a71b8-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="a71b8-141">Trunk1</span></span></p>
<p><span data-ttu-id="a71b8-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="a71b8-142">Trunk2</span></span></p>
<p><span data-ttu-id="a71b8-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="a71b8-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="a71b8-144">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="a71b8-144">Red-GW1</span></span></p>
<p><span data-ttu-id="a71b8-145">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="a71b8-145">Red-GW2</span></span></p>
<p><span data-ttu-id="a71b8-146">达拉斯-GW1</span><span class="sxs-lookup"><span data-stu-id="a71b8-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a71b8-147">Dallas Users Route</span><span class="sxs-lookup"><span data-stu-id="a71b8-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="a71b8-148">^\+?（\d \*） $</span><span class="sxs-lookup"><span data-stu-id="a71b8-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="a71b8-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="a71b8-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="a71b8-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="a71b8-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="a71b8-151">达拉斯-GW1</span><span class="sxs-lookup"><span data-stu-id="a71b8-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a71b8-p104">在表 1 中，名为 GlobalPSTNHopoff 的电话用法添加到 Dallas Calling Policy 中的 DallasUsers 电话用法的后面。这样，当 DallasUsers 电话用法的路由不可用时，具有 Dallas Calling Policy 的呼叫就可以使用针对 GlobalPSTNHopoff 电话用法配置的路由。</span><span class="sxs-lookup"><span data-stu-id="a71b8-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

