---
title: 'Lync Server 2013: 验证通讯簿访问'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 233ad9804ea0f9ddd1075ea01bf7a4c8f35da819
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a>在 Lync Server 2013 中验证通讯簿访问

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-06-05_


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
<td><p>当使用 Lync Server 命令行管理程序在本地运行时, 用户必须是 RTCUniversalServerAdmins 安全组的成员。</p>
<p>使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsAddressBookService cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsAddressBookService cmdlet 为你提供一种验证用户是否可以连接到通讯簿下载 Web 服务的方法。 运行 cmdlet 时, CsAddressBookService 将连接到指定池上的通讯簿下载 Web 服务, 并请求通讯簿文件的位置。 如果 "通讯簿" 下载 Web 服务提供该位置, 则该测试视为成功。 如果请求被拒绝, 则测试被视为失败。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsAddressBookService cmdlet 可以使用预配置的测试帐户运行 (请参阅设置运行 Lync Server 测试的测试帐户) 或已为 Lync Server 启用的任何用户的帐户。 若要使用测试帐户运行此检查, 只需指定正在测试的 Lync Server 池的完全限定的域名 (FQDN)。 例如：

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用实际用户帐户运行此检查, 必须首先创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。 然后, 在调用 Test-CsAddressBookService 时, 必须包含该凭据对象和分配给该帐户的 SIP 地址:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

有关详细信息, 请参阅[CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果指定用户能够连接到通讯簿服务, 则会返回与此类似的输出, 结果属性标记为**成功**:

TargetUri :https://lync-se.fabrikam.com:443/abs/handler

TargetFqdn: atl-cs-001.litwareinc.com

结果: 成功

延迟:00:00: 06.2260399

时发生

自检

如果指定用户无法进行此连接, 则结果将显示为 "失败", 并且将在 "错误" 和 "诊断" 属性中记录其他信息:

TargetUri :

TargetFqdn: atl-cs-001.litwareinc.com

结果: 失败

延迟: 00:00:00

诊断: ErrorCode = 4005, Source = atl-cs-001.litwareinc.com,

原因 = 没有为 SIP 启用目标 URI, 或者没有为其启用目标 URI

并存.

Microsoft DiagnosticHeader

例如, 由于指定的用户 (即 "目标 URI") 不存在或尚未为 Lync Server 启用, 因此上述输出表明测试失败。 你可以验证用户帐户是否有效, 并通过运行类似的命令验证你提供的 SIP 地址是否正确:

Move-csuser-Identity "sip:kenmyer@litwareinc.com" |选择-对象 SipAddress, 已启用

如果测试 CsAddressBookService 失败, 您可能需要重新运行测试, 这一次包括 Verbose 参数:

Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose

当包含 Verbose 参数时, CsAddressBookService 将返回它在检查指定用户登录到 Lync Server 的能力时尝试的每个操作的分步帐户。 例如, 此示例输出显示, CsAddressBookService 在此示例中至少可以下载通讯簿文件:

发送 Http GET 请求。

文件路径 =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

尝试次数 = 1

TimeOut (毫秒) = 60000

已成功下载 ABS 文件https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是测试 CsAddressBookService 可能失败的一些常见原因:

  - 您指定了无效的用户帐户。 你可以通过运行类似如下所示的命令来验证用户帐户是否存在:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 用户帐户有效, 但当前未为 Lync Server 启用该帐户。 若要验证是否已启用 Lync Server 的用户帐户, 请运行类似以下内容的命令:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 属性设置为 False, 则表示当前尚未为 Lync Server 启用用户。

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

