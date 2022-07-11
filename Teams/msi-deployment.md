---
title: '使用 Windows 安装程序批量安装 Teams (MSI) '
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: amitsri
audience: admin
description: 使用 Windows Installer (MSI) 文件将 Teams 客户端分发到多个用户和计算机。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b8c8521aa5e19abe59aa9e4c60fcc41eff9b1c7
ms.sourcegitcommit: 8d7a926758971bee491d24f23b1ad14f5e5c6f7f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2022
ms.locfileid: "66713320"
---
# <a name="bulk-install-teams-using-windows-installer-msi"></a>使用 Windows 安装程序批量安装 Teams (MSI) 

> [!Tip]
> 观看以下会话，了解 Windows 桌面客户端的优势、如何规划它以及如何部署它： [Teams Windows 桌面客户端](https://aka.ms/teams-clients)。

Microsoft 提供 32 位、64 位和 ARM64 MSI 文件，可用于批量部署 Microsoft Teams 以选择用户和计算机。 MSI 文件可用于 [Microsoft Endpoint Configuration Manager](/configmgr/core/understand/introduction)、[组策略](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software) 或第三方分发软件，以便将 Teams 部署到组织。 批量部署非常有用，因为用户无需手动下载和安装 Teams 客户端。 相反，Teams 将部署到计算机，然后在用户首次登录计算机时自动启动。

建议将包部署到计算机，而不是特定用户。 通过面向计算机，这些计算机的所有新用户都将受益于此部署。

>[!NOTE]
> 团队也可以作为Microsoft 365 企业应用版的一部分分发到你的组织。 有关详细信息，请参阅[使用 Microsoft 365 企业应用版 部署 Microsoft Teams](/deployoffice/teams-install)。

## <a name="msi-files"></a>MSI 文件

下表提供了指向 Teams 的 32 位、64 位和 ARM64 MSI 文件的链接。 下载要在组织中的计算机上安装的 MSI。  (32 位或 64 位) Teams 支持的 x86 体系结构独立于计算机上安装的其他 Office 应用。

如果你有 64 位计算机，我们建议安装 64 位 Teams MSI，即使计算机运行的是 32 位版本的 Office。 ARM64 MSI 只能安装在使用 ARM 体系结构的计算机上，例如Surface Pro X。

> [!IMPORTANT]
> 仅在 64 位操作系统上安装 64 位版本的 Teams。 如果尝试在 32 位操作系统上安装 64 位版本的 Teams，安装不会成功，也不会收到错误消息。

|实体  |32 位      |64 位      | ARM64 |
|---------|---------|---------|-----------|
|商用     | [32 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|美国政府 - GCC     | [32 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|美国政府 - GCC High    | [32 位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|美国政府 - DoD     | [32 位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

## <a name="how-the-microsoft-teams-msi-file-works"></a>Microsoft Teams MSI 文件的工作原理

### <a name="pc-installation"></a>电脑安装

Teams MSI 在 `%SystemDrive%\Program Files\Teams Installer` 32 位 Windows 和 `%SystemDrive%\Program Files (x86)\Teams Installer` 64 位 Windows 上放置安装程序。 每当用户登录到新的 Windows 用户配置文件时，就会启动安装程序，并在该用户的文件夹中安装 Teams 应用的 `%LocalAppData%\Microsoft\Teams` 副本。 如果用户已在文件夹中 `%LocalAppData%\Microsoft\Teams` 安装了 Teams 应用，则 MSI 安装程序将跳过该用户的进程。

MSI 文件不能用于部署更新。 Teams 客户端在检测到服务中提供了新版本时会自动更新。 若要重新部署最新的安装程序，请使用下面所述的重新部署 MSI 的过程。 如果部署较旧版本的 MSI 文件，则客户端将自动更新 (除非在 VDI 环境中) 用户尽可能更新。 如果部署的是非常旧的版本，则在用户能够使用 Teams 之前，MSI 将会触发应用更新。

> [!IMPORTANT]
> 我们不建议更改默认安装位置，因为这可能会中断更新流。 版本太旧最终会阻止用户访问服务。

#### <a name="target-computer-requirements"></a>目标计算机要求

确保在满足 [Microsoft Teams 硬件要求](hardware-requirements-for-the-teams-app.md)中列出的要求时安装 Teams 的计算机。

### <a name="vdi-installation"></a>VDI 安装

如需如何在 VDI 上部署 Teams 桌面应用的完整指南，请参阅[适用于虚拟化桌面基础结构的 Teams](teams-for-vdi.md)。

## <a name="clean-up-and-redeployment-procedure"></a>清理和重新部署过程

如果用户从其用户配置文件中卸载 Teams，MSI 安装程序将跟踪用户是否已卸载 Teams 应用，并且不再为该用户配置文件安装 Teams。 要为此用户在已从其中卸载 Teams 的特定计算机上重新部署 Teams，请执行以下操作：

> [!IMPORTANT]
> 后续步骤包含有关如何修改注册表的信息。 在修改注册表之前，请确保备份注册表，并在出现问题时了解如何还原注册表。 有关如何备份、还原和修改注册表的详细信息，请参阅 [高级用户的 Windows 注册表信息](https://support.microsoft.com/help/256986)。

1. 卸载为每个用户配置文件安装的 Teams 应用。 有关详细信息，请参阅 [卸载 Microsoft Teams](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop)。
2. 以递归方式删除每个用户配置文件下 `%LocalAppData%\Microsoft\Teams\` 的目录。
3. 删除 `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` 每个用户配置文件的注册表值。
4. 将 MSI 文件重新部署到该特定计算机。

> [!TIP]
> 还可以使用 Teams [部署清理脚本](scripts/powershell-script-deployment-cleanup.md) 完成步骤 1 和步骤 2。  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>阻止 Teams 在安装后自动启动

MSI 的默认行为是在用户登录时立即安装 Teams 应用，然后自动启动 Teams。 如果不希望 Teams 在安装之后对用户自动启动，则可以使用组策略设置策略设置，或者禁用 MSI 安装程序自动启用。

### <a name="use-group-policy-recommended"></a>使用组策略（推荐）

启用 **阻止 Microsoft Teams 在安装组策略设置后自动启动**[](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software)。 可以在 **用户配置**\\\\策略 **管理模板**\\**Microsoft Teams** 中找到此策略设置。 推荐使用此方法，因为你可以根据组织需要关闭或启用策略设置。

如果在安装 Teams 前启用此策略设置，则Teams 将不会在用户登录 Windows 时自动启动。 用户首次登录 Teams 之后，Teams 将在用户下次登录时自动启动。

如需了解更多信息，请参阅[使用组策略阻止 Teams 在安装后自动启动](/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)。

> [!CAUTION]
> 如果已部署 Teams 并且想要设置此策略以禁用 Teams 自动启动，请先将组策略设置设为想要的值，然后对每个用户运行 [Teams 自动启动重置脚本](scripts/powershell-script-teams-reset-autostart.md)。

### <a name="disable-auto-launch-for-the-msi-installer"></a>禁用 MSI 安装程序自动启动

可以使用以下参数为 MSI 安装程序禁用 `OPTIONS="noAutoStart=true"` 自动启动。  

对于 32 位版本：

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

对于 64 位版本：

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

当用户登录到 Windows 时，将使用 MSI 安装 Teams。 在用户手动启动 Teams 之前，它不会启动。 用户手动启动 Teams 之后，无论用户何时登录，Teams 均会自动启动。

请注意，这些示例还使用 **ALLUSERS=1** 参数。 设置此参数时，Teams Machine-Wide安装程序将显示在控制面板中的程序和功能中，在 Windows 设置中为计算机的所有用户&应用&功能。 然后，如果所有用户在计算机上具有管理员凭据，则可以卸载 Teams。

> [!Note]
> 如果手动运行 MSI，请确保使用已提升的权限运行它。 即便以管理员身份而不是使用已提升的权限运行 MSI，安装程序也无法将选项配置为禁用自动启动。
