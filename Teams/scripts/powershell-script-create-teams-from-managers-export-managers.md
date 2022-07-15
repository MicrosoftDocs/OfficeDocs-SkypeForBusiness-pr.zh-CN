---
title: PowerShell 脚本示例 - 导出管理器及其直接报表
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: brandber
ms.service: msteams
audience: admin
description: 使用此 PowerShell 脚本可帮助为每个经理创建一个团队，并将其直接报表作为团队成员。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fbd1758c0de6d0cb7751b4a447e21ab386f823ba
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825666"
---
# <a name="powershell-script-sample---export-managers-and-their-direct-reports"></a>PowerShell 脚本示例 - 导出管理器及其直接报表

使用此 PowerShell 脚本为组织导出经理列表及其直接报表。 使用此脚本准备为每个经理创建一个人员经理团队，并将其直接报告作为团队成员。

若要了解此 PowerShell 脚本，请参阅 [“创建人员管理器团队](../create-manager-directs-teams.md)”。

如果你不了解 PowerShell 并需要入门帮助，请参阅 [Azure PowerShell 概述](/powershell/azure/overview)。

## <a name="export-managers-script"></a>Export-Managers脚本

```powershell
<#
.SYNOPSIS
  Name: Export-ManagersDirectsFromAAD.ps1
  The purpose of this sample script is to build a list of managers and direct reports to use with the New-TeamsFromManagers.ps1 to create a team for each people manager and their directs.

.DESCRIPTION
 This sample script create new Teams based on the tab delimited .txt file you provide of managers and direct reports. It assumes that DisplayName is not null.

.NOTES
  &copy; 2020 Microsoft Corporation. All rights reserved. This document is provided "as-is." Information and views expressed in this document, including URL and other Internet Web site references, may change without notice.

.EXAMPLE
  Export-ManagersDirectsFromAAD.ps1
#>

#Also create a type that validated the users licenses to ease the create-team burden
#also add checks to see if the types are appropriately in place.

#region Configurable Inputs
$OutputFile = "ExportedManagersDirects.txt"
#endregion

#region Data Model
class DirectReport {
    [string] $UserPrincipalName
}
class Manager {
    [ValidateNotNullOrEmpty()] [string] $UserPrincipalName
    [string] $DisplayName
    [System.Collections.ObjectModel.Collection[DirectReport]]$DirectReports

    Manager (){
        $this.DirectReports = New-Object -TypeName System.Collections.ObjectModel.Collection["DirectReport"]
    }
}
#endregion

#region Helper Functions
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}
#endregion

#region Script Execution
#Step 1: Retrieve AAD users - attribute filtering off DirectReport cannot be applied
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Starting to retrieve ALL Azure AD users."
$AllAADUsers = Get-AzureADUser -All $true -Filter "UserType eq 'Member' and AccountEnabled eq true"
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Retriving Azure AD Users Complete.. `n"

#Step 2: Iterate through users, identify Managers and Directs
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Starting to Retrieve Directs Reports"
$Managers = New-Object -TypeName System.Collections.ObjectModel.Collection["Manager"]
foreach ($user in $AllAADUsers) {
    $directs = Get-AzureADUserDirectReport -ObjectId $user.UserPrincipalName
        if ($null -ne $directs) {
            if ($user.DisplayName -ne "") {
                $manager = New-Object -TypeName Manager
                $manager.UserPrincipalName = $user.UserPrincipalName
                $manager.DisplayName = $user.DisplayName

                foreach ($direct in $directs) {
                    $directReport = New-Object -TypeName DirectReport
                    $directReport.UserPrincipalName = $direct.UserPrincipalName
                    $manager.DirectReports.Add($directReport)
                }
                $Managers.Add($manager)

            }
        Write-Host "$(Get-Timestamp) Info: Added Manager: $($manager.UserPrincipalName)"
        $i++
    }
}
Write-Host -ForegroundColor Green "$(Get-Timestamp) Info: Retriving Direct Reports Complete.. `n"

#Step 3: Output in tab delimited .txt format
$output = New-Object -TypeName System.Collections.ObjectModel.Collection["String"]
$header = "Name`tDisplayName`tDirects"
$output.Add($header)

foreach ($manager in $Managers) {
    [string] $directs = ""
    foreach ($direct in $manager.DirectReports)
    {
        $directs += $direct.UserPrincipalName + ','
    }
    $directs = $directs.Substring(0,$directs.Length-1)
    $row = "$($manager.UserPrincipalName)`t$($manager.DisplayName)`t$($directs)"
    $output.Add($row)
}

#If Output File already exists from a previous run, it will be replaced.
$testPath = Test-Path .\$($OutputFile)
if ($testPath) {
    Remove-Item .\$($OutputFile)
}

foreach ($line in $output) {
    $line | Out-File -FilePath .\$($OutputFile) -Append
}
Write-Host -ForegroundColor Green "$(Get-Timestamp) Exported tab delimited output to $($OutputFile). `n"
#endregion
```
