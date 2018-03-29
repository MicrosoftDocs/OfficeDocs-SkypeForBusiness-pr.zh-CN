---
title: 配置 Skype for Business Server 2015 中的持久聊天用户策略
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 摘要： 请阅读本主题，以了解如何创建业务服务器 2015年在 Skype 的持久聊天服务器的初始用户策略。 持续的聊天用户策略确定允许用户访问聊天室。
ms.openlocfilehash: 01ed6eb048f1949c93260c554eb58d0c76c5259f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="b55a9-104">配置 Skype for Business Server 2015 中的持久聊天用户策略</span><span class="sxs-lookup"><span data-stu-id="b55a9-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b55a9-105">**摘要：**阅读本主题，以了解如何创建业务服务器 2015年在 Skype 的持久聊天服务器的初始用户策略。</span><span class="sxs-lookup"><span data-stu-id="b55a9-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="b55a9-106">持续的聊天用户策略确定允许用户访问聊天室。</span><span class="sxs-lookup"><span data-stu-id="b55a9-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="b55a9-107">您可以管理以下级别的持久聊天服务器用户策略： 全局站点或用户。</span><span class="sxs-lookup"><span data-stu-id="b55a9-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="b55a9-108">最初，您配置全局策略以为部署中的所有用户启用持久聊天设置，然后创建其他用户和站点策略以控制是否为特定用户和站点打开持久聊天。</span><span class="sxs-lookup"><span data-stu-id="b55a9-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="b55a9-109">本主题包括以下部分：</span><span class="sxs-lookup"><span data-stu-id="b55a9-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="b55a9-110">配置全局策略</span><span class="sxs-lookup"><span data-stu-id="b55a9-110">Configure the global policy</span></span>
    
- <span data-ttu-id="b55a9-111">创建站点策略</span><span class="sxs-lookup"><span data-stu-id="b55a9-111">Create a site policy</span></span>
    
- <span data-ttu-id="b55a9-112">创建用户策略</span><span class="sxs-lookup"><span data-stu-id="b55a9-112">Create a user policy</span></span>
    
- <span data-ttu-id="b55a9-113">将策略应用于用户或用户组</span><span class="sxs-lookup"><span data-stu-id="b55a9-113">Apply a policy to a user or user group</span></span>
    
## <a name="configure-the-global-policy"></a><span data-ttu-id="b55a9-114">配置全局策略</span><span class="sxs-lookup"><span data-stu-id="b55a9-114">Configure the global policy</span></span>

<span data-ttu-id="b55a9-115">要配置全局策略：</span><span class="sxs-lookup"><span data-stu-id="b55a9-115">To configure the global policy:</span></span>
  
1. <span data-ttu-id="b55a9-116">从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b55a9-116">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b55a9-117">从**开始**菜单中，选择 Skype 业务服务器的控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="b55a9-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="b55a9-118">在业务服务器控件面板的 Skype，**持久聊天**，请单击，然后单击**聊天的永久策略**。</span><span class="sxs-lookup"><span data-stu-id="b55a9-118">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="b55a9-119">单击策略列表中的“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="b55a9-119">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="b55a9-120">在“**编辑持久聊天策略 - 全局**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b55a9-120">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="b55a9-121">在“**名称**”中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。</span><span class="sxs-lookup"><span data-stu-id="b55a9-121">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="b55a9-122">在**说明**提供了有关用户策略 （例如， _centralSiteName_的全局策略） 的信息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b55a9-122">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="b55a9-123">若要控制所有站点和用户通过网站策略或用户策略未专门控制的持久聊天，选中或清除**启用持久聊天**复选框。</span><span class="sxs-lookup"><span data-stu-id="b55a9-123">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="b55a9-124">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="b55a9-124">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="b55a9-125">创建站点策略</span><span class="sxs-lookup"><span data-stu-id="b55a9-125">Create a site policy</span></span>

<span data-ttu-id="b55a9-126">对于已部署的每个站点，您可以创建特定于站点的持久聊天策略。</span><span class="sxs-lookup"><span data-stu-id="b55a9-126">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="b55a9-127">站点策略中的配置可覆盖全局策略，但仅适用于站点策略所涵盖的特定站点。</span><span class="sxs-lookup"><span data-stu-id="b55a9-127">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="b55a9-128">要创建站点策略：</span><span class="sxs-lookup"><span data-stu-id="b55a9-128">To create a site policy:</span></span>
  
