---
title: "管理我的组织的音频会议设置"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. '
ms.openlocfilehash: 6fb10654c5845fb5524264219e642cd0a250e860
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a>管理我的组织的音频会议设置

它可能是便于您查看所有业务和 Microsoft 小组在一个位置对 Skype 的音频会议设置。 
  
## <a name="assign-an-audio-conferencing-license"></a>指定音频会议许可证

> [!NOTE]
> 不能分配许可证使用**Skype 的业务管理中心**。 您必须使用 Office 365 管理中心。 请参阅[指派的 Skype 业务和 Microsoft 小组的许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。 
  
 **若要指定用户的许可证**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 在**Office 365 管理中心**左侧导航，请转到**用户** > **活动用户**，然后从可用用户列表中选择的用户。
    
    > [!NOTE]
    > [!注释] 如果要同时向多达 20 个用户分配许可证，则可以使用" **选择视图**"下拉列表，然后选择其中一个选项或创建你自己的视图。 然后单击" **编辑**"，单击 **下一步**两次，然后选择许可证并单击" **提交**"。 你也可以使用 Windows Powershell 向多个用户分配许可证。 有关说明和示例 PowerShell 脚本，请参阅[分配的 Skype 业务和 Microsoft 小组的许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。 
  
3. 在"操作"窗格中的" **产品许可证**"下，单击" **编辑**"。 
    
4. 在**产品许可证**页上，打开**音频会议**，然后单击**保存**。 有关授权的详细信息，请参阅[附加业务和 Microsoft 小组授权的 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
    
> [!NOTE]
> 指定许可证后，Microsoft 可能不会初始显示在列表中为音频会议提供商。 如果发生这种情况，请退出 Office 365 管理中心或按 Ctrl+F5 刷新浏览器窗口。 
  
## <a name="assign-a-conference-id-for-a-user"></a>为用户分配会议 ID

当设置为作为音频会议提供商使用 Microsoft 的音频会议，会议 ID 自动分配给用户。 指定的会议 ID 可以是静态或动态，以及时安排的会议，在会议邀请中发送。 
  
当您组织中的人不想记得的随机数; 使用静态标识符他们可以选择一定数量或选择一个容易记住。 当使用动态会议 Id 时，每个会议用户计划将获得分配唯一的会议 id。 如果您想要分配动态而非静态的会议 Id，请参阅[使用音频会议动态 Id，您的组织中](using-audio-conferencing-dynamic-ids-in-your-organization.md)。
  
不能使用 Skype for Business 管理中心来向用户分配会议 ID，但你可以使用 Windows PowerShell cmdlet 来执行此操作。
  
若要为用户设置会议 ID，请运行以下命令：
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> 会议 ID 必须包含 7 位数字，并不能在 Skype 业务管理中心或使用 Windows PowerShell 中进行更改。 
  
请参阅 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) 以了解有关 cmdlet 的更多信息。
  
> [!IMPORTANT]
>  [!重要信息]  创建新会议 ID 后，呼叫者不能再使用旧会议 ID。 应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。 用户可以使用 Skype 业务会议迁移工具来更新其现有的会议。 若要了解如何下载、 安装和运行 Skype 业务会议更新工具，请参阅：[为业务和 Lync Skype 会议更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、 [Skype 业务在线，会议迁移工具 （64 位）](http://go.microsoft.com/fwlink/?LinkID=626047)和[Skype 的在线业务会议迁移工具 （32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。
  
请参阅[请参阅、 更改和重置会议 ID 分配给用户](see-change-and-reset-a-conference-id-assigned-to-a-user.md)。
  
## <a name="change-the-audio-conferencing-provider-from-microsoft-to-a-third-party-provider"></a>更改音频会议提供商从 Microsoft 给第三方提供商

1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **用户**，然后选择您想要更改的音频会议提供商的用户。
    
4. 在"操作"窗格中，单击" **编辑**"。 
    
5. 在**属性**页上，在**提供程序的名称**，选择音频会议提供商的用户。
    
    > [!NOTE]
    > 如果选择了多个用户，您可以只选择音频会议提供商或**无**作为 Microsoft。
  
6. 单击" **保存**"。 
    
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>启用或禁用音频会议的用户发送电子邮件

可以使用业务管理中心为 Skype 或 Windows PowerShell 启用或禁用电子邮件发送给用户。
  
 **使用 Skype 业务管理中心**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 请转到**Office 365 管理中心** > **Skype 业务**并在左边的导航，请单击**音频会议**。
    
3. 在**Microsoft 桥设置**页上，选中或清除**自动发送电子邮件发送给用户，如果他们的音频会议设置更改**。
    
4. 单击" **保存**"。
    
    您还可以发送电子邮件给用户使用音频会议设置通过转到用户的音频会议属性并单击**将会议信息通过电子邮件发送**。 会议邀请但不是插针上包含会议 ID 和默认音频会议电话号码。
    
    请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。
    
 **使用 Windows PowerShell**
  
- 你还可以使用 Windows PowerShell 并运行以下命令： 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    [一组 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)可用于管理您的组织，包括电子邮件的其他设置。
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>更改发送给用户的电子邮件中的发件人的联系人信息

您可以对电子邮件自动发送给您的用户，包括实际的电子邮件地址和发件人的联系人信息的显示名称进行更改。 默认情况下，电子邮件的发件人是 Office 365，但您可以更改的电子邮件地址和显示名称使用 Windows PowerShell 和[一组 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet。 若要将电子邮件发送到用户的电子邮件地址进行更改，您必须：
  
- 在_SendEmailFromAddress_参数中输入电子邮件地址。
    
- 在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。
    
- 将_SendEmailOverride_参数设置为_True_。
    
你可以运行如下命令，更改发送给用户的电子邮件，例如电子邮件的发件人电子邮件地址，或者电子邮件的显示名称：
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

如果要更改电子邮件地址信息，你需要确保你的组织的入站电子邮件策略允许来自自定义电子邮件地址的电子邮件。
  
可以使用[一组 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 来管理您的组织，包括电子邮件的其他设置。
  
[电子邮件自动发送给用户的音频会议设置更改时](emails-sent-to-users-when-their-settings-change.md)，请参阅。
  
## <a name="reset-the-meeting-conference-id"></a>重置会议 ID

1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**，在左边的导航，转到**音频会议**，然后在**会议 ID**下的操作窗格中，请单击**重置**。
    
4. 在**会议 ID 重置？**窗口中，单击**是**。 A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.
    
    > [!IMPORTANT]
    >  [!重要信息] 创建新会议 ID 后，呼叫者不能再使用旧会议 ID。 应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。 用户可以使用 Skype 业务会议迁移工具来更新其现有的会议。 若要了解如何下载、 安装和运行 Skype 业务会议更新工具，请参阅: [会议更新工具 Skype 业务和 Lync] ((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4) [Skype 的在线业务会议迁移工具 （64 位）](http://go.microsoft.com/fwlink/?LinkID=626047)，和[Skype 的在线业务、 会议迁移工具 （32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。
  
请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。
  
## <a name="reset-a-conference-organizers-pin"></a>重置会议组织者的 PIN

当您组织中的人不想记得的随机数; 使用静态标识符他们可以选择一定数量或使用一个容易记住。 当使用动态会议 Id 时，每个会议用户计划将获得分配唯一的会议 id。 如果您想要分配动态而非静态会议 Id，[使用音频会议动态 Id，您的组织中](using-audio-conferencing-dynamic-ids-in-your-organization.md)。
  
虽然静态会议 ID 将自动创建并指派给用户，可能的时间当用户不想使用此一并想要将其设置为某个数字、 或您的用户忘记或丢失了他们的会议 id。 可以使用业务管理中心为 Skype 和 Windows PowerShell 来查看、 更改和重置其会议 id。
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 请转到**Office 365 管理中心** > **Skype 业务**并在左边的导航，请单击**音频会议**。
    
3. 单击**用户**，然后选择您要重置 pin 码以进行用户。
    
4. 在操作窗格中下**针**，单击**重置**。
    
当他们正在启用音频会议或 PIN 重置时，用户将收到一封电子邮件与他们的 PIN。 但如果禁用了自动发送电子邮件、 PIN 重置电子邮件就不会发送，您将不得不手动发送给用户的 PIN。 PIN 将仅在重置后显示一次。 PIN 重置后显示之后，不不再会显示在用户属性;相反，*** 将显示。 
  
请参阅[重置用户的音频会议 PIN](reset-the-audio-conferencing-pin-for-a-user.md)。
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>使用音频会议信息的电子邮件发送给用户

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 请转到**Office 365 管理中心** > **Skype 业务**并在左边的导航，请单击**音频会议**。
    
3. 单击**用户**，然后选择您要重置 pin 码以进行用户。
    
4. 在操作窗格中，单击" **通过电子邮件发送会议信息**"。
    
    > [!NOTE]
    > 执行此操作时，音频会议针不是发送给用户。 
  
请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a>会议组织者设置的默认音频会议电话号码

 **对于会议组织者，如果您已经在音频会议启用用户设置的默认音频会议电话号码**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在左侧的导航中，转到**音频会议** > **用户**。 选择您想要启用音频会议的用户。
    
4. 在操作窗格中，在用户的属性中，单击**编辑**。
    
5. 在**属性**页上，在**提供程序的名称**，使用下拉列表选择音频会议提供商。
    
  - 如果选择 Microsoft 作为音频会议提供商，您可以从列表中选择默认的音频会议电话号码。  
    
  - 如果您选择第三方 ACP 作为音频会议提供商，您将需要手动输入的收费，如有必要，免费电话号码。 这些电话号码将作为默认电话号码。
    
    用户的默认音频会议电话号码是他们安排会议时在会议邀请中显示数字。
    
6. 单击" **保存**"。 
    
请参阅[设置数字包括在邀请电话](set-the-phone-numbers-included-on-invites.md)。
  
 **若要设置默认的音频会议电话号码启用用户输入音频会议后，会议组织者**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **用户**，选择的用户所需，并在操作页中，单击**编辑**。
    
4. 在**属性**页上，在**提供程序的名称**，使用下拉列表选择音频会议提供商。
    
  - 如果用户使用 Microsoft 作为音频会议提供商，您可以从列表中选择默认的音频会议电话号码。  
    
  - 如果用户使用第三方 ACP 作为音频会议提供商，您将需要手动输入的收费，如有必要，免费电话号码。
    
    用户的默认音频会议电话号码是他们安排会议时在会议邀请中显示数字。
    
5. 单击" **保存**"。 
    
请参阅[设置数字包括在邀请电话](set-the-phone-numbers-included-on-invites.md)。
  
## <a name="setting-audio-conferencing-bridge-settings"></a>设置音频会议桥

 **当调用方加入会议设置会议经验**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **Microsoft 网桥的设置**。
    
4. 下**会议连接体验**，请选择下列操作：
    
  - " **启用会议进入和退出通知**"此选项默认情况下选中。 如果清除此复选框，当有人进入或离开会议，将不会通知用户，默认情况下已加入会议。
    
    当用户加入会议的业务或 Microsoft 小组应用程序使用 Skype 和它们修改**公布当人进入或离开时**设置的 Skype 会议或 Microsoft 小组**选项**菜单中可以在逐个会议的基础上设置此会议。
    
  - " **要求呼叫者在加入会议之前录制其名称**"此选项默认情况下选中。 如果清除此复选框，将不要求调用方之前他们加入会议记录他们的姓名。
    
5. 完成更改后，单击" **保存**"。
    
请参见[更改音频会议桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。
  
 **设置会议的针长度**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **Microsoft 网桥的设置**。
    
4. 在**安全**下，输入 PIN**针长度**列表中，为所需的位数，然后单击**保存**。
    
    PIN 必须介于 4 到 12 位。 默认值为 5。
    
请参见[更改音频会议桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。
  
 **启用或禁用音频的用户发送电子邮件**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 请转到**Office 365 管理中心** > **Skype 业务**并在左边的导航，请单击**音频会议**。
    
3. 在**Microsoft 桥设置**页上，选中或清除**自动发送电子邮件发送给用户，如果他们的音频会议设置更改**。
    
4. 单击" **保存**"。
    
    您还可以发送电子邮件给用户使用音频会议设置，转到该用户的音频会议属性并单击**将会议信息通过电子邮件发送**。
    
    如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。
    
    请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。
    
## <a name="see-and-set-the-primary-and-secondary-languages-on-an-audio-conferencing-bridge"></a>查看和设置音频会议桥的主要和次要语言

1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议**，然后单击**Microsoft 桥**。
    
4. 从列表中选择一个电话号码，单击**设置语言**中的操作窗格中，然后在**设置语言**页中，单击使用的**主要语言**列表以查看受支持的语言的完整列表。
    
    您还可以设置时选择 Microsoft 作为音频会议提供商支持的主要和辅助语言。 您的列表中选择的顺序是语言将显示为调用方的顺序相同。
    
请参阅[设置音频会议自动助理语言](set-auto-attendant-languages-for-audio-conferencing.md)。
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>请参阅音频会议拨入号码

1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议** > **Microsoft 桥**。 在此处，您可以：
    
  - 查看 Office 365 集用于音频电话会议的电话号码。 
    
  - 查看位置和主要和次要的语言，将使用音频会议自动助理。
    
  - 选择已启用音频会议时为用户分配默认电话号码。 但是，如果更改了默认的音频会议桥的电话号码，不会更改现有用户的默认电话号码。
    
您可以转到**音频会议** > **用户**和用户的属性来更改默认值从数字在您的组织中可用的列表中选择新的号号用户的选择。
  
请参阅[音频会议号码的列表，请参阅](see-a-list-of-audio-conferencing-numbers.md)。
  
## <a name="see-a-list-of-users-that-are-enabled"></a>查看启用的用户的列表

1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**，在左边的导航中，转到**音频会议**>，然后**用户**。
    
请参阅[请参阅启用了音频会议的用户列表](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)。
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

有几种可以在组织级别使用 Windows PowerShell 管理的设置。 这样就轻松地将设置应用于所有用户。 
    
要获得有关每个 cmdlet 的更多帮助，请参阅 [Skype for Business Online cmdlet](https://go.microsoft.com/fwlink/?LinkId=627324)。

以下是组织级设置： 
> 
- **设置入口/出口通知**默认值为_$true_。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- **设置名称记录**默认值为_$true_。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **设置 PIN 长度**默认值为 5。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **设置仅拨入会议从电话**默认值_$false_。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **设置是否将发送给用户的电子邮件**默认值为_$true_。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **设置是否将来自不同帐户的电子邮件发送**默认值为_$false_。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **设置发送给用户的电子邮件中的开始地址**默认值为_$null_。 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **设置电子邮件发送给用户显示名称**默认值为_$null_。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息   
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 许多相比具有的优势在速度、 简易性和生产率仅使用 Office 365 管理中心，例如当您所更改的设置对于许多用户一次。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
    
## <a name="related-topics"></a>相关主题

[管理用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user.md)

[设置音频会议 for Skype Business 和 Microsoft 团队](set-up-audio-conferencing.md)

