---
title: 持久聊天策略主页
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0dc18d5c-82d6-4d39-afb1-efdb3ae6d2c7
description: 您可以使用持久聊天组的"持久聊天策略"页在全局、池、站点或用户级别管理策略，包括配置默认全局策略和为部署创建一个或多个其他用户和站点策略。 如果策略为用户启用了持久聊天服务器，则持久聊天服务器环境将显示在其客户端中。
ms.openlocfilehash: 9664cbf182fe388fbffd2b270e306a4c17b36e95
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819302"
---
# <a name="persistent-chat-policy-main-page"></a><span data-ttu-id="b8f9b-104">持久聊天策略主页</span><span class="sxs-lookup"><span data-stu-id="b8f9b-104">Persistent Chat Policy Main Page</span></span>
 
<span data-ttu-id="b8f9b-105">您可以使用持久聊天组的"持久聊天策略"页在全局、池、站点或用户级别管理策略，包括配置默认全局策略和为部署创建一个或多个其他用户和站点策略。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-105">You can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="b8f9b-106">如果策略为用户启用了持久聊天服务器，则持久聊天服务器环境将显示在其客户端中。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-106">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their client.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b8f9b-107">在拓扑中，持久聊天服务器站点策略全局、每用户池、每用户站点或每用户应用。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-107">In the topology, Persistent Chat Server site policies apply globally, per user's pool, or per user's site, or per user.</span></span> 
  
<span data-ttu-id="b8f9b-108">部署持久聊天服务器时会自动创建全局策略，可以配置全局策略，但不能将其删除。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-108">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="b8f9b-109">由于全局策略适用于所有用户，因此不必按用户进行设置。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-109">Because the global policy applies to all users, it doesn't have to be set per user.</span></span>
  
<span data-ttu-id="b8f9b-110">可以创建和配置多个站点和用户策略，这些策略与全局策略一起为用户启用持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-110">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="b8f9b-111">池和站点持久聊天服务器策略会覆盖全局持久聊天服务器策略，但仅适用于该网站的用户。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-111">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="b8f9b-112">用户策略将覆盖分配有用户策略的用户的全局、池和网站策略。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-112">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b8f9b-113">若要配置和使用持久聊天服务器，必须先使用拓扑生成器向拓扑中添加持久聊天服务器支持，然后发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-113">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="b8f9b-114">有关详细信息，请参阅 [将持久聊天服务器添加到 Skype for Business Server 2015 拓扑](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-114">For details, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md).</span></span> 
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="b8f9b-115">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="b8f9b-115">Tasks that you can perform</span></span>

<span data-ttu-id="b8f9b-116">您可以在"持久聊天策略"页上执行 **以下任务：** 启用和管理持久聊天服务器策略。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-116">You can perform the following tasks on the **Persistent Chat Policy** page: enable and manage Persistent Chat Server policy.</span></span>
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="b8f9b-117">配置持久聊天的全局策略</span><span class="sxs-lookup"><span data-stu-id="b8f9b-117">To configure the Global Policy for Persistent Chat</span></span>

1. <span data-ttu-id="b8f9b-118">使用分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-118">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b8f9b-119">从 **"开始** "菜单中，选择 Skype for Business Server 控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-119">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="b8f9b-120">在 Skype for Business Server 控制面板中，单击 **"持久聊天**"，然后单击"**持久聊天策略"。**</span><span class="sxs-lookup"><span data-stu-id="b8f9b-120">In Skype for Business Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="b8f9b-121">单击策略列表中的“全局”，再单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-121">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="b8f9b-122">在“编辑持久聊天策略 - 全局”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b8f9b-122">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="b8f9b-123">在“名称”中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-123">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
   - <span data-ttu-id="b8f9b-124">在 **"说明**"中，提供有关用户策略 (例如  _centralSiteName_ 的全局策略) 。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-124">In **Description**, provide details about what the user policy is (for example, Global policy for  _centralSiteName_).</span></span>
    
   - <span data-ttu-id="b8f9b-125">若要控制未通过站点策略或用户策略专门控制的所有站点和用户的持久聊天，请选中或清除"启用 **持久聊天"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-125">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="b8f9b-126">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-126">Click **Commit**.</span></span>
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="b8f9b-127">为站点创建持久聊天策略</span><span class="sxs-lookup"><span data-stu-id="b8f9b-127">To create a Persistent Chat policy for a site</span></span>

