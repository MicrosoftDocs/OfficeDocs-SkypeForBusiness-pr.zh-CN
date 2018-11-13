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
ms.openlocfilehash: b63650833c7c844de11ecb833288b6568604f919
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296094"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-microsoft-teams"></a>在 Microsoft Teams 中管理组织的音频会议设置

你可以更轻松地在一个位置查看 Microsoft Teams 的所有音频会议设置。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>分配音频会议许可证

> [!NOTE]
> 不能使用 Teams 分配许可证。 必须使用 Office 365 管理中心。 请参阅[分配 Skype for Business 和 Microsoft Teams 许可证](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)。 
  
 **为用户分配许可证**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 在 **Office 365 管理中心**的左侧导航中，转到“**用户**” > “**活动用户**”，然后从可用用户列表中选择一个或多个用户。
    
    > [!NOTE]
    > [!注释] 如果要同时向多达 20 个用户分配许可证，则可以使用" **选择视图**"下拉列表，然后选择其中一个选项或创建你自己的视图。 然后单击“**编辑**”，再单击“**下一步**”两次，然后选择许可证并单击“**提交**”。  
  
3. 在“操作”窗格中的“**产品许可证**”下，单击“**编辑**”。 
    
4. 在“**产品许可证**”页面上，开启“**音频会议**”，然后单击“**保存**”。 有关许可的详细信息，请参阅 [Skype for Business 和 Microsoft Teams 加载项许可](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)。
    
> [!NOTE]
> 在分配许可证后，Microsoft 最初可能不会作为音频会议提供商显示在下拉列表中。 如果发生这种情况，请注销 Office 365 管理中心或按 Ctrl+F5 刷新浏览器窗口。 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>启用或禁用向音频会议用户发送电子邮件

![teams-logo-30x30.png](media/teams-logo-30x30.png) **使用 Microsoft Teams 和 Skype for Business 管理中心：**

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在“**会议网桥**”页面顶部，单击“**网桥设置**”。 

3. 在“**网桥设置**”窗格中，启用或禁用“**当用户的拨入设置更改时自动向用户发送电子邮件**”。

4. 单击“**保存**”。

    
**使用 Windows PowerShell**
  
有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>更改向用户发送的电子邮件中的发件人联系信息

你可以更改自动向用户发送的电子邮件，包括实际电子邮件地址和发件人联系信息的显示名称。 默认情况下，这些电子邮件的发件人显示为来自 Office 365，但你可以使用 Windows PowerShell 更改电子邮件地址和显示名称。 有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。
  
## <a name="reset-the-meeting-conference-id"></a>重置会议 ID

![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。

2. 在“**音频会议**”下，单击“**重置会议 ID**”。  

3. 在“**重置会议 ID?**”窗口中，单击“**重置**”。 如果启用了将电子邮件发送给用户，将自动创建会议 ID 并使用新的会议 ID 向用户发送邮件。 默认情况下处于启用状态。

请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user-in-teams.md)。
  
## <a name="reset-a-conference-organizers-pin"></a>重置会议组织者的 PIN

用户安排的每次会议将分配到一个唯一的会议 ID。 虽然会自动创建会议 ID 并将其分配给用户，但有时可能会存在以下情况：用户不希望使用此会议 ID，你希望将其设置为特定号码，或者你的用户记不住或丢失了其会议 ID。 

![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。

2. 在“**音频会议**”下，单击“**重置 PIN**”，然后单击“**重置**”。 
  
当为用户启用了音频会议时或重置 PIN 时，用户将收到包含其 PIN 的电子邮件。 但如果你已禁用自动发送电子邮件，则不会发送 PIN 重置电子邮件，并且你必须手动向用户发送 PIN 信息。 PIN 将仅在重置后显示一次。 PIN 在重置后即会显示，但 PIN 不会再显示在用户属性上，而是会显示 *****。 
  
请参阅[重置音频会议 PIN](reset-the-audio-conferencing-pin-in-teams.md)。
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>向用户发送包含音频会议信息的电子邮件

![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。

2. 在“**音频会议**”下，单击“**通过电子邮件发送会议信息**”。 

    > [!NOTE]
    > 执行此操作时，不向用户发送音频会议 PIN。 

请参阅[向用户发送包含其音频会议信息的电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。
  
## <a name="set-the-phone-numbers-included-on-invites"></a>设置包含在邀请中的电话号码

![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。

2. 在**音频会议**旁边，单击**编辑**。
 
3. 在**音频会议**窗格中，您可以设置**收费电话号码**，如果允许，**免费电话号码**。

4. 单击“**保存**”。
    
请参阅[设置的电话号码包含在邀请](set-the-phone-numbers-included-on-invites-in-teams.md)。
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>选择音频会议网桥的设置

**呼叫者加入会议时设置的会议体验**

![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在**会议桥**页的顶部，单击**网桥的设置**。 

3. 在“**网桥设置**”窗格中，启用或禁用“**会议进入和退出通知**”。

    默认情况下启用。 如果您禁用此选项，某人进入或离开会议时，默认情况下已加入会议的用户不会将收到通知。

4. 在**项/退出通知类型**下选择**音**或**姓名或电话号码**。 

    如果您选择**姓名或电话号码**，可以选择启用或禁用**Ask 呼叫者在记录其姓名之前加入会议**。 

5. 单击“**保存**”。

    
请参阅[更改现有音频会议桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。
  
 **设置会议的 PIN 长度**

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在**会议桥**页的顶部，单击**网桥的设置**。 

3. 在**桥设置**窗格中，输入您希望在**PIN 长度**列表中，PIN 的位数，然后单击**保存**。

    PIN 必须介于4到12位之间。 默认值为 5。

    
请参阅[更改现有音频会议桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。
  
 **启用或禁用从发送给音频的用户的电子邮件**

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在**会议桥**页的顶部，单击**网桥的设置**。 

3. 在**桥设置**窗格中，启用或禁用**自动发送电子邮件发送给用户，如果其音频会议设置更改**。

4. 单击“**保存**”。 
 
    您还可以发送电子邮件向用户音频会议设置后，转到用户的音频会议属性，单击**发送电子邮件中的会议信息**。
    
    如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。

请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>请参阅和上一个音频会议网桥设置主 （默认值） 和辅助 （备用） 语言

![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 从列表中选择一个电话号码，单击**编辑**。

3. 选择**默认语言**和 **（可选） 的备用语言**下所需的语言。

4. 单击“**保存**”。


请参阅[设置音频会议自动助理语言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)。
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>请参阅音频会议拨入号码

![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

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


