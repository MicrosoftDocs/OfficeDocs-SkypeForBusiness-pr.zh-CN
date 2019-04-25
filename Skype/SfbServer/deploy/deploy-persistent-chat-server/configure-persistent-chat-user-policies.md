---
title: 配置 Skype for Business Server 2015 中的持久聊天用户策略
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 摘要： 阅读本主题可了解如何为业务服务器 2015 Persistent Chat Server in Skype 创建初始用户策略。 持久聊天用户策略确定允许用户访问聊天室。
ms.openlocfilehash: e082898d92e622827e2543316b07a8be224c56c3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225453"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="2ea2d-104">配置 Skype for Business Server 2015 中的持久聊天用户策略</span><span class="sxs-lookup"><span data-stu-id="2ea2d-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2ea2d-105">**摘要：** 阅读本主题可了解如何为业务服务器 2015 Persistent Chat Server in Skype 创建初始用户策略。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="2ea2d-106">持久聊天用户策略确定允许用户访问聊天室。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="2ea2d-107">您可以管理持久聊天服务器在以下级别的用户策略： 全局、 站点或用户。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="2ea2d-108">最初，您配置全局策略以为部署中的所有用户启用持久聊天设置，然后创建其他用户和站点策略以控制是否为特定用户和站点打开持久聊天。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="2ea2d-109">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="2ea2d-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="2ea2d-110">配置全局策略</span><span class="sxs-lookup"><span data-stu-id="2ea2d-110">Configure the global policy</span></span>
    
- <span data-ttu-id="2ea2d-111">创建站点策略</span><span class="sxs-lookup"><span data-stu-id="2ea2d-111">Create a site policy</span></span>
    
- <span data-ttu-id="2ea2d-112">创建用户策略</span><span class="sxs-lookup"><span data-stu-id="2ea2d-112">Create a user policy</span></span>
    
- <span data-ttu-id="2ea2d-113">将策略应用于用户或用户组</span><span class="sxs-lookup"><span data-stu-id="2ea2d-113">Apply a policy to a user or user group</span></span>
    
> [!NOTE] 
> <span data-ttu-id="2ea2d-114">持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="2ea2d-115">中团队提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="2ea2d-116">有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-116">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="2ea2d-117">如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="configure-the-global-policy"></a><span data-ttu-id="2ea2d-118">配置全局策略</span><span class="sxs-lookup"><span data-stu-id="2ea2d-118">Configure the global policy</span></span>

<span data-ttu-id="2ea2d-119">配置全局策略：</span><span class="sxs-lookup"><span data-stu-id="2ea2d-119">To configure the global policy:</span></span>
  
1. <span data-ttu-id="2ea2d-120">从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-120">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2ea2d-121">从**开始**菜单上，选择业务 Server Control Panel Skype 或打开一个浏览器窗口中，，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-121">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="2ea2d-122">在业务 Server Control Panel 的 Skype，单击**持久聊天**，，然后单击**持久聊天策略**。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-122">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="2ea2d-123">单击策略列表中的“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-123">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="2ea2d-124">在“**编辑持久聊天策略 - 全局**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="2ea2d-124">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="2ea2d-125">在“**名称**”中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-125">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="2ea2d-126">在**说明**框中，提供有关用户策略内容 （例如， _centralsitename_的全局策略） 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-126">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="2ea2d-127">若要控制的所有站点和未通过站点策略或用户策略明确控制的用户的持久聊天，请选中或清除**启用持久聊天**复选框。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-127">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="2ea2d-128">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-128">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="2ea2d-129">创建站点策略</span><span class="sxs-lookup"><span data-stu-id="2ea2d-129">Create a site policy</span></span>

<span data-ttu-id="2ea2d-130">对于已部署的每个网站，您可以创建特定于站点的持久聊天策略。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-130">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="2ea2d-131">站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-131">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="2ea2d-132">若要创建站点策略：</span><span class="sxs-lookup"><span data-stu-id="2ea2d-132">To create a site policy:</span></span>
  
1. <span data-ttu-id="2ea2d-133">从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-133">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2ea2d-134">从**开始**菜单上，选择业务 Server Control Panel Skype 或打开一个浏览器窗口中，，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-134">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="2ea2d-135">在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天策略**”。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-135">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="2ea2d-136">单击“**新建**”，然后单击“**站点策略**”。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-136">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="2ea2d-137">在“**选择站点**”中，单击要应用此策略的站点。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-137">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="2ea2d-138">在“**新建持久聊天策略**”中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="2ea2d-138">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="2ea2d-139">在“**名称**”中，指定新站点策略的名称（例如，Redmond）。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-139">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="2ea2d-140">在“**说明**”中，提供有关该站点策略内容的详细信息（例如，Redmond 的聊天室策略）。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-140">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="2ea2d-141">若要控制未通过站点策略明确控制的所有站点的持久聊天，请选中或清除“**启用持久聊天**”复选框。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-141">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="2ea2d-142">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-142">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="2ea2d-143">创建用户策略</span><span class="sxs-lookup"><span data-stu-id="2ea2d-143">Create a user policy</span></span>

<span data-ttu-id="2ea2d-144">您可以创建覆盖全局策略和用户所属的任何站点策略的特定于用户的策略。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-144">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="2ea2d-145">若要创建用户策略：</span><span class="sxs-lookup"><span data-stu-id="2ea2d-145">To create a user policy:</span></span>
  
1. <span data-ttu-id="2ea2d-146">从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-146">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2ea2d-147">从**开始**菜单上，选择业务 Server Control Panel Skype 或打开一个浏览器窗口中，，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-147">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="2ea2d-148">在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天策略**”。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-148">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="2ea2d-149">单击“**新建**”，然后单击“**用户策略**”。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-149">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="2ea2d-150">在“**新建持久聊天策略**”中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="2ea2d-150">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="2ea2d-151">在“**名称**”中，指定新用户策略的名称。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-151">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="2ea2d-152">在**说明**框中，提供有关用户策略内容 （例如，为特定用户的持久聊天策略） 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-152">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="2ea2d-153">若要控制未专门通过用户策略控制的所有用户的持久聊天，请选中或清除**启用持久聊天**复选框。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-153">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="2ea2d-154">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-154">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="2ea2d-155">将策略应用于用户帐户</span><span class="sxs-lookup"><span data-stu-id="2ea2d-155">Apply a policy to a user account</span></span>

<span data-ttu-id="2ea2d-156">创建策略后，您可以应用这些更改的用户帐户，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2ea2d-156">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="2ea2d-157">从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-157">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2ea2d-158">从**开始**菜单上，选择业务 Server Control Panel Skype 或打开一个浏览器窗口中，，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-158">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="2ea2d-159">在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-159">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="2ea2d-160">在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-160">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="2ea2d-161">在**持久聊天策略**下**的企业服务器用户编辑 Skype** ，选择要应用的持久聊天用户策略。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-161">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2ea2d-162">**\<自动\>** 设置应用默认有效策略。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-162">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="2ea2d-163">服务器将自动应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-163">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="2ea2d-164">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="2ea2d-164">Click **Commit**.</span></span>
    

