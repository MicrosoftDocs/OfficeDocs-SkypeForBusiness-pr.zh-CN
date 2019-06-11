---
title: 'Lync Server 2013: 测试语音配置'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbe9be7e0f7962bbab546822e7ce6cd47e063540
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中测试语音配置

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
<p>使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsVoiceTestConfiguration cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

Lync 服务器包括多个 Windows PowerShell cmdlet (如 CsVoiceRoute 和 CsVoicePolicy、Test New-cstrunkconfiguration), 使你能够验证你的企业语音基础结构的各个部分-语音路线、语音政策、SIP 中继–按预期工作。

虽然对于所有单个部分都适用的企业语音, 但这一点很重要: 可以具有有效的语音路线、有效的语音策略和有效的 SIP 主干, 但仍有用户无法拨打或接听电话。 因此, Lync 服务器还提供创建语音测试配置的功能。 语音测试配置表示常见的企业语音方案: 您可以指定语音路线、语音政策和拨号计划等内容, 然后验证这些个别项目是否能够协同工作, 以便提供手机服务。 此外, 你可以在给定方案中验证你的预期。 例如, 假设你希望拨入计划 A 和语音策略 B 的组合会导致呼叫通过语音路由 C 进行路由。您可以输入 "语音路由 C" 作为 ExpectedRoute。 运行测试时, 如果未采用 "语音路由 C", 则测试将标记为 "已失败"。

</div>

<div>

## <a name="running-the-test"></a>运行测试

在使用 Windows PowerShell 测试语音配置集合之前, 必须首先使用 CsVoiceTestConfiguration cmdlet 检索这些配置设置的实例。 然后, 必须将该实例输送到 Test CsVoiceTestConfiguration。 例如：

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

若要同时验证所有语音测试配置设置, 请改用以下命令:

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

有关详细信息, 请参阅 CsVoiceTestConfiguration cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

CsVoiceTestConfiguration cmdlet 报告测试是否失败, 并提供有关每个成功测试的详细信息, 例如翻译规则、语音路由和用于完成任务的 PSTN 使用:

结果: 成功

TranslatedNumber: + 15551234

MatchingRule: Description =;模式 = ^ (\\d{4}) $;转换 = + 1\\d;Name = Test; IsInternalExtension = False

FirstMatchingRoute: 网站: 雷德蒙

MatchingUsage: Local

如果测试失败, 则结果报告为失败:

结果: 失败

TranslatedNumber:   

FirstMatchingRoute:

MatchingUsage:      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

由于语音测试配置测试将测试多个不同项目-包括语音策略、拨号计划、语音路由等, 因此可能会导致测试失败的几个不同因素。 如果测试失败, 您的第一步是使用 CsVoiceTestConfiguration cmdlet 查看配置设置本身:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

如果正确配置了设置, 请在包含详细参数的同时重新运行测试:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

详细参数将提供由 Test CsVoiceTestConfiguration 执行的每个操作的分步帐户, 如下例所示:

详细: 正在加载拨号计划: "Global"

详细: 加载语音策略: "RedmondDialPlan"

此分步帐户可能会提供一个有用的线索, 如测试实际失败的位置。 如果不是, 则可以使用其他 Windows PowerShell cmdlet (如 Test-CsVoicePolicy), 然后系统地开始验证语音测试配置设置中包含的单个组件。

此外, 请注意, 测试可以路由呼叫, 但仍会将其标记为失败, 但仍可这样做。如果输入 ExpectedRoute、ExpectedTranslatedNumber 和 ExpectedUsage 的值, 并且不满足这些任何预期条件, 则可能会发生这种情况。 例如, 假设您输入了 "语音路由 C" 作为预期的语音路线, 但测试实际上是使用 "语音路由 D" 完成呼叫。在这种情况下, 测试将标记为 "失败", 因为未使用预期的语音路由。 如果测试失败, 你可以删除 ExpectedRoute、ExpectedTranslatedNumber 和 ExpectedUsage 的值, 然后重新运行测试。 这将帮助你确定失败是因为通话无法完成, 还是你想要一件事并真的收到另一种情况。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Test-CsVoiceTestConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceTestConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

