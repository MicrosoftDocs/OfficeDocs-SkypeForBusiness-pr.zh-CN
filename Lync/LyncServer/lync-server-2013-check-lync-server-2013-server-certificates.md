---
title: 'Lync Server 2013: 检查 Lync Server 2013 服务器证书'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dced86c93b7ec35cb410601f1d72720e25d156b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a>检查 Lync Server 2013 服务器证书

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-11-01_


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
<p>使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsCertificate cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsCertificate cmdlet 使你能够检索有关每个 Lync 服务器证书的信息。 这一点尤其重要, 因为证书具有内置的到期日期。 例如, 私下颁发的证书通常会在12个月后过期。 如果任何 Lync 服务器证书过期, 则将丢失随附的功能, 直到续订或替换该证书。

</div>

<div>

## <a name="running-the-test"></a>运行测试

若要返回每个 Lync 服务器证书的信息, 只需运行以下命令:

`Get-CsCertificate`

或者, 你可以根据到期日期筛选返回的证书信息。 例如, 此命令将返回的数据限制为过期的证书 (不能在2014年6月1日之后使用):

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

有关详细信息, 请参阅 CsCertificate cmdlet 的帮助文档。

请注意, 尽管存在 CsCertificateConfiguration cmdlet, 但对管理员来说它并不是非常有用。 (相反, 该 cmdlet 主要由证书向导使用。)虽然此 cmdlet 有效, 但它返回的信息是最小值, 如以下输出示例中所示:

指纹使用

\---------- ---

A9D51A2911C74FABFF7F2A8A994B20857D399107 默认值

</div>

<div>

## <a name="reviewing-the-output"></a>查看输出

CsCertificate cmdlet 针对每个 Lync 服务器证书返回类似于以下内容的信息:

颁发者: CN = FabrikamCA

NotAfter: 12/28/2015 3:35:41 PM

NotBefore: 1/2/2014 12:49:37 PM

SerialNumber: 611BB01200000000000C

主题: CN = LYNC-SE.fabrikam.com

AlternativeNames: {sip.fabrikam.com, LYNC-SE.fabrikam.com,

meet.fabrikam.com、admin.fabrikam.com ...}

指纹: A9D51A2911C74FABFF7F2A8A994B20857D399107

使用: 默认

通常, 与 Lync Server 证书有关的主要问题涉及日期和时间, 例如当证书生效 (NotBefore) 或过期时 (NotAfter)。 由于这些日期和时间非常重要, 因此你可能希望将返回的数据限制为 "证书使用"、"证书序列号" 和 "证书到期日期" 等信息。然后, 你可以快速查看所有证书以及它们何时过期。 若要仅返回该信息, 请使用该命令以及选项, 如下所示:

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

该命令返回与以下内容类似的数据, 其中的证书按其到期日期顺序排序:

使用 SerialNumber NotAfter

\--- ------------ --------

默认 611BB01200000000000C 12/28/2015 3:35:41 PM

WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM

WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM

如果存在证书问题, 可能需要查看为证书配置的 AlternativeNames。 乍一看, 这似乎是一个问题。 默认情况下, CsCertificate 可能无法显示所有名称, 具体取决于您的控制台窗口的大小:

AlternativeNames: {sip.fabrikam.com, LYNC.fabrikam.com,

meet.fabrikam.com、fabrika ...}

若要查看分配给证书的所有替代名称, 请使用类似于下面的命令:

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

这应显示证书上的所有备用名称:

sip.fabrikam.com

LYNC.fabrikam.com

meet.fabrikam.com

admin.fabrikam.com

LYNC-SE.fabrikam.com

Dialin.fabrikam.com

</div>

<div>

## <a name="see-also"></a>另请参阅


[Get-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

