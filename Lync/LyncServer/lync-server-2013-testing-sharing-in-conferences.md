---
title: Lync Server 2013：测试会议中的共享
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7a98312c04b943d485e1c6668b1c9347c9714e1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a>在 Lync Server 2013 中测试会议中的共享

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-11-01_


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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行<strong>CsDataConference</strong> cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

在 Lync Server 2013 中，数据会议是指使用协作活动（如白板或批注）的任何会议。 **CsDataConference** cmdlet 使您能够验证一对用户是否能够参与数据会议。

</div>

<div>

## <a name="running-the-test"></a>运行测试

示例 1 中显示的命令验证是否可以在池 atl-cs-001.litwareinc.com 上召开数据会议。此命令假定您已为指定的池配置了一对测试用户。如果不存在此类测试用户，此命令将失败。

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

示例2中显示的命令测试一对用户（litwareinc\\pilar 和 litwareinc\\kenmyer）的功能，以登录 Lync Server 2013，然后进行数据会议。 为执行此操作，示例中的第一个命令使用**Get-Credential** Cmdlet 创建 Windows PowerShell 命令行接口 Credential 对象，其中包含用户 Pilar Ackerman 的名称和密码。 （因为登录名（litwareinc\\pilar）已作为参数包含，所以 "Windows PowerShell 凭据请求" 对话框仅要求管理员输入 pilar Ackerman 帐户的密码。）然后，将生成的 credential 对象存储在名为 $cred 1 的变量中。 第二个命令执行相同的操作，但这次返回的是 Ken Myer 帐户的凭据对象。

使用 credential 对象时，第三个命令确定这两个用户是否可以登录 Lync Server 2013 并进行数据会议。 若要执行此任务，请调用**CsDataConference** cmdlet 以及以下参数： TargetFqdn （注册器池的 FQDN）;SenderSipAddress （第一个测试用户的 SIP 地址）;SenderCredential （包含此同一用户的凭据的 Windows PowerShell 对象）;ReceiverSipAddress （其他测试用户的 SIP 地址）;和 ReceiverCredential （包含其他测试用户的凭据的 Windows PowerShell 对象）。

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果正确配置了数据会议，则会收到类似于以下内容的输出，并将 Result 属性标记为**成功：**

目标 Fqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00:00:00

错误消息：

诊断

如果指定用户不能使用数据共享，则结果将显示为 "**失败**"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：

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

以下是**测试 CsDataConference**可能失败的一些常见原因：

  - 提供的参数值不正确。 如果使用，则必须正确配置可选参数或测试将失败。 重新运行不带可选参数的命令，并查看是否成功。

  - 执行数据会议的能力取决于已分配给组织会议的用户的会议策略（如果是**CsDataConference** cmdlet，则为 "sender"）。 如果不允许组织者在他或她的会议中包含协作活动（例如，如果其会议策略将 EnableDataCollaboration 属性设置为 False），则**CsDataConference** cmdlet 将失败。

  - 如果边缘服务器配置错误或尚未部署，则此命令将失败。

</div>

</div>

<span> </span>

</div>

</div>

</div>

