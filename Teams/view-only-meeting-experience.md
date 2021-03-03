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
description: 了解管理员、演示者和与会者的 Teams 仅查看会议体验
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 49f65e1ff47caefd61a9b2753b12da23fd2184e9
ms.sourcegitcommit: b0753baa55841a2c6c5dc006dcdd117704af3b42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2021
ms.locfileid: "50401316"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="74e10-103">Teams 仅查看会议体验</span><span class="sxs-lookup"><span data-stu-id="74e10-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="74e10-104">仅查看会议体验将于 2021 年 3 月初提供。</span><span class="sxs-lookup"><span data-stu-id="74e10-104">View-only meeting experience will be available in early March 2021.</span></span> <span data-ttu-id="74e10-105">此功能将在 2021 年 3 月 1 日启用为默认关闭。</span><span class="sxs-lookup"><span data-stu-id="74e10-105">This feature will be enabled on March 1,2021 as default OFF.</span></span> <span data-ttu-id="74e10-106">如果希望将该功能设置为"默认打开"，则必须在此日期之后更改默认策略。</span><span class="sxs-lookup"><span data-stu-id="74e10-106">You must change the default policy after that date if you want to have the feature be default ON.</span></span> <span data-ttu-id="74e10-107">使用 PowerShell 启用策略 `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="74e10-107">Use PowerShell to enable the policy `Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Enabled`.</span></span>

> [!Note]
> <span data-ttu-id="74e10-108">如果会议或网络研讨会达到容量要求，Teams 将无缝缩放，以容纳 10，000 人仅查看的直播体验。</span><span class="sxs-lookup"><span data-stu-id="74e10-108">If your meeting or webinar hits capacity, Teams will seamlessly scale to accommodate a 10,000-person view-only broadcast experience.</span></span> <span data-ttu-id="74e10-109">此外，在这期间增加远程工作，充分利用今年年底甚至更多的 20，000 人直播。</span><span class="sxs-lookup"><span data-stu-id="74e10-109">Plus, during this time of increased remote work, take advantage of even larger 20,000-person broadcasts through the end of this year.</span></span>

<span data-ttu-id="74e10-110">Microsoft Teams 允许最多 10，000 名与会者加入 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="74e10-110">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="74e10-111">达到主会议的容量后，其他与会者将加入仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="74e10-111">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="74e10-112">首先加入会议的与会者（最多是会议容量）将获得完整的 Teams 会议体验。</span><span class="sxs-lookup"><span data-stu-id="74e10-112">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="74e10-113">他们可以共享音频和视频、查看共享的视频以及参与会议聊天。</span><span class="sxs-lookup"><span data-stu-id="74e10-113">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="74e10-114">达到主要会议容量后加入的与会者将拥有仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="74e10-114">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="74e10-115">我们提供完整的 Android 和 iOS 移动支持，与会者可加入。</span><span class="sxs-lookup"><span data-stu-id="74e10-115">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="74e10-116">在 WW 中，可以聊天和呼叫会议的人数当前限制为 300 人，GCC、GCC High 和 DoD 中为 250 人。</span><span class="sxs-lookup"><span data-stu-id="74e10-116">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="74e10-117">对于拥有 E3/E5/A3/A5 SKU 的任何组织者，默认禁用仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="74e10-117">The view-only experience is disabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="74e10-118">无需进一步配置或设置。</span><span class="sxs-lookup"><span data-stu-id="74e10-118">No further configuration or setup is required.</span></span>

## <a name="disable-teams-view-only-experience"></a><span data-ttu-id="74e10-119">禁用 Teams 仅查看体验</span><span class="sxs-lookup"><span data-stu-id="74e10-119">Disable Teams view-only experience</span></span>

<span data-ttu-id="74e10-120">管理员可以使用 PowerShell 禁用仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="74e10-120">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="74e10-121">将来，管理员还可以在 Teams 管理中心禁用仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="74e10-121">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="74e10-122">对用户的影响</span><span class="sxs-lookup"><span data-stu-id="74e10-122">Impact to users</span></span>

