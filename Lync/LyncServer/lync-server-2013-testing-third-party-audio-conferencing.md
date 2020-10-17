---
title: Lync Server 2013：测试第三方音频会议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51f728bfb5617185bdd9a1ef3b5f21b3e12ca61f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503929"
---
# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中测试第三方音频会议

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 Test-CsAudioConferencingProvider cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

音频会议提供商是为组织提供会议服务的第三方公司。此外，音频会议提供商使外出且未连接到企业网络或 Internet 的用户可以通过音频参加会议。音频会议提供商通常会提供一些高端服务，例如实时翻译、转录和每个会议的实时接线员协助。

**CsAudioConferencingProvider** cmdlet 用于验证用户是否能够建立与他/她的音频会议提供商的连接。 请注意，此 cmdlet 可以采用两种方式之一运行。 许多管理员会使用 CsHealthMonitoringConfiguration cmdlet 为其每个注册器池设置测试用户。 这些测试用户表示预先配置的与综合事务配合使用的一对用户帐户。  (通常是测试帐户，而不是属于实际用户的帐户。 ) 如果为池配置了测试用户，则管理员可以对该池运行 **CsAudioConferencingProvider** cmdlet，而无需指定 (的标识，并提供用于) 测试中所涉及的用户帐户的凭据。

此外，管理员还可以使用实际用户帐户运行 **CsAudioConferencingProvider** cmdlet。 如果您决定使用实际用户帐户进行测试，则需要提供该帐户的登录名和密码。

</div>

<div>

## <a name="running-the-test"></a>运行测试

示例 1 检查为池 atl-cs-001.litwareinc.com 定义的测试用户能否连接到其音频会议提供商。 该命令要求为池定义了至少一个测试用户。 如果没有为 atl-cs-001.litwareinc.com 定义测试用户，则该命令将失败;这是因为 **CsAudioConferencingProvider** cmdlet 将不知道在测试中使用哪个用户。 如果没有为池定义测试用户，则必须包括 UserSipAddress 参数以及该命令在验证与音频会议提供商的连接时应使用的用户帐户凭据。

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

示例2中显示的命令测试特定用户 (litwareinc kenmyer) 的功能 \\ ，以连接到其音频会议提供商。 若要执行此操作，示例中的第一个命令使用 Get-Credential cmdlet 来创建 Windows PowerShell 命令行接口凭据对象，其中包含用户 Ken Myer 的名称和密码。  (因为登录名 litwareinc \\ kenmyer 已作为参数包括在内，所以 "Windows PowerShell 凭据请求" 对话框仅要求管理员输入 Ken Myer 帐户的密码。 ) 生成的凭据对象存储在名为 $credential 的变量中。

然后第二个命令检查此用户能否连接到其音频会议提供商。 若要执行此任务，请调用 Test-CsAudioConferencingProvider cmdlet 以及以下三个参数： TargetFqdn (注册器池的 FQDN) ;UserCredential (包含 Ken Myer 的用户凭据的 Windows PowerShell 对象) ;和 UserSipAddress (与提供的用户凭据) 对应的 SIP 地址。

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果正确配置了音频会议提供商，则会收到与以下内容类似的输出，并将 Result 属性标记为 **成功：**

目标 Fqdn： atl-sql-001.litwareinc.com

结果：成功

延迟：00:00:00

错误消息：

诊断

如果指定的用户无法登录或注销，则结果将显示为 " **失败**"，并且会在 "错误" 和 "诊断" 属性中记录其他信息：

目标 Fqdn： atl-sql-001.litwareinc.com

结果：失败

延迟：00:00:00

错误消息：10060，连接尝试失败，因为连接方

在一段时间后未正确响应，或者

已建立连接失败，因为连接的主机具有

无法响应 \[ 2001：4898： e8： f39e：5c9a： ad83：81b3： 9944 \] ：5061

内部异常：连接尝试失败，因为

连接方在一段时间后未正确响应

时间，或已建立的连接失败，因为连接的主机

未能响应

\[2001：4898： e8： f39e：5c9a： ad83：81b3： 9944 \] ：5061

诊断

例如，以前的输出包括 "连接方未正确响应" 这一说明，这通常表示边缘服务器存在问题。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

以下是 **测试 CsAudioConferencingProvider** 可能失败的一些常见原因：

  - 提供的参数值不正确。 如前面的示例中所示，必须正确配置可选参数或测试将失败。 重新运行不带可选参数的命令，并查看是否成功。

  - 请注意，如果尚未为 **CsAudioConferencingProvider** cmdlet 所采用的用户分配音频会议提供商，则测试将失败。

  - 如果边缘服务器配置错误或尚未部署，则此命令将失败。

</div>

</div>

<span> </span>

</div>

</div>

</div>

