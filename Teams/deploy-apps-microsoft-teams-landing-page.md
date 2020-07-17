---
title: Microsoft Teams 中的应用、聊天机器人和连接器
ms.reviewer: ''
description: 了解应用、聊天机器人和连接器，以及如何根据组织的情况和业务需求决定在 Microsoft Teams 中部署其中的哪些。
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: admin
ms.date: 01/28/2019
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bf2e7304fc452478da57bad003fffc5193353c8b
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085818"
---
# <a name="apps-bots--connectors-in-microsoft-teams"></a><span data-ttu-id="48065-103">Microsoft Teams 中的应用、聊天机器人和连接器</span><span class="sxs-lookup"><span data-stu-id="48065-103">Apps, bots, & connectors in Microsoft Teams</span></span>

<span data-ttu-id="48065-104">应用使你能通过收藏夹服务查找内容，并就在 Teams 中分享内容。</span><span class="sxs-lookup"><span data-stu-id="48065-104">Apps let you find content from your favorite services and share it right in Teams.</span></span> <span data-ttu-id="48065-105">应用可帮助你执行某些操作，例如将服务固定在频道的顶部、与聊天机器人聊天，或者共享和分配任务。</span><span class="sxs-lookup"><span data-stu-id="48065-105">They help you do things such as pin services at the top of a channel, chat with bots, or share and assign tasks.</span></span> <span data-ttu-id="48065-106">若要了解详细信息，请阅读 [Teams 中的应用概述](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)。</span><span class="sxs-lookup"><span data-stu-id="48065-106">To learn more, read [Overview of apps in Teams](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0).</span></span>

<span data-ttu-id="48065-107">我们建议你在 Teams 的初步部署中加入特别推荐的应用 - 例如 Planner。</span><span class="sxs-lookup"><span data-stu-id="48065-107">We recommend that you include our featured apps - such as Planner - in your initial Teams rollout.</span></span> <span data-ttu-id="48065-108">在推动 Teams 采用的过程中添加其他应用、聊天机器人和连接器。</span><span class="sxs-lookup"><span data-stu-id="48065-108">Add other apps, bots, & connectors as you drive Teams adoption.</span></span>

<span data-ttu-id="48065-109">此外，还提供用于创建自定义应用程序的选项。</span><span class="sxs-lookup"><span data-stu-id="48065-109">You also have the option of creating your own custom apps.</span></span> <span data-ttu-id="48065-110">有关详细信息，请参阅“[开发人员文档](/microsoftteams/platform/overview)”。</span><span class="sxs-lookup"><span data-stu-id="48065-110">See our [developer documentation](/microsoftteams/platform/overview) for more information.</span></span>

## <a name="apps-deployment-decisions"></a><span data-ttu-id="48065-111">应用部署决策</span><span class="sxs-lookup"><span data-stu-id="48065-111">Apps deployment decisions</span></span>

