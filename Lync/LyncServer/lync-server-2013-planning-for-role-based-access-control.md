---
title: Lync Server 2013：规划基于角色的访问控制
description: Lync Server 2013：规划基于角色的访问控制。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for role-based access control (RBAC)
ms:assetid: 41204ba3-ce5b-41a8-a6c3-b444468fa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425917(v=OCS.15)
ms:contentKeyID: 48183962
ms.date: 01/28/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 971b3353694a1cdd53d88452717e6a9a360c6870
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549238"
---
# <a name="planning-for-role-based-access-control-in-lync-server-2013"></a><span data-ttu-id="4b935-103">在 Lync Server 2013 中规划基于角色的访问控制</span><span class="sxs-lookup"><span data-stu-id="4b935-103">Planning for role-based access control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b935-104">_**上次修改的主题：** 2015-01-27_</span><span class="sxs-lookup"><span data-stu-id="4b935-104">_**Topic Last Modified:** 2015-01-27_</span></span>

<span data-ttu-id="4b935-105">为了使您能够在保持高安全性标准的同时委派管理任务，Lync Server 2013 提供基于角色的访问控制 (RBAC) 。</span><span class="sxs-lookup"><span data-stu-id="4b935-105">To enable you to delegate administrative tasks while maintaining high standards for security, Lync Server 2013 offers role-based access control (RBAC).</span></span> <span data-ttu-id="4b935-106">使用 RBAC，可通过将用户分配给管理角色来授予管理权限。</span><span class="sxs-lookup"><span data-stu-id="4b935-106">With RBAC, administrative privilege is granted by assigning users to administrative roles.</span></span> <span data-ttu-id="4b935-107">Lync Server 2013 包括一组丰富的内置管理角色，还使您能够创建新角色并为每个新角色指定自定义 cmdlet 列表。</span><span class="sxs-lookup"><span data-stu-id="4b935-107">Lync Server 2013 includes a rich set of built-in administrative roles, and also enables you to create new roles and specify a custom list of cmdlets for each new role.</span></span> <span data-ttu-id="4b935-108">您还可以将 cmdlet 的脚本添加到所允许的预定义和自定义 RBAC 角色任务中。</span><span class="sxs-lookup"><span data-stu-id="4b935-108">You can also add scripts of cmdlets to the allowed tasks of both predefined and custom RBAC roles.</span></span>

<div>

## <a name="better-server-security-and-centralization"></a><span data-ttu-id="4b935-109">更高的服务器安全性和集中化</span><span class="sxs-lookup"><span data-stu-id="4b935-109">Better Server Security and Centralization</span></span>

<span data-ttu-id="4b935-110">使用 RBAC，访问和授权完全基于用户的 Lync Server 角色。</span><span class="sxs-lookup"><span data-stu-id="4b935-110">With RBAC, access and authorization is based precisely on a user’s Lync Server role.</span></span> <span data-ttu-id="4b935-111">这样就可以利用“最小特权”安全做法，以便仅向管理员和用户授予其工作所需的权限。</span><span class="sxs-lookup"><span data-stu-id="4b935-111">This enables use of the security practice of "least privilege," granting administrators and users only the rights that are necessary for their job.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4b935-112">RBAC 限制仅适用于远程工作的管理员，使用 Lync Server 控制面板或 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="4b935-112">RBAC restrictions work only on administrators working remotely, using either the Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="4b935-113">在运行 Lync Server 的服务器上的用户不受 RBAC 限制。</span><span class="sxs-lookup"><span data-stu-id="4b935-113">A user sitting at a server running Lync Server is not restricted by RBAC.</span></span> <span data-ttu-id="4b935-114">因此，Lync Server 的物理安全性对保留 RBAC 限制非常重要。</span><span class="sxs-lookup"><span data-stu-id="4b935-114">Therefore, physical security of your Lync Server is important to preserve RBAC restrictions.</span></span>



</div>

</div>

<div>

