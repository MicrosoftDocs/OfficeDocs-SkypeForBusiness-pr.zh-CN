---
title: Lync Server 2013：测试移动用户交换即时消息的能力
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
ms.openlocfilehash: db5af113c6ea87a700ca824bcef09b525338f4e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a>测试移动用户在 Lync Server 2013 中交换即时消息的能力

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-06-07_


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
<td><p>当使用 Lync Server 命令行管理程序在本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</p>
<p>使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsMcxP2PIM cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

移动服务使移动设备用户可以执行以下操作：

1.  Exchange 即时消息和状态信息。

2.  在内部存储和检索语音邮件，而不是无线提供商。

3.  利用 Lync 服务器功能，例如通过工作电话和拨出式会议进行呼叫。

CsMxcP2PIM cmdlet 提供一种快速简便的方法来验证用户是否可以使用移动服务来交换即时消息。

</div>

<div>

## <a name="running-the-test"></a>运行测试

若要运行此测试，必须为每个帐户创建两个 Windows PowerShell 凭据对象（包含帐户名和密码的对象）。 然后，当你调用 Test-CsMcxP2PIM 时，你必须包含这些凭据对象和两个帐户的 SIP 地址：

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

有关详细信息，请参阅[CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet 的帮助主题。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果两个测试用户可以使用移动服务来交换即时消息，则 CsMcxP2PIM 将返回测试结果成功：

目标 Fqdn： atl-cs-001.litwareinc.com

目标 Uri：http://atl-cs-001.litwareinc.com:443/mcx

结果：成功

延迟：00:00:00

错误消息：

自检

如果测试失败，则结果将设置为 "失败"，并且将显示详细的错误消息和诊断：

目标 Fqdn： atl-cs-001.litwareinc.com

目标 Uri：https://atl-cs-001.litwareinc.com:443/mcx

结果：失败

延迟：00:00:00

错误消息：未收到 Web 票证服务的任何响应。

内部异常： HHTP 请求未经授权

客户端协商方案 "Ntlm"。 的身份验证

从服务器收到的标头是 "协商，NTLM"。

内部异常：远程服务器返回错误：

（401）未经授权。

自检

内部诊断： X-MS-服务器 Fqdb： atl-cs-

001.litwareinc.com

缓存控制： private

内容类型：文本/html;字符集 = utf-8。

服务器： Microsoft-IIS/8。5

WWW-身份验证：协商，NTLM

X-通过： ASP.NET

X-内容类型-选项： nosniff

日期：星期三，28五月 2014 19:16:05 GMT

内容长度：6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

如果测试 CsMcxP2PIM 失败第一步应验证移动服务是否已启动并正在运行。 可通过使用 web 浏览器验证是否可以访问 Lync Server 池的移动服务 URL 来执行此操作。 例如，此命令将验证 pool atl-cs-001.litwareinc.com 的 URL：

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

如果移动服务似乎正在运行，请验证你的两个测试用户是否具有有效的 Lync 服务器帐户。 你可以使用类似下面的命令检索帐户信息：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

如果 Enabled 属性不等于 True 或命令失败，则意味着用户没有有效的 Lync 服务器帐户。

你还应验证用户是否已启用移动。 若要执行此操作，请首先确定分配给该帐户的移动策略：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

知道策略名称后，请使用 CsMobilityPolicy cmdlet 验证有问题的策略（例如，RedmondMobilityPolicy）是否将 EnableMobility 属性设置为 True：

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

如果收到一条带有身份验证头的错误消息，这通常意味着你没有指定有效的用户帐户。 验证用户名和密码，然后再次尝试测试。 如果您确信用户帐户有效，请使用 CsWebServiceConfiguration cmdlet 并检查 UseWindowsAuth 属性的值。 这将告诉你在你的组织中启用了哪些身份验证方法。有关如何解决移动服务问题的更多提示，请参阅分步[解决外部 Lync 移动性连接问题](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)的博客文章。

</div>

</div>

<span> </span>

</div>

</div>

</div>

