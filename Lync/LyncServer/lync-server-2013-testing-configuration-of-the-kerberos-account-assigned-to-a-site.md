---
title: 测试分配给站点的 Kerberos 帐户的配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a608f84c3c302c503450bfe1c763aebacc269e96
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a>在 Lync Server 2013 中测试分配给某个站点的 Kerberos 帐户的配置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-06-05_


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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsKerberosAccountAssignment cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

CsKerberosAccountAssignment cmdlet 使您能够验证 Kerberos 帐户是否与给定网站相关联，该帐户是否已正确配置，以及该帐户是否按预期正常运行。 Kerberos 帐户是计算机帐户，可充当运行 Internet 信息服务器（IIS）的站点中的所有计算机的身份验证主体。 由于这些帐户使用 Kerberos 身份验证协议，因此这些帐户称为 Kerberos 帐户，而新的身份验证过程称为 Kerberos web 身份验证。 这使您可以使用单个帐户管理所有 IIS 服务器。

有关详细信息，请参阅[CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) Cmdlet 的帮助文档。

</div>

<div>

## <a name="running-the-test"></a>运行测试

默认情况下，CsKerberosAccountAssignment 在屏幕上显示非常少的输出。 相反，cmdlet 返回的信息将写入到 HTML 文件中。 因此，我们建议您在每次运行 CsKerberosAccountAssignment 时都包含 Verbose 参数和 Report 参数。 在 cmdlet 运行时，Verbose 参数将在屏幕上提供略微更详细的输出。 Report 参数允许您为由 CsKerberosAccountAssignment 生成的 HTML 文件指定文件路径和文件名。 如果不包含 Report 参数，则 HTML 文件将自动保存到用户文件夹中，并提供如下所示的名称： ce84964a-c4da-c4da-4622-ad34-c54ff3ed361f。

在运行 CsKerberosAccountAssignment 时，还必须指定一个网站标识。 在站点范围内分配 Kerberos 帐户。

下面的命令运行 CsKerberosAccountAssignment，并将输出保存到名为 C：\\Logs\\KerberosTest 的文件中：

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

有关详细信息，请参阅[CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

CsKerberosAccountAssignment cmdlet 不会返回成功或失败的简单指示。 相反，您必须使用 Internet Explorer 查看生成的 HTML 文件。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

以下是测试 CsKerberosAccountAssignment 可能失败的一些常见原因：

  - 您可能指定了错误的站点标识。 若要返回有效网站标识的列表，请使用以下命令：
    
        Get-CsSite | Select-Identity Identity
    
    网站标识通常如下所示：
    
    网站： Redmond

  - 指定的网站可能没有分配给它的 Kerberos 帐户。 您可以通过运行与以下内容类似的命令来确定是否向某个网站分配了 Kerberos 帐户：
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - 您的 Kerberos 帐户的密码可能无效。 如果您在报告中收到以下错误消息，则您可能需要重置 Kerberos 帐户密码：
    
    InvalidKerberosConfiguration： Kerberos 配置无效。
    
    InvalidKerberosConfiguration： atl-cs001.litwareinc.com 上的 Kerberos 配置无效。 预期分配的帐户为 litwareinc\\kerberostest。 确保帐户未过期，并且计算机上配置的密码与帐户的 Active Directory 密码相匹配。
    
    您可以使用[CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) cmdlet 设置密码。

</div>

</div>

<span> </span>

</div>

</div>

</div>