## <a name="roles-and-scope"></a><span data-ttu-id="4b935-115">角色和作用域</span><span class="sxs-lookup"><span data-stu-id="4b935-115">Roles and Scope</span></span>

<span data-ttu-id="4b935-p104">在 RBAC 中，启用*角色* 是为了使用旨在帮助特定类型的管理员或技术人员的 cmdlet 的列表。*作用域* 是一组角色中定义的 cmdlet 可以对其执行操作的对象。受作用域影响的对象可以是用户帐户（按组织单位分组）或服务器（按站点分组）。</span><span class="sxs-lookup"><span data-stu-id="4b935-p104">In RBAC, a *role* is enabled to use a list of cmdlets, designed to be useful for a certain type of administrator or technician. A *scope* is the set of objects which the cmdlets defined in a role can operate on. The objects that scope affects can be either user accounts (grouped by organizational unit) or servers (grouped by site).</span></span>

<span data-ttu-id="4b935-119">下表列出了 Lync Server 中的预定义角色，并提供了每个可执行的任务类型的一般概述。</span><span class="sxs-lookup"><span data-stu-id="4b935-119">The following table lists the predefined roles in Lync Server, and gives a general overview of the types of tasks each can do.</span></span> <span data-ttu-id="4b935-120">第四列显示了每个 Lync 服务器角色的类似 Microsoft Exchange Server 角色（如果有的话）。</span><span class="sxs-lookup"><span data-stu-id="4b935-120">The fourth column shows the similar Microsoft Exchange Server role for each Lync Server role, if there is one.</span></span>

