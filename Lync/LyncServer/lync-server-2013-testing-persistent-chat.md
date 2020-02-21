---
title: Lync Server 2013：测试持久聊天
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2177e4fce4d32bb2dc6c82e1f3fecae367eb2543
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a>在 Lync Server 2013 中测试持久聊天

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行<strong>CsPersistentChatMessage</strong> cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

**CsPersistentChatMessage** cmdlet 验证一对测试用户是否可以使用持久聊天服务交换邮件。 为执行此操作，cmdlet 会将两个用户记录到 Lync Server 2013，将用户连接到持久聊天室，交换一对消息，然后退出聊天室并注销两个用户。 请注意，如果您没有创建任何聊天室，或者没有为两个测试用户帐户分配可访问持久聊天服务的持久聊天策略，则调用此 cmdlet 将会失败。

</div>

<div>

## <a name="running-the-test"></a>运行测试

以下示例中所示的命令测试一对用户（litwareinc\\pilar 和 litwareinc\\kenmyer）以登录到 Lync Server 2013，然后使用持久聊天服务交换邮件的功能。 为执行此操作，示例中的第一个命令使用**Get-Credential** Cmdlet 创建 Windows PowerShell 命令行接口 Credential 对象，该对象包含用户 Pilar Ackerman 的名称和密码。 （因为登录名（litwareinc\\pilar）包含为参数，所以 "Windows PowerShell 凭据请求" 对话框仅要求管理员输入 pilar Ackerman 帐户的密码。）然后，将生成的凭据对象存储在名为 $cred 1 的变量中。 第二个命令执行相同的操作，但这次返回的是 Ken Myer 帐户的凭据对象。

使用 credential 对象时，第三个命令将确定这两个用户是否可以使用持久聊天登录 Lync Server 2013 和 exchange 邮件。 若要执行此任务，请使用以下参数调用**CsPersistentChatMessage** Cmdlet： TargetFqdn （注册器池的 FQDN）;SenderSipAddress （第一个测试用户的 SIP 地址）;SenderCredential （包含此同一用户的凭据的 Windows PowerShell 对象）;ReceiverSipAddress （其他测试用户的 SIP 地址）;和 ReceiverCredential （包含其他测试用户的凭据的 Windows PowerShell 对象）。

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果指定用户具有有效的位置策略，则将接收与以下内容类似的输出，并将 Result 属性标记为 "**成功**"：

目标 Fqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00:00:00

错误消息：

诊断

如果指定用户无法使用持久聊天服务交换邮件，则结果将显示为 "**失败**"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：

警告：无法读取给定的完全限定的注册器端口号

域名（FQDN）。 使用默认注册器端口号。 异常

InvalidOperationException：在拓扑中找不到匹配的群集。

个

TryRetri 的 SipSyntheticTransaction。 SyntheticTransactions

eveRegistrarPortFromTopology （Int32& registrarPortNumber）

目标 Fqdn： atl-cs-001.litwareinc.com

结果：失败

延迟：00:00:00

错误消息：10060，连接尝试失败，因为连接方

在一段时间后未正确响应，或者

已建立连接失败，因为连接的主机具有

无法响应\[2001：4898： e8： f39e：5c9a： ad83：81b3： 9944\]：5061

内部异常：连接尝试失败，因为

连接方在一段时间后未正确响应

时间，或已建立的连接失败，因为连接的主机

未能响应

\[2001：4898： e8： f39e：5c9a： ad83：81b3： 9944\]：5061

诊断

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

以下是**测试 CsPersistentChatMessage**可能失败的一些常见原因：

  - 提供的参数值不正确。 所需的测试帐户可能不存在或已正确创建。

  - 可能存在导致测试超时的意外延迟的网络问题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Grant-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[新 CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