<span data-ttu-id="74e10-123">用户的体验因若干因素而异。</span><span class="sxs-lookup"><span data-stu-id="74e10-123">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="74e10-124">当达到主会议的容量时，如果满足以下任一条件，与会者将无法加入会议：</span><span class="sxs-lookup"><span data-stu-id="74e10-124">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="74e10-125">管理员已禁用 Teams 仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="74e10-125">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="74e10-126">与会者无权绕过大厅。</span><span class="sxs-lookup"><span data-stu-id="74e10-126">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="74e10-127">达到主会议的容量后，会议组织者和演示者将看到一个横幅，通知他们已达到会议容量，新与会者将加入仅查看的与会者。</span><span class="sxs-lookup"><span data-stu-id="74e10-127">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![组织者和演示者的 Teams 客户端和横幅混乱](media/chat-and-banner-message.png)

<span data-ttu-id="74e10-129">当达到主会议的容量时，会议与会者将在加入前屏幕上通知他们以仅查看模式加入。</span><span class="sxs-lookup"><span data-stu-id="74e10-129">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![Teams 预加入屏幕和参与者的消息，告知他们将在仅查看模式下加入](media/view-only-pre-join-screen.png)

<span data-ttu-id="74e10-131">如果有空间，用户始终会加入主会议。</span><span class="sxs-lookup"><span data-stu-id="74e10-131">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="74e10-132">如果主会议达到容量，并且一个或多个与会者离开主会议，则主会议具有可用容量。</span><span class="sxs-lookup"><span data-stu-id="74e10-132">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="74e10-133">加入会议或 (会议) 与会者将加入主会议，直到再次达到容量。</span><span class="sxs-lookup"><span data-stu-id="74e10-133">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="74e10-134">处于"仅查看"体验的与会者不会自动提升为主会议，当前无法手动提升为主会议。</span><span class="sxs-lookup"><span data-stu-id="74e10-134">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="74e10-135">如果尚未设置演示者/与会者角色，主会议中的空间将先到先得地填充。</span><span class="sxs-lookup"><span data-stu-id="74e10-135">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="74e10-136">达到会议容量后，所有其他用户将使用仅查看体验加入。</span><span class="sxs-lookup"><span data-stu-id="74e10-136">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="74e10-137">对会议演示者的影响</span><span class="sxs-lookup"><span data-stu-id="74e10-137">Impact to meeting presenters</span></span>

<span data-ttu-id="74e10-138">会议演示者的限制包括：</span><span class="sxs-lookup"><span data-stu-id="74e10-138">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="74e10-139">您将没有有关仅查看与会者的信息。</span><span class="sxs-lookup"><span data-stu-id="74e10-139">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="74e10-140">我们不支持仅查看与会者的 E-discovery。</span><span class="sxs-lookup"><span data-stu-id="74e10-140">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="74e10-141">用户看不到仅查看的与会者。</span><span class="sxs-lookup"><span data-stu-id="74e10-141">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="74e10-142">不能从会议中删除仅查看与会者。</span><span class="sxs-lookup"><span data-stu-id="74e10-142">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="74e10-143">与会者计数将仅反映会议中的人员，而不是溢出会议室中的人员。</span><span class="sxs-lookup"><span data-stu-id="74e10-143">Attendee count will only reflect the people in the meeting and not the people in the overflow room.</span></span> <span data-ttu-id="74e10-144">因此，演示者无法获取仅查看体验中的人员的确切计数。</span><span class="sxs-lookup"><span data-stu-id="74e10-144">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="74e10-145">仅查看与会者的体验</span><span class="sxs-lookup"><span data-stu-id="74e10-145">Experience for view-only attendees</span></span>

