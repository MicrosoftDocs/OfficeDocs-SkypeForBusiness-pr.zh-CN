---
title: Lync Server 2013：测试位置策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a46eecb63ed35075cb44ff840e733f781357ea6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a>在 Lync Server 2013 中测试位置策略

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 New-cslocationpolicy cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

New-cslocationpolicy cmdlet 验证是否已将位置策略分配给用户。 可以使用位置策略来应用与 E9-1-1 功能和客户端位置相关的设置。 位置策略确定是否为用户启用 E9-1-1，如果答案是 "是"，则是紧急呼叫的行为。 例如，可以使用位置策略定义发生紧急呼叫的号码（美国的911）、企业安全是否应自动通知以及应如何路由呼叫。

可以测试用户或网络子网的位置策略。 如果通过指定 Subnet 参数的值对子网运行测试，则 cmdlet 将尝试解析该子网的位置策略。 如果没有位置策略分配到子网，则将检索配置用户的位置策略。 如果成功检索子网策略，则输出将包含以子网-tagid 开头的 LocationPolicyTagID 值。 如果未找到子网的位置策略，则 LocationPolicyTagID 将以 user-tagid 开头。

</div>

<div>

## <a name="running-the-test"></a>运行测试

可以使用预配置的测试帐户（请参阅设置运行 Lync Server 测试的测试帐户）或已启用 Lync Server 的任何用户的帐户运行 New-cslocationpolicy cmdlet。 若要使用测试帐户运行此检查，只需指定要测试的 Lync Server 池的 FQDN 即可。 例如：

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用实际用户帐户运行此检查，必须首先创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。 然后，您必须在调用 New-cslocationpolicy 时包含该凭据对象和分配给该帐户的 SIP 地址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

有关详细信息，请参阅[new-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果指定用户具有有效的位置策略，则将接收与以下内容类似的输出，并将 Result 属性标记为 "**成功"：**

EnhancedEmergencyServicesEnabled： true

LocationPolicyTagID：用户-tagid

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：06.8630376

误差

诊断

如果找不到指定用户的有效位置策略，则结果将显示为 "失败"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：

TargetFqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00:00:00

错误：未找到404

诊断： ErrorCode = 4005，Source = atl-cs-001.litwareinc.com，

原因 = 未对 SIP 启用目标 URI 或不为其启用目标 URI

尚.

Microsoft DiagnosticHeader

以前的输出表明由于指定用户无效而导致测试失败：该帐户不存在，或者尚未为 Lync Server 启用该用户。 您可以通过运行与以下类似的命令来验证帐户的有效性，并确定是否已为 nm-第 14-第14级启用该帐户：

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

如果 New-cslocationpolicy 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

包含 Verbose 参数时，New-cslocationpolicy 将返回它在验证位置策略时尝试的每个操作的分步帐户。 例如，此输出指示 Lync Server 无法登录测试用户，可能是因为提供了无效密码：

发送注册请求：

目标 Fqdn = atl-cs-011.litwareinc.com

用户 Sip 地址 = sip:kenmyer@litwareinc.com

注册器端口 = 5061

已选择身份验证类型 "IWA"。

针对 sip/atl-001-litwareinc 的注册命中率

"Register" 活动在 "0.0601795" 秒内完成。

"登录被拒绝" 异常。 检查是否正在使用正确的凭据，以及帐户是否处于活动状态。 在工作流过程中发生。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

以下是测试 New-cslocationpolicy 可能失败的一些常见原因：

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

