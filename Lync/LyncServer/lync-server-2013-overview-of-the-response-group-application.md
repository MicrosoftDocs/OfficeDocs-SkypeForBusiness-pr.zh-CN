---
title: Lync Server 2013：响应组应用程序概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 007d6b21ab37aee16ae8c98b202bd3900f4dab45
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a><span data-ttu-id="d9c2e-102">Lync Server 2013 中的响应组应用程序概述</span><span class="sxs-lookup"><span data-stu-id="d9c2e-102">Overview of the Response Group application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9c2e-103">_**上次修改的主题：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="d9c2e-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="d9c2e-104">当呼叫者呼叫响应组时，呼叫会基于智能寻线或呼叫者对互动语音响应 (IVR) 问题的回答路由至代理。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-104">When a caller calls a response group, the call is routed to an agent based on a hunt group or the caller's answers to interactive voice response (IVR) questions.</span></span> <span data-ttu-id="d9c2e-105">响应组应用程序使用标准响应组路由方法将呼叫路由到下一个可用的代理。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-105">The Response Group application uses standard response group routing methods to route the call to the next available agent.</span></span> <span data-ttu-id="d9c2e-106">呼叫路由方法包括串行、最长闲置、并行、循环以及助理路由（即每次传入呼叫时都将同时呼叫所有代理，无论其当前状态如何）。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-106">Call routing methods include serial, longest-idle, parallel, round robin, and Attendant routing (that is, all agents are called at the same time for every incoming call, regardless of their current presence).</span></span> <span data-ttu-id="d9c2e-107">如果没有可用的代理，呼叫将保留在一个队列中，直到代理可用为止。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-107">If no agents are available, the call is held in a queue until an agent is available.</span></span> <span data-ttu-id="d9c2e-108">在队列中时，呼叫者将听到音乐，直到可用代理接受呼叫为止。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-108">While in the queue, the caller hears music until an available agent accepts the call.</span></span> <span data-ttu-id="d9c2e-109">如果队列已满，或者呼叫在队列中已超时，则呼叫者可能会听到一则消息，然后呼叫将断开连接或转接到其他目标。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-109">If the queue is full, or if the call times out while in the queue, the caller might hear a message and then is either disconnected or transferred to a different destination.</span></span> <span data-ttu-id="d9c2e-110">当代理接受呼叫时，呼叫者可能会（也可能不会）看到代理的身份，具体取决于管理员如何配置响应组。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-110">When an agent accepts the call, the caller might or might not be able to see the agent's identity, depending on how the administrator configures the response group.</span></span> <span data-ttu-id="d9c2e-111">代理可以是正式的，这意味着他们必须登录到组，然后才能接受路由至该组的呼叫；也可以是非正式的，这意味着他们无需登录到组，在组外即可接受呼叫。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-111">Agents can either be formal, which means that they must sign in to the group before they can accept calls routed to the group, or informal, which means that they do not sign into and out of the group to accept calls.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d9c2e-p102">只有内部部署用户可以成为代理。如果代理从内部部署移动到联机状态，则不会将响应组呼叫路由到该代理。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-p102">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d9c2e-114">响应组应用程序使用名为 Match 的内部服务对呼叫进行排队并查找可用代理。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-114">The Response Group application uses an internal service, called Match Making, to queue calls and find available agents.</span></span> <span data-ttu-id="d9c2e-115">每台运行响应组应用程序的计算机都会运行 Match service，但一次只能有一个匹配的每个 Lync Server 池处于活动状态-其他计算机是被动的。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-115">Each computer that runs the Response Group application runs the Match Making service, but only one Match Making service per Lync Server pool is active at a time--the others are passive.</span></span> <span data-ttu-id="d9c2e-116">如果在计划外中断期间，活动 Match Making 服务变得不可用，则某一个非活动 Match Making 服务将变成活动状态。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-116">If the active Match Making service becomes unavailable during an unplanned outage, one of the passive Match Making services becomes active.</span></span> <span data-ttu-id="d9c2e-117">响应组应用程序将尽力确保呼叫路由和排队继续不中断。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-117">The Response Group application does its best to make sure that call routing and queuing continues uninterrupted.</span></span> <span data-ttu-id="d9c2e-118">但是，当转换 Match Making 服务时，会丢失此时正在传输的所有呼叫。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-118">However, when a Match Making service transition occurs, any calls that are in transfer at the time are lost.</span></span> <span data-ttu-id="d9c2e-119">例如，如果由于前端服务器停机而导致转换，则当前正在处理的活动匹配的所有呼叫都将失去该前端服务器上的服务。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-119">For example, if the transition is due to the Front End Server going down, any calls currently being handled by the active Match Making service on that Front End Server are also lost.</span></span>



</div>

