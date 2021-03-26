---
title: 仅查看会议体验
author: cichur
ms.author: v-cichur
ms.reviewer: christi.balaki
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解管理员、演示者和与会者的 Teams 专用视图会议体验
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 25cd674e5f93e4f52f0a2cecd2acff97e4844834
ms.sourcegitcommit: f4393657584666842e874d526a08cfa1137b911d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51215327"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="ca5b9-103">Teams 仅查看会议体验</span><span class="sxs-lookup"><span data-stu-id="ca5b9-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="ca5b9-104">Microsoft 365 E3/E5 和 Microsoft 365 A3/A5 中提供了仅查看广播。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="ca5b9-105">该功能将于 2021 年 3 月 1 日启用，默认为“关闭”。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="ca5b9-106">Microsoft 365 政府社区云 (GCC) 中的该功能将于 2021 年 3 月底开始推出。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="ca5b9-107">政府社区云高 (GCCH) 和国防部 (DoD) 将在日后推出。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="ca5b9-108">如果想让该功能默认为 “启动”，必须在该日期之后更改默认策略。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="ca5b9-109">使用 PowerShell 启用策略 `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="ca5b9-110">如果会议或网络研讨会达到饱和状态，Teams 将无缝扩展至容纳 10,000 人的仅限观看广播体验。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-110">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="ca5b9-111">另外，在这个远程工作增加的时期，利用更大规模的 20,000 人广播到今年年底。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="ca5b9-112">Microsoft Teams 允许最多 10,000 名与会者加入一个 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="ca5b9-113">在达到主会议的容量后 (在 WW 中为 300 人，GCC 用户为 250 人进入会议) 时，其他与会者将加入仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-113">After the capacity of the main meeting has been reached (which is when 300 in WW or 250 in GCC users enter a meeting), additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="ca5b9-114">首先加入会议的与会者（最多是主会议的容量）将获得完整的 Teams 会议体验。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-114">Attendees who join the meeting first, up to the capacity of the main meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="ca5b9-115">他们可以共享音频和视频、查看共享视频、并参与会议聊天。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="ca5b9-116">在达到主会场容量后加入的与会者将有仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="ca5b9-117">与会者可以通过 Android 和 iOS 桌面版、Web 版和 Teams (加入仅查看) 。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-117">Attendees will be able to join the view-only experience through desktop, web, and Teams mobile (Android and iOS).</span></span>

> [!Note]
> <span data-ttu-id="ca5b9-118">"主会议"的当前限制容量（换句话说，完全交互用户的数量）在 WW 中为 300，GCC、GCC High 和 DoD 为 250。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-118">The current limit capacity of the "main meeting", or in other words, the number of fully interactive users, is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

## <a name="teams-view-only-experience-controls"></a><span data-ttu-id="ca5b9-119">Teams 仅查看体验控件</span><span class="sxs-lookup"><span data-stu-id="ca5b9-119">Teams view-only experience controls</span></span>

<span data-ttu-id="ca5b9-120">使用 PowerShell 启用仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-120">You enable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled
```

<span data-ttu-id="ca5b9-121">若要禁用仅查看体验，还可使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-121">To disable the view-only experience, you can also use PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="ca5b9-122">将来，你将能够在 Teams 管理中心启用或禁用仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-122">In the future, you'll be able to enable or disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="ca5b9-123">对用户的影响</span><span class="sxs-lookup"><span data-stu-id="ca5b9-123">Impact to users</span></span>

<span data-ttu-id="ca5b9-124">用户的体验会因多种因素而有所不同。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-124">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="ca5b9-125">当主会场容量已满时，如有下列情况之一，与会者将无法参加会议:</span><span class="sxs-lookup"><span data-stu-id="ca5b9-125">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="ca5b9-126">管理员已针对组织者或整个租户禁用了 Teams 仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-126">An administrator has disabled the Teams view-only experience for either the organizer or for the entire tenant.</span></span>
- <span data-ttu-id="ca5b9-127">仅查看与会者不能绕过大厅。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-127">The view-only attendee can't bypass the lobby.</span></span> <span data-ttu-id="ca5b9-128">例如，如果会议的组织者选择仅让"我组织的人"绕过大厅，而组织外部的与会者尝试以仅查看与会者的与会者加入，则他们将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-128">As an example, if an organizer of a meeting chooses to have only **People in my organization** bypass the lobby, and an attendee who is outside of the organization attempts to join as a view-only attendee, they'll be rejected.</span></span>

