---
title: 池故障期间的 Lync Server 2013 响应组体验
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d3977d05c0916cc23f628c0af26be1cbc8a79990
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="ca58c-102">池故障期间 Lync Server 2013 中的响应组体验</span><span class="sxs-lookup"><span data-stu-id="ca58c-102">Response group experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca58c-103">_**上次修改的主题：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="ca58c-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="ca58c-104">本节详细描述了在以下各个阶段响应组活动如何受到影响：</span><span class="sxs-lookup"><span data-stu-id="ca58c-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="ca58c-105">主要池发生中断，但尚未启动故障转移。</span><span class="sxs-lookup"><span data-stu-id="ca58c-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="ca58c-106">服务故障转移到备份池。</span><span class="sxs-lookup"><span data-stu-id="ca58c-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="ca58c-107">服务故障回复到主要池。</span><span class="sxs-lookup"><span data-stu-id="ca58c-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="ca58c-108">发生中断时的用户体验</span><span class="sxs-lookup"><span data-stu-id="ca58c-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="ca58c-109">当池或网站发生中断，但管理员尚未启动故障转移时，按下表所述处理响应组活动。</span><span class="sxs-lookup"><span data-stu-id="ca58c-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ca58c-p101">在灾难恢复期间，根据恢复期间主要池响应组是否已导入备份池，呼叫行为会有所不同。在下表中，对导入的响应组的引用意味着主要池响应组在灾难恢复模式期间已导入到该备份池。</span><span class="sxs-lookup"><span data-stu-id="ca58c-p101">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="ca58c-112">发生中断</span><span class="sxs-lookup"><span data-stu-id="ca58c-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca58c-113">呼叫或用户操作类型</span><span class="sxs-lookup"><span data-stu-id="ca58c-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="ca58c-114">中断期间</span><span class="sxs-lookup"><span data-stu-id="ca58c-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca58c-115">连接到代理的呼叫</span><span class="sxs-lookup"><span data-stu-id="ca58c-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-116">常规呼叫保持连接。</span><span class="sxs-lookup"><span data-stu-id="ca58c-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-117">匿名呼叫将中断。</span><span class="sxs-lookup"><span data-stu-id="ca58c-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca58c-118">正在进行但尚未连接到代理的呼叫</span><span class="sxs-lookup"><span data-stu-id="ca58c-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="ca58c-119">呼叫将中断。</span><span class="sxs-lookup"><span data-stu-id="ca58c-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca58c-120">新呼叫</span><span class="sxs-lookup"><span data-stu-id="ca58c-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-121">呼叫将中断。</span><span class="sxs-lookup"><span data-stu-id="ca58c-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-122">如果已导入响应组，则呼叫将连接到备份池，但驻留在主要池中的代理将无法访问。</span><span class="sxs-lookup"><span data-stu-id="ca58c-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca58c-123">代理代表响应组进行呼叫</span><span class="sxs-lookup"><span data-stu-id="ca58c-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="ca58c-124">此阶段功能被禁用。</span><span class="sxs-lookup"><span data-stu-id="ca58c-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca58c-125">代理登录和代理信息</span><span class="sxs-lookup"><span data-stu-id="ca58c-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-126">可以在代理控制台上看到主要池拥有的代理组，但是代理无法登录。</span><span class="sxs-lookup"><span data-stu-id="ca58c-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-127">可以在代理控制台上看到备份池拥有的代理组，而且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="ca58c-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-128">代理控制台上未显示已导入的代理组。</span><span class="sxs-lookup"><span data-stu-id="ca58c-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca58c-129">响应组配置</span><span class="sxs-lookup"><span data-stu-id="ca58c-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-130">根据主要池的后端数据库的可用性，可以查看由主要池拥有的响应组，但无法对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="ca58c-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-131">可以查看和修改备份池拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="ca58c-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-132">无法使用 Lync Server 控制面板或响应组配置工具查看导入的响应组，但可以使用 Lync Server 命令行管理程序 cmdlet 进行配置。</span><span class="sxs-lookup"><span data-stu-id="ca58c-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="ca58c-133">故障转移期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="ca58c-133">User Experience During Failover</span></span>

