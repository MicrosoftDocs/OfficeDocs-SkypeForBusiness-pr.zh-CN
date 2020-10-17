---
title: 池故障期间的 Lync Server 2013 响应组体验
description: 在池发生故障期间的 Lync Server 2013 响应组体验。
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
ms.openlocfilehash: 7d8d5904bc6934d4c330202bafa66d6dd8a16ff5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564568"
---
# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="8ee70-103">池故障期间 Lync Server 2013 中的响应组体验</span><span class="sxs-lookup"><span data-stu-id="8ee70-103">Response group experience in Lync Server 2013 during pool failure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ee70-104">_**上次修改的主题：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="8ee70-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="8ee70-105">本节详细描述了在以下各个阶段响应组活动如何受到影响：</span><span class="sxs-lookup"><span data-stu-id="8ee70-105">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="8ee70-106">主要池发生中断，但尚未启动故障转移。</span><span class="sxs-lookup"><span data-stu-id="8ee70-106">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="8ee70-107">服务故障转移到备份池。</span><span class="sxs-lookup"><span data-stu-id="8ee70-107">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="8ee70-108">服务故障回复到主要池。</span><span class="sxs-lookup"><span data-stu-id="8ee70-108">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="8ee70-109">发生中断时的用户体验</span><span class="sxs-lookup"><span data-stu-id="8ee70-109">User Experience When Outage Occurs</span></span>

<span data-ttu-id="8ee70-110">当池或网站发生中断，但管理员尚未启动故障转移时，按下表所述处理响应组活动。</span><span class="sxs-lookup"><span data-stu-id="8ee70-110">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ee70-p101">在灾难恢复期间，根据恢复期间主要池响应组是否已导入备份池，呼叫行为会有所不同。在下表中，对导入的响应组的引用意味着主要池响应组在灾难恢复模式期间已导入到该备份池。</span><span class="sxs-lookup"><span data-stu-id="8ee70-p101">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="8ee70-113">发生中断</span><span class="sxs-lookup"><span data-stu-id="8ee70-113">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ee70-114">呼叫或用户操作类型</span><span class="sxs-lookup"><span data-stu-id="8ee70-114">Type of call or user action</span></span></th>
<th><span data-ttu-id="8ee70-115">中断期间</span><span class="sxs-lookup"><span data-stu-id="8ee70-115">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ee70-116">连接到代理的呼叫</span><span class="sxs-lookup"><span data-stu-id="8ee70-116">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-117">常规呼叫保持连接。</span><span class="sxs-lookup"><span data-stu-id="8ee70-117">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-118">匿名呼叫将中断。</span><span class="sxs-lookup"><span data-stu-id="8ee70-118">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee70-119">正在进行但尚未连接到代理的呼叫</span><span class="sxs-lookup"><span data-stu-id="8ee70-119">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="8ee70-120">呼叫将中断。</span><span class="sxs-lookup"><span data-stu-id="8ee70-120">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee70-121">新呼叫</span><span class="sxs-lookup"><span data-stu-id="8ee70-121">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-122">呼叫将中断。</span><span class="sxs-lookup"><span data-stu-id="8ee70-122">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-123">如果已导入响应组，则呼叫将连接到备份池，但驻留在主要池中的代理将无法访问。</span><span class="sxs-lookup"><span data-stu-id="8ee70-123">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee70-124">代理代表响应组进行呼叫</span><span class="sxs-lookup"><span data-stu-id="8ee70-124">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="8ee70-125">此阶段功能被禁用。</span><span class="sxs-lookup"><span data-stu-id="8ee70-125">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee70-126">代理登录和代理信息</span><span class="sxs-lookup"><span data-stu-id="8ee70-126">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-127">可以在代理控制台上看到主要池拥有的代理组，但是代理无法登录。</span><span class="sxs-lookup"><span data-stu-id="8ee70-127">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-128">可以在代理控制台上看到备份池拥有的代理组，而且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="8ee70-128">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-129">代理控制台上未显示已导入的代理组。</span><span class="sxs-lookup"><span data-stu-id="8ee70-129">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee70-130">响应组配置</span><span class="sxs-lookup"><span data-stu-id="8ee70-130">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-131">根据主要池的后端数据库的可用性，可以查看由主要池拥有的响应组，但无法对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="8ee70-131">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-132">可以查看和修改备份池拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="8ee70-132">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-133">无法使用 Lync Server 控制面板或响应组配置工具查看导入的响应组，但可以使用 Lync Server 命令行管理程序 cmdlet 进行配置。</span><span class="sxs-lookup"><span data-stu-id="8ee70-133">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="8ee70-134">故障转移期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="8ee70-134">User Experience During Failover</span></span>

