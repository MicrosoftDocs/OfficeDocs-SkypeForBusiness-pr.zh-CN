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
ms.openlocfilehash: 52f7646010e4048d135e11c98d06a651f923d633
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522609"
---
# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a>Lync Server 2013 中组呼叫应答的部署过程

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-25_

本节概述了部署组内呼叫应答涉及的步骤。 在配置组呼叫应答之前，必须使用 Enterprise Voice 部署 Enterprise Edition 或 Standard Edition。 当您部署企业语音时，会安装并启用组呼叫应答所需的组件。

### <a name="group-call-pickup-deployment-process"></a>组呼叫应答部署过程

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
<li><p>使用 <strong>CsTrustedApplicationPool</strong> cmdlet 可以创建新的受信任应用程序池。</p></li>
<li><p>使用 <strong>CsTrustedApplication</strong> cmdlet 可将 SEFAUtil 工具指定为受信任的应用程序。</p></li>
<li><p>运行 <strong>enable-cstopology</strong> cmdlet 以启用拓扑。</p></li>
<li><p>在第1步中创建的受信任应用程序池中的前端服务器上安装资源工具包工具。</p></li>
<li><p>运行此程序以验证 SEFAUtil 是否正常运行，以在部署中显示用户的呼叫转接设置。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">在 Lync Server 2013 中部署 SEFAUtil 工具</a></p></td>
</tr>
<tr class="even">
<td><p>在呼叫寄存通道表中配置呼叫装货号码范围</p></td>
<td><p>使用 <strong>CSCallParkOrbit</strong> cmdlet 可以在呼叫寄存通道表中创建呼叫应答号码范围，并将呼叫装货范围分配给 GroupPickup 类型。</p>
<div>

> [!NOTE]  
> 必须使用 Lync Server 命令行管理程序在呼叫寄存通道表中创建、修改、删除和查看组内呼叫应答号码范围。 组内呼叫应答号码范围在 Lync Server 控制面板中不可用。


</div>
<div>

> [!NOTE]  
> 对于与现有拨号计划的无缝集成，号码范围通常配置为虚拟扩展块。 将直接向内拨号 (分配为呼叫寄存通道表中的区域号码不支持) 号码。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">在 Lync Server 2013 中配置呼叫应答组号码</a></p></td>
</tr>
<tr class="odd">
<td><p>为用户分配呼叫装货号码，并为用户启用组呼叫应答</p></td>
<td><p>使用 SEFAUtil 资源工具包工具中的/enablegrouppickup 参数可启用组呼叫应答，并为用户分配呼叫应答号码。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">为 Lync Server 2013 中的用户启用组内呼叫应答并分配组号码</a></p></td>
</tr>
<tr class="even">
<td><p>通知用户分配的呼叫应答号码和任何其他感兴趣的号码</p></td>
<td><p>由于任何用户都可以检索对组呼叫应答用户的呼叫，因此用户可能需要监视多个组。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">在 Lync Server 2013 中向用户传达组呼叫装货分配</a></p></td>
</tr>
<tr class="odd">
<td><p>验证你的组呼叫装货部署</p></td>
<td><p>测试发出和检索呼叫以确保配置按预期方式工作。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md"> (可选) 在 Lync Server 2013 中验证组内呼叫应答部署</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

