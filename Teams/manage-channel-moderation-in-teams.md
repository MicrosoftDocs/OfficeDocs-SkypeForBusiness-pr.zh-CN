---
title: 设置和管理频道审核
author: cichur
ms.author: v-cichur
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
description: 了解如何在 Microsoft Teams 中设置审核频道，包括如何将团队成员添加为频道审阅人。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 81e5159cf0e64a4c5b88afea51de528c299daf80
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948638"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a><span data-ttu-id="b0777-103">在 Microsoft Teams 中设置和管理频道审核</span><span class="sxs-lookup"><span data-stu-id="b0777-103">Set up and manage channel moderation in Microsoft Teams</span></span>

<span data-ttu-id="b0777-104">在 Microsoft Teams 中，团队所有者可以启用标准频道的审核，以控制谁可以启动新帖子和回复该频道中的帖子。</span><span class="sxs-lookup"><span data-stu-id="b0777-104">In Microsoft Teams, team owners can turn on moderation for a standard channel to control who can start new posts and reply to posts in that channel.</span></span>

<span data-ttu-id="b0777-105">团队所有者还可以将团队成员添加为审阅人。</span><span class="sxs-lookup"><span data-stu-id="b0777-105">Team owners can also add team members as moderators.</span></span> <span data-ttu-id="b0777-106">团队所有者可能没有频道级别的主题专业知识，无法最好地支持频道审核。</span><span class="sxs-lookup"><span data-stu-id="b0777-106">A team owner might not have the subject matter expertise at the channel level to best support channel moderation.</span></span> <span data-ttu-id="b0777-107">通过允许特定团队成员审查频道，团队所有者和频道审查者可以分担管理频道中内容和上下文的责任。</span><span class="sxs-lookup"><span data-stu-id="b0777-107">By allowing specific team members to moderate a channel, the responsibility of managing content and context within a channel is shared between team owners and channel moderators.</span></span> <span data-ttu-id="b0777-108">例如，团队所有者可以将业务所有者或内容所有者添加为审阅人，这样他们就可以控制该频道中的信息共享。</span><span class="sxs-lookup"><span data-stu-id="b0777-108">For example, a team owner can add business owners or content owners as moderators, which lets them control information sharing in that channel.</span></span>

> [!NOTE]
> <span data-ttu-id="b0777-109">频道审核适用于标准通道。</span><span class="sxs-lookup"><span data-stu-id="b0777-109">Channel moderation is available for standard channels.</span></span> <span data-ttu-id="b0777-110">不适用于常规频道或专用频道。</span><span class="sxs-lookup"><span data-stu-id="b0777-110">It's not available for the General channel or private channels.</span></span>

## <a name="what-can-a-channel-moderator-do"></a><span data-ttu-id="b0777-111">频道审查器可以执行哪些功能？</span><span class="sxs-lookup"><span data-stu-id="b0777-111">What can a channel moderator do?</span></span>

<span data-ttu-id="b0777-112">频道审查器可以：</span><span class="sxs-lookup"><span data-stu-id="b0777-112">Channel moderators can:</span></span>

- <span data-ttu-id="b0777-113">在频道中开始新文章。</span><span class="sxs-lookup"><span data-stu-id="b0777-113">Start new posts in the channel.</span></span> <span data-ttu-id="b0777-114">当为频道启用审核时，只有审阅人可以在该频道中启动新帖子。</span><span class="sxs-lookup"><span data-stu-id="b0777-114">When moderation is turned on for a channel, only moderators can start new posts in that channel.</span></span>
- <span data-ttu-id="b0777-115">在频道中添加和删除作为审阅人的团队成员。</span><span class="sxs-lookup"><span data-stu-id="b0777-115">Add and remove team members as moderators to a channel.</span></span> <span data-ttu-id="b0777-116">请记住，默认情况下，团队所有者是频道审查器，不能删除。</span><span class="sxs-lookup"><span data-stu-id="b0777-116">Keep in mind that by default, team owners are channel moderators and can't be removed.</span></span>
- <span data-ttu-id="b0777-117">控制团队成员是否可以回复现有通道消息，以及机器人和连接器是否可以提交通道消息。</span><span class="sxs-lookup"><span data-stu-id="b0777-117">Control whether team members can reply to existing channel messages and whether bots and connectors can submit channel messages.</span></span>

