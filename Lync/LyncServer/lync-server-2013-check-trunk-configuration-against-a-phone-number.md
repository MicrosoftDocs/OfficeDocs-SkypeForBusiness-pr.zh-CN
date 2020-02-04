---
title: Lync Server 2013：对照电话号码检查中继配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7932e4cb7a7a9d74b945dcd60c2a1211ca5af694
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a>对照 Lync Server 2013 中的电话号码检查中继配置

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
<p>使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 New-cstrunkconfiguration cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

SIP 中继将 Lync Server 内部企业语音网络连接到以下任何内容：

  - 公共交换电话网络（PSTN）。

  - IP-公共分支交换（PBX）。

  - 会话边框控制器（SBC）。

New-cstrunkconfiguration cmdlet 验证电话号码（由用户拨出）是否可以转换为 E-164 网络，并通过指定的 SIP 主干进行路由。

</div>

<div>

## <a name="running-the-test"></a>运行测试

若要运行 New-cstrunkconfiguration cmdlet，必须首先使用 New-cstrunkconfiguration cmdlet 检索 SIP 中继配置设置的实例;然后，将该实例管道传送到 Test-New-cstrunkconfiguration：

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

运行 Test-New-cstrunkconfiguration 而不事先运行 New-cstrunkconfiguration 将不起作用。 例如，此命令将失败，且不返回任何数据：

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

如果您有多个 SIP 中继配置设置集合，则可以使用如下所示的命令在每个集合中测试相同的电话号码：

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

有关详细信息，请参阅 New-cstrunkconfiguration cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果 New-cstrunkconfiguration 可以拨打电话号码，则已翻译的电话号码（以 E：164格式）和用于转换该电话号码的规则都将显示在屏幕上：

TranslatedNumber MatchingRule

\---------------- ------------

\+12065551219全球/雷德蒙

如果测试失败，New-cstrunkconfiguration 将返回空属性值：

TranslatedNumber MatchingRule

\---------------- ------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

如果 New-cstrunkconfiguration 不返回一个匹配项，这通常意味着正在测试的 trunk 配置设置没有传出呼叫号码转换规则，可用于将已拨号码转换为 E-164 格式。 若要检索分配给主干配置设置集合的转换规则，可以使用类似下面的语法：

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

这将针对每个翻译规则返回类似于以下内容的信息：

说明：没有国家/地区代码或区号的电话号码。

模式： ^\\+ （\\d\*） $

`Translation : $1`

名称： NoAreaCode

此时，你检查 Pattern 属性的值（这是一个[正则表达式](http://go.microsoft.com/fwlink/?linkid=400464)字符串），以查看是否有任何翻译规则配置为处理已拨号码。 如果不是，你将必须更改现有规则之一（Set-CsOutboundTranslationRule）或使用 CsOutboundTranslationRule cmdlet 向集合添加新规则。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