<span data-ttu-id="ca58c-p102">当管理员调用至备份池的故障转移时，将在故障转移期间和故障转移之后按下表中所述处理响应组活动。第一列介绍可能发生的活动的类型。中间一列介绍在故障转移到备份池的很短的时间内如何处理每个活动。最后一列介绍在故障转移期间及该过程完成后如何处理活动，备份池将驻留在主池中。</span><span class="sxs-lookup"><span data-stu-id="ca58c-p102">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table. The first column describes the type of activity that might be taking place. The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool. The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ca58c-p103">在灾难恢复期间，根据恢复期间主要池响应组是否已导入备份池，呼叫行为会有所不同。在下表中，对导入的响应组的引用意味着主要池响应组在灾难恢复模式期间已导入到该备份池。</span><span class="sxs-lookup"><span data-stu-id="ca58c-p103">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="ca58c-140">启动故障转移</span><span class="sxs-lookup"><span data-stu-id="ca58c-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca58c-141">呼叫或用户操作类型</span><span class="sxs-lookup"><span data-stu-id="ca58c-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="ca58c-142">故障转移期间</span><span class="sxs-lookup"><span data-stu-id="ca58c-142">During Failover</span></span></th>
<th><span data-ttu-id="ca58c-143">故障转移完成后</span><span class="sxs-lookup"><span data-stu-id="ca58c-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca58c-144">连接到代理的呼叫</span><span class="sxs-lookup"><span data-stu-id="ca58c-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-145">常规呼叫保持连接。</span><span class="sxs-lookup"><span data-stu-id="ca58c-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-146">匿名呼叫将中断。</span><span class="sxs-lookup"><span data-stu-id="ca58c-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-147">常规呼叫保持连接。</span><span class="sxs-lookup"><span data-stu-id="ca58c-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-148">对于已导入的响应组，已到达备份池的匿名呼叫保持连接状态。</span><span class="sxs-lookup"><span data-stu-id="ca58c-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca58c-149">正在进行但尚未连接到代理的呼叫</span><span class="sxs-lookup"><span data-stu-id="ca58c-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="ca58c-150">呼叫将中断。</span><span class="sxs-lookup"><span data-stu-id="ca58c-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-151">如果未导入响应组，则没有任何呼叫处于此状态。</span><span class="sxs-lookup"><span data-stu-id="ca58c-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-152">对于已导入的响应组，已到达备份池的呼叫保持连接状态。</span><span class="sxs-lookup"><span data-stu-id="ca58c-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca58c-153">新呼叫</span><span class="sxs-lookup"><span data-stu-id="ca58c-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-154">呼叫将中断。</span><span class="sxs-lookup"><span data-stu-id="ca58c-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-155">对于已导入的响应组，呼叫将连接到备份池，但驻留在主要池中的代理将无法访问。</span><span class="sxs-lookup"><span data-stu-id="ca58c-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-156">如果无法导入响应组，则将断开呼叫。</span><span class="sxs-lookup"><span data-stu-id="ca58c-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-157">对于已导入的响应组，呼叫将连接到备份池。</span><span class="sxs-lookup"><span data-stu-id="ca58c-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca58c-158">代理代表响应组进行呼叫</span><span class="sxs-lookup"><span data-stu-id="ca58c-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="ca58c-159">此阶段功能被禁用。</span><span class="sxs-lookup"><span data-stu-id="ca58c-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-160">如果未导入响应组，则呼叫失败。</span><span class="sxs-lookup"><span data-stu-id="ca58c-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-161">对于已导入的响应组，呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="ca58c-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca58c-162">代理登录和代理信息</span><span class="sxs-lookup"><span data-stu-id="ca58c-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-163">可以在代理控制台上看到主要池拥有的代理组，但是代理无法登录。</span><span class="sxs-lookup"><span data-stu-id="ca58c-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-164">可以在代理控制台上看到备份池拥有的代理组，而且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="ca58c-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-165">在代理控制台上显示已导入的代理组，而且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="ca58c-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-166">可以在代理控制台上看到主要池拥有的代理组，但是代理无法登录。</span><span class="sxs-lookup"><span data-stu-id="ca58c-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-167">可以在代理控制台上看到备份池拥有的代理组，而且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="ca58c-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-168">在代理控制台上显示已导入的代理组，而且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="ca58c-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca58c-169">响应组配置</span><span class="sxs-lookup"><span data-stu-id="ca58c-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-170">根据主要池的后端数据库的可用性，可以查看由主要池拥有的响应组，但无法对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="ca58c-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-171">可以查看和修改备份池拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="ca58c-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-172">无法使用 Lync Server 控制面板或响应组配置工具查看导入的响应组，但可以使用 Lync Server 命令行管理程序 cmdlet 进行配置。</span><span class="sxs-lookup"><span data-stu-id="ca58c-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-173">根据后端数据库的可用性，可以查看由主要池拥有的响应组，但无法对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="ca58c-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-174">可以查看和修改备份池拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="ca58c-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-175">无法使用 Lync Server 控制面板或响应组配置工具查看导入的响应组，但可以使用 Lync Server 命令行管理程序 cmdlet 进行配置。</span><span class="sxs-lookup"><span data-stu-id="ca58c-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="ca58c-176">故障回复期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="ca58c-176">User Experience During Failback</span></span>

