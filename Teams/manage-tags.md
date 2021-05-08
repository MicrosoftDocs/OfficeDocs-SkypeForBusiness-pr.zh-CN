---
title: 管理 Microsoft Teams 中的标记
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
description: 了解如何在组织内管理标记在 Microsoft Teams。
ms.openlocfilehash: c63817f5b3ee9c736311982b54dbc9a220564229
ms.sourcegitcommit: 5a39061c2156531f4b7f5f69eecf81a8c8b238d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52030102"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="cc1de-103">管理 Microsoft Teams 中的标记</span><span class="sxs-lookup"><span data-stu-id="cc1de-103">Manage tags in Microsoft Teams</span></span>

## <a name="overview"></a><span data-ttu-id="cc1de-104">概述</span><span class="sxs-lookup"><span data-stu-id="cc1de-104">Overview</span></span>

<span data-ttu-id="cc1de-105">使用Microsoft Teams中的标记，用户可以快速轻松地与团队中的一小组人员联系。</span><span class="sxs-lookup"><span data-stu-id="cc1de-105">Tags in Microsoft Teams let users quickly and easily connect with a subset of people on a team.</span></span> <span data-ttu-id="cc1de-106">可以创建和分配自定义标记，以便根据角色、项目、技能或位置等属性对人员进行分类。</span><span class="sxs-lookup"><span data-stu-id="cc1de-106">You can create and assign custom tags to categorize people based on attributes, such as role, project, skill, or location.</span></span> <span data-ttu-id="cc1de-107">或者，可以在即将推出 [Shifts](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) 应用时，根据人员的计划和班次信息 (标记) 。</span><span class="sxs-lookup"><span data-stu-id="cc1de-107">Or, tags can be automatically assigned to people based on their schedule and shift information in the [Shifts app](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) (coming soon).</span></span> <span data-ttu-id="cc1de-108">将标记添加到一个或多个团队成员后，团队中的任何人都可以在 @mentions 中通过频道帖子使用标记，或者仅与分配了该标记的人开始对话。</span><span class="sxs-lookup"><span data-stu-id="cc1de-108">After a tag is added to one or multiple team members, it can be used in @mentions by anyone on the team in a channel post or to start a conversation with only those people who are assigned that tag.</span></span>

<span data-ttu-id="cc1de-109">如前所述，该标记有两种类型的Teams。</span><span class="sxs-lookup"><span data-stu-id="cc1de-109">As mentioned earlier, there are two kinds of tags in Teams.</span></span>

