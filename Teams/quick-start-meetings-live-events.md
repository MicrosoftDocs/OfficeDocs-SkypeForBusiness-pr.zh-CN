---
title: 管理员快速入门 - Microsoft Teams 中的会议和实时事件
ms.reviewer: ''
description: Microsoft Teams 中的会议和实时事件快速入门。
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: b870a15f885922563d8440d571dc5a6eb7ac7540
ms.sourcegitcommit: 929c050c038a64216e38b0a67569a8f18ad4baf2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "43940779"
---
# <a name="admin-quick-start---meetings-and-live-events-in-microsoft-teams"></a><span data-ttu-id="5ece7-103">管理员快速入门 - Microsoft Teams 中的会议和实时事件</span><span class="sxs-lookup"><span data-stu-id="5ece7-103">Admin quick start - Meetings and live events in Microsoft Teams</span></span>

<span data-ttu-id="5ece7-104">在 Microsoft Teams 中开会有两种方式 - 会议和实时事件。</span><span class="sxs-lookup"><span data-stu-id="5ece7-104">There are 2 ways to meet in Microsoft Teams - meetings and live events.</span></span> <span data-ttu-id="5ece7-105">本文介绍如何为你的组织快速推出和配置会议和实时事件。</span><span class="sxs-lookup"><span data-stu-id="5ece7-105">Use this article to quickly roll out and configure meetings and live events for your organization.</span></span> 

 - <span data-ttu-id="5ece7-106">Teams 中的**会议**包括音频、视频和屏幕共享，最多可容纳 250 人。</span><span class="sxs-lookup"><span data-stu-id="5ece7-106">**Meetings** in Teams include audio, video, and screen sharing for up to 250 people.</span></span> <span data-ttu-id="5ece7-107">它们是在 Teams 中进行协作的关键方式之一。</span><span class="sxs-lookup"><span data-stu-id="5ece7-107">They're one of the key ways to collaborate in Teams.</span></span> <span data-ttu-id="5ece7-108">而且，你无需成为组织成员（甚至无需拥有 Teams 帐户！）即可参加 Teams 会议，只需查看邀请中有关呼叫的说明即可。</span><span class="sxs-lookup"><span data-stu-id="5ece7-108">And you don't need to be a member of an organization (or even have a Teams account!) to join a Teams meeting—just look in the invitation for instructions about calling in.</span></span> 

 - <span data-ttu-id="5ece7-109">**实时事件**是 Teams 会议的扩展，使你能够安排和制作流向大型在线受众（最多 10,000 人）的事件。</span><span class="sxs-lookup"><span data-stu-id="5ece7-109">**Live events** are an extension of Teams meetings that enable you to schedule and produce events that stream to large online audiences - up to 10,000 people.</span></span> <span data-ttu-id="5ece7-110">如果你需要召开超过 250 人的会议，请使用实时事件。</span><span class="sxs-lookup"><span data-stu-id="5ece7-110">If you need a meeting for more than 250 people, use a live event.</span></span>

## <a name="get-licenses-for-meetings-and-live-events"></a><span data-ttu-id="5ece7-111">获取会议和实时事件的许可证</span><span class="sxs-lookup"><span data-stu-id="5ece7-111">Get licenses for meetings and live events</span></span>

<span data-ttu-id="5ece7-112">任何人都可以免费参加 Teams 会议或实时事件，无需许可证。</span><span class="sxs-lookup"><span data-stu-id="5ece7-112">Anyone can attend a Teams meeting or live event for free - no license is required.</span></span> <span data-ttu-id="5ece7-113">与会者可通过单击 Teams 或会议邀请中的“**加入**”按钮来参加 Teams 会议或实时事件。</span><span class="sxs-lookup"><span data-stu-id="5ece7-113">Attendees join a Teams meeting or live event by clicking the **Join** button in Teams or the meeting invitation.</span></span> <span data-ttu-id="5ece7-114">会议音频是 Teams 会议的一部分，但如果你希望其他人可以通过电话拨入会议，则需要提供拨入号码。</span><span class="sxs-lookup"><span data-stu-id="5ece7-114">Meeting audio is part of a Teams meeting, but if you want people to be able to dial in to a meeting by phone, you'll need to provide a dial-in number.</span></span> 

