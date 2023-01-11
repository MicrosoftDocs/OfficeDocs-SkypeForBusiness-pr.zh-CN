---
title: 使用 PowerShell 设置实时事件策略
author: MicrosoftHeidi
ms.author: heidip
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
description: 示例介绍如何使用 PowerShell 在 Teams 中设置策略，以控制谁可以在组织中举办实时事件，以及事件中可用的功能。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ef243860ea1450dcd5539d3d5b01025e7eac55cd
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767572"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>使用 PowerShell 在 Microsoft Teams 中设置实时事件策略

可以使用以下Windows PowerShell cmdlet 为 Teams 中的实时事件设置和分配策略设置：

- [Get-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/get-csteamsmeetingbroadcastpolicy)
- [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy)
- [New-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/new-csteamsmeetingbroadcastpolicy)
- [Grant-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy)
- [New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment)

下面是一些示例。

> [!NOTE]
> 必须先连接到 Skype for Business Online PowerShell，然后才能运行这些 cmdlet。 有关详细信息，请参阅[使用 Microsoft 365 管理 Skype for Business Online 或 Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

## <a name="allow-users-to-schedule-live-events"></a>允许用户安排实时事件

> [!NOTE]
> 这些示例适用于 Teams 中生成的事件。

### <a name="allow-a-user-to-schedule-live-events"></a>允许用户安排实时事件

如果用户已分配全局策略，请运行并验证 *AllowBroadcastScheduling* 参数是否设置为 *True*：

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```

然后将用户分配到全局策略，运行：

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>用户方案

#### <a name="you-want-all-users-in-your-organization-to-be-able-to-schedule-live-events"></a>你希望组织中的所有用户都能够安排实时事件

如果为用户分配了全局策略，请运行并验证 *AllowBroadcastScheduling* 是否设置为 *True*：

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```

如果为用户分配了全局策略以外的策略，请运行 并验证 *-AllowBroadcastScheduling* 是否设置为 *True*：

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

#### <a name="you-want-live-events-scheduling-to-be-disabled-across-your-organization"></a>你希望在整个组织中禁用实时事件计划

禁用实时事件计划，运行：

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```

将组织中的所有用户分配到全局策略，运行：

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

#### <a name="you-want-a-large-number-of-users-to-be-able-to-schedule-live-events-and-prevent-a-set-of-users-from-scheduling-them"></a>你希望大量用户能够计划实时事件，并阻止一组用户计划他们

运行并验证 *AllowBroadcastScheduling* 是否设置为 *True*：

```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```

然后将一个或多个用户分配到全局策略，运行：

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

然后将用户分配到此策略，运行：

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```

#### <a name="you-want-to-disable-live-event-scheduling-for-a-large-number-of-the-users-and-allow-a-set-of-users-to-schedule-them"></a>你想要为大量用户禁用实时事件计划，并允许一组用户安排他们

禁用实时事件计划，运行：

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```

然后将这些用户分配到全局策略，运行：

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

创建一个策略以允许实时事件计划，运行：

```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```

启用实时事件计划，运行：

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```

然后将用户分配到此策略，运行：

```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

## <a name="set-who-can-join-live-events"></a>设置谁可以加入实时事件

设置全局策略以允许用户创建每个人都（包括匿名用户）都可以参加和运行的活动：

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```

## <a name="set-the-recording-option-for-live-events"></a>设置实时事件的录制选项

> [!NOTE]
> 此设置仅适用于 Teams 中生成的事件。

设置全局策略以禁用实时事件的录制：

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```

## <a name="set-live-captions-and-subtitles-in-live-events"></a>在直播活动中设置实时字幕和字幕

> [!NOTE]
> 此设置仅适用于 Teams 中生成的事件。

设置全局策略以为活动与会者启用实时字幕和字幕 (听录) ：

```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>相关主题

- [设置 Teams 实时事件](set-up-for-teams-live-events.md)
- [Teams PowerShell 概览](../teams-powershell-overview.md)
