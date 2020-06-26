---
title: 管理 Microsoft 团队中的标记
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna
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
ms.openlocfilehash: b19613268384831aaaa2608fc183b62fdc1b0445
ms.sourcegitcommit: 0979fae58ecd713f8317ed99caae015b5cc2c8e4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2020
ms.locfileid: "44877933"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="d889e-103">管理 Microsoft 团队中的标记</span><span class="sxs-lookup"><span data-stu-id="d889e-103">Manage tags in Microsoft Teams</span></span>

<span data-ttu-id="d889e-104">Microsoft 团队中的标记使用户能够与团队中的一部分人员进行通信。</span><span class="sxs-lookup"><span data-stu-id="d889e-104">Tags in Microsoft Teams let users communicate with a subset of people on a team.</span></span> <span data-ttu-id="d889e-105">可将标记添加到一个或多个团队成员，以便轻松地与用户的正确子集连接。</span><span class="sxs-lookup"><span data-stu-id="d889e-105">Tags can be added to one or multiple team members to easily connect with the right subset of people.</span></span> <span data-ttu-id="d889e-106">团队所有者和成员（如果为其启用了该功能）可以向某个人员添加一个或多个标记。</span><span class="sxs-lookup"><span data-stu-id="d889e-106">Team owners and members (if the feature is enabled for them) can add one or more tags to a person.</span></span> <span data-ttu-id="d889e-107">然后，这些标记可在频道发布中由团队的任何人 @mentions，或者仅与分配了该标记的人员开始对话。</span><span class="sxs-lookup"><span data-stu-id="d889e-107">The tags can then be used in @mentions by anyone on the team in a channel post or to start a conversation with only those people who are assigned that tag.</span></span>

> [!NOTE]
> <span data-ttu-id="d889e-108">专用频道尚不支持标记。</span><span class="sxs-lookup"><span data-stu-id="d889e-108">Tags are not yet supported in private channels.</span></span> <span data-ttu-id="d889e-109">在美国政府社区云（GCC）、GCC 高或国防（DoD）组织中尚不提供标记。</span><span class="sxs-lookup"><span data-stu-id="d889e-109">Tags are not yet available in US Government Community Cloud (GCC), GCC High, or Department of Defense (DoD) organizations.</span></span>

## <a name="how-tags-work"></a><span data-ttu-id="d889e-110">标记的工作方式</span><span class="sxs-lookup"><span data-stu-id="d889e-110">How tags work</span></span>

<span data-ttu-id="d889e-111">可以向特定团队中的人员添加标记。</span><span class="sxs-lookup"><span data-stu-id="d889e-111">A tag can be added to a person on a specific team.</span></span> <span data-ttu-id="d889e-112">添加标记后，可以在聊天中的 @mentions 或团队的任何标准频道中使用。</span><span class="sxs-lookup"><span data-stu-id="d889e-112">After a tag is added, it can be used in @mentions in a chat or in any standard channel of the team.</span></span> <span data-ttu-id="d889e-113">下面是如何在团队中使用标记的一些示例：</span><span class="sxs-lookup"><span data-stu-id="d889e-113">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="d889e-114">商店经理希望向频道发布公告并通知所有出纳。</span><span class="sxs-lookup"><span data-stu-id="d889e-114">A store manager wants to post an announcement to a channel and notify all cashiers.</span></span>
- <span data-ttu-id="d889e-115">组产品经理希望向频道中的所有产品经理发送消息。</span><span class="sxs-lookup"><span data-stu-id="d889e-115">A group product manager wants to message all product managers in a channel.</span></span>
- <span data-ttu-id="d889e-116">医院管理员想要向频道中的所有 radiologists 发送一封邮件。</span><span class="sxs-lookup"><span data-stu-id="d889e-116">A hospital administrator wants to send a message to all radiologists in a channel.</span></span>
- <span data-ttu-id="d889e-117">市场营销经理希望开始与所有设计人员进行群组聊天。</span><span class="sxs-lookup"><span data-stu-id="d889e-117">A marketing manager wants to start a group chat with all designers.</span></span>

