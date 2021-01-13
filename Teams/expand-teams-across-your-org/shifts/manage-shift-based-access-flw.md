---
title: 在 Teams 中管理一线员工基于班次的访问
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在 Teams 中管理组织中一线员工基于班次的访问。
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b73fe9b3c4b39e7d3fa7b31427f563c47e5a737
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823012"
---
# <a name="manage-shift-based-access-for-firstline-workers-in-teams"></a>在 Teams 中管理一线员工基于班次的访问

> [!IMPORTANT]
> 自 2020 年 6 月 30 起，Microsoft StaffHub 已停用。 我们正在将 StaffHub 功能构建到 Microsoft Teams 中。 目前，Teams 包含用于计划管理的 Shifts 应用，其他功能将随着时间的推移而推出。 StaffHub 于 2020 年 6 月 30 日停止为所有用户工作。 尝试打开 StaffHub 的任何人都会显示一条消息，指示他们下载 Teams。 有关详细信息，请参阅 [Microsoft StaffHub 已停用](microsoft-staffhub-to-be-retired.md)。  

## <a name="overview"></a>概述

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft Teams 中的状态向其他用户指示用户的当前可用性和状态。 一线员工的存在通常不如其他员工预测，因为每天的工作时间通常不同。 作为管理员，你可以将 Teams 配置为为组织中一线员工显示一组基于班次的显示状态，以指示他们何时上班和下班。

这些基于班次的显示状态为纯绿色对号，表示"上班"，灰色圆圈表示 &mdash; ![ ](../../media/flw-presence-on-shift.png)  ![ x，表示 ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; [](../../presence-admins.md)"关班"，红色实心圆圈表示"忙碌"与 Teams 中的默认状态集分开。 通过这两组状态，你可以根据用户的角色为组织中人员配置不同的体验。

使用基于班次的访问，可以在一线员工轮班时管理对 Teams 的访问权限。 例如，可以将 Teams 设置为显示一条消息，一线员工必须先确认消息，然后他们才能在未安排班次时使用 Teams。  

## <a name="scenario"></a>使用场景

下面是组织如何管理基于班次的访问的示例。

您的组织中的一线员工应仅为其经理安排和批准的排班工作小时数付费。 不应为在计划排班（包括使用 Teams 应用）外工作的时间付费。 你设置了一条自定义消息，显示"你在 Teams 上轮班的时间不计入应付时间"，当一线员工在轮班时尝试访问 Teams 时，会显示此消息。 如果他们选择使用 Teams，他们单击" **我** 接受"，了解这一次不会付费。

您的组织中还有一些信息工作者，这些员工是工资工，不工作轮班。 将信息工作者配置为使用 Teams 中的默认状态，同时提供一线员工基于班次的显示。

## <a name="shift-based-presence-states"></a>基于班次的状态

下面是基于班次的状态。

|应用配置 |用户配置  |更多信息  |
|---------|---------|---------|
|![实心绿色对号，表示正在轮班](../../media/flw-presence-on-shift.png) 轮班     |         |在班次开始时自动设置         |
|![带 x 的灰色圆圈，指示"关"shift](../../media/flw-presence-off-shift.png) 关班     |         |在轮班结束时自动设置         |
|![实心红色圆圈，表示忙碌](../../media/flw-presence-busy.png) 忙碌      | ![实心红色圆圈，表示忙碌](../../media/flw-presence-busy.png) 忙碌         |自动设置。 还可以在一线员工上班时手动设置。|

## <a name="off-shift-access-to-teams"></a>不轮班访问 Teams

此功能允许你在一线员工上班时管理对 Teams 的访问权限。 如果一线员工在轮班时访问 Teams，可以将 Teams 设置为显示一条消息。 一线员工必须 **单击"我接受** "才能确认消息，才能使用 Teams。

可以使用默认消息、从一组预定义邮件中选择，或自定义邮件以显示任何需要的文本。 下面是默认消息：

![默认消息的屏幕截图](../../media/shifts-presence-message.png)

还可以设置显示消息的频率，并设置第一个班次开始或最后一个轮班结束与限制 Teams 访问之间的宽限期。

## <a name="manage-shift-based-access"></a>管理基于班次的访问

作为管理员，您可以使用策略来控制组织中一线员工基于班次的存在。 可以使用以下 PowerShell cmdlet 管理这些策略：

- [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

使用 New-CsTeamsShiftsPolicy cmdlet 创建新策略，设置想要的策略设置，然后使用 Grant-CsTeamsShiftsPolicy cmdlet 将策略分配给用户。

下面是一些示例。 有关每个策略设置和参数的详细信息（包括可供选择的预定义轮班消息列表）的信息，请参阅[New-CsTeamsShiftsPolicy。](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-1"></a>示例 1

本示例创建一个名为 Off Shift Teams Access 默认消息的新策略。 在此策略中，基于班次的显示状态将打开，每次分配此策略的用户在轮班时访问 Teams 时，都会显示默认消息。 如果接受消息，用户可以在轮班时使用 Teams，第一个班次开始或最后一个轮班结束与限制访问之间的宽限期为 10 分钟。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> 使用 **ShiftNoticeMessageType** 参数设置要显示的消息。 若要查看可用于此参数的预定义消息的列表，请参阅[New-CsTeamsShiftsPolicy。](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-2"></a>示例 2 

本示例创建一个名为 Off Shift Teams Access 自定义消息的新策略。 在此策略中，每次分配此策略的用户在轮班时访问 Teams 时，都会打开基于班次的显示状态并显示自定义消息。 如果接受消息，用户可以在轮班时使用 Teams，第一个班次开始或最后一个轮班结束与限制访问之间的宽限期为 15 分钟。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> 使用 **ShiftNoticeMessageType** 参数设置要显示的消息。 若要了解有关详细信息，请参阅[New-CsTeamsShiftsPolicy。](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-3"></a>示例 3

本示例创建名为 Off Shift Teams Access Message1 的新策略。 在此策略中，每次分配此策略的用户在轮班时访问 Teams 时，都会打开基于班次的显示状态，并显示以下预定义消息。

  "您的雇主不会授权或批准非豁免或每小时员工在其非工作时间使用其网络、应用程序、系统或工具。 接受后，即表示你确认在非班次期间使用 Teams 未授权，并且你将不会获得补偿。" 

如果接受消息，用户可以在轮班时使用 Teams，第一个班次开始或最后一个轮班结束与限制访问之间的宽限期为 3 分钟。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> 使用 **ShiftNoticeMessageType** 参数设置要显示的消息。 若要查看可用于此参数的预定义消息的列表，请参阅[New-CsTeamsShiftsPolicy。](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-4"></a>示例 4

本示例将名为 Off Shift Teams Access 自定义消息的策略分配给名为 remy@contoso.com。

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>相关主题

- [在 Teams 中为组织管理排班应用](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams PowerShell 概览](../../teams-powershell-overview.md)
