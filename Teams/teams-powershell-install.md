---
title: 安装 Microsoft 团队 PowerShell
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
description: 了解如何使用 PowerShell 控件管理 Microsoft 团队。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 849b22d09c79e97c5eaaeab4dee96b1d432970cb
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944082"
---
# <a name="install-microsoft-teams-powershell"></a>安装 Microsoft 团队 PowerShell

本文介绍如何使用[PowerShellGet](/powershell/scripting/gallery/installing-psget)安装 Microsoft 团队 PowerShell 模块。 这些说明适用于[Azure 云 Shell](/azure/cloud-shell/overview)、Linux、MacOS 和 Windows 平台。

## <a name="requirements"></a>要求

团队 PowerShell 在所有平台上使用 PowerShell 6.2.4 和更高版本。 Windows 上的 PowerShell 5.1 也支持它。 安装适用于你的操作系统的[最新版本的 PowerShell](/powershell/scripting/install/installing-powershell) 。 在 PowerShell 6.2.4 和更高版本上运行时，团队 PowerShell 没有其他要求。

> [!WARNING]
> PowerShell 7 和团队 PowerShell 存在已知问题。 为了获得最佳体验，我们建议使用 PowerShell 5.1。

## <a name="install-the-teams-powershell-module"></a>安装团队 PowerShell 模块

> [!NOTE]
> 为获得最佳体验，请使用常规可用性（GA）或公共预览版模块（不是两者）。 它们不打算协同工作。


使用**PowerShellGet** Cmdlet 安装团队 PowerShell 模块。 为系统上的所有用户安装模块需要提升的权限。 使用 Windows 中的 "以**管理员身份运行**" 或使用 `sudo` macOS 或 Linux 上的命令启动 PowerShell 会话：

```powershell
Install-Module MicrosoftTeams
```

默认情况下，PowerShell 库（PSGallery）未配置为**PowerShellGet**的受信任存储库。 首次使用 PSGallery 时，您将看到以下消息：

```output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

回答 `Yes` 或 `Yes to All` 继续安装。


## <a name="install-teams-powershell-public-preview"></a>安装团队 PowerShell 公共预览版

> [!NOTE]
> 如果你使用的是团队 PowerShell 的公共预览版，我们强烈建议你首先卸载 Skype for Business Online 连接器。

为系统上的所有用户安装团队 PowerShell 公共预览版模块需要提升的权限。 使用 Windows 中的 "以**管理员身份运行**" 或使用 `sudo` macOS 或 Linux 上的命令启动 PowerShell 会话。

如果您使用的是 PowerShell 5.1，则必须事先更新**PowerShellGet**模块。 更新**PowerShellGet**后，关闭并重新打开提升的 PowerShell 会话，以确保加载最新的**PowerShellGet** 。

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

若要安装团队 Powershell 公共预览版，请运行以下 PowerShell 命令。

```powershell
Install-Module MicrosoftTeams -AllowPrerelease
```

## <a name="install-the-skype-for-business-online-connector"></a>安装 Skype for Business Online 连接器

> [!WARNING]
> Skype for Business Online 连接器目前是团队 PowerShell 公共预览版的一部分。 将此功能汇总到团队 PowerShell 的 GA 版本后，Skype for Business Online 连接器将不再可用。

下载并安装[Skype for Business PowerShell 模块](https://www.microsoft.com/download/details.aspx?id=39366)，然后在 PowerShell 中运行以下内容。

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a>登录

若要开始使用团队 PowerShell，请使用你的 Azure 凭据登录。

> [!NOTE]
> 如果您使用的是最新的[团队 PowerShell 公共预览版](https://www.powershellgallery.com/packages/MicrosoftTeams/)，则无需安装 Skype For Business Online 连接器。

```powershell
$credential = Get-Credentials

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credentials $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credentials $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>更新团队 PowerShell

若要更新团队 PowerShell，请打开新的提升的 PowerShell 命令提示符，然后运行以下命令：

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> 如果团队 PowerShell 已导入到你的 PowerShell 会话中，更新模块将失败。 关闭 PowerShell 并重新打开一个新的已提升的 PowerShell 会话。


## <a name="uninstall-teams-powershell"></a>卸载团队 PowerShell



若要卸载团队 PowerShell，请打开新的提升的 PowerShell 命令提示符，然后运行以下命令：

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> 如果团队 PowerShell 已导入你的 PowerShell 会话，则卸载该模块将失败。 关闭 PowerShell 并重新打开一个新的已提升的 PowerShell 会话。

## <a name="next-steps"></a>后续步骤

现在，你已准备好使用团队 PowerShell 管理团队。 请参阅[使用团队 PowerShell 管理团队](teams-powershell-managing-teams.md)以开始使用。

## <a name="related-topics"></a>相关主题

[通过团队 PowerShell 管理团队](teams-powershell-managing-teams.md)

[团队 PowerShell 发行说明](teams-powershell-release-notes.md)

[Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet 参考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
