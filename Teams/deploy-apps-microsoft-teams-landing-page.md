---
title: Microsoft Teams 中的应用、聊天机器人和连接器
description: 使用这些部署资源帮助你在 Microsoft Teams 中部署应用。
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/28/2019
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 31e05d8f4690f638f4fafa0df10355531c46578e
ms.sourcegitcommit: 3a0b90af8eb3c10579b9eea7837c60a19a577881
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2019
ms.locfileid: "29594299"
---
# <a name="apps-bots--connectors-in-microsoft-teams"></a><span data-ttu-id="73a18-103">Microsoft Teams 中的应用、聊天机器人和连接器</span><span class="sxs-lookup"><span data-stu-id="73a18-103">Apps, bots, & connectors in Microsoft Teams</span></span>

<span data-ttu-id="73a18-104">应用使你能通过收藏夹服务查找内容，并就在 Teams 中分享内容。</span><span class="sxs-lookup"><span data-stu-id="73a18-104">Apps let you find content from your favorite services and share it right in Teams.</span></span> <span data-ttu-id="73a18-105">应用可帮助你执行某些操作，例如将服务固定在频道的顶部、与聊天机器人聊天，或者共享和分配任务。</span><span class="sxs-lookup"><span data-stu-id="73a18-105">They help you do things such as pin services at the top of a channel, chat with bots, or share and assign tasks.</span></span> <span data-ttu-id="73a18-106">若要了解详细信息，请阅读 [Teams 中的应用概述](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)。</span><span class="sxs-lookup"><span data-stu-id="73a18-106">To learn more, read [Overview of security and compliance in Teams](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0).</span></span>

<span data-ttu-id="73a18-107">我们建议你在 Teams 的初步部署中加入特别推荐的应用 - 例如 Planner。</span><span class="sxs-lookup"><span data-stu-id="73a18-107">We recommend that you include our featured apps - such as Planner - in your initial Teams rollout.</span></span> <span data-ttu-id="73a18-108">在推动 Teams 采用的过程中添加其他应用、聊天机器人和连接器。</span><span class="sxs-lookup"><span data-stu-id="73a18-108">Add other apps, bots, & connectors as you drive Teams adoption.</span></span>



## <a name="apps-deployment-decisions"></a><span data-ttu-id="73a18-109">应用部署决策</span><span class="sxs-lookup"><span data-stu-id="73a18-109">Apps deployment decisions</span></span>

