---
title: Lync Server 2013：检查对电话号码的中继配置
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
ms.openlocfilehash: 6bf9d53d8702fbd9e63ec05af2c4942538f7298e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a>在 Lync Server 2013 中检查对电话号码的中继配置

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Remove-cstrunkconfiguration cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

SIP 中继将 Lync Server 内部企业语音网络连接到以下任一项：

  - 公共交换电话网络（PSTN）。

  - IP-公共交换机（PBX）。

  - 会话边界控制器（SBC）。

Remove-cstrunkconfiguration cmdlet 验证电话号码（由用户拨打）是否可以转换为 e.164 网络，并通过指定的 SIP 中继进行路由。

</div>

<div>

## <a name="running-the-test"></a>运行测试

若要运行 Remove-cstrunkconfiguration cmdlet，必须首先使用 Remove-cstrunkconfiguration cmdlet 检索 SIP 中继配置设置的实例;然后，将该实例通过管道传递到 Remove-cstrunkconfiguration：

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

运行 Remove-cstrunkconfiguration，而不事先运行 Remove-cstrunkconfiguration 将不起作用。 例如，在不返回任何数据的情况下，此命令将失败：

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

如果您有多个 SIP 中继配置设置集合，则可以使用与以下类似的命令来针对同一电话号码测试每个集合：

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

有关详细信息，请参阅 Remove-cstrunkconfiguration cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果 Remove-cstrunkconfiguration 可以呼叫已拨打的号码，则转换的电话号码（以. 164 格式）和用于转换该电话号码的规则都将显示在屏幕上：

TranslatedNumber MatchingRule

\---------------- ------------

\+12065551219全球/雷德蒙

如果测试失败，Remove-cstrunkconfiguration 将返回空的属性值：

TranslatedNumber MatchingRule

\---------------- ------------

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

如果 Remove-cstrunkconfiguration 不返回一个与之匹配的值，这通常意味着要测试的中继配置设置没有一个传出呼叫号码转换规则，可以将拨打的号码转换为 e.164 格式。 若要检索分配给中继配置设置集合的转换规则，可以使用类似如下的语法：

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

对于每个转换规则，返回类似于以下内容的信息：

说明：不带国家/地区代码或区号的电话号码。

模式： ^\\+ （\\d\*） $

`Translation : $1`

名称： NoAreaCode

此时，您需要检查 Pattern 属性的值（它是一个[正则表达式](https://go.microsoft.com/fwlink/?linkid=400464)字符串），以查看是否有任何转换规则配置为用于处理所拨打的号码。 如果不是，则必须更改现有规则之一（CsOutboundTranslationRule）或使用 CsOutboundTranslationRule cmdlet 将新规则添加到集合中。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Test-Remove-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

