---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: 3d4ec38f0007460fa119e69eadc79cd9c51887ee
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2022
ms.locfileid: "64976011"
---
1. 安装 PowerShell 版本 7 或更高版本。 有关分步指南，请参阅在 [Windows 上安装 PowerShell](/powershell/scripting/install/installing-powershell-on-windows)。

1. 在管理员模式下运行 PowerShell。
1. 安装 Microsoft Graph PowerShell 模块。

    ```powershell
    Install-Module Microsoft.Graph
    Import-Module Microsoft.Graph
    ```

    验证其版本是否为 1.6.1 或更高版本。

    ```powershell
    Get-InstalledModule Microsoft.Graph 
    ```

1. 安装Teams预览版 PowerShell 模块。

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    验证它至少是版本 4.1.0，并且包含 Shifts 连接器 cmdlet。

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```

1. 如果运行脚本时出错，请将 PowerShell 设置为退出。

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. 允许脚本在Windows中运行。

    ```powershell
    Set-ExecutionPolicy bypass 
    ```