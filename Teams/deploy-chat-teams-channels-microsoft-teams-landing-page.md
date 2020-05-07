---
title: Microsoft Teams 中的聊天、团队、频道和应用
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 根据组织的配置文件和业务要求在 Microsoft Teams 中部署聊天、团队、频道和应用的分步指导。
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
appliesto:
- Microsoft Teams
- seo-marvel-apr2020
ms.openlocfilehash: e8e2f2b09ab448e0460c82af0fba776f2ce1126a
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44041839"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a><span data-ttu-id="de20b-103">Microsoft Teams 中的聊天、团队、频道和应用</span><span class="sxs-lookup"><span data-stu-id="de20b-103">Chat, teams, channels, & apps in Microsoft Teams</span></span>

<span data-ttu-id="de20b-104">Teams 为组织提供了现成的出色协作体验，并且大多数组织发现默认设置适合它们。</span><span class="sxs-lookup"><span data-stu-id="de20b-104">Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them.</span></span> <span data-ttu-id="de20b-105">本文可帮助你决定是否要根据组织的情况和业务需求更改任何默认设置，然后引导你完成每项更改。</span><span class="sxs-lookup"><span data-stu-id="de20b-105">This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="de20b-106">我们将这些设置分为两组：首先是[你更有可能更改的一组核心设置](#core-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="de20b-106">We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="de20b-107">第二组包括你可能希望根据组织的需求配置的[其他设置](#additional-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="de20b-107">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span> 

<span data-ttu-id="de20b-108">首先，请观看我们的“Teams 聊天、团队和频道”短视频（4 分 30 秒）：</span><span class="sxs-lookup"><span data-stu-id="de20b-108">To get started, watch our short Teams chat, teams, and channels video (4:30 minutes):</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj]

