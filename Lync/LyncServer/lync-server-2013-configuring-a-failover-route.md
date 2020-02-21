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
ms.openlocfilehash: 50917bffe3c6294b554edc7f9c3f620721e04737
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-failover-route-in-lync-server-2013"></a><span data-ttu-id="ed92a-102">在 Lync Server 2013 中配置故障转移路由</span><span class="sxs-lookup"><span data-stu-id="ed92a-102">Configuring a failover route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed92a-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ed92a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ed92a-p101">以下示例显示在 Dallas-GW1 因维护而关闭或因其他原因不可用时，管理员如何定义故障转移路由以供使用。下面的表显示了所需的配置更改。</span><span class="sxs-lookup"><span data-stu-id="ed92a-p101">The following example shows how an administrator can define a failover route for use if the Dallas-GW1 is down for maintenance or is otherwise unavailable. The following tables illustrate the required configuration change.</span></span>

### <a name="table-1-user-policy"></a><span data-ttu-id="ed92a-p102">表 1. 用户策略</span><span class="sxs-lookup"><span data-stu-id="ed92a-p102">Table 1. User Policy</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed92a-108">用户策略</span><span class="sxs-lookup"><span data-stu-id="ed92a-108">User policy</span></span></th>
<th><span data-ttu-id="ed92a-109">电话用法</span><span class="sxs-lookup"><span data-stu-id="ed92a-109">Phone usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed92a-110">Default Calling Policy</span><span class="sxs-lookup"><span data-stu-id="ed92a-110">Default Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="ed92a-111">Local</span><span class="sxs-lookup"><span data-stu-id="ed92a-111">Local</span></span></p>
<p><span data-ttu-id="ed92a-112">名</span><span class="sxs-lookup"><span data-stu-id="ed92a-112">GlobalPSTNHopoff</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed92a-113">Redmond Local Policy</span><span class="sxs-lookup"><span data-stu-id="ed92a-113">Redmond Local Policy</span></span></p></td>
<td><p><span data-ttu-id="ed92a-114">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="ed92a-114">RedmondLocal</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed92a-115">Dallas Calling Policy</span><span class="sxs-lookup"><span data-stu-id="ed92a-115">Dallas Calling Policy</span></span></p></td>
<td><p><span data-ttu-id="ed92a-116">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="ed92a-116">DallasUsers</span></span></p>
<p><span data-ttu-id="ed92a-117">名</span><span class="sxs-lookup"><span data-stu-id="ed92a-117">GlobalPSTNHopoff</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="table-2-routes"></a><span data-ttu-id="ed92a-p103">表 2. 路由</span><span class="sxs-lookup"><span data-stu-id="ed92a-p103">Table 2. Routes</span></span>

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
<th><span data-ttu-id="ed92a-120">路由名称</span><span class="sxs-lookup"><span data-stu-id="ed92a-120">Route name</span></span></th>
<th><span data-ttu-id="ed92a-121">号码模式</span><span class="sxs-lookup"><span data-stu-id="ed92a-121">Number pattern</span></span></th>
<th><span data-ttu-id="ed92a-122">电话用法</span><span class="sxs-lookup"><span data-stu-id="ed92a-122">Phone usage</span></span></th>
<th><span data-ttu-id="ed92a-123">干线</span><span class="sxs-lookup"><span data-stu-id="ed92a-123">Trunk</span></span></th>
<th><span data-ttu-id="ed92a-124">网关</span><span class="sxs-lookup"><span data-stu-id="ed92a-124">Gateway</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed92a-125">Redmond Local Route</span><span class="sxs-lookup"><span data-stu-id="ed92a-125">Redmond Local Route</span></span></p></td>
<td><p><span data-ttu-id="ed92a-126">^\+1（425 | 206 | 253）（\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="ed92a-126">^\+1(425|206|253)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="ed92a-127">Local</span><span class="sxs-lookup"><span data-stu-id="ed92a-127">Local</span></span></p>
<p><span data-ttu-id="ed92a-128">RedmondLocal</span><span class="sxs-lookup"><span data-stu-id="ed92a-128">RedmondLocal</span></span></p></td>
<td><p><span data-ttu-id="ed92a-129">Trunk1</span><span class="sxs-lookup"><span data-stu-id="ed92a-129">Trunk1</span></span></p>
<p><span data-ttu-id="ed92a-130">Trunk2</span><span class="sxs-lookup"><span data-stu-id="ed92a-130">Trunk2</span></span></p></td>
<td><p><span data-ttu-id="ed92a-131">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="ed92a-131">Red-GW1</span></span></p>
<p><span data-ttu-id="ed92a-132">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="ed92a-132">Red-GW2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed92a-133">Dallas Local Route</span><span class="sxs-lookup"><span data-stu-id="ed92a-133">Dallas Local Route</span></span></p></td>
<td><p><span data-ttu-id="ed92a-134">^\+1（972 | 214 | 469）（\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="ed92a-134">^\+1(972|214|469)(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="ed92a-135">Local</span><span class="sxs-lookup"><span data-stu-id="ed92a-135">Local</span></span></p></td>
<td><p><span data-ttu-id="ed92a-136">Trunk3</span><span class="sxs-lookup"><span data-stu-id="ed92a-136">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="ed92a-137">达拉斯-GW1</span><span class="sxs-lookup"><span data-stu-id="ed92a-137">Dallas-GW1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed92a-138">Universal Route</span><span class="sxs-lookup"><span data-stu-id="ed92a-138">Universal Route</span></span></p></td>
<td><p><span data-ttu-id="ed92a-139">^\+?（\d \*） $</span><span class="sxs-lookup"><span data-stu-id="ed92a-139">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="ed92a-140">名</span><span class="sxs-lookup"><span data-stu-id="ed92a-140">GlobalPSTNHopoff</span></span></p></td>
<td><p><span data-ttu-id="ed92a-141">Trunk1</span><span class="sxs-lookup"><span data-stu-id="ed92a-141">Trunk1</span></span></p>
<p><span data-ttu-id="ed92a-142">Trunk2</span><span class="sxs-lookup"><span data-stu-id="ed92a-142">Trunk2</span></span></p>
<p><span data-ttu-id="ed92a-143">Trunk3</span><span class="sxs-lookup"><span data-stu-id="ed92a-143">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="ed92a-144">Red-GW1</span><span class="sxs-lookup"><span data-stu-id="ed92a-144">Red-GW1</span></span></p>
<p><span data-ttu-id="ed92a-145">Red-GW2</span><span class="sxs-lookup"><span data-stu-id="ed92a-145">Red-GW2</span></span></p>
<p><span data-ttu-id="ed92a-146">达拉斯-GW1</span><span class="sxs-lookup"><span data-stu-id="ed92a-146">Dallas-GW1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed92a-147">Dallas Users Route</span><span class="sxs-lookup"><span data-stu-id="ed92a-147">Dallas Users Route</span></span></p></td>
<td><p><span data-ttu-id="ed92a-148">^\+?（\d \*） $</span><span class="sxs-lookup"><span data-stu-id="ed92a-148">^\+?(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="ed92a-149">DallasUsers</span><span class="sxs-lookup"><span data-stu-id="ed92a-149">DallasUsers</span></span></p></td>
<td><p><span data-ttu-id="ed92a-150">Trunk3</span><span class="sxs-lookup"><span data-stu-id="ed92a-150">Trunk3</span></span></p></td>
<td><p><span data-ttu-id="ed92a-151">达拉斯-GW1</span><span class="sxs-lookup"><span data-stu-id="ed92a-151">Dallas-GW1</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ed92a-p104">在表 1 中，名为 GlobalPSTNHopoff 的电话用法添加到 Dallas Calling Policy 中的 DallasUsers 电话用法的后面。这样，当 DallasUsers 电话用法的路由不可用时，具有 Dallas Calling Policy 的呼叫就可以使用针对 GlobalPSTNHopoff 电话用法配置的路由。</span><span class="sxs-lookup"><span data-stu-id="ed92a-p104">In Table 1, a phone usage of GlobalPSTNHopoff is added after the DallasUsers phone usage in the Dallas Calling Policy. This enables calls with the Dallas Calling policy to use routes that are configured for the GlobalPSTNHopoff phone usage if a route for the DallasUsers phone usage is unavailable.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

