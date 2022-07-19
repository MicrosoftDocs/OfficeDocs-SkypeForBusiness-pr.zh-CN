---
title: 使用 PowerShell 设置实时事件策略
author: mkbond007
ms.author: mabond
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: 示例说明如何使用 PowerShell 在 Teams 中设置策略，以控制谁可以在组织中保存实时事件以及事件中可用的功能。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e0d46c0675bd8b810f8dbce8585661184fbef74f
ms.sourcegitcommit: 791d0a341ff873145fa893ece05055729b0b8d50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2022
ms.locfileid: "66838837"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>使用 PowerShell 在 Microsoft Teams 中设置实时事件策略

可以使用以下Windows PowerShell cmdlet 为 Teams 中的实时事件设置和分配策略设置： 
- [Get-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

下面是一些示例。

> [!NOTE]
> 在运行这些 cmdlet 之前，必须连接到 Skype for Business Online PowerShell。 有关详细信息，请参阅[使用 Microsoft 365 或 Office 365 PowerShell 管理 Skype for Business Online](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

## <a name="allow-users-to-schedule-live-events"></a>允许用户计划直播活动 

> [!NOTE]
> 这些示例适用于 Teams 中生成的事件。 对于使用外部应用或设备生成的事件，必须执行其他步骤。 有关详细信息，请参阅 [“让用户计划使用外部应用或设备生成的事件](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)”。

**允许用户计划实时事件**

如果为用户分配了全局策略，请运行并验证 *AllowBroadcastScheduling* 参数是否设置为 *True*：
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
然后，将用户分配到全局策略，运行：
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>用户方案
**你希望组织中的所有用户都能够计划直播活动**

如果为用户分配了全局策略，请运行并验证 *AllowBroadcastScheduling* *是否设置为 *True*：
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
如果为用户分配了除全局策略以外的策略，请运行并验证 *-AllowBroadcastScheduling* 是否设置为 *True*：
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**你希望在整个组织中禁用直播活动计划**

禁用直播活动计划，运行：
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
将组织中的所有用户分配到全局策略，运行：
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**你希望大量用户能够计划实时事件，并阻止一组用户计划活动**

运行并验证 *AllowBroadcastScheduling* 是否设置为 *True*：
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
然后，将用户或用户分配到全局策略，运行：
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

创建不允许安排实时事件的新策略，运行：
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
禁用直播活动计划，运行：
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
然后将用户分配到此策略，运行：
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**你希望为大量用户禁用实时事件计划，并允许一组用户计划活动计划**

禁用直播活动计划，运行：
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
然后将这些用户分配到全局策略，运行：
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
创建策略以允许实时事件计划、运行：
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
启用直播活动计划，运行：
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
然后将用户分配到此策略，运行：
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>设置谁可以加入直播活动
 
设置全局策略以允许用户创建每个人都可以参加、运行的事件，包括匿名用户：
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>设置实时事件的录制选项
> [!NOTE]
> 此设置仅适用于 Teams 中生成的事件。

将全局策略设置为禁用实时事件的录制：
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>在直播活动中设置实时字幕和副标题
> [!NOTE]
> 此设置仅适用于 Teams 中生成的事件。 

将全局策略设置为为活动与会者打开实时字幕和字幕 (听录) ：
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>相关主题
- [设置 Teams 实时事件](set-up-for-teams-live-events.md)
- [Teams PowerShell 概览](../teams-powershell-overview.md)