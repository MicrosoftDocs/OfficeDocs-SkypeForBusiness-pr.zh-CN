---
title: 持久聊天策略
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: 可以使用持久聊天组的聊天的永久策略页管理全局，池、 站点或用户级别上，包括配置默认的全局策略，并创建一个或多个其他用户和站点策略对于您的部署策略。 如果持久聊天服务器启用了用户策略，则在其客户端不会出现持续聊天服务器环境。
ms.openlocfilehash: 13f06436f3339da46e32557dff5290d5ad5541fd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-policy"></a><span data-ttu-id="258ba-104">持久聊天策略</span><span class="sxs-lookup"><span data-stu-id="258ba-104">Persistent Chat Policy</span></span>
 
<span data-ttu-id="258ba-105">您可以使用“**持久聊天**”组的“**持久聊天策略**”页来管理全局级、池级、站点级或用户级的策略，包括为部署配置默认全局策略以及创建一个或多个其他用户和站点策略。</span><span class="sxs-lookup"><span data-stu-id="258ba-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="258ba-106">如果持久聊天服务器启用了用户策略，则在其客户端不会出现持续聊天服务器环境。</span><span class="sxs-lookup"><span data-stu-id="258ba-106">If Persistent Chat Server is enabled for a user by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
<span data-ttu-id="258ba-107">在部署时持久的聊天服务器，它可以配置，但不是会被删除，将自动创建全局策略。</span><span class="sxs-lookup"><span data-stu-id="258ba-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="258ba-108">全球政策适用于所有用户，因为它不必将每个用户设置。</span><span class="sxs-lookup"><span data-stu-id="258ba-108">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="258ba-109">您可以创建和配置的全球政策，以及使用户持续聊天服务器的多个站点和用户的策略。</span><span class="sxs-lookup"><span data-stu-id="258ba-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="258ba-110">池和网站持续聊天服务器策略重写全局持久聊天服务器的策略，但只针对该网站的用户。</span><span class="sxs-lookup"><span data-stu-id="258ba-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="258ba-111">用户策略将覆盖分配有用户策略的用户的全局、池和站点策略。</span><span class="sxs-lookup"><span data-stu-id="258ba-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="258ba-112">配置和使用持久的聊天服务器，必须首先使用拓扑生成器添加到拓扑结构中，持续的聊天服务器支持并发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="258ba-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="258ba-113">有关详细信息，请参阅[添加持久聊天服务器到您 Skype 业务服务器 2015年拓扑](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="258ba-113">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="258ba-114">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="258ba-114">Tasks that you can perform</span></span>

