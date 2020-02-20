---
title: Lync Server 2013：针对语音路由测试电话号码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dc2b921d4e0d487c26532ad1e6102ab32d0162e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a>在 Lync Server 2013 中针对语音路由测试电话号码

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-05-20_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>验证计划</p></td>
<td><p>每月</p></td>
</tr>
<tr class="even">
<td><p>测试工具</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>所需的权限</p></td>
<td><p>在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</p>
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsVoiceRoute cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

语音路由与语音策略结合使用，可帮助将企业语音呼叫路由到 PSTN 网络。 每个语音路由都包含一个正则表达式（一种数字模式），用于标识将通过给定语音路由路由的电话号码：该路由将能够处理与此正则表达式匹配的任何电话号码。 例如，语音路由可能有一个正则表达式，使其能够处理任何10位数字。 这意味着路由将能够处理如下的电话号码：

  - 2065551219

路由将无法处理以下两个号码中的任何一个，两者都不能处理10个数字：

  - 5551219

  - 12065551219

CsVoiceRoute cmdlet 验证给定的语音路由是否可以路由指定的电话号码。

</div>

<div>

## <a name="running-the-test"></a>运行测试

验证语音路由指定电话号码的功能是否为两个步骤的过程。 首先，您必须使用 CsVoiceRoute cmdlet 返回该语音路由的实例，然后您必须使用 CsVoiceRoute cmdlet 来验证该路由处理目标电话号码的能力。 例如，以下命令将验证 RedmondVoiceRoute voice route 是否可以路由电话号码2065551219：

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

请注意，应键入的电话号码应为您希望用户拨打该号码。 例如，如果您不希望用户在拨号时包含国家/地区代码和区号，请使用类似如下的语法：

`-TargetNumber "5551219"`

在这种情况下，目标号码会同时保留国家/地区代码和区号。

若要使用单个命令来测试指定目标号码的所有语音路由，请使用如下语法：

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

有关详细信息，请参阅 CsVoiceRoute cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果语音路由可以路由目标电话号码，CsVoiceRoute cmdlet 只会返回值 True：

MatchesPattern

\--------------

True

这意味着路由可以处理与目标号码类似的号码。 如果语音路由无法处理目标号码，则 CsVoiceRoute 返回值 False：

MatchesPattern

\--------------

False

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

测试语音路由时，"失败" 是相对术语。 在这种情况下，它并不意味着路由在某种程度上是 "中断的" 的，而只是表示路由无法处理目标号码。 这可能是因为语音路由配置不正确。 这也可能意味着路由从未用于使用此模式处理号码。 例如，如果您不希望通过给定路由将呼叫路由到其他国家/地区，可以将路由配置为拒绝包含国家/地区代码的所有电话号码。 如果 CsVoiceRoute 返回 False，如果您希望它返回 True，请验证您是否正确键入了目标编号。 如果执行此操作，请使用与此类似的命令查看为路由配置的 NumberPattern：

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a>另请参阅


[Test-CsVoiceRoute](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

