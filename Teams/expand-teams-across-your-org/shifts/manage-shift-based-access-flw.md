---
title: 管理工作电话中一线员工基于排班Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何管理组织中一线Teams中的基于排班的访问。
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: c69f5678b2a3884f52dd3dc676fce21e2ee67f4f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092540"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>管理工作电话中一线员工基于排班Teams

> [!IMPORTANT]
> 从 2020 年 6 月 30 开始，Microsoft StaffHub 已停用。 我们正在将 StaffHub 功能构建到 Microsoft Teams。 如今，Teams 包含用于日程安排管理的“班次”应用，并且随着时间推移将推出其他功能。 StaffHub 于 2020 年 6 月 30 日停止为所有用户工作。 尝试打开 StaffHub 的任何用户都会看到一则提示其下载 Teams 的消息。 若要了解详细信息，请参阅 [Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。  

## <a name="overview"></a>概述

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

"Microsoft Teams状态"表示用户当前的可用性和其他用户的状态。 一线员工的存在通常不如其他员工预测，因为每天的工作时间通常不同。 作为管理员，您可以配置Teams为您的组织中的一线员工显示一组基于排班的显示状态，以指示其何时上班和下班。

这些基于班次的显示状态实心绿色对号，表示"上移时"，灰色圆圈带 x，表示"关班""关班 &mdash; ![ ](../../media/flw-presence-on-shift.png)  ![ ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; "，"实心红圈"，[](../../presence-admins.md)表示"忙碌"与 Teams 中的默认状态集分开。 通过这两组状态，你可以根据用户的角色为组织成员配置不同的体验。

使用基于班次的访问，可以在一线员工Teams，管理对非班次的访问。 例如，可以将"Teams设置为显示一条消息，即"第一线工作人员必须确认"，Teams排班时才能使用电话。  

## <a name="scenario"></a>使用场景

下面是组织如何管理基于班次的访问的示例。

您的组织中的一线员工只应支付其经理安排和批准的排班工时。 不应为在计划排班外工作的时间支付这些费用，包括使用 Teams 应用。 您设置了一条自定义消息，显示"当您在 Teams 上排班的时间不计入应付时间"，当一线员工尝试在轮班时访问 Teams 时，会显示该消息。 如果他们选择使用Teams，他们单击"我接受"，了解这一次不会付费。

您组织中还有一些具有薪金和不工作班次的信息工作者。 将信息工作者配置为使用默认状态Teams为一线员工提供基于班次的显示。

## <a name="shift-based-presence-states"></a>基于班次的状态

下面是基于班次的"状态"。

|应用配置 |用户配置  |更多信息  |
|---------|---------|---------|
|![实心绿色对号，指示"正在上移"](../../media/flw-presence-on-shift.png) 轮班     |         |在班次开始时自动设置         |
|![带 x 的灰色圆圈，指示"关班"](../../media/flw-presence-off-shift.png) 非班次     |         |在班次结束时自动设置         |
|![实心红色圆圈，表示忙碌](../../media/flw-presence-busy.png) 忙碌      | ![实心红色圆圈，表示忙碌](../../media/flw-presence-busy.png) 忙碌         |自动设置。 还可以在前线工作人员上班时手动设置。|

## <a name="off-shift-access-to-teams"></a>不轮班访问Teams

此功能允许管理在一线Teams非班次时对员工的访问权限。 可以设置Teams，以在"第一线员工"在轮Teams时向"一线员工"显示消息。 一线员工必须 **单击"我接受**"才能确认消息，然后才能Teams。

您可以使用默认消息，从一组预定义邮件中选择，或自定义邮件以显示任何需要的文本。 下面是默认消息：

![默认消息的屏幕截图](../../media/shifts-presence-message.png)

还可以设置显示消息的频率，并设置介于第一个班次开始或最后一个轮班结束和限制对Teams之间的宽限期。

## <a name="manage-shift-based-access"></a>管理基于班次的访问

作为管理员，可以使用策略来控制组织中一线员工基于排班的存在。 可以使用以下 PowerShell cmdlet 管理这些策略：

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

使用 New-CsTeamsShiftsPolicy cmdlet 创建新策略，设置想要的策略设置，然后使用 Grant-CsTeamsShiftsPolicy cmdlet 将策略分配给用户。

此处为一些示例。 有关每个策略设置和参数的详细信息，包括可以选择的预定义班次消息列表，请参阅[New-CsTeamsShiftsPolicy。](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-1"></a>示例 1

本示例创建名为 Off Shift 的新策略Teams访问默认消息。 在此策略中，基于班次的显示状态将打开，并且每当分配了此策略的用户在轮班时访问Teams会显示默认消息。 如果用户接受Teams，则用户可以在轮班时使用此模式，以及第一个轮班开始或最后一个班次结束之间的宽限期，以及限制访问的 10 分钟。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> 使用 **ShiftNoticeMessageType** 参数设置要显示的消息。 若要查看为此参数可以选择的预定义消息列表，请参阅[New-CsTeamsShiftsPolicy。](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-2"></a>示例 2 

本示例创建名为 Off Shift 的新策略Teams Access 自定义消息。 在此策略中，启用基于班次的显示状态，每次分配此策略的用户在轮班时访问Teams显示自定义消息。 如果用户接受Teams，则用户可以在轮班时使用通知，以及第一个轮班开始或最后一个轮班结束之间的宽限期，以及限制访问的 15 分钟。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> 使用 **ShiftNoticeMessageType** 参数设置要显示的消息。 有关详细信息，请参阅[New-CsTeamsShiftsPolicy。](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-3"></a>示例 3

本示例创建名为 Off Shift 的新策略Teams Access Message1。 在此策略中，启用基于班次的显示状态，并且每次分配此策略的用户在轮班时访问Teams显示以下预定义消息。

  "您的雇主不会授权或批准非豁免或每小时员工在其非工作时间使用其网络、应用程序、系统或工具。 通过接受，即表示你确认在Teams轮班期间使用公司，并且您将不获得补偿。" 

如果用户接受Teams，则用户可以在轮班时，以及第一个轮班开始或最后一个轮班结束到限制访问之间的宽限期为 3 分钟。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> 使用 **ShiftNoticeMessageType** 参数设置要显示的消息。 若要查看为此参数可以选择的预定义消息列表，请参阅[New-CsTeamsShiftsPolicy。](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-4"></a>示例 4

本示例将名为 Off Shift Teams Access 自定义消息的策略分配给名为 remy@contoso.com。

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>相关主题

- [在 Teams 中为组织管理排班应用](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams PowerShell 概览](../../teams-powershell-overview.md)