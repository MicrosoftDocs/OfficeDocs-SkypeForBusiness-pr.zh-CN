---
title: 配置 Skype for Business Server 2015 中的持久聊天用户策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 摘要：阅读本主题，了解如何在 Skype for business Server 2015 中为持久聊天服务器创建初始用户策略。 持久聊天用户策略确定是否允许用户访问聊天室。
ms.openlocfilehash: a51304c9e85951e9858d56c511aa8c7519babe51
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795693"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="174bb-104">配置 Skype for Business Server 2015 中的持久聊天用户策略</span><span class="sxs-lookup"><span data-stu-id="174bb-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="174bb-105">**摘要：** 阅读本主题，了解如何在 Skype for business Server 2015 中为持久聊天服务器创建初始用户策略。</span><span class="sxs-lookup"><span data-stu-id="174bb-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="174bb-106">持久聊天用户策略确定是否允许用户访问聊天室。</span><span class="sxs-lookup"><span data-stu-id="174bb-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="174bb-107">你可以在以下级别管理持久聊天服务器用户策略：全局、网站或用户。</span><span class="sxs-lookup"><span data-stu-id="174bb-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="174bb-108">最初，您配置全局策略以为部署中的所有用户启用持久聊天设置，然后创建其他用户和站点策略以控制是否为特定用户和站点打开持久聊天。</span><span class="sxs-lookup"><span data-stu-id="174bb-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="174bb-109">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="174bb-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="174bb-110">配置全局策略</span><span class="sxs-lookup"><span data-stu-id="174bb-110">Configure the global policy</span></span>
    
- <span data-ttu-id="174bb-111">创建站点策略</span><span class="sxs-lookup"><span data-stu-id="174bb-111">Create a site policy</span></span>
    
- <span data-ttu-id="174bb-112">创建用户策略</span><span class="sxs-lookup"><span data-stu-id="174bb-112">Create a user policy</span></span>
    
- <span data-ttu-id="174bb-113">将策略应用于用户或用户组</span><span class="sxs-lookup"><span data-stu-id="174bb-113">Apply a policy to a user or user group</span></span>
    
> [!NOTE] 
> <span data-ttu-id="174bb-114">Skype for business Server 2015 中提供了持久聊天，但 Skype for business Server 2019 不再支持此功能。</span><span class="sxs-lookup"><span data-stu-id="174bb-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="174bb-115">团队中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="174bb-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="174bb-116">有关详细信息，请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。</span><span class="sxs-lookup"><span data-stu-id="174bb-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="174bb-117">如果需要使用持久聊天，您可以选择将需要此功能的用户迁移到团队，或继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="174bb-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="configure-the-global-policy"></a><span data-ttu-id="174bb-118">配置全局策略</span><span class="sxs-lookup"><span data-stu-id="174bb-118">Configure the global policy</span></span>

<span data-ttu-id="174bb-119">要配置全局策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="174bb-119">To configure the global policy:</span></span>
  
1. <span data-ttu-id="174bb-120">从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="174bb-120">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="174bb-121">从 "**开始**" 菜单中，选择 "Skype For business 服务器" 控制面板或打开一个浏览器窗口，然后输入管理员 URL。</span><span class="sxs-lookup"><span data-stu-id="174bb-121">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="174bb-122">在 "Skype for Business 服务器控制面板" 中，单击 "**持久聊天**"，然后单击 "**持久聊天策略**"。</span><span class="sxs-lookup"><span data-stu-id="174bb-122">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="174bb-123">单击策略列表中的“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="174bb-123">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="174bb-124">在“**编辑持久聊天策略 - 全局**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="174bb-124">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="174bb-125">在“**名称**”中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。</span><span class="sxs-lookup"><span data-stu-id="174bb-125">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="174bb-126">在 "**说明**" 中，提供有关用户策略的详细信息（例如， _centralSiteName_的全局策略）。</span><span class="sxs-lookup"><span data-stu-id="174bb-126">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="174bb-127">若要为未通过网站策略或用户策略明确控制的所有网站和用户控制持久聊天，请选中或清除 "**启用持久聊天**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="174bb-127">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="174bb-128">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="174bb-128">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="174bb-129">创建站点策略</span><span class="sxs-lookup"><span data-stu-id="174bb-129">Create a site policy</span></span>

