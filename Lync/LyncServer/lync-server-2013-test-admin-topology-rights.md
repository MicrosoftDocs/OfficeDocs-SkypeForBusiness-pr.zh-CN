---
title: Lync Server 2013：测试管理员拓扑权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 050ba83b4598fc5ed8ed3d40d0b1aa02ba9356b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-admin-topology-rights-in-lync-server-2013"></a>Lync Server 2013 中的测试管理员拓扑权限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-12-08_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>验证计划</p></td>
<td><p>初始 Lync Server 部署之后。 如果出现权限相关问题，则根据需要。</p></td>
</tr>
<tr class="even">
<td><p>测试工具</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>所需的权限</p></td>
<td><p>在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员。</p>
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsSetupPermission cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

默认情况下，只有域管理员才能启用 Lync Server 拓扑，并对 Lync Server 基础结构进行较大的更改。 只要您的域管理员和 Lync Server 管理员是同一个，这就不会出现问题。在许多组织中，Lync Server 管理员不拥有对整个域的管理权限。 默认情况下，这意味着这些管理员（定义为 RTCUniversalServerAdmins 组的成员）无法进行 Lync Server 拓扑更改。 若要向 RTCUniversalServerAdmins 组的成员授予对拓扑的更改权限，您必须使用[CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet 分配所需的 Active Directory 权限。

CsSetupPermission cmdlet 验证在指定的 Active Directory 容器上配置安装 Lync Server 或其某个组件所需的必需权限。 如果未分配权限，则可以运行 CsSetupPermission cmdlet，以向 RTCUniversalServerAdmins 组的成员授予安装和启用 Lync Server 的权限。

<div>


> [!NOTE]  
> 有关由 CsSetupPermission 分配的权限的详细列表，请参阅博客文章<A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">grant-CsSetupPermission And grant-CsOUPermission</A>。



</div>

</div>

<div>

## <a name="running-the-test"></a>运行测试

若要确定是否为 Active Directory 容器分配了安装程序权限，请调用 CsSetupPermission cmdlet。 指定要检查的容器的可分辨名称。 例如，以下命令验证容器 ou = CsServers，dc = litwareinc，dc = com 上的安装程序权限：

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

有关详细信息，请参阅[CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet 的帮助主题。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果 CsSetupPermission 确定已在 Active Directory 容器上设置所需的权限，则 cmdlet 将返回值 True：

True

如果未设置权限，则 CsSetupPermission 将返回值 False。 请注意，此值通常会包含在许多警告消息中。 例如：

警告：访问控制项（ACE） atl-cs-001\\RTCUniversalServerAdmins;允许ExtendedRight;全都全都1131f6aa-9c07-11d1-f79f-00c04fc2dcd2

警告：对象 "CN = 计算机，DC = litwareinc，DC = com" 上的访问控制项（Ace）未准备就绪。

False

警告： "Test-CsSetupPermission" 处理已完成，但出现警告。 在此运行过程中记录了 "2" 警告。

警告：可以在 "\\C： Users\\Admin\\AppData\\Local\\Temp\\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118" 中找到详细结果。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

尽管 CsSetupPermission 的测试失败通常意味着不会为指定的 Active Directory 容器分配安装权限，但有一些罕见的例外情况。 可以使用 CsSetupPermission cmdlet 分配这些权限。 例如，此命令向域 litwareinc.com 中的计算机容器授予安装程序权限：

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

有关详细信息，请参阅[CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

