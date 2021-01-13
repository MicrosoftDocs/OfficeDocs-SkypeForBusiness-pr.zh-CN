---
title: 在 Microsoft Teams 中管理标记
author: cichur
ms.author: v-cichur
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
description: 了解如何在 Microsoft Teams 中管理标记在组织的使用方式。
ms.openlocfilehash: 9d9ba4584572ad1e1707c250ee92c49e9aaec7fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831232"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="d23dd-103">在 Microsoft Teams 中管理标记</span><span class="sxs-lookup"><span data-stu-id="d23dd-103">Manage tags in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="d23dd-104">本文讨论的功能之一（按 **Shift** 标记）尚未发布。</span><span class="sxs-lookup"><span data-stu-id="d23dd-104">One of the features discussed in this article, **tagging by shift**, hasn't yet been released.</span></span> <span data-ttu-id="d23dd-105">已宣布推出，即将推出。</span><span class="sxs-lookup"><span data-stu-id="d23dd-105">It's been announced, and it's coming soon.</span></span> <span data-ttu-id="d23dd-106">如果你是管理员，你可以了解何时将在 [Microsoft 365](https://portal.office.com/adminportal/home) 管理中心的消息中心 (中发布此功能) 。</span><span class="sxs-lookup"><span data-stu-id="d23dd-106">If you're an admin, you can find out when this feature will be released in the Message Center (in the [Microsoft 365 admin center](https://portal.office.com/adminportal/home)).</span></span> <span data-ttu-id="d23dd-107">若要随时了解即将推出的 Teams 功能，请查看 [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)。</span><span class="sxs-lookup"><span data-stu-id="d23dd-107">To stay on top of upcoming Teams features, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).</span></span>

## <a name="overview"></a><span data-ttu-id="d23dd-108">概述</span><span class="sxs-lookup"><span data-stu-id="d23dd-108">Overview</span></span>

<span data-ttu-id="d23dd-109">Microsoft Teams 中的标记允许用户快速轻松地与团队中的一部分人员联系。</span><span class="sxs-lookup"><span data-stu-id="d23dd-109">Tags in Microsoft Teams let users quickly and easily connect with a subset of people on a team.</span></span> <span data-ttu-id="d23dd-110">可以创建和分配自定义标记，以便根据属性（例如角色、项目、技能或位置）对人员进行分类。</span><span class="sxs-lookup"><span data-stu-id="d23dd-110">You can create and assign custom tags to categorize people based on attributes, such as role, project, skill, or location.</span></span> <span data-ttu-id="d23dd-111">或者，标记可以基于其日程安排自动分配给人员，并且 [Shifts](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) 应用中的班次信息 (即将推出) 。</span><span class="sxs-lookup"><span data-stu-id="d23dd-111">Or, tags can be automatically assigned to people based on their schedule and shift information in the [Shifts app](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) (coming soon).</span></span> <span data-ttu-id="d23dd-112">将标记添加到一个或多个团队成员后，团队中的任何人都可以在 @mentions 中通过频道帖子使用标记，或仅与分配了该标记的人开始对话。</span><span class="sxs-lookup"><span data-stu-id="d23dd-112">After a tag is added to one or multiple team members, it can be used in @mentions by anyone on the team in a channel post or to start a conversation with only those people who are assigned that tag.</span></span>

<span data-ttu-id="d23dd-113">如前所述，Teams 中有两种类型的标记。</span><span class="sxs-lookup"><span data-stu-id="d23dd-113">As mentioned earlier, there are two kinds of tags in Teams.</span></span>

