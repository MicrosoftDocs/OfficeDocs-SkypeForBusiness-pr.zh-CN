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
ms.openlocfilehash: 3ade2f47474fe8aaf16c568e8c141dcd84526d86
ms.sourcegitcommit: 561b9bab7d6f5a621436bc85ea28ea14657e7868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034489"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="2a844-103">管理 Microsoft 团队中的标记</span><span class="sxs-lookup"><span data-stu-id="2a844-103">Manage tags in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="2a844-104">尚未在 Microsoft 团队管理中心中看到此功能？</span><span class="sxs-lookup"><span data-stu-id="2a844-104">Don't see this feature in the Microsoft Teams admin center yet?</span></span> <span data-ttu-id="2a844-105">当前正在推出此功能，可能在贵组织中还不可用。</span><span class="sxs-lookup"><span data-stu-id="2a844-105">It's currently being rolled out and might not be available in your organization yet.</span></span> <span data-ttu-id="2a844-106">若要保持在即将到来的团队功能上，请查看[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)。</span><span class="sxs-lookup"><span data-stu-id="2a844-106">To stay on top of upcoming Teams features, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).</span></span>

<span data-ttu-id="2a844-107">Microsoft 团队中的标记使用户能够与团队中的一部分人员进行通信。</span><span class="sxs-lookup"><span data-stu-id="2a844-107">Tags in Microsoft Teams let users communicate with a subset of people on a team.</span></span> <span data-ttu-id="2a844-108">可将标记添加到一个或多个团队成员，以便轻松地与用户的正确子集连接。</span><span class="sxs-lookup"><span data-stu-id="2a844-108">Tags can be added to one or multiple team members to easily connect with the right subset of people.</span></span> <span data-ttu-id="2a844-109">团队所有者和成员（如果为其启用了该功能）可以向某个人员添加一个或多个标记。</span><span class="sxs-lookup"><span data-stu-id="2a844-109">Team owners and members (if the feature is enabled for them) can add one or more tags to a person.</span></span> <span data-ttu-id="2a844-110">然后，可在频道发布 @mentions 由团队中的任何人使用，以便仅与分配了该标记的人员进行通信。</span><span class="sxs-lookup"><span data-stu-id="2a844-110">The tags can then be used in @mentions by anyone on the team in a channel post to communicate with only those people who are assigned that tag.</span></span>

> [!NOTE]
> <span data-ttu-id="2a844-111">专用频道尚不支持标记。</span><span class="sxs-lookup"><span data-stu-id="2a844-111">Tags are not yet supported in private channels.</span></span>

## <a name="how-tags-work"></a><span data-ttu-id="2a844-112">标记的工作方式</span><span class="sxs-lookup"><span data-stu-id="2a844-112">How tags work</span></span>

<span data-ttu-id="2a844-113">可以向特定团队中的人员添加标记。</span><span class="sxs-lookup"><span data-stu-id="2a844-113">A tag can be added to a person on a specific team.</span></span> <span data-ttu-id="2a844-114">添加标记后，可以在团队的任何标准频道 @mentions 中使用。</span><span class="sxs-lookup"><span data-stu-id="2a844-114">After a tag is added, it can be used in @mentions in any standard channel of the team.</span></span> <span data-ttu-id="2a844-115">下面是如何在团队中使用标记的一些示例：</span><span class="sxs-lookup"><span data-stu-id="2a844-115">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="2a844-116">商店经理希望向频道发布公告并通知所有出纳。</span><span class="sxs-lookup"><span data-stu-id="2a844-116">A store manager wants to post an announcement to a channel and notify all cashiers.</span></span>
- <span data-ttu-id="2a844-117">组产品经理希望向频道中的所有产品经理发送消息。</span><span class="sxs-lookup"><span data-stu-id="2a844-117">A group product manager wants to message all product managers in a channel.</span></span>
- <span data-ttu-id="2a844-118">医院管理员想要向频道中的所有 radiologists 发送一封邮件。</span><span class="sxs-lookup"><span data-stu-id="2a844-118">A hospital administrator wants to send a message to all radiologists in a channel.</span></span>

<span data-ttu-id="2a844-119">若要了解详细信息，请参阅[使用团队中的标记](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)。</span><span class="sxs-lookup"><span data-stu-id="2a844-119">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

## <a name="manage-tags-for-your-organization"></a><span data-ttu-id="2a844-120">管理你的组织的标记</span><span class="sxs-lookup"><span data-stu-id="2a844-120">Manage tags for your organization</span></span>

<span data-ttu-id="2a844-121">作为管理员，你可以控制哪些人可以添加标签，以及如何在 Microsoft 团队管理中心中跨你的组织使用标记。</span><span class="sxs-lookup"><span data-stu-id="2a844-121">As an admin, you can control who can add tags and how tags are used across your organization in the Microsoft Teams admin center.</span></span>

![Microsoft 团队管理中心中的标记设置的屏幕截图](media/manage-tags-admin-settings.png)

### <a name="set-who-can-add-tags"></a><span data-ttu-id="2a844-123">设置可以添加标记的人员</span><span class="sxs-lookup"><span data-stu-id="2a844-123">Set who can add tags</span></span>

