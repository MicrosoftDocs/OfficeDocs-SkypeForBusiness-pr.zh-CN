---
title: 仅查看会议体验
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
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
ms.openlocfilehash: 54bbb3c00aae8a2785e867be9614f8509ca9344d
ms.sourcegitcommit: 75ccb8cda9e6dd900df93a2d856ff5f7682ac623
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2021
ms.locfileid: "50237452"
---
# <a name="teams-view-only-meeting-experience"></a><span data-ttu-id="0cf2f-103">Teams 仅查看会议体验</span><span class="sxs-lookup"><span data-stu-id="0cf2f-103">Teams view-only meeting experience</span></span>

> [!Note]
> <span data-ttu-id="0cf2f-104">仅查看会议体验将于 2021 年 3 月初提供。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-104">View-only meeting experience will be available in early March 2021.</span></span>

> [!Note]
> <span data-ttu-id="0cf2f-105">我们暂时增加了 20，000 名与会者的仅查看体验，但 2021 年 6 月 30 日，我们将支持恢复到 10，000 名与会者。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-105">We've temporarily increased view-only experience for 20,000 attendees, but we'll revert support to 10,000 attendees on June 30, 2021.</span></span>

<span data-ttu-id="0cf2f-106">Microsoft Teams 允许最多 10，000 名与会者加入 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-106">Microsoft Teams allows up to 10,000 attendees to join a Teams meeting.</span></span> <span data-ttu-id="0cf2f-107">达到主会议的容量后，其他与会者将加入仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-107">After the capacity of the main meeting has been reached, additional attendees will join with a view-only experience.</span></span>

<span data-ttu-id="0cf2f-108">首先加入会议的与会者（最多是会议容量）将获得完整的 Teams 会议体验。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-108">Attendees who join the meeting first, up to the capacity of the meeting, will get the full Teams meeting experience.</span></span> <span data-ttu-id="0cf2f-109">他们可以共享音频和视频、查看共享的视频以及参与会议聊天。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-109">They can share audio and video, see shared videos, and participate in meeting chat.</span></span>

<span data-ttu-id="0cf2f-110">达到主要会议容量后加入的与会者将拥有仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-110">Attendees who join after the main meeting capacity has been reached will have a view-only experience.</span></span>

<span data-ttu-id="0cf2f-111">我们提供完整的 Android 和 iOS 移动支持，与会者可加入。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-111">We have full Android and iOS mobile support for an attendee to join.</span></span>

> [!Note]
> <span data-ttu-id="0cf2f-112">在 WW 中，可以聊天和呼叫参加会议的人数当前限制为 300 人，GCC、GCC High 和 DoD 中为 250 人。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-112">The current limit for the number of people who can chat and call in to a meeting is 300 in WW and 250 in GCC, GCC High, and DoD.</span></span>

<span data-ttu-id="0cf2f-113">默认情况下，任何拥有 E3/E5/A3/A5 SKU 的组织者都启用仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-113">The view-only experience is enabled by default for any organizer who has E3/E5/A3/A5 SKU.</span></span> <span data-ttu-id="0cf2f-114">无需进一步配置或设置。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-114">No further configuration or setup is required.</span></span>

### <a name="disable-teams-view-only-experience"></a><span data-ttu-id="0cf2f-115">禁用 Teams 仅查看体验</span><span class="sxs-lookup"><span data-stu-id="0cf2f-115">Disable Teams view-only experience</span></span>

