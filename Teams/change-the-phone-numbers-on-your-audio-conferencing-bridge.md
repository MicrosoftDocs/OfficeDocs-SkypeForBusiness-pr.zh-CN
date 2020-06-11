---
title: 更改音频会议桥的电话号码
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
description: 了解将新服务电话号码分配给你的会议桥所需的步骤，以便为你的用户扩展覆盖范围。
ms.openlocfilehash: e0786ad2c35ebe7d9663a71b594f7f5facd73b08
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691378"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>更改音频会议网桥中的电话号码

当您购买**音频会议**许可证时，Microsoft 将为您的组织托管您的音频会议桥。 音频会议网桥提供来自不同位置的拨入电话号码，以便会议组织者和参与者可以使用电话加入 Skype for business 或 Microsoft 团队会议。
  
除了已分配给您的会议网桥的电话号码，您还可以从其他位置[获取其他服务号码](/microsoftteams/getting-service-phone-numbers)（用于音频会议的收费和免费电话号码），然后将它们分配给会议桥，以便您可以为您的用户展开覆盖范围。
  
> [!NOTE]
> 为能够分配/取消分配会议网桥的电话号码，电话号码必须是 "*服务*" 号码。 你可以通过导航到旧版门户中的**语音**  >  **电话号码**并在 "**数字类型**" 列中查看，来查看号码的类型。 必须首先设置 Microsoft 365 或 Office 365 通信信用点数，以便用户可以在免费电话号码上拨入网桥。

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>将新的服务电话号码分配给会议网桥的操作步骤

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>步骤 1-将新电话号码分配给您的音频会议桥

1. 使用你的工作帐户登录到 Microsoft 365 或 Office 365。

2. 转到**Microsoft 365 管理中心**  >  **管理中心**  >  **团队 & Skype**  >  **旧门户**  >  **语音**  >  **电话号码**。

3. 从列表中选择电话号码，然后在 "操作" 窗格中单击 "**分配**"。

4. 在" **分配**"页面上，单击" **保存**"。

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>步骤 2-更改您的会议桥的默认电话号码（可选）

您的会议网桥的默认电话号码定义了当参与者或组织者在会议中发出出站呼叫时，将使用的呼叫方 ID。

只有服务收费电话号码才能设置为您的会议桥的默认号码;**服务免费电话号码不能设置为您的会议网桥的默认号码**。 如果您要分配服务的收费电话号码，并且想要将其设置为您的音频会议网桥的新默认号码，请执行以下步骤：

1. 使用你的工作帐户登录到 Microsoft 365 或 Office 365。

2. 转到**Microsoft 365 管理中心**  >  **管理中心**  >  **团队 & Skype**  >  **会议**  >  **桥**。

3. 突出显示要配置为默认电话的服务电话号码。

4. 选择“**设置为默认值**”。
 
### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>步骤 3-更改用户的会议邀请中包含的默认电话号码（可选）

