---
title: Lync Server 2013：响应组的部署过程
TOCTitle: 响应组的部署过程
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205270(v=OCS.15)
ms:contentKeyID: 49314353
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中响应组的部署过程

 

_**上一次修改主题：** 2015-03-09_

本节概述了部署 响应组应用程序所涉及的阶段和步骤。

### 响应组部署过程

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
<td><p>安装 响应组应用程序</p></td>
<td><p>默认情况下，在您部署 企业语音时，将安装并激活 响应组应用程序。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-enterprise-voice.md">在 Lync Server 2013 中部署企业语音</a></p></td>
</tr>
<tr class="even">
<td><p>安装 响应组的组件</p></td>
<td><p>Lync Server cmdlet、 Lync Server 控制面板、 响应组配置工具、代理的登录和注销控制台以及响应组客户端 Web 服务将作为 Web 服务的一部分进行安装。部署 企业版 池或 Standard Edition Server 时将安装 Web 服务。</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>为 Lync 2013 和 企业语音启用用户</p></td>
<td><p>启用将成为 Lync Server 和 企业语音代理的用户。必须先启用用户，然后才能将其添加到代理组。通常，在 企业版 或 Standard Edition Server 部署期间为 Lync Server 启用用户。在 企业语音部署期间为 企业语音启用用户。</p></td>
<td><p>RTCUniversalUserAdmins</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">禁用或重新启用 Lync Server 的用户帐户</a></p>
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
<li><p>使用 响应组配置工具或 Lync Server 命令行管理程序创建工作流（智能寻线或互动语音响应 (IVR) 呼叫流），包括自定义响应组工作时间和假日。</p>
<div>

> [!NOTE]  
> 可以通过 Lync Server 控制面板访问 响应组配置工具。


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
<p><a href="lync-server-2013-optional-define-response-group-business-hours.md">（可选）在 Lync Server 2013 中定义响应组工作时间</a></p>
<p><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">（可选）定义响应组假日设置</a></p>
<p><a href="lync-server-2013-create-or-modify-a-workflow.md">创建或修改工作流</a></p></td>
</tr>
<tr class="odd">
<td><p>（可选）自定义应用程序级别设置</p></td>
<td><p>使用 Lync Server 命令行管理程序自定义默认保持音乐配置、默认保持音乐音频文件、代理回拨宽限期以及呼叫上下文配置。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-managing-application-level-response-group-settings.md">管理应用程序级别的响应组设置</a></p></td>
</tr>
<tr class="even">
<td><p>（可选）委派响应组的管理</p></td>
<td><p>为用户分配 CsResponseGroupManager 角色以委派响应组的管理。响应组管理员随后可以配置分配给他们的响应组。</p></td>
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

