---
title: 组内呼叫应答的部署过程
TOCTitle: 组内呼叫应答的部署过程
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945615(v=OCS.15)
ms:contentKeyID: 52060956
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 组内呼叫应答的部署过程

 

_**上一次修改主题：** 2015-03-09_

本节概述组内呼叫应答部署中涉及的步骤。必须先部署 企业语音 的 Enterprise Edition 或 Standard Edition，然后才能配置组内呼叫应答。在部署 企业语音 时，将安装并启用组内呼叫应答所需的组件。

### 组内呼叫应答部署过程

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
<th>所需的组和角色</th>
<th>部署文档</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>在拓扑中启用 SEFAUtil 资源工具包工具</p></td>
<td><ol>
<li><p>使用 <strong>New-CsTrustedApplicationPool</strong> cmdlet 创建新的受信任应用程序池。</p></li>
<li><p>使用 <strong>New-CsTrustedApplication</strong> cmdlet 将 SEFAUtil 工具指定为受信任应用程序。</p></li>
<li><p>运行 <strong>Enable-CsTopology</strong> cmdlet 以启用拓扑。</p></li>
<li><p>在第 1 步创建的受信任应用程序池中的 前端服务器上安装资源工具包工具。</p></li>
<li><p>验证 SEFAUtil 正常运行，方法是运行它，以显示部署中用户的呼叫转接设置。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">部署 SEFAUtil 池</a></p></td>
</tr>
<tr class="even">
<td><p>在呼叫寄存通道表中配置呼叫应答号码范围</p></td>
<td><p>使用 <strong>New-CSCallParkOrbit</strong> cmdlet 在呼叫寄存通道表中创建呼叫应答号码范围，并为呼叫应答范围分配 GroupPickup 类型。</p>
<div>

> [!NOTE]  
> 必须使用 Lync Server 命令行管理程序在呼叫寄存通道表中创建、修改、删除和查看组内呼叫应答号码范围。 Lync Server 控制面板中不存在组内呼叫应答号码范围。


</div>
<div>

> [!NOTE]  
> 为与现有拨号计划进行无缝集成，号码范围通常配置为虚拟分机块。不支持将外线直拨分机 (DID) 号码分配为呼叫寄存轨道表中的范围号码。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">配置组内呼叫应答组号码</a></p></td>
</tr>
<tr class="odd">
<td><p>向用户分配呼叫应答号码，并为用户启用组内呼叫应答</p></td>
<td><p>使用 SEFAUtil 资源工具包工具中的 /enablegrouppickup 参数为用户启用组内呼叫应答并分配呼叫应答号码。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">为用户启用组内呼叫应答并分配组号码</a></p></td>
</tr>
<tr class="even">
<td><p>通知用户其分配的呼叫应答号码和任何其他相关号码</p></td>
<td><p>因为任何用户均可检索拨打至组内呼叫应答用户的呼叫，所以用户可能希望监控多个组。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">将组内呼叫应答分配传达给用户</a></p></td>
</tr>
<tr class="odd">
<td><p>验证您的组内呼叫应答部署</p></td>
<td><p>测试发出和取回呼叫以确保配置按预期工作。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">（可选）验证组内呼叫应答部署</a></p></td>
</tr>
</tbody>
</table>

