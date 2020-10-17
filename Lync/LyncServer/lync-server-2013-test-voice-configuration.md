---
title: Lync Server 2013：测试语音配置
description: Lync Server 2013：测试语音配置。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725208(v=OCS.15)
ms:contentKeyID: 63969605
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cc05286e5f534b4d469ef561d9ce009367e15be
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557068"
---
# <a name="test-voice-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中测试语音配置

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsVoiceTestConfiguration cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

Lync Server 包括几个 Windows PowerShell cmdlet (例如 Test-CsVoiceRoute 和 Set-csvoicepolicy、Remove-cstrunkconfiguration) ，使您能够验证企业语音基础结构的各个部分–语音路由、语音策略、SIP 中继是否按预期工作。

虽然所有单个部件都正常工作的企业语音也很重要：可以有有效的语音路由、有效的语音策略和有效的 SIP 中继，但仍有用户无法拨打或接听电话。 因此，Lync Server 还提供了创建语音测试配置的功能。 语音测试配置代表常见的企业语音方案：您可以指定语音路由、语音策略和拨号计划等内容，然后验证这些单个项目是否能够协同工作以提供电话服务。 此外，还可以在给定方案中验证您的期望。 例如，假设您预计 "拨号计划 A" 和 "语音策略 B" 的组合将导致呼叫通过语音路由 C 路由。您可以输入语音路由 C 作为 ExpectedRoute。 运行测试时，如果未采用语音路由 C，则测试将被标记为 "未通过"。

</div>

<div>

## <a name="running-the-test"></a>运行测试

在使用 Windows PowerShell 测试语音配置集合之前，必须首先使用 Get-CsVoiceTestConfiguration cmdlet 检索这些配置设置的实例。 然后，必须将该实例通过管道传递到 CsVoiceTestConfiguration。 例如：

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

若要同时验证所有语音测试配置设置，请改为使用此命令：

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

有关详细信息，请参阅 Test-CsVoiceTestConfiguration cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

Test-CsVoiceTestConfiguration cmdlet 报告测试是失败还是成功，并提供有关每个成功测试的其他信息，如转换规则、语音路由和用于完成任务的 PSTN 用法：

结果：成功

TranslatedNumber： + 15551234

MatchingRule： Description =;Pattern = ^ (\\ d {4}) $;转换 = + 1 \\ d;Name = Test; IsInternalExtension = False

FirstMatchingRoute： site： Redmond

MatchingUsage： Local

如果测试失败，则结果将报告为 "失败"：

结果：失败

TranslatedNumber:   

FirstMatchingRoute:

MatchingUsage:      

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

由于语音测试配置测试会测试多个不同的项目（包括语音策略、拨号计划、语音路由等），因此可能会导致测试失败的几个不同因素。 如果测试失败，您的第一步是使用 Get-CsVoiceTestConfiguration cmdlet 查看配置设置本身：

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

如果正确配置了设置，请重新运行测试，同时包含详细参数：

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

Verbose 参数将提供 Test-CsVoiceTestConfiguration 所执行的每个操作的分步帐户，如以下示例所示：

VERBOSE：正在加载拨号计划： "Global"

VERBOSE：正在加载语音策略： "RedmondDialPlan"

此分步帐户可能会提供一些有用的线索，如测试实际失败的位置。 如果不是，则可以使用其他 Windows PowerShell cmdlet (例如 Set-csvoicepolicy) ，并以系统方式开始验证语音测试配置设置中所包含的各个组件。

此外，还请注意，测试可以路由呼叫但仍被标记为故障，这也是可能的。如果输入 ExpectedRoute、ExpectedTranslatedNumber 和 ExpectedUsage 的值，并且不满足这些预期中的任何一种，则会发生这种情况。 例如，假设您将语音路由 C 输入为预期的语音路由，但测试实际上是使用语音路由 D 完成呼叫。在这种情况下，测试将被标记为 "失败"，因为未使用预期的语音路由。 如果测试失败，您可以删除 ExpectedRoute、ExpectedTranslatedNumber 和 ExpectedUsage 的值，然后重新运行测试。 这将帮助您确定故障是由于无法完成呼叫，还是由于您需要一件事情而实际收到另一个。

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

