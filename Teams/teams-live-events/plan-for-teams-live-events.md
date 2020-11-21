---
title: 在 Microsoft Teams 中规划实时事件
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/19/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
f1.keywords:
- NOCSH
localization_priority: Priority
ms.collection:
- M365-collaboration
- m365initiative-meetings
- enabler-strategic
search.appverid: MET150
description: 在本文中，你将了解在 Microsoft Teams 中设置实时事件之前要考虑的因素。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 45f7d629b53a8f20ed9fb072d5dc8812a680d0c4
ms.sourcegitcommit: 25d14b501c0d62b8b77bbf03dac490f5bc1969bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "49372246"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a><span data-ttu-id="fb642-103">在 Microsoft Teams 中规划实时事件</span><span class="sxs-lookup"><span data-stu-id="fb642-103">Plan for live events in Microsoft Teams</span></span>

<span data-ttu-id="fb642-104">计划 Teams 实时事件时，若要在组织中召开大型会议，则在开始设置之前，需要考虑几个因素。</span><span class="sxs-lookup"><span data-stu-id="fb642-104">When you're planning Teams live events to hold large meetings in your organization, there are several factors that you need to consider before starting the setup.</span></span>

> [!Note]
> <span data-ttu-id="fb642-p101">有关不同平台上的 Teams 实时事件的详细信息，请参阅 [Teams 功能（按平台）](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。请参阅[让你的组织做好准备](../prepare-network.md)，了解 Teams 直播活动的带宽要求。</span><span class="sxs-lookup"><span data-stu-id="fb642-p101">For details about Teams live events on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3). See [prepare your organization](../prepare-network.md) to learn about bandwidth requirements for Teams live events.</span></span>

## <a name="who-can-attend-create-and-schedule-live-events"></a><span data-ttu-id="fb642-107">谁可以参加、创建和计划实时事件</span><span class="sxs-lookup"><span data-stu-id="fb642-107">Who can attend, create, and schedule live events</span></span>

<span data-ttu-id="fb642-p102">任何人都可以在没有许可证的情况下参加实时事件。请阅读[管理员快速入门 - 会议和实时事件](../quick-start-meetings-live-events.md)。</span><span class="sxs-lookup"><span data-stu-id="fb642-p102">Anyone can attend a live event without a license. Read [Admin quick start - Meetings and live events](../quick-start-meetings-live-events.md).</span></span>

<span data-ttu-id="fb642-110">若要安排 Teams 实时事件，用户必须满足以下前提条件。</span><span class="sxs-lookup"><span data-stu-id="fb642-110">The following prerequisites are required for the user to schedule a Teams live event.</span></span>

<span data-ttu-id="fb642-111">以下是制作或呈现 Teams 现场活动必须分配的许可证：</span><span class="sxs-lookup"><span data-stu-id="fb642-111">Here are the licenses that must be assigned to produce or present a Teams live event:</span></span>  

