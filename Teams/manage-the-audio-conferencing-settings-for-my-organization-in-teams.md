---
title: 管理音频会议设置
ms.author: heidip
author: MicrosoftHeidi
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
description: 请参阅Microsoft Teams步骤，将电话拨入式会议许可证和会议 ID 分配给用户和许多其他电话拨入式会议设置。
ms.openlocfilehash: 6d8270d21c90d363ebb74089ce0b37e6c558ecb1
ms.sourcegitcommit: 0967f725aad0a7b9c430b2e30a37ea333007558a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2022
ms.locfileid: "65106327"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>在 Microsoft Teams 中管理贵组织的音频会议设置

在一个位置查看Microsoft Teams的所有音频会议设置可能更容易。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="assign-an-audio-conferencing-license"></a>分配音频会议许可证

> [!NOTE]
> 不能使用Teams分配许可证。 必须使用Microsoft 365 管理中心。 请参阅[分配Microsoft Teams加载项许可证](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

### <a name="to-assign-a-license-for-a-user"></a>为用户分配许可证

1. 使用工作或学校帐户登录到Microsoft 365。

2. 在 **Microsoft 365 管理中心** 的左侧导航中，转到 **UsersActive** >  用户，然后从可用用户列表中选择用户或用户。

    > [!NOTE]
    > If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. 然后单击" **编辑**"，单击 **下一步** 两次，然后选择许可证并单击" **提交**"。  
  
3. 在"操作"窗格中的" **产品许可证**"下，单击" **编辑**"。

4. 在 **产品许可证** 页上，打开 **音频会议**，然后单击 **保存**。 有关许可的详细信息，请[参阅Microsoft Teams附加许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

   > [!NOTE]
   > 分配许可证后，Microsoft 可能最初不会作为音频会议提供商出现在列表中。 如果发生这种情况，请注销管理中心或按 CTRL+F5 刷新浏览器窗口。
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>启用或禁用发送给音频会议用户的电子邮件

### <a name="enable-or-disable-using-the-microsoft-teams-admin-center"></a>使用Microsoft Teams管理中心启用或禁用

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。

2. 在 **“会议桥** ”页的顶部，单击 **“桥”设置**。

3. 在 **“桥”设置** 窗格 **中，如果用户的拨入设置发生更改，则启用或禁用自动向用户发送电子邮件**。

4. 单击“**保存**”。

### <a name="enable-or-disable-using-windows-powershell"></a>使用Windows PowerShell启用或禁用

有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)。
  
## <a name="reset-the-meeting-conference-id"></a>重置会议 ID

### <a name="reset-the-meeting-conference-id-using-the-microsoft-teams-admin-center"></a>使用Microsoft Teams管理中心重置会议 ID

1. 在左侧导航栏中，单击 **“用户**”，然后从可用用户列表中选择用户。

2. 在 **“音频会议”** 下，单击 **“重置会议 ID**”。  

3. 在 **“重置会议 ID？”** 窗口中，单击 **“重置**”。 如果启用了将电子邮件发送给用户，将自动创建会议 ID 并使用新的会议 ID 向用户发送邮件。 默认情况下启用它。

请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user-in-teams.md)。

## <a name="reset-a-conference-organizers-pin"></a>重置会议组织者的 PIN

用户安排的每次会议将分配到一个唯一的会议 ID。 尽管会自动创建会议 ID 并将其分配给用户，但有时用户可能不想使用此 ID，而你想要将其设置为特定数字，或者用户无法记住或丢失其会议 ID。

### <a name="reset-a-conference-organizers-pin-using-the-microsoft-teams-admin-center"></a>使用Microsoft Teams管理中心重置会议组织者的 PIN

1. 在左侧导航栏中，单击 **“用户**”，然后从可用用户列表中选择用户。

2. 在 **“音频会议”** 下，单击 **“重置 PIN**”，然后单击 **“重置**”。
  
启用音频会议或重置 PIN 时，用户将收到带有 PIN 的电子邮件。 但是，如果已禁用自动发送电子邮件，则不会发送 PIN 重置电子邮件，并且必须手动将 PIN 发送给用户。 PIN 将仅在重置后显示一次。 在重置后显示它之后，PIN 将不再显示在用户属性上;相反，**** 将显示。
  
请参阅 [“重置音频会议 PIN](reset-the-audio-conferencing-pin-in-teams.md)”。
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>向用户发送包含音频会议信息的电子邮件

### <a name="send-an-email-using-the-microsoft-teams-admin-center"></a>使用Microsoft Teams管理中心发送电子邮件

1. 在左侧导航栏中，单击 **“用户**”，然后从可用用户列表中选择用户。

2. 在 **“音频会议”** 下，单击 **电子邮件中的“发送会议信息**”。

    > [!NOTE]
    > 执行此操作时，音频会议 PIN 不会发送给用户。

