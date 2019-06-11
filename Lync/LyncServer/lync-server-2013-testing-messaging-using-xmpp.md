---
title: 'Lync Server 2013: 使用 XMPP 测试消息'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acd03cdf2a5215c980b788dbaffafc5936fe5b5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a>使用 Lync Server 2013 中的 XMPP 测试消息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-11-03_


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
<td><p>当使用 Lync Server 命令行管理程序在本地运行时, 用户必须是 RTCUniversalServerAdmins 安全组的成员。</p>
<p>使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行<strong>CsXmppIM</strong> cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

可扩展消息和状态协议 (XMPP) 是一种标准通信协议 (基于 XML), 用于通过 Internet 发送消息。 XMPP 最初被命名为 Jabber, 并且受若干 Internet 消息和通信应用程序 (如 Google 谈话和 Facebook 聊天) 支持。 **CsXmppIM** cmdlet 验证用户是否可以与 XMPP 网络上的用户交换即时消息。 请注意, 要使此测试成功, 您必须拥有 XMPP 用户的有效 SIP 地址, 并且该 SIP 地址必须位于配置为允许的 XMPP 合作伙伴的网络上。

</div>

<div>

## <a name="running-the-test"></a>运行测试

以下示例验证 pool atl-cs-001.litwareinc.com 的 XMPP 即时消息功能。 仅当为池 atl-cs-001.litwareinc.com 定义了测试用户时, 此命令才会运行。 如果有, 则该命令将确定第一个测试用户是否可以向具有 SIP 地址 adelaney@contoso.com 的用户发送 XMPP 即时消息。

如果未定义测试用户, 则该命令将失败, 因为它不会知道哪个用户登录。 如果尚未为池定义测试用户, 则必须包含 UserSipAddress 参数以及在尝试登录时命令应使用的用户的凭据。

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

下一个示例中所示的命令将测试特定用户 (litwareinc\\pilar) 的登录, 以向用户 ADELANEY@CONTOSO.COM 发送 XMPP 即时消息。 为此, 示例中的第一个命令使用 Get 凭据 cmdlet 创建 Windows PowerShell 命令行界面凭据对象, 该对象包含用户 Pilar Ackerman 的名称和密码。 (因为登录名 litwareinc\\pilar 是作为参数提供的, 所以 "Windows PowerShell 凭据请求" 对话框仅要求管理员输入 pilar Ackerman 帐户的密码。)然后, 所生成的凭据对象将存储在名为 $cred 1 的变量中。

然后, 第二个命令将检查此用户是否可以登录到 pool atl-cs-001.litwareinc.com 并发送 XMPP 即时消息。 若要运行此任务, **CsXmppIm** cmdlet 将与四个参数一起调用: TargetFqdn (注册机构池的 FQDN);接收方 (正在发送消息的用户的 SIP 地址);UserCredential (包含 Pilar Ackerman 用户凭据的 Windows PowerShell 对象);和 UserSipAddress (与提供的用户凭据对应的 SIP 地址)。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果 XMPP 即时消息配置正确, 你将收到与此类似的输出, 结果属性标记为**成功:**

目标 Fqdn: atl-cs-001.litwareinc.com

结果: 成功

延迟:00:00: 02.5361946

错误消息:

自检

如果指定用户无法使用 XMPP 即时消息, 则结果将显示为 "**失败**", 并且将在 "错误" 和 "诊断" 属性中记录其他信息:

警告: 无法读取给定的完全限定的注册机构端口号

域名 (FQDN)。 使用默认注册器端口号。 除了

InvalidOperationException: 在拓扑中找不到匹配的群集。

看

SipSyntheticTransaction. TryRetri 的 SyntheticTransactions

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

目标 Fqdn: atl-cs-001.litwareinc.com

结果: 失败

延迟: 00:00:00

错误消息: 10060, 连接尝试失败, 因为已连接的参与方

在一段时间后未正确响应, 或者

已建立连接失败, 因为连接的主机已

无法响应 10.188.116.96: 5061

内部异常: 连接尝试失败, 因为

已连接方在一段时间后未正确响应

时间, 或已建立的连接失败, 因为已连接的主机

无法响应 10.188.116.96: 5061

自检

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是**测试 CsXmppIM**可能失败的一些常见原因:

  - 提供的参数值不正确。 如果使用, 则必须正确配置可选参数, 否则测试将失败。 重新运行不带可选参数的命令, 并查看是否成功。

  - 如果 XMPP 网关配置配置错误或尚未部署, 此命令将失败。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Set-CsXmppGatewayConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

