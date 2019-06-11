---
title: 'Lync Server 2013: 测试待办事项组 IM 的能力'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c371db385b29f68aa8cc9280a901d095c43f2ac2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a>在 Lync Server 2013 中进行群组 IM 测试的功能

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
<p>使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsGroupIM cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsGroupIM cmdlet 验证组织中的用户是否可以执行群组即时消息会话。 运行 Test CsGroupIM 时, cmdlet 会尝试登录一对 Lync Server 的测试用户。 如果成功, CsGroupIM 将使用第一个测试用户创建新会议, 然后邀请第二位用户加入会议。 在交换邮件之后, 两个用户都将从系统断开连接。 请注意, 所有这些操作都不需要用户交互, 并且不会影响任何实际用户。 例如, 假设测试帐户 sip:kenmyer@litwareinc.com 对应于具有真实 Lync 服务器帐户的真实用户。 在这种情况下, 将在不中断真正的 Ken Myer 的情况下执行测试。 例如, 即使 Ken Myer 测试帐户从系统注销, 此人仍将保持登录状态。 同样, 真正的 Ken Myer 将不会收到加入会议的邀请。 该邀请将发送给并接受测试帐户。

有关详细信息, 请参阅[CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) Cmdlet 的帮助文档。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsGroupIM cmdlet 可以使用一对预配置的测试帐户运行 (请参阅设置运行 Lync Server 测试的测试帐户) 或已启用 Lync Server 的任何两个用户的帐户。 若要使用测试帐户运行此检查, 只需指定正在测试的 Lync Server 池的 FQDN。 例如：

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用实际用户帐户运行此检查, 必须为每个帐户创建两个 Lync Server 管理外壳凭据对象 (包含帐户名和密码的对象)。 然后, 当你调用 Test-CsGroupIM 时, 你必须包含这些凭据对象和两个帐户的 SIP 地址:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

有关详细信息, 请参阅[CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果两个用户可以完成组即时消息会话, 你将收到与以下内容类似的输出: 结果属性标记为**成功:**

TargetFqdn: atl-cs-001.litwareinc.com

结果: 成功

延迟:00:00: 06.3812203

时发生

自检

如果两个用户无法完成即时消息会话, 则结果将显示为 "失败", 并且将在 "错误" 和 "诊断" 属性中记录其他信息:

TargetFqdn: atl-cs-001.litwareinc.com

结果: 失败

延迟: 00:00:00

错误: 404, 未找到

诊断: ErrorCode = 4005, Source = atl-cs-001.litwareinc.com,

原因 = 没有为 SIP 启用目标 URI, 或者没有为其启用目标 URI

并存.

Microsoft DiagnosticHeader

以前的输出表明测试失败的原因是至少有一个测试帐户无效, 原因是帐户不存在或者用户尚未启用 Lync Server。 你可以通过运行类似如下所示的命令来验证帐户是否存在以及是否已启用 nm-ocs-第14级帐户:

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

如果 CsGroupIM 失败, 则可能需要重新运行测试, 这一次包括 Verbose 参数:

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

当包含 Verbose 参数时, CsGroupIM 将返回在检查指定用户是否参与组即时消息会话的能力时尝试的每个操作的分步帐户。 例如, 如果你的测试失败, 并且你被告知一个或多个用户帐户无效, 则可以使用 Verbose 参数重新运行测试并确定无效的用户帐户:

正在发送注册请求:

 目标 Fqdn = atl-cs-001.litwareinc.com

 用户 SIP 地址 = sip:kenmyer@litwareinc.com

 注册端口 = 5061

已选择身份验证类型 "IWA"。

"登录被拒绝" 异常。 检查是否正在使用正确的凭据, 帐户是否处于活动状态。

正如你所见, 在此示例中, 具有 SIP 地址 sip:kenmyer@litwareinc.com 的用户无法登录。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是测试 CsGroupIM 可能失败的一些常见原因:

  - 您指定了一个不正确的用户帐户。 你可以通过运行类似如下所示的命令来验证用户帐户是否存在:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 用户帐户有效, 但当前没有为 Lync Server 启用该帐户。 若要验证是否已启用 Lync Server 的用户帐户, 请运行类似如下的命令:
    
    Move-csuser "sip:kenmyer@litwareinc.com" |选择-已启用对象
    
    如果 Enabled 属性设置为 False, 则表示当前未对 Lync Server 启用用户。

  - 即时消息服务可能不可用。 使用 Lync Server, 你可以配置系统, 以便在无法访问存档数据库时即时消息不可用。 你可以通过运行如下所示的命令来验证该命令:
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    如果 BlockOnArchiveFailure 设置为 True, 则应确定存档数据库是否可用。 你可以使用以下命令返回存档数据库的位置:
    
        Get-CsService -ArchivingDatabase

  - 存档服务器可能不可用。 你可以使用以下命令检索存档服务器的 FQDN:
    
        Get-CsService -ArchivingServer
    
    然后, 你可以 ping 相应的服务器以验证其是否可用。 例如：
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

