---
title: 安装 StaffHub PowerShell 模块
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 04/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 了解如何安装并连接到 Microsoft StaffHub PowerShell 模块。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe419348d966d9ddfc5c16eee29d9a5005cd6db8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245913"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>安装 Microsoft StaffHub PowerShell 模块

> [!IMPORTANT]
> 有效 2019 年 10 月 1，，Microsoft StaffHub 将要停用。 我们 StaffHub 功能构建到 Microsoft 团队。 如今，团队包括日程管理引进相关应用程序和其他功能将随着时间的推移推出。 StaffHub 上 2019 年 10 月 1，将停止的所有用户的工作。 尝试打开 StaffHub 的任何人都将显示一条消息，来下载团队。 若要了解详细信息，请参阅[Microsoft StaffHub 要停用](microsoft-staffhub-to-be-retired.md)。  

使用本文中的步骤安装并连接到 Microsoft StaffHub PowerShell 模块。 您将需要此能够通过使用 PowerShell 管理 StaffHub 和移动到的 Microsoft 团队 StaffHub 团队。

## <a name="install-the-microsoft-staffhub-powershell-module"></a>安装 Microsoft StaffHub PowerShell 模块

1. 下载[StaffHub PowerShell 模块](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha)。 
2. 打开 Windows PowerShell 3.0 或更高版本，以管理员身份。 若要执行此操作，单击**开始**，键入**Windows PowerShell**，右键单击**Windows PowerShell**中，，然后选择**以管理员身份运行**。
3. 请运行以下命令：

    ```
    $ENV:PSModulePath
    ```

4. 检查在输出中的文件夹路径，并确保路径中的所有文件夹都存在您的计算机上，转到下一步之前。 如果缺少文件夹，创建它们。
5. 运行以下内容，其中&lt;路径&gt;是从步骤 2 在输出中的路径。 例如，路径可能类似于 C:\Users\User1\Documents\WindowsPowerShell\Modules。

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.2
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.2
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>连接到 Microsoft StaffHub PowerShell 模块

1. 请运行以下命令：

    ```
    Connect-StaffHub
    ```

2. 系统提示时，登录作为全局管理员。

## <a name="related-topics"></a>相关主题

- [Microsoft StaffHub PowerShell 参考](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [将 Microsoft StaffHub 团队迁移到 Teams 中的排班](move-staffhub-teams-to-shifts-in-teams.md)
