---
title: 通过 SCCM 使用 MSI 安装 Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: 管理员可以使用 Teams MSI 批量部署 Microsoft Teams 来选择用户或计算机。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c009433696ac554114a2a06955b4f33beb6543f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281614"
---
<a name="install-microsoft-teams-using-msi"></a>使用 MSI 安装 Microsoft Teams
=================================

> [!Tip]
> 观看以下会话, 了解 Windows 桌面客户端的优点、如何规划它以及如何部署它:[团队 Windows 桌面客户端](https://aka.ms/teams-clients)

若要使用 System Center Configuration Manager 或组策略或任何第三方分发机制进行广泛的部署, Microsoft 提供了 MSI 文件 ( [32 位](https://aka.ms/teams32bitmsi)和[64 位](https://aka.ms/teams64bitmsi)), 管理员可使用这些文件批量部署团队进行选择用户或计算机。 管理员可以使用这些文件远程部署团队, 以便用户不必手动下载团队应用。 部署后, 团队将为登录到该计算机的所有用户自动启动。 (您可以在安装应用后禁用自动启动。 [请参阅下文](#disable-auto-launch-for-the-msi-installer)。)我们建议你将程序包部署到计算机, 以便计算机的所有新用户也将受益于此部署。 
 
> [!Note] 
> 若要了解有关 SCCM 的详细信息, 请参阅[System Center Configuration Manager 简介](https://docs.microsoft.com/sccm/core/understand/introduction)。

## <a name="deployment-procedure-recommended"></a>部署过程 (推荐)
1. 检索最新的程序包。
2. 使用由 MSI 预填充的默认值。
3. 尽可能部署到计算机。

## <a name="how-the-microsoft-teams-msi-package-works"></a>Microsoft 团队 MSI 程序包的工作原理

### <a name="pc-installation"></a>PC 安装

> [!Note] 
> 有关如何将团队部署到虚拟 DesktopInfrastructure (VDI) 环境的指南, 请参阅[VDI 安装](#vdi-installation)。

团队 MSI 将在程序文件中放置一个安装程序。 当用户登录到新的 Windows 用户配置文件时, 将启动安装程序, 并将在该用户的 appdata 文件夹中安装 "团队" 应用副本。 如果用户已在 appdata 文件夹中安装了 "团队" 应用, 则 MSI 安装程序将跳过该用户的进程。

请勿使用 MSI 部署更新, 因为客户端将在检测到服务提供新版本时自动更新。 若要重新部署最新的安装程序, 请使用下面所述的重新部署 MSI 的过程。如果你部署较旧版本的 MSI 程序包, 客户可能会在可能的情况下自动更新该用户。 如果部署了非常旧的版本, MSI 将在用户可以使用团队之前触发应用更新。 

> [!Important] 
> 我们不建议你更改默认安装位置, 因为这可能会中断更新流。 如果版本过旧, 最终会阻止用户访问该服务。 

#### <a name="target-computer-requirements"></a>目标计算机要求

- .NET framework 4.5 或更高版本
- Windows 7 或更高版本
- 每个用户配置文件 3 GB 的磁盘空间 (推荐)

### <a name="vdi-installation"></a>VDI 安装

下面是部署团队桌面应用的过程。 有关完整指南, 请参阅[针对虚拟化桌面基础结构的团队](teams-for-vdi.md)。

1. 根据环境, 使用下列链接之一下载团队 MSI 程序包。 我们建议使用64位操作系统的 VDI VM 64 位版本。

    - [32位版本](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [64位版本](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. 运行以下命令, 将 MSI 安装到 VDI VM (或完成更新)。

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1

    这将把团队安装到程序文件。 此时, 将完成黄金图像设置。

    下一个交互式登录会话将启动团队并要求提供凭据。 请注意, 在 VDI 上使用 ALLUSERS 属性安装团队时, 不可能禁用团队的自动启动。

3. 运行以下命令以从 VDI VM 卸载 MSI (或准备更新它)。

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    这将从程序文件中卸载团队。

## <a name="clean-up-and-redeployment-procedure"></a>清理和重新部署过程

如果用户从其用户配置文件中卸载团队, 则 MSI 安装程序将跟踪用户已卸载团队应用, 并且不再为该用户配置文件安装团队。 若要在卸载的特定计算机上为此用户重新部署团队, 请执行下列操作:

1. 卸载为每个用户配置文件安装的团队应用。 
2. 卸载后, 在%localappdata%\Microsoft\Teams\. 下递归删除目录
3. 将 MSI 程序包重新部署到该特定计算机。

> [!TIP] 
> 你可以使用[Microsoft 团队部署清理](scripts/Powershell-script-teams-deployment-clean-up.md)脚本, 通过 SCCM 完成步骤1和2。

## <a name="disable-auto-launch-for-the-msi-installer"></a>禁用 MSI 安装程序的自动启动

MSI 的默认行为是在用户登录后立即安装团队客户端, 然后自动启动团队。 你可以按如下方式修改此行为, 如下所示:

- 当用户登录到 Windows 时, 将使用 MSI 安装团队
- 但是, 团队客户端将不会启动, 直到用户手动开始团队
- 将在用户桌面上添加开始团队的快捷方式
- 手动启动后, 团队将在用户登录时自动启动

对于32位版本
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
对于64位版本
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  如果手动运行 MSI, 请确保以提升的权限运行 MSI。 即使以管理员身份运行它, 而不以提升的权限运行它, 安装程序也无法将该选项配置为禁用自动启动。
