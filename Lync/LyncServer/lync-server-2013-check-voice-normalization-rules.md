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
ms.openlocfilehash: 04e383f38d5af6f106354a766c857635bcd87eb3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733862"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-voice-normalization-rules-in-lync-server-2013"></a>在 Lync Server 2013 中检查语音规范化规则

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
<p>使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsVoiceNormalizationRule cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceNormalizationRule&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

语音规范化规则用于将用户拨打的电话号码（例如2065551219）转换为 Lync Server （+ 12065551219）使用的格式。 例如，如果用户习惯于拨打电话号码，而不包括国家或地区代码（例如，5551219），则必须具有可将该号码转换为 E-164 格式的语音规范化规则： + 12065551219。 如果没有此类规则，用户将无法调用555-1219。

CsVoiceNormalizationRule cmdlet 验证指定的语音规范化规则是否可以成功转换指定的电话号码。 例如，此命令检查全局规范化规则 NoAreaCode 是否可以规范化和转换拨号字符串5551219。

`Get-CsVoiceNormalizationRule -Identity "global/NoAreaCode" | Test-CsVoiceNormalizationRule -DialedNumber "5551219"`

</div>

<div>

## <a name="running-the-test"></a>运行测试

若要运行 CsVoiceNormalizationRule cmdlet，必须首先使用 CsVoiceNormalizationRule cmdlet 检索正在测试的规则的实例，然后管道该实例进行测试 CsVoiceNormalizationRule。 与此类似的语法不起作用：

CsVoiceNormalizationRule-DialedNumber "12065551219"-NormalizationRule "global/Prefix All"

而是使用以下语法，这种语法结合了 CsVoiceNormalizationRule 和 CsVoiceNormalizationRule cmdlet：

CsVoiceNormalizationRule-Identity "global/Prefix All" |Test-CsVoiceNormalizationRule-DialedNumber "12065551219"

<div>


> [!NOTE]  
> . 或者，你也可以使用此方法检索规则的实例，然后根据指定的电话号码测试该规则：



</div>

`$x = Get-CsVoiceNormalizationRule -Identity "global/Prefix All"`

`Test-CsVoiceNormalizationRule -DialedNumber "12065551219" -NormalizationRule $x`

输入 DialedNumber 参数的值，准确地说您希望拨叫的号码。 例如，如果指定的语音规范化规则应自动添加国家/地区代码（值12065551219中的第1个），则应保留国家/地区代码：

`-DialedNumber "2065551219"`

如果规则配置正确，则在将该号码转换为 Lync Server 使用的164格式时，它将自动添加国家/地区代码。

有关详细信息，请参阅 CsVoiceNormalizationRule cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果指定的语音规范化规则可以转换所提供的数字，则会在屏幕上显示已翻译的数字：

TranslatedNumber

\----------------

\+12065551219

如果测试失败，将返回一个空的已翻译数字：

TranslatedNumber

\----------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

如果 CsVoiceNormalizationRule 确实返回一个已转换的数字，这意味着指定的语音规范化规则无法将所提供的电话号码转换为 Lync Server 使用的格式为164的电子号码。 若要验证，请首先确保键入的电话号码正确无误。 例如，你希望你的语音规范化规则在翻译类似以下内容的数字时遇到问题：

`-DialedNumber "1"`

假设输入的号码正确，下一步应该是验证指定的规范化规则是否设计为处理该电话号码。 例如，一个规范化规则可能设计为处理格式12065551219，但第二个规则可能设计用于处理数字2065551219。 （这是与您的电话号码相同的电话号码，在最开始的地区代码1处减去。）若要返回有关语音规范化规则的详细信息，请运行如下所示的命令：

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

