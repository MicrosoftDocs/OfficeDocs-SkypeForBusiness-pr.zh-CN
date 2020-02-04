---
title: Lync Server 2013：根据语音路线测试电话号码
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
ms.openlocfilehash: 5d4105b54c7d5b745efddeeb961960c402aaa349
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a>根据 Lync Server 2013 中的语音路线测试电话号码

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-05-20_


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
<td><p>需要权限</p></td>
<td><p>当使用 Lync Server 命令行管理程序在本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</p>
<p>使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsVoiceRoute cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

语音路由与语音策略协同工作，帮助将企业语音呼叫路由到 PSTN 网络。 每个语音路由都包含一个正则表达式（数字模式），用于标识将通过给定语音路线路由的电话号码：路由将能够处理与此正则表达式匹配的任何电话号码。 例如，语音路由可能有一个正则表达式，可使其处理任何10位数字。 这意味着路由将能够处理如下所示的电话号码：

  - 2065551219

路由将无法处理以下两个数字中的任何一个，其中两个数字都没有10个数字：

  - 5551219

  - 12065551219

CsVoiceRoute cmdlet 验证给定的语音路线是否可以路由指定的电话号码。

</div>

<div>

## <a name="running-the-test"></a>运行测试

验证语音路线路由指定电话号码的能力是两步过程。 首先，你必须使用 CsVoiceRoute cmdlet 来返回该语音路由的实例，然后你必须使用 CsVoiceRoute cmdlet 验证该路由处理目标电话号码的能力。 例如，此命令将验证 RedmondVoiceRoute 的语音路线是否可以路由电话号码2065551219：

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

请注意，输入的电话号码应为您希望用户拨打该号码时输入。 例如，如果您不希望用户在拨号时包括国家代码和区号，则使用类似于以下语法的语法：

`-TargetNumber "5551219"`

在这种情况下，目标号码将同时保留国家/地区代码和区号。

若要使用单个命令来根据指定的目标号码测试所有语音路由，请使用如下语法：

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

有关详细信息，请参阅 CsVoiceRoute cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果语音路由可以路由目标电话号码，CsVoiceRoute cmdlet 只会返回值 True：

MatchesPattern

\--------------

True

这意味着路由可以处理与目标号码类似的号码。 如果语音路由无法处理目标号码，则 Test-CsVoiceRoute 返回值 False：

MatchesPattern

\--------------

False

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

测试语音路由时，"失败" 是一个相对术语。 在这种情况下，它不意味着路由是以 "损坏;" 为目标的，而是指路由无法处理目标号码。 这可能是因为语音路由配置不正确。 这也可能意味着该路由从未用于处理使用此模式的数字。 例如，如果您不希望通过给定路线将呼叫路由到其他国家/地区，可以将路由配置为拒绝包括国家/地区代码的所有电话号码。 如果 CsVoiceRoute 返回 False （如果你希望它返回 True），请验证是否正确键入了目标编号。 如果执行此操作，请使用与此类似的命令查看为该路由配置的 NumberPattern：

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

