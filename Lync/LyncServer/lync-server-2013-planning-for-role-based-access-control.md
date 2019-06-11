---
title: Lync Server 2013：规划基于角色的访问控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1771eb906685294e588e0c67b1fa8fb1f67a8b6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a>在 Lync Server 2013 中规划基于角色的访问控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2015-01-27_

为了使你能够在保持高安全性标准的同时委派管理任务, Lync Server 2013 提供了基于角色的访问控制 (RBAC)。 通过 RBAC, 管理员权限可通过向管理角色分配用户来授予。 Lync Server 2013 包含一组丰富的内置管理角色, 还使你能够创建新角色并为每个新角色指定一个自定义 cmdlet 列表。 您还可以将 cmdlet 的脚本添加到所允许的预定义和自定义 RBAC 角色任务中。

<div>

## <a name="better-server-security-and-centralization"></a>更好的服务器安全和集中化

使用 RBAC、访问和授权完全基于用户的 Lync 服务器角色。 这允许使用 "最低权限" 安全做法, 仅授予管理员和用户其作业所需的权限。

<div>


> [!IMPORTANT]  
> 只有在远程工作的管理员使用 Lync Server 控制面板或 Lync Server 命令行管理程序时, RBAC 限制才有效。 用户坐在运行 Lync Server 的服务器上时, 该用户不受 RBAC 限制。 因此, 您的 Lync 服务器的物理安全对于保留 RBAC 限制非常重要。



</div>

</div>

<div>

## <a name="roles-and-scope"></a>角色和作用域

在 RBAC 中, 启用了*角色*以使用 cmdlet 的列表, 这些 cmdlet 适用于特定类型的管理员或技术人员。 *作用域*是指角色中定义的 cmdlet 可以操作的对象集。 作用域影响的对象可以是用户帐户 (按组织单位分组) 或服务器 (按网站分组)。

下表列出了 Lync Server 中的预定义角色, 并概括介绍了每个角色可以执行的任务类型。 第四列显示了每个 Lync 服务器角色的类似 Microsoft Exchange 服务器角色 (如果有)。

### <a name="predefined-administrative-roles"></a>预定义的管理角色

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
<th>等同于 Exchange</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CsAdministrator</p></td>
<td><p>可以执行所有管理任务和修改所有设置, 包括创建角色和向角色分配用户。 可以通过添加新的网站、池和服务来扩展部署。</p></td>
<td><p>CSAdministrator</p></td>
<td><p>组织管理</p></td>
</tr>
<tr class="even">
<td><p>CsUserAdministrator</p></td>
<td><p>可以为 Lync Server 启用和禁用用户、移动用户并向用户分配现有策略。 无法修改策略。</p></td>
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
<td><p>可以管理和监视服务器和服务并解决问题。 可以阻止与服务器的新连接、停止和启动服务以及应用软件更新。 全局配置影响无法进行更改。</p></td>
<td><p>CSServerAdministrator</p></td>
<td><p>服务器管理</p></td>
</tr>
<tr class="odd">
<td><p>CsViewOnlyAdministrator</p></td>
<td><p>可以查看部署, 包括用户和服务器信息, 以便监视部署运行状况。</p></td>
<td><p>CSViewOnlyAdministrator</p></td>
<td><p>仅查看组织管理</p></td>
</tr>
<tr class="even">
<td><p>CsHelpDesk</p></td>
<td><p>可以查看部署, 包括用户的属性和策略。 可以运行特定的疑难解答任务。 无法更改用户属性或策略、服务器配置或服务。</p></td>
<td><p>CSHelpDesk</p></td>
<td><p>支持人员</p></td>
</tr>
<tr class="odd">
<td><p>CsArchivingAdministrator</p></td>
<td><p>可以修改存档配置和策略。</p></td>
<td><p>CSArchivingAdministrator</p></td>
<td><p>保留管理, 法律封存</p></td>
</tr>
<tr class="even">
<td><p>CsResponseGroupAdministrator</p></td>
<td><p>可以管理网站内响应组应用程序的配置。</p></td>
<td><p>CSResponseGroupAdministrator</p></td>
<td><p>不适用</p></td>
</tr>
<tr class="odd">
<td><p>CsLocationAdministrator</p></td>
<td><p>增强 9-1-1 (E9-1) 管理的最低权限级别, 包括创建 E9-1 位置和网络标识符, 以及将它们相互关联。 此角色始终分配有全局范围。</p></td>
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
</tbody>
</table>


Lync Server 附带的所有预定义角色都具有全局范围。 若要遵循最低权限做法, 则不应将用户分配给具有全局范围的角色 (如果他们仅管理有限的一组服务器或用户)。 若要实现此目的, 你可以创建基于现有角色的角色, 但范围更有限。