- <span data-ttu-id="cc1de-110">**自定义标记**：团队所有者和 (如果为其启用了该功能，则) 手动创建标记并将其分配给人员。</span><span class="sxs-lookup"><span data-stu-id="cc1de-110">**Custom tags**: Team owners and team members (if the feature is enabled for them) can manually create and assign tags to people.</span></span> <span data-ttu-id="cc1de-111">例如，"Designer"或"Radi一"标记将到达团队中的这些人员集，而无需键入其姓名。</span><span class="sxs-lookup"><span data-stu-id="cc1de-111">For example, a "Designer" or "Radiologist" tag will reach those sets of people on a team without having to type their names.</span></span>
- <span data-ttu-id="cc1de-112">**按排班** 标记：使用此功能，将自动为人员分配与日程安排匹配的标记，在"班次"应用中自动分配Teams。 [](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)</span><span class="sxs-lookup"><span data-stu-id="cc1de-112">**Tagging by shift**: With this feature, people are automatically assigned tags that match their schedule and shift group name in the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) in Teams.</span></span> <span data-ttu-id="cc1de-113">例如，在聊天或频道帖子中使用标记时，"EngineerOnCall"标记将到达在 Shifts 中计划工作的所有工程师。</span><span class="sxs-lookup"><span data-stu-id="cc1de-113">For example, the "EngineerOnCall" tag reaches all engineers who are scheduled in Shifts to work at the time the tag is used in a chat or channel post.</span></span> <span data-ttu-id="cc1de-114">使用按轮班Teams，当用户需要快速中继信息时，无需知道轮班员工的姓名，</span><span class="sxs-lookup"><span data-stu-id="cc1de-114">With tagging by shift, Teams takes the guesswork out of knowing the name of on-shift staff when users need to quickly relay information.</span></span> <span data-ttu-id="cc1de-115">通过将主要员工管理系统（例如 JDA、Kronos 和 AMiON）与工作团队中的 Shifts 集成，还可以支持按班次进行Teams。</span><span class="sxs-lookup"><span data-stu-id="cc1de-115">Tagging by shift can also be backed by major workforce management systems like JDA, Kronos, and AMiON by integrating them with Shifts in Teams.</span></span> <span data-ttu-id="cc1de-116">若要详细了解如何设置此功能，请参阅按 shift [设置标记](#set-up-tagging-by-shift)。</span><span class="sxs-lookup"><span data-stu-id="cc1de-116">To learn more about how to set up this feature, see [Set up tagging by shift](#set-up-tagging-by-shift).</span></span>

> [!NOTE]
> <span data-ttu-id="cc1de-117">专用通道尚不支持标记。</span><span class="sxs-lookup"><span data-stu-id="cc1de-117">Tags are not yet supported in private channels.</span></span> <span data-ttu-id="cc1de-118">标记在 DoD GCC或国防部 (中) 提供。</span><span class="sxs-lookup"><span data-stu-id="cc1de-118">Tags are not available in GCC High, or Department of Defense (DoD) organizations.</span></span> 

## <a name="how-tags-work"></a><span data-ttu-id="cc1de-119">标记工作</span><span class="sxs-lookup"><span data-stu-id="cc1de-119">How tags work</span></span>

<span data-ttu-id="cc1de-120">可以手动添加标记或自动将标记分配给特定团队中的人员。</span><span class="sxs-lookup"><span data-stu-id="cc1de-120">A tag can be manually added or automatically assigned to a person on a specific team.</span></span> <span data-ttu-id="cc1de-121">然后，它可以在聊天@mentions的"至"行上或在团队的任何标准频道上的帖子中使用。</span><span class="sxs-lookup"><span data-stu-id="cc1de-121">It can then be used in @mentions on the **To** line in a chat or in a post on any standard channel of the team.</span></span> <span data-ttu-id="cc1de-122">下面是一些如何在应用中使用的标记Teams：</span><span class="sxs-lookup"><span data-stu-id="cc1de-122">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="cc1de-123">商店经理向频道发布公告以通知所有收银员。</span><span class="sxs-lookup"><span data-stu-id="cc1de-123">A store manager posts an announcement to a channel to notify all cashiers.</span></span>
- <span data-ttu-id="cc1de-124">医院管理员向频道中的所有辐射员发送消息。</span><span class="sxs-lookup"><span data-stu-id="cc1de-124">A hospital administrator sends a message to all radiologists in a channel.</span></span>
- <span data-ttu-id="cc1de-125">营销经理开始与所有设计人员进行群组聊天。</span><span class="sxs-lookup"><span data-stu-id="cc1de-125">A marketing manager starts a group chat with all designers.</span></span>
- <span data-ttu-id="cc1de-126">医生向所有通话卡员发送消息。</span><span class="sxs-lookup"><span data-stu-id="cc1de-126">A nurse sends a message to all on-call cardiologists.</span></span> <span data-ttu-id="cc1de-127">（即将推出）</span><span class="sxs-lookup"><span data-stu-id="cc1de-127">(coming soon)</span></span>
- <span data-ttu-id="cc1de-128">系统工程师向频道发布公告，通知所有轮班现场工程师。</span><span class="sxs-lookup"><span data-stu-id="cc1de-128">A system engineer posts an announcement to a channel to notify all on-shift field engineers.</span></span> <span data-ttu-id="cc1de-129">（即将推出）</span><span class="sxs-lookup"><span data-stu-id="cc1de-129">(coming soon)</span></span>

<span data-ttu-id="cc1de-130">当标记@mentioned对话中时，与标记关联的团队成员将收到通知，就像任何其他@mention。</span><span class="sxs-lookup"><span data-stu-id="cc1de-130">When a tag is @mentioned in a channel conversation, team members associated with the tag will get notified, just like any other @mention.</span></span>

## <a name="manage-custom-tags-for-your-organization"></a><span data-ttu-id="cc1de-131">管理组织的自定义标记</span><span class="sxs-lookup"><span data-stu-id="cc1de-131">Manage custom tags for your organization</span></span>

<span data-ttu-id="cc1de-132">作为管理员，你可以控制在管理中心内在整个组织中Microsoft Teams标记。</span><span class="sxs-lookup"><span data-stu-id="cc1de-132">As an admin, you can control how tags are used across your organization in the Microsoft Teams admin center.</span></span> <span data-ttu-id="cc1de-133">目前，无法通过 PowerShell 管理标记。</span><span class="sxs-lookup"><span data-stu-id="cc1de-133">Currently, you can't use PowerShell to manage tags.</span></span>

![管理中心中标记设置的Microsoft Teams屏幕截图](media/manage-tags-admin-settings.png)

<span data-ttu-id="cc1de-135">一个团队可以有多达 100 个标记，最多 100 个团队成员可以分配到一个标记，并且最多可以将 25 个标记分配给单个用户。</span><span class="sxs-lookup"><span data-stu-id="cc1de-135">A team can have up to 100 tags, up to 100 team members can be assigned to a tag, and up to 25 tags can be assigned to a single user.</span></span> 

### <a name="set-who-can-add-custom-tags"></a><span data-ttu-id="cc1de-136">设置谁可以添加自定义标记</span><span class="sxs-lookup"><span data-stu-id="cc1de-136">Set who can add custom tags</span></span>

<span data-ttu-id="cc1de-137">默认情况下，团队所有者可以添加自定义标记。</span><span class="sxs-lookup"><span data-stu-id="cc1de-137">By default, team owners can add custom tags.</span></span> <span data-ttu-id="cc1de-138">您可以更改此设置以允许团队所有者和团队成员创建、编辑、删除和管理标记，也可以关闭组织的标记。</span><span class="sxs-lookup"><span data-stu-id="cc1de-138">You can change this setting to allow team owners and team members to create, edit, delete, and manage tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="cc1de-139">在管理中心的左侧导航Microsoft Teams，单击"**组织范围的设置"Teams**  >  **设置"。**</span><span class="sxs-lookup"><span data-stu-id="cc1de-139">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="cc1de-140">在 **"标记"** 下 **，在"标记由 管理"旁边**，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="cc1de-140">Under **Tagging**, next to **Tags are managed by**, select one of the following options:</span></span>

    - <span data-ttu-id="cc1de-141">**团队所有者和成员**：允许团队所有者和成员管理标记。</span><span class="sxs-lookup"><span data-stu-id="cc1de-141">**Team owners and members**: Allow team owners and members to manage tags.</span></span>
    - <span data-ttu-id="cc1de-142">**团队所有者**：允许团队所有者管理标记。</span><span class="sxs-lookup"><span data-stu-id="cc1de-142">**Team owners**: Allow team owners to manage tags.</span></span>
    - <span data-ttu-id="cc1de-143">**已禁用**：关闭标记。</span><span class="sxs-lookup"><span data-stu-id="cc1de-143">**Disabled**: Turn off tags.</span></span>

### <a name="configure-custom-tags-settings"></a><span data-ttu-id="cc1de-144">配置自定义标记设置</span><span class="sxs-lookup"><span data-stu-id="cc1de-144">Configure custom tags settings</span></span>

<span data-ttu-id="cc1de-145">可以配置以下标记设置来控制如何在组织中使用自定义标记。</span><span class="sxs-lookup"><span data-stu-id="cc1de-145">You can configure the following tags settings to control how custom tags are used across your organization.</span></span>

1. <span data-ttu-id="cc1de-146">在管理中心的左侧导航Microsoft Teams，单击"**组织范围的设置"Teams**  >  **设置"。**</span><span class="sxs-lookup"><span data-stu-id="cc1de-146">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="cc1de-147">在 **"标记**"下，根据组织的需求设置以下内容。</span><span class="sxs-lookup"><span data-stu-id="cc1de-147">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="cc1de-148">让团队所有者替代谁可以管理标记：启用此设置时，团队所有者可以设置团队成员是否可以在团队内创建和管理标记，并且"标记"的值通过设置进行管理是每个团队的默认值。</span><span class="sxs-lookup"><span data-stu-id="cc1de-148">**Let team owners override who can manage tags**: When you turn on this setting, team owners can set whether team members can create and manage tags within a team and the value of the **Tags are managed by** setting is the default value for each team.</span></span> <span data-ttu-id="cc1de-149">如果关闭此设置，则 **不能** 更改每个团队的"通过设置管理标记"。</span><span class="sxs-lookup"><span data-stu-id="cc1de-149">If you turn off this setting, the **Tags are managed by** setting can't be changed per team.</span></span>
    - <span data-ttu-id="cc1de-150">**建议的默认标记**：用于添加一组默认标记。</span><span class="sxs-lookup"><span data-stu-id="cc1de-150">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="cc1de-151">最多可以添加 25 个标记，每个标记最多可以包含 25 个字符。</span><span class="sxs-lookup"><span data-stu-id="cc1de-151">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="cc1de-152">如果为 (启用该功能，团队所有者和成员) 可以使用这些建议、添加建议或创建一组新的标记。</span><span class="sxs-lookup"><span data-stu-id="cc1de-152">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>
    - <span data-ttu-id="cc1de-153">**允许创建自定义标记**：启用此设置，以允许添加除你设置的建议默认标记外的其他标记。</span><span class="sxs-lookup"><span data-stu-id="cc1de-153">**Let custom tags be created**: Turn on this setting to let people add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="cc1de-154">如果此选项已关闭，则用户只能使用建议的默认标记。</span><span class="sxs-lookup"><span data-stu-id="cc1de-154">If this is turned off, people can only use the suggested default tags.</span></span> <span data-ttu-id="cc1de-155">如果关闭此功能，请确保添加一个或多个默认标记。</span><span class="sxs-lookup"><span data-stu-id="cc1de-155">If you turn this off, make sure that you add one or more default tags.</span></span>

## <a name="manage-custom-tags-settings-for-a-team"></a><span data-ttu-id="cc1de-156">管理团队的自定义标记设置</span><span class="sxs-lookup"><span data-stu-id="cc1de-156">Manage custom tags settings for a team</span></span>

<span data-ttu-id="cc1de-157">如果启用"允许团队所有者替代谁可以管理Microsoft Teams管理中心"设置，团队所有者可以设置成员是否可以在团队级别添加标记。</span><span class="sxs-lookup"><span data-stu-id="cc1de-157">If you turned on the **Let team owners override who can manage tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="cc1de-158">为此，在团队的设置选项卡上，转到"标记 **"，然后选择** 可以添加标记的人。</span><span class="sxs-lookup"><span data-stu-id="cc1de-158">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![团队级别的标记设置的屏幕截图](media/manage-tags-team-settings.png)

## <a name="use-tags"></a><span data-ttu-id="cc1de-160">使用标记</span><span class="sxs-lookup"><span data-stu-id="cc1de-160">Use tags</span></span>

<span data-ttu-id="cc1de-161">下面将了解如何添加自定义标记，以及如何在 Teams) 中的 Shifts 应用时通过 shift (来设置Teams) 。</span><span class="sxs-lookup"><span data-stu-id="cc1de-161">Here's how to add custom tags and how to set up tagging by shift (if you're using the Shifts app in Teams).</span></span> <span data-ttu-id="cc1de-162">若要了解有关详细信息，请查看使用[Teams 中的标记](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)。</span><span class="sxs-lookup"><span data-stu-id="cc1de-162">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

