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
ms.openlocfilehash: 8e0e39b88d7b6c90a55d236038d03cc4cc717319
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-dial-plan-in-lync-server-2013"></a>在 Lync Server 2013 中测试拨号计划

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-06-05_


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
<td><p>需要权限</p></td>
<td><p>当使用 Lync Server 命令行管理程序在本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</p>
<p>使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsDialPlan cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialPlan&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsDialPlan cmdlet 使你能够查看将拨号计划应用到给定电话号码的结果。 拨号计划提供有关如何应用规范化规则的信息，从而使企业语音用户可以拨打电话。 在给定一个已拨号码和拨号计划后，此 cmdlet 将验证将应用拨号计划中的哪个规范化规则以及已翻译的号码。

你可以使用此 cmdlet 解决数字翻译的问题，或验证如何对某些号码应用规则。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsDialPlan cmdlet 要求你执行两个操作。 首先，您必须获取正在测试的拨号计划的实例;可使用 CsDialPlan cmdlet 执行此操作。 其次，您必须指定必须规范化的电话号码。 电话号码所用的格式应与用户拨打/输入的号码相匹配。 例如，此命令检索拨号计划的实例 RedmondDialPlan，并检查电话号码12065551219是否可以正常化：

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "12065551219" | Format-List

如果你具有自动添加国家/地区代码（在本例中为1）和区号（206）的规范化规则，则你可能需要检查电话号码5551219，如下所示：

    Get-CsDialPlan -Identity "RedmondDialPlan" | Test-CsDialPlan -DialedNumber "5551219" | Format-List

有关详细信息，请参阅[CsDialPlan](https://docs.microsoft.com/powershell/module/skype/Test-CsDialPlan) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

Test-CsDialPlan 不同于许多 Lync Server 测试 cmdlet，因为它仅间接指示测试是成功还是失败。 使用 Test-CsDialPlan 时，您不会收到与此类似的输出结果，并明确标记结果：

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：06.8630376

时发生

自检

相反，如果 CsDialPlan 成功，则你将收到有关能够成功转换和使用指定电话号码的规范化规则的信息：

TranslatedNumber： + 12065551219

MatchingRule： Description =;模式 = ^ （\\d （11）） $;转换 = + $ 1;

Name = Prefix All;IsInternalExtension = False

如果测试 CsDialPlan 失败（即，如果拨号计划没有可以翻译指定电话号码的规范化规则），您将只收到 "empty" 输出，如下所示：

TranslatedNumber :

MatchingRule :

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是测试 CsDialPlan 可能失败的一些常见原因：

  - 在指定电话号码时，您可能使用了不正确的格式。 拨号计划包括允许 Lync Server 转换用户拨打或输入的电话号码的规范化规则。 因此，您的拨号计划应具有与用户可能拨打的号码相匹配的规范化规则。 例如，如果用户可能先拨打国家/地区代码、区号，然后拨打电话号码，则表示您的拨号计划应具有用于处理电话号码的规范化规则，如下所示：
    
    12065551219
    
    但是，如果输入错误的电话号码（例如，退出最终数字），则 CsDialPlan 将失败。 这是因为拨号计划有问题，但您输入的电话号码不能解释。

</div>

</div>

<span> </span>

</div>

</div>

</div>

