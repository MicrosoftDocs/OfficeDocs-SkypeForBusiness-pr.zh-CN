---
title: 管理 Microsoft 团队管理中心中的团队
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: 了解如何查看或更新您的 Microsoft 团队管理中心中的团队。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d2903e65e4ef4876f41d367ce961530020e775c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202728"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a>管理 Microsoft 团队管理中心中的团队
==========================================


## <a name="overview"></a>概述

作为一名 IT 管理员，您可能需要查看或更新您的组织已设置的协作，或您的团队可能需要执行修正操作，如分配无所有者团队的所有者。 您可以管理通过 Microsoft 团队 PowerShell 模块和 Microsoft 团队管理中心您组织中使用的团队。 对于使用以下两个工具集的完整的管理功能，您应该确保您已分配下列角色之一：

- 全局管理员
- Teams 服务管理员

您可以了解有关管理角色的团队中[使用的 Microsoft 团队管理角色，来管理团队](using-admin-roles.md)，并且您可以阅读更多有关如何使用 PowerShell cmdlet 进行管理[的 Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)中的团队。  

本文概述了 Microsoft 团队管理中心中的团队的管理工具。

## <a name="teams-overview-grid"></a>团队概述网格

团队的管理工具是 Microsoft 团队管理中心中的**团队**节点下。 (在管理中心中选择**团队** > **管理团队**。)此节点提供已 Microsoft 团队启用您的组织中的组的视图和每个工作组后盾 Office 365 组。

![团队概述网格](media/manage-teams-in-modern-portal-image1.png)  

网格中显示以下属性：

- **团队名称**
- **通道**-团队，包括默认常规通道中的所有频道的计数。
- **用户**的用户总数，包括所有者、 来宾和从租户的成员计数。
- **所有者**-此团队的所有者的计数。
- **来宾**-的 Azure Active Directory B2B 来宾用户属于此团队的成员计数。
- **隐私**-备份 Office 365 组的可见性/AccessType。
- **状态**-已存档或此团队活动状态。  了解有关存档[存档或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)中的团队。
- **GroupID** -备份 Office 365 组的唯一 GroupID
- **分类**-分配给备份 Office 365 组的分类 （如果您的组织中使用）。  了解有关在[创建您的组织中的 Office 组分类](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)的分类。
- **说明**-备份 Office 365 组设置的说明

### <a name="search"></a>搜索

搜索当前支持"始于"的字符串，并搜索**工作组名称**字段。

### <a name="edit"></a>编辑

您可以通过从网格中选择一个团队，然后选择**编辑**按钮编辑组和团队特定设置。

![编辑团队](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a>团队配置文件

您可以通过单击工作组名称来导航从主团队概述网格到任何团队的团队配置文件页。 团队配置文件页用于显示成员、 所有者和属于团队的来宾 (并将其备份 O365 组)，以及团队的通道和设置。 从工作组配置文件页，您可以：

- 添加或删除成员和所有者。
- 添加或删除通道 （请注意，不能删除常规通道）。
- 更新团队和组设置。
 
![团队配置文件](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a>向工作组进行更改

您可以更改团队的以下元素：
- **团队中的用户**-您可以添加或删除成员，以及升级或降级所有者
- **通道**-您可以添加新频道或删除现有通道。  无法删除默认的"常规"通道，并且一次创建您只能编辑的通道名称，不的说明。
- **团队名称**
- **团队说明**
- **团队隐私**-公共或专用
- **团队分类**-通过您的 Office 365 组分类备份
- **团队成员设置**-选择团队成员设置

## <a name="other-supported-changes-to-teams"></a>向工作组其他受支持的更改

- **删除**-删除团队是团队和相应的 Office 365 组软删除。  若要还原的错误地删除的工作组，按照在[还原已删除的 Office 365 组](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide)的说明。
- **存档**的存档团队将置于只读模式中的 Microsoft 团队的团队。  作为一名管理员，您可以存档和代表通过管理门户组织 unarchive 团队。


记录对团队所做的更改。 如果您要修改组设置 （更改名称、 说明、 照片、 隐私、 分类或工作组成员），您将这些更改的归功于您通过审核管道。 如果您执行的操作对特定于团队的设置，则将跟踪所做的更改，并将其团队的常规频道中属于您。

## <a name="troubleshooting"></a>疑难解答

**问题： 团队团队概述网格中缺少**

输入的 Microsoft 团队管理中心时，**团队**选项下您的团队丢失了一些来自团队概述网格中的列表。

**原因**： 该团队已正确 （或尚未） 分析系统这会导致它才能被识别缺少属性，则会发生此问题。

**解决方案： 手动将属性设置为正确值通过 MS 图**

替换为"**ExternalDirectoryObjectId**"属性 **"[Get UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet， **{groupid}** 中的查询的实际的 GroupId 问题，您可以通过 Exchange Online powershell 中，获取其。

1. 访问[图表资源管理器](https://developer.microsoft.com/en-us/graph/graph-explorer)

2. 在左侧菜单上登录到图资源管理器

3. 更改查询行： 修补程序 > v1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}

4. 在请求正文中添加以下值: {"resourceProvisioningOptions":"团队"}

5. 在右上角中运行查询。

6. 确认工作组能够正确显示在 Microsoft 团队管理中心-团队概述 （英文）


## <a name="learn-more"></a>了解更多信息

[Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[管理员角色中的 Microsoft 团队](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

