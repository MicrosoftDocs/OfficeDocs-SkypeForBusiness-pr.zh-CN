---
title: PowerShell 脚本示例 - 创建&消息传送策略
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: 使用此 PowerShell 脚本在 Teams创建消息传送策略并将其分配给组织的用户。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 323809b5a47168c67f2a7a01e45922c69fc248ba
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601117"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell 脚本示例 - 创建和分配消息传递策略

使用此 PowerShell 脚本在脚本中创建消息Microsoft Teams并将其分配给用户。 

有关使用此 PowerShell 脚本的信息，请参阅[快速入门 - Teams 教育版。](../teams-quick-start-edu.yml)

此脚本使用 Skype for Business Online PowerShell 模块中的[Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet。 请参阅[Teams PowerShell 概述](../teams-powershell-overview.md)，详细了解如何Teams PowerShell 管理应用程序。


## <a name="before-you-start"></a>开始前

下载并安装[Skype for Business Online PowerShell 模块](https://www.microsoft.com/download/details.aspx?id=39366)，然后在系统提示时重启计算机。

若要了解更多信息，请参阅使用[Skype for Business PowerShell Office 365 Online。](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

## <a name="sample-script"></a>示例脚本

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
> 也可通过批处理策略分配将消息传递策略直接大规模分配给用户，或者将消息传递策略分配给用户作为其成员的组。 有关详细信息，请参阅[为学校中的大量](../batch-group-policy-assignment-edu.md)用户分配策略和在 Teams 中[分配策略](../assign-policies.md)。