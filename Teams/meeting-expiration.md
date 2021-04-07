---
title: Microsoft Teams 中的会议策略和会议到期时间
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: 了解如何在 Microsoft Teams 中使用会议策略设置来控制会议到期时间。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6e8821781eab70696c9b24c8df18cc8dd0b46870
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598611"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Microsoft Teams 中的会议策略和会议到期时间

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>概述

[](meeting-policies-in-teams.md) Microsoft Teams 中的会议策略用于控制您的组织中的用户是否可以启动和安排会议，以及可供会议参与者用于用户安排的会议的功能。 可以使用全局（组织范围内的默认）策略，也可以创建并分配自定义策略。 在 Microsoft Teams 管理中心或通过使用 Get、New、Set、Remove、Grant [](/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy PowerShell cmdlet 管理会议策略。 [](/powershell/module/skype/get-csteamsmeetingpolicy) [](/powershell/module/skype/new-csteamsmeetingpolicy) [](/powershell/module/skype/set-csteamsmeetingpolicy) [](/powershell/module/skype/remove-csteamsmeetingpolicy)

控制用户是否可以启动和安排会议的会议策略设置还控制用户安排的会议的到期时间。 当会议的会议加入链接和会议 ID 过期时，没有人可以加入会议。 以下会议策略设置确定用户是否可以在 Teams 中启动和安排会议，我们将在整篇文章中引用它们。

- [在频道中允许](meeting-policies-in-teams-general.md#allow-meet-now-in-channels)"现在开会"：控制用户是否可以在频道中启动即席会议。
- [允许频道会议计划](meeting-policies-in-teams-general.md#allow-channel-meeting-scheduling)：控制用户是否可以在频道中安排会议。
- [允许安排私人会议](meeting-policies-in-teams-general.md#allow-scheduling-private-meetings)：控制用户是否可以在 Teams 中安排私人会议。 当会议未发布到团队中的频道时，会议是私密的。
- [允许 Outlook 添加](meeting-policies-in-teams-general.md#allow-the-outlook-add-in)：控制用户是否可以从 Outlook 安排私人会议。 当会议未发布到团队中的频道时，会议是私密的。
- [允许现在在私人会议中召开会议](meeting-policies-in-teams-general.md#allow-meet-now-in-private-meetings)：控制用户是否可以启动即席私人会议。

默认情况下，这些设置为打开状态。 当其中任一设置关闭时，分配有策略的任何用户都无法启动或安排该类型的新会议。 同时，用户以前启动或计划过期的所有现有会议的会议加入链接和会议 ID。

例如，如果为用户分配会议策略，其中这些会议策略设置设置为"开"，然后关闭"在频道中允许立即开会"设置，该用户无法再在频道中启动即席会议，并且频道"现在开会"加入用户之前创建的链接已过期。 用户仍可以启动和安排其他会议类型和加入由其他人组织的会议。

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>当会议加入链接和会议 ID 过期时会发生什么情况？

当会议的会议加入链接和会议 ID 过期时，没有人可以加入会议。 当用户尝试通过链接或通过电话加入会议时，他们收到一条消息，指出会议不再可用。 对话、文件、白板、录制、脚本和与会议相关的其他内容将保留，用户仍可以访问它们。

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>打开和关闭会议策略设置时会发生什么情况？

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>将会议策略设置从"开"切换为"关"

当会议策略设置设置为 **"开**"时，分配有该策略的用户可以启动或安排该类型的会议，每个人都可以加入。 将会议策略设置切换为"关闭"时，分配有该策略的用户无法启动或计划该类型的新会议，并且用户以前安排的现有会议的会议加入链接和会议 ID 已过期。

请记住，用户仍可以加入由其他人组织的会议。

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>将会议策略设置从"关"切换为"开"

将会议策略设置从 **"关"** 切换为"开"时，分配有该策略的用户可以启动或安排该类型的会议。 如果会议策略设置已关闭，然后再次为用户启用，则用户组织的所有以前计划的 (和过期的) 会议将变为活动状态，用户可以使用会议加入链接或通过电话加入它们。  

## <a name="meeting-expiration-scenarios"></a>会议过期方案

下面汇总了本文中讨论的每个会议策略设置的会议到期工作原理。 

|如果你希望... |执行此操作  |会议加入行为  |
|---------|---------|---------|
|使频道"现在开会"由用户启动的会议过期  |在频道 **中关闭"允许现在开会"。**|没有人可以加入频道会议现在由用户启动的会议。         |
|使用户安排的频道会议过期   |关闭"**允许频道会议计划"。**         |没有人可以加入用户安排的频道会议。 这可以防止用户加入以下活动：<ul><li>过去发生的频道会议。</li> <li>计划在将来召开但尚未发生的频道会议。</li><li>将来的定期频道会议实例。</li></ul>       |
|使用户安排的私人会议过期    |关闭 **"允许安排私人会议"，***并关闭*"**允许 Outlook 加载项"。**          |没有人可以加入用户安排的私人会议。 这可以防止用户加入以下活动： <ul><li>过去发生的私人会议。</li> <li>计划在将来召开但尚未发生的私人会议。</li><li>将来的定期私人会议实例。</li></ul> " **允许安排私人会议** "和"允许 **Outlook** 加载项"都必须关闭，以使用户安排的私人会议过期。 如果一个设置处于关闭状态，另一个设置处于打开状态，则现有会议的会议加入链接和会议 ID 将保持活动状态，并且不会过期。      |
|使专用会议现在由用户启动的会议过期  |在私人 **会议中关闭"允许现在开会"。**          |现在没有人可以加入由用户启动的私人会议。         |

如果希望用户访问以前由特定用户安排或启动的会议，您可以：

- 打开该用户的会议策略设置。
- 关闭该用户的会议策略设置，让启用了策略设置的另一个用户创建一个新会议来替换已过期的会议。

> [!NOTE]
> 如果会议是由代理发送的，而代理有权代表其他人（例如经理）发送会议邀请，则会议策略设置将应用于向经理授予 (权限) 。

## <a name="related-topics"></a>相关主题

[管理 Teams 中的会议策略](meeting-policies-in-teams.md)

[向 Teams 中的用户分配策略](assign-policies.md)

[Teams PowerShell 概览](teams-powershell-overview.md)