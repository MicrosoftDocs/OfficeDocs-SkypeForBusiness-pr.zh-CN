---
title: 为你的组织设置客户端策略
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 客户端策略帮助确定可供用户使用的 Skype for Business Online 功能；例如，你可以为一些用户提供传输文件的权限，但拒绝其他用户拥有此权限。
ms.openlocfilehash: 5f5d0d0cb6f404c7c1bb26f763ba15a402db966fd07c4471d0d7ce115cfbf791
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282375"
---
# <a name="set-up-client-policies-for-your-organization"></a>为你的组织设置客户端策略

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

客户端策略帮助确定可供用户使用的 Skype for Business Online 功能；例如，你可以为一些用户提供传输文件的权限，但拒绝其他用户拥有此权限。
  
可以在创建策略时配置客户端策略设置，或者可以使用 **Set-CsClientPolicy** cmdlet 修改现有策略的设置。
  
## <a name="set-your-client-policies"></a>设置你的客户端策略

> [!NOTE]
> 对于 Skype for Business Online 中的所有客户端策略设置，必须使用 Windows PowerShell 并且不能 **使用** Skype for Business **管理中心**。 
  
### <a name="start-windows-powershell"></a>启动Windows PowerShell

> [!NOTE]
> Skype for Business Online 连接器目前是最新 Teams PowerShell 模块的一部分。 如果使用的是最新 Teams PowerShell 公共版本，则无需安装 Skype for Business Online 连接器。
1. 安装[Teams PowerShell 模块](/microsoftteams/teams-powershell-install)。
    
2. 打开Windows PowerShell命令提示符并运行以下命令： 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   如果需要有关启动 Windows PowerShell Windows PowerShell，请参阅在单个 Microsoft 365 窗口中连接所有 Microsoft 365 或[Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)服务Windows PowerShell或为计算机设置[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>禁用图释和状态通知，并阻止保存 VM

- 若要为这些设置创建新策略，请运行：
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  有关详细信息，请参阅 [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet。
    
- 若要向组织中所有用户授予你创建的新策略，请运行：
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  有关详细信息，请参阅 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet。
    
如果已创建策略，可以使用 [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet 更改现有策略，然后使用 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet 将设置应用到用户。
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>启用要在即时消息中可单击的 URL 或超链接

- 若要为这些设置创建新策略，请运行：
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  有关详细信息，请参阅 [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet。
    
- 若要向组织中所有用户授予你创建的新策略，请运行：
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  有关详细信息，请参阅 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet。
    
如果已创建策略，可以使用 [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet 更改现有策略，然后使用 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet 将设置应用到用户。
  
### <a name="prevent-showing-recent-contacts"></a>禁止显示最近的联系人

- 若要为这些设置创建新策略，请运行：
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  有关详细信息，请参阅 [New-CsClientPolicy](/powershell/module/skype/New-CsClientPolicy) cmdlet。
    
- 若要向 Amos Marble 授予创建的新策略，请运行：
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  有关详细信息，请参阅 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet。
    
  如果已创建策略，可以使用 [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) cmdlet 更改现有策略，然后使用 [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) cmdlet 将设置应用到用户。
  
## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用 Windows PowerShell，Microsoft 365管理Office 365 Skype for Business管理点，可在有多个任务需要执行时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [你可能希望使用 Windows PowerShell 管理Microsoft 365或Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell比仅使用 Microsoft 365 管理中心（例如，一次为许多用户进行设置更改时）在速度、简单性和工作效率方面具有许多优势。 通过以下主题了解这些优势：
    
  - [使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>相关主题
[创建自定义外部访问策略](create-custom-external-access-policies.md)

[阻止点到点文件传输](block-point-to-point-file-transfers.md)

[在组织中设置会议策略](set-up-conferencing-policies-for-your-organization.md)

  
