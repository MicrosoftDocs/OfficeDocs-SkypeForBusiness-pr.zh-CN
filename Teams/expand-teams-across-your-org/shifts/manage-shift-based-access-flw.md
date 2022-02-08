---
title: 管理工作电话中一线员工基于排班Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何管理组织中一线Teams基于班次的访问。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: d177ac362b7b8c0d1f91be5322fb49696a5cc9b7
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393484"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>管理工作电话中一线员工基于排班Teams
## <a name="overview"></a>概述

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

"Microsoft Teams状态"表示用户当前的可用性和其他用户的状态。 一线员工的存在通常不如其他员工预测，因为每天的工作时间通常不同。 作为管理员，您可以配置Teams为您的组织中的一线员工显示一组基于排班的显示状态，以指示他们何时上班和下班。

这些基于班次的显示状态&mdash;![Solid 绿色对号，表示"正在轮班"。](../../media/flw-presence-on-shift.png) **在 shift 时**，带 ![x 的灰色圆圈表示"关班"。](../../media/flw-presence-off-shift.png) **"关班**"![（实心红色圆圈&mdash;](../../media/flw-presence-busy.png)）表示"忙碌"与 [](../../presence-admins.md)"正在"状态的默认状态集Teams。 借助这两组状态，你可以根据用户的角色为组织成员配置不同的体验。

使用基于排班的访问，可以在一线Teams排班时管理对员工的访问权限。 例如，可以设置Teams以显示一条消息，即一线员工必须先确认，Teams排班时才能使用。  

## <a name="scenario"></a>使用场景

下面是组织如何管理基于班次的访问的示例。

您的组织中的一线员工只应支付其经理安排和批准的排班工时。 不应为在计划排班外工作的时间支付这些费用，包括使用 Teams 应用。 设置一条自定义消息，显示"Teams 非工作时间不计入应付时间"，当一线员工尝试在轮班时访问 Teams 时，会显示该消息。 如果他们选择使用Teams，则单击"我接受"，了解这一次不会付费。

您组织中还有一些具有薪金和不工作班次的信息工作者。 将信息工作者配置为使用默认状态Teams同时为一线员工提供基于班次的显示。

## <a name="shift-based-presence-states"></a>基于班次的状态

下面是基于班次的"状态"。

|应用配置 |用户配置  |更多信息  |
|---------|---------|---------|
|![实心绿色对号，表示"上移"。](../../media/flw-presence-on-shift.png) 轮班     |         |在班次开始时自动设置         |
|![带 x 的灰色圆圈，指示"关班"](../../media/flw-presence-off-shift.png) 非班次     |         |在班次结束时自动设置         |
|![实心红色圆圈，表示忙碌。](../../media/flw-presence-busy.png) 忙碌      | ![实心红色圆圈，表示忙碌](../../media/flw-presence-busy.png) 忙碌         |自动设置。 还可以在一线工作人员上班时手动设置。|

## <a name="off-shift-access-to-teams"></a>不轮班访问Teams

此功能允许管理在一线Teams员工排班时对员工的访问权限。 您可以设置Teams，在一线员工在轮班时访问Teams向一线员工显示消息。 一线员工必须 **单击"我接受**"才能确认消息，才能Teams。

您可以使用默认消息，从一组预定义邮件中选择，或自定义邮件以显示任何需要的文本。 下面是默认消息：

![默认消息的屏幕截图。](../../media/shifts-presence-message.png)

还可以设置显示消息的频率，并设置介于第一个轮班开始或最后一个轮班结束和限制对Teams之间的宽限期。

## <a name="manage-shift-based-access"></a>管理基于班次的访问

作为管理员，您可以使用策略来控制组织中一线员工基于排班的存在。 可以使用以下 PowerShell cmdlet 管理这些策略：

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

使用 New-CsTeamsShiftsPolicy cmdlet 创建新策略，设置想要的策略设置，然后使用 Grant-CsTeamsShiftsPolicy cmdlet 将策略分配给用户。

此处为一些示例。 有关每个策略设置和参数的详细信息，包括可以选择的预定义班次消息列表，请参阅 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-1"></a>示例 1

本示例创建名为 Off Shift 的新策略Teams访问默认消息。 在此策略中，基于班次的显示状态将打开，并且每当分配了此策略的用户在轮班时访问Teams会显示默认消息。 如果用户接受Teams，则用户可以在轮班时使用该模式，以及第一个班次开始或最后一个轮班结束到限制访问之间的宽限期为 10 分钟。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> 使用 **ShiftNoticeMessageType** 参数设置要显示的消息。 若要查看为此参数可以选择的预定义消息的列表，请参阅 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-2"></a>示例 2 

本示例创建名为 Off Shift 的新策略Teams Access 自定义消息。 在此策略中，每次分配此策略的用户在轮班时访问基于班次Teams显示自定义消息。 如果用户接受Teams，则用户可以在轮班时，以及第一个轮班开始或最后一个轮班结束到限制访问之间的宽限期为 15 分钟。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> 使用 **ShiftNoticeMessageType** 参数设置要显示的消息。 有关详细信息，请参阅 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-3"></a>示例 3

本示例创建名为 Off Shift 的新策略Teams Access Message1。 在此策略中，启用基于班次的显示状态，并且每次分配此策略的用户在轮班时访问Teams显示以下预定义消息。

  "您的雇主不会授权或批准非豁免或每小时员工在其非工作时间使用其网络、应用程序、系统或工具。 通过接受，即表示你确认Teams非授权且您将不获得补偿。" 

如果用户接受Teams，则用户可以在轮班时，以及第一个轮班开始或最后一个轮班结束到限制访问之间的宽限期为 3 分钟。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> 使用 **ShiftNoticeMessageType** 参数设置要显示的消息。 若要查看为此参数可以选择的预定义消息的列表，请参阅 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-4"></a>示例 4

本示例将名为 Off Shift 的策略Teams Access 自定义消息"分配给名为 remy@contoso.com。

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>相关主题

- [在 Teams 中为组织管理排班应用](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams PowerShell 概览](../../teams-powershell-overview.md)