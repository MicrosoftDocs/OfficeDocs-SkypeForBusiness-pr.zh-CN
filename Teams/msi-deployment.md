---
title: 通过 SCCM 使用 MSI 安装 Microsoft Teams
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
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e32eb60b238d606ac30fe74c7551e01efe88242a
ms.sourcegitcommit: c2e315d0fcec742d2e1ba5ad90dffd1a1157a466
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2019
ms.locfileid: "40002226"
---
# <a name="install-microsoft-teams-using-msi"></a>使用 MSI 安装 Microsoft Teams

> [!Tip]
> 观看以下会话，了解 Windows 桌面客户端的优点、如何规划它以及如何部署它：[团队 Windows 桌面客户端](https://aka.ms/teams-clients)

若要使用 System Center Configuration Manager 或组策略或任何第三方分发机制进行广泛的部署，Microsoft 提供了 MSI 文件（32位和64位），管理员可以使用这些文件批量部署团队以选择用户或计算机。 管理员可以使用这些文件远程部署团队，以便用户不必手动下载团队应用。 部署后，团队将为登录到该计算机的所有用户自动启动。 （您可以在安装应用后禁用自动启动。 [请参阅下文](#disable-auto-launch-for-the-msi-installer)。）我们建议你将程序包部署到计算机，以便计算机的所有新用户也将受益于此部署。

以下是指向 MSI 文件的链接：


|元  |32位      |64位      |
|---------|---------|---------|
|交给     | [32位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|联邦政府-GCC     | [32位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|联邦政府-GCC 高    | [32位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|联邦政府-DoD     | [32位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

团队还可以包含在 Office 365 专业增强版的部署中。 有关详细信息，请参阅[部署 Microsoft 团队和 Office 365 专业增强版](https://docs.microsoft.com/deployoffice/teams-install)。

> [!Note]
> 若要了解有关 SCCM 的详细信息，请参阅[System Center Configuration Manager 简介](https://docs.microsoft.com/sccm/core/understand/introduction)。

## <a name="deployment-procedure-recommended"></a>部署过程（推荐）

1. 检索最新的程序包。
2. 使用由 MSI 预填充的默认值。
3. 尽可能部署到计算机。

## <a name="how-the-microsoft-teams-msi-package-works"></a>Microsoft 团队 MSI 程序包的工作原理

### <a name="pc-installation"></a>PC 安装

团队 MSI 将在程序文件中放置一个安装程序。 当用户登录到新的 Windows 用户配置文件时，将启动安装程序，并将在该用户的 appdata 文件夹中安装 "团队" 应用副本。 如果用户已在 appdata 文件夹中安装了 "团队" 应用，则 MSI 安装程序将跳过该用户的进程。

请勿使用 MSI 部署更新，因为客户端将在检测到服务提供新版本时自动更新。 若要重新部署最新的安装程序，请使用下面所述的重新部署 MSI 的过程。如果你部署较旧版本的 MSI 程序包，客户端将在可能的情况下自动更新（在 VDI 环境中除外）。 如果部署了非常旧的版本，MSI 将在用户可以使用团队之前触发应用更新。

> [!Important]
> 我们不建议你更改默认安装位置，因为这可能会中断更新流。 如果版本过旧，最终会阻止用户访问该服务。

#### <a name="target-computer-requirements"></a>目标计算机要求

- .NET framework 4.5 或更高版本
- Windows 7 或更高版本
- 每个用户配置文件 3 GB 的磁盘空间（推荐）

### <a name="vdi-installation"></a>VDI 安装

有关如何在 VDI 上部署团队桌面应用的完整指南，请参阅[针对虚拟化桌面基础结构的团队](teams-for-vdi.md)。

## <a name="clean-up-and-redeployment-procedure"></a>清理和重新部署过程

如果用户从其用户配置文件中卸载团队，则 MSI 安装程序将跟踪用户已卸载团队应用，并且不再为该用户配置文件安装团队。 若要在卸载的特定计算机上为此用户重新部署团队，请执行下列操作：

1. 卸载为每个用户配置文件安装的团队应用。
2. 卸载后，在%localappdata%\Microsoft\Teams\. 下递归删除目录
3. 将 MSI 程序包重新部署到该特定计算机。

> [!TIP]
> 你可以使用[Microsoft 团队部署清理](scripts/Powershell-script-teams-deployment-clean-up.md)脚本，通过 SCCM 完成步骤1和2。

## <a name="disable-auto-launch-for-the-msi-installer"></a>禁用 MSI 安装程序的自动启动

MSI 的默认行为是在用户登录后立即安装团队客户端，然后自动启动团队。 你可以按如下方式修改此行为，如下所示：

- 当用户登录到 Windows 时，将使用 MSI 安装团队
- 但是，团队客户端将不会启动，直到用户手动开始团队
- 将在用户桌面上添加开始团队的快捷方式
- 手动启动后，团队将在用户登录时自动启动

对于32位版本
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
对于64位版本
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
> 如果手动运行 MSI，请确保以提升的权限运行 MSI。 即使以管理员身份运行它，而不以提升的权限运行它，安装程序也无法将该选项配置为禁用自动启动。