<span data-ttu-id="73a18-110">Teams 为组织提供了现成的出色协作体验，并且大多数组织发现默认设置适合它们。</span><span class="sxs-lookup"><span data-stu-id="73a18-110">Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them.</span></span> <span data-ttu-id="73a18-111">本文可帮助你决定是否要根据组织的情况和业务需求更改任何默认设置，然后引导你完成每项更改。</span><span class="sxs-lookup"><span data-stu-id="73a18-111">This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="73a18-112">我们将这些设置分为两组：首先是[你更有可能更改的一组核心设置](#core-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="73a18-112">We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="73a18-113">第二组包括你可能希望根据组织的需求配置的[其他设置](#additional-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="73a18-113">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="73a18-114">核心部署决策</span><span class="sxs-lookup"><span data-stu-id="73a18-114">Core deployment decisions</span></span>

<span data-ttu-id="73a18-115">以下是大多数组织在默认设置不适合的情况下想要更改的应用设置。</span><span class="sxs-lookup"><span data-stu-id="73a18-115">These are the apps settings that most organizations want to change (if the Teams default settings don't work for them).</span></span>

### <a name="app-availability-settings"></a><span data-ttu-id="73a18-116">应用可用性设置</span><span class="sxs-lookup"><span data-stu-id="73a18-116">App availability settings</span></span> 

<span data-ttu-id="73a18-117">Teams 提供一些第一方（Microsoft 提供）和第三方应用来吸引用户、支持高效工作，并在 Teams 中集成了常用的业务服务。</span><span class="sxs-lookup"><span data-stu-id="73a18-117">Teams provides a number of first-party (Microsoft provided) and third-party apps to engage users, support productivity, and integrate commonly used business services into Teams.</span></span> <span data-ttu-id="73a18-118">从 Teams 应用商店获取应用。</span><span class="sxs-lookup"><span data-stu-id="73a18-118">Get apps from the Teams Store.</span></span> <span data-ttu-id="73a18-119">默认情况下，所有应用（包括你通过 [Teams 应用商店审批流程](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process)提交的外部应用）均对所有用户开启。</span><span class="sxs-lookup"><span data-stu-id="73a18-119">By default, all apps, including external apps that you've submitted via the [Teams Store approval process](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), are turned on for all users.</span></span> <span data-ttu-id="73a18-120">例如，用户可以使用 Planner 应用在 Teams 中构建和管理团队任务。</span><span class="sxs-lookup"><span data-stu-id="73a18-120">For example, users can use the Planner app to build and manage team tasks in Teams.</span></span>

<span data-ttu-id="73a18-121">默认情况下，所有 Microsoft 提供的应用和外部应用均可用，并且你可以开启或关闭单独的应用。</span><span class="sxs-lookup"><span data-stu-id="73a18-121">By default, all Microsoft-provided and external apps are available, and you can turn individual apps on or off.</span></span> <span data-ttu-id="73a18-122">你可以通过一项全局设置来为整个组织开启或关闭所有外部应用。</span><span class="sxs-lookup"><span data-stu-id="73a18-122">There's a global setting that lets you turn all external apps on or off for your entire organization.</span></span>

| <span data-ttu-id="73a18-123">询问你自己</span><span class="sxs-lookup"><span data-stu-id="73a18-123">Ask yourself</span></span> | <span data-ttu-id="73a18-124">操作</span><span class="sxs-lookup"><span data-stu-id="73a18-124">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="73a18-125">是否要更改默认 Teams 应用设置？</span><span class="sxs-lookup"><span data-stu-id="73a18-125">Will you change the default Teams apps settings?</span></span> | <span data-ttu-id="73a18-126">有关配置外部应用可用性的详细信息，请参阅[在 Microsoft Teams 中管理应用设置](admin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="73a18-126">For more information about configuring the availability of external apps, see [Admin settings for apps in Microsoft Teams](admin-settings.md).</span></span>|
|||

### <a name="app-permissions-and-other-considerations"></a><span data-ttu-id="73a18-127">应用权限和其他注意事项</span><span class="sxs-lookup"><span data-stu-id="73a18-127">App permissions and other considerations</span></span>

<span data-ttu-id="73a18-128">应用由用户允许，并由管理员或 IT 专业人员通过策略进行管理。</span><span class="sxs-lookup"><span data-stu-id="73a18-128">Apps are consented to by users and managed by the admin or IT pro through policies.</span></span> <span data-ttu-id="73a18-129">但是，在大多数情况下，应用的权限和风险状况是在应用本身内定义的。</span><span class="sxs-lookup"><span data-stu-id="73a18-129">However, for the most part, an app's permissions and risk profile are defined in the app itself.</span></span> 

| <span data-ttu-id="73a18-130">询问你自己</span><span class="sxs-lookup"><span data-stu-id="73a18-130">Ask yourself</span></span> | <span data-ttu-id="73a18-131">操作</span><span class="sxs-lookup"><span data-stu-id="73a18-131">Action</span></span> |
|--------------|--------|
|<br><span data-ttu-id="73a18-132">希望允许访问哪些应用？</span><span class="sxs-lookup"><span data-stu-id="73a18-132">Which apps do I want to allow access to?</span></span> <span data-ttu-id="73a18-133">不希望允许访问哪些应用？</span><span class="sxs-lookup"><span data-stu-id="73a18-133">Which ones do I not want to allow access to?</span></span>  | <ul><li><span data-ttu-id="73a18-134">有关在允许访问应用、聊天机器人、选项卡或连接器时要考虑的事项的列表，请参阅 [Microsoft Teams 应用权限和注意事项](app-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="73a18-134">See [Microsoft Teams apps permissions and considerations](app-permissions.md) for a list of things you should consider when allowing access to an app, bot, tab, or connector.</span></span></li><li><span data-ttu-id="73a18-135">有关将应用提供给组织中的用户的信息，请参阅[在 Teams 租户应用目录中发布应用](tenant-apps-catalog-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="73a18-135">See [Publish apps in the Teams tenant apps catalog](tenant-apps-catalog-teams.md) for information about making an app available to users in your organization.</span></span></li></ul>|
|||

### <a name="bots-for-private-chats-and-channels"></a><span data-ttu-id="73a18-136">用于私人聊天和频道的聊天机器人</span><span class="sxs-lookup"><span data-stu-id="73a18-136">Add bots for private chats and channels in Teams</span></span>

<span data-ttu-id="73a18-137">聊天机器人是自动化程序，它们可响应查询或者提供有关用户感兴趣或想要及时了解的详细信息的更新和通知。</span><span class="sxs-lookup"><span data-stu-id="73a18-137">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="73a18-138">聊天机器人允许用户与云服务交互，例如任务管理、计划以及在 Teams 聊天中投票。</span><span class="sxs-lookup"><span data-stu-id="73a18-138">Bots allow users to interact with cloud services like task management, scheduling, and polling, through chat conversations in Microsoft Teams.</span></span> <span data-ttu-id="73a18-139">Teams 支持在私人聊天和频道中使用聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="73a18-139">Currently, Microsoft Teams support bots in private chats and channels within a team.</span></span> <span data-ttu-id="73a18-140">管理员可以控制是否允许在 Office 365 租户中使用聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="73a18-140">Administrators can control whether the use of bots is allowed or prohibited within the Office 365 tenant.</span></span>

| <span data-ttu-id="73a18-141">询问你自己</span><span class="sxs-lookup"><span data-stu-id="73a18-141">Ask yourself</span></span> | <span data-ttu-id="73a18-142">操作</span><span class="sxs-lookup"><span data-stu-id="73a18-142">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="73a18-143">是否要允许在我的 Office 365 租户中使用自定义聊天机器人？</span><span class="sxs-lookup"><span data-stu-id="73a18-143">Do I want to allow custom bots in my Office 365 tenant?</span></span>|<span data-ttu-id="73a18-144">有关添加聊天机器人的详细信息，请参阅[为 Microsoft Teams 中的私人聊天和频道添加聊天机器人](add-bots.md)。</span><span class="sxs-lookup"><span data-stu-id="73a18-144">For more information about adding bots, see [Add bots for private chats and channels in Microsoft Teams](add-bots.md).</span></span> <span data-ttu-id="73a18-145">有关开启或关闭聊天机器人的信息，请参阅[在 Microsoft Teams 中管理应用设置](admin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="73a18-145">For information about turning custom bots on or off, see [Admin settings for apps in Microsoft Teams](admin-settings.md).</span></span>|
|||

### <a name="built-in-and-custom-tabs"></a><span data-ttu-id="73a18-146">内置和自定义选项卡</span><span class="sxs-lookup"><span data-stu-id="73a18-146">Built-in and custom tabs</span></span>

<span data-ttu-id="73a18-147">所有者和团队成员可以向频道、私人聊天和群组聊天中添加选项卡，以帮助集成其云服务。</span><span class="sxs-lookup"><span data-stu-id="73a18-147">Owners and team members can add additional tabs, to each channel, to help integrate their cloud services.</span></span> <span data-ttu-id="73a18-148">添加选项卡可帮助用户访问并管理自己需要或最常用的数据。</span><span class="sxs-lookup"><span data-stu-id="73a18-148">Additional tabs can be added to channels to help users easily access and manage the data they need or interact with the most.</span></span> <span data-ttu-id="73a18-149">在频道中，默认情况下已创建了“对话”和“文件”选项卡。</span><span class="sxs-lookup"><span data-stu-id="73a18-149">In channels, the Conversations and Files tabs are created by default.</span></span> <span data-ttu-id="73a18-150">在私人聊天中，默认情况下已创建了“对话”、“文件”、“组织”和“活动”选项卡。</span><span class="sxs-lookup"><span data-stu-id="73a18-150">In every private chat, the Conversations, Files, Organization, and Activity tabs are created by default.</span></span> <span data-ttu-id="73a18-151">除了这些内置选项卡外，你还可以设计和添加自定义选项卡。</span><span class="sxs-lookup"><span data-stu-id="73a18-151">In addition to these built-in tabs, you can design and add custom tabs.</span></span> <span data-ttu-id="73a18-152">若要了解如何为你的组织开启或关闭 Teams 应用，请阅读[在 Teams 中管理应用设置](admin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="73a18-152">To learn about turning Teams apps on or off for your organization, read [Admin settings for apps in Teams](admin-settings.md).</span></span>

| <span data-ttu-id="73a18-153">询问你自己</span><span class="sxs-lookup"><span data-stu-id="73a18-153">Ask yourself</span></span> | <span data-ttu-id="73a18-154">操作</span><span class="sxs-lookup"><span data-stu-id="73a18-154">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="73a18-155">是否要允许在我的 Office 365 租户中使用自定义选项卡？</span><span class="sxs-lookup"><span data-stu-id="73a18-155">Do I want to allow custom tabs in my Office 365 tenant?</span></span>|<span data-ttu-id="73a18-156">有关详细信息，请参阅[在 Teams 中使用内置和自定义选项卡](built-in-custom-tabs.md)。</span><span class="sxs-lookup"><span data-stu-id="73a18-156">For more information, see [Use built-in and custom tabs in Teams](built-in-custom-tabs.md).</span></span>|
|||

### <a name="office-365-and-custom-connectors"></a><span data-ttu-id="73a18-157">Office 365 和自定义连接器</span><span class="sxs-lookup"><span data-stu-id="73a18-157">Use Office 365 and custom connectors in Teams</span></span>

<span data-ttu-id="73a18-158">连接器可将内容和更新从你经常使用的服务直接传递到频道中，从而使你的团队能够获得最新内容。</span><span class="sxs-lookup"><span data-stu-id="73a18-158">Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel.</span></span> <span data-ttu-id="73a18-159">通过使用连接器，你的 Teams 用户可以在其 Teams 聊天中接收来自常用服务（例如 Twitter、Trello、Wunderlist、GitHub 和 Visual Studio Team Services (VSTS)）的更新。</span><span class="sxs-lookup"><span data-stu-id="73a18-159">With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and VSTS within the chat stream in their team.</span></span>

| <span data-ttu-id="73a18-160">询问你自己</span><span class="sxs-lookup"><span data-stu-id="73a18-160">Ask yourself</span></span> | <span data-ttu-id="73a18-161">操作</span><span class="sxs-lookup"><span data-stu-id="73a18-161">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="73a18-162">是否希望允许用户创建自定义连接器？</span><span class="sxs-lookup"><span data-stu-id="73a18-162">Do I want to allow users to create custom connectors?</span></span>|<span data-ttu-id="73a18-163">有关详细信息，请参阅[在 Teams 中使用 Office 365 和自定义连接器](office-365-custom-connectors.md)。</span><span class="sxs-lookup"><span data-stu-id="73a18-163">For more information, see [Use Office 365 and custom connectors in Teams](office-365-custom-connectors.md).</span></span>|
|||

## <a name="additional-deployment-decisions"></a><span data-ttu-id="73a18-164">其他部署决策</span><span class="sxs-lookup"><span data-stu-id="73a18-164">Additional deployment decisions</span></span>

<span data-ttu-id="73a18-165">你可能需要根据组织的需求和配置更改这些设置。</span><span class="sxs-lookup"><span data-stu-id="73a18-165">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="activity-reports"></a><span data-ttu-id="73a18-166">活动报告</span><span class="sxs-lookup"><span data-stu-id="73a18-166">Activity reports</span></span>

<span data-ttu-id="73a18-167">你可以使用活动报告来查看组织中的用户使用 Teams 的情况。</span><span class="sxs-lookup"><span data-stu-id="73a18-167">You can use activity reports to see how users in your organization are using Teams.</span></span> <span data-ttu-id="73a18-168">例如，如果某些用户尚未使用 Teams，他们可能不知道如何开始使用或了解如何使用 Teams 提高效率和改善协作。</span><span class="sxs-lookup"><span data-stu-id="73a18-168">For example, if some don’t use Teams yet, they might not know how to get started or understand how they can use Teams to be more productive and collaborative.</span></span> <span data-ttu-id="73a18-169">组织可以使用活动报告来决定在何处优先安排培训和沟通工作。</span><span class="sxs-lookup"><span data-stu-id="73a18-169">Your organization can use the activity reports to decide where to prioritize training and communication efforts.</span></span> <span data-ttu-id="73a18-170">若要查看活动报告，你必须是 Office 365 中的全局管理员、Teams 服务管理员或 Skype for Business 管理员。</span><span class="sxs-lookup"><span data-stu-id="73a18-170">To view activity reports, you must be a global admin in Office 365, Teams service admin, or Skype for Business admin.</span></span>

| <span data-ttu-id="73a18-171">询问你自己</span><span class="sxs-lookup"><span data-stu-id="73a18-171">Ask yourself</span></span> | <span data-ttu-id="73a18-172">操作</span><span class="sxs-lookup"><span data-stu-id="73a18-172">Action</span></span> |
|--------------|--------|
| <br><span data-ttu-id="73a18-173">谁需要查看活动报告，他们是否有查看这些报告的正确权限？</span><span class="sxs-lookup"><span data-stu-id="73a18-173">Who needs to see the activity reports, and do they have the correct permissions to view them?</span></span> |<ul><li><span data-ttu-id="73a18-174">如果不想为用户分配管理员角色，则可以[分配报告阅读者角色](teams-activity-reports.md#reports-reader-role)。</span><span class="sxs-lookup"><span data-stu-id="73a18-174">If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</span></span></li><li><span data-ttu-id="73a18-175">有关在 Azure Active Directory 中分配管理员角色的信息，请参阅[角色和权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)以及[查看和分配角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</span><span class="sxs-lookup"><span data-stu-id="73a18-175">See [Roles and permissions](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal) for information about assigning admin roles in Azure Active Directory.</span></span></li></ul> |
|||


## <a name="next-steps"></a><span data-ttu-id="73a18-176">后续步骤</span><span class="sxs-lookup"><span data-stu-id="73a18-176">Next steps</span></span>
- <span data-ttu-id="73a18-177">[推动采用](adopt-microsoft-teams-landing-page.md)特别推荐的应用，例如 Planner。</span><span class="sxs-lookup"><span data-stu-id="73a18-177">[Drive adoption](adopt-microsoft-teams-landing-page.md) of featured apps, such as Planner.</span></span>
- [<span data-ttu-id="73a18-178">部署会议</span><span class="sxs-lookup"><span data-stu-id="73a18-178">Roll out meetings & conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)
- [<span data-ttu-id="73a18-179">部署云语音</span><span class="sxs-lookup"><span data-stu-id="73a18-179">Roll out cloud voice</span></span>](cloud-voice-landing-page.md)


