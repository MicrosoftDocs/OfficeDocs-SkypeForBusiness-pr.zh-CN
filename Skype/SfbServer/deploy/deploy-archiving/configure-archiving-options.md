---
title: 配置 Skype 业务服务器的存档的选项
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 摘要： 阅读本主题可了解如何配置初始的 Skype 业务服务器的存档选项。 您最初设置存档配置，当您部署存档，但您可以更改、 添加和删除部署后的配置。
ms.openlocfilehash: 80501c01c4e05e0578685b42f8fb83b7faed6c59
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896293"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a><span data-ttu-id="d125b-104">配置 Skype 业务服务器的存档的选项</span><span class="sxs-lookup"><span data-stu-id="d125b-104">Configure archiving options for Skype for Business Server</span></span>
 
<span data-ttu-id="d125b-105">**摘要：** 阅读本主题可了解如何配置初始的 Skype 业务服务器的存档选项。</span><span class="sxs-lookup"><span data-stu-id="d125b-105">**Summary:** Read this topic to learn how to configure initial archiving options for Skype for Business Server.</span></span> <span data-ttu-id="d125b-106">您最初设置存档配置，当您部署存档，但您可以更改、 添加和删除部署后的配置。</span><span class="sxs-lookup"><span data-stu-id="d125b-106">You initially set up archiving configurations when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span>
  
<span data-ttu-id="d125b-107">若要配置初始存档配置，您使用业务 Server Control Panel 的 Skype 指定以下：</span><span class="sxs-lookup"><span data-stu-id="d125b-107">To configure initial archiving configurations, you use Skype for Business Server Control Panel to specify the following:</span></span>
  
- <span data-ttu-id="d125b-108">为业务 Server 部署 Skype 时默认创建的全局级配置</span><span class="sxs-lookup"><span data-stu-id="d125b-108">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="d125b-109">指定如何为特定站点实施存档的可选站点级别配置</span><span class="sxs-lookup"><span data-stu-id="d125b-109">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="d125b-110">指定如何实现存档的特定池的可选池级配置</span><span class="sxs-lookup"><span data-stu-id="d125b-110">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="d125b-111">您需要为以下内容配置选项：</span><span class="sxs-lookup"><span data-stu-id="d125b-111">You will need to configure options for the following:</span></span>
  
- <span data-ttu-id="d125b-112">启用还是禁用存档</span><span class="sxs-lookup"><span data-stu-id="d125b-112">Whether to enable or disable archiving</span></span>
    
- <span data-ttu-id="d125b-113">是否存档 IM 会话</span><span class="sxs-lookup"><span data-stu-id="d125b-113">Whether to archive IM sessions</span></span>
    
- <span data-ttu-id="d125b-114">是否存档 Web 会议会话</span><span class="sxs-lookup"><span data-stu-id="d125b-114">Whether to archive web conferencing sessions</span></span>
    
- <span data-ttu-id="d125b-115">是否在存档不可用时阻止活动</span><span class="sxs-lookup"><span data-stu-id="d125b-115">Whether to block activity when archiving is not available</span></span>
    
- <span data-ttu-id="d125b-116">是否使用 Exchange 集成</span><span class="sxs-lookup"><span data-stu-id="d125b-116">Whether to use Exchange integration</span></span>
    
- <span data-ttu-id="d125b-117">如何设置数据的清除和导出</span><span class="sxs-lookup"><span data-stu-id="d125b-117">How to set up purging and exporting of data</span></span>
    
> [!NOTE]
> <span data-ttu-id="d125b-118">在启用存档之前，应指定所有适当选项。</span><span class="sxs-lookup"><span data-stu-id="d125b-118">You should specify all appropriate options before enabling archiving.</span></span> 
  
