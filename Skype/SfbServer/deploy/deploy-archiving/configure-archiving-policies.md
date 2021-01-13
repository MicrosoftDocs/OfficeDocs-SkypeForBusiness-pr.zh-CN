---
title: 为 Skype for Business Server 配置存档策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 摘要：阅读本主题，了解如何为 Skype for Business Server 用户配置初始存档策略。
ms.openlocfilehash: ab737305561aa20c873bbce6e0f075d17fedd0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820852"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a><span data-ttu-id="d375e-103">为 Skype for Business Server 配置存档策略</span><span class="sxs-lookup"><span data-stu-id="d375e-103">Configure archiving policies for Skype for Business Server</span></span>
 
<span data-ttu-id="d375e-104">**摘要：** 阅读本主题，了解如何为 Skype for Business Server 用户配置初始存档策略。</span><span class="sxs-lookup"><span data-stu-id="d375e-104">**Summary:** Read this topic to learn how to configure initial archiving policies for Skype for Business Server users.</span></span>
  
<span data-ttu-id="d375e-105">在 Skype for Business Server 中，使用策略为位于 Skype for Business Server 上的用户启用和禁用内部通信和外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="d375e-105">In Skype for Business Server, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="d375e-106">其中包括：</span><span class="sxs-lookup"><span data-stu-id="d375e-106">This includes the following:</span></span>
  
- <span data-ttu-id="d375e-107">在部署 Skype for Business Server 时默认创建的全局策略</span><span class="sxs-lookup"><span data-stu-id="d375e-107">A global policy that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="d375e-108">指定如何为特定站点实施存档的可选站点级别策略</span><span class="sxs-lookup"><span data-stu-id="d375e-108">Optional site-level policies that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="d375e-109">指定如何为特定用户实施存档的可选用户级别策略</span><span class="sxs-lookup"><span data-stu-id="d375e-109">Optional user-level policies that specify how archiving is implemented for specific users</span></span>
    
<span data-ttu-id="d375e-110">您最初在部署存档时设置存档策略，但您可以在部署后更改、添加和删除策略。</span><span class="sxs-lookup"><span data-stu-id="d375e-110">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="d375e-111">在 Skype for Business Server 控制面板中，可以使用存档和监控组的"存档策略"页在全局、站点和用户级别管理策略。</span><span class="sxs-lookup"><span data-stu-id="d375e-111">In Skype for Business Server Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global, site, and user levels.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d375e-112">若要控制存档的实现，必须指定选项，例如是否存档 IM 或会议、关键模式的使用和清除选项。</span><span class="sxs-lookup"><span data-stu-id="d375e-112">To control the implementation of archiving, you must specify options, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="d375e-113">默认情况下，全局存档配置或任何站点或池存档配置中都未启用任何选项。</span><span class="sxs-lookup"><span data-stu-id="d375e-113">By default no options are enabled in the global archiving configuration or any site or pool archiving configuration.</span></span> <span data-ttu-id="d375e-114">在启用内部或外部通信的存档之前，应指定所有适当的选项。</span><span class="sxs-lookup"><span data-stu-id="d375e-114">You should specify all appropriate options before enabling archiving for internal or external communications.</span></span> <span data-ttu-id="d375e-115">有关详细信息，请参阅 [配置 Skype for Business Server 的存档选项](configure-archiving-options.md)。</span><span class="sxs-lookup"><span data-stu-id="d375e-115">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d375e-116">如果为部署启用 Microsoft Exchange 集成，Exchange In-Place 保留策略将控制是否对位于 Exchange 上且其邮箱置于"保留"状态的用户In-Place存档。</span><span class="sxs-lookup"><span data-stu-id="d375e-116">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> 
  
<span data-ttu-id="d375e-117">有关存档策略如何工作的详细信息，包括全局、站点和用户策略的层次结构，请参阅[Plan for archiving in Skype for Business Server。](../../plan-your-deployment/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="d375e-117">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="d375e-118">有关部署后如何管理策略的详细信息，请参阅"在 Skype for Business Server 中管理[存档策略"。](../../manage/archiving/policies.md)</span><span class="sxs-lookup"><span data-stu-id="d375e-118">For details about how to manage policies after deployment, see [Manage archiving policies in Skype for Business Server](../../manage/archiving/policies.md).</span></span>
  
## <a name="global-policy"></a><span data-ttu-id="d375e-119">全局策略</span><span class="sxs-lookup"><span data-stu-id="d375e-119">Global policy</span></span>