### <a name="predefined-administrative-roles"></a><span data-ttu-id="4b935-121">预定义的管理角色</span><span class="sxs-lookup"><span data-stu-id="4b935-121">Predefined Administrative Roles</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b935-122">Role</span><span class="sxs-lookup"><span data-stu-id="4b935-122">Role</span></span></th>
<th><span data-ttu-id="4b935-123">允许的任务</span><span class="sxs-lookup"><span data-stu-id="4b935-123">Tasks allowed</span></span></th>
<th><span data-ttu-id="4b935-124">基础 Active Directory 组</span><span class="sxs-lookup"><span data-stu-id="4b935-124">Underlying Active Directory group</span></span></th>
<th><span data-ttu-id="4b935-125">Exchange 等效项</span><span class="sxs-lookup"><span data-stu-id="4b935-125">Exchange equivalent</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b935-126">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="4b935-126">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4b935-p106">可以执行所有管理任务和修改所有设置，包括创建角色和将用户分配给角色。可以通过添加新的站点、池和服务来扩展部署。</span><span class="sxs-lookup"><span data-stu-id="4b935-p106">Can perform all administrative tasks and modify all settings, including creating roles and assigning users to roles. Can expand a deployment by adding new sites, pools, and services.</span></span></p></td>
<td><p><span data-ttu-id="4b935-129">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="4b935-129">CSAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4b935-130">Organization Management</span><span class="sxs-lookup"><span data-stu-id="4b935-130">Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b935-131">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="4b935-131">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4b935-132">可以为 Lync Server 启用和禁用用户，移动用户并向用户分配现有策略。</span><span class="sxs-lookup"><span data-stu-id="4b935-132">Can enable and disable users for Lync Server, move users and assign existing policies to users.</span></span> <span data-ttu-id="4b935-133">不能修改策略。</span><span class="sxs-lookup"><span data-stu-id="4b935-133">Cannot modify policies.</span></span></p></td>
<td><p><span data-ttu-id="4b935-134">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="4b935-134">CSUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4b935-135">Mail Recipients</span><span class="sxs-lookup"><span data-stu-id="4b935-135">Mail Recipients</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b935-136">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="4b935-136">CsVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4b935-137">可以创建、配置和管理与语音相关的设置和策略。</span><span class="sxs-lookup"><span data-stu-id="4b935-137">Can create, configure, and manage voice-related settings and policies.</span></span></p></td>
<td><p><span data-ttu-id="4b935-138">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="4b935-138">CSVoiceAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4b935-139">不适用</span><span class="sxs-lookup"><span data-stu-id="4b935-139">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b935-140">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="4b935-140">CsServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4b935-p108">可以管理、监控服务器和服务，以及排除服务器和服务的故障。可以阻止与服务器建立新连接、停止和启动服务以及应用软件更新。不能做出影响全局配置的更改。</span><span class="sxs-lookup"><span data-stu-id="4b935-p108">Can manage, monitor, and troubleshoot servers and services. Can prevent new connections to servers, stop and start services, and apply software updates. Cannot make changes with global configuration impact.</span></span></p></td>
<td><p><span data-ttu-id="4b935-144">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="4b935-144">CSServerAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4b935-145">Server Management</span><span class="sxs-lookup"><span data-stu-id="4b935-145">Server Management</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b935-146">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="4b935-146">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4b935-147">可以查看部署（包括用户和服务器信息），以便监控部署的运行状况。</span><span class="sxs-lookup"><span data-stu-id="4b935-147">Can view the deployment, including user and server information, in order to monitor deployment health.</span></span></p></td>
<td><p><span data-ttu-id="4b935-148">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="4b935-148">CSViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4b935-149">View-Only Organization Management</span><span class="sxs-lookup"><span data-stu-id="4b935-149">View-Only Organization Management</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b935-150">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="4b935-150">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="4b935-p109">可以查看部署，包括用户的属性和策略。可以运行特定的故障排除任务。不能更改用户属性或策略、服务器配置或服务。</span><span class="sxs-lookup"><span data-stu-id="4b935-p109">Can view the deployment, including user's properties and policies. Can run specific troubleshooting tasks. Cannot change user properties or policies, server configuration, or services.</span></span></p></td>
<td><p><span data-ttu-id="4b935-154">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="4b935-154">CSHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="4b935-155">技术</span><span class="sxs-lookup"><span data-stu-id="4b935-155">HelpDesk</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b935-156">CsArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="4b935-156">CsArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4b935-157">可以修改存档配置和策略。</span><span class="sxs-lookup"><span data-stu-id="4b935-157">Can modify archiving configuration and policies.</span></span></p></td>
<td><p><span data-ttu-id="4b935-158">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="4b935-158">CSArchivingAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4b935-159">Retention Management、Legal Hold</span><span class="sxs-lookup"><span data-stu-id="4b935-159">Retention Management, Legal Hold</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b935-160">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="4b935-160">CsResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4b935-161">可以在站点内管理响应组应用程序的配置。</span><span class="sxs-lookup"><span data-stu-id="4b935-161">Can manage the configuration of the Response Group application within a site.</span></span></p></td>
<td><p><span data-ttu-id="4b935-162">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="4b935-162">CSResponseGroupAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4b935-163">不适用</span><span class="sxs-lookup"><span data-stu-id="4b935-163">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b935-164">CsLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="4b935-164">CsLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4b935-p110">增强型 9-1-1 (E9-1-1) 的最低级别权限管理，包括创建 E9-1-1 位置和网络标识符，以及将这二者相互关联。此角色始终分配有 global 作用域。</span><span class="sxs-lookup"><span data-stu-id="4b935-p110">Lowest level of rights for Enhanced 9-1-1 (E9-1-1) management, including creating E9-1-1 locations and network identifiers, and associating these with each other. This role is always assigned with a global scope.</span></span></p></td>
<td><p><span data-ttu-id="4b935-167">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="4b935-167">CSLocationAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4b935-168">不适用</span><span class="sxs-lookup"><span data-stu-id="4b935-168">Not applicable</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b935-169">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="4b935-169">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="4b935-170">可以管理特定的响应组。</span><span class="sxs-lookup"><span data-stu-id="4b935-170">Can manage specific response groups.</span></span></p></td>
<td><p><span data-ttu-id="4b935-171">CSResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="4b935-171">CSResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="4b935-172">不适用</span><span class="sxs-lookup"><span data-stu-id="4b935-172">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b935-173">CsPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="4b935-173">CsPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4b935-174">可以管理持久聊天功能和特定的持久聊天聊天室。</span><span class="sxs-lookup"><span data-stu-id="4b935-174">Can manage the Persistent Chat feature and specific Persistent Chat rooms.</span></span></p></td>
<td><p><span data-ttu-id="4b935-175">CSPersistentChatAdministrator</span><span class="sxs-lookup"><span data-stu-id="4b935-175">CSPersistentChatAdministrator</span></span></p></td>
<td><p><span data-ttu-id="4b935-176">不适用</span><span class="sxs-lookup"><span data-stu-id="4b935-176">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4b935-177">Lync Server 中发售的所有预定义角色都具有全局作用域。</span><span class="sxs-lookup"><span data-stu-id="4b935-177">All predefined roles shipped in Lync Server have a global scope.</span></span> <span data-ttu-id="4b935-178">为符合“最小特权”做法，如果用户仅管理有限的一组服务器或用户，则不应将他们分配给具有全局作用域的角色。</span><span class="sxs-lookup"><span data-stu-id="4b935-178">To follow least privilege practices, you should not assign users to roles with global scope if they are going to administer only a limited set of servers or users.</span></span> <span data-ttu-id="4b935-179">为此，可以创建基于现有角色但作用域更加有限的角色。</span><span class="sxs-lookup"><span data-stu-id="4b935-179">To accomplish this, you can create roles which are based on an existing role, but with a more limited scope.</span></span>

