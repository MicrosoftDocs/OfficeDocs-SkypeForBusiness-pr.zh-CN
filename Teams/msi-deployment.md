---
title: 通过 Microsoft Endpoint Configuration Manager 使用 MSI 安装 Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 管理员可以使用 Teams MSI 批量部署 Microsoft Teams 来选择用户或计算机。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c048e321241f4403fbb69f71e56b3fc179346951
ms.sourcegitcommit: c16451519e05b47bbb77e09dacd13ff212617e91
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "42327824"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a>使用 Microsoft Endpoint Configuration Manager 安装 Microsoft Teams

> [!Tip]
> 观看以下会话以了解 Windows 桌面客户端的优势，如何规划它，以及如何部署它：[Teams Windows 桌面客户端](https://aka.ms/teams-clients)

为了使用 Microsoft Endpoint Configuration Manager 或组策略或任何第三方分发机制以进行广泛部署，Microsoft 提供了 MSI 文件（32 位和 64 位），供管理员用于将 Teams 批量部署至选定的用户或计算机。 管理员可以使用这些文件远程部署 Teams，使用户无需手动下载 Teams 应用。 部署后，对于登录至计算机上的所有用户，Teams 将会自动启用。 （你可以在安装此应用之后禁用自动启用。 [请参阅下面的](#disable-auto-launch-for-the-msi-installer)。）建议你将程序包部署至计算机，以便该计算机上的所有新用户均可从此部署中受益。

以下是 MSI 文件的链接：


|实体  |32 位      |64 位      |
|---------|---------|---------|
|商用     | [32 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|联邦政府 - GCC     | [32 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|联邦政府 - GCC High    | [32 位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|联邦政府 - DoD     | [32 位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

Office 365 专业增强版部署中页包括 Teams。 有关详细信息，请参阅[使用 Office 365 专业增强版部署 Microsoft Teams](https://docs.microsoft.com/deployoffice/teams-install)。

> [!Note]
> 如需了解与 Microsoft Endpoint Configuration Manager 相关的详细信息，请参阅[什么是 Configuration Manager？](https://docs.microsoft.com/configmgr/core/understand/introduction)。

## <a name="deployment-procedure-recommended"></a>部署过程（推荐）

1. 检索最新程序包。
2. 使用由 MSI 预填充的默认值。
3. 部署到计算机（如可能）。

## <a name="how-the-microsoft-teams-msi-package-works"></a>Microsoft Teams MSI 程序包的工作原理

### <a name="pc-installation"></a>电脑安装

Teams MSI 会将安装程序放置在“Program Files”中。 无论用户何时登录新的 Windows 用户配置文件，该安装程序均会启用并且 Teams 应用副本将安装在该用户的 `AppData` 文件夹中。 如果用户已在 `AppData` 文件夹中安装了 Teams 应用，则MSI 安装程序将为该用户跳过此过程。

请勿使用 MSI 部署更新，因为当客户端从服务中检测到可用的新版本时将会自动更新。 要冲虚部署最新的安装程序，请使用下述重新部署 MSI 流程。 如果部署的是旧版的 MSI 程序包，则除了在 VDI 环境中以外，客户端将为用户自动更新（如可能）。 如果部署的是非常旧的版本，则在用户能够使用 Teams 之前，MSI 将会触发应用更新。

> [!Important]
> 不建议更改默认安装位置，因为这可能会中断更新流。 版本太旧最终会阻止用户访问服务。

#### <a name="target-computer-requirements"></a>目标计算机要求

- .NET framework 4.5 或更高版本
- Windows 8.1 或更高版本
- Windows Server 2012 R2 或更高版本
- 每个用户配置文件 3 GB 磁盘空间（推荐）

### <a name="vdi-installation"></a>VDI 安装

如需如何在 VDI 上部署 Teams 桌面应用的完整指南，请参阅[适用于虚拟化桌面基础结构的 Teams](teams-for-vdi.md)。

## <a name="clean-up-and-redeployment-procedure"></a>清理和重新部署过程

如果用户从其用户配置文件中卸载 Teams，则 MSI 安装程序将跟踪该用户已卸载 Teams 应用并且不再在该用户配置文件中安装 Teams。 要为此用户在已从其中卸载 Teams 的特定计算机上重新部署 Teams，请执行以下操作：

1. 卸载每个用户配置文件中安装的 Teams 应用。
2. 卸载后，在 `%localappdata%\Microsoft\Teams\` 下以递归方式删除目录。
3. 将 MSI 程序包重新部署到该特定计算机。

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>阻止 Teams 在安装后自动启动

MSI 的默认行为是在用户登录时立即安装 Teams 应用，然后自动启动 Teams。 如果不希望 Teams 在安装之后对用户自动启动，则可以使用组策略设置策略设置，或者禁用 MSI 安装程序自动启用。

#### <a name="use-group-policy-recommended"></a>使用组策略（推荐）

启用**阻止 Microsoft Teams 在安装后自动启动**组策略设置。 可在 User Configuration\Policies\Administrative Templates\Microsoft Teams 中找到此策略设置。 推荐使用此方法，因为你可以根据组织需要关闭或启用策略设置。

如果在安装 Teams 前启用此策略设置，则Teams 将不会在用户登录 Windows 时自动启动。 用户首次登录 Teams 之后，Teams 将在用户下次登录时自动启动。

如需了解更多信息，请参阅[使用组策略阻止 Teams 在安装后自动启动](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)。

> [!CAUTION]
> 如果已部署 Teams 并且想要设置此策略以禁用 Teams 自动启动，请先将组策略设置设为想要的值，然后对每个用户运行 [Teams 自动启动重置脚本](scripts/powershell-script-teams-reset-autostart.md)。

### <a name="disable-auto-launch-for-the-msi-installer"></a>禁用 MSI 安装程序自动启动

可以使用如下所示的 **OPTIONS="noAutoStart=true"** 参数禁用 MSI 安装程序自动启动。  

对于 32 位版本

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```

对于 64 位版本

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

当用户登录 Windows 时，Teams 已通过 MSI 安装并且启动 Teams 的快捷方式已添加至用户桌面。 在用户手动启动 Teams 之前，它不会启动。 用户手动启动 Teams 之后，无论用户何时登录，Teams 均会自动启动。

> [!Note]
> 如果手动运行 MSI，请确保使用已提升的权限运行它。 即便以管理员身份而不是使用已提升的权限运行 MSI，安装程序也无法将选项配置为禁用自动启动。