在安排会议时，用户的默认电话号码是会议邀请中包含的电话号码。 有关详细信息，包括为新用户分配默认电话号码的方式，请参阅[设置 Microsoft 团队邀请中包含的电话号码](set-the-phone-numbers-included-on-invites-in-teams.md)，或[在 Skype for Business Online 中设置邀请中包含的电话号码](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。
  
1. 使用你的工作或学校帐户登录。

2. 转到**Microsoft 365 管理中心**  >  **管理中心**  >  **团队 & Skype**  >  **旧版门户**  >  **音频会议**  >  **用户**，然后在列表中选择用户。

3. 在"操作"窗格中单击" **编辑**"。

4. 在 "**默认收费电话号码**" 或 "**默认免费电话号码**" 下，选择列表中的号码，然后单击 "**保存**"。

保存更改后，新的默认电话号码将包含在组织者下次安排新会议时的会议邀请中。

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>步骤 4-使用会议迁移服务更新用户的现有会议邀请（可选）

对于接下来的两个步骤，你将需要启动 Windows PowerShell。
  
如果你更新了某些或所有用户的会议邀请中包含的默认电话号码，你可以选择更新已发送给组织中的用户的会议邀请，并使用会议迁移服务更改其默认电话号码。 有关更多信息，请参阅[设置会议迁移服务 (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。
  
- 为在步骤2中更改了默认电话号码的用户运行会议迁移服务（MMS）。 要执行此操作，请运行以下命令：

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- 你还可以查看会议迁移状态。 一旦没有处于 *待处理*  或 *进行中*  状态的操作时，将会重新安排会议。

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>取消为会议网桥分配的服务电话号码的操作步骤


取消为会议网桥分配的服务电话号码时，用户将不能再使用该电话号码加入任何会议。 由于电话号码已更改，因此，将可能具有电话号码的所有用户更新为其默认号码（如果有），并在从音频会议桥中取消分配电话号码之前更新现有会议邀请非常重要。

如果删除电话号码时未更新用户及其会议，则他们的现有会议邀请可能包含不能用于加入会议的电话号码。

对于前三步，需要启动 Windows PowerShell。 若要查看如何执行此操作，请单击 [想要了解如何使用 Windows PowerShell 管理？](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>步骤 1-将要取消分配的电话号码的用户更新为其默认号码之一

将具有要取消分配的号码的所有用户的默认收费或免费号码替换为默认号码，并开始重新安排其会议的过程。 要执行此操作，请运行以下命令：

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT] 
 >您也可以在 Skype for Business 管理中心更改默认的收费或免费的用户数。 但是，这不会自动重新安排他们的会议。 
 
 有关其他信息，请参阅[设置 Microsoft 团队邀请中包含的电话号码，](set-the-phone-numbers-included-on-invites-in-teams.md)或[在 Skype for Business Online 中设置邀请中包含的电话号码](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。

  > [!NOTE]
  > [!注释] 根据组织的规模，这可能需要一段时间才能完成。

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>第 2 步 - 使用 Windows PowerShell 查看会议迁移状态

一旦没有任何操作处于*挂起*或*正在进行*状态，将重新安排所有会议。

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

有关会议迁移服务的详细信息，请参阅[设置会议迁移服务 (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。
  
### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>步骤 3-取消分配音频会议桥的旧电话号码

1. 使用你的工作或学校帐户登录。

2. 转到**Microsoft 365 管理中心**  >  **管理中心**  >  **团队 & Skype**  >  **旧门户**  >  **语音**  >  **电话号码**。

3. 如果电话号码是免费号码，请从列表中选择电话号码，然后在 "操作" 窗格中单击 "**取消分配**"。 如果电话号码是收费电话号码，请联系[Microsoft 支持](https://go.microsoft.com/fwlink/?linkid=2091806)部门，让电话号码未分配。

4. 如果电话号码是免费号码，请在确认窗口中单击 **"是"** 。

   > [!IMPORTANT]
   > 从音频会议桥中取消分配电话号码后，用户将不再可以使用该电话号码加入新的或现有会议。

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>确认 Windows PowerShell 是否准备就绪

 这些步骤将检查你是否正在运行 Windows PowerShell 版本3.0 或更高版本。

1. 键入 **开始菜单** > **Windows PowerShell** 。

2. 在 _ Windows PowerShell_ 窗口中键入 **Get-Host** ，以检查版本。

3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。 请参阅[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845)以下载 windows PowerShell 并将其更新到版本4.0。
出现提示时，请重启计算机。

4. 你还需要安装适用于 Skype for business Online 的 Windows PowerShell 模块，使你能够创建连接到 Skype for business Online 的远程 Windows PowerShell 会话。 此模块仅在64位计算机上受支持，并且可从[适用于 Skype for Business Online 的 Windows PowerShell 模块](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下载中心下载。
出现提示时，请重启计算机。

如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接到所有 Microsoft 365 或 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)。

### <a name="to-start-windows-powershell"></a>启动 Windows PowerShell

 **启动 Windows PowerShell 会话**

1. From the **Start Menu** > **Windows PowerShell**.

2. 在 " **Windows PowerShell** " 窗口中，通过运行以下内容连接到 Microsoft 365 或 Office 365：

>
  ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

> [!NOTE]
> [!注释] 只需在首次使用 Skype for Business Online Windows PowerShell 模块时运行 **Import-Module** 命令即可。
如果需要有关启动 Windows PowerShell 的详细信息，请参阅使用 Windows PowerShell[连接到单个 Windows powershell 窗口中的所有 Microsoft 365 或 Office 365 服务](https://technet.microsoft.com/library/dn568015.aspx)或[连接到 Skype for business Online](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx)。

### <a name="save-time-and-automate"></a>节省时间并实现自动化

为了通过自动化此过程节省时间，你可以使用[get-csonlinedialinconferencinguser](https://go.microsoft.com/fwlink/?LinkId=617688)或**set-csonlinedialinconferencinguserdefaultnumber** cmdlet。

- 使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet 可更改特定用户的默认收费电话号码或免费电话号码。

  - 若要更改用户的默认免费电话号码，请运行：

  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- 使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet 可基于用户的原始默认电话号码或位置来更改其默认收费电话号码或免费电话号码。

    > [!NOTE]
    > 若要查找 BridgeID，请使用**get-csonlinedialinconferencingbridge**。

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
    > 上面使用的位置需要与在 Microsoft 365 管理中心中设置的用户联系信息匹配。

## <a name="troubleshooting"></a>故障排除

**"取消分配" 按钮不可用**

您希望取消分配某个号码，但该按钮不可用，如果悬停在该按钮上，则会被重定向到联系支持人员，显示以下消息 _"默认或共享号码可以从桥中取消储存。要取消分配专用的收费电话，请联系支持部门。_"。

若要获取有关桥的详细信息，请运行以下 Powershell：
```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

结果，除了标识、名称和区域之类的其他信息之外，还应包含 DefaultServiceNumber。

**例如**，若要取消分配，DefaultServiceNumber "8005551234"
```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234 
```

## <a name="about-windows-powershell"></a>有关 Windows PowerShell

可使用 Windows PowerShell 管理用户并管理他们能否执行的操作内容。 Windows PowerShell 可帮助你使用单一的管理点管理 Microsoft 365 或 Office 365 和 Skype for Business Online，尤其是当你有多个任务需要执行此操作时。 若要开始使用 Windows PowerShell，请参阅下列主题：

  - [Windows PowerShell 和 Skype for Business Online 简介](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell 在速度、简洁性和效率方面具有许多优势，仅限于使用 Microsoft 365 管理中心，例如当你同时为多个用户设置更改时。 通过以下主题了解这些优势：

  - [通过 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相关主题
[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)
