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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: '请参阅 Skype for Business Online 步骤，为用户和许多其他电话拨入式会议设置分配电话拨入式会议许可证和会议 ID。 '
ms.openlocfilehash: eb5313729c2071a64e5d6495e460dbaa475df305
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012126"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>在 Skype for Business Online 中管理我的组织的音频会议设置

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> 如果您要在团队中管理这些设置，请参阅 [在 Microsoft Teams 中管理我的组织的音频会议设置](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams) 。

在一个地方查看 Skype for Business 的所有音频会议设置可能会更方便。


## <a name="assign-an-audio-conferencing-license"></a>分配音频会议许可证

> [!NOTE]
> 你不能使用 Skype for Business 管理中心 **分配许可证**。 必须使用 Microsoft 365 管理中心。 请参阅[分配 Skype for Business 许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。

 **为用户分配许可证**

1. 使用工作或学校帐户登录。

2. 在管理中心的左侧导航中，转到"用户  >  **""活动** 用户"，然后从可用用户列表中选择用户。

    > [!NOTE]
    > [!注释] 如果要同时向多达 20 个用户分配许可证，则可以使用" **选择视图**"下拉列表，然后选择其中一个选项或创建你自己的视图。 然后单击" **编辑**"，单击 **下一步** 两次，然后选择许可证并单击" **提交**"。 你也可以使用 Windows Powershell 向多个用户分配许可证。 有关说明和示例 PowerShell 脚本，请参阅 [分配 Skype for Business 许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。

3. 在"操作"窗格中的" **产品许可证**"下，单击" **编辑**"。

4. 在 **产品许可证** 页上，打开 **音频会议**，然后单击 **保存**。 有关许可的更多信息，请参阅 [Skype for Business 附加许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。

> [!NOTE]
> 分配许可证后，Microsoft 最初可能不会在列表中显示为音频会议提供商。 如果发生这种情况，请注销管理中心或按 Ctrl+F5 刷新浏览器窗口。

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>启用或禁用发送给音频会议用户的电子邮件

![显示 Skype for Business 徽标的图标。](../images/sfb-logo-30x30.png) **使用 Skype for Business 管理中心**

1. 使用工作或学校帐户登录。

2. 转到 Skype **for Business** >管理中心，在左侧导航栏中单击"**音频会议"。**

3. 在 **Microsoft 网桥的设置** 页上，选中或清除 **自动向用户发送电子邮件，如果他们的音频会议设置更改**　。

4. 单击“**保存**”。

    您还可以使用音频会议设置向用户发送电子邮件，方法是：访问用户的音频会议属性，然后单击"**通过电子邮件发送会议信息"。** 会议 ID 和默认音频会议电话号码包含在会议邀请中，但不包括 PIN。

    请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**使用Windows PowerShell**

- 你还可以使用 Windows PowerShell 并运行以下命令：

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) 管理组织的其他设置，包括电子邮件。

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>在发送给用户的电子邮件中更改发件人的联系信息

您可以更改自动发送给用户的电子邮件，包括实际电子邮件地址和显示名称发件人的联系信息。 默认情况下，电子邮件的发件人是 Microsoft 365 或 Office 365，但您可以使用 Windows PowerShell 和 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet 更改电子邮件地址和 显示名称。 若要更改向用户发送电子邮件的电子邮件地址，必须：

- 在 _SendEmailFromAddress 参数中输入_ 电子邮件地址。

- 在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。

- 将 _SendEmailOverride_ 参数设置为 _True_。

你可以运行如下命令，更改发送给用户的电子邮件，例如电子邮件的发件人电子邮件地址，或者电子邮件的显示名称：

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

如果要更改电子邮件地址信息，你需要确保你的组织的入站电子邮件策略允许来自自定义电子邮件地址的电子邮件。

可以使用 [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet 管理组织的其他设置，包括电子邮件。

请参阅 [当用户的音频会议设置更改时自动发送给用户的电子邮件](emails-sent-to-users-when-their-settings-change.md)。

## <a name="reset-the-meeting-conference-id"></a>重置会议 ID

1. 使用工作或学校帐户登录。

2. 转到 Skype for Business > **管理中心**。

3. 在 **Skype for Business 管理中心**，在左侧导航窗格中，转到 **音频会议**，并在 **会议 ID** 下的操作窗格中，单击 **重置**。

4. 在"**重置会议 ID？"** 窗口中，单击"**是"。** 如果启用了将电子邮件发送给用户，将自动创建会议 ID 并使用新的会议 ID 向用户发送邮件。 默认情况下启用它。

    > [!IMPORTANT]
    >  [!重要信息] 创建新会议 ID 后，呼叫者不能再使用旧会议 ID。 应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。 用户可以使用 Skype for Business 会议迁移工具来更新其现有会议。 若要了解如何下载、安装和运行 Skype for Business 会议更新工具，请参阅 [：Skype for Business](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)和 Lync 的会议更新工具 [、Skype for Business Online、会议迁移工具 (64 ](https://go.microsoft.com/fwlink/?LinkID=626047)位) 和 Skype for Business Online 会议迁移工具 ( [32 ](https://www.microsoft.com/download/details.aspx?id=54079)位) 。

请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。

## <a name="reset-a-conference-organizers-pin"></a>重置会议组织者的 PIN

用户安排的每次会议将分配到一个唯一的会议 ID。 尽管会议 ID 将自动创建并分配给用户，但有时用户可能不想使用此 ID，而您想要将其设置为特定号码，或者您的用户无法记住或已丢失其会议 ID。 可以使用 Skype for Business 管理中心和 Windows PowerShell 来查看、更改和重置其会议 ID。


1. 使用工作或学校帐户登录。

2. 转到 Skype **for Business** >管理中心，在左侧导航栏中单击"**音频会议"。**

3. 单击 **"** 用户"，然后选择要重置其 PIN 的用户。

4. 在"操作"窗格中的 **"PIN"下**，单击"**重置"。**

启用音频会议或重置 PIN 时，用户将收到一封包含 PIN 的电子邮件。 但是，如果已禁用自动发送电子邮件，则不会发送 PIN 重置电子邮件，您必须手动将 PIN 发送给用户。 PIN 将仅在重置后显示一次。 重置后显示 PIN 后，PIN 不再显示在用户属性上;而是会显示 ***** 。

请参阅[重置音频会议 PIN。](reset-the-audio-conferencing-pin.md)

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>向用户发送包含音频会议信息的电子邮件

1. 使用工作或学校帐户登录。

2. 转到 Skype **for Business** >管理中心，在左侧导航栏中单击"**音频会议"。**

3. 单击 **"** 用户"，然后选择要重置其 PIN 的用户。

4. 在操作窗格中，单击" **通过电子邮件发送会议信息**"。

    > [!NOTE]
    > 当你这样做时，音频会议 PIN 不会发送给用户。

请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。

## <a name="setting-the-phone-numbers-included-on-invites"></a>设置邀请中包含的电话号码

1. 使用工作或学校帐户登录。

2. 转到 Skype for Business > **管理中心**。

3. 在左侧导航窗格中，转到 **音频会议** > **用户** 　。 选择要为音频会议启用的用户。

4. 在操作窗格中，您可以设置 　**收费电话号码**　，如果允许， **免费电话号码**　。

5. 单击“**保存**”。

请参阅 [设置邀请中包含的电话号码](set-the-phone-numbers-included-on-invites.md)。


## <a name="choosing-audio-conferencing-bridge-settings"></a>选择音频会议网桥的设置

**当呼叫者加入会议时设置会议体验**


1. 使用工作或学校帐户登录。

2. 转到 Skype for Business > **管理中心**。

3. 在 **Skype for Business 管理中心的** 左侧导航中，转到"**音频会议**  >  **""Microsoft 网桥设置"。**

4. 在 **"会议加入体验"** 下，选择以下操作：

   - " **启用会议进入和退出通知**"此选项默认情况下选中。 如果清除此复选框，则默认情况下已加入会议的用户在有人进入或离开会议时不会收到通知。

     当用户使用 Skype for Business 应用加入会议，并修改会议"Skype 会议选项"菜单中的"何时进入或离开时通知"设置时，可以按 **会议进行此设置**。

   - " **要求呼叫者在加入会议之前录制其名称**"此选项默认情况下选中。 如果清除此复选框，呼叫者在加入会议之前不会要求他们录制其姓名。

5. 完成更改后，单击" **保存**"。
    
请参阅 [更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。
  
 **设置会议的 PIN 长度**

1. 使用工作或学校帐户登录。

2. 转到管理中心 **> Skype for Business。**

3. 在 **Skype for Business管理** 中心的 左侧导航中，转到"**音频会议**  >  **""Microsoft 网桥设置"。**

4. 在 **"安全性**"下，在"PIN 长度"列表中输入 PIN的位数，然后单击"保存 **"。**

    PIN 必须介于4到12位之间。 默认值为 5。
    
请参阅 [更改音频会议网桥的设置](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)。
  
 **启用或禁用向音频用户发送电子邮件**

1. 使用工作或学校帐户登录。

2. 转到管理中心 **> Skype for Business** 导航中，单击"音频 **会议"。**

3. 在 **Microsoft 网桥的设置** 页上，选中或清除 **自动向用户发送电子邮件，如果他们的音频会议设置更改**　。

4. 单击“**保存**”。

    您还可以使用音频会议设置向用户发送电子邮件，方法是：访问用户的音频会议属性，然后单击"通过电子邮件发送 **会议信息"。**

    如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。

    请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>在音频会议网桥上 (和) 辅助 (和) 语言的主要语言


1. 使用工作或学校帐户登录。

2. 转到管理中心 **> Skype for Business。**

3. 在 Skype for Business **管理** 中心的 左侧导航中，转到"**音频会议**"，然后单击 **"Microsoft 网桥"。**

4. 从列表中选择一个电话号码，单击"操作"窗格中的"设置语言"，然后在"设置语言"页上，单击"使用主要语言"列表查看受支持语言的完整列表。 

    还可以设置选择 Microsoft 作为音频会议提供商时支持的主要和辅助语言。 您在列表中选择的顺序与将语言呈现给调用方的顺序相同。

请参阅[设置音频会议自动助理语言](set-auto-attendant-languages-for-audio-conferencing.md)。

## <a name="see-audio-conferencing-dial-in-numbers"></a>请参阅音频会议拨入号码

1. 使用工作或学校帐户登录。

2. 转到管理中心 **> Skype for Business。**
 
3. 在 **Skype for Business管理** 中心的 左侧导航中，转到音频 **会议**  >  **Microsoft 网桥**。 可在此处：

   - 查看由音频会议Microsoft 365或Office 365设置的电话号码。

   - 查看音频会议自动助理使用的位置以及主要和辅助语言。

   - 选择为用户启用音频会议时将给予他们的默认电话号码。 但是，如果音频会议网桥的默认电话号码发生更改，则现有用户的默认电话号码不会更改。

你可以转到"**音频** 会议用户"并选择用户的属性，通过从组织中可用的号码列表中选择新号码来更改  >  用户的默认号码。

请参阅 [查看音频会议号码列表](see-a-list-of-audio-conferencing-numbers.md)。

## <a name="see-a-list-of-users-that-are-enabled"></a>查看启用的用户的列表

1. 使用工作或学校帐户登录。

2. 转到管理中心 **> Skype for Business。**

3. 在 **Skype for Business管理** 中心的 左侧导航中，转到"音频会议">"用户 **"。** 

请参阅[请参阅启用了音频会议的用户列表](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)。

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

可以使用以下方法在组织级别管理多个Windows PowerShell。 这样，就可以轻松将设置应用到所有用户。

要获得有关每个 cmdlet 的更多帮助，请参阅 [Skype for Business Online cmdlet](/previous-versions//mt228132(v=technet.10))。

下面是组织级别的设置：

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

- **仅从电话中设置拨入会议** 默认 _$false_。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **设置是否向用户发送电子邮件** 默认值为 _$true_。
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

- **为发送给用户的电子邮件设置显示名称** 默认值为 _$null_。
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关Windows PowerShell
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。 使用Windows PowerShell，可以使用Microsoft 365管理Office 365管理点来管理任务或任务，当您有多个任务需要执行时，可以简化日常工作。 若要开始使用 Windows PowerShell，请参阅下列主题：

  - [为何需要将 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [使用 Microsoft 365 Office 365管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))

- Windows PowerShell管理中心相比，Windows PowerShell在速度、简单性和工作效率方面具有许多优势，例如，一次为许多用户更改设置时。 请在以下主题中了解这些优点：

  - [Windows PowerShell 和 Skype for Business Online 简介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [使用 Windows PowerShell 管理 Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

    [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。 此模块仅在 64 位计算机上受支持，可从 Microsoft 下载中心下载并安装 Teams [PowerShell 模块](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md)。

## <a name="related-topics"></a>相关主题

[管理用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user.md)
