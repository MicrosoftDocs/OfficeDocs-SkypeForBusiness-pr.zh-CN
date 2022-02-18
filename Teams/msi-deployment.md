---
title: '使用 TEAMS 安装程序Windows MSI (批量安装) '
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: amitsri
audience: admin
description: 使用Windows安装程序 (MSI) 文件将 Teams 客户端分发给多个用户和计算机。
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
ms.openlocfilehash: fc9e17f958b1770573cf6729ef6aca9b22ffe03d
ms.sourcegitcommit: a9a056b93b4add3a4d978bb341ea4b66a042b4d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2022
ms.locfileid: "62893561"
---
# <a name="bulk-install-teams-using-windows-installer-msi"></a>使用 TEAMS 安装程序Windows MSI (批量安装) 

> [!Tip]
> 观看以下会话，了解 Windows 桌面客户端的好处、如何规划它以及如何部署它：Teams Windows[桌面客户端](https://aka.ms/teams-clients)。

Microsoft 提供 32 位、64 位和 ARM64 MSI 文件，可用于批量部署Microsoft Teams用户和计算机。 MSI 文件可以[与 Microsoft Endpoint Configuration Manager、](/configmgr/core/understand/introduction)[组策略](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software)或第三方分发软件一起用于将Teams部署到组织。 批量部署非常有用，因为用户无需手动下载和安装Teams客户端。 而是Teams部署到计算机，然后在用户首次登录到计算机时自动启动。

建议将包部署到计算机而不是特定用户。 通过以计算机为目标，这些计算机的所有新用户都将受益于此部署。

>[!NOTE]
> Teams，也可以作为组织的一部分向组织分发Microsoft 365 企业应用版。 有关详细信息，请参阅使用 Microsoft Teams [部署Microsoft 365 企业应用版](/deployoffice/teams-install)。

## <a name="msi-files"></a>MSI 文件

下表提供了指向 32 位、64 位和 ARM64 MSI 文件的链接，Teams。 下载要安装在组织中计算机上的 MSI。 x86 体系结构 (32 位或 64 位) Teams独立于计算机上安装Office应用。

如果有 64 位计算机，建议安装 64 位 Teams MSI，即使计算机运行的是 32 位版本的 Office。 ARM64 MSI 只能安装在使用 ARM 体系结构的计算机上，例如 Surface Pro X。

> [!IMPORTANT]
> 仅在 64 位操作系统Teams安装 64 位版本的操作系统。 如果尝试在 32 位操作系统上安装 64 位版本的 Teams，安装不会成功，也不会收到错误消息。

|实体  |32 位      |64 位      | ARM64 |
|---------|---------|---------|-----------|
|商用     | [32 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|美国政府 - GCC     | [32 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64 位](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|美国政府 - GCC高    | [32 位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64 位](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|美国政府 - DoD     | [32 位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64 位](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

## <a name="how-the-microsoft-teams-msi-file-works"></a>MSI Microsoft Teams的工作原理

### <a name="pc-installation"></a>电脑安装

MSI `%SystemDrive%\Program Files\Teams Installer` Teams在 32 `%SystemDrive%\Program Files (x86)\Teams Installer` 位或 64 位 Windows 上设置安装程序Windows。 每当用户登录新的 Windows配置文件时，安装程序都会启动，Teams应用的副本安装在该用户的 文件夹中`%LocalAppData%\Microsoft\Teams`。 如果用户已在 文件夹中Teams`%LocalAppData%\Microsoft\Teams`应用，MSI 安装程序会跳过该用户的过程。

MSI 文件不能用于部署更新。 当Teams服务提供新版本时，客户端会自动更新。 若要重新部署最新安装程序，请使用重新部署 MSI 的过程，如下所述。 如果部署较旧版本的 MSI 文件，客户端将自动更新 (在 VDI 环境中，) 在用户可能的情况下自动更新。 如果部署的是非常旧的版本，则在用户能够使用 Teams 之前，MSI 将会触发应用更新。

> [!IMPORTANT]
> 不建议更改默认安装位置，因为这样做可能会中断更新流。 版本太旧最终会阻止用户访问服务。

#### <a name="target-computer-requirements"></a>目标计算机要求

请确保安装的计算机满足Teams硬件要求中列出的要求[Microsoft Teams。](hardware-requirements-for-the-teams-app.md)

### <a name="vdi-installation"></a>VDI 安装

如需如何在 VDI 上部署 Teams 桌面应用的完整指南，请参阅[适用于虚拟化桌面基础结构的 Teams](teams-for-vdi.md)。

## <a name="clean-up-and-redeployment-procedure"></a>清理和重新部署过程

如果用户从Teams卸载应用，MSI 安装程序将跟踪该用户已卸载 Teams 应用，并且不再为Teams安装 Teams。 要为此用户在已从其中卸载 Teams 的特定计算机上重新部署 Teams，请执行以下操作：

> [!IMPORTANT]
> 接下来的步骤包含有关如何修改注册表的信息。 请确保在修改注册表之前对其进行备份，并且知道在出现问题时如何还原注册表。 若要详细了解如何备份、还原和修改注册表，请参阅Windows[用户的注册表信息](https://support.microsoft.com/help/256986)。

1. 卸载Teams配置文件安装的应用。 有关详细信息，请参阅卸载[Microsoft Teams](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop)。
2. 在每个用户配置文件的 下以递归 `%LocalAppData%\Microsoft\Teams\` 删除目录。
3. `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi`删除每个用户配置文件的注册表值。
4. 将 MSI 文件重新部署到该特定计算机。

> [!TIP]
> 也可使用 Teams [清理脚本](scripts/powershell-script-deployment-cleanup.md)完成步骤 1 和 2。  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>阻止 Teams 在安装后自动启动

MSI 的默认行为是在用户登录时立即安装 Teams 应用，然后自动启动 Teams。 如果不希望 Teams 在安装之后对用户自动启动，则可以使用组策略设置策略设置，或者禁用 MSI 安装程序自动启用。

### <a name="use-group-policy-recommended"></a>使用组策略（推荐）

启用"**阻止Microsoft Teams安装后自动启动组**[策略](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software)"设置。 可以在"用户配置""策略 **""**\\\\\\管理模板Microsoft Teams **"中查找此策略设置**。 推荐使用此方法，因为你可以根据组织需要关闭或启用策略设置。

如果在安装 Teams 前启用此策略设置，则Teams 将不会在用户登录 Windows 时自动启动。 用户首次登录 Teams 之后，Teams 将在用户下次登录时自动启动。

如需了解更多信息，请参阅[使用组策略阻止 Teams 在安装后自动启动](/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)。

> [!CAUTION]
> 如果已部署 Teams 并且想要设置此策略以禁用 Teams 自动启动，请先将组策略设置设为想要的值，然后对每个用户运行 [Teams 自动启动重置脚本](scripts/powershell-script-teams-reset-autostart.md)。

### <a name="disable-auto-launch-for-the-msi-installer"></a>禁用 MSI 安装程序自动启动

可以使用 参数禁用 MSI 安装程序的自动启动， `OPTIONS="noAutoStart=true"` 如下所示。  

对于 32 位版本：

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

对于 64 位版本：

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

当用户登录 Windows 时，Teams 已通过 MSI 安装并且启动 Teams 的快捷方式已添加至用户桌面。 在用户手动启动 Teams 之前，它不会启动。 用户手动启动 Teams 之后，无论用户何时登录，Teams 均会自动启动。

请注意，这些示例还使用 **ALLUSERS=1** 参数。 设置此参数时，Teams Machine-Wide安装程序会显示在"控制面板"中的"程序和功能"中，&"应用"Windows 设置的"功能"中。 然后，如果用户Teams管理员凭据，则所有用户都可以卸载密码。

> [!Note]
> 如果手动运行 MSI，请确保使用已提升的权限运行它。 即便以管理员身份而不是使用已提升的权限运行 MSI，安装程序也无法将选项配置为禁用自动启动。
