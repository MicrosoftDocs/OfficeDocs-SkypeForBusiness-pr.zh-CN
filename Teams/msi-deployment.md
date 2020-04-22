---
title: 使用 Microsoft 终结点配置管理器安装团队
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
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9e27199d953eb04c20a10765020b179ff303c5e8
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777827"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a>使用 Microsoft Endpoint Configuration Manager 安装 Microsoft Teams

> [!Tip]
> 观看以下会话，了解 Windows 桌面客户端的优点、如何规划它以及如何部署它：[团队 Windows 桌面客户端](https://aka.ms/teams-clients)。

为了使用 Microsoft Endpoint Configuration Manager 或组策略或任何第三方分发机制以进行广泛部署，Microsoft 提供了 MSI 文件（32 位和 64 位），供管理员用于将 Teams 批量部署至选定的用户或计算机。 管理员可以使用这些文件远程部署 Teams，使用户无需手动下载 Teams 应用。 部署后，对于登录至计算机上的所有用户，Teams 将会自动启用。 （你可以在安装此应用之后禁用自动启用。 [请参阅下面的](#disable-auto-launch-for-the-msi-installer)。）建议你将程序包部署至计算机，以便该计算机上的所有新用户均可从此部署中受益。

以下是 MSI 文件的链接：


|实体  |32位      |64位      |
|---------|---------|---------|
|商用     | [32位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|联邦政府 - GCC     | [32位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|联邦政府 - GCC High    | [32位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|联邦政府 - DoD     | [32位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

> [!NOTE]
> 在64位操作系统上安装64位版本的团队。 如果你尝试在32位操作系统上安装64位版本的团队，则安装将不会成功，并且当前不会收到错误消息。

团队也可以包含在适用于企业的 Microsoft 365 应用的部署中。 有关详细信息，请参阅[通过适用于企业的 microsoft 365 应用部署 Microsoft 团队](https://docs.microsoft.com/deployoffice/teams-install)。

> [!Note]
> 若要了解有关 Microsoft 终结点配置管理器的详细信息，请参阅[什么是配置管理器？](https://docs.microsoft.com/configmgr/core/understand/introduction)

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

如果用户从其用户配置文件中卸载团队，则 MSI 安装程序将跟踪用户已卸载团队应用，并且不再为该用户配置文件安装团队。 要为此用户在已从其中卸载 Teams 的特定计算机上重新部署 Teams，请执行以下操作：

> [!IMPORTANT]
> 接下来的步骤包含有关如何修改注册表的信息。 请确保在修改注册表之前对其进行备份，如果出现问题，您知道如何还原注册表。 有关如何备份、还原和修改注册表的详细信息，请参阅[高级用户的 Windows 注册表信息](https://support.microsoft.com/help/256986)。

1. 卸载为每个用户配置文件安装的团队应用。 有关详细信息，请参阅[卸载 Microsoft 团队](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop)。
2. 在下`%localappdata%\Microsoft\Teams\`递归删除目录。
3. 删除`HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi`注册表值。
4. 将 MSI 程序包重新部署到该特定计算机。

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>阻止 Teams 在安装后自动启动

MSI 的默认行为是在用户登录时立即安装 Teams 应用，然后自动启动 Teams。 如果不希望 Teams 在安装之后对用户自动启动，则可以使用组策略设置策略设置，或者禁用 MSI 安装程序自动启用。

### <a name="use-group-policy-recommended"></a>使用组策略（推荐）

启用**阻止 Microsoft Teams 在安装后自动启动**组策略设置。 可在 User Configuration\Policies\Administrative Templates\Microsoft Teams 中找到此策略设置。 推荐使用此方法，因为你可以根据组织需要关闭或启用策略设置。

如果在安装 Teams 前启用此策略设置，则Teams 将不会在用户登录 Windows 时自动启动。 用户首次登录 Teams 之后，Teams 将在用户下次登录时自动启动。

如需了解更多信息，请参阅[使用组策略阻止 Teams 在安装后自动启动](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)。

> [!CAUTION]
> 如果已部署 Teams 并且想要设置此策略以禁用 Teams 自动启动，请先将组策略设置设为想要的值，然后对每个用户运行 [Teams 自动启动重置脚本](scripts/powershell-script-teams-reset-autostart.md)。

### <a name="disable-auto-launch-for-the-msi-installer"></a>禁用 MSI 安装程序自动启动

可以使用如下所示的 **OPTIONS="noAutoStart=true"** 参数禁用 MSI 安装程序自动启动。  

对于32位版本：

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

对于64位版本：

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

当用户登录 Windows 时，Teams 已通过 MSI 安装并且启动 Teams 的快捷方式已添加至用户桌面。 在用户手动启动 Teams 之前，它不会启动。 用户手动启动 Teams 之后，无论用户何时登录，Teams 均会自动启动。

请注意，这些示例还使用**ALLUSERS = 1**参数。 设置此参数时，团队计算机范围的安装程序将显示在 "控制面板" 的 "程序和功能" 和 "应用程序" 中的 "Windows 设置" 中的 "应用 & 功能" 中。 如果团队拥有计算机上的管理员凭据，则所有用户都可以卸载团队。

> [!Note]
> 如果手动运行 MSI，请确保使用已提升的权限运行它。 即便以管理员身份而不是使用已提升的权限运行 MSI，安装程序也无法将选项配置为禁用自动启动。
