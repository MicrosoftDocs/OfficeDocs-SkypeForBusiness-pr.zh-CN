---
title: 在 Microsoft Teams 管理中心中管理团队
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: 了解如何在 Microsoft 团队管理中心查看或更新团队。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c205c8d3b4f57935c1882530815643a90357d1aa
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548267"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 管理中心中管理团队
==========================================


## <a name="overview"></a>概述

作为 IT 管理员, 你可能需要查看或更新你的组织为协作设置的团队, 或者你可能需要执行补救操作, 例如分配 ownerless 团队的所有者。 你可以通过 Microsoft 团队 PowerShell 模块和 Microsoft 团队管理中心管理组织中使用的团队。 对于使用这两个工具集的完全管理功能, 您应该确保已为您分配了下列角色之一:

- 全局管理员
- Teams 服务管理员

可以在[使用 Microsoft 团队管理员角色管理团队](using-admin-roles.md)的团队中了解有关管理员角色的详细信息, 还可以阅读有关如何使用 PowerShell cmdlet 来管理[Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)中的团队的详细信息。  

本文概述了 Microsoft 团队管理中心中的团队管理工具。

## <a name="teams-overview-grid"></a>团队概述网格

团队的管理工具位于 Microsoft 团队管理中心的 "**团队**" 节点下。 (在管理中心中, 选择 "**团队** > **管理团队**"。)每个团队由 Office 365 组支持, 并且此节点提供已在你的组织中启用了 Microsoft 团队的组的视图。

![团队概述网格的屏幕截图](media/manage-teams-in-modern-portal-image1.png)  

网格显示以下属性:

- **团队名称**
- **频道**-组中所有频道的计数, 包括默认的 "常规" 通道。
- **用户**-用户总数 (包括来自租户的所有者、来宾和成员) 的计数。
- **所有者**-此团队的所有者计数。
- **来宾**-属于此团队成员的 Azure ACTIVE Directory B2B 来宾用户的计数。
- **隐私**-支持的 Office 365 组的可见性/AccessType。
- **状态**-此团队的已存档或活动状态。  了解有关存档中的团队[或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)的详细信息。
- **GroupID** -支持 Office 365 组的独特的 GroupID
- **分类**-分配给支持 Office 365 组的分类 (如果在您的组织中使用)。  了解有关分类的详细信息, 请参阅[为组织中的 Office 组创建分类](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)。
- **说明**-针对支持的 Office 365 组设置的说明

### <a name="search"></a>搜索

搜索当前支持字符串 "始于" 并搜索 "**团队名称**" 字段。

### <a name="edit"></a>编辑

通过从网格中选择团队, 然后选择 "**编辑**" 按钮, 可以编辑组和团队特定的设置。

!["编辑团队选项" 的屏幕截图](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a>团队档案

通过单击团队名称, 可以从 "主团队概述" 网格导航到任何团队的团队个人资料页面。 "团队配置文件" 页面显示属于团队的成员、所有者和来宾 (及其支持的 O365 组) 以及团队的频道和设置。 从 "团队个人资料" 页面, 您可以:

- 添加或删除成员和所有者。
- 添加或删除频道 (请注意, 您不能删除 "常规频道")。
- 更新团队和组设置。
 
![示例团队档案的屏幕截图](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a>对团队进行更改

你可以更改团队的以下元素:
- **团队中的用户**-你可以添加或删除成员, 以及提升或降级所有者
- **频道**-您可以添加新频道或删除现有频道。  您不能删除默认的 "常规" 频道, 创建后只能编辑频道名称, 不能编辑描述。
- **团队名称**
- **团队说明**
- **工作组隐私**-公共或私人
- **团队分类**-由 Office 365 组分类支持
- **工作组成员设置**-选择工作组成员设置

## <a name="other-supported-changes-to-teams"></a>对团队的其他受支持的更改

- **删除**-删除团队是团队和对应的 Office 365 组的软删除。  若要还原错误删除的团队, 请按照[还原已删除的 Office 365 组](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide)中的说明进行操作。
- **存档**-存档团队将团队置于 Microsoft 团队内的只读模式。  作为管理员, 你可以通过管理门户代表你的组织存档和 unarchive 团队。


将记录对团队所做的更改。 如果你要修改组设置 (更改名称、说明、照片、隐私、分类或团队成员), 这些更改将通过审核管道向你开放。 如果你要针对特定于团队的设置执行操作, 你的更改将在团队的常规频道中进行跟踪和设置。

## <a name="troubleshooting"></a>疑难解答

**问题: 团队概述网格中缺少团队**

输入 Microsoft 团队管理中心时, 在 "团队" 选项**** 下的 "团队概述" 网格列表中缺少某些团队。

**原因**: 当团队不正确 (或尚未) 被系统分析时, 将出现此问题, 这可能会导致它无法识别某个缺少的属性。

**解决方案: 通过 MS Graph 手动将属性设置为正确的值**

在查询中使用 **"[UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet 作为 "**ExternalDirectoryObjectId**" 属性替换 **{Groupid}** , 它可以通过 Exchange Online powershell 获得相关实际的 groupid。

1. Access [Graph 资源管理器](https://developer.microsoft.com/en-us/graph/graph-explorer)

2. 在左侧菜单中登录到图形资源管理器

3. 将查询行更改为: PATCH > v 1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}

4. 在请求正文中添加以下值: {"resourceProvisioningOptions": ["Team"]}

5. 在右上角运行查询。

6. 确认团队是否正确显示在 Microsoft 团队管理中心-团队概述


## <a name="learn-more"></a>了解更多信息

[Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[Microsoft 团队中的管理员角色](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

