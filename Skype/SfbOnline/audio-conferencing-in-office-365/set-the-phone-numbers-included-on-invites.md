---
title: 设置包含在 Skype for Business Online 邀请中的电话号码
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: '获取创建默认的电话号码，以供呼叫者加入 Skype for Business 会议的步骤。 '
ms.openlocfilehash: d4ab76fc99483812d2be6b2f7009be361f33c3c9
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23851482"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>设置包含在 Skype for Business Online 邀请中的电话号码

> [!Note]
> 有关 Microsoft Teams 中的会议邀请电话号码的信息，请参阅[设置 Microsoft Teams 中包含的电话号码](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams)。

Office 365 中的音频会议使组织中的用户能够创建 Skype for Business 会议，然后允许用户使用电话拨入到这些会议。 在 Office 365 中，可以选择使用 Microsoft 音频会议网桥或者使用由批准的音频会议提供商 (ACP) 托管的第三方音频会议网桥。
  
> [!NOTE]
> 没有任何资源包含音频会议的所有拨入号码的列表。 如果要查看你所在的区域或国家/地区是否有可用的拨入电话号码，请使用 **Skype for Business 管理中心** > **语音** > **电话号码**，点击**添加**，然后点击**新服务号码**。 使用**国家/地区**、** 州/地区**和**城市**列表筛选搜索。 此外，如果要查找免费服务电话号码，从** 国家/地区**列表中选择**免费电话**。
  
会议桥为你的组织提供了一套拨入电话号码。 它们都可用于加入会议组织者已创建的会议，但你可以选择在其会议邀请中包括哪些号码。
  
> [!NOTE]
> 会议组织者的会议邀请中最多可以有一个收费和一个免费电话号码，但每个会议邀请的底部还有一个链接，用于打开用来可加入会议的所有拨入电话号码的完整列表。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>为会议组织者设置默认的拨入电话号码

1. 使用工作或学校帐户登录 Office 365。
    
2. 选择 **管理中心** > **Skype for Business** 。
    
3. 选择**用户**。
    
    ![在 Skype for Business 管理中心显示选择用户](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. 选择要编辑的用户：
    
  - 要选择单个用户，请选择该用户的名称。
    
  - 要选择页面上的所有用户，请都选择列表顶部**显示名称**旁边的复选框。
    
  - 要选择多个用户，请选择每个用户名称旁边的复选框。
    
5. 在右侧窗格中，选择**编辑**。
    
    ![选择编辑图标。](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. 选择**音频会议**。
    
7. 在**属性**页上的**提供商名称**列表中，为用户选择提供商。 根据提供商填写下列方框。
    
  - **Microsoft 是提供商**：使用**默认收费电话号码**和**默认免费电话号码**列表选择用户的默认号码。
    
    > [!NOTE]
    > 在将电话号码设置为用户的默认免费电话号码之前，必须为至少向会议桥分配一个免费电话号码。 若要获取免费电话号码，请参阅[为 Skype for Business 获取服务电话号码](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)。 
  
  - **第三方是提供商**：使用**收费电话号码**和**免费电话号码**字段，为用户输入号码。


## <a name="reset-audio-conferencing-phone-numbers"></a>重置音频会议的电话号码

1. 在 **Skype for Business 管理中心**选择**音频会议**。
    
2. 在页面顶部，选择**用户**。
    
3. 选择要重置的用户，然后在操作窗格单击**清除**。
    
默认情况下，更改用户的会议设置时会给用户发送电子邮件。 若要更改此设置，请参阅[音频会议设置更改时启用或禁用发送电子邮件](enable-or-disable-sending-emails-when-their-settings-change.md)。
  
> [!IMPORTANT]
> 更改用户的音频会议设置时，必须更新定期和将来的 Skype for Business 会议，并将其发送给与会者。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet。
    
- 使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet 可更改特定用户的默认收费电话号码或免费电话号码。
    
    若要更改用户的默认免费电话号码，请运行：
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- 使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet 可基于用户的原始默认电话号码或位置来更改其默认收费电话号码或免费电话号码。
    
    > [!NOTE]
    > 若要查找 BridgeID，请使用 **Get-CsOnlineDialInConferencingBridge**。
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - 若要为没有默认免费电话号码的所有用户将默认免费电话号码设置为 +18005551234，请运行：
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - 若要为默认免费电话号码已设置为 +18005551234 的所有用户将默认免费电话号码更改为 +18005551239，请运行：
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 若要为位于美国的所有用户将默认免费电话号码设置为 +18005551234，请运行：
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
## <a name="want-to-learn-more-about-windows-powershell"></a>要了解有关 Windows PowerShell 的详细信息？
- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
