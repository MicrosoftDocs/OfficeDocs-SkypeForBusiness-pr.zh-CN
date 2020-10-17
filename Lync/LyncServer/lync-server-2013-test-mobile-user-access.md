---
title: Lync Server 2013：测试移动用户访问
description: Lync Server 2013：测试移动用户访问。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e99a05e6ef9fe925126026452823e5edcc100ede
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541868"
---
# <a name="test-mobile-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中测试移动用户访问权限

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-06-07_


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
<td><p>所需的权限</p></td>
<td><p>在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</p>
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsMcxConference cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

移动服务使移动设备用户可以执行以下操作：

1.  Exchange 即时消息和状态信息。

2.  在内部存储和检索语音邮件，而不是使用其无线提供商。

3.  利用 Lync Server 功能，例如通过工作和拨出式会议进行呼叫。 Test-CsMcxConference cmdlet 提供了一种快速而简单的方法来验证用户是否可以使用移动设备加入和参与 Lync Server 会议。

</div>

<div>

## <a name="running-the-test"></a>运行测试

若要运行此检查，必须为每个帐户 (包含帐户名称和密码) 的对象创建三个 Windows PowerShell 凭据对象。 接下来，您必须在调用 Test-CsMcxConference 时包含这些凭据对象和 SIP 地址，如以下示例所示：

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

有关详细信息，请参阅 [CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet 的帮助主题。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果检查成功，Test-CsMcxConference 将报告成功的测试结果：

目标 Fqdn： atl-cs-001.litwareinc.com

目标 Uri： http://atl-cs-001.litwareinc.com:443/mcx

结果：成功

延迟：00:00:00

错误消息：

诊断

如果检查不成功 Test-CsMcxConference 将报告失败的测试结果。 此测试结果通常附带详细的错误消息和诊断。 例如：

目标 Fqdn： atl-cs-001.litwareinc.com

目标 Uri： https://atl-cs-001.litwareinc.com:443/mcx

结果：失败

延迟：00:00:00

错误消息：未收到 Web-Ticket 服务的响应。

内部异常： HHTP 请求未通过客户端授权

协商方案 "Ntlm"。 收到的身份验证标头

来自服务器 "协商"。

内部异常：远程服务器返回错误： (401) 

受到.

诊断

内部诊断： X-MS-服务器-Fqdb： atl-cs-001.litwareinc.com

Cache-Control： private

Content-Type： text/html;字符集 = utf-8。

服务器： Microsoft-IIS/8。5

WWW-Authenticate： Negotiate、NTLM

X-电源： ASP.NET

X-内容类型-选项： nosniff

日期：周三，28年5月 2014 19:22:19 GMT

Content-长度：6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

如果 Test-CsMcxConference 失败，应首先验证移动服务是否正在运行且可以访问。 可通过使用 web 浏览器来验证是否可以访问 Lync Server 池的移动服务 URL 来执行此操作。 例如，以下命令将验证池 atl-cs-001.litwareinc.com 的 URL：

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

如果可以访问移动服务，则应验证测试用户是否具有有效的 Lync Server 帐户。 您可以使用与以下内容类似的命令检索帐户信息：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

如果 Enabled 属性不等于 True，或者如果命令失败，则表示用户没有有效的 Lync Server 帐户。此外，还应验证每个用户帐户是否已启用移动性。 若要执行此操作，请首先确定分配给该帐户的移动策略：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

了解策略名称后，请使用 Get-CsMobilityPolicy cmdlet 确认相关策略 (例如，RedmondMobilityPolicy) 的 EnableMobility 属性设置为 True：

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

如果您在运行 Test-CsMcxConference 通常意味着您未指定有效的用户帐户时收到 "身份验证标头" 错误消息，请验证用户名和密码，然后再次尝试测试。 如果确信用户帐户有效，则使用 Get-CsWebServiceConfiguration cmdlet 并检查 UseWindowsAuth 属性的值。 这将告诉你在组织中启用了哪些身份验证方法。

有关如何对移动服务进行故障排除的更多提示，请参阅博客文章 [故障排除外部 Lync 移动连接问题](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)分步。

</div>

</div>

<span> </span>

</div>

</div>

</div>

