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
ms.openlocfilehash: 2eb302f57cd335decf3523c271ff464f2954db86
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a>Lync Server 2013 中的 "响应" 组的部署过程

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-27_

本部分概述了部署响应组应用程序时所涉及的阶段和步骤。

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
<th>权限</th>
<th>部署文档</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>安装响应组应用程序</p></td>
<td><p>部署企业语音时，将默认安装并激活 "响应组" 应用程序。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">在 Lync Server 2013 中部署企业语音</a></p></td>
</tr>
<tr class="even">
<td><p>为响应组安装组件</p></td>
<td><p>Lync Server cmdlet、Lync Server 控制面板、响应组配置工具、代理的登录和注销控制台，以及响应组客户端 Web 服务作为 Web 服务的一部分进行安装。 在部署企业版池或标准版服务器时，将安装 Web 服务。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>为 Lync 2013 和企业语音启用用户</p></td>
<td><p>启用将用作 Lync Server 和企业语音的代理的用户。 必须先启用用户，然后才能将其添加到代理组。 通常，在企业版或标准版服务器部署期间启用 Lync Server 的用户。 在企业语音部署期间，用户可用于企业语音。</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">禁用或重新启用 Lync Server 2013 的用户帐户</a></p>
<p><a href="lync-server-2013-enable-users-for-enterprise-voice.md">在 Lync Server 2013 中启用企业语音用户</a></p></td>
</tr>
<tr class="even">
<td><p>创建和配置由代理组、队列和工作流构成的响应组</p></td>
<td><ol>
<li><p>使用 Lync Server 控制面板或 Lync Server 命令行管理程序执行下列操作：</p>
<ol>
<li><p>创建和配置代理组。</p></li>
<li><p>创建和配置队列。</p></li>
</ol></li>
<li><p>（可选）使用 Lync Server Management Shell 创建预定义的响应组业务时间和假日。</p></li>
<li><p>使用 "响应组配置" 工具或 Lync Server Management Shell 创建工作流（查寻组或交互式语音响应（IVR）调用流），包括自定义响应组的业务时间和假日。</p>
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
<td><p><a href="lync-server-2013-create-response-group-agent-groups.md">在 Lync Server 2013 中创建响应组代理组</a></p>
<p><a href="lync-server-2013-create-response-group-queues.md">在 Lync Server 2013 中创建响应组队列</a></p>
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">可选在 Lync Server 2013 中定义响应组工作时间</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">可选在 Lync Server 2013 中定义 "响应组" 假日集</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">在 Lync Server 2013 中创建或修改工作流</a></p></td>
</tr>
<tr class="odd">
<td><p>（可选）自定义应用程序级别设置</p></td>
<td><p>使用 Lync Server Management Shell 自定义默认的音乐保留配置、默认的音乐保留音频文件、代理 ringback 宽限期和调用上下文配置。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">在 Lync Server 2013 中管理应用程序级别的 "响应" 组设置</a></p></td>
</tr>
<tr class="even">
<td><p>（可选）委派响应组的管理</p></td>
<td><p>为用户分配 CsResponseGroupManager 角色以委派响应组的配置。 然后，响应组管理员可以配置分配给他们的响应组。</p></td>
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

