---
title: Lync Server 2013：测试 Lync Server 服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98c5f39a636eb300f19cd42131fc42d2480bbf14
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a>在 Lync Server 2013 中测试 Lync Server 服务

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsComputer cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsComputer 验证在本地计算机上运行的所有 Lync Server 2013 服务的状态。 （CsComputer 只能在本地运行，它不能从 Windows PowerShell 的远程实例运行。）此 cmdlet 还检查是否在计算机上打开相应的防火墙端口，并确定在安装 Lync Server 2013 时创建的 Active Directory 组是否已添加到相应的本地组。 例如，CsComputer 将验证是否已将 Active Directory 组 RTCUniversalUserAdmins 添加到 Administrators 组。

有关详细信息，请参阅[CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) Cmdlet 的帮助文档。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsComputer cmdlet 只能在本地计算机上运行，不能从 Windows PowerShell 的远程实例中调用 CsComputer 的测试。 默认情况下，CsComputer 在屏幕上显示非常少的输出，而由 cmdlet 返回的信息将写入 HTML 文件。 因此，我们建议您在每次运行 CsComputer 时都包含 Verbose 参数和 Report 参数。 在 cmdlet 运行时，Verbose 参数将在屏幕上提供略微更详细的输出。 Report 参数允许您为由 CsComputer 生成的 HTML 文件指定文件路径和文件名。 如果不包含 Report 参数，则 HTML 文件将自动保存到用户文件夹中，并提供如下所示的名称： ce84964a-c4da-c4da-4622-ad34-c54ff3ed361f。

下面的示例命令运行 CsComputer，并将输出保存到名为 C：\\Logs\\ComputerTest 的文件中：

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

有关详细信息，请参阅[CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

由于它执行的验证检查的数量很多，因此 CsComputer 不会报告为 **"是"、"测试成功**" 或 "否"，**测试失败**。 相反，您必须使用 Internet Explorer 来确定每个测试的成功或失败情况，才能查看生成的 HTML 文件。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

以下是测试 CsComputer 可能失败的一些常见原因：

  - 测试计算机可能未启用，无法与 Lync Server 一起使用。 如果计算机上的 Lync Server 服务或服务器角色已更改，并且未运行 CsComputer cmdlet，则会发生这种情况。 若要解决此问题，请运行以下命令：
    
        Enable-CsComputer

  - 测试计算机上的复制可能不是最新的。 您可以通过运行 Get-csmanagementstorereplicationstatus cmdlet 来检查计算机的当前复制状态：
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    如果复制状态不是最新的，则可以使用类似如下的命令手动强制执行复制：
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - 可能必须启用拓扑。 如果更改了 Lync Server 拓扑（可能影响本地计算机的更改），则必须启用新的拓扑。 可以通过运行以下命令随时启用拓扑：
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

