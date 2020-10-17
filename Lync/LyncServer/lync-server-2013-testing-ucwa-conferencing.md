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
ms.openlocfilehash: 5879eaa10b128bedbc1e28fe85cee40aed27dddd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503909"
---
# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中测试 UCWA 会议

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 <strong>test-csucwaconference</strong> cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

**Test-csucwaconference** cmdlet 验证一对测试用户是否可以使用统一通信 Web API (UCWA) 计划、加入和执行联机会议。 为此，该 cmdlet 使用 Lync Server web 票证服务对两个测试用户进行身份验证，并将其注册到 Lync Server。 然后，此 cmdlet 使用组织者凭据启动会议，并邀请参与者加入会议。 在加入会议后， **test-csucwaconference** cmdlet 将验证用户是否可以执行 exchange 即时消息和执行池操作，然后断开会议并注销这两个测试用户。 在测试完成后，也会删除计划的会议。

**Test-csucwaconference** cmdlet 还可用于确定匿名用户是否可以加入联机会议。

请注意，除非在该池上安装了 UCWA，否则不应对 Microsoft Lync Server 2010 池运行 **test-csucwaconference** cmdlet。 如果尚未安装 UCWA，则对 **test-csucwaconference** cmdlet 的调用将失败。

</div>

<div>

## <a name="running-the-test"></a>运行测试

示例 1 中显示的命令可验证一对测试用户是否可以参加池 atl-cs-001.litwareinc.com 上的 UCWA 会议。请注意，如果您尚未针对 atl-cs-001.litwareinc.com 预先定义一对运行状况监控配置测试用户，此命令将会失败。

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

示例2中显示的命令测试一对用户 (litwareinc \\ pilar 和 litwareinc \\ kenmyer) 参与 UCWA 会议的能力。 若要执行此操作，示例中的第一个命令使用 Get-Credential cmdlet 来创建 Windows PowerShell 命令行接口 credential 对象，该对象包含用户 Pilar Ackerman 的名称和密码。  (因为登录名 litwareinc \\ pilar 包含为参数，所以 "Windows PowerShell 凭据请求" 对话框仅要求管理员输入 Pilar Ackerman 帐户的密码。 ) 生成的凭据对象将存储在名为 $cred 1 的变量中。 第二个命令执行相同的操作，但这次返回的是 Ken Myer 帐户的凭据对象。

使用这两个 credential 对象时，示例中的第三个命令确定两个用户是否可以参与 UCWA 会议。 若要运行此任务，请调用 **test-csucwaconference** cmdlet 以及以下参数： TargetFqdn (注册器池的 FQDN) ;OrganizerSipAddress (会议组织者) 的 SIP 地址;OrganizerCredential (包含此同一用户的凭据的 Windows PowerShell 对象) ;ParticipantSipAddress (其他测试用户) 的 SIP 地址;和 ParticipantCredential (Windows PowerShell 命令行接口对象，其中包含其他用户) 的凭据。

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果正确配置了会议，则会收到类似于以下内容的输出，并将 Result 属性标记为 **成功：**

目标 Fqdn： atl-cs-001.litwareinc.com

目标 Uri： https://LyncTest-LyncTest。

Microsoft.com:443/CertProv/CertProvisiongService.svc

结果：成功

延迟：00：00：14.9862716

错误消息：

诊断

如果指定用户不能使用会议，则结果将显示为 " **失败**"，并在 "错误" 和 "诊断" 属性中记录其他信息：

警告：无法读取给定的完全限定的注册器端口号

 (FQDN) 的域名称。 使用默认注册器端口号。 异常

InvalidOperationException：在拓扑中找不到匹配的群集。

个

TryRetri 的 SipSyntheticTransaction。 SyntheticTransactions

eveRegistrarPortFromTopology (Int32& registrarPortNumber) 

Test-CsUcwaConference：没有分配的测试用户

\[LyncTest.SelfHost.Corp.Microsoft.com \] 。 验证测试用户配置。

位于第1行：1个字符：1

\+ Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+ CategoryInfo： ResourceUnavailable： (： ) \[ Test-test-csucwaconference\]

，InvalidOperationException

\+ FullyQualifiedErrorId： NotFoundTestUsers、

eticTransactions.TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

以下是 **测试 test-csucwaconference** 可能失败的一些常见原因：

  - 提供的参数值不正确。 如果使用，则必须正确配置可选参数或测试将失败。 重新运行不带可选参数的命令，并查看是否成功。

  - 执行会议的能力取决于已分配给组织会议的用户的会议策略 (在 **test-csucwaconference** cmdlet 中，即 "sender" ) 的情况。 如果不允许组织者在他或她的会议中包含协作活动 (例如，如果其会议策略将 EnableDataCollaboration 属性设置为 False) 则 **test-csucwaconference** cmdlet 将失败。

  - 如果边缘服务器配置错误或尚未部署，则此命令将失败。

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

