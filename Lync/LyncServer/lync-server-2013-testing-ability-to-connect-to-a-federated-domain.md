---
title: Lync Server 2013：测试连接到联盟域的能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82c44cf7cff78fc93054679ae1bc4c66bc6b4c40
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42016233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a>从 Lync Server 2013 中连接到联盟域的测试能力

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsFederatedPartner cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

Test-CsFederatedPartner 验证您能否连接到联盟伙伴的域。 若要验证与某个域的连接，该域必须列在允许（联合）域的集合中。 您可以使用以下命令检索 "允许的域" 列表中的域列表：

    Get-CsAllowedDomain

有关详细信息，请参阅[CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) Cmdlet 的帮助文档。

</div>

<div>

## <a name="running-the-test"></a>运行测试

FederatedPartner cmdlet 需要以下两条信息：边缘服务器的 FQDN 和联盟伙伴的 FQDN。 例如，以下命令将测试连接到域 contoso.com 的能力：

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

通过此命令，您可以测试与当前允许的域列表中的所有域的连接：

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

有关详细信息，请参阅[CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果可以联系指定的域，则会收到类似于以下内容的输出，并将 Result 属性标记为**成功：**

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00:00:00

误差

诊断

如果无法联系指定的域，则结果将显示为 "失败"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：

TargetFqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00:00:00

错误：504，服务器超时

诊断： ErrorCode = 2，Source = atl-cs-litwareinc，Reason = 参阅

响应代码和原因短语。

Microsoft DiagnosticHeader

例如，以前的输出表明测试因服务器超时错误而失败。 这通常指示网络连接问题或联系边缘服务器时出现问题。

如果 CsFederatedPartner 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

以下是测试 CsFederatedPartner 可能失败的一些常见原因：

  - 边缘服务器可能不可用。 您可以使用以下命令来使用您的边缘服务器的 Fqdn：
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    然后，可以 ping 每台边缘服务器以验证是否可以通过网络访问它。 例如：
    
        ping atl-edge-001.litwareinc.com

  - 指定的域可能未列在允许的域列表中。 若要验证已添加到允许的域列表中的域，请使用以下命令：
    
        Get-CsAllowedDomain
    
    如果您想要查看阻止用户与之通信的域的列表，请使用以下命令：
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

