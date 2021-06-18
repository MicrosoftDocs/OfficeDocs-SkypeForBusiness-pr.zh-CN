---
title: 管理音频和视频的会议策略
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
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- seo-marvel-apr2020
description: 了解如何在音频和视频的Teams管理会议策略设置。
ms.openlocfilehash: e599948a78baa96849e9ddaedf6eb2a4a131ebf4
ms.sourcegitcommit: 8c2093f7a048a9a56b36e4a3b4c48ae1206c52f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2021
ms.locfileid: "53004176"
---
# <a name="meeting-policy-settings-for-audio--video"></a><span data-ttu-id="13af9-103">音频和视频的会议&设置</span><span class="sxs-lookup"><span data-stu-id="13af9-103">Meeting policy settings for audio & video</span></span>

<span data-ttu-id="13af9-104"><a name="bkaudioandvideo"> </a>
<a name="ndi"> </a></span><span class="sxs-lookup"><span data-stu-id="13af9-104"><a name="bkaudioandvideo"> </a>
<a name="ndi"> </a></span></span>

<span data-ttu-id="13af9-105">本文介绍特定于音频和视频的会议策略设置。</span><span class="sxs-lookup"><span data-stu-id="13af9-105">This article describes the meeting policy settings specific to audio and video.</span></span> <span data-ttu-id="13af9-106">其中包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="13af9-106">These include the following:</span></span>

