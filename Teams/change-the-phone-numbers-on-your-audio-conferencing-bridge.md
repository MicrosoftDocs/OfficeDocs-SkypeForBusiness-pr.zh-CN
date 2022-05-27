---
title: 更改音频会议桥上的电话号码
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 了解向会议网桥分配新服务电话号码以扩大用户覆盖范围所需的步骤。
ms.openlocfilehash: 0433577334dca5f84854ba1cdc14b81e4ec37e63
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674774"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>更改音频会议网桥中的电话号码

购买 **音频会议** 许可证时，Microsoft 将为组织托管音频会议网桥。 音频会议网桥提供来自不同位置的拨入电话号码，以便会议组织者和参与者可以使用电话加入Skype for Business或Microsoft Teams会议。

除了已分配给会议网桥的电话号码外，还可以从其他位置获取用于音频会议) 的 [附加服务号码](./getting-service-phone-numbers.md) (收费和免费号码，然后将其分配到会议网桥，以便可以扩大用户的覆盖范围。

> [!NOTE]
> 若要能够为会议网桥分配/取消分配电话号码，电话号码必须是“*服务*”号码。 可以通过在Microsoft Teams管理中心导航到 **Voice** > **电话 数字** 并查看 **“数字类型**”列来查看数字的类型。 必须先设置Microsoft 365或Office 365通信额度，以便用户以免费号码拨入网桥。

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>将新的服务电话号码分配给会议网桥的操作步骤

> [!NOTE]
> 除非调用它，否则必须在Microsoft Teams管理中心执行所有这些步骤。

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>步骤 1 - 将新电话号码分配到音频会议网桥

1. 在左侧导航窗格中，转到 **“语音** > **电话数字**。

2. 从列表中选择电话号码，然后单击 **“编辑**”。

3. 在 **“编辑**”页上，在 **“分配到**”下展开下拉列表，然后选择 **“应用会议网桥** > ”。

### <a name="step-2---change-the-default-phone-number-of-your-conference-bridge-optional"></a>步骤 2 - 更改会议网桥的默认电话号码 (可选) 

会议网桥的默认电话号码定义了当参与者或组织者从会议中进行出站呼叫时将使用的呼叫者 ID。

只能将服务收费号码设置为会议网桥的默认号码; **服务免费号码不能设置为会议网桥的默认号码**。 如果要分配服务收费号码，并且要将其设置为音频会议网桥的新默认号码，请执行以下步骤：

1. 在左侧导航窗格中，转到 **会议** > **会议网桥**。

2. 突出显示要配置为默认的服务收费号码。

3. 选择“**设置为默认值**”。

### <a name="step-3---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>步骤 3 - 更改用户会议邀请中包含的默认电话号码 (可选) 

请参阅[设置Microsoft Teams中邀请中包含的电话号码](set-the-phone-numbers-included-on-invites-in-teams.md)。

> [!NOTE]
> 还可以通过将电话号码添加到 *TeamsAudioconferencingpolicy* 并将策略分配给用户来设置电话号码。 添加到策略的收费和免费电话号码优先于通过音频会议设置窗格为用户单独设置的电话号码。 如果未将电话号码添加到 *Teamsaudioconferencingpolicy*，则通过音频会议设置窗格为用户单独设置的电话号码将显示在Microsoft Teams会议请求中。 [音频会议收费和免费号码的策略设置](audio-conferencing-toll-free-numbers-policy.md)包含更多信息。

### <a name="step-4---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>步骤 4 - 使用会议迁移服务更新用户的现有会议邀请 (可选) 

对于接下来的两个步骤，需要开始Windows PowerShell。

如果更新了部分或所有用户的会议邀请中包含的默认电话号码，则可以选择在使用会议迁移服务更改其默认电话号码之前更新已发送给组织中的用户的会议邀请。 有关更多信息，请参阅[设置会议迁移服务 (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。

- 为在步骤 2 中更改了默认电话号码的用户运行会议迁移服务 (MMS) 。 要执行此操作，请运行以下命令：

```PowerShell
    Start-CsExMeetingMigration user@contoso.com
```

- 你还可以查看会议迁移状态。 一旦没有处于 *待处理*  或 *进行中*  状态的操作时，将会重新安排会议。

```PowerShell
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>取消为会议网桥分配的服务电话号码的操作步骤

取消为会议网桥分配的服务电话号码时，用户将不能再使用该电话号码加入任何会议。 由于电话号码正在更改，因此请务必更新所有用户，这些用户可以将电话号码作为其默认号码 (如果有任何) ，并在电话号码未从音频会议网桥上分配之前更新其现有会议邀请。

如果在不更新用户及其会议的情况下删除电话号码，其现有会议邀请可能包含一个不适用于加入其会议的电话号码。

对于前三步，需要启动 Windows PowerShell。 若要查看如何执行此操作，请单击 [想要了解如何使用 Windows PowerShell 管理？](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#about-windows-powershell)

### <a name="step-1---update-users-who-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>步骤 1 - 更新电话号码未分配为其默认号码之一的用户

为将号码取消分配为默认号码的所有用户替换默认收费或免费号码，并启动重新安排会议的过程。 要执行此操作，请运行以下命令：

```PowerShell
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```

 > [!IMPORTANT]
 >还可以更改Microsoft Teams管理中心内的默认收费或免费用户数。 但是，这不会自动重新安排他们的会议。

 有关其他信息，请参阅[设置邀请Microsoft Teams中包含的电话号码](set-the-phone-numbers-included-on-invites-in-teams.md)，或[设置Skype for Business Online 中邀请中包含的电话号码](/SkypeForBusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites)。

  > [!NOTE]
  > [!注释] 根据组织的规模，这可能需要一段时间才能完成。

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>第 2 步 - 使用 Windows PowerShell 查看会议迁移状态

一旦没有处于 *“挂起* ”或“ *正在进行* ”状态的操作，将重新安排所有会议。

```PowerShell
Get-CsMeetingMigrationStatus -SummaryOnly
```

有关会议迁移服务的详细信息，请参阅[设置会议迁移服务 (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。

### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>步骤 3 - 从音频会议桥取消分配旧电话号码

使用Unregister-CsOnlineDialInConferencingServiceNumber cmdlet 从会议桥取消注册收费或免费号码

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll number to be removed" -bridgeId "Conference Bridge ID"
Unregister-CsOnlineDialInConferencingServiceNumber -identity "toll free number to be removed" -bridgeId "Conference Bridge ID"
```

注意：若要查找会议桥 ID，请运行以下 PowerShell：Get-CsOnlineDialInConferencingBridge。

   > [!IMPORTANT]
   > 在音频会议网桥未分配电话号码后，用户将不再可以加入新的或现有的会议。

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
    > 上述位置需要与Microsoft 365 管理中心中设置的用户 () 的联系信息相匹配。

## <a name="troubleshooting"></a>疑难解答

### <a name="the-unassign-button-isnt-available"></a>“取消分配”按钮不可用

你想要取消分配数字，但该按钮不可用，如果将鼠标悬停在该按钮上，则会重定向到与支持部门联系，并显示以下消息：“默认号码或共享号码不能从桥上取消分配。 若要取消分配专用收费号码，请联系支持人员。

若要获取有关桥 () 的详细信息，请运行以下 Powershell：

```PowerShell
Get-CsOnlineDialInConferencingBridge -Name "Conference Bridge"
```

除标识、名称和区域等其他信息外，结果还应包含 DefaultServiceNumber。

**例如**，若要取消分配，DefaultServiceNumber“8005551234”

```PowerShell
Unregister-CsOnlineDialInConferencingServiceNumber -BridgeName "Conference Bridge" -RemoveDefaultServiceNumber 8005551234
```

## <a name="about-windows-powershell"></a>有关 Windows PowerShell

可使用 Windows PowerShell 管理用户并管理他们能否执行的操作内容。 Windows PowerShell可以帮助你使用单个管理点来管理Microsoft 365或Office 365和联机Skype for Business，这可以简化日常工作，尤其是当你有多个任务需要执行时。 若要开始使用 Windows PowerShell，请参阅下列主题：

- [Windows PowerShell 和 Skype for Business Online 简介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

- [为什么要使用 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

Windows PowerShell在速度、简单性和工作效率方面有许多优势，而不是只使用Microsoft 365 管理中心，例如每次对许多用户进行设置更改时。 通过以下主题了解这些优势：

- [使用Windows PowerShell管理Microsoft 365或Office 365的最佳方法](/previous-versions//dn568025(v=technet.10))

- [使用 Windows PowerShell 管理 Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

- [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>相关主题

[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)
