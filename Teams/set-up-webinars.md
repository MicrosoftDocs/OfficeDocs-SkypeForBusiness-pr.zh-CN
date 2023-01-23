---
title: 设置网络研讨会
ms.author: mabond
author: mkbond007
manager: serdars
ms.reviewer: sachung, emryan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
description: 了解如何在 Teams 中管理网络研讨会和会议注册策略。
ms.openlocfilehash: 097f4c385261ba1aea96990751d208b99d4d8b93
ms.sourcegitcommit: 5e0900ed7a21ed4e854cc00dbfb4ae4ff2372262
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2023
ms.locfileid: "69950429"
---
# <a name="set-up-webinars-in-microsoft-teams"></a>在 Microsoft Teams 中设置网络研讨会

> [!NOTE]
> 本文介绍网络研讨会中的一些预览版功能，需要Teams 高级版许可证。

Microsoft 现在提供新的网络研讨会体验;本文介绍如何更新设置以使用这些功能。

如果计划使用网络研讨会，建议使用新的网络研讨会体验。

会议注册包括基本的网络研讨会功能、要求注册会议的功能以及出席情况报告。 通过启用新的网络研讨会体验，你可以使用会议注册和许多新的网络研讨会功能，例如：

- 网络研讨会的专用活动和注册页
- 共同组织者
- 事件页上的演示者 bios
- 注册状态概述和管理

