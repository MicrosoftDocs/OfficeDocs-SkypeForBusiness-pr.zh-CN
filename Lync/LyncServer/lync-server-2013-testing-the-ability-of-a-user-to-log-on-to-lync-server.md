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
ms.openlocfilehash: 9ac7f02d18f1b270b3a58a7ece84cb3a859b32b7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530469"
---
# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a>测试用户登录到 Lync Server 2013 的能力

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsRegistration cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

通过 Test-CsRegistration cmdlet，您可以验证组织中的用户是否可以登录 Lync Server。 运行 CsRegistration 时，cmdlet 会尝试将测试用户登录到 Lync Server，然后，如果成功，则断开该测试用户与系统的连接。 所有这些无需用户进行任何干预，并且不会影响任何真实用户。 例如，假设测试帐户 sip:kenmyer@litwareinc.com 与具有实际 Lync Server 帐户的真实用户相对应。 在该情况下，执行测试不会对真实的 Ken Myer 造成任何干扰。 在 Ken Myer 测试帐户从系统中注销后，Ken Myer 本人还继续处于登录状态。

</div>

<div>

## <a name="running-the-test"></a>运行测试

可以使用预配置的测试帐户运行 Test-CsRegistration cmdlet (请参阅设置用于运行 Lync Server 测试的测试帐户) 或启用了 Lync Server 的任何用户的帐户。 若要使用测试帐户运行此检查，只需指定要测试的 Lync Server 注册器池的 FQDN。 例如：

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用实际用户帐户运行此检查，必须首先创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。 然后，您必须在调用 CsRegistration 时包含该凭据对象和分配给该帐户的 SIP 地址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

有关详细信息，请参阅 [CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果指定的用户可以登录到 (，然后从) Lync Server 注销，您将收到与以下内容类似的输出：结果属性标记为 **成功：**

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：06.8630376

误差

诊断

如果指定用户无法登录或注销，则结果将显示为 "失败"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：

TargetFqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00:00:00

错误：未找到404

诊断： ErrorCode = 1003，source = atl-ws-01-litwareinc，Reason = User

不存在

Microsoft DiagnosticHeader

例如，以前的输出表明由于找不到指定的用户而导致测试失败。 您可以通过运行以下命令来确定 SIP 地址是否有效 (以及用户是否已为 Lync Server) 启用了该 SIP 地址：

    Get-CsUser "sip:kenmyer@litwareinc.com"

如果 Test-CsRegistration 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

包含 Verbose 参数时，Test-CsRegistration 将返回其在检查指定用户登录到 Lync Server 的能力时所尝试的每个操作的分步帐户。 例如：

详细： "注册" 活动已启动。

发送注册请求：

目标 Fqdn = atl-cs-011.litwareinc.com

用户 Sip 地址 = sip:kenmyer@litwareinc.com

注册器端口 = 5061。

选择 "受信任" 的身份验证类型。

"终结点无法注册" 异常。 有关特定原因的错误代码，请参阅在工作流 STRegistrerWorkflow 执行过程中发生的错误。

异常调用堆栈： SipAsyncResult'1. ThrowIfFailed ( # A1

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是 Test-CsRegistration 可能失败的一些常见原因：

  - 您指定了不正确的用户帐户。 您可以通过运行与以下内容类似的命令来验证用户帐户是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 用户帐户有效，但当前未对 Lync Server 启用该帐户。 若要验证是否已为 Lync Server 启用用户帐户，请运行与以下内容类似的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。

  - 您指定了一个不正确的注册器池。 您可以使用以下命令返回注册器池的 Fqdn：
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - 注册器池当前不可用。 尝试 ping 池以查看它是否响应：
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

