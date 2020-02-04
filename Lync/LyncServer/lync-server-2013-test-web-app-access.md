---
title: Lync Server 2013：测试 Web 应用访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test Web App access
ms:assetid: 17d67ea3-f74d-4952-ac2b-92c0dacc8014
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767944(v=OCS.15)
ms:contentKeyID: 63969584
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7618bcc9a69d177950bae64354106a67721e822a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-web-app-access-in-lync-server-2013"></a>在 Lync Server 2013 中测试 Web 应用访问

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
<p>使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsWebApp cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsWebApp cmdlet 验证经过身份验证的用户是否可以使用 Lync Web App 加入 Lync Server 会议。 运行 cmdlet 时，CsWebApp 将与 Web 票证服务联系以获取指定用户的 Web 入场券。 这些入场券有效地充当 Lync Server 会议的 "许可票证"。 如果可以检索票证，并且如果用户可以进行身份验证，则 CsWebApp 将联系 Lync Server 并尝试建立单独的会议，以便发送即时消息、应用程序共享和数据协作。

请注意，测试 CsWebApp 只是验证用于创建这些会议的 Api 和连接。 此 cmdlet 旨在验证 Lync Web App 是否可用于创建和加入会议。 但是，它实际上不会创建和开展会议。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsWebApp cmdlet 可以使用一对预配置的测试帐户或任何两个已启用 Lync Server 的用户的帐户运行。 若要使用测试帐户运行此检查，只需指定正在测试的 Lync Server 池的完全限定的域名。 例如：

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

若要使用实际用户帐户运行此检查，必须为每个帐户创建两个 Windows PowerShell 凭据对象（包含帐户名和密码的对象）。 然后，当你调用 Test-CsWebApp 时，你必须包含这些凭据对象和两个帐户的 SIP 地址：

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

有关详细信息，请参阅[CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) cmdlet 的帮助主题。 请注意，CsWebApp 已弃用，无法在 Lync Server 2013 上使用。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果 CsWebApp 可以将用户加入他们的会议，cmdlet 将返回测试结果成功：

目标 Fqdn：

结果：成功

延迟：00:00:00

错误消息：

自检

如果用户无法加入必要的会议，则测试结果将标记为 "失败"。 通常情况下，CsWebApp 测试还将报告详细的错误消息和诊断：

目标 Fqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00:00:00

错误消息：未收到 Web 票证服务的响应

诊断： HTTP 请求未通过客户端授权

身份验证方案 "Ntlm"。 的身份验证

从服务器收到的标头是 "协商，NTLM"。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

测试 CsWebApp 故障通常涉及用户身份验证错误。 如果 CsWebApp 测试失败，应首先验证指定用户是否具有有效的用户帐户，并且是否已为 Lync Server 启用。 你可以使用类似下面的命令检索帐户信息：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

如果 Enabled 属性不等于 True 或命令失败，则意味着用户没有有效的 Lync 服务器帐户。你还应验证你提供给 cmdlet 的密码是否有效。

</div>

</div>

<span> </span>

</div>

</div>

</div>

