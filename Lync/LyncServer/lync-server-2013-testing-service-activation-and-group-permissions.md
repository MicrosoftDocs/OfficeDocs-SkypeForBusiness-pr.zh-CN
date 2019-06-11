---
title: 'Lync Server 2013: 测试服务激活和组权限'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6616e1f2835ab55f9e3e8f98e5a8693ef3d2fb4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a>在 Lync Server 2013 中测试服务激活和组权限

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
<p>使用 Windows PowerShell 的远程实例运行时, 必须向用户分配具有运行 CsTopology cmdlet 权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表, 请从 Windows PowerShell 提示符处运行以下命令:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

CsTopology cmdlet 使你能够验证 Lync Server 2013 在全局范围内是否正常工作。 默认情况下, 该 cmdlet 检查整个 Lync 服务器基础结构, 验证所需服务是否正在运行以及是否为这些服务以及在安装 Lync Server 时创建的通用安全组设置了相应权限.

除了验证 Lync Server 安装的有效性, CsTopology 还允许你检查特定服务的有效性。 例如, 此命令将检查 pool atl-cs-001.litwareinc.com 上的 A/V 会议服务器的状态:

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a>运行测试

默认情况下, 测试 CsTopology 在屏幕上显示非常少的输出。 而是将 cmdlet 返回的信息写入 HTML 文件。 Report 参数允许你为由 Test CsTopology 生成的 HTML 文件指定文件路径和文件名。 如果不包含报表参数, 则 HTML 文件将自动保存到 "用户" 文件夹, 并获得类似于以下内容的名称: ce84964a-c4da-4622-ad34-c54ff3ed361f。

以下示例命令运行 Test-CsTopology 并将输出保存到名为 C:\\Logs\\ComputerTest 的文件中:

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

有关详细信息, 请参阅[CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) Cmdlet 的帮助文档。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功还是失败

与大多数测试 cmdlet 不同, CsTopology 的测试会报告恢复成功或失败。 部分中, 这是因为每次运行 cmdlet 时都必须执行大量的验证检查。 而是将数据保存到 HTML 报表, 然后可使用 Internet Explorer 查看。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

下面是测试 CsTopology 可能失败的一些常见原因:

  - 测试计算机上的复制可能不是最新的。 你可以通过运行 CsManagementStoreReplicationStatus cmdlet 检查计算机的当前复制状态:
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    如果复制状态不是最新的, 则可以通过使用类似下面的命令手动强制执行复制:
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - 可能必须启用拓扑。 如果更改 Lync Server 拓扑 (可能会影响本地计算机的更改), 则必须启用新拓扑。 可以通过运行以下命令随时启用拓扑:
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

