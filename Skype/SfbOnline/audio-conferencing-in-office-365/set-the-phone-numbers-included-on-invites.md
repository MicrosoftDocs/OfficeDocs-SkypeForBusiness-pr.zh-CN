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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 9ed22a26ddb13d058e81d7fdd046d794623cb3a5176c333429b7227cd279afaa
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326978"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>设置包含在 Skype for Business Online 邀请中的电话号码

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 有关 Microsoft Teams 中的会议邀请电话号码的信息，请参阅[设置 Microsoft Teams 中包含的电话号码](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams)。

会议Microsoft 365音频Office 365使贵组织的用户能够创建 Skype for Business 会议，然后允许用户使用电话拨入这些会议。 在 Microsoft 365 和 Office 365 中，可以选择使用 Microsoft 音频会议网桥或由经批准的音频会议提供商托管的第三方音频会议网桥 (ACP) 。
  
> [!NOTE]
> 没有包含所有音频会议拨入号码列表的资源。 如果你希望查看你的地区或国家/地区是否有可用的拨入电话号码，请使用 **Skype for Business** 管理中心 Voice 电话 号码，单击"添加"，然后单击"新建服务号码  >    >  **"。**  使用 **国家/地区**、**州/地区** 和 **城市** 列表筛选搜索。 此外，如果要查找免费服务电话号码，从 **国家/地区** 列表中选择 **免费电话**。
  
会议桥为你的组织提供了一套拨入电话号码。 它们都可用于加入会议组织者已创建的会议，但你可以选择在其会议邀请中包括哪些号码。
  
> [!NOTE]
> 会议组织者的会议邀请中最多可以有一个收费和一个免费电话号码，但每个会议邀请的底部还有一个链接，用于打开用来可加入会议的所有拨入电话号码的完整列表。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>为会议组织者设置默认的拨入电话号码

1. 使用工作或学校帐户登录。
    
2. 选择 **管理中心** > **Skype for Business** 。
    
3. 选择" **用户**"。
    
    ![在 Skype for Business 管理中心显示选择用户](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. 选择要编辑的用户：
    
   - 要选择单个用户，请选择该用户的名称。
    
   - 要选择页面上的所有用户，请都选择列表顶部 **显示名称** 旁边的复选框。
    
   - 要选择多个用户，请选择每个用户名称旁边的复选框。
    
5. 在右窗格中，选择" **编辑**"。
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. 选择 **音频会议**。
    
7. 在 **属性** 页上的 **提供商名称** 列表中，为用户选择提供商。 根据提供商填写下列方框。
    
   - **Microsoft 是提供商**：使用 **默认收费电话号码** 和 **默认免费电话号码** 列表选择用户的默认号码。
    
     > [!NOTE]
     > 在将电话号码设置为用户的默认免费电话号码之前，必须为至少向会议桥分配一个免费电话号码。 若要获取免费电话号码，请参阅获取免费服务[Skype for Business。](/microsoftteams/getting-service-phone-numbers) 
  
   - **第三方是提供商**：使用 **收费电话号码** 和 **免费电话号码** 字段，为用户输入号码。


## <a name="reset-audio-conferencing-phone-numbers"></a>重置音频会议的电话号码

1. 在Skype for Business **中心中，** 选择"**音频会议"。**
    
2. 在页面顶部，选择 **用户**。
    
3. 选择要重置的用户，然后在操作窗格单击 **清除**。
    
默认情况下，更改用户的会议设置时会给用户发送电子邮件。 若要更改此功能，请参阅音频会议设置更改时启用 [或禁用发送电子邮件](enable-or-disable-sending-emails-when-their-settings-change.md)。
  
> [!IMPORTANT]
> 更改用户的音频会议设置时，必须更新定期和将来的 Skype for Business 会议，并将其发送给与会者。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet。
    
- 使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet 可更改特定用户的默认收费电话号码或免费电话号码。
    
    若要更改用户的默认免费电话号码，请运行：
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- 使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet 可基于用户的原始默认电话号码或位置来更改其默认收费电话号码或免费电话号码。
    
    > [!NOTE]
    > 若要查找 BridgeID，请使用 **Get-CsOnlineDialInConferencingBridge** cmdlet。
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - 若要为没有免费电话号码的所有用户设置默认免费电话号码，请18005551234：
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - 若要将具有 +18005551234 的默认免费电话号码的所有用户的默认免费电话号码更改为 +18005551239，请运行：
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 若要将位于美国的所有用户的默认免费电话号码设置为 +18005551234，请运行：
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a>想要详细了解Windows PowerShell？
- 对于 Windows PowerShell，它全部是关于管理用户以及允许或不允许用户执行的操作。当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [为何需要将 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell比仅使用 Microsoft 365 管理中心（例如，一次为许多用户进行设置更改时）在速度、简单性和工作效率方面具有许多优势。 通过以下主题了解这些优势：
    
  - [使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>相关主题

[尝试或购买音频会议Microsoft 365或Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
