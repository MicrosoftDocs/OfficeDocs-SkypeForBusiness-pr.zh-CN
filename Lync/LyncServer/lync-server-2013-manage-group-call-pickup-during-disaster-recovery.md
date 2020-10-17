---
title: Lync Server 2013：在灾难恢复过程中管理组呼叫装货
description: Lync Server 2013：在灾难恢复过程中管理组呼叫装货。
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
ms.openlocfilehash: 04d85bc83cfe35571c2b0f47f707c9dcd8037d80
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555278"
---
# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="2365a-103">在 Lync Server 2013 中管理灾难恢复期间的组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="2365a-103">Manage Group Call Pickup during disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2365a-104">_**上次修改的主题：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="2365a-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="2365a-105">当前端池因计划外事件而变为不可用时，服务将故障转移到备份池。</span><span class="sxs-lookup"><span data-stu-id="2365a-105">When a Front End pool becomes unavailable due an unplanned incident, service is failed over to the backup pool.</span></span> <span data-ttu-id="2365a-106">在故障转移到备份池的过程中，用户将被重定向到备份池并处于恢复模式。</span><span class="sxs-lookup"><span data-stu-id="2365a-106">During failover to the backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="2365a-107">在恢复模式下，用户不能选择其他用户的呼叫，也不能接听其他用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="2365a-107">While in resiliency mode, users cannot pick up other users' calls or have their calls picked up by other users.</span></span> <span data-ttu-id="2365a-108">故障转移完成后，用户可以像往常一样使用组呼叫应答。</span><span class="sxs-lookup"><span data-stu-id="2365a-108">When failover is complete, users can again use Group Call Pickup as usual.</span></span>

<span data-ttu-id="2365a-109">在故障回复到主池期间，用户会被重定向到主池，并再次处于恢复模式。</span><span class="sxs-lookup"><span data-stu-id="2365a-109">During failback to the primary pool, users are redirected to the primary pool and are again in resiliency mode.</span></span> <span data-ttu-id="2365a-110">在用户离开恢复模式之前，组呼叫应答功能将不可用。</span><span class="sxs-lookup"><span data-stu-id="2365a-110">Group Call Pickup functionality is not available until the users are out of resiliency mode.</span></span>

<span data-ttu-id="2365a-111">本节讨论灾难恢复过程中组呼叫选取的一些注意事项，同时还介绍了用户体验。</span><span class="sxs-lookup"><span data-stu-id="2365a-111">This section discusses some considerations for Group Call Pickup during disaster recovery and also describes the user experience.</span></span>

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a><span data-ttu-id="2365a-112">灾难恢复过程中组呼叫装货的注意事项</span><span class="sxs-lookup"><span data-stu-id="2365a-112">Considerations for Group Call Pickup During Disaster Recovery</span></span>

<span data-ttu-id="2365a-113">在灾难恢复过程中，作为故障转移过程的一部分被重定向到备份池的用户将使用在备份池中为呼叫应答组编号运行的呼叫寄存应用程序。</span><span class="sxs-lookup"><span data-stu-id="2365a-113">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application running in the backup pool for the call pickup group numbers.</span></span> <span data-ttu-id="2365a-114">因此，在灾难恢复过程中对组呼叫选取的支持要求在主池和备份池中部署和启用呼叫寄存应用程序。</span><span class="sxs-lookup"><span data-stu-id="2365a-114">Therefore, support for Group Call Pickup during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

<span data-ttu-id="2365a-115">在完成对备份池的故障转移过程后，必须将呼叫寄存通道表中的组内呼叫应答号范围重定向到备份池。</span><span class="sxs-lookup"><span data-stu-id="2365a-115">The Group Call Pickup number ranges in the call park orbit table must be redirected to the backup pool after the failover process to the backup pool is complete.</span></span> <span data-ttu-id="2365a-116">在将故障回复进程完成后，必须将号码范围重定向回主池。</span><span class="sxs-lookup"><span data-stu-id="2365a-116">The number ranges must be redirected back to the primary pool after the failback process to the primary pool is complete.</span></span> <span data-ttu-id="2365a-117">若要重定向组的呼叫装货范围，请使用 **CsCallParkOrbit** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2365a-117">To redirect the Group Call Pickup ranges, use the **Set-CsCallParkOrbit** cmdlet.</span></span>

