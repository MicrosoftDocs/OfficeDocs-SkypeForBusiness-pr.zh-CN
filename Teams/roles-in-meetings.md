---
title: Teams 会议中的演示者和参与者功能
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解 Teams 会议中的演示者和参与者功能。
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: b0302a5c1f09e6ed6bfbb877709ed3562ce1440a
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938171"
---
<a name="presenter-and-participant-capabilities-in-a-teams-meeting"></a><span data-ttu-id="0a848-103">Teams 会议中的演示者和参与者功能</span><span class="sxs-lookup"><span data-stu-id="0a848-103">Presenter and participant capabilities in a Teams meeting</span></span>
======================================================

<span data-ttu-id="0a848-104">Microsoft Teams 会议支持多种参与者类型。</span><span class="sxs-lookup"><span data-stu-id="0a848-104">Microsoft Teams meetings support many participant types.</span></span> <span data-ttu-id="0a848-105">参与者可以根据自己在组织内部或外部的角色访问各种会议功能。</span><span class="sxs-lookup"><span data-stu-id="0a848-105">Participants can access various meeting features based on their roles inside or outside of an organization.</span></span>

<span data-ttu-id="0a848-106">可用的会议功能有：</span><span class="sxs-lookup"><span data-stu-id="0a848-106">The available meeting features are:</span></span>

- <span data-ttu-id="0a848-107">聊天（包括照片和贴纸）</span><span class="sxs-lookup"><span data-stu-id="0a848-107">Chat (includes photos and stickers)</span></span>
- <span data-ttu-id="0a848-108">会议记录</span><span class="sxs-lookup"><span data-stu-id="0a848-108">Meeting Notes</span></span>
- <span data-ttu-id="0a848-109">白板</span><span class="sxs-lookup"><span data-stu-id="0a848-109">Whiteboard</span></span>
- <span data-ttu-id="0a848-110">录制</span><span class="sxs-lookup"><span data-stu-id="0a848-110">Recording</span></span>
- <span data-ttu-id="0a848-111">文件</span><span class="sxs-lookup"><span data-stu-id="0a848-111">Files</span></span>
    - <span data-ttu-id="0a848-112">将文件共享到会议聊天和在会议聊天中查看/下载文件</span><span class="sxs-lookup"><span data-stu-id="0a848-112">sharing a file into a meeting chat and viewing/downloading a file from a meeting chat</span></span>
    - <span data-ttu-id="0a848-113">在会议中展示 PPT（不是通过屏幕共享功能）和在会议中查看 PPT</span><span class="sxs-lookup"><span data-stu-id="0a848-113">presenting a PPT in a meeting (not via screensharing) and viewing a PPT in a meeting</span></span>
- <span data-ttu-id="0a848-114">安排会议（仅适用于会议）</span><span class="sxs-lookup"><span data-stu-id="0a848-114">Schedule a meeting (for meetings only)</span></span>

<span data-ttu-id="0a848-115">本文介绍了这些参与者功能以及他们对会议功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="0a848-115">This article describes those participant capabilities and what access they have to meeting features.</span></span>

## <a name="presenters-and-organizers"></a><span data-ttu-id="0a848-116">演示者和组织者</span><span class="sxs-lookup"><span data-stu-id="0a848-116">Presenters and organizers</span></span>

<span data-ttu-id="0a848-117">演示者和组织者包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="0a848-117">Presenters and organizers include the following:</span></span>

- <span data-ttu-id="0a848-118">来自我的组织的演示者</span><span class="sxs-lookup"><span data-stu-id="0a848-118">Presenters from my organization</span></span>
- <span data-ttu-id="0a848-119">来自其他组织的演示者 - 包括匿名和外部参与者。</span><span class="sxs-lookup"><span data-stu-id="0a848-119">Presenters from other organizations - this includes anonymous and external participants.</span></span> <span data-ttu-id="0a848-120">演示者由组织者指定，且需要具有来自组织者的个人邀请。</span><span class="sxs-lookup"><span data-stu-id="0a848-120">Presenters are designated by the organizer and require a personal invite from the organizer.</span></span>

<span data-ttu-id="0a848-121">演示者和组织者可访问会议或直播活动中的所有功能。</span><span class="sxs-lookup"><span data-stu-id="0a848-121">Presenters and organizers have access to every feature in a meeting or live event.</span></span>

## <a name="participants"></a><span data-ttu-id="0a848-122">参与者</span><span class="sxs-lookup"><span data-stu-id="0a848-122">Participants</span></span>