- <span data-ttu-id="d23dd-114">**自定义标记**：团队所有者和 (如果为其启用了该功能，) 手动创建标记并将其分配给人员。</span><span class="sxs-lookup"><span data-stu-id="d23dd-114">**Custom tags**: Team owners and team members (if the feature is enabled for them) can manually create and assign tags to people.</span></span> <span data-ttu-id="d23dd-115">例如，"Designer"或"Radi一"标记将到达团队中的这些人员集，而无需键入其姓名。</span><span class="sxs-lookup"><span data-stu-id="d23dd-115">For example, a "Designer" or "Radiologist" tag will reach those sets of people on a team without having to type their names.</span></span>
- <span data-ttu-id="d23dd-116">**即将推出"** 按排班 (标记) ：借助此功能，系统会自动为用户分配与 Teams 中的 Shifts 应用中的日程安排和 [排班组](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) 名称匹配的标记。</span><span class="sxs-lookup"><span data-stu-id="d23dd-116">**Tagging by shift** (coming soon): With this feature, people are automatically assigned tags that match their schedule and shift group name in the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) in Teams.</span></span> <span data-ttu-id="d23dd-117">例如，在聊天或频道帖子使用标记时，"EngineerOnCall"标记将到达在 Shifts 中计划工作的所有工程师。</span><span class="sxs-lookup"><span data-stu-id="d23dd-117">For example, the "EngineerOnCall" tag reaches all engineers who are scheduled in Shifts to work at the time the tag is used in a chat or channel post.</span></span> <span data-ttu-id="d23dd-118">使用按轮班标记时，当用户需要快速中继信息时，Teams 无需知道轮班员工的姓名，因此无需猜测。</span><span class="sxs-lookup"><span data-stu-id="d23dd-118">With tagging by shift, Teams takes the guesswork out of knowing the name of on-shift staff when users need to quickly relay information.</span></span> <span data-ttu-id="d23dd-119">通过将主要员工管理系统（如 JDA、Kronos 和 AMiON）与 Teams 中的 Shifts 集成，也可以支持按班次进行标记。</span><span class="sxs-lookup"><span data-stu-id="d23dd-119">Tagging by shift can also be backed by major workforce management systems like JDA, Kronos, and AMiON by integrating them with Shifts in Teams.</span></span> <span data-ttu-id="d23dd-120">若要详细了解如何设置此功能，请参阅"按 Shift[设置标记"。](#set-up-tagging-by-shift-coming-soon)</span><span class="sxs-lookup"><span data-stu-id="d23dd-120">To learn more about how to set up this feature, see [Set up tagging by shift](#set-up-tagging-by-shift-coming-soon).</span></span>

> [!NOTE]
> <span data-ttu-id="d23dd-121">专用通道尚不支持标记。</span><span class="sxs-lookup"><span data-stu-id="d23dd-121">Tags are not yet supported in private channels.</span></span> <span data-ttu-id="d23dd-122">标记尚未在美国政府社区云 (GCC) 、GCC High 或国防部 (DoD) 提供。</span><span class="sxs-lookup"><span data-stu-id="d23dd-122">Tags are not yet available in US Government Community Cloud (GCC), GCC High, or Department of Defense (DoD) organizations.</span></span> 

## <a name="how-tags-work"></a><span data-ttu-id="d23dd-123">标记如何工作</span><span class="sxs-lookup"><span data-stu-id="d23dd-123">How tags work</span></span>

<span data-ttu-id="d23dd-124">可以手动添加标记或自动将标记分配给特定团队中的人员。</span><span class="sxs-lookup"><span data-stu-id="d23dd-124">A tag can be manually added or automatically assigned to a person on a specific team.</span></span> <span data-ttu-id="d23dd-125">然后，它可以在聊天@mentions的"至"行上或在团队的任何标准频道上的帖子中使用。</span><span class="sxs-lookup"><span data-stu-id="d23dd-125">It can then be used in @mentions on the **To** line in a chat or in a post on any standard channel of the team.</span></span> <span data-ttu-id="d23dd-126">下面是在 Teams 中如何使用标记的一些示例：</span><span class="sxs-lookup"><span data-stu-id="d23dd-126">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="d23dd-127">商店经理向频道发布通知以通知所有收银员。</span><span class="sxs-lookup"><span data-stu-id="d23dd-127">A store manager posts an announcement to a channel to notify all cashiers.</span></span>
- <span data-ttu-id="d23dd-128">医院管理员向频道的所有辐射人员发送消息。</span><span class="sxs-lookup"><span data-stu-id="d23dd-128">A hospital administrator sends a message to all radiologists in a channel.</span></span>
- <span data-ttu-id="d23dd-129">营销经理开始与所有设计人员进行群组聊天。</span><span class="sxs-lookup"><span data-stu-id="d23dd-129">A marketing manager starts a group chat with all designers.</span></span>
- <span data-ttu-id="d23dd-130">一名医生向所有通话医生发送消息。</span><span class="sxs-lookup"><span data-stu-id="d23dd-130">A nurse sends a message to all on-call cardiologists.</span></span> <span data-ttu-id="d23dd-131">（即将推出）</span><span class="sxs-lookup"><span data-stu-id="d23dd-131">(coming soon)</span></span>
- <span data-ttu-id="d23dd-132">系统工程师向频道发布公告，通知所有轮班现场工程师。</span><span class="sxs-lookup"><span data-stu-id="d23dd-132">A system engineer posts an announcement to a channel to notify all on-shift field engineers.</span></span> <span data-ttu-id="d23dd-133">（即将推出）</span><span class="sxs-lookup"><span data-stu-id="d23dd-133">(coming soon)</span></span>

<span data-ttu-id="d23dd-134">当标记在@mentioned对话中时，与标记关联的团队成员将收到通知，就像任何其他@mention。</span><span class="sxs-lookup"><span data-stu-id="d23dd-134">When a tag is @mentioned in a channel conversation, team members associated with the tag will get notified, just like any other @mention.</span></span>

## <a name="manage-custom-tags-for-your-organization"></a><span data-ttu-id="d23dd-135">管理组织的自定义标记</span><span class="sxs-lookup"><span data-stu-id="d23dd-135">Manage custom tags for your organization</span></span>

<span data-ttu-id="d23dd-136">作为管理员，可以在 Microsoft Teams 管理中心控制整个组织的标记使用方式。</span><span class="sxs-lookup"><span data-stu-id="d23dd-136">As an admin, you can control how tags are used across your organization in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d23dd-137">目前，无法通过 PowerShell 管理标记。</span><span class="sxs-lookup"><span data-stu-id="d23dd-137">Currently, you can't use PowerShell to manage tags.</span></span>

![Microsoft Teams 管理中心中标记设置的屏幕截图](media/manage-tags-admin-settings.png)

<span data-ttu-id="d23dd-139">一个团队可以有多达 100 个标记，最多 100 个团队成员可以分配到一个标记，最多 25 个标记可以分配给单个用户。</span><span class="sxs-lookup"><span data-stu-id="d23dd-139">A team can have up to 100 tags, up to 100 team members can be assigned to a tag, and up to 25 tags can be assigned to a single user.</span></span> 

### <a name="set-who-can-add-custom-tags"></a><span data-ttu-id="d23dd-140">设置谁可以添加自定义标记</span><span class="sxs-lookup"><span data-stu-id="d23dd-140">Set who can add custom tags</span></span>

<span data-ttu-id="d23dd-141">默认情况下，团队所有者可以添加自定义标记。</span><span class="sxs-lookup"><span data-stu-id="d23dd-141">By default, team owners can add custom tags.</span></span> <span data-ttu-id="d23dd-142">您可以更改此设置以允许团队所有者和团队成员创建、编辑、删除和管理标记，也可以关闭组织的标记。</span><span class="sxs-lookup"><span data-stu-id="d23dd-142">You can change this setting to allow team owners and team members to create, edit, delete, and manage tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="d23dd-143">在 Microsoft Teams 管理中心的左侧导航栏中，单击 **"组织范围的** 设置  >  **Teams 设置"。**</span><span class="sxs-lookup"><span data-stu-id="d23dd-143">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="d23dd-144">在 **"标记**" **下，选择** 以下选项之一，管理"标记"旁的标记：</span><span class="sxs-lookup"><span data-stu-id="d23dd-144">Under **Tagging**, next to **Tags are managed by**, select one of the following options:</span></span>

    - <span data-ttu-id="d23dd-145">**团队所有者和成员**：允许团队所有者和成员管理标记。</span><span class="sxs-lookup"><span data-stu-id="d23dd-145">**Team owners and members**: Allow team owners and members to manage tags.</span></span>
    - <span data-ttu-id="d23dd-146">**团队所有者**：允许团队所有者管理标记。</span><span class="sxs-lookup"><span data-stu-id="d23dd-146">**Team owners**: Allow team owners to manage tags.</span></span>
    - <span data-ttu-id="d23dd-147">**已禁用**：关闭标记。</span><span class="sxs-lookup"><span data-stu-id="d23dd-147">**Disabled**: Turn off tags.</span></span>

### <a name="configure-custom-tags-settings"></a><span data-ttu-id="d23dd-148">配置自定义标记设置</span><span class="sxs-lookup"><span data-stu-id="d23dd-148">Configure custom tags settings</span></span>

<span data-ttu-id="d23dd-149">可以配置以下标记设置来控制如何在组织中使用自定义标记。</span><span class="sxs-lookup"><span data-stu-id="d23dd-149">You can configure the following tags settings to control how custom tags are used across your organization.</span></span>

1. <span data-ttu-id="d23dd-150">在 Microsoft Teams 管理中心的左侧导航栏中，单击 **"组织范围的** 设置  >  **Teams 设置"。**</span><span class="sxs-lookup"><span data-stu-id="d23dd-150">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="d23dd-151">在 **"标记**"下，根据组织的需求设置以下各项。</span><span class="sxs-lookup"><span data-stu-id="d23dd-151">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="d23dd-152">让团队所有者替代谁可以管理标记：启用此设置时，团队所有者可以设置团队成员是否可以在团队内创建和管理标记，而"标记"的值通过设置为每个团队的默认值进行管理。</span><span class="sxs-lookup"><span data-stu-id="d23dd-152">**Let team owners override who can manage tags**: When you turn on this setting, team owners can set whether team members can create and manage tags within a team and the value of the **Tags are managed by** setting is the default value for each team.</span></span> <span data-ttu-id="d23dd-153">如果关闭此设置，则不能按团队 **通过设置** 管理标记。</span><span class="sxs-lookup"><span data-stu-id="d23dd-153">If you turn off this setting, the **Tags are managed by** setting can't be changed per team.</span></span>
    - <span data-ttu-id="d23dd-154">**建议的默认标记**：用于添加一组默认标记。</span><span class="sxs-lookup"><span data-stu-id="d23dd-154">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="d23dd-155">最多可以添加 25 个标记，每个标记最多可以包含 25 个字符。</span><span class="sxs-lookup"><span data-stu-id="d23dd-155">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="d23dd-156">如果为 (启用该功能，团队所有者和成员) 可以使用这些建议、将其添加到建议或创建一组新的标记。</span><span class="sxs-lookup"><span data-stu-id="d23dd-156">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>
    - <span data-ttu-id="d23dd-157">**允许创建自定义标记**：启用此设置，以允许用户添加您设置的建议默认标记外的其他标记。</span><span class="sxs-lookup"><span data-stu-id="d23dd-157">**Let custom tags be created**: Turn on this setting to let people add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="d23dd-158">如果此选项已关闭，则用户只能使用建议的默认标记。</span><span class="sxs-lookup"><span data-stu-id="d23dd-158">If this is turned off, people can only use the suggested default tags.</span></span> <span data-ttu-id="d23dd-159">如果将其关闭，请确保添加一个或多个默认标记。</span><span class="sxs-lookup"><span data-stu-id="d23dd-159">If you turn this off, make sure that you add one or more default tags.</span></span>

## <a name="manage-custom-tags-settings-for-a-team"></a><span data-ttu-id="d23dd-160">管理团队的自定义标记设置</span><span class="sxs-lookup"><span data-stu-id="d23dd-160">Manage custom tags settings for a team</span></span>

<span data-ttu-id="d23dd-161">如果启用"允许团队所有者 **替代谁可以** 管理 Microsoft Teams 管理中心中的标记设置"，团队所有者可以设置成员是否可以在团队级别添加标记。</span><span class="sxs-lookup"><span data-stu-id="d23dd-161">If you turned on the **Let team owners override who can manage tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="d23dd-162">为此，在团队的"设置"选项卡上，转到"标记"，然后选择可以添加标记的人。</span><span class="sxs-lookup"><span data-stu-id="d23dd-162">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![团队级别的标记设置的屏幕截图](media/manage-tags-team-settings.png)

## <a name="use-tags"></a><span data-ttu-id="d23dd-164">使用标记</span><span class="sxs-lookup"><span data-stu-id="d23dd-164">Use tags</span></span>

<span data-ttu-id="d23dd-165">下面将了解如何添加自定义标记，以及如何在 Teams (中的 Shifts 应用时通过 shift) 设置标记。</span><span class="sxs-lookup"><span data-stu-id="d23dd-165">Here's how to add custom tags and how to set up tagging by shift (if you're using the Shifts app in Teams).</span></span> <span data-ttu-id="d23dd-166">若要了解有关详细信息，请查看"使用[Teams 中的标记"。](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)</span><span class="sxs-lookup"><span data-stu-id="d23dd-166">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

