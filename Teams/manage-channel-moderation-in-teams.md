---
title: 在 Microsoft 团队中设置和管理渠道裁决
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft 团队中设置用于裁决的频道，包括如何将团队成员添加为渠道审阅者。
ms.openlocfilehash: d176c1d0076ea444fb46b69011bad94c0c2b3eb4
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775375"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a><span data-ttu-id="4d685-103">在 Microsoft 团队中设置和管理渠道裁决</span><span class="sxs-lookup"><span data-stu-id="4d685-103">Set up and manage channel moderation in Microsoft Teams</span></span>

<span data-ttu-id="4d685-104">在 Microsoft 团队中，团队所有者可以为频道启用裁决，以控制哪些人可以开始新文章以及答复该频道中的帖子。</span><span class="sxs-lookup"><span data-stu-id="4d685-104">In Microsoft Teams, team owners can turn on moderation for a channel to control who can start new posts and reply to posts in that channel.</span></span>

<span data-ttu-id="4d685-105">团队所有者还可以将团队成员添加为审阅人。</span><span class="sxs-lookup"><span data-stu-id="4d685-105">Team owners can also add team members as moderators.</span></span> <span data-ttu-id="4d685-106">团队所有者可能在频道级别没有主题专业知识，以获得最佳支持渠道裁决。</span><span class="sxs-lookup"><span data-stu-id="4d685-106">A team owner might not have the subject matter expertise at the channel level to best support channel moderation.</span></span> <span data-ttu-id="4d685-107">通过允许特定团队成员来安排频道，管理频道中的内容和上下文的责任由团队所有者和渠道审阅者共享。</span><span class="sxs-lookup"><span data-stu-id="4d685-107">By allowing specific team members to moderate a channel, the responsibility of managing content and context within a channel is shared between team owners and channel moderators.</span></span> <span data-ttu-id="4d685-108">例如，团队所有者可以将企业所有者或内容所有者添加为审阅者，从而使他们可以控制该频道中的信息共享。</span><span class="sxs-lookup"><span data-stu-id="4d685-108">For example, a team owner can add business owners or content owners as moderators, which lets them control information sharing in that channel.</span></span>

## <a name="what-can-a-channel-moderator-do"></a><span data-ttu-id="4d685-109">频道审查方可以执行哪些操作？</span><span class="sxs-lookup"><span data-stu-id="4d685-109">What can a channel moderator do?</span></span>

<span data-ttu-id="4d685-110">频道审阅者可以：</span><span class="sxs-lookup"><span data-stu-id="4d685-110">Channel moderators can:</span></span>

- <span data-ttu-id="4d685-111">在频道中开始新的文章。</span><span class="sxs-lookup"><span data-stu-id="4d685-111">Start new posts in the channel.</span></span> <span data-ttu-id="4d685-112">为频道启用裁决后，只有审阅人可以在该频道中开始新的帖子。</span><span class="sxs-lookup"><span data-stu-id="4d685-112">When moderation is turned on for a channel, only moderators can start new posts in that channel.</span></span>
- <span data-ttu-id="4d685-113">将团队成员添加和删除为频道的审阅人。</span><span class="sxs-lookup"><span data-stu-id="4d685-113">Add and remove team members as moderators to a channel.</span></span> <span data-ttu-id="4d685-114">请记住，默认情况下，团队所有者是 "频道审阅者"，不能删除。</span><span class="sxs-lookup"><span data-stu-id="4d685-114">Keep in mind that by default, team owners are channel moderators and can't be removed.</span></span>
- <span data-ttu-id="4d685-115">控制团队成员是否可以答复现有信道消息，以及机器人和连接器是否可以提交频道消息。</span><span class="sxs-lookup"><span data-stu-id="4d685-115">Control whether team members can reply to existing channel messages and whether bots and connectors can submit channel messages.</span></span>

## <a name="scenarios"></a><span data-ttu-id="4d685-116">方案</span><span class="sxs-lookup"><span data-stu-id="4d685-116">Scenarios</span></span>

<span data-ttu-id="4d685-117">下面是组织如何在团队中使用渠道裁决的一些示例。</span><span class="sxs-lookup"><span data-stu-id="4d685-117">Here's some examples of how your organization can use channel moderation in Teams.</span></span>

### <a name="use-a-channel-as-an-announcement-channel"></a><span data-ttu-id="4d685-118">将频道用作公告通道</span><span class="sxs-lookup"><span data-stu-id="4d685-118">Use a channel as an announcement channel</span></span>

<span data-ttu-id="4d685-119">市场营销团队使用特定的频道来共享关键项目公告和可交付结果。</span><span class="sxs-lookup"><span data-stu-id="4d685-119">The Marketing team uses a specific channel to share key project announcements and deliverables.</span></span> <span data-ttu-id="4d685-120">有时，团队成员向频道发布内容更恰当地属于其他频道。</span><span class="sxs-lookup"><span data-stu-id="4d685-120">Sometimes team members post content to the channel that more appropriately belongs in other channels.</span></span> <span data-ttu-id="4d685-121">团队所有者希望将频道中的信息共享限制为仅通知通知，以便团队成员可以使用该频道保持最重要的内容。</span><span class="sxs-lookup"><span data-stu-id="4d685-121">The team owner wants to restrict information sharing in the channel to only announcements so that team members can use that channel to stay on top of what's important.</span></span>

