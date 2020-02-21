---
title: Lync Server 2013：检查 Lync Server 2013 服务器证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11c5e545bc00de48fa5590dc8c4b119a46ffe9e0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a>检查 Lync Server 2013 服务器证书

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-11-01_


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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Set-cscertificate cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

Set-cscertificate cmdlet 使您能够检索有关每个 Lync Server 证书的信息。 这一点尤其重要，因为证书具有内置到期日期。 例如，私下颁发的证书通常在12个月后过期。 如果你的任何 Lync Server 证书过期，则在续订或替换证书之前，你将失去随附的功能。

</div>

<div>

## <a name="running-the-test"></a>运行测试

若要返回有关每个 Lync Server 证书的信息，请运行以下命令：

`Get-CsCertificate`

或者，您可以根据到期日期筛选返回的证书信息。 例如，以下命令将返回的数据限制为过期的证书（不能在2014年6月1日之后使用）：

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

有关详细信息，请参阅 Set-cscertificate cmdlet 的帮助文档。

请注意，尽管存在 CsCertificateConfiguration cmdlet，但对管理员来说并不是很有用。 （相反，该 cmdlet 主要由证书向导使用。）尽管 cmdlet 可以正常运行，但返回的信息的价值最少，如以下输出示例中所示：

指纹使用

\---------- ---

A9D51A2911C74FABFF7F2A8A994B20857D399107 默认值

</div>

<div>

## <a name="reviewing-the-output"></a>查看输出

Set-cscertificate cmdlet 将为每个 Lync Server 证书返回类似以下内容的信息：

颁发者： CN = FabrikamCA

NotAfter： 12/28/2015 3:35:41 PM

NotBefore： 1/2/2014 12:49:37 PM

SerialNumber：611BB01200000000000C

Subject： CN = LYNC-SE.fabrikam.com

AlternativeNames： {sip.fabrikam.com，LYNC-SE.fabrikam.com，

meet.fabrikam.com、admin.fabrikam.com ...}

指纹： A9D51A2911C74FABFF7F2A8A994B20857D399107

使用： Default

通常，与 Lync Server 证书相关的主要问题涉及日期和时间，例如证书生效的时间（NotBefore）或过期（NotAfter）。 由于这些日期和时间非常重要，因此您可能需要将返回的数据限制为 "证书使用"、"证书序列号" 和 "证书到期日期" 等信息。然后，您可以快速查看所有证书以及它们何时过期。 若要仅返回该信息，请使用命令以及选项，如下所示：

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

该命令将返回与以下内容类似的数据，其中的证书按其到期日期顺序排序：

使用 SerialNumber NotAfter

\--- ------------ --------

默认 611BB01200000000000C 12/28/2015 3:35:41 PM

WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM

WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM

如果存在证书问题，您可能需要查看为证书配置的 AlternativeNames。 乍一看，这似乎是一个问题。 默认情况下，根据控制台窗口的大小，Set-cscertificate 可能无法显示所有名称：

AlternativeNames： {sip.fabrikam.com，LYNC.fabrikam.com，

meet.fabrikam.com、fabrika ...}

若要查看分配给证书的所有替代名称，请使用与此类似的命令：

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

应在证书上显示所有备用名称：

sip.fabrikam.com

LYNC.fabrikam.com

meet.fabrikam.com

admin.fabrikam.com

LYNC-SE.fabrikam.com

Dialin.fabrikam.com

</div>

<div>

## <a name="see-also"></a>另请参阅


[Set-cscertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

