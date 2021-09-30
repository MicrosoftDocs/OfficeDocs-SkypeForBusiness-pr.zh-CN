---
title: 在 Skype for Business Online 中使用其音频会议向用户发送电子邮件
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 在 Skype for Business Online 中向用户发送包含其音频会议信息的电子邮件。
ms.openlocfilehash: 8576417588571fcc76461a635f00cb3095410b86
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012346"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a>在 Skype for Business Online 中向用户发送包含其音频会议信息的电子邮件

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> 有关向 Microsoft Teams 中的用户发送音频会议信息的信息，请参阅在 [Microsoft Teasms](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams)中向用户发送包含其音频会议信息的电子邮件。

有时 Skype for Business 用户可能需要你向用户发送其音频会议信息。 为此，可以使用 Skype for Business 管理 **中心，** 然后单击用户属性下的"通过电子邮件发送会议信息"。 当你发送此电子邮件时，它将包含所有音频会议信息，包括：
  
- 用户的会议电话或拨入电话号码。
    
- 用户的会议 ID。
    
   
下面是发送的电子邮件示例：
  
![电话拨入式会议电子邮件。](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>向用户发送包含音频会议信息的电子邮件

1. 在左侧导航栏中， **单击"用户**"，然后从可用用户列表中选择用户。

2. 在页面的顶部，单击 **编辑**。

3. 在 **"音频会议"下**，单击 **"通过电子邮件发送会议信息"。**

1. 使用工作或学校帐户登录。
    
2. 转到 Skype **for Business**>管理中心，在左侧导航中，单击"**音频会议"。**
    
3. 单击 **"用户**"，然后选择用户。
    
4. 在操作窗格中，单击" **通过电子邮件发送会议信息**"。
    
> [!TIP]
> 您还可以使用音频会议设置向用户发送电子邮件，方法是编辑用户的属性，然后单击"音频会议""  >  **通过电子邮件发送会议信息"。** 

## <a name="what-else-should-you-know-about-this-email"></a>此电子邮件的其他须知事项。

- 启用音频会议后，会向贵组织的用户发送多封电子邮件：
    
  - 向其分配 **音频会议** 许可证时。
    
  - 手动重置用户的音频会议 PIN 时。
    
  - 当你手动重置用户的会议 ID 时。
    
  - 从 **中删除音频会议** 许可证时。
    
  - 当用户的音频会议提供商从 Microsoft 更改为其他提供商或"无 **"时**。
    
  - 当用户的音频会议提供商更改为 Microsoft 时。
    
- 默认情况下，电子邮件的发件人来自 Microsoft 365 或 Office 365，但您可以使用 Windows PowerShell 和 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) cmdlet 更改电子邮件地址和 显示名称。 若要更改向用户发送电子邮件的电子邮件地址，必须：
    
  - 在 SendEmailFromAddress 参数中输入电子邮件地址。
    
  - 将SendEmailOverride参数设置为 True。
    
  - 在 SendEmailFromDisplayName 显示名称输入电子邮件名称。
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > [!注释] 如果要更改电子邮件地址信息，你需要确保你的组织的入站电子邮件策略允许来自设置的自定义电子邮件地址的电子邮件。 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

- 为节省时间或自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet。
    
    若要向用户发送包含其音频会议信息的电子邮件，请运行以下代码：
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- 对于 Windows PowerShell，Skype for Business Online 的功能是管理用户以及允许或不允许用户执行的操作。 使用Windows PowerShell，您可以使用单点管理来管理 Microsoft 365 或 Office 365，当您有多个任务需要执行时，可以简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为何需要使用 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell使用 Microsoft 365 管理中心相比，在速度、简单性和工作效率方面具有许多优势，例如，一次对多个用户进行设置更改时。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [使用 Windows PowerShell 管理 Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。 此模块仅在 64 位计算机上受支持，可从 Microsoft 下载中心下载并安装 Teams [PowerShell 模块](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md)。
  
## <a name="related-topics"></a>相关主题

[在 Microsoft 365 或 Office 365 中试用或购买音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
