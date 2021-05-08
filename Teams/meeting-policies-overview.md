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
description: 了解如何在会议中管理会议策略Teams并使用它们来控制可供会议参与者用于用户安排的会议的功能。
ms.openlocfilehash: d9f403625225711cb21245ca01262d3c0140063f
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598700"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="92004-103">管理 Teams 中的会议策略</span><span class="sxs-lookup"><span data-stu-id="92004-103">Manage meeting policies in Teams</span></span>

<span data-ttu-id="92004-104"><a name="bkautomatically-admit-people"> </a></span><span class="sxs-lookup"><span data-stu-id="92004-104"><a name="bkautomatically-admit-people"> </a></span></span>

<span data-ttu-id="92004-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span><span class="sxs-lookup"><span data-stu-id="92004-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span></span>

<span data-ttu-id="92004-106"><a name="bkallow-transcription"> </a></span><span class="sxs-lookup"><span data-stu-id="92004-106"><a name="bkallow-transcription"> </a></span></span>

<span data-ttu-id="92004-107">会议策略Meeting policies用于控制组织中用户安排的会议的与会者可用的功能。</span><span class="sxs-lookup"><span data-stu-id="92004-107">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="92004-108">可以使用自动创建的全局 (默认整个组织) 策略，也可以创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="92004-108">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="92004-109">可以在 Microsoft Teams 管理中心内或使用 [PowerShell](teams-powershell-overview.md) 管理会议策略。</span><span class="sxs-lookup"><span data-stu-id="92004-109">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="92004-110">有关使用角色管理会议演示者和与会者权限的信息，请参阅 [Teams 会议角色](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。</span><span class="sxs-lookup"><span data-stu-id="92004-110">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="92004-111">可以通过以下方式实施策略，这些策略会在会议开始前、会议期间或会议结束后影响用户的会议体验。</span><span class="sxs-lookup"><span data-stu-id="92004-111">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="92004-112">实施类型</span><span class="sxs-lookup"><span data-stu-id="92004-112">Implementation type</span></span>  |<span data-ttu-id="92004-113">说明</span><span class="sxs-lookup"><span data-stu-id="92004-113">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="92004-114">按组织者</span><span class="sxs-lookup"><span data-stu-id="92004-114">Per-organizer</span></span>    |<span data-ttu-id="92004-115">如果你实现按组织者策略，所有会议参加者都会继承组织者的策略。</span><span class="sxs-lookup"><span data-stu-id="92004-115">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="92004-116">例如 **，"自动** 允许人员"是按组织者的策略，用于控制用户是直接加入会议，还是等待分配有该策略的用户安排的会议。</span><span class="sxs-lookup"><span data-stu-id="92004-116">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="92004-117">按用户</span><span class="sxs-lookup"><span data-stu-id="92004-117">Per-user</span></span>    |<span data-ttu-id="92004-118">实施按用户策略时，只有每用户策略适用于限制组织者和/或会议参与者的某些功能。</span><span class="sxs-lookup"><span data-stu-id="92004-118">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="92004-119">例如， **“在频道中允许立即开会”** 是按用户策略。</span><span class="sxs-lookup"><span data-stu-id="92004-119">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="92004-120">按组织者和按用户</span><span class="sxs-lookup"><span data-stu-id="92004-120">Per-organizer and per-user</span></span>     |<span data-ttu-id="92004-121">当实施按组织者和按用户策略的组合时，会根据会议参与者的策略和组织者的策略对其进行某些功能限制。</span><span class="sxs-lookup"><span data-stu-id="92004-121">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="92004-122">例如，**“允许云录制”** 是按组织者和按用户策略。</span><span class="sxs-lookup"><span data-stu-id="92004-122">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="92004-123">打开此设置以允许会议组织者和参与者开始和停止录制。</span><span class="sxs-lookup"><span data-stu-id="92004-123">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="92004-124">可编辑全局策略中的设置，或创建和分配一个或多个自定义策略。</span><span class="sxs-lookup"><span data-stu-id="92004-124">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="92004-125">除非创建并指定一个自定义策略，否则用户将获得全局策略。</span><span class="sxs-lookup"><span data-stu-id="92004-125">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="92004-126">如果用户启用了音频会议许可或允许用户进行音频会议，则会议详情按钮将可用，否则，会议详情将不可用。</span><span class="sxs-lookup"><span data-stu-id="92004-126">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="92004-127">创建自定义会议策略</span><span class="sxs-lookup"><span data-stu-id="92004-127">Create a custom meeting policy</span></span>

1. <span data-ttu-id="92004-128">在 Microsoft Teams 管理员中心的左侧导航中，转到 **“会议”** > **“会议策略”**。</span><span class="sxs-lookup"><span data-stu-id="92004-128">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="92004-129">单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="92004-129">Click **Add**.</span></span>
3. <span data-ttu-id="92004-130">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="92004-130">Enter a name and description for the policy.</span></span> <span data-ttu-id="92004-131">名称不能包含特殊字符或超过 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="92004-131">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="92004-132">选择想要的设置。</span><span class="sxs-lookup"><span data-stu-id="92004-132">Choose the settings that you want.</span></span>
5. <span data-ttu-id="92004-133">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="92004-133">Click **Save**.</span></span>

<span data-ttu-id="92004-134">例如，假设你有一组用户并且你想要限制这组用户的会议所需的带宽量。</span><span class="sxs-lookup"><span data-stu-id="92004-134">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="92004-135">你要创建新的自定义策略并命名为“带宽限制”，然后禁用以下设置：</span><span class="sxs-lookup"><span data-stu-id="92004-135">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="92004-136">在“音频和视频”中：</span><span class="sxs-lookup"><span data-stu-id="92004-136">Under **Audio & video**:</span></span>

- <span data-ttu-id="92004-137">禁用“允许云录制”。</span><span class="sxs-lookup"><span data-stu-id="92004-137">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="92004-138">禁用“允许 IP 视频”。</span><span class="sxs-lookup"><span data-stu-id="92004-138">Turn off Allow IP video.</span></span>

<span data-ttu-id="92004-139">在“内容共享”中：</span><span class="sxs-lookup"><span data-stu-id="92004-139">Under **Content sharing**:</span></span>

- <span data-ttu-id="92004-140">禁用屏幕共享模式。</span><span class="sxs-lookup"><span data-stu-id="92004-140">Disable screen sharing mode.</span></span>
- <span data-ttu-id="92004-141">禁用“允许白板”。</span><span class="sxs-lookup"><span data-stu-id="92004-141">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="92004-142">禁用“允许共享笔记”。</span><span class="sxs-lookup"><span data-stu-id="92004-142">Turn off Allow shared notes.</span></span>

<span data-ttu-id="92004-143">然后将此策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="92004-143">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="92004-144">编辑会议策略</span><span class="sxs-lookup"><span data-stu-id="92004-144">Edit a meeting policy</span></span>

<span data-ttu-id="92004-145">可以编辑全局策略和创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="92004-145">You can edit the global policy and any custom policies that you create.</span></span>

1. <span data-ttu-id="92004-146">在 Microsoft Teams 管理员中心的左侧导航中，转到 **“会议”** > **“会议策略”**。</span><span class="sxs-lookup"><span data-stu-id="92004-146">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="92004-147">单击策略名称的左侧以选择用户，然后单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="92004-147">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="92004-148">在此处根据需要进行更改。</span><span class="sxs-lookup"><span data-stu-id="92004-148">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="92004-149">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="92004-149">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="92004-150">一次只能向一个用户分配一个会议策略。</span><span class="sxs-lookup"><span data-stu-id="92004-150">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="92004-151">将会议策略分配给用户</span><span class="sxs-lookup"><span data-stu-id="92004-151">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="92004-152">如果已将它分配给用户，则无法删除该策略。</span><span class="sxs-lookup"><span data-stu-id="92004-152">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="92004-153">必须首先为所有受影响的用户指定不同的策略，然后才能删除原来的策略。</span><span class="sxs-lookup"><span data-stu-id="92004-153">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="92004-154">会议策略设置</span><span class="sxs-lookup"><span data-stu-id="92004-154">Meeting policy settings</span></span>

<span data-ttu-id="92004-155">在"会议策略"页面上选择现有策略或选择"添加"以添加新策略时，可以配置以下设置。</span><span class="sxs-lookup"><span data-stu-id="92004-155">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="92004-156">常规</span><span class="sxs-lookup"><span data-stu-id="92004-156">General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="92004-157">音频和视频</span><span class="sxs-lookup"><span data-stu-id="92004-157">Audio & video</span></span>](meeting-policies-audio-and-video.md)
- [<span data-ttu-id="92004-158">内容共享</span><span class="sxs-lookup"><span data-stu-id="92004-158">Content sharing</span></span>](meeting-policies-content-sharing.md)
- [<span data-ttu-id="92004-159">参与者和来宾</span><span class="sxs-lookup"><span data-stu-id="92004-159">Participants & guests</span></span>](meeting-policies-participants-and-guests.md)


## <a name="related-topics"></a><span data-ttu-id="92004-160">相关主题</span><span class="sxs-lookup"><span data-stu-id="92004-160">Related topics</span></span>

- [<span data-ttu-id="92004-161">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="92004-161">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="92004-162">向 Teams 中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="92004-162">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="92004-163">从用户删除 RestrictedAnonymousAccess Teams 会议策略</span><span class="sxs-lookup"><span data-stu-id="92004-163">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)