### <a name="create-and-assign-custom-tags"></a><span data-ttu-id="cc1de-163">创建和分配自定义标记</span><span class="sxs-lookup"><span data-stu-id="cc1de-163">Create and assign custom tags</span></span>

<span data-ttu-id="cc1de-164">若要创建和分配自定义标记，请选择Teams左侧的标记，然后在列表中查找你的团队。</span><span class="sxs-lookup"><span data-stu-id="cc1de-164">To create and assign custom tags, select **Teams** on the left side of the app, and then find your team in the list.</span></span> <span data-ttu-id="cc1de-165">选择 **"""更多选项"，** 然后选择"**管理标记"。**</span><span class="sxs-lookup"><span data-stu-id="cc1de-165">Select **˙˙˙ More options**, and then choose **Manage tags**.</span></span> <span data-ttu-id="cc1de-166">可在此处创建标记并将其分配给团队中的人员。</span><span class="sxs-lookup"><span data-stu-id="cc1de-166">Here, you can create tags and assign them to people on your team.</span></span>

![<span data-ttu-id="cc1de-167">如何在客户端中应用标记的Teams屏幕截图</span><span class="sxs-lookup"><span data-stu-id="cc1de-167">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png)

<span data-ttu-id="cc1de-168">若要删除标记，请选择 **标记旁边的"""更多选项**"，然后选择"删除 **标记"。**</span><span class="sxs-lookup"><span data-stu-id="cc1de-168">To delete a tag, select **˙˙˙ More options** next to the tag, and then select **Delete tag**.</span></span>

