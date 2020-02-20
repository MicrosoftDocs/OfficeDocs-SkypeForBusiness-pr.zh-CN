---
title: Lync Server 2013：测试移动用户对 exchange 即时消息的能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5885ed34fd28f06b9a7d8c4f95abc29d3b5e147
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141658"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a>测试移动用户在 Lync Server 2013 中 exchange 即时消息的功能

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-csmcxp2pim cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

移动服务使移动设备用户可以执行以下操作：

1.  Exchange 即时消息和状态信息。

2.  在内部存储和检索语音邮件，而不是使用其无线提供商。

3.  利用 Lync Server 功能，例如通过工作和拨出式会议进行呼叫。

CsMxcP2PIM cmdlet 提供了一种快速而简单的方法来验证用户是否可以使用移动服务来交换即时消息。

</div>

<div>

## <a name="running-the-test"></a>运行测试

若要运行此测试，必须为每个帐户创建两个 Windows PowerShell 凭据对象（包含帐户名和密码的对象）。 在调用 Test-csmcxp2pim 时，必须包括这些凭据对象和两个帐户的 SIP 地址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

有关详细信息，请参阅[test-csmcxp2pim](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet 的帮助主题。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果两个测试用户可以通过使用移动服务来交换即时消息，则 Test-csmcxp2pim 将返回测试结果 "成功"：

目标 Fqdn： atl-cs-001.litwareinc.com

目标 Uri：http://atl-cs-001.litwareinc.com:443/mcx

结果：成功

延迟：00:00:00

错误消息：

诊断

如果测试失败，则结果将设置为 "失败"，并将显示详细的错误消息和诊断：

目标 Fqdn： atl-cs-001.litwareinc.com

目标 Uri：https://atl-cs-001.litwareinc.com:443/mcx

结果：失败

延迟：00:00:00

错误消息：没有为 Web 票证服务收到任何响应。

内部异常：未授权的 HHTP 请求

客户端协商方案 "Ntlm"。 的身份验证

从服务器接收到的标头是 "协商，NTLM"。

内部异常：远程服务器返回错误：

（401）未经授权。

诊断

内部诊断： X-MS-Fqdb： atl-cs-

001.litwareinc.com

缓存控制： private

Content-Type： text/html;字符集 = utf-8。

服务器： Microsoft-IIS/8。5

WWW-身份验证：协商、NTLM

X-电源： ASP.NET

X-内容类型-选项： nosniff

日期：周三，28年5月 2014 19:16:05 GMT

Content-长度：6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

如果测试 Test-csmcxp2pim 失败，您的第一步应是验证移动服务是否已启动并在运行。 可通过使用 web 浏览器来验证是否可以访问 Lync Server 池的移动服务 URL 来执行此操作。 例如，以下命令将验证池 atl-cs-001.litwareinc.com 的 URL：

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

如果移动服务似乎正在运行，请验证您的两个测试用户是否具有有效的 Lync Server 帐户。 您可以使用与以下内容类似的命令检索帐户信息：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

如果 Enabled 属性不等于 True，或者如果命令失败，则表示用户没有有效的 Lync Server 帐户。

此外，还应验证用户是否已启用移动功能。 若要执行此操作，请首先确定分配给该帐户的移动策略：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

了解策略名称后，使用 Set-csmobilitypolicy cmdlet 验证相关策略（例如，RedmondMobilityPolicy）的 EnableMobility 属性是否设置为 True：

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

如果收到包含身份验证标头的错误消息，则通常意味着您未指定有效的用户帐户。 请验证用户名和密码，然后再次尝试测试。 如果你确信用户帐户有效，则使用 CsWebServiceConfiguration cmdlet 并检查 UseWindowsAuth 属性的值。 这将告诉你在组织中启用了哪些身份验证方法。有关如何对移动服务进行故障排除的更多提示，请参阅博客文章[故障排除外部 Lync 移动连接问题](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)分步。

</div>

</div>

<span> </span>

</div>

</div>

</div>

