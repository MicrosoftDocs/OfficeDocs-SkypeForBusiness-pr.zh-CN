---
title: 使用 PowerShell 在 Microsoft Teams 中设置实时事件策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 有关如何使用 PowerShell 团队以控制谁可以保留在您的组织和功能的实时事件的设置策略的示例有他们创建的事件
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8858b8572a06aede2fa1de98ce9cfc14ed1745bd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204567"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a>使用 PowerShell 在 Microsoft Teams 中设置实时事件策略

可以使用以下 Windows PowerShell cmdlet 设置并分配的工作组中的实时事件的策略设置： 
- [Get CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [设置 CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [新 CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [授予 CsTeamsMeetingBroadcastPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

下面是一些示例。

## <a name="allow-users-to-schedule-live-events"></a>允许用户安排 live 事件 

> [!NOTE]
> 这些示例供快速入门事件。 对于外部编码器事件，其他一些的步骤，您必须执行。 有关详细信息，请参阅[使用户能够安排外部编码器事件](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events)。

**允许用户安排 live 事件**

如果该用户分配全局策略，则运行，并验证*AllowBroadcastScheduling*参数设置为*True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
然后将该用户分配到全局策略中，运行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a>用户方案
**您希望组织能够安排 live 事件中的所有用户**

如果用户分配全局策略，运行并验证该*AllowBroadcastScheduling* * 设置为*True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
如果用户分配全局策略之外的策略，则运行，并验证 *-AllowBroadcastScheduling*设置为*True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
**要安排要禁用整个组织的 live 事件**

禁用 live 事件计划，请运行：
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
组织中的所有用户都分配全局策略，运行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**您希望大量用户能够安排 live 事件和安排它们阻止用户组**

运行并验证*AllowBroadcastScheduling*设置为*True*:
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
然后将一个用户分配给全局策略，运行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

创建一个新的策略，不允许安排 live 事件，运行：
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
禁用 live 事件计划，请运行：
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
然后将用户分配给此策略，请运行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
**您想要禁用的大量用户安排 live 事件并允许用户安排一组**

禁用 live 事件计划，请运行：
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
然后将这些用户分配全局策略，运行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
创建策略，以允许安排 live 事件、 运行：
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
启用 live 事件日程安排，运行：
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
然后将用户分配给此策略，请运行：
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a>设置可以加入 live 事件
 
设置全局策略以允许用户创建事件的任何人，包括匿名用户可以参加、 运行：
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a>设置的实时事件录音选项
> [!NOTE]
> 此设置只应用于快速入门事件。

设置要禁用的实时事件记录的全局策略：
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-transcription-and-translation-in-live-events-coming-soon"></a>在 live 事件 （即将推出） 中设置转录和翻译
> [!NOTE]
> 此设置只应用于快速入门事件。 

设置全局策略以启用转录和转换为事件与会者：
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a>相关主题
- [设置 Teams 实时事件](set-up-for-teams-live-events.md)


