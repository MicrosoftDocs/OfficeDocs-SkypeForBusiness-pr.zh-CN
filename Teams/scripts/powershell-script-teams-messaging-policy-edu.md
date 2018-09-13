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
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 399cc6cf20554cd8ab23e6d75b66b2d6251e46de
ms.sourcegitcommit: 31918f51e8220950af6437a16d8beeb637fba2b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "23961890"
---
<a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="6f979-103">PowerShell 脚本示例-创建并分配邮件策略</span><span class="sxs-lookup"><span data-stu-id="6f979-103">PowerShell script sample - Create and assign a messaging policy</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="6f979-104">使用此 PowerShell 脚本创建的 Microsoft 团队中的邮件策略，并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="6f979-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="6f979-105">有关使用此 PowerShell 脚本的详细信息，请参阅[快速入门-团队教育版](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)。</span><span class="sxs-lookup"><span data-stu-id="6f979-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="6f979-106">如果你不了解 PowerShell 并需要入门帮助，请参阅 [Azure PowerShell 概述](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1)。</span><span class="sxs-lookup"><span data-stu-id="6f979-106">If you're new to PowerShell and need help getting started, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span></span>


## <a name="sample-script"></a><span data-ttu-id="6f979-107">示例脚本</span><span class="sxs-lookup"><span data-stu-id="6f979-107">Sample script</span></span>

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


