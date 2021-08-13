---
title: 在 Microsoft Teams 管理中心中管理 Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: 了解如何在 Microsoft Teams 管理中心查看或更新组织为协作而设置的团队。
localization_priority: Priority
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 314b56c4787049f3ca210de5b55a22ab8487e78d
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "58232677"
---
# <a name="manage-teams-in-the-microsoft-teams-admin-center"></a>在 Microsoft Teams 管理中心中管理团队

## <a name="overview"></a>概述

本文概括介绍了 Microsoft Teams 管理中心中的 Teams 管理工具。

管理员可能需要查看或更新组织为协作而设置的团队，或者可能需要执行修正操作，例如为无主团队分配所有者。 可以通过 Microsoft Teams PowerShell 模块和 Microsoft Teams 管理中心管理组织中使用的团队。 可以在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 访问管理中心。 若要获得使用这两个工具集的完整管理功能，应确保为你分配以下角色之一：

- 全局管理员
- Teams 管理员

可以在[使用 Microsoft Teams 管理员角色管理 Teams](using-admin-roles.md) 中详细了解 Teams 中的管理员角色，还可以阅读有关如何在 [Microsoft Teams cmdlet 参考](/powershell/teams/)中使用 PowerShell cmdlet 管理团队的详细信息。



## <a name="teams-overview-grid"></a>Teams 概述网格

团队管理工具位于 Microsoft Teams 管理中心的“**团队**”节点下。 （在管理中心，选择“**团队**” > “**管理团队**”。）每个团队都由 Microsoft 365 组提供支持，此节点提供了组织中已启用 Microsoft Teams 的组视图。

![Teams 概述网格屏幕截图](media/manage-teams-in-modern-portal-grid.png)  

网格显示以下属性：

- **团队名称**
- **频道** - 团队中所有频道的计数，包括默认常规频道。
- **团队成员** - 用户总数，包括租户的所有者、来宾和成员。
- **所有者** - 此团队的所有者计数。
- **来宾** - 属于此团队成员的 Azure Active Directory B2B 来宾用户计数。
- **隐私** - Microsoft 365 支持组的可见性/访问类型。
- **状态** - 此团队的“已存档”或“活动”状态。 在[存档或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)中详细了解如何存档团队。
- **说明** - Microsoft 365 支持组的说明。
- **分类** - 分配给 Microsoft 365 支持组的分类（如果在组织中使用）。 有关分类的详细信息，请参阅[为组织中的 Office 组创建分类](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)。
- **组 ID** - Microsoft 365 支持组的唯一组 ID。

> [!NOTE]
> 如果在网格中看不到所有这些属性，请单击“**编辑列**”图标。 在“**编辑列**”窗格中，可以使用开关打开或关闭网格中的列。 完成后，单击“**应用**”。

### <a name="add"></a>添加

若要添加新团队，请单击“**添加**”。 在“**添加新团队**”窗格中，为团队提供名称和说明，设置是将其设为私人团队还是公共团队，并设置分类。

> [!NOTE]
> 与 Outlook 等其他客户端的体验不同，新创建的团队可以立即在“Teams 管理中心”中管理。

### <a name="edit"></a>编辑

若要编辑组和团队特定设置，请单击团队名称左侧以选择组，然后选择“**编辑**”。

### <a name="archive"></a>存档

可以存档团队。 存档团队会使团队在 Teams 中进入只读模式。 管理员可以在管理中心代表组织存档和取消存档团队。 

### <a name="delete"></a>删除

删除团队是软删除团队和相应的 Microsoft 365 组。 若要还原错误删除的团队，请按照[还原删除的组](/microsoft-365/admin/create-groups/restore-deleted-group)中的说明进行操作。

### <a name="search"></a>搜索

搜索当前支持字符串“开头为”，并搜索“**团队名称**”字段。

## <a name="team-profile"></a>团队个人资料

可单击团队名称，从主要团队概述网格导航到任何团队的团队个人资料页面。 团队个人资料页面显示属于团队的成员、所有者和来宾（及其 Microsoft 365 支持组），以及团队的频道和设置。 在团队个人资料页面中，可以执行以下操作：

- 添加或删除成员和所有者。
- 添加或删除频道（请注意，不能删除常规频道）。
- 更改团队和组设置。
 
![示例团队个人资料屏幕截图](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a>对团队进行更改

在团队的个人资料页面上，可以更改团队的以下元素：

- **成员** - 添加或删除成员以及升级或降级所有者。
- **频道** - 添加新频道，编辑或删除现有频道。 请记住，不能删除默认常规频道。
- **团队名称**
- **说明**
- **隐私** - 设置团队是公共团队还是私人团队。
- **分类** - 这由 Microsoft 365 组分类提供支持。 选择“**机密**”、“**高度机密**”或“**常规**”。
- **对话设置** - 设置成员是否可以编辑和删除已发送的消息。
- **频道设置** - 设置成员是否可以创建新频道和编辑现有频道，以及添加、编辑和删除选项卡、连接器和应用。

对团队所做的更改将记录在日志中。 如果正修改组设置（更改名称、说明、照片、隐私、分类或团队成员），则这些更改将通过审核管道归于你名下。 如果正对 Teams 特定设置执行操作，则将在团队的“常规”频道中跟踪所做的更改并将其归于你名下。

## <a name="troubleshooting"></a>疑难解答

**问题：团队概述网格中缺少 Teams**

Teams 概述网格中的团队列表中缺少一些团队。

**原因**：当系统错误（或尚未）分析团队时会出现此问题，这可能导致团队缺少属性，无法被识别。

**解决方法：通过 MS Graph 手动将属性设置为正确的值**

使用 **“[Get-UnifiedGroup](/powershell/module/exchange/users-and-groups/get-unifiedgroup)”** cmdlet 将查询中相关实际组 ID 的 **{groupid}**（可通过 Exchange Online PowerShell 获取）替换为“**ExternalDirectoryObjectId**”属性。

1. 访问 [Graph 浏览器](https://developer.microsoft.com/graph/graph-explorer)。

2. 登录到左侧菜单上的 Graph 浏览器。

3. 将查询行更改为：PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}。

4. 在请求正文上添加以下值：{"resourceProvisioningOptions": ["Team"]}。

5. 在右上角运行查询。

6. 确认团队正确显示在“Microsoft Teams 管理中心 - 团队概述”中。

## <a name="learn-more"></a>了解详细信息

- [Teams cmdlet 参考](/powershell/teams/)  
- [使用 Teams 管理员角色管理 Teams](using-admin-roles.md)
- [在 Teams 中规划生命周期管理](plan-teams-lifecycle.md)
