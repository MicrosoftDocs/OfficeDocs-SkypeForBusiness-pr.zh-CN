---
title: " 查看 Skype for Business Online 中启用了音频会议的用户列表"
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解如何从 Skype for Business 业务管理中心查看组织中启用了拨入音频会议 的用户列表。 '
ms.openlocfilehash: 5cb792a3706c93c764f119075fca657b2179a383
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23849850"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a> 查看 Skype for Business Online 中启用了音频会议的用户列表

> [!NOTE]
> 有关在 Microsoft Team 中启用的用户的信息，请参阅查看 Microsoft Teams 中启用了音频会议的用户列表。[ ](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams)

组织中的用户启用 Skype for Business 的音频会议后，你可以查看的已启用用户的列表。 在查看该列表时，还将看到列表中的每个用户正在使用的音频会议提供商类型、用户的默认拨入电话号码以及如果组织没有启用动态会议 ID，他们所组织音频会议的静态会议 ID。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a>查看用户列表

   
- 在左侧导航窗格中，转到**音频会议** > **用户**。

## <a name="what-else-should-i-know"></a>我还需了解哪些信息？

- 当查看已启用的用户的列表时，你可以从列表中选择用户，并使用“操作”窗格编辑该用户的电话拨入式会议设置。
    
- 选择配置为使用 Microsoft 作为音频会议提供商的单个用户时，可以查看默认电话号码和你的组织是否启用动态会议 ID，也可以为用户组织的会议重置会议 ID。
    
- 选择配置为使用第三方音频会议提供商的单个用户时，可以查看音频会议提供商的名称、收费电话号码和免费电话号码（如果已设置）。
    
- 可以使用筛选选项来显示具有以下设置的用户：
    
  - **音频会议开启**
    
  - **音频会议关闭**
    
  - **会议提供商 - Microsoft**
    
  - **会议提供商 - 其他**
    
- 可以使用搜索按钮搜索列表中的某个用户。
    
- 你可以选择多个用户并执行下列操作：
    
  - 为这些用户选择其他默认号码。
    
  - 通过将提供商更改为**无**，可为用户关闭音频会议。
    
  - 如果已为用户分配**音频会议**许可证，请切换为使用 Microsoft 作为音频会议提供商。
    
  - 允许/禁止匿名用户激活选定用户的电话会议。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 当你有多个要执行的任务时，使用 Windows PowerShell 可以通过能够简化日常工作的单点管理来管理 Office 365 和 Skype for Business Online。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- 例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
