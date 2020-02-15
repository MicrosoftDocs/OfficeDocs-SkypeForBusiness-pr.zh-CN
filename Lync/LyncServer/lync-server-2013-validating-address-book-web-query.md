---
title: Lync Server 2013：验证通讯簿 web 查询
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2db1e1e0a94a73c520a3beb0ea1375688b106cfc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a>在 Lync Server 2013 中验证通讯簿 web 查询

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsAddressBookWebQuery cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsAddressBookWebQuery cmdlet 使管理员能够验证用户是否可以使用通讯簿 Web 查询服务搜索特定的联系人。 运行 cmdlet 时，CsAddressBookWebQuery 将首先连接到要进行身份验证的 Web 票证服务。 如果身份验证成功，则 cmdlet 将连接到通讯簿 Web 查询服务，并搜索指定的联系人。 如果找到该联系人，则此 cmdlet 会尝试将该信息返回到本地计算机。 只有在所有这些步骤都可以完成时，测试才会被标记为成功。

有关详细信息，请参阅[CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) Cmdlet 的帮助文档。

</div>

<div>

## <a name="running-the-test"></a>运行测试

可以使用预配置的测试帐户（请参阅设置运行 Lync Server 测试的测试帐户）或已启用 Lync Server 的任何用户的帐户运行 CsAddressBookWebQuery cmdlet。 若要使用测试帐户运行此检查，只需指定 Lync Server 池的 FQDN 以及充当搜索目标的用户的 SIP 地址。 例如：

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

若要使用实际用户帐户运行此检查，必须创建一个包含有效用户名和密码的 Windows PowerShell 凭据对象。 然后，您必须在代码调用 CsAddressBookWebQuery 时包含该凭据对象和分配给该帐户的 SIP 地址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

有关详细信息，请参阅[CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果指定的用户可以连接到通讯簿服务并检索目标用户地址，则将返回类似于以下的输出，并将 Result 属性标记为成功：

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：06.2611356

误差

诊断

如果指定的用户无法连接，或者无法检索目标用户地址，则结果将显示为 "失败"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00:00:00

错误：通讯簿 Web 服务请求失败，响应代码为

NoEntryFound.

诊断

以前的输出表明由于找不到目标用户而导致测试失败。 您可以通过运行与以下内容类似的命令来确定是否已将有效的 SIP 地址传递给测试 CsAddressBookWebQuery：

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

如果 CsAddressBookWebQuery 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

包含 Verbose 参数时，CsAddressBookWebQuery 将返回它在检查指定用户登录到 Lync Server 的能力时所尝试的每个操作的分步帐户。 例如，以下输出表明，CsAddressBookWebQuery 能够连接到通讯簿服务，但无法找到目标 SIP 地址：

"QueryAddressBookWebService" 活动已启动。

呼叫通讯簿 Web 查询服务。 ABWS URL =

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

通讯簿查询异常：通讯簿 Web 服务请求失败，响应代码为 NoEntryFound。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

以下是测试 CsAddressBookWebQuery 可能失败的一些常见原因：

  - 您指定的用户帐户无效。 您可以通过运行与以下内容类似的命令来验证用户帐户是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 用户帐户有效，但当前没有为 Lync Server 启用该帐户。 若要验证是否已为 Lync Server 启用了用户帐户，请运行与以下内容类似的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 属性设置为 False，则表示当前尚未为 Lync Server 启用用户。

  - 目标用户可能不在通讯簿中。

  - 通讯簿可能未完全更新和复制。 您可以通过运行以下命令来强制更新组织中的所有通讯簿服务器：
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

