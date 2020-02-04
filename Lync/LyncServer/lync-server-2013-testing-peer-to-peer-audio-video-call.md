---
title: Lync Server 2013：测试对等音频/视频通话
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e319ace4ee4cc6613ac5ed29659ac14c5853d7b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745632"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a>在 Lync Server 2013 中测试对等音频/视频呼叫

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
<p>使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsP2PAV cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

Test-CsP2PAV 用于确定一对测试用户是否可以参与对等 A/V 对话。 若要测试此方案，cmdlet 将通过登录到 Lync Server 的两个用户开始。 假设两次登录成功，第一位用户邀请第二位用户加入 A/V 呼叫。 第二个用户接受呼叫，将测试两个用户之间的连接，然后结束呼叫并从系统中注销测试用户。

测试 CsP2PAV 实际上不执行 A/V 调用。 不会在测试用户之间交换多媒体信息。 相反，cmdlet 仅验证是否可以建立合适的连接，以及两个用户是否可以进行此类呼叫。

有关详细信息，请参阅[CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) Cmdlet 的帮助文档。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsP2PAV cmdlet 可以使用一对预配置的测试帐户运行（请参阅设置运行 Lync Server 测试的测试帐户）或已启用 Lync Server 的任何两个用户的帐户。 若要使用测试帐户运行此检查，只需指定正在测试的 Lync Server 池的 FQDN。 例如：

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用实际用户帐户运行此检查，必须为每个帐户创建两个 Lync Server 凭据对象（包含帐户名和密码的对象）。 然后，当你调用 Test-CsP2PAV 时，你必须包含这些凭据对象和两个帐户的 SIP 地址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果两个测试用户可以完成对等 A/V 调用，则会收到与以下内容类似的输出：结果属性标记为**成功：**

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：06.8630376

时发生

自检

如果测试用户无法完成呼叫，则结果将显示为 "失败"，并且将在 "错误" 和 "诊断" 属性中记录其他信息：

TargetFqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00:00:00

错误：480，暂时不可用

诊断： ErrorCode = 15030，Source = atl-litwareinc，Reason = Failed

路由到 Exchange Server

Microsoft DiagnosticHeader

例如，以前的输出表明由于无法联系 Microsoft Exchange Server，测试失败。 此错误消息通常表示 Exchange 统一消息的配置出现问题。

如果测试 CsP2PAV 失败，您可能需要重新运行测试，这一次包括 Verbose 参数：

Test-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose

当包含 Verbose 参数时，CsP2PAV 将返回它尝试的每个操作的分步帐户，因为它检查指定用户登录到 Lync 服务器的能力。 例如，假设测试未通过以下诊断：

ErrorCode = 6003，Source = atl-ws-01-litwareinc，Reason = 不支持的对话框外请求

如果重新运行 Test CsP2PAV 并包含 Verbose 参数，将获得如下输出：

详细： "注册" 活动已开始。

正在发送注册请求：

目标 Fqdn = atl-cs-011.litwareinc.com

用户 Sip 地址 = sip:kenmyer@litwareinc.com

注册机构端口 = 5062。

已选择身份验证类型 "IWA"。

"终结点无法注册" 异常。 有关特定原因，请参阅错误代码。 ' 在 STP2PAVWorkflow 执行工作流期间发生。

尽管这可能不会很明显，但如果你仔细检查输出，你将看到指定的注册器端口（端口5062）不正确。 进而导致测试失败。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是测试 CsP2PAV 可能失败的一些常见原因：

  - 您指定的用户帐户无效。 你可以通过运行类似如下所示的命令来验证用户帐户是否存在：
    
    Move-csuser "sip:kenmyer@litwareinc.com"

  - 用户帐户有效，但当前没有为 Lync Server 启用该帐户。 若要验证是否已启用 Lync Server 的用户帐户，请运行类似如下的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。

</div>

</div>

<span> </span>

</div>

</div>

</div>

