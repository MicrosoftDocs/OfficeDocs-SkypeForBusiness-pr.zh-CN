---
title: 设置和管理渠道裁决
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft 团队中设置用于裁决的频道，包括如何将团队成员添加为渠道审阅者。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6cdf6988afb9afbd91c2bfd19ed516c8e8fdf702
ms.sourcegitcommit: 379bfaf6b0584c1ac93341af605f93ab932a442b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240612"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a><span data-ttu-id="ab182-103">在 Microsoft 团队中设置和管理渠道裁决</span><span class="sxs-lookup"><span data-stu-id="ab182-103">Set up and manage channel moderation in Microsoft Teams</span></span>

<span data-ttu-id="ab182-104">在 Microsoft 团队中，团队所有者可以为标准频道启用裁决，以控制哪些人可以开始新文章以及答复该频道中的帖子。</span><span class="sxs-lookup"><span data-stu-id="ab182-104">In Microsoft Teams, team owners can turn on moderation for a standard channel to control who can start new posts and reply to posts in that channel.</span></span>

<span data-ttu-id="ab182-105">团队所有者还可以将团队成员添加为审阅人。</span><span class="sxs-lookup"><span data-stu-id="ab182-105">Team owners can also add team members as moderators.</span></span> <span data-ttu-id="ab182-106">团队所有者可能在频道级别没有主题专业知识，以获得最佳支持渠道裁决。</span><span class="sxs-lookup"><span data-stu-id="ab182-106">A team owner might not have the subject matter expertise at the channel level to best support channel moderation.</span></span> <span data-ttu-id="ab182-107">通过允许特定团队成员来安排频道，管理频道中的内容和上下文的责任由团队所有者和渠道审阅者共享。</span><span class="sxs-lookup"><span data-stu-id="ab182-107">By allowing specific team members to moderate a channel, the responsibility of managing content and context within a channel is shared between team owners and channel moderators.</span></span> <span data-ttu-id="ab182-108">例如，团队所有者可以将企业所有者或内容所有者添加为审阅者，从而使他们可以控制该频道中的信息共享。</span><span class="sxs-lookup"><span data-stu-id="ab182-108">For example, a team owner can add business owners or content owners as moderators, which lets them control information sharing in that channel.</span></span>

> [!NOTE]
> <span data-ttu-id="ab182-109">目前，渠道裁决适用于标准频道。</span><span class="sxs-lookup"><span data-stu-id="ab182-109">Currently, channel moderation is available for standard channels.</span></span> <span data-ttu-id="ab182-110">它不适用于专用频道。</span><span class="sxs-lookup"><span data-stu-id="ab182-110">It's not available for private channels.</span></span>

## <a name="what-can-a-channel-moderator-do"></a><span data-ttu-id="ab182-111">频道审查方可以执行哪些操作？</span><span class="sxs-lookup"><span data-stu-id="ab182-111">What can a channel moderator do?</span></span>

<span data-ttu-id="ab182-112">频道审阅者可以：</span><span class="sxs-lookup"><span data-stu-id="ab182-112">Channel moderators can:</span></span>

- <span data-ttu-id="ab182-113">在频道中开始新的文章。</span><span class="sxs-lookup"><span data-stu-id="ab182-113">Start new posts in the channel.</span></span> <span data-ttu-id="ab182-114">为频道启用裁决后，只有审阅人可以在该频道中开始新的帖子。</span><span class="sxs-lookup"><span data-stu-id="ab182-114">When moderation is turned on for a channel, only moderators can start new posts in that channel.</span></span>
- <span data-ttu-id="ab182-115">将团队成员添加和删除为频道的审阅人。</span><span class="sxs-lookup"><span data-stu-id="ab182-115">Add and remove team members as moderators to a channel.</span></span> <span data-ttu-id="ab182-116">请记住，默认情况下，团队所有者是 "频道审阅者"，不能删除。</span><span class="sxs-lookup"><span data-stu-id="ab182-116">Keep in mind that by default, team owners are channel moderators and can't be removed.</span></span>
- <span data-ttu-id="ab182-117">控制团队成员是否可以答复现有信道消息，以及机器人和连接器是否可以提交频道消息。</span><span class="sxs-lookup"><span data-stu-id="ab182-117">Control whether team members can reply to existing channel messages and whether bots and connectors can submit channel messages.</span></span>

