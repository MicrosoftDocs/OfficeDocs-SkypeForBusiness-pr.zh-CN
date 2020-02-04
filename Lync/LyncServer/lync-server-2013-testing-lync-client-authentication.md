---
title: Lync Server 2013：测试 Lync 客户端身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e24f579a4fcaca2651c0225b515241db00ff990
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-client-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中测试 Lync 客户端身份验证

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
<p>使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsClientAuth cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsClientAuth cmdlet 使你能够确定用户是否可以使用客户端证书登录 Lync 服务器，你可以运行 CsClientAuth cmdlet。 在调用 CsClientAuth 后，cmdlet 将联系证书预配服务，并为指定的用户下载任何客户端证书的副本。 如果可以找到并下载客户端证书，CsClientAuth 将尝试使用该证书登录。 如果登录成功，CsClientAuth 将注销并报告测试已成功。 如果无法找到或下载证书，或者 cmdlet 无法使用该证书登录，则测试 CsClientAuth 将报告测试失败。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsClientAuth cmdlet 是使用已启用 Lync Server 的任何用户的帐户运行的。 若要使用实际用户帐户运行此检查，必须首先创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。 然后，在系统调用 Test-CsClientAuth 时，必须包含该凭据对象和分配给该帐户的 SIP 地址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

有关详细信息，请参阅[CsClientAuth](http://technet.microsoft.com/en-us/library/gg398712\(v=ocs.14\).aspx) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果指定用户可以使用客户端证书登录到 Lync 服务器，你将收到与此类似的输出，结果属性标记为**成功：**

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：06.8630376

时发生

自检

如果指定的用户无法登录，则结果将显示为 "失败"，并且将在 "错误" 和 "诊断" 属性中记录其他信息：

TargetFqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00：00：03.3645259

错误：无法下载给定用户的 CS 证书。 检查是否

提供的 uri 和凭据是正确的。

自检

例如，以前的输出声明由于无法为指定用户找到有效的客户端证书而导致测试失败。 你可以通过运行命令来返回颁发给用户的客户端证书的列表，如下所示：

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

如果 CsClientAuth 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

当包含 Verbose 参数时，CsClientAuth 将返回在检查指定用户登录到 Lync Server 的能力时尝试的每个操作的分步帐户。 例如：

尝试下载用户的 CS 证书： kenmyer@litwareinc.com 终结点： STEpid

Web 服务 url：https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc

无法从 web 服务下载 CS 证书。

选中

\-Web 服务 url 有效且 web 服务正常运行

\-如果使用 PhoneNo\\\\Pin 进行身份验证，请确保它们与用户 uri 匹配

\-如果使用 NTLM\\Kerberos 身份验证，请确保提供有效的凭据

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是测试 CsClientAuth 可能失败的一些常见原因：

  - 您指定的用户帐户无效。 你可以通过运行类似如下所示的命令来验证用户帐户是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 用户帐户有效，但当前没有为 Lync Server 启用该帐户。 若要验证是否已启用 Lync Server 的用户帐户，请运行类似如下的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。

  - 测试用户可能没有有效的客户端证书。 你可以使用类似下面的命令返回有关分配给用户的客户端证书的信息：
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