<span data-ttu-id="8ee70-p102">当管理员调用至备份池的故障转移时，将在故障转移期间和故障转移之后按下表中所述处理响应组活动。第一列介绍可能发生的活动的类型。中间一列介绍在故障转移到备份池的很短的时间内如何处理每个活动。最后一列介绍在故障转移期间及该过程完成后如何处理活动，备份池将驻留在主池中。</span><span class="sxs-lookup"><span data-stu-id="8ee70-p102">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table. The first column describes the type of activity that might be taking place. The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool. The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ee70-p103">在灾难恢复期间，根据恢复期间主要池响应组是否已导入备份池，呼叫行为会有所不同。在下表中，对导入的响应组的引用意味着主要池响应组在灾难恢复模式期间已导入到该备份池。</span><span class="sxs-lookup"><span data-stu-id="8ee70-p103">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="8ee70-141">启动故障转移</span><span class="sxs-lookup"><span data-stu-id="8ee70-141">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ee70-142">呼叫或用户操作类型</span><span class="sxs-lookup"><span data-stu-id="8ee70-142">Type of call or user action</span></span></th>
<th><span data-ttu-id="8ee70-143">故障转移期间</span><span class="sxs-lookup"><span data-stu-id="8ee70-143">During Failover</span></span></th>
<th><span data-ttu-id="8ee70-144">故障转移完成后</span><span class="sxs-lookup"><span data-stu-id="8ee70-144">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ee70-145">连接到代理的呼叫</span><span class="sxs-lookup"><span data-stu-id="8ee70-145">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-146">常规呼叫保持连接。</span><span class="sxs-lookup"><span data-stu-id="8ee70-146">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-147">匿名呼叫将中断。</span><span class="sxs-lookup"><span data-stu-id="8ee70-147">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-148">常规呼叫保持连接。</span><span class="sxs-lookup"><span data-stu-id="8ee70-148">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-149">对于已导入的响应组，已到达备份池的匿名呼叫保持连接状态。</span><span class="sxs-lookup"><span data-stu-id="8ee70-149">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee70-150">正在进行但尚未连接到代理的呼叫</span><span class="sxs-lookup"><span data-stu-id="8ee70-150">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="8ee70-151">呼叫将中断。</span><span class="sxs-lookup"><span data-stu-id="8ee70-151">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-152">如果未导入响应组，则没有任何呼叫处于此状态。</span><span class="sxs-lookup"><span data-stu-id="8ee70-152">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-153">对于已导入的响应组，已到达备份池的呼叫保持连接状态。</span><span class="sxs-lookup"><span data-stu-id="8ee70-153">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee70-154">新呼叫</span><span class="sxs-lookup"><span data-stu-id="8ee70-154">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-155">呼叫将中断。</span><span class="sxs-lookup"><span data-stu-id="8ee70-155">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-156">对于已导入的响应组，呼叫将连接到备份池，但驻留在主要池中的代理将无法访问。</span><span class="sxs-lookup"><span data-stu-id="8ee70-156">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-157">如果无法导入响应组，则将断开呼叫。</span><span class="sxs-lookup"><span data-stu-id="8ee70-157">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-158">对于已导入的响应组，呼叫将连接到备份池。</span><span class="sxs-lookup"><span data-stu-id="8ee70-158">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee70-159">代理代表响应组进行呼叫</span><span class="sxs-lookup"><span data-stu-id="8ee70-159">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="8ee70-160">此阶段功能被禁用。</span><span class="sxs-lookup"><span data-stu-id="8ee70-160">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-161">如果未导入响应组，则呼叫失败。</span><span class="sxs-lookup"><span data-stu-id="8ee70-161">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-162">对于已导入的响应组，呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="8ee70-162">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee70-163">代理登录和代理信息</span><span class="sxs-lookup"><span data-stu-id="8ee70-163">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-164">可以在代理控制台上看到主要池拥有的代理组，但是代理无法登录。</span><span class="sxs-lookup"><span data-stu-id="8ee70-164">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-165">可以在代理控制台上看到备份池拥有的代理组，而且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="8ee70-165">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-166">在代理控制台上显示已导入的代理组，而且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="8ee70-166">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-167">可以在代理控制台上看到主要池拥有的代理组，但是代理无法登录。</span><span class="sxs-lookup"><span data-stu-id="8ee70-167">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-168">可以在代理控制台上看到备份池拥有的代理组，而且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="8ee70-168">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-169">在代理控制台上显示已导入的代理组，而且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="8ee70-169">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee70-170">响应组配置</span><span class="sxs-lookup"><span data-stu-id="8ee70-170">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-171">根据主要池的后端数据库的可用性，可以查看由主要池拥有的响应组，但无法对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="8ee70-171">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-172">可以查看和修改备份池拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="8ee70-172">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-173">无法使用 Lync Server 控制面板或响应组配置工具查看导入的响应组，但可以使用 Lync Server 命令行管理程序 cmdlet 进行配置。</span><span class="sxs-lookup"><span data-stu-id="8ee70-173">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-174">根据后端数据库的可用性，可以查看由主要池拥有的响应组，但无法对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="8ee70-174">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-175">可以查看和修改备份池拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="8ee70-175">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-176">无法使用 Lync Server 控制面板或响应组配置工具查看导入的响应组，但可以使用 Lync Server 命令行管理程序 cmdlet 进行配置。</span><span class="sxs-lookup"><span data-stu-id="8ee70-176">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="8ee70-177">故障回复期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="8ee70-177">User Experience During Failback</span></span>

