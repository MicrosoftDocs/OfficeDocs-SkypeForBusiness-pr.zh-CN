---
title: 'Lync Server 2013: 测试 Lync Server 服务'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b193473ad5941c647c572fae1b7cb5e7ece7f95d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845581"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a>在 Lync Server 2013 中测试 Lync Server 服务

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
<p>使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsComputer cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

测试 CsComputer 验证本地计算机上运行的所有 Lync Server 2013 服务的状态。 (测试 CsComputer 只能在本地运行, 不能从 Windows PowerShell 的远程实例运行。)该 cmdlet 还检查是否在计算机上打开相应的防火墙端口, 并确定安装 Lync Server 2013 时创建的 Active Directory 组是否已添加到相应的本地组。 例如, CsComputer 将验证 Active Directory 组 RTCUniversalUserAdmins 是否已添加到管理员组。

有关详细信息, 请参阅[CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) Cmdlet 的帮助文档。

</div>

<div>

## <a name="running-the-test"></a>运行测试

CsComputer cmdlet 只能在本地计算机上运行, 因此不能从 Windows PowerShell 的远程实例调用 Test CsComputer。 默认情况下, CsComputer 在屏幕上显示非常少的输出, 而由 cmdlet 返回的信息将写入 HTML 文件。 因此, 我们建议你在运行 Test CsComputer 时随时包括 Verbose 参数和 Report 参数。 在运行 cmdlet 时, Verbose 参数将在屏幕上提供稍有更详细的输出。 Report 参数允许你为由 Test CsComputer 生成的 HTML 文件指定文件路径和文件名。 如果不包含报表参数, 则 HTML 文件将自动保存到 "用户" 文件夹, 并获得类似于以下内容的名称: ce84964a-c4da-4622-ad34-c54ff3ed361f。

以下示例命令运行 Test-CsComputer 并将输出保存到名为 C:\\Logs\\ComputerTest 的文件中:

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

有关详细信息, 请参阅[CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

由于执行的验证检查次数, CsComputer 不会报告简单的 **"是"、"测试成功**" 或 "**否", 测试失败**。 而是必须通过使用 Internet Explorer 确定每个测试的成功或失败来查看生成的 HTML 文件。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是测试 CsComputer 可能失败的一些常见原因:

  - 测试计算机可能未启用, 无法与 Lync Server 配合使用。 如果计算机上的 Lync Server 服务或服务器角色已更改且 CsComputer cmdlet 未运行, 则可能会发生这种情况。 若要解决此问题, 请运行以下命令:
    
        Enable-CsComputer

  - 测试计算机上的复制可能不是最新的。 你可以通过运行 CsManagementStoreReplicationStatus cmdlet 检查计算机的当前复制状态:
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    如果复制状态不是最新, 则可以通过使用类似下面的命令手动强制执行复制:
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - 可能必须启用拓扑。 如果更改 Lync Server 拓扑 (可能会影响本地计算机的更改), 则必须启用新拓扑。 可以通过运行以下命令随时启用拓扑:
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

