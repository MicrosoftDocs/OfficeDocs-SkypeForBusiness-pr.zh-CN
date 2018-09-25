---
title: 在 Microsoft Teams 中管理组织的音频会议设置
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解为用户分配电话拨入式会议许可证和会议 ID 的 Microsoft Teams 步骤以及许多其他电话拨入式会议设置。 '
ms.openlocfilehash: 40a6dd3e545e913a134ae7bac80b5ec3085dc96a
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015330"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-microsoft-teams"></a>在 Microsoft Teams 中管理组织的音频会议设置

你可以更轻松地在一个位置查看 Microsoft Teams 的所有音频会议设置。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>分配音频会议许可证

> [!NOTE]
> 使用团队的许可证，您无法将其分配。 您必须使用 Office 365 管理中心。 请参阅[业务和 Microsoft 团队许可证分配 Skype](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)。 
  
 **为用户分配许可证**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 在 **Office 365 管理中心**的左侧导航中，转到“**用户**” > “**活动用户**”，然后从可用用户列表中选择一个或多个用户。
    
    > [!NOTE]
    > [!注释] 如果要同时向多达 20 个用户分配许可证，则可以使用" **选择视图**"下拉列表，然后选择其中一个选项或创建你自己的视图。 然后单击" **编辑**"，单击 **下一步**两次，然后选择许可证并单击" **提交**"。  
  
3. 在“操作”窗格中的“**产品许可证**”下，单击“**编辑**”。 
    
4. 在**产品许可证**页上，打开 **音频会议**，然后单击 **保存**。 有关许可的详细信息，请参阅[业务和 Microsoft 团队授权加载项的 Skype](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)。
    
> [!NOTE]
> 分配许可证后，Microsoft 可能不作为最初在列表中的音频会议提供商。 如果发生这种情况，请退出 Office 365 管理中心或按 Ctrl+F5 刷新浏览器窗口。 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>启用或禁用向音频会议用户发送电子邮件

![teams-logo-30x30.png](media/teams-logo-30x30.png) **使用 Microsoft Teams 和 Skype for Business 管理中心：**

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在“**会议网桥**”页面顶部，单击“**网桥设置**”。 

3. 在“**网桥设置**”窗格中，启用或禁用“**当用户的拨入设置更改时自动向用户发送电子邮件**”。

4. 单击“**保存**”。

    
**使用 Windows PowerShell**
  
有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>更改向用户发送的电子邮件中的发件人联系信息

您可以对自动发送给用户，包括的实际的电子邮件地址和发件人的联系人信息的显示名称的电子邮件进行更改。 默认情况下，电子邮件发件人是 Office 365，但您可以更改的电子邮件地址，并且可以显示使用 Windows PowerShell 的名称。 请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。
  
## <a name="reset-the-meeting-conference-id"></a>重置会议 ID

1. 在左侧导航中，单击“**用户**”，然后从可用用户列表中选择用户。

2. 在页面顶部，单击“**编辑**”。

3. 在“**音频会议**”下，单击“**重置会议 ID**”。  

4. 在**重置的会议 ID？** 窗口中，单击**重置**。 如果启用了将电子邮件发送给用户，将自动创建会议 ID 并使用新的会议 ID 向用户发送邮件。 默认情况下启用它。

请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user-in-teams.md)。
  
## <a name="reset-a-conference-organizers-pin"></a>重置会议组织者的 PIN

用户安排的每次会议将分配到一个唯一的会议 ID。 虽然会议 ID 将自动创建并分配给用户，有时可能时用户不是要使用此和您想要将其设置为一个特定号码，或您的用户不记得丢失其会议 id。 

1. 在左侧导航中，单击“**用户**”，然后从可用用户列表中选择用户。

2. 在页面顶部，单击“**编辑**”。

