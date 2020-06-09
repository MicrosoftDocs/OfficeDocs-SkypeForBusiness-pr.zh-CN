---
title: 管理 Microsoft 团队管理中心中的团队
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: 了解如何在 Microsoft 团队管理中心查看或更新您的组织为协作设置的团队。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ffc71de13948be077c14699e98fca726bced3eb
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638491"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>管理 Microsoft 团队管理中心中的团队
==========================================

## <a name="overview"></a>概述

本文概述了 Microsoft 团队管理中心中的团队管理工具。

作为管理员，你可能需要查看或更新你的组织为协作设置的团队，或者你可能需要执行补救操作，例如分配 ownerless 团队的所有者。 你可以通过 Microsoft 团队 PowerShell 模块和 Microsoft 团队管理中心管理组织中使用的团队。 您可以在上访问管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。 对于使用这两个工具集的完全管理功能，您应该确保已为您分配了下列角色之一：

- 全局管理员
- Teams 服务管理员

可以在[使用 Microsoft 团队管理员角色管理团队](using-admin-roles.md)的团队中了解有关管理员角色的详细信息，还可以阅读有关如何使用 PowerShell cmdlet 来管理[Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)中的团队的详细信息。



## <a name="teams-overview-grid"></a>团队概述网格

团队的管理工具位于 Microsoft 团队管理中心的 "**团队**" 节点下。 （在管理中心中，选择 "**团队**  >  "**管理团队**。）每个团队由 Microsoft 365 组支持，并且此节点提供已在你的组织中启用了 Microsoft 团队的组的视图。

!["团队概述" 网格的屏幕截图](media/manage-teams-in-modern-portal-grid.png)  

网格显示以下属性：

- **团队名称**
- **频道**-组中所有频道的计数，包括默认的 "常规" 通道。
- **团队成员**-总用户数，包括来自租户的所有者、来宾和成员。
- **所有者**-此团队的所有者计数。
- **来宾**-属于此团队成员的 Azure ACTIVE Directory B2B 来宾用户的计数。
- **隐私**-支持的 Microsoft 365 组的可见性/AccessType。
- **状态**-此团队的已存档或活动状态。 了解有关存档[或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)中的存档团队的详细信息。
- **说明**-支持的 Microsoft 365 组的说明。
- **分类**-分配给支持 Microsoft 365 组的分类（如果在您的组织中使用）。 了解有关分类的详细信息，请参阅[为组织中的 Office 组创建分类](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)。
- **GroupID** -支持 Microsoft 365 组的独特的 GroupID。

> [!NOTE]
> 如果在网格中看不到所有这些属性，请单击 "**编辑列**" 图标。 在 "**编辑列**" 窗格中，可以使用切换功能打开或关闭网格中的列。 完成后，单击 "**应用**"。

### <a name="add"></a>插件

若要添加新团队，请单击 "**添加**"。 在 "**添加新团队**" 窗格中，为团队提供名称和说明，设置是要使其成为私有团队还是公共团队，并设置分类。

### <a name="edit"></a>编辑

若要编辑组和团队特定的设置，请通过单击团队名称左侧的团队进行选择，然后选择 "**编辑**"。

### <a name="archive"></a>存档

您可以存档团队。 存档团队会将团队置于团队内的只读模式。 作为管理员，你可以代表你的组织在管理中心中存档和取消存档团队。 

### <a name="delete"></a>删除

删除团队是团队和相应 Microsoft 365 组的软删除。 若要还原错误删除的团队，请按照[还原已删除的组](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)中的说明进行操作。

### <a name="search"></a>搜索

搜索当前支持字符串 "始于" 并搜索 "**团队名称**" 字段。

## <a name="team-profile"></a>团队档案

通过单击团队名称，可以从 "主团队概述" 网格导航到任何团队的团队配置文件页面。 "团队配置文件" 页面显示属于团队的成员、所有者和来宾（及其支持的 Microsoft 365 组）以及团队的频道和设置。 从 "团队个人资料" 页面，您可以：

- 添加或删除成员和所有者。
- 添加或删除频道（请注意，您不能删除 "常规频道"）。
- 更改团队和组设置。
 
![示例团队档案的屏幕截图](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a>对团队进行更改

在团队的配置文件页面上，您可以更改团队的以下元素：

- **成员**-添加或删除成员以及提升或降级所有者。
- **频道**-添加新频道、编辑或删除现有频道。 请记住，您不能删除默认的常规频道。
- **团队名称**
- **说明**
- **隐私**-设置团队是公共的还是私有的。
- **分类**-这由 Microsoft 365 组分类支持。 选择 "**机密**"、"**高度机密**" 或 "**常规**"。
- **对话设置**-设置成员是否可以编辑和删除已发送的邮件。
- **频道设置**-设置成员是否可以创建新频道和编辑现有频道，以及添加、编辑和删除选项卡、连接器和应用。

将记录对团队所做的更改。 如果你要修改组设置（更改名称、说明、照片、隐私、分类或团队成员），则通过审核管道对这些更改进行了设置。 如果你正在针对特定于团队的设置执行操作，你的更改将在团队的常规频道中进行跟踪和设置。

## <a name="troubleshooting"></a>故障排除

**问题：团队概述网格中缺少团队**

团队概述网格中的团队列表中缺少某些团队。

**原因**：当团队不正确（或尚未）被系统分析时，将出现此问题，这可能会导致它无法识别某个缺少的属性。

**解决方案：通过 MS Graph 手动将属性设置为正确的值**

在查询中使用 **"[UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet 作为 "**ExternalDirectoryObjectId**" 属性替换 **{Groupid}** ，它可以通过 Exchange Online powershell 获得相关实际的 groupid。

1. Access [Graph 资源管理器](https://developer.microsoft.com/graph/graph-explorer)。

2. 在左侧菜单中登录到图形资源管理器。

3. 将查询行更改为： PATCH > v 1.0 > https://graph.microsoft.com/v1.0/groups/{groupid} 。

4. 在请求正文中添加以下值： {"resourceProvisioningOptions"： ["Team"]}。

5. 在右上角运行查询。

6. 确认团队是否正确显示在 Microsoft 团队管理中心-团队概述。

## <a name="learn-more"></a>了解详细信息

- [团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [使用团队管理员角色管理团队](using-admin-roles.md)
- [在 Teams 中规划生命周期管理](plan-teams-lifecycle.md)
