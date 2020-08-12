---
title: Microsoft 团队中的会议策略和会议到期
author: LanaChin
ms.author: v-lanac
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
description: 了解如何使用会议策略设置控制 Microsoft 团队中的会议到期时间。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e25ea1c55890a78e9e492dd2c2dd419a6ed34f2
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640970"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Microsoft 团队中的会议策略和会议到期

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>概述

Microsoft 团队中的[会议策略](meeting-policies-in-teams.md)用于控制组织中的用户是否可以启动和安排会议以及由用户安排的会议参与者可使用的功能。 你可以使用全局 (组织范围默认) 策略，或者创建和分配自定义策略。 通过使用 "[获取](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingpolicy)"、"[新建](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy)"、"[设置](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)"、"[删除](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmeetingpolicy)"、"[授权](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy)-CsTeamsMeetingPolicy" PowerShell cmdlet，在 Microsoft 团队管理中心中管理会议策略。

控制用户是否可以启动和安排会议的会议策略设置还控制由用户安排的会议的到期时间。 当会议加入链接和会议的会议 ID 到期时，任何人都不能加入会议。 以下会议策略设置确定用户是否可以在团队中启动和安排会议，我们将在本文中参考。

- [允许在频道中立即开会](meeting-policies-in-teams.md#allow-meet-now-in-channels)：控制用户是否可以在频道中启动即席会议。
- [允许频道会议安排](meeting-policies-in-teams.md#allow-channel-meeting-scheduling)：控制用户是否可以在频道中安排会议。
- [允许安排私人会议](meeting-policies-in-teams.md#allow-scheduling-private-meetings)：控制用户是否可以在团队中安排私人会议。 当会议未发布到团队中的频道时，它是私有的。
- [允许 Outlook 加载项](meeting-policies-in-teams.md#allow-the-outlook-add-in)：控制用户是否可以从 Outlook 安排私人会议。 当会议未发布到团队中的频道时，它是私有的。
- [允许在私人会议中立即开会](meeting-policies-in-teams.md#allow-meet-now-in-private-meetings)：控制用户是否可以启动即席私人会议。

默认情况下，这些设置处于打开状态。 如果这些设置中的任何一个处于关闭状态，则分配了该策略的任何用户都无法启动或计划该类型的新会议。 同时，会议加入的所有现有会议的链接和会议 Id，该用户之前已开始或计划过期。

例如，如果为用户分配了将这些会议策略设置设置为 **"开**" 的会议策略，然后关闭 "**允许在频道中立即开会**" 设置，则该用户无法再在频道中启动即席会议，并且信道 "现在开会" 联接的用户以前创建的链接已过期。 用户仍然可以启动和安排其他会议类型以及加入由其他人组织的会议。

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>会议加入链接和会议 ID 过期后会发生什么情况？

当会议加入链接和会议的会议 ID 到期时，任何人都不能加入会议。 当用户尝试通过链接或手机加入会议时，他们将收到一条消息，指出会议不再可用。 将保留与会议相关的对话、文件、白板、录制、脚本和其他内容，用户仍然可以访问它们。

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>打开和关闭会议策略设置时会发生什么情况？

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>将会议策略设置从 "开" 切换为 "禁用"

当会议策略设置设置为 **"开**" 时，分配了该策略的用户可以启动或计划该类型的会议，所有人都可以加入。 将会议策略设置切换为 "**关**" 时，分配了该策略的用户无法启动或计划该类型的新会议，并且会议加入链接和用户之前安排的现有会议的会议 id 已过期。

请记住，用户仍然可以加入由其他人组织的会议。

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>将会议策略设置从 "关闭" 切换为 "开"

将会议策略设置从 "**关闭**" 切换到 **"打开**" 时，分配了该策略的用户可以启动或计划该类型的会议。 如果已关闭会议策略设置，然后为用户再次打开，则以前安排的所有 (和过期) 由用户组织的会议将处于活动状态，并且用户可以使用会议加入链接或手机加入他们。  

## <a name="meeting-expiration-scenarios"></a>会议到期方案

下面是有关如何为本文中讨论的每个会议策略设置的会议到期情况的摘要。 

|如果需要 .。。 |要执行的操作  |会议加入行为  |
|---------|---------|---------|
|终止频道 "立即开会" 会议已由用户启动  |关闭 **"允许在频道中立即开会"**。|任何人都无法加入由用户启动的频道 "立即开会" 会议。         |
|终止用户计划的频道会议   |关闭 "**允许频道会议安排**"。         |任何人都不能加入由用户计划的频道会议。 这可防止用户加入以下内容：<ul><li>过去发生的频道会议。</li> <li>安排未来且尚未发生的频道会议。</li><li>定期频道会议的未来实例。</li></ul>       |
|使用户计划的私人会议过期    |关闭 "**允许安排私人会议**"*和*"关闭**允许 Outlook 加载项"**。          |任何人都不能加入由用户计划的私人会议。 这可防止用户加入以下内容： <ul><li>过去发生的私人会议。</li> <li>计划未来且尚未发生的私人会议。</li><li>定期私人会议的未来实例。</li></ul> 两者都**允许安排私人会议**，并且**允许 Outlook 加载项**必须关闭才能使用户计划的私人会议过期。 如果一个设置为 "关闭"，而另一个设置处于打开状态，则现有会议的会议加入链接和会议 Id 保持有效且不会过期。      |
|使用户立即开始的私人开会会议到期会议  |关闭**私人会议中的 "允许立即开会"**。          |任何人都无法加入由用户启动的专用 "立即开会" 会议。         |

如果您希望用户能够访问以前由特定用户计划或启动的会议，您可以：

- 为该用户启用 "会议策略" 设置。
- 关闭该用户的会议策略设置，并让另一个已启用策略设置的用户创建新会议以替换过期的会议。

> [!NOTE]
> 如果会议是由代理人（代表另一个人（如经理）发送会议邀请的用户发送的，则会议策略设置将应用于授予管理员) 的权限 (人员。

## <a name="related-topics"></a>相关主题

[管理团队中的会议策略](meeting-policies-in-teams.md)

[向团队中的用户分配策略](assign-policies.md)

[Teams PowerShell 概览](teams-powershell-overview.md)