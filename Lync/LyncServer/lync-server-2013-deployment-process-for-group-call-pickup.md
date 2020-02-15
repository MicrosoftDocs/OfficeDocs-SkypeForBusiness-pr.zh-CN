---
title: Lync Server 2013：组间呼叫应答的部署过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20f583b330812eab8ea32ecd3c545445b0640fae
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="33431-102">Lync Server 2013 中组呼叫应答的部署过程</span><span class="sxs-lookup"><span data-stu-id="33431-102">Deployment process for Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33431-103">_**上次修改的主题：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="33431-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="33431-104">本节概述了部署组内呼叫应答涉及的步骤。</span><span class="sxs-lookup"><span data-stu-id="33431-104">This section provides an overview of the steps involved in deploying Group Call Pickup.</span></span> <span data-ttu-id="33431-105">在配置组呼叫应答之前，必须使用 Enterprise Voice 部署 Enterprise Edition 或 Standard Edition。</span><span class="sxs-lookup"><span data-stu-id="33431-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Group Call Pickup.</span></span> <span data-ttu-id="33431-106">当您部署企业语音时，会安装并启用组呼叫应答所需的组件。</span><span class="sxs-lookup"><span data-stu-id="33431-106">The components required by Group Call Pickup are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="group-call-pickup-deployment-process"></a><span data-ttu-id="33431-107">组呼叫应答部署过程</span><span class="sxs-lookup"><span data-stu-id="33431-107">Group Call Pickup Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33431-108">阶段</span><span class="sxs-lookup"><span data-stu-id="33431-108">Phase</span></span></th>
<th><span data-ttu-id="33431-109">步骤</span><span class="sxs-lookup"><span data-stu-id="33431-109">Steps</span></span></th>
<th><span data-ttu-id="33431-110">所需的组和角色</span><span class="sxs-lookup"><span data-stu-id="33431-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="33431-111">部署文档</span><span class="sxs-lookup"><span data-stu-id="33431-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33431-112">在拓扑中启用 SEFAUtil 资源工具包工具</span><span class="sxs-lookup"><span data-stu-id="33431-112">Enable the SEFAUtil resource kit tool in the topology</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="33431-113">使用<strong>CsTrustedApplicationPool</strong> cmdlet 可以创建新的受信任应用程序池。</span><span class="sxs-lookup"><span data-stu-id="33431-113">Use the <strong>New-CsTrustedApplicationPool</strong> cmdlet to create a new trusted application pool.</span></span></p></li>
<li><p><span data-ttu-id="33431-114">使用<strong>CsTrustedApplication</strong> cmdlet 可将 SEFAUtil 工具指定为受信任的应用程序。</span><span class="sxs-lookup"><span data-stu-id="33431-114">Use the <strong>New-CsTrustedApplication</strong> cmdlet to specify the SEFAUtil tool as trusted application.</span></span></p></li>
<li><p><span data-ttu-id="33431-115">运行<strong>enable-cstopology</strong> cmdlet 以启用拓扑。</span><span class="sxs-lookup"><span data-stu-id="33431-115">Run the <strong>Enable-CsTopology</strong> cmdlet to enable the topology.</span></span></p></li>
<li><p><span data-ttu-id="33431-116">在第1步中创建的受信任应用程序池中的前端服务器上安装资源工具包工具。</span><span class="sxs-lookup"><span data-stu-id="33431-116">Install the resource kit tools on a Front End Server that is in the trusted application pool created in step 1.</span></span></p></li>
<li><p><span data-ttu-id="33431-117">运行此程序以验证 SEFAUtil 是否正常运行，以在部署中显示用户的呼叫转接设置。</span><span class="sxs-lookup"><span data-stu-id="33431-117">Verify that SEFAUtil is running correctly by running it to display the call forwarding settings of a user in the deployment.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="33431-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="33431-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="33431-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">在 Lync Server 2013 中部署 SEFAUtil 工具</a></span><span class="sxs-lookup"><span data-stu-id="33431-119"><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33431-120">在呼叫寄存通道表中配置呼叫装货号码范围</span><span class="sxs-lookup"><span data-stu-id="33431-120">Configure call pickup number ranges in the call park orbit table</span></span></p></td>
<td><p><span data-ttu-id="33431-121">使用<strong>CSCallParkOrbit</strong> cmdlet 可以在呼叫寄存通道表中创建呼叫应答号码范围，并将呼叫装货范围分配给 GroupPickup 类型。</span><span class="sxs-lookup"><span data-stu-id="33431-121">Use the <strong>New-CSCallParkOrbit</strong> cmdlet to create call pickup number ranges in the call park orbit table and assign the call pickup ranges the type GroupPickup.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="33431-122">必须使用 Lync Server 命令行管理程序在呼叫寄存通道表中创建、修改、删除和查看组内呼叫应答号码范围。</span><span class="sxs-lookup"><span data-stu-id="33431-122">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="33431-123">组内呼叫应答号码范围在 Lync Server 控制面板中不可用。</span><span class="sxs-lookup"><span data-stu-id="33431-123">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="33431-124">对于与现有拨号计划的无缝集成，号码范围通常配置为虚拟扩展块。</span><span class="sxs-lookup"><span data-stu-id="33431-124">For seamless integration with existing dial plans, number ranges are typically configured as a block of virtual extensions.</span></span> <span data-ttu-id="33431-125">不支持将直接向内拨号（已为）号码分配给呼叫寄存通道表中的区域号码。</span><span class="sxs-lookup"><span data-stu-id="33431-125">Assigning Direct Inward Dialing (DID) numbers as range numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="33431-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="33431-126">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="33431-127">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="33431-127">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="33431-128">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="33431-128">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="33431-129">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="33431-129">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="33431-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">在 Lync Server 2013 中配置呼叫应答组号码</a></span><span class="sxs-lookup"><span data-stu-id="33431-130"><a href="lync-server-2013-configure-call-pickup-group-numbers.md">Configure call pickup group numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33431-131">为用户分配呼叫装货号码，并为用户启用组呼叫应答</span><span class="sxs-lookup"><span data-stu-id="33431-131">Assign a call pickup number to users, and enable Group Call Pickup for the users</span></span></p></td>
<td><p><span data-ttu-id="33431-132">使用 SEFAUtil 资源工具包工具中的/enablegrouppickup 参数可启用组呼叫应答，并为用户分配呼叫应答号码。</span><span class="sxs-lookup"><span data-stu-id="33431-132">Use the /enablegrouppickup parameter in the SEFAUtil resource kit tool to enable Group Call Pickup and assign a call pickup number for users.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="33431-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">为 Lync Server 2013 中的用户启用组内呼叫应答并分配组号码</a></span><span class="sxs-lookup"><span data-stu-id="33431-133"><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33431-134">通知用户分配的呼叫应答号码和任何其他感兴趣的号码</span><span class="sxs-lookup"><span data-stu-id="33431-134">Notify users of their assigned call pickup number and any other number of interest</span></span></p></td>
<td><p><span data-ttu-id="33431-135">由于任何用户都可以检索对组呼叫应答用户的呼叫，因此用户可能需要监视多个组。</span><span class="sxs-lookup"><span data-stu-id="33431-135">Because any user can retrieve a call made to a Group Call Pickup user, users may want to monitor more than one group.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="33431-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">在 Lync Server 2013 中向用户传达组呼叫装货分配</a></span><span class="sxs-lookup"><span data-stu-id="33431-136"><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">Communicate Group Call Pickup assignments to users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33431-137">验证你的组呼叫装货部署</span><span class="sxs-lookup"><span data-stu-id="33431-137">Verify your Group Call Pickup deployment</span></span></p></td>
<td><p><span data-ttu-id="33431-138">测试发出和检索呼叫以确保配置按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="33431-138">Test placing and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="33431-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">Optional在 Lync Server 2013 中验证组内的 "呼叫装货" 部署</a></span><span class="sxs-lookup"><span data-stu-id="33431-139"><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

