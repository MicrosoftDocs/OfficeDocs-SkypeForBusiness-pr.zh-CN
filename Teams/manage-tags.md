---
title: 管理 Microsoft 团队中的标记
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna, salu
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
description: 了解如何在 Microsoft 团队中管理组织中如何使用标记。
ms.openlocfilehash: 965de27b2671106bed4e5c877f26a7132bf61040
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940522"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="6bf09-103">管理 Microsoft 团队中的标记</span><span class="sxs-lookup"><span data-stu-id="6bf09-103">Manage tags in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="6bf09-104">本文中讨论的功能之一是 " **按班次标记**"，尚未发布。</span><span class="sxs-lookup"><span data-stu-id="6bf09-104">One of the features discussed in this article, **tagging by shift**, hasn't yet been released.</span></span> <span data-ttu-id="6bf09-105">已宣布，即将推出。</span><span class="sxs-lookup"><span data-stu-id="6bf09-105">It's been announced, and it's coming soon.</span></span><span data-ttu-id="6bf09-106">如果您是管理员，则可以在 ([Microsoft 365 管理中心](https://portal.office.com/adminportal/home) ") 中的" 邮件中心 "中看到此功能的发布时间。</span><span class="sxs-lookup"><span data-stu-id="6bf09-106"> If you're an admin, you can find out when this feature will be released in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span> <span data-ttu-id="6bf09-107">若要保持在即将到来的团队功能上，请查看 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)。</span><span class="sxs-lookup"><span data-stu-id="6bf09-107">To stay on top of upcoming Teams features, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).</span></span>

## <a name="overview"></a><span data-ttu-id="6bf09-108">概述</span><span class="sxs-lookup"><span data-stu-id="6bf09-108">Overview</span></span>

<span data-ttu-id="6bf09-109">Microsoft 团队中的标记使用户可以快速轻松地与团队中的一部分人员连接。</span><span class="sxs-lookup"><span data-stu-id="6bf09-109">Tags in Microsoft Teams let users quickly and easily connect with a subset of people on a team.</span></span> <span data-ttu-id="6bf09-110">你可以创建和分配自定义标记，以便根据属性（如角色、项目、技能或位置）对人员进行分类。</span><span class="sxs-lookup"><span data-stu-id="6bf09-110">You can create and assign custom tags to categorize people based on attributes, such as role, project, skill, or location.</span></span> <span data-ttu-id="6bf09-111">或者，可以根据其日程安排将标记自动分配给人员，并在 " [倒班" 应用](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) 中将信息移动 (即将推出) 。</span><span class="sxs-lookup"><span data-stu-id="6bf09-111">Or, tags can be automatically assigned to people based on their schedule and shift information in the [Shifts app](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) (coming soon).</span></span> <span data-ttu-id="6bf09-112">将标记添加到一个或多个团队成员后，可在频道发布中由团队中的任何人使用 @mentions 或开始与分配了该标记的人员进行对话。</span><span class="sxs-lookup"><span data-stu-id="6bf09-112">After a tag is added to one or multiple team members, it can be used in @mentions by anyone on the team in a channel post or to start a conversation with only those people who are assigned that tag.</span></span>

<span data-ttu-id="6bf09-113">正如前面所述，团队中有两种类型的标记。</span><span class="sxs-lookup"><span data-stu-id="6bf09-113">As mentioned earlier, there are two kinds of tags in Teams.</span></span>

