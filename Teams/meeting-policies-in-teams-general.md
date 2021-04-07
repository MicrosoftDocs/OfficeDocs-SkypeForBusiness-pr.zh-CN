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
description: 了解如何在 Teams 中管理常规会议策略设置。
ms.openlocfilehash: fb5f537e5cc96ba363fb4aa68bbfff2af513db6b
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598701"
---
# <a name="meeting-policy-settings---general"></a>会议策略设置 - 常规

<a name="bkgeneral"> </a>

本文介绍 Teams 会议的以下常规策略设置：

- [在频道中允许"现在开会"](#allow-meet-now-in-channels)
- [允许 Outlook 加载项](#allow-the-outlook-add-in)
- [允许频道会议安排](#allow-channel-meeting-scheduling)
- [允许安排私人会议](#allow-scheduling-private-meetings)
- [允许现在在私人会议中召开会议](#allow-meet-now-in-private-meetings)
- [指定的演示者角色模式](#designated-presenter-role-mode)
- [会议出席情况报告](#meeting-attendance-report)
- [群岛模式的会议提供商](#meeting-provider-for-islands-mode)

## <a name="allow-meet-now-in-channels"></a>在频道中允许"现在开会"

这是每个用户的策略，在会议启动之前适用。 此设置控制用户是否可以在 Teams 频道中启动临时会议。 如果启用此功能，用户可以单击"会议"按钮以在频道中启动临时会议或安排会议。 默认值为 True。

[![显示消息下方的"现在开会"图标的屏幕截图 ](media/meeting-policies-meet-now.png)](media/meeting-policies-meet-now.png#lightbox)

## <a name="allow-the-outlook-add-in"></a>允许 Outlook 加载项

这是每个用户的策略，在会议启动之前适用。 此设置控制是否可以在 Outlook 中安排 Teams 会议 (Windows、Mac、Web 和移动) 。

![显示安排新会议的能力的屏幕截图](media/meeting-policies-outlook-add-in.png)

如果关闭此功能，用户在 Outlook 中创建新会议时无法安排 Teams 会议。 例如，在 Outlook on Windows 中，"新建 **Teams** 会议"选项不会显示在功能区中。

## <a name="allow-channel-meeting-scheduling"></a>允许频道会议安排

使用现有的 AllowChannelMeetingScheduling 策略控制可在团队频道日历上创建的事件类型。 这是每个用户的策略，在会议启动之前适用。 此设置控制用户是否可以在 Teams 频道中安排会议。 默认情况下，此设置已打开。 

如果此策略已关闭，用户将不能创建新的频道会议。 但是，活动的组织者可以编辑现有频道会议。

计划会议将被禁用。

![显示 Teams 中的"安排会议"选项的屏幕截图](media/schedule-meeting-option.png)

通道选择被禁用。

[![显示用于选择要安排会议频道的日历选项的屏幕截图。 ](media/meeting-policies-select-a-channel-to-meet-in.png)](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)

在频道帖子页面中，将禁用以下内容：

- **频道答复** 撰写框上的"安排会议"按钮。
  ![显示用于选择要安排会议频道的日历选项的屏幕截图。](media/schedule-meeting-disabled-in-chat2.png)
  
- **频道标题上的** "安排会议"按钮。
  ![显示用于选择要通过其安排会议频道的日历选项的屏幕截图。](media/schedule-now-in-header.png)

在频道日历中：

- **频道日历标题** 上的"添加新事件"按钮将被禁用。
  ![显示日历选项的屏幕截图，用于选择使您能够安排会议的频道。](media/add-new-event-disabled.png)

- 用户将无法在频道日历上拖动并选择一个时间块来创建频道会议。

- 用户不能使用键盘快捷方式在频道日历上创建会议。

在管理中心：

通道日历应用会显示在应用权限策略页面的 **"Microsoft** 应用"部分。

![显示 Teams 管理中心的应用权限策略的屏幕截图。](media/manage-microsoft-apps-policy.png)

## <a name="allow-scheduling-private-meetings"></a>允许安排私人会议

这是每个用户的策略，在会议启动之前适用。 此设置控制用户是否可以在 Teams 中安排私人会议。 当会议未发布到团队中的频道时，会议是私密的。

请注意，如果 **关闭"允许** 安排私人会议"和"**允许** 频道会议安排"，则Teams 中的用户禁用了"添加必需的与会者"和"添加频道"选项。 默认情况下，此设置已打开。

## <a name="allow-meet-now-in-private-meetings"></a>允许现在在私人会议中召开会议

这是每个用户的策略，在会议启动之前适用。 此设置控制用户是否可以启动临时私人会议。  默认情况下，此设置已打开。

## <a name="designated-presenter-role-mode"></a>指定的演示者角色模式

这是按用户的策略。 此设置允许您在 Teams 客户端的会议选项中更改"谁可以出席？"**设置的默认值**。 此策略设置会影响所有会议，包括"现在开会"会议。

" **谁可以演示？"** 设置允许会议组织者选择谁可以是会议中的演示者。 有关详细信息，请参阅更改 [Teams 会议的参与者设置](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) 和 [Teams 会议的角色](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)。

目前，只能使用 PowerShell 配置此策略设置。 可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有 Teams 会议策略。 或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建新的 Teams 会议策略并将其分配给用户。

若要在 Teams 中指定"谁可以出席 **？"** 设置的默认值，将 **SpecifyedPresenterRoleMode** 参数设置为以下参数之一：

- **EveryoneUserOverride：** 所有会议参与者都可以是演示者。 此值为默认值。 此参数对应于 Teams **中的"每个人** "设置。
- **EveryoneInCompanyUserOverride：** 组织中经过身份验证的用户（包括来宾用户）可以是演示者。 此参数对应于 Teams 中的 **"组织人员** "设置。
- **组织者OnlyUserOverride：** 只有会议组织者才能是演示者，所有会议参与者都指定为与会者。 此参数对应于 Teams 中的 **"仅我** "设置。

请记住，设置默认值后，会议组织者仍然可以在 Teams 中更改此设置，并选择谁可以在他们安排的会议中出席。

## <a name="meeting-attendance-report"></a>会议出席情况报告

这是按用户的策略。 此设置控制会议组织者是否可以下载 [会议出席报告](teams-analytics-and-reports/meeting-attendance-report.md)。

目前，只能使用 PowerShell 配置此策略设置。 可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有 Teams 会议策略。 或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建新的 Teams 会议策略并将其分配给用户。

若要使会议组织者能够下载会议出席情况报告，将 **AllowEngagementReport** 参数设置为"已启用 **"。** 启用后，下载报表的选项会显示在"参与者 **"窗格中** 。

若要防止会议组织者下载报告，将 参数设置为"已 **禁用"。** 默认情况下，此设置处于禁用状态，并且下载报表的选项不可用。

## <a name="meeting-provider-for-islands-mode"></a>群岛模式的会议提供商

这是按用户的策略。 此设置控制哪些 Outlook 会议加载项用于位于 *群岛模式 的用户*。 你可以指定用户是只能使用 Team 会议加载项，还是可同时使用 Teams 会议加载项和 Skype for Business 会议加载项来在 Outlook 中安排会议。

你只能将此策略应用于处于孤岛模式且其 Teams 会议策略中的 **AllowOutlookAddIn** 参数设置为 **True** 的用户。

目前，只能使用 PowerShell 设置此策略。 可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有 Teams 会议策略。 或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建新的 Teams 会议策略并将其分配给用户。

若要指定希望哪些会议加载项可供用户使用，请设置 **PreferredMeetingProviderForIslandsMode** 参数，如下所示：

- 将 参数设置为 **TeamsAndSfB，** 以在 Outlook 中同时启用 Teams 会议加载项和 Skype for Business 加载项。 此值为默认值。
- 将 参数设置为 **Teams，** 以在 Outlook 中仅启用 Teams 会议加载项。 此策略设置可确保所有将来的会议都有 Teams 会议加入链接。 它不会将现有 Skype for Business 会议加入链接迁移到 Teams。 此策略设置不会影响 Skype for Business 中的状态、聊天、PSTN 呼叫或其他任何功能，这意味着用户将继续使用 Skype for Business 实现这些功能。

  如果将 参数设置为 **Teams，** 然后切换回 **TeamsAndSfB，** 则两个会议加载项都已启用。 但是，请注意，现有 Teams 会议加入链接不会迁移到 Skype for Business。 只有更改后安排的 Skype for Business 会议才具有 Skype for Business 会议加入链接。

## <a name="meeting-reactions"></a>会议回应

AllowMeetingReactions 设置只能使用 PowerShell 应用。 无法从 Teams 管理中心打开或关闭 AllowMeetingReactions。

会议回应默认为"关闭"。 为用户关闭回应并不意味着用户无法安排的会议使用回应。 无论默认设置如何，会议组织者仍可从会议选项页面打开回应。


## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)
- [向 Teams 中的用户分配策略](assign-policies.md)
- [从用户中删除 RestrictedAnonymousAccess Teams 会议策略](meeting-policies-restricted-anonymous-access.md)