<span data-ttu-id="b8f9b-128">对于已部署的每个站点，可以创建特定于站点的持久聊天策略。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-128">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>
  
<span data-ttu-id="b8f9b-129">站点策略中的配置将覆盖全局策略，但仅适用于站点策略覆盖的指定站点。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-129">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>
  
1. <span data-ttu-id="b8f9b-130">使用分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-130">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b8f9b-131">从 **"开始** "菜单中，选择 Skype for Business Server 控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="b8f9b-132">在左侧导航栏中，单击“持久聊天”，然后单击“持久聊天策略”。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-132">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="b8f9b-133">单击“新建”，然后单击“站点策略”。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-133">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="b8f9b-134">在“选择站点”中，单击要应用此策略的站点。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-134">In **Select a Site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="b8f9b-135">在“新建持久聊天策略”中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b8f9b-135">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="b8f9b-136">在“名称”中，指定新站点策略的名称（例如，Redmond）。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-136">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
   - <span data-ttu-id="b8f9b-137">在“说明”中，提供有关该站点策略内容的详细信息（例如，Redmond 的聊天室策略）。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-137">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
   - <span data-ttu-id="b8f9b-138">若要控制未通过站点策略明确控制的所有站点的持久聊天，请选中或清除“启用持久聊天”复选框。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-138">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
7. <span data-ttu-id="b8f9b-139">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-139">Click **Commit**.</span></span>
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="b8f9b-140">为持久聊天创建用户策略</span><span class="sxs-lookup"><span data-stu-id="b8f9b-140">To create a user policy for Persistent Chat</span></span>

<span data-ttu-id="b8f9b-141">在 Skype for Business Server 控制面板中，定义可以分配给用户中的用户 **的用户策略**。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-141">In the Skype for Business Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>
  
<span data-ttu-id="b8f9b-142">用户策略将覆盖全局策略和站点策略，但仅适用于分配了该用户策略的特定用户。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-142">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>
  
1. <span data-ttu-id="b8f9b-143">使用分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-143">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b8f9b-144">从 **"开始** "菜单中，选择 Skype for Business Server 控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-144">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="b8f9b-145">在左侧导航栏中，单击“持久聊天”，然后单击“持久聊天策略”。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-145">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
4. <span data-ttu-id="b8f9b-146">单击“新建”，然后单击“用户策略”。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-146">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="b8f9b-147">在“新建持久聊天策略”中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b8f9b-147">In **New Persistent Chat Policy**, do the following:</span></span>
    
   - <span data-ttu-id="b8f9b-148">在“名称”中，指定新用户策略的名称。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-148">In **Name**, specify a name for the new user policy.</span></span>
    
   - <span data-ttu-id="b8f9b-149">在 **"** 说明"中，提供有关用户策略 (例如，特定用户的持久聊天策略) 。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-149">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
   - <span data-ttu-id="b8f9b-150">若要控制未通过用户策略明确控制的所有用户的持久聊天，请选中或清除"启用 **持久聊天"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-150">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>
    
6. <span data-ttu-id="b8f9b-151">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-151">Click **Commit**.</span></span>
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="b8f9b-152">将持久聊天用户策略应用于用户帐户</span><span class="sxs-lookup"><span data-stu-id="b8f9b-152">To apply a Persistent Chat user policy to a user account</span></span>

<span data-ttu-id="b8f9b-153">如果用户已启用 Skype for Business，可以将相应的策略应用于特定用户，以对持久聊天服务器启用或禁用这些策略。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-153">If a user has been enabled for Skype for Business, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>
  
<span data-ttu-id="b8f9b-154">使用本主题中的过程将以前创建的持久聊天用户策略应用于一个或多个用户帐户或用户组。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-154">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>
  
1. <span data-ttu-id="b8f9b-155">使用分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-155">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b8f9b-156">从 **"开始** "菜单中，选择 Skype for Business Server 控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-156">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="b8f9b-157">在左侧导航栏中，单击“用户”，然后搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-157">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="b8f9b-158">在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-158">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="b8f9b-159">在 **"编辑持久聊天\*\*\*\*策略下的** Lync Server 用户"中，选择要应用持久聊天用户策略。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-159">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b8f9b-160">设置 **\<Automatic\>** 应用默认的有效策略。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-160">The **\<Automatic\>** settings apply the default effective policy.</span></span> <span data-ttu-id="b8f9b-161">服务器将自动应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-161">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="b8f9b-162">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="b8f9b-162">Click **Commit**.</span></span>
    

