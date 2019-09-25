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
description: 了解如何安装并连接到 Microsoft StaffHub PowerShell 模块的预发布版本。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80f8f586d8a2a41d0d716e0821eb1f6d8d4bcbee
ms.sourcegitcommit: 6ba9eeb81b7d55ffc319d6d6658d0ecac83c2159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "37142030"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>安装 Microsoft StaffHub PowerShell 模块

> [!IMPORTANT]
> 2019年10月1日生效，Microsoft StaffHub 将停用。 我们正在将 StaffHub 功能构建到 Microsoft 团队中。 今天，团队包括 "倒班" 应用，用于计划管理，而其他功能将随着时间的推移而推出。 StaffHub 将停止为2019年10月1日的所有用户工作。 任何试图打开 StaffHub 的人都将显示一条消息，指导他们下载团队。 若要了解详细信息，请参阅[Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。  

使用本文中的步骤安装并连接到 Microsoft StaffHub PowerShell 模块的预发布版本。 你将需要此操作才能[将你的 StaffHub 团队移动到团队](move-staffhub-teams-to-shifts-in-teams.md)。

## <a name="install-the-prerelease-version-of-the-microsoft-staffhub-powershell-module"></a>安装 Microsoft StaffHub PowerShell 模块的预发布版本

1. 以管理员身份打开 Windows PowerShell 3.0 或更高版本。若要执行此操作，请单击 "**开始**"，键入**windows powershell**，右键单击 " **windows powershell**"，然后选择 "**以管理员身份运行**"。
    > [!NOTE]
    > 若要获取最新版本的 Windows PowerShell，请参阅[安装 Windows powershell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)。 
2. 运行以下内容安装 StaffHub PowerShell 模块的预发布版本：

    ```
    Install-Module -Name MicrosoftStaffHub -AllowPrerelease
    ```
3. 您可能会看到警告消息：

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

    键入`Y`，然后单击`Enter`。
 
4. 退出 Windows PowerShell。

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>连接到 Microsoft StaffHub PowerShell 模块

1. 请运行以下命令：

    ```
    Connect-StaffHub
    ```

2. 出现提示时，以全局管理员身份登录。

## <a name="related-topics"></a>相关主题

- [Microsoft StaffHub PowerShell 参考](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [将 Microsoft StaffHub 团队迁移到 Teams 中的排班](move-staffhub-teams-to-shifts-in-teams.md)
