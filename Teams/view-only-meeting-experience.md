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
ms.openlocfilehash: 6fc7838ac1f3235acf576d437e3dabccfc2a0b6f
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875052"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="8ffb3-103">Teams 仅查看会议体验</span><span class="sxs-lookup"><span data-stu-id="8ffb3-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="8ffb3-104">Microsoft 365 E3/E5 和 Microsoft 365 A3/A5 中提供了仅查看广播。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-104">View-only broadcasts is available in Microsoft 365 E3/E5 and Microsoft 365 A3/A5.</span></span> <span data-ttu-id="8ffb3-105">该功能将于 2021 年 3 月 1 日启用，默认为“关闭”。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-105">This feature will be enabled March 1, 2021 as default OFF.</span></span> <span data-ttu-id="8ffb3-106">Microsoft 365 政府社区云 (GCC) 中的该功能将于 2021 年 3 月底开始推出。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-106">The feature in Microsoft 365 Government Community Cloud (GCC) will begin to roll out at the end of March 2021.</span></span> <span data-ttu-id="8ffb3-107">政府社区云高 (GCCH) 和国防部 (DoD) 将在日后推出。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-107">Government Community Cloud High (GCCH) and Department of Defense (DoD) will roll out at a later date.</span></span> <span data-ttu-id="8ffb3-108">如果想让该功能默认为 “启动”，必须在该日期之后更改默认策略。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-108">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="8ffb3-109">使用 PowerShell 启用策略 `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-109">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="8ffb3-110">如果会议或网络研讨会达到饱和状态，Teams 将无缝扩展至容纳 10,000 人的仅限观看广播体验。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-110">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="8ffb3-111">另外，在这个远程工作增加的时期，利用更大规模的 20,000 人广播到今年年底。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-111">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="8ffb3-112">Microsoft Teams 允许最多 10,000 名与会者加入一个 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-112">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="8ffb3-113">达到主会场的容量后，更多的参会人员将参加仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-113">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="8ffb3-114">先加入会议的参会者，以会议容量为限，将获得完整的 Teams 会议体验。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-114">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="8ffb3-115">他们可以共享音频和视频、查看共享视频、并参与会议聊天。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-115">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="8ffb3-116">在达到主会场容量后加入的与会者将有仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-116">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="8ffb3-117">我们有完整的 Android 和 iOS 手机支持供与会者加入。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-117">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="8ffb3-118">目前，WWW 的聊天和电话会议人数限制是 300 人，GCC、GCC High 和 DoD 的是 250 人。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-118">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="8ffb3-119">凡是拥有 E3/E5/A3/A5 SKU 的组织者，默认禁用仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-119">The view-only experience is disabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="8ffb3-120">无需进一步配置或设置。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-120">No further configuration or setup is required.</span></span>

## <a name="disable-teams-view-only-experience"></a><span data-ttu-id="8ffb3-121">禁用 Teams 仅查看体验</span><span class="sxs-lookup"><span data-stu-id="8ffb3-121">Disable Teams view-only experience</span></span>

<span data-ttu-id="8ffb3-122">管理员可以使用 PowerShell 禁用仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-122">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="8ffb3-123">未来，管理员还可以在 Teams 管理中心中禁用仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-123">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="8ffb3-124">对用户的影响</span><span class="sxs-lookup"><span data-stu-id="8ffb3-124">Impact to users</span></span>

<span data-ttu-id="8ffb3-125">用户的体验会因多种因素而有所不同。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-125">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="8ffb3-126">当主会场容量已满时，如有下列情况之一，与会者将无法参加会议:</span><span class="sxs-lookup"><span data-stu-id="8ffb3-126">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="8ffb3-127">一位管理员已经禁用了团队仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-127">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="8ffb3-128">与会者没有绕过大厅的权限。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-128">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="8ffb3-129">当达到主会议的容量时，会议组织者和演讲者会看到一条横幅，通知他们会议容量已经达到，新的参会者将加入仅查看与会者中。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-129">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![为组织者和演讲者提供 Teams 客户端和横幅信息](media/chat-and-banner-message.png)

<span data-ttu-id="8ffb3-131">当达到主会议的容量时，会议平台会在预加入界面上通知他们以仅查看模式加入。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-131">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![Teams 预加入屏幕和告诉参与者他们将以纯视图模式加入的信息](media/view-only-pre-join-screen.png)

