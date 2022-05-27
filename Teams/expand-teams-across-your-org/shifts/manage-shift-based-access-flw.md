---
title: 管理Teams中一线工人的基于轮班的访问权限
author: SerdarSoysal
ms.author: serdars
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何管理组织中一线工作者Teams中基于班次的访问权限。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9cb488dfb95647079b51269059ee5c0b120cb9cc
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675214"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>管理Teams中一线工人的基于轮班的访问权限
## <a name="overview"></a>概述

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft Teams中的状态向其他用户指示用户的当前可用性和状态。 一线工人的存在往往比其他工作人员更难以预测，因为他们的工作时间通常不是每天相同的。 作为管理员，你可以将Teams配置为显示一组基于班次的状态，供组织中的一线工作人员指示他们何时上下班。

这些基于班次的状态表示&mdash;![纯绿色复选标记，指示“轮班”。](../../media/flw-presence-on-shift.png) **轮班时**， ![带有 x 的灰色圆圈指示“脱班”。](../../media/flw-presence-off-shift.png) **脱班**，![纯红色圆圈，指示 **忙碌**&mdash;](../../media/flw-presence-busy.png)与Teams中的 [默认状态集](../../presence-admins.md)分开。 使用这两组状态，可以根据组织中人员的角色为其配置不同的体验。

使用基于轮班的访问权限，可以在一线工作人员轮班时管理对Teams的访问。 例如，可以将Teams设置为显示一条消息，一线工作人员必须先确认该消息，然后才能在未按计划轮班时使用Teams。  

## <a name="scenario"></a>使用场景

下面是组织如何管理基于班次的访问权限的示例。

你的组织中有一线工作人员，他们只应在经理安排和批准的轮班上工作数小时。 不应为在计划班次之外工作的时间（包括使用Teams应用）付费。 你设置了一条自定义消息，显示“轮班时Teams时间不计入应付费时间”，当一线工作人员尝试在下班时访问Teams时，会显示该消息。 如果他们选择使用Teams，他们单击 **我接受** 的理解，他们不会支付这一次。

组织中还有受薪、不轮班工作的信息工作者。 将信息工作者配置为使用Teams中的默认状态，同时为一线工作人员提供基于轮班的状态。

## <a name="shift-based-presence-states"></a>基于班次的状态

下面是基于班次的状态。

|应用配置 |用户配置  |更多信息  |
|---------|---------|---------|
|![纯绿色复选标记，指示启用班次。](../../media/flw-presence-on-shift.png) 轮班时     |         |在班次开始时自动设置         |
|![带有 x 的灰色圆圈，指示关闭班次](../../media/flw-presence-off-shift.png) 关闭班次     |         |在班次结束时自动设置         |
|![实心红色圆圈，表示忙碌。](../../media/flw-presence-busy.png) 忙碌      | ![实心红色圆圈，表示忙碌](../../media/flw-presence-busy.png) 忙碌         |自动设置。 也可以在一线工作人员轮班时手动设置。|

## <a name="off-shift-access-to-teams"></a>离班访问Teams

使用此功能，可在一线工作人员轮班时管理对Teams的访问权限。 如果一线工作人员在下班时访问Teams，则可以设置Teams以向他们显示一条消息。 一线工作人员必须单击 **“我接受**”以确认消息，然后才能使用Teams。

可以使用默认消息、从一组预定义的消息中进行选择，或自定义消息以显示所需的任何文本。 默认消息如下：

![默认消息的屏幕截图。](../../media/shifts-presence-message.png)

还可以设置显示消息的频率，并设置从第一个班次开始或最后一个班次结束到限制对Teams的访问之间的宽限期。

## <a name="manage-shift-based-access"></a>管理基于班次的访问

作为管理员，可以使用策略来控制组织中一线员工基于班次的存在。 使用以下 PowerShell cmdlet 管理这些策略：

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

使用New-CsTeamsShiftsPolicy cmdlet 创建新策略、设置所需的策略设置，然后使用Grant-CsTeamsShiftsPolicy cmdlet 将策略分配给用户。

此处为一些示例。 有关每个策略设置和参数的详细信息，包括可从中选择的预定义的脱班消息列表，请参阅 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-1"></a>示例 1

在此示例中，我们将创建名为“关闭班次”的新策略Teams访问默认消息。 在此策略中，将启用基于班次的状态，并且每次分配此策略的用户在停班时访问Teams时都会显示默认消息。 如果用户接受消息，则用户可以在脱班时使用Teams;第一个班次开始或最后一班结束以及访问受限时间为 10 分钟之间的宽限期。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> 使用 **ShiftNoticeMessageType** 参数设置要显示的消息。 若要查看可为此参数选择的预定义消息的列表，请参阅 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-2"></a>示例 2 

在此示例中，我们将创建名为“关闭班次”的新策略Teams访问自定义消息。 在此策略中，将启用基于班次的状态，并且每次分配此策略的用户在停班时访问Teams时都会显示自定义消息。 如果用户接受消息，则用户可以在脱班时使用Teams;第一个班次开始或最后一班结束以及限制访问时间为 15 分钟之间的宽限期。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> 使用 **ShiftNoticeMessageType** 参数设置要显示的消息。 若要了解详细信息，请参阅 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-3"></a>示例 3

在此示例中，我们将创建名为“关闭班次”的新策略Teams访问消息 1。 在此策略中，将打开基于班次的状态，并且每次分配此策略的用户在轮班时访问Teams时，都会显示以下预定义消息。

  “你的雇主不授权或批准非豁免或每小时员工在其非工作时间使用其网络、应用程序、系统或工具。 通过接受，你确认在轮班期间使用Teams未获得授权，你将不会得到补偿。 

如果用户接受消息，则用户可以在脱班时使用Teams;第一个班次开始或最后一个班次结束和限制访问时间之间的宽限期为 3 分钟。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> 使用 **ShiftNoticeMessageType** 参数设置要显示的消息。 若要查看可为此参数选择的预定义消息的列表，请参阅 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-4"></a>示例 4

在此示例中，我们将名为 Off Shift Teams访问自定义消息的策略分配给名为 remy@contoso.com 的用户。

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>相关主题

- [在 Teams 中为组织管理排班应用](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams PowerShell 概览](../../teams-powershell-overview.md)