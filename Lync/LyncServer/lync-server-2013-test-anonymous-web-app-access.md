---
title: Lync Server 2013：测试匿名 Web 应用访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test anonymous Web App access
ms:assetid: 92f691cd-e05e-4bab-beb5-251d4b837a19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767949(v=OCS.15)
ms:contentKeyID: 63969630
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9df6a040e71b0dfe82a52cf519357d058b78a1d7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-anonymous-web-app-access-in-lync-server-2013"></a>在 Lync Server 2013 中测试匿名 Web 应用访问

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsWebAppAnonymous cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebAppAnonymous&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsWebAppAnonymous cmdlet 验证匿名用户是否可以使用 Lync Web App 加入 Lync Server 会议。 运行 cmdlet 时，CsWebAppAnonymous 会与 Web 票证服务联系，以获取匿名用户的 web 票证。 如果 cmdlet 成功获取此票证，则 CsWebAppAnonymous 将与 Lync Server 联系，并尝试建立独立会议以实现即时消息、应用程序共享和数据协作。

请注意，测试 CsWebAppAnonymous 仅验证用于创建这些会议的 Api 和连接。 此 cmdlet 不会实际创建和执行任何会议。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsWebAppAnonymous cmdlet 可使用一对预配置的测试帐户或任何两个已启用 Lync Server 的用户的帐户运行。 若要使用测试帐户运行此检查，只需指定要测试的 Lync Server 池的完全限定的域名即可。 例如：

    Test-CsWebAppAnonymous -TargetFqdn atl-cs-001.litwareinc.com

若要使用实际用户帐户运行此检查，必须为每个帐户创建两个 Lync Server 命令行管理程序凭据对象（包含帐户名和密码的对象）。 在调用 CsWebAppAnonymous 时，必须包括这些凭据对象和两个帐户的 SIP 地址：

    $cred1 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1

有关详细信息，请参阅 CsWebAppAnonymous cmdlet 的帮助主题。 请注意，CsWebAppAnonymous 已弃用，无法在 Lync Server 2013 上使用。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果 CsWebAppAnonymous 可以将匿名用户加入到他或她的会议中，该 cmdlet 将返回测试结果成功：

目标 Fqdn：

结果：成功

延迟：00:00:00

错误消息：

诊断

如果匿名用户不能加入必要的会议，则测试结果将被标记为失败。 通常情况下，CsWebAppAnonymous 还将报告回详细的错误消息和诊断：

目标 Fqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00：00：05.9746266

错误消息：没有为 Web 票证服务收到任何响应

诊断： HTTP 请求未通过客户端授权

身份验证方案 "Ntlm"。 的身份验证

从服务器接收到的标头是 "协商，NTLM"。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

CsWebAppAnonymous 故障通常围绕用户身份验证错误进行旋转：必须使用有效的用户帐户运行测试，即使 cmdlet 检查匿名用户连接到 Lync Server 的能力也是如此。 如果 CsWebAppAnonymous 失败，应验证指定的用户是否具有有效的 Lync Server 用户帐户。 您可以通过使用类似如下的命令来检索 Lync Server 帐户信息：

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

如果 Enabled 属性不等于 True，或者如果命令失败，则表示用户没有有效的 Lync Server 帐户。

您还应验证在运行 cmdlet 时提供的密码是否是有效的密码。

Office Web Apps Server 的配置问题也可能导致测试 CsWebAppAnonymous 失败。如果你收到以下诊断，则通常会出现这种情况：

HTTP 请求未通过客户端身份验证方案 "Ntlm" 进行授权。 从服务器收到的身份验证标头为 "协商，NTLM"。

有关诊断和解决 Office Web Apps Server 问题的详细信息，请参阅博客文章[Office Web Apps server 2013-计算机始终报告为](http://www.wictorwilen.se/office-web-apps-server-2013---machines-are-always-reported-as-unhealthy)"不正常"。

</div>

</div>

<span> </span>

</div>

</div>

</div>

