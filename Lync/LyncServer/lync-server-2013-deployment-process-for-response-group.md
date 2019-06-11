---
title: 'Lync Server 2013: 响应组的部署过程'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2151532b31f3c1660be98d11ac9d9c337ffecb64
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a><span data-ttu-id="bdd4d-102">Lync Server 2013 中的 "响应" 组的部署过程</span><span class="sxs-lookup"><span data-stu-id="bdd4d-102">Deployment process for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdd4d-103">_**主题上次修改时间:** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="bdd4d-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="bdd4d-104">本部分概述了部署响应组应用程序时所涉及的阶段和步骤。</span><span class="sxs-lookup"><span data-stu-id="bdd4d-104">This section provides an overview of the phases and steps involved in deploying the Response Group application.</span></span>

### <a name="response-group-deployment-process"></a><span data-ttu-id="bdd4d-105">响应组部署过程</span><span class="sxs-lookup"><span data-stu-id="bdd4d-105">Response Group Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bdd4d-106">阶段</span><span class="sxs-lookup"><span data-stu-id="bdd4d-106">Phase</span></span></th>
<th><span data-ttu-id="bdd4d-107">步骤</span><span class="sxs-lookup"><span data-stu-id="bdd4d-107">Steps</span></span></th>
<th><span data-ttu-id="bdd4d-108">权限</span><span class="sxs-lookup"><span data-stu-id="bdd4d-108">Permissions</span></span></th>
<th><span data-ttu-id="bdd4d-109">部署文档</span><span class="sxs-lookup"><span data-stu-id="bdd4d-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bdd4d-110">安装响应组应用程序</span><span class="sxs-lookup"><span data-stu-id="bdd4d-110">Install the Response Group application</span></span></p></td>
<td><p><span data-ttu-id="bdd4d-111">部署企业语音时, 将默认安装并激活 "响应组" 应用程序。</span><span class="sxs-lookup"><span data-stu-id="bdd4d-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="bdd4d-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="bdd4d-112">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="bdd4d-113"><a href="lync-server-2013-deploying-enterprise-voice.md">在 Lync Server 2013 中部署企业语音</a></span><span class="sxs-lookup"><span data-stu-id="bdd4d-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd4d-114">为响应组安装组件</span><span class="sxs-lookup"><span data-stu-id="bdd4d-114">Install components for Response Group</span></span></p></td>
<td><p><span data-ttu-id="bdd4d-115">Lync Server cmdlet、Lync Server 控制面板、响应组配置工具、代理的登录和注销控制台, 以及响应组客户端 Web 服务作为 Web 服务的一部分进行安装。</span><span class="sxs-lookup"><span data-stu-id="bdd4d-115">Lync Server cmdlets, the Lync Server Control Panel, Response Group Configuration Tool, agents' sign-in and sign-out console, and Response Group Client Web service are installed as part of Web Services.</span></span> <span data-ttu-id="bdd4d-116">在部署企业版池或标准版服务器时, 将安装 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="bdd4d-116">Web Services is installed when you deploy an Enterprise Edition pool or a Standard Edition server.</span></span></p></td>
<td><p><span data-ttu-id="bdd4d-117">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="bdd4d-117">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="bdd4d-118"><a href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="bdd4d-118"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd4d-119">为 Lync 2013 和企业语音启用用户</span><span class="sxs-lookup"><span data-stu-id="bdd4d-119">Enable users for Lync 2013 and for Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="bdd4d-120">启用将用作 Lync Server 和企业语音的代理的用户。</span><span class="sxs-lookup"><span data-stu-id="bdd4d-120">Enable users who will be agents for Lync Server and Enterprise Voice.</span></span> <span data-ttu-id="bdd4d-121">必须先启用用户，然后才能将其添加到代理组。</span><span class="sxs-lookup"><span data-stu-id="bdd4d-121">Users must be enabled before you can add them to agent groups.</span></span> <span data-ttu-id="bdd4d-122">通常, 在企业版或标准版服务器部署期间启用 Lync Server 的用户。</span><span class="sxs-lookup"><span data-stu-id="bdd4d-122">Typically, users are enabled for Lync Server during the Enterprise Edition or Standard Edition server deployment.</span></span> <span data-ttu-id="bdd4d-123">在企业语音部署期间, 用户可用于企业语音。</span><span class="sxs-lookup"><span data-stu-id="bdd4d-123">Users are enabled for Enterprise Voice during the Enterprise Voice deployment.</span></span></p></td>
<td><p><span data-ttu-id="bdd4d-124">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="bdd4d-124">RTCUniversalUserAdmins</span></span></p>
<p><span data-ttu-id="bdd4d-125">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="bdd4d-125">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="bdd4d-126">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="bdd4d-126">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bdd4d-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">禁用或重新启用 Lync Server 2013 的用户帐户</a></span><span class="sxs-lookup"><span data-stu-id="bdd4d-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="bdd4d-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">在 Lync Server 2013 中启用企业语音用户</a></span><span class="sxs-lookup"><span data-stu-id="bdd4d-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd4d-129">创建和配置由代理组、队列和工作流构成的响应组</span><span class="sxs-lookup"><span data-stu-id="bdd4d-129">Create and configure response groups, which consist of agent groups, queues, and workflows</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="bdd4d-130">使用 Lync Server 控制面板或 Lync Server 命令行管理程序执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="bdd4d-130">Use the Lync Server Control Panel or Lync Server Management Shell to do the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="bdd4d-131">创建和配置代理组。</span><span class="sxs-lookup"><span data-stu-id="bdd4d-131">Create and configure agent groups.</span></span></p></li>
<li><p><span data-ttu-id="bdd4d-132">创建和配置队列。</span><span class="sxs-lookup"><span data-stu-id="bdd4d-132">Create and configure queues.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="bdd4d-133">(可选) 使用 Lync Server Management Shell 创建预定义的响应组业务时间和假日。</span><span class="sxs-lookup"><span data-stu-id="bdd4d-133">Optionally, use Lync Server Management Shell to create predefined response group business hours and holidays.</span></span></p></li>
<li><p><span data-ttu-id="bdd4d-134">使用 "响应组配置" 工具或 Lync Server Management Shell 创建工作流 (查寻组或交互式语音响应 (IVR) 调用流), 包括自定义响应组的业务时间和假日。</span><span class="sxs-lookup"><span data-stu-id="bdd4d-134">Use the Response Group Configuration Tool or Lync Server Management Shell to create workflows (hunt groups or interactive voice response (IVR) call flows), including custom response group business hours and holidays.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="bdd4d-135">您可以通过 Lync Server 控制面板访问 "响应组配置" 工具。</span><span class="sxs-lookup"><span data-stu-id="bdd4d-135">You can access the Response Group Configuration Tool through Lync Server Control Panel.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="bdd4d-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="bdd4d-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="bdd4d-137">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="bdd4d-137">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="bdd4d-138">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="bdd4d-138">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="bdd4d-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="bdd4d-139">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="bdd4d-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="bdd4d-140">CsAdministrator</span></span></p>
<p><span data-ttu-id="bdd4d-141">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="bdd4d-141">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="bdd4d-142"><a href="lync-server-2013-create-response-group-agent-groups.md">在 Lync Server 2013 中创建响应组代理组</a></span><span class="sxs-lookup"><span data-stu-id="bdd4d-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Create Response Group agent groups Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="bdd4d-143"><a href="lync-server-2013-create-response-group-queues.md">在 Lync Server 2013 中创建响应组队列</a></span><span class="sxs-lookup"><span data-stu-id="bdd4d-143"><a href="lync-server-2013-create-response-group-queues.md">Create Response Group queues in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="bdd4d-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">可选在 Lync Server 2013 中定义响应组工作时间</a></span><span class="sxs-lookup"><span data-stu-id="bdd4d-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="bdd4d-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">可选在 Lync Server 2013 中定义 "响应组" 假日集</a></span><span class="sxs-lookup"><span data-stu-id="bdd4d-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="bdd4d-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">在 Lync Server 2013 中创建或修改工作流</a></span><span class="sxs-lookup"><span data-stu-id="bdd4d-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Create or modify a workflow in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd4d-147">（可选）自定义应用程序级别设置</span><span class="sxs-lookup"><span data-stu-id="bdd4d-147">(Optional) Customize application-level settings</span></span></p></td>
<td><p><span data-ttu-id="bdd4d-148">使用 Lync Server Management Shell 自定义默认的音乐保留配置、默认的音乐保留音频文件、代理 ringback 宽限期和调用上下文配置。</span><span class="sxs-lookup"><span data-stu-id="bdd4d-148">Use Lync Server Management Shell to customize the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span></p></td>
<td><p><span data-ttu-id="bdd4d-149">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="bdd4d-149">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="bdd4d-150">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="bdd4d-150">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="bdd4d-151">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="bdd4d-151">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="bdd4d-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="bdd4d-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="bdd4d-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="bdd4d-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bdd4d-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">在 Lync Server 2013 中管理应用程序级别的 "响应" 组设置</a></span><span class="sxs-lookup"><span data-stu-id="bdd4d-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Managing application-level Response Group settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bdd4d-155">（可选）委派响应组的管理</span><span class="sxs-lookup"><span data-stu-id="bdd4d-155">(Optional) Delegate management of response groups</span></span></p></td>
<td><p><span data-ttu-id="bdd4d-156">为用户分配 CsResponseGroupManager 角色以委派响应组的配置。</span><span class="sxs-lookup"><span data-stu-id="bdd4d-156">Assign users the CsResponseGroupManager role to delegate configuration of response groups.</span></span> <span data-ttu-id="bdd4d-157">然后, 响应组管理员可以配置分配给他们的响应组。</span><span class="sxs-lookup"><span data-stu-id="bdd4d-157">Response Group Managers can then configure the response groups assigned to them.</span></span></p></td>
<td><p><span data-ttu-id="bdd4d-158">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="bdd4d-158">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="bdd4d-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="bdd4d-159">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="bdd4d-160">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="bdd4d-160">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="bdd4d-161">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="bdd4d-161">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="bdd4d-162">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="bdd4d-162">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bdd4d-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync Server 2013 中规划基于角色的访问控制</a></span><span class="sxs-lookup"><span data-stu-id="bdd4d-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bdd4d-164">验证响应组部署</span><span class="sxs-lookup"><span data-stu-id="bdd4d-164">Verify your Response Group deployment</span></span></p></td>
<td><p><span data-ttu-id="bdd4d-165">测试智能寻线和互动语音响应工作流的应答呼叫，以确保您的配置按预期工作。</span><span class="sxs-lookup"><span data-stu-id="bdd4d-165">Test answering calls to your hunt group and interactive voice response workflows to ensure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

