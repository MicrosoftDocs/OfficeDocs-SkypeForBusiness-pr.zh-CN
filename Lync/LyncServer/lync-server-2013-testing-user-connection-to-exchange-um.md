---
title: Lync Server 2013：测试用户与 Exchange UM 的连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b72552f56041103e381291bf13ab13283a3c47ee
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a>在 Lync Server 2013 中测试用户与 Exchange UM 的连接

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行<strong>test-csexumconnectivity</strong> cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

**Test-csexumconnectivity** cmdlet 验证指定的用户是否可以连接到 Microsoft Exchange Server 2013 统一消息服务。 请注意，此 cmdlet 仅验证是否可以与服务建立连接。 它不测试服务本身。 若要测试统一消息服务（通过运行实际在用户的邮箱中留下语音邮件的综合事务 cmdlet），请使用 Test-CsExUMVoiceMail cmdlet。

</div>

<div>

## <a name="running-the-test"></a>运行测试

下面的示例测试 pool atl-cs-001.litwareinc.com 的 Exchange 统一消息连接。 仅当为池 atl-cs-001.litwareinc.com 定义了测试用户时，才能使用此命令。 如果有，则该命令将确定第一个测试用户是否可以连接到统一消息。 如果没有为池配置测试用户，则该命令将失败。

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

以下示例中所示的命令测试用户 litwareinc\\Kenmyer 的 Exchange 统一消息连接。 若要执行此操作，示例中的第一个命令使用了**Get Credential** cmdlet 为用户 litwareinc\\kenmyer 创建 Windows PowerShell 命令行接口凭据对象。 请注意，您必须为此帐户提供密码才能创建有效的凭据对象，并确保**test-csexumconnectivity** cmdlet 可以运行其检查。

该示例中的第二个命令使用提供的凭据对象（$x）和用户 litwareinc\\KENMYER 的 SIP 地址，以确定此用户是否可以连接到 Exchange 统一消息。

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

下一个示例中所示的命令是刚刚显示的命令的变体。 在这种情况下，将包含 OutLoggerVariable 参数，以生成由**测试 test-csexumconnectivity**执行的每个步骤的详细日志，cmdletand 每个步骤的成功或失败。 若要执行此操作，请将 OutLoggerVariable 参数添加到参数值 ExumText 中。这会导致详细的日志记录信息存储在名为 $ExumTest 的变量中。 在示例的最后一个命令中，ToXML() 方法用于将日志信息转换为 XML 格式。 然后，将 XML 数据写入到一个名为 C：\\的文件中\\，并使用 Out file cmdlet 来记录 ExumTest。

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果已正确配置 Exchange 集成，则会收到类似于以下内容的输出，并将 Result 属性标记为**成功**：

目标 Fqdn： atl-cs-001.litwareinc.com

结果：成功

延迟：00:00:00

错误消息：

诊断

如果指定的用户无法接收通知，则结果将显示为 "**失败**"，并且将在 "错误" 和 "诊断" 属性中记录其他信息：

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

以下是**测试 test-csexumconnectivity**可能失败的一些常见原因：

  - 提供的参数值不正确。 如果使用，则必须正确配置可选参数或测试将失败。 重新运行不带可选参数的命令，并查看是否成功。

  - 如果 Exchange 服务器配置错误或尚未部署，则此命令将失败。

  - 如果无法通过网络访问 Exchange 服务器，则此命令将失败。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