<span data-ttu-id="de20b-109">*2019年11月新增功能*</span><span class="sxs-lookup"><span data-stu-id="de20b-109">*New in November 2019*</span></span>
 - <span data-ttu-id="de20b-110">现在可[使用 Advisor for Teams（预览版）帮助你推出 Microsoft Teams](use-advisor-teams-roll-out.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-110">You can now [use Advisor for Teams (preview) to help you roll out Microsoft Teams](use-advisor-teams-roll-out.md).</span></span> <span data-ttu-id="de20b-111">Advisor for Teams（预览版）为你提供 Teams 推出的分步指导。</span><span class="sxs-lookup"><span data-stu-id="de20b-111">Advisor for Teams (preview) walks you through your Teams rollout.</span></span> <span data-ttu-id="de20b-112">它将评估 Office 365 环境并确定更新或修改所需的最常用配置，帮助你成功推出 Teams。</span><span class="sxs-lookup"><span data-stu-id="de20b-112">It assesses your Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span>
 - <span data-ttu-id="de20b-113">[Microsoft YouTube 频道 IT 团队基础知识](https://aka.ms/MicrosoftTeamsforIT)，包括简短（8-10 分钟）的视频，显示如何推出、配置和管理团队。</span><span class="sxs-lookup"><span data-stu-id="de20b-113">[Microsoft Teams Essentials for IT YouTube channel](https://aka.ms/MicrosoftTeamsforIT), including short (8-10 minute) videos that show you how to roll out, configure, and manage Teams.</span></span>

> [!TIP]
> <span data-ttu-id="de20b-114">我们建议你在 Teams 的初步部署中加入特别推荐的应用 - 例如 Planner。</span><span class="sxs-lookup"><span data-stu-id="de20b-114">We recommend that you include our featured apps -- such as Planner -- in your initial Teams rollout.</span></span> <span data-ttu-id="de20b-115">在推动 Teams 采用的过程中添加其他[应用、聊天机器人和连接器](deploy-apps-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-115">Add other [apps, bots, and connectors](deploy-apps-microsoft-teams-landing-page.md) as you drive Teams adoption.</span></span>

## <a name="chat-deployment-prerequisites"></a><span data-ttu-id="de20b-116">聊天部署先决条件</span><span class="sxs-lookup"><span data-stu-id="de20b-116">Chat deployment prerequisites</span></span>

<span data-ttu-id="de20b-117">在整个组织内部署 Teams 之前，请花些时间确认你环境已准备好使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="de20b-117">Before you roll out Teams across your organization, take time to confirm that your environment is ready for Teams.</span></span> <span data-ttu-id="de20b-118">请查看[为 Teams 准备贵组织的网络](prepare-network.md)，并对环境进行必要的更改。</span><span class="sxs-lookup"><span data-stu-id="de20b-118">Review [Prepare your organization's network for Teams](prepare-network.md) and make any required changes to your environment.</span></span>

|<span data-ttu-id="de20b-119">询问你自己</span><span class="sxs-lookup"><span data-stu-id="de20b-119">Ask yourself</span></span>|<span data-ttu-id="de20b-120">操作</span><span class="sxs-lookup"><span data-stu-id="de20b-120">Action</span></span> |
|------------|-------|
|<span data-ttu-id="de20b-121">我的组织是否已准备好部署 Teams？</span><span class="sxs-lookup"><span data-stu-id="de20b-121">Is my organization ready to roll out Teams?</span></span>|<span data-ttu-id="de20b-122">为了回答此问题，请参阅：</span><span class="sxs-lookup"><span data-stu-id="de20b-122">To answer this question, see:</span></span> <ul><li>[<span data-ttu-id="de20b-123">为 Teams 准备贵组织的网络</span><span class="sxs-lookup"><span data-stu-id="de20b-123">Prepare your organization's network for Teams</span></span>](prepare-network.md)</li><li>[<span data-ttu-id="de20b-124">Office 365 URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="de20b-124">Office 365 URLs and IP address ranges</span></span>](office-365-urls-ip-address-ranges.md)</li><li>[<span data-ttu-id="de20b-125">在创建团队时规划 Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="de20b-125">Plan for Microsoft 365 Groups when creating teams</span></span>](plan-office-365-groups.md)</li></ul>|
|||

## <a name="core-deployment-decisions"></a><span data-ttu-id="de20b-126">核心部署决策</span><span class="sxs-lookup"><span data-stu-id="de20b-126">Core deployment decisions</span></span>

<span data-ttu-id="de20b-127">以下是大多数组织在默认设置不适合的情况下想要更改的聊天、团队和频道设置。</span><span class="sxs-lookup"><span data-stu-id="de20b-127">These are the chat, teams, and channels settings that most organizations want to change (if the default settings don't work for them).</span></span>

### <a name="teams-administrators"></a><span data-ttu-id="de20b-128">Teams 管理员</span><span class="sxs-lookup"><span data-stu-id="de20b-128">Teams administrators</span></span>

<span data-ttu-id="de20b-129">Teams 提供了一组可用于为组织管理 Teams 的自定义管理员角色。</span><span class="sxs-lookup"><span data-stu-id="de20b-129">Teams provides a set of custom administrator roles that can be used to manage Teams for your organization.</span></span> <span data-ttu-id="de20b-130">这些角色为管理员提供各种能力。</span><span class="sxs-lookup"><span data-stu-id="de20b-130">The roles provide various capabilities to administrators.</span></span>

| <span data-ttu-id="de20b-131">询问你自己</span><span class="sxs-lookup"><span data-stu-id="de20b-131">Ask yourself</span></span> | <span data-ttu-id="de20b-132">操作</span><span class="sxs-lookup"><span data-stu-id="de20b-132">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="de20b-133">将为谁分配 Teams 通信管理员角色？</span><span class="sxs-lookup"><span data-stu-id="de20b-133">Who will be assigned the Teams Communications Administrator role?</span></span>|<span data-ttu-id="de20b-134">若要详细了解 Teams 管理员角色，请参阅[使用 Microsoft Teams 管理员角色来管理 Teams](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-134">To learn more about Teams administrator roles see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>|
|<span data-ttu-id="de20b-135">将为谁分配 Teams 通信支持工程师角色？</span><span class="sxs-lookup"><span data-stu-id="de20b-135">Who will be assigned the Teams Communications Support Engineer role?</span></span>|<span data-ttu-id="de20b-136">若要分配管理员角色，请参阅[使用 Active Directory 为用户分配管理员和非管理员角色](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="de20b-136">To assign admin roles, see [Assign administrator and non-administrator roles to users with Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>|
|<span data-ttu-id="de20b-137">将为谁分配 Teams 通信支持专家角色？</span><span class="sxs-lookup"><span data-stu-id="de20b-137">Who will be assigned the Teams Communications Support Specialist role?</span></span>||
|||

### <a name="teams-owners-and-members"></a><span data-ttu-id="de20b-138">Teams 所有者和成员</span><span class="sxs-lookup"><span data-stu-id="de20b-138">Teams owners and members</span></span>

<span data-ttu-id="de20b-139">除了管理员角色之外，Teams 还允许你分配所有者和成员用户角色，并选择他们提供审阅人功能（如果已设置审核功能）以控制谁可以在渠道中执行特定操作。</span><span class="sxs-lookup"><span data-stu-id="de20b-139">In addition to administrator roles, Teams lets you assign owner and member user roles, and selectively give them moderator capabilities (if moderation has been set up) to control who can perform certain actions within a channel.</span></span> <span data-ttu-id="de20b-140">通过审核功能，你可以控制谁可以在频道中发表新帖子，添加和删除作为审阅人的团队成员，以及控制团队成员能否回复现有频道消息。</span><span class="sxs-lookup"><span data-stu-id="de20b-140">Moderation allows you to control who can start new posts in a channel, add and remove team members as moderators, and control whether team members can reply to existing channel messages.</span></span>

|<span data-ttu-id="de20b-141">询问你自己</span><span class="sxs-lookup"><span data-stu-id="de20b-141">Ask yourself</span></span>|<span data-ttu-id="de20b-142">操作</span><span class="sxs-lookup"><span data-stu-id="de20b-142">Action</span></span> |
|------------|-------|
|<span data-ttu-id="de20b-143">应该为每个角色分配哪些人员？</span><span class="sxs-lookup"><span data-stu-id="de20b-143">Who should be assigned to each role?</span></span> | <span data-ttu-id="de20b-144">若要比较每个角色的功能，请参阅[在 Microsoft Teams 中分配团队所有者、审阅人和成员](assign-roles-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-144">To compare the capabilities of each role, see [Assign team owners, moderators, and members in Microsoft Teams](assign-roles-permissions.md).</span></span>
|<span data-ttu-id="de20b-145">如何分配用户角色？</span><span class="sxs-lookup"><span data-stu-id="de20b-145">How do I assign a user role?</span></span> | <span data-ttu-id="de20b-146">若要分配或更改角色，请参阅[分配用户角色](assign-roles-permissions.md#assign-a-user-role)。</span><span class="sxs-lookup"><span data-stu-id="de20b-146">To assign or change a role, see [Assign a user role](assign-roles-permissions.md#assign-a-user-role).</span></span>
|<span data-ttu-id="de20b-147">我是否需要控制谁可以在频道中发布和答复？</span><span class="sxs-lookup"><span data-stu-id="de20b-147">Do I need to control who can post and reply in a channel?</span></span> | <span data-ttu-id="de20b-148">若要配置审核，请参阅[在 Microsoft Teams 中设置和管理频道审核](manage-channel-moderation-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-148">To configure moderation, see [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md).</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="de20b-149">消息策略</span><span class="sxs-lookup"><span data-stu-id="de20b-149">Messaging policies</span></span>

<span data-ttu-id="de20b-150">消息策略控制为 Teams 中的用户提供哪些聊天和频道消息功能。</span><span class="sxs-lookup"><span data-stu-id="de20b-150">Messaging policies control which chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="de20b-151">例如，谁可以编辑和删除已发送的消息、谁可以使用聊天、谁可以在对话中使用 Meme，等等。</span><span class="sxs-lookup"><span data-stu-id="de20b-151">For example, who can edit and delete sent messages, who can use chat, who can use memes in conversations, and more.</span></span> <span data-ttu-id="de20b-152">默认情况下，会为用户分配全局消息策略，所有功能均**开启**。</span><span class="sxs-lookup"><span data-stu-id="de20b-152">By default, users are assigned the global messaging policy and all features are **On**.</span></span> <span data-ttu-id="de20b-153">可以使用默认全局策略，或者为组织中的人员创建一个或多个自定义消息策略。</span><span class="sxs-lookup"><span data-stu-id="de20b-153">You can use the default global policy or create one or more custom messaging policies for people in your organization.</span></span> 

|<span data-ttu-id="de20b-154">询问你自己</span><span class="sxs-lookup"><span data-stu-id="de20b-154">Ask yourself</span></span>|<span data-ttu-id="de20b-155">操作</span><span class="sxs-lookup"><span data-stu-id="de20b-155">Action</span></span> |
|------------|-------|
|<span data-ttu-id="de20b-156">是否要自定义全局消息策略？</span><span class="sxs-lookup"><span data-stu-id="de20b-156">Will I customize the global messaging policy?</span></span>|<span data-ttu-id="de20b-157">有关使用 Microsoft Teams 管理中心来更改全局消息策略或添加新策略的信息，请参阅[在 Teams 中管理消息策略](messaging-policies-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-157">For information about using the Microsoft Teams admin center to change the global messaging policy or add a new policy, see [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>|
|<span data-ttu-id="de20b-158">是否需要多个消息策略？</span><span class="sxs-lookup"><span data-stu-id="de20b-158">Do I require multiple messaging policies?</span></span>|<span data-ttu-id="de20b-159">若要在 PowerShell 中创建和分配消息策略，请参阅 [PowerShell 脚本示例 - 创建和分配消息策略](scripts/powershell-script-teams-messaging-policy-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-159">To create and assign a messaging policy in PowerShell, see [PowerShell script sample - Create and assign a messaging policy](scripts/powershell-script-teams-messaging-policy-edu.md).</span></span>|
|<span data-ttu-id="de20b-160">如何确定哪些用户组获取哪些消息策略？</span><span class="sxs-lookup"><span data-stu-id="de20b-160">How will I determine which groups of users get which messaging policy?</span></span>|<span data-ttu-id="de20b-161">若要了解 CsTeamsMessagingPolicy cmdlet，请参阅 [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="de20b-161">To learn about the CsTeamsMessagingPolicy cmdlets, see [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).</span></span>|
||| 

### <a name="external-access"></a><span data-ttu-id="de20b-162">外部访问</span><span class="sxs-lookup"><span data-stu-id="de20b-162">External access</span></span>

<span data-ttu-id="de20b-163">利用外部访问功能（以前称为联合），你的 Teams 和 Skype for Business 用户可以与组织外部的用户通信。</span><span class="sxs-lookup"><span data-stu-id="de20b-163">External access (formerly known as federation) lets your Teams and Skype for Business users communicate with users who are outside of your organization.</span></span> <span data-ttu-id="de20b-164">通过启用此功能并将域添加到允许的列表，你的用户将能与其他域和组织中的用户通信。</span><span class="sxs-lookup"><span data-stu-id="de20b-164">By turning this on and adding domains to the allowed list, your users can communicate with users in other domains and organizations.</span></span><span data-ttu-id="de20b-165">外部访问与来宾访问的不同之处在于，将为整个域（而不是个人）授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="de20b-165"> External access differs from guest access in that an entire domain is given access permission, not an individual.</span></span> <span data-ttu-id="de20b-166">默认情况下会关闭外部访问。</span><span class="sxs-lookup"><span data-stu-id="de20b-166">External access is turned off by default.</span></span>

|<span data-ttu-id="de20b-167">询问你自己</span><span class="sxs-lookup"><span data-stu-id="de20b-167">Ask yourself</span></span>|<span data-ttu-id="de20b-168">操作</span><span class="sxs-lookup"><span data-stu-id="de20b-168">Action</span></span> |
|------------|-------|
|<ul><li><span data-ttu-id="de20b-169">是否要为我的组织启用外部访问？</span><span class="sxs-lookup"><span data-stu-id="de20b-169">Will I turn on external access for my organization?</span></span></li><li><span data-ttu-id="de20b-170">如果启用，是否要限制我的组织可以与哪些域进行通信？</span><span class="sxs-lookup"><span data-stu-id="de20b-170">If enabled, will I limit which domains my organization can communicate with?</span></span></li></ul> |<br><span data-ttu-id="de20b-171">若要启用外部访问，请参阅[规划外部访问](manage-external-access.md#plan-for-external-access)。</span><span class="sxs-lookup"><span data-stu-id="de20b-171">To turn on external access, see [Plan for external access](manage-external-access.md#plan-for-external-access).</span></span>|
|||

### <a name="guest-access"></a><span data-ttu-id="de20b-172">来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="de20b-172">Guest access</span></span>

<span data-ttu-id="de20b-173">Teams 中的来宾访问可让组织外部的个人访问团队和频道。</span><span class="sxs-lookup"><span data-stu-id="de20b-173">Guest access in Teams lets individuals outside your organization access teams and channels.</span></span> <span data-ttu-id="de20b-174">可以使用来宾访问设置来控制来宾用户能够使用或无法使用哪些功能。</span><span class="sxs-lookup"><span data-stu-id="de20b-174">You can use the guest access settings to control which features guest users can or can't use.</span></span> <span data-ttu-id="de20b-175">默认情况下会关闭来宾访问。</span><span class="sxs-lookup"><span data-stu-id="de20b-175">Guest access is turned off by default.</span></span> <span data-ttu-id="de20b-176">若要了解详细信息，请参阅 [Teams 中的来宾访问](https://docs.microsoft.com/microsoftteams/guest-access)。</span><span class="sxs-lookup"><span data-stu-id="de20b-176">To learn more, see [Guest access in Teams](https://docs.microsoft.com/microsoftteams/guest-access).</span></span>

> [!NOTE]
> <span data-ttu-id="de20b-177">有关外部访问和来宾访问的详细信息，请参阅此处 — [与 Microsoft Teams 中其他组织的用户通信](communicate-with-users-from-other-organizations.md)</span><span class="sxs-lookup"><span data-stu-id="de20b-177">For more on External access and Guest access see here - [Communicate with users from other organizations in Microsoft Teams](communicate-with-users-from-other-organizations.md)</span></span>


|<span data-ttu-id="de20b-178">询问你自己</span><span class="sxs-lookup"><span data-stu-id="de20b-178">Ask yourself</span></span>|<span data-ttu-id="de20b-179">操作</span><span class="sxs-lookup"><span data-stu-id="de20b-179">Action</span></span> |
|------------|-------|
|<span data-ttu-id="de20b-180">是否要为我的组织启用来宾访问？</span><span class="sxs-lookup"><span data-stu-id="de20b-180">Will I turn on guest access for my organization?</span></span>|<span data-ttu-id="de20b-181">若要启用来宾访问，请参阅[在 Teams 中启用或禁用来宾访问](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-181">To turn on guest access, see [Turn on or off guest access in Teams](set-up-guests.md).</span></span>|
|<span data-ttu-id="de20b-182">如果启用，是否要自定义可供组织中的来宾使用的功能？</span><span class="sxs-lookup"><span data-stu-id="de20b-182">If enabled, will I customize the features available to guests in my organization?</span></span>|<span data-ttu-id="de20b-183">若要自定义来宾访问功能可用性，请参阅[在 Teams 中授权来宾访问](teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-183">To customize guest access feature availability, see [Authorize guest access in Teams](teams-dependencies.md).</span></span>|
|||

### <a name="teams-settings"></a><span data-ttu-id="de20b-184">Teams 设置</span><span class="sxs-lookup"><span data-stu-id="de20b-184">Teams settings</span></span>

<span data-ttu-id="de20b-185">Teams 设置允许你针对诸如电子邮件集成、云存储选项、组织选项卡、会议室设备设置和搜索范围等功能设置团队。</span><span class="sxs-lookup"><span data-stu-id="de20b-185">Teams settings let you set up your teams for features such as email integration, cloud storage options, organization tab, meeting room device setup, and search scope.</span></span> <span data-ttu-id="de20b-186">更改这些设置时，所做更改将应用于组织中的所有团队。</span><span class="sxs-lookup"><span data-stu-id="de20b-186">When you make changes to these settings, they apply to all the teams in your organization.</span></span><span data-ttu-id="de20b-187">若要了解详细信息，请参阅 [Teams 设置](enable-features-office-365.md#teams-settings)。</span><span class="sxs-lookup"><span data-stu-id="de20b-187"> To learn more, see [Teams settings](enable-features-office-365.md#teams-settings).</span></span>

|<span data-ttu-id="de20b-188">询问你自己</span><span class="sxs-lookup"><span data-stu-id="de20b-188">Ask yourself</span></span>|<span data-ttu-id="de20b-189">操作</span><span class="sxs-lookup"><span data-stu-id="de20b-189">Action</span></span> |
|------------|-------|
|<span data-ttu-id="de20b-190">是否要为我的组织自定义 Teams 设置？</span><span class="sxs-lookup"><span data-stu-id="de20b-190">Will I customize Teams settings for my organization?</span></span> | <span data-ttu-id="de20b-191">若要了解 Teams 设置以及如何自定义这些设置，请参阅 [Teams 设置](enable-features-office-365.md#teams-settings)。</span><span class="sxs-lookup"><span data-stu-id="de20b-191">To learn about Teams settings and how to customize them, see [Teams settings](enable-features-office-365.md#teams-settings).</span></span>|
|||

### <a name="teams-clients"></a><span data-ttu-id="de20b-192">Teams 客户端</span><span class="sxs-lookup"><span data-stu-id="de20b-192">Teams clients</span></span>

<span data-ttu-id="de20b-193">Teams 支持从 Web 到桌面直至移动客户端的多种客户端，默认配置允许用户选择所需的任一客户端。</span><span class="sxs-lookup"><span data-stu-id="de20b-193">Teams supports a number of clients from web to desktop to mobile, and the default configuration lets users choose whichever clients they want.</span></span><span data-ttu-id="de20b-194">若要了解详细信息，请参阅[获取 Teams 客户端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-194"> To learn more, see [Get clients for Teams](get-clients.md).</span></span>

|<span data-ttu-id="de20b-195">询问你自己</span><span class="sxs-lookup"><span data-stu-id="de20b-195">Ask yourself</span></span>|<span data-ttu-id="de20b-196">操作</span><span class="sxs-lookup"><span data-stu-id="de20b-196">Action</span></span> |
|------------|-------|
|<span data-ttu-id="de20b-197">是否要为我的组织自定义 Teams 客户端可用性？</span><span class="sxs-lookup"><span data-stu-id="de20b-197">Will I customize Teams client availability for my organization?</span></span>|<span data-ttu-id="de20b-198">请参阅 [Teams 应用的硬件要求](hardware-requirements-for-the-teams-app.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-198">Check out [Hardware requirements for the Teams app](hardware-requirements-for-the-teams-app.md).</span></span> |
|<span data-ttu-id="de20b-199">是否要为我的组织自定义 Teams 客户端设置？</span><span class="sxs-lookup"><span data-stu-id="de20b-199">Will I customize Teams client settings for my organization?</span></span>|<span data-ttu-id="de20b-200">了解如何[使用 MSI 安装 Teams](msi-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-200">Learn how to [Install Teams using MSI](msi-deployment.md).</span></span>|
|||


### <a name="teams-usage-reporting"></a><span data-ttu-id="de20b-201">Teams 使用情况报告</span><span class="sxs-lookup"><span data-stu-id="de20b-201">Teams usage reporting</span></span>

<span data-ttu-id="de20b-202">Office 365 中的全局管理员、Teams 服务管理员和报表阅读者角色可以查看 Teams 使用情况报告。</span><span class="sxs-lookup"><span data-stu-id="de20b-202">The Global Admin in Office 365, Teams Service Admin, and Reports Readers roles can view Teams usage reports.</span></span> <span data-ttu-id="de20b-203">若要了解详细信息，请参阅 [Microsoft 365 使用情况分析](https://docs.microsoft.com/office365/admin/usage-analytics/usage-analytics?redirectSourcePath=%252farticle%252fMicrosoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f&view=o365-worldwide)文章。</span><span class="sxs-lookup"><span data-stu-id="de20b-203">To learn more, see the [Microsoft 365 usage analytics articles](https://docs.microsoft.com/office365/admin/usage-analytics/usage-analytics?redirectSourcePath=%252farticle%252fMicrosoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f&view=o365-worldwide).</span></span>

|<span data-ttu-id="de20b-204">询问你自己</span><span class="sxs-lookup"><span data-stu-id="de20b-204">Ask yourself</span></span>|<span data-ttu-id="de20b-205">操作</span><span class="sxs-lookup"><span data-stu-id="de20b-205">Action</span></span> |
|------------|-------|
|<br> <span data-ttu-id="de20b-206">谁需要查看 Teams 使用情况报告，他们是否有查看这些报告的正确角色？</span><span class="sxs-lookup"><span data-stu-id="de20b-206">Who needs to see the Teams usage reports, and do they have the correct role to view them?</span></span> |<ul><li><span data-ttu-id="de20b-207">如果用户不是管理员，请[分配报告阅读者角色](teams-activity-reports.md#reports-reader-role)。</span><span class="sxs-lookup"><span data-stu-id="de20b-207">If the user isn't an admin, [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</span></span></li><li><span data-ttu-id="de20b-208">请参阅[角色和权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)以及[查看和分配角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)，了解如何在 Azure Active Directory 中分配管理员角色。</span><span class="sxs-lookup"><span data-stu-id="de20b-208">See [Roles and permissions](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal) to learn how to assign admin roles in Azure Active Directory.</span></span> |
|||

### <a name="teams-default-apps"></a><span data-ttu-id="de20b-209">Teams 默认应用</span><span class="sxs-lookup"><span data-stu-id="de20b-209">Teams default apps</span></span> 

<span data-ttu-id="de20b-210">Teams 提供一些第一方（Microsoft 提供）和第三方应用来吸引用户、支持高效工作，并在 Teams 中集成了常用的业务服务。</span><span class="sxs-lookup"><span data-stu-id="de20b-210">Teams provides a number of first-party (Microsoft provided) and third-party apps to engage users, support productivity, and integrate commonly used business services into Teams.</span></span> <span data-ttu-id="de20b-211">从 Teams 应用商店获取应用。</span><span class="sxs-lookup"><span data-stu-id="de20b-211">Get apps from the Teams Store.</span></span> <span data-ttu-id="de20b-212">默认情况下 Teams 中已启用应用。</span><span class="sxs-lookup"><span data-stu-id="de20b-212">Apps are turned on by default in Teams.</span></span> 

<span data-ttu-id="de20b-213">若要详细了解如何在 Teams 中部署和管理应用，请参阅我们深入的[应用、聊天机器人和连接器](deploy-apps-microsoft-teams-landing-page.md)指引。</span><span class="sxs-lookup"><span data-stu-id="de20b-213">To learn more about rolling out and managing apps in Teams, see our in-depth [Apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md) guidance.</span></span>


## <a name="additional-deployment-decisions"></a><span data-ttu-id="de20b-214">其他部署决策</span><span class="sxs-lookup"><span data-stu-id="de20b-214">Additional deployment decisions</span></span>

<span data-ttu-id="de20b-215">你可能需要根据组织的需求和配置更改这些设置。</span><span class="sxs-lookup"><span data-stu-id="de20b-215">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="teams-licensing"></a><span data-ttu-id="de20b-216">Teams 许可</span><span class="sxs-lookup"><span data-stu-id="de20b-216">Teams licensing</span></span>

<span data-ttu-id="de20b-217">Teams 作为许多 Office 365 许可证的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="de20b-217">Teams is provided as part of many Office 365 licenses.</span></span> <span data-ttu-id="de20b-218">若要了解有关 Teams 许可的详细信息，请参阅 [Microsoft Teams 服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="de20b-218">To learn more about Teams licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

|<span data-ttu-id="de20b-219">询问你自己</span><span class="sxs-lookup"><span data-stu-id="de20b-219">Ask yourself</span></span>|<span data-ttu-id="de20b-220">操作</span><span class="sxs-lookup"><span data-stu-id="de20b-220">Action</span></span> |
|------------|-------|
|<span data-ttu-id="de20b-221">我的用户是否有使用要部署的所有 Teams 功能所需的许可证？</span><span class="sxs-lookup"><span data-stu-id="de20b-221">Do my users have the licenses they need in order to use all the Teams features I want to roll out?</span></span> | <span data-ttu-id="de20b-222">若要了解有关许可要求的信息，请参阅 [Microsoft Teams 服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="de20b-222">To learn about licensing requirements, read [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>|
|||

### <a name="exchange-and-sharepoint-interoperability"></a><span data-ttu-id="de20b-223">Exchange 和 SharePoint 互操作性</span><span class="sxs-lookup"><span data-stu-id="de20b-223">Exchange and SharePoint interoperability</span></span> 

<span data-ttu-id="de20b-224">为了获得全面的 Teams 体验，应该为每个用户启用 Exchange Online、SharePoint Online 和 Office 365 组创建。</span><span class="sxs-lookup"><span data-stu-id="de20b-224">For the full Teams experience, every user should be enabled for Exchange Online, SharePoint Online, and Office 365 Group creation.</span></span> <span data-ttu-id="de20b-225">下列文章概述的信息与以下各项相关：各种环境中托管的 Exchange 邮箱、Exchange 与 Teams 的交互方式，以及 SharePoint 和 OneDrive for Business 的类似注意事项。</span><span class="sxs-lookup"><span data-stu-id="de20b-225">The following articles outline information related to Exchange mailboxes hosted in various environments, how Exchange and Teams interact, and similar considerations for SharePoint and OneDrive for Business.</span></span> 

|<span data-ttu-id="de20b-226">询问你自己</span><span class="sxs-lookup"><span data-stu-id="de20b-226">Ask yourself</span></span>|<span data-ttu-id="de20b-227">操作</span><span class="sxs-lookup"><span data-stu-id="de20b-227">Action</span></span> |
|------------|-------|
| <span data-ttu-id="de20b-228">是否能随当前 Exchange 和 SharePoint 部署一起部署所需的 Teams 功能？</span><span class="sxs-lookup"><span data-stu-id="de20b-228">Will I be able to deploy the Teams features that I require with the current Exchange and SharePoint deployments?</span></span> |<span data-ttu-id="de20b-229">有关 Teams 中的 Exchange 和 SharePoint 的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="de20b-229">For more information about Exchange and SharePoint in Teams, see:</span></span><ul><li> [<span data-ttu-id="de20b-230">Exchange 与 Teams 如何交互</span><span class="sxs-lookup"><span data-stu-id="de20b-230">How Exchange and Teams interact</span></span>](exchange-teams-interact.md)</li><li>[<span data-ttu-id="de20b-231">SharePoint Online 和 OneDrive for Business 与 Teams 如何交互</span><span class="sxs-lookup"><span data-stu-id="de20b-231">How SharePoint Online and OneDrive for Business interact with Teams</span></span>](sharepoint-onedrive-interact.md)|
|||

### <a name="teams-limits-and-specifications"></a><span data-ttu-id="de20b-232">Teams 限制和规范</span><span class="sxs-lookup"><span data-stu-id="de20b-232">Teams limits and specifications</span></span> 

<span data-ttu-id="de20b-233">规划 Teams 的企业部署时，你应考虑任何相关的限制和规范，例如团队中的最大成员数、用户可创建的最大团队数，诸如此类。</span><span class="sxs-lookup"><span data-stu-id="de20b-233">When planning an enterprise deployment of Teams, you should take into account any relevant limitations and specifications, such as the maximum number of members in a team, the maximum number of teams a user can create, and so on.</span></span>

|<span data-ttu-id="de20b-234">询问你自己</span><span class="sxs-lookup"><span data-stu-id="de20b-234">Ask yourself</span></span>|<span data-ttu-id="de20b-235">操作</span><span class="sxs-lookup"><span data-stu-id="de20b-235">Action</span></span> |
|------------|-------|
| <span data-ttu-id="de20b-236">我的 Teams 部署可能会遇到什么限制？</span><span class="sxs-lookup"><span data-stu-id="de20b-236">What limits am I likely to hit with my Teams rollout?</span></span> | <span data-ttu-id="de20b-237">若要了解详细信息，请阅读 [Teams 的限制和规范](limits-specifications-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-237">To learn more, read [Limits and specifications for Teams](limits-specifications-teams.md).</span></span> |
|||

### <a name="office-365-urls-and-ports"></a><span data-ttu-id="de20b-238">Office 365 URL 和端口</span><span class="sxs-lookup"><span data-stu-id="de20b-238">Office 365 URLs and ports</span></span>

<span data-ttu-id="de20b-239">对其 Internet 流量保持精细控制的组织应阅读 [Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)，了解必须为 Teams 正确配置的 URL、IP 地址、端口和协议的最新列表。</span><span class="sxs-lookup"><span data-stu-id="de20b-239">Organizations that maintain fine-grained control of their internet traffic should read [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) for an up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="de20b-240">Microsoft 一直在改进 Office 365 服务并添加新功能，因此，所需端口、URL 和 IP 地址可能会随时间变化。</span><span class="sxs-lookup"><span data-stu-id="de20b-240">Microsoft is continuously improving the Office 365 service and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="de20b-241">建议你通过 RSS 订阅，以在此信息更新或更改时收到通知。</span><span class="sxs-lookup"><span data-stu-id="de20b-241">We recommend that you subscribe via RSS to receive notifications when this information is updated or changed.</span></span> <span data-ttu-id="de20b-242">至少需确保你已打开在上述[聊天部署先决条件](#chat-deployment-prerequisites)中列出的端口。</span><span class="sxs-lookup"><span data-stu-id="de20b-242">At a minimum, make sure you've opened the ports listed above in [Chat deployment prerequisites](#chat-deployment-prerequisites).</span></span>

|<span data-ttu-id="de20b-243">询问你自己</span><span class="sxs-lookup"><span data-stu-id="de20b-243">Ask yourself</span></span>|<span data-ttu-id="de20b-244">操作</span><span class="sxs-lookup"><span data-stu-id="de20b-244">Action</span></span> |
|------------|-------|
| <span data-ttu-id="de20b-245">是否需要 Internet 访问规则才能让用户使用 Teams，或者开放最少所需的端口是否足够？</span><span class="sxs-lookup"><span data-stu-id="de20b-245">Do I require internet access rules to enable users to use Teams, or is it sufficient to open the minimum required ports?</span></span> | <span data-ttu-id="de20b-246">若要了解详细信息，请参阅 [Office 365 URL 和 IP 地址范围](office-365-urls-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-246">To learn more, see [Office 365 URLs and IP address ranges](office-365-urls-ip-address-ranges.md).</span></span>|
|||


### <a name="governance-naming-conventions-who-can-create-teams"></a><span data-ttu-id="de20b-247">管理（命名约定，可创建团队的人员）</span><span class="sxs-lookup"><span data-stu-id="de20b-247">Governance (naming conventions, who can create teams)</span></span>

<span data-ttu-id="de20b-248">你的组织可能需要你对团队的命名和分类方式、谁可以创建团队以及团队到期、保留和存档加以控制。</span><span class="sxs-lookup"><span data-stu-id="de20b-248">Your organization might require that you implement controls on how teams are named and classified, who can create teams, and team expiration, retention, and archiving.</span></span> <span data-ttu-id="de20b-249">这称为管理。</span><span class="sxs-lookup"><span data-stu-id="de20b-249">This is called governance.</span></span> <span data-ttu-id="de20b-250">你可以使用 Azure Active Directory (Azure AD) 来配置各个方面。</span><span class="sxs-lookup"><span data-stu-id="de20b-250">You can use Azure Active Directory (Azure AD) to configure each of these areas.</span></span>


| <span data-ttu-id="de20b-251">询问你自己</span><span class="sxs-lookup"><span data-stu-id="de20b-251">Ask yourself</span></span> | <span data-ttu-id="de20b-252">操作</span><span class="sxs-lookup"><span data-stu-id="de20b-252">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="de20b-253">是否需要对谁可以创建团队进行控制？</span><span class="sxs-lookup"><span data-stu-id="de20b-253">Will I need to implement controls on who can create teams?</span></span>| <span data-ttu-id="de20b-254">请阅读[在 Teams 中规划管理](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-254">Read [Plan for governance in Teams](plan-teams-governance.md).</span></span>|
|<span data-ttu-id="de20b-255">是否需要对团队的命名方式进行控制？</span><span class="sxs-lookup"><span data-stu-id="de20b-255">Will I need to implement controls on how teams are named?</span></span>|<span data-ttu-id="de20b-256">请阅读[在 Azure AD 中为 Microsoft 365 组实施命名策略](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)。</span><span class="sxs-lookup"><span data-stu-id="de20b-256">Read [Enforce a naming policy for Microsoft 365 groups in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).</span></span>|
|||

### <a name="teams-application-policy-side-rail-control"></a><span data-ttu-id="de20b-257">Teams 应用程序策略（侧边栏控制）</span><span class="sxs-lookup"><span data-stu-id="de20b-257">Teams application policy (side-rail control)</span></span>

<span data-ttu-id="de20b-258">固定的应用显示在 Teams 的侧边栏中。</span><span class="sxs-lookup"><span data-stu-id="de20b-258">A pinned app shows up in the side rail in Teams.</span></span> <span data-ttu-id="de20b-259">通过创建 Teams 应用程序策略，你可以预先配置一组固定的 Teams 应用，以便针对经过挑选的用户组个性化 Teams。</span><span class="sxs-lookup"><span data-stu-id="de20b-259">By creating Teams application policies, you can preconfigure sets of pinned Teams apps to personalize Teams for select groups of users.</span></span> <span data-ttu-id="de20b-260">默认情况下，“**在 Microsoft Teams 中允许外部应用**”设置处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="de20b-260">By default, the **Allow external apps in Microsoft Teams** setting is turned on.</span></span>

| <span data-ttu-id="de20b-261">询问你自己</span><span class="sxs-lookup"><span data-stu-id="de20b-261">Ask yourself</span></span> | <span data-ttu-id="de20b-262">操作</span><span class="sxs-lookup"><span data-stu-id="de20b-262">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="de20b-263">是否应该创建一组预先配置的固定 Teams 应用程序？</span><span class="sxs-lookup"><span data-stu-id="de20b-263">Should I create preconfigured sets of pinned Teams applications?</span></span> | <span data-ttu-id="de20b-264">请阅读 [Teams 中应用的管理员设置](admin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-264">Read [Admin settings for apps in Teams](admin-settings.md).</span></span>|
|<span data-ttu-id="de20b-265">如何决定哪些组接收这些应用分组？</span><span class="sxs-lookup"><span data-stu-id="de20b-265">How will I decide which groups receive these app groupings?</span></span>|<span data-ttu-id="de20b-266">请阅读[团队应用权限和注意事项](app-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-266">Read [Teams apps permissions and considerations](app-permissions.md).</span></span>|
|||

### <a name="archiving-and-compliance"></a><span data-ttu-id="de20b-267">存档与合规性</span><span class="sxs-lookup"><span data-stu-id="de20b-267">Archiving and compliance</span></span> 

<span data-ttu-id="de20b-268">你的组织可能要求你对团队的存档方式以及某些类型的团队中包含的数据类型加以控制。</span><span class="sxs-lookup"><span data-stu-id="de20b-268">Your organization might require that you implement controls on how teams are archived and the types of data that are held in certain types of teams.</span></span> <span data-ttu-id="de20b-269">请阅读 [Teams 中的的安全性和合规性概述](security-compliance-overview.md)，了解哪些设置默认情况下已启用。</span><span class="sxs-lookup"><span data-stu-id="de20b-269">Read [Overview of security and compliance in Teams](security-compliance-overview.md) to learn which settings are turned on by default.</span></span>

| <span data-ttu-id="de20b-270">询问你自己</span><span class="sxs-lookup"><span data-stu-id="de20b-270">Ask yourself</span></span> | <span data-ttu-id="de20b-271">操作</span><span class="sxs-lookup"><span data-stu-id="de20b-271">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="de20b-272">是否需要配置团队保留？</span><span class="sxs-lookup"><span data-stu-id="de20b-272">Will I need to configure team retention?</span></span>|<span data-ttu-id="de20b-273">若要设置保留策略，请参阅[设置 Teams 保留策略](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-273">To set up retention policies, see [Set up Teams retention policies](retention-policies.md).</span></span>|
|<span data-ttu-id="de20b-274">是否需要配置团队存档？</span><span class="sxs-lookup"><span data-stu-id="de20b-274">Will I need to configure team archiving?</span></span>|<span data-ttu-id="de20b-275">若要存档或还原团队，请参阅[存档或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。</span><span class="sxs-lookup"><span data-stu-id="de20b-275">To archive or restore a team, see [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>|
|<span data-ttu-id="de20b-276">是否需要配置其他合规性设置？</span><span class="sxs-lookup"><span data-stu-id="de20b-276">Will I need to configure additional compliance settings?</span></span>|<span data-ttu-id="de20b-277">有关安全性和合规性的详细信息，请参阅 [Teams 中的安全性和合规性概述](security-compliance-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-277">For more information about security and compliance, see [Overview of security and compliance in Teams](security-compliance-overview.md).</span></span>|
|||

### <a name="conditional-access"></a><span data-ttu-id="de20b-278">条件访问</span><span class="sxs-lookup"><span data-stu-id="de20b-278">Conditional access</span></span> 

<span data-ttu-id="de20b-279">对于核心工作效率方案（包括会议、日历、互操作聊天和文件共享），Teams 高度依赖 Exchange Online、SharePoint Online 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="de20b-279">Teams relies heavily on Exchange Online, SharePoint Online, and Skype for Business Online for core productivity scenarios, including meetings, calendars, interop chats, and file sharing.</span></span> <span data-ttu-id="de20b-280">当用户在任何客户端上直接登录 Teams 时，为这些云应用设置的条件访问策略将应用于 Teams。</span><span class="sxs-lookup"><span data-stu-id="de20b-280">Conditional access policies that are set for these cloud apps apply to Teams when a user signs in directly to Teams, on any client.</span></span> <span data-ttu-id="de20b-281">为这些云应用设置的条件访问策略控制各个方面，例如用户是否可从某些网络访问 Teams 服务。</span><span class="sxs-lookup"><span data-stu-id="de20b-281">Conditional access policies that are set for the Teams cloud app control aspects such as whether users can access Teams services from certain networks.</span></span>

| <span data-ttu-id="de20b-282">询问你自己</span><span class="sxs-lookup"><span data-stu-id="de20b-282">Ask yourself</span></span> | <span data-ttu-id="de20b-283">操作</span><span class="sxs-lookup"><span data-stu-id="de20b-283">Action</span></span> |
|--------------|--------|
|<br><span data-ttu-id="de20b-284">是否需要为 Teams 配置条件访问？</span><span class="sxs-lookup"><span data-stu-id="de20b-284">Will I need to configure conditional access for Teams?</span></span>|<ul><li><span data-ttu-id="de20b-285">若要了解访问策略的工作方式，请参阅[条件访问策略如何在 Teams 中发挥作用？](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)</span><span class="sxs-lookup"><span data-stu-id="de20b-285">To understand how access policies work, see [How do conditional access policies work for Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)</span></span></li><li><span data-ttu-id="de20b-286">若要为 Teams 设置多重身份验证 (MFA)，请参阅：</span><span class="sxs-lookup"><span data-stu-id="de20b-286">To set up multi-factor authentication (MFA) for Teams, see:</span></span><ul><li>[<span data-ttu-id="de20b-287">快速入门：具有 Azure Active Directory 条件访问权限的特定应用需要 MFA</span><span class="sxs-lookup"><span data-stu-id="de20b-287">Quickstart: Require MFA for specific apps with Azure Active Directory conditional access</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-mfa)</li><li>[<span data-ttu-id="de20b-288">Azure Active Directory 条件访问设置参考</span><span class="sxs-lookup"><span data-stu-id="de20b-288">Azure Active Directory conditional access settings reference</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|
|||


### <a name="education-edu"></a><span data-ttu-id="de20b-289">教育版 (EDU)</span><span class="sxs-lookup"><span data-stu-id="de20b-289">Education (EDU)</span></span> 

<span data-ttu-id="de20b-290">在教育行业工作的 IT 专业人员可以利用 Teams 教育版，该版本提供的许多功能经过定制，可满足学生、教职员工和更广泛行业特定于教育的方案需求。</span><span class="sxs-lookup"><span data-stu-id="de20b-290">IT pros working in education can take advantage of Teams for Education, which comes with a number of capabilities that have been tailored to meet education-specific scenarios for students, faculty, and the wider business.</span></span>

| <span data-ttu-id="de20b-291">询问你自己</span><span class="sxs-lookup"><span data-stu-id="de20b-291">Ask yourself</span></span> | <span data-ttu-id="de20b-292">操作</span><span class="sxs-lookup"><span data-stu-id="de20b-292">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="de20b-293">是否要使用特定于 EDU 的 Teams 模板？</span><span class="sxs-lookup"><span data-stu-id="de20b-293">Will I use EDU-specific Teams templates?</span></span> |<span data-ttu-id="de20b-294">若要详细了解 Teams 教育版，请参阅[面向管理员的 Microsoft 教育管理常见问题](plan-teams-governance-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-294">To learn more about Teams for Education, see [Microsoft Education governance FAQ for admins](plan-teams-governance-edu.md).</span></span>|
|<span data-ttu-id="de20b-295">是否要部署范围限定的搜索？</span><span class="sxs-lookup"><span data-stu-id="de20b-295">Will I deploy scoped search?</span></span>|<span data-ttu-id="de20b-296">若要为 EDU 设置 Teams，请参阅[快速入门 - Teams 教育版管理](teams-quick-start-edu.yml)。</span><span class="sxs-lookup"><span data-stu-id="de20b-296">To set up Teams for EDU, see [Quickstart - Teams for Education admins](teams-quick-start-edu.yml).</span></span>|
|<span data-ttu-id="de20b-297">是否要将 Teams 与 School Data Sync 服务集成来配置用户帐户？</span><span class="sxs-lookup"><span data-stu-id="de20b-297">Will I integrate Teams with the School Data Sync service to provision user accounts?</span></span>|[<span data-ttu-id="de20b-298">面向教育版管理员的 Teams 资源</span><span class="sxs-lookup"><span data-stu-id="de20b-298">Teams resources for Education admins</span></span>](resources-teams-edu.md)|
|||

### <a name="government---gcc-considerations"></a><span data-ttu-id="de20b-299">政府版 - GCC 注意事项</span><span class="sxs-lookup"><span data-stu-id="de20b-299">Government - GCC considerations</span></span>

<span data-ttu-id="de20b-300">对于在美国联邦政府、州政府、地方政府、部族政府或准州政府实体或者所处理数据遵从政府法规和要求的其他实体推动 Office 365 部署的 IT 专业人员，使用 Microsoft 365 政府版 - GCC（政府社区云）可以适当地满足其需求。</span><span class="sxs-lookup"><span data-stu-id="de20b-300">The use of Microsoft 365 for Government - GCC (Government Community Cloud) is appropriate to meet the requirements of IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements.</span></span>

| <span data-ttu-id="de20b-301">询问你自己</span><span class="sxs-lookup"><span data-stu-id="de20b-301">Ask yourself</span></span> | <span data-ttu-id="de20b-302">操作</span><span class="sxs-lookup"><span data-stu-id="de20b-302">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="de20b-303">是否要在 Microsoft 365 政府版 – GCC 环境中部署 Teams？</span><span class="sxs-lookup"><span data-stu-id="de20b-303">Will I need to deploy Teams in a Microsoft 365 Government – GCC environment?</span></span> | <span data-ttu-id="de20b-304">有关部署注意事项，请参阅[规划 Microsoft 365 政府版 - GCC 部署](plan-for-government-gcc.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-304">For deployment considerations, see [Plan for Microsoft 365 Government - GCC deployments](plan-for-government-gcc.md).</span></span>|
|||

## <a name="next-steps"></a><span data-ttu-id="de20b-305">后续步骤</span><span class="sxs-lookup"><span data-stu-id="de20b-305">Next steps</span></span>
- <span data-ttu-id="de20b-306">[推动采用](adopt-microsoft-teams-landing-page.md)聊天、团队、频道和应用。</span><span class="sxs-lookup"><span data-stu-id="de20b-306">[Drive adoption](adopt-microsoft-teams-landing-page.md) of chat, teams, channels, & apps.</span></span>
- <span data-ttu-id="de20b-307">在 Teams 的初步部署中加入特别推荐的应用 - 例如 Planner。</span><span class="sxs-lookup"><span data-stu-id="de20b-307">Include featured apps - such as Planner - in your initial Teams rollout.</span></span> <span data-ttu-id="de20b-308">在推动 Teams 采用的过程中添加其他[应用、聊天机器人和连接器](deploy-apps-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="de20b-308">Add other [apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md) as you drive Teams adoption.</span></span>
- [<span data-ttu-id="de20b-309">部署会议</span><span class="sxs-lookup"><span data-stu-id="de20b-309">Roll out meetings & conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)
- [<span data-ttu-id="de20b-310">部署云语音</span><span class="sxs-lookup"><span data-stu-id="de20b-310">Roll out cloud voice</span></span>](cloud-voice-landing-page.md)

