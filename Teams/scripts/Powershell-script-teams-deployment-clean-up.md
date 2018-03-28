---
title: PowerShell 脚本示例-协助 Microsoft 小组部署清理
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
description: 使用此 PowerShell 脚本在 Teams 中创建公司范围的公共团队。
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 1466a08d493538eadb6cd2bfc2f50ac15acb0fa7
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a><span data-ttu-id="32a6d-103">PowerShell 脚本示例-Microsoft 小组部署清理</span><span class="sxs-lookup"><span data-stu-id="32a6d-103">PowerShell Script Sample - Microsoft Teams deployment clean up</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="32a6d-104">此 PowerShell 脚本可用于从目标 machines\users Microsoft 小组清理。</span><span class="sxs-lookup"><span data-stu-id="32a6d-104">This PowerShell script can be leveraged for the cleanup of Microsoft Teams from target machines\users.</span></span> <span data-ttu-id="32a6d-105">它应为每个用户在目标计算机上执行。</span><span class="sxs-lookup"><span data-stu-id="32a6d-105">It should be executed for every user on a targeted machine.</span></span> 


## <a name="sample-script"></a><span data-ttu-id="32a6d-106">示例脚本</span><span class="sxs-lookup"><span data-stu-id="32a6d-106">Sample script</span></span>

````powershell
<#
.SYNOPSIS
This script allows you to uninstall the Microsoft Teams app and remove Teams directory for a user.
.DESCRIPTION
Use this script to clear the installed Microsoft Teams application. Run this PowerShell script for each user profile for which the Teams App was installed on a machine. After the PowerShell has executed on all user profiles, Teams can be redeployed.
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


