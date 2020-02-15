---
title: Lync Server 2013：测试电话拨入式会议会话
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d83d3c3fe933a4538d9c2508668497af42c3340
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a>在 Lync Server 2013 中测试电话拨入式会议会话

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-csdialinconferencing cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

Test-csdialinconferencing cmdlet 验证用户是否可以参与电话拨入式会议。 测试-Test-csdialinconferencing 通过尝试将测试用户登录到系统来工作。 如果登录成功，则 cmdlet 将使用用户的凭据和权限来尝试所有可用的电话拨入式会议访问号码。 将记录每个拨入尝试的成功或失败情况，然后将从 Lync Server 注销测试用户。测试 Test-csdialinconferencing 仅验证是否可以建立适当的连接。 Cmdlet 实际上不会进行任何电话呼叫，也不会创建任何其他用户可以加入的电话拨入式会议。

</div>

<div>

## <a name="running-the-test"></a>运行测试

可以使用预配置的测试帐户（请参阅设置运行 Lync Server 测试的测试帐户）或已启用 Lync Server 的任何用户的帐户运行 Test-csdialinconferencing cmdlet。 若要使用测试帐户运行此检查，只需指定要测试的 Lync Server 池的 FQDN 即可。 例如：

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

若要使用实际用户帐户运行此检查，必须创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。 然后，必须将该凭据对象和帐户 SIP 地址包括在调用的 Test-csdialinconferencing：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

有关详细信息，请参阅[test-csdialinconferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果指定用户可以登录到 Lync Server，然后使用其中一个可用的电话拨入式会议访问号码进行连接，则会收到类似于以下内容的输出，并将 Result 属性标记为 "**成功"：**

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：06.8630376

误差

诊断

如果指定的用户无法建立此连接，则结果将显示为 "失败"，并且将在 "错误" 和 "诊断" 属性中记录其他信息：

TargetFqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00:00:00

错误：登录被拒绝。 检查正确的凭据是否

正在使用，帐户处于活动状态。

内部异常： NegotiateSecurityAssociation 失败，错误：-

2146893044

诊断

以前的输出指示已拒绝测试用户对 Lync Server 本身的访问。 这通常意味着传递给 Test-Test-csdialinconferencing 的用户凭据无效。 反过来，您应该重新创建 Windows PowerShell 凭据对象。 虽然您可以检索用户帐户的密码，但您可以通过使用类似如下的命令来验证 SIP 地址：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

以下是测试 Test-csdialinconferencing 可能失败的一些常见原因：

  - 您指定的用户帐户无效。 您可以通过运行与以下内容类似的命令来验证用户帐户是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 用户帐户有效，但当前未对 Lync Server 启用该帐户。 若要验证是否已为 Lync Server 启用用户帐户，请运行与以下内容类似的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。

  - 您可能有一个不正确的电话拨入式会议访问号码。 您可以使用以下命令返回当前配置的电话拨入式会议访问号码列表：
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

