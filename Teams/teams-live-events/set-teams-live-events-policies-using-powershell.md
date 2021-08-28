---
title: 使用 PowerShell 设置实时事件策略
author: cichur
ms.author: v-cichur
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
description: 如何使用 PowerShell 在 Teams 中设置策略以控制哪些人可以在组织中保存实时事件以及事件可用功能的示例。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dd408ab17d91a826b0d85a6c2515e8f21013242a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58629174"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>使用 PowerShell 在 Microsoft Teams 中设置实时事件策略

可以使用以下 cmdlet Windows PowerShell为实时事件设置和分配策略Teams： 
- [Get-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Grant-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

下面是一些示例。

> [!NOTE]
> 在运行这些 cmdlet 之前，必须连接到 Skype for Business PowerShell。 有关详细信息，请参阅使用[powerShell Skype for Business管理 Microsoft 365 Office 365 Online。](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

## <a name="allow-users-to-schedule-live-events"></a>允许用户计划实时事件 

> [!NOTE]
> 这些示例适用于在 Teams 中生成的事件。 对于使用外部应用或设备生成的事件，必须执行其他步骤。 有关详细信息，请参阅 [允许用户计划使用外部应用或设备生成的事件](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)。

**允许用户计划实时事件**

如果为用户分配了全局策略，请运行 并验证 *AllowBroadcastScheduling* 参数是否设置为 *True：*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
然后将用户分配到全局策略，运行：
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>用户方案
**希望组织中的所有用户能够安排实时事件**

如果为用户分配了全局策略，请运行 并验证 *AllowBroadcastScheduling* *是否设置为 *True：*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
如果为用户分配了全局策略外的策略，请运行 并验证 *-AllowBroadcastScheduling* 是否设置为 *True：*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**您希望在整个组织中禁用实时事件计划**

禁用实时事件计划，运行：
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
将组织中所有用户分配到全局策略，请运行：
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**您希望大量用户能够计划实时事件，并防止一组用户计划这些事件**

运行 并验证 *AllowBroadcastScheduling* 是否设置为 *True：*
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
然后将用户分配到全局策略，运行：
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

创建不允许计划实时事件的新策略，请运行：
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
禁用实时事件计划，运行：
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
然后，将用户分配到此策略，运行：
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**希望为大量用户禁用实时事件计划，并允许一组用户安排它们**

禁用实时事件计划，运行：
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
然后将这些用户分配到全局策略，运行：
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
创建一个策略以允许实时事件计划，请运行：
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
启用实时事件计划，运行：
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
然后，将用户分配到此策略，运行：
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>设置谁可以加入实时事件
 
设置全局策略以允许用户创建每个人（包括匿名用户）都可以参与、运行的事件：
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>设置实时事件的录制选项
> [!NOTE]
> 此设置仅适用于在 Teams 中生成的事件。

设置全局策略以禁用实时事件的录制：
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>在实时活动中设置实时字幕和字幕
> [!NOTE]
> 此设置仅适用于在 Teams 中生成的事件。 

设置全局策略，为活动与会者启用实时 (字幕) 字幕：
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>相关主题
- [设置 Teams 直播活动](set-up-for-teams-live-events.md)
- [Teams PowerShell 概览](../teams-powershell-overview.md)