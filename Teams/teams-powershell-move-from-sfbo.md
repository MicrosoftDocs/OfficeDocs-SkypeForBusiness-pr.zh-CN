---
title: 从 Skype for Business Online 连接器迁移到 Teams PowerShell 模块
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
ms.openlocfilehash: cdd6460e6a17a15193104a0871a57fa6dbff8105
ms.sourcegitcommit: 70c07a6b1be81681eec32a89872e2218d70c514d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2021
ms.locfileid: "58866354"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>从 Skype for Business Online 连接器迁移到 Teams PowerShell 模块

TeamsPowerShell 模块提供一组完整的 cmdlet，用于Teams PowerShell 命令行管理数据。 管理员无需为Skype For Business Online 连接器Teams管理。

> [!NOTE]
> Teams 2021 年 3 月 16 日 (MC244740 消息中心发布消息通知管理员;MC250940，日期为 2021 年 4 月 16) 此更改。
>
> TeamsPowerShell 模块使用新式身份验证，Windows WinRM (客户端) 基础远程管理"，以允许基本身份验证。 有关如何[启用](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1)WinRM Windows PowerShell身份验证的说明，请参阅下载并安装。

## <a name="how-to-migrate"></a>如何迁移

从使用 Skype for Business Online 连接器迁移到 Teams PowerShell 模块非常简单。 以下步骤介绍了如何这样做。

1. 安装 PowerShell 模块Teams最新版本。 有关步骤，请参阅[安装 Microsoft Teams PowerShell。](teams-powershell-install.md)

2. 卸载 Skype For Business Online 连接器。 为此，请在"控制面板"中转到"程序和功能"，选择"Skype for Business Online"，Windows PowerShell"模块 **"，** 然后选择"卸载 **"。**

3. 在 PowerShell 脚本中，更改 从 中引用的模块 ```Import-Module``` 名称

    `SkypeOnlineConnector` 或 `LyncOnlineConnector` `MicrosoftTeams` 。

    例如，将 `Import-Module -Name SkypeOnlineConnector` 更改为 `Import-Module -Name MicrosoftTeams` 。

4. 使用 powerShell Teams 2.0 或更高版本时，请更新引用 的 `New-CsOnlineSession` 脚本 `Connect-MicrosoftTeams` 。 `Import-PsSession`不再需要建立一个Skype for Business远程 PowerShell 会话，因为使用 时，该会话是隐式的 `Connect-MicrosoftTeams` 。

    ```powershell
       # When using the Skype for Business online connector
         
         # Establishing a session
         Import-Module SkypeOnlineConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session 
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # When using Teams PowerShell Module 2.0 or later
       
         # Establishing a session
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session  
         Disconnect-MicrosoftTeams
    ```

## <a name="related-topics"></a>相关主题

[安装 Microsoft Teams PowerShell](teams-powershell-install.md)

[使用 Teams PowerShell Teams管理资源](teams-powershell-managing-teams.md)

[TeamsPowerShell 发行说明](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet 参考](/powershell/teams/?view=teams-ps)

[Skype for Business cmdlet 参考](/powershell/skype/intro?view=skype-ps)
