---
title: Lync Server 2013：验证通讯簿访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f18651cd75df62cf1d5f8c543d0e5c11361c7db
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a>在 Lync Server 2013 中验证通讯簿访问权限

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsAddressBookService cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsAddressBookService cmdlet 提供了一种方法，用于验证用户是否可以连接到通讯簿下载 Web 服务。 运行 cmdlet 时，CsAddressBookService 会连接到指定池上的通讯簿下载 Web 服务，并请求通讯簿文件的位置。 如果通讯簿下载 Web 服务提供该位置，则认为测试已成功。 如果请求被拒绝，则将测试视为失败。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsAddressBookService cmdlet 可以使用预配置的测试帐户（请参阅设置运行 Lync Server 测试的测试帐户）或已启用 Lync Server 的任何用户的帐户运行。 若要使用测试帐户运行此检查，您只需指定要测试的 Lync Server 池的完全限定域名（FQDN）。 例如：

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用实际用户帐户运行此检查，必须首先创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。 然后，您必须在调用 CsAddressBookService 时包含该凭据对象和分配给该帐户的 SIP 地址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

有关详细信息，请参阅[CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果指定用户可以连接到通讯簿服务，则将返回类似于以下的输出结果，并将 Result 属性标记为**成功**：

TargetUrihttps://lync-se.fabrikam.com:443/abs/handler

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：06.2260399

误差

诊断

如果指定用户无法建立此连接，则结果将显示为 "失败"，并将在 "错误" 和 "诊断" 属性中记录其他信息：

TargetUri

TargetFqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00:00:00

诊断： ErrorCode = 4005，Source = atl-cs-001.litwareinc.com，

原因 = 未对 SIP 启用目标 URI 或不为其启用目标 URI

尚.

Microsoft DiagnosticHeader

例如，由于指定的用户（即 "目标 URI"）不存在或尚未为 Lync Server 启用，因此上述输出表明测试失败。 您可以通过运行类似以下的命令来验证用户帐户是否有效，并验证是否提供了正确的 SIP 地址：

Get-csuser-Identity "sip:kenmyer@litwareinc.com" |选择-对象 SipAddress，已启用

如果 CsAddressBookService 失败，您可能需要重新运行测试，这一次包括 Verbose 参数：

CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose

当包含 Verbose 参数时，CsAddressBookService 将返回在检查指定用户登录到 Lync Server 的能力时所尝试的每个操作的分步帐户。 例如，以下示例输出显示，CsAddressBookService （至少在此示例中）可以下载通讯簿文件：

发送 Http GET 请求。

文件路径 =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

尝试次数 = 1

TimeOut （毫秒） = 60000

成功下载了 ABS 文件https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

以下是测试 CsAddressBookService 可能失败的一些常见原因：

  - 您指定的用户帐户无效。 您可以通过运行与以下内容类似的命令来验证用户帐户是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 用户帐户有效，但当前没有为 Lync Server 启用该帐户。 若要验证是否已为 Lync Server 启用了用户帐户，请运行与以下内容类似的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 属性设置为 False，则表示当前尚未为 Lync Server 启用用户。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