<span data-ttu-id="174bb-130">对于已部署的每个网站，你可以创建特定于站点的持久聊天策略。</span><span class="sxs-lookup"><span data-stu-id="174bb-130">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="174bb-131">站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。</span><span class="sxs-lookup"><span data-stu-id="174bb-131">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="174bb-132">要创建网站策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="174bb-132">To create a site policy:</span></span>
  
1. <span data-ttu-id="174bb-133">从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="174bb-133">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="174bb-134">从 "**开始**" 菜单中，选择 "Skype For business 服务器" 控制面板或打开一个浏览器窗口，然后输入管理员 URL。</span><span class="sxs-lookup"><span data-stu-id="174bb-134">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="174bb-135">在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天策略**”。</span><span class="sxs-lookup"><span data-stu-id="174bb-135">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="174bb-136">单击“**新建**”，然后单击“**站点策略**”。</span><span class="sxs-lookup"><span data-stu-id="174bb-136">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="174bb-137">在“**选择站点**”中，单击要应用此策略的站点。</span><span class="sxs-lookup"><span data-stu-id="174bb-137">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="174bb-138">在“**新建持久聊天策略**”中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="174bb-138">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="174bb-139">在“**名称**”中，指定新站点策略的名称（例如，Redmond）。</span><span class="sxs-lookup"><span data-stu-id="174bb-139">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="174bb-140">在“**说明**”中，提供有关该站点策略内容的详细信息（例如，Redmond 的聊天室策略）。</span><span class="sxs-lookup"><span data-stu-id="174bb-140">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="174bb-141">若要控制未通过站点策略明确控制的所有站点的持久聊天，请选中或清除“**启用持久聊天**”复选框。</span><span class="sxs-lookup"><span data-stu-id="174bb-141">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="174bb-142">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="174bb-142">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="174bb-143">创建用户策略</span><span class="sxs-lookup"><span data-stu-id="174bb-143">Create a user policy</span></span>

<span data-ttu-id="174bb-144">你可以创建替代全局策略和用户所属的任何网站策略的特定于用户的策略。</span><span class="sxs-lookup"><span data-stu-id="174bb-144">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="174bb-145">要创建用户策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="174bb-145">To create a user policy:</span></span>
  
1. <span data-ttu-id="174bb-146">从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="174bb-146">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="174bb-147">从 "**开始**" 菜单中，选择 "Skype For business 服务器" 控制面板或打开一个浏览器窗口，然后输入管理员 URL。</span><span class="sxs-lookup"><span data-stu-id="174bb-147">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="174bb-148">在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天策略**”。</span><span class="sxs-lookup"><span data-stu-id="174bb-148">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="174bb-149">单击“**新建**”，然后单击“**用户策略**”。</span><span class="sxs-lookup"><span data-stu-id="174bb-149">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="174bb-150">在“**新建持久聊天策略**”中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="174bb-150">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="174bb-151">在“**名称**”中，指定新用户策略的名称。</span><span class="sxs-lookup"><span data-stu-id="174bb-151">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="174bb-152">在 "**说明**" 中，提供有关用户策略的详细信息（例如，针对特定用户的持久聊天策略）。</span><span class="sxs-lookup"><span data-stu-id="174bb-152">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="174bb-153">若要为未通过用户策略明确控制的所有用户控制持久聊天，请选中或清除 "**启用持久聊天**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="174bb-153">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="174bb-154">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="174bb-154">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="174bb-155">将策略应用于用户帐户</span><span class="sxs-lookup"><span data-stu-id="174bb-155">Apply a policy to a user account</span></span>

<span data-ttu-id="174bb-156">创建策略后，您可以将其应用到用户帐户，如下所示：</span><span class="sxs-lookup"><span data-stu-id="174bb-156">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="174bb-157">从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="174bb-157">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="174bb-158">从 "**开始**" 菜单中，选择 "Skype For business 服务器" 控制面板或打开一个浏览器窗口，然后输入管理员 URL。</span><span class="sxs-lookup"><span data-stu-id="174bb-158">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="174bb-159">在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="174bb-159">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="174bb-160">在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="174bb-160">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="174bb-161">在 "**永久聊天策略**" 下的 "**编辑 Skype for Business 服务器" 用户**中，选择要应用的持久聊天用户策略。</span><span class="sxs-lookup"><span data-stu-id="174bb-161">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="174bb-162">" \*\* \<自动\> \*\*设置" 应用默认有效策略。</span><span class="sxs-lookup"><span data-stu-id="174bb-162">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="174bb-163">服务器将自动应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="174bb-163">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="174bb-164">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="174bb-164">Click **Commit**.</span></span>
    

