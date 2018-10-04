---
title: 更改音频会议网桥的电话号码
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: When you buy Audio Conferencing licenses, Microsoft is hosting your audio conferencing bridge for your organization. The audio conferencing bridge gives out dial-in phone numbers from different locations so meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.
ms.openlocfilehash: 26a6e8dcb467ceea990b974d1687e0a5998eeb4b
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372239"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>更改音频会议网桥的电话号码

When you buy **Audio Conferencing** licenses, Microsoft is hosting your *audio conferencing bridge*  for your organization. The audio conferencing bridge gives out dial-in phone numbers from different locations so meeting organizers and participants can use them to join Skype for Business or Microsoft Teams meetings using a phone.
  
除了已分配给您的会议桥的电话号码，您可以[获取额外的服务号码](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)（收费和免费电话号码用于音频会议） 从其他位置，然后分配给会议桥接以便您可以展开您的用户的范围。
  
> [!NOTE]
> To be able to assign/unassign a phone number for a conferencing bridge, the phone number must be a '*service*' number. You can see the type of number it is by navigating to **Voice** > **Phone numbers** and looking in the **Number Type** column. Office 365 Communications Credits must be set up first in order for users to dial into the bridge on a toll free number.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>将新的服务电话号码分配给会议网桥的操作步骤

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>步骤 1-将新的电话号码分配给音频的会议桥

1. 使用你的工作帐户登录 Office 365。

2. 转到**Office 365 管理中心** > **管理中心** > **团队和 Skype** > **旧门户** > **语音** > **电话号码**。

3. 从列表中，并在操作窗格中选择的电话号码，请单击**分配**。

4. 在" **分配**"页面上，单击" **保存**"。

    Only a service toll number can be set as the default number for your conferencing bridge; **service toll-free numbers can't be set as the default number of your conferencing bridge**. If you are assigning a service toll number and you would like to set it as the new default number for your audio conferencing bridge, select **Use this number as the default**.

    > [!NOTE]
    > [!注释] 分配了新电话号码后，即使该号码已经是新默认号码，现有用户的默认号码也不会更改。 设置默认收费和免费电话号码添加到组织者的会议邀请，请参阅[Microsoft](set-the-phone-numbers-included-on-invites-in-teams.md)团队的说明或[业务 online Skype](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)的说明。 
  


### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>第 2 步 - 更改用户的会议邀请中包含的默认电话号码（可选）

