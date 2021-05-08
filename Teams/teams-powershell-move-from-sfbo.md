---
title: 从 Skype for Business Online 连接器移动到 Teams PowerShell 模块
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 了解如何从 Skype for Business Online 连接器移动到 Teams PowerShell 模块以管理Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5a2b502edc84c853a0a140a11f8c028b7c78aca6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094123"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>从 Skype for Business Online 连接器移动到 Teams PowerShell 模块

若要从使用 Skype for Business Online 连接器转移到 Teams PowerShell 模块来管理 Teams，需要更新现有的 PowerShell 脚本。 本文介绍如何进行此操作。

1. 安装 PowerShell 模块Teams最新版本。 有关步骤，请参阅[安装 Microsoft Teams Powershell。](teams-powershell-install.md)
2. 卸载 Skype For Business Online 连接器。 为此，请在"控制面板"中，转到"程序和功能"，选择"Skype for Business **Online"，Windows PowerShell** 模块"，然后选择"卸载 **"。** 
3. 在 PowerShell 脚本中，将 中引用的模块名称从 ```Import-Module``` 或 ```SkypeOnlineConnector``` 更改为 ```LyncOnlineConnector``` ```MicrosoftTeams``` 。

    例如，将 ```Import-Module -Name SkypeOnlineConnector``` 更改为 ```Import-Module -Name MicrosoftTeams``` 。
4. 使用 PowerShell Teams 2.0 或更高版本时，将 New-csOnlineSession 更改为 连接-MicrosoftTeams。 

```powershell
  # When using Teams PowerShell Module 1.1.6
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfbSession
   
   # When using Teams PowerShell Module 2.0 or later
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="related-topics"></a>相关主题

[安装 Microsoft Teams Powershell](teams-powershell-install.md)

[使用 Teams PowerShell Teams管理资源](teams-powershell-managing-teams.md)

[TeamsPowerShell 发行说明](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet 参考](/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet 参考](/powershell/skype/intro?view=skype-ps)