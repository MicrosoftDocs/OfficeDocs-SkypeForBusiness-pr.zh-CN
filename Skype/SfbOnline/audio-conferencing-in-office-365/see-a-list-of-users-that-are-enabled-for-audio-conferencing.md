---
title: 在 Skype for Business Online 中查看已启用音频会议的用户的列表
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bd0cd155-4c6d-424d-a2c9-af7974a2d34c
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
description: '了解如何从 Skype for Business 业务管理中心查看组织中启用了拨入音频会议 的用户列表。 '
ms.openlocfilehash: 9fb3a5ca8e21969ea5c09a5ac5c282dc4b816eff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298928"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a>在 Skype for Business Online 中查看已启用音频会议的用户的列表

> [!NOTE]
> 有关在 Microsoft Team 中启用的用户的信息，请参阅查看 Microsoft Teams 中启用了音频会议的用户列表。[ ](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams)

After you have enabled Skype for Business users in your organization for Audio Conferencing, you can view the list of those users who have been enabled. When you look at the list, you will also see for each user in the list the type of audio conferencing provider that they are using, the default dial-in phone number for the user, and if you organization isn't enabled for dynamic conference IDs, the static conference IDs for audio conferencing meetings that they organize.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a>查看用户列表

   
- 在左侧导航窗格中，转到 **音频会议** > **用户** 　。

## <a name="what-else-should-i-know"></a>我还需了解哪些信息？

- 当你查看已启用用户的列表时, 你可以从列表中选择用户并使用操作窗格编辑该用户的音频会议设置。
    
- 当你选择配置为使用 Microsoft 作为音频会议提供商的单个用户时, 你可以查看默认电话号码以及你的组织是否已启用动态会议 Id, 你可以重置会议的会议 ID用户进行组织。
    
- 当你选择配置为使用第三方音频会议提供商的单个用户时, 你可以查看音频会议提供商的名称、收费电话号码和免费电话号码 (如果已设置)。
    
- 可以使用筛选选项来显示具有以下设置的用户：
    
  - **音频会议开启**
    
  - **音频会议关闭**
    
  - **会议提供商 - Microsoft**
    
  - **会议提供商 - 其他**
    
- 可以使用搜索按钮搜索列表中的某个用户。
    
- 你可以选择多个用户并执行下列操作：
    
  - 为这些用户选择其他默认号码。
    
  - 通过将提供程序更改为 "**无**" 来关闭用户的音频会议。
    
  - 如果用户已分配**音频会议**许可证, 则切换到 Microsoft 作为音频会议提供商。
    
  - 允许/禁止匿名用户激活选定用户的电话会议。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
