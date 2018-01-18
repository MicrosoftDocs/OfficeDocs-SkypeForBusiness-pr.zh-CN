---
title: "设置您的组织的会议策略"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "会议是 Skype for Business Online 的重要部分：通过会议，多组用户可以在线集中在一起来查看幻灯片和视频、共享应用、交换文件以及进行通信与协作。"
ms.openlocfilehash: 6ccfdd3e5153a7b22d26fb492690da0e476fe9ee
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-conferencing-policies-for-your-organization"></a>设置您的组织的会议策略

会议是 Skype for Business Online 的重要部分：通过会议，多组用户可以在线集中在一起来查看幻灯片和视频、共享应用、交换文件以及进行通信与协作。
  
很重要的会议和会议设置的控制。在某些情况下，可能有安全方面的考虑： 默认情况下，任何人，包括未经授权的用户可以参与会议并保存的任何幻灯片或在这些会议期间分发的讲义。此外，可能会有偶尔的法律问题。例如，默认情况下，会议参与者允许对共享的内容; 使注释不过，会议存档时，不保存这些批注。如果您的组织需要保留所有的电子通信的记录，您可能要禁用注释。 
  
在 Skype 的在线业务，通过会议策略管理会议。会议策略确定的特性和功能，可在会议中，包括从会议可以包括 IP 音频和视频最大数量的人员可以出席会议。在全局范围内或每个用户范围，则可以配置会议策略。这为管理员提供很强的灵活性为决定哪些功能会对可用的用户时。
  
策略设置可以配置在创建策略时，也可以使用**一组 CsConferencingPolicy** cmdlet 来修改现有的策略设置。
  
## <a name="set-your-conferencing-policies"></a>设置你的会议策略

> [!NOTE]
> 对于所有会议策略中设置的 Skype 的在线业务，您必须都使用 Windows PowerShell 并且您都**不能都使用** **Skype 的业务管理中心**。 
  
### <a name="verify-and-start-windows-powershell"></a>验证并启动 Windows PowerShell

- **检查正在运行的是 Windows PowerShell 3.0 版本或更高版本**
    
1. 若要验证正在运行版本 3.0 或更高: **「 开始 」 菜单** > **Windows PowerShell**。
    
2. 通过在" **Windows PowerShell**"窗口中键入  _Get-Host_ 来检查版本。
    
3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。
    
4. 还需要安装 Skype for Business Online 的 Windows PowerShell 模块，才可创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。可访问[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)，从 Microsoft 下载中心下载此模块，此模块仅在 64 位计算机上受支持。出现提示时，请重启计算机。
    
    如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。
    
- **启动 Windows PowerShell 会话**
    
1. 从**「 开始 」 菜单** > **Windows PowerShell**。
    
2. 在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：
    
    > [!NOTE]
    > [!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  如果希望在启动 Windows PowerShell 的详细信息，请参阅[连接到一个 Windows PowerShell 窗口中的所有 Office 365 提供服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)或[连接到使用 Windows PowerShell 在线业务 Skype](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx)。
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a>在会议期间阻止文件传输和桌面共享

- 若要创建新的策略，这些设置，请运行：
> 
  ```
  New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
  ```
  请参阅详细信息[新建 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet。
    
- 若要授予您组织中的所有用户创建新的策略，请运行：
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
  ```
  请参阅详细信息[授予 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet。
    
  如果您已经创建一个策略，可以使用[一组 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet 可以更改现有的策略，并将[授予 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet 将设置应用于您的用户。
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a>阻止的会议记录，并防止匿名会议参与者

- 若要创建新的策略，这些设置，请运行： 
> 
  ```
  New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
  ```
请参阅详细信息[新建 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet。
    
- 若要创建新策略授予 Amos 大理石，运行：
> 
  ```
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
  ```
请参阅详细信息[授予 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet。
    
如果您已经创建一个策略，可以使用[一组 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet 可以更改现有的策略，并将[授予 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet 将设置应用于您的用户。
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a>阻止匿名参与者录制会议和外部用户保存会议内容

- 若要创建新的策略，这些设置，请运行：  
> 
  ```
  New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
  ```
请参阅详细信息[新建 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) cmdlet。
    
- 若要授予组织中为所有用户都创建新策略，请运行：
    
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
  ```

请参阅详细信息[授予 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet。
    
如果您已经创建一个策略，可以使用[一组 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) cmdlet 可以更改现有的策略，并将[授予 CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) cmdlet 将设置应用于您的用户。
  
## <a name="want-to-know-more-about-windows-powershell"></a>要了解有关 Windows PowerShell 的详细信息？

- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为何想使用 Windows PowerShell 管理 Office 365 的 6 个理由）](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相关主题
[创建自定义的外部访问策略](create-custom-external-access-policies.md)

[块的点对点文件传输](block-point-to-point-file-transfers.md)

[设置您的组织的客户端策略](set-up-client-policies-for-your-organization.md)