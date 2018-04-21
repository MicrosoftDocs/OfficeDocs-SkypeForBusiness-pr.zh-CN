---
title: 在 Microsoft Teams 中分配角色和权限
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
description: 了解如何在 Microsoft Teams 中分配团队所有者和成员角色，包括创建团队的权限。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e0c0e64dc4a112c6f2c9ded4c68b45eb0740b5f3
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
<a name="assign-roles-and-permissions-in-microsoft-teams"></a>在 Microsoft Teams 中分配角色和权限
===============================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

在 Microsoft Teams 中有两种角色：**所有者**和**成员**。 默认情况下，会为创建新团队的用户授予所有者状态。 如果团队是从现有 Office 365 组创建的，则将继承权限。

下表显示了所有者与成员之间的权限差异：

|  |团队所有者  |团队成员  |
|---------|---------|---------|
|**创建团队**     |是        |否         |
|**离开团队**     |是         |是         |
|**编辑团队名称/说明**      |是         |否         |
|**删除团队**      |是         |否         |
|**添加频道**      |是         |是*         |
|**编辑频道名称/说明**      |是         |是*         |
|**删除频道**      |是         |是*         |
|**添加成员**      |是**         |否         |
|**添加选项卡**      |是         |是*         |
|**添加连接器**      |是         |是*         |
|**添加聊天机器人**      |是         |是*         |
\* 所有者可以在团队级别关闭这些项，这样成员将无权访问相应项。

\*\*向团队添加成员后，所有者也可以将成员提升到所有者状态。 此外，所有者也可以将自己的状态降级为成员。



> [!NOTE]
> 所有者可以在“查看团队”选项中将其他成员设为所有者。 一个团队最多可以有 100 个所有者。 建议至少指定几个所有者以帮助管理团队；这样也可以防止当唯一的所有者离开贵组织时出现孤立的群组。 有关孤立群组的详细信息，请参阅[向孤立群组分配新所有者](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)。


<a name="permissions-to-create-teams"></a>创建团队的权限
---------------------------

默认情况下，在 Exchange Online 中有邮箱的所有用户都有权创建 Office 365 组，进而有权在 Microsoft Teams 中创建团队。 你可以通过向一组用户委派组创建和管理权限，更加严格地控制和限制新团队的创建，进而控制和限制新 Office 365 组的创建。

如果贵组织有意执行此操作，下面的说明概述了为此需要执行的任务。

1.  确定或创建一个安全组 (SG)，该安全组由拥有创建 Office 365 组的委派权限的用户组成。

    a.  **操作：** 在 Office 365 中设置一个安全组，以便你可以添加能够创建 Office 365 组的用户。

    b.  有关详细信息，请参阅[在 Office 365 管理中心中创建、编辑或删除安全组](https://support.office.com/article/Create-edit-or-delete-a-security-group-in-the-Office-365-admin-center-55c96b32-e086-4c9e-948b-a018b44510cb)。

2.  确认是否启用了允许用户创建组的公司范围的控制。

    a.  **操作：** 运行以下 PowerShell 脚本，并确认 UsersPermissiontoCreateGroupsEnabled 参数是否设置为 **True**。

    ```
    Connect-MsolService

    Get-MsolCompanyInformation
    ```

    b.  如果不为 True，请运行 Set-MsolCompanySettings cmdlet **以将其设置为 True**。
Set-MsolCompanySettings -UsersPermissionToCreateGroupsEnabled $True

    c. 有关详细信息，请参阅：[管理 Office 365 组创建](https://support.office.com/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-001&ad=US#checkclevelsettings)。

3.  配置 Office 365 组设置以仅允许标识的安全组有权创建组。

    a.  **操作：** 创建一个组设置对象，其中包含将为其分配创建组的委派权限的组的配置设置。 

    ```
    Connect-AzureAD

    $Template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b

    $Setting = $template.CreateDirectorySetting()

    $setting["EnableGroupCreation"] = "true"

    $setting["GroupCreationAllowedGroupId"] = "&lt;ObjectId of Group Allowed to Create Groups>"

    New-AzureADDirectorySetting -DirectorySetting $settings
    ```

    b. 有关详细信息，请参阅：[管理 Office 365 组创建](https://support.office.com/article/Manage-Office-365-Group-Creation-4c46c8cb-17d0-44b5-9776-005fced8e618?ui=en-US&rs=en-US&ad=US#step3)。


||||
|---------|---------|---------|
| ![决策点图标。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |决策点         |是否所有 Microsoft Teams 用户都将能够创建团队（建议）？         |
| ![后续步骤图标。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |后续步骤         |如果你需要限制可以创建团队的人员，请修改可以创建 Office 365 组的人员的默认权限         |
