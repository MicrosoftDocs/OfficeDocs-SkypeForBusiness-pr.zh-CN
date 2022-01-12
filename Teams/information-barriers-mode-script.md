---
title: 使用 PowerShell 脚本更改信息屏障模式
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.reviewer: smahadevan
ms.service: msteams
audience: admin
description: 部署信息屏障后使用此 PowerShell 脚本，将租户中所有组的模式从开放模式更新为隐式模式。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3030f40ed61eb2e0e86967132d9575de8334a6c6
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767489"
---
# <a name="change-information-barriers-modes-with-a-powershell-script"></a>使用 PowerShell 脚本更改信息屏障模式

使用此 PowerShell 脚本更新租户中所有 (连接) 组在 IB Teams模式的信息屏障。 部署信息屏障后，需要更新这些组的模式。 在启用 IB 之前预配的组分配有 *打开模式。* 在 *开放* 模式下，没有任何适用的 IB 策略。 启用 IB 后， *隐式* 将成为你创建的任何新组的默认模式。 但是，现有组仍保留 *开放* 模式配置。 运行此脚本，将这些现有组更改为 *隐式* 模式。

在此脚本中，将使用 PowerShell 模块Exchange Online [Get-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) cmdlet 来更新模式。 若要了解有关使用 PowerShell 管理Teams，请参阅[powerShell Teams概述](./teams-powershell-overview.md)。

## <a name="sample-script"></a>示例脚本

需使用分配给租户的工作或学校帐户全局管理员角色运行此脚本。

```powershell
<#
.SYNOPSIS
This script updates the information barrier mode for all Teams-connected groups in your tenant at the same time.
.DESCRIPTION
Use this script to update the info barrier mode from open to implicit across the groups in your tenant.
#>

$teams = Get-UnifiedGroup -Filter {ResourceProvisioningOptions -eq "Team"} -ResultSize Unlimited

Write-Output ([string]::Format("Number of Teams = {0}", @($teams).Length))

$teamsToUpdate = New-Object System.Collections.ArrayList

foreach($team in $teams)
{
  if ($team.InformationBarrierMode -eq "Open")
  {
    $teamsToUpdate.Add($team.ExternalDirectoryObjectId) | out-null
  }
}

Write-Output ([string]::Format("Number of Teams to be backfilled = {0}", @($teamsToUpdate).Length))

$outfile = "BackfillFailedTeams.csv"

if (!(Test-Path "$outfile"))
{
  $newcsv = {} | Select "ExternalDirectoryObjectId", "ExceptionDetails" | Export-Csv $outfile -NoTypeInformation  
}
else
{
  $dateTime = Get-Date
  $newEntry = "{0},{1}" -f "New session started", $dateTime
  $newEntry | add-content $outfile
}

$SuccessfullyBackfilledGroup = 0

for($i = 0; $i -lt @($teamsToUpdate).Length; $i++)
{
  Invoke-Command { Set-UnifiedGroup $teamsToUpdate[$i] -InformationBarrierMode "Implicit" } -ErrorVariable ErrorOutput

  if ($ErrorOutput)
  {
    # saving the errors in a csv file
    $errorBody = $ErrorOutput[0].ToString() -replace "`n"," " -replace "`r"," " -replace ",", " "
    $newEntry = "{0},{1}" -f $teamsToUpdate[$i].ToString(), '"' + $errorBody + '"'
    $newEntry | add-content $outfile
  }
  else
  {
    $SuccessfullyBackfilledGroup++
  }

  if (($i+1) % 100 -eq 0)
  {
    # print the number of teams backfilled after the batch of 100 updates
    Write-Output ([string]::Format("Number of Teams processed= {0}", $i+1)) 
  }
}

Write-Output ([string]::Format("Backfill completed. Groups backfilled: {0}, Groups failed to backfill: {1}", $SuccessfullyBackfilledGroup, @($teamsToUpdate).Length - $SuccessfullyBackfilledGroup))

if (!($SuccessfullyBackfilledGroup -eq @($teamsToUpdate).Length))
{
  Write-Output ([string]::Format("Check the failed teams in BackfillFailedTeams.csv, retry to backfill the failed teams.")) 
}

```