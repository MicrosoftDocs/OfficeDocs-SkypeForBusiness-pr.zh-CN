---
title: Lync Server 2013：呼叫寄存的部署过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 997097da30db000df82cba020b043748a1a5f62d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522629"
---
# <a name="deployment-process-for-call-park-in-lync-server-2013"></a>Lync Server 2013 中呼叫寄存的部署过程

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-25_

本节概述了部署呼叫寄存应用程序所涉及的步骤。 在配置呼叫寄存之前，必须使用 Enterprise Voice 部署 Enterprise Edition 或 Standard Edition。 当您部署企业语音时，会安装并启用呼叫寄存所需的组件。

### <a name="call-park-deployment-process"></a>呼叫寄存部署过程

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
<td><p>在通道表中配置呼叫寄存通道范围</p></td>
<td><p>使用 Lync Server 控制面板或 <strong>CSCallParkOrbit</strong> cmdlet 可以在呼叫寄存通道表中创建轨道范围，并将它们与承载呼叫寄存应用程序的应用程序服务相关联。</p>
<div>

> [!NOTE]  
> 为与现有拨号计划进行无缝集成，通道范围通常配置为虚拟分机块。不支持将外线直拨分机 (DID) 号码分配为呼叫寄存通道表中的通道号码。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">在 Lync Server 2013 中创建或修改呼叫寄存通道范围</a></p></td>
</tr>
<tr class="even">
<td><p>配置呼叫寄存设置</p></td>
<td><p>使用 <strong>CsCpsConfiguration</strong> cmdlet 可以配置呼叫寄存设置。 我们建议您至少配置 <strong>OnTimeoutURI</strong> 选项，以配置在寄存呼叫超时时使用的回退目标。您还可以配置以下设置：</p>
<ul>
<li><p>（可选）配置 <strong>EnableMusicOnHold</strong> 以启用或禁用保持音乐。</p></li>
<li><p>（可选）配置 <strong>MaxCallPickupAttempts</strong> 以确定将寄存呼叫转接到回退统一资源标识符 (URI) 之前该呼叫回拨应答电话的次数。</p></li>
<li><p>（可选）配置 <strong>CallPickupTimeoutThreshold</strong> 以确定呼叫寄存后到回拨应答该呼叫的电话之前等待的时间。</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-call-park-settings.md">在 Lync Server 2013 中配置呼叫寄存设置</a></p></td>
</tr>
<tr class="odd">
<td><p>（可选）自定义保持音乐</p></td>
<td><p>使用 <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet 自定义并上载音频文件（如果不使用默认的保持音乐）。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-customize-call-park-music-on-hold.md">在 Lync Server 2013 中自定义呼叫寄存暂停音乐</a></p></td>
</tr>
<tr class="even">
<td><p>配置语音策略以为用户启用呼叫寄存</p></td>
<td><p>使用 Lync Server 控制面板或带有<strong>EnableCallPark</strong>选项的<strong>set-csvoicepolicy</strong> cmdlet 为语音策略中的用户启用呼叫寄存。</p>
<div>

> [!NOTE]  
> 默认情况下，对所有用户禁用呼叫寄存。


</div>
<div>

> [!NOTE]  
> 如果具有多个语音策略，请确保为每个语音策略（而不只是默认策略）设置 EnableCallPark 属性。


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsUserAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-enable-call-park-for-users.md">在 Lync Server 2013 中为用户启用呼叫寄存</a></p></td>
</tr>
<tr class="odd">
<td><p>验证呼叫寄存的规范化规则</p></td>
<td><p>不能对呼叫寄存通道进行规范化。验证规范化规则是否未包含任何通道范围。如有必要，创建其他规范化规则以阻止对通道进行规范化。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">在 Lync Server 2013 中验证呼叫寄存的规范化规则</a></p></td>
</tr>
<tr class="even">
<td><p>验证您的呼叫寄存部署</p></td>
<td><p>测试停车和检索调用以确保您的配置按预期方式工作。</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-call-park-deployment.md"> (可选) 在 Lync Server 2013 中验证呼叫寄存部署</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

