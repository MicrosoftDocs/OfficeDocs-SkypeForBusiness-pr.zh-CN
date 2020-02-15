---
title: Lync Server 2013：测试管理员权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0acb60648333e228b3a48df379c794b6f2b43fce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-permissions-in-lync-server-2013"></a>在 Lync Server 2013 中测试管理员权限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-08-18_


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
<p>使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 CsOUPermission cmdlet 的权限的 RBAC 角色。 若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>说明

当您安装 Lync Server 2013 1 时，安装程序执行的任务将为 RTCUniversalUserAdmins 组提供管理用户、计算机、联系人、应用程序联系人和 InetOrg 人员所需的 Active Directory 权限。 如果您已在 Active Directory 安装程序中禁用权限继承，则无法分配这些权限。 因此，RTCUniversalUserAdmins 组的成员将无法管理 Lync Server 实体。 这些管理权限将仅适用于域管理员。

CsOUPermission cmdlet 验证在 Active Directory 容器上是否设置了管理用户、计算机和其他对象所需的权限。 如果未设置这些权限，则可以通过运行[CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) cmdlet 来解决此问题。

请注意，CsOUPermission 只能将权限分配给 RTCUniversalUserAdmins 组的成员。 不能使用此 cmdlet 向任意用户或组授予权限。 如果您希望不同的用户或组拥有用户管理权限，则应将该用户（或组）添加到 RTCUniversalUserAdmins 组。

有关 OU 权限的详细信息，请参阅文章[：在计算机、用户或 InetOrgPerson 容器上禁用了 Lync Server 2013 中的权限继承](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)。

</div>

<div>

## <a name="running-the-test"></a>运行测试

若要验证是否在容器上设置了管理权限，请运行 CsOUPermission cmdlet，然后运行容器的可分辨名称和要验证的权限类型。 例如，以下命令将检查是否在 OU ou = Redmond，dc = litwareinc，dc = com 上设置了用户权限：

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

若要使用单个命令验证多个权限，请将每个权限类型括在引号中，然后使用逗号分隔这些类型。 例如，下面的一个命令验证用户、计算机和联系人权限：

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

有关详细信息，请参阅[CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) cmdlet 的帮助主题。

</div>

<div>

## <a name="determining-success-or-failure"></a>确定成功或失败

如果已设置所需的权限，则 CsOUPermission 将返回一个单字响应：

True

如果没有设置所需的权限，则 CsOUPermission 将返回值 False。 您可能需要搜索一段时间才能找到此值。 它通常嵌入到多个伴随的警告中。 例如：

警告：访问控制项（ACE） atl-cs-001\\RTCUniversalUserReadOnlyGroup;允许ReadPropertyContainerInherit;其子bf967aba-0de6-11d0-00aa003049e2;d819615a-3b9b-4738-b47e-f1bd8ee3aea4

警告：对象 "OU = 北美，DC = atl-cs-001\\DC = LITWAREINC，dc = com" 的访问控制项（ace）未准备就绪。

False

警告： "Test-CsOUPermission" 处理已完成，但出现警告。 在此运行过程中记录了 "2" 警告。

警告：可以在 "\\C： Users\\Admin\\AppData\\Local\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de" 处找到详细结果。

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>测试可能失败的原因

如果 CsOUPermission 失败，则通常意味着指定的权限尚未分配给 RTCUniversalUserAdmins 组。 您可以使用 CsOUPermission cmdlet 来解决此问题，并分配所需的权限。 例如，以下命令将用户、联系人和 inetOrgPersons 的 OU 权限提供给 RTCUniversalUserAdmins 组：

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

有关详细信息，请参阅 CsOUPermission cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

