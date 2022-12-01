---
title: 在 Microsoft Teams 中存档或删除团队
manager: serdars
ms.author: mikeplum
author: MikePlumleyMSFT
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: 本文介绍如何在 Microsoft Teams 中存档或永久删除团队。
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 79a9472286a7e08e8c6dce4c4f40d76b7e4f2b4e
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198964"
---
# <a name="archive-or-delete-a-team-in-microsoft-teams"></a>在 Microsoft Teams 中存档或删除团队

随着时间的推移，在 Microsoft Teams 中创建的团队可能不再使用，或者你可能希望在项目结束时存档或删除团队。 如果你是 Microsoft Teams 的管理员，请按照本文中的步骤进行操作，以存档或删除不再需要的团队。  (如果你是团队所有者，还可以 [存档团队](https://support.microsoft.com/office/dc161cfd-b328-440f-974b-5da5bd98b5a7)。) 

将团队存档时，该团队的所有活动都会停止。 存档团队还会存档团队中的专用频道及其关联的网站集。  但是，你仍然可以添加或删除成员以及更新角色，而且仍可查看标准和专用通道、文件和聊天中的所有团队活动。

删除团队时，标准频道和专用频道中的团队活动 (以及关联的网站集) 、文件和聊天也会被删除。

> [!IMPORTANT]
> 可以重新激活存档的团队，但无法直接还原已删除的团队。 应先考虑将团队存档并推迟删除，直至确定不再需要团队再进行删除操作。

## <a name="archive-a-team"></a>存档团队

请按照以下步骤将团队存档。 必须是 Teams 服务管理员才能管理这些策略。 请参阅 [Teams 管理员角色管理 Teams](./using-admin-roles.md) ，了解管理员角色和权限。

1. 在管理中心，选择“ **Teams**”。
2. 通过单击团队名称选择团队。
3. 选择“**存档**”。 此时将显示以下消息。

    ![Teams 存档消息的屏幕截图。](media/teams-archive-message.png)

4. 若要防止用户编辑与团队关联的 SharePoint 网站和 Wiki 选项卡中的内容，请选择“ **使 SharePoint 网站为团队成员只读**”。  (Teams 所有者仍可编辑此内容。) 
5. 选择“**存档**”以存档团队。 团队的状态将更改为 **“已存档**”，它将在位于团队列表底部的 **“隐藏团队** ”中暂时可用，并且旁边将添加一个表示已存档状态的小图标。 从 **“隐藏的团队”** 中删除后，它将在“**存档****”下的“管理团队”** 视图中可用。 若要查看和搜索已存档团队的内容，请在“ **存档** ”列表中选择其名称。

## <a name="make-an-archived-team-active"></a>激活已存档的团队

请按照以下步骤使已存档的团队再次处于活动状态。

1. 在管理中心，选择“ **Teams**”。
2. 通过单击团队名称选择团队。
3. 选择 **“还原**”。 团队的状态将更改为 **“活动**”。 请注意，它不会自动移回 **团队** 内部。

## <a name="delete-a-team"></a>删除团队

如果将来不再需要该团队，则可将其删除，而不是将其存档。 请按照以下步骤删除团队。

1. 在管理中心，选择“ **Teams**”。
2. 通过单击团队名称选择团队。
3. 选择“**删除**”。 此时将显示一条确认消息。
4. 选择“**删除**”以永久删除团队。

## <a name="restore-a-deleted-team"></a>还原已删除的团队

按照以下步骤通过还原与团队关联的 Microsoft 365 组来还原已删除的团队。 还原团队的 Microsoft 365 组可还原团队内容，包括选项卡、标准频道和专用频道及其关联的网站集。

默认情况下，已删除Microsoft 365 组保留 30 天。 这 30 天时间被称为“软删除”，因为还可以对组进行还原。 若要了解详细信息，请参阅 [还原已删除的组](/microsoft-365/admin/create-groups/restore-deleted-group)。

### <a name="install-the-azureadpreview-module"></a>安装 AzureADPreview 模块

1. 以管理员身份打开 Windows PowerShell。
2. 如果安装了早期版本的 AzureADPreview 模块或安装了 AzureAD 模块，请通过运行以下命令之一将其卸载：

    ```PowerShell
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```

3. 通过运行以下命令安装最新版本的 AzureADPreview 模块：

    ```PowerShell
    Install-Module AzureADPreview
    ```

### <a name="restore-the-deleted-microsoft-365-group"></a>还原已删除的 Microsoft 365 组

1. 通过运行以下命令连接到 Azure AD：

    ```PowerShell
    Connect-AzureAD
    ```

    提示登录时，请使用管理员帐户和密码登录。

1. 运行以下命令以显示 30 天保留期内的所有软删除Microsoft 365 组的列表。 如果有多个组，请使用 **-All $True** 参数。

    ```PowerShell
    Get-AzureADMSDeletedGroup
    ```

1. 找到要还原的组，然后记下 `Id`。
1. 运行以下命令以还原组，其中 `[Id]` 是组 ID。

    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```

1. 运行以下命令，验证组是否已成功还原，其中 `[Id]` 是组 ID。

    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    完成还原过程可能需要长达 24 小时，此后在 Teams 中将显示团队以及与团队关联的内容（包括选项卡和频道）。

## <a name="related-topics"></a>相关主题

- [存档或还原团队](https://support.microsoft.com/office/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)