<span data-ttu-id="d375e-120">部署前端服务器时，Skype for Business Server 会创建用于存档的全局策略。</span><span class="sxs-lookup"><span data-stu-id="d375e-120">When you deploy your Front End Servers, Skype for Business Server creates a global policy for archiving.</span></span> <span data-ttu-id="d375e-121">默认情况下，全局策略中禁用存档。</span><span class="sxs-lookup"><span data-stu-id="d375e-121">By default, archiving is disabled in the global policy.</span></span> <span data-ttu-id="d375e-122">全局策略控制是否针对整个部署的内部和外部通信启用存档，除非您设置了站点或用户策略（这将覆盖全局策略）或为部分或所有用户使用 Microsoft Exchange 集成。</span><span class="sxs-lookup"><span data-stu-id="d375e-122">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="d375e-123">如果使用 Microsoft Exchange 集成，则全局策略不适用于位于 Exchange 上且将邮箱置于保留状态In-Place用户。</span><span class="sxs-lookup"><span data-stu-id="d375e-123">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange and have the mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a><span data-ttu-id="d375e-124">为 Skype for Business Server 存档数据库配置存档的全局策略</span><span class="sxs-lookup"><span data-stu-id="d375e-124">Configure the global policy for archiving for Skype for Business Server archiving databases</span></span>

