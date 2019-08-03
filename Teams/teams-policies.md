---
title: 管理 Microsoft 团队中的团队策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理组织中的团队策略, 以控制用户可在团队和频道中执行的操作。
f1keywords:
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 243492b5429e34d42f6dd452e5fcf04a957cafd2
ms.sourcegitcommit: 7ae59d1091ea086b7253c1d8ce85c28fabc5537a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/02/2019
ms.locfileid: "36166309"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>管理 Microsoft 团队中的团队策略

作为管理员, 你可以使用 Microsoft 团队中的团队策略控制你的组织中的哪些用户可以在团队和频道中执行的操作。 例如, 你可以设置是否允许用户在搜索结果和团队库中发现专用团队以及是否允许用户创建专用频道。

可在 Microsoft 团队管理中心中管理团队策略。 你可以使用全局 (组织范围默认) 策略或创建自定义策略并将其分配给用户。 除非你创建并分配自定义策略, 否则你组织中的用户将自动获取全局策略。

你可以编辑全局策略, 也可以创建并分配自定义策略。 如果向用户分配了自定义策略, 则该策略将应用于用户。 如果未向用户分配自定义策略, 则全局策略将应用于该用户。 编辑全局策略或分配策略后, 所做的更改可能需要长达24小时才能生效。

## <a name="create-a-custom-teams-policy"></a>创建自定义团队策略

1. 在 Microsoft 团队管理中心的左侧导航中, 转到 "**团队** > **团队策略**"。
2. 单击“添加”****。
3. 输入策略的名称和说明。

    ![团队策略设置的屏幕截图](media/teams-policies.png)
4. 选择所需的设置:

- [**发现专用团队**](https://docs.microsoft.com/MicrosoftTeams/teams-policies#discoverteams): 启用此设置可允许用户在搜索结果和团队库中发现个人团队。
- [**创建专用通道**](https://docs.microsoft.com/MicrosoftTeams/teams-policies#createchannels): 启用此设置可允许用户创建专用频道。

5. 单击“**保存**”。

## <a name="edit-a-teams-policy"></a>编辑团队策略

你可以编辑全局策略或你创建的任何自定义策略。

1. 在 Microsoft 团队管理中心的左侧导航中, 转到 "**团队** > **团队策略**"。
2. 通过单击策略名称左侧, 然后单击 "**编辑**", 选择策略。
3. 打开或关闭所需设置, 然后单击 "**保存**"。

## <a name="assign-a-custom-teams-policy-to-users"></a>向用户分配自定义团队策略

你可以使用 Microsoft 团队管理中心将自定义策略分配给一个或多个用户或 Skype for business PowerShell 模块, 以便为用户组 (如安全组或通讯组) 分配自定义策略。

### <a name="assign-a-custom-teams-policy-to-a-user"></a>向用户分配自定义团队策略

1. 在 Microsoft 团队管理中心的左侧导航中, 转到 "**用户**", 然后单击 "用户"。
2. 单击 "**策略**", 然后单击 "**分配的策略**" 旁边的 "**编辑**"。
3. 在 "**团队策略**" 下, 选择要分配的策略, 然后单击 "**保存**"。

若要一次为多个用户分配自定义团队策略, 请参阅[批量编辑团队用户设置](edit-user-settings-in-bulk.md)。

或者, 您也可以执行以下操作:

1. 在 Microsoft 团队管理中心的左侧导航中, 转到 "**团队** > **团队策略**"。
2. 通过单击策略名称的左侧, 选择策略。
3. 选择 "**管理用户**"。
4. 在 "**管理用户**" 窗格中, 按 "显示名称" 或 "按用户名搜索用户", 选择名称, 然后选择 "**添加**"。 对要添加的每个用户重复此步骤。
5. 添加完用户后, 单击 "**保存**"。

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a>向组中的用户分配自定义团队策略

你可能需要向已标识的多个用户分配自定义团队策略。 例如, 你可能想要向安全组中的所有用户分配策略。 你可以通过连接到 Azure Active Directory PowerShell for Graph 模块和 Skype for Business PowerShell 模块来执行此操作。 有关使用 PowerShell 管理团队的详细信息, 请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。

在此示例中, 我们将名为 "市场营销团队" 策略的团队策略分配给 "Contoso 市场营销" 组中的所有用户。  

> [!NOTE]
> 请按照[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤, 确保首先连接到用于 Graph 模块和 Skype For business powershell 模块的 Azure Active Directory powershell。

获取特定组的 GroupObjectId。
```
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
获取指定组的成员。
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
将组中的所有用户分配到特定团队策略。 在此示例中, 它是市场营销团队政策。
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.EmailAddress}
``` 
此命令可能需要几分钟才能执行, 具体取决于组中的成员数量。

## <a name="related-topics"></a>相关主题

- [在 Teams 中管理私人团队的发现](manage-discovery-of-private-teams.md)
