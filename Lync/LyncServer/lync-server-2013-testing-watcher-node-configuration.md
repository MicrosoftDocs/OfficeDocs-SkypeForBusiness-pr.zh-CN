---
title: Lync Server 2013：测试观察程序节点配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d5b73b0c56aa2f1ce4a0db2925354dd658ec2f0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中测试观察程序节点配置

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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行<strong>new-cswatchernodeconfiguration</strong> cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

如果使用 Microsoft System Center Operations Manager 监视 Lync Server 2013，则可以选择设置 "观察程序节点"：定期和自动运行综合事务以验证 Lync Server 是否正常工作的计算机需. 观察程序节点分配给池，并通过使用**new-cswatchernodeconfiguration** cmdlet 进行管理。 请注意，如果正在使用 System Center Operations Manager，那么无需安装观察程序节点。 您仍可以在不使用观察程序节点的情况下监视系统。 唯一的区别在于，要运行的任何合成事务都必须手动调用，而不是由 Operations Manager 自动调用。

**New-cswatchernodeconfiguration** cmdlet 使您能够验证是否已正确配置观察程序节点，并将其分配给有效的 Lync Server 2013 池。 请注意，必须在观察程序节点本身上运行**new-cswatchernodeconfiguration** cmdlet。 无法对远程计算机运行 cmdlet。

</div>

<div>

## <a name="running-the-test"></a>运行测试

以下命令验证组织中使用的每个观察程序节点的配置设置。

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

以下成功的示例输出显示了具有四台边缘服务器的系统。

对照拓扑验证目标池 atl-cs-001.litwareinc.com。

成功：拓扑中存在目标池 atl-cs-001.litwareinc.com。

成功：目标池 atl-cs-001.litwareinc.com 已安装注册器角色。

成功：目标池 atl-cs-001.litwareinc.com 是受支持的版本。

成功：5061目标池 atl-cs-001.litwareinc.com 的端口号正确。

已启动在观察程序节点配置中检查缺少的池。 如果检测到任何错误，则会将其打印出来。

在观察程序节点配置中检查缺少的池已完成。

已启动对观察程序节点安装创建的观察程序节点注册表项的检查。 如果检测到任何错误，则会将其打印出来。

检查由观察程序节点安装创建的观察程序节点注册表项是否已完成。 检测到的身份验证类型为 "协商"。

已成功验证测试用户的凭据 sip 是否存在： user1@ atl-cs-001.litwareinc.com in credential management store。

已成功验证测试用户的凭据 sip 是否存在： user2@ atl-cs-001.litwareinc.com in credential management store。

已启动在观察程序节点配置中检查缺少的池。 如果检测到任何错误，则会将其打印出来。

警告：池 atl-cs-001.litwareinc.com 具有注册器

已安装角色，但没有为其配置的测试用户。

在观察程序节点配置中检查缺少的池已完成。

检查由观察程序节点安装所创建的观察程序节点注册表项是

启动. 如果检测到任何错误，则会将其打印出来。

New-cswatchernodeconfiguration：在中找不到运行状况注册表项

Microsoft\\\\实时通信的软件。 请确保观察程序节点 .msi 是

正确安装。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

以下是**测试 new-cswatchernodeconfiguration**可能失败的一些常见原因：

  - 未正确安装观察程序节点。

  - 未配置任何测试用户。

</div>

<div>

## <a name="see-also"></a>另请参阅


[New-cswatchernodeconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[新 New-cswatchernodeconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[New-cswatchernodeconfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[New-cswatchernodeconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

