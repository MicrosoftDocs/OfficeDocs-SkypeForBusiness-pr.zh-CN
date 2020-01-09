---
title: Lync Server 2013：测试将推送通知发送到智能手机
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 653becc1cc22abc8b3c04e0ab3d2a2d1260a98d9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a>在 Lync Server 2013 中测试指向智能电话的推送通知

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2017-03-15_


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
<p>使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行 CsMcxPushNotification cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

推送通知服务（Apple 推送通知服务和 Microsoft 推送通知服务）可以向移动设备（如 Iphone 和 Windows 电话）发送有关事件（如新即时消息或新语音邮件）的通知，即使 Lync 客户端在这些设备上，当前暂停或在后台运行。 推送通知服务是在 Microsoft 服务器上运行的基于云的服务。 为了利用推送通知，你必须能够连接到推送通知交换所并进行身份验证。 CsMcxPushNotification cmdlet 使管理员能够验证推送通知请求是否可以通过 Edge 服务器路由到推送通知交换所。

</div>

<div>

## <a name="running-the-test"></a>运行测试

若要测试推送通知服务，请调用 CsMcxPushNotification cmdlet。 请确保指定 Edge 服务器的完全限定的域名：

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

有关详细信息，请参阅[CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) cmdlet 的帮助主题。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果 Test CsMcxPushNotification 成功，cmdlet 将返回测试结果成功：

TargetFqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00:00:00

时发生

自检

如果 CsMcxPushNotification 无法连接到推送通知交换所，则 cmdlet 通常不会返回测试结果失败。 相反，此命令通常完全失败。 例如：

测试-CsMcxPushNotification：从网络收到504（服务器超时）响应，操作失败。 有关详细信息，请参阅异常详细信息。

在第一行：1个字符：27

\+\< \< CsMcxPushNotification \< - \< AccessEdgeFqdn lyncedge.mydomain.com

\+CategoryInfo： OperationStopped：（:)\[Test-CsMcxPushNotification\]、FailureResponseException

\+FullyQualifiedErrorId： WorkflowNotCompleted、SyntheticTransactions TestMcxPushNotificationCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

如果推送通知服务失败通常表示与边缘服务器通信的问题，或者与推送通知交换所进行通信的问题。 如果在运行 Test CsMcxPushNotification 时遇到问题，您应执行的第一件事是验证边缘服务器是否正常工作。 执行此操作的一种方法是使用 CsAVEdgeConnectivity cmdlet：

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

此检查将验证指定用户是否可以连接到边缘服务器。

如果边缘服务器似乎正常工作，则这通常意味着你无法连接到推送通知 clearinghouse。 反过来，这通常意味着你未正确配置 clearinghouse URI 或你没有指向此 URL 的 DNS SRV 记录。 你可以通过运行以下命令验证 URI 是否设置为正确的值（sip:push@push.lync.com）：

    Get-CsMcxConfiguration

如果 PushNotificationProxyUri 属性设置为 sip:push@push.lync.com 以外的任何其他内容，则可以使用 McxConfiguration cmdlet 更正该问题。 例如，此命令在整个组织中正确设置 URI：

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

有关详细信息，请参阅[CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) cmdlet 的帮助主题。

如果 URI 配置正确，则下一步应该是验证你是否具有解析为 SIP 域和边缘服务器的 DNS SRV 记录。 有关如何配置这些记录的详细信息，请参阅移动性的帮助主题 DNS 要求。 请注意，以下错误消息通常表示 DNS 记录的问题：

从网络收到504（服务器超时）响应，操作失败。 有关详细信息，请参阅异常详细信息。

也可能该测试 CsMcxConfiguration 将失败，并出现以下错误消息：

Test-CsMcxPushNotification：推送通知请求被拒绝。

在第一行：1个字符：27

\+Test-CsMcxPushNotification\<\<\<\<

\+CategoryInfo： OperationStopped：（:)\[Test-CsMcxPushNotification\]、SyntheticTransactionException

\+FullyQualifiedErrorId： WorkflowNotCompleted、SyntheticTransactions TestMcxPushNotificationCmdlet

如果启用了 URL 筛选并阻止了 http：和 https：前缀，则通常会出现 "推送通知请求被拒绝" 消息。 你可以使用类似如下的命令确定被阻止的前缀：

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

如果结果中显示了 "http：" 或 "https："，则必须将其从 "阻止的前缀" 列表中删除，"推送通知" 才能正常工作。 这可以通过使用以下类似命令来实现：

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

有关详细信息，请参阅[CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

