---
title: PowerShell 脚本示例 - Teams 部署清理
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: 使用此 PowerShell 脚本卸载 Teams 并删除用户的 Teams 文件夹。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95b7f12f9d7b531de2c50ba2de197f2f799916a2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117290"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a><span data-ttu-id="e7885-103">PowerShell 脚本示例 - Teams 部署清理</span><span class="sxs-lookup"><span data-stu-id="e7885-103">PowerShell script sample - Teams deployment clean up</span></span>

<span data-ttu-id="e7885-104">使用此脚本删除 Teams。</span><span class="sxs-lookup"><span data-stu-id="e7885-104">Use this script to remove Teams.</span></span> <span data-ttu-id="e7885-105">此脚本卸载 Teams 并删除用户的 Teams 文件夹。</span><span class="sxs-lookup"><span data-stu-id="e7885-105">This script uninstalls Teams and removes the Teams folder for a user.</span></span> <span data-ttu-id="e7885-106">针对计算机上安装 Teams 的每个用户配置文件运行此脚本。</span><span class="sxs-lookup"><span data-stu-id="e7885-106">Run this script for each user profile in which Teams was installed on a computer.</span></span>


## <a name="sample-script"></a><span data-ttu-id="e7885-107">示例脚本</span><span class="sxs-lookup"><span data-stu-id="e7885-107">Sample script</span></span>

````powershell
<#
.SYNOPSIS
This script uninstalls the Teams app and removes the Teams directory for a user.
.DESCRIPTION
Use this script to remove and clear the Teams app from a computer. Run this PowerShell script for each user profile in which Teams was installed on the computer. After you run this script for all user profiles, redeploy Teams.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams', 'Update.exe')

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

## <a name="related-topics"></a><span data-ttu-id="e7885-108">相关主题</span><span class="sxs-lookup"><span data-stu-id="e7885-108">Related topics</span></span>

- [<span data-ttu-id="e7885-109">使用 Microsoft Endpoint Configuration Manager 安装 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e7885-109">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>](../msi-deployment.md)
- [<span data-ttu-id="e7885-110">使用 Microsoft 365 应用部署 Teams</span><span class="sxs-lookup"><span data-stu-id="e7885-110">Deploy Teams with Microsoft 365 Apps</span></span>](/deployoffice/teams-install)