## <a name="scenarios"></a><span data-ttu-id="b0777-118">方案</span><span class="sxs-lookup"><span data-stu-id="b0777-118">Scenarios</span></span>

<span data-ttu-id="b0777-119">下面是组织如何在 Teams 中使用频道审核的一些示例。</span><span class="sxs-lookup"><span data-stu-id="b0777-119">Here's some examples of how your organization can use channel moderation in Teams.</span></span>

### <a name="use-a-channel-as-an-announcement-channel"></a><span data-ttu-id="b0777-120">使用频道作为公告频道</span><span class="sxs-lookup"><span data-stu-id="b0777-120">Use a channel as an announcement channel</span></span>

<span data-ttu-id="b0777-121">营销团队使用特定渠道共享关键项目公告和可交付结果。</span><span class="sxs-lookup"><span data-stu-id="b0777-121">The Marketing team uses a specific channel to share key project announcements and deliverables.</span></span> <span data-ttu-id="b0777-122">有时，工作组成员将内容发布给其他频道中更合适的内容。</span><span class="sxs-lookup"><span data-stu-id="b0777-122">Sometimes team members post content to the channel that more appropriately belongs in other channels.</span></span> <span data-ttu-id="b0777-123">团队所有者希望将频道中的信息共享限制为仅发布公告，以便团队成员可以使用该频道随时了解重要内容。</span><span class="sxs-lookup"><span data-stu-id="b0777-123">The team owner wants to restrict information sharing in the channel to only announcements so that team members can use that channel to stay on top of what's important.</span></span>

<span data-ttu-id="b0777-124">在此方案中，团队所有者将市场营销潜在顾客添加为审阅人，以便他们可以在频道中发布公告，并关闭团队成员回复该频道中的消息的能力。</span><span class="sxs-lookup"><span data-stu-id="b0777-124">In this scenario, the team owner adds Marketing leads as moderators so they can post announcements in the channel and turns off the ability for team members to reply to messages in that channel.</span></span>

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a><span data-ttu-id="b0777-125">在 Teams for Education 中使用频道进行课堂讨论</span><span class="sxs-lookup"><span data-stu-id="b0777-125">Use a channel for class discussions in Teams for Education</span></span>

<span data-ttu-id="b0777-126">在 Teams 教育中，科学教师希望使用频道让学生参与有关特定课堂主题的重点讨论。</span><span class="sxs-lookup"><span data-stu-id="b0777-126">In Teams for Education, a science teacher wants to use a channel to engage students in focused discussions on specific classroom topics.</span></span>

<span data-ttu-id="b0777-127">在此方案中，教师允许其教学助手主持频道。</span><span class="sxs-lookup"><span data-stu-id="b0777-127">In this scenario, the teacher allows their teaching assistants to moderate the channel.</span></span> <span data-ttu-id="b0777-128">然后，教学助理可以创建新文章来发起和推动与学生的讨论。</span><span class="sxs-lookup"><span data-stu-id="b0777-128">The teaching assistants can then create new posts to initiate and drive discussions with students.</span></span>

## <a name="manage-channel-moderation"></a><span data-ttu-id="b0777-129">管理频道审核</span><span class="sxs-lookup"><span data-stu-id="b0777-129">Manage channel moderation</span></span>

<span data-ttu-id="b0777-130">在 Teams 中，转到频道，单击"**更多选项..."**  > **管理频道**。</span><span class="sxs-lookup"><span data-stu-id="b0777-130">In Teams, go to the channel, click **More options ...** > **Manage channel**.</span></span> <span data-ttu-id="b0777-131">在这里，可以启用和关闭审查、将团队成员添加为审阅人，以及设置首选项。</span><span class="sxs-lookup"><span data-stu-id="b0777-131">From here you can turn on and turn off moderation, add team members as moderators, and set preferences.</span></span>