## <a name="scenarios"></a><span data-ttu-id="ab182-118">方案</span><span class="sxs-lookup"><span data-stu-id="ab182-118">Scenarios</span></span>

<span data-ttu-id="ab182-119">下面是组织如何在团队中使用渠道裁决的一些示例。</span><span class="sxs-lookup"><span data-stu-id="ab182-119">Here's some examples of how your organization can use channel moderation in Teams.</span></span>

### <a name="use-a-channel-as-an-announcement-channel"></a><span data-ttu-id="ab182-120">将频道用作公告通道</span><span class="sxs-lookup"><span data-stu-id="ab182-120">Use a channel as an announcement channel</span></span>

<span data-ttu-id="ab182-121">市场营销团队使用特定的频道来共享关键项目公告和可交付结果。</span><span class="sxs-lookup"><span data-stu-id="ab182-121">The Marketing team uses a specific channel to share key project announcements and deliverables.</span></span> <span data-ttu-id="ab182-122">有时，团队成员向频道发布内容更恰当地属于其他频道。</span><span class="sxs-lookup"><span data-stu-id="ab182-122">Sometimes team members post content to the channel that more appropriately belongs in other channels.</span></span> <span data-ttu-id="ab182-123">团队所有者希望将频道中的信息共享限制为仅通知通知，以便团队成员可以使用该频道保持最重要的内容。</span><span class="sxs-lookup"><span data-stu-id="ab182-123">The team owner wants to restrict information sharing in the channel to only announcements so that team members can use that channel to stay on top of what's important.</span></span>

<span data-ttu-id="ab182-124">在此方案中，团队所有者将市场营销线索添加为审阅者，以便他们可以在频道中发布公告，并关闭工作组成员答复该频道中的邮件的功能。</span><span class="sxs-lookup"><span data-stu-id="ab182-124">In this scenario, the team owner adds Marketing leads as moderators so they can post announcements in the channel and turns off the ability for team members to reply to messages in that channel.</span></span>

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a><span data-ttu-id="ab182-125">在教育团队中使用渠道进行课堂讨论</span><span class="sxs-lookup"><span data-stu-id="ab182-125">Use a channel for class discussions in Teams for Education</span></span>

<span data-ttu-id="ab182-126">在 "教育团队" 中，一位科学老师希望使用频道在特定教室主题的重点讨论中吸引学生。</span><span class="sxs-lookup"><span data-stu-id="ab182-126">In Teams for Education, a science teacher want to use a channel to engage students in focused discussions on specific classroom topics.</span></span>

<span data-ttu-id="ab182-127">在这种情况下，教师可以通过 "教学助手" 来使频道适中。</span><span class="sxs-lookup"><span data-stu-id="ab182-127">In this scenario, the teacher allows their teaching assistants to moderate the channel.</span></span> <span data-ttu-id="ab182-128">然后，"教学助手" 可以创建新的文章来启动和推动与学生进行讨论。</span><span class="sxs-lookup"><span data-stu-id="ab182-128">The teaching assistants can then create new posts to initiate and drive discussions with students.</span></span>

## <a name="manage-channel-moderation"></a><span data-ttu-id="ab182-129">管理渠道裁决</span><span class="sxs-lookup"><span data-stu-id="ab182-129">Manage channel moderation</span></span>

<span data-ttu-id="ab182-130">在 "团队" 中，转到频道，单击 "**更多选项 ...** " > **管理频道**。</span><span class="sxs-lookup"><span data-stu-id="ab182-130">In Teams, go to the channel, click **More options ...** > **Manage channel**.</span></span> <span data-ttu-id="ab182-131">在此处，您可以打开和关闭 "裁决"，将团队成员添加为审阅者，以及设置首选项。</span><span class="sxs-lookup"><span data-stu-id="ab182-131">From here you can turn on and turn off moderation, add team members as moderators, and set preferences.</span></span>

