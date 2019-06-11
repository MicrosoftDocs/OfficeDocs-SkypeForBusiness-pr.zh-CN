---
title: 池故障期间的 Lync Server 2013 响应组体验
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90911bebc7c3e60847f5b3fcb8f69523697af0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="08dd8-102">池故障期间 Lync Server 2013 中的响应组体验</span><span class="sxs-lookup"><span data-stu-id="08dd8-102">Response group experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08dd8-103">_**主题上次修改时间:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="08dd8-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="08dd8-104">本部分详细介绍了如何在以下阶段影响响应组活动:</span><span class="sxs-lookup"><span data-stu-id="08dd8-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="08dd8-105">主池出现中断, 但尚未启动故障转移。</span><span class="sxs-lookup"><span data-stu-id="08dd8-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="08dd8-106">服务已故障转移到备份池。</span><span class="sxs-lookup"><span data-stu-id="08dd8-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="08dd8-107">服务故障回复到主池。</span><span class="sxs-lookup"><span data-stu-id="08dd8-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="08dd8-108">出现停机时的用户体验</span><span class="sxs-lookup"><span data-stu-id="08dd8-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="08dd8-109">当池或网站发生停机, 但管理员尚未启动故障转移时, 将按下表中所述处理响应组活动。</span><span class="sxs-lookup"><span data-stu-id="08dd8-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="08dd8-110">在灾难恢复期间, 取决于在恢复期间是否将主池响应组导入到备份池中, 调用的行为有所不同。</span><span class="sxs-lookup"><span data-stu-id="08dd8-110">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="08dd8-111">在下表中, 对导入的响应组的引用意味着在灾难恢复模式中将主要池响应组导入到备份池中。</span><span class="sxs-lookup"><span data-stu-id="08dd8-111">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="08dd8-112">发生中断</span><span class="sxs-lookup"><span data-stu-id="08dd8-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08dd8-113">呼叫或用户操作的类型</span><span class="sxs-lookup"><span data-stu-id="08dd8-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="08dd8-114">停机期间</span><span class="sxs-lookup"><span data-stu-id="08dd8-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08dd8-115">连接到代理的通话</span><span class="sxs-lookup"><span data-stu-id="08dd8-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-116">定期通话仍保持连接状态。</span><span class="sxs-lookup"><span data-stu-id="08dd8-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-117">匿名通话已断开连接。</span><span class="sxs-lookup"><span data-stu-id="08dd8-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08dd8-118">尚未连接到代理的正在进行的通话</span><span class="sxs-lookup"><span data-stu-id="08dd8-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="08dd8-119">通话断开。</span><span class="sxs-lookup"><span data-stu-id="08dd8-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08dd8-120">新通话</span><span class="sxs-lookup"><span data-stu-id="08dd8-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-121">通话断开。</span><span class="sxs-lookup"><span data-stu-id="08dd8-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-122">如果已导入响应组, 则呼叫将连接到备份池, 但无法访问托管在主池中的代理。</span><span class="sxs-lookup"><span data-stu-id="08dd8-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08dd8-123">代理代表响应组呼叫</span><span class="sxs-lookup"><span data-stu-id="08dd8-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="08dd8-124">在此阶段中禁用功能。</span><span class="sxs-lookup"><span data-stu-id="08dd8-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08dd8-125">代理登录和代理信息</span><span class="sxs-lookup"><span data-stu-id="08dd8-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-126">主池拥有的代理组可以在代理控制台上查看, 但代理无法登录。</span><span class="sxs-lookup"><span data-stu-id="08dd8-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-127">可以在代理控制台上查看备份池所拥有的代理组, 并且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="08dd8-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-128">代理控制台上不显示导入的代理组。</span><span class="sxs-lookup"><span data-stu-id="08dd8-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08dd8-129">响应组配置</span><span class="sxs-lookup"><span data-stu-id="08dd8-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-130">可以查看由主池拥有的响应组, 具体取决于主池的后端数据库的可用性, 但不能进行修改。</span><span class="sxs-lookup"><span data-stu-id="08dd8-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-131">可以查看和修改备份池拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="08dd8-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-132">无法使用 Lync Server 控制面板或响应组配置工具查看导入的响应组, 但可以使用 Lync Server Management Shell cmdlet 进行配置。</span><span class="sxs-lookup"><span data-stu-id="08dd8-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="08dd8-133">故障转移期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="08dd8-133">User Experience During Failover</span></span>

