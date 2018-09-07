---
title: 电子邮件发送给用户使用他们的 Microsoft 团队中的音频会议信息
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: 中的 Microsoft 团队发送您的用户使用他们的音频会议信息的电子邮件。
ms.openlocfilehash: 3ee0d5f7eda551e5231cae535dec08439c19e081
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850774"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a>电子邮件发送给用户使用他们的 Microsoft 团队中的音频会议信息

有时 Microsoft 团队用户可能需要您向他们发送其音频会议信息。 您可以通过单击**发送电子邮件的会议信息**下的用户属性来执行此操作。 当您发送此电子邮件时，它将包含的所有音频会议信息，包括：
  
- 用户的会议电话或拨入电话号码。
    
- 用户的会议 ID。
    
   
下面是发送的电子邮件的示例：
  
![电话拨入式会议电子邮件](media/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>向用户发送电子邮件与音频会议信息

1. 在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。

2. 在页面的顶部，单击**编辑**。

3. 在**音频会议**，单击**发送电子邮件中的会议信息**。


## <a name="what-else-should-you-know-about-this-email"></a>此电子邮件的其他须知事项。

- 有多个电子邮件发送给组织中的用户启用了后为音频会议：
    
  - 当**音频会议**许可证分配给它们。
    
  - 当您手动重置用户的音频会议 PIN。
    
  - 当你手动重置用户的会议 ID 时。
    
  - 当**音频会议**许可证已从它们。
    
  - 当用户音频会议提供商从 Microsoft 更改为其他提供程序或**无**。
    
  - 向 Microsoft 更改时用户音频会议提供商。
    
- 默认情况下，电子邮件发件人将从 Office 365，但您可以更改的电子邮件地址，并且可以使用 Windows PowerShell 显示名称。 请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。
  
## <a name="want-to-know-more-about-windows-powershell"></a>要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。
    
  
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
