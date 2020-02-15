---
title: Lync Server 2013：测试执行组 IM 的能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97562d82f751280ec4d1a8f154af2b85ed2be128
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a>在 Lync Server 2013 中测试组 IM 的能力

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsGroupIM cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsGroupIM cmdlet 验证组织中的用户是否可以执行组即时消息会话。 运行 CsGroupIM 时，cmdlet 会尝试将一对测试用户登录到 Lync Server。 如果登录成功，Test-CsGroupIM 将使用第一个测试用户创建新会议，然后邀请第二个用户加入会议。 交换消息之后，这两个用户断开与系统的连接。 请注意，这一切在没有任何用户交互的情况下发生，而不会影响任何实际用户。 例如，假设测试帐户 sip:kenmyer@litwareinc.com 与具有实际 Lync Server 帐户的真实用户相对应。 在这种情况下，执行测试的过程中不会对真实的 Ken Myer 造成任何中断。 例如，即使从系统注销 Ken Myer 的测试帐户，Ken Myer 本人仍将保持已登录状态。 同样，实际 Ken Myer 不会收到加入会议的邀请。 该邀请将发送到测试帐户并由其接受。

有关详细信息，请参阅[CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) Cmdlet 的帮助文档。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsGroupIM cmdlet 可使用一对预配置的测试帐户（请参阅设置运行 Lync Server 测试的测试帐户）或任何两个已启用 Lync Server 的用户的帐户运行。 若要使用测试帐户运行此检查，只需指定要测试的 Lync Server 池的 FQDN 即可。 例如：

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用实际用户帐户运行此检查，必须为每个帐户创建两个 Lync Server 命令行管理程序凭据对象（包含帐户名和密码的对象）。 在调用 CsGroupIM 时，必须包括这些凭据对象和两个帐户的 SIP 地址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

有关详细信息，请参阅[CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果两个用户可以完成组即时消息会话，您将收到与以下内容类似的输出，其中结果属性标记为**成功：**

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：06.3812203

误差

诊断

如果两个用户无法完成即时消息会话，则结果将显示为 "失败"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：

TargetFqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00:00:00

错误：未找到404

诊断： ErrorCode = 4005，Source = atl-cs-001.litwareinc.com，

原因 = 未对 SIP 启用目标 URI 或不为其启用目标 URI

尚.

Microsoft DiagnosticHeader

由于帐户不存在或尚未为 Lync Server 启用用户，因此以前的输出表明测试失败，因为其中至少有一个测试帐户无效。 您可以通过运行与以下内容类似的命令来验证帐户是否存在，以及帐户是否已启用 nm-第 14-第3级：

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

如果 CsGroupIM 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

包含 Verbose 参数时，CsGroupIM 将返回其在检查指定用户是否参与组即时消息会话的能力时所尝试的每个操作的分步帐户。 例如，如果您的测试失败，并且您被告知一个或多个用户帐户无效，则可以使用 Verbose 参数重新运行测试并确定哪个用户帐户无效：

发送注册请求：

 目标 Fqdn = atl-cs-001.litwareinc.com

 用户 SIP 地址 = sip:kenmyer@litwareinc.com

 寄存器端口 = 5061

已选择身份验证类型 "IWA"。

"登录被拒绝" 异常。 检查是否正在使用正确的凭据，以及帐户是否处于活动状态。

您可以看到，在此示例中，拥有 SIP 地址 sip:kenmyer@litwareinc.com 的用户无法登录。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

以下是测试 CsGroupIM 可能失败的一些常见原因：

  - 您指定了不正确的用户帐户。 您可以通过运行与以下内容类似的命令来验证用户帐户是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 用户帐户有效，但当前未对 Lync Server 启用该帐户。 若要验证是否已为 Lync Server 启用了用户帐户，请运行与以下内容类似的命令：
    
    Get-csuser "sip:kenmyer@litwareinc.com" |选择-对象已启用
    
    如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。

  - 即时消息服务可能不可用。 使用 Lync Server，可以配置系统，以便在无法访问存档数据库时，即时消息不可用。 您可以通过运行与以下内容类似的命令来验证这一点：
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    如果将 BlockOnArchiveFailure 设置为 True，则应确定存档数据库是否可用。 您可以使用以下命令返回存档数据库的位置：
    
        Get-CsService -ArchivingDatabase

  - 存档服务器可能不可用。 您可以使用以下命令检索存档服务器的 FQDN：
    
        Get-CsService -ArchivingServer
    
    然后，可以 ping 相应的服务器以验证其是否可用。 例如：
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

