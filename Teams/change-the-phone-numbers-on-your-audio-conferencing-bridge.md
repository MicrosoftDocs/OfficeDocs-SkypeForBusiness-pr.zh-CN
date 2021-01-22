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
ms.openlocfilehash: 7f9efd4289f24b4248cddd732773d7c96e728f0c
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918748"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>更改音频会议网桥中的电话号码

当你购买 **音频会议许可证** 时，Microsoft 将托管你的组织的音频会议网桥。 音频会议网桥提供不同位置的拨入电话号码，以便会议组织者和参与者可以使用它们通过电话加入 Skype for Business 或 Microsoft Teams 会议。
  
除了已分配给会议网桥的电话号码外，你可以从其他位置获取用于音频会议[](/microsoftteams/getting-service-phone-numbers)) 的其他服务号码 (收费和免费号码，然后将它们分配给会议网桥，以便你可以扩大用户的覆盖范围。
  
> [!NOTE]
> 为了能够为会议网桥分配/取消分配电话号码，电话号码必须是"*服务*"号码。 通过导航到 Microsoft Teams 管理中心中的语音电话号码并查看"号码类型"列，可以看到号码  >  的类型。  必须先设置 Microsoft 365 或 Office 365 通信积分，用户才能拨打免费电话号码拨入网桥。

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>将新的服务电话号码分配给会议网桥的操作步骤

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>步骤 1 - 将新电话号码分配给音频会议网桥

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航窗格中，转到 **"语音**  >  **电话号码"。**

2. 从列表中选择电话号码，然后单击"编辑 **"。**

3. 在"**编辑"** 页面上的 **"分配到"下**，展开下拉列表，然后选择"会议 **网桥** 应用  >  **"。**

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>步骤 2 - 将会议网桥的默认电话号码 (可选) 

会议网桥的默认电话号码定义当参与者或组织者从会议内拨打出站呼叫时将使用的呼叫者 ID。

只能将收费服务号码设置为会议网桥的默认号码; **无法将** 服务免费号码设置为会议网桥的默认号码。 如果要分配收费服务号码，并且希望将其设置为音频会议网桥的新默认号码，请执行以下步骤：

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航窗格中，转到 **"会议**  >  **网桥"。**

2. 突出显示要配置为默认值的服务收费电话号码。

3. 选择“**设置为默认值**”。
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>步骤 3 - 更改用户的会议邀请中包含的默认电话号码 (可选) 

用户的默认电话号码是安排会议时会议邀请中包含的号码。 有关详细信息，包括如何为新用户分配默认电话号码，请参阅"在 [Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md) 中设置邀请中包括的电话号码"或"设置 [Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)中的邀请中包含的电话号码"。

![一个显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png) **使用 Microsoft Teams 管理中心**

1. 在左侧导航窗格中，转到 **"用户** "，然后单击列表中所需用户的显示名称。

2. 在音频 **会议旁边，** 单击"编辑 **"。**

3. 在 **收费电话号码** 或 **免费电话号码** 下，从下拉列表中选择号码，然后单击"应用 **"。**

应用更改后，新的默认电话号码将在组织者下次安排新会议时包含在会议邀请中。

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>步骤 4 - 使用会议迁移服务更新用户的现有会议邀请 (可选) 

对于接下来的两个步骤，需要开始Windows PowerShell。
  
如果您更新了部分或所有用户的会议邀请中包含的默认电话号码，您可以选择更新在使用会议迁移服务更改默认电话号码之前已发送给您的组织中的用户的会议邀请。 有关更多信息，请参阅[设置会议迁移服务 (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。
  
- 使用 MMS (会议) 在步骤 2 中更改其默认电话号码的用户运行 MMS 帐户。 要执行此操作，请运行以下命令：

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- 你还可以查看会议迁移状态。 一旦没有处于 *待处理*  或 *进行中*  状态的操作时，将会重新安排会议。

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>取消为会议网桥分配的服务电话号码的操作步骤


取消为会议网桥分配的服务电话号码时，用户将不能再使用该电话号码加入任何会议。 由于电话号码正在更改，因此，必须更新可能将电话号码作为默认号码 (的所有用户（如果有) ）并更新其现有会议邀请，然后才能从音频会议网桥取消分配电话号码。

如果在不更新用户及其会议的情况下删除电话号码，则其现有会议邀请可能包含一个无法加入其会议的电话号码。

对于前三步，需要启动 Windows PowerShell。 若要查看如何执行此操作，请单击 [想要了解如何使用 Windows PowerShell 管理？](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>步骤 1 - 更新将电话号码取消分配为默认号码之一的用户

为具有要取消分配号码的所有用户替换默认收费或免费电话号码作为默认号码，并开始重新安排其会议的过程。 要执行此操作，请运行以下命令：

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >还可以在 Microsoft Teams 管理中心更改默认收费或免费用户数。 但是，这不会自动重新安排他们的会议。 
 
 有关其他信息，请参阅"在[Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md)中设置邀请中包含的电话号码"或"设置 Skype for Business Online 中的邀请中包含的[电话号码"。](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)

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

1. 在左侧导航中，转到 **"语音**  >  **电话号码"。**

2. 如果电话号码是免费电话号码，请从列表中选择电话号码，然后单击"释放 **"。** 如果电话号码是收费电话号码，请联系 [Microsoft](https://go.microsoft.com/fwlink/?linkid=2091806) 支持部门以取消分配电话号码。

3. 如果电话号码是免费电话号码，请在 **确认窗口中单击** "是"。

   > [!IMPORTANT]
   > 从音频会议网桥取消分配电话号码后，用户不再能够加入新会议或现有会议。

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>确认 Windows PowerShell 是否准备就绪

 这些步骤检查你运行的是Windows PowerShell 3.0 或更高版本。

1. 键入 **开始菜单** > **Windows PowerShell** 。

2. 在 _Windows PowerShell_ 窗口中键入 **Get-Host** ，以检查版本。

3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。 请参阅 [Windows 管理框架 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) 下载并更新Windows PowerShell 4.0 版。
出现提示时，请重启计算机。

4. 你还需要安装 Skype for Business Online Windows PowerShell模块，该模块使你能够创建连接到 Skype for Business Online Windows PowerShell远程聊天会话。 此模块仅在 64 位计算机上受支持，可以从适用于 Skype for Business Online 的 Windows PowerShell 模块上的 Microsoft 下载 [中心下载](https://go.microsoft.com/fwlink/?LinkId=294688)。
出现提示时，请重启计算机。

如果需要了解更多信息，请参阅"在单个客户端窗口中连接到所有 [Microsoft 365 或 Office 365 Windows PowerShell服务](https://technet.microsoft.com/library/dn568015.aspx)。

### <a name="to-start-windows-powershell"></a>启动 Windows PowerShell

 **启动 Windows PowerShell 会话**

1. From the **Start Menu** > **Windows PowerShell**.

2. 在Windows PowerShell **窗口中** ，通过运行以下程序连接到 Microsoft 365 或 Office 365：

> [!NOTE]
> Skype for Business Online 连接器当前是最新 Teams PowerShell 模块的一部分。
>
> 如果你使用的是最新的 [Teams PowerShell 公共](https://www.powershellgallery.com/packages/MicrosoftTeams/)版本，则无需安装 Skype for Business Online 连接器。

>
  ```PowerShell
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> [!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。
如果你需要有关启动 Windows PowerShell，请参阅"在单个 Windows PowerShell 窗口中连接到所有[Microsoft 365 或 Office 365](https://technet.microsoft.com/library/dn568015.aspx)服务，或者使用 Windows PowerShell 连接到[Skype for Business Online。](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)

### <a name="save-time-and-automate"></a>节省时间并自动执行

若要通过自动执行此过程来节省时间，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) 或 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet。

- 使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet 可更改特定用户的默认收费电话号码或免费电话号码。

  - 若要更改用户的默认免费电话号码，请运行：

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- 使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet 可基于用户的原始默认电话号码或位置来更改其默认收费电话号码或免费电话号码。

    > [!NOTE]
    > 若要查找 BridgeID，请使用 **Get-CsOnlineDialInConferencingBridge。**

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
    > 上面使用的位置需要匹配用户在 Microsoft 365 (设置) 联系人的联系信息。

## <a name="troubleshooting"></a>疑难解答

**"取消分配"按钮不可用**

你想要取消分配号码，但按钮不可用，并且如果将鼠标悬停在该号码上，将重定向至联系支持人员，显示以下消息："无法从网桥取消分配默认号码或共享号码。 _若要取消分配专用收费电话号码，请联系支持人员_。"。

若要获取有关网桥 () ，请运行以下 Powershell：
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

结果（标识、名称和区域等其他信息）也应包含 DefaultServiceNumber。

**要** 取消分配的示例，DefaultServiceNumber "8005551234"
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>有关 Windows PowerShell

可使用 Windows PowerShell 管理用户并管理他们能否执行的操作内容。 Windows PowerShell可以通过单点管理来帮助你管理 Microsoft 365 或 Office 365 和 Skype for Business Online，从而简化日常工作，尤其是当你有多个任务需要执行时。 若要开始使用 Windows PowerShell，请参阅下列主题：

  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell与仅使用 Microsoft 365 管理中心相比，在速度、简单性和工作效率方面具有许多优势，例如一次为许多用户进行设置更改时。 通过以下主题了解这些优势：

  - [使用 Office 365 管理 Microsoft 365 或 Office 365 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相关主题
[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)