<span data-ttu-id="0cf2f-116">管理员可以使用 PowerShell 禁用仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-116">Administrators can disable the view-only experience using PowerShell.</span></span>

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -StreamingAttendeeMode Disabled
```

<span data-ttu-id="0cf2f-117">将来，管理员还可以在 Teams 管理中心禁用仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-117">In the future, it will also be possible for administrators to disable the view-only experience in the Teams admin center.</span></span>

## <a name="impact-to-users"></a><span data-ttu-id="0cf2f-118">对用户的影响</span><span class="sxs-lookup"><span data-stu-id="0cf2f-118">Impact to users</span></span>

<span data-ttu-id="0cf2f-119">用户的体验因若干因素而异。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-119">A user's experience will vary depending on several factors.</span></span>

<span data-ttu-id="0cf2f-120">当达到主会议的容量时，如果满足以下任一条件，与会者将无法加入会议：</span><span class="sxs-lookup"><span data-stu-id="0cf2f-120">When the capacity of the main meeting has been reached, an attendee will be unable to join the meeting if any of the following are true:</span></span>

- <span data-ttu-id="0cf2f-121">管理员已禁用 Teams 仅查看体验。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-121">An administrator has disabled the Teams view-only experience.</span></span>
- <span data-ttu-id="0cf2f-122">与会者无权绕过大厅。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-122">The attendee doesn't have permission to bypass the lobby.</span></span>

<span data-ttu-id="0cf2f-123">达到主会议的容量后，会议组织者和演示者将看到一个横幅，告知他们已达到会议容量，并且新与会者将加入仅查看的与会者。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-123">When the capacity of the main meeting has been reached, the meeting organizer and presenters will see a banner informing them that the meeting capacity has been reached and that new attendees will join a view-only attendee.</span></span>

  ![组织者和演示者的 Teams 客户端和横幅混乱](media/chat-and-banner-message.png)

<span data-ttu-id="0cf2f-125">当达到主会议的容量时，会议与会者将在加入前屏幕上通知他们正在仅查看模式下加入。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-125">When the capacity of the main meeting has been reached, meeting attendees will be informed on the pre-join screen that they're joining in view-only mode.</span></span>

  ![Teams 预加入屏幕和参与者的消息，告知他们将在仅查看模式下加入](media/view-only-pre-join-screen.png)

<span data-ttu-id="0cf2f-127">如果有空间，用户始终会加入主会议。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-127">If there's space, a user will always join the main meeting.</span></span> <span data-ttu-id="0cf2f-128">如果主会议达到容量，并且一个或多个与会者离开主会议，则主会议具有可用容量。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-128">If the main meeting reaches capacity, and one or more attendees leave the main meeting, the main meeting has available capacity.</span></span> <span data-ttu-id="0cf2f-129">加入会议或 (会议) 与会者将加入主会议，直到会议再次达到容量。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-129">Attendees who join (or rejoin) the meeting will join the main meeting until it reaches capacity again.</span></span> <span data-ttu-id="0cf2f-130">处于"仅查看"体验的与会者不会自动提升为主会议，当前无法手动提升为主会议。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-130">Attendees who are in the view-only experience won't automatically be promoted to the main meeting and can't currently be manually promoted to the main meeting.</span></span>

<span data-ttu-id="0cf2f-131">如果尚未设置演示者/与会者角色，主会议中的空间将先到先得地填充。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-131">If presenter/attendee roles haven't been set, spaces in the main meeting are filled on a first-come, first-served basis.</span></span> <span data-ttu-id="0cf2f-132">达到会议容量后，所有其他用户将使用仅查看体验加入。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-132">Once the meeting capacity has been reached, all other users will join with a view-only experience.</span></span>

## <a name="impact-to-meeting-presenters"></a><span data-ttu-id="0cf2f-133">对会议演示者的影响</span><span class="sxs-lookup"><span data-stu-id="0cf2f-133">Impact to meeting presenters</span></span>

<span data-ttu-id="0cf2f-134">我们将在普通会议中为在会议选项中明确指示为演示者的用户保留空间。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-134">We'll reserve space in the normal meeting for users explicitly indicated as presenters in the meeting options.</span></span> <span data-ttu-id="0cf2f-135">如果演示者离开，然后又重新加入会议，他们将作为演示者进入会议。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-135">If a presenter leaves and then later rejoins the meeting, they'll be let into the meeting as a presenter.</span></span>

<span data-ttu-id="0cf2f-136">会议演示者的限制包括：</span><span class="sxs-lookup"><span data-stu-id="0cf2f-136">Limitations for meeting presenters include:</span></span>

- <span data-ttu-id="0cf2f-137">您将没有有关仅查看与会者的信息。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-137">You'll have no information about the view-only attendee.</span></span> <span data-ttu-id="0cf2f-138">我们不支持仅查看与会者的 E-discovery。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-138">We don't support E-discovery for view-only attendees.</span></span>
- <span data-ttu-id="0cf2f-139">用户看不到仅查看与会者。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-139">Users can't see the view-only attendees.</span></span>
- <span data-ttu-id="0cf2f-140">不能从会议中删除仅查看与会者。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-140">You can't remove a view-only attendee from the meeting.</span></span>

> [!Note]
> <span data-ttu-id="0cf2f-141">与会者计数将仅反映会议中的人员，而不是溢出会议室中的人员。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-141">Attendee count will only reflect the people in the meeting and not the people in the overflow room.</span></span> <span data-ttu-id="0cf2f-142">因此，演示者无法获取仅查看体验中的人员的确切计数。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-142">Therefore, presenters can't get an exact count of who is in the view-only experience.</span></span>

## <a name="experience-for-view-only-attendees"></a><span data-ttu-id="0cf2f-143">仅查看与会者的体验</span><span class="sxs-lookup"><span data-stu-id="0cf2f-143">Experience for view-only attendees</span></span>

<span data-ttu-id="0cf2f-144">Teams 仅查看体验允许与会者：</span><span class="sxs-lookup"><span data-stu-id="0cf2f-144">The Teams view-only experience allows attendees to:</span></span>

- <span data-ttu-id="0cf2f-145">在 Teams 主要会议中听取参与者的意见。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-145">Listen to the participants in the main Teams meeting.</span></span>
- <span data-ttu-id="0cf2f-146">如果活动发言人正在共享视频， (活动扬声器的视频源) 。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-146">See the video feed for the active speaker (if the active speaker is sharing video).</span></span>
- <span data-ttu-id="0cf2f-147">查看使用共享桌面功能共享的内容。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-147">See content being shared using the share desktop functionality.</span></span>

<span data-ttu-id="0cf2f-148">仅查看与会者将无法在会议中体验以下选项：</span><span class="sxs-lookup"><span data-stu-id="0cf2f-148">The view-only attendee won't be able to experience the following options in meetings:</span></span>

- <span data-ttu-id="0cf2f-149">如果与会者没有权限根据设置的大厅策略或选项绕过大厅，请加入会议。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-149">Join the meeting if the attendee doesn't have permission to bypass the lobby based on set lobby policies or options.</span></span>
- <span data-ttu-id="0cf2f-150">通过音频会议加入溢出会议室。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-150">Join the Overflow Room via Audio Conferencing.</span></span>
- <span data-ttu-id="0cf2f-151">通过 Microsoft Teams Room 系统或通过 CVI 云视频互操作 (加入溢出) 服务。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-151">Join the Overflow Room via Microsoft Teams Room system or via Cloud Video Interop (CVI) services.</span></span>
- <span data-ttu-id="0cf2f-152">通过 Teams Android 移动应用加入 Overflow Room。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-152">Join the Overflow Room via the Teams Android mobile app.</span></span>
- <span data-ttu-id="0cf2f-153">共享其音频或视频。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-153">Share their audio or video.</span></span>
- <span data-ttu-id="0cf2f-154">查看或参与会议聊天。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-154">See or participate in the meeting chat.</span></span>
- <span data-ttu-id="0cf2f-155">查看会议参与者的视频源，除非参与者是活动发言人。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-155">See the video feed of meeting participants unless the participant is the active speaker.</span></span>
- <span data-ttu-id="0cf2f-156">查看使用本机共享 PowerPoint 功能或单个应用程序共享共享的 PowerPoint (桌面共享) 。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-156">See PowerPoint files that are shared using the native share PowerPoint functionality or individual application shares (other than desktop sharing).</span></span>

## <a name="view-only-feature-limitations"></a><span data-ttu-id="0cf2f-157">仅查看功能限制</span><span class="sxs-lookup"><span data-stu-id="0cf2f-157">View-only feature limitations</span></span>

- <span data-ttu-id="0cf2f-158">仅查看的与会者将始终看到实时字幕，而不考虑该会议的实时字幕设置。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-158">View-only attendees will always see live captions, regardless of the live-captions setting for that meeting.</span></span> <span data-ttu-id="0cf2f-159">目前仅支持英语字幕。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-159">Only English Captions are supported at this time.</span></span>
- <span data-ttu-id="0cf2f-160">流式处理技术将支持仅查看与会者。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-160">View-only attendees will be supported by streaming technology.</span></span>
- <span data-ttu-id="0cf2f-161">仅查看的与会者不会包括在出席报告中。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-161">View-only attendees won't be included in the attendance report.</span></span>
- <span data-ttu-id="0cf2f-162">仅查看与会者将拥有单个视频体验。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-162">View-only attendees will have a single video experience.</span></span> <span data-ttu-id="0cf2f-163">他们可以看到活动发言人或正在共享的内容，但不能同时看到两者。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-163">They can see either the active speaker or the content being shared, but not both.</span></span>
- <span data-ttu-id="0cf2f-164">我们当前不支持仅查看与会者的库、大型库或"共同"模式布局。 </span><span class="sxs-lookup"><span data-stu-id="0cf2f-164">We don't currently support **Gallery**, **Large gallery**, or **Together mode** layouts for view-only attendees.</span></span>  
- <span data-ttu-id="0cf2f-165">仅查看与会者的延迟与普通与会者不同。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-165">View-only attendees won't have the same latency as a regular attendee.</span></span> <span data-ttu-id="0cf2f-166"><sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0cf2f-166"><sup>1</sup></span></span>

  <span data-ttu-id="0cf2f-167"><sup>1</sup> 个仅查看与会者将在会议进行 30 秒的视频和音频延迟。</span><span class="sxs-lookup"><span data-stu-id="0cf2f-167"><sup>1</sup> View-only attendees will be at a 30-second video and audio delay in the meeting.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="0cf2f-168">相关主题</span><span class="sxs-lookup"><span data-stu-id="0cf2f-168">Related topics</span></span>

- [<span data-ttu-id="0cf2f-169">Teams 的高级通信加载项</span><span class="sxs-lookup"><span data-stu-id="0cf2f-169">Advanced communications add-on for Teams</span></span>](teams-add-on-licensing/advanced-communications.md)
- [<span data-ttu-id="0cf2f-170">Teams 限制和规范</span><span class="sxs-lookup"><span data-stu-id="0cf2f-170">Limits and specifications for Teams</span></span>](limits-specifications-teams.md)