- <span data-ttu-id="6bf09-114">**自定义标记**：团队所有者和团队成员 (如果为其启用了功能) 可以手动创建标签并将其分配给人员。</span><span class="sxs-lookup"><span data-stu-id="6bf09-114">**Custom tags**: Team owners and team members (if the feature is enabled for them) can manually create and assign tags to people.</span></span> <span data-ttu-id="6bf09-115">例如，"设计者" 或 "Radiologist" 标记将与团队中的用户组联系，而无需键入他们的姓名。</span><span class="sxs-lookup"><span data-stu-id="6bf09-115">For example, a "Designer" or "Radiologist" tag will reach those sets of people on a team without having to type their names.</span></span>
- <span data-ttu-id="6bf09-116">通过 " (即将推出") 中**的 "添加标签**"：使用此功能，将自动向人员分配与团队中的[倒班应用](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)中的计划和班次组名称相匹配的标记。</span><span class="sxs-lookup"><span data-stu-id="6bf09-116">**Tagging by shift** (coming soon): With this feature, people are automatically assigned tags that match their schedule and shift group name in the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) in Teams.</span></span> <span data-ttu-id="6bf09-117">例如，当在聊天或频道发布中使用标记时，"EngineerOnCall" 标记将达到安排的所有工程师的工作时间。</span><span class="sxs-lookup"><span data-stu-id="6bf09-117">For example, the "EngineerOnCall" tag reaches all engineers who are scheduled in Shifts to work at the time the tag is used in a chat or channel post.</span></span> <span data-ttu-id="6bf09-118">使用 "按 shift 进行标记"，当用户需要快速中继信息时，团队将不知道班次轮换人员的姓名。</span><span class="sxs-lookup"><span data-stu-id="6bf09-118">With tagging by shift, Teams takes the guesswork out of knowing the name of on-shift staff when users need to quickly relay information.</span></span> <span data-ttu-id="6bf09-119">通过 shift 进行标记还可以由主要劳动力管理系统（如 JDA、Kronos 和 AMiON）进行支持，方法是将其与团队中的倒班集成。</span><span class="sxs-lookup"><span data-stu-id="6bf09-119">Tagging by shift can also be backed by major workforce management systems like JDA, Kronos, and AMiON by integrating them with Shifts in Teams.</span></span> <span data-ttu-id="6bf09-120">若要了解有关如何设置此功能的详细信息，请参阅 [通过 Shift 设置标记](#set-up-tagging-by-shift-coming-soon)。</span><span class="sxs-lookup"><span data-stu-id="6bf09-120">To learn more about how to set up this feature, see [Set up tagging by shift](#set-up-tagging-by-shift-coming-soon).</span></span>

> [!NOTE]
> <span data-ttu-id="6bf09-121">专用频道尚不支持标记。</span><span class="sxs-lookup"><span data-stu-id="6bf09-121">Tags are not yet supported in private channels.</span></span> <span data-ttu-id="6bf09-122">在美国政府社区云 (GCC) 、GCC 高或国防 (DoD) 组织中尚不提供标记。</span><span class="sxs-lookup"><span data-stu-id="6bf09-122">Tags are not yet available in US Government Community Cloud (GCC), GCC High, or Department of Defense (DoD) organizations.</span></span>

## <a name="how-tags-work"></a><span data-ttu-id="6bf09-123">标记的工作方式</span><span class="sxs-lookup"><span data-stu-id="6bf09-123">How tags work</span></span>

<span data-ttu-id="6bf09-124">标记可手动添加或自动分配给特定团队中的人员。</span><span class="sxs-lookup"><span data-stu-id="6bf09-124">A tag can be manually added or automatically assigned to a person on a specific team.</span></span> <span data-ttu-id="6bf09-125">然后，可以在 "收件人" 行上的 " **收件人** " 行中使用它，或在团队的任何标准频道中的帖子中 @mentions 使用它。</span><span class="sxs-lookup"><span data-stu-id="6bf09-125">It can then be used in @mentions on the **To** line in a chat or in a post on any standard channel of the team.</span></span> <span data-ttu-id="6bf09-126">下面是如何在团队中使用标记的一些示例：</span><span class="sxs-lookup"><span data-stu-id="6bf09-126">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="6bf09-127">商店经理向频道发布公告以通知所有出纳。</span><span class="sxs-lookup"><span data-stu-id="6bf09-127">A store manager posts an announcement to a channel to notify all cashiers.</span></span>
- <span data-ttu-id="6bf09-128">医院管理员向频道中的所有 radiologists 发送一条消息。</span><span class="sxs-lookup"><span data-stu-id="6bf09-128">A hospital administrator sends a message to all radiologists in a channel.</span></span>
- <span data-ttu-id="6bf09-129">市场营销经理开始与所有设计人员进行群组聊天。</span><span class="sxs-lookup"><span data-stu-id="6bf09-129">A marketing manager starts a group chat with all designers.</span></span>
- <span data-ttu-id="6bf09-130">护士将一封邮件发送给所有待命电话 cardiologists。</span><span class="sxs-lookup"><span data-stu-id="6bf09-130">A nurse sends a message to all on-call cardiologists.</span></span> <span data-ttu-id="6bf09-131">（即将推出）</span><span class="sxs-lookup"><span data-stu-id="6bf09-131">(coming soon)</span></span>
- <span data-ttu-id="6bf09-132">系统工程师将公告发布到频道以通知所有现场活动工程师。</span><span class="sxs-lookup"><span data-stu-id="6bf09-132">A system engineer posts an announcement to a channel to notify all on-shift field engineers.</span></span> <span data-ttu-id="6bf09-133">（即将推出）</span><span class="sxs-lookup"><span data-stu-id="6bf09-133">(coming soon)</span></span>

<span data-ttu-id="6bf09-134">当标记在频道对话中 @mentioned 时，与该标记相关联的团队成员将收到通知，就像任何其他 @mention 一样。</span><span class="sxs-lookup"><span data-stu-id="6bf09-134">When a tag is @mentioned in a channel conversation, team members associated with the tag will get notified, just like any other @mention.</span></span>

## <a name="manage-custom-tags-for-your-organization"></a><span data-ttu-id="6bf09-135">管理你的组织的自定义标记</span><span class="sxs-lookup"><span data-stu-id="6bf09-135">Manage custom tags for your organization</span></span>

<span data-ttu-id="6bf09-136">作为管理员，你可以控制在 Microsoft 团队管理中心的组织内使用标记的方式。</span><span class="sxs-lookup"><span data-stu-id="6bf09-136">As an admin, you can control how tags are used across your organization in the Microsoft Teams admin center.</span></span>

![Microsoft 团队管理中心中的标记设置的屏幕截图](media/manage-tags-admin-settings.png)

<span data-ttu-id="6bf09-138">一个团队最多可以有100个标记，最多可以向100个团队成员分配一个标记，并且可以将最多25个标记分配给单个用户。</span><span class="sxs-lookup"><span data-stu-id="6bf09-138">A team can have up to 100 tags, up to 100 team members can be assigned to a tag, and up to 25 tags can be assigned to a single user.</span></span> 

### <a name="set-who-can-add-custom-tags"></a><span data-ttu-id="6bf09-139">设置可添加自定义标记的人员</span><span class="sxs-lookup"><span data-stu-id="6bf09-139">Set who can add custom tags</span></span>

<span data-ttu-id="6bf09-140">默认情况下，团队所有者可以添加自定义标记。</span><span class="sxs-lookup"><span data-stu-id="6bf09-140">By default, team owners can add custom tags.</span></span> <span data-ttu-id="6bf09-141">你可以更改此设置以允许团队所有者和团队成员创建、编辑、删除和管理标记，也可以关闭你的组织的标记。</span><span class="sxs-lookup"><span data-stu-id="6bf09-141">You can change this setting to allow team owners and team members to create, edit, delete, and manage tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="6bf09-142">在 Microsoft 团队管理中心的左侧导航中，单击 "**组织范围设置**"  >  **团队设置**。</span><span class="sxs-lookup"><span data-stu-id="6bf09-142">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="6bf09-143">在 **"标记"** 下的 "标记" 的 " **管理方式**" 下，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="6bf09-143">Under **Tagging**, next to **Tags are managed by**, select one of the following options:</span></span>

    - <span data-ttu-id="6bf09-144">**团队所有者和成员**：允许团队所有者和成员管理标记。</span><span class="sxs-lookup"><span data-stu-id="6bf09-144">**Team owners and members**: Allow team owners and members to manage tags.</span></span>
    - <span data-ttu-id="6bf09-145">**团队所有者**：允许团队所有者管理标记。</span><span class="sxs-lookup"><span data-stu-id="6bf09-145">**Team owners**: Allow team owners to manage tags.</span></span>
    - <span data-ttu-id="6bf09-146">**已禁用**：关闭标记。</span><span class="sxs-lookup"><span data-stu-id="6bf09-146">**Disabled**: Turn off tags.</span></span>

### <a name="configure-custom-tags-settings"></a><span data-ttu-id="6bf09-147">配置自定义标记设置</span><span class="sxs-lookup"><span data-stu-id="6bf09-147">Configure custom tags settings</span></span>

<span data-ttu-id="6bf09-148">你可以配置以下标记设置以控制如何在组织中使用自定义标记。</span><span class="sxs-lookup"><span data-stu-id="6bf09-148">You can configure the following tags settings to control how custom tags are used across your organization.</span></span>

1. <span data-ttu-id="6bf09-149">在 Microsoft 团队管理中心的左侧导航中，单击 "**组织范围设置**"  >  **团队设置**。</span><span class="sxs-lookup"><span data-stu-id="6bf09-149">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="6bf09-150">在 " **标记**" 下，根据组织的需要设置以下各项。</span><span class="sxs-lookup"><span data-stu-id="6bf09-150">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="6bf09-151">**让团队所有者覆盖可以管理标记的人员**：启用此设置后，团队所有者可以设置团队成员是否可以在团队内创建和管理标记，并且 **通过设置管理标记** 的值是每个团队的默认值。</span><span class="sxs-lookup"><span data-stu-id="6bf09-151">**Let team owners override who can manage tags**: When you turn on this setting, team owners can set whether team members can create and manage tags within a team and the value of the **Tags are managed by** setting is the default value for each team.</span></span> <span data-ttu-id="6bf09-152">如果关闭此设置，则通过无法更改每个团队的设置 **来管理标记** 。</span><span class="sxs-lookup"><span data-stu-id="6bf09-152">If you turn off this setting, the **Tags are managed by** setting can't be changed per team.</span></span>
    - <span data-ttu-id="6bf09-153">**建议的默认标记**：使用此项添加一组默认标记。</span><span class="sxs-lookup"><span data-stu-id="6bf09-153">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="6bf09-154">您最多可以添加25个标签，每个标签最多可以包含25个字符。</span><span class="sxs-lookup"><span data-stu-id="6bf09-154">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="6bf09-155">团队所有者和成员 (如果为其启用了该功能) 可以使用这些建议、添加到它们或创建新的标记集。</span><span class="sxs-lookup"><span data-stu-id="6bf09-155">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>
    - <span data-ttu-id="6bf09-156">**创建自定义标记**：启用此设置可让用户添加除了所设置的建议默认标记以外的其他标记。</span><span class="sxs-lookup"><span data-stu-id="6bf09-156">**Let custom tags be created**: Turn on this setting to let people add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="6bf09-157">如果关闭此功能，则用户只能使用建议的默认标记。</span><span class="sxs-lookup"><span data-stu-id="6bf09-157">If this is turned off, people can only use the suggested default tags.</span></span> <span data-ttu-id="6bf09-158">如果关闭此功能，请确保添加一个或多个默认标记。</span><span class="sxs-lookup"><span data-stu-id="6bf09-158">If you turn this off, make sure that you add one or more default tags.</span></span>

## <a name="manage-custom-tags-settings-for-a-team"></a><span data-ttu-id="6bf09-159">管理团队的自定义标记设置</span><span class="sxs-lookup"><span data-stu-id="6bf09-159">Manage custom tags settings for a team</span></span>

<span data-ttu-id="6bf09-160">如果你在 Microsoft 团队管理中心中启用了 " **让团队所有者覆盖哪些人可以管理标记** " 设置，团队所有者可以设置成员是否可以在团队级别添加标记。</span><span class="sxs-lookup"><span data-stu-id="6bf09-160">If you turned on the **Let team owners override who can manage tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="6bf09-161">若要执行此操作，请在团队的 " **设置** " 选项卡上，转到 " **标记**"，然后选择可以添加标记的人员。</span><span class="sxs-lookup"><span data-stu-id="6bf09-161">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![团队级别的标记设置的屏幕截图](media/manage-tags-team-settings.png)

## <a name="use-tags"></a><span data-ttu-id="6bf09-163">使用标记</span><span class="sxs-lookup"><span data-stu-id="6bf09-163">Use tags</span></span>

<span data-ttu-id="6bf09-164">下面介绍了如何添加自定义标记，以及如何在使用团队) 中的 "倒班" 应用时按 shift (设置标记。</span><span class="sxs-lookup"><span data-stu-id="6bf09-164">Here's how to add custom tags and how to set up tagging by shift (if you're using the Shifts app in Teams).</span></span> <span data-ttu-id="6bf09-165">若要了解详细信息，请参阅 [使用团队中的标记](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)。</span><span class="sxs-lookup"><span data-stu-id="6bf09-165">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