<div>

## <a name="creating-a-scoped-role"></a><span data-ttu-id="4b935-180">创建作用域角色</span><span class="sxs-lookup"><span data-stu-id="4b935-180">Creating a Scoped Role</span></span>

<span data-ttu-id="4b935-181">创建作用域有限的角色（作用域角色）时，需指定作用域、该角色所基于的现有角色以及要将该角色分配到的 Active Directory 组。</span><span class="sxs-lookup"><span data-stu-id="4b935-181">When you create a role with limited scope (a scoped role), you specify the scope, along with the existing role it is based on and the Active Directory group to be assigned the role.</span></span> <span data-ttu-id="4b935-182">指定的 Active Directory 组必须是已创建的组。</span><span class="sxs-lookup"><span data-stu-id="4b935-182">The Active Directory group you specify must already be created.</span></span> <span data-ttu-id="4b935-183">以下 cmdlet 示例创建的角色具有其中一种预定义管理角色的权限，但具有有限作用域。</span><span class="sxs-lookup"><span data-stu-id="4b935-183">The following cmdlet is an example of a creating a role which has the privileges of one of the pre-defined administrative roles, but with limited scope.</span></span> <span data-ttu-id="4b935-184">它将创建一个名为的新角色 `Site01 Server Administrators` 。</span><span class="sxs-lookup"><span data-stu-id="4b935-184">It creates a new role called `Site01 Server Administrators`.</span></span> <span data-ttu-id="4b935-185">该角色具有预定义的 CsServerAdministrator 角色的功能，但仅适用于位于 Site01 站点上的服务器。</span><span class="sxs-lookup"><span data-stu-id="4b935-185">The role has the abilities of the predefined CsServerAdministrator role, but only for the servers located in the Site01 site.</span></span> <span data-ttu-id="4b935-186">为使此 cmdlet 正常工作，必须已定义 Site01 网站，并且名为的通用安全组 `Site01 Server Administrators` 必须已存在。</span><span class="sxs-lookup"><span data-stu-id="4b935-186">For this cmdlet to work, the Site01 site must already be defined, and a universal security group named `Site01 Server Administrators` must already exist.</span></span>

    New-CsAdminRole -Identity "Site01 Server Administrators" -Template CsServerAdministrator -ConfigScopes "site:Site01"

