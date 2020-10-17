---
title: 为团队中的一线工作者管理基于班次的访问
author: LanaChin
ms.author: v-lanac
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在组织中管理一线工作人员的团队中的基于班次的访问权限。
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ec470422e402da07171bef627d1592c73d6c12f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514129"
---
# <a name="manage-shift-based-access-for-firstline-workers-in-teams"></a>为团队中的一线工作者管理基于班次的访问

> [!IMPORTANT]
> 2020年6月30日生效，Microsoft StaffHub 已停用。 我们正在将 StaffHub 功能构建到 Microsoft 团队中。 今天，团队包括 "倒班" 应用，用于计划管理，而其他功能将随着时间的推移而推出。 StaffHub 已停止为2020年6月30日的所有用户工作。 任何试图打开 StaffHub 的人都将显示一条消息，指导他们下载团队。 若要了解详细信息，请参阅 [Microsoft StaffHub 已停](microsoft-staffhub-to-be-retired.md)用。  

## <a name="overview"></a>概述

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft 团队中的状态表示用户的当前可用性和其他用户的状态。 与其他职员相比，一线工作人员的状态通常不会比其他职员更容易预测，因为它们的工作时间通常不是同一天。 作为管理员，你可以将团队配置为显示组织中的一线工作人员的一组基于班次的状态，以指示它们何时处于 "开" 和 "关" 班次。

这些基于转换的状态显示 " &mdash; ![ 纯绿色复选标记"，指示 "shift on shift" （ ](../../media/flw-presence-on-shift.png) **On shift** ![ x 的灰色圆圈）指示 "移 ](../../media/flw-presence-off-shift.png) **出**Shift" （ ![ 纯红色圆圈）表示 "忙碌"，表示 "忙碌" ](../../media/flw-presence-busy.png) **Busy** &mdash; 。 [default set of presence states](../../presence-admins.md) 通过这两组状态状态，您可以根据自己的角色为组织中的人员配置不同的体验。

使用基于班次的访问，您可以在一线工作人员停止班次时管理团队的访问权限。 例如，您可以将团队设置为显示一条消息，一线工作人员必须在他们使用团队而不是计划班次时才可以使用它们。  

## <a name="scenario"></a>使用场景

下面是组织如何管理基于班次的访问的示例。

您的组织中有一线工作人员，仅应在其经理计划和批准的倒班上支付。 不应在计划班次之外工作所花费的时间进行支付，包括使用团队应用。 您设置了一个自定义消息，显示 "当下班后的时间超出" 班次不计为应付帐款时间 "，当一线工作人员尝试在停止班次时访问团队时，将显示该时间。 如果他们选择使用团队，他们单击 " **我接受** " 即表示不会支付这些团队。

您的组织中还包含 salaried 的信息工作者和不起作用的人员。 将您的信息工作者配置为使用团队中的默认状态，同时为一线工作人员提供基于班次的状态。

## <a name="shift-based-presence-states"></a>基于班次的状态

下面是基于班次的状态。

|应用配置 |用户配置  |更多信息  |
|---------|---------|---------|
|![稳定绿色复选标记，指示在班次上](../../media/flw-presence-on-shift.png) 在班次上     |         |在班次开始时自动设置         |
|![X 的灰色圆圈表示离开班次](../../media/flw-presence-off-shift.png) 离开班次     |         |在班次结束时自动设置         |
|![实心红色圆圈，表示忙碌](../../media/flw-presence-busy.png) 忙碌      | ![实心红色圆圈，表示忙碌](../../media/flw-presence-busy.png) 忙碌         |自动设置。 当一线工作者在班次上时，也可以手动设置。|

## <a name="off-shift-access-to-teams"></a>关闭对团队的班次访问

此功能可让你在一线工作人员停止班次时管理团队的访问权限。 你可以将团队设置为向一线工作人员显示一条消息，前提是他们在关闭班次时访问团队。 一线工作人员必须单击 " **我接受** " 才能使用团队确认消息。

可以使用默认消息、从一组预定义的消息中进行选择，或自定义消息以显示所需的任何文本。 下面是默认消息：

![默认邮件的屏幕截图](../../media/shifts-presence-message.png)

你还可以在显示消息时设置频率，并设置在第一次班次开始或上一班次结束以及团队访问受限时的宽限期。

## <a name="manage-shift-based-access"></a>管理基于班次的访问

作为管理员，你可以使用策略控制组织中的一线工作人员的基于班次的状态。 你可以使用以下 PowerShell cmdlet 管理这些策略：

- [新-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [授权-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

使用 New-CsTeamsShiftsPolicy cmdlet 创建新策略，设置所需的策略设置，然后使用 Grant-CsTeamsShiftsPolicy cmdlet 将策略分配给用户。

下面是一些示例。 有关每个策略设置和参数的详细信息，包括可从中进行选择的预定义关闭班次消息的列表，请参阅 [CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-1"></a>示例 1

在此示例中，我们创建一个名为 "关闭班次团队" 的新策略，并访问默认消息。 在此策略中，打开基于移动的状态，并且每次分配了此策略的用户在关闭班次时都将显示默认消息。 用户在接受消息时可以使用团队，并且在第一次班次开始或上一班次结束时和访问受限时间之间的宽限期是10分钟。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> 使用 **ShiftNoticeMessageType** 参数设置要显示的消息。 若要查看可供此参数选择的预定义消息的列表，请参阅 [CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-2"></a>示例 2 

在此示例中，我们创建一个名为 "关闭倒班团队" 的新策略，访问自定义消息。 在此策略中，打开基于移动的状态，并且每次分配了此策略的用户在关闭班次时都将显示自定义消息。 用户在接受消息时可以使用团队，如果他们接受消息，则可以使用团队，在第一次班次开始或上一班次结束时和访问受限时间之间的宽限期是15分钟。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> 使用 **ShiftNoticeMessageType** 参数设置要显示的消息。 若要了解详细信息，请参阅 [CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-3"></a>示例 3

在此示例中，我们创建名为 "关闭倒班团队访问 Message1" 的新策略。 在此策略中，将打开基于移动的状态，并且每次分配了此策略的用户在关闭班次时都将显示以下预定义消息。

  "在非工作时间内，您的雇主不会授权或批准通过非豁免或每小时员工使用其网络、应用程序、系统或工具。 通过接受，您确认您在非授权的情况下使用团队，并且不会获得报酬。 

用户在接受消息时可以使用团队，如果他们接受消息，则可以使用团队，在第一次班次开始或上一班次结束时和访问受限时间之间的宽限期为3分钟。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> 使用 **ShiftNoticeMessageType** 参数设置要显示的消息。 若要查看可供此参数选择的预定义消息的列表，请参阅 [CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-4"></a>示例 4

在此示例中，我们将名为 "注销班次团队" 的策略分配给名为 remy@contoso.com 的用户的自定义消息。

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>相关主题

- [在 Teams 中为组织管理排班应用](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams PowerShell 概览](../../teams-powershell-overview.md)
