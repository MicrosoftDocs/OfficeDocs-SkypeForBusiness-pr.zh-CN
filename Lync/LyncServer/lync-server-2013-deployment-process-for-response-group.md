---
title: Lync Server 2013：响应组的部署过程
description: Lync Server 2013：响应组的部署过程。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b50fb7903a2fcc301bbf435013b8f8df4e775a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551028"
---
# <a name="deployment-process-for-response-group-in-lync-server-2013"></a><span data-ttu-id="5b922-103">Lync Server 2013 中响应组的部署过程</span><span class="sxs-lookup"><span data-stu-id="5b922-103">Deployment process for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b922-104">_**上次修改的主题：** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="5b922-104">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="5b922-105">本节概述了部署响应组应用程序所涉及的阶段和步骤。</span><span class="sxs-lookup"><span data-stu-id="5b922-105">This section provides an overview of the phases and steps involved in deploying the Response Group application.</span></span>

### <a name="response-group-deployment-process"></a><span data-ttu-id="5b922-106">响应组部署过程</span><span class="sxs-lookup"><span data-stu-id="5b922-106">Response Group Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b922-107">阶段</span><span class="sxs-lookup"><span data-stu-id="5b922-107">Phase</span></span></th>
<th><span data-ttu-id="5b922-108">步骤</span><span class="sxs-lookup"><span data-stu-id="5b922-108">Steps</span></span></th>
<th><span data-ttu-id="5b922-109">权限</span><span class="sxs-lookup"><span data-stu-id="5b922-109">Permissions</span></span></th>
<th><span data-ttu-id="5b922-110">部署文档</span><span class="sxs-lookup"><span data-stu-id="5b922-110">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b922-111">安装响应组应用程序</span><span class="sxs-lookup"><span data-stu-id="5b922-111">Install the Response Group application</span></span></p></td>
<td><p><span data-ttu-id="5b922-112">默认情况下，在部署企业语音时，会安装并激活响应组应用程序。</span><span class="sxs-lookup"><span data-stu-id="5b922-112">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="5b922-113">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5b922-113">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="5b922-114"><a href="lync-server-2013-deploying-enterprise-voice.md">在 Lync Server 2013 中部署企业语音</a></span><span class="sxs-lookup"><span data-stu-id="5b922-114"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b922-115">安装响应组的组件</span><span class="sxs-lookup"><span data-stu-id="5b922-115">Install components for Response Group</span></span></p></td>
<td><p><span data-ttu-id="5b922-116">Lync server cmdlet、Lync Server 控制面板、响应组配置工具、代理、登录和注销控制台以及响应组客户端 Web 服务作为 Web 服务的一部分安装。</span><span class="sxs-lookup"><span data-stu-id="5b922-116">Lync Server cmdlets, the Lync Server Control Panel, Response Group Configuration Tool, agents' sign-in and sign-out console, and Response Group Client Web service are installed as part of Web Services.</span></span> <span data-ttu-id="5b922-117">部署 Enterprise Edition 池或 Standard Edition Server 时，会安装 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="5b922-117">Web Services is installed when you deploy an Enterprise Edition pool or a Standard Edition server.</span></span></p></td>
<td><p><span data-ttu-id="5b922-118">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5b922-118">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="5b922-119"><a href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5b922-119"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b922-120">为用户启用 Lync 2013 和企业语音</span><span class="sxs-lookup"><span data-stu-id="5b922-120">Enable users for Lync 2013 and for Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="5b922-121">启用将成为 Lync Server 和企业语音的代理的用户。</span><span class="sxs-lookup"><span data-stu-id="5b922-121">Enable users who will be agents for Lync Server and Enterprise Voice.</span></span> <span data-ttu-id="5b922-122">必须先启用用户，然后才能将其添加到代理组。</span><span class="sxs-lookup"><span data-stu-id="5b922-122">Users must be enabled before you can add them to agent groups.</span></span> <span data-ttu-id="5b922-123">通常情况下，在企业版或 Standard Edition server 部署期间启用 Lync Server 的用户。</span><span class="sxs-lookup"><span data-stu-id="5b922-123">Typically, users are enabled for Lync Server during the Enterprise Edition or Standard Edition server deployment.</span></span> <span data-ttu-id="5b922-124">在企业语音部署期间为用户启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="5b922-124">Users are enabled for Enterprise Voice during the Enterprise Voice deployment.</span></span></p></td>
<td><p><span data-ttu-id="5b922-125">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="5b922-125">RTCUniversalUserAdmins</span></span></p>
<p><span data-ttu-id="5b922-126">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b922-126">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="5b922-127">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b922-127">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5b922-128"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">为 Lync Server 2013 禁用或重新启用用户帐户</a></span><span class="sxs-lookup"><span data-stu-id="5b922-128"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="5b922-129"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">在 Lync Server 2013 中为用户启用企业语音</a></span><span class="sxs-lookup"><span data-stu-id="5b922-129"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b922-130">创建和配置由代理组、队列和工作流构成的响应组</span><span class="sxs-lookup"><span data-stu-id="5b922-130">Create and configure response groups, which consist of agent groups, queues, and workflows</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="5b922-131">使用 Lync Server 控制面板或 Lync Server 命令行管理程序执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5b922-131">Use the Lync Server Control Panel or Lync Server Management Shell to do the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="5b922-132">创建和配置代理组。</span><span class="sxs-lookup"><span data-stu-id="5b922-132">Create and configure agent groups.</span></span></p></li>
<li><p><span data-ttu-id="5b922-133">创建和配置队列。</span><span class="sxs-lookup"><span data-stu-id="5b922-133">Create and configure queues.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="5b922-134">（可选）使用 Lync Server 命令行管理程序创建预定义的响应组工作时间和假日。</span><span class="sxs-lookup"><span data-stu-id="5b922-134">Optionally, use Lync Server Management Shell to create predefined response group business hours and holidays.</span></span></p></li>
<li><p><span data-ttu-id="5b922-135">使用响应组配置工具或 Lync Server 命令行管理程序创建工作流 (智能寻线或互动语音响应 (IVR) 呼叫流) ，包括自定义响应组工作时间和假日。</span><span class="sxs-lookup"><span data-stu-id="5b922-135">Use the Response Group Configuration Tool or Lync Server Management Shell to create workflows (hunt groups or interactive voice response (IVR) call flows), including custom response group business hours and holidays.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="5b922-136">您可以通过 Lync Server 控制面板访问 "响应组配置" 工具。</span><span class="sxs-lookup"><span data-stu-id="5b922-136">You can access the Response Group Configuration Tool through Lync Server Control Panel.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="5b922-137">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5b922-137">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5b922-138">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b922-138">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="5b922-139">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b922-139">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="5b922-140">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b922-140">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5b922-141">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b922-141">CsAdministrator</span></span></p>
<p><span data-ttu-id="5b922-142">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="5b922-142">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="5b922-143"><a href="lync-server-2013-create-response-group-agent-groups.md">创建响应组代理组 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="5b922-143"><a href="lync-server-2013-create-response-group-agent-groups.md">Create Response Group agent groups Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="5b922-144"><a href="lync-server-2013-create-response-group-queues.md">在 Lync Server 2013 中创建响应组队列</a></span><span class="sxs-lookup"><span data-stu-id="5b922-144"><a href="lync-server-2013-create-response-group-queues.md">Create Response Group queues in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="5b922-145"><a href="lync-server-2013-optional-define-response-group-business-hours.md"> (可选) 在 Lync Server 2013 中定义响应组工作时间</a></span><span class="sxs-lookup"><span data-stu-id="5b922-145"><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="5b922-146"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md"> (可选) 在 Lync Server 2013 中定义响应组假日集</a></span><span class="sxs-lookup"><span data-stu-id="5b922-146"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="5b922-147"><a href="lync-server-2013-create-or-modify-a-workflow.md">在 Lync Server 2013 中创建或修改工作流</a></span><span class="sxs-lookup"><span data-stu-id="5b922-147"><a href="lync-server-2013-create-or-modify-a-workflow.md">Create or modify a workflow in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b922-148">（可选）自定义应用程序级别设置</span><span class="sxs-lookup"><span data-stu-id="5b922-148">(Optional) Customize application-level settings</span></span></p></td>
<td><p><span data-ttu-id="5b922-149">使用 Lync Server 命令行管理程序自定义默认的保持音乐配置、默认的保持音乐音频文件、代理回拨宽限期和呼叫上下文配置。</span><span class="sxs-lookup"><span data-stu-id="5b922-149">Use Lync Server Management Shell to customize the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span></p></td>
<td><p><span data-ttu-id="5b922-150">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5b922-150">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5b922-151">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b922-151">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="5b922-152">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b922-152">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="5b922-153">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b922-153">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5b922-154">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b922-154">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5b922-155"><a href="lync-server-2013-managing-application-level-response-group-settings.md">在 Lync Server 2013 中管理应用程序级响应组设置</a></span><span class="sxs-lookup"><span data-stu-id="5b922-155"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Managing application-level Response Group settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b922-156">（可选）委派响应组的管理</span><span class="sxs-lookup"><span data-stu-id="5b922-156">(Optional) Delegate management of response groups</span></span></p></td>
<td><p><span data-ttu-id="5b922-157">为用户分配 CsResponseGroupManager 角色以委派响应组的配置。</span><span class="sxs-lookup"><span data-stu-id="5b922-157">Assign users the CsResponseGroupManager role to delegate configuration of response groups.</span></span> <span data-ttu-id="5b922-158">然后，响应组管理员可以配置分配给它们的响应组。</span><span class="sxs-lookup"><span data-stu-id="5b922-158">Response Group Managers can then configure the response groups assigned to them.</span></span></p></td>
<td><p><span data-ttu-id="5b922-159">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5b922-159">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="5b922-160">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b922-160">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="5b922-161">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b922-161">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="5b922-162">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b922-162">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="5b922-163">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="5b922-163">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="5b922-164"><a href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync Server 2013 中规划基于角色的访问控制</a></span><span class="sxs-lookup"><span data-stu-id="5b922-164"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b922-165">验证响应组部署</span><span class="sxs-lookup"><span data-stu-id="5b922-165">Verify your Response Group deployment</span></span></p></td>
<td><p><span data-ttu-id="5b922-166">测试智能寻线和互动语音响应工作流的应答呼叫，以确保您的配置按预期工作。</span><span class="sxs-lookup"><span data-stu-id="5b922-166">Test answering calls to your hunt group and interactive voice response workflows to ensure that your configuration works as expected.</span></span></p></td>
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