<span data-ttu-id="ab182-132">通道裁决是每个通道的设置。</span><span class="sxs-lookup"><span data-stu-id="ab182-132">Channel moderation is a per-channel setting.</span></span> <span data-ttu-id="ab182-133">频道裁决没有租户级别的设置。</span><span class="sxs-lookup"><span data-stu-id="ab182-133">There's no tenant-level setting for channel moderation.</span></span> <span data-ttu-id="ab182-134">如果您希望我们添加租户级通道裁决设置，请在[团队 UserVoice](https://microsoftteams.uservoice.com/)上请求。</span><span class="sxs-lookup"><span data-stu-id="ab182-134">If you'd like us to add a tenant-level channel moderation setting, request it on [Teams UserVoice](https://microsoftteams.uservoice.com/).</span></span>

![manage-channel-moderation-in-teams-preferences](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a><span data-ttu-id="ab182-136">打开或关闭频道裁决</span><span class="sxs-lookup"><span data-stu-id="ab182-136">Turn on or turn off moderation for a channel</span></span>

<span data-ttu-id="ab182-137">默认情况下，"裁决" 处于关闭状态，这意味着常规频道设置适用于团队所有者和团队成员。</span><span class="sxs-lookup"><span data-stu-id="ab182-137">By default, moderation is off, which means that the usual channel settings apply to team owners and team members.</span></span> <span data-ttu-id="ab182-138">例如，您可以将新帖子限制为仅限团队成员，或允许每个人（包括来宾）开始新的文章。</span><span class="sxs-lookup"><span data-stu-id="ab182-138">For example, you can restrict new posts to only team members or allow everyone, including guests, to start new posts.</span></span>

<span data-ttu-id="ab182-139">若要为频道启用裁决，请在 "**通道裁决**" 下，单击 **"打开"**。</span><span class="sxs-lookup"><span data-stu-id="ab182-139">To turn on moderation for a channel, under **Channel moderation**, click **On**.</span></span> <span data-ttu-id="ab182-140">当频道裁决处于开启时，只有审阅人可以开始新的帖子。</span><span class="sxs-lookup"><span data-stu-id="ab182-140">When channel moderation is on, only moderators can start new posts.</span></span> 

### <a name="add-or-remove-channel-moderators"></a><span data-ttu-id="ab182-141">添加或删除频道审阅者</span><span class="sxs-lookup"><span data-stu-id="ab182-141">Add or remove channel moderators</span></span>

<span data-ttu-id="ab182-142">在 "**谁是审阅人**" 下，单击 "**管理**"，然后添加或删除团队成员为 "审阅者"。</span><span class="sxs-lookup"><span data-stu-id="ab182-142">Under **Who are the moderators?**, click **Manage**, and then add or remove team members as moderators.</span></span> <span data-ttu-id="ab182-143">团队所有者和审阅者可以添加和删除其他审阅人。</span><span class="sxs-lookup"><span data-stu-id="ab182-143">Team owners and moderators can add and remove other moderators.</span></span>  

### <a name="set-team-member-permissions"></a><span data-ttu-id="ab182-144">设置团队成员权限</span><span class="sxs-lookup"><span data-stu-id="ab182-144">Set team member permissions</span></span>

<span data-ttu-id="ab182-145">在 "**团队成员权限**" 下，选中要允许的活动旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="ab182-145">Under **Team member permissions**, select the check boxes next to the activities  you want to allow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ab182-146">相关主题</span><span class="sxs-lookup"><span data-stu-id="ab182-146">Related topics</span></span>

- [<span data-ttu-id="ab182-147">Teams 中的团队和频道概述</span><span class="sxs-lookup"><span data-stu-id="ab182-147">Overview of teams and channels in Teams</span></span>](teams-channels-overview.md)
