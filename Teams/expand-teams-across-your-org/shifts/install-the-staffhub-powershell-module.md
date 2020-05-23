---
title: 安装 StaffHub PowerShell 模块
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何安装并连接到 Microsoft StaffHub PowerShell 模块并将 StaffHub 团队移动到 Microsoft 团队。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b81e28c198ca3ae26979bb61895acdb61842f354
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350166"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>安装 Microsoft StaffHub PowerShell 模块

> [!IMPORTANT]
> 2020年6月30日生效，Microsoft StaffHub 将停用。 我们正在将 StaffHub 功能构建到 Microsoft 团队中。 今天，团队包括 "倒班" 应用，用于计划管理，而其他功能将随着时间的推移而推出。 StaffHub 将在2020年6月30日停止为所有用户工作。 任何试图打开 StaffHub 的人都将显示一条消息，指导他们下载团队。 若要了解详细信息，请参阅[Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。  

使用本文中的步骤安装并连接到 Microsoft StaffHub PowerShell 模块。 你将需要此操作才能[将你的 StaffHub 团队移动到团队](move-staffhub-teams-to-shifts-in-teams.md)。

## <a name="install-the-microsoft-staffhub-powershell-module"></a>安装 Microsoft StaffHub PowerShell 模块

1. 下载[StaffHub PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftStaffHub)。
2. 以管理员身份打开 Windows PowerShell 3.0 或更高版本。若要执行此操作，请单击 "**开始**"，键入**windows powershell**，右键单击 " **windows powershell**"，然后选择 "**以管理员身份运行**"。
    > [!NOTE]
    > 若要获取最新版本的 Windows PowerShell，请参阅[安装 Windows powershell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)。
3. 请运行以下命令：

    ```PowerShell
    $ENV:PSModulePath
    ```
4. 检查输出中的文件夹路径，并确保你的计算机上的所有文件夹都存在于你的计算机上，然后再转到下一步。 如果文件夹丢失，请创建它们。
5. 运行以下内容以允许安装 StaffHub PowerShell 模块：

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
6. 运行以下，其中 &lt; path &gt; 是步骤3的输出中的路径。 例如，路径可能如下所示 C:\Users\User1\Documents\WindowsPowerShell\Modules。

    请确保单独运行每个命令。

    ```PowerShell
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    ```
7. 退出 Windows PowerShell。
8. 以全局管理员身份打开 Windows PowerShell 3.0 或更高版本，然后运行以下操作：

    ```PowerShell
    Install-Module -Name MicrosoftStaffHub
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>连接到 Microsoft StaffHub PowerShell 模块

1. 请运行以下命令：

    ```PowerShell
    Connect-StaffHub
    ```

2. 出现提示时，以全局管理员身份登录。

## <a name="related-topics"></a>相关主题

- [Microsoft StaffHub PowerShell 参考](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
- [将 Microsoft StaffHub 团队迁移到 Teams 中的排班](move-staffhub-teams-to-shifts-in-teams.md)
