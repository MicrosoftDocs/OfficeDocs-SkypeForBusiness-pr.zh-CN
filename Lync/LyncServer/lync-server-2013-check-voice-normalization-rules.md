---
title: Lync Server 2013：检查语音规范化规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check voice normalization rules
ms:assetid: bf71a218-71cd-4b64-b8e8-b3a98b6e87a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725212(v=OCS.15)
ms:contentKeyID: 63969649
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cf48022fc62f959bbddcd3cb6978e2e668a9334
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a>在 Lync Server 2013 中检查语音规范化规则

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsVoiceNormalizationRule cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

语音规范化规则用于将用户拨打的电话号码（例如，2065551219）转换为 Lync Server 使用的164格式（+ 12065551219）。 例如，如果用户习惯于拨打电话号码，而不包括国家/地区代码或区号（例如，5551219），则您必须有一个可以将该号码转换为. 164 格式的语音规范化规则： + 12065551219。 如果没有此类规则，则用户将无法调用555-1219。

CsVoiceNormalizationRule cmdlet 验证指定的语音规范化规则是否可以成功转换指定的电话号码。 例如，此命令会检查全局规范化规则 NoAreaCode 是否可以规范化和转换拨号字符串5551219。

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a>运行测试

若要运行 CsVoiceNormalizationRule cmdlet，必须首先使用 CsVoiceNormalizationRule cmdlet 检索正在测试的规则的实例，然后通过管道将该实例指定为 Test-CsVoiceNormalizationRule。 与此类似的语法不起作用：

CsVoiceNormalizationRule-DialedNumber "12065551219" – NormalizationRule "global/Prefix All"

请改用如下所示的语法，其中组合了 CsVoiceNormalizationRule 和 CsVoiceNormalizationRule cmdlet：

CsVoiceNormalizationRule-Identity "global/Prefix All" |CsVoiceNormalizationRule-DialedNumber "12065551219"

<div>


> [!NOTE]  
> . 或者，您也可以使用此方法检索规则的实例，然后针对指定的电话号码测试该规则：



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

输入 DialedNumber 参数的值，完全就像您预期要拨打的号码一样。 例如，如果指定的语音规范化规则应自动添加国家/地区代码（值12065551219中的第1个），则应保留国家/地区代码：

`-DialedNumber "2065551219"`

如果正确配置了规则，则会在将号码转换为 Lync Server 使用的 e.164 格式时自动添加国家/地区代码。

有关详细信息，请参阅 CsVoiceNormalizationRule cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果指定的语音规范化规则可以转换所提供的数字，则会在屏幕上显示转换后的数字：

TranslatedNumber

\----------------

\+12065551219

如果测试失败，则返回一个空的已翻译数字：

TranslatedNumber

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

如果 CsVoiceNormalizationRule 确实返回一个已翻译的号码，这意味着指定的语音规范化规则无法将提供的电话号码转换为 Lync Server 使用的 e.164 格式。 若要验证这一点，请首先确保键入的电话号码正确。 例如，您可能希望语音规范化规则在翻译类似以下内容的数字时遇到问题：

`-DialedNumber "1"`

如果正确输入了号码，下一步应是验证指定的规范化规则是否设计为可处理该电话号码。 例如，一个规范化规则设计为可处理格式12065551219，但第二个规则可能设计为处理数字2065551219。 （这是与开头的国家/地区代码1相同的电话号码。）若要返回有关语音规范化规则的详细信息，请运行与以下内容类似的命令：

`Get-CsVoiceNormalizationRule -Identity "global/Prefix All" | Format-List`

若要返回有关所有语音规范化规则的详细信息，请改为运行以下命令：

`Get-CsVoiceNormalizationRule | Format-List`

</div>

<div>

## <a name="see-also"></a>另请参阅


[Test-CsVoiceNormalizationRule](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceNormalizationRule)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

