---
title: Lync Server 2013：使用 XMPP 测试邮件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79af6165da1c8d5093912f36413ef98812226cbc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518989"
---
# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a>在 Lync Server 2013 中使用 XMPP 测试邮件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-11-03_


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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 <strong>CsXmppIM</strong> cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

可扩展消息传递和状态协议 (XMPP) 是用于在 Internet 中发送消息的标准通信协议（基于 XML）。 XMPP 最初被命名为 Jabber，并受几个 Internet 邮件和通信应用程序（如 Google 谈话和 Facebook 聊天）的支持。 **CsXmppIM** cmdlet 验证用户是否可以与 XMPP 网络上的用户交换即时消息。 请注意，为使此测试成功，必须为 XMPP 用户提供有效的 SIP 地址，并且该 SIP 地址必须位于配置为允许的 XMPP 合作伙伴的网络中。

</div>

<div>

## <a name="running-the-test"></a>运行测试

下面的示例验证 pool atl-cs-001.litwareinc.com 的 XMPP 即时消息功能。 仅当为池 atl-cs-001.litwareinc.com 定义了测试用户时，才会运行此命令。 如果有，则该命令将确定第一个测试用户是否可以向具有 SIP 地址 adelaney@contoso.com 的用户发送 XMPP 即时消息。

如果未定义测试用户，则命令将失败，因为它不会知道哪个用户登录。 如果尚未为池定义测试用户，则必须包括 UserSipAddress 参数以及在尝试登录时该命令应使用的用户的凭据。

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

下一示例中显示的命令测试特定用户 (litwareinc \\ pilar) 登录以将 XMPP 即时消息发送到用户 adelaney@contoso.com 的功能。 若要执行此操作，示例中的第一个命令使用 Get-Credential cmdlet 来创建 Windows PowerShell 命令行接口 credential 对象，该对象包含用户 Pilar Ackerman 的名称和密码。  (因为登录名 litwareinc \\ pilar 作为参数包括在内，所以 "Windows PowerShell 凭据请求" 对话框仅要求管理员输入 Pilar Ackerman 帐户的密码。 ) 生成的 Credential 对象将存储在名为 $cred 1 的变量中。

然后，第二个命令将检查此用户是否可以登录到池 atl-cs-001.litwareinc.com 并发送 XMPP 即时消息。 若要运行此任务，请调用 **CsXmppIm** cmdlet 以及四个参数： TargetFqdn (注册器池的 FQDN) ;接收器 (要向其发送邮件的用户的 SIP 地址) ;UserCredential (包含 Pilar Ackerman 的用户凭据的 Windows PowerShell 对象) ;和 UserSipAddress (与提供的用户凭据) 相对应的 SIP 地址。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果正确配置 XMPP 即时消息，则会收到类似于以下内容的输出，并将 Result 属性标记为 **成功：**

目标 Fqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：02.5361946

错误消息：

诊断

如果指定用户无法使用 XMPP 即时消息，则结果将显示为 " **失败**"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：

警告：无法读取给定的完全限定的注册器端口号

 (FQDN) 的域名称。 使用默认注册器端口号。 异常

InvalidOperationException：在拓扑中找不到匹配的群集。

个

TryRetri 的 SipSyntheticTransaction。 SyntheticTransactions

eveRegistrarPortFromTopology (Int32& registrarPortNumber) 

目标 Fqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00:00:00

错误消息：10060，连接尝试失败，因为连接方

在一段时间后未正确响应，或者

已建立连接失败，因为连接的主机具有

未能响应10.188.116.96：5061

内部异常：连接尝试失败，因为

连接方在一段时间后未正确响应

时间，或已建立的连接失败，因为连接的主机

未能响应10.188.116.96：5061

诊断

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

以下是 **测试 CsXmppIM** 可能失败的一些常见原因：

  - 提供的参数值不正确。 如果使用，则必须正确配置可选参数或测试将失败。 重新运行不带可选参数的命令，并查看是否成功。

  - 如果 XMPP 网关配置配置不正确或尚未部署，则此命令将失败。

</div>

<div>

## <a name="see-also"></a>另请参阅


[CsXmppGatewayConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