1. <span data-ttu-id="d375e-125">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d375e-125">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d375e-126">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="d375e-126">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d375e-127">在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档策略”**。</span><span class="sxs-lookup"><span data-stu-id="d375e-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="d375e-128">在“存档策略”页上，单击“全局”，再单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="d375e-128">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d375e-129">在“编辑存档策略 - 全局”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="d375e-129">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="d375e-130">在“名称”中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。</span><span class="sxs-lookup"><span data-stu-id="d375e-130">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span> 
    
   - <span data-ttu-id="d375e-131">在 **"说明**"中，提供有关策略 (例如  *，divisionName*  的全局策略。</span><span class="sxs-lookup"><span data-stu-id="d375e-131">In **Description**, provide information about what the policy is (for example, Global policy for  *divisionName*  .</span></span>
    
   - <span data-ttu-id="d375e-132">要控制未通过特定站点策略或用户策略控制的所有站点和用户的内部通信存档，请选中或清除“存档内部通信”复选框。</span><span class="sxs-lookup"><span data-stu-id="d375e-132">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="d375e-133">要控制未通过特定站点策略或用户策略控制的所有站点和用户的外部通信存档，请选中或清除“存档外部通信”复选框。</span><span class="sxs-lookup"><span data-stu-id="d375e-133">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="d375e-134">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="d375e-134">Click **Commit**.</span></span>
    
## <a name="site-policies"></a><span data-ttu-id="d375e-135">网站策略</span><span class="sxs-lookup"><span data-stu-id="d375e-135">Site policies</span></span>

<span data-ttu-id="d375e-136">您可以通过为特定站点创建存档策略来为这些站点启用或禁用存档。</span><span class="sxs-lookup"><span data-stu-id="d375e-136">You can enable or disable archiving for specific sites by creating an archiving policy for each of those sites.</span></span> <span data-ttu-id="d375e-137">站点策略会覆盖全局策略，但用户策略会覆盖站点策略。</span><span class="sxs-lookup"><span data-stu-id="d375e-137">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="d375e-138">存档策略仅适用于不使用 Microsoft Exchange 集成，或者如果您使用 Microsoft Exchange 集成，但有些用户未在 Exchange 上存储，并且其邮箱被置于In-Place保留状态。</span><span class="sxs-lookup"><span data-stu-id="d375e-138">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="create-an-archiving-policy-for-a-site"></a><span data-ttu-id="d375e-139">为站点创建存档策略</span><span class="sxs-lookup"><span data-stu-id="d375e-139">Create an archiving policy for a site</span></span>

1. <span data-ttu-id="d375e-140">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d375e-140">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d375e-141">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="d375e-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="d375e-142">在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档策略”**。</span><span class="sxs-lookup"><span data-stu-id="d375e-142">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="d375e-143">有关存档策略如何工作的详细信息，包括全局、站点和用户策略的层次结构，请参阅[Plan for archiving in Skype for Business Server。](../../plan-your-deployment/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="d375e-143">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
    
4. <span data-ttu-id="d375e-144">单击“新建”，然后单击“站点策略”。</span><span class="sxs-lookup"><span data-stu-id="d375e-144">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="d375e-145">在 **"选择站点**"中，单击要应用策略的站点。</span><span class="sxs-lookup"><span data-stu-id="d375e-145">In **Select a site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="d375e-146">在 **“新建存档策略”** 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="d375e-146">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="d375e-147">在 **"名称**"中，指定站点策略的名称。</span><span class="sxs-lookup"><span data-stu-id="d375e-147">In **Name**, specify the name for the site policy.</span></span> 
    
   - <span data-ttu-id="d375e-148">在 **"说明**"中，提供有关站点策略 (例如，Redmond) 。</span><span class="sxs-lookup"><span data-stu-id="d375e-148">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
   - <span data-ttu-id="d375e-149">若要控制指定站点的内部通信存档，请选中或清除"存档 **内部通信"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="d375e-149">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="d375e-150">若要控制指定站点的外部通信的存档，请选中或清除"存档 **外部通信"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="d375e-150">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>
    
7. <span data-ttu-id="d375e-151">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="d375e-151">Click **Commit**.</span></span>
    
## <a name="user-policies"></a><span data-ttu-id="d375e-152">用户策略</span><span class="sxs-lookup"><span data-stu-id="d375e-152">User policies</span></span>

<span data-ttu-id="d375e-153">您可以通过为用户创建和配置存档策略，然后将该策略应用于特定用户或用户组来为特定用户启用或禁用存档。</span><span class="sxs-lookup"><span data-stu-id="d375e-153">You can enable or disable archiving for specific users by creating and configuring an archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="d375e-154">用户策略会覆盖任何全局策略或站点策略。</span><span class="sxs-lookup"><span data-stu-id="d375e-154">User policies override any global policy or site policies.</span></span> <span data-ttu-id="d375e-155">存档策略仅适用于不使用 Microsoft Exchange 集成，或者如果您使用 Microsoft Exchange 集成，但有些用户未在 Exchange 上存储，并且其邮箱被置于In-Place保留状态。</span><span class="sxs-lookup"><span data-stu-id="d375e-155">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a><span data-ttu-id="d375e-156">为 Skype for Business Server 上用户配置存档策略</span><span class="sxs-lookup"><span data-stu-id="d375e-156">Configure an archiving policy for users homed on Skype for Business Server</span></span>

1. <span data-ttu-id="d375e-157">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d375e-157">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d375e-158">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="d375e-158">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d375e-159">在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档策略”**。</span><span class="sxs-lookup"><span data-stu-id="d375e-159">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="d375e-160">单击 **“新建”**，然后单击 **“用户策略”**。</span><span class="sxs-lookup"><span data-stu-id="d375e-160">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="d375e-161">在“新建存档策略”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="d375e-161">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="d375e-162">在“名称”中，指定用户策略的名称。</span><span class="sxs-lookup"><span data-stu-id="d375e-162">In **Name**, specify the name for the user policy.</span></span> 
    
   - <span data-ttu-id="d375e-163">在“说明”中，提供有关该用户策略内容的信息（例如，法律部门的用户策略）。</span><span class="sxs-lookup"><span data-stu-id="d375e-163">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
   - <span data-ttu-id="d375e-164">若要控制用户策略的内部通信存档，请选中或清除“存档内部通信”复选框。</span><span class="sxs-lookup"><span data-stu-id="d375e-164">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="d375e-165">若要控制用户策略的外部通信存档，请选中或清除“存档外部通信”复选框。</span><span class="sxs-lookup"><span data-stu-id="d375e-165">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="d375e-166">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="d375e-166">Click **Commit**.</span></span>
    
<span data-ttu-id="d375e-167">用户策略仅适用于为其分配策略的用户。</span><span class="sxs-lookup"><span data-stu-id="d375e-167">A user policy applies only to users to whom you assign the policy.</span></span>
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a><span data-ttu-id="d375e-168">将 Skype for Business Server 存档策略应用于用户</span><span class="sxs-lookup"><span data-stu-id="d375e-168">Apply a Skype for Business Server archiving policy to a user</span></span>

1. <span data-ttu-id="d375e-169">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d375e-169">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d375e-170">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="d375e-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d375e-171">在左侧导航栏中，单击“用户”，然后搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d375e-171">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="d375e-172">在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="d375e-172">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d375e-173">在 **"编辑 Skype for Business Server 用户** 存档 **策略"** 下，选择要应用存档用户策略。</span><span class="sxs-lookup"><span data-stu-id="d375e-173">In **Edit Skype for Business Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d375e-174">这些设置 **\<Automatic\>** 将应用默认服务器安装设置。</span><span class="sxs-lookup"><span data-stu-id="d375e-174">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="d375e-175">服务器将自动应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="d375e-175">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="d375e-176">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="d375e-176">Click **Commit**.</span></span>
    

