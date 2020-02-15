---
title: Lync Server 2013：测试对等音频/视频呼叫
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
ms.openlocfilehash: 462442b7afea193866dc96aaf57085d780f43a39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a>在 Lync Server 2013 中测试对等音频/视频呼叫

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsP2PAV cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsP2PAV 用于确定一对测试用户是否可以参与对等 A/V 会话对话。 若要测试此方案，cmdlet 将通过在两个用户上登录到 Lync Server 来启动。 假设这两个用户登录成功，然后第一个用户邀请第二个用户加入 A/V 呼叫。 第二个用户接受呼叫，将测试两个用户之间的连接；然后呼叫结束，测试用户从系统中注销。

CsP2PAV 不会实际执行 A/V 调用。 不会在测试用户之间交换多媒体信息。 相反，cmdlet 仅验证是否可以建立适当的连接，以及两个用户是否可以执行此类调用。

有关详细信息，请参阅[CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) Cmdlet 的帮助文档。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsP2PAV cmdlet 可使用一对预配置的测试帐户（请参阅设置运行 Lync Server 测试的测试帐户）或任何两个已启用 Lync Server 的用户的帐户运行。 若要使用测试帐户运行此检查，只需指定要测试的 Lync Server 池的 FQDN 即可。 例如：

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用实际用户帐户运行此检查，必须为每个帐户创建两个 Lync Server 凭据对象（包含帐户名和密码的对象）。 在调用 CsP2PAV 时，必须包括这些凭据对象和两个帐户的 SIP 地址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果两个测试用户可以完成对等 A/V 呼叫，则会收到类似于以下内容的输出，并将 Result 属性标记为**成功：**

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：06.8630376

误差

诊断

如果测试用户无法完成该调用，则结果将显示为 "失败"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：

TargetFqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00:00:00

错误：480，暂时不可用

诊断： ErrorCode = 15030，Source = atl-cs-001，Reason = Failed

路由到 Exchange Server

Microsoft DiagnosticHeader

例如，以前的输出表明由于无法联系 Microsoft Exchange Server 而导致测试失败。 此错误消息通常表明 Exchange 统一消息的配置存在问题。

如果 CsP2PAV 失败，您可能需要重新运行测试，这一次包括 Verbose 参数：

CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose

包含 Verbose 参数时，CsP2PAV 将返回其尝试的每个操作的分步帐户，因为它检查指定用户登录到 Lync Server 的能力。 例如，假设测试因以下诊断而失败：

ErrorCode = 6003，Source = atl-cs-001，Reason = 不支持的对话框请求 litwareinc

如果重新运行 Test-CsP2PAV 并包含 Verbose 参数，您将获得如下输出：

详细： "注册" 活动已启动。

发送注册请求：

目标 Fqdn = atl-cs-011.litwareinc.com

用户 Sip 地址 = sip:kenmyer@litwareinc.com

注册器端口 = 5062。

已选择身份验证类型 "IWA"。

"终结点无法注册" 异常。 有关具体原因，请参阅错误代码。 在工作流 STP2PAVWorkflow 执行过程中发生。

虽然这可能不是显而易见的，但如果仔细检查输出，将会发现指定了不正确的注册器端口（端口5062）。 进而导致测试失败。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

以下是测试 CsP2PAV 可能失败的一些常见原因：

  - 您指定的用户帐户无效。 您可以通过运行与以下内容类似的命令来验证用户帐户是否存在：
    
    Get-csuser "sip:kenmyer@litwareinc.com"

  - 用户帐户有效，但当前未对 Lync Server 启用该帐户。 若要验证是否已为 Lync Server 启用用户帐户，请运行与以下内容类似的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。

</div>

</div>

<span> </span>

</div>

</div>

</div>