用户的默认电话是他们安排会议时在会议邀请中包含的号码。 有关详细信息，请参阅[设置的电话号码包含在邀请中的 Microsoft 团队](set-the-phone-numbers-included-on-invites-in-teams.md)或[设置的电话号码包含在邀请中的业务联机 Skype](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。
  
1. 使用你的工作或学校帐户登录 Office 365。

2. 转到**Office 365 管理中心** > **管理中心** > **团队和 Skype** > **旧门户** > **音频会议** > **用户**和选择列表中的用户。

3. 在"操作"窗格中单击" **编辑**"。

4. 在**默认收费电话号码**或**默认免费电话号码**，请在列表中选择并单击**保存**。

在保存所做的更改后，新的默认电话号码将包含在会议邀请的下次他们安排新的会议的组织者。

### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>第 3 步 - 使用会议迁移服务更新用户的现有会议邀请（可选）

接下来的两个步骤，您需要启动 Windows PowerShell。
  
Using the Meeting Migration Service, you can optionally update meeting invites that were already sent to users in your organization before their default phone numbers were changed. For additional information, see [Setting up the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
  
- Run the Meeting Migration Service (MMS) for the users who had their default phone numbers changed in Step 2. To do this, run the following command:

```
    Start-CsExMeetingMigration user@contoso.com
```

- 你还可以查看会议迁移状态。一旦没有处于 *待处理*  或 *进行中*  状态的操作时，将会重新安排会议。

```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>取消为会议网桥分配的服务电话号码的操作步骤


When you unassign a phone number from a conferencing bridge, users won't be able to join any meetings using that phone number anymore. Because the phone number is changing, it's important to update all users that could have a phone number as their default number (if any) and to update their existing meeting invites before the phone number is unassigned from the audio conferencing bridge.

如果删除电话号码时没有通知用户及更新其会议，那么他们的现有会议邀请可能包含无法再用于加入其会议的电话号码。

For the first three steps, you will need to start Windows PowerShell. To see how to do this, click [Want to know how to manage with Windows PowerShell?](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-that-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>第 1 步 - 通知其默认号码之一是要取消分配的电话号码的用户

为其默认号码是要取消分配的号码的用户替换默认的收费或免费号码，并开始重新安排其会议的过程。要执行此操作，请运行以下命令：

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >You can also change the default toll or toll-free number of users in the Skype for Business admin center. However, this won't automatically reschedule their meetings. 
 
 有关其他信息，请参阅[设置的电话号码包含在邀请中的 Microsoft 团队](set-the-phone-numbers-included-on-invites-in-teams.md)或[设置的电话号码包含在邀请中的业务联机 Skype](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。

  > [!NOTE]
  > [!注释] 根据组织的规模，这可能需要一段时间才能完成。

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>第 2 步 - 使用 Windows PowerShell 查看会议迁移状态

没有处于*挂起*或*正在进行中*状态的操作后，将重新安排的所有会议。

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

有关会议迁移服务的详细信息，请参阅[设置会议迁移服务 (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>步骤 3-取消旧的电话号码分配给音频的会议桥

1. 使用你的工作或学校帐户登录 Office 365。

2. 转到**Office 365 管理中心** > **管理中心** > **团队和 Skype** > **旧门户** > **语音** > **电话号码**。

3. 从列表中，并在操作窗格中选择的电话号码，请单击**取消分配**。

4. 在确认窗口中，单击**是**。

   > [!IMPORTANT]
   > 从现有音频会议桥未分配电话号码后，将不再可供用户加入新的或现有会议的电话号码。

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>确认 Windows PowerShell 是否准备就绪

 这些步骤检查您运行 Windows PowerShell 版本 3.0 或更高。

1. 键入 **开始菜单** > **Windows PowerShell** 。

2. 在 _ Windows PowerShell_ 窗口中键入 **Get-Host** ，以检查版本。

3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。

4. You also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module is supported only on 64-bit computers and can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.

如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)。

### <a name="to-start-windows-powershell"></a>启动 Windows PowerShell

 **启动 Windows PowerShell 会话**

1. 从 **开始菜单** > **Windows PowerShell** 。

2. 在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：

    > [!NOTE]
    > [!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。

>
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

如果您希望有关启动 Windows PowerShell 的详细信息，请参阅[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)或[Connecting to Skype 业务 online 使用 Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)。

### <a name="save-time-and-automate"></a>节省时间并自动给出

要通过自动执行此过程来节省时间，可以使用[集 CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688)或**集 CsOnlineDialInConferencingUserDefaultNumber** cmdlet。

- 使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet 可更改特定用户的默认收费电话号码或免费电话号码。

  - 若要更改用户的默认免费电话号码，请运行：

  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- 使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet 可基于用户的原始默认电话号码或位置来更改其默认收费电话号码或免费电话号码。

    > [!NOTE]
    > 若要查找 BridgeID，请使用**Get-CsOnlineDialInConferencingBridge**。

  - 若要为没有默认免费电话号码的所有用户将默认免费电话号码设置为 8005551234，请运行：

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 若要为默认免费电话号码已设置为 8005551234 的所有用户将默认免费电话号码更改为 8005551239，并自动重新安排其会议，请运行：

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - 若要为位于美国的所有用户将默认免费电话号码设置为 8005551234，并自动重新安排其会议，请运行：

  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > [!注释] 上面使用的位置信息需要与 Office 365 管理中心中设置的用户联系信息匹配。

## <a name="about-windows-powershell"></a>有关 Windows PowerShell

With Windows PowerShell you can manage users and what they are or are not allowed to do. Windows PowerShell  can help you manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, especially when you've got multiple tasks to do. To get started with Windows PowerShell, see these topics:

  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)

例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：

  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相关主题
[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)