<span data-ttu-id="48065-112">Teams 为组织提供了现成的出色协作体验，并且大多数组织发现默认设置适合它们。</span><span class="sxs-lookup"><span data-stu-id="48065-112">Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them.</span></span> <span data-ttu-id="48065-113">本文可帮助你决定是否要根据组织的情况和业务需求更改任何默认设置，然后引导你完成每项更改。</span><span class="sxs-lookup"><span data-stu-id="48065-113">This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="48065-114">我们将这些设置分为两组：首先是[你更有可能更改的一组核心设置](#core-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="48065-114">We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="48065-115">第二组包括你可能希望根据组织的需求配置的[其他设置](#additional-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="48065-115">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="48065-116">核心部署决策</span><span class="sxs-lookup"><span data-stu-id="48065-116">Core deployment decisions</span></span>

<span data-ttu-id="48065-117">以下是大多数组织在默认设置不适合的情况下想要更改的应用设置。</span><span class="sxs-lookup"><span data-stu-id="48065-117">These are the apps settings that most organizations want to change (if the Teams default settings don't work for them).</span></span>

### <a name="app-availability-settings"></a><span data-ttu-id="48065-118">应用可用性设置</span><span class="sxs-lookup"><span data-stu-id="48065-118">App availability settings</span></span> 

<span data-ttu-id="48065-119">Teams 提供了一些由 Microsoft 和第三方发布的应用来吸引客户、支持高效工作，而且 Teams 中还集成了常用的业务服务。</span><span class="sxs-lookup"><span data-stu-id="48065-119">Teams provides a number of apps published by Microsoft and by third parties to engage users, support productivity, and integrate commonly used business services into Teams.</span></span> <span data-ttu-id="48065-120">从 Teams 应用商店获取应用。</span><span class="sxs-lookup"><span data-stu-id="48065-120">Get apps from the Teams Store.</span></span> <span data-ttu-id="48065-121">默认情况下，所有应用（包括你通过 [Teams 应用商店审批流程](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process)提交的自定义应用）均对所有用户开启。</span><span class="sxs-lookup"><span data-stu-id="48065-121">By default, all apps, including custom apps that you've submitted via the [Teams Store approval process](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), are turned on for all users.</span></span> <span data-ttu-id="48065-122">例如，用户可以使用 Planner 应用在 Teams 中构建和管理团队任务。</span><span class="sxs-lookup"><span data-stu-id="48065-122">For example, users can use the Planner app to build and manage team tasks in Teams.</span></span>

<span data-ttu-id="48065-123">默认情况下，所有 Microsoft 提供的应用和自定义应用均可用，且你可启用或关闭单独的应用。</span><span class="sxs-lookup"><span data-stu-id="48065-123">By default, all Microsoft-provided and custom apps are available, and you can turn individual apps on or off.</span></span> <span data-ttu-id="48065-124">可通过一项全组织范围内的设置来为整个组织启用或关闭所有自定义应用。</span><span class="sxs-lookup"><span data-stu-id="48065-124">There's an org-wide setting that lets you turn all custom apps on or off for your entire organization.</span></span>

| <span data-ttu-id="48065-125">询问您自己</span><span class="sxs-lookup"><span data-stu-id="48065-125">Ask yourself</span></span> | <span data-ttu-id="48065-126">操作</span><span class="sxs-lookup"><span data-stu-id="48065-126">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="48065-127">是否要更改默认 Teams 应用设置？</span><span class="sxs-lookup"><span data-stu-id="48065-127">Will you change the default Teams apps settings?</span></span> | <span data-ttu-id="48065-128">要详细了解可用于管理组织内部应用的策略和设置，请参阅 [Microsoft Teams 中针对应用的管理员设置](admin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="48065-128">For more information about policies and settings that you can use to manage apps in your organization, see [Admin settings for apps in Microsoft Teams](admin-settings.md).</span></span>|
|||

### <a name="app-permissions-and-other-considerations"></a><span data-ttu-id="48065-129">应用权限和其他注意事项</span><span class="sxs-lookup"><span data-stu-id="48065-129">App permissions and other considerations</span></span>

<span data-ttu-id="48065-130">应用由用户允许，并由管理员或 IT 专业人员通过策略进行管理。</span><span class="sxs-lookup"><span data-stu-id="48065-130">Apps are consented to by users and managed by the admin or IT pro through policies.</span></span> <span data-ttu-id="48065-131">但是，在大多数情况下，应用的权限和风险状况是在应用本身内定义的。</span><span class="sxs-lookup"><span data-stu-id="48065-131">However, for the most part, an app's permissions and risk profile are defined in the app itself.</span></span> 

| <span data-ttu-id="48065-132">询问你自己</span><span class="sxs-lookup"><span data-stu-id="48065-132">Ask yourself</span></span> | <span data-ttu-id="48065-133">操作</span><span class="sxs-lookup"><span data-stu-id="48065-133">Action</span></span> |
|--------------|--------|
|<br><span data-ttu-id="48065-134">希望允许访问哪些应用？</span><span class="sxs-lookup"><span data-stu-id="48065-134">Which apps do I want to allow access to?</span></span> <span data-ttu-id="48065-135">不希望允许访问哪些应用？</span><span class="sxs-lookup"><span data-stu-id="48065-135">Which ones do I not want to allow access to?</span></span>  | <ul><li><span data-ttu-id="48065-136">有关在允许访问应用、聊天机器人、选项卡或连接器时要考虑的事项的列表，请参阅 [Microsoft Teams 应用权限和注意事项](app-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="48065-136">See [Microsoft Teams apps permissions and considerations](app-permissions.md) for a list of things you should consider when allowing access to an app, bot, tab, or connector.</span></span></li><li><span data-ttu-id="48065-137">有关将应用提供给组织中的用户的信息，请参阅“[在 Microsoft Teams 管理中心管理应用](manage-apps.md)”。</span><span class="sxs-lookup"><span data-stu-id="48065-137">See [Manage your apps in the Microsoft Teams admin center](manage-apps.md) for information about making an app available to users in your organization.</span></span></li></ul>|
|||

### <a name="bots-for-private-chats-and-channels"></a><span data-ttu-id="48065-138">用于私人聊天和频道的聊天机器人</span><span class="sxs-lookup"><span data-stu-id="48065-138">Bots for private chats and channels</span></span>

<span data-ttu-id="48065-139">聊天机器人是自动化程序，它们可响应查询或者提供有关用户感兴趣或想要及时了解的详细信息的更新和通知。</span><span class="sxs-lookup"><span data-stu-id="48065-139">Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about.</span></span> <span data-ttu-id="48065-140">聊天机器人允许用户与云服务交互，例如任务管理、计划以及在 Teams 聊天中投票。</span><span class="sxs-lookup"><span data-stu-id="48065-140">Bots allow users to interact with cloud services such as task management, scheduling, and polling in a Teams chat.</span></span> <span data-ttu-id="48065-141">Teams 支持在私人聊天和频道中使用聊天机器人。</span><span class="sxs-lookup"><span data-stu-id="48065-141">Teams supports bots in private chats and channels.</span></span> <span data-ttu-id="48065-142">管理员可以控制是否允许在 Microsoft 365 和 Office 365 组织中使用机器人。</span><span class="sxs-lookup"><span data-stu-id="48065-142">Administrators can control whether the use of bots is allowed in a Microsoft 365 or Office 365 organization.</span></span>

| <span data-ttu-id="48065-143">询问你自己</span><span class="sxs-lookup"><span data-stu-id="48065-143">Ask yourself</span></span> | <span data-ttu-id="48065-144">Action</span><span class="sxs-lookup"><span data-stu-id="48065-144">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="48065-145">是否要允许在我的组织中使用自定义聊天机器人？</span><span class="sxs-lookup"><span data-stu-id="48065-145">Do I want to allow custom bots in my organization?</span></span>|<span data-ttu-id="48065-146">有关添加聊天机器人的详细信息，请参阅[为 Microsoft Teams 中的私人聊天和频道添加聊天机器人](add-bots.md)。</span><span class="sxs-lookup"><span data-stu-id="48065-146">For more information about adding bots, see [Add bots for private chats and channels in Microsoft Teams](add-bots.md).</span></span> <span data-ttu-id="48065-147">有关开启或关闭聊天机器人的信息，请参阅[在 Microsoft Teams 中管理应用设置](admin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="48065-147">For information about turning custom bots on or off, see [Admin settings for apps in Microsoft Teams](admin-settings.md).</span></span>|
|||

### <a name="built-in-and-custom-tabs"></a><span data-ttu-id="48065-148">内置和自定义选项卡</span><span class="sxs-lookup"><span data-stu-id="48065-148">Built-in and custom tabs</span></span>

<span data-ttu-id="48065-149">所有者和团队成员可以向频道、私人聊天和群组聊天中添加选项卡，以帮助集成其云服务。</span><span class="sxs-lookup"><span data-stu-id="48065-149">Owners and team members can add tabs to a channel, private chat, and group chat to help integrate their cloud services.</span></span> <span data-ttu-id="48065-150">添加选项卡可帮助用户访问并管理自己需要或最常用的数据。</span><span class="sxs-lookup"><span data-stu-id="48065-150">Add tabs to help users access and manage the data they need or use the most.</span></span> <span data-ttu-id="48065-151">在频道中，默认情况下已创建了“对话”和“文件”选项卡。</span><span class="sxs-lookup"><span data-stu-id="48065-151">In channels, the Conversations and Files tabs are created by default.</span></span> <span data-ttu-id="48065-152">在私人聊天中，默认情况下已创建了“对话”、“文件”、“组织”和“活动”选项卡。</span><span class="sxs-lookup"><span data-stu-id="48065-152">In every private chat, the Conversations, Files, Organization, and Activity tabs are created by default.</span></span> <span data-ttu-id="48065-153">除了这些内置选项卡外，你还可以设计和添加自定义选项卡。</span><span class="sxs-lookup"><span data-stu-id="48065-153">In addition to these built-in tabs, you can design and add custom tabs.</span></span> <span data-ttu-id="48065-154">若要了解如何为你的组织开启或关闭 Teams 应用，请阅读[在 Teams 中管理应用设置](admin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="48065-154">To learn about turning Teams apps on or off for your organization, read [Admin settings for apps in Teams](admin-settings.md).</span></span>

| <span data-ttu-id="48065-155">询问你自己</span><span class="sxs-lookup"><span data-stu-id="48065-155">Ask yourself</span></span> | <span data-ttu-id="48065-156">Action</span><span class="sxs-lookup"><span data-stu-id="48065-156">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="48065-157">是否要允许在我的组织中使用自定义选项卡？</span><span class="sxs-lookup"><span data-stu-id="48065-157">Do I want to allow custom tabs in my organization?</span></span>|<span data-ttu-id="48065-158">有关详细信息，请参阅[在 Teams 中使用内置和自定义选项卡](built-in-custom-tabs.md)。</span><span class="sxs-lookup"><span data-stu-id="48065-158">For more information, see [Use built-in and custom tabs in Teams](built-in-custom-tabs.md).</span></span>|
|||

### <a name="custom-connectors"></a><span data-ttu-id="48065-159">自定义连接器</span><span class="sxs-lookup"><span data-stu-id="48065-159">Custom connectors</span></span>

<span data-ttu-id="48065-160">连接器可将内容和更新从你经常使用的服务直接传递到频道中，从而使你的团队能够获得最新内容。</span><span class="sxs-lookup"><span data-stu-id="48065-160">Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel.</span></span> <span data-ttu-id="48065-161">通过使用连接器，你的 Teams 用户可以在其 Teams 聊天中接收来自常用服务（例如 Twitter、Trello、Wunderlist、GitHub 和 Azure DevOps Services）的更新。</span><span class="sxs-lookup"><span data-stu-id="48065-161">With connectors, your Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.</span></span>

| <span data-ttu-id="48065-162">询问你自己</span><span class="sxs-lookup"><span data-stu-id="48065-162">Ask yourself</span></span> | <span data-ttu-id="48065-163">操作</span><span class="sxs-lookup"><span data-stu-id="48065-163">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="48065-164">是否希望允许用户创建自定义连接器？</span><span class="sxs-lookup"><span data-stu-id="48065-164">Do I want to allow users to create custom connectors?</span></span>|<span data-ttu-id="48065-165">有关详细信息，请参阅[在 Teams 中使用自定义连接器](office-365-custom-connectors.md)。</span><span class="sxs-lookup"><span data-stu-id="48065-165">For more information, see [Use custom connectors in Teams](office-365-custom-connectors.md).</span></span>|
|||

## <a name="additional-deployment-decisions"></a><span data-ttu-id="48065-166">其他部署决策</span><span class="sxs-lookup"><span data-stu-id="48065-166">Additional deployment decisions</span></span>

<span data-ttu-id="48065-167">你可能需要根据组织的需求和配置更改这些设置。</span><span class="sxs-lookup"><span data-stu-id="48065-167">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="activity-reports"></a><span data-ttu-id="48065-168">活动报告</span><span class="sxs-lookup"><span data-stu-id="48065-168">Activity reports</span></span>

<span data-ttu-id="48065-169">你可以使用活动报告来查看组织中的用户使用 Teams 的情况。</span><span class="sxs-lookup"><span data-stu-id="48065-169">You can use activity reports to see how users in your organization are using Teams.</span></span> <span data-ttu-id="48065-170">例如，如果某些用户尚未使用 Teams，他们可能不知道如何开始使用或了解如何使用 Teams 提高工作效率和改善协作。</span><span class="sxs-lookup"><span data-stu-id="48065-170">For example, if some don't use Teams yet, they might not know how to get started or understand how they can use Teams to be more productive and collaborative.</span></span> <span data-ttu-id="48065-171">组织可以使用活动报告来决定在何处优先安排培训和沟通工作。</span><span class="sxs-lookup"><span data-stu-id="48065-171">Your organization can use the activity reports to decide where to prioritize training and communication efforts.</span></span> <span data-ttu-id="48065-172">若要查看活动报告，你必须是 Microsoft 365 或 Office 365 中的全局管理员、Teams 服务管理员或 Skype for Business 管理员。</span><span class="sxs-lookup"><span data-stu-id="48065-172">To view activity reports, you must be a global admin in Microsoft 365 or Office 365, Teams service admin, or Skype for Business admin.</span></span>

| <span data-ttu-id="48065-173">询问你自己</span><span class="sxs-lookup"><span data-stu-id="48065-173">Ask yourself</span></span> | <span data-ttu-id="48065-174">操作</span><span class="sxs-lookup"><span data-stu-id="48065-174">Action</span></span> |
|--------------|--------|
| <br><span data-ttu-id="48065-175">谁需要查看活动报告，他们是否有查看这些报告的正确权限？</span><span class="sxs-lookup"><span data-stu-id="48065-175">Who needs to see the activity reports, and do they have the correct permissions to view them?</span></span> |<ul><li><span data-ttu-id="48065-176">如果不想为用户分配管理员角色，则可以[分配报告阅读者角色](teams-activity-reports.md#reports-reader-role)。</span><span class="sxs-lookup"><span data-stu-id="48065-176">If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</span></span></li><li><span data-ttu-id="48065-177">有关在 Azure Active Directory 中分配管理员角色的信息，请参阅[角色和权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)以及[查看和分配角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)。</span><span class="sxs-lookup"><span data-stu-id="48065-177">See [Roles and permissions](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal) for information about assigning admin roles in Azure Active Directory.</span></span></li></ul> |
|||

### <a name="app-templates"></a><span data-ttu-id="48065-178">应用模板</span><span class="sxs-lookup"><span data-stu-id="48065-178">App templates</span></span>

<span data-ttu-id="48065-179">应用模板是适用于 Microsoft Teams 的生产就绪型应用，它们由社区驱动、开放源代码且可在 GitHub 上获取。</span><span class="sxs-lookup"><span data-stu-id="48065-179">App templates are production-ready apps for Microsoft Teams that are community driven, open-source, and available on GitHub.</span></span> <span data-ttu-id="48065-180">每个模板都包含为组织部署和安装该应用的详细说明，从而提供了一个可立即安装并开始使用的即用型应用。</span><span class="sxs-lookup"><span data-stu-id="48065-180">Each contains detailed instructions for deploying and installing that app for your organization, providing a ready-to-use app that you can install and begin using immediately.</span></span> <span data-ttu-id="48065-181">此外，还提供完整的源代码，以便你可以对其进行详细的研究，或获取相应代码并进行更改以满足你的特定需求。</span><span class="sxs-lookup"><span data-stu-id="48065-181">The complete source code is available as well, so you can explore it in detail, or fork the code and alter it to meet your specific needs.</span></span>

| <span data-ttu-id="48065-182">询问你自己</span><span class="sxs-lookup"><span data-stu-id="48065-182">Ask yourself</span></span> | <span data-ttu-id="48065-183">Action</span><span class="sxs-lookup"><span data-stu-id="48065-183">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="48065-184">我是否想要安装任何 Teams 应用模板，例如 Icebreaker？</span><span class="sxs-lookup"><span data-stu-id="48065-184">Do I want to install any Teams app templates, such as Icebreaker?</span></span> |<span data-ttu-id="48065-185">若要了解详细信息，请参阅[适用于 Teams 的应用模板](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="48065-185">To learn more, read [App templates for Teams](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span>|
|||


## <a name="next-steps"></a><span data-ttu-id="48065-186">后续步骤</span><span class="sxs-lookup"><span data-stu-id="48065-186">Next steps</span></span>
- <span data-ttu-id="48065-187">[推动采用](adopt-microsoft-teams-landing-page.md)特别推荐的应用，例如 Planner。</span><span class="sxs-lookup"><span data-stu-id="48065-187">[Drive adoption](adopt-microsoft-teams-landing-page.md) of featured apps, such as Planner.</span></span>
- [<span data-ttu-id="48065-188">部署会议</span><span class="sxs-lookup"><span data-stu-id="48065-188">Roll out meetings & conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)
- [<span data-ttu-id="48065-189">部署云语音</span><span class="sxs-lookup"><span data-stu-id="48065-189">Roll out cloud voice</span></span>](cloud-voice-landing-page.md)


