---
title: 使用 PowerShell 脚本更改信息屏障模式
description: 部署信息屏障后，请使用此 PowerShell 脚本将租户中所有组的模式从打开更新为隐式更新。
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.reviewer: smahadevan
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- tier2
- purview-compliance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63403c5e5ee495a7a110aa9239868fd6a9bb5803
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2022
ms.locfileid: "68047122"
---
# <a name="change-information-barriers-modes-with-a-powershell-script"></a>使用 PowerShell 脚本更改信息屏障模式

使用此 PowerShell 脚本更新租户中所有连接 Teams 的组的信息屏障 (IB) 模式。 部署信息屏障后，需要更新这些组的模式。 为启用 IB 之前预配的组分配 *开放* 模式。 在 *“打开* ”模式下，没有任何适用的 IB 策略。 启用 IB 后， *隐式* 会成为你创建的任何新组的默认模式。 但是，现有组仍保留 *开放* 模式配置。 运行此脚本以将这些现有组更改为 *隐式* 模式。

在此脚本中，你将使用 [Get-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup) cmdlet（位于 Exchange Online PowerShell 模块中）来更新模式。 若要详细了解如何使用 PowerShell 管理 Teams，请参阅 [Teams PowerShell 概述](./teams-powershell-overview.md)。

## <a name="sample-script"></a>示例脚本

你需要使用已分配为租户全局管理员角色的工作或学校帐户来运行此脚本。

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