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
ms.openlocfilehash: fb5f537e5cc96ba363fb4aa68bbfff2af513db6b
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598701"
---
# <a name="meeting-policy-settings---general"></a><span data-ttu-id="56fc6-103">会议策略设置 - 常规</span><span class="sxs-lookup"><span data-stu-id="56fc6-103">Meeting policy settings - General</span></span>

<span data-ttu-id="56fc6-104"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="56fc6-104"><a name="bkgeneral"> </a></span></span>

<span data-ttu-id="56fc6-105">本文介绍以下用于会议常规Teams设置：</span><span class="sxs-lookup"><span data-stu-id="56fc6-105">This article describes the following general policy settings for Teams meetings:</span></span>

- [<span data-ttu-id="56fc6-106">允许在频道中立即开会</span><span class="sxs-lookup"><span data-stu-id="56fc6-106">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="56fc6-107">允许 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="56fc6-107">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="56fc6-108">允许频道会议安排</span><span class="sxs-lookup"><span data-stu-id="56fc6-108">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="56fc6-109">允许安排私人会议</span><span class="sxs-lookup"><span data-stu-id="56fc6-109">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)
- [<span data-ttu-id="56fc6-110">允许在私人会议中立即开会</span><span class="sxs-lookup"><span data-stu-id="56fc6-110">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)
- [<span data-ttu-id="56fc6-111">指定的演示者角色模式</span><span class="sxs-lookup"><span data-stu-id="56fc6-111">Designated presenter role mode</span></span>](#designated-presenter-role-mode)
- [<span data-ttu-id="56fc6-112">会议出席情况报告</span><span class="sxs-lookup"><span data-stu-id="56fc6-112">Meeting attendance report</span></span>](#meeting-attendance-report)
- [<span data-ttu-id="56fc6-113">群岛模式的会议提供商</span><span class="sxs-lookup"><span data-stu-id="56fc6-113">Meeting provider for Islands mode</span></span>](#meeting-provider-for-islands-mode)

## <a name="allow-meet-now-in-channels"></a><span data-ttu-id="56fc6-114">允许在频道中立即开会</span><span class="sxs-lookup"><span data-stu-id="56fc6-114">Allow Meet now in channels</span></span>

<span data-ttu-id="56fc6-115">这是按用户政策，在会议开始前适用。</span><span class="sxs-lookup"><span data-stu-id="56fc6-115">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="56fc6-116">此设置控制用户是否可以在频道中启动Teams会议。</span><span class="sxs-lookup"><span data-stu-id="56fc6-116">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="56fc6-117">如果启用此功能，用户可以单击"会议"按钮以在频道中启动临时会议或安排会议。</span><span class="sxs-lookup"><span data-stu-id="56fc6-117">If you turn this on, users can click the **Meet** button to start an ad hoc meeting or schedule a meeting in the channel.</span></span> <span data-ttu-id="56fc6-118">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="56fc6-118">The default value is True.</span></span>

<span data-ttu-id="56fc6-119">[![显示消息下方的"现在开会"图标的屏幕截图 ](media/meeting-policies-meet-now.png)](media/meeting-policies-meet-now.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="56fc6-119">[ ![Screenshot showing the Meet now icon below a message](media/meeting-policies-meet-now.png) ](media/meeting-policies-meet-now.png#lightbox)</span></span>

## <a name="allow-the-outlook-add-in"></a><span data-ttu-id="56fc6-120">允许 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="56fc6-120">Allow the Outlook add-in</span></span>

<span data-ttu-id="56fc6-121">这是按用户政策，在会议开始前适用。</span><span class="sxs-lookup"><span data-stu-id="56fc6-121">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="56fc6-122">此设置控制是否可以从 Outlook (Windows、Mac、Web和移动设备) 内安排 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="56fc6-122">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![截图显示了安排新会议的能力](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="56fc6-124">如果关闭此功能，用户在 Teams中创建新会议时无法安排Outlook。</span><span class="sxs-lookup"><span data-stu-id="56fc6-124">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="56fc6-125">例如，在 Windows 上的 Outlook 中，**“新 Teams 会议”** 选项不会显示在功能区中。</span><span class="sxs-lookup"><span data-stu-id="56fc6-125">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

## <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="56fc6-126">允许安排频道会议</span><span class="sxs-lookup"><span data-stu-id="56fc6-126">Allow channel meeting scheduling</span></span>

<span data-ttu-id="56fc6-127">使用现有的 AllowChannelMeetingScheduling 策略来控制可以在团队频道日历上创建的事件类型。</span><span class="sxs-lookup"><span data-stu-id="56fc6-127">Use the existing AllowChannelMeetingScheduling policy to control the types of events that can be created on the team channel calendars.</span></span> <span data-ttu-id="56fc6-128">这是按用户政策，在会议开始前适用。</span><span class="sxs-lookup"><span data-stu-id="56fc6-128">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="56fc6-129">此设置控制用户是否可以在 Teams 频道中安排会议。</span><span class="sxs-lookup"><span data-stu-id="56fc6-129">This setting controls whether users can schedule a meeting in a Teams channel.</span></span> <span data-ttu-id="56fc6-130">默认情况下，此设置已启动。</span><span class="sxs-lookup"><span data-stu-id="56fc6-130">By default, this setting is turned on.</span></span> 

<span data-ttu-id="56fc6-131">如果此策略已关闭，用户将不能创建新的频道会议。</span><span class="sxs-lookup"><span data-stu-id="56fc6-131">If this policy is turned off, users will not be able to create new channel meetings.</span></span> <span data-ttu-id="56fc6-132">但是，现有的频道会议可以由活动的组织者进行编辑。</span><span class="sxs-lookup"><span data-stu-id="56fc6-132">However, existing channel meetings can be edited by the organizer of the event.</span></span>

<span data-ttu-id="56fc6-133">将禁用会议日程安排。</span><span class="sxs-lookup"><span data-stu-id="56fc6-133">Schedule a meeting will be disabled.</span></span>

![显示"安排会议"选项的屏幕截图Teams](media/schedule-meeting-option.png)

<span data-ttu-id="56fc6-135">将禁用“频道选择”。</span><span class="sxs-lookup"><span data-stu-id="56fc6-135">Channel selection is disabled.</span></span>

<span data-ttu-id="56fc6-136">[![显示用于选择要安排会议频道的日历选项的屏幕截图。 ](media/meeting-policies-select-a-channel-to-meet-in.png)](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="56fc6-136">[ ![Screenshot showing the calendar option for selecting a channel that you want to schedule a meeting in.](media/meeting-policies-select-a-channel-to-meet-in.png) ](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)</span></span>

<span data-ttu-id="56fc6-137">在频道帖子页面中，将禁用以下内容：</span><span class="sxs-lookup"><span data-stu-id="56fc6-137">In the channel posts page, the following will be disabled:</span></span>

- <span data-ttu-id="56fc6-138">在频道回复撰写框中的 **“安排会议”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="56fc6-138">**Schedule a meeting** button on the channel reply compose box.</span></span>
  <span data-ttu-id="56fc6-139">![显示用于选择要安排会议频道的日历选项的屏幕截图。](media/schedule-meeting-disabled-in-chat2.png)</span><span class="sxs-lookup"><span data-stu-id="56fc6-139">![Screenshot showing the calendar option for selecting a channel in which you want to schedule a meeting.](media/schedule-meeting-disabled-in-chat2.png)</span></span>
  
- <span data-ttu-id="56fc6-140">频道标题上的 **“安排会议”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="56fc6-140">**Schedule a meeting** button on the channel header.</span></span>
  <span data-ttu-id="56fc6-141">![显示用于选择要通过其安排会议频道的日历选项的屏幕截图。](media/schedule-now-in-header.png)</span><span class="sxs-lookup"><span data-stu-id="56fc6-141">![Screenshot showing the calendar option for selecting a channel through which you want to schedule a meeting.](media/schedule-now-in-header.png)</span></span>

<span data-ttu-id="56fc6-142">在频道日历中:</span><span class="sxs-lookup"><span data-stu-id="56fc6-142">In the channel calendar:</span></span>

- <span data-ttu-id="56fc6-143">将禁用频道日历标题上的 **“添加新事件”** 按钮。</span><span class="sxs-lookup"><span data-stu-id="56fc6-143">**Add new event** button on channel calendar header will be disabled.</span></span>
  <span data-ttu-id="56fc6-144">![显示日历选项的屏幕截图，用于选择使您能够安排会议的频道。](media/add-new-event-disabled.png)</span><span class="sxs-lookup"><span data-stu-id="56fc6-144">![Screenshot showing the calendar option for selecting a channel that will enable you to schedule a meeting.](media/add-new-event-disabled.png)</span></span>

- <span data-ttu-id="56fc6-145">用户将无法在频道日历上拖动并选择一个时间块来创建频道会议。</span><span class="sxs-lookup"><span data-stu-id="56fc6-145">Users will not be able to drag and select a time block on the channel calendar to create a channel meeting.</span></span>

- <span data-ttu-id="56fc6-146">用户不能使用键盘快捷方式在频道日历上创建会议。</span><span class="sxs-lookup"><span data-stu-id="56fc6-146">Users cannot use Keyboard shortcuts to create a meeting on the channel calendar.</span></span>

<span data-ttu-id="56fc6-147">在管理中心:</span><span class="sxs-lookup"><span data-stu-id="56fc6-147">In the admin center:</span></span>

<span data-ttu-id="56fc6-148">频道日历应用将显示在应用权限策略页面的 **Microsoft 应用** 部分。</span><span class="sxs-lookup"><span data-stu-id="56fc6-148">The channel calendar app will show up in the **Microsoft apps** section on the app permission policies page.</span></span>

![显示管理中心内应用权限Teams屏幕截图。](media/manage-microsoft-apps-policy.png)

## <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="56fc6-150">允许安排私人会议</span><span class="sxs-lookup"><span data-stu-id="56fc6-150">Allow scheduling private meetings</span></span>

<span data-ttu-id="56fc6-151">这是按用户政策，在会议开始前适用。</span><span class="sxs-lookup"><span data-stu-id="56fc6-151">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="56fc6-152">此设置控制用户是否可以在 Teams 中安排私人会议。</span><span class="sxs-lookup"><span data-stu-id="56fc6-152">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="56fc6-153">当会议未发布到团队中的某个频道时，这个会议就是私人的。</span><span class="sxs-lookup"><span data-stu-id="56fc6-153">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="56fc6-154">请注意，如果 **关闭"允许** 安排私人会议"和"**允许** 频道会议安排"，则"添加必需的与会者"和"添加频道"选项将禁用Teams。</span><span class="sxs-lookup"><span data-stu-id="56fc6-154">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span> <span data-ttu-id="56fc6-155">默认情况下，此设置已启动。</span><span class="sxs-lookup"><span data-stu-id="56fc6-155">By default, this setting is turned on.</span></span>

## <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="56fc6-156">允许在私人会议中立即开会</span><span class="sxs-lookup"><span data-stu-id="56fc6-156">Allow Meet now in private meetings</span></span>

<span data-ttu-id="56fc6-157">这是按用户政策，在会议开始前适用。</span><span class="sxs-lookup"><span data-stu-id="56fc6-157">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="56fc6-158">此设置控制用户是否可以启动临时私人会议。</span><span class="sxs-lookup"><span data-stu-id="56fc6-158">This setting controls whether a user can start an ad hoc private meeting.</span></span>  <span data-ttu-id="56fc6-159">默认情况下，此设置已启动。</span><span class="sxs-lookup"><span data-stu-id="56fc6-159">By default, this setting is turned on.</span></span>

## <a name="designated-presenter-role-mode"></a><span data-ttu-id="56fc6-160">指定的演示者角色模式</span><span class="sxs-lookup"><span data-stu-id="56fc6-160">Designated presenter role mode</span></span>

<span data-ttu-id="56fc6-161">这是按用户策略。</span><span class="sxs-lookup"><span data-stu-id="56fc6-161">This is a per-user policy.</span></span> <span data-ttu-id="56fc6-162">通过此设置，可更改 Teams 客户端中 **“会议选项中”** 的 **“谁能演示?”** 设置的默认值。</span><span class="sxs-lookup"><span data-stu-id="56fc6-162">This setting lets you change the default value of the **Who can present?** setting in **Meeting options** in the Teams client.</span></span> <span data-ttu-id="56fc6-163">此策略设置影响所有会议，包括 “立即开会会议”。</span><span class="sxs-lookup"><span data-stu-id="56fc6-163">This policy setting affects all meetings, including Meet Now meetings.</span></span>

<span data-ttu-id="56fc6-164">通过 **“谁能演示?”** 会议组织者可以选择谁可以成为会议中的演示者。</span><span class="sxs-lookup"><span data-stu-id="56fc6-164">The **Who can present?** setting lets meeting organizers choose who can be presenters in a meeting.</span></span> <span data-ttu-id="56fc6-165">要了解更多信息，请参阅 [更改 Teams 会议的与会者设置](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) 和 [Teams 会议中的角色](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)。</span><span class="sxs-lookup"><span data-stu-id="56fc6-165">To learn more, see [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) and [Roles in a Teams meeting](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).</span></span>

<span data-ttu-id="56fc6-166">目前，只能使用 PowerShell 来配置此策略设置。</span><span class="sxs-lookup"><span data-stu-id="56fc6-166">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="56fc6-167">可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有的 Teams 会议策略。</span><span class="sxs-lookup"><span data-stu-id="56fc6-167">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="56fc6-168">或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建一个新的 Teams 会议策略，并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="56fc6-168">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="56fc6-169">要在 Teams 中指定 **“谁能演示?”** 设置的默认值，请将 **DesignatedPresenterRoleMode** 参数设置为以下之一:</span><span class="sxs-lookup"><span data-stu-id="56fc6-169">To specify the default value of the **Who can present?** setting in Teams, set the **DesignatedPresenterRoleMode** parameter to one of the following:</span></span>

- <span data-ttu-id="56fc6-170">**EveryoneUserOverride**:  所有会议参与者都能成为演示者。</span><span class="sxs-lookup"><span data-stu-id="56fc6-170">**EveryoneUserOverride**:  All meeting participants can be presenters.</span></span> <span data-ttu-id="56fc6-171">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="56fc6-171">This is the default value.</span></span> <span data-ttu-id="56fc6-172">该参数对应 Teams 中的 **“每个人”** 设置。</span><span class="sxs-lookup"><span data-stu-id="56fc6-172">This parameter corresponds to the **Everyone** setting in Teams.</span></span>
- <span data-ttu-id="56fc6-173">**EveryoneInCompanyUserOverride**: 组织中的认证用户，包括客人用户，都能成为演示者。</span><span class="sxs-lookup"><span data-stu-id="56fc6-173">**EveryoneInCompanyUserOverride**: Authenticated users in the organization, including guest users, can be presenters.</span></span> <span data-ttu-id="56fc6-174">此参数对应 Teams 中 **“我的组织中的人员”** 设置。</span><span class="sxs-lookup"><span data-stu-id="56fc6-174">This parameter corresponds to the **People in my organization** setting in Teams.</span></span>
- <span data-ttu-id="56fc6-175">**OrganizerOnlyUserOverride**: 只有会议组织者可以成为演示者，所有其他会议参与者都将指定为与会者。</span><span class="sxs-lookup"><span data-stu-id="56fc6-175">**OrganizerOnlyUserOverride**: Only the meeting organizer can be a presenter and all meeting participants are designated as attendees.</span></span> <span data-ttu-id="56fc6-176">此参数对应 Teams 中的 **“只有我”** 设置。</span><span class="sxs-lookup"><span data-stu-id="56fc6-176">This parameter corresponds to the **Only me** setting in Teams.</span></span>

<span data-ttu-id="56fc6-177">请记住，在设置默认值后，会议组织者仍然可以在 Teams 中更改此设置，并选择谁可以在他们安排的会议中演示。</span><span class="sxs-lookup"><span data-stu-id="56fc6-177">Keep in mind that after you set the default value, meeting organizers can still change this setting in Teams and choose who can present in the meetings that they schedule.</span></span>

## <a name="meeting-attendance-report"></a><span data-ttu-id="56fc6-178">会议出席情况报告</span><span class="sxs-lookup"><span data-stu-id="56fc6-178">Meeting attendance report</span></span>

<span data-ttu-id="56fc6-179">这是按用户策略。</span><span class="sxs-lookup"><span data-stu-id="56fc6-179">This is a per-user policy.</span></span> <span data-ttu-id="56fc6-180">此设置控制会议组织者是否可以下载 [会议出席报告](teams-analytics-and-reports/meeting-attendance-report.md)。</span><span class="sxs-lookup"><span data-stu-id="56fc6-180">This setting controls whether meeting organizers can download the [meeting attendance report](teams-analytics-and-reports/meeting-attendance-report.md).</span></span>

<span data-ttu-id="56fc6-181">目前，只能使用 PowerShell 来配置此策略设置。</span><span class="sxs-lookup"><span data-stu-id="56fc6-181">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="56fc6-182">可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有的 Teams 会议策略。</span><span class="sxs-lookup"><span data-stu-id="56fc6-182">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="56fc6-183">或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建一个新的 Teams 会议策略，并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="56fc6-183">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="56fc6-184">若要启用会议组织者下载会议出席报告，请将 **AllowEngagementReport** 参数设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="56fc6-184">To enable a meeting organizer to download the meeting attendance report, set the **AllowEngagementReport** parameter  to **Enabled**.</span></span> <span data-ttu-id="56fc6-185">启用后，下载报告的选项会显示在 **“参与者”** 窗格中。</span><span class="sxs-lookup"><span data-stu-id="56fc6-185">When enabled, the option to download the report is displayed in the **Participants** pane.</span></span>

<span data-ttu-id="56fc6-186">若要防止会议组织者下载报告，请将该参数设置为 **禁用**。</span><span class="sxs-lookup"><span data-stu-id="56fc6-186">To prevent a meeting organizer from downloading the report, set the parameter to **Disabled**.</span></span> <span data-ttu-id="56fc6-187">默认情况下，该设置是禁用的，并且下载报告的选项不可用。</span><span class="sxs-lookup"><span data-stu-id="56fc6-187">By default, this setting is disabled and the option to download the report isn't available.</span></span>

## <a name="meeting-provider-for-islands-mode"></a><span data-ttu-id="56fc6-188">群岛模式的会议提供商</span><span class="sxs-lookup"><span data-stu-id="56fc6-188">Meeting provider for Islands mode</span></span>

<span data-ttu-id="56fc6-189">这是按用户策略。</span><span class="sxs-lookup"><span data-stu-id="56fc6-189">This is a per-user policy.</span></span> <span data-ttu-id="56fc6-190">此设置可控制 *处于并行模式的用户* 使用哪个 Outlook 会议加载项。</span><span class="sxs-lookup"><span data-stu-id="56fc6-190">This setting controls which Outlook meeting add-in is used for *users who are in Islands mode*.</span></span> <span data-ttu-id="56fc6-191">你可以指定用户是只能使用 Team 会议加载项，还是可同时使用 Teams 会议加载项和 Skype for Business 会议加载项来在 Outlook 中安排会议。</span><span class="sxs-lookup"><span data-stu-id="56fc6-191">You can specify whether users can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook.</span></span>

<span data-ttu-id="56fc6-192">你只能将此策略应用于处于孤岛模式且其 Teams 会议策略中的 **AllowOutlookAddIn** 参数设置为 **True** 的用户。</span><span class="sxs-lookup"><span data-stu-id="56fc6-192">You can only apply this policy to users who are in Islands mode and have the **AllowOutlookAddIn** parameter set to **True** in their Teams meeting policy.</span></span>

<span data-ttu-id="56fc6-193">目前，只能使用 PowerShell 来设置该策略。</span><span class="sxs-lookup"><span data-stu-id="56fc6-193">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="56fc6-194">可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有的 Teams 会议策略。</span><span class="sxs-lookup"><span data-stu-id="56fc6-194">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="56fc6-195">或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建一个新的 Teams 会议策略，并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="56fc6-195">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="56fc6-196">若要指定希望用户可以使用哪种会议加载项，请按以下方式设置 **PreferredMeetingProviderForIslandsMode** 参数:</span><span class="sxs-lookup"><span data-stu-id="56fc6-196">To specify which meeting add-in you want to be available to users, set the **PreferredMeetingProviderForIslandsMode** parameter as follows:</span></span>

- <span data-ttu-id="56fc6-197">将参数设置为 **TeamsAndSfB** 以启用 Outlook 中的 Teams 会议加载项和 Skype for Business 加载项。</span><span class="sxs-lookup"><span data-stu-id="56fc6-197">Set the parameter to **TeamsAndSfB** to enable both the Teams Meeting add-in and Skype for Business add-in in Outlook.</span></span> <span data-ttu-id="56fc6-198">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="56fc6-198">This is the default value.</span></span>
- <span data-ttu-id="56fc6-199">将参数设置为 **Teams**，以便仅启用 Outlook 中的 Teams 会议加载项。</span><span class="sxs-lookup"><span data-stu-id="56fc6-199">Set the parameter to **Teams** to enable only the Teams Meeting add-in in Outlook.</span></span> <span data-ttu-id="56fc6-200">此策略设置可确保所有将来的会议均具有 Teams 会议的加入链接。</span><span class="sxs-lookup"><span data-stu-id="56fc6-200">This policy setting ensures that all future meetings have a Teams meeting join link.</span></span> <span data-ttu-id="56fc6-201">它不能将现有的 Skype for Business 会议加入链接迁移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="56fc6-201">It doesn't migrate existing Skype for Business meeting join links to Teams.</span></span> <span data-ttu-id="56fc6-202">该策略设置不会影响 Skype for Business 中的状态、聊天、PSTN 呼叫或任何其他功能，这意味着用户将继续使用 Skype for Business 的这些功能。</span><span class="sxs-lookup"><span data-stu-id="56fc6-202">This policy setting doesn't affect presence, chat, PSTN calling, or any other capabilities in Skype for Business, which means that users will continue to use Skype for Business for these capabilities.</span></span>

  <span data-ttu-id="56fc6-203">如果将参数设置为 **Teams**，然后切换回 **TeamsAndSfB**，则将启用这两个会议加载项。</span><span class="sxs-lookup"><span data-stu-id="56fc6-203">If you set the parameter to **Teams**, and then switch back to **TeamsAndSfB**, both meeting add-ins are enabled.</span></span> <span data-ttu-id="56fc6-204">但是，请注意，Teams会议加入链接不会迁移到Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="56fc6-204">However, note that existing Teams meeting join links won't be migrated to Skype for Business.</span></span> <span data-ttu-id="56fc6-205">只有在更改后安排的 Skype for Business 会议才会有 Skype for Business 会议加入链接。</span><span class="sxs-lookup"><span data-stu-id="56fc6-205">Only Skype for Business meetings scheduled after the change will have a Skype for Business meeting join link.</span></span>

## <a name="meeting-reactions"></a><span data-ttu-id="56fc6-206">会议回应</span><span class="sxs-lookup"><span data-stu-id="56fc6-206">Meeting reactions</span></span>

<span data-ttu-id="56fc6-207">AllowMeetingReactions 设置只能使用 PowerShell 应用。</span><span class="sxs-lookup"><span data-stu-id="56fc6-207">The AllowMeetingReactions setting can only be applied using PowerShell.</span></span> <span data-ttu-id="56fc6-208">在 Teams 管理中心，没有任何选项可以打开或关闭 AllowMeetingReactions。</span><span class="sxs-lookup"><span data-stu-id="56fc6-208">There is no option to toggle AllowMeetingReactions on or off from the Teams admin center.</span></span>

<span data-ttu-id="56fc6-209">会议回应默认为“关闭”。</span><span class="sxs-lookup"><span data-stu-id="56fc6-209">Meeting reactions are Off by default.</span></span> <span data-ttu-id="56fc6-210">关闭用户的回应，并不意味着用户不能在自己安排的会议中使用回应。</span><span class="sxs-lookup"><span data-stu-id="56fc6-210">Turning off reactions for a user doesn't mean that a user can't use reactions in meetings they schedule.</span></span> <span data-ttu-id="56fc6-211">无论默认设置如何，会议组织者仍然可以从会议选项页面开启回应。</span><span class="sxs-lookup"><span data-stu-id="56fc6-211">The meeting organizer can still turn on reactions from the meeting option page, regardless of the default setting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="56fc6-212">相关主题</span><span class="sxs-lookup"><span data-stu-id="56fc6-212">Related topics</span></span>

- [<span data-ttu-id="56fc6-213">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="56fc6-213">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="56fc6-214">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="56fc6-214">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="56fc6-215">从用户删除 RestrictedAnonymousAccess Teams 会议策略</span><span class="sxs-lookup"><span data-stu-id="56fc6-215">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
