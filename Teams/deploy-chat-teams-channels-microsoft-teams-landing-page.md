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
description: 在 Microsoft Teams 中部署聊天、团队、频道和应用的分步指导
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87de516afbd94a0d1784edd52efbcc5b10e262dd
ms.sourcegitcommit: 29034bda30a8460eb18600785f785528d0944041
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "42285824"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a><span data-ttu-id="60f1c-103">Microsoft Teams 中的聊天、团队、频道和应用</span><span class="sxs-lookup"><span data-stu-id="60f1c-103">Chat, teams, channels, & apps in Microsoft Teams</span></span>

<span data-ttu-id="60f1c-104">Teams 为组织提供了现成的出色协作体验，并且大多数组织发现默认设置适合它们。</span><span class="sxs-lookup"><span data-stu-id="60f1c-104">Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them.</span></span> <span data-ttu-id="60f1c-105">本文可帮助你决定是否要根据组织的情况和业务需求更改任何默认设置，然后引导你完成每项更改。</span><span class="sxs-lookup"><span data-stu-id="60f1c-105">This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="60f1c-106">我们将这些设置分为两组：首先是[你更有可能更改的一组核心设置](#core-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-106">We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="60f1c-107">第二组包括你可能希望根据组织的需求配置的[其他设置](#additional-deployment-decisions)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-107">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span> 

<span data-ttu-id="60f1c-108">首先，请观看我们的“Teams 聊天、团队和频道”短视频（4 分 30 秒）：</span><span class="sxs-lookup"><span data-stu-id="60f1c-108">To get started, watch our short Teams chat, teams, and channels video (4:30 minutes):</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj]