1. <span data-ttu-id="b55a9-129">从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b55a9-129">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b55a9-130">从**开始**菜单中，选择 Skype 业务服务器的控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="b55a9-130">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="b55a9-131">在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天策略**”。</span><span class="sxs-lookup"><span data-stu-id="b55a9-131">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="b55a9-132">单击“**新建**”，然后单击“**站点策略**”。</span><span class="sxs-lookup"><span data-stu-id="b55a9-132">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="b55a9-133">在“**选择站点**”中，单击要应用此策略的站点。</span><span class="sxs-lookup"><span data-stu-id="b55a9-133">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="b55a9-134">在“**新建持久聊天策略**”中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b55a9-134">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="b55a9-135">在“**名称**”中，指定新站点策略的名称（例如，Redmond）。</span><span class="sxs-lookup"><span data-stu-id="b55a9-135">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="b55a9-136">在“**说明**”中，提供有关该站点策略内容的详细信息（例如，Redmond 的聊天室策略）。</span><span class="sxs-lookup"><span data-stu-id="b55a9-136">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="b55a9-137">若要控制未通过站点策略明确控制的所有站点的持久聊天，请选中或清除“**启用持久聊天**”复选框。</span><span class="sxs-lookup"><span data-stu-id="b55a9-137">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="b55a9-138">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="b55a9-138">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="b55a9-139">创建用户策略</span><span class="sxs-lookup"><span data-stu-id="b55a9-139">Create a user policy</span></span>

<span data-ttu-id="b55a9-140">您可以创建特定于用户的策略，该策略可覆盖用户所属的全局策略和任何站点策略。</span><span class="sxs-lookup"><span data-stu-id="b55a9-140">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="b55a9-141">要创建用户策略：</span><span class="sxs-lookup"><span data-stu-id="b55a9-141">To create a user policy:</span></span>
  
1. <span data-ttu-id="b55a9-142">从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b55a9-142">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b55a9-143">从**开始**菜单中，选择 Skype 业务服务器的控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="b55a9-143">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="b55a9-144">在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天策略**”。</span><span class="sxs-lookup"><span data-stu-id="b55a9-144">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="b55a9-145">单击“**新建**”，然后单击“**用户策略**”。</span><span class="sxs-lookup"><span data-stu-id="b55a9-145">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="b55a9-146">在“**新建持久聊天策略**”中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b55a9-146">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="b55a9-147">在“**名称**”中，指定新用户策略的名称。</span><span class="sxs-lookup"><span data-stu-id="b55a9-147">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="b55a9-148">在**说明**提供了有关用户策略 （例如，持久性聊天针对特定用户的策略） 的信息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b55a9-148">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="b55a9-149">若要控制所有用户通过用户策略不专门控制的持久聊天，选中或清除**启用持久聊天**复选框。</span><span class="sxs-lookup"><span data-stu-id="b55a9-149">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="b55a9-150">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="b55a9-150">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="b55a9-151">向用户组应用策略</span><span class="sxs-lookup"><span data-stu-id="b55a9-151">Apply a policy to a user account</span></span>

<span data-ttu-id="b55a9-152">创建策略后，您可以将策略应用于用户账户，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b55a9-152">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="b55a9-153">从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b55a9-153">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b55a9-154">从**开始**菜单中，选择 Skype 业务服务器的控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="b55a9-154">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="b55a9-155">在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b55a9-155">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="b55a9-156">在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="b55a9-156">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="b55a9-157">**持续对话策略**下**编辑业务服务器用户的 Skype** ，在选择想要应用的持久聊天用户策略。</span><span class="sxs-lookup"><span data-stu-id="b55a9-157">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b55a9-158">**\<自动\>**应用默认的有效策略设置。</span><span class="sxs-lookup"><span data-stu-id="b55a9-158">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="b55a9-159">服务器将自动应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="b55a9-159">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="b55a9-160">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="b55a9-160">Click **Commit**.</span></span>
    