<span data-ttu-id="4b935-187">运行此 cmdlet 之后，作为组成员的所有用户 `Site01 Server Administrators` 将具有对 Site01 中的服务器的服务器管理员权限。</span><span class="sxs-lookup"><span data-stu-id="4b935-187">After this cmdlet runs, all users who are members of the `Site01 Server Administrators` group will have server administrator privileges for the servers in Site01.</span></span> <span data-ttu-id="4b935-188">此外，随后添加到此通用安全组的任何用户也会获得此角色的权限。</span><span class="sxs-lookup"><span data-stu-id="4b935-188">Additionally, any users who are later added to this universal security group also gain the privileges of this role.</span></span> <span data-ttu-id="4b935-189">请注意，角色本身和分配给它的通用安全组都被称为 `Site01 Server Administrators` 。</span><span class="sxs-lookup"><span data-stu-id="4b935-189">Note that both the role itself, and the universal security group it is assigned to are called `Site01 Server Administrators`.</span></span>

<span data-ttu-id="4b935-190">以下示例限定用户作用域，而不是服务器作用域。</span><span class="sxs-lookup"><span data-stu-id="4b935-190">The following example limits user scope instead of server scope.</span></span> <span data-ttu-id="4b935-191">它创建一个 `Sales Users Administrator` 角色来管理销售组织单位中的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="4b935-191">It creates a `Sales Users Administrator` role to administer the user accounts in the Sales organizational unit.</span></span> <span data-ttu-id="4b935-192">必须已创建 SalesUsersAdministrator 通用安全组，此 cmdlet 才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="4b935-192">The SalesUsersAdministrator universal security group must already be created for this cmdlet to work.</span></span>

    New-CsAdminRole -Identity "Sales Users Administrator " -Template CsUserAdministrator -UserScopes "OU:OU=Sales, OU=Lync Tenants, DC=Domain, DC=com"

</div>

<div>

## <a name="creating-a-new-role"></a><span data-ttu-id="4b935-193">新建角色</span><span class="sxs-lookup"><span data-stu-id="4b935-193">Creating a New Role</span></span>

<span data-ttu-id="4b935-p115">要创建的角色必须能够访问 cmdlet 组而不是其中一个预定义角色，或者必须能够访问一组脚本或模块，您再次需要从使用其中一个预定义角色作为模板开始。请注意，角色能够运行的脚本和模块必须存储在以下位置：</span><span class="sxs-lookup"><span data-stu-id="4b935-p115">To create a role that has access to a set of cmdlets not in one of the predefined roles, or to a set of scripts or modules, you again start by using one of the predefined roles as a template. Note that scripts and modules that roles are to be able to run must be stored in the following locations:</span></span>

  - <span data-ttu-id="4b935-196">Lync 模块路径，默认情况下 C： \\ Program files \\ 常见文件 \\ Microsoft Lync Server 2013 \\ 模块 \\ Lync</span><span class="sxs-lookup"><span data-stu-id="4b935-196">The Lync module path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\Lync</span></span>

  - <span data-ttu-id="4b935-197">用户脚本路径，默认情况下 C： \\ Program files \\ 常见文件 \\ Microsoft Lync Server 2013 \\ AdminScripts</span><span class="sxs-lookup"><span data-stu-id="4b935-197">The user script path, which is by default C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\AdminScripts</span></span>

<span data-ttu-id="4b935-198">要创建新角色，请使用 **New-CsAdminRole** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4b935-198">To make a new role, you use the **New-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="4b935-199">在运行 **CsAdminRole**之前，必须先创建将与此角色关联的基础通用安全组。</span><span class="sxs-lookup"><span data-stu-id="4b935-199">Before running **New-CsAdminRole**, you must first create the underlying universal security group that will be associated with this role.</span></span>

