---
title: 'Lync Server 2013: 组呼叫装货的部署过程'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Group Call Pickup
ms:assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945615(v=OCS.15)
ms:contentKeyID: 51541444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04ff5eda01c5436240c0baca2b1711bba8e9c996
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-group-call-pickup-in-lync-server-2013"></a>Lync Server 2013 中的组呼叫装货的部署过程

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-25_

本部分概述了部署组呼叫时所涉及的步骤。 您必须先部署企业版企业版或标准版, 然后再配置群组呼叫装货。 当您部署企业语音时, 将安装并启用组呼叫挑选所需的组件。

### <a name="group-call-pickup-deployment-process"></a>组内呼叫应答部署过程

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
<td><p>启用拓扑中的 SEFAUtil 资源工具包工具</p></td>
<td><ol>
<li><p>使用 <strong>New-CsTrustedApplicationPool</strong> cmdlet 创建新的受信任应用程序池。</p></li>
<li><p>使用 <strong>New-CsTrustedApplication</strong> cmdlet 将 SEFAUtil 工具指定为受信任应用程序。</p></li>
<li><p>运行 <strong>Enable-CsTopology</strong> cmdlet 来启用拓扑。</p></li>
<li><p>在步骤1中创建的受信任的应用程序池中的前端服务器上安装资源工具包工具。</p></li>
<li><p>验证 SEFAUtil 正常运行，方法是运行它，以显示部署中用户的呼叫转接设置。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-deploy-the-sefautil-tool.md">Deploy the SEFAUtil tool in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>在呼叫寄存通道表中配置呼叫应答号码范围</p></td>
<td><p>使用<strong>CSCallParkOrbit</strong> cmdlet 在 "呼叫公园轨道" 表中创建呼叫装货号码范围, 并将 "呼叫装货" 范围分配给类型 GroupPickup。</p>
<div>

> [!NOTE]  
> 您必须使用 Lync Server Management Shell 在 "呼叫公园轨道" 表中创建、修改、删除和查看组呼叫的装货号码范围。 组呼叫装货号码范围在 Lync Server 控制面板中不可用。


</div>
<div>

> [!NOTE]  
> 为与现有拨号计划进行无缝集成，号码范围通常配置为虚拟分机块。不支持将外线直拨分机 (DID) 号码分配为呼叫寄存轨道表中的范围号码。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-pickup-group-numbers.md">在 Lync Server 2013 中配置呼叫装货组号码</a></p></td>
</tr>
<tr class="odd">
<td><p>为用户分配呼叫装货号码, 并为用户启用组呼叫装货</p></td>
<td><p>使用 SEFAUtil 资源工具包工具中的/enablegrouppickup 参数启用组呼叫装货, 并为用户分配呼叫装货号码。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md">为 Lync Server 2013 中的用户启用组呼叫装货和分配组号码</a></p></td>
</tr>
<tr class="even">
<td><p>通知用户其分配的呼叫应答号码和任何其他相关号码</p></td>
<td><p>由于任何用户都可以检索对组调用 Pickup 用户的呼叫, 因此用户可能希望监视多个组。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-communicate-group-call-pickup-assignment-to-users.md">向 Lync Server 2013 中的用户传达组呼叫装货作业</a></p></td>
</tr>
<tr class="odd">
<td><p>验证组呼叫装货部署</p></td>
<td><p>测试发出和取回呼叫以确保配置按预期工作。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-the-group-call-pickup-deployment.md">可选验证 Lync Server 2013 中的组呼叫装货部署</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