### <a name="create-and-assign-custom-tags"></a><span data-ttu-id="d23dd-167">创建和分配自定义标记</span><span class="sxs-lookup"><span data-stu-id="d23dd-167">Create and assign custom tags</span></span>

<span data-ttu-id="d23dd-168">若要创建和分配自定义标记，请选择应用左侧的 **Teams，** 然后在列表中查找你的团队。</span><span class="sxs-lookup"><span data-stu-id="d23dd-168">To create and assign custom tags, select **Teams** on the left side of the app, and then find your team in the list.</span></span> <span data-ttu-id="d23dd-169">选择 **" 更多选项**，然后选择"**管理标记"。**</span><span class="sxs-lookup"><span data-stu-id="d23dd-169">Select **˙˙˙ More options**, and then choose **Manage tags**.</span></span> <span data-ttu-id="d23dd-170">在这里，你可以创建标记并将其分配给团队中的人员。</span><span class="sxs-lookup"><span data-stu-id="d23dd-170">Here, you can create tags and assign them to people on your team.</span></span>

![<span data-ttu-id="d23dd-171">如何在 Teams 客户端中应用标记的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="d23dd-171">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png)

<span data-ttu-id="d23dd-172">若要删除标记，请选择 **该标记旁边的 10** 个"更多"选项，然后选择"**删除标记"。**</span><span class="sxs-lookup"><span data-stu-id="d23dd-172">To delete a tag, select **˙˙˙ More options** next to the tag, and then select **Delete tag**.</span></span>

