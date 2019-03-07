---
title: PowerShell 脚本示例-创建并分配邮件策略
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
description: 使用此 PowerShell 脚本在工作组中创建邮件策略，并将其分配给您的组织中的用户。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d65deff9f424fad8fed11d7b10cbe40ced387161
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30463041"
---
<a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell 脚本示例-创建并分配邮件策略
-------------------------------------------------------------------------

使用此 PowerShell 脚本创建的 Microsoft 团队中的邮件策略，并将其分配给用户。 

有关使用此 PowerShell 脚本的详细信息，请参阅[快速入门-团队教育版](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)。

如果你不了解 PowerShell 并需要入门帮助，请参阅 [Azure PowerShell 概述](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1)。


## <a name="sample-script"></a>示例脚本

````powershell
<#
.SYNOPSIS
This script creates a messaging policy in Teams and assigns it to users.
.DESCRIPTION
Use this script to create a messaging policy and assign it to users in your organization.
#>

$dataSetFilePath = "<csv file with user ids for newly provisioned students> "
 $dataSet = Import-Csv "$($dataSetFilePath)" -Header UserId –delimiter ","
 foreach($line in $dataSet)
 {
    $userId = $line.UserId
    Write-Host $userId
    Grant-CsTeamsMessagingPolicy -PolicyName "<<PolicyName for a policy created with Chat Off>>" -Identity $userId

 }
````


