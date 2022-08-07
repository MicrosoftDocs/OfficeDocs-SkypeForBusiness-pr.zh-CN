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
ms.collection:
- M365-collaboration
ms.openlocfilehash: 1993371099d0712d21106987f21575e85e181ad7
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268924"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>关闭 Teams 本机文件上传策略

Microsoft Teams 使用 OneDrive 和 SharePoint 来存储和共享内容，但某些组织和用户可能更愿意使用第三方存储提供程序。  

如果组织为内容存储选择第三方，则需要关闭 `NativeFileEntryPoints` Teams 文件策略中的参数。 默认情况下启用此参数，显示将内容从 OneDrive 或 SharePoint 上传到 Teams 聊天或频道的选项。

本文将帮助你使用 PowerShell 创建、设置、分配和删除 `NativeFileEntryPoints` 参数。

>[!NOTE]
>关闭 Teams 文件策略后，用户将看不到 Teams 中 OneDrive 和 SharePoint 的访问点，但新团队和频道的创建将继续触发匹配的 SharePoint 库的生成。

## <a name="prepare-to-update-the-teams-files-policy"></a>准备更新 Teams 文件策略

### <a name="set-up-microsoft-powershell"></a>设置 Microsoft PowerShell

目前，无法在 Teams 管理中心更改此策略。 贵组织的 Microsoft 365 租户管理员必须使用本文后面详述的 PowerShell cmdlet 进行更改。

了解如何通过阅读“[安装 Microsoft Teams PowerShell 模块”，使用PowerShell 库安装 PowerShell Teams 模块](teams-powershell-install.md)。

若要安装或下载 Teams PowerShell 模块，请[参阅适用于 Microsoft Teams 的PowerShell 库](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0)。

有关如何为 Teams 管理设置 PowerShell 的详细信息，请参阅 [使用 Microsoft Teams PowerShell 管理 Teams](teams-powershell-managing-teams.md)。

### <a name="allow-third-party-apps-in-teams-admin-center"></a>在 Teams 管理员中心中允许第三方应用

此步骤不是更改 Teams 文件策略所必需的，但在准备好将第三方存储提供程序集成到用户的 Teams 体验中时，需要执行此步骤。

Microsoft 365 租户管理员需要在 Teams 管理中心启用“允许第三方应用”策略。

若要了解如何允许第三方或自定义应用，请参阅 [Microsoft Teams 管理中心管理应用中的](/microsoftteams/manage-apps#manage-org-wide-app-settings)组织范围的应用设置。

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>为整个租户关闭 NativeFileEntryPoints

`-Identity`将参数设置为`Global`将策略设置应用于组织中的所有用户。

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>适用于整个租户的示例 PowerShell 策略 cmdlet

此示例 PowerShell 命令将参数`Disabled`设置`NativeFileEntryPoints`为整个租户。

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>检查租户的状态  

若要查看租户的 Teams 文件策略的当前状态，请使用 `Get-CsTeamsFilesPolicy` cmdlet。

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>打开或关闭本机文件上传点

若要为整个租户打开或关闭本机文件上传点，请将参数设置`NativeFileEntryPoints`为或`Enabled``Disabled`。

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

还可以通过创建新的 Teams 文件策略 `-Identity` 字符串并将新创建的策略分配给用户来更新特定用户的 Teams 文件策略。

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>特定用户的示例 PowerShell 策略 cmdlet

此示例 PowerShell 命令将创建一个命名为和参数设置为`Disabled`的新`CsTeamsFilesPolicy``-Identity`。`NativeFileEntryPoints` `UserPolicy`

为用户分配`CsTeamsFilesPolicy``-Identity UserPolicy`用户时，将关闭其本机文件入口点。

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>向用户分配策略

创建新策略后，可以使用 `Grant-CsTeamsFilesPolicy` 该 cmdlet 将该策略分配给用户。

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>更新策略

如果需要更改新 Teams 文件 `UserPolicy`策略的设置，请使用 `Set-CsTeamsFilePolicy` 该 cmdlet。

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>删除用户完整列表的策略

若要从分配给 Teams 文件策略 `UserPolicy`的所有用户中删除策略，请使用 `Remove-CsTeamsFilesPolicy` cmdlet。

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> 对策略进行更改后，最多允许 12 小时的更改显示在用户的 Teams 客户端中。
