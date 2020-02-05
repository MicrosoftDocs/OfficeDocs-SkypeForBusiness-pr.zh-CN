---
title: 配置 Skype for Business 服务器的存档策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 摘要：阅读本主题，了解如何为 Skype for business Server 用户配置初始存档策略。
ms.openlocfilehash: ff946fe2fde2fcd8aae842e809a89bffb7852bca
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769205"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a><span data-ttu-id="e2584-103">配置 Skype for Business 服务器的存档策略</span><span class="sxs-lookup"><span data-stu-id="e2584-103">Configure archiving policies for Skype for Business Server</span></span>
 
<span data-ttu-id="e2584-104">**摘要：** 阅读本主题，了解如何为 Skype for Business Server 用户配置初始存档策略。</span><span class="sxs-lookup"><span data-stu-id="e2584-104">**Summary:** Read this topic to learn how to configure initial archiving policies for Skype for Business Server users.</span></span>
  
<span data-ttu-id="e2584-105">在 Skype for Business Server 中，你可以使用策略为托管在 Skype for business 服务器上的用户启用和禁用内部通信和外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="e2584-105">In Skype for Business Server, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="e2584-106">这包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="e2584-106">This includes the following:</span></span>
  
- <span data-ttu-id="e2584-107">部署 Skype for Business 服务器时默认创建的全局策略</span><span class="sxs-lookup"><span data-stu-id="e2584-107">A global policy that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="e2584-108">指定如何为特定站点实施存档的可选站点级别策略</span><span class="sxs-lookup"><span data-stu-id="e2584-108">Optional site-level policies that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="e2584-109">指定如何为特定用户实施存档的可选用户级策略</span><span class="sxs-lookup"><span data-stu-id="e2584-109">Optional user-level policies that specify how archiving is implemented for specific users</span></span>
    
<span data-ttu-id="e2584-110">您最初在部署存档时设置存档策略，但您可以在部署后更改、添加和删除策略。</span><span class="sxs-lookup"><span data-stu-id="e2584-110">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="e2584-111">在 "Skype for Business 服务器控制面板" 中，可以使用 "**存档和监视**" 组的 "**存档策略**" 页面管理全局、网站和用户级别的策略。</span><span class="sxs-lookup"><span data-stu-id="e2584-111">In Skype for Business Server Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global, site, and user levels.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e2584-112">为了控制存档的实施，您必须指定选项，如是否存档 IM 或会议、关键模式的使用，以及清除选项。</span><span class="sxs-lookup"><span data-stu-id="e2584-112">To control the implementation of archiving, you must specify options, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="e2584-113">默认情况下，在全局存档配置或任何站点或池存档配置中不会启用任何选项。</span><span class="sxs-lookup"><span data-stu-id="e2584-113">By default no options are enabled in the global archiving configuration or any site or pool archiving configuration.</span></span> <span data-ttu-id="e2584-114">您应先指定所有适当的选项，然后再针对内部或外部通信启用存档。</span><span class="sxs-lookup"><span data-stu-id="e2584-114">You should specify all appropriate options before enabling archiving for internal or external communications.</span></span> <span data-ttu-id="e2584-115">有关详细信息，请参阅[配置 Skype for Business 服务器的存档选项](configure-archiving-options.md)。</span><span class="sxs-lookup"><span data-stu-id="e2584-115">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e2584-116">如果为你的部署启用 Microsoft Exchange 集成，则 Exchange 就地保留策略控制是否为托管于 Exchange 的用户启用存档，并将其邮箱置于原地保留。</span><span class="sxs-lookup"><span data-stu-id="e2584-116">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> 
  
