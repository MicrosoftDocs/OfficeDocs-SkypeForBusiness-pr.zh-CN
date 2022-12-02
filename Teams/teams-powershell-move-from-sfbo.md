---
title: 从 Skype for Business Online Connector 迁移到 Teams PowerShell 模块
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 了解如何从 Skype for Business Online Connector 迁移到 Teams PowerShell 模块以管理 Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 648ce1fb69f9e1641840f2e4b92acc1b98f4bbe8
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242286"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>从 Skype for Business Online Connector 迁移到 Teams PowerShell 模块

Teams PowerShell 模块提供了一组完整的 cmdlet，用于直接从 PowerShell 命令行管理 Teams。 管理员不需要 Skype For Business Online Connector 进行 Teams 管理。

> [!NOTE]
> Teams 管理员通过消息中心帖子 (MC244740 收到通知，日期为 2021 年 3 月 16 日;MC250940，日期为 2021 年 4 月 16 日，) 有关此更改。
>
> Teams PowerShell 模块使用新式身份验证，但基础 Windows 远程管理 (WinRM) 客户端必须配置为允许基本身份验证。 有关如何为基本身份验证启用 WinRM 的说明，请参阅[下载并安装Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1)。

## <a name="how-to-migrate"></a>如何迁移

从使用 Skype for Business Online Connector 迁移到 Teams PowerShell 模块非常简单。 以下步骤说明如何执行此操作。

1. 安装最新的 Teams PowerShell 模块。 有关步骤，请参阅[安装 Microsoft Teams PowerShell](teams-powershell-install.md)。

2. 卸载 Skype for Business Online 连接器。 为此，请在控制面板转到 **“程序和功能**”，选择“**Skype for Business联机”，Windows PowerShell模块**，然后选择“**卸载**”。

3. 在 PowerShell 脚本中，从 更改中 ```Import-Module``` 引用的模块名称

    `SkypeOnlineConnector` 或 `LyncOnlineConnector` 更改为 `MicrosoftTeams`。

    例如，将 更改为 `Import-Module -Name SkypeOnlineConnector` `Import-Module -Name MicrosoftTeams`。

4. 使用 Teams PowerShell 模块 2.0 或更高版本时，请更新引用 的`New-CsOnlineSession``Connect-MicrosoftTeams`脚本。 `Import-PsSession`不再需要建立Skype for Business联机远程 PowerShell 会话，因为使用 `Connect-MicrosoftTeams`时会隐式完成。

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

[使用 Teams PowerShell 管理 Teams](teams-powershell-managing-teams.md)

[Teams PowerShell 发行说明](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet 参考](/powershell/teams/)

[Skype for Business cmdlet 参考](/powershell/skype/intro)