- <span data-ttu-id="fb642-p103">Microsoft 或 Office 365 企业版 E1、E3 或 E5 许可证，或 Office 365 教育版 A3 或 A5 许可证。此要求的例外情况是：如果满足 [来宾用户](plan-for-teams-live-events.md#guest-to-present) 的其他条件，来宾用户无需许可证即可出席。</span><span class="sxs-lookup"><span data-stu-id="fb642-p103">A Microsoft or Office 365 Enterprise E1, E3, or E5 license or an Office 365 Education A3 or A5 license. The exception to this requirement is guest users can present without a license if the other criteria for [guest users](plan-for-teams-live-events.md#guest-to-present) is met.</span></span>
- <span data-ttu-id="fb642-114">Microsoft Teams 许可证 - 包含在第一个项目符号列出的许可证中。</span><span class="sxs-lookup"><span data-stu-id="fb642-114">A Microsoft Teams license - this is included in the licenses listed in the first bullet.</span></span>
- <span data-ttu-id="fb642-115">如果你计划将内容共享到外部应用或设备，则需要 Microsoft Stream 许可证；请参阅 [Microsoft Stream 许可证](https://docs.microsoft.com/stream/license-overview)。</span><span class="sxs-lookup"><span data-stu-id="fb642-115">A Microsoft Stream license - is required if you are planning to share the content to an external app or device; see [Microsoft Stream licensing](https://docs.microsoft.com/stream/license-overview).</span></span>

  <span data-ttu-id="fb642-p104">如果你希望用户仅进行录制和下载录制的内容，那么这些用户无需拥有 Microsoft Stream 许可证。这意味着录制的内容不会存储在 Microsoft Stream 中，而是存储在 Azure 媒体服务 (AMS) 中，且存储 180 天后被删除。目前，管理员无法控制或管理此设置来包含删除这些内容的功能。</span><span class="sxs-lookup"><span data-stu-id="fb642-p104">Users won't need a Microsoft Stream license assigned if you want users to only record and download the recordings. This will mean that the recordings aren't stored in Microsoft Stream but are instead stored in Azure Media Services (AMS) with a 180-day limit before it's deleted. It's not something at this point that an admin can control or manage to include the ability to delete it.</span></span>

>[!Note]
> <span data-ttu-id="fb642-p105">将会议录制从 Microsoft Stream 改为 [OneDrive for Business 和 SharePoint](../tmr-meeting-recording-change.md) 将是一种分阶段的方法。在发布时，你将能够选择加入此体验，如果想继续使用 Stream，则在 11 月你必须选择退出，在 2021 年初的某个时候，我们将要求所有客户使用 OneDrive for Business 和 SharePoint 进行会议录制。</span><span class="sxs-lookup"><span data-stu-id="fb642-p105">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to OneDrive for Business and SharePoint for meeting recordings.</span></span>

> [!NOTE]
> <span data-ttu-id="fb642-121">目前，没有任何 Microsoft 365 小型企业版计划可用于创建和保留 Teams 实时事件。</span><span class="sxs-lookup"><span data-stu-id="fb642-121">At this time there aren't any Microsoft 365 Small Business plans that can be used to create and hold Teams live events.</span></span>

<span data-ttu-id="fb642-122">注意，Microsoft 365 或 Office 365 许可证是经过身份验证的用户参见实时事件的必要条件，但是此要求取决于所使用的制作方式：</span><span class="sxs-lookup"><span data-stu-id="fb642-122">It's important to know that a Microsoft 365 or Office 365 license is required to participate in a live event as an authenticated user, but this requirement depends on the production method used:</span></span>

- <span data-ttu-id="fb642-123">**使用 Teams 制作的事件**  必须为用户分配 Teams 许可证。</span><span class="sxs-lookup"><span data-stu-id="fb642-123">**For events produced in Teams**  The user must be assigned a Teams license.</span></span>
- <span data-ttu-id="fb642-124">**使用外部应用程序或设备制作的事件** 必须向该用户分配 Stream 许可证。</span><span class="sxs-lookup"><span data-stu-id="fb642-124">**For events produced with an external app or device** The user must be assigned a Stream license.</span></span>

> [!NOTE]
> <span data-ttu-id="fb642-125">“Teams 实时活动”现在可为美国政府云社区（GCC）组织提供。</span><span class="sxs-lookup"><span data-stu-id="fb642-125">Teams live events is now available for US Government Cloud Community (GCC) organizations.</span></span>

<span data-ttu-id="fb642-126">有关许可的详细信息，请参阅 [Microsoft Teams 附加许可](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)。</span><span class="sxs-lookup"><span data-stu-id="fb642-126">For more information about licensing, see [Microsoft Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

<span data-ttu-id="fb642-127">用户必须：</span><span class="sxs-lookup"><span data-stu-id="fb642-127">The user must have:</span></span>

- <span data-ttu-id="fb642-128">Teams 中已启用私人会议安排（*TeamsMeetingPolicy -AllowPrivateMeetingScheduling 参数 = True*）。</span><span class="sxs-lookup"><span data-stu-id="fb642-128">Private meeting scheduling in Teams enabled (*The TeamsMeetingPolicy -AllowPrivateMeetingScheduling parameter = True*).</span></span>
- <span data-ttu-id="fb642-129">Teams 会议中已启用视频共享（*TeamsMeetingPolicy -AllowIPVideo 参数 = True*）。</span><span class="sxs-lookup"><span data-stu-id="fb642-129">Video sharing enabled in Teams meetings (*The TeamsMeetingPolicy -AllowIPVideo parameter = True*).</span></span>
- <span data-ttu-id="fb642-130">Teams 会议中启用屏幕共享（*TeamsMeetingPolicy -ScreenSharingMode parameter = EntireScreen*）。</span><span class="sxs-lookup"><span data-stu-id="fb642-130">Screen sharing enabled in Teams meetings (*The TeamsMeetingPolicy -ScreenSharingMode parameter = EntireScreen*).</span></span>
- <span data-ttu-id="fb642-131">Teams 中启用实时会议安排（*TeamsMeetingBroadcastPolicy -AllowBroadcastScheduling 参数 = True*）。</span><span class="sxs-lookup"><span data-stu-id="fb642-131">Live event scheduling in Teams enabled (*The TeamsMeetingBroadcastPolicy -AllowBroadcastScheduling parameter = True*).</span></span>
- <span data-ttu-id="fb642-132">使用 Stream 创建实时事件的权限（适用于外部应用或设备制作）。</span><span class="sxs-lookup"><span data-stu-id="fb642-132">Permissions to create live events in Stream (for external app or device production).</span></span>
- <span data-ttu-id="fb642-133">配置了共存模式，以能够安排 Teams 会议（*并行、会议优先或仅 Teams*）。</span><span class="sxs-lookup"><span data-stu-id="fb642-133">Coexistence mode configured to be able to schedule Teams meetings (*Islands, Meeting First, or Teams Only*).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb642-134">未经身份验证的匿名用户不能被邀请为 Teams 实时事件中的“制作者”或“演示者”。</span><span class="sxs-lookup"><span data-stu-id="fb642-134">Non-authenticated anonymous users can't be invited as producers or presenters in Teams live events.</span></span>

### <a name="guest-to-present"></a>[<span data-ttu-id="fb642-135">出席来宾</span><span class="sxs-lookup"><span data-stu-id="fb642-135">Guest to present</span></span>](#guest-to-present)

<span data-ttu-id="fb642-136">若要让来宾出席直播活动，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="fb642-136">For a guest to present in a live event, do the following:</span></span>

1. <span data-ttu-id="fb642-137">[将该用户作为来宾添加到团队](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。</span><span class="sxs-lookup"><span data-stu-id="fb642-137">[Add the user as a guest to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span>
2. <span data-ttu-id="fb642-138">让该用户接受来宾邀请并加入团队。</span><span class="sxs-lookup"><span data-stu-id="fb642-138">Have the user accept the guest invitation and join the team.</span></span>
3. <span data-ttu-id="fb642-139">[安排直播活动并将来宾添加到活动组](https://support.microsoft.com/article/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)。</span><span class="sxs-lookup"><span data-stu-id="fb642-139">[Schedule the live event and add the guest to your event group](https://support.microsoft.com/article/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2).</span></span>

<span data-ttu-id="fb642-p106">作为最佳做法，我们建议你为直播活动的制作者和演示者创建一个频道，以便他们可以在活动前聊天和共享信息。没有 Microsoft 365 凭据的来宾将无法在 Teams 中看到日历。为便于用户加入活动，制作者可将活动链接发布到相应频道。演示者随后可以打开 Teams，转到该频道，然后单击链接以加入该活动。</span><span class="sxs-lookup"><span data-stu-id="fb642-p106">As a best practice, we recommend that you create a channel for producers and presenters of the live event so they can chat and share information before the event. Guests who don't have Microsoft 365 credentials won't see the Calendar in Teams. To make it easy for them to join the event, producers can post the event link to the channel. Presenters can then open Teams, go to the channel, and then click the link to join the event.</span></span>

## <a name="who-can-watch-live-events"></a><span data-ttu-id="fb642-144">谁可以观看实时事件</span><span class="sxs-lookup"><span data-stu-id="fb642-144">Who can watch live events</span></span>

| <span data-ttu-id="fb642-145">与会者可见性</span><span class="sxs-lookup"><span data-stu-id="fb642-145">Attendee visibility</span></span> | <span data-ttu-id="fb642-146">Teams 制作</span><span class="sxs-lookup"><span data-stu-id="fb642-146">Teams production</span></span> | <span data-ttu-id="fb642-147">外部应用或设备制作</span><span class="sxs-lookup"><span data-stu-id="fb642-147">External app or device production</span></span> |
|------------------------------|-----------------|----------------------|
|<span data-ttu-id="fb642-148">公共（匿名用户）</span><span class="sxs-lookup"><span data-stu-id="fb642-148">Public (anonymous users)</span></span>      |  <span data-ttu-id="fb642-149">是</span><span class="sxs-lookup"><span data-stu-id="fb642-149">Yes</span></span>            |  <span data-ttu-id="fb642-150">否</span><span class="sxs-lookup"><span data-stu-id="fb642-150">No</span></span>                  |
|<span data-ttu-id="fb642-151">来宾用户</span><span class="sxs-lookup"><span data-stu-id="fb642-151">Guest users</span></span>                   |  <span data-ttu-id="fb642-152">是</span><span class="sxs-lookup"><span data-stu-id="fb642-152">Yes</span></span>            |  <span data-ttu-id="fb642-153">否</span><span class="sxs-lookup"><span data-stu-id="fb642-153">No</span></span>                  |
|<span data-ttu-id="fb642-154">外部访问（联盟）公司中的任何人</span><span class="sxs-lookup"><span data-stu-id="fb642-154">Everyone in external access (federation) company</span></span> |  <span data-ttu-id="fb642-155">是<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fb642-155">Yes<sup>1</sup></span></span>|  <span data-ttu-id="fb642-156">否</span><span class="sxs-lookup"><span data-stu-id="fb642-156">No</span></span>                  |
|<span data-ttu-id="fb642-157">公司中的所有人</span><span class="sxs-lookup"><span data-stu-id="fb642-157">Everyone in company</span></span>           |  <span data-ttu-id="fb642-158">是</span><span class="sxs-lookup"><span data-stu-id="fb642-158">Yes</span></span>            |  <span data-ttu-id="fb642-159">是</span><span class="sxs-lookup"><span data-stu-id="fb642-159">Yes</span></span>                 |
|<span data-ttu-id="fb642-160">指定组/人员</span><span class="sxs-lookup"><span data-stu-id="fb642-160">Specific groups / people</span></span>      |  <span data-ttu-id="fb642-161">是</span><span class="sxs-lookup"><span data-stu-id="fb642-161">Yes</span></span>            |  <span data-ttu-id="fb642-162">是</span><span class="sxs-lookup"><span data-stu-id="fb642-162">Yes</span></span>                 |

<span data-ttu-id="fb642-163"><sup>1</sup>只能通过“人员和组”邀请外部访问（联盟）与会者。</span><span class="sxs-lookup"><span data-stu-id="fb642-163"><sup>1</sup> External access (federation) attendees can only be invited through People & Group</span></span> <br>

## <a name="teams-live-events-and-skype-meeting-broadcast"></a><span data-ttu-id="fb642-164">Teams 实时事件和Skype 会议直播</span><span class="sxs-lookup"><span data-stu-id="fb642-164">Teams live events and Skype Meeting Broadcast</span></span>

<span data-ttu-id="fb642-165">下表突出显示了实时事件中提供的核心功能以及区别 Skype 会议直播的方式。</span><span class="sxs-lookup"><span data-stu-id="fb642-165">The following table highlights core capabilities and features offered in live events and how they differ from Skype Meeting Broadcast.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb642-166">**Microsoft 365 实时事件限制的增加**</span><span class="sxs-lookup"><span data-stu-id="fb642-166">**Microsoft 365 live event limit increases**</span></span>
>
> <span data-ttu-id="fb642-167">**为帮助支持我们的客户，从 2021 年 1 月 1 日起，我们将为 Teams、Stream 和 Yammer 中托管的直播活动扩展临时人数上限，包括**：</span><span class="sxs-lookup"><span data-stu-id="fb642-167">**To help support our customers, through January 1, 2021, we will extend temporary limit increases for live events hosted in Teams, Stream, and Yammer, including**:</span></span>
>
>- <span data-ttu-id="fb642-168">每场活动最多可容纳 2 万名参考者</span><span class="sxs-lookup"><span data-stu-id="fb642-168">Up to 20,000 attendees per event</span></span>
>- <span data-ttu-id="fb642-169">每个 Teams 租户最多可同时举行 50 场活动</span><span class="sxs-lookup"><span data-stu-id="fb642-169">Up to 50 simultaneous events per Teams tenant</span></span>
>- <span data-ttu-id="fb642-170">每次直播最多持续 16 个小时</span><span class="sxs-lookup"><span data-stu-id="fb642-170">Up to 16 hours per broadcast</span></span>
>
> <span data-ttu-id="fb642-p107">此外，可通过 Microsoft 365 实时事件辅助计划来安排最多有 10 万名与会者的实时事件。团队将评估每个请求，并与你确定可用选项。[了解详情](https://aka.ms/Stream/Blog/LiveEventOptions)。**2021 年 1 月 1 日后，要提高上述人数上限的客户需购买 [高级通信加载项](../teams-add-on-licensing/advanced-communications.md)。**</span><span class="sxs-lookup"><span data-stu-id="fb642-p107">Additionally, live events with up to 100,000 attendees can be planned through the Microsoft 365 live events assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions). **After January 1, 2021, customers who need these limit increases will be required to purchase the [Advanced Communications add-on](../teams-add-on-licensing/advanced-communications.md).**</span></span>

| <span data-ttu-id="fb642-175">功能</span><span class="sxs-lookup"><span data-stu-id="fb642-175">Capability</span></span> | <span data-ttu-id="fb642-176">Skype 会议直播</span><span class="sxs-lookup"><span data-stu-id="fb642-176">Skype Meeting Broadcast</span></span> | <span data-ttu-id="fb642-177">在 Teams 中制作的事件</span><span class="sxs-lookup"><span data-stu-id="fb642-177">Events produced in Teams</span></span> | <span data-ttu-id="fb642-178">使用外部应用或设备制作的事件</span><span class="sxs-lookup"><span data-stu-id="fb642-178">Events produced in external app or device</span></span> |
|---------|---------|---------|---------|
|<span data-ttu-id="fb642-179">最大受众规模</span><span class="sxs-lookup"><span data-stu-id="fb642-179">Maximum audience size</span></span> |<span data-ttu-id="fb642-180">10,000 名与会者</span><span class="sxs-lookup"><span data-stu-id="fb642-180">10,000 attendees</span></span> |<span data-ttu-id="fb642-181">10,000 名与会者<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fb642-181">10,000 attendees<sup>1</sup></span></span> |<span data-ttu-id="fb642-182">10,000 名与会者<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fb642-182">10,000 attendees<sup>1</sup></span></span> |
|<span data-ttu-id="fb642-183">实时事件最大持续时间</span><span class="sxs-lookup"><span data-stu-id="fb642-183">Maximum duration of live event</span></span> |<span data-ttu-id="fb642-184">4 小时</span><span class="sxs-lookup"><span data-stu-id="fb642-184">4 hours</span></span> |<span data-ttu-id="fb642-185">4 小时</span><span class="sxs-lookup"><span data-stu-id="fb642-185">4 hours</span></span> |<span data-ttu-id="fb642-186">4 小时</span><span class="sxs-lookup"><span data-stu-id="fb642-186">4 hours</span></span> |
|<span data-ttu-id="fb642-187">现场活动中演示者和制作者最大数量</span><span class="sxs-lookup"><span data-stu-id="fb642-187">Maximum number of presenters and producers in a live event</span></span> |<span data-ttu-id="fb642-188">10 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="fb642-188">10 <sup>2</sup></span></span> |<span data-ttu-id="fb642-189">10 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="fb642-189">10 <sup>2</sup></span></span> |<span data-ttu-id="fb642-190">10 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="fb642-190">10 <sup>2</sup></span></span> |
|<span data-ttu-id="fb642-191">每个 Microsoft 365 或 Office 365 组织的最大并发实时事件数量</span><span class="sxs-lookup"><span data-stu-id="fb642-191">Maximum number of concurrent live events per Microsoft 365 or Office 365 organization</span></span> |<span data-ttu-id="fb642-192">15</span><span class="sxs-lookup"><span data-stu-id="fb642-192">15</span></span>  | <span data-ttu-id="fb642-193">15</span><span class="sxs-lookup"><span data-stu-id="fb642-193">15</span></span>  | <span data-ttu-id="fb642-194">15</span><span class="sxs-lookup"><span data-stu-id="fb642-194">15</span></span>  |
|<span data-ttu-id="fb642-195">创建实时事件</span><span class="sxs-lookup"><span data-stu-id="fb642-195">Live event creation</span></span> |   <span data-ttu-id="fb642-196">Skype 会议直播门户</span><span class="sxs-lookup"><span data-stu-id="fb642-196">Skype Meeting Broadcast Portal</span></span> |<span data-ttu-id="fb642-197">团队、Yammer （通过 Teams）</span><span class="sxs-lookup"><span data-stu-id="fb642-197">Teams, Yammer via Teams</span></span> | <span data-ttu-id="fb642-198">Teams、Yammer （通过团队），Stream</span><span class="sxs-lookup"><span data-stu-id="fb642-198">Teams, Yammer via Teams, Stream</span></span> |
|<span data-ttu-id="fb642-199">受众参与 – Yammer</span><span class="sxs-lookup"><span data-stu-id="fb642-199">Audience engagement – Yammer</span></span> |<span data-ttu-id="fb642-200">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fb642-200">&#x2714;</span></span> |<span data-ttu-id="fb642-201">&#x2714;（集成体验）</span><span class="sxs-lookup"><span data-stu-id="fb642-201">&#x2714; (integrated experience)</span></span> |<span data-ttu-id="fb642-202">&#x2714;（集成体验）</span><span class="sxs-lookup"><span data-stu-id="fb642-202">&#x2714; (integrated experience)</span></span> |
|<span data-ttu-id="fb642-203">受众参与 – 已审核问答</span><span class="sxs-lookup"><span data-stu-id="fb642-203">Audience engagement – Moderated Q & A</span></span> |<span data-ttu-id="fb642-204">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fb642-204">&#x2714;</span></span>  |<span data-ttu-id="fb642-205">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fb642-205">&#x2714;</span></span> |<span data-ttu-id="fb642-206">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fb642-206">&#x2714;</span></span> |
|<span data-ttu-id="fb642-207">Windows 制作者客户端</span><span class="sxs-lookup"><span data-stu-id="fb642-207">Producer client on Windows</span></span> |<span data-ttu-id="fb642-208">&#x2714; (Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="fb642-208">&#x2714; (Skype for Business)</span></span> |<span data-ttu-id="fb642-209">&#x2714; (Teams)</span><span class="sxs-lookup"><span data-stu-id="fb642-209">&#x2714; (Teams)</span></span> |<span data-ttu-id="fb642-210">&#x2714; （Stream、Teams （通过嵌入 Stream））</span><span class="sxs-lookup"><span data-stu-id="fb642-210">&#x2714; (Stream, Teams via Stream Embed)</span></span> |
|<span data-ttu-id="fb642-211">Mac 制作者客户端</span><span class="sxs-lookup"><span data-stu-id="fb642-211">Producer client on Mac</span></span> |<span data-ttu-id="fb642-212">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="fb642-212">&#x274C;</span></span>  | <span data-ttu-id="fb642-213">&#x2714; (Teams)</span><span class="sxs-lookup"><span data-stu-id="fb642-213">&#x2714; (Teams)</span></span> |<span data-ttu-id="fb642-214">&#x2714; （Stream、Teams （通过嵌入 Stream））</span><span class="sxs-lookup"><span data-stu-id="fb642-214">&#x2714; (Stream, Teams via Stream Embed)</span></span> |
|<span data-ttu-id="fb642-215">制作者用户界面参与者计数</span><span class="sxs-lookup"><span data-stu-id="fb642-215">Attendee count in Producer UI</span></span> |<span data-ttu-id="fb642-216">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="fb642-216">&#x274C;</span></span>  |<span data-ttu-id="fb642-217">&#x2714; (Teams)</span><span class="sxs-lookup"><span data-stu-id="fb642-217">&#x2714; (Teams)</span></span> |<span data-ttu-id="fb642-218">&#x2714; （Stream、Teams （通过嵌入 Stream））</span><span class="sxs-lookup"><span data-stu-id="fb642-218">&#x2714; (Stream, Teams via Stream Embed)</span></span> |
|<span data-ttu-id="fb642-219">允许多个演示者</span><span class="sxs-lookup"><span data-stu-id="fb642-219">Allows multiple presenters</span></span> |<span data-ttu-id="fb642-220">&#x2714; (Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="fb642-220">&#x2714; (Skype for Business)</span></span> |<span data-ttu-id="fb642-221">&#x2714; (Teams)</span><span class="sxs-lookup"><span data-stu-id="fb642-221">&#x2714; (Teams)</span></span> |<span data-ttu-id="fb642-222">不适用</span><span class="sxs-lookup"><span data-stu-id="fb642-222">N/A</span></span>  |
|<span data-ttu-id="fb642-223">会议期间邀请演示者</span><span class="sxs-lookup"><span data-stu-id="fb642-223">Invite a presenter during the meeting</span></span> |<span data-ttu-id="fb642-224">&#x2714; (Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="fb642-224">&#x2714; (Skype for Business)</span></span> |<span data-ttu-id="fb642-225">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="fb642-225">&#x274C;</span></span> |<span data-ttu-id="fb642-226">不适用</span><span class="sxs-lookup"><span data-stu-id="fb642-226">N/A</span></span> |
|<span data-ttu-id="fb642-227">演示者通过 Web 和移动设备加入</span><span class="sxs-lookup"><span data-stu-id="fb642-227">Presenter join on Web and Mobile</span></span> |<span data-ttu-id="fb642-228">&#x2714; (Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="fb642-228">&#x2714; (Skype for Business)</span></span>  |<span data-ttu-id="fb642-229">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="fb642-229">&#x274C;</span></span> |<span data-ttu-id="fb642-230">不适用</span><span class="sxs-lookup"><span data-stu-id="fb642-230">N/A</span></span> |
|<span data-ttu-id="fb642-231">外部访问（联盟）和来宾演示者/与会者</span><span class="sxs-lookup"><span data-stu-id="fb642-231">External access (federation) & Guest presenters/attendees</span></span> |<span data-ttu-id="fb642-232">&#x2714; (Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="fb642-232">&#x2714; (Skype for Business)</span></span>  |  <span data-ttu-id="fb642-233">&#x2714; (Teams)</span><span class="sxs-lookup"><span data-stu-id="fb642-233">&#x2714; (Teams)</span></span> |<span data-ttu-id="fb642-234">不适用</span><span class="sxs-lookup"><span data-stu-id="fb642-234">N/A</span></span> |
|<span data-ttu-id="fb642-235">演示者 – PSTN 接入</span><span class="sxs-lookup"><span data-stu-id="fb642-235">Presenter – PSTN access</span></span> |<span data-ttu-id="fb642-236">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="fb642-236">&#x274C;</span></span> |<span data-ttu-id="fb642-237">&#x2714; (Teams)</span><span class="sxs-lookup"><span data-stu-id="fb642-237">&#x2714; (Teams)</span></span> |<span data-ttu-id="fb642-238">不适用</span><span class="sxs-lookup"><span data-stu-id="fb642-238">N/A</span></span> |
|<span data-ttu-id="fb642-239">演示屏幕</span><span class="sxs-lookup"><span data-stu-id="fb642-239">Present a screen</span></span> |<span data-ttu-id="fb642-240">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="fb642-240">&#x274C;</span></span> |<span data-ttu-id="fb642-241">&#x2714; (Teams)</span><span class="sxs-lookup"><span data-stu-id="fb642-241">&#x2714; (Teams)</span></span> |<span data-ttu-id="fb642-242">不适用</span><span class="sxs-lookup"><span data-stu-id="fb642-242">N/A</span></span> |
|<span data-ttu-id="fb642-243">在 Windows 上共享系统音频（仅在屏幕共享时可用）</span><span class="sxs-lookup"><span data-stu-id="fb642-243">Share system audio on Windows (available only when screen sharing)</span></span>|<span data-ttu-id="fb642-244">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="fb642-244">&#x274C;</span></span> |<span data-ttu-id="fb642-245">&#x2714; (Teams)</span><span class="sxs-lookup"><span data-stu-id="fb642-245">&#x2714; (Teams)</span></span> |<span data-ttu-id="fb642-246">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fb642-246">&#x2714;</span></span> |
|<span data-ttu-id="fb642-247">演示 PowerPoint （PPT 共享）</span><span class="sxs-lookup"><span data-stu-id="fb642-247">Present a PowerPoint (PPT sharing)</span></span> |<span data-ttu-id="fb642-248">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fb642-248">&#x2714;</span></span> |<span data-ttu-id="fb642-249">&#x274C;（通过屏幕共享缓解）</span><span class="sxs-lookup"><span data-stu-id="fb642-249">&#x274C; (mitigated via screen sharing)</span></span> |<span data-ttu-id="fb642-250">不适用</span><span class="sxs-lookup"><span data-stu-id="fb642-250">N/A</span></span> |
|<span data-ttu-id="fb642-251">云基会议录制</span><span class="sxs-lookup"><span data-stu-id="fb642-251">Cloud based meeting recording</span></span> |<span data-ttu-id="fb642-252">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fb642-252">&#x2714;</span></span> |<span data-ttu-id="fb642-253">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fb642-253">&#x2714;</span></span> |<span data-ttu-id="fb642-254">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fb642-254">&#x2714;</span></span> |
|<span data-ttu-id="fb642-255">自动将录制发布到 Stream</span><span class="sxs-lookup"><span data-stu-id="fb642-255">Auto publish recording to Stream</span></span> |<span data-ttu-id="fb642-256">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="fb642-256">&#x274C;</span></span> |<span data-ttu-id="fb642-257">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="fb642-257">&#x274C;</span></span> |<span data-ttu-id="fb642-258">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fb642-258">&#x2714;</span></span> |
|<span data-ttu-id="fb642-259">实时辅助字幕与字幕</span><span class="sxs-lookup"><span data-stu-id="fb642-259">Live captions and subtitles</span></span> |<span data-ttu-id="fb642-260">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fb642-260">&#x2714;</span></span> |<span data-ttu-id="fb642-261">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fb642-261">&#x2714;</span></span> |<span data-ttu-id="fb642-262">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="fb642-262">&#x274C;</span></span> |
|<span data-ttu-id="fb642-263">实时事件录制字幕</span><span class="sxs-lookup"><span data-stu-id="fb642-263">Captions in live event recordings</span></span> |<span data-ttu-id="fb642-264">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fb642-264">&#x2714;</span></span> |<span data-ttu-id="fb642-265">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fb642-265">&#x2714;</span></span> |<span data-ttu-id="fb642-266">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fb642-266">&#x2714;</span></span> |
|<span data-ttu-id="fb642-267">与会者 DVR 控件（暂停、后退）</span><span class="sxs-lookup"><span data-stu-id="fb642-267">Attendee DVR controls (pause, rewind)</span></span> |<span data-ttu-id="fb642-268">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fb642-268">&#x2714;</span></span> |<span data-ttu-id="fb642-269">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fb642-269">&#x2714;</span></span> |<span data-ttu-id="fb642-270">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fb642-270">&#x2714;</span></span> |
|<span data-ttu-id="fb642-271">合作伙伴 eCDN 支持</span><span class="sxs-lookup"><span data-stu-id="fb642-271">Partner eCDN Support</span></span> |<span data-ttu-id="fb642-272">&#x2714; (Kollective, Hive, Riverbed)</span><span class="sxs-lookup"><span data-stu-id="fb642-272">&#x2714; (Kollective, Hive, Riverbed)</span></span> |<span data-ttu-id="fb642-273">&#x2714; (Kollective, Hive, Riverbed)</span><span class="sxs-lookup"><span data-stu-id="fb642-273">&#x2714; (Kollective, Hive, Riverbed)</span></span> |<span data-ttu-id="fb642-274">&#x2714; (Hive, Kollective, Ramp, Riverbed)</span><span class="sxs-lookup"><span data-stu-id="fb642-274">&#x2714; (Hive, Kollective, Ramp, Riverbed)</span></span> |
|<span data-ttu-id="fb642-275">制作者直播后受众报告</span><span class="sxs-lookup"><span data-stu-id="fb642-275">Post-broadcast attendance report for Producers</span></span> |<span data-ttu-id="fb642-276">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fb642-276">&#x2714;</span></span> |<span data-ttu-id="fb642-277">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="fb642-277">&#x2714;</span></span> |<span data-ttu-id="fb642-278">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="fb642-278">&#x274C;</span></span> |
|<span data-ttu-id="fb642-279">受众情绪分析 – 实时投票和民意调查</span><span class="sxs-lookup"><span data-stu-id="fb642-279">Audience Sentiment Analysis – Live voting & polls</span></span> |<span data-ttu-id="fb642-280">&#x2714; (Microsoft Pulse)</span><span class="sxs-lookup"><span data-stu-id="fb642-280">&#x2714; (Microsoft Pulse)</span></span> |<span data-ttu-id="fb642-281">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="fb642-281">&#x274C;</span></span> |<span data-ttu-id="fb642-282">&#x274C;</span><span class="sxs-lookup"><span data-stu-id="fb642-282">&#x274C;</span></span> |

<span data-ttu-id="fb642-p108"><sup>1</sup> 设定的限制可能会更改。查看 [Teams 限制和规范](../limits-specifications-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="fb642-p108"><sup>1</sup> The limits that are set might be changed. Check [Limits and specifications for Teams](../limits-specifications-teams.md).</span></span><br/>
<span data-ttu-id="fb642-285"><sup>2</sup> 可在实时事件中拥有多达 100 位演示者和制作者，但列表中仅显示最后 10 位发言的人员。</span><span class="sxs-lookup"><span data-stu-id="fb642-285"><sup>2</sup> You can have up to 100 presenters and producers in a live event, but only the last 10 who spoke show up in the list.</span></span>

## <a name="regional-availability"></a><span data-ttu-id="fb642-286">区域可用性</span><span class="sxs-lookup"><span data-stu-id="fb642-286">Regional availability</span></span>

<span data-ttu-id="fb642-p109">可在全球中的多个区域实用 Teams 实时事件。以下信息显示事件团队成员和参与者的空闲时间。</span><span class="sxs-lookup"><span data-stu-id="fb642-p109">You can use Teams live events in multiple regions across the world. The following information shows availability for event team members and attendees.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb642-289">将根据组织者和 Microsoft 365 租户的位置自动选择事件的区域。</span><span class="sxs-lookup"><span data-stu-id="fb642-289">The region for the event is automatically selected depending on the organizer and the Microsoft 365 tenant location.</span></span>

<span data-ttu-id="fb642-290">**可用于以下区域数据中心**</span><span class="sxs-lookup"><span data-stu-id="fb642-290">**Available in these regional data centers**</span></span>

- <span data-ttu-id="fb642-291">北美洲</span><span class="sxs-lookup"><span data-stu-id="fb642-291">North America</span></span>
- <span data-ttu-id="fb642-292">中美洲</span><span class="sxs-lookup"><span data-stu-id="fb642-292">Central America</span></span>
- <span data-ttu-id="fb642-293">南美洲</span><span class="sxs-lookup"><span data-stu-id="fb642-293">South America</span></span>
- <span data-ttu-id="fb642-294">亚太地区</span><span class="sxs-lookup"><span data-stu-id="fb642-294">Asia Pacific</span></span>
- <span data-ttu-id="fb642-295">欧洲/非洲</span><span class="sxs-lookup"><span data-stu-id="fb642-295">Europe/Africa</span></span>

<span data-ttu-id="fb642-296">**以下国家/地区（支持）的数据位置**</span><span class="sxs-lookup"><span data-stu-id="fb642-296">**Data location for these countries/regions (supported)**</span></span>

- <span data-ttu-id="fb642-297">澳大利亚</span><span class="sxs-lookup"><span data-stu-id="fb642-297">Australia</span></span>
- <span data-ttu-id="fb642-298">加拿大</span><span class="sxs-lookup"><span data-stu-id="fb642-298">Canada</span></span>
- <span data-ttu-id="fb642-299">印度</span><span class="sxs-lookup"><span data-stu-id="fb642-299">India</span></span>
- <span data-ttu-id="fb642-300">日本</span><span class="sxs-lookup"><span data-stu-id="fb642-300">Japan</span></span>
- <span data-ttu-id="fb642-301">英国</span><span class="sxs-lookup"><span data-stu-id="fb642-301">United Kingdom</span></span>

<span data-ttu-id="fb642-302">**不支持这些国家/地区和云**</span><span class="sxs-lookup"><span data-stu-id="fb642-302">**These countries/regions and clouds aren't supported**</span></span>

- <span data-ttu-id="fb642-303">德国</span><span class="sxs-lookup"><span data-stu-id="fb642-303">Germany</span></span>
- <span data-ttu-id="fb642-304">法国</span><span class="sxs-lookup"><span data-stu-id="fb642-304">France</span></span>
- <span data-ttu-id="fb642-305">挪威</span><span class="sxs-lookup"><span data-stu-id="fb642-305">Norway</span></span>
- <span data-ttu-id="fb642-306">南非</span><span class="sxs-lookup"><span data-stu-id="fb642-306">South Africa</span></span>
- <span data-ttu-id="fb642-307">韩国</span><span class="sxs-lookup"><span data-stu-id="fb642-307">South Korea</span></span>
- <span data-ttu-id="fb642-308">瑞士</span><span class="sxs-lookup"><span data-stu-id="fb642-308">Switzerland</span></span>
- <span data-ttu-id="fb642-309">阿拉伯联合酋长国</span><span class="sxs-lookup"><span data-stu-id="fb642-309">UAE</span></span>
- <span data-ttu-id="fb642-310">政府社区云 (GCC)-H</span><span class="sxs-lookup"><span data-stu-id="fb642-310">Government Community Cloud (GCC)-H</span></span>
- <span data-ttu-id="fb642-311">DOD</span><span class="sxs-lookup"><span data-stu-id="fb642-311">DOD</span></span>

<span data-ttu-id="fb642-312">**例外和注意事项**</span><span class="sxs-lookup"><span data-stu-id="fb642-312">**Exclusions and considerations**</span></span>

- <span data-ttu-id="fb642-313">**数据位置：** 暂不支持除以上所列国家/地区之外的其他任何 Teams 数据位置。</span><span class="sxs-lookup"><span data-stu-id="fb642-313">**Data location:** Teams data locations, outside of the ones listed above, are not currently supported.</span></span>
- <span data-ttu-id="fb642-p110">**中国：**  事件团队成员和参与者将无法使用 Teams 事件，因为 Azure CDN 在中国不可访问。解决方法是使用公司 VPN 连接，后者通过客户的公司网络获取连接到 CDN 的客户端。</span><span class="sxs-lookup"><span data-stu-id="fb642-p110">**China:** Event team members and attendees will not be able to use Teams live events because Azure CDN is not accessible in China. A workaround is to use a company VPN connection, which gets the client connected to CDN via the customer's corporate network.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fb642-316">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fb642-316">Next steps</span></span>

<span data-ttu-id="fb642-317">转到[设置 Teams 实时事件](set-up-for-teams-live-events.md)。</span><span class="sxs-lookup"><span data-stu-id="fb642-317">Go to [Set up for Teams live events](set-up-for-teams-live-events.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="fb642-318">相关主题</span><span class="sxs-lookup"><span data-stu-id="fb642-318">Related topics</span></span>

- [<span data-ttu-id="fb642-319">什么是 Teams 实时事件？</span><span class="sxs-lookup"><span data-stu-id="fb642-319">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="fb642-320">设置 Teams 实时事件</span><span class="sxs-lookup"><span data-stu-id="fb642-320">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="fb642-321">配置 Teams 实时事件设置</span><span class="sxs-lookup"><span data-stu-id="fb642-321">Configure live events settings in Teams</span></span>](configure-teams-live-events.md)