3. 在“**音频会议**”下，单击“**重置 PIN**”，然后单击“**重置**”。 
  
    
当他们正在启用音频会议或 PIN 重置时，用户将收到电子邮件与他们的 PIN。 但如果您已禁用自动发送电子邮件，将不会发送的 PIN 重置电子邮件和必须手动发送给用户的 PIN。 PIN 将仅在重置后显示一次。 正在重置之后显示后，不会再显示 PIN 用户属性;而是 *** 将显示。 
  
请参阅[重置音频会议 PIN](reset-the-audio-conferencing-pin-in-teams.md)。
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>向用户发送包含音频会议信息的电子邮件

1. 在左侧导航中，单击“**用户**”，然后从可用用户列表中选择用户。

2. 在页面顶部，单击“**编辑**”。

3. 在“**音频会议**”下，单击“**通过电子邮件发送会议信息**”。 

    > [!NOTE]
    > 执行此操作时，不向用户发送音频会议 PIN。 

  
请参阅[向用户发送包含其音频会议信息的电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。
  
## <a name="setting-the-phone-numbers-included-on-invites"></a>设置包含在邀请中的电话号码。

1. 在左侧导航中，单击“**用户**”，然后从可用用户列表中选择用户。

2. 在“**音频会议**”旁边，单击“**编辑**”。
 
3. 在“**音频会议**”窗格中，可以设置**收费电话号码**，如果允许，并可以设置**免费电话号码**。

4. 单击“**保存**”。
    
请参阅[设置包含在邀请中的电话号码](set-the-phone-numbers-included-on-invites-in-teams.md)。
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a>选择音频会议网桥的设置

**设置呼叫者加入会议时的会议体验**


1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在“**会议网桥**”页面顶部，单击“**网桥设置**”。 

3. 在“**网桥设置**”窗格中，启用或禁用“**会议进入和退出通知**”。

    默认情况下启用。 如果您禁用此选项，某人进入或离开会议时，默认情况下已加入会议的用户不会将收到通知。

4. 在“**进入/退出公告类型**”下，选择“**声音**”或“**姓名或电话号码**”。 

    如果你选择“**姓名或电话号码**”，则你还可以选择启用或禁用“**要求呼叫者在加入会议之前录制其姓名**”。 

5. 单击“**保存**”。

    
请参阅[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。
  
 **设置会议的 PIN 长度**

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在“**会议网桥**”页面顶部，单击“**网桥设置**”。 

3. 在“**网桥设置**”窗格中的“**PIN 长度**”列表中输入所需的 PIN 位数，然后单击“**保存**”。

    PIN 必须介于4到12位之间。 默认值为 5。

    
请参阅[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。
  
 **启用或禁用向音频用户发送电子邮件**


1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在“**会议网桥**”页面顶部，单击“**网桥设置**”。 

3. 在“**网桥设置**”窗格中，启用或禁用“**当用户的音频会议设置更改时自动向用户发送电子邮件**”。

4. 单击“**保存**”。 
 
    你还可以转到用户的音频会议属性并单击“**通过电子邮件发送会议信息**”以向用户发送包含音频会议设置的电子邮件。
    
    如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。

请参阅[向用户发送包含其音频会议信息的电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>查看和设置音频会议网桥的主要（默认）和辅助（备用）语言

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 从列表中选择一个电话号码，然后单击“**编辑**”。

3. 在“**默认语言**”和“**备用语言 (可选)**”下选择所需语言。

4. 单击“**保存**”。


请参阅[设置音频会议自动助理语言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)。
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>请参阅音频会议拨入号码


1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 从列表中选择一个电话号码，单击**编辑**。 此处可以：
    
  - 查看 Office 365 设置要用于音频会议的电话号码。 
    
  - 查看位置，和主要语言，将使用的音频会议自动助理。

  
请参阅[音频会议号码的列表，请参阅](see-a-list-of-audio-conferencing-numbers-in-teams.md)。
  

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。
  
    
## <a name="related-topics"></a>相关主题

[管理用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


