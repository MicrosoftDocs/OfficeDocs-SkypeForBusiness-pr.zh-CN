---
title: Lync Server 2013：针对语音策略测试电话号码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2ac10938dbbc2810e5b43aae85711bf8413ad27
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519159"
---
# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a>在 Lync Server 2013 中针对语音策略测试电话号码

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsVoicePolicy cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

企业语音用户通过公用电话交换电话网络发出的传出电话呼叫 (PSTN) 枢轴的功能，在很大程度上取决于三个方面：

  - 为用户分配的语音策略。

  - 用于将呼叫从 Lync Server 路由到 PSTN 网络的语音路由。

  - PSTN 用法，即将语音策略连接到语音路由的 Lync Server 属性。

PSTN 用法尤为重要：它是将语音策略连接到语音路由的属性。  (语音策略和语音路由如果它们共有至少一个 PSTN 用法，则称为 "已连接"。 ) 语音策略可以在不指定 PSTN 用法的情况下进行配置。 在这种情况下，分配了该策略的用户将无法通过 PSTN 网络发出传出呼叫。 同样，没有至少一个指定 PSTN 用法的语音路由也无法将呼叫路由到 PSTN 网络。

Test-CsVoicePolicy cmdlet 验证给定的语音策略是否有 PSTN 用法，以及该使用情况是否至少由一个语音路由共享。 如果 Test-CsVoicePolicy 成功运行验证，cmdlet 将返回找到的第一个有效语音路由的名称，也会报告将策略连接到路由的 PSTN 用法的名称。

</div>

<div>

## <a name="running-the-test"></a>运行测试

若要运行 Test-CsVoicePolicy cmdlet，您必须首先使用 Get-CsVoicePolicy cmdlet 检索要测试的语音策略实例;然后，必须将该实例通过管道传递到 Set-csvoicepolicy。 例如：

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

请注意，此命令不使用 Get-CsVoicePolicy 检索语音策略实例将失败：

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

如果要根据指定的电话号码检查所有语音策略，请使用类似如下的命令：

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

请注意，必须使用 e.164 格式指定 TargetNumber。 Test-CsVoicePolicy 不会尝试将电话号码正常化或转换为. 164 格式。

有关详细信息，请参阅 Test-CsVoicePolicy cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果语音策略可以找到匹配的语音路由和匹配的 PSTN 用法，则将在屏幕上显示路由和使用：

FirstMatchingRoute MatchingUsage

\------------------ -------------

RedmondVoiceRoute RedmondPstnUsage

如果找不到合适的语音路由或合适的 PSTN 用法，将在屏幕上显示空白属性值：

FirstMatchingRoute MatchingUsage

\------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

如果 Test-CsVoicePolicy 不返回匹配项，则表示语音策略不会与语音路由共享 PSTN 用法。 若要验证，请使用与以下内容类似的 cmdlet 来验证是否为语音策略分配了 PSTN 用法：

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

接下来，运行此命令以确定 PSTN 用法分配给每个语音路由：

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

如果您看到任何匹配项 (也就是说，如果您看到一个或多个与语音策略共享至少一个 PSTN 用法的语音路由) ，则应运行 Test-CsVoiceRoute cmdlet 以验证语音路由可以拨打所提供的电话号码。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Test-Set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

