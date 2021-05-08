---
title: PowerShell 脚本示例 - 创建&消息传送策略
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: 使用此 PowerShell 脚本在 Teams消息策略并将其分配给组织的用户。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c665b96c0c44c2ea763c343bb2857d4c2b9dbb26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117270"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="47520-103">PowerShell 脚本示例 - 创建和分配消息传递策略</span><span class="sxs-lookup"><span data-stu-id="47520-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="47520-104">使用此 PowerShell 脚本在脚本中创建消息Microsoft Teams并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="47520-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="47520-105">有关使用此 PowerShell 脚本的信息，请参阅[快速入门 - Teams 教育。](../teams-quick-start-edu.yml)</span><span class="sxs-lookup"><span data-stu-id="47520-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](../teams-quick-start-edu.yml).</span></span>

<span data-ttu-id="47520-106">此脚本使用 Skype for Business Online PowerShell 模块中的[Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="47520-106">This script uses the [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet which is in the Skype for Business Online PowerShell module.</span></span> <span data-ttu-id="47520-107">请参阅[Teams PowerShell 概述](../teams-powershell-overview.md)，了解有关使用 PowerShell Teams管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="47520-107">See [Teams PowerShell overview](../teams-powershell-overview.md) to learn more about managing Teams using PowerShell.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="47520-108">开始前</span><span class="sxs-lookup"><span data-stu-id="47520-108">Before you start</span></span>

<span data-ttu-id="47520-109">下载并安装[Skype for Business Online PowerShell 模块](https://www.microsoft.com/download/details.aspx?id=39366)，然后在系统提示时重启计算机。</span><span class="sxs-lookup"><span data-stu-id="47520-109">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="47520-110">若要了解更多内容，[请参阅使用 Skype for Business PowerShell Office 365 Online。](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="47520-110">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="sample-script"></a><span data-ttu-id="47520-111">示例脚本</span><span class="sxs-lookup"><span data-stu-id="47520-111">Sample script</span></span>

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

> [!NOTE]
> <span data-ttu-id="47520-112">也可通过批处理策略分配将消息传递策略直接大规模分配给用户，或者将消息传递策略分配给用户作为其成员的组。</span><span class="sxs-lookup"><span data-stu-id="47520-112">You can also assign a messaging policy directly to users at scale through a batch policy assignment or to a group that the users are members of.</span></span> <span data-ttu-id="47520-113">有关详细信息，请参阅[为学校中的大量](../batch-group-policy-assignment-edu.md)用户分配策略和在[Teams。](../assign-policies.md)</span><span class="sxs-lookup"><span data-stu-id="47520-113">For more information see [Assign policies to large sets of users in your school](../batch-group-policy-assignment-edu.md) and [Assign policies to your users in Teams](../assign-policies.md).</span></span>