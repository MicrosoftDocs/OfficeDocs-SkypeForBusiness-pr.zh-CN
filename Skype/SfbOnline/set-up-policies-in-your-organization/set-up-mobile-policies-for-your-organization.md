---
title: 为你的组织设置移动策略
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: 你可以设置你的用户如何在移动设备上使用 Skype for Business 应用连接到 Skype for Business Online，例如允许用户使用工作电话号码而不是移动电话号码在移动电话上拨打和接听电话的功能。 还需要使用移动策略来要求在拨打或接听电话时使用 Wi-Fi 连接。
ms.openlocfilehash: b0e2f7524f300733840159eacfcf27bb54f5e815
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100488"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>为你的组织设置移动策略

你可以设置你的用户如何在移动设备上使用 Skype for Business 应用连接到 Skype for Business Online，例如允许用户使用工作电话号码而不是移动电话号码在移动电话上拨打和接听电话的功能。 还需要使用移动策略来要求在拨打或接听电话时使用 Wi-Fi 连接。
  
可以在创建策略时配置移动策略设置，或者可以使用 **Set-CsMobilityPolicy** cmdlet 修改现有策略的设置。
  
## <a name="set-your-mobile-policies"></a>设置你的移动策略

> [!NOTE]
> 对于 Skype for Business Online 中所有移动策略设置，必须使用 Windows PowerShell 并且不能使用 Skype **for Business 管理中心**。 
  
### <a name="start-windows-powershell"></a>启动Windows PowerShell

> [!NOTE]
> Skype for Business Online 连接器当前是最新 Teams PowerShell 模块的一部分。 如果你使用的是最新的 Teams PowerShell 公共版本，则不需要安装 Skype for Business Online 连接器。
1. 安装 [Teams PowerShell 模块](/microsoftteams/teams-powershell-install)。
    
2. 打开 Windows PowerShell 命令提示符并运行以下命令： 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   如果需要有关启动 Windows PowerShell，请参阅在单个 Windows PowerShell 窗口中连接到所有[Microsoft 365 或 Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)服务或设置计算机[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
   
### <a name="require-a-wifi-connection-for-video-for-a-user"></a>要求用户进行视频操作时使用 WiFi 连接

- 若要为这些设置创建新策略，请运行：
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   有关详细信息，请参阅 [New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) cmdlet。
    
- 若要向组织中所有用户授予你创建的新策略，请运行：
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   有关详细信息，请参阅 [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet。
    
  如果已创建策略，可以使用 [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) cmdlet 更改现有策略，然后使用[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet 将设置应用到用户。
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>禁止用户使用 Skype for Business 应用

- 若要为这些设置创建新策略，请运行：
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  有关详细信息，请参阅 [New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) cmdlet。
    
- 若要向 Amos Marble 授予创建的新策略，请运行：  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   有关详细信息，请参阅 [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet。
    
  如果已创建策略，可以使用 [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) cmdlet 更改现有策略，然后使用 [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet 将设置应用到用户。
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>禁止用户使用移动设备拨打 IP 语音电话。

- 若要为这些设置创建新策略，请运行：
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   有关详细信息，请参阅 [New-CsMobilityPolicy](/powershell/module/skype/New-CsMobilityPolicy) cmdlet。
    
- 若要向组织中所有用户授予你创建的新策略，请运行：
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  有关详细信息，请参阅 [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet。
    
如果已创建策略，可以使用 [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) cmdlet 更改现有策略，然后使用[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) cmdlet 将设置应用到用户。
  
## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用 Windows PowerShell，当你有多个任务需要执行时，可以使用可以简化日常工作的单一管理点来管理 Microsoft 365 或 Office 365 和 Skype for Business Online。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [你可能希望使用 Office 365 Windows PowerShell Office 365 的六大原因](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell比使用 Microsoft 365 管理中心（例如，一次对许多用户进行设置更改时）具有许多速度、简单性和工作效率优势。 通过以下主题了解这些优势：
    
  - [使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>相关主题
[创建自定义外部访问策略](create-custom-external-access-policies.md)

[阻止点到点文件传输](block-point-to-point-file-transfers.md)

[为你的组织设置客户端策略](set-up-client-policies-for-your-organization.md)

[在组织中设置会议策略](set-up-conferencing-policies-for-your-organization.md)

  
