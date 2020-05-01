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
ms.openlocfilehash: 748167dc8e03b53fc07611df0ff464d984fb5678
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951057"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>PowerShell 脚本示例 - 创建和分配消息传递策略

使用此 PowerShell 脚本在 Microsoft 团队中创建邮件策略，并将其分配给用户。 

有关使用此 PowerShell 脚本的详细信息，请参阅[快速入门-团队教育](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)版。

此脚本使用 Skype for Business Online PowerShell 模块中的[CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet。 请参阅[团队 PowerShell 概述](../teams-powershell-overview.md)以了解有关使用 PowerShell 管理团队的详细信息。


## <a name="before-you-start"></a>开始前

下载并安装[Skype For Business Online PowerShell 模块](https://www.microsoft.com/download/details.aspx?id=39366)，如果出现提示，请重新启动计算机。

若要了解详细信息，请参阅[管理 Office 365 PowerShell 的 Skype For Business Online](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。


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
> 你还可以使用批策略分配将消息策略分配给大型用户集。 有关详细信息，请参阅[为你的学校中的大型用户分配策略](../batch-policy-assignment-edu.md)，并[为团队中的用户分配策略](../assign-policies.md)。
