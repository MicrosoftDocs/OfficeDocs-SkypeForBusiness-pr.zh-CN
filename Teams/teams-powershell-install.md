---
title: 安装 Microsoft Teams PowerShell
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 了解如何使用 PowerShell 控件管理 Microsoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 002f2bc8408536d79274c5e9b001f5e2a5eb55b3
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768333"
---
# <a name="install-microsoft-teams-powershell"></a>安装 Microsoft Teams PowerShell

本文介绍如何使用 [PowerShellGet](/powershell/scripting/gallery/installing-psget)安装 Microsoft Teams PowerShell 模块。 这些说明在 [Azure Cloud](/azure/cloud-shell/overview)Shell、Linux、macOS 和 Windows 平台上工作。

## <a name="requirements"></a>要求

Teams PowerShell 要求在所有平台上使用 PowerShell 5.1 或更高版本。 安装[适用于操作系统的最新版本的 PowerShell。](/powershell/scripting/install/installing-powershell)

> [!NOTE]
> 为获得最佳体验，建议使用 PowerShell 5.1。

## <a name="install-the-teams-powershell-module"></a>安装 Teams PowerShell 模块

> [!NOTE]
> 为获得最佳体验，请使用公开发布版 (GA) 公共预览版模块 - 而不是同时使用两者。 它们并非旨在协同工作。


使用 **PowerShellGet** cmdlet 安装 Teams PowerShell 模块。 为系统上的所有用户安装模块需要提升的权限。 使用在 Windows 中 **以管理员** 角色运行或在 macOS 或 Linux 上使用 命令启动 PowerShell `sudo` 会话：

```powershell
Install-Module MicrosoftTeams
```

默认情况下，PSGallery (PowerShell 库) 未配置为 **PowerShellGet** 的受信任存储库。 首次使用 PSGallery 时，会看到以下消息：

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

对 **"** 全部 **"回答"** 是"或"是"以继续安装。

## <a name="sign-in"></a>登录

若要开始使用 Teams PowerShell，请通过 Azure 凭据登录。

> [!NOTE]
> 如果你使用的是最新的 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)公共预览版 ，则不需要安装 Skype for Business Online 连接器。

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a>使用 MFA 和新式身份验证登录

 如果帐户使用多重身份验证，请使用本部分中的步骤。

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>
```

## <a name="update-teams-powershell"></a>更新 Teams PowerShell

若要更新 Teams PowerShell，请打开新的提升权限的 PowerShell 命令提示符并运行以下命令：

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> 如果 Teams PowerShell 已导入 PowerShell 会话，则更新模块将失败。 关闭 PowerShell，然后重新打开新的提升权限的 PowerShell 会话。


## <a name="uninstall-teams-powershell"></a>卸载 Teams PowerShell

若要卸载 Teams PowerShell，请打开新的提升权限的 PowerShell 命令提示符并运行以下命令：

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> 如果 Teams PowerShell 已导入 PowerShell 会话，卸载模块将失败。 关闭 PowerShell，然后重新打开新的提升权限的 PowerShell 会话。

## <a name="install-teams-powershell-public-preview"></a>安装 Teams PowerShell 公共预览版

> [!NOTE]
> 如果你使用的是 Teams PowerShell 的公共预览版，我们强烈建议你首先卸载 Skype for Business Online 连接器。

为系统上的所有用户安装 Teams PowerShell 公共预览版模块需要提升的权限。 使用在 Windows 中 **以管理员** 角色运行或在 macOS 或 Linux 上使用 命令启动 PowerShell `sudo` 会话。

如果使用 PowerShell 5.1，必须事先更新 **PowerShellGet** 模块。 更新 **PowerShellGet** 后，关闭并重新打开提升权限的 PowerShell 会话，以确保加载最新的 **PowerShellGet。**

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

若要安装 Teams PowerShell 公共预览版，请运行下面的 PowerShell 命令。

> [!NOTE]
> 可以通过运行"Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"在 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 库或 PowerShell 中查找最新的预览版本

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="next-steps"></a>后续步骤

现在，可以使用 Teams PowerShell 管理 Teams。 请参阅 [使用 Teams PowerShell 管理 Teams](teams-powershell-managing-teams.md) 以开始。

## <a name="related-topics"></a>相关主题

[使用 Teams PowerShell 管理 Teams](teams-powershell-managing-teams.md)

[Teams PowerShell 发行说明](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet 参考](/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet 参考](/powershell/skype/intro?view=skype-ps)