<span data-ttu-id="258ba-115">您可以在**持久聊天策略**页上执行以下任务：启用“持久聊天服务器”策略；管理“持久聊天服务器”策略。</span><span class="sxs-lookup"><span data-stu-id="258ba-115">You can perform the following tasks on the **Persistent Chat Policy** page: enable Persistent Chat Server policy; manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="258ba-116">要配置全局策略持续聊天</span><span class="sxs-lookup"><span data-stu-id="258ba-116">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="258ba-117">从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="258ba-117">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="258ba-118">从**开始**菜单中，选择 Skype 业务服务器的控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="258ba-118">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="258ba-119">在业务服务器控件面板的 Skype，**持久聊天**，请单击，然后单击**聊天的永久策略**。</span><span class="sxs-lookup"><span data-stu-id="258ba-119">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="258ba-120">单击策略列表中的“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="258ba-120">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="258ba-121">在“**编辑持久聊天策略 - 全局**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="258ba-121">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
  - <span data-ttu-id="258ba-122">在“**名称**”中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。</span><span class="sxs-lookup"><span data-stu-id="258ba-122">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
  - <span data-ttu-id="258ba-123">在**说明**提供了有关用户策略 （例如， _centralSiteName_的全局策略） 的信息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="258ba-123">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
  - <span data-ttu-id="258ba-124">若要控制所有站点和用户通过网站策略或用户策略未专门控制的持久聊天，选中或清除**启用持久聊天**复选框。</span><span class="sxs-lookup"><span data-stu-id="258ba-124">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="258ba-125">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="258ba-125">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="258ba-126">若要创建持久聊天网站的策略</span><span class="sxs-lookup"><span data-stu-id="258ba-126">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="258ba-127">对于每个已部署的站点，您可以创建特定于站点的持久对话策略。</span><span class="sxs-lookup"><span data-stu-id="258ba-127">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="258ba-128">站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。</span><span class="sxs-lookup"><span data-stu-id="258ba-128">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="258ba-129">从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="258ba-129">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="258ba-130">从**开始**菜单中，选择 Skype 业务服务器的控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="258ba-130">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="258ba-131">在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天策略**”。</span><span class="sxs-lookup"><span data-stu-id="258ba-131">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="258ba-132">单击“**新建**”，然后单击“**站点策略**”。</span><span class="sxs-lookup"><span data-stu-id="258ba-132">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="258ba-133">在“**选择站点**”中，单击要应用此策略的站点。</span><span class="sxs-lookup"><span data-stu-id="258ba-133">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="258ba-134">在“**新建持久聊天策略**”中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="258ba-134">In **New Persistent Chat Policy**, do the following:</span></span>
    
  - <span data-ttu-id="258ba-135">在“**名称**”中，指定新站点策略的名称（例如，Redmond）。</span><span class="sxs-lookup"><span data-stu-id="258ba-135">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
  - <span data-ttu-id="258ba-136">在“**说明**”中，提供有关该站点策略内容的详细信息（例如，Redmond 的聊天室策略）。</span><span class="sxs-lookup"><span data-stu-id="258ba-136">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
  - <span data-ttu-id="258ba-137">若要控制未通过站点策略明确控制的所有站点的持久聊天，请选中或清除“**启用持久聊天**”复选框。</span><span class="sxs-lookup"><span data-stu-id="258ba-137">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="258ba-138">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="258ba-138">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="258ba-139">若要创建一个用户策略持续聊天</span><span class="sxs-lookup"><span data-stu-id="258ba-139">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="258ba-140">在 Skype 业务服务器控件面板中，您定义可以分配给**用户**的用户的用户策略。</span><span class="sxs-lookup"><span data-stu-id="258ba-140">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="258ba-141">用户策略将覆盖全局策略和站点策略，但是仅限于为其分配了该用户策略的特定用户。</span><span class="sxs-lookup"><span data-stu-id="258ba-141">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="258ba-142">从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="258ba-142">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="258ba-143">从**开始**菜单中，选择 Skype 业务服务器的控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="258ba-143">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="258ba-144">在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天策略**”。</span><span class="sxs-lookup"><span data-stu-id="258ba-144">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="258ba-145">单击“**新建**”，然后单击“**用户策略**”。</span><span class="sxs-lookup"><span data-stu-id="258ba-145">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="258ba-146">在“**新建持久聊天策略**”中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="258ba-146">In **New Persistent Chat Policy**, do the following:</span></span>
    
  - <span data-ttu-id="258ba-147">在“**名称**”中，指定新用户策略的名称。</span><span class="sxs-lookup"><span data-stu-id="258ba-147">In **Name**, specify a name for the new user policy.</span></span>
    
  - <span data-ttu-id="258ba-148">在**说明**提供了有关用户策略 （例如，持久性聊天针对特定用户的策略） 的信息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="258ba-148">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
  - <span data-ttu-id="258ba-149">若要控制所有用户通过用户策略不专门控制的持久聊天，选中或清除**启用持久聊天**复选框。</span><span class="sxs-lookup"><span data-stu-id="258ba-149">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="258ba-150">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="258ba-150">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="258ba-151">持久的聊天用户策略应用到用户帐户</span><span class="sxs-lookup"><span data-stu-id="258ba-151">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="258ba-152">如果用户已启用的 Skype 业务服务器，您可以对特定用户启用或禁用它们持久聊天服务器应用适当的政策。</span><span class="sxs-lookup"><span data-stu-id="258ba-152">If a user has been enabled for Skype for Business Server, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="258ba-153">使用本主题中的过程将以前创建的持久性聊天用户策略应用于一个或多个用户帐户或用户组。</span><span class="sxs-lookup"><span data-stu-id="258ba-153">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="258ba-154">从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="258ba-154">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="258ba-155">从**开始**菜单中，选择 Skype 业务服务器的控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="258ba-155">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="258ba-156">在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="258ba-156">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="258ba-157">在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="258ba-157">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="258ba-158">在**编辑 Lync 服务器用户****持续聊天的策略**下，选择您要应用的持久聊天用户策略。</span><span class="sxs-lookup"><span data-stu-id="258ba-158">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="258ba-159">**\<自动\>**应用默认的有效策略设置。</span><span class="sxs-lookup"><span data-stu-id="258ba-159">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="258ba-160">服务器将自动应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="258ba-160">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="258ba-161">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="258ba-161">Click **Commit**.</span></span>
    

