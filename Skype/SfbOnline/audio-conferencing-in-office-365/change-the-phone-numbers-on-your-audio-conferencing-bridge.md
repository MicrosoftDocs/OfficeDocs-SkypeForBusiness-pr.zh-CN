---
title: 更改音频会议网桥的电话号码
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6403f6d1-c05a-44ab-a6e0-558000e246f4
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
description: 在购买音频会议许可证时，是 Microsoft 在托管组织的音频会议网桥。 该会议网桥会提供不同地点的拨入电话号码，会议组织者和参与者可以借助电话用这些号码参加 Skype for Business 或者 Microsoft Teams 会议。
ms.openlocfilehash: c567c1394c60b0be04cae90865cea14b856f1cd5
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255708"
---
# <a name="change-the-phone-numbers-on-your-audio-conferencing-bridge"></a>更改音频会议网桥的电话号码

在购买 **音频会议** 许可证时，是 Microsoft 在托管组织的 *音频会议网桥* 。 该会议网桥会提供不同地点的拨入电话号码，会议组织者和参与者可以借助电话用这些号码参加 Skype for Business 或者 Microsoft Teams 会议。

除了已分配的会议网桥电话号码，还可以从其他位置 [获取额外的服务号码](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md) （用于音频会议的收费和免费电话号码），然后分配给会议网桥以便展开用户的范围。

> [!NOTE]
> 为了能够为某个会议网桥分配 / 取消分配电话号码，电话号码必须是一个“ *服务* ”号码。 通过导航至 **语音** > **电话号码** 并查看 **号码类型** 列，可以看到号码类型是什么。 为了让用户拨入免费电话号码上的网桥，应首先设置 Office 365 通信点数。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="steps-when-you-are-assigning-a-new-service-phone-number-to-your-conference-bridge"></a>将新的服务电话号码分配给会议网桥的操作步骤

### <a name="step-1---assign-the-new-phone-number-to-your-audio-conferencing-bridge"></a>第 1 步 - 将新的电话号码分配给音频会议网桥

1. 使用工作帐户登录 Office 365。

2. 转至 **Office 365 管理中心** > **管理中心** > **Skype for Business** > **语音** > **电话号码** 。

3. 从列表中选择电话号码，然后在“操作”窗格中，单击 **分配** 。

4. 在 **分配** 页面上，单击 **保存** 。

    只有收费服务电话号码可以设置为会议网桥的默认号码； **免费服务电话号码不能设置为会议网桥的默认号码** 。 如果在分配收费服务号码时希望将其设置为会议网桥的新默认号码，请选择 **使用此号码作为默认号码** 。

    > [!NOTE]
    > [!注释] 分配了新电话号码后，即使该号码已经是新默认号码，现有用户的默认号码也不会更改。 若要设置添加到组织者的会议邀请的默认收费电话号码或免费电话号码，请参阅 [设置邀请中包含的电话号码](set-the-phone-numbers-included-on-invites.md) 。



### <a name="step-2---change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users-optional"></a>第 2 步 - 更改用户会议邀请中包含的默认电话号码（可选）

用户的默认电话是他们安排会议时在会议邀请中包含的电话号码。 有关详细信息，请参阅 [设置邀请中的电话号码](set-the-phone-numbers-included-on-invites.md) 。

1. 使用工作或学校帐户登录 Office 365。

2. 转至 **Office 365 管理中心** > **管理中心** > **Skype for Business** > **音频会议** > **用户** 在列表中选择用户。

3. 在"操作"窗格中单击 **编辑** 。

4. 在 **默认收费电话号码** 或者 **默认免费电话号码** 下，选择列表中的电话号码并单击 **保存** 。

保存更改后，他们再安排会议时，组织者的会议邀请中包含的将是新的默认电话号码。

### <a name="step-3---update-existing-meeting-invites-of-users-using-the-meeting-migration-service-optional"></a>第 3 步 - 使用会议迁移服务更新用户的现有会议邀请（可选）

接下来的两个步骤，将需要启动 Windows PowerShell。

通过使用会议迁移服务，可以选择更新会议邀请，这些邀请在默认电话号码被更改之前就发送给了组织中的用户。 有关更多信息，请参阅 [设置会议迁移服务 (MMS)](setting-up-the-meeting-migration-service-mms.md) 。

- 对其默认电话号码已在第 2 步中更改了的用户运行会议迁移服务 (MMS)。 要执行此操作，请运行以下命令：

```
    Start-CsExMeetingMigration user@contoso.com
```

- 亦可查看会议迁移状态。一旦在 *挂起* 或者 *正在进行* 状态中没有操作，所有会议将被重新安排。

```
    Get-CsMeetingMigrationStatus -SummaryOnly
```

## <a name="steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge"></a>取消为会议网桥分配的服务电话号码的操作步骤


取消为会议网桥分配的服务电话号码时，用户将不能再使用该电话号码参加任何会议。 由于电话号码在不断变化，在取消为音频会议网桥分配的电话号码之前，重要的是更新所有可能具有某个电话号码作为其默认号码的用户（如果存在），并更新现有会议邀请。

如果删除电话号码时没有通知用户及更新其会议，那么他们的现有会议邀请可能包含无法再用于加入其会议的电话号码。

