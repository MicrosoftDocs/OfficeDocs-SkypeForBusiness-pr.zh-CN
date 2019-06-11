---
title: 'Lync Server 2013: 测试与 Lync 通知的 Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Exchange to Lync notifications
ms:assetid: ed2d6325-3cf5-4450-9951-03092bcb0a7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727315(v=OCS.15)
ms:contentKeyID: 63969665
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fba2f5ad22cb4a741192d5e4d51020b8c04cc39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a>在 Lync Server 2013 中测试与 Lync 通知的 Exchange

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
<p>使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行<strong>CsExStorageNotification</strong> cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

**CsExStorageNotification** cmdlet 用于验证 Microsoft Exchange Server 2013 通知服务是否可以在每次更新用户的联系人列表时通知 Lync Server 2013。 仅当使用统一联系人存储时, 此 cmdlet 才有效。

</div>

<div>

## <a name="running-the-test"></a>运行测试

示例1测试中显示的命令可查看 Lync Server 存储服务是否可以连接到用户 sip:kenmyer@litwareinc.com 的 Microsoft Exchange Server 邮箱通知服务。 在此示例中, NetNamedPipe 用作 WCF 绑定。

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果 Exchange 集成配置正确, 则会收到与此类似的输出, 结果属性标记为**成功**:

目标 Fqdn: atl-cs-001.litwareinc.com

结果: 成功

延迟: 00:00:00

错误消息:

自检

如果指定的用户无法接收通知, 则结果将显示为 "失败", 并且将在 "错误" 和 "诊断" 属性中记录其他信息:

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

下面是**测试 CsExStorageNotification**可能失败的一些常见原因:

  - 提供的参数值不正确。 如果使用, 则必须正确配置可选参数, 否则测试将失败。 重新运行不带可选参数的命令, 并查看是否成功。

  - 如果 Microsoft Exchange Server 配置错误或尚未部署, 此命令将失败。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

