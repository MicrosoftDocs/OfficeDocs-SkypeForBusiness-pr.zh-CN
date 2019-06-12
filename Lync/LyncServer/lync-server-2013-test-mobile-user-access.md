---
title: 'Lync Server 2013: 测试移动用户访问'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eda2ec2d02fe4189c8e34cf700f6f1fd07895ef6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中测试移动用户访问权限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-06-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>验证计划</p></td>
<td><p>每月</p></td>
</tr>
<tr class="even">
<td><p>测试工具</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>需要权限</p></td>
<td><p>当使用 Lync Server 命令行管理程序在本地运行时, 用户必须是 RTCUniversalServerAdmins 安全组的成员。</p>
<p>使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsMcxConference cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

移动服务使移动设备用户可以执行以下操作:

1.  Exchange 即时消息和状态信息。

2.  在内部存储和检索语音邮件, 而不是无线提供商。

3.  利用 Lync 服务器功能, 例如通过工作电话和拨出式会议进行呼叫。 CsMcxConference cmdlet 提供一种快速简便的方式来验证用户是否可以使用移动设备加入和参与 Lync Server 会议。

</div>

<div>

## <a name="running-the-test"></a>运行测试

若要运行此检查, 必须为每个帐户创建三个 Windows PowerShell 凭据对象 (包含帐户名和密码的对象)。 然后, 当你调用 Test CsMcxConference 时, 你必须包含这些凭据对象和两个帐户的 SIP 地址, 如下例所示:

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

有关详细信息, 请参阅[CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet 的帮助主题。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果检查成功, 则测试 CsMcxConference 将报告成功的测试结果:

目标 Fqdn: atl-cs-001.litwareinc.com

目标 Uri:http://atl-cs-001.litwareinc.com:443/mcx

结果: 成功

延迟: 00:00:00

错误消息:

自检

如果支票未成功测试, CsMcxConference 将报告失败的测试结果。 此测试结果通常附带详细的错误消息和诊断。 例如：

目标 Fqdn: atl-cs-001.litwareinc.com

目标 Uri:https://atl-cs-001.litwareinc.com:443/mcx

结果: 失败

延迟: 00:00:00

错误消息: 未收到 Web 票证服务的任何响应。

内部异常: HHTP 请求未通过客户端授权

协商方案 "Ntlm"。 收到的身份验证标头

来自服务器的 "协商"。

内部异常: 远程服务器返回错误: (401)

便.

自检

内部诊断: X 毫秒-服务器-Fqdb: atl-cs-001.litwareinc.com

缓存控制: private

内容类型: 文本/html;字符集 = utf-8。

服务器: Microsoft-IIS/8。5

WWW-身份验证: 协商, NTLM

X-通过: ASP.NET

X-内容类型-选项: nosniff

日期: 星期三, 28 五月 2014 19:22:19 GMT

内容长度: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

如果测试 CsMcxConference 失败, 应首先验证移动服务是否正在运行且可访问。 可通过使用 web 浏览器验证是否可以访问 Lync Server 池的移动服务 URL 来执行此操作。 例如, 此命令将验证 pool atl-cs-001.litwareinc.com 的 URL:

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

如果可以访问移动服务, 则应验证测试用户是否具有有效的 Lync 服务器帐户。 你可以使用类似下面的命令检索帐户信息:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

如果 Enabled 属性不等于 True 或命令失败, 则意味着用户没有有效的 Lync 服务器帐户。你还应验证每个用户帐户是否已启用移动。 若要执行此操作, 请首先确定分配给该帐户的移动策略:

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

知道策略名称后, 请使用 CsMobilityPolicy cmdlet 验证有问题的策略 (例如, RedmondMobilityPolicy) 是否将 EnableMobility 属性设置为 True:

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

如果你在运行测试 CsMcxConference 时收到 "身份验证头" 错误消息, 这通常意味着你未指定有效的用户帐户, 请验证用户名和密码, 然后再次尝试测试。 如果您确信用户帐户有效, 请使用 CsWebServiceConfiguration cmdlet 并检查 UseWindowsAuth 属性的值。 这将告诉你在你的组织中启用了哪些身份验证方法。

有关如何解决移动服务问题的更多提示, 请参阅分步[解决外部 Lync 移动性连接问题](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)的博客文章。

</div>

</div>

<span> </span>

</div>

</div>

</div>