对于前三步，需要启动 Windows PowerShell。 若要查看如何执行此操作，请单击 [想要了解如何使用 Windows PowerShell 管理？](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#bkPowerShell)

### <a name="step-1---update-users-that-have-the-phone-number-to-be-unassigned-as-one-of-their-default-numbers"></a>第 1 步 - 更新其默认电话号码之一要被取消分配的电话号码的用户

为其默认号码是要取消分配的号码的用户替换默认的收费或免费号码，并开始重新安排其会议的过程。要执行此操作，请运行以下命令：

```
Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber <Number to be removed> -ToNumber <Number to be set as new default> -NumberType <"Toll" or "Toll-Free"> -RescheduleMeetings
```
 > [!IMPORTANT]
 >还可以在 Sktpy 管理中心更改默认的用户收费电话号码或免费电话号码。 但是，这不会自动重新安排他们的会议。

 有关详细信息，请参阅 [设置邀请中的电话号码](set-the-phone-numbers-included-on-invites.md) 。

  > [!NOTE]
  > 根据组织的规模，这可能需要一段时间才能完成。

### <a name="step-2---view-meeting-migration-status-using-windows-powershell"></a>第 2 步 - 使用 Windows PowerShell 查看会议迁移状态

一旦在 *挂起* 或 *正在进行* 状态下没有操作，所有会议将被重新安排。

```
Get-CsMeetingMigrationStatus -SummaryOnly
```

有关会议迁移服务的详细信息，请参阅 [设置会议迁移服务 (MMS)](setting-up-the-meeting-migration-service-mms.md) 。

### <a name="step-3---unassign-the-old-phone-number-from-the-audio-conferencing-bridge"></a>第 3 步 - 取消为音频会议网桥分配的旧电话号码

1. 使用工作或学校帐户登录 Office 365。

2. 转至 **Office 365 管理中心** > **管理中心** > **Skype for Business** > **语音** > **电话号码** 。

3. 从列表中选择电话号码，然后在“操作”窗格中单击 **取消分配** 。

4. 在确认窗口中，单击 **是** 。

  > [!IMPORTANT]
  > 从音频会议网桥中取消分配某个电话号码后，用户就无法使用该电话号码参加新的或现有会议。

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 进行管理吗？
<a name="bkPowerShell"> </a>

### <a name="to-verify-that-windows-powershell-is-ready-to-go"></a>确认 Windows PowerShell 是否准备就绪

 这些步骤检查运行的是不是 3.0 或以上版本的 Windows PowerShell。

1. 键入 **开始菜单** > **Windows PowerShell** 。

2. 在 _ Windows PowerShell_ 窗口中键入 **Get-Host** ，以检查版本。

3. 如果你没有 3.0 版本或更高版本，则需要下载并安装 Windows PowerShell 更新。请参阅 [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) 以下载 Windows PowerShell 并将其更新到 4.0 版本。出现提示时，请重启计算机。

4. 还需要为 Skype for Business Online 安装 Windows PowerShell 模块，以便创建一个连接 Skype for Business Online 的远程 Windows PowerShell 会话。 仅 64 位计算机支持此模块，可在 Microsoft 下载中心的 [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) 下载此模块。
出现提示时，请重启计算机。

如果需要了解详细信息，请参阅[在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。

### <a name="to-start-windows-powershell"></a>启动 Windows PowerShell

 **启动 Windows PowerShell 会话**

1. 从 **开始菜单** > **Windows PowerShell** 。

2. 在" **Windows PowerShell** "窗口中连接到 Office 365 组织，方法是通过运行：

    > [!NOTE]
    > 首次使用 Skype for Business Online Windows PowerShell 模块时只需运行 **Import-Module** 命令即可。

>
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

如果想要深入了解如何启动 Windows PowerShell，请参阅 [在单个 Windows PowerShell 窗口中连接所有 Office 365 服务](https://technet.microsoft.com/EN-US/library/dn568015.aspx) 或 [使用 Windows PowerShell 连接到 Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx) 。

### <a name="save-time-and-automate"></a>节省时间并自动给出

要通过自动执行此过程来节省时间，可以使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) 或 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet。

- 使用 [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet 更改特定用户的默认收费电话号码或免费电话号码。

  - 若要更改用户的默认免费电话号码，请运行：

  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   80045551234
  ```

- 使用 **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet 基于用户的原始默认电话号码或原始位置来更改其默认收费电话号码或免费电话号码。

    > [!NOTE]
    > 若要查找 BridgeID，请使用 **Get-CsOnlineDialInConferencingBridge** 。

  - 为所有没有默认免费电话号码的用户将默认免费电话号码设置为 8005551234，请运行：

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
    > 上面使用的位置信息需要与在 Office 365 管理中心中设置的用户联系人信息相匹配。

## <a name="about-windows-powershell"></a>有关 Windows PowerShell

可使用 Windows PowerShell 管理用户并管理他们能否执行的操作内容。 Windows PowerShell 可以通过能够简化日常工作的单点管理来帮助管理 Office 365 和 Skype for Business Online，尤其当有多个要执行的任务时。 若要开始使用 Windows PowerShell，请参阅下列主题：

  - [Windows PowerShell 和 Skype for Business Online 的介绍](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [为什么要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)

例如当你一次对多个用户更改设置时，Windows PowerShell 比起仅使用 Office 365 管理中心，在速度、简明性和效率方面具有许多优势。通过以下主题了解这些优势：

  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [使用 Windows PowerShell 管理 Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相关主题
[更改音频会议网桥的设置](change-the-settings-for-an-audio-conferencing-bridge.md)