<span data-ttu-id="5ece7-115">对于将组织、安排和主持会议或实时事件的人员，他们将需要下表中列出的其中一个 Microsoft 365 或 Office 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="5ece7-115">For the people who will organize, schedule, and host meetings or live events, they'll need one of the Microsoft 365 or Office 365 licenses listed in the table below.</span></span> <span data-ttu-id="5ece7-116">如果你已在使用 Teams，那么你可能拥有组织和主持会议和实时事件所需的许可证。</span><span class="sxs-lookup"><span data-stu-id="5ece7-116">If you're already using Teams, you probably have the license you need for organizing and hosting meetings and live events.</span></span> 

:::image type="content" source="media/quick-start-meetings-live-events-image1.png" alt-text="包含 Teams 会议或实时事件所需许可证的表":::

> <span data-ttu-id="5ece7-118"><sup>1</sup>  会议组织者需要具有[音频会议附加许可证](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)才能发送包含拨入式会议的邀请。</span><span class="sxs-lookup"><span data-stu-id="5ece7-118"><sup>1</sup>  Meeting organizers need to have an [Audio Conferencing add-on license](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) to send an invite that includes dial-in conferencing.</span></span>
>
> <span data-ttu-id="5ece7-119"><sup>2</sup>  会议拨出至[**拨打**号码](set-up-the-call-me-feature-for-your-users.md)呼叫我要求组织者拥有 E5 或 [音频会议加载项许可证](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="5ece7-119"><sup>2</sup>  Meeting dial out to a [**Call me at** number](set-up-the-call-me-feature-for-your-users.md) requires organizers to have an E5 or [Audio Conference add-in license](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span> <span data-ttu-id="5ece7-120">可能还需要[拨号计划](what-are-dial-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="5ece7-120">A [dial plan](what-are-dial-plans.md) may also be needed.</span></span> 


<span data-ttu-id="5ece7-121">要了解有关许可的详细信息，请阅读[适用于 Teams 的 Office 365 许可](Office-365-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="5ece7-121">To learn more about licensing, read [Office 365 licensing for Teams](Office-365-licensing.md).</span></span> 

## <a name="make-sure-your-networks-ready"></a><span data-ttu-id="5ece7-122">请确保网络已准备就绪</span><span class="sxs-lookup"><span data-stu-id="5ece7-122">Make sure your network's ready</span></span>

<span data-ttu-id="5ece7-123">如果你在推出 Microsoft 365 或 Office 365 时已准备好网络，则可能已准备就绪。</span><span class="sxs-lookup"><span data-stu-id="5ece7-123">If you already prepared your network when you rolled out Microsoft 365 or Office 365, you're probably all set.</span></span> <span data-ttu-id="5ece7-124">无论是哪种情况，尤其是如果你要快速推出 Teams 作为你的第一个 Office 365 工作负载以支持**远程工作者** - 请阅读[准备适用于 Teams 的组织网络](prepare-network.md)，以确保一切就绪。</span><span class="sxs-lookup"><span data-stu-id="5ece7-124">In any case - and especially if you're rolling out Teams quickly as your first Office 365 workload to support **remote workers** - read [Prepare your organization's network for Teams](prepare-network.md) to be sure you're ready.</span></span>

## <a name="meetings-and-conferencing"></a><span data-ttu-id="5ece7-125">会话和电话会议</span><span class="sxs-lookup"><span data-stu-id="5ece7-125">Meetings and conferencing</span></span>

- <span data-ttu-id="5ece7-126">作为管理员，你将为所有人配置[会议设置](meeting-settings-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="5ece7-126">As the admin, you'll configure [meeting settings](meeting-settings-in-teams.md) for everyone.</span></span> <span data-ttu-id="5ece7-127">然后，你可使用[会议策略](meeting-policies-in-teams.md)来控制你的用户可以使用（或不可以使用）哪些会议功能。</span><span class="sxs-lookup"><span data-stu-id="5ece7-127">Then you'll use [meeting policies](meeting-policies-in-teams.md) to control what meeting features are (and aren't) available for your users.</span></span> 

- <span data-ttu-id="5ece7-128">若要了解如何管理会议录制，请阅读 [Teams 云会议录制](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="5ece7-128">To learn about managing meeting recording, read [Teams cloud meeting recording](cloud-recording.md).</span></span>

- <span data-ttu-id="5ece7-129">如果你的用户是 Teams 会议的新用户，请与他们共享[管理会议](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4)培训。</span><span class="sxs-lookup"><span data-stu-id="5ece7-129">If your users are new to Teams meetings, share the [Manage meetings](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4) training with them.</span></span> <span data-ttu-id="5ece7-130">观看我们的讲师指导在线课堂，[使用 Teams 举行高效会议](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings)。</span><span class="sxs-lookup"><span data-stu-id="5ece7-130">Check out our instructor-led online class, [Run effective meetings with Teams](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings).</span></span>

- <span data-ttu-id="5ece7-131">要了解有关管理会议选项的信息，请参阅[更改 Teams 会议的参与者设置](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e)。</span><span class="sxs-lookup"><span data-stu-id="5ece7-131">To learn about managing meeting options, read [Change participant settings for a Teams meeting](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e).</span></span>

- <span data-ttu-id="5ece7-132">请不要忘记[管理用户的设备](device-management.md) - 电话、耳机和相机。</span><span class="sxs-lookup"><span data-stu-id="5ece7-132">Don't forget about [managing your users' devices](device-management.md) - phones, headsets, cameras.</span></span> <span data-ttu-id="5ece7-133">要获取有关经过 Teams 认证的设备的最新信息，请转到 [Teams 设备](https://office.com/teamsdevices)。</span><span class="sxs-lookup"><span data-stu-id="5ece7-133">To get the latest and up-to-date information on Teams certified devices, go to [Teams devices](https://office.com/teamsdevices).</span></span>

## <a name="live-events"></a><span data-ttu-id="5ece7-134">实时事件</span><span class="sxs-lookup"><span data-stu-id="5ece7-134">Live events</span></span>

- <span data-ttu-id="5ece7-135">与会议类似，管理员为[所有人配置实时事件](teams-live-events/configure-teams-live-events.md)。</span><span class="sxs-lookup"><span data-stu-id="5ece7-135">Similar to meetings, you - the admin - [configure live events](teams-live-events/configure-teams-live-events.md) for everyone.</span></span> <span data-ttu-id="5ece7-136">然后设置（并分配）[实时事件策略](teams-live-events/set-up-for-teams-live-events.md)以控制用户可以（和不可）执行的操作。</span><span class="sxs-lookup"><span data-stu-id="5ece7-136">Then set up (and assign) [live event policies](teams-live-events/set-up-for-teams-live-events.md) to control what your users can (and can't) do.</span></span>

- <span data-ttu-id="5ece7-137">请确保实时事件的制作者和组织者都经过了培训 - 将[实时事件入门](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a)发送给他们。</span><span class="sxs-lookup"><span data-stu-id="5ece7-137">Make sure your live event producers and organizers are trained - send them to [Get started with live events](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a).</span></span>

- <span data-ttu-id="5ece7-138">如果你不熟悉实时事件，请查看[什么是 Teams 实时事件？](teams-live-events/what-are-teams-live-events.md)和[规划 Teams 实时事件](teams-live-events/plan-for-teams-live-events.md)。</span><span class="sxs-lookup"><span data-stu-id="5ece7-138">If you're new to live events, check out [What are Teams live events?](teams-live-events/what-are-teams-live-events.md) and [Plan for Teams live events](teams-live-events/plan-for-teams-live-events.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5ece7-139">相关主题</span><span class="sxs-lookup"><span data-stu-id="5ece7-139">Related topics</span></span>

[<span data-ttu-id="5ece7-140">Teams 中的会议和电话会议</span><span class="sxs-lookup"><span data-stu-id="5ece7-140">Meetings and conferencing in Teams</span></span>](deploy-meetings-microsoft-teams-landing-page.md)

[<span data-ttu-id="5ece7-141">Teams 中的会议</span><span class="sxs-lookup"><span data-stu-id="5ece7-141">Audio conferencing in Teams</span></span>](deploy-audio-conferencing-teams-landing-page.md)

[<span data-ttu-id="5ece7-142">Teams 中的实时事件</span><span class="sxs-lookup"><span data-stu-id="5ece7-142">Live events in Teams</span></span>](teams-live-events/what-are-teams-live-events.md)

[<span data-ttu-id="5ece7-143">Teams 限制和规范</span><span class="sxs-lookup"><span data-stu-id="5ece7-143">Limits and specifications for Teams</span></span>](limits-specifications-teams.md)

[<span data-ttu-id="5ece7-144">Microsoft 技术社区： Microsoft 365 中的实时事件</span><span class="sxs-lookup"><span data-stu-id="5ece7-144">Microsoft Technical Community: Live events in Microsoft 365</span></span>](https://resources.techcommunity.microsoft.com/live-events/)
