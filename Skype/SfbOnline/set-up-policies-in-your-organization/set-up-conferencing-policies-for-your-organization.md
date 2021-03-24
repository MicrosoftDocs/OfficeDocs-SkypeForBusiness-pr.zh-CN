---
title: 为你的组织设置会议策略
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
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
description: 会议是 Skype for Business Online 的重要部分：通过会议，多组用户可以在线集中在一起来查看幻灯片和视频、共享应用、交换文件以及进行通信与协作。
ms.openlocfilehash: f4c8831408ed5c17073456306c0f48add73161ff
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100518"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a>为你的组织设置会议策略

会议是 Skype for Business Online 的重要部分：通过会议，多组用户可以在线集中在一起来查看幻灯片和视频、共享应用、交换文件以及进行通信与协作。
  
务必要维护对会议的控制和会议设置。 在有些情况下，可能会有安全问题：默认情况下，任何人（包括未经身份验证的用户）都可以参与会议，并保存在那些会议期间分发的任何幻灯片或讲义。 此外，偶尔可能有法律问题。 例如，默认情况下，允许会议参与者对共享内容进行批注;但是，存档会议时不会保存这些批注。 如果你的组织需要保留所有电子通信记录，你可能希望禁用批注。 
  
在 Skype for Business Online 中，会议使用会议策略进行管理。 会议策略确定可以在会议中使用的特性和功能，包括从会议是否可以包括 IP 音频和视频到可以参加会议的最大人数等所有内容。 可以按全局范围或单个用户范围来配置会议策略。 这为管理员在决定哪些功能可供哪些用户使用时提供了极大的灵活性。
  
可以在创建策略时配置策略设置，或者可以使用 **Set-CsConferencingPolicy** cmdlet 修改现有策略的设置。
  
## <a name="set-your-conferencing-policies"></a>设置你的会议策略

> [!NOTE]
> 对于 Skype for Business Online 中的所有会议策略设置，必须使用 Windows PowerShell 并且不能使用 **Skype for Business 管理中心**。 

### <a name="start-windows-powershell"></a>启动Windows PowerShell

 > [!Note]
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
      
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a>在会议期间阻止文件传输和桌面共享

- 若要为这些设置创建新策略，请运行：
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   有关详细信息，请参阅 [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet。
    
- 若要向组织中所有用户授予你创建的新策略，请运行：
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   有关详细信息，请参阅 [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet。
    
  如果已创建策略，可以使用 [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet 更改现有策略，然后使用[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet 将设置应用到用户。
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a>阻止录制会议并防止匿名会议参与者

- 若要为这些设置创建新策略，请运行： 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   有关详细信息，请参阅 [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet。
    
- 若要向 Amos Marble 授予创建的新策略，请运行：
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   有关详细信息，请参阅 [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet。
    
如果已创建策略，可以使用 [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet 更改现有策略，然后使用 [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet 将设置应用到用户。
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a>阻止匿名参与者录制会议和外部用户保存会议内容

- 若要为这些设置创建新策略，请运行：  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   有关详细信息，请参阅 [New-CsConferencingPolicy](/powershell/module/skype/New-CsConferencingPolicy) cmdlet。
    
- 若要向组织中所有用户授予你创建的新策略，请运行：
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

有关详细信息，请参阅 [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet。
    
如果已创建策略，可以使用 [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) cmdlet 更改现有策略，然后使用[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) cmdlet 将设置应用到用户。
  
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

  
