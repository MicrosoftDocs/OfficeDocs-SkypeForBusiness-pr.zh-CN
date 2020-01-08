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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 33c2f69cbd05efedf5af1bb35c7ea5d560930da4
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962510"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>设置包含在 Skype for Business Online 邀请中的电话号码

> [!Note]
> 有关 Microsoft Teams 中的会议邀请电话号码的信息，请参阅[设置 Microsoft Teams 中包含的电话号码](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams)。

Audio Conferencing in Office 365 enables users in your organization to create Skype for Business meetings, and then allow users to dial in to those meetings using a phone. In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).
  
> [!NOTE]
> There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing. If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**. Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.
  
A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.
  
> [!NOTE]
> 会议组织者的会议邀请中最多可以有一个收费和一个免费电话号码，但每个会议邀请的底部还有一个链接，用于打开用来可加入会议的所有拨入电话号码的完整列表。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>为会议组织者设置默认的拨入电话号码

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 选择 **管理中心** > **Skype for Business** 。
    
3. 选择" **用户**"。
    
    ![在 Skype for Business 管理中心显示选择用户](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. 选择要编辑的用户：
    
   - 要选择单个用户，请选择该用户的名称。
    
   - 要选择页面上的所有用户，请都选择列表顶部**显示名称**旁边的复选框。
    
   - 要选择多个用户，请选择每个用户名称旁边的复选框。
    
5. 在右窗格中，选择" **编辑**"。
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. 选择**音频会议**。
    
7. On the **Properties** page, in the **Provider name** list, choose the provider for the user. Depending on the provider, complete the following boxes.
    
   - **Microsoft 是提供商**：使用**默认收费电话号码**和**默认免费电话号码**列表选择用户的默认号码。
    
     > [!NOTE]
     > At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user. To get a toll-free number, see [Getting service phone numbers for Skype for Business](/microsoftteams/getting-service-phone-numbers). 
  
   - **第三方是提供商**：使用**收费电话号码**和**免费电话号码**字段，为用户输入号码。


## <a name="reset-audio-conferencing-phone-numbers"></a>重置音频会议的电话号码

1. 在**Skype For business 管理中心**，选择 "**音频会议**"。
    
2. 在页面顶部，选择**用户**。
    
3. 选择要重置的用户，然后在操作窗格单击**清除**。
    
By default, when you change a user's conferencing settings, an email is sent to the user. To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).
  
> [!IMPORTANT]
> 更改用户的音频会议设置时，必须更新定期和将来的 Skype for Business 会议，并将其发送给与会者。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet。
    
- 使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet 可更改特定用户的默认收费电话号码或免费电话号码。
    
    若要更改用户的默认免费电话号码，请运行：
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- 使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet 可基于用户的原始默认电话号码或位置来更改其默认收费电话号码或免费电话号码。
    
    > [!NOTE]
    > 若要查找 BridgeID，请使用**get-csonlinedialinconferencingbridge** cmdlet。
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - 若要为所有用户设置默认免费电话号码，而不是 + 18005551234，请运行：
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - 若要将具有 + 18005551234 的所有用户的默认免费电话号码更改为 + 18005551239 的默认免费号码，请运行：
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 若要将美国所有用户的默认免费号码设置为 + 18005551234，请运行：
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？
- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你同时为多个用户设置更改时。了解以下主题中的这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
