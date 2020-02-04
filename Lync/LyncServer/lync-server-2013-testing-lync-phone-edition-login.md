---
title: Lync Server 2013：测试 Lync Phone Edition 登录
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bfce8b1e034fd9772e10178366b0ed524fdbd55
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a>在 Lync Server 2013 中测试 Lync Phone Edition 登录

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
<p>使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsPhoneBootstrap cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsPhoneBootstrap cmdlet 使管理员能够验证特定用户（使用电话号码和分配给他/她的 PIN）是否可以从 Lync 2013 Phone 版兼容的设备登录到系统。 （实际不需要设备即可运行测试。）

为了让测试 CsPhoneBootstrap 进行检查，托管要测试的用户帐户的注册机构池必须使用 DHCP 才能发现。 若要确定注册机构是否以这种方式被发现，请使用 cmdlet CsRegistrarConfiguration 并检查 EnableDHCPServer 属性的值。 如果此属性设置为 False，则必须使用 CsRegistrarConfiguration 将属性值设置为 True，并使用 DHCP 使注册机构可发现。 也可以使用企业 DHCP 服务器并配置 Lync Server 特定的选项来执行此操作。

</div>

<div>

## <a name="running-the-test"></a>运行测试

若要运行 CsPhoneBootstrap cmdlet，必须至少为有效的 Lync 服务器用户提供电话号码和客户端个人识别码（PIN）。 例如，此命令将测试具有电话号码12065551219和引脚0712的用户的登录能力：

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

若要进行更全面的检查，您还可以包括用户的 SIP 地址。 在这种情况下，电话号码、客户端 PIN 和 SIP 地址必须全部有效才能使测试成功：

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

有关详细信息，请参阅[CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果指定用户能够连接到 Lync Server，你将收到类似于此的输出，结果属性标记为 "**成功"：**

TargetUri :https://atl-cs-001.litwareinc.com:443/CertProv/

CertProvisioningService

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：06.3981276

时发生

自检

如果指定的用户无法建立连接，则结果将显示为 "失败"，并且将在 "错误" 和 "诊断" 属性中记录其他信息：

TargetFqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00：00：04.1993845

错误：错误-Web 票证服务未收到任何响应。

自检

以前的输出表明测试失败的原因是 Web 票证服务未响应。 这可能是由于服务本身有问题，也可能是由于 SIP 地址、电话号码或客户 PIN 传递到了 CsPhoneBootstrap。 你可以使用类似下面的命令验证用户的 SIP 地址和电话号码：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

你可以通过使用命令验证用户是否具有有效的 PIN，如下所示：

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

如果 CsPhoneBootstrap 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

当包含 Verbose 参数时，CsPhoneBootstrap 将返回在检查指定用户登录到 Lync Server 的能力时尝试的每个操作的分步帐户。 例如，下面是一个失败登录的部分输出，其中包含错误 PIN 的会话：

将 PIN 验证与电话\\分机：12065551219针：0712配合使用

无法获取 web 票证

选中

\-Web 服务 url 有效且 web 服务正常运行

\-如果使用 PhoneNo\\PIN 进行身份验证，请确保它们与用户 uri 匹配

\-如果使用 NTLM\\Kerberos 身份验证，请确保提供有效的凭据

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是测试 CsPhoneBootstrap 可能失败的一些常见原因：

  - 您可能指定了一个无效的 SIP 地址。 你可以使用以下命令验证 SIP 地址是否正确：
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - 您可能指定了一个无效的 PIN 码。 虽然您无法检索用户的 PIN 码，但您可以通过使用类似下面的命令验证用户是否至少拥有 PIN 码：
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - 您可能指定了一个无效的电话号码。 你可以使用类似如下的命令验证用户的电话：
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - 注册机构池不是启用 DHCP 的。 若要确定注册机构池是否已为 DHCP 启用，请运行 CsRegistrarConfiguration cmdlet 并检查 EnableDHCPServer 属性的值。 例如：
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

