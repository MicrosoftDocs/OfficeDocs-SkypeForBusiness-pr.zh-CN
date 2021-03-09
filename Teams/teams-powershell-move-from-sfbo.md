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
description: 了解如何从 Skype for Business Online 连接器移动到 Teams PowerShell 模块以管理 Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32029de1ec33ee89c8dba30d8368131b291fc3f8
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569078"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>从 Skype for Business Online 连接器移动到 Teams PowerShell 模块

若要从使用 Skype for Business Online 连接器转移到 Teams PowerShell 模块来管理 Teams，需要更新现有 PowerShell 脚本。 本文介绍如何进行此操作。

1. 安装最新的 Teams PowerShell 模块。 有关步骤，请参阅["安装 Microsoft Teams Powershell"。](teams-powershell-install.md)
2. 卸载 Skype for Business Online 连接器。 为此，请在"控制面板"中，转到"程序和功能"，选择 **"Skype for Business Online"，** 选择"Windows PowerShell模块"，然后选择"**卸载"。** 
3. 在 PowerShell 脚本中，更改从/向引用的 ```Import-Module``` ```SkypeOnlineConnector``` 模块 ```LyncOnlineConnector``` 名称 ```MicrosoftTeams``` 。

    例如，更改为 ```Import-Module -Name SkypeOnlineConnector``` ```Import-Module -Name MicrosoftTeams``` 。
4. 使用 Teams PowerShell 模块 2.0 或更高版本时，请将 New-csOnlineSession 更改为 Connect-MicrosoftTeams。 

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

[使用 Teams PowerShell 管理 Teams](teams-powershell-managing-teams.md)

[Teams PowerShell 发行说明](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet 参考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
