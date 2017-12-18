---
title: "管理我的组织的音频会议设置"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
description: "See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. "
---

# 管理我的组织的音频会议设置

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
它可能更容易以查看所有 Skype for Business 和 Microsoft 团队在一个位置的音频会议设置。
  
## 分配音频会议许可证

> [!NOTE]
> 不能分配许可证使用 **Skype for Business 管理中心**。您必须使用 Office 365 管理中心。请参阅[分配 Skype for Business 和 Microsoft 团队合作的用户许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。 
  
 **若要为用户分配许可证**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 在 **Office 365 管理中心**的左侧导航中，转到 **用户**> **活动用户**，然后从可用的用户列表中选择或多个用户。
    
    > [!NOTE]
    > 如果您要同时向达 20 个用户分配许可证，您可以使用 **选择视图**下拉列表，然后选择其中一个选项或创建您自己的视图。然后单击 **编辑** **下一步**两次选择的许可证，然后单击 **提交**。 您可以使用 Windows Powershell 到多个用户分配许可证。有关说明和示例 PowerShell 脚本，请参阅[分配 Skype for Business 和 Microsoft 团队合作的用户许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。 
  
3. 在"操作"窗格中的" **产品许可证**"下，单击" **编辑**"。
    
4. 在 **产品许可证**页面上启用 **音频会议**，然后单击 **保存**。 有关许可的详细信息，请参阅[Skype for Business 和 Microsoft 团队许可加载项](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
    
> [!NOTE]
> 分配许可证后，Microsoft 可能无法显示最初在列表中作为音频会议提供商。如果发生这种情况，注销 Office 365 管理中心中或者按 CTRL + F5 刷新浏览器窗口。 
  
## 为用户分配会议 ID

设置为使用 Microsoft 作为音频会议提供商的音频会议时，会议 ID 自动分配给用户。分配的会议 ID 可以是静态或动态并发送会议邀请中的计划会议时。
  
当您组织中的人员不想要记住的一个随机数; 使用静态 Id他们可以选择特定编号，或选择其中一个容易记住。当使用动态会议 Id 时，每个会议用户计划将获得分配一个唯一的会议 id。如果您要分配动态而不是静态会议 Id，[在您的组织中使用音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。
  
不能使用 Skype for Business 管理中心来向用户分配会议 ID，但你可以使用 Windows PowerShell cmdlet 来执行此操作。
  
若要为用户设置会议 ID，请运行以下命令：
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> 会议 ID 必须包含 7 位，并且您无法在 Skype for Business 管理中心，或通过使用 Windows PowerShell 中更改它。 
  
请参阅[设置 CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 )若要了解有关 cmdlet 的详细信息。
  
> [!IMPORTANT]
>  创建新的会议 ID 后，呼叫者不使用旧的会议 ID。您应通知重新安排现有会议邀请，以确保新会议 ID 添加到邀请的用户。用户可以使用Skype for Business会议迁移工具更新其现有的会议。若要了解如何下载、 安装和运行 Skype 业务会议更新工具，请参阅：> [Skype for Business 和 Lync 的会议更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)> [Skype for Business Online、会议迁移工具（64 位）](http://go.microsoft.com/fwlink/?LinkID=626047)> [Skype for Business Online、 会议迁移工具 （32 位）](https://go.microsoft.com/fwlink/?LinkID=626046)
  
请参阅[请参阅、 更改和重置会议 ID 分配给用户](see-change-and-reset-a-conference-id-assigned-to-a-user.md)。
  
## 将音频会议提供商从 Microsoft 更改为第三方提供商

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到" **Office 365 管理中心**">" **Skype for Business**"。
    
3. 在 **Skype for Business 管理中心**，在左侧导航中，转到 **音频会议**> **用户**，然后选择您想要更改的音频会议提供商的用户。
    
4. 在"操作"窗格中，单击" **编辑**"。
    
5. 在 **属性**页上，在 **提供商名称**下选择用户的音频会议提供商。
    
    > [!NOTE]
    > 您可以仅选择 Microsoft 作为音频会议提供商或 **无**如果选择了多个用户。 
  
6. 单击" **保存**"。
    
请参阅[更改用户的电话拨入式会议提供商](https://support.office.com/article/9b74f053-4d23-485f-9232-3d30370a8c6e)。
  
## 启用或禁用电子邮件发送给音频会议的用户

您可以使用 Skype for Business 管理中心或 Windows PowerShell 以启用或禁用发送给用户的电子邮件。
  
 **使用 for Business 管理中心中的 Skype**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到 **Office 365 管理中心**> **Skype for Business** ，然后在左侧导航中，单击 **音频会议**。
    
3. 在 **Microsoft 网桥设置**页面中，选中或清除 **自动将发送给用户的电子邮件，如果更改了其音频会议设置**。
    
4. 单击" **保存**"。
    
    您也可以发送电子邮件向用户与音频会议设置通过转到用户的音频会议属性并单击 **发送会议信息通过电子邮件**。 在会议邀请，但不是 PIN，则包含会议 ID 和默认音频会议电话号码。
    
    请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-audio-conferencing-information.md)。
    
 **使用 Windows PowerShell**
  
- 你还可以使用 Windows PowerShell 并运行以下命令：
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    [设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)可用于管理您的组织，包括电子邮件的其他设置。
    
## 更改发送给用户的电子邮件中的发件人的联系人信息

自动发送给您的用户，包括实际的电子邮件地址和发件人的联系人信息的显示名称的电子邮件，您可以进行更改。默认情况下，发件人的电子邮件是 Office 365，但您可以更改电子邮件地址，并显示名称使用 Windows PowerShell 和[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet。要向用户发送电子邮件的电子邮件地址进行更改，您必须：
  
- 在  _SendEmailFromAddress_ 参数中输入电子邮件地址。
    
- 在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。
    
- 将  _SendEmailOverride_ 参数设置为 _True_。
    
你可以运行如下命令，更改发送给用户的电子邮件，例如电子邮件的发件人电子邮件地址，或者电子邮件的显示名称：
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

如果要更改电子邮件地址信息，你需要确保你的组织的入站电子邮件策略允许来自自定义电子邮件地址的电子邮件。
  
[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 可用于管理您的组织，包括电子邮件的其他设置。
  
请参阅[其音频会议设置更改时自动发送给用户的电子邮件](emails-that-are-automatically-sent-to-users-when-their-audio-conferencing-settin.md)。
  
## 重置会议 ID

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到" **Office 365 管理中心**">" **Skype for Business**"。
    
3. 在 **Skype for Business 管理中心**，在左侧导航中，转到 **音频会议**，然后在 **会议 ID**下的操作窗格中，单击 **重置**。
    
4. 在 **重置会议 ID？**窗口中，单击 **是**。将自动创建的会议 ID 和电子邮件发送给用户的新会议 id 是否已启用向用户发送电子邮件。默认情况下启用它。
    
    > [!IMPORTANT]
    >  创建新的会议 ID 后，呼叫者不使用旧的会议 ID。您应通知重新安排现有会议邀请，以确保新会议 ID 添加到邀请的用户。用户可以使用Skype for Business会议迁移工具更新其现有的会议。若要了解如何下载、 安装和运行 Skype 业务会议更新工具，请参阅：> [Skype for Business 和 Lync 的会议更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)> [Skype for Business Online、会议迁移工具（64 位）](http://go.microsoft.com/fwlink/?LinkID=626047)> [Skype for Business Online、 会议迁移工具 （32 位）](https://go.microsoft.com/fwlink/?LinkID=626046)
  
请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。
  
## 重置会议组织者的 PIN

当您组织中的人员不想要记住的一个随机数; 使用静态 Id他们可以选择特定数字或使用一个容易记住。当使用动态会议 Id 时，每个会议用户计划将获得分配一个唯一的会议 id。如果您要分配动态而不是静态会议 Id，[在您的组织中使用音频会议动态 Id](using-audio-conferencing-dynamic-ids-in-your-organization.md)。
  
虽然将自动创建并分配给用户的静态会议 ID，有时可能需要时用户不希望使用此和您想要将其设置为特定数字，或您的用户不记得或丢失了其会议 id。您可以使用 Skype for Business 管理中心和 Windows PowerShell 来查看、 更改和重置其会议 id。
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到 **Office 365 管理中心**> **Skype for Business** ，然后在左侧导航中，单击 **音频会议**。
    
3. 单击 **用户**，然后选择您想要重置 PIN 的用户。
    
4. 在操作窗格中，在 **固定**下单击 **重置**。
    
当他们正在启用音频会议或重置 PIN 时，用户将收到一封电子邮件与他们的 PIN。但如果您已禁用自动发送电子邮件、 PIN 重置电子邮件不会被发送，必须手动发送给用户的 PIN。 已重置后，将只会一次显示 PIN。PIN 重置后显示后，将不会再会显示在用户属性;相反，*** 将会显示。
  
请参阅[重置用户的音频会议 PIN](reset-the-audio-conferencing-pin-for-a-user.md)。
  
## 向用户发送一封电子邮件与音频会议信息

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到 **Office 365 管理中心**> **Skype for Business** ，然后在左侧导航中，单击 **音频会议**。
    
3. 单击 **用户**，然后选择您想要重置 PIN 的用户。
    
4. 在操作窗格中，单击" **通过电子邮件发送会议信息**"。
    
    > [!NOTE]
    > 执行此操作时，音频会议 PIN 不发送给用户。 
  
请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-audio-conferencing-information.md)。
  
## 为会议组织者设置的默认音频会议电话号码

 **若要为会议组织者，您将为用户启用音频会议时设置默认音频会议电话号码**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到" **Office 365 管理中心**">" **Skype for Business**"。
    
3. 在左侧导航中，转到 **音频会议**> **用户**。选择您想要启用的音频会议的用户。
    
4. 在操作窗格中，在用户的属性中，单击 **编辑**。
    
5. 在 **属性**页上，在 **提供程序的名称**，使用下拉列表选择音频会议提供商。
    
  - 如果选择 Microsoft 作为音频会议提供商，您可以从列表中选择的默认音频会议电话号码。
    
  - 如果选择第三方 ACP 作为音频会议提供商，您将需要手动输入付费号码，如果需要，免费电话号码。这些电话号码将默认电话号码。
    
    用户的默认音频会议电话号码是他们安排会议时，在会议邀请显示的数字。
    
6. 单击" **保存**"。
    
请参阅[为会议组织者包含在邀请中设置音频会议电话号码](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md)。
  
 **若要设置为会议组织者之后您启用了用户的音频会议, 的默认音频会议电话号码**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到" **Office 365 管理中心**">" **Skype for Business**"。
    
3. 在 **Skype for Business 管理中心**，在左侧导航中，转到 **音频会议**> **用户**，选择所需的用户，然后在操作页上，单击 **编辑**。
    
4. 在 **属性**页上，在 **提供程序的名称**，使用下拉列表选择音频会议提供商。
    
  - 如果用户使用 Microsoft 作为音频会议提供商，您可以从列表中选择的默认音频会议电话号码。
    
  - 如果用户使用第三方 ACP 作为音频会议提供商，您将需要手动输入付费号码，如果需要，免费电话号码。
    
    用户的默认音频会议电话号码是他们安排会议时，在会议邀请显示的数字。
    
5. 单击" **保存**"。
    
请参阅[为会议组织者包含在邀请中设置音频会议电话号码](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md)。
  
## 设置音频会议网桥的设置

 **当呼叫者加入会议时设置会议体验**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到" **Office 365 管理中心**">" **Skype for Business**"。
    
3. 在 **Skype for Business 管理中心**，在左侧导航中，转到 **音频会议**> **Microsoft 网桥的设置**。
    
4. 在 **会议加入体验**，下，选择下列操作：
    
  - **启用会议进入和退出通知打开**默认情况下选择此选项。如果清除此复选框，则默认情况下已加入会议的用户不会收到当有人进入或离开会议。
    
    用户加入会议使用 Skype for Business 或 Microsoft 团队应用和他们修改的 Skype 会议或 Microsoft 小组 **选项**菜单中的 **当人员进入或离开时发出通知**设置时，可以在逐个会议的基础上设置此会议。
    
  - **要求呼叫者能够录制其姓名之前加入会议**默认情况下选择此选项。如果清除此复选框，不要求呼叫者加入会议之前录制其姓名。
    
5. 完成更改后，单击" **保存**"。
    
请参阅[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。
  
 **设置会议 PIN 长度**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到" **Office 365 管理中心**">" **Skype for Business**"。
    
3. 在 **Skype for Business 管理中心**，在左侧导航中，转到 **音频会议**> **Microsoft 网桥的设置**。
    
4. 在 **安全**，输入所需的 pin **PIN 长度**列表中的位数，然后单击 **保存**。
    
    4 到 12 位之间必须固定。默认为 5。
    
请参阅[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。
  
 **启用或禁用电子邮件发送到音频的用户**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到 **Office 365 管理中心**> **Skype for Business** ，然后在左侧导航中，单击 **音频会议**。
    
3. 在 **Microsoft 网桥设置**页面中，选中或清除 **自动将发送给用户的电子邮件，如果更改了其音频会议设置**。
    
4. 单击" **保存**"。
    
    您也可以发送电子邮件向用户与音频会议设置，通过转到用户的音频会议属性并单击 **发送会议信息通过电子邮件**。
    
    如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。
    
    请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-audio-conferencing-information.md)。
    
## 请参阅和音频会议网桥设置主要和辅助语言

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到" **Office 365 管理中心**">" **Skype for Business**"。
    
3. 在 **Skype for Business 管理中心**，在左侧导航中，转到 **音频会议**，然后单击 **Microsoft 网桥**。
    
4. 从列表中选择的电话号码，请单击在操作窗格中的 **设置语言**，然后在 **设置语言**页面上，单击使用 **主要语言**列表以查看受支持语言的完整列表。
    
    您还可以设置当你选择 Microsoft 作为音频会议提供商支持的主要和辅助语言。您的列表中选择的顺序是在其中将向呼叫者显示语言的顺序相同。
    
请参阅[设置音频会议自动助理语言](set-auto-attendant-languages-for-audio-conferencing.md)。
  
## 请参阅音频会议拨入号码

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到" **Office 365 管理中心**">" **Skype for Business**"。
    
3. 在 **Skype for Business 管理中心**，在左侧导航中，转到 **音频会议**> **Microsoft 网桥**。可在此处：
    
  - 查看 Office 365 设置要用于音频会议的电话号码。
    
  - 查看位置以及主要和辅助语言，将使用的音频会议自动助理。
    
  - 选择音频会议启用它们时，将向用户提供的默认电话号码。但是，如果更改了默认电话号码的音频会议网桥，不会更改现有用户的默认电话号码。
    
您可以转到 **音频会议**> **用户**和用户通过在您的组织中可用的数字的列表中选择新号码的用户的属性更改默认编号的选择。
  
请参阅[请参阅音频会议号码列表](see-a-list-of-audio-conferencing-numbers.md)。
  
## 查看启用的用户的列表

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到" **Office 365 管理中心**">" **Skype for Business**"。
    
3. 在 **Skype for Business 管理中心**，在左侧导航中，转到 **音频会议**>，然后 **用户**。
    
请参阅[请参阅启用了音频会议的用户列表](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)。
  
## 想知道如何使用 Windows PowerShell 进行管理吗？

- 有几个您可以在组织级别使用 Windows PowerShell 管理的设置。这使得可以轻松地将设置应用于您的所有用户。下面是组织级别设置：
    
    若要在每个 cmdlet 获取更多帮助，请参阅[Skype for Business Online cmdlet](https://go.microsoft.com/fwlink/?LinkId=627324)。
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

    默认值为  _$true_。
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

    默认值为  _$true_。
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

    默认值为 5。
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

    默认值为  _$false_。
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    默认值为  _$true_。
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

    默认值为  _$false_。
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

    默认值为  _$null_。
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

    默认值为  _$null_。
    
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么您需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 具有许多优于速度、 简单起见和工作效率中的仅使用 Office 365 管理中心中，例如，当您正在进行设置更改为许多用户，一次。 了解有关以下主题中的以下优势：
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  
## 另请参阅
<a name="MT_Footer"> </a>

#### 其他资源

[设置音频会议 for Skype Business 和 Microsoft 团队](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)