### <a name="set-up-tagging-by-shift"></a><span data-ttu-id="cc1de-169">按 Shift 设置标记</span><span class="sxs-lookup"><span data-stu-id="cc1de-169">Set up tagging by shift</span></span>

1. <span data-ttu-id="cc1de-170">在Teams，转到[Shifts 应用](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)。</span><span class="sxs-lookup"><span data-stu-id="cc1de-170">In Teams, go to the [Shifts app](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop).</span></span>
2. <span data-ttu-id="cc1de-171">创建 [班次组](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) ，并基于角色等属性命名。</span><span class="sxs-lookup"><span data-stu-id="cc1de-171">Create [shift groups](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) and name them after an attribute such as a role.</span></span> <span data-ttu-id="cc1de-172">例如，EngineerOnCall。</span><span class="sxs-lookup"><span data-stu-id="cc1de-172">For example, EngineerOnCall.</span></span> <span data-ttu-id="cc1de-173">班次组名称将是标记的名称。</span><span class="sxs-lookup"><span data-stu-id="cc1de-173">The shift group name will be the name of the tag.</span></span>
3. <span data-ttu-id="cc1de-174">[通过向团队成员](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) 分配班次来填写日程安排。</span><span class="sxs-lookup"><span data-stu-id="cc1de-174">[Fill out a schedule](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) by assigning shifts to members of you teams.</span></span> <span data-ttu-id="cc1de-175">完成后，在 Shifts 应用的右上角，选择"**与团队共享"。**</span><span class="sxs-lookup"><span data-stu-id="cc1de-175">When you're finished, in the upper-right corner of the Shifts app, select **Share with team**.</span></span>
4. <span data-ttu-id="cc1de-176">等待 15 分钟，让计划的排班填充标记服务。</span><span class="sxs-lookup"><span data-stu-id="cc1de-176">Wait 15 minutes for the scheduled shifts to populate the tagging service.</span></span>
5. <span data-ttu-id="cc1de-177">在任意位置使用标记，在 Teams。</span><span class="sxs-lookup"><span data-stu-id="cc1de-177">Use the tag anywhere you use tags in Teams.</span></span>

<span data-ttu-id="cc1de-178">按 shift 标记可让用户实时联系轮班人员。</span><span class="sxs-lookup"><span data-stu-id="cc1de-178">Tagging by shift allows your users to reach the people on-shift in real time.</span></span> <span data-ttu-id="cc1de-179">通知仅发送给使用标记开始聊天或频道帖子时轮班的人。</span><span class="sxs-lookup"><span data-stu-id="cc1de-179">Notifications are sent only to those people who are on shift at the time a tag is used to start a chat or in a channel post.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cc1de-180">相关主题</span><span class="sxs-lookup"><span data-stu-id="cc1de-180">Related topics</span></span>

[<span data-ttu-id="cc1de-181">在 Teams</span><span class="sxs-lookup"><span data-stu-id="cc1de-181">Using tags in Teams</span></span>](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[<span data-ttu-id="cc1de-182">在 Teams 中为组织管理排班应用</span><span class="sxs-lookup"><span data-stu-id="cc1de-182">Manage the Shifts app for your organization in Teams</span></span>](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[<span data-ttu-id="cc1de-183">Shifts 帮助文档</span><span class="sxs-lookup"><span data-stu-id="cc1de-183">Shifts Help documentation</span></span>](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