<span data-ttu-id="ca58c-177">在管理员对主要池调用故障回复时，按下表所述在故障回复期间以及故障回复之后对响应组活动进行处理。</span><span class="sxs-lookup"><span data-stu-id="ca58c-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ca58c-p104">在灾难恢复期间，根据恢复期间主要池响应组是否已导入备份池，呼叫行为会有所不同。在下表中，对导入的响应组的引用意味着主要池响应组在灾难恢复模式期间已导入到该备份池。</span><span class="sxs-lookup"><span data-stu-id="ca58c-p104">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="ca58c-180">故障回复中的呼叫处理</span><span class="sxs-lookup"><span data-stu-id="ca58c-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca58c-181">呼叫或用户操作类型</span><span class="sxs-lookup"><span data-stu-id="ca58c-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="ca58c-182">故障回复期间</span><span class="sxs-lookup"><span data-stu-id="ca58c-182">During Failback</span></span></th>
<th><span data-ttu-id="ca58c-183">故障回复完成后</span><span class="sxs-lookup"><span data-stu-id="ca58c-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca58c-184">连接到代理的呼叫</span><span class="sxs-lookup"><span data-stu-id="ca58c-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-185">常规呼叫保持连接。</span><span class="sxs-lookup"><span data-stu-id="ca58c-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-186">如果未导入响应组，则没有任何匿名呼叫处于此状态。</span><span class="sxs-lookup"><span data-stu-id="ca58c-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-187">对于已导入的响应组，匿名呼叫保持连接。</span><span class="sxs-lookup"><span data-stu-id="ca58c-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-188">常规呼叫保持连接。</span><span class="sxs-lookup"><span data-stu-id="ca58c-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-189">如果未导入响应组，则没有任何匿名呼叫处于此状态。</span><span class="sxs-lookup"><span data-stu-id="ca58c-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-190">对于已导入的响应组，匿名呼叫保持连接。</span><span class="sxs-lookup"><span data-stu-id="ca58c-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca58c-191">正在进行但尚未连接到代理的呼叫</span><span class="sxs-lookup"><span data-stu-id="ca58c-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-192">如果未导入响应组，则没有任何呼叫处于此状态。</span><span class="sxs-lookup"><span data-stu-id="ca58c-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-193">对于已导入的响应组，呼叫将中断。</span><span class="sxs-lookup"><span data-stu-id="ca58c-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-194">如果未导入响应组，则没有任何呼叫处于此状态。</span><span class="sxs-lookup"><span data-stu-id="ca58c-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-195">对于已导入的响应组，呼叫将中断。</span><span class="sxs-lookup"><span data-stu-id="ca58c-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca58c-196">新呼叫</span><span class="sxs-lookup"><span data-stu-id="ca58c-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="ca58c-197">呼叫连接到主要池，但驻留在主要池中的代理将无法访问。</span><span class="sxs-lookup"><span data-stu-id="ca58c-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="ca58c-198">呼叫连接到主要池。</span><span class="sxs-lookup"><span data-stu-id="ca58c-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca58c-199">代理代表响应组进行呼叫</span><span class="sxs-lookup"><span data-stu-id="ca58c-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="ca58c-200">此阶段功能被禁用。</span><span class="sxs-lookup"><span data-stu-id="ca58c-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="ca58c-201">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="ca58c-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca58c-202">代理登录和代理信息</span><span class="sxs-lookup"><span data-stu-id="ca58c-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-203">可以在代理控制台上看到主要池拥有的代理组，但是代理无法登录。</span><span class="sxs-lookup"><span data-stu-id="ca58c-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-204">可以在代理控制台上看到备份池拥有的代理组，而且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="ca58c-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-205">在代理控制台上显示已导入的代理组，而且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="ca58c-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-206">可以在代理控制台上看到主要池拥有的代理组，而且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="ca58c-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-207">可以在代理控制台上看到备份池拥有的代理组，而且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="ca58c-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-208">代理控制台上未显示已导入的代理组。</span><span class="sxs-lookup"><span data-stu-id="ca58c-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca58c-209">响应组配置</span><span class="sxs-lookup"><span data-stu-id="ca58c-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-210">根据主要池的后端数据库的可用性，可以查看由主要池拥有的响应组，但无法对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="ca58c-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-211">可以查看和修改备份池拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="ca58c-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-212">无法使用 Lync Server 控制面板或响应组配置工具查看导入的响应组，但可以使用 Lync Server 命令行管理程序 cmdlet 进行配置。</span><span class="sxs-lookup"><span data-stu-id="ca58c-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="ca58c-213">可以查看和修改主要池拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="ca58c-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-214">可以查看和修改备份池拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="ca58c-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="ca58c-215">无法使用 Lync Server 控制面板或响应组配置工具查看导入的响应组，但可以使用 Lync Server 命令行管理程序 cmdlet 进行配置。</span><span class="sxs-lookup"><span data-stu-id="ca58c-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