<span data-ttu-id="74e10-146">Teams 仅查看体验允许与会者：</span><span class="sxs-lookup"><span data-stu-id="74e10-146">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="74e10-147">在 Teams 主要会议中听取参与者的意见。</span><span class="sxs-lookup"><span data-stu-id="74e10-147">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="74e10-148">如果活动发言人正在共享视频， (活动扬声器的视频源) 。</span><span class="sxs-lookup"><span data-stu-id="74e10-148">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="74e10-149">查看使用共享桌面功能共享的内容。</span><span class="sxs-lookup"><span data-stu-id="74e10-149">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="74e10-150">仅查看与会者将无法在会议中体验以下选项：</span><span class="sxs-lookup"><span data-stu-id="74e10-150">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="74e10-151">如果与会者没有权限根据设置的大厅策略或选项绕过大厅，请加入会议。</span><span class="sxs-lookup"><span data-stu-id="74e10-151">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="74e10-152">通过音频会议加入溢出会议室。</span><span class="sxs-lookup"><span data-stu-id="74e10-152">Join the Overflow Room via Audio Conferencing.</span></span>
- <span data-ttu-id="74e10-153">通过 Microsoft Teams Room 系统或通过 CVI 云视频互操作 (加入溢出) 服务。</span><span class="sxs-lookup"><span data-stu-id="74e10-153">Join the Overflow Room via Microsoft Teams Room system or via Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="74e10-154">共享其音频或视频。</span><span class="sxs-lookup"><span data-stu-id="74e10-154">Share their audio or video.</span></span>
- <span data-ttu-id="74e10-155">查看或参与会议聊天。</span><span class="sxs-lookup"><span data-stu-id="74e10-155">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="74e10-156">查看会议参与者的视频源，除非参与者是活动发言人。</span><span class="sxs-lookup"><span data-stu-id="74e10-156">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="74e10-157">查看使用本机共享 PowerPoint 功能共享的 PowerPoint 文件或桌面共享 (应用程序共享) 。</span><span class="sxs-lookup"><span data-stu-id="74e10-157">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="74e10-158">仅查看功能限制</span><span class="sxs-lookup"><span data-stu-id="74e10-158">View-only feature limitations</span></span>

- <span data-ttu-id="74e10-159">无论会议的实时字幕设置如何，仅查看的与会者将始终看到实时字幕。</span><span class="sxs-lookup"><span data-stu-id="74e10-159">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="74e10-160">目前仅支持英语字幕。</span><span class="sxs-lookup"><span data-stu-id="74e10-160">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="74e10-161">流式处理技术将支持仅查看与会者。</span><span class="sxs-lookup"><span data-stu-id="74e10-161">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="74e10-162">仅查看的与会者不会包括在出席报告中。</span><span class="sxs-lookup"><span data-stu-id="74e10-162">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="74e10-163">仅查看与会者将拥有单个视频体验。</span><span class="sxs-lookup"><span data-stu-id="74e10-163">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="74e10-164">他们可以看到活动发言人或正在共享的内容，但不能同时看到这两者。</span><span class="sxs-lookup"><span data-stu-id="74e10-164">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="74e10-165">我们当前不支持仅查看与会者的库、大型库或"共同"模式布局。 </span><span class="sxs-lookup"><span data-stu-id="74e10-165">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="74e10-166">仅查看与会者的延迟与普通与会者不同。</span><span class="sxs-lookup"><span data-stu-id="74e10-166">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="74e10-167"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="74e10-167"><sup>1</sup></span></span>

  <span data-ttu-id="74e10-168"><sup>1</sup> 个仅查看与会者将在会议进行 30 秒的视频和音频延迟。</span><span class="sxs-lookup"><span data-stu-id="74e10-168"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="74e10-169">相关主题</span><span class="sxs-lookup"><span data-stu-id="74e10-169">Related topics</span></span>

- [<span data-ttu-id="74e10-170">Teams 的高级通信加载项</span><span class="sxs-lookup"><span data-stu-id="74e10-170">Advanced communications add-on for Teams</span></span>](teams-add-on-licensing/advanced-communications.md)
- [<span data-ttu-id="74e10-171">Teams 限制和规范</span><span class="sxs-lookup"><span data-stu-id="74e10-171">Limits and specifications for Teams</span></span>](limits-specifications-teams.md)
