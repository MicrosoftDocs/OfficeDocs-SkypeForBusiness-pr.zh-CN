---
title: Lync Server 2013：在灾难恢复过程中管理组呼叫装货
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Group Call Pickup during disaster recovery
ms:assetid: 2d32f19f-c649-4a72-a4fb-edd338e3a7cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945618(v=OCS.15)
ms:contentKeyID: 51541455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 633ccf1c792f951d13c747c935af51569365c753
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="5d674-102">在 Lync Server 2013 中管理灾难恢复期间的组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="5d674-102">Manage Group Call Pickup during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d674-103">_**上次修改的主题：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="5d674-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="5d674-104">当前端池因计划外事件而变为不可用时，服务将故障转移到备份池。</span><span class="sxs-lookup"><span data-stu-id="5d674-104">When a Front End pool becomes unavailable due an unplanned incident, service is failed over to the backup pool.</span></span> <span data-ttu-id="5d674-105">在故障转移到备份池的过程中，用户将被重定向到备份池并处于恢复模式。</span><span class="sxs-lookup"><span data-stu-id="5d674-105">During failover to the backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="5d674-106">在恢复模式下，用户不能选择其他用户的呼叫，也不能接听其他用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="5d674-106">While in resiliency mode, users cannot pick up other users' calls or have their calls picked up by other users.</span></span> <span data-ttu-id="5d674-107">故障转移完成后，用户可以像往常一样使用组呼叫应答。</span><span class="sxs-lookup"><span data-stu-id="5d674-107">When failover is complete, users can again use Group Call Pickup as usual.</span></span>

<span data-ttu-id="5d674-108">在故障回复到主池期间，用户会被重定向到主池，并再次处于恢复模式。</span><span class="sxs-lookup"><span data-stu-id="5d674-108">During failback to the primary pool, users are redirected to the primary pool and are again in resiliency mode.</span></span> <span data-ttu-id="5d674-109">在用户离开恢复模式之前，组呼叫应答功能将不可用。</span><span class="sxs-lookup"><span data-stu-id="5d674-109">Group Call Pickup functionality is not available until the users are out of resiliency mode.</span></span>

<span data-ttu-id="5d674-110">本节讨论灾难恢复过程中组呼叫选取的一些注意事项，同时还介绍了用户体验。</span><span class="sxs-lookup"><span data-stu-id="5d674-110">This section discusses some considerations for Group Call Pickup during disaster recovery and also describes the user experience.</span></span>

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a><span data-ttu-id="5d674-111">灾难恢复过程中组呼叫装货的注意事项</span><span class="sxs-lookup"><span data-stu-id="5d674-111">Considerations for Group Call Pickup During Disaster Recovery</span></span>

<span data-ttu-id="5d674-112">在灾难恢复过程中，作为故障转移过程的一部分被重定向到备份池的用户将使用在备份池中为呼叫应答组编号运行的呼叫寄存应用程序。</span><span class="sxs-lookup"><span data-stu-id="5d674-112">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application running in the backup pool for the call pickup group numbers.</span></span> <span data-ttu-id="5d674-113">因此，在灾难恢复过程中对组呼叫选取的支持要求在主池和备份池中部署和启用呼叫寄存应用程序。</span><span class="sxs-lookup"><span data-stu-id="5d674-113">Therefore, support for Group Call Pickup during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

<span data-ttu-id="5d674-114">在完成对备份池的故障转移过程后，必须将呼叫寄存通道表中的组内呼叫应答号范围重定向到备份池。</span><span class="sxs-lookup"><span data-stu-id="5d674-114">The Group Call Pickup number ranges in the call park orbit table must be redirected to the backup pool after the failover process to the backup pool is complete.</span></span> <span data-ttu-id="5d674-115">在将故障回复进程完成后，必须将号码范围重定向回主池。</span><span class="sxs-lookup"><span data-stu-id="5d674-115">The number ranges must be redirected back to the primary pool after the failback process to the primary pool is complete.</span></span> <span data-ttu-id="5d674-116">若要重定向组的呼叫装货范围，请使用**CsCallParkOrbit** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5d674-116">To redirect the Group Call Pickup ranges, use the **Set-CsCallParkOrbit** cmdlet.</span></span>

<span data-ttu-id="5d674-117">如果使用其他完全限定的域名（FQDN）部署新池以替换主池，则需要将与主池关联的所有组呼叫应答号码范围重新分配给新池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="5d674-117">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Group Call Pickup number ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="5d674-118">若要将号码范围重新分配给新池，您可以使用**CsCallParkOrbit** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5d674-118">To reassign number ranges to the new pool, you can use the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="5d674-119">有关**CsCallParkOrbit** cmdlet 的详细信息，请参阅[CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)。</span><span class="sxs-lookup"><span data-stu-id="5d674-119">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a><span data-ttu-id="5d674-120">池故障期间的组内呼叫装货体验</span><span class="sxs-lookup"><span data-stu-id="5d674-120">Group Call Pickup Experience During Pool Failure</span></span>