### <a name="create-and-assign-custom-tags"></a><span data-ttu-id="6bf09-166">创建和分配自定义标记</span><span class="sxs-lookup"><span data-stu-id="6bf09-166">Create and assign custom tags</span></span>

<span data-ttu-id="6bf09-167">若要创建和分配自定义标记，请选择应用左侧的 " **团队** "，然后在列表中找到您的团队。</span><span class="sxs-lookup"><span data-stu-id="6bf09-167">To create and assign custom tags, select **Teams** on the left side of the app, and then find your team in the list.</span></span> <span data-ttu-id="6bf09-168">选择 **̇̇̇更多选项**，然后选择 " **管理标记**"。</span><span class="sxs-lookup"><span data-stu-id="6bf09-168">Select **˙˙˙ More options**, and then choose **Manage tags**.</span></span> <span data-ttu-id="6bf09-169">在此处，你可以创建标记并将其分配给团队中的人员。</span><span class="sxs-lookup"><span data-stu-id="6bf09-169">Here, you can create tags and assign them to people on your team.</span></span>

![<span data-ttu-id="6bf09-170">如何在团队客户端应用标记的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="6bf09-170">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png)

<span data-ttu-id="6bf09-171">若要删除标记，请选择标记旁边的 **̇̇̇更多选项** ，然后选择 " **删除标记**"。</span><span class="sxs-lookup"><span data-stu-id="6bf09-171">To delete a tag, select **˙˙˙ More options** next to the tag, and then select **Delete tag**.</span></span>

