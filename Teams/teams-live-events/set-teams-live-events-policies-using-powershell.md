---
title: 使用 PowerShell 在 Microsoft Teams 中设置实时事件策略
author: chuckedmonson
ms.author: chucked
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 有关如何使用 PowerShell 设置团队中的策略以控制哪些人可以在你的组织中拥有实时事件以及他们创建的事件中可用的功能的示例
appliesto:
- Microsoft Teams
ms.openlocfilehash: d9f96adcf4aa40b93b89b99013b9bc5ca466c25b
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "37570164"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>使用 PowerShell 在 Microsoft Teams 中设置实时事件策略

你可以使用以下 Windows PowerShell cmdlet 为团队中的实时事件设置和分配策略设置： 
- [CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [Set-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [新-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [授权-CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

下面是一些示例。

## <a name="allow-users-to-schedule-live-events"></a>允许用户安排实时事件 

> [!NOTE]
> 这些示例适用于团队中生成的事件。 对于使用外部应用或设备生成的事件，必须执行其他步骤。 有关详细信息，请参阅[使用户能够计划使用外部应用或设备生成的事件](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)。

**允许用户安排实时事件**

如果向用户分配了全局策略，请运行并验证*AllowBroadcastScheduling*参数是否设置为*True*：
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
然后，将该用户分配给全局策略，运行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>用户方案
**希望组织中的所有用户都能够安排实时事件**

如果向用户分配了全局策略，请运行并验证*AllowBroadcastScheduling* * 是否设置为*True*：
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
如果向用户分配了全局策略之外的策略，请运行并验证 *-AllowBroadcastScheduling*是否设置为*True*：
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**你希望在你的组织中禁用实时事件计划**

禁用实时事件调度，运行：
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
将组织中的所有用户分配给全局策略，请运行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**您希望大量用户能够安排实时事件，并防止一组用户安排实时事件**

运行并验证*AllowBroadcastScheduling*是否设置为*True*：
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
然后，将一个或用户分配给全局策略，运行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

创建不允许安排实时事件的新策略，运行：
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
禁用实时事件调度，运行：
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
然后将用户分配给此策略，运行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**您希望为大量用户禁用实时事件调度，并允许一组用户安排它们**

禁用实时事件调度，运行：
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
然后将这些用户分配给全局策略，运行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
创建允许实时事件调度的策略，请运行：
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
启用实时事件调度，运行：
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
然后将用户分配给此策略，运行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>设置可以加入实时事件的人员
 
将全局策略设置为允许用户创建所有人（包括匿名用户）都可以出席的事件，请运行：
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>设置实时事件的录制选项
> [!NOTE]
> 此设置仅适用于团队中产生的事件。

将全局策略设置为禁用实时事件的录制：
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a>在实时事件中设置实时字幕和副标题
> [!NOTE]
> 此设置仅适用于团队中产生的事件。 

设置全局策略，为活动与会者打开实时字幕和副标题（脚本）：
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>相关主题
- [设置 Teams 实时事件](set-up-for-teams-live-events.md)