<span data-ttu-id="4b935-200">以下 cmdlet 为创建新角色的示例。</span><span class="sxs-lookup"><span data-stu-id="4b935-200">The following cmdlets serve as an example of a creating a new role.</span></span> <span data-ttu-id="4b935-201">它们创建一个名为的新角色类型 `MyHelpDeskScriptRole` 。</span><span class="sxs-lookup"><span data-stu-id="4b935-201">They create a new role type called `MyHelpDeskScriptRole`.</span></span> <span data-ttu-id="4b935-202">该新角色具有预定义 CsHelpDesk 角色的功能，另外还可以运行名为“testscript”的脚本中的函数。</span><span class="sxs-lookup"><span data-stu-id="4b935-202">The new role has the abilities of the predefined CsHelpDesk role, and can additionally run the functions in a script named “testscript”.</span></span>

    New-CsAdminRole -Identity "MyHelpDeskScriptRole" -Template CsHelpDesk -ScriptModules @{Add="testScript.ps1"}

<span data-ttu-id="4b935-203">若要使用此 cmdlet，您必须首先创建通用安全组 MyHelpDeskScriptRole。</span><span class="sxs-lookup"><span data-stu-id="4b935-203">For this cmdlet to work, you must have first created the universal security group MyHelpDeskScriptRole.</span></span>

<span data-ttu-id="4b935-204">运行此 cmdlet 后，您可以直接将用户分配给此角色（这种情况下，这些用户具有全局作用域），或者基于此角色创建作用域角色，如本文前面“创建作用域角色”所述。</span><span class="sxs-lookup"><span data-stu-id="4b935-204">After this cmdlet runs, you can assign users directly to this role (in which case they have global scope), or create a scoped role based on this role, as explained in Creating a Scoped Role, previously in this document.</span></span>

</div>

<div>

## <a name="assigning-roles-to-users"></a><span data-ttu-id="4b935-205">将角色分配给用户</span><span class="sxs-lookup"><span data-stu-id="4b935-205">Assigning Roles to Users</span></span>

<span data-ttu-id="4b935-206">每个 Lync Server 角色都与基础 Active Directory 通用安全组相关联。</span><span class="sxs-lookup"><span data-stu-id="4b935-206">Each Lync Server role is associated with an underlying Active Directory universal security group.</span></span> <span data-ttu-id="4b935-207">添加到基础组的任何用户都能获得该角色的功能。</span><span class="sxs-lookup"><span data-stu-id="4b935-207">Any users who you add to the underlying group gain the abilities of that role.</span></span>

<span data-ttu-id="4b935-208">上述各节中的示例都创建了一个新角色，并向新角色分配了现有的通用安全组。</span><span class="sxs-lookup"><span data-stu-id="4b935-208">The examples in the preceding sections both created a new role and assigned an existing universal security group to the new role.</span></span> <span data-ttu-id="4b935-209">要将现有角色分配给一个或多个用户，请将这些用户添加到与该角色关联的组中。</span><span class="sxs-lookup"><span data-stu-id="4b935-209">To assign an existing role to one or more users, add those users to the group associated with the role.</span></span> <span data-ttu-id="4b935-210">您可以向这些组中添加个人用户和通用安全组。</span><span class="sxs-lookup"><span data-stu-id="4b935-210">You can add both individual users and universal security groups to these groups.</span></span>

<span data-ttu-id="4b935-211">例如，将 **CsAdministrator** 角色自动授予 Active Directory 中的 **CS Administrators** 通用安全组。</span><span class="sxs-lookup"><span data-stu-id="4b935-211">For example, the **CsAdministrator** role is automatically granted to the **CS Administrators** universal security group in Active Directory.</span></span> <span data-ttu-id="4b935-212">当您部署 Lync Server 时，将在 Active Directory 中创建此通用安全组。</span><span class="sxs-lookup"><span data-stu-id="4b935-212">This universal security group is created in Active Directory when you deploy Lync Server.</span></span> <span data-ttu-id="4b935-213">要向用户或组授予此权限，只需将其添加到 **CS Administrators** 组中。</span><span class="sxs-lookup"><span data-stu-id="4b935-213">To grant a user or group this privilege, you can simply add them to the **CS Administrators** group.</span></span>

