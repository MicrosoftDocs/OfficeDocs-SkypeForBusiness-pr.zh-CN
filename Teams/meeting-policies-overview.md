---
title: 管理会议策略
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
- ms.teamsadmincenter.meetingpolicies.overview
- seo-marvel-apr2020
description: 了解如何在 Teams 中管理会议策略设置，并使用它们来控制可供会议参与者用于用户安排的会议的功能。
ms.openlocfilehash: d9f403625225711cb21245ca01262d3c0140063f
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598700"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="b6f3b-103">管理 Teams 中的会议策略</span><span class="sxs-lookup"><span data-stu-id="b6f3b-103">Manage meeting policies in Teams</span></span>

<span data-ttu-id="b6f3b-104"><a name="bkautomatically-admit-people"> </a></span><span class="sxs-lookup"><span data-stu-id="b6f3b-104"><a name="bkautomatically-admit-people"> </a></span></span>

<span data-ttu-id="b6f3b-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span><span class="sxs-lookup"><span data-stu-id="b6f3b-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span></span>

<span data-ttu-id="b6f3b-106"><a name="bkallow-transcription"> </a></span><span class="sxs-lookup"><span data-stu-id="b6f3b-106"><a name="bkallow-transcription"> </a></span></span>

<span data-ttu-id="b6f3b-107">会议策略Meeting policies用于控制组织中用户安排的会议的与会者可用的功能。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-107">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="b6f3b-108">可以使用全局策略 (组织范围的默认) 自动创建或创建和分配自定义策略的策略。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-108">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="b6f3b-109">在 Microsoft Teams 管理中心中或通过使用 [PowerShell 管理会议策略](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-109">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b6f3b-110">有关使用角色管理会议演示者和与会者的权限的信息，请参阅 [Teams 会议中的角色](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-110">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="b6f3b-111">您可以通过以下方式实施策略，这会影响用户在会议开始、会议期间或会议后的会议体验。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-111">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="b6f3b-112">实现类型</span><span class="sxs-lookup"><span data-stu-id="b6f3b-112">Implementation type</span></span>  |<span data-ttu-id="b6f3b-113">说明</span><span class="sxs-lookup"><span data-stu-id="b6f3b-113">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="b6f3b-114">每个组织者</span><span class="sxs-lookup"><span data-stu-id="b6f3b-114">Per-organizer</span></span>    |<span data-ttu-id="b6f3b-115">实施按组织者的策略时，所有会议参与者将继承组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-115">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="b6f3b-116">例如 **，"自动** 允许人员"是按组织者的策略，用于控制用户是直接加入会议，还是等待分配有该策略的用户安排的会议。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-116">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="b6f3b-117">按用户</span><span class="sxs-lookup"><span data-stu-id="b6f3b-117">Per-user</span></span>    |<span data-ttu-id="b6f3b-118">实施每用户策略时，仅应用按用户策略来限制组织者和/或会议参与者的某些功能。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-118">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="b6f3b-119">例如 **，"允许现在在频道中开会** "是按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-119">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="b6f3b-120">按组织者和按用户</span><span class="sxs-lookup"><span data-stu-id="b6f3b-120">Per-organizer and per-user</span></span>     |<span data-ttu-id="b6f3b-121">实施按组织者策略和按用户策略的组合时，某些功能会基于会议参与者的策略和组织者的策略进行限制。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-121">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="b6f3b-122">例如， **允许云录制** 是按组织者和按用户的策略。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-122">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="b6f3b-123">打开此设置以允许会议组织者和参与者开始和停止录制。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-123">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="b6f3b-124">可以在全局策略中编辑设置，也可以创建并分配一个或多个自定义策略。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-124">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="b6f3b-125">除非创建并分配自定义策略，否则用户将获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-125">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="b6f3b-126">如果用户已启用音频会议许可证或用户允许音频会议，则会议详细信息按钮将可用，否则会议详细信息将不可用。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-126">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="b6f3b-127">创建自定义会议策略</span><span class="sxs-lookup"><span data-stu-id="b6f3b-127">Create a custom meeting policy</span></span>

1. <span data-ttu-id="b6f3b-128">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"会议**  >  **会议策略"。**</span><span class="sxs-lookup"><span data-stu-id="b6f3b-128">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="b6f3b-129">单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-129">Click **Add**.</span></span>
3. <span data-ttu-id="b6f3b-130">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-130">Enter a name and description for the policy.</span></span> <span data-ttu-id="b6f3b-131">名称不能包含特殊字符或超过 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-131">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="b6f3b-132">选择想要的设置。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-132">Choose the settings that you want.</span></span>
5. <span data-ttu-id="b6f3b-133">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-133">Click **Save**.</span></span>

<span data-ttu-id="b6f3b-134">例如，假设你有一组用户并且你想要限制这组用户的会议所需的带宽量。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-134">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="b6f3b-135">你要创建新的自定义策略并命名为“带宽限制”，然后禁用以下设置：</span><span class="sxs-lookup"><span data-stu-id="b6f3b-135">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="b6f3b-136">在“音频和视频”中：</span><span class="sxs-lookup"><span data-stu-id="b6f3b-136">Under **Audio & video**:</span></span>

- <span data-ttu-id="b6f3b-137">禁用“允许云录制”。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-137">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="b6f3b-138">禁用“允许 IP 视频”。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-138">Turn off Allow IP video.</span></span>

<span data-ttu-id="b6f3b-139">在“内容共享”中：</span><span class="sxs-lookup"><span data-stu-id="b6f3b-139">Under **Content sharing**:</span></span>

- <span data-ttu-id="b6f3b-140">禁用屏幕共享模式。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-140">Disable screen sharing mode.</span></span>
- <span data-ttu-id="b6f3b-141">禁用“允许白板”。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-141">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="b6f3b-142">禁用“允许共享笔记”。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-142">Turn off Allow shared notes.</span></span>

<span data-ttu-id="b6f3b-143">然后将此策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-143">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="b6f3b-144">编辑会议策略</span><span class="sxs-lookup"><span data-stu-id="b6f3b-144">Edit a meeting policy</span></span>

<span data-ttu-id="b6f3b-145">可以编辑全局策略和创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-145">You can edit the global policy and any custom policies that you create.</span></span>

1. <span data-ttu-id="b6f3b-146">在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"会议**  >  **会议策略"。**</span><span class="sxs-lookup"><span data-stu-id="b6f3b-146">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="b6f3b-147">单击策略名称的左侧以选择用户，然后单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-147">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="b6f3b-148">在此处根据需要进行更改。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-148">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="b6f3b-149">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-149">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="b6f3b-150">一次只能为用户分配一个会议策略。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-150">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="b6f3b-151">将会议策略分配给用户</span><span class="sxs-lookup"><span data-stu-id="b6f3b-151">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="b6f3b-152">如果将用户分配到策略，则不能删除该策略。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-152">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="b6f3b-153">必须先将不同的策略分配给所有受影响的用户，然后可以删除原始策略。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-153">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="b6f3b-154">会议策略设置</span><span class="sxs-lookup"><span data-stu-id="b6f3b-154">Meeting policy settings</span></span>

<span data-ttu-id="b6f3b-155">在"会议策略"页面上选择现有策略或选择"添加"以添加新策略时，可以配置以下设置。</span><span class="sxs-lookup"><span data-stu-id="b6f3b-155">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="b6f3b-156">常规</span><span class="sxs-lookup"><span data-stu-id="b6f3b-156">General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="b6f3b-157">音频&视频</span><span class="sxs-lookup"><span data-stu-id="b6f3b-157">Audio & video</span></span>](meeting-policies-audio-and-video.md)
- [<span data-ttu-id="b6f3b-158">内容共享</span><span class="sxs-lookup"><span data-stu-id="b6f3b-158">Content sharing</span></span>](meeting-policies-content-sharing.md)
- [<span data-ttu-id="b6f3b-159">来宾&参与者</span><span class="sxs-lookup"><span data-stu-id="b6f3b-159">Participants & guests</span></span>](meeting-policies-participants-and-guests.md)


## <a name="related-topics"></a><span data-ttu-id="b6f3b-160">相关主题</span><span class="sxs-lookup"><span data-stu-id="b6f3b-160">Related topics</span></span>

- [<span data-ttu-id="b6f3b-161">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="b6f3b-161">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="b6f3b-162">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="b6f3b-162">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="b6f3b-163">从用户中删除 RestrictedAnonymousAccess Teams 会议策略</span><span class="sxs-lookup"><span data-stu-id="b6f3b-163">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)