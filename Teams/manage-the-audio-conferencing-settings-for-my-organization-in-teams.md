---
title: 管理音频会议设置
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
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: '请参阅Microsoft Teams为用户和许多其他电话拨入式会议设置分配电话拨入式会议许可证和会议 ID 的步骤。 '
ms.openlocfilehash: 41ca513706e9aeb7028266d4ac6d494d1826af1d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624584"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>在 Microsoft Teams 中管理贵组织的音频会议设置

在一个地方查看会议的所有音频会议设置Microsoft Teams更方便。 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>分配音频会议许可证

> [!NOTE]
> 你不能使用许可证分配Teams。 必须使用Microsoft 365 管理中心。 请参阅[分配Microsoft Teams许可证。](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 
  
 **为用户分配许可证**
  
1. 使用Microsoft 365或学校帐户登录登录。
    
2. 在左侧导航栏中Microsoft 365 管理中心，转到"用户  >  **""活动** 用户"，然后从可用用户列表中选择用户。
    
    > [!NOTE]
    > [!注释] 如果要同时向多达 20 个用户分配许可证，则可以使用" **选择视图**"下拉列表，然后选择其中一个选项或创建你自己的视图。 然后单击" **编辑**"，单击 **下一步** 两次，然后选择许可证并单击" **提交**"。  
  
3. 在"操作"窗格中的" **产品许可证**"下，单击" **编辑**"。 
    
4. 在 **产品许可证** 页上，打开 **音频会议**，然后单击 **保存**。 有关许可的更多内容，请参阅[Microsoft Teams附加许可。](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
    
   > [!NOTE]
   > 分配许可证后，Microsoft 最初可能不会在列表中显示为音频会议提供商。 如果发生这种情况，请注销管理中心或按 Ctrl+F5 刷新浏览器窗口。 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>启用或禁用发送给音频会议用户的电子邮件

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在"会议网桥"**页面顶部**，单击"**网桥设置"。** 

3. 在"**网桥设置"** 窗格中，启用或禁用"如果用户的拨入 **设置更改时自动发送电子邮件"。**

4. 单击“**保存**”。

    
**使用Windows PowerShell**
  
有关详细信息[，Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps)参考。
  
## <a name="reset-the-meeting-conference-id"></a>重置会议 ID

![一个图标，显示Teams ](media/teams-logo-30x30.png) **徽标使用 Microsoft Teams管理中心**

1. 在左侧导航栏中， **单击"用户**"，然后从可用用户列表中选择用户。

2. 在 **"音频会议"下**，单击"**重置会议 ID"。**  

3. 在"**重置会议 ID？"** 窗口中，单击"重置 **"。** 如果启用了将电子邮件发送给用户，将自动创建会议 ID 并使用新的会议 ID 向用户发送邮件。 默认情况下启用它。

请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user-in-teams.md)。
  
## <a name="reset-a-conference-organizers-pin"></a>重置会议组织者的 PIN

用户安排的每次会议将分配到一个唯一的会议 ID。 尽管会议 ID 将自动创建并分配给用户，但有时用户可能不想使用此 ID，而您想要将其设置为特定号码，或者您的用户无法记住或已丢失其会议 ID。 

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航栏中， **单击"用户**"，然后从可用用户列表中选择用户。

2. 在 **"音频会议"下**，单击 **"重置 PIN"，** 然后单击"重置 **"。** 
  
启用音频会议或重置 PIN 时，用户将收到一封包含 PIN 的电子邮件。 但是，如果已禁用自动发送电子邮件，则不会发送 PIN 重置电子邮件，您必须手动将 PIN 发送给用户。 PIN 将仅在重置后显示一次。 重置后显示 PIN 后，PIN 不再显示在用户属性上;而是会显示 ***** 。 
  
请参阅[重置音频会议 PIN。](reset-the-audio-conferencing-pin-in-teams.md)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>向用户发送包含音频会议信息的电子邮件

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航栏中， **单击"用户**"，然后从可用用户列表中选择用户。

2. 在 **"音频会议"下**，单击 **"通过电子邮件发送会议信息"。** 

    > [!NOTE]
    > 当你这样做时，音频会议 PIN 不会发送给用户。 

请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。
  
## <a name="set-the-phone-numbers-included-on-invites"></a>设置包含在邀请中的电话号码

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航栏中， **单击"用户**"，然后从可用用户列表中选择用户。

2. 在 **音频会议** 旁边，单击 **编辑**。
 
3. 在 **"音频会议"** 窗格中，你可以设置收费电话号码，如果允许，还可以设置 **免费电话号码**。

4. 单击“**保存**”。
    
请参阅 [设置邀请中包含的电话号码](set-the-phone-numbers-included-on-invites-in-teams.md)。
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>选择音频会议网桥设置

**当呼叫者加入会议时设置会议体验**

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在"会议网桥"**页面顶部**，单击"**网桥设置"。** 

3. 在“**网桥设置**”窗格中，启用或禁用“**会议进入和退出通知**”。

    默认情况下会启用此功能。 如果禁用此选项，则默认情况下已加入会议的用户在有人进入或离开会议时不会收到通知。

4. 在 **"进入/退出通知类型"** 下，选择"**音调**"或 **"姓名"或"电话号码"。** 

    如果选择"**姓名"或"** 电话号码"，还可以选择启用或禁用"让呼叫者在加入会议 **之前录制其姓名"。** 
    > [!NOTE]
    > 默认情况下，外部参与者看不到拨入参与者的电话号码。 如果想要保持这些电话号码的隐私，请选择“**进入/退出公告类型**”的“**提示音**”（这会阻止 Teams 读出电话号码）。


5. 单击“**保存**”。

    
请参阅 [更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。
  
 **设置会议的 PIN 长度**

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在"会议网桥"**页面顶部**，单击"**网桥设置"。** 

3. 在"**网桥设置**"窗格中，在"PIN 长度"列表中输入 PIN 的位数，然后单击"保存 **"。**

    PIN 必须介于4到12位之间。 默认值为 5。

    
请参阅 [更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。
  
 **启用或禁用向音频用户发送电子邮件**

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 在"会议网桥"**页面顶部**，单击"**网桥设置"。** 

3. 在"**网桥设置"** 窗格中，启用或禁用"如果用户的音频会议设置更改时自动 **发送电子邮件"。**

4. 单击“**保存**”。 
 
    您还可以使用音频会议设置向用户发送电子邮件，方法是：访问用户的音频会议属性，然后单击"通过电子邮件发送 **会议信息"。**
    
    如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。

请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>在音频会议网桥上查看 (和) 辅助 () 和备用语言

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 从列表中选择一个电话号码，然后单击"编辑 **"。**

3. 在"默认语言"和"备用语言"**下选择** (**可选) 。**

4. 单击“**保存**”。


请参阅[设置音频会议自动助理语言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)。
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>请参阅音频会议拨入号码

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。 

2. 从列表中选择一个电话号码，然后单击"编辑 **"。** 可在此处：
    
   - 查看用于音频会议的电话号码。 
    
   - 查看音频会议自动助理使用的位置和主要语言。

  
请参阅 [查看音频会议号码列表](see-a-list-of-audio-conferencing-numbers-in-teams.md)。
  

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用Windows PowerShell，Microsoft 365 Office 365单点管理来管理任务或任务，可在有多个任务需要执行时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为何需要将 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 管理Office 365或Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。
  
    
## <a name="related-topics"></a>相关主题

[管理用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)