### <a name="set-up-tagging-by-shift-coming-soon"></a><span data-ttu-id="d23dd-173">通过 shift 和即将 (设置标记) </span><span class="sxs-lookup"><span data-stu-id="d23dd-173">Set up tagging by shift (coming soon)</span></span>

1. <span data-ttu-id="d23dd-174">在 Teams 中，转到 [Shifts 应用](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)。</span><span class="sxs-lookup"><span data-stu-id="d23dd-174">In Teams, go to the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop).</span></span>
2. <span data-ttu-id="d23dd-175">创建 [班次组](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) ，并基于角色等属性命名。</span><span class="sxs-lookup"><span data-stu-id="d23dd-175">Create [shift groups](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) and name them after an attribute such as a role.</span></span> <span data-ttu-id="d23dd-176">例如，EngineerOnCall。</span><span class="sxs-lookup"><span data-stu-id="d23dd-176">For example, EngineerOnCall.</span></span> <span data-ttu-id="d23dd-177">班次组名称将是标记的名称。</span><span class="sxs-lookup"><span data-stu-id="d23dd-177">The shift group name will be the name of the tag.</span></span>
3. <span data-ttu-id="d23dd-178">[通过向团队成员](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) 分配班次来填写日程安排。</span><span class="sxs-lookup"><span data-stu-id="d23dd-178">[Fill out a schedule](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) by assigning shifts to members of you teams.</span></span> <span data-ttu-id="d23dd-179">完成后，在 Shifts 应用的右上角，选择"与 **团队共享"。**</span><span class="sxs-lookup"><span data-stu-id="d23dd-179">When you're finished, in the upper-right corner of the Shifts app, select **Share with team**.</span></span>
4. <span data-ttu-id="d23dd-180">等待 15 分钟，让计划的排班填充标记服务。</span><span class="sxs-lookup"><span data-stu-id="d23dd-180">Wait 15 minutes for the scheduled shifts to populate the tagging service.</span></span>
5. <span data-ttu-id="d23dd-181">在 Teams 中你使用标记的任何位置使用标记。</span><span class="sxs-lookup"><span data-stu-id="d23dd-181">Use the tag anywhere you use tags in Teams.</span></span>

<span data-ttu-id="d23dd-182">按 Shift 标记可让用户实时联系轮班人员。</span><span class="sxs-lookup"><span data-stu-id="d23dd-182">Tagging by shift allows your users to reach the people on-shift in real time.</span></span> <span data-ttu-id="d23dd-183">通知仅发送给使用标记开始聊天或频道帖子时轮班的人。</span><span class="sxs-lookup"><span data-stu-id="d23dd-183">Notifications are sent only to those people who are on shift at the time a tag is used to start a chat or in a channel post.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d23dd-184">相关主题</span><span class="sxs-lookup"><span data-stu-id="d23dd-184">Related topics</span></span>

[<span data-ttu-id="d23dd-185">在 Teams 中使用标记</span><span class="sxs-lookup"><span data-stu-id="d23dd-185">Using tags in Teams</span></span>](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[<span data-ttu-id="d23dd-186">在 Teams 中为组织管理排班应用</span><span class="sxs-lookup"><span data-stu-id="d23dd-186">Manage the Shifts app for your organization in Teams</span></span>](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[<span data-ttu-id="d23dd-187">Shifts 帮助文档</span><span class="sxs-lookup"><span data-stu-id="d23dd-187">Shifts Help documentation</span></span>](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
