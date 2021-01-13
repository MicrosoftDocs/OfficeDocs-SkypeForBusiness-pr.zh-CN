---
title: 在 Skype for Business Server 2015 中配置持久聊天用户策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 摘要：阅读本主题，了解如何在 Skype for Business Server 2015 中为持久聊天服务器创建初始用户策略。 持久聊天用户策略确定是否允许用户访问聊天室。
ms.openlocfilehash: 531146a55b0282db191f503ef39e9be9e4d5f879
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802112"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="e7994-104">在 Skype for Business Server 2015 中配置持久聊天用户策略</span><span class="sxs-lookup"><span data-stu-id="e7994-104">Configure Persistent Chat user policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e7994-105">**摘要：** 阅读本主题，了解如何在 Skype for Business Server 2015 中为持久聊天服务器创建初始用户策略。</span><span class="sxs-lookup"><span data-stu-id="e7994-105">**Summary:** Read this topic to learn how to create initial user policies for Persistent Chat Server in Skype for Business Server 2015.</span></span> <span data-ttu-id="e7994-106">持久聊天用户策略确定是否允许用户访问聊天室。</span><span class="sxs-lookup"><span data-stu-id="e7994-106">Persistent Chat user policies determine whether or not users are allowed access to chat rooms.</span></span>
  
<span data-ttu-id="e7994-107">您可以在以下级别管理持久聊天服务器用户策略：全局、站点或用户。</span><span class="sxs-lookup"><span data-stu-id="e7994-107">You can manage Persistent Chat Server user policies at the following levels: global, site, or user.</span></span> <span data-ttu-id="e7994-108">最初，将全局策略配置为为部署中的所有用户启用持久聊天设置，然后创建其他用户和站点策略以控制是否为特定用户和站点启用持久聊天。</span><span class="sxs-lookup"><span data-stu-id="e7994-108">Initially, you configure the global policy to enable Persistent Chat settings for all users in your deployment, and then create additional user and site policies to control whether Persistent Chat is turned on for specific users and sites.</span></span>
  
<span data-ttu-id="e7994-109">本主题包含以下各部分：</span><span class="sxs-lookup"><span data-stu-id="e7994-109">This topic contains the following sections:</span></span>
  
- <span data-ttu-id="e7994-110">配置全局策略</span><span class="sxs-lookup"><span data-stu-id="e7994-110">Configure the global policy</span></span>
    
- <span data-ttu-id="e7994-111">创建站点策略</span><span class="sxs-lookup"><span data-stu-id="e7994-111">Create a site policy</span></span>
    
- <span data-ttu-id="e7994-112">创建用户策略</span><span class="sxs-lookup"><span data-stu-id="e7994-112">Create a user policy</span></span>
    
- <span data-ttu-id="e7994-113">将策略应用于用户或用户组</span><span class="sxs-lookup"><span data-stu-id="e7994-113">Apply a policy to a user or user group</span></span>
    
> [!NOTE] 
> <span data-ttu-id="e7994-114">持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="e7994-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e7994-115">Teams 中也提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="e7994-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="e7994-116">有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。</span><span class="sxs-lookup"><span data-stu-id="e7994-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="e7994-117">如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="e7994-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>

## <a name="configure-the-global-policy"></a><span data-ttu-id="e7994-118">配置全局策略</span><span class="sxs-lookup"><span data-stu-id="e7994-118">Configure the global policy</span></span>

<span data-ttu-id="e7994-119">配置全局策略：</span><span class="sxs-lookup"><span data-stu-id="e7994-119">To configure the global policy:</span></span>
  
1. <span data-ttu-id="e7994-120">使用分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e7994-120">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e7994-121">从 **"开始** "菜单中，选择 Skype for Business Server 控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="e7994-121">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="e7994-122">在 Skype for Business Server 控制面板中，单击 **"持久聊天**"，然后单击"**持久聊天策略"。**</span><span class="sxs-lookup"><span data-stu-id="e7994-122">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="e7994-123">单击策略列表中的“全局”，再单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="e7994-123">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="e7994-124">在“编辑持久聊天策略 - 全局”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e7994-124">In **Edit Persistent Chat Policy - Global**, do the following:</span></span> 
    
   - <span data-ttu-id="e7994-125">在“名称”中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。</span><span class="sxs-lookup"><span data-stu-id="e7994-125">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="e7994-126">在 **"说明**"中，提供有关用户策略 (例如  _centralSiteName_ 的全局策略) 。</span><span class="sxs-lookup"><span data-stu-id="e7994-126">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="e7994-127">若要控制未通过站点策略或用户策略专门控制的所有站点和用户的持久聊天，请选中或清除"启用 **持久聊天"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="e7994-127">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="e7994-128">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="e7994-128">Click **Commit**.</span></span>
    
## <a name="create-a-site-policy"></a><span data-ttu-id="e7994-129">创建站点策略</span><span class="sxs-lookup"><span data-stu-id="e7994-129">Create a site policy</span></span>

