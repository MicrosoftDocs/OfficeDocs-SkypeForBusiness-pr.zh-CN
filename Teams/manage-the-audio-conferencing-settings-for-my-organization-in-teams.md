---
title: 在 Microsoft Teams 中管理贵组织的音频会议设置
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
- M365-collaboration
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: '了解为用户分配电话拨入式会议许可证和会议 ID 的 Microsoft Teams 步骤以及许多其他电话拨入式会议设置。 '
ms.openlocfilehash: b8a93b9f6ad47b4b1f4203e4611331bfe3c13b59
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2019
ms.locfileid: "34343911"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>在 Microsoft Teams 中管理贵组织的音频会议设置

你可以更轻松地在一个位置查看 Microsoft Teams 的所有音频会议设置。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>分配音频会议许可证

> [!NOTE]
> 不能使用 Teams 分配许可证。 您必须使用 Microsoft 365 管理中心。 请参阅[分配 Skype for Business 和 Microsoft Teams 许可证](assign-teams-licenses.md)。 
  
 **为用户分配许可证**
  
1. 使用你的工作或学校帐户登录 Microsoft 365。
    
2. 在**Microsoft 365 管理中心**的左侧导航中, 转到 "**用户** > **活动用户**", 然后从可用的用户列表中选择一个或一组用户。
    
    > [!NOTE]
    > [!注释] 如果要同时向多达 20 个用户分配许可证，则可以使用" **选择视图**"下拉列表，然后选择其中一个选项或创建你自己的视图。 然后单击“**编辑**”，再单击“**下一步**”两次，然后选择许可证并单击“**提交**”。  
  
3. 在“操作”窗格中的“**产品许可证**”下，单击“**编辑**”。 
    
4. 在“**产品许可证**”页面上，开启“**音频会议**”，然后单击“**保存**”。 有关许可的详细信息, 请参阅[Microsoft 团队加载项许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
    
> [!NOTE]
> 在分配许可证后，Microsoft 最初可能不会作为音频会议提供商显示在下拉列表中。 如果发生这种情况，请注销 Office 365 管理中心或按 Ctrl+F5 刷新浏览器窗口。 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>启用或禁用向音频会议用户发送电子邮件

![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在“**会议网桥**”页面顶部，单击“**网桥设置**”。 

3. 在“**网桥设置**”窗格中，启用或禁用“**当用户的拨入设置更改时自动向用户发送电子邮件**”。

4. 单击“**保存**”。

    
**使用 Windows PowerShell**
  
有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。
  
## <a name="reset-the-meeting-conference-id"></a>重置会议 ID

![](media/teams-logo-30x30.png) **使用 Microsoft 团队管理中心**显示团队徽标的图标

1. 在左侧导航中, 单击 "**用户**", 然后从可用用户列表中选择用户。

2. 在 "**音频会议**" 下, 单击 "**重置会议 ID**"。  

3. 在 "**重置会议 ID"** 窗口中, 单击 "**重置**"。 如果启用了将电子邮件发送给用户，将自动创建会议 ID 并使用新的会议 ID 向用户发送邮件。 默认情况下启用它。

请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user-in-teams.md)。
  
## <a name="reset-a-conference-organizers-pin"></a>重置会议组织者的 PIN

用户安排的每次会议将分配到一个唯一的会议 ID。 尽管将自动创建会议 ID 并将其分配给用户, 但有时用户不希望使用此 ID, 并且您想要将其设置为特定的号码, 或者您的用户忘记或丢失了其会议 ID。 

![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

1. 在左侧导航中, 单击 "**用户**", 然后从可用用户列表中选择用户。

2. 在 "**音频会议**" 下, 单击 "**重置 PIN**", 然后单击 "**重置**"。 
  
当启用音频会议或 PIN 重置时, 用户将收到其 PIN 的电子邮件。 但是, 如果您已禁用自动发送电子邮件, 则不会发送 PIN 重置电子邮件, 您必须手动将 PIN 发送给用户。 PIN 将仅在重置后显示一次。 在重置后, 该 PIN 将不再显示在用户的属性上, 而是将不再显示。此时将显示 * * * * * *。 
  
请参阅[重置音频会议 PIN 码](reset-the-audio-conferencing-pin-in-teams.md)。
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>向用户发送包含音频会议信息的电子邮件

![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

1. 在左侧导航中, 单击 "**用户**", 然后从可用用户列表中选择用户。

2. 在 "**音频会议**" 下, 单击 "**通过电子邮件发送会议信息**"。 

    > [!NOTE]
    > 执行此操作时, 音频会议 PIN 不会发送给用户。 

请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。
  
## <a name="set-the-phone-numbers-included-on-invites"></a>设置包含在邀请中的电话号码

![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

1. 在左侧导航中, 单击 "**用户**", 然后从可用用户列表中选择用户。

2. 在**音频会议**旁边，单击**编辑**。
 
3. 在 "**音频会议**" 窗格中, 您可以设置**收费号码**, 如果允许, 还可以设置免费**电话号码**。

4. 单击“**保存**”。
    
请参阅[设置邀请附带的电话号码](set-the-phone-numbers-included-on-invites-in-teams.md)。
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>选择 "音频会议桥" 设置

**设置呼叫者加入会议时的会议体验**

![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在 "**会议桥**" 页面顶部, 单击 "**桥接设置**"。 

3. 在“**网桥设置**”窗格中，启用或禁用“**会议进入和退出通知**”。

    默认情况下, 此功能处于启用状态。 如果禁用此选项, 当有人进入或离开会议时, 已加入会议的用户不会收到通知。

4. 在 "**输入/退出通知类型**" 下, 选择 "**声音**" 或 "姓名"**或 "电话号码**"。 

    如果选择 "**姓名" 或 "电话号码**", 还可以选择在**加入会议之前启用或禁用 Ask 呼叫者录制其姓名**。 

5. 单击“**保存**”。

    
请参阅[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。
  
 **设置会议的 PIN 长度**

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在 "**会议桥**" 页面顶部, 单击 "**桥接设置**"。 

3. 在 "**桥设置**" 窗格中, 在 " **pin 长度**" 列表中输入 pin 所需的位数, 然后单击 "**保存**"。

    PIN 必须介于4到12位之间。 默认值为 5。

    
请参阅[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。
  
 **启用或禁用向音频用户发送电子邮件**

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在 "**会议桥**" 页面顶部, 单击 "**桥接设置**"。 

3. 在 "**桥设置**" 窗格中,**如果用户的音频会议设置发生更改**, 则启用或禁用 "自动向用户发送电子邮件"。

4. 单击“**保存**”。 
 
    您还可以通过音频会议设置向用户发送电子邮件, 方法是转到用户的音频会议属性, 然后单击 **"在电子邮件中发送会议信息**"。
    
    如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。

请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>在音频会议桥处查看和设置主要 (默认) 和辅助 (备用) 语言

![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 从列表中选择电话号码, 然后单击 "**编辑**"。

3. 选择 "**默认语言**" 和 "**备用语言 (可选)**" 下所需的语言。

4. 单击“**保存**”。


请参阅[设置音频会议自动助理语言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)。
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>请参阅音频会议拨入号码

![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 从列表中选择电话号码, 然后单击 "**编辑**"。 可在此处执行以下操作:
    
   - 查看由 Office 365 设置用于音频会议的电话号码。 
    
   - 查看音频会议自动助理将使用的位置和主要语言。

  
请参阅[音频会议号码列表](see-a-list-of-audio-conferencing-numbers-in-teams.md)。
  

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)了解详细信息。
  
    
## <a name="related-topics"></a>相关主题

[管理用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)