<span data-ttu-id="d9c2e-120">在 Lync Server 2013 中，有两个管理角色可用于管理响应组：响应组管理器和响应组管理员。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-120">In Lync Server 2013, two management roles are available for managing response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="d9c2e-121">响应组管理员可以管理任何响应组的任何方面。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-121">Response Group Administrators can manage any aspect of any response group.</span></span> <span data-ttu-id="d9c2e-122">响应组管理员只能管理某些方面，并且只能管理它们所拥有的响应组。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-122">Response Group Managers can manage only certain aspects, and only for the response groups that they own.</span></span> <span data-ttu-id="d9c2e-123">新的管理员角色有助于降低管理成本，因为您可以将特定响应组的有限责任委派给已启用企业语音的任何用户。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-123">The new Manager role can help reduce administration costs, because you can delegate limited responsibilities for specific response groups to any user who is enabled for Enterprise Voice.</span></span>

<span data-ttu-id="d9c2e-124">为了适应新的经理角色，Lync Server 2013 响应组应用程序引入了托管或非托管的**工作流类型**。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-124">To accommodate the new Manager role, Lync Server 2013 Response Group application introduces a **Workflow Type** of Managed or Unmanaged.</span></span> <span data-ttu-id="d9c2e-125">下表介绍了托管响应组和非托管响应组。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-125">The following table describes Managed and Unmanaged response groups.</span></span>

### <a name="managed-and-unmanaged-response-groups"></a><span data-ttu-id="d9c2e-126">托管响应组和非托管响应组</span><span class="sxs-lookup"><span data-stu-id="d9c2e-126">Managed and Unmanaged Response Groups</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9c2e-127">响应组类型</span><span class="sxs-lookup"><span data-stu-id="d9c2e-127">Response group type</span></span></th>
<th><span data-ttu-id="d9c2e-128">说明</span><span class="sxs-lookup"><span data-stu-id="d9c2e-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d9c2e-129">受</span><span class="sxs-lookup"><span data-stu-id="d9c2e-129">Unmanaged</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d9c2e-130">非托管响应组未分配有 Manager。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-130">Unmanaged response groups have no assigned Managers.</span></span> <span data-ttu-id="d9c2e-131">只有响应组管理员可以配置这些响应组。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-131">Only the Response Group Administrator can configure these response groups.</span></span></p></li>
<li><p><span data-ttu-id="d9c2e-132">多个非托管响应组可共享一个队列或代理组。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-132">Multiple unmanaged response groups can share a queue or agent group.</span></span></p></li>
<li><p><span data-ttu-id="d9c2e-133">当您将响应组从以前的版本迁移到 Lync Server 2013 时，该类型将设置为 "非托管"。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-133">When you migrate response groups from a prior version to Lync Server 2013, the type is set to Unmanaged.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d9c2e-134">托管</span><span class="sxs-lookup"><span data-stu-id="d9c2e-134">Managed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d9c2e-135">响应组管理员可以配置托管响应组的任何方面。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-135">Response Group Administrators can configure any aspect of managed response groups.</span></span></p></li>
<li><p><span data-ttu-id="d9c2e-136">响应组管理者无法查看或修改未显式分配给它们的响应组。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-136">Response Group Managers cannot view or modify response groups that are not explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="d9c2e-137">响应组管理员可以仅为显式分配给它们的响应组配置部分设置。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-137">Response Group Managers can configure only some settings for the response groups that are explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="d9c2e-138">托管响应组无法与任何其他响应组（托管或非托管）共享任何队列或代理组。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-138">Managed response groups can't share any queues or agent groups with any other response group, managed or unmanaged.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d9c2e-139">下表介绍了响应组管理器可为分配给它们的响应组执行和不能执行的操作。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-139">The following table describes the actions that Response Group Managers can and cannot perform for the response groups assigned to them.</span></span>

