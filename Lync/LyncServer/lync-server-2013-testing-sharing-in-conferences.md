---
title: 'Lync Server 2013: 测试会议中的共享'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce4cd1a45d1eddf8875d85ff28886b0c04c29cfe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a>在 Lync Server 2013 中测试会议中的共享

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-11-01_


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
<p>使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行<strong>CsDataConference</strong> cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

在 Lync Server 2013 中, 数据会议是指使用协作活动 (如 whiteboarding 或批注) 的任何会议。 **CsDataConference** cmdlet 使你能够验证一对用户是否能够参与数据会议。

</div>

<div>

## <a name="running-the-test"></a>运行测试

示例1中所示的命令验证是否可以在 pool atl-cs-001.litwareinc.com 上进行数据会议。 此命令假设你为指定的池配置了一对测试用户。 如果不存在这样的测试用户, 该命令将失败。

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

示例2中所示的命令将测试一对用户 (litwareinc\\pilar 和 litwareinc\\kenmyer) 的功能以登录 Lync Server 2013, 然后进行数据会议。 为此, 示例中的第一个命令使用**Get 凭据**Cmdlet 创建 Windows PowerShell 命令行界面凭据对象, 该对象包含用户 Pilar Ackerman 的名称和密码。 (因为登录名 (litwareinc\\pilar) 已包含为参数, 所以 "Windows PowerShell 凭据请求" 对话框仅要求管理员输入 pilar Ackerman 帐户的密码。)然后, 所生成的凭据对象将存储在名为 $cred 1 的变量中。 第二个命令执行相同操作, 这一次返回 Ken Myer 帐户的凭据对象。

使用凭据对象, 第三个命令确定这两个用户是否可以登录 Lync Server 2013 并进行数据会议。 若要执行此任务, **CsDataConference** cmdlet 与以下参数一起调用: TargetFqdn (注册机构池的 FQDN);SenderSipAddress (第一测试用户的 SIP 地址);SenderCredential (包含此同一用户的凭据的 Windows PowerShell 对象);ReceiverSipAddress (其他测试用户的 SIP 地址);和 ReceiverCredential (包含其他测试用户的凭据的 Windows PowerShell 对象)。

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果正确配置了数据会议, 则会收到与此类似的输出, 结果属性标记为**成功:**

目标 Fqdn: atl-cs-001.litwareinc.com

结果: 成功

延迟: 00:00:00

错误消息:

自检

如果指定用户无法使用数据共享, 则结果将显示为 "**失败**", 并且将在 "错误" 和 "诊断" 属性中记录其他信息:

目标 Fqdn: atl-cs-001.litwareinc.com

结果: 失败

延迟: 00:00:00

错误消息: 10060, 连接尝试失败, 因为已连接的参与方

在一段时间后未正确响应, 或者

已建立连接失败, 因为连接的主机已

无法响应\[2001: 4898: e8: f39e: 5c9a: ad83: 81b3: 9944\]: 5061

内部异常: 连接尝试失败, 因为

已连接方在一段时间后未正确响应

时间, 或已建立的连接失败, 因为已连接的主机

无法响应

\[2001: 4898: e8: f39e: 5c9a: ad83: 81b3: 9944\]: 5061

自检

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是**测试 CsDataConference**可能失败的一些常见原因:

  - 提供的参数值不正确。 如果使用, 则必须正确配置可选参数, 否则测试将失败。 重新运行不带可选参数的命令, 并查看是否成功。

  - 执行数据会议的能力取决于已分配给组织会议的用户的会议策略 (在**CsDataConference** cmdlet 的情况下为 "sender")。 如果不允许组织者在其会议中包含协作活动 (例如, 如果其会议策略将 EnableDataCollaboration 属性设置为 False), 则**CsDataConference** cmdlet 将失败。

  - 如果边缘服务器配置错误或尚未部署, 此命令将失败。

</div>

</div>

<span> </span>

</div>

</div>

</div>