<span data-ttu-id="0a848-123">有多种类型的会议参与者：</span><span class="sxs-lookup"><span data-stu-id="0a848-123">There are several types of meeting participants:</span></span>

- [<span data-ttu-id="0a848-124">租户内参与者</span><span class="sxs-lookup"><span data-stu-id="0a848-124">In-tenant participant</span></span>](#in-tenant-participant)
- [<span data-ttu-id="0a848-125">来宾参与者</span><span class="sxs-lookup"><span data-stu-id="0a848-125">Guest participant</span></span>](#guest-participant)
- [<span data-ttu-id="0a848-126">外部（联合）参与者</span><span class="sxs-lookup"><span data-stu-id="0a848-126">External (federated) participant</span></span>](#external-federated-participant)
- [<span data-ttu-id="0a848-127">匿名参与者</span><span class="sxs-lookup"><span data-stu-id="0a848-127">Anonymous participant</span></span>](#anonymous-participant)

### <a name="in-tenant-participant"></a><span data-ttu-id="0a848-128">租户内参与者</span><span class="sxs-lookup"><span data-stu-id="0a848-128">In-tenant participant</span></span>

<span data-ttu-id="0a848-129">租户内参与者为组织内部人员，并且具有租户凭据。</span><span class="sxs-lookup"><span data-stu-id="0a848-129">The in-tenant participant belongs to the organization and has credentials for the tenant.</span></span> <span data-ttu-id="0a848-130">有关此类参与者的详细信息，请参阅[安全性与 Microsoft Teams](teams-security-guide.md#participant-types)。</span><span class="sxs-lookup"><span data-stu-id="0a848-130">Learn more about this participant in [Security and Microsoft Teams](teams-security-guide.md#participant-types).</span></span>

|  |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| <span data-ttu-id="0a848-131">**功能**</span><span class="sxs-lookup"><span data-stu-id="0a848-131">**Feature**</span></span>        | <span data-ttu-id="0a848-132">会议前</span><span class="sxs-lookup"><span data-stu-id="0a848-132">Pre-meeting</span></span> | <span data-ttu-id="0a848-133">会议中</span><span class="sxs-lookup"><span data-stu-id="0a848-133">In-meeting</span></span> | <span data-ttu-id="0a848-134">会议后</span><span class="sxs-lookup"><span data-stu-id="0a848-134">Post-meeting</span></span> |
| <span data-ttu-id="0a848-135">聊天</span><span class="sxs-lookup"><span data-stu-id="0a848-135">Chat</span></span> | <span data-ttu-id="0a848-136">是</span><span class="sxs-lookup"><span data-stu-id="0a848-136">Yes</span></span> | <span data-ttu-id="0a848-137">是</span><span class="sxs-lookup"><span data-stu-id="0a848-137">Yes</span></span> | <span data-ttu-id="0a848-138">是</span><span class="sxs-lookup"><span data-stu-id="0a848-138">Yes</span></span> |
| <span data-ttu-id="0a848-139">会议记录</span><span class="sxs-lookup"><span data-stu-id="0a848-139">Meeting Notes</span></span> | <span data-ttu-id="0a848-140">是</span><span class="sxs-lookup"><span data-stu-id="0a848-140">Yes</span></span> | <span data-ttu-id="0a848-141">是</span><span class="sxs-lookup"><span data-stu-id="0a848-141">Yes</span></span> |<span data-ttu-id="0a848-142">是</span><span class="sxs-lookup"><span data-stu-id="0a848-142">Yes</span></span> |
| <span data-ttu-id="0a848-143">白板</span><span class="sxs-lookup"><span data-stu-id="0a848-143">Whiteboard</span></span> | <span data-ttu-id="0a848-144">是</span><span class="sxs-lookup"><span data-stu-id="0a848-144">Yes</span></span> | <span data-ttu-id="0a848-145">是</span><span class="sxs-lookup"><span data-stu-id="0a848-145">Yes</span></span> |<span data-ttu-id="0a848-146">是</span><span class="sxs-lookup"><span data-stu-id="0a848-146">Yes</span></span> |
| <span data-ttu-id="0a848-147">录制</span><span class="sxs-lookup"><span data-stu-id="0a848-147">Recording</span></span> | <span data-ttu-id="0a848-148">不适用</span><span class="sxs-lookup"><span data-stu-id="0a848-148">N/A</span></span> |<span data-ttu-id="0a848-149">是</span><span class="sxs-lookup"><span data-stu-id="0a848-149">Yes</span></span> | <span data-ttu-id="0a848-150">是</span><span class="sxs-lookup"><span data-stu-id="0a848-150">Yes</span></span> |
| <span data-ttu-id="0a848-151">文件 - 将文件共享到会议聊天和在会议聊天中查看/下载文件</span><span class="sxs-lookup"><span data-stu-id="0a848-151">Files - sharing a file into a meeting chat and viewing/downloading a file from a meeting chat</span></span> | <span data-ttu-id="0a848-152">是</span><span class="sxs-lookup"><span data-stu-id="0a848-152">Yes</span></span> | <span data-ttu-id="0a848-153">是</span><span class="sxs-lookup"><span data-stu-id="0a848-153">Yes</span></span> | <span data-ttu-id="0a848-154">是</span><span class="sxs-lookup"><span data-stu-id="0a848-154">Yes</span></span> |
| <span data-ttu-id="0a848-155">文件 - 在会议中展示 PPT（不是通过屏幕共享）和在会议中查看 PPT</span><span class="sxs-lookup"><span data-stu-id="0a848-155">Files - presenting a PPT in a meeting (not via screensharing) and viewing a PPT in a meeting</span></span> | <span data-ttu-id="0a848-156">是</span><span class="sxs-lookup"><span data-stu-id="0a848-156">Yes</span></span> | <span data-ttu-id="0a848-157">是</span><span class="sxs-lookup"><span data-stu-id="0a848-157">Yes</span></span> | <span data-ttu-id="0a848-158">是</span><span class="sxs-lookup"><span data-stu-id="0a848-158">Yes</span></span> |
| <span data-ttu-id="0a848-159">安排会议</span><span class="sxs-lookup"><span data-stu-id="0a848-159">Schedule a meeting</span></span> | <span data-ttu-id="0a848-160">是</span><span class="sxs-lookup"><span data-stu-id="0a848-160">Yes</span></span> | <span data-ttu-id="0a848-161">不适用</span><span class="sxs-lookup"><span data-stu-id="0a848-161">N/A</span></span> | <span data-ttu-id="0a848-162">不适用</span><span class="sxs-lookup"><span data-stu-id="0a848-162">N/A</span></span> |
|||||||

### <a name="guest-participant"></a><span data-ttu-id="0a848-163">来宾参与者</span><span class="sxs-lookup"><span data-stu-id="0a848-163">Guest participant</span></span>

<span data-ttu-id="0a848-164">来宾参与者是来自另一个组织的人员，该人员受邀基于 Azure Active Directory B2B 平台访问 Teams 或贵组织租户中的其他资源。</span><span class="sxs-lookup"><span data-stu-id="0a848-164">A guest participant is someone from another organization who has been invited to access Teams or other resources in your organization's tenant, based on the Azure Active Directory B2B platform.</span></span> <span data-ttu-id="0a848-165">来宾用户可受邀加入常规会议和频道会议。</span><span class="sxs-lookup"><span data-stu-id="0a848-165">Guest users can be invited to join regular meetings and channel meetings.</span></span> <span data-ttu-id="0a848-166">有关来宾参与者的详细信息，请参阅[来宾体验介绍](guest-experience.md#comparison-of-team-member-and-guest-capabilities)。</span><span class="sxs-lookup"><span data-stu-id="0a848-166">Read more about a guest participant in [What the guest experience is like](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span></span>

|  |  | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| <span data-ttu-id="0a848-167">**功能**</span><span class="sxs-lookup"><span data-stu-id="0a848-167">**Feature**</span></span>        | <span data-ttu-id="0a848-168">会议前</span><span class="sxs-lookup"><span data-stu-id="0a848-168">Pre-meeting</span></span> | <span data-ttu-id="0a848-169">会议中</span><span class="sxs-lookup"><span data-stu-id="0a848-169">In-meeting</span></span> | <span data-ttu-id="0a848-170">会议后</span><span class="sxs-lookup"><span data-stu-id="0a848-170">Post-meeting</span></span> |
| <span data-ttu-id="0a848-171">聊天</span><span class="sxs-lookup"><span data-stu-id="0a848-171">Chat</span></span> | <span data-ttu-id="0a848-172">是</span><span class="sxs-lookup"><span data-stu-id="0a848-172">Yes</span></span> | <span data-ttu-id="0a848-173">是</span><span class="sxs-lookup"><span data-stu-id="0a848-173">Yes</span></span> | <span data-ttu-id="0a848-174">是</span><span class="sxs-lookup"><span data-stu-id="0a848-174">Yes</span></span> |
| <span data-ttu-id="0a848-175">会议记录</span><span class="sxs-lookup"><span data-stu-id="0a848-175">Meeting Notes</span></span> | <span data-ttu-id="0a848-176">是</span><span class="sxs-lookup"><span data-stu-id="0a848-176">Yes</span></span> | <span data-ttu-id="0a848-177">是</span><span class="sxs-lookup"><span data-stu-id="0a848-177">Yes</span></span> | <span data-ttu-id="0a848-178">是</span><span class="sxs-lookup"><span data-stu-id="0a848-178">Yes</span></span> |
| <span data-ttu-id="0a848-179">白板</span><span class="sxs-lookup"><span data-stu-id="0a848-179">Whiteboard</span></span> | <span data-ttu-id="0a848-180">否</span><span class="sxs-lookup"><span data-stu-id="0a848-180">No</span></span> | <span data-ttu-id="0a848-181">否</span><span class="sxs-lookup"><span data-stu-id="0a848-181">No</span></span> |<span data-ttu-id="0a848-182">否</span><span class="sxs-lookup"><span data-stu-id="0a848-182">No</span></span> |
| <span data-ttu-id="0a848-183">录制</span><span class="sxs-lookup"><span data-stu-id="0a848-183">Recording</span></span> | <span data-ttu-id="0a848-184">不适用</span><span class="sxs-lookup"><span data-stu-id="0a848-184">N/A</span></span> |<span data-ttu-id="0a848-185">否</span><span class="sxs-lookup"><span data-stu-id="0a848-185">No</span></span> | <span data-ttu-id="0a848-186">否</span><span class="sxs-lookup"><span data-stu-id="0a848-186">No</span></span> |
| <span data-ttu-id="0a848-187">文件 - 将文件共享到会议聊天和在会议聊天中查看/下载文件</span><span class="sxs-lookup"><span data-stu-id="0a848-187">Files - sharing a file into a meeting chat and viewing/downloading a file from a meeting chat</span></span> | <span data-ttu-id="0a848-188">是</span><span class="sxs-lookup"><span data-stu-id="0a848-188">Yes</span></span> | <span data-ttu-id="0a848-189">是</span><span class="sxs-lookup"><span data-stu-id="0a848-189">Yes</span></span> | <span data-ttu-id="0a848-190">是</span><span class="sxs-lookup"><span data-stu-id="0a848-190">Yes</span></span> |
| <span data-ttu-id="0a848-191">文件 - 在会议中展示 PPT（不是通过屏幕共享）和在会议中查看 PPT</span><span class="sxs-lookup"><span data-stu-id="0a848-191">Files - presenting a PPT in a meeting (not via screensharing) and viewing a PPT in a meeting</span></span> | <span data-ttu-id="0a848-192">是</span><span class="sxs-lookup"><span data-stu-id="0a848-192">Yes</span></span> | <span data-ttu-id="0a848-193">是</span><span class="sxs-lookup"><span data-stu-id="0a848-193">Yes</span></span> | <span data-ttu-id="0a848-194">是</span><span class="sxs-lookup"><span data-stu-id="0a848-194">Yes</span></span> |
| <span data-ttu-id="0a848-195">安排会议</span><span class="sxs-lookup"><span data-stu-id="0a848-195">Schedule a meeting</span></span> | <span data-ttu-id="0a848-196">否</span><span class="sxs-lookup"><span data-stu-id="0a848-196">No</span></span> | <span data-ttu-id="0a848-197">不适用</span><span class="sxs-lookup"><span data-stu-id="0a848-197">N/A</span></span> | <span data-ttu-id="0a848-198">不适用</span><span class="sxs-lookup"><span data-stu-id="0a848-198">N/A</span></span> |
|||||||

### <a name="external-federated-participant"></a><span data-ttu-id="0a848-199">外部（联合）参与者</span><span class="sxs-lookup"><span data-stu-id="0a848-199">External (federated) participant</span></span>

<span data-ttu-id="0a848-200">外部参与者是另一个组织中使用 Teams 的人员，该人员受邀加入会议，但无权访问贵组织中的其他共享资源。</span><span class="sxs-lookup"><span data-stu-id="0a848-200">An external participant is someone using Teams in another organization who has been invited to join a meeting, but does not otherwise have access to other shared resources from your organization.</span></span> <span data-ttu-id="0a848-201">外部用户参与者会出现在会议名单中，且其显示名称与他们在自己组织中的标识名称相同。</span><span class="sxs-lookup"><span data-stu-id="0a848-201">External user participants appear in the meeting roster with the same identity name as they have in their own organization.</span></span> <span data-ttu-id="0a848-202">有关外部参与者的详细信息，请参阅[与其他组织的用户通信](communicate-with-users-from-other-organizations.md#external-access)。</span><span class="sxs-lookup"><span data-stu-id="0a848-202">Read more about an external participant in [Communicate with users from other organizations](communicate-with-users-from-other-organizations.md#external-access).</span></span>

|  ||
|-|-|-|
| <span data-ttu-id="0a848-203">**功能**</span><span class="sxs-lookup"><span data-stu-id="0a848-203">**Feature**</span></span> |||
| <span data-ttu-id="0a848-204">聊天</span><span class="sxs-lookup"><span data-stu-id="0a848-204">Chat</span></span> | <span data-ttu-id="0a848-205">是</span><span class="sxs-lookup"><span data-stu-id="0a848-205">Yes</span></span> |
| <span data-ttu-id="0a848-206">会议记录</span><span class="sxs-lookup"><span data-stu-id="0a848-206">Meeting Notes</span></span> | <span data-ttu-id="0a848-207">不适用</span><span class="sxs-lookup"><span data-stu-id="0a848-207">N/A</span></span> |  
| <span data-ttu-id="0a848-208">白板</span><span class="sxs-lookup"><span data-stu-id="0a848-208">Whiteboard</span></span> | <span data-ttu-id="0a848-209">不适用</span><span class="sxs-lookup"><span data-stu-id="0a848-209">N/A</span></span> |
| <span data-ttu-id="0a848-210">录制</span><span class="sxs-lookup"><span data-stu-id="0a848-210">Recording</span></span> | <span data-ttu-id="0a848-211">不适用</span><span class="sxs-lookup"><span data-stu-id="0a848-211">N/A</span></span> |  
| <span data-ttu-id="0a848-212">文件 - 将文件共享到会议聊天和在会议聊天中查看/下载文件</span><span class="sxs-lookup"><span data-stu-id="0a848-212">Files - sharing a file into a meeting chat and viewing/downloading a file from a meeting chat</span></span> |  |  |  |
| <span data-ttu-id="0a848-213">文件 - 在会议中展示 PPT（不是通过屏幕共享）和在会议中查看 PPT</span><span class="sxs-lookup"><span data-stu-id="0a848-213">Files - presenting a PPT in a meeting (not via screensharing) and viewing a PPT in a meeting</span></span> |  |  |  |
| <span data-ttu-id="0a848-214">安排会议</span><span class="sxs-lookup"><span data-stu-id="0a848-214">Schedule a meeting</span></span> | <span data-ttu-id="0a848-215">不适用</span><span class="sxs-lookup"><span data-stu-id="0a848-215">N/A</span></span> |
|||

### <a name="anonymous-participant"></a><span data-ttu-id="0a848-216">匿名参与者</span><span class="sxs-lookup"><span data-stu-id="0a848-216">Anonymous participant</span></span>

<span data-ttu-id="0a848-217">匿名参与者与外部用户类似，但其身份未被投映到会议中。</span><span class="sxs-lookup"><span data-stu-id="0a848-217">The anonymous participant is like an external user, but their identity is not projected into the meeting.</span></span> <span data-ttu-id="0a848-218">在加入时，他们将手动输入一个昵称。</span><span class="sxs-lookup"><span data-stu-id="0a848-218">At join time, they manually enter a nickname.</span></span> <span data-ttu-id="0a848-219">有关匿名参与者的详细信息，请参阅[安全性与 Microsoft Teams](teams-security-guide.md#participant-types)。</span><span class="sxs-lookup"><span data-stu-id="0a848-219">Learn more about an anonymous participant in [Security and Microsoft Teams](teams-security-guide.md#participant-types).</span></span>

|   | | |||
|---------|----------------|----------------|---------------------|------------|--------------|
| <span data-ttu-id="0a848-220">**功能**</span><span class="sxs-lookup"><span data-stu-id="0a848-220">**Feature**</span></span>        | <span data-ttu-id="0a848-221">会议前</span><span class="sxs-lookup"><span data-stu-id="0a848-221">Pre-meeting</span></span> | <span data-ttu-id="0a848-222">会议中</span><span class="sxs-lookup"><span data-stu-id="0a848-222">In-meeting</span></span> | <span data-ttu-id="0a848-223">会议后</span><span class="sxs-lookup"><span data-stu-id="0a848-223">Post-meeting</span></span> |
| <span data-ttu-id="0a848-224">聊天</span><span class="sxs-lookup"><span data-stu-id="0a848-224">Chat</span></span> | <span data-ttu-id="0a848-225">不适用</span><span class="sxs-lookup"><span data-stu-id="0a848-225">N/A</span></span> | <span data-ttu-id="0a848-226">是</span><span class="sxs-lookup"><span data-stu-id="0a848-226">Yes</span></span> | <span data-ttu-id="0a848-227">不适用</span><span class="sxs-lookup"><span data-stu-id="0a848-227">N/A</span></span> |
| <span data-ttu-id="0a848-228">会议记录</span><span class="sxs-lookup"><span data-stu-id="0a848-228">Meeting Notes</span></span> | <span data-ttu-id="0a848-229">不适用</span><span class="sxs-lookup"><span data-stu-id="0a848-229">N/A</span></span> | <span data-ttu-id="0a848-230">否</span><span class="sxs-lookup"><span data-stu-id="0a848-230">No</span></span> | <span data-ttu-id="0a848-231">不适用</span><span class="sxs-lookup"><span data-stu-id="0a848-231">N/A</span></span> |
| <span data-ttu-id="0a848-232">白板</span><span class="sxs-lookup"><span data-stu-id="0a848-232">Whiteboard</span></span> | <span data-ttu-id="0a848-233">不适用</span><span class="sxs-lookup"><span data-stu-id="0a848-233">N/A</span></span> | <span data-ttu-id="0a848-234">否</span><span class="sxs-lookup"><span data-stu-id="0a848-234">No</span></span> | <span data-ttu-id="0a848-235">不适用</span><span class="sxs-lookup"><span data-stu-id="0a848-235">N/A</span></span> |
| <span data-ttu-id="0a848-236">录制</span><span class="sxs-lookup"><span data-stu-id="0a848-236">Recording</span></span> | <span data-ttu-id="0a848-237">不适用</span><span class="sxs-lookup"><span data-stu-id="0a848-237">N/A</span></span> | <span data-ttu-id="0a848-238">否</span><span class="sxs-lookup"><span data-stu-id="0a848-238">No</span></span> | <span data-ttu-id="0a848-239">不适用</span><span class="sxs-lookup"><span data-stu-id="0a848-239">N/A</span></span> |
| <span data-ttu-id="0a848-240">文件 - 将文件共享到会议聊天和在会议聊天中查看/下载文件</span><span class="sxs-lookup"><span data-stu-id="0a848-240">Files - sharing a file into a meeting chat and viewing/downloading a file from a meeting chat</span></span> |  |  |  |
| <span data-ttu-id="0a848-241">文件 - 在会议中展示 PPT（不是通过屏幕共享）和在会议中查看 PPT</span><span class="sxs-lookup"><span data-stu-id="0a848-241">Files - presenting a PPT in a meeting (not via screensharing) and viewing a PPT in a meeting</span></span> |  |  |  |
| <span data-ttu-id="0a848-242">安排会议</span><span class="sxs-lookup"><span data-stu-id="0a848-242">Schedule a meeting</span></span> | <span data-ttu-id="0a848-243">不适用</span><span class="sxs-lookup"><span data-stu-id="0a848-243">N/A</span></span> | <span data-ttu-id="0a848-244">不适用</span><span class="sxs-lookup"><span data-stu-id="0a848-244">N/A</span></span> | <span data-ttu-id="0a848-245">不适用</span><span class="sxs-lookup"><span data-stu-id="0a848-245">N/A</span></span> |
|||||||

## <a name="related-topics"></a><span data-ttu-id="0a848-246">相关主题</span><span class="sxs-lookup"><span data-stu-id="0a848-246">Related topics</span></span>

[<span data-ttu-id="0a848-247">安全性与 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0a848-247">Security and Microsoft Teams</span></span>](teams-security-guide.md)

[<span data-ttu-id="0a848-248">Teams 中的来宾访问</span><span class="sxs-lookup"><span data-stu-id="0a848-248">Guest access in Teams</span></span>](guest-access.md)
