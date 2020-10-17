---
title: Lync Server 2013：测试 PSTN 电话呼叫
description: Lync Server 2013：测试 PSTN 电话呼叫。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b42ea6dd46145961a34386d704f8f44e9b7909ad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547398"
---
# <a name="testing-pstn-phone-call-in-lync-server-2013"></a>在 Lync Server 2013 中测试 PSTN 电话呼叫

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
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

Test-CsPstnOutboundCall cmdlet 测试用户拨打 PSTN 上的电话号码的能力。 运行 CsPstnOutboundCall 时，cmdlet 将首先尝试将测试用户记录到 Lync Server。 如果登录成功，则 cmdlet 将尝试通过 PSTN 网关发出电话呼叫。 将使用拨号计划、语音策略以及分配给测试帐户的其他策略和设置进行此电话呼叫。 当应答呼叫时，cmdlet 会通过网络发送双音多频 (DTMF) 代码，以验证媒体连接性。

Test-CsPstnOutboundCall 在执行其测试时将发起真实的电话呼叫：目标电话将响铃，必须接电话测试才能成功。 此外，还必须由管理员手动终止此呼叫。

</div>

<div>

## <a name="running-the-test"></a>运行测试

可以使用预配置的测试帐户运行 Test-CsPstnOutboundCall cmdlet (请参阅设置用于运行 Lync Server 测试的测试帐户) 或启用了 Lync Server 的任何用户的帐户。 若要使用测试帐户运行此检查，只需指定要测试的 Lync Server 池的 FQDN 和要调用的 PSTN 电话号码。 例如：

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

若要使用实际用户帐户运行此检查，必须首先创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。 然后，您必须在调用 CsPstnOutboundCall 时包含该凭据对象和分配给该帐户的 SIP 地址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

有关详细信息，请参阅 [CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果指定的用户可以进行呼叫，并且接听呼叫，您将收到与以下内容类似的输出，并将 Result 属性标记为 **成功：**

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：06.8630376

误差

诊断

如果指定用户无法发出呼叫，或者呼叫未应答，则结果将显示为 "失败"，并且在 "错误" 和 "诊断" 属性中将记录其他信息：

TargetFqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00:00:0987365

错误：403，已禁止

诊断： ErrorCode = 12001，Source = atl-cs-001，Reason = User

策略不包含电话路由使用情况

由于分配给指定用户的语音策略不包含电话使用情况，以前的输出表明测试失败。  (电话惯例将语音策略与语音路由关联。 如果没有语音策略和相应的语音路由，则无法通过 PSTN 进行呼叫。 ) 

如果 Test-CsPstnOutboundCall 失败，您可能需要重新运行测试，这一次包括 Verbose 参数：

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

包含 Verbose 参数时，Test-CsPstnOutboundCall 将返回其在检查指定用户登录到 Lync Server 的能力时所尝试的每个操作的分步帐户。 例如，以下输出表明网络问题阻止了与 PSTN 的连接：

为 "sip： + 12065551219@litwareinc .com; user = phone" 建立音频视频呼叫。

找不到异常 "A 404 () 从网络收到响应，操作失败。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是 Test-CsPstnOutboundCall 可能失败的一些常见原因：

  - 您指定的用户帐户无效。 您可以通过运行与以下内容类似的命令来验证用户帐户是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 用户帐户有效，但当前未对 Lync Server 启用该帐户。 若要验证是否已为 Lync Server 启用用户帐户，请运行与以下内容类似的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。

  - 分配给指定用户的语音策略没有有效的 PSTN 用法。 您可以使用类似如下的命令来确定分配给用户的语音策略：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    然后，如果使用如下所示的命令 RedmondVoicePolicy 分配给该策略的任何) ，则可以确定 PSTN (用法，该命令将检索有关每用户语音策略的信息：
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

