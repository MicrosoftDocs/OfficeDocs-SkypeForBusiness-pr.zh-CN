---
title: Lync Server 2013：测试拨号计划
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the dial plan
ms:assetid: 70eec03c-aca3-4106-86a7-77ae96b53779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690130(v=OCS.15)
ms:contentKeyID: 63969616
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c758f2f16d59db92841a5e7ef727a41cee8a8d4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530439"
---
# <a name="testing-the-dial-plan-in-lync-server-2013"></a>在 Lync Server 2013 中测试拨号计划

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>验证计划</p></td>
<td><p>每天</p></td>
</tr>
<tr class="even">
<td><p>测试工具</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>所需的权限</p></td>
<td><p>在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</p>
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsDialPlan cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

使用 Test-CsDialPlan cmdlet，可以查看将拨号计划应用于给定电话号码的结果。 拨号计划提供的信息（如应用规范化规则的方式），使企业语音用户可以打电话。 给定一个已拨电话和拨号计划，此 cmdlet 将验证应用该拨号计划中的哪个规范化规则以及转换后的号码是什么。

您可以使用此 cmdlet 对号码转换问题进行故障排除，或验证如何对特定号码应用规则。

</div>

<div>

## <a name="running-the-test"></a>运行测试

Test-CsDialPlan cmdlet 要求您执行两项操作。 首先，您必须获取正在测试的拨号计划的实例;可以使用 Get-CsDialPlan cmdlet 执行此操作。 其次，必须指定必须规范化的电话号码。 用于电话号码的格式应与用户拨打/输入的号码相匹配。 例如，此命令检索 RedmondDialPlan 的拨号计划实例，并检查电话号码12065551219是否可以规范化：

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

如果您有一个在此示例中自动添加国家/地区代码 (的规范化规则，则 1) ，区号 (206) ，那么您可能需要检查电话号码5551219，如下所示：

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

有关详细信息，请参阅 [grant-csdialplan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

Test-CsDialPlan 与许多 Lync Server 测试 cmdlet 不同，因为它仅间接指示测试是成功还是失败。 使用 Test-CsDialPlan 时，您不会收到与以下内容类似的返回输出结果，并对结果进行了明确标记：

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：06.8630376

误差

诊断

相反，如果 Test-CsDialPlan 成功，则您将收到能够成功转换和使用指定电话号码的规范化规则的相关信息：

TranslatedNumber： + 12065551219

MatchingRule： Description =;模式 = ^ (\\ d (11) # B3 $;转换 = + $ 1;

Name = Prefix All;IsInternalExtension = False

如果 Test-CsDialPlan 失败 (也就是说，如果拨号计划没有可将指定的电话号码转换) 的规范化规则，您将只收到如下所示的 "空" 输出：

TranslatedNumber :

MatchingRule :

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是 Test-CsDialPlan 可能失败的一些常见原因：

  - 在指定电话号码时，可能使用了不正确的格式。 拨号计划包括使 Lync Server 能够转换用户拨打或输入的电话号码的规范化规则。 因此，您的拨号计划应具有与用户可能拨打的号码相匹配的规范化规则。 例如，如果用户可能拨打国家/地区代码、区号和电话号码本身，则意味着您的拨号计划应具有用于处理电话号码的规范化规则，如下所示：
    
    12065551219
    
    但是，如果输入不正确的电话号码 (例如，不使用最后的数字) ，Test-CsDialPlan 将失败。 这是因为拨号计划有问题，但您输入的电话号码不是无法解释的。

</div>

</div>

<span> </span>

</div>

</div>

</div>

