---
title: 管理员快速入门 - Microsoft Teams 中的会议和实时事件
ms.reviewer: ''
description: 管理员快速入门指南，介绍如何为 Microsoft Teams 获取许可证、在其中部署和配置在线会议和实时事件。
ms.topic: article
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03611f2d166883ce960e272e2f3b11300cd20c54
ms.sourcegitcommit: 616b6d0d5be2b333519b79ab59a4117036ba647e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363577"
---
# <a name="admin-quick-start---meetings-and-live-events-in-microsoft-teams"></a><span data-ttu-id="8e23f-103">管理员快速入门 - Microsoft Teams 中的会议和实时事件</span><span class="sxs-lookup"><span data-stu-id="8e23f-103">Admin quick start - Meetings and live events in Microsoft Teams</span></span>

<span data-ttu-id="8e23f-p101">在 Microsoft Teams 中有两种会议方式 - 会议和实时事件。使用本文介绍如何为你的组织快速推出和配置会议和实时事件。</span><span class="sxs-lookup"><span data-stu-id="8e23f-p101">There are 2 ways to meet in Microsoft Teams - meetings and live events. Use this article to quickly roll out and configure meetings and live events for your organization.</span></span>

> [!Note]
> <span data-ttu-id="8e23f-106">有关在不同平台上快速配置 Teams 会议和事件的详细信息，请参阅 [Teams 功能（按平台）](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。</span><span class="sxs-lookup"><span data-stu-id="8e23f-106">For details about quickly configuring Teams meetings and events on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

 - <span data-ttu-id="8e23f-p102">Teams 中的 **会议** 包括最多可容纳 300 人的音频、视频和屏幕共享。它们是团队协作的主要方法之一。无需成为某个组织的成员（甚至无需用拥有 Teams 帐户！）即可加入 Teams 会议 — 只需在邀请中查找有关呼叫的说明。</span><span class="sxs-lookup"><span data-stu-id="8e23f-p102">**Meetings** in Teams include audio, video, and screen sharing for up to 1000 people. They're one of the key ways to collaborate in Teams. And you don't need to be a member of an organization (or even have a Teams account!) to join a Teams meeting—just look in the invitation for instructions about calling in.</span></span>

 - <span data-ttu-id="8e23f-p103">**实时活动** 是 Teams 会议的扩展，使你能够安排和制作流向大型在线受众的活动（最多 10,000 人）。如果需要一个超过300人的会议，请使用实时活动。</span><span class="sxs-lookup"><span data-stu-id="8e23f-p103">**Live events** are an extension of Teams meetings that enable you to schedule and produce events that stream to large online audiences - up to 10,000 people. If you need a meeting for more than 1000 people, use a live event.</span></span>

## <a name="get-licenses-for-meetings-and-live-events"></a><span data-ttu-id="8e23f-112">获取会议和实时事件的许可证</span><span class="sxs-lookup"><span data-stu-id="8e23f-112">Get licenses for meetings and live events</span></span>

<span data-ttu-id="8e23f-p104">任何人都可以免费参加 Teams 会议或公开实时事件 - 无需许可证。与会者可通过点击 Teams 中的 **加入** 按钮或会议邀请来加入 Teams 会议或实时事件。会议音频是 Teams 会议的一部分，但如果你希望其他人可以通过电话拨入会议，则需要提供一个拨入号码。</span><span class="sxs-lookup"><span data-stu-id="8e23f-p104">Anyone can attend a Teams meeting or public live event for free - no license is required. Attendees join a Teams meeting or live event by clicking the **Join** button in Teams or the meeting invitation. Meeting audio is part of a Teams meeting, but if you want people to be able to dial in to a meeting by phone, you'll need to provide a dial-in number.</span></span>

<span data-ttu-id="8e23f-116">对于将组织、安排和主持会议或实时事件的人员，他们将需要 [Microsoft Teams 服务说明](/office365/servicedescriptions/teams-service-description)中所述的许可套餐之一。</span><span class="sxs-lookup"><span data-stu-id="8e23f-116">For the people who will organize, schedule, and host meetings or live events, they'll need one of the licensing plans described in the [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span> 

<span data-ttu-id="8e23f-117">如果你已在使用 Teams，那么你可能拥有组织和主持会议和实时事件所需的许可证。</span><span class="sxs-lookup"><span data-stu-id="8e23f-117">If you're already using Teams, you probably have the license you need for organizing and hosting meetings and live events.</span></span>

## <a name="make-sure-your-networks-ready"></a><span data-ttu-id="8e23f-118">请确保网络已准备就绪</span><span class="sxs-lookup"><span data-stu-id="8e23f-118">Make sure your network's ready</span></span>

<span data-ttu-id="8e23f-p105">如果在推出 Microsoft 365 或 Office 365 时已经准备好了所有你可能已设置好的网络。无论是哪种情况下 - 尤其是如果你要快速推出 Teams 作为你的第一个 Office 365 工作负载以支持 **远程工作者** - 请确认你已准备好阅读 [为 Teams 准备组织网络](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="8e23f-p105">If you already prepared your network when you rolled out Microsoft 365 or Office 365, you're probably all set. In any case - and especially if you're rolling out Teams quickly as your first Office 365 workload to support **remote workers** - read [Prepare your organization's network for Teams](prepare-network.md) to be sure you're ready.</span></span>

## <a name="meetings-and-conferencing"></a><span data-ttu-id="8e23f-121">会话和电话会议</span><span class="sxs-lookup"><span data-stu-id="8e23f-121">Meetings and conferencing</span></span>

- <span data-ttu-id="8e23f-p106">作为管理员，你将为每个人配置[会议设置](meeting-settings-in-teams.md)。然后，你可使用[会议策略](meeting-policies-in-teams.md)来控制你的用户可用（或不可用）哪些会议功能。</span><span class="sxs-lookup"><span data-stu-id="8e23f-p106">As the admin, you'll configure [meeting settings](meeting-settings-in-teams.md) for everyone. Then you'll use [meeting policies](meeting-policies-in-teams.md) to control what meeting features are (and aren't) available for your users.</span></span>

- <span data-ttu-id="8e23f-124">若要了解如何管理会议录制，请阅读 [Teams 云会议录制](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="8e23f-124">To learn about managing meeting recording, read [Teams cloud meeting recording](cloud-recording.md).</span></span>

- <span data-ttu-id="8e23f-p107">如果你的用户是首次参加团队会议，请与他们共享 [管理会议](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4) 培训。请查看我们的讲师指导在线课堂， [与团队召开高效会议](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings)。</span><span class="sxs-lookup"><span data-stu-id="8e23f-p107">If your users are new to Teams meetings, share the [Manage meetings](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4) training with them. Check out our instructor-led online class, [Run effective meetings with Teams](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings).</span></span>

- <span data-ttu-id="8e23f-127">要了解有关管理会议选项的信息，请参阅[更改 Teams 会议的参与者设置](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e)。</span><span class="sxs-lookup"><span data-stu-id="8e23f-127">To learn about managing meeting options, read [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e).</span></span>

- <span data-ttu-id="8e23f-p108">请不要忘记 [管理用户的设备](./devices/device-management.md) - 手机、耳机和照相机。若要获取有关 Teams 认证设备的最新和刚更新的信息，请转到 [团队设备](https://office.com/teamsdevices)。</span><span class="sxs-lookup"><span data-stu-id="8e23f-p108">Don't forget about [managing your users' devices](./devices/device-management.md) - phones, headsets, cameras. To get the latest and up-to-date information on Teams certified devices, go to [Teams devices](https://office.com/teamsdevices).</span></span>

## <a name="live-events"></a><span data-ttu-id="8e23f-130">实时事件</span><span class="sxs-lookup"><span data-stu-id="8e23f-130">Live events</span></span>

- <span data-ttu-id="8e23f-p109">与会议类似，你 - 管理员 - 为所有人[配置实时事件](teams-live-events/configure-teams-live-events.md) 。然后设置（并分配）[实时事件策略](teams-live-events/set-up-for-teams-live-events.md) 以控制用户可以（和无法）执行的操作。</span><span class="sxs-lookup"><span data-stu-id="8e23f-p109">Similar to meetings, you - the admin - [configure live events](teams-live-events/configure-teams-live-events.md) for everyone. Then set up (and assign) [live event policies](teams-live-events/set-up-for-teams-live-events.md) to control what your users can (and can't) do.</span></span>

- <span data-ttu-id="8e23f-133">请确保实时事件的制作者和组织者都经过了培训 - 将[实时事件入门](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a)发送给他们。</span><span class="sxs-lookup"><span data-stu-id="8e23f-133">Make sure your live event producers and organizers are trained - send them to [Get started with live events](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a).</span></span>

- <span data-ttu-id="8e23f-134">如果你不熟悉实时事件，请查看[什么是 Teams 实时事件？](teams-live-events/what-are-teams-live-events.md)和[规划 Teams 实时事件](teams-live-events/plan-for-teams-live-events.md)。</span><span class="sxs-lookup"><span data-stu-id="8e23f-134">If you're new to live events, check out [What are Teams live events?](teams-live-events/what-are-teams-live-events.md) and [Plan for Teams live events](teams-live-events/plan-for-teams-live-events.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8e23f-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="8e23f-135">Related topics</span></span>

[<span data-ttu-id="8e23f-136">Teams 中的会议和电话会议</span><span class="sxs-lookup"><span data-stu-id="8e23f-136">Meetings and conferencing in Teams</span></span>](deploy-meetings-microsoft-teams-landing-page.md)

[<span data-ttu-id="8e23f-137">Teams 中的会议</span><span class="sxs-lookup"><span data-stu-id="8e23f-137">Audio conferencing in Teams</span></span>](deploy-audio-conferencing-teams-landing-page.md)

[<span data-ttu-id="8e23f-138">Teams 中的实时事件</span><span class="sxs-lookup"><span data-stu-id="8e23f-138">Live events in Teams</span></span>](teams-live-events/what-are-teams-live-events.md)

[<span data-ttu-id="8e23f-139">Teams 限制和规范</span><span class="sxs-lookup"><span data-stu-id="8e23f-139">Limits and specifications for Teams</span></span>](limits-specifications-teams.md)

[<span data-ttu-id="8e23f-140">Microsoft 技术社区： Microsoft 365 中的实时事件</span><span class="sxs-lookup"><span data-stu-id="8e23f-140">Microsoft Technical Community: Live events in Microsoft 365</span></span>](https://resources.techcommunity.microsoft.com/live-events/)
