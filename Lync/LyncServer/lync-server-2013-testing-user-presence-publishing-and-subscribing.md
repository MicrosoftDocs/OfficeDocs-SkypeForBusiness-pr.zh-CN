---
title: Lync Server 2013：测试用户状态发布和订阅
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user presence publishing and subscribing
ms:assetid: 27694c71-8e63-4aa4-b49f-fa06ccb81949
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743832(v=OCS.15)
ms:contentKeyID: 63969587
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f6dcc7461362129df72eefd0fd1ab3f5dd809b5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a>在 Lync Server 2013 中测试用户状态发布和订阅

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsPresence cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsPresence 用于确定一对测试用户是否可以登录 Lync Server，然后交换状态信息。 为此，此 cmdlet 首先使这两个用户登录系统。 如果登录成功，第一个测试用户随后将要求从第二个用户接收状态信息。 第二个用户发布此信息，然后 Test-CsPresence 验证是否信息是否已成功传输到第一个用户。 在交换状态信息后，这两个测试用户就会从 Lync Server 注销。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsPresence cmdlet 可使用一对预配置的测试帐户（请参阅设置运行 Lync Server 测试的测试帐户）或任何两个已启用 Lync Server 的用户的帐户运行。 若要使用测试帐户运行此检查，只需指定要测试的 Lync Server 池的 FQDN 即可。 例如：

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用实际用户帐户运行此检查，必须为每个帐户创建两个 Windows PowerShell 凭据对象（包含帐户名和密码的对象）。 在调用 CsPresence 时，必须包括这些凭据对象和两个帐户的 SIP 地址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

有关详细信息，请参阅[CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果指定用户可以交换状态信息，则会收到类似于以下内容的输出，并将 Result 属性标记为 "**成功"：**

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：06.3280315

误差

诊断

如果两个用户不能交换状态信息，则结果将显示为 "失败"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：

TargetFqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00:00:00

错误：未找到404

诊断： ErrorCode = 4005，Source = atl-cs-001.litwareinc.com，

原因 = 未对 SIP 启用目标 URI 或不为其启用目标 URI

尚.

Microsoft DiagnosticHeader

例如，由于至少有两个用户帐户中的一个无效，因此以前的输出表明测试失败：该帐户不存在，或者尚未为 Lync Server 启用该帐户。 您可以通过运行与以下内容类似的命令来验证帐户是否存在，并确定是否为 Lync Server 启用了这些帐户：

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

如果 CsPresence 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

包含 Verbose 参数时，CsPresence 将返回其在检查指定用户登录到 Lync Server 的能力时所尝试的每个操作的分步帐户。 例如：

注册请求命中未知

"Register" 活动在 "0.0345791" 秒内完成。

"SelfSubscribeActivity" 活动已启动。

"SelfSubscribeActivity" 活动在 "0.0041174" 秒内完成。

"SubscribePresence" 活动已启动。

"SubscribePresence" 活动在 "0.0038764" 秒内完成。

"PublishPresence" 活动已启动。

在25秒内未收到异常 "状态通知"。 ruing 工作流 STPresenceWorkflow 执行发生。

在25秒内未收到状态通知这一事实可能表示网络问题阻止交换信息。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

以下是测试 CsPresence 可能失败的一些常见原因：

  - 您指定了不正确的用户帐户。 您可以通过运行与以下内容类似的命令来验证用户帐户是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 用户帐户有效，但当前未对 Lync Server 启用该帐户。 若要验证是否已为 Lync Server 启用用户帐户，请运行与以下内容类似的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。

</div>

</div>

<span> </span>

</div>

</div>

</div>

