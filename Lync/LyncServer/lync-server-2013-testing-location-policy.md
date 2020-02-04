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
ms.openlocfilehash: 2a954405cb8dbba842250e0545ac8661d4f3795c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a>在 Lync Server 2013 中测试位置策略

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
<p>使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsLocationPolicy cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsLocationPolicy cmdlet 验证是否已向用户分配了位置策略。 位置策略用于应用与 E9-1-1 功能和客户端位置相关的设置。 位置策略确定用户是否已启用 E9-1，如果答案是 "是"，则是紧急呼叫的行为。 例如，您可以使用位置策略来定义紧急呼叫的号码（美国911）、是否应自动通知企业安全以及如何路由通话等。

你可以测试用户或网络子网上的位置策略。 如果针对子网运行测试（通过指定子网参数的值），则 cmdlet 将尝试解析该子网的位置策略。 如果未向子网分配位置策略，将检索已配置用户的位置策略。 如果成功检索子网策略，则输出将包括以子网 tagid 开头的 LocationPolicyTagID 值。 如果找不到子网的位置策略，LocationPolicyTagID 将以用户 tagid 开头。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsLocationPolicy cmdlet 可以使用预配置的测试帐户运行（请参阅设置运行 Lync Server 测试的测试帐户）或已启用 Lync Server 的任何用户的帐户。 若要使用测试帐户运行此检查，只需指定正在测试的 Lync Server 池的 FQDN。 例如：

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用实际用户帐户运行此检查，必须首先创建一个包含帐户名称和密码的 Windows PowerShell 凭据对象。 然后，在调用 Test-CsLocationPolicy 时，必须包含该凭据对象和分配给该帐户的 SIP 地址：

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

有关详细信息，请参阅[CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果指定用户具有有效的位置策略，则会收到与此类似的输出，结果属性标记为**成功：**

EnhancedEmergencyServicesEnabled： true

LocationPolicyTagID：用户-tagid

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：06.8630376

时发生

自检

如果找不到指定用户的有效位置策略，则结果将显示为 "失败"，并且将在 "错误" 和 "诊断" 属性中记录其他信息：

TargetFqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00:00:00

错误：404，未找到

诊断： ErrorCode = 4005，Source = atl-cs-001.litwareinc.com，

原因 = 没有为 SIP 启用目标 URI，或者没有为其启用目标 URI

并存.

Microsoft DiagnosticHeader

以前的输出表明由于指定用户无效而导致测试失败：帐户不存在或尚未为 Lync Server 启用用户。 你可以验证帐户的有效性，并通过运行如下命令确定是否已为 nm-ocs-14-3 启用该帐户：

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

如果 CsLocationPolicy 失败，则可能需要重新运行测试，这一次包括 Verbose 参数：

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

当包含 Verbose 参数时，CsLocationPolicy 将返回在验证位置策略时尝试的每个操作的分步帐户。 例如，此输出表明 Lync Server 无法登录测试用户，可能是因为提供了无效密码：

正在发送注册请求：

目标 Fqdn = atl-cs-011.litwareinc.com

用户 Sip 地址 = sip:kenmyer@litwareinc.com

注册机构端口 = 5061

已选择身份验证类型 "IWA"。

对 sip/atl-cs-001 的注册命中率 litwareinc

"Register" 活动在 "0.0601795" 秒内完成。

"登录被拒绝" 异常。 检查使用的凭据是否正确，帐户是否处于活动状态。 ' 在工作流期间发生。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是测试 CsLocationPolicy 可能失败的一些常见原因：

  - 您指定的用户帐户无效。 你可以通过运行类似如下所示的命令来验证用户帐户是否存在：
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 用户帐户有效，但当前没有为 Lync Server 启用该帐户。 若要验证是否已启用 Lync Server 的用户帐户，请运行类似如下的命令：
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    如果 Enabled 属性设置为 False，则表示当前未对 Lync Server 启用用户。

</div>

</div>

<span> </span>

</div>

</div>

</div>

