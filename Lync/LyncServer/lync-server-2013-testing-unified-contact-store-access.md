---
title: Lync Server 2013：测试统一联系人存储区访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34dbf6ede9f58b39df1722e742511ee0844c41f7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42218288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a>在 Lync Server 2013 中测试统一联系人存储区访问

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-05-15_


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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行<strong>test-csunifiedcontactstore</strong> cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

Lync Server 2013 中引入的统一联系人存储使管理员可以选择将用户的联系人存储在 Microsoft Exchange Server 2013 中，而不是在 Lync Server 中。 这样，除了 Lync 2013 之外，用户还可以访问 Outlook Web Access 中的一组相同的联系人。 （或者，您可以继续在 Lync Server 中存储联系人。 在这种情况下，用户将必须维护两组独立的联系人：一个用于 Outlook 和 Outlook Web Access，另一个用于 Lync 2013。）

您可以通过运行**test-csunifiedcontactstore** cmdlet 来确定是否已将用户的联系人移动到统一联系人存储库。 **Test-csunifiedcontactstore** cmdlet 将使用指定的用户帐户，并连接到统一的联系人存储库，并尝试为该用户检索联系人。 如果不能检索联系人，则命令将会失败，并出现 "该用户未收到联系人信息" 消息。 ”

请注意，如果用户已成功迁移到统一联系人存储区，但其联系人列表中没有联系人， **test-csunifiedcontactstore** cmdlet 将失败。 指定用户必须至少有一个联系人的**test-csunifiedcontactstore** cmdlet 才能成功完成。

</div>

<div>

## <a name="running-the-test"></a>运行测试

以下示例中所示的命令决定了用户 litwareinc\\kenmyer 的联系人是否可以在统一联系人存储库中找到。 若要执行此操作，示例中的第一个命令使用了**Get Credential** cmdlet 为用户 litwareinc\\kenmyer 创建 Windows PowerShell 命令行接口凭据对象。 请注意，您必须为此帐户提供密码才能创建有效的凭据对象并确保**test-csunifiedcontactstore** cmdlet 可以运行其检查。

该示例中的第二个命令使用提供的凭据对象（$x）和用户 litwareinc\\KENMYER 的 SIP 地址，以确定是否可以在统一联系人存储库中找到其联系人。

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果正确配置了对联系人存储的访问，您将收到与以下内容类似的输出，并将 Result 属性标记为 "**成功"：**

目标 Fqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00：00：14.9862716

错误消息：

诊断

如果未正确配置对联系人存储区的访问，则结果将显示为 "**失败**"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：

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

未能响应10.188.116.96：5061

内部异常：连接尝试失败，因为

连接方在一段时间后未正确响应

时间，或已建立的连接失败，因为连接的主机

未能响应10.188.116.96：5061

诊断

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

以下是**测试 test-csunifiedcontactstore**可能失败的一些常见原因：

  - 提供的参数值不正确。 如果使用，则必须正确配置可选参数或测试将失败。 重新运行不带可选参数的命令，并查看是否成功。

  - 连接到统一联系人存储失败，并且尝试检索用户的联系人失败。 可能存在网络连接问题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[新 CsUserServicesPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[CsUserServicesPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

