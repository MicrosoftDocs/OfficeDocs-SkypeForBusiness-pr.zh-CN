---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: c612f8d8e0f48249d9eabe19c5ae7513b0ae9d75
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593636"
---
1. 安装 PowerShell 版本 7 或更高版本。 有关分步指南，请参阅[在 Windows 上安装 PowerShell](/powershell/scripting/install/installing-powershell-on-windows)。

1. 在管理员模式下运行 PowerShell。
1. 安装 Microsoft Graph PowerShell 模块。

    ```powershell
    Install-Module Microsoft.Graph
    Import-Module Microsoft.Graph
    ```

    验证其版本为 1.6.1 或更高版本。

    ```powershell
    Get-InstalledModule Microsoft.Graph 
    ```

1. 安装 Teams 预览版 PowerShell 模块。

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    验证其版本是否至少为 4.1.0，并包含 Shifts 连接器 cmdlet。

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```
 
1. 安装 MSAL PowerShell 模块。

    ```powershell
    Install-Module -Name MSAL.PS
    Import-Module MSAL.PS
    ```

1. 如果运行脚本时发生错误，将 PowerShell 设置为退出。

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. 允许脚本在 Windows。

    ```powershell
    Set-ExecutionPolicy bypass 
    ```