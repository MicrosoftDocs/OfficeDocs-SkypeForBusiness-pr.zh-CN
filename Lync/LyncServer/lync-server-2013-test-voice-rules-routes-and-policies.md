---
title: Lync Server 2013：测试语音规则、路由和策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c3b2d98846e537a9a416eaabaf6b02627c7273f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a>在 Lync Server 2013 中测试语音规则、路由和策略

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
<p>使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsVoiceUser cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

当用户进行电话呼叫时，呼叫到达其目标所需的路线取决于分配给该用户的策略和拨号计划。 如果给定用户的 SIP 地址和电话号码，CsVoiceUser cmdlet 将验证问题用户是否可以完成对该号码的呼叫。 如果测试成功，CsVoiceUser 返回以下内容：

  - 转换为电子164格式的数字（基于用户的拨号计划）

  - 提供该翻译的规范化规则

  - 使用的语音路由（基于路线优先级）;

  - 将用户语音策略链接到语音路由的电话使用。

通过 CsVoiceUser，你可以确定特定的电话号码是否按预期进行路由和翻译，并帮助解决单个用户遇到的与呼叫相关的问题。

</div>

<div>

## <a name="running-the-test"></a>运行测试

运行 CsVoiceUser cmdlet 时，你必须提供两条信息：要拨打的号码（DialedNumber）和正在测试的用户帐户的标识。 例如，此命令将测试具有 SIP 地址 sip:kenmyer@litwareinc.com 的用户的功能，以便拨打电话号码 + 1206555-1219：

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

电话号码应按您希望的拨号方式进行格式设置。 例如，如果在拨长途电话之前，用户通常不先拨1，则应使用以下格式：

`-DialedNumber "2065551219"`

当然，在这种情况下，如果你没有可以将数字2065551219正确转换为 Lync Server 使用的 E：164电话格式的规范化规则，测试将失败。 有关详细信息，请参阅帮助主题 CsVoiceNormalizationRule cmdlet。

如果你想要对每个用户帐户运行此相同的测试，你可以使用类似于以下的命令：

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

有关详细信息，请参阅 CsVoiceUser cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果测试成功完成（即，如果用户可以拨打指定号码的电话），则输出将显示 "已翻译电话号码" 和 "匹配规范化规则" 和 "语音路由" 等信息：

TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage

\----------------    ------------    ------------------    -------------

\+12065551219 Descripti   LocalRoute Local

由于 Windows PowerShell 屏幕的限制，至少一些返回的信息（最值得注意的是匹配规范化规则的完整说明）可能不会在屏幕上显示。 如果你仅对测试的成功或失败感兴趣，则可能不重要。 如果你希望查看返回数据的完整详细信息，请在运行测试时将输出输送到格式列表 cmdlet：

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

这将以更易于读取器的格式显示输出：

TranslatedNumber： + 12065551219

MatchingRule： Description =;模式 = ^ （\\d{11}） $;转换 = + $ 1;

Name = Prefix All; IsInternalExtension = False

FirsMatchingRoute : LocalRoute

MatchingUsage： Local

如果测试失败，CsVoiceUser 将返回一组空的属性值：

TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage

\---------------- ------------ ------------------ -------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

CsVoiceUser cmdlet 可能失败的原因有多种：可能没有可用于翻译所提供的电话号码的规范化规则。 语音路线可能出现问题。 分配给有问题的用户的拨号计划可能存在配置问题。 因此，你可能希望在运行 CsVoiceUser cmdlet 时包含详细参数：

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

包括详细 cmdlet 时，CsVoiceUser 将颁发执行检查时采取的所有步骤的详细帐户。 例如，你可能会看到类似以下的步骤： 

详细：查找标识为 "sip:kenmyer@litwareinc.com" 的用户

详细：正在加载拨号计划： "RedmondDialPlan"

这些附加信息可提供有关可用于查明失败原因的步骤的提示。 例如，此处显示的详细输出告诉我们，正在测试的用户是否已分配了拨号计划 RedmondDialPlan。 如果测试失败，下一个逻辑下一步是验证 RedmondDialPlan 是否可以转换提供的电话号码。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Test-CsVoiceUser](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

