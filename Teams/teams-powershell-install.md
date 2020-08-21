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
ms.openlocfilehash: 966dd62a9917c616c53fc57e13ca468e64acf218
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824933"
---
# <a name="install-microsoft-teams-powershell"></a>安装 Microsoft Teams PowerShell

本文介绍如何使用 [PowerShellGet](/powershell/scripting/gallery/installing-psget)安装 Microsoft Teams PowerShell 模块。 这些说明适用于 Azure 云 Shell、Linux、macOS 和 Windows 平台。 [Azure Cloud Shell](/azure/cloud-shell/overview)

## <a name="requirements"></a>要求

Teams PowerShell 要求所有平台上使用 PowerShell 5.1 或更高版本。 安装[适用于你的操作系统的最新版 PowerShell。](/powershell/scripting/install/installing-powershell)

> [!WARNING]
> PowerShell 7 和 Teams PowerShell 存在已知问题。 为获得最佳体验，我们建议使用 PowerShell 5.1。

## <a name="install-the-teams-powershell-module"></a>安装 Teams PowerShell 模块

> [!NOTE]
> 为了获得最佳体验，请使用 GA 或公 (共) 体中的) 功能，而不是使用两者都可使用。 这些按钮不要协同工作。


使用 **PowerShellGet** cmdlet 安装 Teams PowerShell 模块。 为系统上的所有用户安装模块需要具有提升的权限。 使用 Windows 中的"以管理员身份 **运行"启动** PowerShell 会话，或在 `sudo` macOS 或 Linux 上使用命令：

```powershell
Install-Module MicrosoftTeams
```

默认情况下，PowerShell (库管理器与 **powerShellGet**的受) 信任存储库而未配置为受信任的存储库。 首次使用 PSGallery 时，您会看到以下消息：

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

对所有年**的解****答或是**"是"以继续安装。


## <a name="install-teams-powershell-public-preview"></a>安装 Teams PowerShell 公共预览

> [!NOTE]
> 如果你使用的是 Teams PowerShell 的公共预览版，我们强烈建议首先卸载 Skype for Business Online Connector。

为系统上的所有用户安装 Teams PowerShell 公共预览版模块需要提升的权限。 使用 Windows 中的"以管理员身份 **运行"启动** PowerShell 会话，或在 `sudo` macOS 或 Linux 上使用命令。

如果使用 PowerShell 5.1，则必须提前更新 **PowerShellGet** 模块。 更新**PowerShellGet**后，请关闭并重新打开提级的 PowerShell 会话，以确保加载最新的**PowerShellGet。**

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

若要安装 Teams PowerShell 公共预览版，请运行以下 PowerShell 命令。

> [!NOTE]
> 可通过运行"查找模块 -AllowPrerelease"，在 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 库或 PowerShell 中找到最新预览版本

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.3-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a>安装 Skype for Business Online Connector

> [!WARNING]
> Skype for Business Online 连接器当前是 Teams PowerShell 公共预览版的一部分。 在我们将此功能推出到 Teams PowerShell 的 GA 版本中后，Skype for Business Online 连接器将不再可用。

下载并安装 [Skype for Business PowerShell 模块](https://www.microsoft.com/download/details.aspx?id=39366)，然后在 PowerShell 中运行以下内容。

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a>登录

要开始使用 Teams PowerShell，请使用 Azure 凭据登录。

> [!NOTE]
> 如果你使用的是最新的 Teams [PowerShell 公共预览版](https://www.powershellgallery.com/packages/MicrosoftTeams/)，则无需安装 Skype for Business Online Connector。

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>更新 Teams PowerShell

若要更新 Teams PowerShell，请打开一个新的增强的 PowerShell 命令提示符，并运行以下命令：

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> 如果已将 Teams PowerShell 导入 PowerShell 会话中，更新模块将失败。 关闭 PowerShell 并重新打开一个新的提级 PowerShell 会话。


## <a name="uninstall-teams-powershell"></a>卸载 Teams PowerShell



若要卸载 Teams PowerShell，请打开一个新的增强的 PowerShell 命令提示符，并运行以下命令：

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> 如果已将 Teams PowerShell 导入 PowerShell 会话中，则卸载模块将失败。 关闭 PowerShell 并重新打开一个新的提级 PowerShell 会话。

## <a name="next-steps"></a>后续步骤

现在，你就可以使用 Teams PowerShell 管理 Teams。 请参阅 [使用 Teams 和 Teams PowerShell 管理 Teams](teams-powershell-managing-teams.md) 以开始使用。

## <a name="related-topics"></a>相关主题

[使用 Teams PowerShell 管理 Teams](teams-powershell-managing-teams.md)

[Teams PowerShell 发行说明](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet 参考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
