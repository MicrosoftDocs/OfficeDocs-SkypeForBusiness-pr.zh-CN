---
title: Lync Server 2013：测试 UCWA 会议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9496b2a860f0a8272d6eb98df6a2c897aa245ec9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中测试 UCWA 会议

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-11-03_


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
<td><p>当使用 Lync Server 命令行管理程序在本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</p>
<p>使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行<strong>CsUcwaConference</strong> cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

**CsUcwaConference** cmdlet 验证一对测试用户是否可以使用统一通信 Web API （UCWA）安排、加入和召开联机会议。 为此，cmdlet 使用 Lync Server web ticket 服务对这两个测试用户进行身份验证，并使用 Lync Server 注册它们。 然后，该 cmdlet 使用组织者凭据启动会议，并邀请参与者加入会议。 加入会议后， **CsUcwaConference** cmdlet 验证用户是否可以执行诸如 exchange 即时消息和执行池之类的操作，然后断开会议并注销两个测试用户。 计划的会议在测试完成后也会被删除。

**CsUcwaConference** cmdlet 还可用于确定匿名用户是否可以加入联机会议。

请注意，除非在该池中安装了 UCWA，否则不应针对 Microsoft Lync Server 2010 池运行**CsUcwaConference** cmdlet。 如果 UCWA 尚未安装，则对**CsUcwaConference** cmdlet 的调用将失败。

</div>

<div>

## <a name="running-the-test"></a>运行测试

示例1中所示的命令验证一对测试用户是否可以参与 pool atl-cs-001.litwareinc.com 上的 UCWA 会议。 请注意，如果尚未预定义一对 atl-cs-001.litwareinc.com 的运行状况监视配置测试用户，此命令将失败。

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

示例2中所示的命令测试一对用户（litwareinc\\pilar 和 litwareinc\\kenmyer）的功能以参与 UCWA 会议。 为此，示例中的第一个命令使用 Get 凭据 cmdlet 创建 Windows PowerShell 命令行界面凭据对象，该对象包含用户 Pilar Ackerman 的名称和密码。 （由于 "登录名"、\\"litwareinc pilar" 已作为参数包含，因此 "Windows PowerShell 凭据请求" 对话框仅要求管理员输入 pilar Ackerman 帐户的密码。）然后，所生成的凭据对象将存储在名为 $cred 1 的变量中。 第二个命令执行相同操作，这一次返回 Ken Myer 帐户的凭据对象。

使用这两个凭据对象，示例中的第三个命令确定两个用户是否可以参与 UCWA 会议。 若要运行此任务， **CsUcwaConference** cmdlet 与以下参数一起调用： TargetFqdn （注册机构池的 FQDN）;OrganizerSipAddress （会议组织者的 SIP 地址）;OrganizerCredential （包含此同一用户的凭据的 Windows PowerShell 对象）;ParticipantSipAddress （其他测试用户的 SIP 地址）;和 ParticipantCredential （包含其他用户的凭据的 Windows PowerShell 命令行界面对象）。

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果会议配置正确，你将收到类似于此的输出，结果属性标记为 "**成功"：**

目标 Fqdn： atl-cs-001.litwareinc.com

目标 Uri： https://LyncTest-LyncTest。

Microsoft.com:443/CertProv/CertProvisiongService.svc

结果：成功

延迟：00：00：14.9862716

错误消息：

自检

如果指定用户无法使用会议，则结果将显示为 "**失败**"，并且将在 "错误" 和 "诊断" 属性中记录其他信息：

警告：无法读取给定的完全限定的注册机构端口号

域名（FQDN）。 使用默认注册器端口号。 除了

InvalidOperationException：在拓扑中找不到匹配的群集。

看

SipSyntheticTransaction. TryRetri 的 SyntheticTransactions

eveRegistrarPortFromTopology （Int32& registrarPortNumber）

Test-CsUcwaConference：没有分配测试用户

\[LyncTest.SelfHost.Corp.Microsoft.com\]。 验证测试用户配置。

在第1行：1个字符：1

\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo： ResourceUnavailable：（:)\[Test-CsUcwaConference\]

, InvalidOperationException

\+FullyQualifiedErrorId： NotFoundTestUsers、

eticTransactions.TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是**测试 CsUcwaConference**可能失败的一些常见原因：

  - 提供的参数值不正确。 如果使用，则必须正确配置可选参数，否则测试将失败。 重新运行不带可选参数的命令，并查看是否成功。

  - 执行会议的功能取决于已分配给组织会议的用户的会议策略（在**CsUcwaConference** cmdlet 的情况下为 "sender"）。 如果不允许组织者在其会议中包含协作活动（例如，如果其会议策略将 EnableDataCollaboration 属性设置为 False），则**CsUcwaConference** cmdlet 将失败。

  - 如果边缘服务器配置错误或尚未部署，此命令将失败。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

