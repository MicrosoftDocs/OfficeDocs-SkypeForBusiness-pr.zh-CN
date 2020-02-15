---
title: Lync Server 2013：验证音频/视频会议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82abbf918f4b375c10fdf201591e099f5cd4262e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a>在 Lync Server 2013 中验证音频/视频会议

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
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>验证计划</p></td>
<td><p>每天</p></td>
</tr>
<tr class="odd">
<td><p>测试工具</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="even">
<td><p>所需的权限</p></td>
<td><p>在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</p>
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsAVConference cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsAVConference cmdlet 检查两个测试用户是否可以参与音频/视频（A/V）会议。 运行此 cmdlet 时，这两个用户将登录系统。 成功登录后，第一个用户会创建 A/V 会议，然后等待第二个用户加入该会议。 简单交换数据之后，删除此会议并注销这两个测试用户。

请注意，CsAVConference 不会在两个测试用户之间进行实际的 A/V 会议。 相反，cmdlet 会验证两个用户是否可以建立执行此类会议所需的所有连接。

在[CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)中，可以找到此命令的更多示例。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsAVConference cmdlet 可使用一对预配置的测试帐户（请参阅设置运行 Lync Server 测试的测试帐户）或任何两个已启用 Lync Server 的用户的帐户运行。 若要使用测试帐户运行此检查，只需指定要测试的 Lync Server 池的 FQDN 即可。 例如：

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用实际用户帐户运行此检查，必须为每个帐户创建两个 Windows PowerShell 凭据对象（包含帐户名和密码的对象）。 然后，在调用 CsAVConference 时，必须包含两个帐户的凭据对象和 SIP 地址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

有关详细信息，请参阅[CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果指定用户可以成功完成 A/V 会议，则会收到与以下内容类似的输出，并将 Result 属性标记为 "**成功"：**

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：02.6841765

误差

诊断

如果用户无法完成会议，则结果将显示为 "失败"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：

TargetFqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00:00:00

错误：未找到404

诊断： ErrorCode = 4005，Source = atl-cs-001.litwareinc.com，

原因 = 未对 SIP 启用目标 URI 或不为其启用目标 URI

尚.

Microsoft DiagnosticHeader

例如，由于帐户不存在或尚未为 Lync Server 启用帐户，因此以前的输出显示测试失败，因为这两个用户帐户中至少有一个帐户无效。 您可以通过运行与以下内容类似的命令来验证这两个测试帐户是否存在，以及是否为 Lync Server 启用了这些帐户：

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

如果 CsAVConference 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

当包含 Verbose 参数时，CsAVConference 将返回其在检查指定用户是否参与 AV 会议的能力时所尝试的每个操作的分步帐户。 例如，假设您的测试失败，并且您收到以下诊断：

ErrorCode = 1008，Source = accessproxy，Reason = 无法解析 DNS SRV 记录

如果使用 Verbose 参数重新运行测试，则返回的分步信息将包含类似如下的输出：

详细： "注册" 活动已启动。

发送注册请求：

目标 Fqdn = atl-cs-001.litwareinc.com

用户 Sip 地址 = sip:davidlongmire@litwareinc.com

注册器端口 = 5061。

选择 "受信任" 的身份验证类型。

"注册" 活动已开始。

发送注册请求：

目标 Fqdn = atl-cs-001.litwareinc.com

用户 Sip 地址 = sip:kenmyer@litwareinc.com

注册器端口 = 5061。

选择 "受信任" 的身份验证类型。

"终结点无法注册" 异常。 有关具体原因，请参阅错误代码。 在工作流过程中发生

该输出中的最后一行指示用户 sip:kenmyer@litwareinc.com 无法注册 Lync Server。 这意味着，您应验证 SIP 地址 sip:kenmyer@litwareinc.com 是否有效，以及是否为 Lync Server 启用了关联的用户。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

以下是测试 CsAVConference 可能失败的一些常见原因：

  - 您指定的用户帐户无效。 您可以通过运行与以下内容类似的命令来验证用户帐户是否存在：
    
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

