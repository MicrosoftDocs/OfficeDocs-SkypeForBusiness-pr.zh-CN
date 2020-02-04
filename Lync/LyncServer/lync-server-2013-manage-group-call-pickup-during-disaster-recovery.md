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
ms.openlocfilehash: 45ebe93ebc1711f49d4578a2a5d908104ca2a411
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-group-call-pickup-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="d2ac4-102">在 Lync Server 2013 中的灾难恢复期间管理组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="d2ac4-102">Manage Group Call Pickup during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2ac4-103">_**主题上次修改时间：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="d2ac4-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="d2ac4-104">当前端池因计划外事件而变为不可用时，服务将故障转移到备份池。</span><span class="sxs-lookup"><span data-stu-id="d2ac4-104">When a Front End pool becomes unavailable due an unplanned incident, service is failed over to the backup pool.</span></span> <span data-ttu-id="d2ac4-105">在故障转移到备份池的过程中，用户将被重定向到备份池并处于复原模式。</span><span class="sxs-lookup"><span data-stu-id="d2ac4-105">During failover to the backup pool, users are redirected to the backup pool and are in resiliency mode.</span></span> <span data-ttu-id="d2ac4-106">在弹性模式下，用户无法获取其他用户的通话或让其他用户能够接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="d2ac4-106">While in resiliency mode, users cannot pick up other users' calls or have their calls picked up by other users.</span></span> <span data-ttu-id="d2ac4-107">故障转移完成后，用户可以再次使用群组呼叫分拣。</span><span class="sxs-lookup"><span data-stu-id="d2ac4-107">When failover is complete, users can again use Group Call Pickup as usual.</span></span>

<span data-ttu-id="d2ac4-108">在回切到主池期间，用户将被重定向到主池，并再次进入恢复模式。</span><span class="sxs-lookup"><span data-stu-id="d2ac4-108">During failback to the primary pool, users are redirected to the primary pool and are again in resiliency mode.</span></span> <span data-ttu-id="d2ac4-109">只有在用户退出恢复模式后，组呼叫分拣功能才可用。</span><span class="sxs-lookup"><span data-stu-id="d2ac4-109">Group Call Pickup functionality is not available until the users are out of resiliency mode.</span></span>

<span data-ttu-id="d2ac4-110">本部分讨论了在灾难恢复过程中进行组呼叫拾取的一些注意事项，还介绍了用户体验。</span><span class="sxs-lookup"><span data-stu-id="d2ac4-110">This section discusses some considerations for Group Call Pickup during disaster recovery and also describes the user experience.</span></span>

<div>

## <a name="considerations-for-group-call-pickup-during-disaster-recovery"></a><span data-ttu-id="d2ac4-111">灾难恢复期间组呼叫装货的注意事项</span><span class="sxs-lookup"><span data-stu-id="d2ac4-111">Considerations for Group Call Pickup During Disaster Recovery</span></span>

<span data-ttu-id="d2ac4-112">在灾难恢复过程中，已被重定向到备份池的用户作为故障转移过程的一部分，使用在备份池中为呼叫装货组编号运行的调用寄存应用程序。</span><span class="sxs-lookup"><span data-stu-id="d2ac4-112">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park application running in the backup pool for the call pickup group numbers.</span></span> <span data-ttu-id="d2ac4-113">因此，在灾难恢复过程中对组呼叫拾取的支持要求在主池和备份池中部署和启用呼叫驻留应用程序。</span><span class="sxs-lookup"><span data-stu-id="d2ac4-113">Therefore, support for Group Call Pickup during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

<span data-ttu-id="d2ac4-114">在备份池完成故障转移过程后，必须将 "呼叫驻留" 轨道表中的组呼叫装货号码范围重定向到备份池。</span><span class="sxs-lookup"><span data-stu-id="d2ac4-114">The Group Call Pickup number ranges in the call park orbit table must be redirected to the backup pool after the failover process to the backup pool is complete.</span></span> <span data-ttu-id="d2ac4-115">在故障恢复过程完成后，必须将数字范围重定向到主池。</span><span class="sxs-lookup"><span data-stu-id="d2ac4-115">The number ranges must be redirected back to the primary pool after the failback process to the primary pool is complete.</span></span> <span data-ttu-id="d2ac4-116">若要重定向组呼叫的装货范围，请使用**CsCallParkOrbit** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d2ac4-116">To redirect the Group Call Pickup ranges, use the **Set-CsCallParkOrbit** cmdlet.</span></span>

<span data-ttu-id="d2ac4-117">如果你部署具有不同完全限定的域名（FQDN）的新池来替换主池，你需要将与主池关联的所有组呼叫装货号码范围重新分配给新池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d2ac4-117">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Group Call Pickup number ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="d2ac4-118">若要将号码范围重新分配给新池，你可以使用**CsCallParkOrbit** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d2ac4-118">To reassign number ranges to the new pool, you can use the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="d2ac4-119">有关**CsCallParkOrbit** cmdlet 的详细信息，请参阅[set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)。</span><span class="sxs-lookup"><span data-stu-id="d2ac4-119">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

<div>

## <a name="group-call-pickup-experience-during-pool-failure"></a><span data-ttu-id="d2ac4-120">池故障期间的组呼叫装货体验</span><span class="sxs-lookup"><span data-stu-id="d2ac4-120">Group Call Pickup Experience During Pool Failure</span></span>

