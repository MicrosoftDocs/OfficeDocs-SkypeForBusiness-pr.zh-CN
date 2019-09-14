---
title: 在 Microsoft Teams 中存档或删除团队
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: 了解如何存档或永久删除团队。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cdbc5a03698fc5aa8cd7d686ad0c3038132236f1
ms.sourcegitcommit: 21ef0846c8d9bc986550d34614bae1cb9eb2ded8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2019
ms.locfileid: "36980571"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a>在 Microsoft Teams 中存档或删除团队
===========================================

随着时间的推移，在 Microsoft 团队中创建的团队可能无法使用，或者你可能希望在项目结束时存档或删除团队。 如果你是 Microsoft 团队管理员，请按照本文中的步骤存档或删除不再需要的团队。 存档团队时，该团队的所有活动将停止，但你仍可以添加或删除成员和更新角色，但仍可以查看频道、文件和聊天中的所有团队活动。 删除团队时，也会删除关联频道、文件和聊天中的团队活动。

> [!IMPORTANT]
> 已存档的团队可以重新激活，但不能直接撤消删除已删除的团队。 请考虑先存档团队，然后推迟删除，直到确定不再需要团队。

## <a name="archive-a-team"></a>存档团队

请按照以下步骤存档团队。

1. 在 "Microsoft 团队管理中心" 中，选择 "**团队**"。
2. 通过单击团队名称选择团队。
3. 选择 "**存档**"。 将显示以下消息。

    ![工作组档案邮件的屏幕截图](media/teams-archive-message.png)

4. 如果要为团队的 SharePoint 网站设置为只读，请选中该复选框。
5. 选择 "**存档**" 以存档团队。 团队的状态将更改为 "已**存档**"。

## <a name="make-an-archived-team-active"></a>使已存档的团队处于活动状态

请按照以下步骤使已存档的团队再次处于活动状态。

1. 在 "Microsoft 团队管理中心" 中，选择 "**团队**"。
2. 通过单击团队名称选择团队。
3. 选择 " **Unarchive**"。 团队的状态将更改为 "**活动**"。

## <a name="delete-a-team"></a>删除团队

如果将来不再需要该团队，则可以删除它，而不是将其存档。 请按照以下步骤删除团队。

1.  在 "Microsoft 团队管理中心" 中，选择 "**团队**"。
2.  通过单击团队名称选择团队。
3.  选择 "**删除**"。 将显示一条确认消息。
4.  选择 "**删除**" 以永久删除团队。

## <a name="restore-a-deleted-team"></a>还原已删除的团队

通过还原与团队关联的 Office 365 组，请按照以下步骤还原已删除的团队。 默认情况下，已删除的 Office 365 组将保留30天。 此30天期限称为 "软删除"，因为你可以还原组。 若要了解详细信息，请参阅[还原已删除的 Office 365 组](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group)。

### <a name="install-the-azureadpreview-module"></a>安装 AzureADPreview 模块

1. 以管理员身份打开 Windows PowerShell。
2. 如果安装了早期版本的 AzureADPreview 模块或安装了 AzureAD 模块，请通过运行下列操作之一将其卸载：

    ``` 
    Uninstall-Module AzureADPreview
    ```

    ```
    Uninstall-Module AzureAD
    ```
3. 通过运行以下内容安装最新版本的 AzureADPreview 模块：

    ```
    Install-Module AzureADPreview
    ```    

### <a name="restore-the-deleted-office-365-group"></a>还原已删除的 Office 365 组

1. 通过运行以下内容连接到 Azure AD：
    ```
    Connect-AzureAD
    ```
    出现提示时，请使用管理员帐户和密码登录。  
2. 运行以下操作以显示仍在30天保留期内的所有软删除 Office 365 组的列表。 如果你有大量的组，请使用 **-All $True**参数。
    ```
    Get-AzureADMSDeletedGroup
    ``` 
3. 找到要还原的组，然后记下该 Id。
4. 运行以下操作以还原组，其中 [Id] 是组 Id。
    ```
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  运行以下操作以验证组是否已成功还原，其中 [Id] 是组 Id。
    ```
    Get-AzureADGroup -ObjectId [Id]
    ```

    完成还原过程最多需要24小时，之后团队中将显示与团队相关联的团队和内容，包括选项卡和频道。
