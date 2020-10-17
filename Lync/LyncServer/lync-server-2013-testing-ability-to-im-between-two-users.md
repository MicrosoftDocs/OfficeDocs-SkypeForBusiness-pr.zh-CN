---
title: Lync Server 2013：在两个用户之间测试 IM 的功能
description: Lync Server 2013：在两个用户之间测试 IM 的功能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1409cfb58ed435a66dcf61db56660ca760e16422
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560798"
---
# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a>在 Lync Server 2013 中的两个用户之间测试 IM 的功能

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsIM cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

Test-CsIM cmdlet 验证一对测试用户是否可以交换即时消息。 调用后，Test-CsIM cmdlet 将通过尝试将一对测试用户登录到 Lync Server 来启动。 假定两次登录成功，则 cmdlet 将在两个测试用户之间启动 IM 会话。  (User 1 邀请用户2到 IM 会话，而用户2接受邀请。 ) 在验证是否可以在两个用户之间交换邮件之后，Test-CsIM 将结束 IM 会话并将这两个用户从系统注销。

有关详细信息，请参阅 [CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) Cmdlet 的帮助文档。

</div>

<div>

## <a name="running-the-test"></a>运行测试

可以使用一对预配置的测试帐户运行 Test-CsIM cmdlet (参阅设置用于运行 Lync Server 测试的测试帐户) 或已为其启用 Lync Server 的任意两个用户的帐户。 若要使用测试帐户运行此检查，只需指定要测试的 Lync Server 池的 FQDN 即可。 例如：

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用实际用户帐户运行此检查，必须为每个帐户 (包含帐户名称和密码) 的对象创建两个 Windows PowerShell 凭据对象。 在调用 CsIM 时，必须包括这些凭据对象和两个帐户的 SIP 地址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

有关详细信息，请参阅 [CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果两个用户可以完成即时消息会话，您将收到与以下内容类似的输出，并将 Result 属性标记为 " **成功"：**

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：06.6630911

误差

诊断

如果测试用户无法完成会话，则结果将显示为 "失败"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：

TargetFqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00:00:00

错误：504，服务器超时

诊断： ErrorCode = 2，Source = atl-cs-litwareinc，Reason = 参阅

响应代码和原因短语。

Microsoft DiagnosticHeader

例如，以前的输出表明由于找不到指定的用户而导致测试失败。 您可以通过运行以下命令来确定 SIP 地址是否有效 (以及用户是否已为 Lync Server) 启用了该 SIP 地址：

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

如果 Test-CsIM 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

包含 Verbose 参数时，Test-CsIM 将返回它在检查了两个测试用户参与 IM 会话的能力时所尝试的每个操作的分步帐户。 例如，以下是当一组错误的用户凭据 (在这种情况下，在为 CsIM 提供不正确的密码) 的情况下会发生的示例输出：

发送注册请求：

目标 Fqdn = atl-cs-011.litwareinc.com

用户 Sip 地址 = sip:kenmyer@litwareinc.com

注册器端口 = 5061

已选择身份验证类型 "IWA"。

针对 sip/atl-001-litwareinc 的注册命中率

"Register" 活动在 "0.0601795" 秒内完成。

"登录被拒绝" 异常。 检查是否正在使用正确的凭据，以及帐户是否处于活动状态。 在工作流过程中发生。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是 Test-CsIM 可能失败的一些常见原因：

  - 您指定的用户帐户无效。 您可以通过运行与以下内容类似的命令来验证用户帐户是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 用户帐户有效，但当前未对 Lync Server 启用该帐户。 若要验证是否已为 Lync Server 启用用户帐户，请运行与以下内容类似的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。

  - 即时消息服务可能不可用。 使用 Lync Server，可以配置系统，以便在无法访问存档数据库时 IM 不可用。 您可以通过运行与以下内容类似的命令来验证这一点：
    
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

