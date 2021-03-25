---
title: 查看 Skype for Business Online 中已启用音频会议的用户列表
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '了解如何从 Skype for Business 业务管理中心查看组织中启用了拨入音频会议 的用户列表。 '
ms.openlocfilehash: 2cb4481f480f5be9f45064aed1fd48f9f5c28496
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114128"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a>查看 Skype for Business Online 中已启用音频会议的用户列表

> [!NOTE]
> 有关在 Microsoft Team 中启用的用户的信息，请参阅查看 Microsoft Teams 中启用了音频会议的用户列表。[ ](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams)

在组织中为 Skype for Business 用户启用音频会议后，您可以查看已启用这些用户的列表。 查看列表时，还会在列表中的每个用户看到他们使用的音频会议提供商的类型、用户的默认拨入电话号码，并且如果你的组织未启用动态会议 ID，则还会看到他们组织的音频会议会议的静态会议 ID。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a>查看用户列表

   
- 在左侧导航窗格中，转到 **音频会议** > **用户** 　。

## <a name="what-else-should-i-know"></a>我还需了解哪些信息？

- 查看已启用的用户列表时，可以从列表中选择一个用户，并使用"操作"窗格编辑该用户的音频会议设置。
    
- 当您选择配置为使用 Microsoft 作为音频会议提供商的单个用户时，您可以查看默认电话号码以及您的组织是否启用了动态会议 ID，并且您可以重置用户组织的会议的会议 ID。
    
- 选择配置为使用第三方音频会议提供商的单个用户时，如果设置了) ，您可以查看音频会议提供商的名称、收费电话号码和免费电话号码 (。
    
- 可以使用筛选选项来显示具有以下设置的用户：
    
  - **音频会议开启**
    
  - **音频会议关闭**
    
  - **会议提供商 - Microsoft**
    
  - **会议提供商 - 其他**
    
- 可以使用搜索按钮搜索列表中的某个用户。
    
- 你可以选择多个用户并执行下列操作：
    
  - 为这些用户选择其他默认号码。
    
  - 将提供商更改为"无"，为用户关闭音频 **会议**。
    
  - 如果用户已分配有音频会议许可证，请切换到 Microsoft 作为音频 **会议提供商。**
    
  - 允许/禁止匿名用户激活选定用户的电话会议。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用 Windows PowerShell，当你有多个任务需要执行时，可以使用可以简化日常工作的单一管理点来管理 Microsoft 365 或 Office 365 和 Skype for Business Online。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [为何需要使用 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell比使用 Microsoft 365 管理中心（例如，一次对许多用户进行设置更改时）具有许多速度、简单性和工作效率优势。 通过以下主题了解这些优势：
    
  - [使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>相关主题

[在 Microsoft 365 或 Office 365 中试用或购买音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)