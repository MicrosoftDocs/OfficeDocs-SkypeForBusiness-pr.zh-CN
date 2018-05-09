---
title: 音频会议号码的列表，请参阅
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
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
description: 'Learn how to look up your dial-in conferencing numbers from within Skype for Business. '
ms.openlocfilehash: bccd4a5c02dbb6bc32c27e315b80a39705284429
ms.sourcegitcommit: b93d1a0012aacb164d700db0143683cb6f276bf4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
---
# <a name="see-a-list-of-audio-conferencing-numbers"></a>音频会议号码的列表，请参阅

当您设置音频会议的 Skype 的业务和 Microsoft 团队的用户时，您可以查看为音频会议提供给他们的电话号码。 此列表都会将所有可供您的组织的音频会议电话号码。
  
 **正在搜索价格？** 请参阅[定价音频会议](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements)。
  
> [!IMPORTANT]
> **没有音频会议中包含的所有电话拨入式号码列表的资源。** 如果您要查找要查看如果电话拨入电话号码中提供了您的区域或国家/地区，请转到**业务管理中心的 Skype** > **语音** > **电话号码**，单击**添加**，然后单击**新服务号码**。 使用“**国家/地区**”、“**州/地区**”和“**城市**”列表对你的搜索进行筛选。 此外，如果您要查找免费电话服务号码，选择**免费电话**从**国家/地区**列表。
  
如果仅有一个电话号码在你的组织中可用，则会将其作为你的所有用户的默认号码。 当多个电话号码可用时，你可以为每个用户选择默认电话号码。 此默认号码将 Skype 中包括的业务和 Microsoft 团队的会议邀请。
  
您可以看到[设置的电话号码包含在邀请](set-the-phone-numbers-included-on-invites.md)以更改为单个用户的电话拨入式电话号码。
  
> [!NOTE]
> [!注释] 国内拨入号码供你的组织专用，是唯一可以设为默认电话号码的号码。 但是，国际拨入号码可能会在多个组织之间共享。 
  
## <a name="to-view-your-audio-conferencing-phone-numbers"></a>若要查看您的音频会议电话号码

![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航窗格中，转到**会议** > **会议桥**。 
2.  查看可用于音频会议的电话号码。

- 您还可以查看的位置和音频会议自动助理将使用的主要语言。

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**

1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **Microsoft 桥**，然后：
    
  - 您可以查看可用于音频会议的电话号码。
    
  - 您还可以查看位置，并将使用的音频会议的主要和辅助语言自动助理。
    
> [!NOTE]
> 您可以转到**音频会议** > **用户**和用户属性来更改默认号码由从您的组织中的可用号码的列表中选择新号码的选择。 请参阅[设置的电话号码包含在邀请](set-the-phone-numbers-included-on-invites.md)。 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) cmdlet。
    
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么您需要使用 Office 365 PowerShell 中](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 具有很多好处中快速、 简便起见和生产力通过只使用 Office 365 管理中心中的，如时要进行设置更改多个用户一次。 请在以下主题中了解这些优点：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