<span data-ttu-id="4d685-122">在此方案中，团队所有者将市场营销线索添加为审阅者，以便他们可以在频道中发布公告，并关闭工作组成员答复该频道中的邮件的功能。</span><span class="sxs-lookup"><span data-stu-id="4d685-122">In this scenario, the team owner adds Marketing leads as moderators so they can post announcements in the channel and turns off the ability for team members to reply to messages in that channel.</span></span>

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a><span data-ttu-id="4d685-123">在教育团队中使用渠道进行课堂讨论</span><span class="sxs-lookup"><span data-stu-id="4d685-123">Use a channel for class discussions in Teams for Education</span></span>

<span data-ttu-id="4d685-124">在 "教育团队" 中，一位科学老师希望使用频道在特定教室主题的重点讨论中吸引学生。</span><span class="sxs-lookup"><span data-stu-id="4d685-124">In Teams for Education, a science teacher want to use a channel to engage students in focused discussions on specific classroom topics.</span></span>

<span data-ttu-id="4d685-125">在这种情况下，教师可以通过 "教学助手" 来使频道适中。</span><span class="sxs-lookup"><span data-stu-id="4d685-125">In this scenario, the teacher allows their teaching assistants to moderate the channel.</span></span> <span data-ttu-id="4d685-126">然后，"教学助手" 可以创建新的文章来启动和推动与学生进行讨论。</span><span class="sxs-lookup"><span data-stu-id="4d685-126">The teaching assistants can then create new posts to initiate and drive discussions with students.</span></span>

## <a name="manage-channel-moderation"></a><span data-ttu-id="4d685-127">管理渠道裁决</span><span class="sxs-lookup"><span data-stu-id="4d685-127">Manage channel moderation</span></span>

<span data-ttu-id="4d685-128">在 "团队" 中，转到频道，单击 "**更多选项 ...** " > **管理频道**。</span><span class="sxs-lookup"><span data-stu-id="4d685-128">In Teams, go to the channel, click **More options ...** > **Manage channel**.</span></span> <span data-ttu-id="4d685-129">在此处，您可以打开和关闭 "裁决"，将团队成员添加为审阅者，以及设置首选项。</span><span class="sxs-lookup"><span data-stu-id="4d685-129">From here you can turn on and turn off moderation, add team members as moderators, and set preferences.</span></span>

<span data-ttu-id="4d685-130">通道裁决是每个通道的设置。</span><span class="sxs-lookup"><span data-stu-id="4d685-130">Channel moderation is a per-channel setting.</span></span> <span data-ttu-id="4d685-131">频道裁决没有租户级别的设置。</span><span class="sxs-lookup"><span data-stu-id="4d685-131">There's no tenant-level setting for channel moderation.</span></span> <span data-ttu-id="4d685-132">如果您希望我们添加租户级通道裁决设置，请在[团队 UserVoice](https://microsoftteams.uservoice.com/)上请求。</span><span class="sxs-lookup"><span data-stu-id="4d685-132">If you'd like us to add a tenant-level channel moderation setting, request it on [Teams UserVoice](https://microsoftteams.uservoice.com/).</span></span>

![manage-channel-moderation-in-teams-preferences](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a><span data-ttu-id="4d685-134">打开或关闭频道裁决</span><span class="sxs-lookup"><span data-stu-id="4d685-134">Turn on or turn off moderation for a channel</span></span>

<span data-ttu-id="4d685-135">默认情况下，"裁决" 处于关闭状态，这意味着常规频道设置适用于团队所有者和团队成员。</span><span class="sxs-lookup"><span data-stu-id="4d685-135">By default, moderation is off, which means that the usual channel settings apply to team owners and team members.</span></span> <span data-ttu-id="4d685-136">例如，您可以将新帖子限制为仅限团队成员，或允许每个人（包括来宾）开始新的文章。</span><span class="sxs-lookup"><span data-stu-id="4d685-136">For example, you can restrict new posts to only team members or allow everyone, including guests, to start new posts.</span></span>

<span data-ttu-id="4d685-137">若要为频道启用裁决，请在 "**通道裁决**" 下，单击 **"打开"**。</span><span class="sxs-lookup"><span data-stu-id="4d685-137">To turn on moderation for a channel, under **Channel moderation**, click **On**.</span></span> <span data-ttu-id="4d685-138">当频道裁决处于开启时，只有审阅人可以开始新的帖子。</span><span class="sxs-lookup"><span data-stu-id="4d685-138">When channel moderation is on, only moderators can start new posts.</span></span> 

### <a name="add-or-remove-channel-moderators"></a><span data-ttu-id="4d685-139">添加或删除频道审阅者</span><span class="sxs-lookup"><span data-stu-id="4d685-139">Add or remove channel moderators</span></span>

<span data-ttu-id="4d685-140">在 "**谁是审阅人**" 下，单击 "**管理**"，然后添加或删除团队成员为 "审阅者"。</span><span class="sxs-lookup"><span data-stu-id="4d685-140">Under **Who are the moderators?**, click **Manage**, and then add or remove team members as moderators.</span></span> <span data-ttu-id="4d685-141">团队所有者和审阅者可以添加和删除其他审阅人。</span><span class="sxs-lookup"><span data-stu-id="4d685-141">Team owners and moderators can add and remove other moderators.</span></span>  

### <a name="set-team-member-permissions"></a><span data-ttu-id="4d685-142">设置团队成员权限</span><span class="sxs-lookup"><span data-stu-id="4d685-142">Set team member permissions</span></span>

<span data-ttu-id="4d685-143">在 "**团队成员权限**" 下，选中要允许的活动旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="4d685-143">Under **Team member permissions**, select the check boxes next to the activities  you want to allow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4d685-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="4d685-144">Related topics</span></span>

- [<span data-ttu-id="4d685-145">团队中的团队和频道概述</span><span class="sxs-lookup"><span data-stu-id="4d685-145">Overview of teams and channels in Teams</span></span>](teams-channels-overview.md)
