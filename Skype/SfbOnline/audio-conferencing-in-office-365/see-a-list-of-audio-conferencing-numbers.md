---
title: 请参阅  Skype for Business Online 中的音频会议号码列表
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
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
description: '学习如何在 Skype for Business 内查找电话拨入会议号码。 '
ms.openlocfilehash: 118b929f16f0c6edf5c512ddc9b94529a34a8860
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861146"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>请参阅  Skype for Business Online 中的音频会议号码列表

> [!NOTE]
> 有关 Microsoft Teams 中的音频会议号码的信息，请参阅 [Microsoft Teams 的音频会议号码列表](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams)。

当为  Skype for Business 用户设置时音频会议时，您可以查看为音频会议提供给他们的电话号码。 此列表将提供可用于你的组织的所有音频会议的电话号码。
  
 **正在搜索价格？** 请参阅[音频会议的定价](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements)。
  
> [!IMPORTANT]
> **没有包含音频会议的所有拨入号码列表的资源。** 如果要查看你所在的区域或国家/地区是否有可用的拨入电话号码，请转到 **Skype for Business 管理中心** > **语音** > **电话号码**，点击**添加**，然后单击**新服务号码**。 使用**国家/地区**、**州/地区**和**城市**列表对您的搜索进行筛选。 如果您要查找免费服务号码，请从**州/地区**列表中选择**免费**。
  
如果仅有一个电话号码在你的组织中可用，则会将其作为你的所有用户的默认号码。 当多个电话号码可用时，您可以为每个用户选择默认电话号码。 本默认号码将包含在 Skype for Business 会议邀请中。
  
您可以看到[设置邀请包含的电话号码](set-the-phone-numbers-included-on-invites.md)以更改为单个用户的电话拨入式电话号码。
  
> [!NOTE]
> [!注释] 国内拨入号码供你的组织专用，是唯一可以设为默认电话号码的号码。 但是，国际拨入号码可能会在多个组织之间共享。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>若要查看您的音频会议电话号码

1. 使用您的工作或学校帐户登录 Office 365。
    
2. 转到 **Office 365 管理中心** > **Skype for Business**。
    
3. 在左侧导航的 **Skype for Business 管理中心**中，转到**音频会议** > **Microsoft 桥接**，然后：
    
  - 可以查看用于音频会议的电话号码。
    
  - 您还可以查看将由音频会议自动助理使用的位置和主要和辅助语言。
    
> [!NOTE]
> 您可以转到**音频会议** > **用户**，选择用户的属性，通过从组织中可用的号码列表中选择一个新号码来更改用户的默认号码。 请参阅[设置邀请中所包含的电话号码](set-the-phone-numbers-included-on-invites.md)。 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) cmdlet。
    
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 与仅使用 Office 365 管理中心相比，Windows PowerShell 在速度、简化和工作效率方面具有许多优点，例如，当一次更改许多用户的设置时。 请在以下主题中了解这些优点：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
  
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
