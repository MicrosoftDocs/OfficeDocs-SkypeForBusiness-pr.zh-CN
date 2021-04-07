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
# <a name="meeting-policy-settings---general"></a><span data-ttu-id="9381f-103">会议策略设置 - 常规</span><span class="sxs-lookup"><span data-stu-id="9381f-103">Meeting policy settings - General</span></span>

<span data-ttu-id="9381f-104"><a name="bkgeneral"> </a></span><span class="sxs-lookup"><span data-stu-id="9381f-104"><a name="bkgeneral"> </a></span></span>

<span data-ttu-id="9381f-105">本文介绍 Teams 会议的以下常规策略设置：</span><span class="sxs-lookup"><span data-stu-id="9381f-105">This article describes the following general policy settings for Teams meetings:</span></span>

- [<span data-ttu-id="9381f-106">在频道中允许"现在开会"</span><span class="sxs-lookup"><span data-stu-id="9381f-106">Allow Meet now in channels</span></span>](#allow-meet-now-in-channels)
- [<span data-ttu-id="9381f-107">允许 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="9381f-107">Allow the Outlook add-in</span></span>](#allow-the-outlook-add-in)
- [<span data-ttu-id="9381f-108">允许频道会议安排</span><span class="sxs-lookup"><span data-stu-id="9381f-108">Allow channel meeting scheduling</span></span>](#allow-channel-meeting-scheduling)
- [<span data-ttu-id="9381f-109">允许安排私人会议</span><span class="sxs-lookup"><span data-stu-id="9381f-109">Allow scheduling private meetings</span></span>](#allow-scheduling-private-meetings)
- [<span data-ttu-id="9381f-110">允许现在在私人会议中召开会议</span><span class="sxs-lookup"><span data-stu-id="9381f-110">Allow Meet now in private meetings</span></span>](#allow-meet-now-in-private-meetings)
- [<span data-ttu-id="9381f-111">指定的演示者角色模式</span><span class="sxs-lookup"><span data-stu-id="9381f-111">Designated presenter role mode</span></span>](#designated-presenter-role-mode)
- [<span data-ttu-id="9381f-112">会议出席情况报告</span><span class="sxs-lookup"><span data-stu-id="9381f-112">Meeting attendance report</span></span>](#meeting-attendance-report)
- [<span data-ttu-id="9381f-113">群岛模式的会议提供商</span><span class="sxs-lookup"><span data-stu-id="9381f-113">Meeting provider for Islands mode</span></span>](#meeting-provider-for-islands-mode)

## <a name="allow-meet-now-in-channels"></a><span data-ttu-id="9381f-114">在频道中允许"现在开会"</span><span class="sxs-lookup"><span data-stu-id="9381f-114">Allow Meet now in channels</span></span>

<span data-ttu-id="9381f-115">这是每个用户的策略，在会议启动之前适用。</span><span class="sxs-lookup"><span data-stu-id="9381f-115">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="9381f-116">此设置控制用户是否可以在 Teams 频道中启动临时会议。</span><span class="sxs-lookup"><span data-stu-id="9381f-116">This setting controls whether a user can start an ad hoc meeting in a Teams channel.</span></span> <span data-ttu-id="9381f-117">如果启用此功能，用户可以单击"会议"按钮以在频道中启动临时会议或安排会议。</span><span class="sxs-lookup"><span data-stu-id="9381f-117">If you turn this on, users can click the **Meet** button to start an ad hoc meeting or schedule a meeting in the channel.</span></span> <span data-ttu-id="9381f-118">默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="9381f-118">The default value is True.</span></span>

<span data-ttu-id="9381f-119">[![显示消息下方的"现在开会"图标的屏幕截图 ](media/meeting-policies-meet-now.png)](media/meeting-policies-meet-now.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="9381f-119">[ ![Screenshot showing the Meet now icon below a message](media/meeting-policies-meet-now.png) ](media/meeting-policies-meet-now.png#lightbox)</span></span>

## <a name="allow-the-outlook-add-in"></a><span data-ttu-id="9381f-120">允许 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="9381f-120">Allow the Outlook add-in</span></span>

<span data-ttu-id="9381f-121">这是每个用户的策略，在会议启动之前适用。</span><span class="sxs-lookup"><span data-stu-id="9381f-121">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="9381f-122">此设置控制是否可以在 Outlook 中安排 Teams 会议 (Windows、Mac、Web 和移动) 。</span><span class="sxs-lookup"><span data-stu-id="9381f-122">This setting controls whether Teams meetings can be scheduled from within Outlook (Windows, Mac, web, and mobile).</span></span>

![显示安排新会议的能力的屏幕截图](media/meeting-policies-outlook-add-in.png)

<span data-ttu-id="9381f-124">如果关闭此功能，用户在 Outlook 中创建新会议时无法安排 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="9381f-124">If you turn this off, users are unable to schedule Teams meetings when they create a new meeting in Outlook.</span></span> <span data-ttu-id="9381f-125">例如，在 Outlook on Windows 中，"新建 **Teams** 会议"选项不会显示在功能区中。</span><span class="sxs-lookup"><span data-stu-id="9381f-125">For example, in Outlook on Windows, the **New Teams Meeting** option won't show up in the ribbon.</span></span>

## <a name="allow-channel-meeting-scheduling"></a><span data-ttu-id="9381f-126">允许频道会议安排</span><span class="sxs-lookup"><span data-stu-id="9381f-126">Allow channel meeting scheduling</span></span>

<span data-ttu-id="9381f-127">使用现有的 AllowChannelMeetingScheduling 策略控制可在团队频道日历上创建的事件类型。</span><span class="sxs-lookup"><span data-stu-id="9381f-127">Use the existing AllowChannelMeetingScheduling policy to control the types of events that can be created on the team channel calendars.</span></span> <span data-ttu-id="9381f-128">这是每个用户的策略，在会议启动之前适用。</span><span class="sxs-lookup"><span data-stu-id="9381f-128">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="9381f-129">此设置控制用户是否可以在 Teams 频道中安排会议。</span><span class="sxs-lookup"><span data-stu-id="9381f-129">This setting controls whether users can schedule a meeting in a Teams channel.</span></span> <span data-ttu-id="9381f-130">默认情况下，此设置已打开。</span><span class="sxs-lookup"><span data-stu-id="9381f-130">By default, this setting is turned on.</span></span> 

<span data-ttu-id="9381f-131">如果此策略已关闭，用户将不能创建新的频道会议。</span><span class="sxs-lookup"><span data-stu-id="9381f-131">If this policy is turned off, users will not be able to create new channel meetings.</span></span> <span data-ttu-id="9381f-132">但是，活动的组织者可以编辑现有频道会议。</span><span class="sxs-lookup"><span data-stu-id="9381f-132">However, existing channel meetings can be edited by the organizer of the event.</span></span>

<span data-ttu-id="9381f-133">计划会议将被禁用。</span><span class="sxs-lookup"><span data-stu-id="9381f-133">Schedule a meeting will be disabled.</span></span>

![显示 Teams 中的"安排会议"选项的屏幕截图](media/schedule-meeting-option.png)

<span data-ttu-id="9381f-135">通道选择被禁用。</span><span class="sxs-lookup"><span data-stu-id="9381f-135">Channel selection is disabled.</span></span>

<span data-ttu-id="9381f-136">[![显示用于选择要安排会议频道的日历选项的屏幕截图。 ](media/meeting-policies-select-a-channel-to-meet-in.png)](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="9381f-136">[ ![Screenshot showing the calendar option for selecting a channel that you want to schedule a meeting in.](media/meeting-policies-select-a-channel-to-meet-in.png) ](media/meeting-policies-select-a-channel-to-meet-in.png#lightbox)</span></span>

<span data-ttu-id="9381f-137">在频道帖子页面中，将禁用以下内容：</span><span class="sxs-lookup"><span data-stu-id="9381f-137">In the channel posts page, the following will be disabled:</span></span>

- <span data-ttu-id="9381f-138">**频道答复** 撰写框上的"安排会议"按钮。</span><span class="sxs-lookup"><span data-stu-id="9381f-138">**Schedule a meeting** button on the channel reply compose box.</span></span>
  <span data-ttu-id="9381f-139">![显示用于选择要安排会议频道的日历选项的屏幕截图。](media/schedule-meeting-disabled-in-chat2.png)</span><span class="sxs-lookup"><span data-stu-id="9381f-139">![Screenshot showing the calendar option for selecting a channel in which you want to schedule a meeting.](media/schedule-meeting-disabled-in-chat2.png)</span></span>
  
- <span data-ttu-id="9381f-140">**频道标题上的** "安排会议"按钮。</span><span class="sxs-lookup"><span data-stu-id="9381f-140">**Schedule a meeting** button on the channel header.</span></span>
  <span data-ttu-id="9381f-141">![显示用于选择要通过其安排会议频道的日历选项的屏幕截图。](media/schedule-now-in-header.png)</span><span class="sxs-lookup"><span data-stu-id="9381f-141">![Screenshot showing the calendar option for selecting a channel through which you want to schedule a meeting.](media/schedule-now-in-header.png)</span></span>

<span data-ttu-id="9381f-142">在频道日历中：</span><span class="sxs-lookup"><span data-stu-id="9381f-142">In the channel calendar:</span></span>

- <span data-ttu-id="9381f-143">**频道日历标题** 上的"添加新事件"按钮将被禁用。</span><span class="sxs-lookup"><span data-stu-id="9381f-143">**Add new event** button on channel calendar header will be disabled.</span></span>
  <span data-ttu-id="9381f-144">![显示日历选项的屏幕截图，用于选择使您能够安排会议的频道。](media/add-new-event-disabled.png)</span><span class="sxs-lookup"><span data-stu-id="9381f-144">![Screenshot showing the calendar option for selecting a channel that will enable you to schedule a meeting.](media/add-new-event-disabled.png)</span></span>

- <span data-ttu-id="9381f-145">用户将无法在频道日历上拖动并选择一个时间块来创建频道会议。</span><span class="sxs-lookup"><span data-stu-id="9381f-145">Users will not be able to drag and select a time block on the channel calendar to create a channel meeting.</span></span>

- <span data-ttu-id="9381f-146">用户不能使用键盘快捷方式在频道日历上创建会议。</span><span class="sxs-lookup"><span data-stu-id="9381f-146">Users cannot use Keyboard shortcuts to create a meeting on the channel calendar.</span></span>

<span data-ttu-id="9381f-147">在管理中心：</span><span class="sxs-lookup"><span data-stu-id="9381f-147">In the admin center:</span></span>

<span data-ttu-id="9381f-148">通道日历应用会显示在应用权限策略页面的 **"Microsoft** 应用"部分。</span><span class="sxs-lookup"><span data-stu-id="9381f-148">The channel calendar app will show up in the **Microsoft apps** section on the app permission policies page.</span></span>

![显示 Teams 管理中心的应用权限策略的屏幕截图。](media/manage-microsoft-apps-policy.png)

## <a name="allow-scheduling-private-meetings"></a><span data-ttu-id="9381f-150">允许安排私人会议</span><span class="sxs-lookup"><span data-stu-id="9381f-150">Allow scheduling private meetings</span></span>

<span data-ttu-id="9381f-151">这是每个用户的策略，在会议启动之前适用。</span><span class="sxs-lookup"><span data-stu-id="9381f-151">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="9381f-152">此设置控制用户是否可以在 Teams 中安排私人会议。</span><span class="sxs-lookup"><span data-stu-id="9381f-152">This setting controls whether users can schedule private meetings in Teams.</span></span> <span data-ttu-id="9381f-153">当会议未发布到团队中的频道时，会议是私密的。</span><span class="sxs-lookup"><span data-stu-id="9381f-153">A meeting is private when it's not published to a channel in a team.</span></span>

<span data-ttu-id="9381f-154">请注意，如果 **关闭"允许** 安排私人会议"和"**允许** 频道会议安排"，则Teams 中的用户禁用了"添加必需的与会者"和"添加频道"选项。</span><span class="sxs-lookup"><span data-stu-id="9381f-154">Note that if you turn off **Allow scheduling private meetings** and **Allow channel meeting scheduling**,  the **Add required attendees** and **Add channel** options are disabled for users in Teams.</span></span> <span data-ttu-id="9381f-155">默认情况下，此设置已打开。</span><span class="sxs-lookup"><span data-stu-id="9381f-155">By default, this setting is turned on.</span></span>

## <a name="allow-meet-now-in-private-meetings"></a><span data-ttu-id="9381f-156">允许现在在私人会议中召开会议</span><span class="sxs-lookup"><span data-stu-id="9381f-156">Allow Meet now in private meetings</span></span>

<span data-ttu-id="9381f-157">这是每个用户的策略，在会议启动之前适用。</span><span class="sxs-lookup"><span data-stu-id="9381f-157">This is a per-user policy and applies before a meeting starts.</span></span> <span data-ttu-id="9381f-158">此设置控制用户是否可以启动临时私人会议。</span><span class="sxs-lookup"><span data-stu-id="9381f-158">This setting controls whether a user can start an ad hoc private meeting.</span></span>  <span data-ttu-id="9381f-159">默认情况下，此设置已打开。</span><span class="sxs-lookup"><span data-stu-id="9381f-159">By default, this setting is turned on.</span></span>

## <a name="designated-presenter-role-mode"></a><span data-ttu-id="9381f-160">指定的演示者角色模式</span><span class="sxs-lookup"><span data-stu-id="9381f-160">Designated presenter role mode</span></span>

<span data-ttu-id="9381f-161">这是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="9381f-161">This is a per-user policy.</span></span> <span data-ttu-id="9381f-162">此设置允许您在 Teams 客户端的会议选项中更改"谁可以出席？"**设置的默认值**。</span><span class="sxs-lookup"><span data-stu-id="9381f-162">This setting lets you change the default value of the **Who can present?** setting in **Meeting options** in the Teams client.</span></span> <span data-ttu-id="9381f-163">此策略设置会影响所有会议，包括"现在开会"会议。</span><span class="sxs-lookup"><span data-stu-id="9381f-163">This policy setting affects all meetings, including Meet Now meetings.</span></span>

<span data-ttu-id="9381f-164">" **谁可以演示？"** 设置允许会议组织者选择谁可以是会议中的演示者。</span><span class="sxs-lookup"><span data-stu-id="9381f-164">The **Who can present?** setting lets meeting organizers choose who can be presenters in a meeting.</span></span> <span data-ttu-id="9381f-165">有关详细信息，请参阅更改 [Teams 会议的参与者设置](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) 和 [Teams 会议的角色](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)。</span><span class="sxs-lookup"><span data-stu-id="9381f-165">To learn more, see [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) and [Roles in a Teams meeting](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019).</span></span>

<span data-ttu-id="9381f-166">目前，只能使用 PowerShell 配置此策略设置。</span><span class="sxs-lookup"><span data-stu-id="9381f-166">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="9381f-167">可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有 Teams 会议策略。</span><span class="sxs-lookup"><span data-stu-id="9381f-167">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="9381f-168">或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建新的 Teams 会议策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="9381f-168">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="9381f-169">若要在 Teams 中指定"谁可以出席 **？"** 设置的默认值，将 **SpecifyedPresenterRoleMode** 参数设置为以下参数之一：</span><span class="sxs-lookup"><span data-stu-id="9381f-169">To specify the default value of the **Who can present?** setting in Teams, set the **DesignatedPresenterRoleMode** parameter to one of the following:</span></span>

- <span data-ttu-id="9381f-170">**EveryoneUserOverride：** 所有会议参与者都可以是演示者。</span><span class="sxs-lookup"><span data-stu-id="9381f-170">**EveryoneUserOverride**:  All meeting participants can be presenters.</span></span> <span data-ttu-id="9381f-171">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="9381f-171">This is the default value.</span></span> <span data-ttu-id="9381f-172">此参数对应于 Teams **中的"每个人** "设置。</span><span class="sxs-lookup"><span data-stu-id="9381f-172">This parameter corresponds to the **Everyone** setting in Teams.</span></span>
- <span data-ttu-id="9381f-173">**EveryoneInCompanyUserOverride：** 组织中经过身份验证的用户（包括来宾用户）可以是演示者。</span><span class="sxs-lookup"><span data-stu-id="9381f-173">**EveryoneInCompanyUserOverride**: Authenticated users in the organization, including guest users, can be presenters.</span></span> <span data-ttu-id="9381f-174">此参数对应于 Teams 中的 **"组织人员** "设置。</span><span class="sxs-lookup"><span data-stu-id="9381f-174">This parameter corresponds to the **People in my organization** setting in Teams.</span></span>
- <span data-ttu-id="9381f-175">**组织者OnlyUserOverride：** 只有会议组织者才能是演示者，所有会议参与者都指定为与会者。</span><span class="sxs-lookup"><span data-stu-id="9381f-175">**OrganizerOnlyUserOverride**: Only the meeting organizer can be a presenter and all meeting participants are designated as attendees.</span></span> <span data-ttu-id="9381f-176">此参数对应于 Teams 中的 **"仅我** "设置。</span><span class="sxs-lookup"><span data-stu-id="9381f-176">This parameter corresponds to the **Only me** setting in Teams.</span></span>

<span data-ttu-id="9381f-177">请记住，设置默认值后，会议组织者仍然可以在 Teams 中更改此设置，并选择谁可以在他们安排的会议中出席。</span><span class="sxs-lookup"><span data-stu-id="9381f-177">Keep in mind that after you set the default value, meeting organizers can still change this setting in Teams and choose who can present in the meetings that they schedule.</span></span>

## <a name="meeting-attendance-report"></a><span data-ttu-id="9381f-178">会议出席情况报告</span><span class="sxs-lookup"><span data-stu-id="9381f-178">Meeting attendance report</span></span>

<span data-ttu-id="9381f-179">这是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="9381f-179">This is a per-user policy.</span></span> <span data-ttu-id="9381f-180">此设置控制会议组织者是否可以下载 [会议出席报告](teams-analytics-and-reports/meeting-attendance-report.md)。</span><span class="sxs-lookup"><span data-stu-id="9381f-180">This setting controls whether meeting organizers can download the [meeting attendance report](teams-analytics-and-reports/meeting-attendance-report.md).</span></span>

<span data-ttu-id="9381f-181">目前，只能使用 PowerShell 配置此策略设置。</span><span class="sxs-lookup"><span data-stu-id="9381f-181">Currently, you can only use PowerShell to configure this policy setting.</span></span> <span data-ttu-id="9381f-182">可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有 Teams 会议策略。</span><span class="sxs-lookup"><span data-stu-id="9381f-182">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="9381f-183">或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建新的 Teams 会议策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="9381f-183">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="9381f-184">若要使会议组织者能够下载会议出席情况报告，将 **AllowEngagementReport** 参数设置为"已启用 **"。**</span><span class="sxs-lookup"><span data-stu-id="9381f-184">To enable a meeting organizer to download the meeting attendance report, set the **AllowEngagementReport** parameter  to **Enabled**.</span></span> <span data-ttu-id="9381f-185">启用后，下载报表的选项会显示在"参与者 **"窗格中** 。</span><span class="sxs-lookup"><span data-stu-id="9381f-185">When enabled, the option to download the report is displayed in the **Participants** pane.</span></span>

<span data-ttu-id="9381f-186">若要防止会议组织者下载报告，将 参数设置为"已 **禁用"。**</span><span class="sxs-lookup"><span data-stu-id="9381f-186">To prevent a meeting organizer from downloading the report, set the parameter to **Disabled**.</span></span> <span data-ttu-id="9381f-187">默认情况下，此设置处于禁用状态，并且下载报表的选项不可用。</span><span class="sxs-lookup"><span data-stu-id="9381f-187">By default, this setting is disabled and the option to download the report isn't available.</span></span>

## <a name="meeting-provider-for-islands-mode"></a><span data-ttu-id="9381f-188">群岛模式的会议提供商</span><span class="sxs-lookup"><span data-stu-id="9381f-188">Meeting provider for Islands mode</span></span>

<span data-ttu-id="9381f-189">这是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="9381f-189">This is a per-user policy.</span></span> <span data-ttu-id="9381f-190">此设置控制哪些 Outlook 会议加载项用于位于 *群岛模式 的用户*。</span><span class="sxs-lookup"><span data-stu-id="9381f-190">This setting controls which Outlook meeting add-in is used for *users who are in Islands mode*.</span></span> <span data-ttu-id="9381f-191">你可以指定用户是只能使用 Team 会议加载项，还是可同时使用 Teams 会议加载项和 Skype for Business 会议加载项来在 Outlook 中安排会议。</span><span class="sxs-lookup"><span data-stu-id="9381f-191">You can specify whether users can only use the Teams Meeting add-in or both the Teams Meeting and Skype for Business Meeting add-ins to schedule meetings in Outlook.</span></span>

<span data-ttu-id="9381f-192">你只能将此策略应用于处于孤岛模式且其 Teams 会议策略中的 **AllowOutlookAddIn** 参数设置为 **True** 的用户。</span><span class="sxs-lookup"><span data-stu-id="9381f-192">You can only apply this policy to users who are in Islands mode and have the **AllowOutlookAddIn** parameter set to **True** in their Teams meeting policy.</span></span>

<span data-ttu-id="9381f-193">目前，只能使用 PowerShell 设置此策略。</span><span class="sxs-lookup"><span data-stu-id="9381f-193">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="9381f-194">可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有 Teams 会议策略。</span><span class="sxs-lookup"><span data-stu-id="9381f-194">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="9381f-195">或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建新的 Teams 会议策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="9381f-195">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet and assign it to users.</span></span>

<span data-ttu-id="9381f-196">若要指定希望哪些会议加载项可供用户使用，请设置 **PreferredMeetingProviderForIslandsMode** 参数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9381f-196">To specify which meeting add-in you want to be available to users, set the **PreferredMeetingProviderForIslandsMode** parameter as follows:</span></span>

- <span data-ttu-id="9381f-197">将 参数设置为 **TeamsAndSfB，** 以在 Outlook 中同时启用 Teams 会议加载项和 Skype for Business 加载项。</span><span class="sxs-lookup"><span data-stu-id="9381f-197">Set the parameter to **TeamsAndSfB** to enable both the Teams Meeting add-in and Skype for Business add-in in Outlook.</span></span> <span data-ttu-id="9381f-198">此值为默认值。</span><span class="sxs-lookup"><span data-stu-id="9381f-198">This is the default value.</span></span>
- <span data-ttu-id="9381f-199">将 参数设置为 **Teams，** 以在 Outlook 中仅启用 Teams 会议加载项。</span><span class="sxs-lookup"><span data-stu-id="9381f-199">Set the parameter to **Teams** to enable only the Teams Meeting add-in in Outlook.</span></span> <span data-ttu-id="9381f-200">此策略设置可确保所有将来的会议都有 Teams 会议加入链接。</span><span class="sxs-lookup"><span data-stu-id="9381f-200">This policy setting ensures that all future meetings have a Teams meeting join link.</span></span> <span data-ttu-id="9381f-201">它不会将现有 Skype for Business 会议加入链接迁移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="9381f-201">It doesn't migrate existing Skype for Business meeting join links to Teams.</span></span> <span data-ttu-id="9381f-202">此策略设置不会影响 Skype for Business 中的状态、聊天、PSTN 呼叫或其他任何功能，这意味着用户将继续使用 Skype for Business 实现这些功能。</span><span class="sxs-lookup"><span data-stu-id="9381f-202">This policy setting doesn't affect presence, chat, PSTN calling, or any other capabilities in Skype for Business, which means that users will continue to use Skype for Business for these capabilities.</span></span>

  <span data-ttu-id="9381f-203">如果将 参数设置为 **Teams，** 然后切换回 **TeamsAndSfB，** 则两个会议加载项都已启用。</span><span class="sxs-lookup"><span data-stu-id="9381f-203">If you set the parameter to **Teams**, and then switch back to **TeamsAndSfB**, both meeting add-ins are enabled.</span></span> <span data-ttu-id="9381f-204">但是，请注意，现有 Teams 会议加入链接不会迁移到 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="9381f-204">However, note that existing Teams meeting join links won't be migrated to Skype for Business.</span></span> <span data-ttu-id="9381f-205">只有更改后安排的 Skype for Business 会议才具有 Skype for Business 会议加入链接。</span><span class="sxs-lookup"><span data-stu-id="9381f-205">Only Skype for Business meetings scheduled after the change will have a Skype for Business meeting join link.</span></span>

## <a name="meeting-reactions"></a><span data-ttu-id="9381f-206">会议回应</span><span class="sxs-lookup"><span data-stu-id="9381f-206">Meeting reactions</span></span>

<span data-ttu-id="9381f-207">AllowMeetingReactions 设置只能使用 PowerShell 应用。</span><span class="sxs-lookup"><span data-stu-id="9381f-207">The AllowMeetingReactions setting can only be applied using PowerShell.</span></span> <span data-ttu-id="9381f-208">无法从 Teams 管理中心打开或关闭 AllowMeetingReactions。</span><span class="sxs-lookup"><span data-stu-id="9381f-208">There is no option to toggle AllowMeetingReactions on or off from the Teams admin center.</span></span>

<span data-ttu-id="9381f-209">会议回应默认为"关闭"。</span><span class="sxs-lookup"><span data-stu-id="9381f-209">Meeting reactions are Off by default.</span></span> <span data-ttu-id="9381f-210">为用户关闭回应并不意味着用户无法安排的会议使用回应。</span><span class="sxs-lookup"><span data-stu-id="9381f-210">Turning off reactions for a user doesn't mean that a user can't use reactions in meetings they schedule.</span></span> <span data-ttu-id="9381f-211">无论默认设置如何，会议组织者仍可从会议选项页面打开回应。</span><span class="sxs-lookup"><span data-stu-id="9381f-211">The meeting organizer can still turn on reactions from the meeting option page, regardless of the default setting.</span></span>


## <a name="related-topics"></a><span data-ttu-id="9381f-212">相关主题</span><span class="sxs-lookup"><span data-stu-id="9381f-212">Related topics</span></span>

- [<span data-ttu-id="9381f-213">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="9381f-213">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="9381f-214">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="9381f-214">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="9381f-215">从用户中删除 RestrictedAnonymousAccess Teams 会议策略</span><span class="sxs-lookup"><span data-stu-id="9381f-215">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
