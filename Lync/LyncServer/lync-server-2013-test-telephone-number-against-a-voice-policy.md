---
title: 'Lync Server 2013: 根据语音策略测试电话号码'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test telephone number against a voice policy
ms:assetid: 30c51700-17c6-4c57-891a-8d5ec30b50ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725207(v=OCS.15)
ms:contentKeyID: 63969596
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7a1e24a07a0f6e1e985c9fc42f7468838074d3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-policy-in-lync-server-2013"></a>根据 Lync Server 2013 中的语音策略测试电话号码

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-05-20_


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
<td><p>当使用 Lync Server 命令行管理程序在本地运行时, 用户必须是 RTCUniversalServerAdmins 安全组的成员。</p>
<p>使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsVoicePolicy cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoicePolicy&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

企业语音用户通过公共交换电话网络 (PSTN) 枢轴进行拨出电话呼叫的能力, 在很大程度上取决于以下三个方面:

  - 分配给用户的语音策略。

  - 用于将来自 Lync 服务器的呼叫路由到 PSTN 网络的语音路由。

  - PSTN 使用, 即将语音策略连接到语音路由的 Lync Server 属性。

PSTN 用法尤其重要: 它是将语音策略连接到语音路由的属性。 (如果语音政策和语音路线有至少一个 PSTN 使用, 则表示已连接。)可以在不指定 PSTN 使用的情况下配置语音策略。 在这种情况下, 已分配该策略的用户将无法通过 PSTN 网络进行传出呼叫。 同样, 没有指定 PSTN 使用的语音路由也无法将呼叫路由到 PSTN 网络。

CsVoicePolicy cmdlet 验证给定的语音策略是否具有 PSTN 使用情况, 以及该使用情况是否至少已由一个语音路由共享。 如果由 Test CsVoicePolicy 运行的验证成功, 则 cmdlet 将返回找到的第一个有效语音路由的名称, 以及将策略连接到路由的 PSTN 使用的名称。

</div>

<div>

## <a name="running-the-test"></a>运行测试

若要运行 CsVoicePolicy cmdlet, 必须首先使用 CsVoicePolicy cmdlet 检索要测试的语音策略实例;然后, 必须将该实例管道 CsVoicePolicy。 例如：

`Get-CsVoicePolicy -Identity "Global" | Test-CsVoicePolicy -TargetNumber "+12065551219"`

请注意, 此命令不使用 CsVoicePolicy 检索语音策略实例将失败:

`Test-CsVoicePolicy -TargetNumber "+12065551219" -VoicePolicy "Global"`

如果要根据指定的电话号码检查所有语音策略, 请使用如下所示的命令:

`Get-CsVoicePolicy | Test-CsVoicePolicy -TargetNumber "+12065551219"`

请注意, TargetNumber 必须使用 E.i 格式进行指定。 Test-CsVoicePolicy 不会尝试将电话号码正常化或转换为 E-164 格式。

有关详细信息, 请参阅 CsVoicePolicy cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果语音策略可以找到匹配的语音路由和匹配的 PSTN 使用, 则将在屏幕上显示路由和使用情况:

FirstMatchingRoute MatchingUsage

\------------------ -------------

RedmondVoiceRoute RedmondPstnUsage

如果找不到合适的语音路线或合适的 PSTN 使用, 将在屏幕上显示空属性值:

FirstMatchingRoute MatchingUsage

\------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

如果 CsVoicePolicy 不返回一个匹配项, 这可能意味着语音策略不会与语音路由共享 PSTN 使用。 若要验证, 请使用类似于以下内容的 cmdlet 验证分配给语音策略的 PSTN 用法:

`Get-CsVoicePolicy -Identity "Global" | Select-Object PstnUsages | Format-List`

接下来, 运行此命令以确定分配给每个语音路由的 PSTN 使用情况:

`Get-CsVoiceRoute | Select-Object Identity, PstnUsages`

如果你看到任何匹配项 (即, 如果你看到一个或多个与你的语音策略共享至少一个 PSTN 使用的语音路由), 则你应该运行 CsVoiceRoute cmdlet 以验证语音路由是否可以拨打所提供的电话号码。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Test-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsVoicePolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

