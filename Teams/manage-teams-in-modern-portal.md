---
title: 管理团队中的 Microsoft 团队 & Business Admin Center 的 Skype
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: 了解如何查看或更新您的团队中的 Microsoft 团队 & Business Admin Center 的 Skype。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 210824858d953a99844817b3ef27265626d91928
ms.sourcegitcommit: c0679cbaf7df38769f722afd65c4232311d25515
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2019
ms.locfileid: "29562780"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a>管理团队中的 Microsoft 团队 & Business Admin Center 的 Skype
==========================================

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

## <a name="overview"></a>概述

作为一名 IT 管理员，您可能需要查看或更新您的组织已设置的协作，或您的团队可能需要执行修正操作，如分配无所有者团队的所有者。 您可以管理业务管理中心的通过 Microsoft 团队 PowerShell 模块和 Microsoft 团队 & Skype 您组织中使用的团队。 对于使用以下两个工具集的完整的管理功能，您应该确保您已分配下列角色之一：

- 全局管理员
- Teams 服务管理员

您还应确保您的帐户已被分配非试用团队许可证管理。 作为一个已知问题的一部分，您应该确保您的帐户具有只有**一个**管理角色分配。  您可以了解有关 Microsoft 团队中[使用的 Microsoft 团队管理角色，来管理团队](using-admin-roles.md)，管理员角色的详细信息，并可以了解有关如何使用 PowerShell cmdlet 进行管理[的 Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)中的团队。  

本文概述了团队中的 Microsoft 团队 & Business Admin Center 的 Skype 的管理工具。

## <a name="teams-overview-grid"></a>团队概述网格

团队的管理工具是 Microsoft 团队 & Skype 的业务管理中心中的**团队**节点下。 (在管理中心中选择**团队** > **管理团队**。)此节点提供已 Microsoft 团队启用您的组织中的组的视图和每个工作组后盾 Office 365 组。

> [!NOTE]
> 我们正在回填以前创建以确保它们将出现在此视图的团队。

![团队概述网格](media/manage-teams-in-modern-portal-image1.png)  

网格中显示以下属性：

- **团队名称**
- **通道**-团队，包括默认常规通道中的所有频道的计数。
- **用户**的用户总数，包括所有者、 来宾和从租户的成员计数。
- **所有者**-此团队的所有者的计数。
- **来宾**-的 Azure Active Directory B2B 来宾用户属于此团队的成员计数。
- **隐私**-备份 Office 365 组的 AccessType。

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


记录对团队所做的更改。 如果您要修改组设置 （更改名称、 说明、 照片、 隐私、 分类或工作组成员），您将这些更改的归功于您通过审核管道。 如果您执行的操作对特定于团队的设置，则将跟踪所做的更改，并将其团队的常规频道中属于您。

## <a name="troubleshooting"></a>故障排除

**问题： 团队团队概述网格中缺少**

当您输入的 Microsoft 团队 & Business Admin Center 的 Skype 时，**团队**选项下您的团队一些缺少团队概述网格中的列表。

**原因**： 该团队已正确 （或尚未） 分析系统这会导致它才能被识别缺少属性，则会发生此问题。

**解决方案： 手动将属性设置为正确值通过 MS 图**

替换为"**ExternalDirectoryObjectId**"属性 **"[Get UnifiedGroup](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet， **{groupid}** 中的查询的实际的 GroupId 问题，您可以通过 Exchange Online powershell 中，获取其。

1. 访问[图表资源管理器](https://developer.microsoft.com/en-us/graph/graph-explorer)

2. 在左侧菜单上登录到图资源管理器

3. 更改查询行： 修补程序 > v1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}

4. 在请求正文中添加以下值: {"resourceProvisioningOptions":"团队"}

5. 在右上角中运行查询。

6. 确认工作组正确显示回到上的 Microsoft 团队 & Business Admin Center-的 Skype 团队概述 （英文）


## <a name="learn-more"></a>了解更多信息

[Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[管理员角色中的 Microsoft 团队](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