<span data-ttu-id="d889e-118">当标记在频道对话中 @mentioned 时，与该标记相关联的团队成员将收到通知，就像任何其他 @mention 一样。</span><span class="sxs-lookup"><span data-stu-id="d889e-118">When a tag is @mentioned in a channel conversation, team members associated with the tag will get notified, just like any other @mention.</span></span>

<span data-ttu-id="d889e-119">若要了解详细信息，请参阅[使用团队中的标记](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)。</span><span class="sxs-lookup"><span data-stu-id="d889e-119">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

## <a name="manage-tags-for-your-organization"></a><span data-ttu-id="d889e-120">管理你的组织的标记</span><span class="sxs-lookup"><span data-stu-id="d889e-120">Manage tags for your organization</span></span>

<span data-ttu-id="d889e-121">作为管理员，你可以控制哪些人可以添加标签，以及如何在 Microsoft 团队管理中心中跨你的组织使用标记。</span><span class="sxs-lookup"><span data-stu-id="d889e-121">As an admin, you can control who can add tags and how tags are used across your organization in the Microsoft Teams admin center.</span></span>

![Microsoft 团队管理中心中的标记设置的屏幕截图](media/manage-tags-admin-settings.png)

<span data-ttu-id="d889e-123">一个团队最多可以有100个标记，最多可以向100个团队成员分配一个标记，并且可以将最多25个标记分配给单个用户。</span><span class="sxs-lookup"><span data-stu-id="d889e-123">A team can have up to 100 tags, up to 100 team members can be assigned to a tag, and up to 25 tags can be assigned to a single user.</span></span> 

### <a name="set-who-can-add-tags"></a><span data-ttu-id="d889e-124">设置可以添加标记的人员</span><span class="sxs-lookup"><span data-stu-id="d889e-124">Set who can add tags</span></span>

<span data-ttu-id="d889e-125">默认情况下，团队所有者可以添加标记。</span><span class="sxs-lookup"><span data-stu-id="d889e-125">By default, team owners can add tags.</span></span> <span data-ttu-id="d889e-126">你可以更改此设置以允许团队所有者和团队成员添加标记，也可以关闭你的组织的标记。</span><span class="sxs-lookup"><span data-stu-id="d889e-126">You can change this setting to allow team owners and team members to add tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="d889e-127">在 Microsoft 团队管理中心的左侧导航中，单击 "**组织范围设置**"  >  **团队设置**。</span><span class="sxs-lookup"><span data-stu-id="d889e-127">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="d889e-128">在 "**标记**" 下，在 "**标记已启用**" 旁边，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="d889e-128">Under **Tagging**, next to **Tagging is enabled for**, select one of the following options:</span></span>

    - <span data-ttu-id="d889e-129">**团队所有者和成员**：允许团队所有者和成员添加标记。</span><span class="sxs-lookup"><span data-stu-id="d889e-129">**Team owners and members**: Allow team owners and members to add tags.</span></span>
    - <span data-ttu-id="d889e-130">**团队所有者**：允许团队所有者添加标记。</span><span class="sxs-lookup"><span data-stu-id="d889e-130">**Team owners**: Allow team owners to add tags.</span></span>
    - <span data-ttu-id="d889e-131">**已禁用**：关闭标记。</span><span class="sxs-lookup"><span data-stu-id="d889e-131">**Disabled**: Turn off tags.</span></span>

### <a name="configure-tags-settings"></a><span data-ttu-id="d889e-132">配置标签设置</span><span class="sxs-lookup"><span data-stu-id="d889e-132">Configure tags settings</span></span>

<span data-ttu-id="d889e-133">你可以配置以下标记设置以控制如何在组织中使用标记。</span><span class="sxs-lookup"><span data-stu-id="d889e-133">You can configure the following tags settings to control how tags are used across your organization.</span></span>