<span data-ttu-id="2a844-124">默认情况下，团队所有者可以添加标记。</span><span class="sxs-lookup"><span data-stu-id="2a844-124">By default, team owners can add tags.</span></span> <span data-ttu-id="2a844-125">你可以更改此设置以允许团队所有者和团队成员添加标记，也可以关闭你的组织的标记。</span><span class="sxs-lookup"><span data-stu-id="2a844-125">You can change this setting to allow team owners and team members to add tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="2a844-126">在 Microsoft 团队管理中心的左侧导航中，单击 "**组织范围设置** > "**团队设置**。</span><span class="sxs-lookup"><span data-stu-id="2a844-126">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="2a844-127">在 "**标记**" 下，在 "**标记已启用**" 旁边，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="2a844-127">Under **Tagging**, next to **Tagging is enabled for**, select one of the following options:</span></span>

    - <span data-ttu-id="2a844-128">**团队所有者和成员**：允许团队所有者和成员添加标记。</span><span class="sxs-lookup"><span data-stu-id="2a844-128">**Team owners and members**: Allow team owners and members to add tags.</span></span>
    - <span data-ttu-id="2a844-129">**团队所有者**：允许团队所有者添加标记。</span><span class="sxs-lookup"><span data-stu-id="2a844-129">**Team owners**: Allow team owners to add tags.</span></span>
    - <span data-ttu-id="2a844-130">**已禁用**：关闭标记。</span><span class="sxs-lookup"><span data-stu-id="2a844-130">**Disabled**: Turn off tags.</span></span>

### <a name="configure-tags-settings"></a><span data-ttu-id="2a844-131">配置标签设置</span><span class="sxs-lookup"><span data-stu-id="2a844-131">Configure tags settings</span></span>

<span data-ttu-id="2a844-132">你可以配置以下标记设置以控制如何在组织中使用标记。</span><span class="sxs-lookup"><span data-stu-id="2a844-132">You can configure the following tags settings to control how tags are used across your organization.</span></span>

1. <span data-ttu-id="2a844-133">在 Microsoft 团队管理中心的左侧导航中，单击 "**组织范围设置** > "**团队设置**。</span><span class="sxs-lookup"><span data-stu-id="2a844-133">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="2a844-134">在 "**标记**" 下，根据组织的需要设置以下各项。</span><span class="sxs-lookup"><span data-stu-id="2a844-134">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="2a844-135">**团队所有者可以覆盖可以应用标记的人员**：当启用此功能时，团队所有者可以允许或禁止成员在团队设置中添加标记。</span><span class="sxs-lookup"><span data-stu-id="2a844-135">**Team owner can override who can apply tags**: When this is turned on, team owners can allow or disallow members to add tags in team settings.</span></span>
    - <span data-ttu-id="2a844-136">**成员可以添加其他标记**：如果允许团队成员添加标记，请启用此设置，让团队成员添加除了所设置的建议默认标记以外的其他标记。</span><span class="sxs-lookup"><span data-stu-id="2a844-136">**Members can add additional tags**: If you allow team members to add tags, turn this on to let team members add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="2a844-137">如果关闭此功能，团队成员只能使用默认标记。</span><span class="sxs-lookup"><span data-stu-id="2a844-137">If this is turned off, team members can only use the default tags.</span></span>
    - <span data-ttu-id="2a844-138">**建议的默认标记**：使用此项添加一组默认标记。</span><span class="sxs-lookup"><span data-stu-id="2a844-138">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="2a844-139">您最多可以添加25个标签，每个标签最多可以包含25个字符。</span><span class="sxs-lookup"><span data-stu-id="2a844-139">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="2a844-140">团队所有者和成员（如果为其启用了该功能）可以使用这些建议、添加到这些建议或创建新的标记集。</span><span class="sxs-lookup"><span data-stu-id="2a844-140">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>

## <a name="manage-tags-settings-for-a-team"></a><span data-ttu-id="2a844-141">管理团队的标记设置</span><span class="sxs-lookup"><span data-stu-id="2a844-141">Manage tags settings for a team</span></span>

<span data-ttu-id="2a844-142">如果已打开**团队所有者可以覆盖**Microsoft 团队管理中心中可以应用 "标记" 设置的人员，团队所有者可以设置成员是否可以在团队级别添加标记。</span><span class="sxs-lookup"><span data-stu-id="2a844-142">If you turned on the **Team owner can override who can apply tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="2a844-143">若要执行此操作，请在团队的 "**设置**" 选项卡上，转到 "**标记**"，然后选择可以添加标记的人员。</span><span class="sxs-lookup"><span data-stu-id="2a844-143">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![团队级别的标记设置的屏幕截图](media/manage-tags-team-settings.png)

## <a name="add-tags-in-teams"></a><span data-ttu-id="2a844-145">在团队中添加标记</span><span class="sxs-lookup"><span data-stu-id="2a844-145">Add tags in Teams</span></span>

<span data-ttu-id="2a844-146">在团队中，团队的 "管理团队" 页面的 "**成员**" 选项卡包括 "**标记**" 列。</span><span class="sxs-lookup"><span data-stu-id="2a844-146">In Teams, the **Members** tab of the Manage team page for a team includes a **Tags** column.</span></span> <span data-ttu-id="2a844-147">团队所有者和成员（如果为其启用了该功能）可以单击成员旁边的 "**管理标记**"，以查看该成员的建议标记列表，并将标记添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="2a844-147">Team owners and members (if the feature is enabled for them) can click **Manage tags** next to a member to see the list of suggested tags for that member and add tags to the list.</span></span>

![<span data-ttu-id="2a844-148">如何在团队客户端应用标记的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="2a844-148">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png) 