<span data-ttu-id="5d674-121">下表汇总了灾难恢复阶段的组呼叫装货体验。</span><span class="sxs-lookup"><span data-stu-id="5d674-121">The following table summarizes the Group Call Pickup experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="5d674-122">灾难恢复期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="5d674-122">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d674-123">呼叫状态</span><span class="sxs-lookup"><span data-stu-id="5d674-123">Call state</span></span></th>
<th><span data-ttu-id="5d674-124">故障转移到备份池</span><span class="sxs-lookup"><span data-stu-id="5d674-124">Failover to backup pool</span></span></th>
<th><span data-ttu-id="5d674-125">故障回复到主池</span><span class="sxs-lookup"><span data-stu-id="5d674-125">Failback to primary pool</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d674-126">新呼叫</span><span class="sxs-lookup"><span data-stu-id="5d674-126">New calls</span></span></p></td>
<td><p><span data-ttu-id="5d674-127"><strong>在故障转移过程中：</strong></span><span class="sxs-lookup"><span data-stu-id="5d674-127"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d674-128">用户处于恢复模式时，组呼叫应答不可用</span><span class="sxs-lookup"><span data-stu-id="5d674-128">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="5d674-129"><strong>故障转移完成后：</strong></span><span class="sxs-lookup"><span data-stu-id="5d674-129"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d674-130">用户离开弹性和组呼叫应答范围被重定向到备份池时可用的组内呼叫装货</span><span class="sxs-lookup"><span data-stu-id="5d674-130">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected to backup pool</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5d674-131"><strong>在故障回复过程中：</strong></span><span class="sxs-lookup"><span data-stu-id="5d674-131"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d674-132">用户处于恢复模式时，组呼叫应答不可用</span><span class="sxs-lookup"><span data-stu-id="5d674-132">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="5d674-133"><strong>故障回复完成后：</strong></span><span class="sxs-lookup"><span data-stu-id="5d674-133"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d674-134">当用户无法使用弹性和组呼叫应答号范围重定向回主池时，可以使用组内呼叫应答</span><span class="sxs-lookup"><span data-stu-id="5d674-134">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected back to primary pool</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d674-135">组内呼叫应答队列中的呼叫</span><span class="sxs-lookup"><span data-stu-id="5d674-135">Calls in Group Call Pickup queue</span></span></p></td>
<td><p><span data-ttu-id="5d674-136"><strong>在故障转移过程中：</strong></span><span class="sxs-lookup"><span data-stu-id="5d674-136"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d674-137">无法通过组呼叫应答应答队列中的呼叫。</span><span class="sxs-lookup"><span data-stu-id="5d674-137">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="5d674-138"><strong>故障转移完成后：</strong></span><span class="sxs-lookup"><span data-stu-id="5d674-138"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d674-139">处于此状态的呼叫</span><span class="sxs-lookup"><span data-stu-id="5d674-139">No calls in this state</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5d674-140"><strong>在故障回复过程中：</strong></span><span class="sxs-lookup"><span data-stu-id="5d674-140"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d674-141">无法通过组呼叫应答应答队列中的呼叫。</span><span class="sxs-lookup"><span data-stu-id="5d674-141">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="5d674-142"><strong>故障回复完成后：</strong></span><span class="sxs-lookup"><span data-stu-id="5d674-142"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d674-143">无法通过组呼叫应答应答队列中的呼叫。</span><span class="sxs-lookup"><span data-stu-id="5d674-143">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d674-144">已建立呼叫</span><span class="sxs-lookup"><span data-stu-id="5d674-144">Established call</span></span></p></td>
<td><p><span data-ttu-id="5d674-145"><strong>在故障转移过程中：</strong></span><span class="sxs-lookup"><span data-stu-id="5d674-145"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d674-146">呼叫保持连接</span><span class="sxs-lookup"><span data-stu-id="5d674-146">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="5d674-147"><strong>故障转移完成后：</strong></span><span class="sxs-lookup"><span data-stu-id="5d674-147"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d674-148">呼叫保持连接</span><span class="sxs-lookup"><span data-stu-id="5d674-148">Calls stay connected</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="5d674-149"><strong>在故障回复过程中：</strong></span><span class="sxs-lookup"><span data-stu-id="5d674-149"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d674-150">呼叫保持连接</span><span class="sxs-lookup"><span data-stu-id="5d674-150">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="5d674-151"><strong>故障回复完成后：</strong></span><span class="sxs-lookup"><span data-stu-id="5d674-151"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="5d674-152">呼叫保持连接</span><span class="sxs-lookup"><span data-stu-id="5d674-152">Calls stay connected</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

