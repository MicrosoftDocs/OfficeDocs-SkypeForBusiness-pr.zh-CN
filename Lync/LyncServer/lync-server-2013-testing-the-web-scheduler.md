---
title: 'Lync Server 2013: 测试 Web 计划程序'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: beb4030a87302c8abaaba9418eaba06b831ed8d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a>在 Lync Server 2013 中测试 Web 计划程序

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
<p>使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行<strong>CsWebScheduler</strong> cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

**CsWebScheduler** cmdlet 使你能够确定特定用户是否可以使用 Web 计划程序安排会议。 Web 计划程序允许未运行 Outlook 的用户安排联机会议。 在其他内容中, 此新功能 (它包含 Microsoft Lync Server 2010 资源工具包中随附的 Web 计划程序工具中的功能) 使用户能够:

  - 安排新的联机会议。

  - 列出他或她安排的所有会议。

  - 查看/修改现有会议。

  - 删除现有会议。

  - 使用预配置的 SMTP 邮件服务器向会议参与者发送电子邮件邀请。

  - 加入现有会议。

</div>

<div>

## <a name="running-the-test"></a>运行测试

以下示例验证 pool atl-cs-001.litwareinc.com 的 Web 计划程序。 仅当为池 atl-cs-001.litwareinc.com 定义了测试用户时, 此命令才会运行。 如果有, 则该命令将确定第一个测试用户是否可以使用 Web 计划程序安排联机会议。

如果未定义测试用户, 则该命令将失败, 因为它不会知道哪个用户登录。 如果尚未为池定义测试用户, 则必须在尝试登录时包含该命令应使用的 UserSipAddress 参数和用户凭据。

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

下一个示例中所示的命令将测试特定用户 (litwareinc\\kenmeyer) 的功能, 以使用 Web 计划程序安排联机会议。 若要执行此操作, 示例中的第一个命令使用了**Get 凭据**Cmdlet 创建 Windows PowerShell 命令行界面凭据对象, 该对象包含用户 Ken Meyer 的用户名和密码。 (由于登录名 litwareinc\\kenmeyer 包含为参数, 因此 "Windows PowerShell 凭据请求" 对话框仅要求管理员输入 Ken Meyer 帐户的密码。)然后, 所生成的凭据对象将存储在名为 $cred 1 的变量中。

然后, 第二个命令将检查此用户是否可以登录到 pool atl-cs-001.litwareinc.com 和安排联机会议。 若要运行此任务, **CsWebScheduler** cmdlet 将与三个参数一起调用: TargetFqdn (注册机构池的 FQDN);UserCredential (包含 Pilar Ackerman 用户凭据的 Windows PowerShell 对象);和 UserSipAddress (与提供的用户凭据对应的 SIP 地址)。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

如果正确配置了 web 计划程序, 则会收到类似于此的输出, 结果属性标记为 "**成功**":

目标 Fqdn: atl-cs-001.litwareinc.com

目标 Uri: https://atl-cs-001.litwareinc.com。

litwareinc.com:443/Scheduler

结果: 成功

延迟: 00:00:00

错误消息:

自检

如果 web 计划程序配置不正确, 则结果将显示为 "**失败**", 并且将在 "错误" 和 "诊断" 属性中记录其他信息:

警告: 无法读取给定的完全限定的注册机构端口号

域名 (FQDN)。 使用默认注册器端口号。 除了

InvalidOperationException: 在拓扑中找不到匹配的群集。

看

SipSyntheticTransaction. TryRetri 的 SyntheticTransactions

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

目标 Fqdn: atl-cs-001.litwareinc.com

目标 Uri:

结果: 失败

延迟: 00:00:00

错误消息: 在拓扑中找不到匹配的群集。

自检

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是**测试 CsWebScheduler**可能失败的一些常见原因:

  - 提供的参数值不正确。 如果使用, 则必须正确配置可选参数, 否则测试将失败。 重新运行不带可选参数的命令, 并查看是否成功。

  - 如果 Web 计划程序配置错误或尚未部署, 此命令将失败。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Set-CsWebServer](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

