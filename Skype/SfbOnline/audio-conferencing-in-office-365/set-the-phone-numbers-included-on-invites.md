---
title: 设置的电话号码包含在邀请
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 03b6f3b2ce270d1dd6e2855dec4ee2af9a2447c8
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="set-the-phone-numbers-included-on-invites"></a>设置的电话号码包含在邀请

Office 365 中的音频会议，组织中的用户创建的业务和 Microsoft 团队会议 Skype，然后允许这些会议使用电话拨入的用户。 在 Office 365 中，您可以使用 Microsoft 音频会议网桥或位于由已批准的音频会议提供商 (ACP) 的第三方音频会议桥的选择。
  
> [!NOTE]
> 没有资源包含音频会议的所有拨入号码的列表。 如果您要查找要查看如果电话拨入电话号码中提供了您的区域或国家/地区，使用**业务管理中心的 Skype** > **语音** > **电话号码**，单击**添加**然后**新服务号码**. **国家/地区**，**国家/地区使用列表**和**市/县**筛选搜索。 > 此外，如果您要查找免费服务收费电话号码，选择**免费电话**从**国家/地区**列表。
  
会议桥为您提供了一套电话拨入电话号码为组织。 所有这些可用于加入会议的会议组织者已创建，但您可以选择将在其会议邀请包括哪些功能。
  
> [!NOTE]
> 可以有一个收费和一个免费电话号码的会议组织者，会议邀请上的最大值，但还有位于底部的每个打开的完整列表可用于加入会议的所有电话拨入电话号码的会议邀请的链接。 
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) 为会议组织者设置的默认电话拨入式电话号码

1. 使用你的工作或学校帐户登录 Office 365。
    
2. Choose **Admin centers** > **Skype for Business**.
    
3. 选择" **用户**"。
    
    ![业务管理中心的 Skype 中选择用户的显示](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. 选择您想要编辑的用户：
    
  - 要选择单个用户，请选择该用户的名称。
    
  - 要选择页面上的所有用户，请都选择列表顶部的**显示名称**旁边的框。
    
  - 要选择多个用户，请选择每个用户的名称旁边的框。
    
5. 在右窗格中，选择" **编辑**"。
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. 选择**音频会议**。
    
7. 在**属性**页上的**提供程序名称**列表中，选择为用户提供程序。 具体取决于提供程序，填写下列框。
    
  - **Microsoft 是提供程序**： 使用**默认收费电话号码**和**默认免费电话号码**列表选择用户的默认号码。
    
    > [!NOTE]
    > 它可以设置为默认免费电话号码的用户之前，必须为至少一个免费电话号码分配到您的会议桥。 若要获取免费电话号码，请参阅[业务和 Microsoft 团队的 Skype 获取服务电话号码](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)。 
  
  - **第三方是提供程序**： 使用**收费电话号码**和**免费电话号码**字段，用户输入的数字。
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-reset-audio-conferencing-phone-numbers"></a>![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) 重置音频会议的电话号码

1. 在**Skype 业务管理中心的**中，选择**要进行音频会议**。
    
2. 在页面顶部，选择**用户**。
    
3. 选择您要重置的用户，然后单击在操作窗格的**清除**。
    
默认情况下，当您更改用户的会议设置电子邮件发送给用户。 若要更改此设置，请参阅[启用或禁用发送电子邮件时要进行音频会议设置更改](enable-or-disable-sending-emails-when-their-settings-change.md)。
  
> [!IMPORTANT]
> 更改用户的音频会议设置时，必须更新定期和将来的 Skype，业务和 Microsoft 团队的会议，并将其发送给与会者中。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet。
    
- 使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet 可更改特定用户的默认收费电话号码或免费电话号码。
    
    若要更改用户的默认免费电话号码，请运行：
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- 使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet 可基于用户的原始默认电话号码或位置来更改其默认收费电话号码或免费电话号码。
    
    > [!NOTE]
    > 若要查找 BridgeID，请使用**Get-CsOnlineDialInConferencingBridge**。
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - 若要不向 +18005551234 的所有用户设置默认免费电话号码，请运行：
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - 若要更改的所有用户的已为其默认免费电话号码与 +18005551239 +18005551234 默认免费电话号码，请运行：
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 若要设置的位于到 +18005551234 美国的所有用户的默认免费电话号码，请运行：
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
## <a name="want-to-learn-more-about-windows-powershell"></a>要了解有关 Windows PowerShell 的详细信息？
- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为什么您需要使用 Office 365 PowerShell 中](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
