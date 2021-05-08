---
title: 更改音频会议网桥上的电话号码
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 了解向会议网桥分配新服务电话号码以扩大用户的覆盖范围所需的步骤。
ms.openlocfilehash: f477c583db36e6dee514a84f32de202361d01c11
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102657"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>更改音频会议网桥中的电话号码

当你购买 **音频会议许可证** 时，Microsoft 将托管你的组织的音频会议网桥。 音频会议网桥提供不同位置的拨入电话号码，以便会议组织者和参与者可以使用它们通过电话加入 Skype for Business 或 Microsoft Teams 会议。
  
除了已分配给会议网桥的电话号码外，您还可以从其他位置获取用于音频会议) 的其他服务号码 [ (](./getting-service-phone-numbers.md) 收费和免费号码，然后将这些号码分配给会议网桥，以便你可以扩大用户的覆盖范围。
  
> [!NOTE]
> 为了能够为会议网桥分配/取消分配电话号码，电话号码必须是"*服务"* 号码。 导航到管理中心中的"语音"或"电话"并查看"号码类型"Microsoft Teams，  >  可看到号码的类型。  Microsoft 365或Office 365，必须先设置通信信用额度，用户才能拨打免费号码拨入网桥。

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>将新的服务电话号码分配给会议网桥的操作步骤

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>步骤 1 - 将新电话号码分配给音频会议网桥

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航窗格中，转到"**语音** 电话  >  **数字"。**

2. 从列表中选择电话号码，然后单击"编辑 **"。**

3. 在"**编辑"** 页面上的 **"分配到"下**，展开下拉列表，然后选择"会议 **网桥** 应用  >  **"。**

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>步骤 2 - 更改会议网桥的默认电话号码 (可选) 

会议网桥的默认电话号码定义当参与者或组织者从会议内拨打出站呼叫时将使用的呼叫者 ID。

只能将服务收费电话号码设置为会议网桥的默认号码; **无法将服务** 免费号码设置为会议网桥的默认号码。 如果要分配服务收费电话号码，并且希望将其设置为音频会议网桥的新默认号码，请执行以下步骤：

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航窗格中，转到"**会议**  >  **会议网桥"。**

2. 突出显示要配置为默认值的服务收费电话号码。

3. 选择“**设置为默认值**”。
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>步骤 3 - 更改用户的会议邀请中包含的默认电话号码 (可选) 

用户的默认电话号码是安排会议时包含在其会议邀请中的号码。 有关详细信息，包括如何为新用户分配默认电话号码，请参阅在 Microsoft Teams 中设置邀请中包含的电话号码[或](set-the-phone-numbers-included-on-invites-in-teams.md)设置 Skype for Business Online 中的邀请[中包含的电话号码](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航窗格中，转到 **"用户"，** 然后单击列表中的所需用户的"显示名称"。

2. 在"**音频会议"旁边**，单击"编辑 **"。**

3. 在 **"收费** 电话号码 **"或"免费** 电话号码"下，从下拉列表中选择号码，然后单击"应用 **"。**

应用更改后，组织者下次安排新会议时，新的默认电话号码将包含在会议邀请中。

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>步骤 4 - 使用会议迁移服务更新用户的现有会议邀请 (可选) 

对于接下来的两个步骤，需要开始Windows PowerShell。
  
如果您更新了部分或所有用户的会议邀请中包含的默认电话号码，您可以选择更新在使用会议迁移服务更改用户的默认电话号码之前已发送给您的组织中的用户的会议邀请。 有关更多信息，请参阅[设置会议迁移服务 (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。
  
- 为在步骤 2 中更改 (用户) MMS 帐户运行会议迁移服务。 要执行此操作，请运行以下命令：

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- 你还可以查看会议迁移状态。一旦没有处于 *待处理*  或 *进行中*  状态的操作时，将会重新安排会议。

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>取消为会议网桥分配的服务电话号码的操作步骤


取消为会议网桥分配的服务电话号码时，用户将不能再使用该电话号码加入任何会议。 由于电话号码正在更改，因此，必须更新具有电话号码作为默认号码的所有用户 (如果有) ，并且从音频会议网桥取消分配电话号码之前更新其现有会议邀请。

如果在不更新用户及其会议的情况下删除了电话号码，则其现有会议邀请可能包含一个无法加入其会议的电话号码。

对于前三步，需要启动 Windows PowerShell。 若要查看如何执行此操作，请单击 [想要了解如何使用 Windows PowerShell 管理？](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>步骤 1 - 更新将电话号码取消分配为默认号码之一的用户

将具有取消分配号码的所有用户的默认收费或免费号码替换为默认号码，并开始重新安排其会议的过程。 要执行此操作，请运行以下命令：

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >还可在管理中心内更改默认收费或免费Microsoft Teams号码。 但是，这不会自动重新安排他们的会议。 
 
 有关其他信息，请参阅[设置](set-the-phone-numbers-included-on-invites-in-teams.md)邀请中包含的电话号码Microsoft Teams或在 Skype for Business Online 中设置[邀请中包含的电话号码](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。

  > [!NOTE]
  > [!注释] 根据组织的规模，这可能需要一段时间才能完成。

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>第 2 步 - 使用 Windows PowerShell 查看会议迁移状态

在没有任何操作进入"挂起"或"正在进行"状态后，将 *重新安排所有* 会议。

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

有关会议迁移服务的详细信息，请参阅[设置会议迁移服务 (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>步骤 3 - 从音频会议网桥取消分配旧电话号码

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航栏中，转到"**语音**  >  **"电话号码"**。

2. 如果电话号码是免费电话号码，请从列表中选择电话号码，然后单击"释放 **"。** 如果电话号码是收费电话号码，请联系 [Microsoft](/microsoft-365/admin/contact-support-for-business-products) 支持部门以取消分配电话号码。

3. 如果电话号码是免费电话号码，请在确认窗口中 **单击"是** "。

   > [!IMPORTANT]
   > 从音频会议网桥取消分配电话号码后，用户将无法再使用电话号码加入新会议或现有会议。

### <a name="save-time-and-automate"></a>节省时间并自动执行

若要通过自动执行此过程来节省时间，可以使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) 或 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet。

- 使用 [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet 可更改特定用户的默认收费电话号码或免费电话号码。

  - 若要更改用户的默认免费电话号码，请运行：

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- 使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet 可基于用户的原始默认电话号码或位置来更改其默认收费电话号码或免费电话号码。

    > [!NOTE]
    > 若要查找 BridgeID，请使用 **Get-CsOnlineDialInConferencingBridge**。

  - 若要为没有默认免费电话号码的所有用户将默认免费电话号码设置为 8005551234，请运行：

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```

  - 若要为默认免费电话号码已设置为 8005551234 的所有用户将默认免费电话号码更改为 8005551239，并自动重新安排其会议，请运行：

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber 8005551234 -ToNumber 8005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

  - 若要为位于美国的所有用户将默认免费电话号码设置为 8005551234，并自动重新安排其会议，请运行：

  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber 8005551234 -NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings
  ```

    > [!NOTE]
    > 上面使用的位置需要匹配用户在管理 (中) 设置的Microsoft 365信息。

## <a name="troubleshooting"></a>疑难解答

**"取消分配"按钮不可用**

您希望取消分配号码，但按钮不可用，并且如果将鼠标悬停在该号码上，将重定向至联系支持人员，显示以下消息："无法从网桥取消分配默认号码或共享号码。 _若要取消分配专用收费号码，请联系支持人员_。"。

若要获取有关网桥 () ，请运行以下 Powershell：
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

结果（除了标识、名称和区域等其他信息）还应包含 DefaultServiceNumber。

**示例**， 要取消分配，DefaultServiceNumber 为 "8005551234"
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>有关 Windows PowerShell

可使用 Windows PowerShell 管理用户并管理他们能否执行的操作内容。 Windows PowerShell单点管理Microsoft 365管理 Office 365 Skype for Business Online，可以简化日常工作，尤其是有多个任务需要执行时。 若要开始使用 Windows PowerShell，请参阅下列主题：

  - [Windows PowerShell 和 Skype for Business Online 简介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [为什么要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

Windows PowerShell管理中心相比，Microsoft 365在速度、简单性和工作效率方面具有许多优势，例如，一次对许多用户进行设置更改时。 通过以下主题了解这些优势：

  - [使用 Microsoft 365 Office 365 管理Windows PowerShell](/previous-versions//dn568025(v=technet.10))

  - [使用 Windows PowerShell 管理 Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>相关主题
[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)