---
title: PowerShell 脚本示例 - 创建和分配消息传递策略
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: 使用此 PowerShell 脚本在团队中创建邮件策略，并将其分配给组织中的用户。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c1dbd4dfa470f8ed02c83e48603dc2647fdc90b3
ms.sourcegitcommit: 4ee9835282e1440d03abc6dbcd172bc20c5b3015
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2020
ms.locfileid: "43096977"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="e665c-103">PowerShell 脚本示例 - 创建和分配消息传递策略</span><span class="sxs-lookup"><span data-stu-id="e665c-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="e665c-104">使用此 PowerShell 脚本在 Microsoft 团队中创建邮件策略，并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="e665c-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="e665c-105">有关使用此 PowerShell 脚本的详细信息，请参阅[快速入门-团队教育](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)版。</span><span class="sxs-lookup"><span data-stu-id="e665c-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="e665c-106">如果你不了解 PowerShell 并需要入门帮助，请参阅 [Azure PowerShell 概述](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1)。</span><span class="sxs-lookup"><span data-stu-id="e665c-106">If you're new to PowerShell and need help getting started, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span></span>


## <a name="before-you-start"></a><span data-ttu-id="e665c-107">开始前</span><span class="sxs-lookup"><span data-stu-id="e665c-107">Before you start</span></span>
<span data-ttu-id="e665c-108">下载并安装[Skype For Business Online 连接器模块](https://www.microsoft.com/download/details.aspx?id=39366)，如果出现提示，请重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="e665c-108">Download and install the [Skype for Business Online Connector module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="e665c-109">查看有关详细信息，请查看[管理 Office 365 PowerShell 的 Skype For Business Online](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="e665c-109">View [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) for more.</span></span>


## <a name="sample-script"></a><span data-ttu-id="e665c-110">示例脚本</span><span class="sxs-lookup"><span data-stu-id="e665c-110">Sample script</span></span>

```powershell
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
```