<span data-ttu-id="e2584-117">有关存档策略的工作原理的详细信息，包括全局、网站和用户策略的层次结构，请参阅[Skype For Business 服务器中的存档计划](../../plan-your-deployment/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="e2584-117">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="e2584-118">有关如何在部署后管理策略的详细信息，请参阅[管理 Skype For Business 服务器中的存档策略](../../manage/archiving/policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e2584-118">For details about how to manage policies after deployment, see [Manage archiving policies in Skype for Business Server](../../manage/archiving/policies.md).</span></span>
  
## <a name="global-policy"></a><span data-ttu-id="e2584-119">全局策略</span><span class="sxs-lookup"><span data-stu-id="e2584-119">Global policy</span></span>

<span data-ttu-id="e2584-120">当您部署前端服务器时，Skype for Business 服务器将为存档创建全局策略。</span><span class="sxs-lookup"><span data-stu-id="e2584-120">When you deploy your Front End Servers, Skype for Business Server creates a global policy for archiving.</span></span> <span data-ttu-id="e2584-121">默认情况下，将在全局策略中禁用存档。</span><span class="sxs-lookup"><span data-stu-id="e2584-121">By default, archiving is disabled in the global policy.</span></span> <span data-ttu-id="e2584-122">全局策略控制是否为整个部署启用存档以进行内部和外部通信，除非你设置网站或用户策略（这将覆盖全局策略），或者你对部分或全部使用 Microsoft Exchange 集成您的用户。</span><span class="sxs-lookup"><span data-stu-id="e2584-122">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="e2584-123">如果您使用 Microsoft Exchange 集成，则全局策略不会应用于托管在 Exchange 上的任何用户，并将邮箱置于原地保留状态。</span><span class="sxs-lookup"><span data-stu-id="e2584-123">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange and have the mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a><span data-ttu-id="e2584-124">为 Skype for business Server 存档数据库配置全局策略以存档</span><span class="sxs-lookup"><span data-stu-id="e2584-124">Configure the global policy for archiving for Skype for Business Server archiving databases</span></span>

1. <span data-ttu-id="e2584-125">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e2584-125">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e2584-126">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="e2584-126">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e2584-127">在左侧导航栏中，单击“监控和存档”\*\*\*\*，然后单击“存档策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e2584-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="e2584-128">在“**存档策略**”页上，单击“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="e2584-128">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="e2584-129">在“**编辑存档策略 - 全局**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e2584-129">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="e2584-130">在“**名称**”中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。</span><span class="sxs-lookup"><span data-stu-id="e2584-130">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span> 
    
   - <span data-ttu-id="e2584-131">在 "**说明**" 中，提供有关策略的内容（例如， *divisionName*的全局策略）的信息。</span><span class="sxs-lookup"><span data-stu-id="e2584-131">In **Description**, provide information about what the policy is (for example, Global policy for  *divisionName*  .</span></span>
    
   - <span data-ttu-id="e2584-132">要控制未通过特定站点策略或用户策略控制的所有站点和用户的内部通信存档，请选中或清除“**存档内部通信**”复选框。</span><span class="sxs-lookup"><span data-stu-id="e2584-132">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="e2584-133">要控制未通过特定站点策略或用户策略控制的所有站点和用户的外部通信存档，请选中或清除“**存档外部通信**”复选框。</span><span class="sxs-lookup"><span data-stu-id="e2584-133">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="e2584-134">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="e2584-134">Click **Commit**.</span></span>
    
## <a name="site-policies"></a><span data-ttu-id="e2584-135">站点策略</span><span class="sxs-lookup"><span data-stu-id="e2584-135">Site policies</span></span>

<span data-ttu-id="e2584-136">您可通过为特定站点中的每个站点创建存档策略来启用或禁用这些站点的存档。</span><span class="sxs-lookup"><span data-stu-id="e2584-136">You can enable or disable archiving for specific sites by creating an archiving policy for each of those sites.</span></span> <span data-ttu-id="e2584-137">站点策略将覆盖全局策略，但用户策略将覆盖站点策略。</span><span class="sxs-lookup"><span data-stu-id="e2584-137">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="e2584-138">仅当你不使用 Microsoft Exchange 集成时，或者，如果你使用的是 Microsoft Exchange 集成，但某些用户没有托管在 Exchange 上，并且其邮箱放置在原地保留中，则仅适用于存档策略。</span><span class="sxs-lookup"><span data-stu-id="e2584-138">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="create-an-archiving-policy-for-a-site"></a><span data-ttu-id="e2584-139">创建站点的存档策略</span><span class="sxs-lookup"><span data-stu-id="e2584-139">Create an archiving policy for a site</span></span>

1. <span data-ttu-id="e2584-140">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e2584-140">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e2584-141">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="e2584-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="e2584-142">在左侧导航栏中，单击“监控和存档”\*\*\*\*，然后单击“存档策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e2584-142">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="e2584-143">有关存档策略的工作原理的详细信息，包括全局、网站和用户策略的层次结构，请参阅[Skype For Business 服务器中的存档计划](../../plan-your-deployment/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="e2584-143">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
    
4. <span data-ttu-id="e2584-144">单击“**新建**”，然后单击“**站点策略**”。</span><span class="sxs-lookup"><span data-stu-id="e2584-144">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="e2584-145">在“**选择站点**”中，单击要应用此策略的站点。</span><span class="sxs-lookup"><span data-stu-id="e2584-145">In **Select a site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="e2584-146">在“**新建存档策略**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e2584-146">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="e2584-147">在“**名称**”中，指定站点策略的名称。</span><span class="sxs-lookup"><span data-stu-id="e2584-147">In **Name**, specify the name for the site policy.</span></span> 
    
   - <span data-ttu-id="e2584-148">在“**说明**”中，提供有关该站点策略内容的信息（例如，Redmond 的站点策略）。</span><span class="sxs-lookup"><span data-stu-id="e2584-148">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
   - <span data-ttu-id="e2584-149">若要控制指定站点的内部通信存档，请选中或清除“**存档内部通信**”复选框。</span><span class="sxs-lookup"><span data-stu-id="e2584-149">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="e2584-150">若要控制指定站点的外部通信存档，请选中或清除“**存档外部通信**”复选框。</span><span class="sxs-lookup"><span data-stu-id="e2584-150">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>
    
7. <span data-ttu-id="e2584-151">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="e2584-151">Click **Commit**.</span></span>
    
## <a name="user-policies"></a><span data-ttu-id="e2584-152">用户策略</span><span class="sxs-lookup"><span data-stu-id="e2584-152">User policies</span></span>

<span data-ttu-id="e2584-153">通过为用户创建和配置存档策略、然后将该策略应用于特定用户或用户组，可为特定用户启用或禁用存档。</span><span class="sxs-lookup"><span data-stu-id="e2584-153">You can enable or disable archiving for specific users by creating and configuring an archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="e2584-154">用户策略会覆盖任何全局策略或站点策略。</span><span class="sxs-lookup"><span data-stu-id="e2584-154">User policies override any global policy or site policies.</span></span> <span data-ttu-id="e2584-155">仅当你不使用 Microsoft Exchange 集成时，或者，如果你使用的是 Microsoft Exchange 集成，但某些用户没有托管在 Exchange 上，并且其邮箱放置在原地保留中，则仅适用于存档策略。</span><span class="sxs-lookup"><span data-stu-id="e2584-155">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a><span data-ttu-id="e2584-156">为驻留在 Skype for business 服务器上的用户配置存档策略</span><span class="sxs-lookup"><span data-stu-id="e2584-156">Configure an archiving policy for users homed on Skype for Business Server</span></span>

1. <span data-ttu-id="e2584-157">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e2584-157">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e2584-158">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="e2584-158">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e2584-159">在左侧导航栏中，单击“监控和存档”\*\*\*\*，然后单击“存档策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e2584-159">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="e2584-160">单击“**新建**”，然后单击“**用户策略**”。</span><span class="sxs-lookup"><span data-stu-id="e2584-160">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="e2584-161">在“**新建存档策略**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e2584-161">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="e2584-162">在“**名称**”中，指定用户策略的名称。</span><span class="sxs-lookup"><span data-stu-id="e2584-162">In **Name**, specify the name for the user policy.</span></span> 
    
   - <span data-ttu-id="e2584-163">在“**说明**”中，提供有关该用户策略内容的信息（例如，法律部门的用户策略）。</span><span class="sxs-lookup"><span data-stu-id="e2584-163">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
   - <span data-ttu-id="e2584-164">若要控制用户策略的内部通信存档，请选中或清除“**存档内部通信**”复选框。</span><span class="sxs-lookup"><span data-stu-id="e2584-164">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="e2584-165">若要控制用户策略的外部通信存档，请选中或清除“**存档外部通信**”复选框。</span><span class="sxs-lookup"><span data-stu-id="e2584-165">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="e2584-166">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="e2584-166">Click **Commit**.</span></span>
    
<span data-ttu-id="e2584-167">用户策略仅适用于为其分配策略的用户。</span><span class="sxs-lookup"><span data-stu-id="e2584-167">A user policy applies only to users to whom you assign the policy.</span></span>
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a><span data-ttu-id="e2584-168">将 Skype for Business 服务器存档策略应用于用户</span><span class="sxs-lookup"><span data-stu-id="e2584-168">Apply a Skype for Business Server archiving policy to a user</span></span>

1. <span data-ttu-id="e2584-169">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e2584-169">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e2584-170">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="e2584-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e2584-171">在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e2584-171">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="e2584-172">在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="e2584-172">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="e2584-173">在 "编辑**策略**" 下的 "**编辑 Skype for business 服务器" 用户**中，选择要应用的存档用户策略。</span><span class="sxs-lookup"><span data-stu-id="e2584-173">In **Edit Skype for Business Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e2584-174">" \*\* \<自动\> \*\*设置" 应用默认服务器安装设置。</span><span class="sxs-lookup"><span data-stu-id="e2584-174">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="e2584-175">服务器将自动应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="e2584-175">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="e2584-176">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="e2584-176">Click **Commit**.</span></span>
    