<span data-ttu-id="b0777-132">通道审核是按通道设置。</span><span class="sxs-lookup"><span data-stu-id="b0777-132">Channel moderation is a per-channel setting.</span></span> <span data-ttu-id="b0777-133">没有用于通道审核的租户级设置。</span><span class="sxs-lookup"><span data-stu-id="b0777-133">There's no tenant-level setting for channel moderation.</span></span> <span data-ttu-id="b0777-134">如果希望我们添加租户级频道审核设置，请通过 [Teams UserVoice 请求](https://microsoftteams.uservoice.com/)。</span><span class="sxs-lookup"><span data-stu-id="b0777-134">If you'd like us to add a tenant-level channel moderation setting, request it on [Teams UserVoice](https://microsoftteams.uservoice.com/).</span></span>

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

![管理频道-审核-团队中的首选项](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a><span data-ttu-id="b0777-136">打开或关闭频道审核</span><span class="sxs-lookup"><span data-stu-id="b0777-136">Turn on or turn off moderation for a channel</span></span>

<span data-ttu-id="b0777-137">默认情况下，审核已关闭，这意味着通常的频道设置适用于团队所有者和团队成员。</span><span class="sxs-lookup"><span data-stu-id="b0777-137">By default, moderation is off, which means that the usual channel settings apply to team owners and team members.</span></span> <span data-ttu-id="b0777-138">例如，您可以将新帖子限制为仅团队成员，或允许每个人（包括来宾）启动新文章。</span><span class="sxs-lookup"><span data-stu-id="b0777-138">For example, you can restrict new posts to only team members or allow everyone, including guests, to start new posts.</span></span>

<span data-ttu-id="b0777-139">若要为频道启用审核，请在"频道审查"**下，单击**"**打开"。**</span><span class="sxs-lookup"><span data-stu-id="b0777-139">To turn on moderation for a channel, under **Channel moderation**, click **On**.</span></span> <span data-ttu-id="b0777-140">当频道审查打开时，只有审阅人可以启动新文章。</span><span class="sxs-lookup"><span data-stu-id="b0777-140">When channel moderation is on, only moderators can start new posts.</span></span> 

### <a name="add-or-remove-channel-moderators"></a><span data-ttu-id="b0777-141">添加或删除频道审查器</span><span class="sxs-lookup"><span data-stu-id="b0777-141">Add or remove channel moderators</span></span>

<span data-ttu-id="b0777-142">在 **"审阅人是谁？"** 下，单击" **管理**"，然后添加或删除团队成员作为审阅人。</span><span class="sxs-lookup"><span data-stu-id="b0777-142">Under **Who are the moderators?**, click **Manage**, and then add or remove team members as moderators.</span></span> <span data-ttu-id="b0777-143">团队所有者和审阅人可以添加和删除其他审阅人。</span><span class="sxs-lookup"><span data-stu-id="b0777-143">Team owners and moderators can add and remove other moderators.</span></span>  

### <a name="set-team-member-permissions"></a><span data-ttu-id="b0777-144">设置团队成员权限</span><span class="sxs-lookup"><span data-stu-id="b0777-144">Set team member permissions</span></span>

<span data-ttu-id="b0777-145">在 **"团队成员权限**"下，选中要允许的活动旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="b0777-145">Under **Team member permissions**, select the check boxes next to the activities  you want to allow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b0777-146">相关主题</span><span class="sxs-lookup"><span data-stu-id="b0777-146">Related topics</span></span>

- [<span data-ttu-id="b0777-147">Teams 中的团队和频道概述</span><span class="sxs-lookup"><span data-stu-id="b0777-147">Overview of teams and channels in Teams</span></span>](teams-channels-overview.md)
