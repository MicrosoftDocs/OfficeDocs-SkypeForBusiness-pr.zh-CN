---
title: 管理常规会议策略
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.general
- seo-marvel-apr2020
description: 了解如何在会议环境中管理常规会议Teams。
ms.openlocfilehash: e9e38f724d5327ed54bad8098c1f7fae0c300e34
ms.sourcegitcommit: 3650579196d5f340ef32b31ba975285e08ab1848
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2021
ms.locfileid: "58392919"
---
# <a name="meeting-policy-settings---general"></a>会议策略设置 - 常规

<a name="bkgeneral"> </a>

本文介绍以下用于会议常规Teams设置：

- [允许在频道中立即开会](#allow-meet-now-in-channels)
- [允许 Outlook 加载项](#allow-the-outlook-add-in)
- [允许频道会议安排](#allow-channel-meeting-scheduling)
- [允许安排私人会议](#allow-scheduling-private-meetings)
- [允许在私人会议中立即开会](#allow-meet-now-in-private-meetings)
- [指定的演示者角色模式](#designated-presenter-role-mode)
- [允许参与报告](#allow-engagement-report)
- [允许会议注册](#allow-meeting-registration)
- [Who注册](#who-can-register)
- [群岛模式的会议提供商](#meeting-provider-for-islands-mode)

## <a name="allow-meet-now-in-channels"></a>允许在频道中立即开会

这是按用户政策，在会议开始前适用。 此设置控制用户是否可以在频道中启动Teams会议。 如果启用此功能，用户可以单击"会议"按钮以在频道中启动临时会议或安排会议。 默认值为 True。

[![显示消息下方的"现在开会"图标的屏幕截图 ](media/meeting-policies-meet-now.png)](media/meeting-policies-meet-now.png#lightbox)

## <a name="allow-the-outlook-add-in"></a>允许 Outlook 加载项

这是按用户政策，在会议开始前适用。 此设置控制是否可以从 Outlook (Windows、Mac、Web和移动设备) 内安排 Teams 会议。

![截图显示了安排新会议的能力](media/meeting-policies-outlook-add-in.png)

如果关闭此功能，用户在Teams会议时无法安排Outlook。 例如，在 Windows 上的 Outlook 中，**“新 Teams 会议”** 选项不会显示在功能区中。

## <a name="allow-channel-meeting-scheduling"></a>允许安排频道会议

使用现有的 AllowChannelMeetingScheduling 策略来控制可以在团队频道日历上创建的事件类型。 这是按用户政策，在会议开始前适用。 此设置控制用户是否可以在 Teams 频道中安排会议。 默认情况下，此设置已启动。 

如果此策略已关闭，用户将不能创建新的频道会议。 但是，现有的频道会议可以由活动的组织者进行编辑。

将禁用会议日程安排。

![显示"安排会议"选项的屏幕截图Teams](media/schedule-meeting-option.png)

将禁用“频道选择”。

[![显示用于选择要安排会议频道的日历选项的屏幕截图。 ](media/meeting-policies-select-a-channel-to-meet-in.png)](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)

在频道帖子页面中，将禁用以下内容：

- 在频道回复撰写框中的 **“安排会议”** 按钮。
  ![显示用于选择要安排会议频道的日历选项的屏幕截图。](media/schedule-meeting-disabled-in-chat2.png)
  
- 频道标题上的 **“安排会议”** 按钮。
  ![显示用于选择要通过其安排会议频道的日历选项的屏幕截图。](media/schedule-now-in-header.png)

在频道日历中:

- 将禁用频道日历标题上的 **“添加新事件”** 按钮。
  ![显示日历选项的屏幕截图，用于选择使您能够安排会议的频道。](media/add-new-event-disabled.png)

- 用户将无法在频道日历上拖动并选择一个时间块来创建频道会议。

- 用户不能使用键盘快捷方式在频道日历上创建会议。

在管理中心:

频道日历应用将显示在应用权限策略页面的 **Microsoft 应用** 部分。

![显示管理中心内应用权限Teams的屏幕截图。](media/manage-microsoft-apps-policy.png)

## <a name="allow-scheduling-private-meetings"></a>允许安排私人会议

这是按用户政策，在会议开始前适用。 此设置控制用户是否可以在 Teams 中安排私人会议。 当会议未发布到团队中的某个频道时，这个会议就是私人的。

请注意，如果 **关闭"允许** 安排私人会议"和"允许频道会议安排"，则"添加必需的与会者"和"添加频道"选项将禁用Teams。  默认情况下，此设置已启动。

## <a name="allow-meet-now-in-private-meetings"></a>允许在私人会议中立即开会

这是按用户政策，在会议开始前适用。 此设置控制用户是否可以启动临时私人会议。  默认情况下，此设置已启动。

## <a name="designated-presenter-role-mode"></a>指定的演示者角色模式

这是按用户策略。 通过此设置，可更改 Teams 客户端中 **“会议选项中”** 的 **“谁能演示?”** 设置的默认值。 此策略设置影响所有会议，包括 “立即开会会议”。

通过 **“谁能演示?”** 会议组织者可以选择谁可以成为会议中的演示者。 要了解更多信息，请参阅 [更改 Teams 会议的与会者设置](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) 和 [Teams 会议中的角色](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)。

目前，只能使用 PowerShell 来配置此策略设置。 可以使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有的 Teams 会议策略。 或者，使用 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建一个新的 Teams 会议策略，并将其分配给用户。

要在 Teams 中指定 **“谁能演示?”** 设置的默认值，请将 **DesignatedPresenterRoleMode** 参数设置为以下之一:

- **EveryoneUserOverride**:  所有会议参与者都能成为演示者。 此值为默认值。 该参数对应 Teams 中的 **“每个人”** 设置。
- **EveryoneInCompanyUserOverride**: 组织中的认证用户，包括客人用户，都能成为演示者。 此参数对应 Teams 中 **“我的组织中的人员”** 设置。
- **OrganizerOnlyUserOverride**: 只有会议组织者可以成为演示者，所有其他会议参与者都将指定为与会者。 此参数对应 Teams 中的 **“只有我”** 设置。

请记住，在设置默认值后，会议组织者仍然可以在 Teams 中更改此设置，并选择谁可以在他们安排的会议中演示。

## <a name="allow-engagement-report"></a>允许参与报告

这是按用户策略。 此设置控制会议组织者是否可以下载 [会议出席报告](teams-analytics-and-reports/meeting-attendance-report.md)。

此策略默认为关闭状态，允许组织者查看谁注册并参加他们设置的会议和网络研讨会。 若要在管理中心Teams，请转到"**会议**  >  **会议** 策略"，将策略设置为"已启用 **"。**

可以使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有的 Teams 会议策略。 或者，使用 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建一个新的 Teams 会议策略，并将其分配给用户。

若要使会议组织者能够下载会议出席情况报告，将 **AllowEngagementReport** 参数设置为"已启用 **"。** 启用后，下载报告的选项会显示在 **“参与者”** 窗格中。 默认情况下，此设置未启用。

若要防止会议组织者下载报告，请将该参数设置为 **禁用**。

## <a name="allow-meeting-registration"></a>允许会议注册

这是按用户策略。 如果启用此功能，您的组织中的用户可以设置网络研讨会。 默认启用此策略。

若要在管理中心内编辑Teams策略，请转到 **"会议**  >  **会议策略"。** 若要关闭会议注册，将策略设置为"关闭 **"。**

可以使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有的 Teams 会议策略。 或者，使用 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建一个新的 Teams 会议策略，并将其分配给用户。

若要启用会议注册，将 **AllowMeetingRegistration 参数** 设置为 **True。** 默认设置为 **True。**

若要关闭会议注册并防止用户安排网络研讨会，将 参数设置为 **False。**

## <a name="who-can-register"></a>Who注册

此策略控制哪些用户可以注册和参加网络研讨会。 此策略有两个选项，仅在启用 **"允许会议** 注册"时可用。

- 如果希望 **Who** 包括匿名用户在内的所有人注册和参加组织中用户设置的网络研讨会，请设置"可注册到每个人"。
- 如果希望 **Who** 注册并参加网络研讨会，请设置"可注册到组织中所有人"。

默认情况下 **，Who注册设置为**"每个人 **"。** 若要在管理中心内编辑Teams策略，请转到 **"会议**  >  **会议策略"。**

可以使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有的 Teams 会议策略。 或者，使用 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建一个新的 Teams 会议策略，并将其分配给用户。

若要允许每个人（包括匿名用户）注册和参加网络研讨会，将 **WhoCanRegister** 参数设置为 **"每个人"。** 默认情况下，此选项 **设置为"每个人** "。

若要仅允许您的组织中的用户注册并参加网络研讨会，将 参数设置为 **EveryoneInCompany。**

## <a name="meeting-provider-for-islands-mode"></a>群岛模式的会议提供商

这是按用户策略。 此设置可控制 *处于并行模式的用户* 使用哪个 Outlook 会议加载项。 你可以指定用户是只能使用 Team 会议加载项，还是可同时使用 Teams 会议加载项和 Skype for Business 会议加载项来在 Outlook 中安排会议。

你只能将此策略应用于处于孤岛模式且其 Teams 会议策略中的 **AllowOutlookAddIn** 参数设置为 **True** 的用户。

目前，只能使用 PowerShell 来设置该策略。 可以使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有的 Teams 会议策略。 或者，使用 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建一个新的 Teams 会议策略，并将其分配给用户。

若要指定希望用户可以使用哪种会议加载项，请按以下方式设置 **PreferredMeetingProviderForIslandsMode** 参数:

- 将参数设置为 **TeamsAndSfB** 以启用 Outlook 中的 Teams 会议加载项和 Skype for Business 加载项。 此值为默认值。
- 将参数设置为 **Teams**，以便仅启用 Outlook 中的 Teams 会议加载项。 此策略设置可确保所有将来的会议均具有 Teams 会议的加入链接。 它不能将现有的 Skype for Business 会议加入链接迁移到 Teams。 该策略设置不会影响 Skype for Business 中的状态、聊天、PSTN 呼叫或任何其他功能，这意味着用户将继续使用 Skype for Business 的这些功能。

  如果将参数设置为 **Teams**，然后切换回 **TeamsAndSfB**，则将启用这两个会议加载项。 但是，请注意，Teams会议加入链接不会迁移到Skype for Business。 只有在更改后安排的 Skype for Business 会议才会有 Skype for Business 会议加入链接。

## <a name="meeting-reactions"></a>会议回应

AllowMeetingReactions 设置只能使用 PowerShell 应用。 在 Teams 管理中心，没有任何选项可以打开或关闭 AllowMeetingReactions。

会议回应默认为“关闭”。 关闭用户的回应，并不意味着用户不能在自己安排的会议中使用回应。 无论默认设置如何，会议组织者仍然可以从会议选项页面开启回应。


## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
- [在 Teams](policy-assignment-overview.md)
- [从用户删除 RestrictedAnonymousAccess Teams 会议策略](meeting-policies-restricted-anonymous-access.md)