<span data-ttu-id="08dd8-134">当管理员将故障转移调用到备份池时, 将在故障转移期间和之后处理响应组活动, 如下表所述。</span><span class="sxs-lookup"><span data-stu-id="08dd8-134">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table.</span></span> <span data-ttu-id="08dd8-135">第一列描述可能发生的活动类型。</span><span class="sxs-lookup"><span data-stu-id="08dd8-135">The first column describes the type of activity that might be taking place.</span></span> <span data-ttu-id="08dd8-136">中间列描述了如何在短时间内处理每个活动, 以故障转移到备份池。</span><span class="sxs-lookup"><span data-stu-id="08dd8-136">The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool.</span></span> <span data-ttu-id="08dd8-137">最后一列介绍在故障转移过程完成并且为主池准备了备份池后, 在持续时间内活动的处理方式。</span><span class="sxs-lookup"><span data-stu-id="08dd8-137">The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="08dd8-138">在灾难恢复期间, 取决于在恢复期间是否将主池响应组导入到备份池中, 调用的行为有所不同。</span><span class="sxs-lookup"><span data-stu-id="08dd8-138">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="08dd8-139">在下表中, 对导入的响应组的引用意味着在灾难恢复模式中将主要池响应组导入到备份池中。</span><span class="sxs-lookup"><span data-stu-id="08dd8-139">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="08dd8-140">已启动故障转移</span><span class="sxs-lookup"><span data-stu-id="08dd8-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08dd8-141">呼叫或用户操作的类型</span><span class="sxs-lookup"><span data-stu-id="08dd8-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="08dd8-142">故障转移期间</span><span class="sxs-lookup"><span data-stu-id="08dd8-142">During Failover</span></span></th>
<th><span data-ttu-id="08dd8-143">故障转移完成后</span><span class="sxs-lookup"><span data-stu-id="08dd8-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08dd8-144">连接到代理的通话</span><span class="sxs-lookup"><span data-stu-id="08dd8-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-145">定期通话仍保持连接状态。</span><span class="sxs-lookup"><span data-stu-id="08dd8-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-146">匿名通话已断开连接。</span><span class="sxs-lookup"><span data-stu-id="08dd8-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-147">定期通话仍保持连接状态。</span><span class="sxs-lookup"><span data-stu-id="08dd8-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-148">对于导入的响应组, 已达到备份池的匿名呼叫仍保持连接。</span><span class="sxs-lookup"><span data-stu-id="08dd8-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08dd8-149">尚未连接到代理的正在进行的通话</span><span class="sxs-lookup"><span data-stu-id="08dd8-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="08dd8-150">通话断开。</span><span class="sxs-lookup"><span data-stu-id="08dd8-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-151">如果未导入响应组, 则没有通话处于此状态。</span><span class="sxs-lookup"><span data-stu-id="08dd8-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-152">对于导入的响应组, 已达到备份池的呼叫仍保持连接。</span><span class="sxs-lookup"><span data-stu-id="08dd8-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08dd8-153">新通话</span><span class="sxs-lookup"><span data-stu-id="08dd8-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-154">通话断开。</span><span class="sxs-lookup"><span data-stu-id="08dd8-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-155">对于导入的响应组, 呼叫将连接到备份池, 但无法访问主池中托管的代理。</span><span class="sxs-lookup"><span data-stu-id="08dd8-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-156">如果未导入响应组, 则通话将断开连接。</span><span class="sxs-lookup"><span data-stu-id="08dd8-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-157">对于导入的响应组, 呼叫将连接到备份池。</span><span class="sxs-lookup"><span data-stu-id="08dd8-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08dd8-158">代理代表响应组呼叫</span><span class="sxs-lookup"><span data-stu-id="08dd8-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="08dd8-159">在此阶段中禁用功能</span><span class="sxs-lookup"><span data-stu-id="08dd8-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-160">如果未导入响应组, 呼叫将失败。</span><span class="sxs-lookup"><span data-stu-id="08dd8-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-161">对于导入的响应组, 通话成功。</span><span class="sxs-lookup"><span data-stu-id="08dd8-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08dd8-162">代理登录和代理信息</span><span class="sxs-lookup"><span data-stu-id="08dd8-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-163">主池拥有的代理组可以在代理控制台上查看, 但代理无法登录。</span><span class="sxs-lookup"><span data-stu-id="08dd8-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-164">可以在代理控制台上查看备份池所拥有的代理组, 并且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="08dd8-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-165">已导入的代理组将显示在代理控制台上, 并且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="08dd8-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-166">主池拥有的代理组可以在代理控制台上查看, 但代理无法登录。</span><span class="sxs-lookup"><span data-stu-id="08dd8-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-167">可以在代理控制台上查看备份池所拥有的代理组, 并且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="08dd8-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-168">已导入的代理组将显示在代理控制台上, 并且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="08dd8-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08dd8-169">响应组配置</span><span class="sxs-lookup"><span data-stu-id="08dd8-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-170">可以查看由主池拥有的响应组, 具体取决于主池的后端数据库的可用性, 但不能进行修改。</span><span class="sxs-lookup"><span data-stu-id="08dd8-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-171">可以查看和修改备份池拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="08dd8-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-172">无法使用 Lync Server 控制面板或响应组配置工具查看导入的响应组, 但可以使用 Lync Server Management Shell cmdlet 进行配置。</span><span class="sxs-lookup"><span data-stu-id="08dd8-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-173">可以查看由主池拥有的响应组, 具体取决于后端数据库的可用性, 但不能进行修改。</span><span class="sxs-lookup"><span data-stu-id="08dd8-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-174">可以查看和修改备份池拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="08dd8-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-175">无法使用 Lync Server 控制面板或响应组配置工具查看导入的响应组, 但可以使用 Lync Server Management Shell cmdlet 进行配置。</span><span class="sxs-lookup"><span data-stu-id="08dd8-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="08dd8-176">故障回复期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="08dd8-176">User Experience During Failback</span></span>

