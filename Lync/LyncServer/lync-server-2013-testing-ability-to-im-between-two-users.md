---
title: Lync Server 2013：测试在两个用户之间即时消息的功能
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
ms.openlocfilehash: 201aceceadeba3c6c97530925273097fe039bc08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a>在 Lync Server 2013 中的两个用户之间进行即时消息测试的功能

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
<p>使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsIM cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsIM cmdlet 验证一对测试用户是否可以交换即时消息。 调用后，CsIM cmdlet 将通过尝试登录到 Lync Server 的一对测试用户来启动。 假设两次登录成功，则该 cmdlet 将在两个测试用户之间启动 IM 会话。 （用户1邀请用户2加入 IM 会话，而用户2接受邀请。）验证消息可以在两个用户之间交换后，CsIM 将结束 IM 会话并将这两个用户从系统注销。

有关详细信息，请参阅[CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) Cmdlet 的帮助文档。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsIM cmdlet 可以使用一对预配置的测试帐户运行（请参阅设置运行 Lync Server 测试的测试帐户）或已启用 Lync Server 的任何两个用户的帐户。 若要使用测试帐户运行此检查，只需指定正在测试的 Lync Server 池的 FQDN。 例如：

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用实际用户帐户运行此检查，必须为每个帐户创建两个 Windows PowerShell 凭据对象（包含帐户名和密码的对象）。 然后，当你调用 Test-CsIM 时，你必须包含这些凭据对象和两个帐户的 SIP 地址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

有关详细信息，请参阅[CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果两个用户可以完成即时消息会话，则会收到与此类似的输出，结果属性标记为**成功：**

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：06.6630911

时发生

自检

如果测试用户无法完成会话，则结果将显示为 "失败"，并且将在 "错误" 和 "诊断" 属性中记录其他信息：

TargetFqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00:00:00

错误：504，服务器超时

诊断： ErrorCode = 2，Source = atl-litwareinc，Reason = 请参阅

响应代码和原因短语。

Microsoft DiagnosticHeader

例如，以前的输出表明由于找不到指定用户，测试失败。 可通过运行以下命令确定 SIP 地址是否有效（以及用户是否已为 Lync Server 启用了该 SIP 地址）：

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

如果 CsIM 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

当包含 Verbose 参数时，CsIM 会在检查两个测试用户是否参与 IM 会话的能力时返回它尝试的每个操作的分步帐户。 例如，以下是在为 CsIM 提供错误的用户凭据集（在此情况下，密码不正确）时发生的示例输出：

正在发送注册请求：

目标 Fqdn = atl-cs-011.litwareinc.com

用户 Sip 地址 = sip:kenmyer@litwareinc.com

注册机构端口 = 5061

已选择身份验证类型 "IWA"。

对 sip/atl-cs-001 的注册命中率 litwareinc

"Register" 活动在 "0.0601795" 秒内完成。

"登录被拒绝" 异常。 检查使用的凭据是否正确，帐户是否处于活动状态。 ' 在工作流期间发生。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是测试 CsIM 可能失败的一些常见原因：

  - 您指定的用户帐户无效。 你可以通过运行类似如下所示的命令来验证用户帐户是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 用户帐户有效，但当前没有为 Lync Server 启用该帐户。 若要验证是否已启用 Lync Server 的用户帐户，请运行类似如下的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 属性设置为 False，表示当前未对 Lync Server 启用用户。

  - 即时消息服务可能不可用。 使用 Lync Server，你可以配置系统，以便在无法访问存档数据库时即时消息不可用。 你可以通过运行如下所示的命令来验证该命令：
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    如果 BlockOnArchiveFailure 设置为 True，则应确定存档数据库是否可用。 你可以使用以下命令返回存档数据库的位置：
    
        Get-CsService -ArchivingDatabase

  - 存档服务器可能不可用。 你可以使用以下命令检索存档服务器的 FQDN：
    
        Get-CsService -ArchivingServer
    
    然后，你可以 ping 相应的服务器以验证其是否可用。 例如：
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