<span data-ttu-id="4b935-214">可向用户分配多个 RBAC 角色，方法是将该用户添加到与每个角色相对应的基础 Active Directory 组中。</span><span class="sxs-lookup"><span data-stu-id="4b935-214">A user can be given multiple RBAC roles by being added to the underlying Active Directory groups that correspond to each role.</span></span>

<span data-ttu-id="4b935-215">请注意，如果创建了角色，以后添加到基础 Active Directory 组的用户也可获得该角色的功能。</span><span class="sxs-lookup"><span data-stu-id="4b935-215">Note that when you create a role, users who are later added to the underlying Active Directory group gain the abilities of that role.</span></span>

</div>

<div>

## <a name="modifying-the-abilities-of-a-role"></a><span data-ttu-id="4b935-216">修改角色的功能</span><span class="sxs-lookup"><span data-stu-id="4b935-216">Modifying the Abilities of a Role</span></span>

<span data-ttu-id="4b935-p121">您可以修改角色能够运行的 cmdlet 和脚本的列表。您可以同时修改自定义角色能够运行的 cmdlet 和脚本，但是您只能修改预定义角色的脚本。您键入的每个 cmdlet 均可添加、删除或替换 cmdlet 或脚本。</span><span class="sxs-lookup"><span data-stu-id="4b935-p121">You can modify the list of cmdlets and scripts that a role can run. You can modify both the cmdlets and scripts that custom roles can run, but you can modify only the scripts for predefined roles. Each cmdlet you type can add, remove, or replace cmdlets or scripts.</span></span>

<span data-ttu-id="4b935-220">若要修改角色，请使用 **Set-CsAdminRole** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4b935-220">To modify a role, use the **Set-CsAdminRole** cmdlet.</span></span> <span data-ttu-id="4b935-221">下面的 cmdlet 将从角色中删除一个脚本。</span><span class="sxs-lookup"><span data-stu-id="4b935-221">The following cmdlet removes one script from the role.</span></span>

    Set-CsAdminRole -Identity "MyHelpDeskScriptRole" -ScriptModules @{Remove="testScript.ps1"}

</div>

</div>

<div>

## <a name="planning-for-rbac"></a><span data-ttu-id="4b935-222">规划 RBAC</span><span class="sxs-lookup"><span data-stu-id="4b935-222">Planning for RBAC</span></span>

<span data-ttu-id="4b935-223">对于要向其授予 Lync Server 部署的任何类型的管理权限的每个用户，请确切地考虑他们需要执行的任务，然后将他们分配给其工作所需的权限最少的角色和作用域。</span><span class="sxs-lookup"><span data-stu-id="4b935-223">For each person who is to be given any kind of administrative rights for your Lync Server deployment, consider exactly which tasks they need to perform, then assign them to roles with the least privilege and scope necessary for their job.</span></span> <span data-ttu-id="4b935-224">如果需要，您可以使用 **Set-CsAdminRole** cmdlet 创建一个仅使用该用户完成任务所需 cmdlet 的新角色。</span><span class="sxs-lookup"><span data-stu-id="4b935-224">If necessary, you can use the **Set-CsAdminRole** cmdlet to create a new role with only the cmdlets necessary for this person’s tasks.</span></span>

<span data-ttu-id="4b935-p124">具有 CsAdministrator 角色的用户可以创建所有类型的角色（包括基于 CsAdministrator 的角色）并向其分配用户。最佳实践是将 CsAdministrator 角色分配给少数受信任的用户。</span><span class="sxs-lookup"><span data-stu-id="4b935-p124">Users who have the CsAdministrator role can create all types of roles, including roles based on CsAdministrator, and assign users to them. The best practice is to assign the CsAdministrator role to a very small set of trusted users.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