<span data-ttu-id="d125b-119">有关操作的详细信息实现存档配置，包括您可以指定的选项和层次结构的存档配置，请参阅[Plan for Business Server 的 Skype 的存档](../../plan-your-deployment/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="d125b-119">For details about how archiving configurations are implemented, including which options you can specify and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="d125b-120">有关如何管理的详细信息后部署通过使用控制面板，或使用 Windows PowerShell 配置，请参阅[管理 Skype 业务服务器中的存档选项](../../manage/archiving/options.md)。</span><span class="sxs-lookup"><span data-stu-id="d125b-120">For details about how to manage configurations after deployment by using the Control Panel or by using Windows PowerShell, see [Manage archiving options in Skype for Business Server](../../manage/archiving/options.md).</span></span>
  
## <a name="configure-global-level-archiving-options"></a><span data-ttu-id="d125b-121">配置全局级别存档选项</span><span class="sxs-lookup"><span data-stu-id="d125b-121">Configure global level archiving options</span></span>

<span data-ttu-id="d125b-122">当您向拓扑添加存档并发布拓扑时，业务服务器 Skype 创建存档的全局配置。</span><span class="sxs-lookup"><span data-stu-id="d125b-122">When you add archiving to your topology and publish the topology, Skype for Business Server creates a global configuration for archiving.</span></span> <span data-ttu-id="d125b-123">默认情况下，不会在全局配置中启用任何存档选项。</span><span class="sxs-lookup"><span data-stu-id="d125b-123">By default, no archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="d125b-124">除非您自己设置站点或池配置（这将重写全局配置），否则全局配置将控制要为整个部署启用的选项。</span><span class="sxs-lookup"><span data-stu-id="d125b-124">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>
  
<span data-ttu-id="d125b-125">在全局级别配置存档选项：</span><span class="sxs-lookup"><span data-stu-id="d125b-125">To configure archiving options at the global level:</span></span>
  
1. <span data-ttu-id="d125b-126">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d125b-126">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d125b-127">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="d125b-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d125b-128">在左侧导航栏中，单击“监控和存档”\*\*\*\*，然后单击“存档配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d125b-128">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="d125b-129">在“**存档配置**”页上，单击“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="d125b-129">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="d125b-130">在“**编辑存档设置 - 全局**”的“**存档设置**”下拉列表中，选择下列存档选项之一：</span><span class="sxs-lookup"><span data-stu-id="d125b-130">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="d125b-131">**禁用存档**</span><span class="sxs-lookup"><span data-stu-id="d125b-131">**Disable archiving**</span></span>
    
   - <span data-ttu-id="d125b-132">**存档 IM 会话**</span><span class="sxs-lookup"><span data-stu-id="d125b-132">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="d125b-133">**存档 IM 和 Web 会议会话**</span><span class="sxs-lookup"><span data-stu-id="d125b-133">**Archive IM and web conferencing sessions**</span></span>
    
6. <span data-ttu-id="d125b-134">此外在**编辑存档设置-全局**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d125b-134">Also on the **Edit Archiving Setting - Global** page, do the following:</span></span>
    
   - <span data-ttu-id="d125b-135">要在存档不可用时阻止活动，请选中“**存档失败时阻止即时消息 (IM) 或 Web 会议会话**”复选框。</span><span class="sxs-lookup"><span data-stu-id="d125b-135">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="d125b-136">若要使用 Microsoft Exchange Server 存储存档数据，请单击**Microsoft Exchange 集成**复选框。</span><span class="sxs-lookup"><span data-stu-id="d125b-136">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="d125b-137">若要启用数据清除，请选中“**启用存档数据清除**”复选框，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="d125b-137">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="d125b-138">要指定在特定的天数之后清除，请单击“**在最长期限（天）后清除导出的存档数据和存储的存档数据**”，然后指定天数。</span><span class="sxs-lookup"><span data-stu-id="d125b-138">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="d125b-139">要限制仅清除已导出的存档数据，请单击“**仅清除导出的存档数据**”。</span><span class="sxs-lookup"><span data-stu-id="d125b-139">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="d125b-140">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="d125b-140">Click **Commit**.</span></span>
    
## <a name="configure-site-level-archiving-options"></a><span data-ttu-id="d125b-141">配置站点级别存档选项</span><span class="sxs-lookup"><span data-stu-id="d125b-141">Configure site level archiving options</span></span>

<span data-ttu-id="d125b-142">您可以为特定站点指定存档选项。</span><span class="sxs-lookup"><span data-stu-id="d125b-142">You can specify archiving options for a specific site.</span></span> <span data-ttu-id="d125b-143">站点配置可覆盖全局配置，但它仅适用于站点配置中指定的站点。</span><span class="sxs-lookup"><span data-stu-id="d125b-143">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> 
  
1. <span data-ttu-id="d125b-144">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d125b-144">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d125b-145">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="d125b-145">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d125b-146">在左侧导航栏中，单击“监控和存档”\*\*\*\*，然后单击“存档配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d125b-146">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="d125b-147">在“**存档配置**”页上，单击“**新建**”，然后单击“**站点配置**”。</span><span class="sxs-lookup"><span data-stu-id="d125b-147">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>
    
5. <span data-ttu-id="d125b-148">在“**选择站点**”中，选择要为存档配置的站点。</span><span class="sxs-lookup"><span data-stu-id="d125b-148">In **Select a Site**, select the site to be configured for archiving.</span></span>
    
6. <span data-ttu-id="d125b-149">在“**新建存档设置**”的“**存档设置**”下拉列表框中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="d125b-149">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="d125b-150">若要只为即时消息 (IM) 会话启用存档，请单击“**存档 IM 会话**”。</span><span class="sxs-lookup"><span data-stu-id="d125b-150">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="d125b-151">若要为 IM 会话和会议启用存档，请单击“**存档 IM 和 Web 会议会话**”。</span><span class="sxs-lookup"><span data-stu-id="d125b-151">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="d125b-152">若要为策略禁用存档，请单击“**禁用存档**”。</span><span class="sxs-lookup"><span data-stu-id="d125b-152">To disable archiving for the policy, click **Disable archiving**.</span></span>
    
7. <span data-ttu-id="d125b-153">另请在“**新建存档设置**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="d125b-153">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="d125b-154">要在存档不可用时阻止活动，请选中“**存档失败时阻止即时消息 (IM) 或 Web 会议会话**”复选框。</span><span class="sxs-lookup"><span data-stu-id="d125b-154">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="d125b-155">若要使用 Microsoft Exchange Server 存储存档数据，请单击**Microsoft Exchange 集成**复选框。</span><span class="sxs-lookup"><span data-stu-id="d125b-155">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="d125b-156">若要启用数据清除，请选中“**启用存档数据清除**”复选框，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="d125b-156">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="d125b-157">要指定在特定的天数之后清除，请单击“**在最长期限（天）后清除导出的存档数据和存储的存档数据**”，然后指定天数。</span><span class="sxs-lookup"><span data-stu-id="d125b-157">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="d125b-158">要限制仅清除已导出的存档数据，请单击“**仅清除导出的存档数据**”。</span><span class="sxs-lookup"><span data-stu-id="d125b-158">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="d125b-159">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="d125b-159">Click **Commit**.</span></span>
    
## <a name="configure-pool-level-archiving-options"></a><span data-ttu-id="d125b-160">配置池级别存档选项</span><span class="sxs-lookup"><span data-stu-id="d125b-160">Configure pool level archiving options</span></span>

<span data-ttu-id="d125b-p106">您可以为特定池指定存档选项。池配置可覆盖全局配置和站点配置，但它仅适用于池配置中指定的池。</span><span class="sxs-lookup"><span data-stu-id="d125b-p106">You can specify archiving options for a specific pool. A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>
  
1. <span data-ttu-id="d125b-163">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d125b-163">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d125b-164">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="d125b-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d125b-165">在左侧导航栏中，单击“监控和存档”\*\*\*\*，然后单击“存档配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d125b-165">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="d125b-166">在“**存档配置**”页上，单击“**新建**”，然后单击“**池配置**”。</span><span class="sxs-lookup"><span data-stu-id="d125b-166">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>
    
5. <span data-ttu-id="d125b-167">在“**选择服务**”中，选择要为存档配置的池。</span><span class="sxs-lookup"><span data-stu-id="d125b-167">In **Select a Service**, select the pool to be configured for archiving.</span></span>
    
6. <span data-ttu-id="d125b-168">在“**新建存档设置**”的“**存档设置**”下拉列表中，选择下列存档选项之一：</span><span class="sxs-lookup"><span data-stu-id="d125b-168">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="d125b-169">**禁用存档**</span><span class="sxs-lookup"><span data-stu-id="d125b-169">**Disable archiving**</span></span>
    
   - <span data-ttu-id="d125b-170">**存档 IM 会话**</span><span class="sxs-lookup"><span data-stu-id="d125b-170">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="d125b-171">**存档 IM 和 Web 会议会话**</span><span class="sxs-lookup"><span data-stu-id="d125b-171">**Archive IM and web conferencing sessions**</span></span>
    
7. <span data-ttu-id="d125b-172">另请在“**新建存档设置**”页中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="d125b-172">Also in **New Archiving Setting** page, do the following:</span></span>
    
   - <span data-ttu-id="d125b-173">要在存档不可用时阻止活动，请选中“**存档失败时阻止即时消息 (IM) 或 Web 会议会话**”复选框。</span><span class="sxs-lookup"><span data-stu-id="d125b-173">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="d125b-174">若要使用 Microsoft Exchange Server 存储存档数据，请单击**Microsoft Exchange 集成**复选框。</span><span class="sxs-lookup"><span data-stu-id="d125b-174">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="d125b-175">若要启用数据清除，请选中“**启用存档数据清除**”复选框，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="d125b-175">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="d125b-176">要指定在特定的天数之后清除，请单击“**在最长期限（天）后清除导出的存档数据和存储的存档数据**”，然后指定天数。</span><span class="sxs-lookup"><span data-stu-id="d125b-176">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="d125b-177">要限制仅清除已导出的存档数据，请单击“**仅清除导出的存档数据**”。</span><span class="sxs-lookup"><span data-stu-id="d125b-177">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="d125b-178">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="d125b-178">Click **Commit**.</span></span>
    

