---
title: 将的电话号码包括在邀请
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: ae0f26c02bef1262b54cd509f9e539ef68aec112
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="set-the-phone-numbers-included-on-invites"></a>将的电话号码包括在邀请

Office 365 中的音频会议使组织中的用户创建 Skype 业务和 Microsoft 小组会议，然后允许用户拨入到那些使用电话的会议。 Office 365 中您可以使用 Microsoft 音频会议桥或由经认可的音频会议提供商 (ACP) 承载第三方音频会议桥的选择。
  
> [!NOTE]
> 没有资源包含音频会议的所有拨入号码的列表。 如果您希望看到如果有可用的拨入电话号码在您的区域或国家/地区，使用**Skype 业务管理中心的** > **语音** > **的电话号码**，单击**添加**，然后**新的服务编号**. 对于**国家/地区**，请**国家/地区中使用的列表**和**城市**筛选 > 而且，如果您正在寻找免费服务收费电话号码，选择**免费**从**国家/地区**列表。
  
会议桥提供为您的组织的拨入电话号码组。 所有这些可以用来参加会议，会议组织者创建，但是您可以选择哪些文件将包括在其会议的邀请。
  
> [!NOTE]
> 可以有一个免费电话和邀请的会议组织者，在一个免费电话号码的最多，但还有底部打开的完整列表，可用于参加会议的所有拨入电话号码中的每个会议邀请中的链接。 
  
## <a name="setting-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>会议组织者设置的默认拨入电话号码

1. 使用你的工作或学校帐户登录 Office 365。
    
2. Choose **Admin centers** > **Skype for Business**.
    
3. 选择" **用户**"。
    
    ![显示业务管理中心为 Skype 中选择用户](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. 选择您要编辑的用户：
    
  - 若要选择单个用户，请选择用户的名称。
    
  - 要选择该页上的所有用户，请都选择位于列表的顶部**显示名称**旁边的框。
    
  - 若要选择多个用户，请选择每个用户的名称旁边的框。
    
5. 在右窗格中，选择" **编辑**"。
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. 选择**音频会议**。
    
7. 在**属性**页的**提供程序名称**列表中，选择为用户提供。 根据提供商中，填写以下框。
    
  - **Microsoft 将提供程序**： 使用**默认收费电话号码**和**免费电话号码的默认**列表选择用户的默认数字。
    
    > [!NOTE]
    > 至少一个免费电话号码必须分配给会议桥前它可以设置为用户的默认免费电话号码。 若要获取免费电话号码，请参阅[获得 Skype 业务和 Microsoft 团队的服务电话号码](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)。 
  
  - **第三方为提供程序**： 使用**收费电话号码**和**免费电话号码**字段，用户输入的数字。
    
## <a name="reset-audio-conferencing-phone-numbers"></a>重置音频会议电话号码

1. 在**Skype 的业务管理中心**，选择**音频会议**。
    
2. 在页面的顶部，选择**用户**。
    
3. 选择您要重置，的用户，然后在操作窗格中，单击**清除**。
    
默认情况下，当您更改用户的会议设置，电子邮件发送给用户。 若要更改此设置，请参阅[启用或禁用音频会议设置更改时发送的电子邮件](enable-or-disable-sending-emails-when-their-settings-change.md)。
  
> [!IMPORTANT]
> 更改用户的音频会议设置时，必须更新定期和未来 Skype 业务和 Microsoft 小组会议，并发送给与会者。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet。
    
- 使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet 可更改特定用户的默认收费电话号码或免费电话号码。
    
    若要更改用户的默认免费电话号码，请运行：
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- 使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet 可基于用户的原始默认电话号码或位置来更改其默认收费电话号码或免费电话号码。
    
    > [!NOTE]
    > 若要查找 BridgeID，使用**Get CsOnlineDialInConferencingBridge**。
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - 若要设置默认的免费电话号码没有 1 到 +18005551234 的所有用户，请运行：
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - 若要更改默认的 +18005551234 作为其默认免费电话号码为 +18005551239 的所有用户的免费电话号码，请运行：
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 若要设置默认的 （美国） 到 +18005551234 中的所有用户的免费电话号码，请运行：
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
## <a name="want-to-learn-more-about-windows-powershell"></a>要了解有关 Windows PowerShell？
- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为什么需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
