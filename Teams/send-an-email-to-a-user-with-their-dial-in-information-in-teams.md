---
title: 在 Microsoft Teams 中向用户发送包含其音频会议信息的电子邮件
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
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: 在 Microsoft Teams 中向你的用户发送包含其音频会议信息的电子邮件。
ms.openlocfilehash: 85e219481884bb08a2574809b6170c232abccf83
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892089"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a>在 Microsoft Teams 中向用户发送包含其音频会议信息的电子邮件

有时，Microsoft Teams 用户可能需要你向其发送电话音频会议信息。 你可以单击用户的属性下的“**通过电子邮件发送会议信息**”来完成。 当你发送此电子邮件时，它将包含所有音频会议信息，包括：
  
- 用户的会议电话或拨入电话号码。
    
- 用户的会议 ID。
    
   
下面是发送的电子邮件示例：
  
![电话拨入式会议电子邮件](media/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>向用户发送包含音频会议信息的电子邮件

1. 在左侧导航中，单击“**用户**”，然后从可用用户列表中选择用户。

2. 在页面顶部，单击“**编辑**”。

3. 在“**音频会议**”下，单击“**通过电子邮件发送会议信息**”。


## <a name="what-else-should-you-know-about-this-email"></a>你还应该了解有关此电子邮件的哪些信息？

- 在为贵组织中的用户启用了音频会议后，会向他们发送多封电子邮件：
    
  - 向其分配**音频会议**许可证时。
    
  - 当你手动重置用户的音频会议 PIN 时。
    
  - 当你手动重置用户的会议 ID 时。
    
  - 删除用户的**音频会议**许可证时。
    
  - 当用户的音频会议提供商从 Microsoft 更改为另一个提供商或“**无**”时。
    
  - 当用户的音频会议提供商更改为 Microsoft 时。
    
- 默认情况下，这些电子邮件的发件人将显示为来自 Office 365，但你可以使用 Windows PowerShell 更改电子邮件地址和显示名称。 有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。
  
## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。
    
  
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
