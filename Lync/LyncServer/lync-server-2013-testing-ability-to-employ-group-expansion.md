---
title: Lync Server 2013：测试使用组扩展的能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d79c5432bc2efca0d3a958d3837793eaf227b251
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a>测试在 Lync Server 2013 中使用组扩展的能力

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
<p>使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsGroupExpansion cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsGroupExpansion cmdlet 使你可以确定组扩展是否在你的组织内工作。 启用组扩展后，用户将通讯组配置为联系人。 这意味着，这些用户可以通过将邮件寻址到组而不是该组的单个成员来向所有组成员发送相同的即时消息。 组扩展使你能够快速轻松地查看所有组成员及其当前状态。

使用 CsGroupExpansion cmdlet，你可以使用组的电子邮件地址指定 Active Directory 通讯组。 CsGroupExpansion 然后使用组扩展检索组成员身份，并将检索到的列表与您提供的组电子邮件地址的成员身份进行比较。 如果两个列表匹配，则组扩展正常工作。 请注意，你可以通过两种方式测试组扩展：测试服务本身或测试关联的 web 服务。

有关详细信息，请参阅[CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) Cmdlet 的帮助文档。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsGroupExpansion cmdlet 可以使用预配置的测试帐户运行（请参阅设置运行 Lync Server 测试的测试帐户）或已启用 Lync Server 的任何用户的帐户。 若要使用测试帐户运行此检查，只需指定要测试的 Lync Server 池的 FQDN 和有效通讯组的电子邮件地址。 例如：

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

若要使用实际用户帐户运行此检查，必须首先创建一个 Lync Server 凭据对象，其中包含帐户名称和密码。 然后，在系统调用 Test-CsGroupExpansion 时，必须包含该凭据对象和分配给该帐户的 SIP 地址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

有关详细信息，请参阅[CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果指定的用户可以使用组扩展，则会收到与以下内容类似的输出：结果属性标记为**成功：**

TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：01.1234976

时发生

自检

如果指定用户不能使用组扩展，则结果将显示为 "失败"，并且将在 "错误" 和 "诊断" 属性中记录其他信息：

TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00:00:00

时发生

自检

测试-CsGroupExpansion：终结点无法注册。 有关特定原因，请参阅错误代码。

以前的输出表明测试失败的原因是指定的用户无法向 Lync 服务器注册。 如果测试帐户不存在或尚未为 Lync Server 启用，则通常会发生这种情况。 你可以通过运行类似如下所示的命令来验证帐户是否存在，并确定是否已启用 nm-ocs-第14级帐户：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

如果 CsGroupExpansion 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

当包含 Verbose 参数时，CsGroupExpansion 将返回在检查指定用户登录到 Lync Server 的能力时尝试的每个操作的分步帐户。 例如，以下输出表明找不到指定的通讯组：

正在尝试获取 web 票证。

Web 服务 url：https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc

使用 NTLM/Kerb auth。

GetWebTicketActivity 已完成。

已开始 "VerifyDistributionList" 活动。

DLX Web 服务响应状态为： NotFound。

"VerifyDistributionList" 活动在 "0.2597923" 秒内完成。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是测试 CsGroupExpansion 可能失败的一些常见原因：

  - 您指定了无效的用户帐户。 你可以通过运行类似如下所示的命令来验证用户帐户是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 用户帐户有效，但当前没有为 Lync Server 启用该帐户。 若要验证是否已启用 Lync Server 的用户帐户，请运行类似如下的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。

  - 组扩展可能已禁用。 可以关闭组扩展。 如果组扩展已禁用，则 CsGroupExpansion cmdlet 将失败。 若要确定是否已启用组扩展，请使用类似下面的命令：
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

