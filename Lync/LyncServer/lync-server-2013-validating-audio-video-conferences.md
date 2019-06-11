---
title: 'Lync Server 2013: 验证音频/视频会议'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0e608f0c765c4dd552645320ec947c7e8a54ac4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a>在 Lync Server 2013 中验证音频/视频会议

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
<td><p>需要权限</p></td>
<td><p>当使用 Lync Server 命令行管理程序在本地运行时, 用户必须是 RTCUniversalServerAdmins 安全组的成员。</p>
<p>使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsAVConference cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsAVConference cmdlet 检查两个测试用户是否可以参与音频/视频 (A/V) 会议。 当 cmdlet 运行时, 两个用户登录到系统。 成功登录后, 第一个用户将创建一个/V 会议, 然后等待第二位用户加入该会议。 在数据的简短交换后, 会议将被删除, 并且两个测试用户已注销。

请注意, CsAVConference 不会在两个测试用户之间进行实际的 A/V 会议。 相反, cmdlet 将验证两个用户是否可以建立执行此类会议所需的所有连接。

可在[CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)中找到此命令的更多示例。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsAVConference cmdlet 可以使用一对预配置的测试帐户运行 (请参阅设置运行 Lync Server 测试的测试帐户) 或已启用 Lync Server 的任何两个用户的帐户。 若要使用测试帐户运行此检查, 只需指定正在测试的 Lync Server 池的 FQDN。 例如：

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用实际用户帐户运行此检查, 必须为每个帐户创建两个 Windows PowerShell 凭据对象 (包含帐户名和密码的对象)。 然后, 在调用 Test-CsAVConference 时, 必须包含两个帐户的凭据对象和 SIP 地址:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

有关详细信息, 请参阅[CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果指定用户可以成功完成 A/V 会议, 你将收到类似于此的输出, 结果属性标记为 "成功" **:**

TargetFqdn: atl-cs-001.litwareinc.com

结果: 成功

延迟:00:00: 02.6841765

时发生

自检

如果用户无法完成会议, 则结果将显示为 "失败", 并且将在 "错误" 和 "诊断" 属性中记录其他信息:

TargetFqdn: atl-cs-001.litwareinc.com

结果: 失败

延迟: 00:00:00

错误: 404, 未找到

诊断: ErrorCode = 4005, Source = atl-cs-001.litwareinc.com,

原因 = 没有为 SIP 启用目标 URI, 或者没有为其启用目标 URI

并存.

Microsoft DiagnosticHeader

例如, 以前的输出表明由于帐户不存在或者帐户尚未为 Lync Server 启用, 导致测试失败的原因是两个用户帐户中的至少一个帐户无效。 你可以通过运行类似如下所示的命令来验证两个测试帐户是否存在, 以及是否为 Lync Server 启用了这些帐户:

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

如果 CsAVConference 失败, 则可能需要重新运行测试, 这一次包括 Verbose 参数:

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

当包含 Verbose 参数时, CsAVConference 将返回在检查指定用户是否参与 AV 会议的能力时尝试的每个操作的分步帐户。 例如, 假设测试失败并收到以下诊断:

ErrorCode = 1008, Source = accessproxy, Reason = 无法解析 DNS SRV 记录

如果使用 Verbose 参数重新运行测试, 返回的分步信息将包含类似以下内容的输出:

详细: "注册" 活动已开始。

正在发送注册请求:

目标 Fqdn = atl-cs-001.litwareinc.com

用户 Sip 地址 = sip:davidlongmire@litwareinc.com

注册机构端口 = 5061。

已选中 "受信任" 身份验证类型。

"注册" 活动已开始。

正在发送注册请求:

目标 Fqdn = atl-cs-001.litwareinc.com

用户 Sip 地址 = sip:kenmyer@litwareinc.com

注册机构端口 = 5061。

已选中 "受信任" 身份验证类型。

"终结点无法注册" 异常。 有关特定原因, 请参阅错误代码。 ' 工作流期间发生

该输出中的最后一行指示用户 sip:kenmyer@litwareinc.com 无法注册 Lync Server。 这意味着你应该验证 SIP 地址 sip:kenmyer@litwareinc.com 是否有效, 以及是否为 Lync Server 启用关联的用户。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是测试 CsAVConference 可能失败的一些常见原因:

  - 您指定的用户帐户无效。 你可以通过运行类似如下所示的命令来验证用户帐户是否存在:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 用户帐户有效, 但当前没有为 Lync Server 启用该帐户。 若要验证是否已启用 Lync Server 的用户帐户, 请运行类似如下的命令:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 属性设置为 False, 表示当前未对 Lync Server 启用用户。

</div>

</div>

<span> </span>

</div>

</div>

</div>