<div>

## <a name="creating-a-scoped-role"></a>创建作用域角色

创建具有有限范围 (作用域角色) 的角色时, 指定作用域以及它所基于的现有角色以及要为其分配角色的 Active Directory 组。 你指定的 Active Directory 组必须已创建。 以下 cmdlet 是创建一个角色的示例, 该角色具有一个预定义的管理角色的权限, 但范围有限。 它将创建一个名`Site01 Server Administrators`为的新角色。 角色具有预定义的 CsServerAdministrator 角色的功能, 但仅适用于位于 Site01 网站中的服务器。 为使此 cmdlet 正常工作, Site01 网站必须已定义, 并且名为`Site01 Server Administrators`的通用安全组必须已经存在。

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

运行此 cmdlet 后, 属于`Site01 Server Administrators`该组成员的所有用户将拥有 Site01 中服务器的服务器管理员权限。 此外, 随后添加到此通用安全组的任何用户也会获得此角色的权限。 请注意, 角色本身和分配给它的通用安全组都被称为`Site01 Server Administrators`。

以下示例限制用户范围, 而不是服务器范围。 它将创建`Sales Users Administrator`一个角色来管理销售组织单位中的用户帐户。 必须已创建 SalesUsersAdministrator 通用安全组, 此 cmdlet 才能正常工作。

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a>创建新角色

若要创建可访问一组不在预定义角色或一组脚本或模块中的一组 cmdlet 的角色, 请再次使用预定义角色之一作为模板开始。 请注意, 角色可以运行的脚本和模块必须存储在以下位置:

  - Lync\\模块路径, 默认情况下为 C: 程序文件\\常见文件\\Microsoft Lync Server 2013\\模块 Lync\\

  - 用户脚本\\路径, 默认情况下为 C: 程序文件\\常见文件\\Microsoft Lync Server 2013 AdminScripts\\

若要创建新角色, 请使用**CsAdminRole** cmdlet。 在运行**New-CsAdminRole**之前, 必须首先创建将与此角色关联的基础通用安全组。

以下 cmdlet 用作创建新角色的示例。 他们创建了一个名`MyHelpDeskScriptRole`为的新角色类型。 新角色具有预定义的 CsHelpDesk 角色的功能, 并且还可以在名为 "testscript" 的脚本中运行函数。

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

为使此 cmdlet 正常工作, 你必须首先创建通用安全组 MyHelpDeskScriptRole。

运行此 cmdlet 后, 你可以直接将用户分配给此角色 (在这种情况下, 它们具有全局范围), 或创建基于此角色的作用域角色, 如在本文档前面创建作用域角色中所述。

</div>

<div>

## <a name="assigning-roles-to-users"></a>向用户分配角色

每个 Lync 服务器角色都与一个基础 Active Directory 通用安全组相关联。 你添加到基础组的任何用户都可以获得该角色的能力。

上述部分中的示例创建了一个新角色并向新角色分配了现有通用安全组。 若要将现有角色分配给一个或多个用户, 请将这些用户添加到与该角色关联的组中。 你可以将单个用户和通用安全组添加到这些组。

例如, **CsAdministrator**角色将自动授予 Active Directory 中的**CS 管理员**通用安全组。 当你部署 Lync Server 时, 将在 Active Directory 中创建此通用安全组。 若要向用户或组授予此权限, 只需将其添加到**CS 管理员**组即可。

通过将用户添加到对应于每个角色的基础 Active Directory 组, 可向用户提供多个 RBAC 角色。

请注意, 当你创建一个角色时, 后来添加到基础 Active Directory 组的用户将获得该角色的能力。

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a>修改角色的功能

你可以修改角色可以运行的 cmdlet 和脚本的列表。 你可以修改自定义角色可以运行的 cmdlet 和脚本, 但只能修改预定义角色的脚本。 您键入的每个 cmdlet 都可以添加、删除或替换 cmdlet 或脚本。

若要修改角色, 请使用**CsAdminRole** cmdlet。 以下 cmdlet 删除角色中的一个脚本。

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a>制定 RBAC 计划

对于要针对 Lync Server 部署获得任何类型的管理权限的每个人, 请考虑他们需要执行的任务, 然后将它们分配给其作业所需的最低权限和作用域角色。 如有必要, 你可以使用**CsAdminRole** cmdlet 创建一个新角色, 其中仅包含此人员的任务所需的 cmdlet。

具有 CsAdministrator 角色的用户可以创建所有类型的角色, 包括基于 CsAdministrator 的角色, 并为用户分配用户。 最佳做法是将 CsAdministrator 角色分配给一组非常小的受信任的用户。

</div>

</div>

<span> </span>

</div>

</div>

</div>