请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。
  
## <a name="set-the-phone-numbers-included-on-invites"></a>设置包含在邀请中的电话号码

### <a name="set-invite-phone-numbers-using-the-microsoft-teams-admin-center"></a>使用Microsoft Teams管理中心设置邀请电话号码

请参阅[设置Microsoft Teams中邀请中包含的电话号码](set-the-phone-numbers-included-on-invites-in-teams.md)。

> [!NOTE]
> 还可以通过将电话号码添加到 *TeamsAudioconferencingpolicy* 并将策略分配给用户来设置电话号码。 添加到策略的收费和免费电话号码优先于通过音频会议设置窗格为用户单独设置的电话号码。 如果未将电话号码添加到 *Teamsaudioconferencingpolicy*，则通过音频会议设置窗格为用户单独设置的电话号码将显示在Microsoft Teams会议请求中。 [用于收费和免费号码的音频会议策略设置](audio-conferencing-toll-free-numbers-policy.md) 包含更多信息。

## <a name="choose-audio-conferencing-bridge-settings"></a>选择音频会议网桥设置

### <a name="set-the-meeting-experience-when-callers-join-a-meeting-using-the-microsoft-teams-admin-center"></a>使用Microsoft Teams管理中心设置呼叫者加入会议时的会议体验

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。

2. 在 **“会议桥** ”页的顶部，单击 **“桥”设置**。

3. 在“**网桥设置**”窗格中，启用或禁用“**会议进入和退出通知**”。

    默认情况下启用此功能。 如果禁用此选项，默认情况下已加入会议的用户在某人进入或离开会议时不会收到通知。

4. 在 **“进入/退出公告”类型** 下，选择 **“色调** ”、“ **姓名”或“电话号码**”。

    如果选择 **“姓名”或“电话号码**”，则还可以选择启用或禁用 **“询问呼叫者”，以便在加入会议之前记录其姓名**。
    > [!NOTE]
    > 默认情况下，外部参与者看不到拨入参与者的电话号码。 如果想要保持这些电话号码的隐私，请选择“**进入/退出公告类型**”的“**提示音**”（这会阻止 Teams 读出电话号码）。
5. 单击“**保存**”。

请参阅 [“更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)”。
  
### <a name="set-the-pin-length-for-meetings"></a>设置会议的 PIN 长度

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。

2. 在 **“会议桥** ”页的顶部，单击 **“桥”设置**。

3. 在“ **桥设置”** 窗格中，在 **PIN 长度** 列表中输入 PIN 所需的数字数，然后单击“ **保存**”。

    PIN 必须介于4到12位之间。 默认值为 5。

请参阅 [“更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)”。

### <a name="enable-or-disable-email-from-being-sent-to-audio-users"></a>启用或禁用发送到音频用户的电子邮件

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。

2. 在 **“会议桥** ”页的顶部，单击 **“桥”设置**。

3. 在 **“桥”设置** 窗格中， **如果用户的音频会议设置发生更改**，则启用或禁用自动向用户发送电子邮件。

4. 单击“**保存**”。

    还可以通过转到用户的音频会议属性并单击 **电子邮件中的“发送会议信息**”，向用户发送包含音频会议设置的电子邮件。

    如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。

请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)。

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>查看和设置音频会议桥上的主要 (默认) 和辅助 (备用) 语言

### <a name="see-primary-and-secondary-languages-using-the-microsoft-teams-admin-center"></a>使用Microsoft Teams管理中心查看主要语言和辅助语言

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。

2. 从列表中选择电话号码，然后单击 **“编辑**”。

3. 在 **默认语言** 和备用语言下选择所需的 **语言 (可选)**。

4. 单击“**保存**”。

请参阅[设置音频会议自动助理语言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)。
  
## <a name="see-audio-conferencing-dial-in-numbers-using-the-microsoft-teams-admin-center"></a>使用Microsoft Teams管理中心查看音频会议拨入号码

1. 在左侧导航中，转到“**会议**” > “**会议网桥**”。

2. 从列表中选择电话号码，然后单击 **“编辑**”。 可在此处执行以下操作：

   - 查看要用于音频会议的电话号码。

   - 查看音频会议自动助理将使用的位置和主要语言。

[请参阅音频会议号码列表](see-a-list-of-audio-conferencing-numbers-in-teams.md)。

## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息？

Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用Windows PowerShell，可以使用单个管理点来管理Microsoft 365或Office 365，以便在需要执行多个任务时简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

- [为何需要使用 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [使用Windows PowerShell管理Microsoft 365或Office 365的最佳方法](/previous-versions//dn568025(v=technet.10))

有关 Windows PowerShell 的详细信息，请参阅 [Microsoft Teams PowerShell 参考](/powershell/module/teams/?view=teams-ps)了解详细信息。

## <a name="related-topics"></a>相关主题

[管理用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)