<span data-ttu-id="e7994-130">对于已部署的每个站点，可以创建特定于站点的持久聊天策略。</span><span class="sxs-lookup"><span data-stu-id="e7994-130">For each site that you have deployed, you can create a site-specific Persistent Chat policy.</span></span> <span data-ttu-id="e7994-131">站点策略中的配置将覆盖全局策略，但仅适用于站点策略覆盖的指定站点。</span><span class="sxs-lookup"><span data-stu-id="e7994-131">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span> <span data-ttu-id="e7994-132">创建站点策略：</span><span class="sxs-lookup"><span data-stu-id="e7994-132">To create a site policy:</span></span>
  
1. <span data-ttu-id="e7994-133">使用分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e7994-133">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e7994-134">从 **"开始** "菜单中，选择 Skype for Business Server 控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="e7994-134">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="e7994-135">在左侧导航栏中，单击“持久聊天”，然后单击“持久聊天策略”。</span><span class="sxs-lookup"><span data-stu-id="e7994-135">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="e7994-136">单击“新建”，然后单击“站点策略”。</span><span class="sxs-lookup"><span data-stu-id="e7994-136">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="e7994-137">在“选择站点”中，单击要应用此策略的站点。</span><span class="sxs-lookup"><span data-stu-id="e7994-137">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="e7994-138">在“新建持久聊天策略”中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="e7994-138">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="e7994-139">在“名称”中，指定新站点策略的名称（例如，Redmond）。</span><span class="sxs-lookup"><span data-stu-id="e7994-139">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="e7994-140">在“说明”中，提供有关该站点策略内容的详细信息（例如，Redmond 的聊天室策略）。</span><span class="sxs-lookup"><span data-stu-id="e7994-140">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="e7994-141">若要控制未通过站点策略明确控制的所有站点的持久聊天，请选中或清除“启用持久聊天”复选框。</span><span class="sxs-lookup"><span data-stu-id="e7994-141">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="e7994-142">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="e7994-142">Click **Commit**.</span></span>
    
## <a name="create-a-user-policy"></a><span data-ttu-id="e7994-143">创建用户策略</span><span class="sxs-lookup"><span data-stu-id="e7994-143">Create a user policy</span></span>

<span data-ttu-id="e7994-144">可以创建用户特定的策略，以覆盖全局策略和用户所属的任何站点策略。</span><span class="sxs-lookup"><span data-stu-id="e7994-144">You can create user-specific policies that override the global policy and any site policies to which the user belongs.</span></span> <span data-ttu-id="e7994-145">创建用户策略：</span><span class="sxs-lookup"><span data-stu-id="e7994-145">To create a user policy:</span></span>
  
1. <span data-ttu-id="e7994-146">使用分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e7994-146">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e7994-147">从 **"开始** "菜单中，选择 Skype for Business Server 控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="e7994-147">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="e7994-148">在左侧导航栏中，单击“持久聊天”，然后单击“持久聊天策略”。</span><span class="sxs-lookup"><span data-stu-id="e7994-148">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="e7994-149">单击“新建”，然后单击“用户策略”。</span><span class="sxs-lookup"><span data-stu-id="e7994-149">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="e7994-150">在“新建持久聊天策略”中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="e7994-150">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="e7994-151">在“名称”中，指定新用户策略的名称。</span><span class="sxs-lookup"><span data-stu-id="e7994-151">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="e7994-152">在 **"** 说明"中，提供有关用户策略 (例如，特定用户的持久聊天策略) 。</span><span class="sxs-lookup"><span data-stu-id="e7994-152">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="e7994-153">若要控制未通过用户策略明确控制的所有用户的持久聊天，请选中或清除"启用 **持久聊天"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="e7994-153">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="e7994-154">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="e7994-154">Click **Commit**.</span></span>
    
## <a name="apply-a-policy-to-a-user-account"></a><span data-ttu-id="e7994-155">将策略应用于用户帐户</span><span class="sxs-lookup"><span data-stu-id="e7994-155">Apply a policy to a user account</span></span>

<span data-ttu-id="e7994-156">创建策略后，可以将策略应用于用户帐户，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e7994-156">After you create policies, you can apply them to a user account as follows:</span></span>
  
1. <span data-ttu-id="e7994-157">使用分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e7994-157">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e7994-158">从 **"开始** "菜单中，选择 Skype for Business Server 控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="e7994-158">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="e7994-159">在左侧导航栏中，单击“用户”，然后搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e7994-159">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="e7994-160">在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="e7994-160">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="e7994-161">在 **"编辑持久聊天** 策略下的Skype for Business Server 用户"中，选择要应用持久聊天用户策略。</span><span class="sxs-lookup"><span data-stu-id="e7994-161">In **Edit Skype for Business Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e7994-162">设置 **\<Automatic\>** 应用默认的有效策略。</span><span class="sxs-lookup"><span data-stu-id="e7994-162">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="e7994-163">服务器将自动应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="e7994-163">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="e7994-164">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="e7994-164">Click **Commit**.</span></span>
    