<span data-ttu-id="d2ac4-121">下表总结了组通过灾难恢复阶段的装货体验。</span><span class="sxs-lookup"><span data-stu-id="d2ac4-121">The following table summarizes the Group Call Pickup experience through the phases of disaster recovery.</span></span>

### <a name="user-experience-during-disaster-recovery"></a><span data-ttu-id="d2ac4-122">灾难恢复期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="d2ac4-122">User Experience During Disaster Recovery</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2ac4-123">通话状态</span><span class="sxs-lookup"><span data-stu-id="d2ac4-123">Call state</span></span></th>
<th><span data-ttu-id="d2ac4-124">故障转移到备份池</span><span class="sxs-lookup"><span data-stu-id="d2ac4-124">Failover to backup pool</span></span></th>
<th><span data-ttu-id="d2ac4-125">回切到主池</span><span class="sxs-lookup"><span data-stu-id="d2ac4-125">Failback to primary pool</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2ac4-126">新通话</span><span class="sxs-lookup"><span data-stu-id="d2ac4-126">New calls</span></span></p></td>
<td><p><span data-ttu-id="d2ac4-127"><strong>在故障转移过程中：</strong></span><span class="sxs-lookup"><span data-stu-id="d2ac4-127"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="d2ac4-128">用户在复原模式下无法使用组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="d2ac4-128">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="d2ac4-129"><strong>故障切换完成后：</strong></span><span class="sxs-lookup"><span data-stu-id="d2ac4-129"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="d2ac4-130">当用户退出弹性和组呼叫装货号码范围被重定向到备份池时，可以使用组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="d2ac4-130">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected to backup pool</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d2ac4-131"><strong>在故障回复过程中：</strong></span><span class="sxs-lookup"><span data-stu-id="d2ac4-131"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="d2ac4-132">用户在复原模式下无法使用组呼叫装货</span><span class="sxs-lookup"><span data-stu-id="d2ac4-132">Group Call Pickup not available for users in resiliency mode</span></span></p></li>
</ul>
<p><span data-ttu-id="d2ac4-133"><strong>故障回复完成后：</strong></span><span class="sxs-lookup"><span data-stu-id="d2ac4-133"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="d2ac4-134">当用户退出弹性和组呼叫时，组呼叫的装货号码范围将被重定向到主池</span><span class="sxs-lookup"><span data-stu-id="d2ac4-134">Group Call Pickup available when users out of resiliency and Group Call Pickup number ranges are redirected back to primary pool</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2ac4-135">组呼叫装货队列中的呼叫</span><span class="sxs-lookup"><span data-stu-id="d2ac4-135">Calls in Group Call Pickup queue</span></span></p></td>
<td><p><span data-ttu-id="d2ac4-136"><strong>在故障转移过程中：</strong></span><span class="sxs-lookup"><span data-stu-id="d2ac4-136"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="d2ac4-137">无法通过组呼叫提货应答队列中的通话。</span><span class="sxs-lookup"><span data-stu-id="d2ac4-137">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="d2ac4-138"><strong>故障切换完成后：</strong></span><span class="sxs-lookup"><span data-stu-id="d2ac4-138"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="d2ac4-139">此状态下没有通话</span><span class="sxs-lookup"><span data-stu-id="d2ac4-139">No calls in this state</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d2ac4-140"><strong>在故障回复过程中：</strong></span><span class="sxs-lookup"><span data-stu-id="d2ac4-140"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="d2ac4-141">无法通过组呼叫提货应答队列中的通话。</span><span class="sxs-lookup"><span data-stu-id="d2ac4-141">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul>
<p><span data-ttu-id="d2ac4-142"><strong>故障回复完成后：</strong></span><span class="sxs-lookup"><span data-stu-id="d2ac4-142"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="d2ac4-143">无法通过组呼叫提货应答队列中的通话。</span><span class="sxs-lookup"><span data-stu-id="d2ac4-143">Calls in queue cannot be answered through Group Call Pickup.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2ac4-144">已建立通话</span><span class="sxs-lookup"><span data-stu-id="d2ac4-144">Established call</span></span></p></td>
<td><p><span data-ttu-id="d2ac4-145"><strong>在故障转移过程中：</strong></span><span class="sxs-lookup"><span data-stu-id="d2ac4-145"><strong>During failover process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="d2ac4-146">通话保持连接</span><span class="sxs-lookup"><span data-stu-id="d2ac4-146">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="d2ac4-147"><strong>故障切换完成后：</strong></span><span class="sxs-lookup"><span data-stu-id="d2ac4-147"><strong>After failover is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="d2ac4-148">通话保持连接</span><span class="sxs-lookup"><span data-stu-id="d2ac4-148">Calls stay connected</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d2ac4-149"><strong>在故障回复过程中：</strong></span><span class="sxs-lookup"><span data-stu-id="d2ac4-149"><strong>During failback process:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="d2ac4-150">通话保持连接</span><span class="sxs-lookup"><span data-stu-id="d2ac4-150">Calls stay connected</span></span></p></li>
</ul>
<p><span data-ttu-id="d2ac4-151"><strong>故障回复完成后：</strong></span><span class="sxs-lookup"><span data-stu-id="d2ac4-151"><strong>After failback is complete:</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="d2ac4-152">通话保持连接</span><span class="sxs-lookup"><span data-stu-id="d2ac4-152">Calls stay connected</span></span></p></li>
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