在 [Teams 网络研讨会入门](https://support.microsoft.com/office/42f3f874-22dc-4289-b53f-bbc1a69013e3)中详细了解最终用户可用的新功能。

如果组织启用了会议注册，则所有新创建的网络研讨会都将获得新体验。 以前安排的网络研讨会将使用以前的网络研讨会体验。 新体验使用 TeamsEventsPolicy。 如果已关闭网络研讨会，随着新体验的推出，网络研讨会将保持关闭状态。

目前，基本网络研讨会体验由使用 Teams 会议策略 (Set-CsTeamsMeetingPolicy) 进行会议注册控制。 将来，会议注册设置不会控制网络研讨会;网络研讨会正在过渡到由 Teams 事件策略 (Set-CsTeamsEventsPolicy) 控制。

新的网络研讨会体验在 PowerShell 中配置。 请参阅 [有关如何设置新网络研讨会体验](#set-up-new-webinar-experience)的示例。

有关会议、网络研讨会和直播活动之间的差异的详细信息，请参阅 [会议、网络研讨会和实时事件](quick-start-meetings-live-events.md)。

> [!NOTE]
> 对于本地用户，新的网络研讨会体验尚不可用。
>
> 新的网络研讨会体验不适用于 Microsoft 365 GCC、Microsoft 365 GCC High 或 Microsoft 365 DoD。 现有的网络研讨会体验不适用于 Microsoft 365 GCC High 或 Microsoft 365 DoD。

> [!IMPORTANT]
> 若要让用户设置网络研讨会，必须在 SharePoint 中配置Microsoft Lists，方法是启用创建用于电子数据展示的个人列表。 若要了解详细信息，请参阅[Microsoft Lists的控制设置](/sharepoint/control-lists)。

## <a name="set-up-new-webinar-experience"></a>设置新的网络研讨会体验

必须使用 PowerShell 为组织设置新的网络研讨会体验。 在 Teams 管理中心配置新的网络研讨会体验的功能尚不可用。

会议注册必须打开才能使用新的网络研讨会体验。

### <a name="configure-the-new-webinar-experience-with-powershell"></a>使用 PowerShell 配置新的网络研讨会体验

若要设置新的网络研讨会体验，请在 **set-CsTeamsEventsPolicy** cmdlet Windows PowerShell使用以下属性。

|参数|默认设置|说明|
|---------|-----------|---------------|
|AllowWebinars|已启用|此设置确定用户是否可以创建网络研讨会。|
|EventAccessType|所有人|此设置确定哪些用户可以访问要注册的事件注册页或事件站点，以及允许哪些用户类型在事件中加入会话 () 。|

必须先连接到 Microsoft Teams PowerShell，然后才能运行这些 cmdlet。 有关详细信息，请参阅 [使用 Microsoft Teams PowerShell 管理 Teams](/microsoftteams/teams-powershell-managing-teams)。

1. 启用会议注册。

    ```powershell
    Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowMeetingRegistration $True
    ```

1. 激活新的网络研讨会体验。

    ```powershell
    Set-CsTeamsEventsPolicy -Identity <policy name> -AllowWebinars Enabled
    ```

1. 配置谁可以注册网络研讨会和会议。

    - **仅允许 ** 组织中的用户注册网络研讨会和meetings_*

        ```powershell
        Set-CsTeamsEventsPolicy -Identity <policy name> -EventAccessType EveryoneInCompanyExcludingGuests
        ```

    - **允许所有人（包括匿名用户）注册网络研讨会和会议**

        ```powershell
        Set-CsTeamsEventsPolicy -Identity <policy name> -EventAccessType Everyone
        ```

> [!IMPORTANT]
> 如果在“会议设置”中关闭了 **“匿名用户可以加入****会议”**，则匿名用户无法加入网络研讨会。 若要了解详细信息并启用此设置，请参阅 [Teams 中的会议设置](meeting-settings-in-teams.md)。

## <a name="configure-meeting-registration"></a>配置会议注册

若要使用网络研讨会，必须启用会议注册。

可以使用 **会议** > **策略** 下的 Teams 管理中心来设置会议注册和网络研讨会。

### <a name="meeting-registration"></a>会议注册

如果启用 **会议注册**，组织中的用户可以安排需要注册的网络研讨会和会议。 默认情况下，此设置已启动。 如果要关闭会议注册和网络研讨会，请将此策略设置为 **“关闭**”。

**专用会议安排** 必须启用，会议注册才能正常工作。 详细了解 [私人会议安排](meeting-policies-in-teams-general.md)。

对于教育租户中的学生，此策略默认处于关闭状态。 有关如何为学生启用私人会议安排的详细信息，请参阅[Teams 教育版策略和策略包](policy-packages-edu.md)。

#### <a name="who-can-register"></a>谁可以注册

> [!NOTE]
> 此策略不适用于新的网络研讨会体验。 若要配置谁可以注册新的网络研讨会体验，请使用 `Set-CsTeamsEventsPolicy -EventAccessType`，如 [使用 PowerShell 配置新的网络研讨会体验](#configure-the-new-webinar-experience-with-powershell)中所示。

此策略控制哪些用户只能通过会议注册来注册和参加网络研讨会。 此策略有两个选项，仅当会议 **注册** 处于打开状态时才可用。 默认情况下， **“谁可以注册** ”设置为“ **每个人**”。

如果选择“ **所有人**”，所有用户（包括匿名用户）都可以注册并参加网络研讨会。 如果选择 **组织中的“所有人**”，则只有组织中的用户可以注册并参加网络研讨会。 如果会议注册处于关闭状态，则“ **谁可以注册** ”设置将不可用，并且没有人可以注册网络研讨会。

**谁可以注册** 的默认值是教育租户 **中组织中的每个人**。 有关详细信息，请参阅[Teams 教育版策略向导](easy-policy-setup-edu.md)。

## <a name="collect-webinar-and-meeting-registration-attendance"></a>收集网络研讨会和会议注册出席情况

可以使用 **“会议策略”** > 下的 Teams 管理中心打开 **“参与”报告**。

启用此设置后，组织者可以看到谁注册并参加了他们设置的网络研讨会或会议的报告。 默认情况下，此策略处于打开状态。 有关详细信息，请参阅 [Teams 中的会议策略 - 参与报告](meeting-policies-in-teams-general.md#engagement-report)。 有关最终用户体验的信息，请参阅 [查看和下载会议出席情况报告](https://support.microsoft.com/office/ae7cf170-530c-47d3-84c1-3aedac74d310)。

在 PowerShell 中， **AllowEngagementReport** 参数可用于启用此功能。 默认情况下，此策略处于打开状态。 若要将其关闭，请在 PowerShell 中运行以下命令：

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowEngagementReport Disabled
```

有关 cmdlet 的详细信息，请阅读 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) 。

## <a name="turn-off-webinars"></a>关闭网络研讨会

可以使用 PowerShell 关闭网络研讨会。 这将关闭新的网络研讨会体验以及仅通过会议注册的网络研讨会。

使用以下 PowerShell 脚本关闭网络研讨会：

```powershell
Set-CsTeamsMeetingPolicy -Identity <policy name> -AllowMeetingRegistration $False
Set-CSTeamsEventsPolicy -Identity <policy name> -AllowWebinars Disabled
```

## <a name="related-topics"></a>相关主题

- [Teams 中的会议策略 - 常规](meeting-policies-in-teams-general.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Set-CsTeamsEventsPolicy](/powershell/module/teams/set-csteamseventspolicy)
