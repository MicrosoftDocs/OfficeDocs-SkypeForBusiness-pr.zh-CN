---
title: 管理我的组织的音频会议设置
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. '
ms.openlocfilehash: b2759e4ee1f8e8cac2f753eb5afecbf13642abb0
ms.sourcegitcommit: 2c084358844f02fbf7953f2ea49ed6d710cbf06f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2018
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a>管理我的组织的音频会议设置

可能是您更轻松地查看所有业务和在一个位置的 Microsoft 团队 Skype 的音频会议设置。 
  
## <a name="assign-an-audio-conferencing-license"></a>分配音频会议许可

> [!NOTE]
> 无法分配使用**的业务管理中心 Skype**的许可证。 您必须使用 Office 365 管理中心。 请参阅[业务和 Microsoft 团队许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。 
  
 **分配用户许可证**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 在**Office 365 管理中心**的左侧导航窗格中，转到**用户** > **活动用户**，然后从可用的用户列表中选择用户。
    
    > [!NOTE]
    > [!注释] 如果要同时向多达 20 个用户分配许可证，则可以使用" **选择视图**"下拉列表，然后选择其中一个选项或创建你自己的视图。 然后单击" **编辑**"，单击 **下一步**两次，然后选择许可证并单击" **提交**"。 你也可以使用 Windows Powershell 向多个用户分配许可证。 有关说明和示例 PowerShell 脚本，请参阅[业务和 Microsoft 团队许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。 
  
3. 在"操作"窗格中的" **产品许可证**"下，单击" **编辑**"。 
    
4. 在**产品许可证**页上，打开**要进行音频会议**，然后单击**保存**。 有关许可的详细信息，请参阅[业务和 Microsoft 团队授权加载项的 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。
    
> [!NOTE]
> 分配许可证后，Microsoft 可能不作为最初在列表中的音频会议提供商。 如果发生这种情况，请退出 Office 365 管理中心或按 Ctrl+F5 刷新浏览器窗口。 
  
## <a name="assign-a-conference-id-for-a-user"></a>为用户分配会议 ID

设置为使用 Microsoft 作为音频会议提供商的音频会议时，会议 ID 自动分配给用户。 安排会议时，将会议邀请中发送的会议 ID。 将获取每个用户安排的会议分配一个唯一的会议 id。
  
不能使用 Skype for Business 管理中心来向用户分配会议 ID，但你可以使用 Windows PowerShell cmdlet 来执行此操作。
  
若要为用户设置会议 ID，请运行以下命令：
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> 会议 ID 必须包含 7 位，并且不能在 Skype 业务管理中心或使用 Windows PowerShell 中进行更改。 
  
请参阅 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) 以了解有关 cmdlet 的更多信息。
  
> [!IMPORTANT]
>  [!重要信息]  创建新会议 ID 后，呼叫者不能再使用旧会议 ID。 应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。 用户可以使用业务会议迁移工具的 Skype 更新其现有会议。 若要查看如何下载、 安装和运行 Skype 业务会议更新工具，请参阅： [Skype 商业和 Lync 会议更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、[业务 online，会议迁移工具 （64 位） 的 Skype](http://go.microsoft.com/fwlink/?LinkID=626047)和[Skype 业务 online 会议迁移工具 （32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。
  
请参阅[请参阅、 更改和重置会议 ID 分配给用户](see-change-and-reset-a-conference-id-assigned-to-a-user.md)。
    
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>启用或禁用发送到音频会议用户的电子邮件

![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航窗格中，转到**会议** > **会议桥**。 

2. 在**会议桥**页的顶部，单击**网桥的设置**。 

3. 在**桥设置**窗格中，启用或禁用**自动发送电子邮件发送给用户，如果其电话拨入式设置更改**。

4. 单击" **保存**"。

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到**Office 365 管理中心** > **for Business 的 Skype** ，在左侧导航窗格中，单击**音频会议**。
    
3. 在**Microsoft 网桥的设置**页上，选中或清除**自动发送电子邮件发送给用户，如果其音频会议设置更改**。
    
4. 单击" **保存**"。
    
    您还可以发送电子邮件向用户使用音频会议设置转到用户的音频会议属性，单击**发送会议信息通过电子邮件**。 会议邀请，但不是 PIN 包含会议 ID 和默认音频会议电话号码。
    
    请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。
    
 **使用 Windows PowerShell**
  
- 你还可以使用 Windows PowerShell 并运行以下命令： 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    [设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285)可用于管理您的组织，包括电子邮件的其他设置。
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>更改发件人发送给用户的电子邮件中的联系人信息

您可以对自动发送给用户，包括的实际的电子邮件地址和发件人的联系人信息的显示名称的电子邮件进行更改。 默认情况下，电子邮件发件人是 Office 365 中，但您可以更改电子邮件地址和显示名称使用 Windows PowerShell 和[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet。 若要更改向用户发送电子邮件的电子邮件地址，您必须：
  
- _SendEmailFromAddress_参数中输入的电子邮件地址。
    
- 在  _SendEmailFromDisplayName_ 参数中输入电子邮件的显示名称。
    
- _SendEmailOverride_参数设置为_True_。
    
你可以运行如下命令，更改发送给用户的电子邮件，例如电子邮件的发件人电子邮件地址，或者电子邮件的显示名称：
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

如果要更改电子邮件地址信息，你需要确保你的组织的入站电子邮件策略允许来自自定义电子邮件地址的电子邮件。
  
[设置 CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet 可用于管理您的组织，包括电子邮件的其他设置。
  
请参阅[自动发送给其音频会议设置更改时的用户的电子邮件](emails-sent-to-users-when-their-settings-change.md)。
  
## <a name="reset-the-meeting-conference-id"></a>重置会议 ID

![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。

2. 在页面的顶部，单击**编辑**。

3. 在**音频会议**，下单击**重置会议 ID**。  

4. 在**重置的会议 ID？**窗口中，单击**重置**。 A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**  

1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议**，并在**会议 ID**下的操作窗格中，单击**重置**。
    
4. 在**重置的会议 ID？**窗口中，单击**是**。 A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.
    
    > [!IMPORTANT]
    >  [!重要信息] 创建新会议 ID 后，呼叫者不能再使用旧会议 ID。 应通知用户重新安排其现有会议邀请，从而确保将新会议 ID 添加到邀请中。 用户可以使用业务会议迁移工具的 Skype 更新其现有会议。 若要查看如何下载、 安装和运行 Skype 业务会议更新工具，请参阅： [Skype 商业和 Lync 会议更新工具](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)、[业务 online，会议迁移工具 （64 位） 的 Skype](http://go.microsoft.com/fwlink/?LinkID=626047)和[Skype 业务 online 会议迁移工具 （32 位）](https://www.microsoft.com/en-us/download/details.aspx?id=54079)。
  
请参阅[重置用户的会议 ID](reset-a-conference-id-for-a-user.md)。
  
## <a name="reset-a-conference-organizers-pin"></a>重置会议组织者的 PIN

将获取每个用户安排的会议分配一个唯一的会议 id。 虽然会议 ID 将自动创建并分配给用户，有时可能时用户不是要使用此和您想要将其设置为一个特定号码，或您的用户不记得丢失其会议 id。 您可用于业务管理中心的 Skype 和 Windows PowerShell 查看、 更改和重置用户的会议 id。

![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。

2. 在页面的顶部，单击**编辑**。

3. 在**音频会议**，下单击**重置 PIN**，，然后单击**重置**。 
  
![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype** 

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到**Office 365 管理中心** > **for Business 的 Skype** ，在左侧导航窗格中，单击**音频会议**。
    
3. 单击**用户**，然后选择您要重置 PIN 的用户。
    
4. 在操作窗格中，在**PIN**下单击**重置**。
    
当他们正在启用音频会议或 PIN 重置时，用户将收到电子邮件与他们的 PIN。 但如果您已禁用自动发送电子邮件，将不会发送的 PIN 重置电子邮件和必须手动发送给用户的 PIN。 PIN 将仅在重置后显示一次。 正在重置之后显示后，不会再显示 PIN 用户属性;而是 *** 将显示。 
  
请参阅[重置 PIN 的音频会议](reset-the-audio-conferencing-pin.md)。
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>向用户发送电子邮件与音频会议信息

![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航窗格中，单击**用户**，然后选择从可用的用户列表的用户。

2. 在页面的顶部，单击**编辑**。

3. 在**音频会议**，单击**发送电子邮件中的会议信息**。 

    > [!NOTE]
    > 当执行此操作时，音频会议 PIN 不发送给用户。 

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**  

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到**Office 365 管理中心** > **for Business 的 Skype** ，在左侧导航窗格中，单击**音频会议**。
    
3. 单击**用户**，然后选择您要重置 PIN 的用户。
    
4. 在操作窗格中，单击" **通过电子邮件发送会议信息**"。
    
    > [!NOTE]
    > 当执行此操作时，音频会议 PIN 不发送给用户。 
  
请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a>为会议组织者设置的默认音频会议电话号码

 **若要为会议组织者，您将为用户启用音频会议时设置默认音频会议电话号码**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在左侧导航窗格中，转到**音频会议** > **用户**。 选择您想要启用音频会议的用户。
    
4. 在操作窗格中，在用户属性中，单击**编辑**。
    
5. 在**属性**页上，在**提供程序名称**下使用下拉列表选择音频会议提供商。
    
  - 如果选择 Microsoft 作为音频会议提供商，您可以从列表中选择默认音频会议的电话号码。  
    
  - 如果您选择第三方 ACP 作为音频会议提供商，您将需要手动输入收费电话和如果需要，免费电话号码。 这些电话号码将作为默认电话号码。
    
    用户的默认音频会议电话号码是他们安排会议时，会议邀请显示的号码。
    
6. 单击" **保存**"。 
    
请参阅[设置的电话号码包含在邀请](set-the-phone-numbers-included-on-invites.md)。
  
 **若要为启用音频会议用户后，会议组织者设置的默认音频会议电话号码**
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **用户**，选择所需的用户，并在操作页上，单击**编辑**。
    
4. 在**属性**页上，在**提供程序名称**下使用下拉列表选择音频会议提供商。
    
  - 如果用户使用 Microsoft 为音频会议提供商，您可以从列表中选择默认音频会议的电话号码。  
    
  - 如果用户使用第三方 ACP 作为音频会议提供商，您将需要手动输入收费电话和如果需要，免费电话号码。
    
    用户的默认音频会议电话号码是他们安排会议时，会议邀请显示的号码。
    
5. 单击" **保存**"。 
    
请参阅[设置的电话号码包含在邀请](set-the-phone-numbers-included-on-invites.md)。
  
## <a name="choosing-audio-conferencing-bridge-settings"></a>选择音频会议网桥的设置

**呼叫者加入会议时设置的会议体验**

 ![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航窗格中，转到**会议** > **会议桥**。 

2. 在**会议桥**页的顶部，单击**网桥的设置**。 

3. 在**桥设置**窗格中，启用或禁用**会议项和退出通知**。

    默认情况下启用。 如果您禁用此选项，某人进入或离开会议时，默认情况下已加入会议的用户不会将收到通知。

4. 在**项/退出通知类型**下选择**音**或**姓名或电话号码**。 

    如果您选择**姓名或电话号码**，可以选择启用或禁用**Ask 呼叫者在记录其姓名之前加入会议**。 

1. 单击" **保存**"。

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype** 
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **Microsoft 网桥的设置**。
    
4. 在**会议加入体验**，下选择下列操作：
    
  - " **启用会议进入和退出通知**"此选项默认情况下选中。 如果清除此复选框，某人进入或离开会议时，默认情况下已加入会议的用户不会收到通知。
    
    用户加入会议的业务或 Microsoft 团队应用程序使用 Skype 和它们修改的 Skype 会议或 Microsoft 团队**选项**菜单中的**公告时人员进入或离开**设置时，可以逐个会议逐个设置此会议。
    
  - " **要求呼叫者在加入会议之前录制其名称**"此选项默认情况下选中。 如果清除此复选框，呼叫者不需要记录其姓名，他们加入会议之前。
    
5. 完成更改后，单击" **保存**"。
    
请参阅[更改现有音频会议桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。
  
 **设置会议的 PIN 长度**

 ![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航窗格中，转到**会议** > **会议桥**。 

2. 在**会议桥**页的顶部，单击**网桥的设置**。 

3. 在**桥设置**窗格中，输入您希望在**PIN 长度**列表中，PIN 的位数，然后单击**保存**。

    PIN 必须在 4 到 12 位之间。 默认值为 5。

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype** 
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **Microsoft 网桥的设置**。
    
4. 在**安全**下输入您希望在**PIN 长度**列表中，PIN 的位数，然后单击**保存**。
    
    PIN 必须在 4 到 12 位之间。 默认值为 5。
    
请参阅[更改现有音频会议桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)。
  
 **启用或禁用从发送给音频的用户的电子邮件**

 ![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航窗格中，转到**会议** > **会议桥**。 

2. 在**会议桥**页的顶部，单击**网桥的设置**。 

3. 在**桥设置**窗格中，启用或禁用**自动发送电子邮件发送给用户，如果其音频会议设置更改**。

4. 单击" **保存**"。 
 
    您还可以发送电子邮件向用户音频会议设置后，转到用户的音频会议属性，单击**发送电子邮件中的会议信息**。
    
    如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype** 
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. 转到**Office 365 管理中心** > **for Business 的 Skype** ，在左侧导航窗格中，单击**音频会议**。
    
3. 在**Microsoft 网桥的设置**页上，选中或清除**自动发送电子邮件发送给用户，如果其音频会议设置更改**。
    
4. 单击" **保存**"。
    
    您还可以发送电子邮件向用户音频会议设置后，转到用户的音频会议属性，单击**发送会议信息通过电子邮件**。
    
    如果执行此操作，则将发送仅包括会议 ID 和会议电话号码的电子邮件，但不包括 PIN。
    
    请参阅[对其音频会议信息的用户发送电子邮件](send-an-email-to-a-user-with-their-dial-in-information.md)。
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>请参阅和上一个音频会议网桥设置主 （默认值） 和辅助 （备用） 语言

 ![团队-徽标-30x30.png](../images/teams-logo-30x30.png) **使用的 Microsoft 团队和 Skype 的业务管理中心**

1. 在左侧导航窗格中，转到**会议** > **会议桥**。 

2. 从列表中选择一个电话号码，单击**编辑**。

3. 选择**默认语言**和**（可选） 的备用语言**下所需的语言。

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype** 

1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议**，然后单击**Microsoft 桥**。
    
4. 从列表中选择一个电话号码，单击操作窗格中中的**设置语言**，然后在**设置语言**页上，单击使用**主要语言**列表，以查看受支持的语言的完整列表。
    
    您还可以设置时选择 Microsoft 作为音频会议提供商支持的主要和辅助语言。 在列表中选择的顺序是相同的顺序在其中将向呼叫者显示语言。
    
请参阅[设置音频会议自动助理语言](set-auto-attendant-languages-for-audio-conferencing.md)。
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png--see-audio-conferencing-dial-in-numbers"></a>![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png)  请参阅音频会议拨入号码

1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议** > **Microsoft 桥**。 此处可以：
    
  - 查看 Office 365 设置要用于音频会议的电话号码。 
    
  - 查看位置和主要和辅助语言，将使用的音频会议自动助理。
    
  - 选择它们启用音频会议时，将向用户提供的默认电话号码。 但是，如果音频会议桥的默认电话号码发生更改，都不会更改现有用户的默认电话号码。
    
您可以转到**音频会议** > **用户**和用户的属性更改默认的数字的用户通过从您的组织中提供的号码的列表中选择新号码的选择。
  
请参阅[音频会议号码的列表，请参阅](see-a-list-of-audio-conferencing-numbers.md)。
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-see-a-list-of-users-that-are-enabled"></a>![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) 查看启用的用户的列表

1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. 在**业务管理中心的 Skype**，在左侧导航窗格中，转到**音频会议**>，然后**用户**。
    
请参阅[请参阅启用了音频会议的用户列表](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md)。
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？

有几种您可以使用 Windows PowerShell 的组织级别管理的设置。 这便于将设置应用于所有用户。 
    
要获得有关每个 cmdlet 的更多帮助，请参阅 [Skype for Business Online cmdlet](https://go.microsoft.com/fwlink/?LinkId=627324)。

下面是组织级别设置： 
> 
- **设置条目/退出通知**默认值为 _$true_。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- **设置名称录制**默认值为 _$true_。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **设置 PIN 长度**默认值为 5。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **设置仅电话拨入式会议从电话**默认 _$false_。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **设置是否向用户发送电子邮件**默认值为 _$true_。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **设置是否发送电子邮件从不同的帐户**默认值为 _$false_。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **设置在发送给用户的电子邮件发件人地址**默认值为 _$null_。 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **设置电子邮件发送给用户的显示名称**默认值为 _$null_。
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a>想要了解有关 Windows PowerShell 的详细信息   
- Windows PowerShell Office 365 的功能是管理用户以及允许或不允许用户执行某些操作。使用 Windows PowerShell，可以通过单点管理来管理 ，这样做可在有多个任务需要执行时简化日常工作。若要开始使用 Windows PowerShell，请参阅下列主题：
    
  - [为什么您需要使用 Office 365 PowerShell 中](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 具有很多好处中快速、 简便起见和生产力通过只使用 Office 365 管理中心中的，如时要进行设置更改多个用户一次。 请在以下主题中了解这些优点： 
    
  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    [!注释] 使用适用于 Skype for Business Online 的 Windows PowerShell 模块，你可以创建连接到 Skype for Business Online 的远程 Windows PowerShell 会话。此模块仅在 64 位计算机上受支持，可以从 Microsoft 下载中心的[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)下载。
    
## <a name="related-topics"></a>相关主题

[管理用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user.md)


