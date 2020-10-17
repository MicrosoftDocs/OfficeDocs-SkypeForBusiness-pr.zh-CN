---
title: Lync Server 2013：测试 Lync 客户端身份验证
description: Lync Server 2013：测试 Lync 客户端身份验证。
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
ms.openlocfilehash: 03694b7fd56d7847d8d493304b97af335d2a5b4d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560578"
---
# <a name="testing-lync-client-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中测试 Lync 客户端身份验证

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsClientAuth cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

Test-CsClientAuth cmdlet 使您能够确定用户是否可以使用客户端证书登录 Lync Server，可以运行 Test-CsClientAuth cmdlet。 呼叫 Test-CsClientAuth 之后，cmdlet 将与证书提供服务联系，并下载一份指定用户的任意客户端证书。 如果可以找到并下载客户端证书，Test-CsClientAuth 将尝试使用该证书进行登录。 如果登录成功，则 Test-CsClientAuth 将注销并报告测试成功。 如果无法找到或下载证书，或者 cmdlet 无法使用该证书登录，则 Test-CsClientAuth 将报告测试失败。

</div>

<div>

## <a name="running-the-test"></a>运行测试

使用为 Lync Server 启用的任何用户的帐户运行 Test-CsClientAuth cmdlet。 若要使用实际用户帐户运行此检查，必须首先创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。 然后，必须在系统调用 CsClientAuth 时包含该凭据对象和分配给该帐户的 SIP 地址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

有关详细信息，请参阅 [CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果指定用户可以使用客户端证书登录到 Lync Server，则会收到类似于以下的输出，并将 Result 属性标记为 " **成功"：**

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：06.8630376

误差

诊断

如果指定的用户无法登录，则结果将显示为 "失败"，并将在 "错误和诊断" 属性中记录其他信息：

TargetFqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00：00：03.3645259

错误：无法为给定用户下载 CS 证书。 检查是否

提供的 uri 和凭据是正确的。

诊断

例如，由于无法为指定用户找到有效的客户端证书，因此以前的输出表明测试失败。 您可以通过运行命令来返回颁发给用户的客户端证书的列表，如下所示：

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

如果 Test-CsClientAuth 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

包含 Verbose 参数时，Test-CsClientAuth 将返回其在检查指定用户登录到 Lync Server 的能力时所尝试的每个操作的分步帐户。 例如：

尝试为用户下载 CS 证书： kenmyer@litwareinc.com 终结点： STEpid

Web 服务 url： https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc

无法从 web 服务下载 CS 证书。

复选

\- Web 服务 url 有效且 web 服务正常运行

\-如果使用 PhoneNo \\ \\ Pin 进行身份验证，请确保它们与用户 uri 匹配

\- 如果使用 NTLM \\ Kerberos 身份验证，请确保提供有效的凭据

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是 Test-CsClientAuth 可能失败的一些常见原因：

  - 您指定的用户帐户无效。 您可以通过运行与以下内容类似的命令来验证用户帐户是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 用户帐户有效，但当前未对 Lync Server 启用该帐户。 若要验证是否已为 Lync Server 启用用户帐户，请运行与以下内容类似的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。

  - 测试用户可能没有有效的客户端证书。 您可以使用类似如下的命令返回有关分配给用户的客户端证书的信息：
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

