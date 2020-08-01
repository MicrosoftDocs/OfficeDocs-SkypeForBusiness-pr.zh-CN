---
title: PowerShell 脚本示例-创建 & 分配消息策略
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
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 318a430f6f59cbb28ffeda4336c36ae07533615b
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533737"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="a4afa-103">PowerShell 脚本示例 - 创建和分配消息传递策略</span><span class="sxs-lookup"><span data-stu-id="a4afa-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="a4afa-104">使用此 PowerShell 脚本在 Microsoft 团队中创建邮件策略，并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="a4afa-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="a4afa-105">有关使用此 PowerShell 脚本的详细信息，请参阅[快速入门-团队教育](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)版。</span><span class="sxs-lookup"><span data-stu-id="a4afa-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="a4afa-106">此脚本使用 Skype for Business Online PowerShell 模块中的[CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a4afa-106">This script uses the [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet which is in the Skype for Business Online PowerShell module.</span></span> <span data-ttu-id="a4afa-107">请参阅[团队 PowerShell 概述](../teams-powershell-overview.md)以了解有关使用 PowerShell 管理团队的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a4afa-107">See [Teams PowerShell overview](../teams-powershell-overview.md) to learn more about managing Teams using PowerShell.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="a4afa-108">开始前</span><span class="sxs-lookup"><span data-stu-id="a4afa-108">Before you start</span></span>

<span data-ttu-id="a4afa-109">下载并安装[Skype For Business Online PowerShell 模块](https://www.microsoft.com/download/details.aspx?id=39366)，如果出现提示，请重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="a4afa-109">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="a4afa-110">若要了解详细信息，请参阅[管理 Office 365 PowerShell 的 Skype For Business Online](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a4afa-110">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="sample-script"></a><span data-ttu-id="a4afa-111">示例脚本</span><span class="sxs-lookup"><span data-stu-id="a4afa-111">Sample script</span></span>

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
> <span data-ttu-id="a4afa-112">你还可以通过批处理策略分配将消息策略直接分配给用户，或者将消息策略分配给用户是其成员的组。</span><span class="sxs-lookup"><span data-stu-id="a4afa-112">You can also assign a messaging policy directly to users at scale through a batch policy assignment or to a group that the users are members of.</span></span> <span data-ttu-id="a4afa-113">有关详细信息，请参阅[为你的学校中的大型用户分配策略](../batch-group-policy-assignment-edu.md)，并[为团队中的用户分配策略](../assign-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a4afa-113">For more information see [Assign policies to large sets of users in your school](../batch-group-policy-assignment-edu.md) and [Assign policies to your users in Teams](../assign-policies.md).</span></span>
