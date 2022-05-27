---
title: 安装Microsoft Teams PowerShell
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
description: 了解如何使用 PowerShell 控件来管理Microsoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58d64a64fd7c9714e84042e4e1aa1be3eb4505db
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65682003"
---
# <a name="install-microsoft-teams-powershell-module"></a>安装Microsoft Teams PowerShell 模块

本文介绍如何使用 PowerShell 库 安装 Microsoft Teams PowerShell 模块。 所有Windows平台都支持Microsoft Teams PowerShell 模块。 不支持 Mac 和 Linux。

## <a name="requirements"></a>要求

Microsoft Teams PowerShell 模块要求在所有平台上使用 PowerShell 5.1 或更高版本。 安装适用于操作系统 [的最新版本的 PowerShell](/powershell/scripting/install/installing-powershell) 。

若要检查 PowerShell 版本，请在 PowerShell 会话中运行以下命令：

```powershell
$PSVersionTable.PSVersion
```

建议使用Install-Module cmdlet 安装 Microsoft Teams PowerShell 模块。

如果 PowerShell 库 (PSGallery) 未配置为 **PowerShellGet** 的受信任存储库，则首次使用 PSGallery 时会看到以下消息：

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

回答 **“是** ”或 **“是** ”以继续安装。

## <a name="installing-using-the-powershellgallery"></a>使用 PowerShellGallery 进行安装

Microsoft Teams PowerShell 模块目前支持用于 Windows 上的 PowerShell 5.1。 按照以下步骤安装模块：

- 更新到 [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell)。 如果使用的是 Windows 10 版本 1607 或更高版本，则已安装 PowerShell 5.1。
- [安装.NET Framework 4.7.2](/dotnet/framework/install) 或更高版本。
- 运行以下命令以安装最新的 PowerShellGet：

  ```powershell
  Install-Module -Name PowerShellGet -Force -AllowClobber
  ```

- 安装Teams PowerShell 模块。

  ```powershell
  Install-Module -Name MicrosoftTeams -Force -AllowClobber
  ```

## <a name="offline-installation"></a>脱机安装

在某些环境中，无法连接到PowerShell 库。 在这些情况下，请执行以下 [手动安装步骤](https://aka.ms/psgallery-manualdownload)。

## <a name="sign-in"></a>登录

若要开始使用 Microsoft Teams PowerShell 模块，请使用 Azure 凭据登录。

```PowerShell
Connect-MicrosoftTeams
```

## <a name="update-teams-powershell-module"></a>更新 Teams PowerShell 模块

若要更新任何 PowerShell 模块，应使用用于安装模块的相同方法。 例如，如果最初使用 Install-Module，则应使用 [Update-Module](/powershell/module/powershellget/update-module) 获取最新版本。

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> 如果已将 Teams PowerShell 导入到 PowerShell 会话中，则更新模块将失败。 关闭 PowerShell 并重新打开新的提升的 PowerShell 会话。

## <a name="uninstall-teams-powershell"></a>卸载 Teams PowerShell

若要卸载 Microsoft Teams PowerShell，请打开新的 PowerShell 命令提示符并运行以下命令：

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions
```

## <a name="next-steps"></a>后续步骤

现在，可以使用 Microsoft Teams PowerShell 管理Microsoft Teams了。 请参阅[使用 Teams PowerShell 管理Teams](teams-powershell-managing-teams.md)以入门。

## <a name="related-topics"></a>相关主题

[使用 Teams PowerShell 管理Teams](teams-powershell-managing-teams.md)

[Teams PowerShell 发行说明](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet 参考](/powershell/teams/)

[Skype for Business cmdlet 参考](/powershell/skype/intro)