- [<span data-ttu-id="13af9-107">允许转录</span><span class="sxs-lookup"><span data-stu-id="13af9-107">Allow transcription</span></span>](#allow-transcription)
- [<span data-ttu-id="13af9-108">允许云录制</span><span class="sxs-lookup"><span data-stu-id="13af9-108">Allow cloud recording</span></span>](#allow-cloud-recording)
- [<span data-ttu-id="13af9-109">IP 音频模式</span><span class="sxs-lookup"><span data-stu-id="13af9-109">Mode for IP audio</span></span>](#mode-for-ip-audio)
- [<span data-ttu-id="13af9-110">IP 视频模式</span><span class="sxs-lookup"><span data-stu-id="13af9-110">Mode for IP video</span></span>](#mode-for-ip-video)
- [<span data-ttu-id="13af9-111">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="13af9-111">Allow IP video</span></span>](#allow-ip-video)
- [<span data-ttu-id="13af9-112">媒体位率 (Kbs)</span><span class="sxs-lookup"><span data-stu-id="13af9-112">Media bit rate (Kbs)</span></span>](#media-bit-rate-kbs)
- [<span data-ttu-id="13af9-113">视频筛选器模式</span><span class="sxs-lookup"><span data-stu-id="13af9-113">Video filters mode</span></span>](#video-filters-mode)
- [<span data-ttu-id="13af9-114">允许自定义背景设置</span><span class="sxs-lookup"><span data-stu-id="13af9-114">Allow custom background settings</span></span>](#allow-custom-background-settings)

### <a name="allow-transcription"></a><span data-ttu-id="13af9-115">允许转录</span><span class="sxs-lookup"><span data-stu-id="13af9-115">Allow transcription</span></span>

<span data-ttu-id="13af9-116">这是按组织者和按用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="13af9-116">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="13af9-117">此设置控制播放会议录制内容期间是否提供字幕和转录功能。</span><span class="sxs-lookup"><span data-stu-id="13af9-117">This setting controls whether captions and transcription features are available during playback of meeting recordings.</span></span> <span data-ttu-id="13af9-118">如果将其关闭，则在播放会议录制内容期间“**搜索**”和“**CC**”选项将不可用。</span><span class="sxs-lookup"><span data-stu-id="13af9-118">If you turn this off, the **Search** and **CC** options won't be available during playback of a meeting recording.</span></span> <span data-ttu-id="13af9-119">启动录制的人员需要打开此设置，以便录制内容也包含脚本。</span><span class="sxs-lookup"><span data-stu-id="13af9-119">The person who started the recording needs this setting turned on so that the recording also includes transcription.</span></span>

<span data-ttu-id="13af9-120">请注意，录制的会议的听录目前仅支持将语言设置为英语Teams在会议中使用英语的用户。</span><span class="sxs-lookup"><span data-stu-id="13af9-120">Note that transcription for recorded meetings is currently only supported for users who have the language in Teams set to English and when English is spoken in the meeting.</span></span>

### <a name="allow-cloud-recording"></a><span data-ttu-id="13af9-121">允许云录制</span><span class="sxs-lookup"><span data-stu-id="13af9-121">Allow cloud recording</span></span>

<span data-ttu-id="13af9-122">这是按组织者和按用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="13af9-122">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="13af9-123">此设置控制是否可以录制此用户的会议。</span><span class="sxs-lookup"><span data-stu-id="13af9-123">This setting controls whether this user's meetings can be recorded.</span></span> <span data-ttu-id="13af9-124">如果为参与者打开策略设置，并且他们是同一组织的经过身份验证的用户，则会议组织者或其他会议参与者可以启动录制。</span><span class="sxs-lookup"><span data-stu-id="13af9-124">The recording can be started by the meeting organizer or by another meeting participant if the policy setting is turned on for the participant and if they're an authenticated user from the same organization.</span></span>

<span data-ttu-id="13af9-125">组织之外的人员，如联合和匿名用户，无法启动录制。</span><span class="sxs-lookup"><span data-stu-id="13af9-125">People outside your organization, such as federated and anonymous users, can't start the recording.</span></span> <span data-ttu-id="13af9-126">来宾用户无法启动或停止录制。</span><span class="sxs-lookup"><span data-stu-id="13af9-126">Guest users can't start or stop the recording.</span></span>

![显示录制选项的屏幕截图](media/meeting-policies-recording.png)

<span data-ttu-id="13af9-128">查看以下示例。</span><span class="sxs-lookup"><span data-stu-id="13af9-128">Let's look at the following example.</span></span>

|<span data-ttu-id="13af9-129">用户</span><span class="sxs-lookup"><span data-stu-id="13af9-129">User</span></span> |<span data-ttu-id="13af9-130">会议策略</span><span class="sxs-lookup"><span data-stu-id="13af9-130">Meeting policy</span></span>  |<span data-ttu-id="13af9-131">允许云录制</span><span class="sxs-lookup"><span data-stu-id="13af9-131">Allow cloud recording</span></span> |
|---------|---------|---------|
|<span data-ttu-id="13af9-132">Daniela</span><span class="sxs-lookup"><span data-stu-id="13af9-132">Daniela</span></span> | <span data-ttu-id="13af9-133">全局</span><span class="sxs-lookup"><span data-stu-id="13af9-133">Global</span></span>   | <span data-ttu-id="13af9-134">关闭</span><span class="sxs-lookup"><span data-stu-id="13af9-134">Off</span></span> |
|<span data-ttu-id="13af9-135">Amanda</span><span class="sxs-lookup"><span data-stu-id="13af9-135">Amanda</span></span> | <span data-ttu-id="13af9-136">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="13af9-136">Location1MeetingPolicy</span></span> | <span data-ttu-id="13af9-137">开</span><span class="sxs-lookup"><span data-stu-id="13af9-137">On</span></span>|
|<span data-ttu-id="13af9-138">John (外部用户)</span><span class="sxs-lookup"><span data-stu-id="13af9-138">John (external user)</span></span> | <span data-ttu-id="13af9-139">不适用</span><span class="sxs-lookup"><span data-stu-id="13af9-139">Not applicable</span></span> | <span data-ttu-id="13af9-140">不适用</span><span class="sxs-lookup"><span data-stu-id="13af9-140">Not applicable</span></span>|

<span data-ttu-id="13af9-141">无法录制由 Daniela 组织的会议，已启用策略设置的 Amanda 无法录制 Daniela 组织的会议。</span><span class="sxs-lookup"><span data-stu-id="13af9-141">Meetings organized by Daniela can't be recorded and Amanda, who has the policy setting enabled, can't record meetings organized by Daniela.</span></span> <span data-ttu-id="13af9-142">可以录制由 Amanda 组织的会议，但禁用了策略设置的 Daniela 和外部用户的 John 无法录制 Amanda 组织的会议。</span><span class="sxs-lookup"><span data-stu-id="13af9-142">Meetings organized by Amanda can be recorded, however,  Daniela, who has the policy setting disabled and John who is an external user, can't record meetings organized by Amanda.</span></span>

<span data-ttu-id="13af9-143">若要了解有关云会议记录的更多信息，请参阅 [Teams 云会议录制](cloud-recording.md)。</span><span class="sxs-lookup"><span data-stu-id="13af9-143">To learn more about cloud meeting recording, see [Teams cloud meeting recording](cloud-recording.md).</span></span>

### <a name="mode-for-ip-audio"></a><span data-ttu-id="13af9-144">IP 音频模式</span><span class="sxs-lookup"><span data-stu-id="13af9-144">Mode for IP audio</span></span>

<span data-ttu-id="13af9-145">这是按用户策略。</span><span class="sxs-lookup"><span data-stu-id="13af9-145">This is a per-user policy.</span></span> <span data-ttu-id="13af9-146">此设置控制是否可以在会议和群组通话中打开音频。</span><span class="sxs-lookup"><span data-stu-id="13af9-146">This setting controls whether audio can be turned on in meetings and group calls.</span></span> <span data-ttu-id="13af9-147">下面是此设置的值。</span><span class="sxs-lookup"><span data-stu-id="13af9-147">Here are the values for this setting.</span></span>

|<span data-ttu-id="13af9-148">设置值</span><span class="sxs-lookup"><span data-stu-id="13af9-148">Setting value</span></span> |<span data-ttu-id="13af9-149">行为</span><span class="sxs-lookup"><span data-stu-id="13af9-149">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="13af9-150">**已启用传出和传入音频**</span><span class="sxs-lookup"><span data-stu-id="13af9-150">**Outgoing and incoming audio enabled**</span></span>    |<span data-ttu-id="13af9-p107">会议允许传出和传入音频。这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="13af9-p107">Outgoing and incoming audio is allowed in the meeting. This is the default setting.</span></span> |
|<span data-ttu-id="13af9-153">**禁用**</span><span class="sxs-lookup"><span data-stu-id="13af9-153">**Disabled**</span></span>     |<span data-ttu-id="13af9-154">传出和传入音频在会议中已关闭。</span><span class="sxs-lookup"><span data-stu-id="13af9-154">Outgoing and incoming audio is turned off in the meeting.</span></span>     |

<span data-ttu-id="13af9-155">如果用户设置为 **"已** 禁用"，该用户仍可以安排和组织会议，但他们不能使用音频。</span><span class="sxs-lookup"><span data-stu-id="13af9-155">If set to **Disabled** for a user, that user can still schedule and organize meetings but they can't use audio.</span></span> <span data-ttu-id="13af9-156">若要加入会议，他们必须通过 PSTN 公用电话交换网 (电话) 或通过电话拨入会议呼叫并加入。</span><span class="sxs-lookup"><span data-stu-id="13af9-156">To join a meeting, they have to dial in through the Public Switched Telephone Network (PSTN) or have the meeting call and join them by phone.</span></span> <span data-ttu-id="13af9-157">没有指定任何策略的会议参与者 (例如，匿名参与者) 将此设置为默认 **启用传出和传入音频**。</span><span class="sxs-lookup"><span data-stu-id="13af9-157">Meeting participants who don't have any policies assigned (for example, anonymous participants) have this set to **Outgoing and incoming audio enabled** by default.</span></span> <span data-ttu-id="13af9-158">在 Teams 移动客户端上，如果禁用此设置，用户必须通过 PSTN 拨入会议。</span><span class="sxs-lookup"><span data-stu-id="13af9-158">On Teams mobile clients, if this setting is disabled, the user has to dial in to the meeting through the PSTN.</span></span>

<span data-ttu-id="13af9-159">此设置不适用于 1:1 呼叫。</span><span class="sxs-lookup"><span data-stu-id="13af9-159">This setting doesn't apply to 1:1 calls.</span></span> <span data-ttu-id="13af9-160">若要限制 1:1 通话，请配置 Teams [通话策略](teams-calling-policy.md) 并关闭 **“进行私人通话”** 设置。</span><span class="sxs-lookup"><span data-stu-id="13af9-160">To restrict 1:1 calls, configure a Teams [calling policy](teams-calling-policy.md) and turn off the **Make private calls** setting.</span></span> <span data-ttu-id="13af9-161">此设置也不适用于 Surface Hub 和 Microsoft Teams 会议室设备等会议室设备。</span><span class="sxs-lookup"><span data-stu-id="13af9-161">This setting also doesn't apply to conference room devices such as Surface Hub and Microsoft Teams Rooms devices.</span></span>

<span data-ttu-id="13af9-162">此设置尚未适用于 Microsoft 365 政府社区云 (GCC)、GCC High 或国防部 (DoD) 环境。</span><span class="sxs-lookup"><span data-stu-id="13af9-162">This setting isn't yet available for Microsoft 365 Government Community Cloud (GCC), GCC High, or Department of Defense (DoD) environments.</span></span>

<span data-ttu-id="13af9-163">有关详细信息，请参阅 [会议参与者管理音频/视频](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="13af9-163">To learn more, see [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

### <a name="mode-for-ip-video"></a><span data-ttu-id="13af9-164">IP 视频模式</span><span class="sxs-lookup"><span data-stu-id="13af9-164">Mode for IP video</span></span>

<span data-ttu-id="13af9-165">这是按用户策略。</span><span class="sxs-lookup"><span data-stu-id="13af9-165">This is a per-user policy.</span></span> <span data-ttu-id="13af9-166">此设置控制是否可以在会议和群组通话中打开视频。</span><span class="sxs-lookup"><span data-stu-id="13af9-166">This setting controls whether video can be turned on in meetings and group calls.</span></span> <span data-ttu-id="13af9-167">下面是此设置的值。</span><span class="sxs-lookup"><span data-stu-id="13af9-167">Here are the values for this setting.</span></span>

|<span data-ttu-id="13af9-168">设置值</span><span class="sxs-lookup"><span data-stu-id="13af9-168">Setting value</span></span> |<span data-ttu-id="13af9-169">行为</span><span class="sxs-lookup"><span data-stu-id="13af9-169">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="13af9-170">**已启用传出和传入视频**</span><span class="sxs-lookup"><span data-stu-id="13af9-170">**Outgoing and incoming video enabled**</span></span>    | <span data-ttu-id="13af9-171">会议允许传出和传入视频。</span><span class="sxs-lookup"><span data-stu-id="13af9-171">Outgoing and incoming video is allowed in the meeting.</span></span> <span data-ttu-id="13af9-172">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="13af9-172">This is the default setting.</span></span> |
|<span data-ttu-id="13af9-173">**禁用**</span><span class="sxs-lookup"><span data-stu-id="13af9-173">**Disabled**</span></span>     | <span data-ttu-id="13af9-174">传出和传入视频在会议中已关闭。</span><span class="sxs-lookup"><span data-stu-id="13af9-174">Outgoing and incoming video is turned off in the meeting.</span></span> <span data-ttu-id="13af9-175">在 Teams 移动客户端上，用户无法在会议中分享视频或照片。</span><span class="sxs-lookup"><span data-stu-id="13af9-175">On Teams mobile clients, users can't share videos or photos in the meeting.</span></span> <br><br><span data-ttu-id="13af9-176">请注意，如果 **禁用"IP** 音频模式"，则 **"IP** 视频模式"也将保持禁用状态。</span><span class="sxs-lookup"><span data-stu-id="13af9-176">Note that if **Mode for IP audio** is disabled, then **Mode for IP video** will also remain disabled.</span></span>  |

<span data-ttu-id="13af9-177">如果为用户设置为 **禁用**，则该用户无法打开视频或查看其他会议参与者共享的视频。</span><span class="sxs-lookup"><span data-stu-id="13af9-177">If set to **Disabled** for a  user, that user can't turn on video or view videos shared by other meeting participants.</span></span> <span data-ttu-id="13af9-178">没有指定任何策略的会议参与者 (例如，匿名参与者) 将此设置为默认 **启用传出和传入视频**。</span><span class="sxs-lookup"><span data-stu-id="13af9-178">Meeting participants who don't have any policies assigned (for example, anonymous participants) have this set to **Outgoing and incoming video enabled** by default.</span></span>

<span data-ttu-id="13af9-179">此设置不适用于 Surface Hub 和 Microsoft Teams 会议室设备等会议室设备。</span><span class="sxs-lookup"><span data-stu-id="13af9-179">This setting doesn't apply to conference room devices such as Surface Hub and Microsoft Teams Rooms devices.</span></span>

<span data-ttu-id="13af9-180">此设置尚未适用于 Microsoft 365 政府社区云 (GCC)、GCC High 或国防部 (DoD) 环境。</span><span class="sxs-lookup"><span data-stu-id="13af9-180">This setting isn't yet available for Microsoft 365 Government Community Cloud (GCC), GCC High, or Department of Defense (DoD) environments.</span></span>

> [!NOTE]
> <span data-ttu-id="13af9-181">请记住，该设置同时控制传出和传入的视频，而 **允许 IP 视频** 设置则控制传出视频。</span><span class="sxs-lookup"><span data-stu-id="13af9-181">Keep in mind that this setting controls both outgoing and incoming video whereas the **Allow IP video** setting controls outgoing video.</span></span> <span data-ttu-id="13af9-182">若要了解更多信息，请参阅[哪些 IP 视频策略设置优先?](#which-ip-video-policy-setting-takes-precedence) 和 [管理会议参与者的音频/视频 ](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="13af9-182">To learn more, see [Which IP video policy setting takes precedence?](#which-ip-video-policy-setting-takes-precedence) and [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

<span data-ttu-id="13af9-183">有关详细信息，请参阅 [会议参与者管理音频/视频](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="13af9-183">To learn more, see [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

### <a name="allow-ip-video"></a><span data-ttu-id="13af9-184">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="13af9-184">Allow IP video</span></span>

<span data-ttu-id="13af9-185">这是按组织者和按用户策略的组合。</span><span class="sxs-lookup"><span data-stu-id="13af9-185">This is a combination of a per-organizer and per-user policy.</span></span> <span data-ttu-id="13af9-186">视频是会议的重要组成部分。</span><span class="sxs-lookup"><span data-stu-id="13af9-186">Video is a key component to meetings.</span></span> <span data-ttu-id="13af9-187">在一些组织中，管理员可能希望对有视频的用户会议进行更多的控制。</span><span class="sxs-lookup"><span data-stu-id="13af9-187">In some organizations, admins might want more control over which users' meetings have video.</span></span> <span data-ttu-id="13af9-188">此设置控制是否可以在用户主持的会议和用户启动的 1:1 和群组通话中打开视频。</span><span class="sxs-lookup"><span data-stu-id="13af9-188">This setting controls whether video can be turned on in meetings hosted by a user and in 1:1 and group calls started by a user.</span></span> <span data-ttu-id="13af9-189">在Teams客户端上，此设置控制用户是否可以在会议中共享照片和视频。</span><span class="sxs-lookup"><span data-stu-id="13af9-189">On Teams mobile clients, this setting controls whether users can share photos and videos in a meeting.</span></span>

<span data-ttu-id="13af9-190">由启用了此策略设置的用户组织的会议，如果与会者也启用了此策略设置，则允许与会者在会议中进行视频共享。</span><span class="sxs-lookup"><span data-stu-id="13af9-190">Meetings organized by a user who has this policy setting enabled, allow video sharing in the meeting by the meeting participants, if the participants also have the policy setting enabled.</span></span> <span data-ttu-id="13af9-191">没有指定任何策略的会议参与者 (例如，匿名和联合参与者) 继承会议组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="13af9-191">Meeting participants who don't have any policies assigned (for example, anonymous and federated participants) inherit the policy of the meeting organizer.</span></span>

> [!NOTE]
> <span data-ttu-id="13af9-192">请记住，此设置控制传出视频，而 **IP 视频的模式** 设置则控制传出和传入视频。</span><span class="sxs-lookup"><span data-stu-id="13af9-192">Keep in mind that this setting controls outgoing video whereas the **Mode for IP video** setting controls both outgoing and incoming video.</span></span> <span data-ttu-id="13af9-193">若要了解更多信息，请参阅[哪些 IP 视频策略设置优先?](#which-ip-video-policy-setting-takes-precedence) 和 [管理会议参与者的音频/视频 ](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="13af9-193">To learn more, see [Which IP video policy setting takes precedence?](#which-ip-video-policy-setting-takes-precedence) and [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

| <span data-ttu-id="13af9-194">Teams 桌面和 Web 客户端</span><span class="sxs-lookup"><span data-stu-id="13af9-194">Teams desktop and web client</span></span> |<span data-ttu-id="13af9-195">Teams 移动客户端</span><span class="sxs-lookup"><span data-stu-id="13af9-195">Teams mobile client</span></span>  |
|:-------:|:-------:|
|![截图截图显示在桌面上通过音频/视频设置加入会议的画面](media/meeting-policies-audio-video-settings.png)    |![屏幕截图显示在移动设备上通过音频/视频设置加入会议的画面](media/meeting-policies-mobile-join.png)          |

<span data-ttu-id="13af9-198">查看以下示例。</span><span class="sxs-lookup"><span data-stu-id="13af9-198">Let's look at the following example.</span></span>

|<span data-ttu-id="13af9-199">用户</span><span class="sxs-lookup"><span data-stu-id="13af9-199">User</span></span> |<span data-ttu-id="13af9-200">会议策略</span><span class="sxs-lookup"><span data-stu-id="13af9-200">Meeting policy</span></span>  |<span data-ttu-id="13af9-201">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="13af9-201">Allow IP video</span></span> |
|---------|---------|---------|
|<span data-ttu-id="13af9-202">Daniela</span><span class="sxs-lookup"><span data-stu-id="13af9-202">Daniela</span></span>   | <span data-ttu-id="13af9-203">全局</span><span class="sxs-lookup"><span data-stu-id="13af9-203">Global</span></span>   | <span data-ttu-id="13af9-204">开</span><span class="sxs-lookup"><span data-stu-id="13af9-204">On</span></span>       |
|<span data-ttu-id="13af9-205">Amanda</span><span class="sxs-lookup"><span data-stu-id="13af9-205">Amanda</span></span>    | <span data-ttu-id="13af9-206">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="13af9-206">Location1MeetingPolicy</span></span>        | <span data-ttu-id="13af9-207">关闭</span><span class="sxs-lookup"><span data-stu-id="13af9-207">Off</span></span>      |

<span data-ttu-id="13af9-208">由 Daniela 主持的会议允许开启视频。</span><span class="sxs-lookup"><span data-stu-id="13af9-208">Meetings hosted by Daniela allow video to be turned on.</span></span> <span data-ttu-id="13af9-209">Daniela 可以加入会议并打开视频。</span><span class="sxs-lookup"><span data-stu-id="13af9-209">Daniela can join the meeting and turn on video.</span></span> <span data-ttu-id="13af9-210">Amanda 无法打开 Daniela 会议中的视频，因为 Amanda 的策略设置为不允许视频。</span><span class="sxs-lookup"><span data-stu-id="13af9-210">Amanda can't turn on video in Daniela's meeting because Amanda's policy is set to not allow video.</span></span> <span data-ttu-id="13af9-211">Amanda 可以看到其他与会者在会议上分享的视频。</span><span class="sxs-lookup"><span data-stu-id="13af9-211">Amanda can see videos shared by other participants in the meeting.</span></span>

<span data-ttu-id="13af9-212">在 Amanda 主持的会议中，无论分配给他们的视频策略如何，任何人都无法打开视频。</span><span class="sxs-lookup"><span data-stu-id="13af9-212">In meetings hosted by Amanda, no one can turn on video, regardless of the video policy assigned to them.</span></span> <span data-ttu-id="13af9-213">这意味着 Daniela 不能在 Amanda 的会议上开视频。</span><span class="sxs-lookup"><span data-stu-id="13af9-213">This means Daniela can't turn on video in Amanda's meetings.</span></span>  

<span data-ttu-id="13af9-214">如果 Daniela 给 Amanda 打电话时开着视频，Amanda 可以只用音频接听电话。</span><span class="sxs-lookup"><span data-stu-id="13af9-214">If Daniela calls Amanda with video on, Amanda can answer the call with audio only.</span></span>  <span data-ttu-id="13af9-215">电话接通后，Amanda 可以看到 Daniela 的视频，但无法打开视频。</span><span class="sxs-lookup"><span data-stu-id="13af9-215">When the call is connected, Amanda can see Daniela's video, but can't turn on video.</span></span> <span data-ttu-id="13af9-216">如果 Amanda 给 Daniela 打电话，Daniela 可以用视频和音频接听电话。</span><span class="sxs-lookup"><span data-stu-id="13af9-216">If Amanda calls Daniela, Daniela can answer the call with video and audio.</span></span> <span data-ttu-id="13af9-217">通话接通后，Daniela 可以根据需要打开或关闭其视频。</span><span class="sxs-lookup"><span data-stu-id="13af9-217">When the call is connected, Daniela can turn on or turn off her video, as needed.</span></span>

<span data-ttu-id="13af9-218">有关详细信息，请参阅 [会议参与者管理音频/视频](#manage-audiovideo-for-meeting-participants)。</span><span class="sxs-lookup"><span data-stu-id="13af9-218">To learn more, see [Manage audio/video for meeting participants](#manage-audiovideo-for-meeting-participants).</span></span>

#### <a name="which-ip-video-policy-setting-takes-precedence"></a><span data-ttu-id="13af9-219">哪个 IP 视频策略设置优先？</span><span class="sxs-lookup"><span data-stu-id="13af9-219">Which IP video policy setting takes precedence?</span></span>

<span data-ttu-id="13af9-p121">对于用户，视频的最多限制策略设置优先。此处为一些示例。</span><span class="sxs-lookup"><span data-stu-id="13af9-p121">For a user, the most restrictive policy setting for video takes precedence. Here's some examples.</span></span>

|<span data-ttu-id="13af9-222">允许 IP 视频</span><span class="sxs-lookup"><span data-stu-id="13af9-222">Allow IP video</span></span>|<span data-ttu-id="13af9-223">IP 视频模式</span><span class="sxs-lookup"><span data-stu-id="13af9-223">Mode for IP video</span></span>|<span data-ttu-id="13af9-224">会议体验</span><span class="sxs-lookup"><span data-stu-id="13af9-224">Meeting experience</span></span>|
|---------|---------|---------|
|<span data-ttu-id="13af9-225">组织者: **打开**</span><span class="sxs-lookup"><span data-stu-id="13af9-225">Organizer: **On**</span></span><br><br><span data-ttu-id="13af9-226">参与者: **打开**</span><span class="sxs-lookup"><span data-stu-id="13af9-226">Participant: **On**</span></span> |<span data-ttu-id="13af9-227">参与者: **禁用**</span><span class="sxs-lookup"><span data-stu-id="13af9-227">Participant: **Disabled**</span></span>        |<span data-ttu-id="13af9-228">**IP 视频模式** 设置优先。</span><span class="sxs-lookup"><span data-stu-id="13af9-228">The **Mode for IP video** setting takes precedence.</span></span> <span data-ttu-id="13af9-229">分配到此策略的参与者不能开启或查看他人分享的视频。</span><span class="sxs-lookup"><span data-stu-id="13af9-229">The participant who is assigned this policy can't turn on or view videos shared by others.</span></span>|
|<span data-ttu-id="13af9-230">组织者: **打开**</span><span class="sxs-lookup"><span data-stu-id="13af9-230">Organizer: **On**</span></span><br><br><span data-ttu-id="13af9-231">参与者: **打开**</span><span class="sxs-lookup"><span data-stu-id="13af9-231">Participant: **On**</span></span> |<span data-ttu-id="13af9-232">参与者: **启用传出和传入视频**</span><span class="sxs-lookup"><span data-stu-id="13af9-232">Participant: **Outgoing and incoming video enabled**</span></span>          |<span data-ttu-id="13af9-233">分配到该策略的参与者可以打开或查看他人分享的视频。</span><span class="sxs-lookup"><span data-stu-id="13af9-233">The participant who is assigned this policy can turn on or view videos shared by others.</span></span>         |
|<span data-ttu-id="13af9-234">组织者: **打开**</span><span class="sxs-lookup"><span data-stu-id="13af9-234">Organizer: **On**</span></span><br><br><span data-ttu-id="13af9-235">参与者: **关闭**</span><span class="sxs-lookup"><span data-stu-id="13af9-235">Participant: **Off**</span></span> |<span data-ttu-id="13af9-236">参与者: **启用传出和传入视频**</span><span class="sxs-lookup"><span data-stu-id="13af9-236">Participant: **Outgoing and incoming video enabled**</span></span>         |<span data-ttu-id="13af9-237">允许 **IP 视频** 设置优先。</span><span class="sxs-lookup"><span data-stu-id="13af9-237">The **Allow IP video** setting takes precedence.</span></span> <span data-ttu-id="13af9-238">参与者只能看到传入视频，无法发送传出视频。</span><span class="sxs-lookup"><span data-stu-id="13af9-238">Participants can only see incoming video and can't send outgoing video.</span></span>         |
|<span data-ttu-id="13af9-239">组织者: **打开**</span><span class="sxs-lookup"><span data-stu-id="13af9-239">Organizer: **On**</span></span><br><br><span data-ttu-id="13af9-240">参与者: **关闭**</span><span class="sxs-lookup"><span data-stu-id="13af9-240">Participant: **Off**</span></span> |<span data-ttu-id="13af9-241">参与者: **禁用**</span><span class="sxs-lookup"><span data-stu-id="13af9-241">Participant: **Disabled**</span></span>         |<span data-ttu-id="13af9-242">**IP 视频模式** 设置优先。</span><span class="sxs-lookup"><span data-stu-id="13af9-242">The **Mode for IP video** setting takes precedence.</span></span> <span data-ttu-id="13af9-243">参与者无法看到传入或传出的视频。</span><span class="sxs-lookup"><span data-stu-id="13af9-243">The participant can't see incoming or outgoing video.</span></span>|
|<span data-ttu-id="13af9-244">组织者: **关闭**</span><span class="sxs-lookup"><span data-stu-id="13af9-244">Organizer: **Off**</span></span>    |       |<span data-ttu-id="13af9-245">**允许 IP 视频** 设置优先，因为它已为组织者关闭。</span><span class="sxs-lookup"><span data-stu-id="13af9-245">The **Allow IP video** setting takes precedence because it's turned off for the organizer.</span></span> <span data-ttu-id="13af9-246">任何人都不能在分配此策略的用户组织会议中打开视频。</span><span class="sxs-lookup"><span data-stu-id="13af9-246">No one can turn on video in meetings organized by the user who is assigned this policy.</span></span>         |

### <a name="manage-audiovideo-for-meeting-participants"></a><span data-ttu-id="13af9-247">管理与会者的音频/视频</span><span class="sxs-lookup"><span data-stu-id="13af9-247">Manage audio/video for meeting participants</span></span>

|<span data-ttu-id="13af9-248">如果你想要...</span><span class="sxs-lookup"><span data-stu-id="13af9-248">If you want to...</span></span>  |<span data-ttu-id="13af9-249">设置以下策略设置</span><span class="sxs-lookup"><span data-stu-id="13af9-249">Set the following policy settings</span></span>  |
|---------|---------|
|<span data-ttu-id="13af9-250">禁用会议参与者的音频和视频</span><span class="sxs-lookup"><span data-stu-id="13af9-250">Disable audio and video for participants in meetings</span></span>  |<span data-ttu-id="13af9-251">IP 音频模式: **禁用**</span><span class="sxs-lookup"><span data-stu-id="13af9-251">Mode for IP audio: **Disabled**</span></span><br> <span data-ttu-id="13af9-252">IP 视频模式: **禁用**</span><span class="sxs-lookup"><span data-stu-id="13af9-252">Mode for IP video: **Disabled**</span></span><br><span data-ttu-id="13af9-253">允许 IP 视频: 不适用</span><span class="sxs-lookup"><span data-stu-id="13af9-253">Allow IP video: N/A</span></span>       |
|<span data-ttu-id="13af9-254">只为会议参与者启用传入的视频和音频</span><span class="sxs-lookup"><span data-stu-id="13af9-254">Enable only incoming video and audio for participants in meetings</span></span>  |<span data-ttu-id="13af9-255">IP 音频模式: **启用传出和传入音频**</span><span class="sxs-lookup"><span data-stu-id="13af9-255">Mode for IP audio: **Outgoing and incoming audio enabled**</span></span><br> <span data-ttu-id="13af9-256">IP 视频模式: **启用传出和传入视频**</span><span class="sxs-lookup"><span data-stu-id="13af9-256">Mode for IP video: **Outgoing and incoming video enabled**</span></span><br><span data-ttu-id="13af9-257">允许 IP 视频: **关闭**</span><span class="sxs-lookup"><span data-stu-id="13af9-257">Allow IP video: **Off**</span></span>       |
|<span data-ttu-id="13af9-258">禁用会议参与者的视频 (参与者仅有音频)</span><span class="sxs-lookup"><span data-stu-id="13af9-258">Disable video for participants in meetings (participants have audio only)</span></span>|  <span data-ttu-id="13af9-259">IP 音频模式: **启用传出和传入音频**</span><span class="sxs-lookup"><span data-stu-id="13af9-259">Mode for IP audio: **Enable outgoing and incoming audio**</span></span><br> <span data-ttu-id="13af9-260">IP 视频模式: **禁用**</span><span class="sxs-lookup"><span data-stu-id="13af9-260">Mode for IP video: **Disabled**</span></span><br><span data-ttu-id="13af9-261">允许 IP 视频: 不适用</span><span class="sxs-lookup"><span data-stu-id="13af9-261">Allow IP video: N/A</span></span>
|<span data-ttu-id="13af9-262">为会议参与者启用音频和视频</span><span class="sxs-lookup"><span data-stu-id="13af9-262">Enable audio and video for participants in meetings</span></span>    |<span data-ttu-id="13af9-263">IP 音频模式: **启用的传出和传入** (默认)</span><span class="sxs-lookup"><span data-stu-id="13af9-263">Mode for IP audio: **Outgoing and incoming audio enabled** (default)</span></span><br> <span data-ttu-id="13af9-264">IP 视频模式: **启用传出和传入视频** (默认)</span><span class="sxs-lookup"><span data-stu-id="13af9-264">Mode for IP video: **Outgoing and incoming video enabled** (default)</span></span><br><span data-ttu-id="13af9-265">允许 IP 视频: **打开** (默认)</span><span class="sxs-lookup"><span data-stu-id="13af9-265">Allow IP video: **On** (default)</span></span>    |

<span data-ttu-id="13af9-266">适用会议组织者政策和用户政策之间最严格的政策。</span><span class="sxs-lookup"><span data-stu-id="13af9-266">The most restrictive policy between the meeting organizer’s policy and the user’s policy applies.</span></span> <span data-ttu-id="13af9-267">例如，如果组织者有限制视频的策略，而用户的策略不限制视频，那么会议参与者就会继承会议组织者的策略，在会议中无法访问视频。</span><span class="sxs-lookup"><span data-stu-id="13af9-267">For example, if an organizer has a policy that restricts video and a user’s policy doesn't restrict video, meeting participants inherit the policy of the meeting organizer and don't have access to video in meetings.</span></span> <span data-ttu-id="13af9-268">这意味着他们只能使用音频加入会议。</span><span class="sxs-lookup"><span data-stu-id="13af9-268">This means that they can join the meeting with audio only.</span></span>

> [!NOTE]
> <span data-ttu-id="13af9-269">当用户通过电话启动群组呼叫加入时，不会出现 **使用电话进行音频** 的画面。</span><span class="sxs-lookup"><span data-stu-id="13af9-269">When a user starts a group call to join by phone, the **Use phone for audio** screen doesn't appear.</span></span> <span data-ttu-id="13af9-270">这是一个已知的问题，我们正在努力解决。</span><span class="sxs-lookup"><span data-stu-id="13af9-270">This is a known issue that we're working to resolve.</span></span> <span data-ttu-id="13af9-271">若要解决这个问题，选择 **其他加入选项** 下的 **电话音频**。</span><span class="sxs-lookup"><span data-stu-id="13af9-271">To work around this issue, select **Phone audio** under **Other join options**.</span></span>  

#### <a name="teams-mobile-clients"></a><span data-ttu-id="13af9-272">Teams 移动设备客户端</span><span class="sxs-lookup"><span data-stu-id="13af9-272">Teams mobile clients</span></span>

<span data-ttu-id="13af9-273">对于Teams客户端上的用户，会议期间共享照片和视频的能力也取决于"允许 **IP** 视频"或 **"IP 视频模式"** 设置。</span><span class="sxs-lookup"><span data-stu-id="13af9-273">For users on Teams mobile clients, the ability to share photos and videos during a meeting is also determined by the **Allow IP video** or **IP video mode** setting.</span></span> <span data-ttu-id="13af9-274">根据策略设置优先，将无法使用分享视频和照片的功能。</span><span class="sxs-lookup"><span data-stu-id="13af9-274">Depending on which policy setting takes precedence, the ability to share videos and photos won't be available.</span></span> <span data-ttu-id="13af9-275">这不会影响屏幕共享，可以使用单独的 [屏幕共享模式](meeting-policies-content-sharing.md#screen-sharing-mode) 设置进行配置。</span><span class="sxs-lookup"><span data-stu-id="13af9-275">This doesn't affect screen sharing, which you configure using a separate [Screen sharing mode](meeting-policies-content-sharing.md#screen-sharing-mode) setting.</span></span> <span data-ttu-id="13af9-276">此外，还可以设置 [Teams 移动性策略](/powershell/module/skype/new-csteamsmobilitypolicy)，防止移动用户通过蜂窝连接使用 IP 视频，这意味着他们必须使用 WiFi 连接。</span><span class="sxs-lookup"><span data-stu-id="13af9-276">Additionally, you can set a [Teams mobility policy](/powershell/module/skype/new-csteamsmobilitypolicy) to prevent mobile users from using IP video over a cellular connection, which means they must use a WiFi connection.</span></span>

### <a name="media-bit-rate-kbs"></a><span data-ttu-id="13af9-277">媒体位率 (Kbs)</span><span class="sxs-lookup"><span data-stu-id="13af9-277">Media bit rate (Kbs)</span></span>

<span data-ttu-id="13af9-278">这是按用户策略。</span><span class="sxs-lookup"><span data-stu-id="13af9-278">This is a per-user policy.</span></span> <span data-ttu-id="13af9-279">此设置确定用户通话和会议中基于音频、视频和视频的应用共享传输的媒体比特率。</span><span class="sxs-lookup"><span data-stu-id="13af9-279">This setting determines the media bit rate for audio, video, and video-based app sharing transmissions in calls and meetings for the user.</span></span> <span data-ttu-id="13af9-280">它适用于通话或会议中用户的上行和下行媒体遍历。</span><span class="sxs-lookup"><span data-stu-id="13af9-280">It's applied to both the uplink and downlink media traversal for users in the call or meeting.</span></span> <span data-ttu-id="13af9-281">此设置可让你对组织中的带宽管理进行精细控制。</span><span class="sxs-lookup"><span data-stu-id="13af9-281">This setting gives you granular control over managing bandwidth in your organization.</span></span> <span data-ttu-id="13af9-282">根据用户所需的会议场景，我们建议准备足够的带宽，以保证优质的体验。</span><span class="sxs-lookup"><span data-stu-id="13af9-282">Depending on the meetings scenarios required by users, we recommend having enough bandwidth in place for a good quality experience.</span></span> <span data-ttu-id="13af9-283">最小值为 30Kbps，最大值取决于会议场景。</span><span class="sxs-lookup"><span data-stu-id="13af9-283">The minimum value is 30 Kbps and the maximum value depends on the meeting scenario.</span></span> <span data-ttu-id="13af9-284">若要了解有关在 Teams 中举行高质量会议、通话和实时活动的最低推荐带宽的更多信息，请参阅 [“带宽要求”](prepare-network.md#bandwidth-requirements)。</span><span class="sxs-lookup"><span data-stu-id="13af9-284">To learn more about the minimum recommended bandwidth for good quality meetings, calls, and live events in Teams, see [Bandwidth requirements](prepare-network.md#bandwidth-requirements).</span></span>

<span data-ttu-id="13af9-285">如果没有足够的带宽供会议使用，与会者会看到一条表明网络质量差的消息。</span><span class="sxs-lookup"><span data-stu-id="13af9-285">If there isn't enough bandwidth for a meeting, participants see a message that indicates poor network quality.</span></span>

<span data-ttu-id="13af9-286">对于需要最高质量视频体验的会议，如 CEO 董事会会议和 Teams 直播活动，我们建议将带宽设置为 10 Mbps。</span><span class="sxs-lookup"><span data-stu-id="13af9-286">For meetings that need the highest-quality video experience, such as CEO board meetings and Teams live events, we recommend you set the bandwidth to 10 Mbps.</span></span> <span data-ttu-id="13af9-287">即使设置了最大体验，当检测到某些网络状况时，Teams 媒体栈也会根据不同的场景，适应低带宽的条件。</span><span class="sxs-lookup"><span data-stu-id="13af9-287">Even when the maximum experience is set, the Teams media stack adapts to low-bandwidth conditions when certain network conditions are detected, depending on the scenario.</span></span>

## <a name="video-filters-mode"></a><span data-ttu-id="13af9-288">视频筛选器模式</span><span class="sxs-lookup"><span data-stu-id="13af9-288">Video filters mode</span></span>

<span data-ttu-id="13af9-289"><a name="bkvideofilters"> </a></span><span class="sxs-lookup"><span data-stu-id="13af9-289"><a name="bkvideofilters"> </a></span></span>

<span data-ttu-id="13af9-p131">这是每用户策略。此设置控制用户是否可以自定义他们在会议中的视频背景。</span><span class="sxs-lookup"><span data-stu-id="13af9-p131">This is a per-user policy. This setting controls whether users can customize their video background in a meeting.</span></span>

<span data-ttu-id="13af9-292">目前，只能使用 PowerShell 来设置该策略。</span><span class="sxs-lookup"><span data-stu-id="13af9-292">Currently, you can only use PowerShell to set this policy.</span></span> <span data-ttu-id="13af9-293">可以使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet 编辑现有的 Teams 会议策略。</span><span class="sxs-lookup"><span data-stu-id="13af9-293">You can edit an existing Teams meeting policy by using the [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) cmdlet.</span></span> <span data-ttu-id="13af9-294">或者，使用 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet 创建一个新的 Teams 会议策略，然后将该策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="13af9-294">Or, create a new Teams meeting policy by using the [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) cmdlet, and then assign the policy to users.</span></span>

<span data-ttu-id="13af9-295">要指定用户是否可以在会议中自定义视频背景，请按以下方式设置 **VideoFiltersMode** 参数:</span><span class="sxs-lookup"><span data-stu-id="13af9-295">To specify whether users can customize their video background in a meeting, set the **VideoFiltersMode** parameter as follows:</span></span>

|<span data-ttu-id="13af9-296">在 PowerShell 中设置值</span><span class="sxs-lookup"><span data-stu-id="13af9-296">Setting value in PowerShell</span></span> |<span data-ttu-id="13af9-297">行为</span><span class="sxs-lookup"><span data-stu-id="13af9-297">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="13af9-298">**NoFilters**</span><span class="sxs-lookup"><span data-stu-id="13af9-298">**NoFilters**</span></span>     |<span data-ttu-id="13af9-299">用户无法自定义其视频背景。</span><span class="sxs-lookup"><span data-stu-id="13af9-299">User can't customize their video background.</span></span>|
|<span data-ttu-id="13af9-300">**BlurOnly**</span><span class="sxs-lookup"><span data-stu-id="13af9-300">**BlurOnly**</span></span>     |<span data-ttu-id="13af9-301">用户可以选择模糊其视频背景。</span><span class="sxs-lookup"><span data-stu-id="13af9-301">User has the option to blur their video background.</span></span> |
|<span data-ttu-id="13af9-302">**BlurandDefaultBackgrounds**</span><span class="sxs-lookup"><span data-stu-id="13af9-302">**BlurandDefaultBackgrounds**</span></span>     |<span data-ttu-id="13af9-303">用户可以选择模糊显示视频背景或选择从默认的图像集作为他们的背景。</span><span class="sxs-lookup"><span data-stu-id="13af9-303">User has the option to blur their video background or choose from the default set of images to use as their background.</span></span> |
|<span data-ttu-id="13af9-304">**AllFilters**</span><span class="sxs-lookup"><span data-stu-id="13af9-304">**AllFilters**</span></span>     |<span data-ttu-id="13af9-305">使用 可以选择模糊其视频背景、从默认图像集选择或上传自定义图像以用作背景。</span><span class="sxs-lookup"><span data-stu-id="13af9-305">Use has the option to blur their video background, choose from the default set of images, or upload custom images to use as their background.</span></span> |

> [!NOTE]
> <span data-ttu-id="13af9-306">用户上传的图片不会经过 Teams 的筛选。</span><span class="sxs-lookup"><span data-stu-id="13af9-306">Images uploaded by users aren't screened by Teams.</span></span> <span data-ttu-id="13af9-307">当使用 **AllFilters** 设置时，应该制定内部组织政策，以防止用户上传攻击性或不适当的图像，或组织无权用于 Teams 会议背景的图像。</span><span class="sxs-lookup"><span data-stu-id="13af9-307">When you use the **AllFilters** setting, you should have internal organization policies to prevent users from uploading offensive or inappropriate images, or images your organization don't have rights to use for Teams meeting backgrounds.</span></span>

### <a name="allow-custom-background-settings"></a><span data-ttu-id="13af9-308">允许自定义背景设置</span><span class="sxs-lookup"><span data-stu-id="13af9-308">Allow custom background settings</span></span>

<span data-ttu-id="13af9-309">可以添加要用于每个租户的自定义背景图像。</span><span class="sxs-lookup"><span data-stu-id="13af9-309">You can add custom background images to be used per tenant.</span></span> <span data-ttu-id="13af9-310">此功能允许公司将企业品牌应用到Teams会议。</span><span class="sxs-lookup"><span data-stu-id="13af9-310">This feature allows companies to apply corporate branding to Teams meetings.</span></span>

1. <span data-ttu-id="13af9-311">登录到 Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="13af9-311">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="13af9-312">选择 **"会议策略**  >  **自定义会议图像"。**</span><span class="sxs-lookup"><span data-stu-id="13af9-312">Select **Meeting Policies** > **Customize meeting images**.</span></span>

   ![会议策略选择，突出显示"自定义会议图像"按钮](media/custom-background-image-button.png)

3. <span data-ttu-id="13af9-314">从 **"组织范围\*\*\*\*的背景图像"中选择"打开"。**</span><span class="sxs-lookup"><span data-stu-id="13af9-314">Select **On** from **Org wide background images**.</span></span>

4. <span data-ttu-id="13af9-315">选择 **"+ 添加图像"。**</span><span class="sxs-lookup"><span data-stu-id="13af9-315">Select **+ Add images**.</span></span>

5. <span data-ttu-id="13af9-316">在"管理背景"面板中，选择"**添加图像"。**</span><span class="sxs-lookup"><span data-stu-id="13af9-316">In the Managing backgrounds panel, select **Add image**.</span></span>

6. <span data-ttu-id="13af9-317">确保映像满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="13af9-317">Ensure that the images meet these requirements:</span></span>
  
   - <span data-ttu-id="13af9-318">最小大小 360 px</span><span class="sxs-lookup"><span data-stu-id="13af9-318">Minimum size 360 px</span></span>
   - <span data-ttu-id="13af9-319">最大大小 2048 px</span><span class="sxs-lookup"><span data-stu-id="13af9-319">Maximum size 2048 px</span></span>
   - <span data-ttu-id="13af9-320">PNG、JPG 或 BMP 的文件类型</span><span class="sxs-lookup"><span data-stu-id="13af9-320">File type of PNG, JPG, or BMP</span></span>
   - <span data-ttu-id="13af9-321">最多可以上传 50 个图像</span><span class="sxs-lookup"><span data-stu-id="13af9-321">Maximum 50 images can be uploaded</span></span>

7. <span data-ttu-id="13af9-322">预览已选择的图像，然后选择"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="13af9-322">Preview the images that you've selected, and then select **Close**.</span></span>

8. <span data-ttu-id="13af9-323">查看图像并根据需要添加更多图像。</span><span class="sxs-lookup"><span data-stu-id="13af9-323">Review the images and add more as needed.</span></span>

9. <span data-ttu-id="13af9-324">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="13af9-324">Select **Save**.</span></span>

<span data-ttu-id="13af9-325">与会者将看到他们参加会议时可以使用的一系列背景图像。</span><span class="sxs-lookup"><span data-stu-id="13af9-325">The meeting attendees will see a selection of background images that they can use when they attend a meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="13af9-326">更改最多可能需要 24 小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="13af9-326">It could take up to 24 hours for the changes to take effect.</span></span>

## <a name="related-topics"></a><span data-ttu-id="13af9-327">相关主题</span><span class="sxs-lookup"><span data-stu-id="13af9-327">Related topics</span></span>

- [<span data-ttu-id="13af9-328">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="13af9-328">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="13af9-329">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="13af9-329">Assign policies to your users in Teams</span></span>](assign-policies.md)
