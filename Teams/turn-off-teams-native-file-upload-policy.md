---
title: 关闭Teams本机文件Upload策略
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: 了解如何使用 PowerShell 创建、设置、分配和Teams文件策略。
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64bd9d23527ef1a63df4f258e89de5e60862a878
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2022
ms.locfileid: "62192483"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>关闭Teams本机文件Upload策略

Microsoft Teams使用 OneDrive SharePoint (ODSP) 存储和共享内容，但某些组织和用户可能希望使用第三方存储提供程序。  

如果你的组织为内容存储选择第三方，则需要在"文件"策略中Teams ``NativeFileEntryPoints`` 参数。 默认启用此参数，显示将内容从 ODSP 上传到聊天或Teams的选项。

本文将帮助你使用 PowerShell 创建、设置、分配和 ``NativeFileEntryPoints`` 删除 参数。

>[!NOTE]
>关闭 Teams 文件策略后，用户在 Teams 中不会看到 OneDrive 和 SharePoint (ODSP) 的访问点，但新团队和频道的创建将继续触发生成匹配的 SharePoint 库。

## <a name="prepare-to-update-the-teams-files-policy"></a>准备更新 Teams 文件策略

### <a name="set-up-microsoft-powershell"></a>设置 Microsoft PowerShell

目前，此策略在管理中心Teams更改。 组织的租户管理员Microsoft 365使用本文稍后详细介绍的 PowerShell cmdlet 进行更改。

阅读安装 PowerShell 模块Teams，了解如何使用[PowerShell 库Microsoft Teams PowerShell 模块](teams-powershell-install.md)。

若要安装或下载 Teams PowerShell 模块，请参阅[PowerShell 库Microsoft Teams。](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0)

若要详细了解如何设置 PowerShell Teams管理，请参阅[使用 Teams PowerShell Microsoft Teams管理](teams-powershell-managing-teams.md)。

### <a name="allow-third-party-apps-in-teams-admin-center"></a>允许管理中心Teams第三方应用

无需此步骤即可更改 Teams 文件策略，但准备好将第三方存储提供程序集成到用户的 Teams 体验时，需要执行此步骤。

你的Microsoft 365管理员需要在管理中心启用"允许第三方应用"Teams策略。

若要了解如何允许第三方或自定义应用，请参阅在管理中心管理应用中管理组织Microsoft Teams[设置](/microsoftteams/manage-apps#manage-org-wide-app-settings)。

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>关闭整个租户的 NativeFileEntryPoints

将 ``-Identity`` 参数设置为 ``Global`` 会向组织中所有用户应用策略设置。

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>整个租户的示例 PowerShell 策略 cmdlet

此示例 PowerShell 命令将整个 ``NativeFileEntryPoints`` 租户的 参数 ``Disabled`` 设置为 。

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>检查租户的状态  

若要查看租户的"文件"策略Teams状态，请使用 ``Get-CsTeamsFilesPolicy`` cmdlet。

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>打开或关闭本机文件上传点

若要打开或关闭整个租户的本机文件上传点，将 ``NativeFileEntryPoints`` 参数设置为 ``Enabled`` 或 ``Disabled`` 。

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>删除用户的策略

若要删除Teams文件策略，请使用 ``Remove-CsTeamsFilesPolicy`` cmdlet。

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>为特定用户关闭 NativeFileEntryPoints

也可通过创建新的 Teams 文件策略字符串并将新创建的策略分配给用户，来更新特定用户的 Teams ``-Identity`` 文件策略。

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>特定用户的示例 PowerShell 策略 cmdlet

此示例 PowerShell 命令将创建一个新的 ，其 ``CsTeamsFilesPolicy`` ``-Identity`` 名为 ， ``UserPolicy`` 参数设置为 ``NativeFileEntryPoints`` ``Disabled`` 。

为用户分配 时， ``CsTeamsFilesPolicy`` ``-Identity UserPolicy`` 其本机文件入口点将关闭。

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>向用户分配策略

创建新策略后，可以使用 cmdlet 将策略分配给 ``Grant-CsTeamsFilesPolicy`` 用户。

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>更新策略

如果需要更改新文件策略Teams设置 ``UserPolicy`` ，请使用 ``Set-CsTeamsFilePolicy`` cmdlet。

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>删除用户完整列表的策略

若要从分配到文件策略的所有用户中删除Teams策略， ``UserPolicy`` 请使用 ``Remove-CsTeamsFilesPolicy`` cmdlet。

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> 更改策略后，最多允许 12 小时更改显示在用户的客户端Teams中。
