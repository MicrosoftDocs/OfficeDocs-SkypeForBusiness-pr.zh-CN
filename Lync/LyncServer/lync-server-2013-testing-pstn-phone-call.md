---
title: 'Lync Server 2013: 测试 PSTN 电话呼叫'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing PSTN phone call
ms:assetid: dc7d319d-a627-45b6-a978-6111901251e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690133(v=OCS.15)
ms:contentKeyID: 63969656
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 641b2f77079fee100d8f3ac85a1a7580d7cf7d84
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-phone-call-in-lync-server-2013"></a>在 Lync Server 2013 中测试 PSTN 电话呼叫

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
<p>使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsRegistration cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnOutboundCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsPstnOutboundCall cmdlet 可测试用户拨打 PSTN 上的电话号码的功能的能力。 运行 Test CsPstnOutboundCall 时, cmdlet 首先尝试将测试用户登录到 Lync Server。 如果登录成功, 则 cmdlet 将尝试通过 PSTN 网关进行电话呼叫。 此电话将使用拨号计划、语音策略以及分配给测试帐户的其他策略和设置进行呼叫。 接听呼叫时, cmdlet 通过网络发送双音调多频率 (DTMF) 代码以验证媒体连接。

进行测试时, CsPstnOutboundCall 将进行实际的电话呼叫: 目标电话将响铃, 并且必须回答该测试才能成功。 此通话也必须由管理员手动结束。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsPstnOutboundCall cmdlet 可以使用预配置的测试帐户运行 (请参阅设置运行 Lync Server 测试的测试帐户) 或已启用 Lync Server 的任何用户的帐户。 若要使用测试帐户运行此检查, 只需指定正在测试的 Lync Server 池的 FQDN 以及正在调用的 PSTN 电话号码。 例如：

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219"

若要使用实际用户帐户运行此检查, 必须首先创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。 然后, 在调用 Test-CsPstnOutboundCall 时, 必须包含该凭据对象和分配给该帐户的 SIP 地址:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

有关详细信息, 请参阅[CsPstnOutboundCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnOutboundCall) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果指定的用户可以进行呼叫, 并且接听呼叫, 则会收到与此类似的输出, 结果属性标记为**成功:**

TargetFqdn: atl-cs-001.litwareinc.com

结果: 成功

延迟:00:00: 06.8630376

时发生

自检

如果指定的用户不能进行呼叫或不接听呼叫, 则结果将显示为 "失败", 并且将在 "错误" 和 "诊断" 属性中记录其他信息:

TargetFqdn: atl-cs-001.litwareinc.com

结果: 失败

延迟: 00:00:0987365

错误: 403, "已禁止"

诊断: ErrorCode = 12001, Source = atl-litwareinc, Reason = User

策略不包含手机路线使用情况

以前的输出表明测试失败的原因是分配给指定用户的语音策略不包含电话使用。 (电话使用将语音策略与语音路线关联。 如果没有语音政策和相应的语音路线, 则不能通过 PSTN 进行呼叫。)

如果测试 CsPstnOutboundCall 失败, 您可能需要重新运行测试, 这一次包括 Verbose 参数:

    Test-CsPstnOutboundCall -TargetFqdn "atl-cs-001.litwareinc.com" -TargetPstnPhoneNumber "+12065551219" -Verbose

当包含 Verbose 参数时, CsPstnOutboundCall 将返回在检查指定用户登录到 Lync Server 的能力时尝试的每个操作的分步帐户。 例如, 此输出表明网络问题阻止与 PSTN 的连接:

正在与 "sip: +12065551219@litwareinc.com; user = phone" 建立音频视频通话。

从网络收到了异常 ' A 404 (未找到) 响应, 操作失败。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是测试 CsPstnOutboundCall 可能失败的一些常见原因:

  - 您指定了无效的用户帐户。 你可以通过运行类似如下所示的命令来验证用户帐户是否存在:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 用户帐户有效, 但当前没有为 Lync Server 启用该帐户。 若要验证是否已启用 Lync Server 的用户帐户, 请运行类似如下的命令:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 属性设置为 False, 表示当前未对 Lync Server 启用用户。

  - 分配给指定用户的语音策略没有有效的 PSTN 使用。 你可以使用类似下面的命令确定分配给用户的语音策略:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    然后, 你可以使用如下所示的命令确定分配给该策略的 PSTN 用途 (如果有), 该命令将检索有关每用户语音策略 RedmondVoicePolicy 的信息:
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

