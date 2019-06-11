---
title: 测试分配给网站的 Kerberos 帐户的配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e12a780c4c900423b23eff6cdaae15ba15786b6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a>在 Lync Server 2013 中测试分配给网站的 Kerberos 帐户的配置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-06-05_


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
<p>使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsKerberosAccountAssignment cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsKerberosAccountAssignment cmdlet 使你能够验证 Kerberos 帐户是否与给定的网站相关联、此帐户是否已正确配置以及帐户是否按预期工作。 Kerberos 帐户是计算机帐户, 可用作运行 Internet 信息服务器 (IIS) 的网站中的所有计算机的身份验证主体。 由于这些帐户使用 Kerberos 身份验证协议, 因此帐户称为 Kerberos 帐户, 新的身份验证过程称为 Kerberos web 身份验证。 这使你可以使用单个帐户管理所有 IIS 服务器。

有关详细信息, 请参阅[CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) Cmdlet 的帮助文档。

</div>

<div>

## <a name="running-the-test"></a>运行测试

默认情况下, 测试 CsKerberosAccountAssignment 在屏幕上显示非常少的输出。 而是将 cmdlet 返回的信息写入 HTML 文件。 因此, 我们建议你在运行 Test CsKerberosAccountAssignment 时随时包括 Verbose 参数和 Report 参数。 在运行 cmdlet 时, Verbose 参数将在屏幕上提供稍有更详细的输出。 Report 参数允许你为由 Test CsKerberosAccountAssignment 生成的 HTML 文件指定文件路径和文件名。 如果不包含报表参数, 则 HTML 文件将自动保存到 "用户" 文件夹, 并获得类似于以下内容的名称: ce84964a-c4da-4622-ad34-c54ff3ed361f。

在运行 Test CsKerberosAccountAssignment 时, 还必须指定网站标识。 在网站范围内分配 Kerberos 帐户。

以下命令运行 Test-CsKerberosAccountAssignment 并将输出保存到名为 C:\\Logs\\KerberosTest 的文件中:

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

有关详细信息, 请参阅[CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

CsKerberosAccountAssignment cmdlet 不会返回简单的成功或失败指示。 而是必须使用 Internet Explorer 查看生成的 HTML 文件。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是测试 CsKerberosAccountAssignment 可能失败的一些常见原因:

  - 您可能指定了一个不正确的站点标识。 若要返回有效网站标识的列表, 请使用以下命令:
    
        Get-CsSite | Select-Identity Identity
    
    网站标识通常如下所示:
    
    网站: 雷德蒙

  - 指定网站可能未分配 Kerberos 帐户。 你可以通过运行如下命令确定是否将 Kerberos 帐户分配给网站:
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - 您的 Kerberos 帐户可能有一个无效密码。 如果在报告中收到以下错误消息, 您可能需要重置 Kerberos 帐户密码:
    
    InvalidKerberosConfiguration: Kerberos 配置无效。
    
    InvalidKerberosConfiguration: atl-cs001.litwareinc.com 上的 Kerberos 配置无效。 所需的指定帐户为\\litwareinc kerberostest。 确保帐户未过期, 并且计算机上配置的密码与帐户的 Active Directory 密码相匹配。
    
    你可以使用[CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15)) cmdlet 设置密码。

</div>

</div>

<span> </span>

</div>

</div>

</div>

