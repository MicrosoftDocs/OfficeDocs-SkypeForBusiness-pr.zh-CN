---
title: PowerShell 脚本示例 - 创建&消息传送策略
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: 使用此 PowerShell 脚本在 Teams 中创建消息传送策略并将其分配给组织的用户。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e3d1fa3ebe45785c088852c518ac5490263fa6aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804652"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell 脚本示例 - 创建和分配消息传递策略

使用此 PowerShell 脚本在 Microsoft Teams 中创建消息传送策略并将其分配给用户。 

有关使用此 PowerShell 脚本的信息，请参阅[快速入门 - Teams 教育。](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)

此脚本使用 Skype for Business Online PowerShell 模块中的 [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet。 请参阅 [Teams PowerShell 概述](../teams-powershell-overview.md) ，了解有关使用 PowerShell 管理 Teams 的更多内容。


## <a name="before-you-start"></a>开始前

下载并安装 [Skype for Business Online PowerShell 模块](https://www.microsoft.com/download/details.aspx?id=39366)，然后在系统提示时重启计算机。

若要了解更多内容，请参阅["使用 Office 365 PowerShell 管理 Skype for Business Online"。](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

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
> 还可以通过批处理策略分配将消息传递策略直接大规模分配给用户，或者将消息传递策略分配给用户作为其成员的组。 有关详细信息，请参阅["为学校中的大量](../batch-group-policy-assignment-edu.md)用户分配策略"和"在 Teams 中[为用户分配策略"。](../assign-policies.md)
