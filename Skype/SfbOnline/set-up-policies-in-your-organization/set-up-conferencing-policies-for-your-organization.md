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
ms.openlocfilehash: d7bbcca81888487d54fa1a08eaf09b5462dc391f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776237"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a>为你的组织设置会议策略

会议是 Skype for Business Online 的重要部分：通过会议，多组用户可以在线集中在一起来查看幻灯片和视频、共享应用、交换文件以及进行通信与协作。
  
保持对会议和会议设置的控制非常重要。在某些情况下，可能存在安全问题：默认情况下，任何人（包括未经身份验证的用户）都可以加入会议，并保存在这些会议中分发的任何幻灯片或讲义。此外，可能还存在一些偶然的法律问题。例如，默认情况下，会议参与者可以在共享内容上进行注释;但是，在存档会议时，这些注释不会保存。如果您的组织需要保留所有电子通信的记录，您可能希望禁用注释。 
  
在 Skype for Business Online 中，通过使用会议策略管理会议。会议策略确定可在会议中使用的功能和功能，包括来自会议的所有内容，包括从会议到可参加会议的最大人数。可以在全局范围内或在每用户范围内配置会议策略。这在确定哪些功能将提供给哪些用户的情况下为管理员提供了巨大的灵活性。
  
策略设置可以在创建策略时进行配置，也可以使用**CsConferencingPolicy** cmdlet 修改现有策略的设置。
  
## <a name="set-your-conferencing-policies"></a>设置你的会议策略

> [!NOTE]
> 对于 Skype for Business Online 中的所有会议策略设置，必须使用 Windows PowerShell，并且**不能使用** **Skype for business 管理中心**。 
  
### <a name="verify-and-start-windows-powershell"></a>验证并启动 Windows PowerShell

- **检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**
    
    1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
        
    2. 通过在" _Windows PowerShell_"窗口中键入  **Get-Host** 来检查版本。
        
    3. 如果你没有版本3.0 或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)以下载 windows PowerShell 并将其更新到版本4.0。出现提示时，请重新启动计算机。
        
    4. 还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。
    
    如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)。
    
- **启动 Windows PowerShell 会话**
    
    1. From the **Start Menu** > **Windows PowerShell**.
        
    2. 在 " **Windows PowerShell** " 窗口中，通过运行以下内容连接到 Microsoft 365 或 Office 365：
        
        > [!NOTE]
        > [!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。

       ```PowerShell      
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   如果需要有关启动 Windows PowerShell 的详细信息，请参阅[在单个 Windows powershell 窗口中连接到所有 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)或[设置适用于 Windows powershell 的计算机](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a>在会议期间阻止文件传输和桌面共享

- 若要为这些设置创建新的策略，请运行：
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   有关[CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet 的详细信息，请参阅。
    
- 若要向组织中的所有用户授予您创建的新策略，请运行：
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   有关[CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet 的详细信息，请参阅。
    
  如果你已创建策略，你可以使用[CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet 对现有策略进行更改，然后使用[CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet 将设置应用到你的用户。
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a>阻止录制会议和阻止匿名会议参与者

- 若要为这些设置创建新的策略，请运行： 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   有关[CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet 的详细信息，请参阅。
    
- 若要将您创建的新策略授予 Amos 大理石，请运行：
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   有关[CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet 的详细信息，请参阅。
    
如果你已创建策略，你可以使用[CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet 对现有策略进行更改，然后使用[CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet 将设置应用到你的用户。
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a>阻止匿名参与者录制会议和外部用户保存会议内容

- 若要为这些设置创建新的策略，请运行：  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   有关[CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) cmdlet 的详细信息，请参阅。
    
- 若要为你的组织中的所有用户授予你创建的新策略，请运行：
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

有关[CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet 的详细信息，请参阅。
    
如果你已创建策略，你可以使用[CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) cmdlet 对现有策略进行更改，然后使用[CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) cmdlet 将设置应用到你的用户。
  
## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [可能希望使用 Windows PowerShell 管理 Office 365 的六个原因](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你同时为多个用户设置更改时。 通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相关主题
[创建自定义外部访问策略](create-custom-external-access-policies.md)

[阻止点到点文件传输](block-point-to-point-file-transfers.md)

[为你的组织设置客户端策略](set-up-client-policies-for-your-organization.md)

  
 