<span data-ttu-id="ca5b9-129">当达到主会议的容量时，会议组织者和演示者将看到一个横幅，通知他们新与会者将作为仅查看的与会者加入。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that new attendees will join as view-only attendees.</span></span>

  ![为组织者和演讲者提供 Teams 客户端和横幅信息](media/chat-and-banner-message.png)

<span data-ttu-id="ca5b9-131">当达到主会议的容量时，会议平台会在预加入界面上通知他们以仅查看模式加入。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![Teams 预加入屏幕和告诉参与者他们将以纯视图模式加入的信息](media/view-only-pre-join-screen.png)

<span data-ttu-id="ca5b9-133">如果有空间，用户将始终加入主会议。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="ca5b9-134">如果主会场达到容纳量，有一名或多名与会者离开主会场，则主会场有可用容量。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="ca5b9-135">加入 (或重新加入) 会议的与会者将加入主会议，直到会议再次达到饱和。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="ca5b9-136">处于仅查看体验中的参会者不会自动晋升到主会议，目前无法手动晋升到主会议。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="ca5b9-137">如果已设置演示者和与会者角色，并且演示者在 的主会议达到容量后尝试加入会议，他们将作为仅查看的与会者加入，并且与其他仅查看的与会者具有相同的限制。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-137">If presenter and attendee roles have been set, and a presenter attempts to join a meeting after the main meeting of has reached capacity, they'll join as a view-only attendee and have the same limitations as other view-only attendees.</span></span> <span data-ttu-id="ca5b9-138">支持确保所有演示者加入主会议将在以后推出。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-138">Support to ensure all presenters join the main meeting will roll out at a later date.</span></span> <span data-ttu-id="ca5b9-139">组织者将始终获得主会议空间保证。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-139">The organizer will always be guaranteed space in the main meeting.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="ca5b9-140">对会议演示者的影响</span><span class="sxs-lookup"><span data-stu-id="ca5b9-140">Impact to meeting presenters</span></span>

<span data-ttu-id="ca5b9-141">对会议演示者的限制包括：</span><span class="sxs-lookup"><span data-stu-id="ca5b9-141">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="ca5b9-142">你不会有任何关于仅查看与会者的信息。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-142">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="ca5b9-143">我们不支持仅查与会者的电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-143">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="ca5b9-144">主会议中的用户看不到仅查看与会者。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-144">Users in the main meeting can't see the view-only attendees.</span></span>
- <span data-ttu-id="ca5b9-145">不能从会议中删除仅查看的与会者。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-145">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="ca5b9-146">与会者计数仅反映主会议中的人员，而不是仅查看会议室中的人员。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-146">Attendee count will only reflect the people in the main meeting and not the people in the view-only room.</span></span> <span data-ttu-id="ca5b9-147">因此，演示者无法准确统计仅查看体验中的用户。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-147">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="ca5b9-148">仅查看与会者的体验</span><span class="sxs-lookup"><span data-stu-id="ca5b9-148">Experience for view-only attendees</span></span>

<span data-ttu-id="ca5b9-149">通过 Teams 的仅查看体验，与会者可以:</span><span class="sxs-lookup"><span data-stu-id="ca5b9-149">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="ca5b9-150">收听主 Teams 会议中参与者的发言。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-150">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="ca5b9-151">查看当前发言者的视频源 (如果当前发言者正在共享视频)。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-151">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="ca5b9-152">查看使用共享桌面或屏幕功能共享的内容。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-152">See content being shared using the share desktop or screen functionality.</span></span>

