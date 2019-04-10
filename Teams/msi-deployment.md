---
title: 通过 SCCM 使用 MSI 安装 Microsoft Teams
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: 管理员可以使用 Teams MSI 批量部署 Microsoft Teams 来选择用户或计算机。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8412b6998e824c05ac4d7f394d2283c265f78b04
ms.sourcegitcommit: 9bb2bfd09ca279752dbedf17911ea46568649c4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "31749682"
---
<a name="install-microsoft-teams-using-msi"></a>使用 MSI 安装 Microsoft Teams
=================================

> [!Tip]
> 观看下面的会话，若要了解有关 Windows 桌面客户端、 如何规划其以及如何将其部署的优势：[团队 Windows 桌面客户端](https://aka.ms/teams-clients)

若要使用广泛部署 System Center Configuration Manager，组策略或任何第三方分发机制，Microsoft 提供了管理员可以使用批量部署团队选择的 MSI 文件 （ [32 位](https://aka.ms/teams32bitmsi)和[64 位](https://aka.ms/teams64bitmsi)）用户或计算机。 管理员可以使用这些文件，以便用户无需手动下载团队应用程序远程部署团队。 在部署时，团队将自动启动的所有用户登录的计算机。 （您可以禁用自动启动后安装应用程序。 [请参见下文](#disable-auto-launch-for-the-msi-installer)。）我们建议您部署包到计算机，这样的计算机的所有新用户也将从此部署中获益。 
 
> [!Note] 
> 若要了解有关 SCCM 的详细信息，请参阅[Introduction 到 System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction)。

## <a name="deployment-procedure-recommended"></a>部署过程 （推荐）
1. 检索的最新程序包。
2. 使用默认值由 MSI 预填充。
3. 部署到计算机时可能。

## <a name="how-the-microsoft-teams-msi-package-works"></a>Microsoft 团队 MSI 数据包的工作原理

### <a name="pc-installation"></a>PC 安装

> [!Note] 
> 有关如何将团队部署到虚拟 DesktopInfrastructure (VDI) 环境的指南，请参阅[VDI 安装](#vdi-installation)。

团队 MSI 将安装程序置于 Program Files。 只要用户迹象到新的 Windows 用户配置文件，将启动安装程序和一份团队应用程序将安装该用户的应用程序数据文件夹中。 如果用户已安装应用程序数据文件夹中的团队应用程序，MSI 安装程序将跳过该用户的过程。

不要使用 MSI 部署更新，因为客户端检测到新版本可从服务时将自动更新。 若要重新部署最新的安装程序，请使用如下所述的 MSI 中重新部署的过程。如果您部署的 MSI 程序包的旧版本，客户端将自动更新时可能的用户。 如果部署获取非常旧版本，MSI 将触发应用程序更新之前用户能够使用团队。 

> [!Important] 
> 我们不建议您更改默认安装位置，因为这可能会中断的更新流程。 具有太旧版本最终将阻止用户访问服务。 

#### <a name="target-computer-requirements"></a>目标计算机要求

- .NET framework 4.5 或更高版本
- Windows 7 或更高版本
- 3 GB 的磁盘空间，每个用户配置文件 （推荐）

### <a name="vdi-installation"></a>VDI 安装

下面是部署团队桌面应用程序的过程。 完整的指南，请参阅[虚拟化桌面基础结构团队](teams-for-vdi.md)。

1. 下载团队 MSI 程序包使用具体取决于环境的以下链接之一。 建议 VDI vm 与 64 位操作系统的 64 位版本。

    - [32 位版本](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [64 位版本](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. 运行以下命令以安装 VDI VM MSI （或完成更新它）。

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    此安装程序文件的团队。 此时，金色映像安装已完成。

    下一个交互式登录会话启动团队，并要求提供凭据。 请注意，不能使用 ALLUSER 属性 VDI 上安装团队时禁用自动启动的团队。

3. 运行以下命令以卸载从 VDI 虚拟机的 MSI （或准备更新它）。

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    这将从 Program Files 卸载团队。

## <a name="clean-up-and-redeployment-procedure"></a>清理和重新部署过程

如果用户从其用户配置文件中卸载团队，MSI 安装程序将跟踪用户已卸载团队应用程序和不再为该用户配置文件安装团队。 若要重新团队部署为此用户其中它已卸载特定计算机上，执行以下操作：

1. 卸载团队应用程序安装每个用户配置文件。 
2. 卸载后，删除目录以递归方式 %localappdata%\microsoft\teams\ 下。
3. 重新部署特定计算机的 MSI 数据包。

> [!TIP] 
> 您可以使用我们[的 Microsoft 团队部署清理](scripts/Powershell-script-teams-deployment-clean-up.md)的脚本完成通过 SCCM 的步骤 1 和 2。

## <a name="disable-auto-launch-for-the-msi-installer"></a>禁用自动启动的 MSI 安装程序

MSI 默认行为是安装团队客户端，只要用户使用登录，然后自动启动团队。 您可以如下所示修改此行为与以下参数：

- 当用户登录到 Windows 时，将使用 MSI 安装团队
- 但是，团队客户端之前不会启动用户已手动启动团队
- 将用户的桌面上添加一个快捷方式，以启动团队
- 手动启动后，团队将自动启动时用户登录

32 位版本
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
64 位版本
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  如果手动运行 MSI，请务必运行以提升的权限。 即使您运行它作为管理员，但不运行以提升的权限，安装程序不能配置选项后，可以禁用自动启动。