### <a name="set-up-tagging-by-shift-coming-soon"></a><span data-ttu-id="6bf09-172">通过 (即将推出的班次) 设置标记</span><span class="sxs-lookup"><span data-stu-id="6bf09-172">Set up tagging by shift (coming soon)</span></span>

1. <span data-ttu-id="6bf09-173">在 "团队" 中，转到 " [移动" 应用](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)。</span><span class="sxs-lookup"><span data-stu-id="6bf09-173">In Teams, go to the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop).</span></span>
2. <span data-ttu-id="6bf09-174">创建 [shift 组](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) 并将其命名为一个属性（如角色）。</span><span class="sxs-lookup"><span data-stu-id="6bf09-174">Create [shift groups](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) and name them after an attribute such as a role.</span></span> <span data-ttu-id="6bf09-175">例如，EngineerOnCall。</span><span class="sxs-lookup"><span data-stu-id="6bf09-175">For example, EngineerOnCall.</span></span> <span data-ttu-id="6bf09-176">Shift 组名称将是该标记的名称。</span><span class="sxs-lookup"><span data-stu-id="6bf09-176">The shift group name will be the name of the tag.</span></span>
3. <span data-ttu-id="6bf09-177">通过向团队成员分配倒班来[填写日程](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea)。</span><span class="sxs-lookup"><span data-stu-id="6bf09-177">[Fill out a schedule](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) by assigning shifts to members of you teams.</span></span> <span data-ttu-id="6bf09-178">完成后，在 "移动" 应用的右上角，选择 " **与团队共享**"。</span><span class="sxs-lookup"><span data-stu-id="6bf09-178">When you're finished, in the upper-right corner of the Shifts app, select **Share with team**.</span></span>
4. <span data-ttu-id="6bf09-179">等待15分钟，安排的班次填充标记服务。</span><span class="sxs-lookup"><span data-stu-id="6bf09-179">Wait 15 minutes for the scheduled shifts to populate the tagging service.</span></span>
5. <span data-ttu-id="6bf09-180">在团队中使用标记的任意位置使用标记。</span><span class="sxs-lookup"><span data-stu-id="6bf09-180">Use the tag anywhere you use tags in Teams.</span></span>

<span data-ttu-id="6bf09-181">通过 shift 进行标记使你的用户能够实时联系到人员进行中的班次。</span><span class="sxs-lookup"><span data-stu-id="6bf09-181">Tagging by shift allows your users to reach the people on-shift in real time.</span></span> <span data-ttu-id="6bf09-182">通知仅发送给在使用标记开始聊天或频道发布时具有班次的人员。</span><span class="sxs-lookup"><span data-stu-id="6bf09-182">Notifications are sent only to those people who are on shift at the time a tag is used to start a chat or in a channel post.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6bf09-183">相关主题</span><span class="sxs-lookup"><span data-stu-id="6bf09-183">Related topics</span></span>

[<span data-ttu-id="6bf09-184">使用团队中的标记</span><span class="sxs-lookup"><span data-stu-id="6bf09-184">Using tags in Teams</span></span>](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[<span data-ttu-id="6bf09-185">在 Teams 中为组织管理排班应用</span><span class="sxs-lookup"><span data-stu-id="6bf09-185">Manage the Shifts app for your organization in Teams</span></span>](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[<span data-ttu-id="6bf09-186">班次帮助文档</span><span class="sxs-lookup"><span data-stu-id="6bf09-186">Shifts Help documentation</span></span>](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