<span data-ttu-id="8ffb3-133">如果有空间，用户将始终加入主会议。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-133">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="8ffb3-134">如果主会场达到容纳量，有一名或多名与会者离开主会场，则主会场有可用容量。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-134">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="8ffb3-135">加入 (或重新加入) 会议的与会者将加入主会议，直到会议再次达到饱和。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-135">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="8ffb3-136">处于仅查看体验中的参会者不会自动晋升到主会议，目前无法手动晋升到主会议。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-136">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="8ffb3-137">如果没有确定演示者/与会者的角色，主会场的位置将按照先到先得的原则填补。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-137">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="8ffb3-138">一旦达到会议容量，所有其他用户都将以进查看体验加入。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-138">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="8ffb3-139">对会议演示者的影响</span><span class="sxs-lookup"><span data-stu-id="8ffb3-139">Impact to meeting presenters</span></span>

<span data-ttu-id="8ffb3-140">对会议演示者的限制包括：</span><span class="sxs-lookup"><span data-stu-id="8ffb3-140">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="8ffb3-141">你不会有任何关于仅查看与会者的信息。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-141">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="8ffb3-142">我们不支持仅查与会者的电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-142">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="8ffb3-143">用户无法看到仅查看的与会者。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-143">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="8ffb3-144">不能从会议中删除仅查看的与会者。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-144">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="8ffb3-145">出席人数将只反映会议中的人员，而不反映仅查看会议室中的人员。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-145">Attendee count will only reflect the people in the meeting and not the people in the view-only room.</span></span> <span data-ttu-id="8ffb3-146">因此，演示者无法准确统计仅查看体验中的用户。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-146">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="8ffb3-147">仅查看与会者的体验</span><span class="sxs-lookup"><span data-stu-id="8ffb3-147">Experience for view-only attendees</span></span>

<span data-ttu-id="8ffb3-148">通过 Teams 的仅查看体验，与会者可以:</span><span class="sxs-lookup"><span data-stu-id="8ffb3-148">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="8ffb3-149">收听主 Teams 会议中参与者的发言。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-149">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="8ffb3-150">查看当前发言者的视频源 (如果当前发言者正在共享视频)。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-150">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="8ffb3-151">查看使用共享桌面功能共享的内容。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-151">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="8ffb3-152">仅查看中的与会者将无法在会议中体验以下选项:</span><span class="sxs-lookup"><span data-stu-id="8ffb3-152">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="8ffb3-153">如果与会者没有根据设定的大厅政策或选项绕过大厅的权限，加入会议。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-153">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="8ffb3-154">使用音频会议加入仅查看会议室。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-154">Join the view-only room using Audio Conferencing.</span></span>
- <span data-ttu-id="8ffb3-155">使用 Microsoft Teams 会议室系统或使用云视频互操作(CVI) 服务，加入仅查看会议室。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-155">Join the view-only room using Microsoft Teams Room system or using Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="8ffb3-156">共享他们的音频或视频。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-156">Share their audio or video.</span></span>
- <span data-ttu-id="8ffb3-157">查看或参与会议聊天。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-157">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="8ffb3-158">除非与会者是主动发言的人，否则可以看到会议参与者的视频源。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-158">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="8ffb3-159">请参阅使用本机共享 PowerPoint 功能或单个应用程序共享 (除桌面共享外) 共享的 PowerPoint 文件。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-159">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="8ffb3-160">仅查看功能限制</span><span class="sxs-lookup"><span data-stu-id="8ffb3-160">View-only feature limitations</span></span>

- <span data-ttu-id="8ffb3-161">无论该会议的实时字幕设置如何，仅查看的与会者将始终看到实时字幕。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-161">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="8ffb3-162">目前只支持英文字幕。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-162">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="8ffb3-163">仅查看的与会者将得到流媒体处理技术的支持。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-163">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="8ffb3-164">仅查看的与会者不会列入出席报告中。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-164">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="8ffb3-165">仅查看的与会者将有单一的视频体验。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-165">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="8ffb3-166">他们可以看到活动发言人或共享的内容，但不能两者同时看到。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-166">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="8ffb3-167">我们当前不支持 **库**、**大型库** 或仅供与会者浏览的 **同框场景模式**。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-167">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="8ffb3-168">仅查看的与会者不会有和普通与会者一样的延迟。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-168">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="8ffb3-169"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8ffb3-169"><sup>1</sup></span></span>

  <span data-ttu-id="8ffb3-170"><sup>1</sup> 仅查看的与会者将在会议上有 30 秒的视频和音频延迟。</span><span class="sxs-lookup"><span data-stu-id="8ffb3-170"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  
