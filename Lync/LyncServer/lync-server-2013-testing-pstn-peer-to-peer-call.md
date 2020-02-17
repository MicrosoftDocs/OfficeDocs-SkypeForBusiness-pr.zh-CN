---
title: Lync Server 2013：测试 PSTN 对等呼叫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61c172ea79e646e9deec1c56e792d4e7c4df3a26
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a>在 Lync Server 2013 中测试 PSTN 对等呼叫

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsPstnPeerToPeerCall cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

CsPstnPeerToPeerCall cmdlet 验证一对用户是否必须通过公用电话交换网（PSTN）网关对对等呼叫进行呼叫的能力。 在调用 CsPstnPeerToPeerCall 时，cmdlet 将首先尝试登录到 Lync Server 的两个测试用户。 如果登录成功，则 cmdlet 将使用户1尝试通过 PSTN 网关调用用户2。 CsPstnPeerToPeerCall 将使用拨号计划、语音策略以及分配给测试用户的其他策略和配置设置进行此呼叫。 如果测试按计划进行，则 cmdlet 将验证用户2是否能够应答呼叫，然后从系统中注销两个测试帐户。

CsPstnPeerToPeerCall 进行实际的电话呼叫，一个验证是否可以建立连接，还会通过网络传输 DTMF 代码，以确定是否可以通过该连接发送媒体。 呼叫由 cmdlet 本身应答，且无需手动终止呼叫。 （也就是说，没有人必须回答，然后挂断呼叫的电话。）

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsPstnPeerToPeerCall cmdlet 可使用一对预配置的测试帐户（请参阅设置运行 Lync Server 测试的测试帐户）或任何两个已启用 Lync Server 的用户的帐户运行。 若要使用测试帐户运行此检查，只需指定要测试的 Lync Server 池的 FQDN 即可。 例如：

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

若要使用实际用户帐户运行此检查，必须为每个帐户创建两个 Windows PowerShell 凭据对象（包含帐户名和密码的对象）。 在调用 CsPstnPeerToPeerCall 时，必须包括这些凭据对象和两个帐户的 SIP 地址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

有关详细信息，请参阅[CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果指定的用户可以完成对等呼叫，您将收到与以下内容类似的输出，并将 Result 属性标记为**成功：**

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：06.8630376

误差

诊断

如果指定用户无法完成对等呼叫，则结果将显示为 "失败"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：

TargetFqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00:00:0182361

错误：403，已禁止

诊断： ErrorCode = 12001，Source = atl-cs-001.litwareinc.com，

Reason = User Policy 不包含电话路由使用情况

由于分配给至少一个指定用户的语音策略不包含电话使用情况，以前的输出表明测试失败。 （电话惯例将语音策略与语音路由关联。 如果没有语音策略和相应的语音路由，则无法通过 PSTN 进行呼叫。

如果 CsPstnPeerToPeerCall 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

包含 Verbose 参数时，CsPstnPeerToPeerCall 将返回其在检查指定用户登录到 Lync Server 的能力时所尝试的每个操作的分步帐户。 例如，以下输出表明网络问题阻止了与 PSTN 的连接：

为 "sip： + 12065551219@litwareinc .com; user = phone" 建立音频视频呼叫。

从网络收到异常 "A 404 （未找到）" 响应，操作失败。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

以下是测试 CsPstnPeerToPeerCall 可能失败的一些常见原因：

  - 您指定的用户帐户无效。 您可以通过运行与以下内容类似的命令来验证用户帐户是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 用户帐户有效，但当前未对 Lync Server 启用该帐户。 若要验证是否已为 Lync Server 启用用户帐户，请运行与以下内容类似的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。

  - 分配给指定用户的语音策略没有有效的 PSTN 用法。 您可以使用类似如下的命令来确定分配给用户的语音策略：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    然后，您可以使用类似如下的命令来确定分配给该策略的 PSTN 用法（如果有），该命令将检索有关每个用户的语音策略 RedmondVoicePolicy 的信息：
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