<span data-ttu-id="60f1c-109">*2019年11月新增功能*</span><span class="sxs-lookup"><span data-stu-id="60f1c-109">*New in November 2019*</span></span>
 - <span data-ttu-id="60f1c-110">现在可[使用 Advisor for Teams（预览版）帮助你推出 Microsoft Teams](use-advisor-teams-roll-out.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-110">You can now [use Advisor for Teams (preview) to help you roll out Microsoft Teams](use-advisor-teams-roll-out.md).</span></span> <span data-ttu-id="60f1c-111">Advisor for Teams（预览版）为你提供 Teams 推出的分步指导。</span><span class="sxs-lookup"><span data-stu-id="60f1c-111">Advisor for Teams (preview) walks you through your Teams rollout.</span></span> <span data-ttu-id="60f1c-112">它将评估 Office 365 环境并确定更新或修改所需的最常用配置，帮助你成功推出 Teams。</span><span class="sxs-lookup"><span data-stu-id="60f1c-112">It assesses your Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span>
 - <span data-ttu-id="60f1c-113">[Microsoft YouTube 频道 IT 团队基础知识](https://aka.ms/MicrosoftTeamsforIT)，包括简短（8-10 分钟）的视频，显示如何推出、配置和管理团队。</span><span class="sxs-lookup"><span data-stu-id="60f1c-113">[Microsoft Teams Essentials for IT YouTube channel](https://aka.ms/MicrosoftTeamsforIT), including short (8-10 minute) videos that show you how to roll out, configure, and manage Teams.</span></span>

> [!TIP]
> <span data-ttu-id="60f1c-114">我们建议你在 Teams 的初步部署中加入特别推荐的应用 - 例如 Planner。</span><span class="sxs-lookup"><span data-stu-id="60f1c-114">We recommend that you include our featured apps-such as Planner-in your initial Teams rollout.</span></span> <span data-ttu-id="60f1c-115">在推动 Teams 采用的过程中添加其他[应用、聊天机器人和连接器](deploy-apps-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-115">Add other [apps, bots, and connectors](deploy-apps-microsoft-teams-landing-page.md) as you drive Teams adoption.</span></span>

## <a name="chat-deployment-prerequisites"></a><span data-ttu-id="60f1c-116">聊天部署先决条件</span><span class="sxs-lookup"><span data-stu-id="60f1c-116">Chat deployment prerequisites</span></span>

<span data-ttu-id="60f1c-117">在整个组织内部署 Teams 之前，请花些时间确认你环境已准备好使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="60f1c-117">Before you roll out Teams across your organization, take time to confirm that your environment is ready for Teams.</span></span> <span data-ttu-id="60f1c-118">查看以下信息，并对你的环境进行任何必需的更改。</span><span class="sxs-lookup"><span data-stu-id="60f1c-118">Review the following information and make any required changes to your environment.</span></span>

- <span data-ttu-id="60f1c-119">若要获得完整的 Teams 体验，你的组织必须部署了 [Exchange Online 和 SharePoint Online](#exchange-and-sharepoint-interoperability)，并且你必须有适用于 Office 365 的已验证域（例如，contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="60f1c-119">To get the full Teams experience, your organization must have deployed [Exchange Online and SharePoint Online](#exchange-and-sharepoint-interoperability), and you must have a verified domain for Office 365 (for example, contoso.com).</span></span>

- <span data-ttu-id="60f1c-120">若要在整个组织内大规模部署聊天、团队和频道，请确保所有地点都权访问 Internet，以便可以连接到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="60f1c-120">To scale chat, teams, and channels across your organization, make sure all locations have internet access so they can connect to Office 365.</span></span> <span data-ttu-id="60f1c-121">至少确保以下常用端口在所有地点已向 Internet 开放：</span><span class="sxs-lookup"><span data-stu-id="60f1c-121">At a minimum, make sure that the following common ports are open to the internet from all locations:</span></span>

    - <span data-ttu-id="60f1c-122">为将使用 Teams 的客户端发出的传出流量开放 **TCP** 端口 80 和 443</span><span class="sxs-lookup"><span data-stu-id="60f1c-122">Open **TCP** ports 80 and 443 for outgoing traffic from clients that will use Teams</span></span>
    - <span data-ttu-id="60f1c-123">为将使用 Teams 的客户端发出的传出流量开放 **UDP** 端口 3478 至 3481 </span><span class="sxs-lookup"><span data-stu-id="60f1c-123">Open **UDP** ports 3478 through 3481 for outgoing traffic from clients that will use Teams</span></span>

|<span data-ttu-id="60f1c-124">询问你自己</span><span class="sxs-lookup"><span data-stu-id="60f1c-124">Ask yourself</span></span>|<span data-ttu-id="60f1c-125">操作</span><span class="sxs-lookup"><span data-stu-id="60f1c-125">Action</span></span> |
|------------|-------|
|<span data-ttu-id="60f1c-126">我的组织是否已准备好部署 Teams？</span><span class="sxs-lookup"><span data-stu-id="60f1c-126">Is my organization ready to roll out Teams?</span></span>|<span data-ttu-id="60f1c-127">为了回答此问题，请参阅：</span><span class="sxs-lookup"><span data-stu-id="60f1c-127">To answer this question, see:</span></span> <ul><li>[<span data-ttu-id="60f1c-128">为 Teams 准备贵组织的网络</span><span class="sxs-lookup"><span data-stu-id="60f1c-128">Prepare your organization's network for Teams</span></span>](prepare-network.md)</li><li>[<span data-ttu-id="60f1c-129">Office 365 URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="60f1c-129">Office 365 URLs and IP address ranges</span></span>](office-365-urls-ip-address-ranges.md)</li><li>[<span data-ttu-id="60f1c-130">在创建团队时规划 Office 365 组</span><span class="sxs-lookup"><span data-stu-id="60f1c-130">Plan for Office 365 Groups when creating teams</span></span>](plan-office-365-groups.md)</li></ul>|
|||

## <a name="core-deployment-decisions"></a><span data-ttu-id="60f1c-131">核心部署决策</span><span class="sxs-lookup"><span data-stu-id="60f1c-131">Core deployment decisions</span></span>

<span data-ttu-id="60f1c-132">以下是大多数组织在默认设置不适合的情况下想要更改的聊天、团队和频道设置。</span><span class="sxs-lookup"><span data-stu-id="60f1c-132">These are the chat, teams, and channels settings that most organizations want to change (if the default settings don't work for them).</span></span>

### <a name="teams-administrators"></a><span data-ttu-id="60f1c-133">Teams 管理员</span><span class="sxs-lookup"><span data-stu-id="60f1c-133">Teams administrators</span></span>

<span data-ttu-id="60f1c-134">Teams 提供了一组可用于为组织管理 Teams 的自定义管理员角色。</span><span class="sxs-lookup"><span data-stu-id="60f1c-134">Teams provides a set of custom administrator roles that can be used to manage Teams for your organization.</span></span> <span data-ttu-id="60f1c-135">这些角色为管理员提供各种能力。</span><span class="sxs-lookup"><span data-stu-id="60f1c-135">The roles provide various capabilities to administrators.</span></span>

| <span data-ttu-id="60f1c-136">询问你自己</span><span class="sxs-lookup"><span data-stu-id="60f1c-136">Ask yourself</span></span> | <span data-ttu-id="60f1c-137">操作</span><span class="sxs-lookup"><span data-stu-id="60f1c-137">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="60f1c-138">将为谁分配 Teams 通信管理员角色？</span><span class="sxs-lookup"><span data-stu-id="60f1c-138">Who will be assigned the Teams Communications Administrator role?</span></span>|<span data-ttu-id="60f1c-139">若要详细了解 Teams 管理员角色，请参阅[使用 Microsoft Teams 管理员角色来管理 Teams](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-139">To learn more about Teams administrator roles see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>|
|<span data-ttu-id="60f1c-140">将为谁分配 Teams 通信支持工程师角色？</span><span class="sxs-lookup"><span data-stu-id="60f1c-140">Who will be assigned the Teams Communications Support Engineer role?</span></span>|<span data-ttu-id="60f1c-141">若要分配管理员角色，请参阅[使用 Active Directory 为用户分配管理员和非管理员角色](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-141">To assign admin roles, see [Assign administrator and non-administrator roles to users with Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).</span></span>|
|<span data-ttu-id="60f1c-142">将为谁分配 Teams 通信支持专家角色？</span><span class="sxs-lookup"><span data-stu-id="60f1c-142">Who will be assigned the Teams Communications Support Specialist role?</span></span>||
|||

### <a name="teams-owners-and-members"></a><span data-ttu-id="60f1c-143">Teams 所有者和成员</span><span class="sxs-lookup"><span data-stu-id="60f1c-143">Teams owners and members</span></span>

<span data-ttu-id="60f1c-144">除了管理员角色之外，Teams 还允许你分配所有者和成员用户角色，并选择他们提供审阅人功能（如果已设置审核功能）以控制谁可以在渠道中执行特定操作。</span><span class="sxs-lookup"><span data-stu-id="60f1c-144">In addition to administrator roles, Teams lets you assign owner and member user roles, and selectively give them moderator capabilities (if moderation has been set up) to control who can perform certain actions within a channel.</span></span> <span data-ttu-id="60f1c-145">通过审核功能，你可以控制谁可以在频道中发表新帖子，添加和删除作为审阅人的团队成员，以及控制团队成员能否回复现有频道消息。</span><span class="sxs-lookup"><span data-stu-id="60f1c-145">Moderation allows you to control who can start new posts in a channel, add and remove team members as moderators, and control whether team members can reply to existing channel messages.</span></span>

|<span data-ttu-id="60f1c-146">询问你自己</span><span class="sxs-lookup"><span data-stu-id="60f1c-146">Ask yourself</span></span>|<span data-ttu-id="60f1c-147">操作</span><span class="sxs-lookup"><span data-stu-id="60f1c-147">Action</span></span> |
|------------|-------|
|<span data-ttu-id="60f1c-148">应该为每个角色分配哪些人员？</span><span class="sxs-lookup"><span data-stu-id="60f1c-148">Who should be assigned to each role?</span></span> | <span data-ttu-id="60f1c-149">若要比较每个角色的功能，请参阅[在 Microsoft Teams 中分配团队所有者、审阅人和成员](assign-roles-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-149">To compare the capabilities of each role, see [Assign team owners, moderators, and members in Microsoft Teams](assign-roles-permissions.md).</span></span>
|<span data-ttu-id="60f1c-150">如何分配用户角色？</span><span class="sxs-lookup"><span data-stu-id="60f1c-150">How do I assign a user role?</span></span> | <span data-ttu-id="60f1c-151">若要分配或更改角色，请参阅[分配用户角色](assign-roles-permissions.md#assign-a-user-role)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-151">To assign or change a role, see [Assign a user role](assign-roles-permissions.md#assign-a-user-role).</span></span>
|<span data-ttu-id="60f1c-152">我是否需要控制谁可以在频道中发布和答复？</span><span class="sxs-lookup"><span data-stu-id="60f1c-152">Do I need to control who can post and reply in a channel?</span></span> | <span data-ttu-id="60f1c-153">若要配置审核，请参阅[在 Microsoft Teams 中设置和管理频道审核](manage-channel-moderation-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-153">To configure moderation, see [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md).</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="60f1c-154">消息策略</span><span class="sxs-lookup"><span data-stu-id="60f1c-154">Messaging policies</span></span>

<span data-ttu-id="60f1c-155">消息策略控制为 Teams 中的用户提供哪些聊天和频道消息功能。</span><span class="sxs-lookup"><span data-stu-id="60f1c-155">Messaging policies control which chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="60f1c-156">例如，谁可以编辑和删除已发送的消息、谁可以使用聊天、谁可以在对话中使用 Meme，等等。</span><span class="sxs-lookup"><span data-stu-id="60f1c-156">For example, who can edit and delete sent messages, who can use chat, who can use memes in conversations, and more.</span></span> <span data-ttu-id="60f1c-157">默认情况下，会为用户分配全局消息策略，所有功能均**开启**。</span><span class="sxs-lookup"><span data-stu-id="60f1c-157">By default, users are assigned the global messaging policy and all features are **On**.</span></span> <span data-ttu-id="60f1c-158">可以使用默认全局策略，或者为组织中的人员创建一个或多个自定义消息策略。</span><span class="sxs-lookup"><span data-stu-id="60f1c-158">You can use the default global policy or create one or more custom messaging policies for people in your organization.</span></span> 

|<span data-ttu-id="60f1c-159">询问你自己</span><span class="sxs-lookup"><span data-stu-id="60f1c-159">Ask yourself</span></span>|<span data-ttu-id="60f1c-160">操作</span><span class="sxs-lookup"><span data-stu-id="60f1c-160">Action</span></span> |
|------------|-------|
|<span data-ttu-id="60f1c-161">是否要自定义全局消息策略？</span><span class="sxs-lookup"><span data-stu-id="60f1c-161">Will I customize the global messaging policy?</span></span>|<span data-ttu-id="60f1c-162">有关使用 Microsoft Teams 管理中心来更改全局消息策略或添加新策略的信息，请参阅[在 Teams 中管理消息策略](messaging-policies-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-162">For information about using the Microsoft Teams admin center to change the global messaging policy or add a new policy, see [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>|
|<span data-ttu-id="60f1c-163">是否需要多个消息策略？</span><span class="sxs-lookup"><span data-stu-id="60f1c-163">Do I require multiple messaging policies?</span></span>|<span data-ttu-id="60f1c-164">若要在 PowerShell 中创建和分配消息策略，请参阅 [PowerShell 脚本示例 - 创建和分配消息策略](scripts/powershell-script-teams-messaging-policy-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-164">To create and assign a messaging policy in PowerShell, see [PowerShell script sample - Create and assign a messaging policy](scripts/powershell-script-teams-messaging-policy-edu.md).</span></span>|
|<span data-ttu-id="60f1c-165">如何确定哪些用户组获取哪些消息策略？</span><span class="sxs-lookup"><span data-stu-id="60f1c-165">How will I determine which groups of users get which messaging policy?</span></span>|<span data-ttu-id="60f1c-166">若要了解 CsTeamsMessagingPolicy cmdlet，请参阅 [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-166">To learn about the CsTeamsMessagingPolicy cmdlets, see [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps).</span></span>|
||| 

### <a name="external-access"></a><span data-ttu-id="60f1c-167">外部访问</span><span class="sxs-lookup"><span data-stu-id="60f1c-167">External access</span></span>

<span data-ttu-id="60f1c-168">利用外部访问功能（以前称为联合），你的 Teams 和 Skype for Business 用户可以与组织外部的用户通信。</span><span class="sxs-lookup"><span data-stu-id="60f1c-168">External access (formerly known as federation) lets your Teams and Skype for Business users communicate with users who are outside of your organization.</span></span> <span data-ttu-id="60f1c-169">通过启用此功能并将域添加到允许的列表，你的用户将能与其他域和组织中的用户通信。</span><span class="sxs-lookup"><span data-stu-id="60f1c-169">By turning this on and adding domains to the allowed list, your users can communicate with users in other domains and organizations.</span></span><span data-ttu-id="60f1c-170">外部访问与来宾访问的不同之处在于，将为整个域（而不是个人）授予访问权限。</span><span class="sxs-lookup"><span data-stu-id="60f1c-170"> External access differs from guest access in that an entire domain is given access permission, not an individual.</span></span> <span data-ttu-id="60f1c-171">默认情况下会关闭外部访问。</span><span class="sxs-lookup"><span data-stu-id="60f1c-171">External access is turned off by default.</span></span>

|<span data-ttu-id="60f1c-172">询问你自己</span><span class="sxs-lookup"><span data-stu-id="60f1c-172">Ask yourself</span></span>|<span data-ttu-id="60f1c-173">操作</span><span class="sxs-lookup"><span data-stu-id="60f1c-173">Action</span></span> |
|------------|-------|
|<ul><li><span data-ttu-id="60f1c-174">是否要为我的组织启用外部访问？</span><span class="sxs-lookup"><span data-stu-id="60f1c-174">Will I turn on external access for my organization?</span></span></li><li><span data-ttu-id="60f1c-175">如果启用，是否要限制我的组织可以与哪些域进行通信？</span><span class="sxs-lookup"><span data-stu-id="60f1c-175">If enabled, will I limit which domains my organization can communicate with?</span></span></li></ul> |<br><span data-ttu-id="60f1c-176">若要启用外部访问，请参阅[规划外部访问](manage-external-access.md#plan-for-external-access)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-176">To turn on external access, see [Plan for external access](manage-external-access.md#plan-for-external-access).</span></span>|
|||

### <a name="guest-access"></a><span data-ttu-id="60f1c-177">来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="60f1c-177">Guest access</span></span>

<span data-ttu-id="60f1c-178">Teams 中的来宾访问可让组织外部的个人访问团队和频道。</span><span class="sxs-lookup"><span data-stu-id="60f1c-178">Guest access in Teams lets individuals outside your organization access teams and channels.</span></span> <span data-ttu-id="60f1c-179">可以使用来宾访问设置来控制来宾用户能够使用或无法使用哪些功能。</span><span class="sxs-lookup"><span data-stu-id="60f1c-179">You can use the guest access settings to control which features guest users can or can’t use.</span></span> <span data-ttu-id="60f1c-180">默认情况下会关闭来宾访问。</span><span class="sxs-lookup"><span data-stu-id="60f1c-180">Guest access is turned off by default.</span></span> <span data-ttu-id="60f1c-181">若要了解详细信息，请参阅 [Teams 中的来宾访问](https://docs.microsoft.com/microsoftteams/guest-access)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-181">To learn more, see [Guest access in Teams](https://docs.microsoft.com/microsoftteams/guest-access).</span></span>

|<span data-ttu-id="60f1c-182">询问你自己</span><span class="sxs-lookup"><span data-stu-id="60f1c-182">Ask yourself</span></span>|<span data-ttu-id="60f1c-183">操作</span><span class="sxs-lookup"><span data-stu-id="60f1c-183">Action</span></span> |
|------------|-------|
|<span data-ttu-id="60f1c-184">是否要为我的组织启用来宾访问？</span><span class="sxs-lookup"><span data-stu-id="60f1c-184">Will I turn on guest access for my organization?</span></span>|<span data-ttu-id="60f1c-185">若要启用来宾访问，请参阅[在 Teams 中启用或禁用来宾访问](set-up-guests.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-185">To turn on guest access, see [Turn on or off guest access in Teams](set-up-guests.md).</span></span>|
|<span data-ttu-id="60f1c-186">如果启用，是否要自定义可供组织中的来宾使用的功能？</span><span class="sxs-lookup"><span data-stu-id="60f1c-186">If enabled, will I customize the features available to guests in my organization?</span></span>|<span data-ttu-id="60f1c-187">若要自定义来宾访问功能可用性，请参阅[在 Teams 中授权来宾访问](teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-187">To customize guest access feature availability, see [Authorize guest access in Teams](teams-dependencies.md).</span></span>|
|||

### <a name="teams-settings"></a><span data-ttu-id="60f1c-188">Teams 设置</span><span class="sxs-lookup"><span data-stu-id="60f1c-188">Teams settings</span></span>

<span data-ttu-id="60f1c-189">Teams 设置允许你针对诸如电子邮件集成、云存储选项、组织选项卡、会议室设备设置和搜索范围等功能设置团队。</span><span class="sxs-lookup"><span data-stu-id="60f1c-189">Teams settings let you set up your teams for features such as email integration, cloud storage options, organization tab, meeting room device setup, and search scope.</span></span> <span data-ttu-id="60f1c-190">更改这些设置时，所做更改将应用于组织中的所有团队。</span><span class="sxs-lookup"><span data-stu-id="60f1c-190">When you make changes to these settings, they apply to all the teams in your organization.</span></span><span data-ttu-id="60f1c-191">若要了解详细信息，请参阅 [Teams 设置](enable-features-office-365.md#teams-settings)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-191"> To learn more, see [Teams settings](enable-features-office-365.md#teams-settings).</span></span>

|<span data-ttu-id="60f1c-192">询问你自己</span><span class="sxs-lookup"><span data-stu-id="60f1c-192">Ask yourself</span></span>|<span data-ttu-id="60f1c-193">操作</span><span class="sxs-lookup"><span data-stu-id="60f1c-193">Action</span></span> |
|------------|-------|
|<span data-ttu-id="60f1c-194">是否要为我的组织自定义 Teams 设置？</span><span class="sxs-lookup"><span data-stu-id="60f1c-194">Will I customize Teams settings for my organization?</span></span> | <span data-ttu-id="60f1c-195">若要了解 Teams 设置以及如何自定义这些设置，请参阅 [Teams 设置](enable-features-office-365.md#teams-settings)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-195">To learn about Teams settings and how to customize them, see [Teams settings](enable-features-office-365.md#teams-settings).</span></span>|
|||

### <a name="teams-clients"></a><span data-ttu-id="60f1c-196">Teams 客户端</span><span class="sxs-lookup"><span data-stu-id="60f1c-196">Teams clients</span></span>

<span data-ttu-id="60f1c-197">Teams 支持从 Web 到桌面直至移动客户端的多种客户端，默认配置允许用户选择所需的任一客户端。</span><span class="sxs-lookup"><span data-stu-id="60f1c-197">Teams supports a number of clients from web to desktop to mobile, and the default configuration lets users choose whichever clients they want.</span></span><span data-ttu-id="60f1c-198">若要了解详细信息，请参阅[获取 Teams 客户端](get-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-198"> To learn more, see [Get clients for Teams](get-clients.md).</span></span>

|<span data-ttu-id="60f1c-199">询问你自己</span><span class="sxs-lookup"><span data-stu-id="60f1c-199">Ask yourself</span></span>|<span data-ttu-id="60f1c-200">操作</span><span class="sxs-lookup"><span data-stu-id="60f1c-200">Action</span></span> |
|------------|-------|
|<span data-ttu-id="60f1c-201">是否要为我的组织自定义 Teams 客户端可用性？</span><span class="sxs-lookup"><span data-stu-id="60f1c-201">Will I customize Teams client availability for my organization?</span></span>|<span data-ttu-id="60f1c-202">请参阅 [Teams 应用的硬件要求](hardware-requirements-for-the-teams-app.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-202">Check out [Hardware requirements for the Teams app](hardware-requirements-for-the-teams-app.md).</span></span> |
|<span data-ttu-id="60f1c-203">是否要为我的组织自定义 Teams 客户端设置？</span><span class="sxs-lookup"><span data-stu-id="60f1c-203">Will I customize Teams client settings for my organization?</span></span>|<span data-ttu-id="60f1c-204">了解如何[使用 MSI 安装 Teams](msi-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-204">Learn how to [Install Teams using MSI](msi-deployment.md).</span></span>|
|||


### <a name="teams-usage-reporting"></a><span data-ttu-id="60f1c-205">Teams 使用情况报告</span><span class="sxs-lookup"><span data-stu-id="60f1c-205">Teams usage reporting</span></span>

<span data-ttu-id="60f1c-206">Office 365 中的全局管理员、Teams 服务管理员和报表阅读者角色可以查看 Teams 使用情况报告。</span><span class="sxs-lookup"><span data-stu-id="60f1c-206">The Global Admin in Office 365, Teams Service Admin, and Reports Readers roles can view Teams usage reports.</span></span> <span data-ttu-id="60f1c-207">若要了解详细信息，请参阅 [Microsoft 365 使用情况分析](https://docs.microsoft.com/office365/admin/usage-analytics/usage-analytics?redirectSourcePath=%252farticle%252fMicrosoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f&view=o365-worldwide)文章。</span><span class="sxs-lookup"><span data-stu-id="60f1c-207">To learn more, see the [Microsoft 365 usage analytics articles](https://docs.microsoft.com/office365/admin/usage-analytics/usage-analytics?redirectSourcePath=%252farticle%252fMicrosoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f&view=o365-worldwide).</span></span>

|<span data-ttu-id="60f1c-208">询问你自己</span><span class="sxs-lookup"><span data-stu-id="60f1c-208">Ask yourself</span></span>|<span data-ttu-id="60f1c-209">操作</span><span class="sxs-lookup"><span data-stu-id="60f1c-209">Action</span></span> |
|------------|-------|
|<br> <span data-ttu-id="60f1c-210">谁需要查看 Teams 使用情况报告，他们是否有查看这些报告的正确角色？</span><span class="sxs-lookup"><span data-stu-id="60f1c-210">Who needs to see the Teams usage reports, and do they have the correct role to view them?</span></span> |<ul><li><span data-ttu-id="60f1c-211">如果用户不是管理员，请[分配报告阅读者角色](teams-activity-reports.md#reports-reader-role)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-211">If the user isn't an admin, [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</span></span></li><li><span data-ttu-id="60f1c-212">请参阅[角色和权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)以及[查看和分配角色](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)，了解如何在 Azure Active Directory 中分配管理员角色。</span><span class="sxs-lookup"><span data-stu-id="60f1c-212">See [Roles and permissions](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal) to learn how to assign admin roles in Azure Active Directory.</span></span> |
|||

### <a name="teams-default-apps"></a><span data-ttu-id="60f1c-213">Teams 默认应用</span><span class="sxs-lookup"><span data-stu-id="60f1c-213">Teams default apps</span></span> 

<span data-ttu-id="60f1c-214">Teams 提供一些第一方（Microsoft 提供）和第三方应用来吸引用户、支持高效工作，并在 Teams 中集成了常用的业务服务。</span><span class="sxs-lookup"><span data-stu-id="60f1c-214">Teams provides a number of first-party (Microsoft provided) and third-party apps to engage users, support productivity, and integrate commonly used business services into Teams.</span></span> <span data-ttu-id="60f1c-215">从 Teams 应用商店获取应用。</span><span class="sxs-lookup"><span data-stu-id="60f1c-215">Get apps from the Teams Store.</span></span> <span data-ttu-id="60f1c-216">默认情况下 Teams 中已启用应用。</span><span class="sxs-lookup"><span data-stu-id="60f1c-216">Apps are turned on by default in Teams.</span></span> 

<span data-ttu-id="60f1c-217">若要详细了解如何在 Teams 中部署和管理应用，请参阅我们深入的[应用、聊天机器人和连接器](deploy-apps-microsoft-teams-landing-page.md)指引。</span><span class="sxs-lookup"><span data-stu-id="60f1c-217">To learn more about rolling out and managing apps in Teams, see our in-depth [Apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md) guidance.</span></span>


## <a name="additional-deployment-decisions"></a><span data-ttu-id="60f1c-218">其他部署决策</span><span class="sxs-lookup"><span data-stu-id="60f1c-218">Additional deployment decisions</span></span>

<span data-ttu-id="60f1c-219">你可能需要根据组织的需求和配置更改这些设置。</span><span class="sxs-lookup"><span data-stu-id="60f1c-219">You may want to change these settings, based on your organization's needs and configuration.</span></span>

### <a name="teams-licensing"></a><span data-ttu-id="60f1c-220">Teams 许可</span><span class="sxs-lookup"><span data-stu-id="60f1c-220">Teams licensing</span></span>

<span data-ttu-id="60f1c-221">Teams 作为许多 Office 365 许可证的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="60f1c-221">Teams is provided as part of many Office 365 licenses.</span></span> <span data-ttu-id="60f1c-222">若要详细了解 Teams 许可，请参阅[适用于 Teams 的 Office 365 许可](office-365-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-222">To learn more about Teams licensing, see [Office 365 licensing for Teams](office-365-licensing.md).</span></span>

|<span data-ttu-id="60f1c-223">询问你自己</span><span class="sxs-lookup"><span data-stu-id="60f1c-223">Ask yourself</span></span>|<span data-ttu-id="60f1c-224">操作</span><span class="sxs-lookup"><span data-stu-id="60f1c-224">Action</span></span> |
|------------|-------|
|<span data-ttu-id="60f1c-225">我的用户是否有使用要部署的所有 Teams 功能所需的许可证？</span><span class="sxs-lookup"><span data-stu-id="60f1c-225">Do my users have the licenses they need in order to use all the Teams features I want to roll out?</span></span> | <span data-ttu-id="60f1c-226">若要了解许可要求，请阅读[适用于 Teams 的 Office 365 许可](office-365-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-226">To learn about licensing requirements, read [Office 365 licensing for Teams](office-365-licensing.md).</span></span>|
|||

### <a name="exchange-and-sharepoint-interoperability"></a><span data-ttu-id="60f1c-227">Exchange 和 SharePoint 互操作性</span><span class="sxs-lookup"><span data-stu-id="60f1c-227">Exchange and SharePoint interoperability</span></span> 

<span data-ttu-id="60f1c-228">为了获得全面的 Teams 体验，应该为每个用户启用 Exchange Online、SharePoint Online 和 Office 365 组创建。</span><span class="sxs-lookup"><span data-stu-id="60f1c-228">For the full Teams experience, every user should be enabled for Exchange Online, SharePoint Online, and Office 365 Group creation.</span></span> <span data-ttu-id="60f1c-229">下列文章概述的信息与以下各项相关：各种环境中托管的 Exchange 邮箱、Exchange 与 Teams 的交互方式，以及 SharePoint 和 OneDrive for Business 的类似注意事项。</span><span class="sxs-lookup"><span data-stu-id="60f1c-229">The following articles outline information related to Exchange mailboxes hosted in various environments, how Exchange and Teams interact, and similar considerations for SharePoint and OneDrive for Business.</span></span> 

|<span data-ttu-id="60f1c-230">询问你自己</span><span class="sxs-lookup"><span data-stu-id="60f1c-230">Ask yourself</span></span>|<span data-ttu-id="60f1c-231">操作</span><span class="sxs-lookup"><span data-stu-id="60f1c-231">Action</span></span> |
|------------|-------|
| <span data-ttu-id="60f1c-232">是否能随当前 Exchange 和 SharePoint 部署一起部署所需的 Teams 功能？</span><span class="sxs-lookup"><span data-stu-id="60f1c-232">Will I be able to deploy the Teams features that I require with the current Exchange and SharePoint deployments?</span></span> |<span data-ttu-id="60f1c-233">有关 Teams 中的 Exchange 和 SharePoint 的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="60f1c-233">For more information about Exchange and SharePoint in Teams, see:</span></span><ul><li> [<span data-ttu-id="60f1c-234">Exchange 与 Teams 如何交互</span><span class="sxs-lookup"><span data-stu-id="60f1c-234">How Exchange and Teams interact</span></span>](exchange-teams-interact.md)</li><li>[<span data-ttu-id="60f1c-235">SharePoint Online 和 OneDrive for Business 与 Teams 如何交互</span><span class="sxs-lookup"><span data-stu-id="60f1c-235">How SharePoint Online and OneDrive for Business interact with Teams</span></span>](sharepoint-onedrive-interact.md)|
|||

### <a name="teams-limits-and-specifications"></a><span data-ttu-id="60f1c-236">Teams 限制和规范</span><span class="sxs-lookup"><span data-stu-id="60f1c-236">Teams limits and specifications</span></span> 

<span data-ttu-id="60f1c-237">规划 Teams 的企业部署时，你应考虑任何相关的限制和规范，例如团队中的最大成员数、用户可创建的最大团队数，诸如此类。</span><span class="sxs-lookup"><span data-stu-id="60f1c-237">When planning an enterprise deployment of Teams, you should take into account any relevant limitations and specifications, such as the maximum number of members in a team, the maximum number of teams a user can create, and so on.</span></span>

|<span data-ttu-id="60f1c-238">询问你自己</span><span class="sxs-lookup"><span data-stu-id="60f1c-238">Ask yourself</span></span>|<span data-ttu-id="60f1c-239">操作</span><span class="sxs-lookup"><span data-stu-id="60f1c-239">Action</span></span> |
|------------|-------|
| <span data-ttu-id="60f1c-240">我的 Teams 部署可能会遇到什么限制？</span><span class="sxs-lookup"><span data-stu-id="60f1c-240">What limits am I likely to hit with my Teams rollout?</span></span> | <span data-ttu-id="60f1c-241">若要了解详细信息，请阅读 [Teams 的限制和规范](limits-specifications-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-241">To learn more, read [Limits and specifications for Teams](limits-specifications-teams.md).</span></span> |
|||

### <a name="office-365-urls-and-ports"></a><span data-ttu-id="60f1c-242">Office 365 URL 和端口</span><span class="sxs-lookup"><span data-stu-id="60f1c-242">Office 365 URLs and ports</span></span>

<span data-ttu-id="60f1c-243">对其 Internet 流量保持精细控制的组织应阅读 [Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)，了解必须为 Teams 正确配置的 URL、IP 地址、端口和协议的最新列表。</span><span class="sxs-lookup"><span data-stu-id="60f1c-243">Organizations that maintain fine-grained control of their internet traffic should read [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) for an up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="60f1c-244">Microsoft 一直在改进 Office 365 服务并添加新功能，因此，所需端口、URL 和 IP 地址可能会随时间变化。</span><span class="sxs-lookup"><span data-stu-id="60f1c-244">Microsoft is continuously improving the Office 365 service and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="60f1c-245">建议你通过 RSS 订阅，以在此信息更新或更改时收到通知。</span><span class="sxs-lookup"><span data-stu-id="60f1c-245">We recommend that you subscribe via RSS to receive notifications when this information is updated or changed.</span></span> <span data-ttu-id="60f1c-246">至少需确保你已打开在上述[聊天部署先决条件](#chat-deployment-prerequisites)中列出的端口。</span><span class="sxs-lookup"><span data-stu-id="60f1c-246">At a minimum, make sure you've opened the ports listed above in [Chat deployment prerequisites](#chat-deployment-prerequisites).</span></span>

|<span data-ttu-id="60f1c-247">询问你自己</span><span class="sxs-lookup"><span data-stu-id="60f1c-247">Ask yourself</span></span>|<span data-ttu-id="60f1c-248">操作</span><span class="sxs-lookup"><span data-stu-id="60f1c-248">Action</span></span> |
|------------|-------|
| <span data-ttu-id="60f1c-249">是否需要 Internet 访问规则才能让用户使用 Teams，或者开放最少所需的端口是否足够？</span><span class="sxs-lookup"><span data-stu-id="60f1c-249">Do I require internet access rules to enable users to use Teams, or is it sufficient to open the minimum required ports?</span></span> | <span data-ttu-id="60f1c-250">若要了解详细信息，请参阅 [Office 365 URL 和 IP 地址范围](office-365-urls-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-250">To learn more, see [Office 365 URLs and IP address ranges](office-365-urls-ip-address-ranges.md).</span></span>|
|||


### <a name="governance-naming-conventions-who-can-create-teams"></a><span data-ttu-id="60f1c-251">管理（命名约定，可创建团队的人员）</span><span class="sxs-lookup"><span data-stu-id="60f1c-251">Governance (naming conventions, who can create teams)</span></span>

<span data-ttu-id="60f1c-252">你的组织可能需要你对团队的命名和分类方式、谁可以创建团队以及团队到期、保留和存档加以控制。</span><span class="sxs-lookup"><span data-stu-id="60f1c-252">Your organization might require that you implement controls on how teams are named and classified, who can create teams, and team expiration, retention, and archiving.</span></span> <span data-ttu-id="60f1c-253">这称为管理。</span><span class="sxs-lookup"><span data-stu-id="60f1c-253">This is called governance.</span></span> <span data-ttu-id="60f1c-254">你可以使用 Azure Active Directory (Azure AD) 来配置各个方面。</span><span class="sxs-lookup"><span data-stu-id="60f1c-254">You can use Azure Active Directory (Azure AD) to configure each of these areas.</span></span>


| <span data-ttu-id="60f1c-255">询问你自己</span><span class="sxs-lookup"><span data-stu-id="60f1c-255">Ask yourself</span></span> | <span data-ttu-id="60f1c-256">操作</span><span class="sxs-lookup"><span data-stu-id="60f1c-256">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="60f1c-257">是否需要对谁可以创建团队进行控制？</span><span class="sxs-lookup"><span data-stu-id="60f1c-257">Will I need to implement controls on who can create teams?</span></span>| <span data-ttu-id="60f1c-258">请阅读[在 Teams 中规划管理](plan-teams-governance.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-258">Read [Plan for governance in Teams](plan-teams-governance.md).</span></span>|
|<span data-ttu-id="60f1c-259">是否需要对团队的命名方式进行控制？</span><span class="sxs-lookup"><span data-stu-id="60f1c-259">Will I need to implement controls on how teams are named?</span></span>|<span data-ttu-id="60f1c-260">请阅读[在 Azure AD 中为 Office 365 组实施命名策略](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-260">Read [Enforce a naming policy for Office 365 groups in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy).</span></span>|
|||

### <a name="teams-application-policy-side-rail-control"></a><span data-ttu-id="60f1c-261">Teams 应用程序策略（侧边栏控制）</span><span class="sxs-lookup"><span data-stu-id="60f1c-261">Teams application policy (side-rail control)</span></span>

<span data-ttu-id="60f1c-262">固定的应用显示在 Teams 的侧边栏中。</span><span class="sxs-lookup"><span data-stu-id="60f1c-262">A pinned app shows up in the side rail in Teams.</span></span> <span data-ttu-id="60f1c-263">通过创建 Teams 应用程序策略，你可以预先配置一组固定的 Teams 应用，以便针对经过挑选的用户组个性化 Teams。</span><span class="sxs-lookup"><span data-stu-id="60f1c-263">By creating Teams application policies, you can preconfigure sets of pinned Teams apps to personalize Teams for select groups of users.</span></span> <span data-ttu-id="60f1c-264">默认情况下，“**在 Microsoft Teams 中允许外部应用**”设置处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="60f1c-264">By default, the **Allow external apps in Microsoft Teams** setting is turned on.</span></span>

| <span data-ttu-id="60f1c-265">询问你自己</span><span class="sxs-lookup"><span data-stu-id="60f1c-265">Ask yourself</span></span> | <span data-ttu-id="60f1c-266">操作</span><span class="sxs-lookup"><span data-stu-id="60f1c-266">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="60f1c-267">是否应该创建一组预先配置的固定 Teams 应用程序？</span><span class="sxs-lookup"><span data-stu-id="60f1c-267">Should I create preconfigured sets of pinned Teams applications?</span></span> | <span data-ttu-id="60f1c-268">请阅读 [Teams 中应用的管理员设置](admin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-268">Read [Admin settings for apps in Teams](admin-settings.md).</span></span>|
|<span data-ttu-id="60f1c-269">如何决定哪些组接收这些应用分组？</span><span class="sxs-lookup"><span data-stu-id="60f1c-269">How will I decide which groups receive these app groupings?</span></span>|<span data-ttu-id="60f1c-270">请阅读[团队应用权限和注意事项](app-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-270">Read [Teams apps permissions and considerations](app-permissions.md).</span></span>|
|||

### <a name="archiving-and-compliance"></a><span data-ttu-id="60f1c-271">存档与合规性</span><span class="sxs-lookup"><span data-stu-id="60f1c-271">Archiving and compliance</span></span> 

<span data-ttu-id="60f1c-272">你的组织可能要求你对团队的存档方式以及某些类型的团队中包含的数据类型加以控制。</span><span class="sxs-lookup"><span data-stu-id="60f1c-272">Your organization might require that you implement controls on how teams are archived and the types of data that are held in certain types of teams.</span></span> <span data-ttu-id="60f1c-273">请阅读 [Teams 中的的安全性和合规性概述](security-compliance-overview.md)，了解哪些设置默认情况下已启用。</span><span class="sxs-lookup"><span data-stu-id="60f1c-273">Read [Overview of security and compliance in Teams](security-compliance-overview.md) to learn which settings are turned on by default.</span></span>

| <span data-ttu-id="60f1c-274">询问你自己</span><span class="sxs-lookup"><span data-stu-id="60f1c-274">Ask yourself</span></span> | <span data-ttu-id="60f1c-275">操作</span><span class="sxs-lookup"><span data-stu-id="60f1c-275">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="60f1c-276">是否需要配置团队保留？</span><span class="sxs-lookup"><span data-stu-id="60f1c-276">Will I need to configure team retention?</span></span>|<span data-ttu-id="60f1c-277">若要设置保留策略，请参阅[设置 Teams 保留策略](retention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-277">To set up retention policies, see [Set up Teams retention policies](retention-policies.md).</span></span>|
|<span data-ttu-id="60f1c-278">是否需要配置团队存档？</span><span class="sxs-lookup"><span data-stu-id="60f1c-278">Will I need to configure team archiving?</span></span>|<span data-ttu-id="60f1c-279">若要存档或还原团队，请参阅[存档或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-279">To archive or restore a team, see [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>|
|<span data-ttu-id="60f1c-280">是否需要配置其他合规性设置？</span><span class="sxs-lookup"><span data-stu-id="60f1c-280">Will I need to configure additional compliance settings?</span></span>|<span data-ttu-id="60f1c-281">有关安全性和合规性的详细信息，请参阅 [Teams 中的安全性和合规性概述](security-compliance-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-281">For more information about security and compliance, see [Overview of security and compliance in Teams](security-compliance-overview.md).</span></span>|
|||

### <a name="conditional-access"></a><span data-ttu-id="60f1c-282">条件访问</span><span class="sxs-lookup"><span data-stu-id="60f1c-282">Conditional access</span></span> 

<span data-ttu-id="60f1c-283">对于核心工作效率方案（包括会议、日历、互操作聊天和文件共享），Teams 高度依赖 Exchange Online、SharePoint Online 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="60f1c-283">Teams relies heavily on Exchange Online, SharePoint Online, and Skype for Business Online for core productivity scenarios, including meetings, calendars, interop chats, and file sharing.</span></span> <span data-ttu-id="60f1c-284">当用户在任何客户端上直接登录 Teams 时，为这些云应用设置的条件访问策略将应用于 Teams。</span><span class="sxs-lookup"><span data-stu-id="60f1c-284">Conditional access policies that are set for these cloud apps apply to Teams when a user signs in directly to Teams, on any client.</span></span> <span data-ttu-id="60f1c-285">为这些云应用设置的条件访问策略控制各个方面，例如用户是否可从某些网络访问 Teams 服务。</span><span class="sxs-lookup"><span data-stu-id="60f1c-285">Conditional access policies that are set for the Teams cloud app control aspects such as whether users can access Teams services from certain networks.</span></span>

| <span data-ttu-id="60f1c-286">询问你自己</span><span class="sxs-lookup"><span data-stu-id="60f1c-286">Ask yourself</span></span> | <span data-ttu-id="60f1c-287">操作</span><span class="sxs-lookup"><span data-stu-id="60f1c-287">Action</span></span> |
|--------------|--------|
|<br><span data-ttu-id="60f1c-288">是否需要为 Teams 配置条件访问？</span><span class="sxs-lookup"><span data-stu-id="60f1c-288">Will I need to configure conditional access for Teams?</span></span>|<ul><li><span data-ttu-id="60f1c-289">若要了解访问策略的工作方式，请参阅[条件访问策略如何在 Teams 中发挥作用？](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)</span><span class="sxs-lookup"><span data-stu-id="60f1c-289">To understand how access policies work, see [How do conditional access policies work for Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)</span></span></li><li><span data-ttu-id="60f1c-290">若要为 Teams 设置多重身份验证 (MFA)，请参阅：</span><span class="sxs-lookup"><span data-stu-id="60f1c-290">To set up multi-factor authentication (MFA) for Teams, see:</span></span><ul><li>[<span data-ttu-id="60f1c-291">快速入门：具有 Azure Active Directory 条件访问权限的特定应用需要 MFA</span><span class="sxs-lookup"><span data-stu-id="60f1c-291">Quickstart: Require MFA for specific apps with Azure Active Directory conditional access</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-mfa)</li><li>[<span data-ttu-id="60f1c-292">Azure Active Directory 条件访问设置参考</span><span class="sxs-lookup"><span data-stu-id="60f1c-292">Azure Active Directory conditional access settings reference</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|
|||


### <a name="education-edu"></a><span data-ttu-id="60f1c-293">教育版 (EDU)</span><span class="sxs-lookup"><span data-stu-id="60f1c-293">Education (EDU)</span></span> 

<span data-ttu-id="60f1c-294">在教育行业工作的 IT 专业人员可以利用 Teams 教育版，该版本提供的许多功能经过定制，可满足学生、教职员工和更广泛行业特定于教育的方案需求。</span><span class="sxs-lookup"><span data-stu-id="60f1c-294">IT pros working in education can take advantage of Teams for Education, which comes with a number of capabilities that have been tailored to meet education-specific scenarios for students, faculty, and the wider business.</span></span>

| <span data-ttu-id="60f1c-295">询问你自己</span><span class="sxs-lookup"><span data-stu-id="60f1c-295">Ask yourself</span></span> | <span data-ttu-id="60f1c-296">操作</span><span class="sxs-lookup"><span data-stu-id="60f1c-296">Action</span></span> |
|--------------|--------|
|<span data-ttu-id="60f1c-297">是否要使用特定于 EDU 的 Teams 模板？</span><span class="sxs-lookup"><span data-stu-id="60f1c-297">Will I use EDU-specific Teams templates?</span></span> |<span data-ttu-id="60f1c-298">若要详细了解 Teams 教育版，请参阅[面向管理员的 Microsoft 教育管理常见问题](plan-teams-governance-edu.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-298">To learn more about Teams for Education, see [Microsoft Education governance FAQ for admins](plan-teams-governance-edu.md).</span></span>|
|<span data-ttu-id="60f1c-299">是否要部署范围限定的搜索？</span><span class="sxs-lookup"><span data-stu-id="60f1c-299">Will I deploy scoped search?</span></span>|<span data-ttu-id="60f1c-300">若要为 EDU 设置 Teams，请参阅[快速入门 - Teams 教育版管理](teams-quick-start-edu.yml)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-300">To set up Teams for EDU, see [Quickstart - Teams for Education admins](teams-quick-start-edu.yml).</span></span>|
|<span data-ttu-id="60f1c-301">是否要将 Teams 与 School Data Sync 服务集成来配置用户帐户？</span><span class="sxs-lookup"><span data-stu-id="60f1c-301">Will I integrate Teams with the School Data Sync service to provision user accounts?</span></span>|[<span data-ttu-id="60f1c-302">面向教育版管理员的 Teams 资源</span><span class="sxs-lookup"><span data-stu-id="60f1c-302">Teams resources for Education admins</span></span>](resources-teams-edu.md)|
|||

### <a name="government---gcc-considerations"></a><span data-ttu-id="60f1c-303">政府版 - GCC 注意事项</span><span class="sxs-lookup"><span data-stu-id="60f1c-303">Government - GCC considerations</span></span>

<span data-ttu-id="60f1c-304">对于在美国联邦政府、州政府、地方政府、部族政府或准州政府实体或者所处理数据遵从政府法规和要求的其他实体推动 Office 365 部署的 IT 专业人员，使用 Microsoft 365 政府版 - GCC（政府社区云）可以适当地满足其需求。</span><span class="sxs-lookup"><span data-stu-id="60f1c-304">The use of Microsoft 365 for Government - GCC (Government Community Cloud) is appropriate to meet the requirements of IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that’s subject to government regulations and requirements.</span></span>

| <span data-ttu-id="60f1c-305">询问你自己</span><span class="sxs-lookup"><span data-stu-id="60f1c-305">Ask yourself</span></span> | <span data-ttu-id="60f1c-306">操作</span><span class="sxs-lookup"><span data-stu-id="60f1c-306">Action</span></span> |
|--------------|--------|
| <span data-ttu-id="60f1c-307">是否要在 Microsoft 365 政府版 – GCC 环境中部署 Teams？</span><span class="sxs-lookup"><span data-stu-id="60f1c-307">Will I need to deploy Teams in a Microsoft 365 Government – GCC environment?</span></span> | <span data-ttu-id="60f1c-308">有关部署注意事项，请参阅[规划 Microsoft 365 政府版 - GCC 部署](plan-for-government-gcc.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-308">For deployment considerations, see [Plan for Microsoft 365 Government - GCC deployments](plan-for-government-gcc.md).</span></span>|
|||

## <a name="next-steps"></a><span data-ttu-id="60f1c-309">后续步骤</span><span class="sxs-lookup"><span data-stu-id="60f1c-309">Next steps</span></span>
- <span data-ttu-id="60f1c-310">[推动采用](adopt-microsoft-teams-landing-page.md)聊天、团队、频道和应用。</span><span class="sxs-lookup"><span data-stu-id="60f1c-310">[Drive adoption](adopt-microsoft-teams-landing-page.md) of chat, teams, channels, & apps.</span></span>
- <span data-ttu-id="60f1c-311">在 Teams 的初步部署中加入特别推荐的应用 - 例如 Planner。</span><span class="sxs-lookup"><span data-stu-id="60f1c-311">Include featured apps - such as Planner - in your initial Teams rollout.</span></span> <span data-ttu-id="60f1c-312">在推动 Teams 采用的过程中添加其他[应用、聊天机器人和连接器](deploy-apps-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="60f1c-312">Add other [apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md) as you drive Teams adoption.</span></span>
- [<span data-ttu-id="60f1c-313">部署会议</span><span class="sxs-lookup"><span data-stu-id="60f1c-313">Roll out meetings & conferencing</span></span>](deploy-meetings-microsoft-teams-landing-page.md)
- [<span data-ttu-id="60f1c-314">部署云语音</span><span class="sxs-lookup"><span data-stu-id="60f1c-314">Roll out cloud voice</span></span>](cloud-voice-landing-page.md)