<span data-ttu-id="08dd8-177">当管理员将故障回复调用到主池时, 将在故障回复期间和之后处理响应组活动, 如下表所述。</span><span class="sxs-lookup"><span data-stu-id="08dd8-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="08dd8-178">在灾难恢复期间, 取决于在恢复期间是否将主池响应组导入到备份池中, 调用的行为有所不同。</span><span class="sxs-lookup"><span data-stu-id="08dd8-178">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="08dd8-179">在下表中, 对导入的响应组的引用意味着在灾难恢复模式中将主要池响应组导入到备份池中。</span><span class="sxs-lookup"><span data-stu-id="08dd8-179">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="08dd8-180">故障回复中的呼叫处理</span><span class="sxs-lookup"><span data-stu-id="08dd8-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08dd8-181">呼叫或用户操作的类型</span><span class="sxs-lookup"><span data-stu-id="08dd8-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="08dd8-182">在故障回复期间</span><span class="sxs-lookup"><span data-stu-id="08dd8-182">During Failback</span></span></th>
<th><span data-ttu-id="08dd8-183">故障回复完成后</span><span class="sxs-lookup"><span data-stu-id="08dd8-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08dd8-184">连接到代理的通话</span><span class="sxs-lookup"><span data-stu-id="08dd8-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-185">定期通话仍保持连接状态。</span><span class="sxs-lookup"><span data-stu-id="08dd8-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-186">如果未导入响应组, 则没有任何匿名通话处于此状态。</span><span class="sxs-lookup"><span data-stu-id="08dd8-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-187">对于导入的响应组, 匿名通话仍保持连接。</span><span class="sxs-lookup"><span data-stu-id="08dd8-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-188">定期通话仍保持连接状态。</span><span class="sxs-lookup"><span data-stu-id="08dd8-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-189">如果未导入响应组, 则没有任何匿名通话处于此状态。</span><span class="sxs-lookup"><span data-stu-id="08dd8-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-190">对于导入的响应组, 匿名通话仍保持连接。</span><span class="sxs-lookup"><span data-stu-id="08dd8-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08dd8-191">尚未连接到代理的正在进行的通话</span><span class="sxs-lookup"><span data-stu-id="08dd8-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-192">如果未导入响应组, 则没有通话处于此状态。</span><span class="sxs-lookup"><span data-stu-id="08dd8-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-193">对于导入的响应组, 呼叫将断开连接。</span><span class="sxs-lookup"><span data-stu-id="08dd8-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-194">如果未导入响应组, 则没有通话处于此状态。</span><span class="sxs-lookup"><span data-stu-id="08dd8-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-195">对于导入的响应组, 呼叫将断开连接。</span><span class="sxs-lookup"><span data-stu-id="08dd8-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08dd8-196">新通话</span><span class="sxs-lookup"><span data-stu-id="08dd8-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="08dd8-197">呼叫连接到主池, 但驻留在主池中的代理不可访问。</span><span class="sxs-lookup"><span data-stu-id="08dd8-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="08dd8-198">呼叫将连接到主池。</span><span class="sxs-lookup"><span data-stu-id="08dd8-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08dd8-199">代理代表响应组呼叫</span><span class="sxs-lookup"><span data-stu-id="08dd8-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="08dd8-200">在此阶段中禁用功能。</span><span class="sxs-lookup"><span data-stu-id="08dd8-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="08dd8-201">通话成功。</span><span class="sxs-lookup"><span data-stu-id="08dd8-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08dd8-202">代理登录和代理信息</span><span class="sxs-lookup"><span data-stu-id="08dd8-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-203">主池拥有的代理组可以在代理控制台上查看, 但代理无法登录。</span><span class="sxs-lookup"><span data-stu-id="08dd8-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-204">可以在代理控制台上查看备份池所拥有的代理组, 并且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="08dd8-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-205">已导入的代理组将显示在代理控制台上, 并且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="08dd8-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-206">可以在代理控制台上查看主池拥有的代理组, 并且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="08dd8-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-207">可以在代理控制台上查看备份池所拥有的代理组, 并且代理可以登录。</span><span class="sxs-lookup"><span data-stu-id="08dd8-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-208">代理控制台上不显示导入的代理组。</span><span class="sxs-lookup"><span data-stu-id="08dd8-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08dd8-209">响应组配置</span><span class="sxs-lookup"><span data-stu-id="08dd8-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-210">可以查看由主池拥有的响应组, 具体取决于主池的后端数据库的可用性, 但不能进行修改。</span><span class="sxs-lookup"><span data-stu-id="08dd8-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-211">可以查看和修改备份池拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="08dd8-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-212">无法使用 Lync Server 控制面板或响应组配置工具查看导入的响应组, 但可以使用 Lync Server Management Shell cmdlet 进行配置。</span><span class="sxs-lookup"><span data-stu-id="08dd8-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="08dd8-213">可以查看和修改主池拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="08dd8-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-214">可以查看和修改备份池拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="08dd8-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="08dd8-215">无法使用 Lync Server 控制面板或响应组配置工具查看导入的响应组, 但可以使用 Lync Server Management Shell cmdlet 进行配置。</span><span class="sxs-lookup"><span data-stu-id="08dd8-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

