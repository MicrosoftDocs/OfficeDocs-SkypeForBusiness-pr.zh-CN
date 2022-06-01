---
title: PowerShell 脚本示例 - 创建&分配消息传送策略
author: serdars
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: 使用此 PowerShell 脚本在Teams中创建消息传送策略，并将其分配给组织中的用户。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 09254f9ed85f69551ee825dbeb8ae063a010f780
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823703"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell 脚本示例 - 创建和分配消息传递策略

使用此 PowerShell 脚本在Microsoft Teams中创建消息传送策略，并将其分配给用户。 

有关使用此 PowerShell 脚本的详细信息，请参阅[快速入门 - Teams 教育版](../teams-quick-start-edu.yml)。

此脚本使用 [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet，该 cmdlet 位于 Skype for Business Online PowerShell 模块中。 请参阅 [Teams PowerShell 概述](../teams-powershell-overview.md)，详细了解如何使用 PowerShell 管理Teams。


## <a name="before-you-start"></a>开始前

下载并安装 [Skype for Business Online PowerShell 模块](https://www.microsoft.com/download/details.aspx?id=54616)，然后在出现提示时重启计算机。

若要精简更多内容，请参阅[使用 Office 365 PowerShell 管理 Skype for Business Online](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

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
> 还可以通过批处理策略分配或用户是其成员的组，将消息传送策略直接分配给大规模用户。 有关详细信息，请参阅为[学校中的大量用户分配策略](../batch-group-policy-assignment-edu.md)，并在[Teams中为用户分配策略](../policy-assignment-overview.md)。