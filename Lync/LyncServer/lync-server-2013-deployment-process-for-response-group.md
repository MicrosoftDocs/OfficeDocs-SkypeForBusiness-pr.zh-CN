---
title: Lync Server 2013：响应组的部署过程
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
ms.openlocfilehash: dfc249ec8df233e6c22c9d5c1b54b81e23c5a173
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a>Lync Server 2013 中响应组的部署过程

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-27_

本节概述了部署响应组应用程序所涉及的阶段和步骤。

### <a name="response-group-deployment-process"></a>响应组部署过程

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>阶段</th>
<th>步骤</th>
<th>Permissions</th>
<th>部署文档</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>安装响应组应用程序</p></td>
<td><p>默认情况下，在部署企业语音时，会安装并激活响应组应用程序。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">在 Lync Server 2013 中部署企业语音</a></p></td>
</tr>
<tr class="even">
<td><p>安装响应组的组件</p></td>
<td><p>Lync server cmdlet、Lync Server 控制面板、响应组配置工具、代理、登录和注销控制台以及响应组客户端 Web 服务作为 Web 服务的一部分安装。 部署 Enterprise Edition 池或 Standard Edition Server 时，会安装 Web 服务。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>为用户启用 Lync 2013 和企业语音</p></td>
<td><p>启用将成为 Lync Server 和企业语音的代理的用户。 必须先启用用户，然后才能将其添加到代理组。 通常情况下，在企业版或 Standard Edition server 部署期间启用 Lync Server 的用户。 在企业语音部署期间为用户启用企业语音。</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">为 Lync Server 2013 禁用或重新启用用户帐户</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">在 Lync Server 2013 中为用户启用企业语音</a></p></td>
</tr>
<tr class="even">
<td><p>创建和配置由代理组、队列和工作流构成的响应组</p></td>
<td><ol>
<li><p>使用 Lync Server 控制面板或 Lync Server 命令行管理程序执行以下操作：</p>
<ol>
<li><p>创建和配置代理组。</p></li>
<li><p>创建和配置队列。</p></li>
</ol></li>
<li><p>（可选）使用 Lync Server 命令行管理程序创建预定义的响应组工作时间和假日。</p></li>
<li><p>使用响应组配置工具或 Lync Server 命令行管理程序创建工作流（智能寻线或互动语音响应（IVR）呼叫流），包括自定义响应组工作时间和假日。</p>
<div>

> [!NOTE]  
> 您可以通过 Lync Server 控制面板访问 "响应组配置" 工具。


</div></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsResponseGroupManager</p></td>
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">创建响应组代理组 Lync Server 2013</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">在 Lync Server 2013 中创建响应组队列</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">Optional在 Lync Server 2013 中定义响应组工作时间</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">Optional在 Lync Server 2013 中定义响应组假日集</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">在 Lync Server 2013 中创建或修改工作流</a></p></td>
</tr>
<tr class="odd">
<td><p>（可选）自定义应用程序级别设置</p></td>
<td><p>使用 Lync Server 命令行管理程序自定义默认的保持音乐配置、默认的保持音乐音频文件、代理回拨宽限期和呼叫上下文配置。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">在 Lync Server 2013 中管理应用程序级响应组设置</a></p></td>
</tr>
<tr class="even">
<td><p>（可选）委派响应组的管理</p></td>
<td><p>为用户分配 CsResponseGroupManager 角色以委派响应组的配置。 然后，响应组管理员可以配置分配给它们的响应组。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync Server 2013 中规划基于角色的访问控制</a></p></td>
</tr>
<tr class="odd">
<td><p>验证响应组部署</p></td>
<td><p>测试智能寻线和互动语音响应工作流的应答呼叫，以确保您的配置按预期工作。</p></td>
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