<span data-ttu-id="ca5b9-153">仅查看中的与会者将无法在会议中体验以下选项:</span><span class="sxs-lookup"><span data-stu-id="ca5b9-153">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="ca5b9-154">如果与会者没有根据设定的大厅政策或选项绕过大厅的权限，加入会议。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-154">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="ca5b9-155">使用音频会议加入仅查看会议室。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-155">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="ca5b9-156">使用 Microsoft Teams 会议室系统或 CVI 服务中的云视频互操作 (仅) 聊天室。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-156">Join the view-only room using Microsoft Teams Rooms system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="ca5b9-157">共享他们的音频或视频。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-157">Share their audio or video.</span></span>
- <span data-ttu-id="ca5b9-158">查看或参与会议聊天。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-158">See or participate in the meeting chat.</span></span>
  - <span data-ttu-id="ca5b9-159">前 1000 (或 300（具体取决于主会议限制) 受邀加入会议的用户将被添加到聊天中。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-159">The first 1000 (or 300 depending on your main meeting limit) users invited to the meeting will be added to the chat.</span></span>
  - <span data-ttu-id="ca5b9-160">虽然仅查看用户不会在会议中看到聊天，但如果是受邀的前 350 名用户，他们仍可以在主应用上聊天。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-160">While view-only users won't see the chat in the meeting, they might still be able to chat on the main app if they were the first 350 people invited.</span></span>
  - <span data-ttu-id="ca5b9-161">相反，如果交互式用户不是前 350 位受邀加入会议的用户的一部分，他们将无法访问主 Teams 应用和会议中的会议聊天。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-161">Conversely, if an interactive user wasn't part of the first 350 users invited to the meeting, they'll not get access to the meeting chat both on the main Teams App and in the meeting.</span></span>
- <span data-ttu-id="ca5b9-162">除非与会者是主动发言的人，否则可以看到会议参与者的视频源。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-162">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="ca5b9-163">查看使用 PowerPoint Live 功能共享的 PowerPoint 文件，或者使用桌面或屏幕共享功能 (应用程序共享共享) 。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-163">See PowerPoint files that are shared using the PowerPoint Live functionality or individual application shares (other than desktop or screen sharing).</span></span>
- <span data-ttu-id="ca5b9-164">在会议中举手。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-164">Raise their hand in the meeting.</span></span>
- <span data-ttu-id="ca5b9-165">发送或查看回应。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-165">Send or see reactions.</span></span>
- <span data-ttu-id="ca5b9-166">与集成到 Teams 会议的任何 3P 应用（包括投票）交互。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-166">Interact with any 3P App integrating into the Teams Meeting, including Polls.</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="ca5b9-167">仅查看功能限制</span><span class="sxs-lookup"><span data-stu-id="ca5b9-167">View-only feature limitations</span></span>

- <span data-ttu-id="ca5b9-168">仅查看与会者只能在桌面和 Web 上看到实时字幕。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-168">View-only attendees will only be able to see Live Captions on Desktop and Web.</span></span> <span data-ttu-id="ca5b9-169">目前只支持英文字幕。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-169">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="ca5b9-170">仅查看的与会者将得到流媒体处理技术的支持。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-170">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="ca5b9-171">仅查看的与会者不会列入出席报告中。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-171">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="ca5b9-172">仅查看的与会者将有单一的视频体验。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-172">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="ca5b9-173">他们可以看到活动发言人或共享的内容，但不能两者同时看到。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-173">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="ca5b9-174">我们当前不支持 **库**、**大型库** 或仅供与会者浏览的 **同框场景模式**。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-174">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="ca5b9-175">仅查看的与会者不会有和普通与会者一样的延迟。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-175">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="ca5b9-176"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ca5b9-176"><sup>1</sup></span></span>

  <span data-ttu-id="ca5b9-177"><sup>1</sup> 仅查看的与会者将在会议上有 30 秒的视频和音频延迟。</span><span class="sxs-lookup"><span data-stu-id="ca5b9-177"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