<span data-ttu-id="8ee70-178">在管理员对主要池调用故障回复时，按下表所述在故障回复期间以及故障回复之后对响应组活动进行处理。</span><span class="sxs-lookup"><span data-stu-id="8ee70-178">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ee70-p104">在灾难恢复期间，根据恢复期间主要池响应组是否已导入备份池，呼叫行为会有所不同。在下表中，对导入的响应组的引用意味着主要池响应组在灾难恢复模式期间已导入到该备份池。</span><span class="sxs-lookup"><span data-stu-id="8ee70-p104">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="8ee70-181">故障回复中的呼叫处理</span><span class="sxs-lookup"><span data-stu-id="8ee70-181">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ee70-182">呼叫或用户操作类型</span><span class="sxs-lookup"><span data-stu-id="8ee70-182">Type of call or user action</span></span></th>
<th><span data-ttu-id="8ee70-183">故障回复期间</span><span class="sxs-lookup"><span data-stu-id="8ee70-183">During Failback</span></span></th>
<th><span data-ttu-id="8ee70-184">故障回复完成后</span><span class="sxs-lookup"><span data-stu-id="8ee70-184">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ee70-185">连接到代理的呼叫</span><span class="sxs-lookup"><span data-stu-id="8ee70-185">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-186">常规呼叫保持连接。</span><span class="sxs-lookup"><span data-stu-id="8ee70-186">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-187">如果未导入响应组，则没有任何匿名呼叫处于此状态。</span><span class="sxs-lookup"><span data-stu-id="8ee70-187">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-188">对于已导入的响应组，匿名呼叫保持连接。</span><span class="sxs-lookup"><span data-stu-id="8ee70-188">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-189">常规呼叫保持连接。</span><span class="sxs-lookup"><span data-stu-id="8ee70-189">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-190">如果未导入响应组，则没有任何匿名呼叫处于此状态。</span><span class="sxs-lookup"><span data-stu-id="8ee70-190">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-191">对于已导入的响应组，匿名呼叫保持连接。</span><span class="sxs-lookup"><span data-stu-id="8ee70-191">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee70-192">正在进行但尚未连接到代理的呼叫</span><span class="sxs-lookup"><span data-stu-id="8ee70-192">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-193">如果未导入响应组，则没有任何呼叫处于此状态。</span><span class="sxs-lookup"><span data-stu-id="8ee70-193">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-194">对于已导入的响应组，呼叫将中断。</span><span class="sxs-lookup"><span data-stu-id="8ee70-194">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-195">如果未导入响应组，则没有任何呼叫处于此状态。</span><span class="sxs-lookup"><span data-stu-id="8ee70-195">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-196">对于已导入的响应组，呼叫将中断。</span><span class="sxs-lookup"><span data-stu-id="8ee70-196">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee70-197">新呼叫</span><span class="sxs-lookup"><span data-stu-id="8ee70-197">New calls</span></span></p></td>
<td><p><span data-ttu-id="8ee70-198">呼叫连接到主要池，但驻留在主要池中的代理将无法访问。</span><span class="sxs-lookup"><span data-stu-id="8ee70-198">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="8ee70-199">呼叫连接到主要池。</span><span class="sxs-lookup"><span data-stu-id="8ee70-199">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee70-200">代理代表响应组进行呼叫</span><span class="sxs-lookup"><span data-stu-id="8ee70-200">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="8ee70-201">此阶段功能被禁用。</span><span class="sxs-lookup"><span data-stu-id="8ee70-201">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="8ee70-202">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="8ee70-202">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ee70-203">代理登录和代理信息</span><span class="sxs-lookup"><span data-stu-id="8ee70-203">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-204">可以在代理控制台上看到主要池拥有的代理组，但是代理无法登录。</span><span class="sxs-lookup"><span data-stu-id="8ee70-204">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-205">可以在代理控制台上看到备份池拥有的代理组，而且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="8ee70-205">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-206">在代理控制台上显示已导入的代理组，而且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="8ee70-206">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-207">可以在代理控制台上看到主要池拥有的代理组，而且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="8ee70-207">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-208">可以在代理控制台上看到备份池拥有的代理组，而且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="8ee70-208">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-209">代理控制台上未显示已导入的代理组。</span><span class="sxs-lookup"><span data-stu-id="8ee70-209">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ee70-210">响应组配置</span><span class="sxs-lookup"><span data-stu-id="8ee70-210">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-211">根据主要池的后端数据库的可用性，可以查看由主要池拥有的响应组，但无法对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="8ee70-211">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-212">可以查看和修改备份池拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="8ee70-212">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-213">无法使用 Lync Server 控制面板或响应组配置工具查看导入的响应组，但可以使用 Lync Server 命令行管理程序 cmdlet 进行配置。</span><span class="sxs-lookup"><span data-stu-id="8ee70-213">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="8ee70-214">可以查看和修改主要池拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="8ee70-214">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-215">可以查看和修改备份池拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="8ee70-215">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="8ee70-216">无法使用 Lync Server 控制面板或响应组配置工具查看导入的响应组，但可以使用 Lync Server 命令行管理程序 cmdlet 进行配置。</span><span class="sxs-lookup"><span data-stu-id="8ee70-216">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

