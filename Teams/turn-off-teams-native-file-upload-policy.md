---
title: 关闭 Teams 本机文件上传策略
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: 了解如何使用 PowerShell 创建、设置、分配和调整 Teams 文件策略。
audience: admin
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
ms.openlocfilehash: 6c7d5c89c780fa5c9286f5d7f7d2304f2e6c6220
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198524"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>关闭 Teams 本机文件上传策略

Microsoft Teams 使用 OneDrive 和 SharePoint 来存储和共享内容，但某些组织和用户可能更喜欢使用第三方存储提供程序。  

如果你的组织为内容存储选择第三方，则需要关闭 `NativeFileEntryPoints` Teams 文件策略中的 参数。 默认情况下，此参数处于启用状态，显示将内容从 OneDrive 或 SharePoint 上传到 Teams 聊天或频道的选项。

本文将帮助你使用 PowerShell 创建、设置、分配和删除 `NativeFileEntryPoints` 参数。

>[!NOTE]
>关闭 Teams 文件策略后，用户在 Teams 中看不到 OneDrive 和 SharePoint 的接入点，但创建新团队和频道将继续触发匹配 SharePoint 库的生成。

## <a name="prepare-to-update-the-teams-files-policy"></a>准备更新 Teams 文件策略

### <a name="set-up-microsoft-powershell"></a>Microsoft PowerShell 设置

目前，无法在 Teams 管理中心中更改此策略。 组织的Microsoft 365 租户管理员必须使用本文稍后详述的 PowerShell cmdlet 进行更改。

阅读安装 Microsoft Teams PowerShell 模块，了解如何使用 PowerShell 库 [安装 PowerShell Teams 模块](teams-powershell-install.md)。

若要安装或下载 Teams PowerShell 模块，请参阅[适用于 Microsoft Teams 的 PowerShell 库](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0)。

有关如何为 Teams 管理设置 PowerShell 的详细信息，请参阅[使用 Microsoft Teams PowerShell 管理 Teams](teams-powershell-managing-teams.md)。

### <a name="allow-third-party-apps-in-teams-admin-center"></a>在 Teams 管理员中心允许第三方应用

更改 Teams 文件策略不需要此步骤，但当你准备好将第三方存储提供程序集成到用户的 Teams 体验中时，此步骤是必需的。

Microsoft 365 租户管理员需要在 Teams 管理中心启用“允许第三方应用”策略。

若要了解如何允许第三方应用或自定义应用，请参阅在 [Microsoft Teams 管理中心管理应用中的管理](/microsoftteams/manage-apps#manage-org-wide-app-settings)组织范围应用设置。

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>关闭整个租户的 NativeFileEntryPoints

将 `-Identity` 参数设置为 `Global` 会将策略设置应用于组织中的所有用户。

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>整个租户的示例 PowerShell 策略 cmdlet

此示例 PowerShell 命令将整个租户的参数`NativeFileEntryPoints``Disabled`设置为 。

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>检查租户的状态  

若要查看租户的 Teams 文件策略的当前状态，请使用 `Get-CsTeamsFilesPolicy` cmdlet。

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>打开或关闭本机文件上传点

若要打开或关闭整个租户的本机文件上传点，请将 `NativeFileEntryPoints` 参数设置为 `Enabled` 或 `Disabled`。

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>删除用户的策略

若要删除用户的 Teams 文件策略，请使用 `Remove-CsTeamsFilesPolicy` cmdlet。

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>为特定用户关闭 NativeFileEntryPoints

还可以通过创建新的 Teams 文件策略字符串并将新创建的策略分配给用户，为特定用户更新 Teams 文件策略 `-Identity` 。

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>特定用户的示例 PowerShell 策略 cmdlet

此示例 PowerShell 命令将创建名为 且`NativeFileEntryPoints`参数设置为 `Disabled`的新`-Identity``CsTeamsFilesPolicy`。`UserPolicy`

当用户使用 `-Identity UserPolicy`分配`CsTeamsFilesPolicy`时，其本机文件入口点将被关闭。

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>向用户分配策略

创建新策略后，可以使用 cmdlet 将该策略分配给用户 `Grant-CsTeamsFilesPolicy` 。

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>更新策略

如果需要更改新的 Teams 文件策略 `UserPolicy`的设置，请使用 `Set-CsTeamsFilePolicy` cmdlet。

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>删除用户完整列表的策略

若要从分配到 Teams 文件策略 的所有用户中删除策略 `UserPolicy`，请使用 `Remove-CsTeamsFilesPolicy` cmdlet。

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> 对策略进行更改后，最多需要 12 小时才能在用户的 Teams 客户端中显示更改。