<span data-ttu-id="2365a-118">如果使用其他完全限定的域名部署新池 (FQDN) 替换主池，则需要将与主池关联的所有组呼叫应答号码范围重新分配给新池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2365a-118">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Group Call Pickup number ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="2365a-119">若要将号码范围重新分配给新池，您可以使用 **CsCallParkOrbit** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2365a-119">To reassign number ranges to the new pool, you can use the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="2365a-120">有关 **CsCallParkOrbit** cmdlet 的详细信息，请参阅 [CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)。</span><span class="sxs-lookup"><span data-stu-id="2365a-120">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a><span data-ttu-id="2365a-121">池故障期间的组内呼叫装货体验</span><span class="sxs-lookup"><span data-stu-id="2365a-121">Group Call Pickup Experience During Pool Failure</span></span>

<span data-ttu-id="2365a-122">下表汇总了灾难恢复阶段的组呼叫装货体验。</span><span class="sxs-lookup"><span data-stu-id="2365a-122">The following table summarizes the Group Call Pickup experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="2365a-123">灾难恢复期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="2365a-123">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2365a-124">呼叫状态</span><span class="sxs-lookup"><span data-stu-id="2365a-124">Call state</span></span></th>
<th><span data-ttu-id="2365a-125">故障转移到备份池</span><span class="sxs-lookup"><span data-stu-id="2365a-125">Failover to backup pool</span></span></th>
<th><span data-ttu-id="2365a-126">故障回复到主池</span><span class="sxs-lookup"><span data-stu-id="2365a-126">Failback to primary pool</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2365a-127">新呼叫</span><span class="sxs-lookup"><span data-stu-id="2365a-127">New calls</span></span></p></td>
<td><p><span data-ttu-id="2365a-128"><strong>在故障转移过程中：</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-128"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2365a-129">用户处于恢复模式时，组呼叫应答不可用</span><span class="sxs-lookup"><span data-stu-id="2365a-129">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="2365a-130"><strong>故障转移完成后：</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-130"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2365a-131">用户离开弹性和组呼叫应答范围被重定向到备份池时可用的组内呼叫装货</span><span class="sxs-lookup"><span data-stu-id="2365a-131">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected to backup pool</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2365a-132"><strong>在故障回复过程中：</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-132"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2365a-133">用户处于恢复模式时，组呼叫应答不可用</span><span class="sxs-lookup"><span data-stu-id="2365a-133">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="2365a-134"><strong>故障回复完成后：</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-134"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2365a-135">当用户无法使用弹性和组呼叫应答号范围重定向回主池时，可以使用组内呼叫应答</span><span class="sxs-lookup"><span data-stu-id="2365a-135">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected back to primary pool</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2365a-136">组内呼叫应答队列中的呼叫</span><span class="sxs-lookup"><span data-stu-id="2365a-136">Calls in Group Call Pickup queue</span></span></p></td>
<td><p><span data-ttu-id="2365a-137"><strong>在故障转移过程中：</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-137"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2365a-138">无法通过组呼叫应答应答队列中的呼叫。</span><span class="sxs-lookup"><span data-stu-id="2365a-138">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="2365a-139"><strong>故障转移完成后：</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-139"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2365a-140">处于此状态的呼叫</span><span class="sxs-lookup"><span data-stu-id="2365a-140">No calls in this state</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2365a-141"><strong>在故障回复过程中：</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-141"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2365a-142">无法通过组呼叫应答应答队列中的呼叫。</span><span class="sxs-lookup"><span data-stu-id="2365a-142">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="2365a-143"><strong>故障回复完成后：</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-143"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2365a-144">无法通过组呼叫应答应答队列中的呼叫。</span><span class="sxs-lookup"><span data-stu-id="2365a-144">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2365a-145">已建立呼叫</span><span class="sxs-lookup"><span data-stu-id="2365a-145">Established call</span></span></p></td>
<td><p><span data-ttu-id="2365a-146"><strong>在故障转移过程中：</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-146"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2365a-147">呼叫保持连接</span><span class="sxs-lookup"><span data-stu-id="2365a-147">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="2365a-148"><strong>故障转移完成后：</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-148"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2365a-149">呼叫保持连接</span><span class="sxs-lookup"><span data-stu-id="2365a-149">Calls stay connected</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2365a-150"><strong>在故障回复过程中：</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-150"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2365a-151">呼叫保持连接</span><span class="sxs-lookup"><span data-stu-id="2365a-151">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="2365a-152"><strong>故障回复完成后：</strong></span><span class="sxs-lookup"><span data-stu-id="2365a-152"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="2365a-153">呼叫保持连接</span><span class="sxs-lookup"><span data-stu-id="2365a-153">Calls stay connected</span></span></p></li>
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

