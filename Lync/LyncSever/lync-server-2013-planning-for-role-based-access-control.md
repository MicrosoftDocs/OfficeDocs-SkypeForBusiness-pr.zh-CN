---
title: Lync Server 2013：规划基于角色的访问控制
TOCTitle: 规划基于角色的访问控制 (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425917(v=OCS.15)
ms:contentKeyID: 49312650
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中规划基于角色的访问控制

 

_**上一次修改主题：** 2015-03-09_

为使您能够在保持高标准安全性的同时委派管理任务， Lync Server 2013 引入了基于角色的访问控制 (RBAC)。使用 RBAC，可通过将用户分配给管理角色来授予管理权限。 Lync Server 2013 包含一组丰富的内置管理角色，另外还允许您创建新角色并为每个新角色指定自定义 cmdlet 列表。您还可以将 cmdlet 的脚本添加到所允许的预定义和自定义 RBAC 角色任务中。

## 更高的服务器安全性和集中化

使用 RBAC，可根据用户的 Lync Server 角色实现精确访问和授权。这样就可以利用“最小特权”安全做法，以便仅向管理员和用户授予其工作所需的权限。

> [!IMPORTANT]
> RBAC 限制仅适用于使用 Lync Server 控制面板或 Lync Server 命令行管理程序进行远程工作的管理员。位于运行 Lync Server 的服务器上的用户不受 RBAC 限制。因此， Lync Server 的物理安全性对维护 RBAC 限制十分重要。


## 角色和作用域

在 RBAC 中，启用 *角色* 是为了使用旨在帮助特定类型的管理员或技术人员的 cmdlet 的列表。 *作用域* 是一组角色中定义的 cmdlet 可以对其执行操作的对象。受作用域影响的对象可以是用户帐户（按组织单位分组）或服务器（按站点分组）。

下表列出了 Lync Server 中的预定义角色，并概述了每个角色可以执行的任务类型。第四列显示了每个 Lync Server 角色的类似 Microsoft Exchange Server 角色（如果有）。

### 预定义的管理角色

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>角色</th>
<th>允许的任务</th>
<th>基础 Active Directory 组</th>
<th>Exchange 等效项</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CsAdministrator</p></td>
<td><p>可以执行所有管理任务和修改所有设置，包括创建角色和将用户分配给角色。可以通过添加新的站点、池和服务来扩展部署。</p></td>
<td><p>CSAdministrator</p></td>
<td><p>组织管理</p></td>
</tr>
<tr class="even">
<td><p>CsUserAdministrator</p></td>
<td><p>可以为用户启用和禁用 Lync Server、移动用户和将现有策略分配给用户。不能修改策略。</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>邮件收件人</p></td>
</tr>
<tr class="odd">
<td><p>CsVoiceAdministrator</p></td>
<td><p>可以创建、配置和管理与语音相关的设置和策略。</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="even">
<td><p>CsServerAdministrator</p></td>
<td><p>可以管理、监控服务器和服务，以及排除服务器和服务的故障。可以阻止与服务器建立新连接、停止和启动服务以及应用软件更新。不能做出影响全局配置的更改。</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>服务器管理</p></td>
</tr>
<tr class="odd">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>可以查看部署（包括用户和服务器信息），以便监控部署的运行状况。</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>仅查看组织管理</p></td>
</tr>
<tr class="even">
<td><p>CsHelpDesk</p></td>
<td><p>可以查看部署，包括用户的属性和策略。可以运行特定的故障排除任务。不能更改用户属性或策略、服务器配置或服务。</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>技术支持人员</p></td>
</tr>
<tr class="odd">
<td><p>CsArchivingAdministrator</p></td>
<td><p>可以修改存档配置和策略。</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>Retention Management、Legal Hold</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>可以在站点内管理响应组应用程序的配置。</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>CsLocationAdministrator</p></td>
<td><p>增强型 9-1-1 (E9-1-1) 的最低级别权限管理，包括创建 E9-1-1 位置和网络标识符，以及将这二者相互关联。此角色始终分配有全局作用域。</p></td>
<td><p>CSLocationAdministrator</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupManager</p></td>
<td><p>可以管理特定的响应组。</p></td>
<td><p>CSResponseGroupManager</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>CsPersistentChatAdministrator</p></td>
<td><p>可以管理持久聊天功能和特定的持久聊天聊天室。</p></td>
<td><p>CSPersistentChatAdministrator</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="even">
<td><p>CsAdministrator</p></td>
<td><p>可以执行所有管理任务和修改所有设置，包括创建角色和将用户分配给角色。可以通过添加新的站点、池和服务来扩展部署。</p></td>
<td><p>CSAdministrator</p></td>
<td><p>组织管理</p></td>
</tr>
<tr class="odd">
<td><p>CsUserAdministrator</p></td>
<td><p>可以为用户启用和禁用 Lync Server、移动用户和将现有策略分配给用户。不能修改策略。</p></td>
<td><p>CSUserAdministrator</p></td>
<td><p>邮件收件人</p></td>
</tr>
<tr class="even">
<td><p>CsVoiceAdministrator</p></td>
<td><p>可以创建、配置和管理与语音相关的设置和策略。</p></td>
<td><p>CSVoiceAdministrator</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>CsServerAdministrator</p></td>
<td><p>可以管理、监控服务器和服务，以及排除服务器和服务的故障。可以阻止与服务器建立新连接、停止和启动服务以及应用软件更新。不能做出影响全局配置的更改。</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>服务器管理</p></td>
</tr>
<tr class="even">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>可以查看部署（包括用户和服务器信息），以便监控部署的运行状况。</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>仅查看组织管理</p></td>
</tr>
<tr class="odd">
<td><p>CsHelpDesk</p></td>
<td><p>可以查看部署，包括用户的属性和策略。可以运行特定的故障排除任务。不能更改用户属性或策略、服务器配置或服务。</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>技术支持人员</p></td>
</tr>
<tr class="even">
<td><p>CsArchivingAdministrator</p></td>
<td><p>可以修改存档配置和策略。</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>Retention Management、Legal Hold</p></td>
</tr>
<tr class="odd">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>可以在站点内管理响应组应用程序的配置。</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="even">
<td><p>CsLocationAdministrator</p></td>
<td><p>增强型 9-1-1 (E9-1-1) 的最低级别权限管理，包括创建 E9-1-1 位置和网络标识符，以及将这二者相互关联。此角色始终分配有全局作用域。</p></td>
<td><p>CSLocationAdministrator</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>CsResponseGroupManager</p></td>
<td><p>可以管理特定的响应组。</p></td>
<td><p>CSResponseGroupManager</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="even">
<td><p>CsPersistentChatAdministrator</p></td>
<td><p>可以管理持久聊天功能和特定的持久聊天聊天室。</p></td>
<td><p>CSPersistentChatAdministrator</p></td>
<td><p>不适用</p></td>
</tr>
</tbody>
</table>


Lync Server 中附带的所有预定义角色都具有全局作用域。为符合“最小特权”做法，如果用户仅管理有限的一组服务器或用户，则不应将他们分配给具有全局作用域的角色。为此，可以创建基于现有角色但作用域更加有限的角色。

## 创建作用域角色

创建作用域有限的角色（作用域角色）时，需指定作用域、该角色所基于的现有角色以及要将该角色分配到的 Active Directory 组。指定的 Active Directory 组必须是已创建的组。以下 cmdlet 示例创建的角色具有其中一种预定义管理角色的权限，但具有有限作用域。它创建名为 `Site01 Server Administrators` 的新角色。该角色具有预定义的 CsServerAdministrator 角色的功能，但仅适用于位于 Site01 站点上的服务器。要运行此 cmdlet，必须已定义 Site01 站点并且名为 `Site01 Server Administrators` 的统一安全组必须已存在。

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

运行此 cmdlet 后， `Site01 Server Administrators` 组的所有成员用户都将具有对 Site01 中服务器的服务器管理员权限。此外，以后添加到此统一安全组的所有用户也可以获得此角色的权限。请注意，角色本身及其分配到的统一安全组都称为 `Site01 Server Administrators`。

以下示例限定用户作用域，而不是服务器作用域。它创建 `Sales Users Administrator` 角色来管理 Sales 组织单位中的用户帐户。为使此 cmdlet 正常工作，必须已创建 SalesUsersAdministrator 统一安全组。

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

## 新建角色

要创建的角色必须能够访问 cmdlet 组而不是其中一个预定义角色，或者必须能够访问一组脚本或模块，您再次需要从使用其中一个预定义角色作为模板开始。请注意，角色能够运行的脚本和模块必须存储在以下位置：

  - Lync 模块路径，默认情况下为 C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\Lync

  - 用户脚本路径，默认情况下为 C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\AdminScripts

要创建新角色，请使用 **New-CsAdminRole** cmdlet。在运行 **New-CsAdminRole** 之前，您必须首先创建将与该角色关联的基础统一安全组。

以下 cmdlet 为创建新角色的示例。它们创建一个名为 `MyHelpDeskScriptRole` 的新角色。该新角色具有预定义 CsHelpDesk 角色的功能，另外还可以运行名为“testscript”的脚本中的函数。

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

要运行此 cmdlet，您必须首先创建统一安全组 MyHelpDeskScriptRole。

运行此 cmdlet 后，您可以直接将用户分配给此角色（这种情况下，这些用户具有全局作用域），或者基于此角色创建作用域角色，如本文前面“创建作用域角色”所述。

## 将角色分配给用户

每个 Lync Server 角色都与一个基本 Active Directory 统一安全组关联。添加到基础组的任何用户都能获得该角色的功能。

上节中的示例创建了一个新角色，并向其分配了现有统一安全组。要将现有角色分配给一个或多个用户，请将这些用户添加到与该角色关联的组中。您可以向这些组中添加单个用户，也可以添加统一安全组。

例如，会自动为 Active Directory 中的 **CS Administrators** 统一安全组授予 **CsAdministrator** 角色。此统一安全组是部署 Lync Server 时在 Active Directory 中创建的。要向用户或组授予此权限，只需将其添加到 **CS Administrators** 组中。

可向用户分配多个 RBAC 角色，方法是将该用户添加到与每个角色相对应的基础 Active Directory 组中。

请注意，如果创建了角色，以后添加到基础 Active Directory 组的用户也可获得该角色的功能。

## 修改角色的功能

您可以修改角色能够运行的 cmdlet 和脚本的列表。您可以同时修改自定义角色能够运行的 cmdlet 和脚本，但是您只能修改预定义角色的脚本。您键入的每个 cmdlet 均可添加、删除或替换 cmdlet 或脚本。

若要修改角色，请使用 **Set-CsAdminRole** cmdlet。以下 cmdlet 可从角色中删除一个脚本。

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

## 规划 RBAC

对于为其赋予了对 Lync Server 部署的任何类型管理权限的每位用户，请考虑他们具体需要执行哪些任务，然后将他们分配给具有他们工作所需的最小特权和作用域的角色。如果需要，您可以使用 **Set-CsAdminRole** cmdlet 创建一个仅使用该用户完成任务所需 cmdlet 的新角色。

具有 CsAdministrator 角色的用户可以创建所有类型的角色（包括基于 CsAdministrator 的角色）并向其分配用户。最佳实践是将 CsAdministrator 角色分配给少数受信任的用户。

