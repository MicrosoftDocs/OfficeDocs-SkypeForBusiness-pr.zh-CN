---
title: 在 Skype for Business Online 中管理我的组织的音频会议设置
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
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
description: '请参阅 Skype for business Online 步骤，将电话拨入式会议许可证和会议 ID 分配给用户以及其他许多电话拨入式会议设置。 '
ms.openlocfilehash: aa8e9cbaf063ebf1780e3f8ce45b7bd54ced474f
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164141"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>在 Skype for Business Online 中管理我的组织的音频会议设置

> [!NOTE]
> 如果您要在团队中管理这些设置，请参阅 [在 Microsoft Teams 中管理我的组织的音频会议设置](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams) 。

您可以更轻松地在一个位置查看 Skype for business 的所有音频会议设置。


## <a name="assign-an-audio-conferencing-license"></a>分配音频会议许可证

> [!NOTE]
> 您不能使用**Skype For business 管理中心**分配许可证。您必须使用 Microsoft 365 管理中心。请参阅[分配 Skype For business 许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。

 **为用户分配许可证**

1. 使用你的工作或学校帐户登录。

2. 在管理中心的左侧导航中，转到 "**用户** > **活动用户**"，然后从可用的用户列表中选择一个或一组用户。

    > [!NOTE]
    > If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view. Then click **Edit**, **Next** twice then select the license and click **Submit**. You can also assign licenses to multiple users by using Windows Powershell. For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

3. 在"操作"窗格中的" **产品许可证**"下，单击" **编辑**"。

4. On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**. For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

> [!NOTE]
> 分配许可证后，Microsoft 可能不会以音频会议提供商的形式最初显示在列表中。如果出现这种情况，请注销管理中心或按 CTRL + F5 刷新浏览器窗口。

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>启用或禁用发送给音频会议用户的电子邮件

![显示 Skype for Business 徽标的图标](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**

1. 使用你的工作或学校帐户登录。

2. 转到管理中心 > **Skype for** business，然后在左侧导航中，单击 "**音频会议**"。

3. 在  **Microsoft 网桥的设置** 页上，选中或清除 **自动向用户发送电子邮件，如果他们的音频会议设置更改**   。

4. 单击“**保存**”。

    You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**. The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.

    请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**使用 Windows PowerShell**

- 你还可以使用 Windows PowerShell 并运行以下命令：

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    你可以使用[set-csonlinedialinconferencingtenantsettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)管理组织的其他设置，包括电子邮件。

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>更改发送给用户的电子邮件中的发件人的联系人信息

您可以对自动发送给您的用户的电子邮件进行更改，包括实际电子邮件地址和发件人的联系人信息的显示名称。默认情况下，电子邮件的发件人是 Microsoft 365 或 Office 365，但你可以使用 Windows PowerShell 和[set-csonlinedialinconferencingtenantsettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet 更改电子邮件地址和显示名称。若要对向用户发送电子邮件的电子邮件地址进行更改，必须执行以下操作：

- 在_SendEmailFromAddress_参数中输入电子邮件地址。

- 在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。

- 将_SendEmailOverride_参数设置为 _True_。

你可以运行如下命令，更改发送给用户的电子邮件，例如电子邮件的发件人电子邮件地址，或者电子邮件的显示名称：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

如果要更改电子邮件地址信息，你需要确保你的组织的入站电子邮件策略允许来自自定义电子邮件地址的电子邮件。

你可以使用[set-csonlinedialinconferencingtenantsettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet 管理你的组织的其他设置，包括电子邮件。

请参阅[在用户的音频会议设置更改时自动发送给用户的电子邮件](emails-sent-to-users-when-their-settings-change.md)。

## <a name="reset-the-meeting-conference-id"></a>重置会议 ID

1. 使用你的工作或学校帐户登录。

2. 转到管理中心 > **Skype For business**。

3. 在**Skype for Business 管理中心**，在左侧导航窗格中，转到 **音频会议**，并在 **会议 ID**下的操作窗格中，单击 **重置**。

4. In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.

    > [!IMPORTANT]
    >  After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).

请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。

## <a name="reset-a-conference-organizers-pin"></a>重置会议组织者的 PIN

Each meeting that a user schedules will get assigned a unique conference ID. Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID. You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.


1. 使用你的工作或学校帐户登录。

2. 转到管理中心 > **Skype for** business，然后在左侧导航中，单击 "**音频会议**"。

3. 单击 "**用户**"，然后选择要为其重置 PIN 的用户。

4. 在操作窗格中的 "**固定**" 下，单击 "**重置**"。

Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, ***** will be shown.

请参阅[重置音频会议 PIN 码](reset-the-audio-conferencing-pin.md)。

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>向用户发送包含音频会议信息的电子邮件

1. 使用你的工作或学校帐户登录。

2. 转到管理中心 > **Skype for** business，然后在左侧导航中，单击 "**音频会议**"。

3. 单击 "**用户**"，然后选择要为其重置 PIN 的用户。

4. 在操作窗格中，单击" **通过电子邮件发送会议信息**"。

    > [!NOTE]
    > 执行此操作时，音频会议 PIN 不会发送给用户。

请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。

## <a name="setting-the-phone-numbers-included-on-invites"></a>设置邀请中包含的电话号码

1. 使用你的工作或学校帐户登录。

2. 转到管理中心 > **Skype For business**。

3. In the left navigation, go to **Audio conferencing** > **Users**. Select the user that you want to enable for Audio Conferencing.

4. 在操作窗格中，您可以设置 　**收费电话号码**　，如果允许， **免费电话号码**　。

5. 单击“**保存**”。

请参阅[设置邀请附带的电话号码](set-the-phone-numbers-included-on-invites.md)。


## <a name="choosing-audio-conferencing-bridge-settings"></a>选择音频会议网桥的设置

**设置呼叫者加入会议时的会议体验**


1. 使用你的工作或学校帐户登录。

2. 转到管理中心 > **Skype For business**。

3. 在**Skype for business 管理中心**的左侧导航中，转到 "**音频会议** > **Microsoft 网桥设置**"。

4. 在 "**会议加入体验**" 下，选择以下操作：

   - **Enable meeting entry and exit notifications to be turned on** This is selected by default. If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.

     当用户使用 Skype for Business 应用加入会议，并且他们在会议的 "Skype 会议**选项**" 菜单中修改 "**当用户进入或离开时通知**" 设置时，可以按会议进行设置。

   - **Ask callers to record their name before joining the meeting** This is selected by default. If you clear this check box, callers won't be asked to record their name before they join a meeting.

5. 完成更改后，单击" **保存**"。
    
请参阅[更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。
  
 **设置会议的 PIN 长度**

1. 使用你的工作或学校帐户登录。

2. 转到管理中心 > **Skype For business**。

3. 在**Skype for business 管理中心**的左侧导航中，转到 "**音频会议** > **Microsoft 网桥设置**"。

4. 在 "**安全**" 下，在 " **pin 长度**" 列表中输入您希望的 pin 位数，然后单击 "**保存**"。

    The PIN must be between 4 and 12 digits. The default is 5.
    
请参阅[更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。
  
 **启用或禁用向音频用户发送电子邮件**

1. 使用你的工作或学校帐户登录。

2. 转到管理中心 > **Skype for** business，然后在左侧导航中，单击 "**音频会议**"。

3. 在 **Microsoft 网桥的设置** 页上，选中或清除 **自动向用户发送电子邮件，如果他们的音频会议设置更改**　。

4. 单击“**保存**”。

    您还可以通过音频会议设置向用户发送电子邮件，方法是转到用户的音频会议属性，然后单击 "**通过电子邮件发送会议信息**"。

    如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。

    请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>在音频会议桥处查看和设置主要（默认）和辅助（备用）语言


1. 使用你的工作或学校帐户登录。

2. 转到管理中心 > **Skype For business**。

3. 在**Skype For business 管理中心**的左侧导航中，转到 "**音频会议**"，然后单击 " **Microsoft bridge**"。

4. 从列表中选择电话号码，在 "操作" 窗格中单击 "**设置语言**"，然后在 "**设置语言**" 页面上，单击 "使用**主要语言**列表" 查看受支持语言的完整列表。

    You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.

请参阅[设置音频会议自动助理语言](set-auto-attendant-languages-for-audio-conferencing.md)。

## <a name="see-audio-conferencing-dial-in-numbers"></a>请参阅音频会议拨入号码

1. 使用你的工作或学校帐户登录。

2. 转到管理中心 > **Skype For business**。
 
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:

   - 查看由 Microsoft 365 或 Office 365 设置用于音频会议的电话号码。

   - 查看音频会议自动助理将使用的位置以及主要和辅助语言。

   - Select the default phone number that will be given to users when they are enabled for Audio Conferencing. However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.

您可以转到**音频会议** > **用户**并选择用户的属性以更改用户的默认号码，方法是从您的组织中可用的号码列表中选择新号码。

请参阅[音频会议号码列表](see-a-list-of-audio-conferencing-numbers.md)。

## <a name="see-a-list-of-users-that-are-enabled"></a>查看启用的用户的列表

1. 使用你的工作或学校帐户登录。

2. 转到管理中心 > **Skype For business**。

3. 在**Skype For business 管理中心**的左侧导航中，转到 "**音频会议**>" 和 "**用户**"。

请参阅[请参阅启用了音频会议的用户列表](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)。

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

There are several settings that you can manage at the organization level using Windows PowerShell. This makes it easy to apply settings to all of your users.

要获得有关每个 cmdlet 的更多帮助，请参阅 [Skype for Business Online cmdlet](https://go.microsoft.com/fwlink/?LinkId=627324)。

下面是组织级设置：

- **设置输入/退出通知** 默认值为 _$true_ 。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- **设置名称录制** 默认值为 _$true_ 。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **设置 PIN 长度** 默认值为 5。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **仅从电话中设置拨入会议**默认 _$false_。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **设置是否向用户发送电子邮件**默认值为 _$true_。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **设置是否从不同的帐户发送电子邮件** 默认值为 _$false_ 。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **在发送给用户的电子邮件中设置发件地址** 默认值为 _$null_。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **为发送给用户的电子邮件设置显示名称**默认值为 _$null_。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a>希望了解有关 Windows PowerShell 的详细信息
- Windows PowerShell 全部用于管理用户以及允许或禁止用户执行的操作。使用 Windows PowerShell，你可以使用单一的管理点管理 Microsoft 365 或 Office 365，这可以在你有多个任务时简化日常工作。若要开始使用 Windows PowerShell，请参阅以下主题：

  - [为什么需要使用 Microsoft 365 或 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [通过 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](https://go.microsoft.com/fwlink/?LinkId=525142)

- Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用管理中心，例如当你为多个用户同时进行设置更改时。了解以下主题中的这些优势：

  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)

    [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。

## <a name="related-topics"></a>相关主题

[管理用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user.md)


