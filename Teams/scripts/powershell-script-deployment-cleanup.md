---
title: PowerShell 脚本示例 - Teams 部署清理
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: 使用此 PowerShell 脚本卸载 Teams 并删除用户的 Teams 文件夹。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d7875cb01b928567d5883f36e21eb2f0de0bccf6
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825686"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a>PowerShell 脚本示例 - Teams 部署清理

使用此脚本删除 Teams。 此脚本卸载 Teams 并删除用户的 Teams 文件夹。 为计算机上安装 Teams 的每个用户配置文件运行此脚本。


## <a name="sample-script"></a>示例脚本

````powershell
<#
.SYNOPSIS
This script uninstalls the Teams app and removes the Teams directory for a user.
.DESCRIPTION
Use this script to remove and clear the Teams app from a computer. Run this PowerShell script for each user profile in which Teams was installed on the computer. After you run this script for all user profiles, redeploy Teams.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($TeamsPath, 'Update.exe')

try
{
    if ([System.IO.File]::Exists($TeamsUpdateExePath)) {
        Write-Host "Uninstalling Teams process"

        # Uninstall app
        $proc = Start-Process $TeamsUpdateExePath "-uninstall -s" -PassThru
        $proc.WaitForExit()
    }
    Write-Host "Deleting Teams directory"
    Remove-Item –path $TeamsPath -recurse
}
catch
{
    Write-Output "Uninstall failed with exception $_.exception.message"
    exit /b 1
}

````

## <a name="related-topics"></a>相关主题

- [使用 Microsoft Endpoint Configuration Manager 安装 Microsoft Teams](../msi-deployment.md)
- [使用Microsoft 365 应用版部署 Teams](/deployoffice/teams-install)
