---
title: Lync Server 2013：测试用户登录 Lync Server 的能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fb1d0af8a5191c7e0af1ffe3319c426c116b586
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a>测试用户登录 Lync Server 2013 的能力

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
<p>使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsRegistration cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsRegistration cmdlet 使你能够验证你的组织中的用户是否可以登录 Lync Server。 运行 Test CsRegistration 时，cmdlet 会尝试登录到 Lync Server 的测试用户，如果成功，则将测试用户从系统断开连接。 所有这些操作在没有任何用户交互的情况下发生，并且不会影响任何实际用户。 例如，假设测试帐户 sip:kenmyer@litwareinc.com 对应于具有真实 Lync 服务器帐户的真实用户。 在这种情况下，将在不中断真正的 Ken Myer 的情况下执行测试。 当 Ken Myer 测试帐户从系统注销时，该用户将保持登录状态的 Ken Myer。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsRegistration cmdlet 可以使用预配置的测试帐户运行（请参阅设置运行 Lync Server 测试的测试帐户）或已启用 Lync Server 的任何用户的帐户。 若要使用测试帐户运行此检查，只需指定正在测试的 Lync Server 注册机构的 FQDN。 例如：

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用实际用户帐户运行此检查，必须首先创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。 然后，在调用 Test-CsRegistration 时，必须包含该凭据对象和分配给该帐户的 SIP 地址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

有关详细信息，请参阅[CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果指定用户可以登录到（然后从 Lync Server 注销），你将收到与以下内容类似的输出，结果属性标记为**成功：**

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：06.8630376

时发生

自检

如果指定的用户无法登录或注销，则结果将显示为 "失败"，并且将在 "错误" 和 "诊断" 属性中记录其他信息：

TargetFqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00:00:00

错误：404，未找到

诊断： ErrorCode = 1003，source = atl-litwareinc，Reason = User

不存在

Microsoft DiagnosticHeader

例如，以前的输出表明由于找不到指定用户，测试失败。 可通过运行以下命令确定 SIP 地址是否有效（以及用户是否已为 Lync Server 启用了该 SIP 地址）：

    Get-CsUser "sip:kenmyer@litwareinc.com"

如果 CsRegistration 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

当包含 Verbose 参数时，CsRegistration 将返回在检查指定用户登录到 Lync Server 的能力时尝试的每个操作的分步帐户。 例如：

详细： "注册" 活动已开始。

正在发送注册请求：

目标 Fqdn = atl-cs-011.litwareinc.com

用户 Sip 地址 = sip:kenmyer@litwareinc.com

注册机构端口 = 5061。

已选中 "受信任" 身份验证类型。

"终结点无法注册" 异常。 请参阅在执行工作流 STRegistrerWorkflow 时出现的特定原因的 ErrorCode。

异常调用堆栈： SipAsyncResult'1： ThrowIfFailed （）

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是测试 CsRegistration 可能失败的一些常见原因：

  - 您指定了一个不正确的用户帐户。 你可以通过运行类似如下所示的命令来验证用户帐户是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 用户帐户有效，但当前没有为 Lync Server 启用该帐户。 若要验证是否已启用 Lync Server 的用户帐户，请运行类似如下的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。

  - 您指定了一个不正确的注册机构池。 你可以使用以下命令返回注册机构池的 Fqdn：
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - 注册机构池目前不可用。 尝试 ping 池以查看它是否响应：
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