1. <span data-ttu-id="d889e-134">在 Microsoft 团队管理中心的左侧导航中，单击 "**组织范围设置**"  >  **团队设置**。</span><span class="sxs-lookup"><span data-stu-id="d889e-134">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="d889e-135">在 "**标记**" 下，根据组织的需要设置以下各项。</span><span class="sxs-lookup"><span data-stu-id="d889e-135">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="d889e-136">**团队所有者可以覆盖可以应用标记的人员**：当启用此功能时，团队所有者可以允许或禁止成员在团队设置中添加标记。</span><span class="sxs-lookup"><span data-stu-id="d889e-136">**Team owner can override who can apply tags**: When this is turned on, team owners can allow or disallow members to add tags in team settings.</span></span>
    - <span data-ttu-id="d889e-137">**成员可以添加其他标记**：如果允许团队成员添加标记，请启用此设置，让团队成员添加除了所设置的建议默认标记以外的其他标记。</span><span class="sxs-lookup"><span data-stu-id="d889e-137">**Members can add additional tags**: If you allow team members to add tags, turn this on to let team members add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="d889e-138">如果关闭此功能，团队成员只能使用默认标记。</span><span class="sxs-lookup"><span data-stu-id="d889e-138">If this is turned off, team members can only use the default tags.</span></span>
    - <span data-ttu-id="d889e-139">**建议的默认标记**：使用此项添加一组默认标记。</span><span class="sxs-lookup"><span data-stu-id="d889e-139">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="d889e-140">您最多可以添加25个标签，每个标签最多可以包含25个字符。</span><span class="sxs-lookup"><span data-stu-id="d889e-140">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="d889e-141">团队所有者和成员（如果为其启用了该功能）可以使用这些建议、添加到这些建议或创建新的标记集。</span><span class="sxs-lookup"><span data-stu-id="d889e-141">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>

## <a name="manage-tags-settings-for-a-team"></a><span data-ttu-id="d889e-142">管理团队的标记设置</span><span class="sxs-lookup"><span data-stu-id="d889e-142">Manage tags settings for a team</span></span>

<span data-ttu-id="d889e-143">如果已打开**团队所有者可以覆盖**Microsoft 团队管理中心中可以应用 "标记" 设置的人员，团队所有者可以设置成员是否可以在团队级别添加标记。</span><span class="sxs-lookup"><span data-stu-id="d889e-143">If you turned on the **Team owner can override who can apply tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="d889e-144">若要执行此操作，请在团队的 "**设置**" 选项卡上，转到 "**标记**"，然后选择可以添加标记的人员。</span><span class="sxs-lookup"><span data-stu-id="d889e-144">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![团队级别的标记设置的屏幕截图](media/manage-tags-team-settings.png)

## <a name="use-tags"></a><span data-ttu-id="d889e-146">使用标记</span><span class="sxs-lookup"><span data-stu-id="d889e-146">Use tags</span></span>

### <a name="add-tags"></a><span data-ttu-id="d889e-147">添加标记</span><span class="sxs-lookup"><span data-stu-id="d889e-147">Add tags</span></span>

<span data-ttu-id="d889e-148">若要创建和分配标记，请选择应用左侧的 "**团队**"，然后在列表中找到您的团队。</span><span class="sxs-lookup"><span data-stu-id="d889e-148">To create and assign tags, select **Teams** on the left side of the app, and then find your team in the list.</span></span> <span data-ttu-id="d889e-149">选择 "**更多选项**"，然后选择 "**管理标记**"。</span><span class="sxs-lookup"><span data-stu-id="d889e-149">Select **More options**, and then choose **Manage tags**.</span></span>

<span data-ttu-id="d889e-150">在此处，你可以创建标记并将其分配给团队中的人员。</span><span class="sxs-lookup"><span data-stu-id="d889e-150">Here, you can create tags and assign them to people on your team.</span></span>

![<span data-ttu-id="d889e-151">如何在团队客户端应用标记的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="d889e-151">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png)

### <a name="delete-tags"></a><span data-ttu-id="d889e-152">删除标记</span><span class="sxs-lookup"><span data-stu-id="d889e-152">Delete tags</span></span>

<span data-ttu-id="d889e-153">删除与标记相关联的所有团队成员，标记将被删除。</span><span class="sxs-lookup"><span data-stu-id="d889e-153">Remove all team members associated with the tag and the tag will be deleted.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d889e-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="d889e-154">Related topics</span></span>

[<span data-ttu-id="d889e-155">使用团队中的标记</span><span class="sxs-lookup"><span data-stu-id="d889e-155">Using tags in Teams</span></span>](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)