### <a name="response-group-manager-capabilities"></a><span data-ttu-id="d9c2e-140">响应组 Manager 功能</span><span class="sxs-lookup"><span data-stu-id="d9c2e-140">Response Group Manager Capabilities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d9c2e-141">可以配置：</span><span class="sxs-lookup"><span data-stu-id="d9c2e-141">Can configure:</span></span></th>
<th><span data-ttu-id="d9c2e-142">可以创建、删除或配置：</span><span class="sxs-lookup"><span data-stu-id="d9c2e-142">Can create, delete, or configure:</span></span></th>
<th><span data-ttu-id="d9c2e-143">无法</span><span class="sxs-lookup"><span data-stu-id="d9c2e-143">Cannot:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="d9c2e-144">Agent</span><span class="sxs-lookup"><span data-stu-id="d9c2e-144">Agents</span></span></p></li>
<li><p><span data-ttu-id="d9c2e-145">欢迎消息</span><span class="sxs-lookup"><span data-stu-id="d9c2e-145">Welcome message</span></span></p></li>
<li><p><span data-ttu-id="d9c2e-146">响应组名称</span><span class="sxs-lookup"><span data-stu-id="d9c2e-146">Response Group name</span></span></p></li>
<li><p><span data-ttu-id="d9c2e-147">说明</span><span class="sxs-lookup"><span data-stu-id="d9c2e-147">Description</span></span></p></li>
<li><p><span data-ttu-id="d9c2e-148">显示号码</span><span class="sxs-lookup"><span data-stu-id="d9c2e-148">Display number</span></span></p></li>
<li><p><span data-ttu-id="d9c2e-149">工作时间</span><span class="sxs-lookup"><span data-stu-id="d9c2e-149">Business hours</span></span></p></li>
<li><p><span data-ttu-id="d9c2e-150">保持音乐</span><span class="sxs-lookup"><span data-stu-id="d9c2e-150">Music on hold</span></span></p></li>
<li><p><span data-ttu-id="d9c2e-151">状态（活动/非活动）</span><span class="sxs-lookup"><span data-stu-id="d9c2e-151">Status (active/inactive)</span></span></p></li>
<li><p><span data-ttu-id="d9c2e-152">智能寻线工作流和互动语音响应 (IVR) 工作流</span><span class="sxs-lookup"><span data-stu-id="d9c2e-152">Hunt group workflows or Interactive voice response (IVR) workflows</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="d9c2e-153">代理组</span><span class="sxs-lookup"><span data-stu-id="d9c2e-153">Agent Groups</span></span></p></li>
<li><p><span data-ttu-id="d9c2e-154">队列</span><span class="sxs-lookup"><span data-stu-id="d9c2e-154">Queues</span></span></p></li>
<li><p><span data-ttu-id="d9c2e-155">假日集</span><span class="sxs-lookup"><span data-stu-id="d9c2e-155">Holiday sets</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="d9c2e-156">创建或删除任意类型的工作流</span><span class="sxs-lookup"><span data-stu-id="d9c2e-156">Create or delete any type of workflow</span></span></p></li>
<li><p><span data-ttu-id="d9c2e-157">修改核心响应组设置，如：“SIP URI”<strong></strong>、“电话号码”<strong></strong>或“工作流类型”<strong></strong>。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-157">Modify core response group settings, such as: <strong>SIP URI</strong>, <strong>Telephone Number</strong>, or <strong>Workflow Type</strong>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d9c2e-158">响应组管理员可以使用以下工具管理其指定的响应组。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-158">Response Group Managers can use the following tools to manage their designated response groups.</span></span>

  - <span data-ttu-id="d9c2e-159">Lync 服务器控制面板</span><span class="sxs-lookup"><span data-stu-id="d9c2e-159">Lync Server Control Panel</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d9c2e-160">响应组管理员只能使用此工具来管理响应组设置。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-160">Response Group Managers can only manage Response Group settings with this tool.</span></span> <span data-ttu-id="d9c2e-161">其他 Lync Server 设置对管理者不可用。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-161">Other Lync Server settings are not available to Managers.</span></span>

    
    </div>

  - <span data-ttu-id="d9c2e-162">响应组配置工具</span><span class="sxs-lookup"><span data-stu-id="d9c2e-162">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="d9c2e-163">Lync Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="d9c2e-163">Lync Server Management Shell</span></span>

<span data-ttu-id="d9c2e-164">响应组可以很好地扩展到部门或工作组环境（有关详细信息，请参阅[Lync Server 2013 中的响应组容量规划](lync-server-2013-capacity-planning-for-response-group.md)），并且可以在全新的电话安装中部署。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-164">Response Group scales well to departmental or workgroup environments (for details, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) and can be deployed in entirely new telephony installations.</span></span> <span data-ttu-id="d9c2e-165">它支持来自企业语音部署和本地运营商网络的传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-165">It supports incoming calls from the Enterprise Voice deployment and from the local carrier network.</span></span> <span data-ttu-id="d9c2e-166">代理可以使用 Lync 2013、Lync 2010、Lync 2010 助理或 Lync Phone Edition 将呼叫路由到它们。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-166">Agents can use Lync 2013, Lync 2010, Lync 2010 Attendant, or Lync Phone Edition to take the calls routed to them.</span></span>

<span data-ttu-id="d9c2e-167">响应组应用程序是企业语音的一个组件。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-167">The Response Group application is a component of Enterprise Voice.</span></span> <span data-ttu-id="d9c2e-168">部署企业语音时，会自动安装并激活响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="d9c2e-168">When you deploy Enterprise Voice, the Response Group application is installed and activated automatically.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

